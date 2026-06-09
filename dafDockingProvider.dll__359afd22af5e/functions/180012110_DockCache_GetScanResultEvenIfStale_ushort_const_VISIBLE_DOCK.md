# DockCache::GetScanResultEvenIfStale(ushort const *,_VISIBLE_DOCK *)

- ea: `0x180012110`
- end: `0x180012177`
- name: `?GetScanResultEvenIfStale@DockCache@@QEAAJPEBGPEAU_VISIBLE_DOCK@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const unsigned __int16 *, struct _VISIBLE_DOCK *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a040`
- `0x18000e7d0`

## callees

- `0x180011c2c`
- `0x180012110`
- `0x180012180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012128`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012128`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001215f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001215f`

## pseudocode

```c
__int64 __fastcall DockCache::GetScanResultEvenIfStale(
        struct _RTL_CRITICAL_SECTION *this,
        const unsigned __int16 *a2,
        struct _VISIBLE_DOCK *a3)
{
  int Dock; // ebx
  Dock *v8; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection(this);
  v8 = 0;
  Dock = DockCache::FindDock((DockCache *)this, a2, &v8);
  if ( Dock >= 0 )
    Dock = Dock::GetVisibleEvenIfStale(v8, a3);
  LeaveCriticalSection(this);
  return (unsigned int)Dock;
}

```

## disassembly

```asm
0x180012110  mov     [rsp+arg_8], rbx
0x180012115  mov     [rsp+arg_10], rsi
0x18001211a  push    rdi
0x18001211b  sub     rsp, 20h
0x18001211f  mov     rsi, r8
0x180012122  mov     rbx, rdx
0x180012125  mov     rdi, rcx
0x180012128  call    cs:__imp_EnterCriticalSection
0x18001212e  lea     r8, [rsp+28h+arg_0]; struct Dock **
0x180012133  mov     [rsp+28h+arg_0], 0
0x18001213c  mov     rdx, rbx; unsigned __int16 *
0x18001213f  mov     rcx, rdi; this
0x180012142  call    ?FindDock@DockCache@@AEAAJPEBGPEAPEAVDock@@@Z; DockCache::FindDock(ushort const *,Dock * *)
0x180012147  mov     ebx, eax
0x180012149  test    eax, eax
0x18001214b  js      short loc_18001215C
0x18001214d  mov     rcx, [rsp+28h+arg_0]; this
0x180012152  mov     rdx, rsi; struct _VISIBLE_DOCK *
0x180012155  call    ?GetVisibleEvenIfStale@Dock@@QEAAJPEAU_VISIBLE_DOCK@@@Z; Dock::GetVisibleEvenIfStale(_VISIBLE_DOCK *)
0x18001215a  mov     ebx, eax
0x18001215c  mov     rcx, rdi; lpCriticalSection
0x18001215f  call    cs:__imp_LeaveCriticalSection
0x180012165  mov     rsi, [rsp+28h+arg_10]
0x18001216a  mov     eax, ebx
0x18001216c  mov     rbx, [rsp+28h+arg_8]
0x180012171  add     rsp, 20h
0x180012175  pop     rdi
0x180012176  retn
```
