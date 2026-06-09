# Smb2InvalidateContainingDirInfoCacheEx

- ea: `0x140028ba0`
- end: `0x140028cae`
- name: `Smb2InvalidateContainingDirInfoCacheEx`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002f280`

## callees

- `0x140028ba0`
- `0x140029c14`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028c96`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140028c96`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028bed`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140028bed`
- `rdbss!RxNameCacheExpireEntry` at `0x140028c62`
- `rdbss!RxNameCacheExpireEntry` at `0x140028c62`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028c4b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028c7c`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028c4b`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140028c7c`
- `rdbss!RxCrackPathName` at `0x140028bd8`
- `rdbss!RxCrackPathName` at `0x140028bd8`

## pseudocode

```c
__int64 __fastcall Smb2InvalidateContainingDirInfoCacheEx(__int64 a1, __int64 a2, struct _NAME_CACHE_CONTROL_ *a3)
{
  __int64 v4; // rax
  int v5; // edi
  struct _NAME_CACHE *i; // rax
  __int128 v8; // [rsp+30h] [rbp-18h] BYREF

  v4 = a2;
  v5 = a1;
  v8 = 0;
  if ( !a2 )
    v4 = *(_QWORD *)(a1 + 56) + 360LL;
  RxCrackPathName(v4, &v8, 0, 0);
  ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
      v5,
      (__int64)&v8);
  }
  for ( i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a3, &v8, 0, 0);
        i;
        i = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a3, &v8, 0, 0) )
  {
    RxNameCacheExpireEntry(a3, i);
  }
  return ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
}

```

## disassembly

```asm
0x140028ba0  mov     [rsp+arg_0], rbx
0x140028ba5  push    rdi
0x140028ba6  sub     rsp, 40h
0x140028baa  xorps   xmm0, xmm0
0x140028bad  mov     rbx, r8
0x140028bb0  mov     rax, rdx
0x140028bb3  mov     rdi, rcx
0x140028bb6  movups  [rsp+48h+var_18], xmm0
0x140028bbb  test    rdx, rdx
0x140028bbe  jnz     short loc_140028BCA
0x140028bc0  mov     rax, [rcx+38h]
0x140028bc4  add     rax, 168h
0x140028bca  xor     r9d, r9d
0x140028bcd  lea     rdx, [rsp+48h+var_18]
0x140028bd2  xor     r8d, r8d
0x140028bd5  mov     rcx, rax
0x140028bd8  call    cs:__imp_RxCrackPathName
0x140028bdf  nop     dword ptr [rax+rax+00h]
0x140028be4  xor     edx, edx
0x140028be6  lea     rcx, Smb2DirCacheLock
0x140028bed  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140028bf4  nop     dword ptr [rax+rax+00h]
0x140028bf9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140028c00  lea     rax, WPP_GLOBAL_Control
0x140028c07  cmp     rcx, rax
0x140028c0a  jz      short loc_140028C3D
0x140028c0c  test    dword ptr [rcx+2Ch], 100h
0x140028c13  jz      short loc_140028C3D
0x140028c15  cmp     byte ptr [rcx+29h], 2
0x140028c19  jb      short loc_140028C3D
0x140028c1b  mov     rcx, [rcx+18h]
0x140028c1f  lea     rax, [rsp+48h+var_18]
0x140028c24  mov     edx, 13h
0x140028c29  mov     [rsp+48h+var_28], rax
0x140028c2e  mov     r9, rdi
0x140028c31  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x140028c38  call    WPP_SF_qZ
0x140028c3d  xor     r9d, r9d
0x140028c40  lea     rdx, [rsp+48h+var_18]
0x140028c45  xor     r8d, r8d
0x140028c48  mov     rcx, rbx
0x140028c4b  call    cs:__imp_RxNameCacheFetchEntryEx
0x140028c52  nop     dword ptr [rax+rax+00h]
0x140028c57  test    rax, rax
0x140028c5a  jz      short loc_140028C8D
0x140028c5c  mov     rdx, rax; NameCache
0x140028c5f  mov     rcx, rbx; NameCacheCtl
0x140028c62  call    cs:__imp_RxNameCacheExpireEntry
0x140028c69  nop     dword ptr [rax+rax+00h]
0x140028c6e  xor     r9d, r9d
0x140028c71  lea     rdx, [rsp+48h+var_18]
0x140028c76  xor     r8d, r8d
0x140028c79  mov     rcx, rbx
0x140028c7c  call    cs:__imp_RxNameCacheFetchEntryEx
0x140028c83  nop     dword ptr [rax+rax+00h]
0x140028c88  test    rax, rax
0x140028c8b  jnz     short loc_140028C5C
0x140028c8d  xor     edx, edx
0x140028c8f  lea     rcx, Smb2DirCacheLock
0x140028c96  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140028c9d  nop     dword ptr [rax+rax+00h]
0x140028ca2  mov     rbx, [rsp+48h+arg_0]
0x140028ca7  add     rsp, 40h
0x140028cab  pop     rdi
0x140028cac  retn
```
