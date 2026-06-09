# CListenerController::~CListenerController(void)

- ea: `0x18000edec`
- end: `0x18000ee98`
- name: `??1CListenerController@@EEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CListenerController *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000eed0`

## callees

- `0x18000edec`
- `0x18000f2d0`
- `0x180031010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18000ee43`
- `KERNEL32!CloseHandle` at `0x18000ee43`
- `KERNEL32!WaitForSingleObject` at `0x18000ee39`
- `KERNEL32!WaitForSingleObject` at `0x18000ee39`
- `KERNEL32!DeleteCriticalSection` at `0x18000ee19`
- `KERNEL32!DeleteCriticalSection` at `0x18000ee19`

## pseudocode

```c
void __fastcall CListenerController::~CListenerController(CListenerController *this)
{
  bool v1; // zf
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  v1 = *((_DWORD *)this + 16) == 0;
  *(_QWORD *)this = &CListenerController::`vftable';
  if ( !v1 )
  {
    CListenerController::Stop((__int64)this, 1);
    if ( *((_DWORD *)this + 5) )
    {
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
      *((_DWORD *)this + 5) = 0;
    }
    *((_DWORD *)this + 16) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 12);
  if ( v3 )
  {
    WaitForSingleObject(v3, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
  v4 = *((_QWORD *)this + 10);
  if ( v4 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    *((_QWORD *)this + 10) = 0;
  }
  v5 = *((_QWORD *)this + 9);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 9) = 0;
  }
  *((_DWORD *)this + 4) = 1668246648;
}

```

## disassembly

```asm
0x18000edec  push    rbx
0x18000edee  sub     rsp, 20h
0x18000edf2  cmp     dword ptr [rcx+40h], 0
0x18000edf6  lea     rax, ??_7CListenerController@@6B@; const CListenerController::`vftable'
0x18000edfd  mov     [rcx], rax
0x18000ee00  mov     rbx, rcx
0x18000ee03  jz      short loc_18000EE2D
0x18000ee05  mov     edx, 1
0x18000ee0a  call    ?Stop@CListenerController@@QEAAJW4eSTATE@@@Z; CListenerController::Stop(eSTATE)
0x18000ee0f  cmp     dword ptr [rbx+14h], 0
0x18000ee13  jz      short loc_18000EE26
0x18000ee15  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000ee19  call    cs:__imp_DeleteCriticalSection
0x18000ee1f  mov     dword ptr [rbx+14h], 0
0x18000ee26  mov     dword ptr [rbx+40h], 0
0x18000ee2d  mov     rcx, [rbx+60h]; hHandle
0x18000ee31  test    rcx, rcx
0x18000ee34  jz      short loc_18000EE51
0x18000ee36  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000ee39  call    cs:__imp_WaitForSingleObject
0x18000ee3f  mov     rcx, [rbx+60h]; hObject
0x18000ee43  call    cs:__imp_CloseHandle
0x18000ee49  mov     qword ptr [rbx+60h], 0
0x18000ee51  mov     rcx, [rbx+50h]
0x18000ee55  test    rcx, rcx
0x18000ee58  jz      short loc_18000EE6E
0x18000ee5a  mov     rax, [rcx]
0x18000ee5d  mov     rax, [rax+8]
0x18000ee61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee66  mov     qword ptr [rbx+50h], 0
0x18000ee6e  mov     rcx, [rbx+48h]
0x18000ee72  test    rcx, rcx
0x18000ee75  jz      short loc_18000EE8B
0x18000ee77  mov     rax, [rcx]
0x18000ee7a  mov     rax, [rax+10h]
0x18000ee7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee83  mov     qword ptr [rbx+48h], 0
0x18000ee8b  mov     dword ptr [rbx+10h], 636F6C78h
0x18000ee92  add     rsp, 20h
0x18000ee96  pop     rbx
0x18000ee97  retn
```
