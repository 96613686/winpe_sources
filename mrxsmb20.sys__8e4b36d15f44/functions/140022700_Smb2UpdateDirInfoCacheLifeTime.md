# Smb2UpdateDirInfoCacheLifeTime

- ea: `0x140022700`
- end: `0x1400227fb`
- name: `Smb2UpdateDirInfoCacheLifeTime`
- size: `251`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140011fd0`
- `0x14001d020`

## callees

- `0x140022700`
- `0x140029894`

## import_xrefs

- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400227de`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400227de`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002274a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14002274a`
- `rdbss!RxNameCacheActivateEntry` at `0x140022781`
- `rdbss!RxNameCacheActivateEntry` at `0x140022781`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140022764`
- `rdbss!RxNameCacheFetchEntryEx` at `0x140022764`
- `rdbss!RxCrackPathName` at `0x140022735`
- `rdbss!RxCrackPathName` at `0x140022735`

## pseudocode

```c
__int64 __fastcall Smb2UpdateDirInfoCacheLifeTime(__int64 a1, struct _NAME_CACHE_CONTROL_ *a2, ULONG a3)
{
  int v3; // edi
  __int64 v6; // rcx
  struct _NAME_CACHE *Entry; // rax
  __int128 v9; // [rsp+30h] [rbp-18h] BYREF

  v3 = a1;
  v6 = *(_QWORD *)(a1 + 56) + 360LL;
  v9 = 0;
  RxCrackPathName(v6, 0, &v9, 0);
  ExAcquirePushLockExclusiveEx(&Smb2DirCacheLock, 0);
  Entry = (struct _NAME_CACHE *)RxNameCacheFetchEntryEx(a2, &v9, 0, 0);
  if ( Entry )
  {
    RxNameCacheActivateEntry(a2, Entry, a3, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qZd(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_fb97726eb6f036c688a7379a523a601c_Traceguids,
        v3,
        (__int64)&v9,
        a3);
    }
  }
  return ExReleasePushLockExclusiveEx(&Smb2DirCacheLock, 0);
}

```

## disassembly

```asm
0x140022700  mov     [rsp+arg_0], rbx
0x140022705  mov     [rsp+arg_8], rsi
0x14002270a  push    rdi
0x14002270b  sub     rsp, 40h
0x14002270f  mov     rdi, rcx
0x140022712  mov     esi, r8d
0x140022715  mov     rcx, [rcx+38h]
0x140022719  lea     r8, [rsp+48h+var_18]
0x14002271e  mov     rbx, rdx
0x140022721  xorps   xmm0, xmm0
0x140022724  add     rcx, 168h
0x14002272b  xor     r9d, r9d
0x14002272e  xor     edx, edx
0x140022730  movups  [rsp+48h+var_18], xmm0
0x140022735  call    cs:__imp_RxCrackPathName
0x14002273c  nop     dword ptr [rax+rax+00h]
0x140022741  xor     edx, edx
0x140022743  lea     rcx, Smb2DirCacheLock
0x14002274a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140022751  nop     dword ptr [rax+rax+00h]
0x140022756  xor     r9d, r9d
0x140022759  lea     rdx, [rsp+48h+var_18]
0x14002275e  xor     r8d, r8d
0x140022761  mov     rcx, rbx
0x140022764  call    cs:__imp_RxNameCacheFetchEntryEx
0x14002276b  nop     dword ptr [rax+rax+00h]
0x140022770  test    rax, rax
0x140022773  jz      short loc_1400227D5
0x140022775  xor     r9d, r9d; MRxContext
0x140022778  mov     r8d, esi; LifeTime
0x14002277b  mov     rdx, rax; NameCache
0x14002277e  mov     rcx, rbx; NameCacheCtl
0x140022781  call    cs:__imp_RxNameCacheActivateEntry
0x140022788  nop     dword ptr [rax+rax+00h]
0x14002278d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140022794  lea     rax, WPP_GLOBAL_Control
0x14002279b  cmp     rcx, rax
0x14002279e  jz      short loc_1400227D5
0x1400227a0  test    dword ptr [rcx+2Ch], 100h
0x1400227a7  jz      short loc_1400227D5
0x1400227a9  cmp     byte ptr [rcx+29h], 2
0x1400227ad  jb      short loc_1400227D5
0x1400227af  mov     rcx, [rcx+18h]
0x1400227b3  lea     rax, [rsp+48h+var_18]
0x1400227b8  mov     edx, 15h
0x1400227bd  mov     [rsp+48h+var_20], esi
0x1400227c1  mov     r9, rdi
0x1400227c4  mov     [rsp+48h+var_28], rax
0x1400227c9  lea     r8, WPP_fb97726eb6f036c688a7379a523a601c_Traceguids
0x1400227d0  call    WPP_SF_qZd
0x1400227d5  xor     edx, edx
0x1400227d7  lea     rcx, Smb2DirCacheLock
0x1400227de  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400227e5  nop     dword ptr [rax+rax+00h]
0x1400227ea  mov     rbx, [rsp+48h+arg_0]
0x1400227ef  mov     rsi, [rsp+48h+arg_8]
0x1400227f4  add     rsp, 40h
0x1400227f8  pop     rdi
0x1400227f9  retn
```
