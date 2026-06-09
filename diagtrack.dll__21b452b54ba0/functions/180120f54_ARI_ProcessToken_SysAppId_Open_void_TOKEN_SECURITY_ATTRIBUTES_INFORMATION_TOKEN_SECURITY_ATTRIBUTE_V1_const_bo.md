# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180120f54`
- end: `0x1801210a4`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `336`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180121414`

## callees

- `0x180120f54`
- `0x180121480`
- `0x180121500`
- `0x18020bab8`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180121034`
- `ntdll!RtlInitUnicodeString` at `0x180121034`
- `ntdll!RtlCompareUnicodeString` at `0x180121060`
- `ntdll!RtlCompareUnicodeString` at `0x180121060`
- `ntdll!NtQueryInformationToken` at `0x180120f91`
- `ntdll!NtQueryInformationToken` at `0x180121004`
- `ntdll!NtQueryInformationToken` at `0x180120f91`
- `ntdll!NtQueryInformationToken` at `0x180121004`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180120fae`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180121010`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180120fae`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180121010`

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
0x180120f54  mov     rax, rsp
0x180120f57  mov     [rax+8], rbx
0x180120f5b  mov     [rax+10h], rsi
0x180120f5f  mov     [rax+20h], r9
0x180120f63  push    rdi
0x180120f64  push    r14
0x180120f66  push    r15
0x180120f68  sub     rsp, 50h
0x180120f6c  xor     r9d, r9d; TokenInformationLength
0x180120f6f  mov     dword ptr [rax+20h], 0
0x180120f76  mov     r14, r8
0x180120f79  lea     rax, [rax+20h]
0x180120f7d  mov     r15, rdx
0x180120f80  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180120f85  xor     r8d, r8d; TokenInformation
0x180120f88  mov     rdi, rcx
0x180120f8b  lea     esi, [r9+27h]
0x180120f8f  mov     edx, esi; TokenInformationClass
0x180120f91  call    cs:__imp_NtQueryInformationToken
0x180120f97  cmp     eax, 0C0000023h
0x180120f9c  jz      short loc_180120FB9
0x180120f9e  test    eax, eax
0x180120fa0  jnz     short loc_180120FAC
0x180120fa2  mov     eax, 54Fh
0x180120fa7  jmp     loc_180121090
0x180120fac  mov     ecx, eax; Status
0x180120fae  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180120fb4  jmp     loc_180121090
0x180120fb9  mov     ecx, dword ptr [rsp+68h+Size]
0x180120fc0  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x180120fc5  mov     rbx, rax
0x180120fc8  test    rax, rax
0x180120fcb  jnz     short loc_180120FD5
0x180120fcd  lea     ebx, [rax+8]
0x180120fd0  jmp     loc_180121076
0x180120fd5  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x180120fdd  xor     edx, edx; Val
0x180120fdf  mov     rcx, rbx; void *
0x180120fe2  call    memset_0
0x180120fe7  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x180120fef  lea     rax, [rsp+68h+Size]
0x180120ff7  mov     r8, rbx; TokenInformation
0x180120ffa  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180120fff  mov     edx, esi; TokenInformationClass
0x180121001  mov     rcx, rdi; TokenHandle
0x180121004  call    cs:__imp_NtQueryInformationToken
0x18012100a  test    eax, eax
0x18012100c  jns     short loc_18012101A
0x18012100e  mov     ecx, eax; Status
0x180121010  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180121016  mov     edi, eax
0x180121018  jmp     short loc_180121086
0x18012101a  cmp     dword ptr [rbx+4], 0
0x18012101e  jbe     short loc_180121081
0x180121020  xorps   xmm0, xmm0
0x180121023  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18012102a  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18012102f  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180121034  call    cs:__imp_RtlInitUnicodeString
0x18012103a  xorps   xmm0, xmm0
0x18012103d  xor     edi, edi
0x18012103f  movups  [rsp+68h+var_28], xmm0
0x180121044  cmp     edi, [rbx+4]
0x180121047  jnb     short loc_180121081
0x180121049  mov     rax, [rbx+8]
0x18012104d  lea     rcx, [rdi+rdi*4]
0x180121051  mov     r8b, 1; CaseInsensitive
0x180121054  lea     rsi, [rax+rcx*8]
0x180121058  mov     rdx, rsi; String2
0x18012105b  lea     rcx, [rsp+68h+DestinationString]; String1
0x180121060  call    cs:__imp_RtlCompareUnicodeString
0x180121066  test    eax, eax
0x180121068  jz      short loc_18012106E
0x18012106a  inc     edi
0x18012106c  jmp     short loc_180121044
0x18012106e  mov     [r14], rsi
0x180121071  mov     [r15], rbx
0x180121074  xor     ebx, ebx
0x180121076  xor     ecx, ecx; P
0x180121078  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18012107d  mov     eax, ebx
0x18012107f  jmp     short loc_180121090
0x180121081  mov     edi, 490h
0x180121086  mov     rcx, rbx; P
0x180121089  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x18012108e  mov     eax, edi
0x180121090  mov     rbx, [rsp+68h+arg_0]
0x180121095  mov     rsi, [rsp+68h+arg_8]
0x18012109a  add     rsp, 50h
0x18012109e  pop     r15
0x1801210a0  pop     r14
0x1801210a2  pop     rdi
0x1801210a3  retn
```
