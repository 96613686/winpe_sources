# CPropMgrImpl::~CPropMgrImpl(void)

- ea: `0x180012400`
- end: `0x18001243a`
- name: `??1CPropMgrImpl@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CPropMgrImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800123cc`

## callees

- `0x180012400`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012427`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012427`
- `USER32!DestroyWindow` at `0x18001241d`
- `USER32!DestroyWindow` at `0x18001241d`

## pseudocode

```c
void __fastcall CPropMgrImpl::~CPropMgrImpl(CPropMgrImpl *this)
{
  HWND v2; // rcx

  CPropMgrImpl::s_pThePropMgrImpl = 0;
  v2 = (HWND)*((_QWORD *)this + 2);
  if ( v2 )
    DestroyWindow(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedDecrement((_DWORD *)&qword_180061978 + 1);
}

```

## disassembly

```asm
0x180012400  push    rbx
0x180012402  sub     rsp, 20h
0x180012406  mov     rbx, rcx
0x180012409  mov     cs:?s_pThePropMgrImpl@CPropMgrImpl@@0PEAV1@EA, 0; CPropMgrImpl * CPropMgrImpl::s_pThePropMgrImpl
0x180012414  mov     rcx, [rcx+10h]; hWnd
0x180012418  test    rcx, rcx
0x18001241b  jz      short loc_180012423
0x18001241d  call    cs:__imp_DestroyWindow
0x180012423  lea     rcx, [rbx+20h]; lpCriticalSection
0x180012427  call    cs:__imp_DeleteCriticalSection
0x18001242d  lock dec dword ptr cs:qword_180061978+4
0x180012434  add     rsp, 20h
0x180012438  pop     rbx
0x180012439  retn
```
