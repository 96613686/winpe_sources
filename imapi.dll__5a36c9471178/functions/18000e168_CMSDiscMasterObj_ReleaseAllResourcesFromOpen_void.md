# CMSDiscMasterObj::ReleaseAllResourcesFromOpen(void)

- ea: `0x18000e168`
- end: `0x18000e265`
- name: `?ReleaseAllResourcesFromOpen@CMSDiscMasterObj@@AEAAXXZ`
- size: `253`
- prototype: `void __fastcall(CMSDiscMasterObj *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000baa0`
- `0x18000ce60`

## callees

- `0x180007bac`
- `0x18000e168`
- `0x1800109d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e223`
- `KERNEL32!DeleteCriticalSection` at `0x18000e223`

## pseudocode

```c
void __fastcall CMSDiscMasterObj::ReleaseAllResourcesFromOpen(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 v2; // rcx
  HANDLE OwningThread; // rcx
  ULONG_PTR SpinCount; // rcx
  bool v5; // zf
  ULONG_PTR v6; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 76, &WPP_13db7a1dc07b38b67da169871fcda232_Traceguids);
  v2 = *(_QWORD *)&this[12].LockCount;
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)&this[12].LockCount = 0;
  }
  OwningThread = this[12].OwningThread;
  if ( OwningThread )
  {
    (*(void (__fastcall **)(HANDLE))(*(_QWORD *)OwningThread + 16LL))(OwningThread);
    this[12].OwningThread = 0;
  }
  SpinCount = this[11].SpinCount;
  if ( SpinCount )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)SpinCount + 16LL))(SpinCount);
    this[11].SpinCount = 0;
  }
  v5 = BYTE4(this[14].SpinCount) == 0;
  this[12].DebugInfo = 0;
  if ( !v5 )
  {
    DeleteCriticalSection(this + 15);
    BYTE4(this[14].SpinCount) = 0;
  }
  CMyUpdateList::RemoveAll((CMyUpdateList *)&this[4].SpinCount);
  v6 = this[10].SpinCount;
  if ( v6 )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v6 + 16LL))(v6);
    this[10].SpinCount = 0;
  }
}

```

## disassembly

```asm
0x18000e168  push    rbx
0x18000e16a  sub     rsp, 20h
0x18000e16e  mov     rbx, rcx
0x18000e171  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e178  lea     rax, WPP_GLOBAL_Control
0x18000e17f  cmp     rcx, rax
0x18000e182  jz      short loc_18000E19F
0x18000e184  test    byte ptr [rcx+44h], 1
0x18000e188  jz      short loc_18000E19F
0x18000e18a  mov     rcx, [rcx+38h]
0x18000e18e  lea     r8, WPP_13db7a1dc07b38b67da169871fcda232_Traceguids
0x18000e195  mov     edx, 4Ch ; 'L'
0x18000e19a  call    WPP_SF_
0x18000e19f  mov     rcx, [rbx+1E8h]
0x18000e1a6  test    rcx, rcx
0x18000e1a9  jz      short loc_18000E1C2
0x18000e1ab  mov     rax, [rcx]
0x18000e1ae  mov     rax, [rax+10h]
0x18000e1b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1b7  mov     qword ptr [rbx+1E8h], 0
0x18000e1c2  mov     rcx, [rbx+1F0h]
0x18000e1c9  test    rcx, rcx
0x18000e1cc  jz      short loc_18000E1E5
0x18000e1ce  mov     rax, [rcx]
0x18000e1d1  mov     rax, [rax+10h]
0x18000e1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1da  mov     qword ptr [rbx+1F0h], 0
0x18000e1e5  mov     rcx, [rbx+1D8h]
0x18000e1ec  test    rcx, rcx
0x18000e1ef  jz      short loc_18000E208
0x18000e1f1  mov     rax, [rcx]
0x18000e1f4  mov     rax, [rax+10h]
0x18000e1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1fd  mov     qword ptr [rbx+1D8h], 0
0x18000e208  cmp     byte ptr [rbx+254h], 0
0x18000e20f  mov     qword ptr [rbx+1E0h], 0
0x18000e21a  jz      short loc_18000E230
0x18000e21c  lea     rcx, [rbx+258h]; lpCriticalSection
0x18000e223  call    cs:__imp_DeleteCriticalSection
0x18000e229  mov     byte ptr [rbx+254h], 0
0x18000e230  lea     rcx, [rbx+0C0h]; this
0x18000e237  call    ?RemoveAll@CMyUpdateList@@QEAAEXZ; CMyUpdateList::RemoveAll(void)
0x18000e23c  mov     rcx, [rbx+1B0h]
0x18000e243  test    rcx, rcx
0x18000e246  jz      short loc_18000E25F
0x18000e248  mov     rax, [rcx]
0x18000e24b  mov     rax, [rax+10h]
0x18000e24f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e254  mov     qword ptr [rbx+1B0h], 0
0x18000e25f  add     rsp, 20h
0x18000e263  pop     rbx
0x18000e264  retn
```
