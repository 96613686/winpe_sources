# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x180019070`
- end: `0x1800192d0`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `608`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800038d0`
- `0x180003e18`

## callees

- `0x180019070`
- `0x1800192d8`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800191ae`
- `ntdll!RtlInitUnicodeString` at `0x1800191d3`
- `ntdll!RtlInitUnicodeString` at `0x1800191ae`
- `ntdll!RtlInitUnicodeString` at `0x1800191d3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800192a1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199dba`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800192a1`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199dba`
- `ntdll!NtQueryInformationToken` at `0x1800190b2`
- `ntdll!NtQueryInformationToken` at `0x180019163`
- `ntdll!NtQueryInformationToken` at `0x1800190b2`
- `ntdll!NtQueryInformationToken` at `0x180019163`
- `ntdll!RtlCompareUnicodeString` at `0x180019204`
- `ntdll!RtlCompareUnicodeString` at `0x180019224`
- `ntdll!RtlCompareUnicodeString` at `0x180019204`
- `ntdll!RtlCompareUnicodeString` at `0x180019224`
- `ntdll!RtlFreeHeap` at `0x18001924a`
- `ntdll!RtlFreeHeap` at `0x18001924a`
- `ntdll!RtlAllocateHeap` at `0x18001911d`
- `ntdll!RtlAllocateHeap` at `0x18001911d`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v8; // eax
  PVOID Heap; // rax
  PVOID v11; // rbx
  int v12; // eax
  char v13; // r15
  bool v14; // r14
  unsigned int v15; // edi
  __int64 v16; // rax
  struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *v17; // rbp
  ULONG v18; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-38h] BYREF
  ULONG TokenInformationLength; // [rsp+98h] [rbp+20h] BYREF

  if ( a4 )
    *(_BYTE *)a4 = 0;
  TokenInformationLength = 0;
  v8 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v8 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(TokenInformationLength, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v11 = Heap) != 0) )
    {
      memset_0(Heap, 0, TokenInformationLength);
      v12 = NtQueryInformationToken(
              TokenHandle,
              TokenSecurityAttributes,
              v11,
              TokenInformationLength,
              &TokenInformationLength);
      if ( v12 < 0 )
      {
        v18 = RtlNtStatusToDosErrorNoTeb(v12);
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v11);
        return v18;
      }
      else
      {
        if ( *((_DWORD *)v11 + 1) )
        {
          v13 = 1;
          v14 = a4 != 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          String1 = 0;
          if ( a4 )
            RtlInitUnicodeString(&String1, L"WIN://PKG");
          v15 = 0;
          while ( v15 < *((_DWORD *)v11 + 1) )
          {
            v16 = *((_QWORD *)v11 + 1);
            v17 = (struct _TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)(v16 + 40LL * v15);
            if ( v13 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v16 + 40LL * v15), 1u) )
            {
              *a3 = v17;
              if ( !v14 )
                goto LABEL_24;
              v13 = 0;
              ++v15;
            }
            else
            {
              if ( v14 && !RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)v17, 1u) )
              {
                *(_BYTE *)a4 = 1;
                if ( !v13 )
                {
LABEL_24:
                  *a2 = v11;
                  AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                  return 0;
                }
                v14 = 0;
              }
              ++v15;
            }
          }
        }
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
        return 1168;
      }
    }
    else
    {
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
      return 8;
    }
  }
  else if ( v8 )
  {
    return RtlNtStatusToDosErrorNoTeb(v8);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x180019070  push    rbp
0x180019072  push    rsi
0x180019073  push    rdi
0x180019074  push    r12
0x180019076  push    r13
0x180019078  sub     rsp, 50h
0x18001907c  mov     rsi, r9
0x18001907f  mov     r13, r8
0x180019082  mov     r12, rdx
0x180019085  mov     rdi, rcx
0x180019088  test    r9, r9
0x18001908b  jz      short loc_180019091
0x18001908d  mov     byte ptr [r9], 0
0x180019091  lea     rax, [rsp+78h+TokenInformationLength]
0x180019099  xor     ebp, ebp
0x18001909b  xor     r9d, r9d; TokenInformationLength
0x18001909e  mov     [rsp+78h+TokenInformationLength], ebp
0x1800190a5  xor     r8d, r8d; TokenInformation
0x1800190a8  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800190ad  mov     edx, 27h ; '''; TokenInformationClass
0x1800190b2  call    cs:__imp_NtQueryInformationToken
0x1800190b9  nop     dword ptr [rax+rax+00h]
0x1800190be  cmp     eax, 0C0000023h
0x1800190c3  jnz     loc_1800192BE
0x1800190c9  mov     ecx, [rsp+78h+TokenInformationLength]
0x1800190d0  mov     eax, 10h
0x1800190d5  mul     rcx
0x1800190d8  mov     [rsp+78h+arg_0], rbx
0x1800190e0  mov     qword ptr [rsp+78h+DestinationString.Length], rbp
0x1800190e5  test    rdx, rdx
0x1800190e8  jz      short loc_18001910B
0x1800190ea  xor     ecx, ecx; P
0x1800190ec  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800190f1  mov     eax, 8
0x1800190f6  mov     rbx, [rsp+78h+arg_0]
0x1800190fe  add     rsp, 50h
0x180019102  pop     r13
0x180019104  pop     r12
0x180019106  pop     rdi
0x180019107  pop     rsi
0x180019108  pop     rbp
0x180019109  retn
0x18001910b  mov     rcx, gs:60h
0x180019114  mov     r8, rax; Size
0x180019117  xor     edx, edx; Flags
0x180019119  mov     rcx, [rcx+30h]; HeapHandle
0x18001911d  call    cs:__imp_RtlAllocateHeap
0x180019124  nop     dword ptr [rax+rax+00h]
0x180019129  mov     rbx, rax
0x18001912c  test    rax, rax
0x18001912f  jz      short loc_1800190EA
0x180019131  mov     r8d, [rsp+78h+TokenInformationLength]; Size
0x180019139  xor     edx, edx; Val
0x18001913b  mov     rcx, rax; void *
0x18001913e  call    memset_0
0x180019143  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18001914b  lea     rax, [rsp+78h+TokenInformationLength]
0x180019153  mov     r8, rbx; TokenInformation
0x180019156  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18001915b  mov     edx, 27h ; '''; TokenInformationClass
0x180019160  mov     rcx, rdi; TokenHandle
0x180019163  call    cs:__imp_NtQueryInformationToken
0x18001916a  nop     dword ptr [rax+rax+00h]
0x18001916f  test    eax, eax
0x180019171  js      loc_18001929F
0x180019177  mov     [rsp+78h+arg_8], r14
0x18001917f  mov     [rsp+78h+arg_10], r15
0x180019187  cmp     [rbx+4], ebp
0x18001918a  jbe     loc_180019238
0x180019190  xorps   xmm0, xmm0
0x180019193  lea     rdx, SourceString; "WIN://SYSAPPID"
0x18001919a  test    rsi, rsi
0x18001919d  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800191a2  mov     r15b, 1
0x1800191a5  setnz   r14b
0x1800191a9  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800191ae  call    cs:__imp_RtlInitUnicodeString
0x1800191b5  nop     dword ptr [rax+rax+00h]
0x1800191ba  xorps   xmm0, xmm0
0x1800191bd  movups  xmmword ptr [rsp+78h+String1.Length], xmm0
0x1800191c2  test    rsi, rsi
0x1800191c5  jz      short loc_1800191DF
0x1800191c7  lea     rdx, aWinPkg; "WIN://PKG"
0x1800191ce  lea     rcx, [rsp+78h+String1]; DestinationString
0x1800191d3  call    cs:__imp_RtlInitUnicodeString
0x1800191da  nop     dword ptr [rax+rax+00h]
0x1800191df  mov     edi, ebp
0x1800191e1  cmp     edi, [rbx+4]
0x1800191e4  jnb     short loc_180019238
0x1800191e6  mov     eax, edi
0x1800191e8  lea     rcx, [rax+rax*4]
0x1800191ec  mov     rax, [rbx+8]
0x1800191f0  lea     rbp, [rax+rcx*8]
0x1800191f4  test    r15b, r15b
0x1800191f7  jz      short loc_180019214
0x1800191f9  mov     r8b, 1; CaseInsensitive
0x1800191fc  lea     rcx, [rsp+78h+DestinationString]; String1
0x180019201  mov     rdx, rbp; String2
0x180019204  call    cs:__imp_RtlCompareUnicodeString
0x18001920b  nop     dword ptr [rax+rax+00h]
0x180019210  test    eax, eax
0x180019212  jz      short loc_180019270
0x180019214  test    r14b, r14b
0x180019217  jz      short loc_180019234
0x180019219  mov     r8b, 1; CaseInsensitive
0x18001921c  lea     rcx, [rsp+78h+String1]; String1
0x180019221  mov     rdx, rbp; String2
0x180019224  call    cs:__imp_RtlCompareUnicodeString
0x18001922b  nop     dword ptr [rax+rax+00h]
0x180019230  test    eax, eax
0x180019232  jz      short loc_180019283
0x180019234  inc     edi
0x180019236  jmp     short loc_1800191E1
0x180019238  mov     rcx, gs:60h
0x180019241  mov     r8, rbx; P
0x180019244  xor     edx, edx; Flags
0x180019246  mov     rcx, [rcx+30h]; HeapHandle
0x18001924a  call    cs:__imp_RtlFreeHeap
0x180019251  nop     dword ptr [rax+rax+00h]
0x180019256  mov     eax, 490h
0x18001925b  mov     r14, [rsp+78h+arg_8]
0x180019263  mov     r15, [rsp+78h+arg_10]
0x18001926b  jmp     loc_1800190F6
0x180019270  mov     [r13+0], rbp
0x180019274  test    r14b, r14b
0x180019277  jz      short loc_18001928B
0x180019279  xor     r15b, r15b
0x18001927c  inc     edi
0x18001927e  jmp     loc_1800191E1
0x180019283  mov     byte ptr [rsi], 1
0x180019286  test    r15b, r15b
0x180019289  jnz     short loc_18001929A
0x18001928b  xor     ecx, ecx; P
0x18001928d  mov     [r12], rbx
0x180019291  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180019296  xor     eax, eax
0x180019298  jmp     short loc_18001925B
0x18001929a  xor     r14b, r14b
0x18001929d  jmp     short loc_180019234
0x18001929f  mov     ecx, eax; Status
0x1800192a1  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800192a8  nop     dword ptr [rax+rax+00h]
0x1800192ad  mov     rcx, rbx; P
0x1800192b0  mov     edi, eax
0x1800192b2  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800192b7  mov     eax, edi
0x1800192b9  jmp     loc_1800190F6
0x1800192be  test    eax, eax
0x1800192c0  jnz     loc_180199DB8
0x1800192c6  mov     eax, 54Fh
0x1800192cb  jmp     loc_1800190FE
0x180199db8  mov     ecx, eax; Status
0x180199dba  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180199dc1  nop     dword ptr [rax+rax+00h]
0x180199dc6  nop
0x180199dc7  jmp     loc_1800190FE
```
