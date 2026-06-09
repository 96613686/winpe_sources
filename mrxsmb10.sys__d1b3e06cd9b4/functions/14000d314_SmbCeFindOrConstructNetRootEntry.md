# SmbCeFindOrConstructNetRootEntry

- ea: `0x14000d314`
- end: `0x14000d658`
- name: `SmbCeFindOrConstructNetRootEntry`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x14000ce24`

## callees

- `0x140001e40`
- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x140005c60`
- `0x14000a440`
- `0x14000cbbc`
- `0x14000d314`
- `0x14000ebd8`
- `0x1400166c0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d36e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d5d8`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d36e`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14000d5d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5be`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d5be`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d581`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000d581`
- `ntoskrnl!ExAllocatePool2` at `0x14000d40c`
- `ntoskrnl!ExAllocatePool2` at `0x14000d40c`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d4ba`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d4e1`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d508`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d52d`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d555`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d4ba`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d4e1`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d508`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d52d`
- `rdbss!RxNameCacheInitializeEx` at `0x14000d555`
- `mrxsmb!MRxSmbRemoteBootShare` at `0x14000d5ca`

## pseudocode

```c
__int64 __fastcall SmbCeFindOrConstructNetRootEntry(__int64 a1, __int64 *a2)
{
  __int64 v3; // rcx
  __int64 v5; // rax
  char *v6; // rdi
  __int64 v7; // rsi
  __int64 Object; // rbx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 Pool2; // rax
  unsigned int v12; // ecx
  KIRQL v13; // al
  _QWORD *v14; // rcx
  unsigned int v15; // ebx

  v3 = *(_QWORD *)(a1 + 32);
  *a2 = 0;
  v5 = SmbCeReferenceAssociatedServerEntry(v3);
  v6 = (char *)v5;
  if ( !v5 )
    return (unsigned int)-1073741811;
  v7 = v5 + 200;
  Object = 0;
  v9 = *(_QWORD *)(v5 + 200);
  if ( v9 != v5 + 200 )
    Object = v9 - 32;
  while ( Object )
  {
    if ( !RtlCompareUnicodeString(*(PCUNICODE_STRING *)(a1 + 88), (PCUNICODE_STRING)(Object + 88), 1u) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, Object);
      }
      MRxSmbTrackRefCount(Object, "SmbCeFindOrConstructNetRootEntry", 2268);
      _InterlockedIncrement((volatile signed __int32 *)(Object + 8));
      goto LABEL_23;
    }
    v10 = *(_QWORD *)(Object + 32);
    Object = 0;
    if ( v10 != v7 )
      Object = v10 - 32;
  }
  Object = SmbMmAllocateObject(1);
  if ( !Object )
  {
LABEL_26:
    v15 = -1073741670;
    goto LABEL_27;
  }
  Pool2 = ExAllocatePool2(258, **(unsigned __int16 **)(a1 + 88), 1917742419);
  *(_QWORD *)(Object + 96) = Pool2;
  if ( !Pool2 )
  {
    SmbMmFreeObjectPool(Object);
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, Object);
  v12 = **(unsigned __int16 **)(a1 + 88);
  *(_WORD *)(Object + 88) = v12;
  *(_WORD *)(Object + 90) = v12;
  memmove(*(void **)(Object + 96), *(const void **)(*(_QWORD *)(a1 + 88) + 8LL), v12);
  *(_QWORD *)(Object + 56) = v6;
  *(_WORD *)(Object + 108) = 0;
  *(_BYTE *)(Object + 105) = *(_BYTE *)(a1 + 77);
  *(_QWORD *)(Object + 128) = Object + 120;
  *(_QWORD *)(Object + 120) = Object + 120;
  *(_DWORD *)(Object + 12) = 0;
  RxNameCacheInitializeEx(Object + 288, 40, 200);
  RxNameCacheInitializeEx(Object + 472, 24, 200);
  RxNameCacheInitializeEx(Object + 656, 8, 200);
  RxNameCacheInitializeEx(Object + 840, 0, 200);
  RxNameCacheInitializeEx(Object + 1024, 8352, 200);
  MRxSmbTrackRefCount(Object, "SmbCeFindOrConstructNetRootEntry", 2335);
  _InterlockedIncrement((volatile signed __int32 *)(Object + 8));
  v13 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v14 = *(_QWORD **)(v7 + 8);
  s_SmbCeDbSpinLockSavedIrql = v13;
  if ( *v14 != v7 )
    __fastfail(3u);
  *(_QWORD *)(Object + 40) = v14;
  *(_QWORD *)(Object + 32) = v7;
  *v14 = Object + 32;
  *(_QWORD *)(v7 + 8) = Object + 32;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, v13);
  if ( !RtlCompareUnicodeString(*(PCUNICODE_STRING *)(a1 + 88), MRxSmbRemoteBootShare, 1u) )
    *(_BYTE *)(Object + 1232) = 1;
  v6 = 0;
LABEL_23:
  *a2 = Object;
  v15 = 0;
  if ( !v6 )
    return v15;
LABEL_27:
  MRxSmbTrackDerefCount(v6, "SmbCeFindOrConstructNetRootEntry", 2374);
  SmbReferenceRecord(v6 + 792, "SmbCeFindOrConstructNetRootEntry", 2374);
  SmbCepDereferenceServerEntry(v6);
  return v15;
}

```

## disassembly

```asm
0x14000d314  push    rbx
0x14000d316  push    rbp
0x14000d317  push    rsi
0x14000d318  push    rdi
0x14000d319  push    r14
0x14000d31b  push    r15
0x14000d31d  sub     rsp, 38h
0x14000d321  mov     rbp, rcx
0x14000d324  xor     r15d, r15d
0x14000d327  mov     rcx, [rcx+20h]
0x14000d32b  mov     r14, rdx
0x14000d32e  mov     [rdx], r15
0x14000d331  call    SmbCeReferenceAssociatedServerEntry
0x14000d336  mov     rdi, rax
0x14000d339  test    rax, rax
0x14000d33c  jz      loc_14000D643
0x14000d342  lea     rsi, [rax+0C8h]
0x14000d349  mov     ebx, r15d
0x14000d34c  mov     r8, [rsi]
0x14000d34f  cmp     r8, rsi
0x14000d352  lea     rdx, [r8-20h]
0x14000d356  cmovnz  rbx, rdx
0x14000d35a  test    rbx, rbx
0x14000d35d  jz      loc_14000D3E4
0x14000d363  mov     rcx, [rbp+58h]; String1
0x14000d367  lea     rdx, [rbx+58h]; String2
0x14000d36b  mov     r8b, 1; CaseInSensitive
0x14000d36e  call    cs:__imp_RtlCompareUnicodeString
0x14000d375  nop     dword ptr [rax+rax+00h]
0x14000d37a  test    eax, eax
0x14000d37c  jz      short loc_14000D392
0x14000d37e  mov     rcx, [rbx+20h]
0x14000d382  mov     rbx, r15
0x14000d385  cmp     rcx, rsi
0x14000d388  lea     rax, [rcx-20h]
0x14000d38c  cmovnz  rbx, rax
0x14000d390  jmp     short loc_14000D35A
0x14000d392  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d399  lea     rax, WPP_GLOBAL_Control
0x14000d3a0  cmp     rcx, rax
0x14000d3a3  jz      short loc_14000D3C6
0x14000d3a5  test    dword ptr [rcx+2Ch], 200h
0x14000d3ac  jz      short loc_14000D3C6
0x14000d3ae  mov     rcx, [rcx+18h]
0x14000d3b2  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14000d3b9  mov     edx, 20h ; ' '
0x14000d3be  mov     r9, rbx
0x14000d3c1  call    WPP_SF_q
0x14000d3c6  mov     r8d, 8DCh
0x14000d3cc  lea     rdx, aSmbcefindorcon_2; "SmbCeFindOrConstructNetRootEntry"
0x14000d3d3  mov     rcx, rbx
0x14000d3d6  call    MRxSmbTrackRefCount
0x14000d3db  lock inc dword ptr [rbx+8]
0x14000d3df  jmp     loc_14000D5F2
0x14000d3e4  mov     ecx, 1
0x14000d3e9  call    SmbMmAllocateObject
0x14000d3ee  mov     rbx, rax
0x14000d3f1  test    rax, rax
0x14000d3f4  jz      loc_14000D607
0x14000d3fa  mov     rcx, [rbp+58h]
0x14000d3fe  mov     r8d, 724E6D53h
0x14000d404  movzx   edx, word ptr [rcx]
0x14000d407  mov     ecx, 102h
0x14000d40c  call    cs:__imp_ExAllocatePool2
0x14000d413  nop     dword ptr [rax+rax+00h]
0x14000d418  mov     [rbx+60h], rax
0x14000d41c  test    rax, rax
0x14000d41f  jz      loc_14000D5FF
0x14000d425  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000d42c  lea     rax, WPP_GLOBAL_Control
0x14000d433  cmp     rcx, rax
0x14000d436  jz      short loc_14000D459
0x14000d438  test    dword ptr [rcx+2Ch], 200h
0x14000d43f  jz      short loc_14000D459
0x14000d441  mov     rcx, [rcx+18h]
0x14000d445  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14000d44c  mov     edx, 21h ; '!'
0x14000d451  mov     r9, rbx
0x14000d454  call    WPP_SF_q
0x14000d459  mov     rax, [rbp+58h]
0x14000d45d  movzx   ecx, word ptr [rax]
0x14000d460  mov     [rbx+58h], cx
0x14000d464  mov     r8d, ecx; Size
0x14000d467  mov     [rbx+5Ah], cx
0x14000d46b  mov     rdx, [rbp+58h]
0x14000d46f  mov     rcx, [rbx+60h]; void *
0x14000d473  mov     rdx, [rdx+8]; Src
0x14000d477  call    memmove
0x14000d47c  mov     [rbx+38h], rdi
0x14000d480  lea     rcx, [rbx+120h]
0x14000d487  mov     [rbx+6Ch], r15w
0x14000d48c  xor     r9d, r9d
0x14000d48f  mov     al, [rbp+4Dh]
0x14000d492  mov     edi, 0C8h
0x14000d497  mov     [rbx+69h], al
0x14000d49a  mov     r8d, edi
0x14000d49d  lea     rax, [rbx+78h]
0x14000d4a1  mov     [rsp+68h+var_40], r15
0x14000d4a6  mov     [rax+8], rax
0x14000d4aa  lea     edx, [r9+28h]
0x14000d4ae  mov     [rax], rax
0x14000d4b1  mov     [rbx+0Ch], r15d
0x14000d4b5  mov     [rsp+68h+var_48], r15
0x14000d4ba  call    cs:__imp_RxNameCacheInitializeEx
0x14000d4c1  nop     dword ptr [rax+rax+00h]
0x14000d4c6  xor     r9d, r9d
0x14000d4c9  mov     [rsp+68h+var_40], r15
0x14000d4ce  lea     rcx, [rbx+1D8h]
0x14000d4d5  mov     [rsp+68h+var_48], r15
0x14000d4da  mov     r8d, edi
0x14000d4dd  lea     edx, [r9+18h]
0x14000d4e1  call    cs:__imp_RxNameCacheInitializeEx
0x14000d4e8  nop     dword ptr [rax+rax+00h]
0x14000d4ed  xor     r9d, r9d
0x14000d4f0  mov     [rsp+68h+var_40], r15
0x14000d4f5  lea     rcx, [rbx+290h]
0x14000d4fc  mov     [rsp+68h+var_48], r15
0x14000d501  mov     r8d, edi
0x14000d504  lea     edx, [r9+8]
0x14000d508  call    cs:__imp_RxNameCacheInitializeEx
0x14000d50f  nop     dword ptr [rax+rax+00h]
0x14000d514  lea     rcx, [rbx+348h]
0x14000d51b  mov     [rsp+68h+var_40], r15
0x14000d520  xor     r9d, r9d
0x14000d523  mov     [rsp+68h+var_48], r15
0x14000d528  mov     r8d, edi
0x14000d52b  xor     edx, edx
0x14000d52d  call    cs:__imp_RxNameCacheInitializeEx
0x14000d534  nop     dword ptr [rax+rax+00h]
0x14000d539  lea     rcx, [rbx+400h]
0x14000d540  mov     [rsp+68h+var_40], r15
0x14000d545  xor     r9d, r9d
0x14000d548  mov     [rsp+68h+var_48], r15
0x14000d54d  mov     r8d, edi
0x14000d550  mov     edx, 20A0h
0x14000d555  call    cs:__imp_RxNameCacheInitializeEx
0x14000d55c  nop     dword ptr [rax+rax+00h]
0x14000d561  mov     r8d, 91Fh
0x14000d567  lea     rdx, aSmbcefindorcon_2; "SmbCeFindOrConstructNetRootEntry"
0x14000d56e  mov     rcx, rbx
0x14000d571  call    MRxSmbTrackRefCount
0x14000d576  lock inc dword ptr [rbx+8]
0x14000d57a  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000d581  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000d588  nop     dword ptr [rax+rax+00h]
0x14000d58d  mov     rcx, [rsi+8]
0x14000d591  mov     dl, al; NewIrql
0x14000d593  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000d599  cmp     [rcx], rsi
0x14000d59c  jz      short loc_14000D5A5
0x14000d59e  mov     ecx, 3
0x14000d5a3  int     29h; Win8: RtlFailFast(ecx)
0x14000d5a5  lea     rax, [rbx+20h]
0x14000d5a9  mov     [rax+8], rcx
0x14000d5ad  mov     [rax], rsi
0x14000d5b0  mov     [rcx], rax
0x14000d5b3  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000d5ba  mov     [rsi+8], rax
0x14000d5be  call    cs:__imp_KeReleaseSpinLock
0x14000d5c5  nop     dword ptr [rax+rax+00h]
0x14000d5ca  mov     rdx, cs:__imp_MRxSmbRemoteBootShare; String2
0x14000d5d1  mov     r8b, 1; CaseInSensitive
0x14000d5d4  mov     rcx, [rbp+58h]; String1
0x14000d5d8  call    cs:__imp_RtlCompareUnicodeString
0x14000d5df  nop     dword ptr [rax+rax+00h]
0x14000d5e4  test    eax, eax
0x14000d5e6  jnz     short loc_14000D5EF
0x14000d5e8  mov     byte ptr [rbx+4D0h], 1
0x14000d5ef  mov     rdi, r15
0x14000d5f2  mov     [r14], rbx
0x14000d5f5  mov     ebx, r15d
0x14000d5f8  test    rdi, rdi
0x14000d5fb  jz      short loc_14000D648
0x14000d5fd  jmp     short loc_14000D60C
0x14000d5ff  mov     rcx, rbx
0x14000d602  call    SmbMmFreeObjectPool
0x14000d607  mov     ebx, 0C000009Ah
0x14000d60c  mov     esi, 946h
0x14000d611  lea     rdx, aSmbcefindorcon_2; "SmbCeFindOrConstructNetRootEntry"
0x14000d618  mov     r8d, esi
0x14000d61b  mov     rcx, rdi
0x14000d61e  call    MRxSmbTrackDerefCount
0x14000d623  lea     rcx, [rdi+318h]
0x14000d62a  mov     r8d, esi
0x14000d62d  lea     rdx, aSmbcefindorcon_2; "SmbCeFindOrConstructNetRootEntry"
0x14000d634  call    SmbReferenceRecord
0x14000d639  mov     rcx, rdi; pContext
0x14000d63c  call    SmbCepDereferenceServerEntry
0x14000d641  jmp     short loc_14000D648
0x14000d643  mov     ebx, 0C000000Dh
0x14000d648  mov     eax, ebx
0x14000d64a  add     rsp, 38h
0x14000d64e  pop     r15
0x14000d650  pop     r14
0x14000d652  pop     rdi
0x14000d653  pop     rsi
0x14000d654  pop     rbp
0x14000d655  pop     rbx
0x14000d656  retn
```
