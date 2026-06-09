# CiAddDynamicCatalog

- ea: `0x1800608bc`
- end: `0x180060b75`
- name: `CiAddDynamicCatalog`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18005e420`

## callees

- `0x18000ecb4`
- `0x18001d1c0`
- `0x1800608bc`
- `0x180061108`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1800608ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1800608ed`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180060a2b`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180060a2b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180060b0f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180060b0f`
- `ntoskrnl!ExAllocatePool2` at `0x18006090c`
- `ntoskrnl!ExAllocatePool2` at `0x180060996`
- `ntoskrnl!ExAllocatePool2` at `0x18006090c`
- `ntoskrnl!ExAllocatePool2` at `0x180060996`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060b34`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060b4d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060b1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180060b1b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180060a56`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180060a6c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180060a56`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180060a6c`
- `ntoskrnl!ProbeForRead` at `0x1800609cb`
- `ntoskrnl!ProbeForRead` at `0x1800609cb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180060a9d`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180060a9d`

## pseudocode

```c
__int64 __fastcall CiAddDynamicCatalog(volatile void *a1, unsigned int a2)
{
  SIZE_T v2; // r14
  void *v3; // r15
  __int64 Pool2; // rax
  _QWORD *v5; // rsi
  HRESULT v6; // ebx
  UNICODE_STRING *v7; // r12
  unsigned __int16 *v8; // rdx
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // cx
  __int64 v11; // rax
  __int64 *i; // r14
  _QWORD *v13; // rcx
  UNICODE_STRING pusResult; // [rsp+28h] [rbp-40h] BYREF

  v2 = a2;
  if ( !a1 || a2 <= 2 )
    return 3221225476LL;
  v3 = 0;
  KeEnterCriticalRegion();
  CipTryAcquireCatalogStoreLockExclusive();
  Pool2 = ExAllocatePool2(256, 40, 1919109443);
  v5 = (_QWORD *)Pool2;
  if ( Pool2 )
  {
    *(_DWORD *)Pool2 = 26;
    v7 = (UNICODE_STRING *)(Pool2 + 8);
    *(_WORD *)(Pool2 + 8) = 0;
    v6 = ULongToUShort(v2, (USHORT *)(Pool2 + 10));
    if ( v6 < 0 )
      goto LABEL_24;
    v9 = *v8 + 116;
    v10 = v9 < 0x74u ? -1 : *v8 + 116;
    v6 = *v8 >= 0xFF8Cu ? 0x80070216 : 0;
    *v8 = v10;
    if ( v9 < 0x74u )
      goto LABEL_24;
    v11 = ExAllocatePool2(258, v10, 1919109443);
    v3 = (void *)v11;
    if ( v11 )
    {
      v5[2] = v11;
      ProbeForRead(a1, v2, 2u);
      *(_QWORD *)&pusResult.Length = 0;
      pusResult.Buffer = (PWSTR)a1;
      v6 = ULongToUShort(v2, &pusResult.MaximumLength);
      if ( v6 >= 0 )
      {
        pusResult.Length = pusResult.MaximumLength;
        v6 = RtlUnicodeStringValidateEx(&pusResult, 0);
        if ( v6 >= 0 )
        {
          RtlCopyUnicodeString(v7, &pusResult);
          if ( *(_WORD *)(v5[2] + 2 * ((unsigned __int64)v7->Length >> 1) - 2) != 92 )
            RtlAppendUnicodeStringToString(v7, &Source);
          RtlAppendUnicodeStringToString(v7, &stru_1800303E0);
          for ( i = (__int64 *)qword_180048780; i != &qword_180048780; i = (__int64 *)*i )
          {
            if ( (*(_DWORD *)(i - 3) & 0x10) != 0 && RtlEqualUnicodeString(v7, (PCUNICODE_STRING)i - 1, 1u) )
            {
              v6 = 0x40000000;
              goto LABEL_24;
            }
          }
          v13 = (_QWORD *)qword_180048788;
          if ( *(__int64 **)qword_180048788 != &qword_180048780 )
            __fastfail(3u);
          v5[3] = &qword_180048780;
          v5[4] = v13;
          *v13 = v5 + 3;
          qword_180048788 = (__int64)(v5 + 3);
          v5 = 0;
          v3 = 0;
        }
      }
      goto LABEL_24;
    }
  }
  v6 = -1073741801;
LABEL_24:
  ExReleasePushLockExclusiveEx(&g_CatalogStoreListLock, 0);
  KeLeaveCriticalRegion();
  if ( v5 )
    ExFreePoolWithTag(v5, 0x72634943u);
  if ( v3 )
    ExFreePoolWithTag(v3, 0x72634943u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800608bc  mov     [rsp+arg_8], rbx
0x1800608c1  mov     [rsp+Address], rcx
0x1800608c6  push    rsi
0x1800608c7  push    rdi
0x1800608c8  push    r12
0x1800608ca  push    r14
0x1800608cc  push    r15
0x1800608ce  sub     rsp, 40h
0x1800608d2  mov     r14d, edx
0x1800608d5  xor     edi, edi
0x1800608d7  test    rcx, rcx
0x1800608da  jz      loc_180060B5D
0x1800608e0  cmp     r14d, 2
0x1800608e4  jbe     loc_180060B5D
0x1800608ea  mov     r15d, edi
0x1800608ed  call    cs:__imp_KeEnterCriticalRegion
0x1800608f4  nop     dword ptr [rax+rax+00h]
0x1800608f9  call    CipTryAcquireCatalogStoreLockExclusive
0x1800608fe  lea     edx, [rdi+28h]
0x180060901  mov     ecx, 100h
0x180060906  mov     r8d, 72634943h
0x18006090c  call    cs:__imp_ExAllocatePool2
0x180060913  nop     dword ptr [rax+rax+00h]
0x180060918  mov     rsi, rax
0x18006091b  mov     [rsp+68h+arg_10], rax
0x180060923  test    rax, rax
0x180060926  jnz     short loc_180060932
0x180060928  mov     ebx, 0C0000017h
0x18006092d  jmp     loc_180060B06
0x180060932  mov     dword ptr [rax], 1Ah
0x180060938  lea     r12, [rax+8]
0x18006093c  mov     [r12], di
0x180060941  lea     rdx, [rax+0Ah]; pusResult
0x180060945  mov     ecx, r14d; ulOperand
0x180060948  call    ULongToUShort
0x18006094d  mov     ebx, eax
0x18006094f  test    eax, eax
0x180060951  js      loc_180060B06
0x180060957  movzx   eax, word ptr [rdx]
0x18006095a  mov     r8w, 74h ; 't'
0x18006095f  add     ax, r8w
0x180060963  cmp     ax, r8w
0x180060967  jb      short loc_18006096E
0x180060969  movzx   ecx, ax
0x18006096c  jmp     short loc_180060973
0x18006096e  mov     ecx, 0FFFFh
0x180060973  sbb     ebx, ebx
0x180060975  and     ebx, 80070216h
0x18006097b  mov     [rdx], cx
0x18006097e  cmp     ax, r8w
0x180060982  jb      loc_180060B06
0x180060988  movzx   edx, cx
0x18006098b  mov     ecx, 102h
0x180060990  mov     r8d, 72634943h
0x180060996  call    cs:__imp_ExAllocatePool2
0x18006099d  nop     dword ptr [rax+rax+00h]
0x1800609a2  mov     r15, rax
0x1800609a5  mov     [rsp+68h+arg_18], rax
0x1800609ad  test    rax, rax
0x1800609b0  jz      loc_180060928
0x1800609b6  mov     [rsi+10h], rax
0x1800609ba  mov     rdx, r14; Length
0x1800609bd  mov     r8d, 2; Alignment
0x1800609c3  mov     rbx, [rsp+68h+Address]
0x1800609c8  mov     rcx, rbx; Address
0x1800609cb  call    cs:__imp_ProbeForRead
0x1800609d2  nop     dword ptr [rax+rax+00h]
0x1800609d7  xorps   xmm0, xmm0
0x1800609da  movups  xmmword ptr [rsp+68h+pusResult.Length], xmm0
0x1800609df  mov     [rsp+68h+pusResult.Buffer], rbx
0x1800609e4  lea     rdx, [rsp+68h+pusResult.MaximumLength]; pusResult
0x1800609e9  mov     ecx, r14d; ulOperand
0x1800609ec  call    ULongToUShort
0x1800609f1  mov     ebx, eax
0x1800609f3  mov     [rsp+68h+var_48], eax
0x1800609f7  test    eax, eax
0x1800609f9  js      loc_180060B06
0x1800609ff  movzx   eax, [rsp+68h+pusResult.MaximumLength]
0x180060a04  mov     [rsp+68h+pusResult.Length], ax
0x180060a09  xor     edx, edx; dwFlags
0x180060a0b  lea     rcx, [rsp+68h+pusResult]; SourceString
0x180060a10  call    RtlUnicodeStringValidateEx
0x180060a15  mov     ebx, eax
0x180060a17  mov     [rsp+68h+var_48], eax
0x180060a1b  test    eax, eax
0x180060a1d  js      loc_180060B06
0x180060a23  lea     rdx, [rsp+68h+pusResult]; SourceString
0x180060a28  mov     rcx, r12; DestinationString
0x180060a2b  call    cs:__imp_RtlCopyUnicodeString
0x180060a32  nop     dword ptr [rax+rax+00h]
0x180060a37  nop
0x180060a38  movzx   ecx, word ptr [r12]
0x180060a3d  shr     rcx, 1
0x180060a40  mov     rax, [rsi+10h]
0x180060a44  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x180060a4a  jz      short loc_180060A62
0x180060a4c  lea     rdx, Source; Source
0x180060a53  mov     rcx, r12; Destination
0x180060a56  call    cs:__imp_RtlAppendUnicodeStringToString
0x180060a5d  nop     dword ptr [rax+rax+00h]
0x180060a62  lea     rdx, stru_1800303E0; Source
0x180060a69  mov     rcx, r12; Destination
0x180060a6c  call    cs:__imp_RtlAppendUnicodeStringToString
0x180060a73  nop     dword ptr [rax+rax+00h]
0x180060a78  mov     r14, cs:qword_180048780
0x180060a7f  lea     rdx, qword_180048780
0x180060a86  cmp     r14, rdx
0x180060a89  jz      short loc_180060AC0
0x180060a8b  mov     eax, [r14-18h]
0x180060a8f  test    al, 10h
0x180060a91  jz      short loc_180060AB4
0x180060a93  lea     rdx, [r14-10h]; String2
0x180060a97  mov     r8b, 1; CaseInSensitive
0x180060a9a  mov     rcx, r12; String1
0x180060a9d  call    cs:__imp_RtlEqualUnicodeString
0x180060aa4  nop     dword ptr [rax+rax+00h]
0x180060aa9  test    al, al
0x180060aab  jnz     short loc_180060AB9
0x180060aad  lea     rdx, qword_180048780
0x180060ab4  mov     r14, [r14]
0x180060ab7  jmp     short loc_180060A86
0x180060ab9  mov     ebx, 40000000h
0x180060abe  jmp     short loc_180060B06
0x180060ac0  mov     rcx, cs:qword_180048788
0x180060ac7  cmp     [rcx], rdx
0x180060aca  jz      short loc_180060AD3
0x180060acc  mov     ecx, 3
0x180060ad1  int     29h; Win8: RtlFailFast(ecx)
0x180060ad3  lea     rax, [rsi+18h]
0x180060ad7  mov     [rax], rdx
0x180060ada  mov     [rax+8], rcx
0x180060ade  mov     [rcx], rax
0x180060ae1  mov     cs:qword_180048788, rax
0x180060ae8  mov     rsi, rdi
0x180060aeb  mov     r15, rdi
0x180060aee  jmp     short loc_180060B06
0x180060af0  mov     ebx, eax
0x180060af2  mov     [rsp+68h+var_48], eax
0x180060af6  mov     rsi, [rsp+68h+arg_10]
0x180060afe  mov     r15, [rsp+68h+arg_18]
0x180060b06  xor     edx, edx
0x180060b08  lea     rcx, g_CatalogStoreListLock
0x180060b0f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x180060b16  nop     dword ptr [rax+rax+00h]
0x180060b1b  call    cs:__imp_KeLeaveCriticalRegion
0x180060b22  nop     dword ptr [rax+rax+00h]
0x180060b27  test    rsi, rsi
0x180060b2a  jz      short loc_180060B40
0x180060b2c  mov     edx, 72634943h; Tag
0x180060b31  mov     rcx, rsi; P
0x180060b34  call    cs:__imp_ExFreePoolWithTag
0x180060b3b  nop     dword ptr [rax+rax+00h]
0x180060b40  test    r15, r15
0x180060b43  jz      short loc_180060B59
0x180060b45  mov     edx, 72634943h; Tag
0x180060b4a  mov     rcx, r15; P
0x180060b4d  call    cs:__imp_ExFreePoolWithTag
0x180060b54  nop     dword ptr [rax+rax+00h]
0x180060b59  mov     eax, ebx
0x180060b5b  jmp     short loc_180060B62
0x180060b5d  mov     eax, 0C0000004h
0x180060b62  mov     rbx, [rsp+68h+arg_8]
0x180060b67  add     rsp, 40h
0x180060b6b  pop     r15
0x180060b6d  pop     r14
0x180060b6f  pop     r12
0x180060b71  pop     rdi
0x180060b72  pop     rsi
0x180060b73  retn
```
