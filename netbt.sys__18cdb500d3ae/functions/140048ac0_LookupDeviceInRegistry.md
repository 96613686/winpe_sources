# LookupDeviceInRegistry

- ea: `0x140048ac0`
- end: `0x140048dac`
- name: `LookupDeviceInRegistry`
- size: `748`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140047630`
- `0x140047b84`
- `0x1400487cc`

## callees

- `0x1400401c4`
- `0x140040294`
- `0x140048ac0`
- `0x1400493c4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140048caf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140048caf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140048b89`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140048b89`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048ce0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048c48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140048ce0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048cd4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048c3c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048cd4`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048b04`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140048b04`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048aef`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140048aef`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d44`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048be5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048bf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048c29`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048cf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d2e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140048d44`
- `ntoskrnl!ExAllocatePool2` at `0x140048c8c`
- `ntoskrnl!ExAllocatePool2` at `0x140048c8c`

## pseudocode

```c
__int64 __fastcall LookupDeviceInRegistry(const UNICODE_STRING *a1, _OWORD *a2, struct _UNICODE_STRING *a3)
{
  int v3; // ebp
  int Registry; // eax
  PVOID *v6; // rdi
  PVOID *v7; // rbx
  char *v8; // rsi
  unsigned int v9; // r12d
  __int64 v10; // r14
  __int64 v11; // r15
  __int64 Pool2; // rax
  PVOID v14; // [rsp+30h] [rbp-48h] BYREF
  PVOID v15[8]; // [rsp+38h] [rbp-40h] BYREF
  PVOID P; // [rsp+98h] [rbp+20h] BYREF

  v3 = 0;
  P = 0;
  v14 = 0;
  v15[0] = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  Registry = NbtReadRegistry((__int64 *)&P, (__int64 *)&v14, v15);
  v6 = (PVOID *)P;
  v7 = (PVOID *)v14;
  v8 = (char *)v15[0];
  if ( Registry >= 0 && P && v14 && v15[0] )
  {
    v9 = -1073741823;
    while ( v3 < (unsigned __int16)word_140039508 )
    {
      v10 = 2LL * v3;
      if ( !RtlCompareUnicodeString(a1, (PCUNICODE_STRING)&v6[v10 + 1], 1u) )
      {
        v9 = 0;
        if ( a2 )
        {
          v11 = (__int64)v3 << 6;
          *a2 = *(_OWORD *)&v8[v11];
          a2[1] = *(_OWORD *)&v8[v11 + 16];
          a2[2] = *(_OWORD *)&v8[v11 + 32];
          a2[3] = *(_OWORD *)&v8[v11 + 48];
        }
        if ( a3 )
        {
          a3->MaximumLength = WORD1(v7[v10 + 1]);
          Pool2 = ExAllocatePool2(64, WORD1(v7[v10 + 1]), 925983310);
          a3->Buffer = (wchar_t *)Pool2;
          if ( Pool2 )
          {
            RtlCopyUnicodeString(a3, (PCUNICODE_STRING)&v7[v10 + 1]);
          }
          else
          {
            if ( (BYTE3(xmmword_140038420) & 1) != 0 )
              WPP_SF_(1048, 81, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids);
            v9 = -1073741670;
          }
        }
        break;
      }
      ++v3;
    }
    ExFreePoolWithTag(*v6, 0);
    ExFreePoolWithTag(v6, 0);
    ExFreePoolWithTag(*v7, 0);
    ExFreePoolWithTag(v7, 0);
    ExFreePoolWithTag(v8, 0);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    return v9;
  }
  else
  {
    if ( (BYTE3(xmmword_140038420) & 1) != 0 )
      WPP_SF_qqq(1048, 80, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids, P, v14, v15[0]);
    ExReleaseResourceLite(&Resource);
    KeLeaveCriticalRegion();
    if ( v6 )
    {
      ExFreePoolWithTag(*v6, 0);
      ExFreePoolWithTag(v6, 0);
    }
    if ( v7 )
    {
      ExFreePoolWithTag(*v7, 0);
      ExFreePoolWithTag(v7, 0);
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    return 3221225804LL;
  }
}

```

## disassembly

```asm
0x140048ac0  mov     rax, rsp
0x140048ac3  mov     [rax+18h], rbx
0x140048ac7  mov     [rax+10h], rdx
0x140048acb  mov     [rax+8], rcx
0x140048acf  push    rbp
0x140048ad0  push    rsi
0x140048ad1  push    rdi
0x140048ad2  push    r12
0x140048ad4  push    r13
0x140048ad6  push    r14
0x140048ad8  push    r15
0x140048ada  sub     rsp, 40h
0x140048ade  xor     ebp, ebp
0x140048ae0  mov     r13, r8
0x140048ae3  mov     [rax+20h], rbp
0x140048ae7  mov     [rax-48h], rbp
0x140048aeb  mov     [rax-40h], rbp
0x140048aef  call    cs:__imp_KeEnterCriticalRegion
0x140048af6  nop     dword ptr [rax+rax+00h]
0x140048afb  mov     dl, 1; Wait
0x140048afd  lea     rcx, Resource; Resource
0x140048b04  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140048b0b  nop     dword ptr [rax+rax+00h]
0x140048b10  lea     r8, [rsp+78h+var_40]
0x140048b15  lea     rdx, [rsp+78h+var_48]
0x140048b1a  lea     rcx, [rsp+78h+P]
0x140048b22  call    NbtReadRegistry
0x140048b27  mov     rdi, [rsp+78h+P]
0x140048b2f  mov     rbx, [rsp+78h+var_48]
0x140048b34  mov     rsi, [rsp+78h+var_40]
0x140048b39  test    eax, eax
0x140048b3b  js      loc_140048CC0
0x140048b41  test    rdi, rdi
0x140048b44  jz      loc_140048CC0
0x140048b4a  test    rbx, rbx
0x140048b4d  jz      loc_140048CC0
0x140048b53  test    rsi, rsi
0x140048b56  jz      loc_140048CC0
0x140048b5c  mov     r12d, 0C0000001h
0x140048b62  movzx   eax, cs:word_140039508
0x140048b69  cmp     ebp, eax
0x140048b6b  jge     short loc_140048BE0
0x140048b6d  mov     rcx, [rsp+78h+String1]; String1
0x140048b75  lea     rdx, [rdi+8]
0x140048b79  movsxd  r15, ebp
0x140048b7c  mov     r8b, 1; CaseInSensitive
0x140048b7f  mov     r14, r15
0x140048b82  shl     r14, 4
0x140048b86  add     rdx, r14; String2
0x140048b89  call    cs:__imp_RtlCompareUnicodeString
0x140048b90  nop     dword ptr [rax+rax+00h]
0x140048b95  test    eax, eax
0x140048b97  jz      short loc_140048B9D
0x140048b99  inc     ebp
0x140048b9b  jmp     short loc_140048B62
0x140048b9d  mov     rax, [rsp+78h+arg_8]
0x140048ba5  xor     r12d, r12d
0x140048ba8  test    rax, rax
0x140048bab  jz      short loc_140048BD7
0x140048bad  shl     r15, 6
0x140048bb1  movups  xmm0, xmmword ptr [r15+rsi]
0x140048bb6  movaps  xmmword ptr [rax], xmm0
0x140048bb9  movups  xmm1, xmmword ptr [r15+rsi+10h]
0x140048bbf  movaps  xmmword ptr [rax+10h], xmm1
0x140048bc3  movups  xmm0, xmmword ptr [r15+rsi+20h]
0x140048bc9  movaps  xmmword ptr [rax+20h], xmm0
0x140048bcd  movups  xmm1, xmmword ptr [r15+rsi+30h]
0x140048bd3  movaps  xmmword ptr [rax+30h], xmm1
0x140048bd7  test    r13, r13
0x140048bda  jnz     loc_140048C70
0x140048be0  mov     rcx, [rdi]; P
0x140048be3  xor     edx, edx; Tag
0x140048be5  call    cs:__imp_ExFreePoolWithTag
0x140048bec  nop     dword ptr [rax+rax+00h]
0x140048bf1  xor     edx, edx; Tag
0x140048bf3  mov     rcx, rdi; P
0x140048bf6  call    cs:__imp_ExFreePoolWithTag
0x140048bfd  nop     dword ptr [rax+rax+00h]
0x140048c02  mov     rcx, [rbx]; P
0x140048c05  xor     edx, edx; Tag
0x140048c07  call    cs:__imp_ExFreePoolWithTag
0x140048c0e  nop     dword ptr [rax+rax+00h]
0x140048c13  xor     edx, edx; Tag
0x140048c15  mov     rcx, rbx; P
0x140048c18  call    cs:__imp_ExFreePoolWithTag
0x140048c1f  nop     dword ptr [rax+rax+00h]
0x140048c24  xor     edx, edx; Tag
0x140048c26  mov     rcx, rsi; P
0x140048c29  call    cs:__imp_ExFreePoolWithTag
0x140048c30  nop     dword ptr [rax+rax+00h]
0x140048c35  lea     rcx, Resource; Resource
0x140048c3c  call    cs:__imp_ExReleaseResourceLite
0x140048c43  nop     dword ptr [rax+rax+00h]
0x140048c48  call    cs:__imp_KeLeaveCriticalRegion
0x140048c4f  nop     dword ptr [rax+rax+00h]
0x140048c54  mov     eax, r12d
0x140048c57  mov     rbx, [rsp+78h+arg_10]
0x140048c5f  add     rsp, 40h
0x140048c63  pop     r15
0x140048c65  pop     r14
0x140048c67  pop     r13
0x140048c69  pop     r12
0x140048c6b  pop     rdi
0x140048c6c  pop     rsi
0x140048c6d  pop     rbp
0x140048c6e  retn
0x140048c70  movzx   eax, word ptr [r14+rbx+0Ah]
0x140048c76  mov     ecx, 40h ; '@'
0x140048c7b  mov     [r13+2], ax
0x140048c80  mov     r8d, 3731624Eh
0x140048c86  movzx   edx, word ptr [r14+rbx+0Ah]
0x140048c8c  call    cs:__imp_ExAllocatePool2
0x140048c93  nop     dword ptr [rax+rax+00h]
0x140048c98  mov     [r13+8], rax
0x140048c9c  test    rax, rax
0x140048c9f  jz      loc_140048D5A
0x140048ca5  lea     rdx, [rbx+8]
0x140048ca9  mov     rcx, r13; DestinationString
0x140048cac  add     rdx, r14; SourceString
0x140048caf  call    cs:__imp_RtlCopyUnicodeString
0x140048cb6  nop     dword ptr [rax+rax+00h]
0x140048cbb  jmp     loc_140048BE0
0x140048cc0  test    byte ptr cs:xmmword_140038420+3, 1
0x140048cc7  jnz     loc_140048D84
0x140048ccd  lea     rcx, Resource; Resource
0x140048cd4  call    cs:__imp_ExReleaseResourceLite
0x140048cdb  nop     dword ptr [rax+rax+00h]
0x140048ce0  call    cs:__imp_KeLeaveCriticalRegion
0x140048ce7  nop     dword ptr [rax+rax+00h]
0x140048cec  test    rdi, rdi
0x140048cef  jz      short loc_140048D13
0x140048cf1  mov     rcx, [rdi]; P
0x140048cf4  xor     edx, edx; Tag
0x140048cf6  call    cs:__imp_ExFreePoolWithTag
0x140048cfd  nop     dword ptr [rax+rax+00h]
0x140048d02  xor     edx, edx; Tag
0x140048d04  mov     rcx, rdi; P
0x140048d07  call    cs:__imp_ExFreePoolWithTag
0x140048d0e  nop     dword ptr [rax+rax+00h]
0x140048d13  test    rbx, rbx
0x140048d16  jz      short loc_140048D3A
0x140048d18  mov     rcx, [rbx]; P
0x140048d1b  xor     edx, edx; Tag
0x140048d1d  call    cs:__imp_ExFreePoolWithTag
0x140048d24  nop     dword ptr [rax+rax+00h]
0x140048d29  xor     edx, edx; Tag
0x140048d2b  mov     rcx, rbx; P
0x140048d2e  call    cs:__imp_ExFreePoolWithTag
0x140048d35  nop     dword ptr [rax+rax+00h]
0x140048d3a  test    rsi, rsi
0x140048d3d  jz      short loc_140048D50
0x140048d3f  xor     edx, edx; Tag
0x140048d41  mov     rcx, rsi; P
0x140048d44  call    cs:__imp_ExFreePoolWithTag
0x140048d4b  nop     dword ptr [rax+rax+00h]
0x140048d50  mov     eax, 0C000014Ch
0x140048d55  jmp     loc_140048C57
0x140048d5a  test    byte ptr cs:xmmword_140038420+3, 1
0x140048d61  jz      short loc_140048D79
0x140048d63  mov     edx, 51h ; 'Q'
0x140048d68  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x140048d6f  mov     ecx, 418h
0x140048d74  call    WPP_SF_
0x140048d79  mov     r12d, 0C000009Ah
0x140048d7f  jmp     loc_140048BE0
0x140048d84  mov     edx, 50h ; 'P'
0x140048d89  mov     [rsp+78h+var_50], rsi
0x140048d8e  mov     ecx, 418h
0x140048d93  mov     [rsp+78h+var_58], rbx
0x140048d98  mov     r9, rdi
0x140048d9b  lea     r8, WPP_cc017ff6cf963b7d6adb67bc69d04f29_Traceguids
0x140048da2  call    WPP_SF_qqq
0x140048da7  jmp     loc_140048CCD
```
