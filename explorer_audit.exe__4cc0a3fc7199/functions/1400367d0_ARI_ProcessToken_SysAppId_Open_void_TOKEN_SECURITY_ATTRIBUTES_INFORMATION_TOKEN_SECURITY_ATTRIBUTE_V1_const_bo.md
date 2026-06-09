# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1400367d0`
- end: `0x140036920`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140036610`

## callees

- `0x1400367d0`
- `0x140036928`
- `0x140036960`
- `0x140104ce0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1400368b0`
- `ntdll!RtlInitUnicodeString` at `0x1400368b0`
- `ntdll!RtlCompareUnicodeString` at `0x1400368dc`
- `ntdll!RtlCompareUnicodeString` at `0x1400368dc`
- `ntdll!NtQueryInformationToken` at `0x14003680d`
- `ntdll!NtQueryInformationToken` at `0x140036880`
- `ntdll!NtQueryInformationToken` at `0x14003680d`
- `ntdll!NtQueryInformationToken` at `0x140036880`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003682a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003688c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003682a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14003688c`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  void *v9; // rax
  void *v10; // rdx
  void *v11; // rbx
  int v12; // ebx
  int v13; // eax
  ULONG v14; // edi
  __int64 v15; // rdi
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v16; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-38h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h]
  ULONG Size; // [rsp+88h] [rbp+20h] BYREF
  int Size_4; // [rsp+8Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    v9 = (void *)ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(Size);
    v11 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, Size);
      v13 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v11, Size, &Size);
      if ( v13 >= 0 )
      {
        if ( *((_DWORD *)v11 + 1) )
        {
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          v15 = 0;
          v18 = 0;
          while ( (unsigned int)v15 < *((_DWORD *)v11 + 1) )
          {
            v16 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(*((_QWORD *)v11 + 1) + 40 * v15);
            if ( !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)v16, 1u) )
            {
              *a3 = v16;
              *a2 = v11;
              v12 = 0;
              goto LABEL_15;
            }
            v15 = (unsigned int)(v15 + 1);
          }
        }
        v14 = 1168;
      }
      else
      {
        v14 = RtlNtStatusToDosErrorNoTeb(v13);
      }
      ARI::Free(v11, v10);
      return v14;
    }
    else
    {
      v12 = 8;
LABEL_15:
      ARI::Free(0, v10);
      return v12;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1400367d0  mov     rax, rsp
0x1400367d3  mov     [rax+8], rbx
0x1400367d7  mov     [rax+10h], rsi
0x1400367db  mov     [rax+20h], r9
0x1400367df  push    rdi
0x1400367e0  push    r14
0x1400367e2  push    r15
0x1400367e4  sub     rsp, 50h
0x1400367e8  xor     r9d, r9d; TokenInformationLength
0x1400367eb  mov     dword ptr [rax+20h], 0
0x1400367f2  mov     r14, r8
0x1400367f5  lea     rax, [rax+20h]
0x1400367f9  mov     r15, rdx
0x1400367fc  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140036801  xor     r8d, r8d; TokenInformation
0x140036804  mov     rdi, rcx
0x140036807  lea     esi, [r9+27h]
0x14003680b  mov     edx, esi; TokenInformationClass
0x14003680d  call    cs:__imp_NtQueryInformationToken
0x140036813  cmp     eax, 0C0000023h
0x140036818  jz      short loc_140036835
0x14003681a  test    eax, eax
0x14003681c  jnz     short loc_140036828
0x14003681e  mov     eax, 54Fh
0x140036823  jmp     loc_14003690C
0x140036828  mov     ecx, eax; Status
0x14003682a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140036830  jmp     loc_14003690C
0x140036835  mov     ecx, dword ptr [rsp+68h+Size]
0x14003683c  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x140036841  mov     rbx, rax
0x140036844  test    rax, rax
0x140036847  jnz     short loc_140036851
0x140036849  lea     ebx, [rax+8]
0x14003684c  jmp     loc_1400368F2
0x140036851  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x140036859  xor     edx, edx; Val
0x14003685b  mov     rcx, rbx; void *
0x14003685e  call    memset_0
0x140036863  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x14003686b  lea     rax, [rsp+68h+Size]
0x140036873  mov     r8, rbx; TokenInformation
0x140036876  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x14003687b  mov     edx, esi; TokenInformationClass
0x14003687d  mov     rcx, rdi; TokenHandle
0x140036880  call    cs:__imp_NtQueryInformationToken
0x140036886  test    eax, eax
0x140036888  jns     short loc_140036896
0x14003688a  mov     ecx, eax; Status
0x14003688c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140036892  mov     edi, eax
0x140036894  jmp     short loc_140036902
0x140036896  cmp     dword ptr [rbx+4], 0
0x14003689a  jbe     short loc_1400368FD
0x14003689c  xorps   xmm0, xmm0
0x14003689f  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1400368a6  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x1400368ab  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x1400368b0  call    cs:__imp_RtlInitUnicodeString
0x1400368b6  xorps   xmm0, xmm0
0x1400368b9  xor     edi, edi
0x1400368bb  movups  [rsp+68h+var_28], xmm0
0x1400368c0  cmp     edi, [rbx+4]
0x1400368c3  jnb     short loc_1400368FD
0x1400368c5  mov     rax, [rbx+8]
0x1400368c9  lea     rcx, [rdi+rdi*4]
0x1400368cd  mov     r8b, 1; CaseInsensitive
0x1400368d0  lea     rsi, [rax+rcx*8]
0x1400368d4  mov     rdx, rsi; String2
0x1400368d7  lea     rcx, [rsp+68h+DestinationString]; String1
0x1400368dc  call    cs:__imp_RtlCompareUnicodeString
0x1400368e2  test    eax, eax
0x1400368e4  jz      short loc_1400368EA
0x1400368e6  inc     edi
0x1400368e8  jmp     short loc_1400368C0
0x1400368ea  mov     [r14], rsi
0x1400368ed  mov     [r15], rbx
0x1400368f0  xor     ebx, ebx
0x1400368f2  xor     ecx, ecx; P
0x1400368f4  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1400368f9  mov     eax, ebx
0x1400368fb  jmp     short loc_14003690C
0x1400368fd  mov     edi, 490h
0x140036902  mov     rcx, rbx; P
0x140036905  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x14003690a  mov     eax, edi
0x14003690c  mov     rbx, [rsp+68h+arg_0]
0x140036911  mov     rsi, [rsp+68h+arg_8]
0x140036916  add     rsp, 50h
0x14003691a  pop     r15
0x14003691c  pop     r14
0x14003691e  pop     rdi
0x14003691f  retn
```
