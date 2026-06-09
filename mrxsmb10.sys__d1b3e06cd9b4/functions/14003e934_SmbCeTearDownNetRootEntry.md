# SmbCeTearDownNetRootEntry

- ea: `0x14003e934`
- end: `0x14003ea67`
- name: `SmbCeTearDownNetRootEntry`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400122a8`

## callees

- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x14000cd90`
- `0x14000ebd8`
- `0x14003e934`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea41`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ea41`
- `rdbss!RxNameCacheFinalize` at `0x14003e9bc`
- `rdbss!RxNameCacheFinalize` at `0x14003e9cf`
- `rdbss!RxNameCacheFinalize` at `0x14003e9e2`
- `rdbss!RxNameCacheFinalize` at `0x14003e9f5`
- `rdbss!RxNameCacheFinalize` at `0x14003ea08`
- `rdbss!RxNameCacheFinalize` at `0x14003e9bc`
- `rdbss!RxNameCacheFinalize` at `0x14003e9cf`
- `rdbss!RxNameCacheFinalize` at `0x14003e9e2`
- `rdbss!RxNameCacheFinalize` at `0x14003e9f5`
- `rdbss!RxNameCacheFinalize` at `0x14003ea08`

## pseudocode

```c
__int64 __fastcall SmbCeTearDownNetRootEntry(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids, a1);
  MRxSmbTrackDerefCount(*(_QWORD *)(a1 + 56), "SmbCeTearDownNetRootEntry", 2476);
  SmbReferenceRecord(*(_QWORD *)(a1 + 56) + 792LL, "SmbCeTearDownNetRootEntry", 2476);
  SmbCepDereferenceServerEntry(*(PVOID *)(a1 + 56));
  *(_QWORD *)(a1 + 56) = 0;
  RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 288));
  RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 472));
  RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 656));
  RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 840));
  RxNameCacheFinalize((PNAME_CACHE_CONTROL)(a1 + 1024));
  v2 = *(void **)(a1 + 96);
  if ( v2 )
  {
    ExFreePoolWithTag(v2, 0);
    *(_QWORD *)(a1 + 96) = 0;
  }
  v3 = *(void **)(a1 + 1208);
  if ( v3 )
  {
    ExFreePoolWithTag(v3, 0);
    *(_QWORD *)(a1 + 1208) = 0;
  }
  return SmbMmFreeObject(a1);
}

```

## disassembly

```asm
0x14003e934  push    rbx
0x14003e936  sub     rsp, 20h
0x14003e93a  mov     rbx, rcx
0x14003e93d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003e944  lea     rax, WPP_GLOBAL_Control
0x14003e94b  cmp     rcx, rax
0x14003e94e  jz      short loc_14003E971
0x14003e950  test    dword ptr [rcx+2Ch], 200h
0x14003e957  jz      short loc_14003E971
0x14003e959  mov     rcx, [rcx+18h]
0x14003e95d  lea     r8, WPP_dc77a1bfe1f333f3a4c6c4eeb4778daa_Traceguids
0x14003e964  mov     edx, 22h ; '"'
0x14003e969  mov     r9, rbx
0x14003e96c  call    WPP_SF_q
0x14003e971  mov     rcx, [rbx+38h]
0x14003e975  lea     rdx, aSmbceteardownn; "SmbCeTearDownNetRootEntry"
0x14003e97c  mov     r8d, 9ACh
0x14003e982  call    MRxSmbTrackDerefCount
0x14003e987  mov     rcx, [rbx+38h]
0x14003e98b  lea     rdx, aSmbceteardownn; "SmbCeTearDownNetRootEntry"
0x14003e992  add     rcx, 318h
0x14003e999  mov     r8d, 9ACh
0x14003e99f  call    SmbReferenceRecord
0x14003e9a4  mov     rcx, [rbx+38h]; pContext
0x14003e9a8  call    SmbCepDereferenceServerEntry
0x14003e9ad  lea     rcx, [rbx+120h]; NameCacheCtl
0x14003e9b4  mov     qword ptr [rbx+38h], 0
0x14003e9bc  call    cs:__imp_RxNameCacheFinalize
0x14003e9c3  nop     dword ptr [rax+rax+00h]
0x14003e9c8  lea     rcx, [rbx+1D8h]; NameCacheCtl
0x14003e9cf  call    cs:__imp_RxNameCacheFinalize
0x14003e9d6  nop     dword ptr [rax+rax+00h]
0x14003e9db  lea     rcx, [rbx+290h]; NameCacheCtl
0x14003e9e2  call    cs:__imp_RxNameCacheFinalize
0x14003e9e9  nop     dword ptr [rax+rax+00h]
0x14003e9ee  lea     rcx, [rbx+348h]; NameCacheCtl
0x14003e9f5  call    cs:__imp_RxNameCacheFinalize
0x14003e9fc  nop     dword ptr [rax+rax+00h]
0x14003ea01  lea     rcx, [rbx+400h]; NameCacheCtl
0x14003ea08  call    cs:__imp_RxNameCacheFinalize
0x14003ea0f  nop     dword ptr [rax+rax+00h]
0x14003ea14  mov     rcx, [rbx+60h]; P
0x14003ea18  test    rcx, rcx
0x14003ea1b  jz      short loc_14003EA33
0x14003ea1d  xor     edx, edx; Tag
0x14003ea1f  call    cs:__imp_ExFreePoolWithTag
0x14003ea26  nop     dword ptr [rax+rax+00h]
0x14003ea2b  mov     qword ptr [rbx+60h], 0
0x14003ea33  mov     rcx, [rbx+4B8h]; P
0x14003ea3a  test    rcx, rcx
0x14003ea3d  jz      short loc_14003EA58
0x14003ea3f  xor     edx, edx; Tag
0x14003ea41  call    cs:__imp_ExFreePoolWithTag
0x14003ea48  nop     dword ptr [rax+rax+00h]
0x14003ea4d  mov     qword ptr [rbx+4B8h], 0
0x14003ea58  mov     rcx, rbx
0x14003ea5b  call    SmbMmFreeObject
0x14003ea60  add     rsp, 20h
0x14003ea64  pop     rbx
0x14003ea65  retn
```
