# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x140028f90`
- end: `0x140029105`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `373`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140028da8`

## callees

- `0x140028f90`
- `0x14002910c`
- `0x140029148`
- `0x14010ed90`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x140029088`
- `ntdll!RtlInitUnicodeString` at `0x140029088`
- `ntdll!RtlCompareUnicodeString` at `0x1400290ba`
- `ntdll!RtlCompareUnicodeString` at `0x1400290ba`
- `ntdll!NtQueryInformationToken` at `0x140028fcd`
- `ntdll!NtQueryInformationToken` at `0x14002904c`
- `ntdll!NtQueryInformationToken` at `0x140028fcd`
- `ntdll!NtQueryInformationToken` at `0x14002904c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140028ff0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14002905e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x140028ff0`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x14002905e`

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
0x140028f90  mov     rax, rsp
0x140028f93  mov     [rax+8], rbx
0x140028f97  mov     [rax+10h], rsi
0x140028f9b  mov     [rax+20h], r9
0x140028f9f  push    rdi
0x140028fa0  push    r14
0x140028fa2  push    r15
0x140028fa4  sub     rsp, 50h
0x140028fa8  xor     r9d, r9d; TokenInformationLength
0x140028fab  mov     dword ptr [rax+20h], 0
0x140028fb2  mov     r14, r8
0x140028fb5  lea     rax, [rax+20h]
0x140028fb9  mov     r15, rdx
0x140028fbc  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140028fc1  xor     r8d, r8d; TokenInformation
0x140028fc4  mov     rdi, rcx
0x140028fc7  lea     esi, [r9+27h]
0x140028fcb  mov     edx, esi; TokenInformationClass
0x140028fcd  call    cs:__imp_NtQueryInformationToken
0x140028fd4  nop     dword ptr [rax+rax+00h]
0x140028fd9  cmp     eax, 0C0000023h
0x140028fde  jz      short loc_140029001
0x140028fe0  test    eax, eax
0x140028fe2  jnz     short loc_140028FEE
0x140028fe4  mov     eax, 54Fh
0x140028fe9  jmp     loc_1400290F0
0x140028fee  mov     ecx, eax; Status
0x140028ff0  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140028ff7  nop     dword ptr [rax+rax+00h]
0x140028ffc  jmp     loc_1400290F0
0x140029001  mov     ecx, dword ptr [rsp+68h+Size]
0x140029008  call    ??$Allocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@_K@Z; ARI::Allocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(unsigned __int64)
0x14002900d  mov     rbx, rax
0x140029010  test    rax, rax
0x140029013  jnz     short loc_14002901D
0x140029015  lea     ebx, [rax+8]
0x140029018  jmp     loc_1400290D6
0x14002901d  mov     r8d, dword ptr [rsp+68h+Size]; Size
0x140029025  xor     edx, edx; Val
0x140029027  mov     rcx, rbx; void *
0x14002902a  call    memset_0
0x14002902f  mov     r9d, dword ptr [rsp+68h+Size]; TokenInformationLength
0x140029037  lea     rax, [rsp+68h+Size]
0x14002903f  mov     r8, rbx; TokenInformation
0x140029042  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x140029047  mov     edx, esi; TokenInformationClass
0x140029049  mov     rcx, rdi; TokenHandle
0x14002904c  call    cs:__imp_NtQueryInformationToken
0x140029053  nop     dword ptr [rax+rax+00h]
0x140029058  test    eax, eax
0x14002905a  jns     short loc_14002906E
0x14002905c  mov     ecx, eax; Status
0x14002905e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x140029065  nop     dword ptr [rax+rax+00h]
0x14002906a  mov     edi, eax
0x14002906c  jmp     short loc_1400290E6
0x14002906e  cmp     dword ptr [rbx+4], 0
0x140029072  jbe     short loc_1400290E1
0x140029074  xorps   xmm0, xmm0
0x140029077  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x14002907e  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x140029083  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x140029088  call    cs:__imp_RtlInitUnicodeString
0x14002908f  nop     dword ptr [rax+rax+00h]
0x140029094  xorps   xmm0, xmm0
0x140029097  xor     edi, edi
0x140029099  movups  [rsp+68h+var_28], xmm0
0x14002909e  cmp     edi, [rbx+4]
0x1400290a1  jnb     short loc_1400290E1
0x1400290a3  mov     rax, [rbx+8]
0x1400290a7  lea     rcx, [rdi+rdi*4]
0x1400290ab  mov     r8b, 1; CaseInsensitive
0x1400290ae  lea     rsi, [rax+rcx*8]
0x1400290b2  mov     rdx, rsi; String2
0x1400290b5  lea     rcx, [rsp+68h+DestinationString]; String1
0x1400290ba  call    cs:__imp_RtlCompareUnicodeString
0x1400290c1  nop     dword ptr [rax+rax+00h]
0x1400290c6  test    eax, eax
0x1400290c8  jz      short loc_1400290CE
0x1400290ca  inc     edi
0x1400290cc  jmp     short loc_14002909E
0x1400290ce  mov     [r14], rsi
0x1400290d1  mov     [r15], rbx
0x1400290d4  xor     ebx, ebx
0x1400290d6  xor     ecx, ecx; P
0x1400290d8  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1400290dd  mov     eax, ebx
0x1400290df  jmp     short loc_1400290F0
0x1400290e1  mov     edi, 490h
0x1400290e6  mov     rcx, rbx; P
0x1400290e9  call    ?Free@ARI@@YAXPEAX@Z; ARI::Free(void *)
0x1400290ee  mov     eax, edi
0x1400290f0  mov     rbx, [rsp+68h+arg_0]
0x1400290f5  mov     rsi, [rsp+68h+arg_8]
0x1400290fa  add     rsp, 50h
0x1400290fe  pop     r15
0x140029100  pop     r14
0x140029102  pop     rdi
0x140029103  retn
```
