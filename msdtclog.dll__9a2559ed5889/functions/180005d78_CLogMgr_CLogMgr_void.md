# CLogMgr::CLogMgr(void)

- ea: `0x180005d78`
- end: `0x180005fc7`
- name: `??0CLogMgr@@QEAA@XZ`
- size: `591`
- prototype: `CLogMgr *__fastcall(CLogMgr *this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800062a0`

## callees

- `0x180005d78`
- `0x18000e64c`
- `0x18000e6fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005ea6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005ed5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005ea6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180005ed5`

## string_xrefs

- `0x180005ebc`: `CreateEvent returned a NULL handle.`
- `0x180005eeb`: `CreateEvent returned a NULL handle.`

## pseudocode

```c
CLogMgr *__fastcall CLogMgr::CLogMgr(CLogMgr *this, unsigned int a2)
{
  unsigned int v3; // edx
  unsigned int v4; // edx
  HANDLE EventA; // rax
  unsigned __int16 *v6; // rdx
  HANDLE v7; // rax
  unsigned __int16 *v8; // rdx

  *(_QWORD *)this = &CLogMgr::`vftable';
  CSemExclusive::CSemExclusive((CLogMgr *)((char *)this + 40), a2);
  *((_QWORD *)this + 12) = &CILogStorage::`vftable';
  *((_QWORD *)this + 13) = this;
  *((_QWORD *)this + 14) = this;
  *((_QWORD *)this + 15) = &CILogStorageInfo::`vftable';
  *((_QWORD *)this + 16) = this;
  *((_QWORD *)this + 17) = this;
  *((_QWORD *)this + 18) = &CILogRecordPointer::`vftable';
  *((_QWORD *)this + 19) = this;
  *((_QWORD *)this + 20) = this;
  *((_QWORD *)this + 21) = &CILogInit2A::`vftable';
  *((_QWORD *)this + 22) = this;
  *((_QWORD *)this + 23) = this;
  *((_QWORD *)this + 24) = &CILogInit2W::`vftable';
  *((_QWORD *)this + 25) = this;
  *((_QWORD *)this + 26) = this;
  *((_QWORD *)this + 27) = &CILogCreateStorage2A::`vftable';
  *((_QWORD *)this + 28) = this;
  *((_QWORD *)this + 29) = this;
  *((_QWORD *)this + 30) = &CILogCreateStorage2W::`vftable';
  *((_QWORD *)this + 31) = this;
  *((_QWORD *)this + 32) = this;
  *((_QWORD *)this + 33) = &CILogUISConnect::`vftable';
  *((_QWORD *)this + 34) = this;
  *((_QWORD *)this + 35) = this;
  *((_DWORD *)this + 72) = 0;
  CSemExclusive::CSemExclusive((CLogMgr *)((char *)this + 304), v3);
  *((_QWORD *)this + 48) = 0;
  CSemExclusive::CSemExclusive((CLogMgr *)((char *)this + 408), v4);
  EventA = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 58) = EventA;
  if ( !EventA )
    UtsemWin32Error(L"CreateEvent returned a NULL handle.", v6, 0x64u);
  v7 = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 60) = v7;
  if ( !v7 )
    UtsemWin32Error(L"CreateEvent returned a NULL handle.", v8, 0x64u);
  *((_QWORD *)this + 72) = 0;
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 94) = 0;
  *((_DWORD *)this + 95) = 1;
  *((_QWORD *)this + 46) = 0;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 49) = 0;
  *((_QWORD *)this + 78) = 0;
  *((_DWORD *)this + 73) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 62) = 0;
  *((_DWORD *)this + 126) = 0;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  *((_QWORD *)this + 70) = 0;
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 73) = 0;
  *((_DWORD *)this + 148) = 0;
  *((_QWORD *)this + 75) = 0;
  *((_QWORD *)this + 76) = 0;
  *((_QWORD *)this + 77) = 0;
  *((_DWORD *)this + 158) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  return this;
}

```

## disassembly

```asm
0x180005d78  mov     [rsp+arg_8], rbx
0x180005d7d  mov     [rsp+arg_0], rcx
0x180005d82  push    rdi
0x180005d83  sub     rsp, 20h
0x180005d87  mov     rbx, rcx
0x180005d8a  lea     rax, ??_7CLogMgr@@6B@; const CLogMgr::`vftable'
0x180005d91  mov     [rcx], rax
0x180005d94  add     rcx, 28h ; '('; this
0x180005d98  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180005d9d  nop
0x180005d9e  lea     rax, ??_7CILogStorage@@6B@; const CILogStorage::`vftable'
0x180005da5  mov     [rbx+60h], rax
0x180005da9  mov     [rbx+68h], rbx
0x180005dad  mov     [rbx+70h], rbx
0x180005db1  lea     rax, ??_7CILogStorageInfo@@6B@; const CILogStorageInfo::`vftable'
0x180005db8  mov     [rbx+78h], rax
0x180005dbc  mov     [rbx+80h], rbx
0x180005dc3  mov     [rbx+88h], rbx
0x180005dca  lea     rax, ??_7CILogRecordPointer@@6B@; const CILogRecordPointer::`vftable'
0x180005dd1  mov     [rbx+90h], rax
0x180005dd8  mov     [rbx+98h], rbx
0x180005ddf  mov     [rbx+0A0h], rbx
0x180005de6  lea     rax, ??_7CILogInit2A@@6B@; const CILogInit2A::`vftable'
0x180005ded  mov     [rbx+0A8h], rax
0x180005df4  mov     [rbx+0B0h], rbx
0x180005dfb  mov     [rbx+0B8h], rbx
0x180005e02  lea     rax, ??_7CILogInit2W@@6B@; const CILogInit2W::`vftable'
0x180005e09  mov     [rbx+0C0h], rax
0x180005e10  mov     [rbx+0C8h], rbx
0x180005e17  mov     [rbx+0D0h], rbx
0x180005e1e  lea     rax, ??_7CILogCreateStorage2A@@6B@; const CILogCreateStorage2A::`vftable'
0x180005e25  mov     [rbx+0D8h], rax
0x180005e2c  mov     [rbx+0E0h], rbx
0x180005e33  mov     [rbx+0E8h], rbx
0x180005e3a  lea     rax, ??_7CILogCreateStorage2W@@6B@; const CILogCreateStorage2W::`vftable'
0x180005e41  mov     [rbx+0F0h], rax
0x180005e48  mov     [rbx+0F8h], rbx
0x180005e4f  mov     [rbx+100h], rbx
0x180005e56  lea     rax, ??_7CILogUISConnect@@6B@; const CILogUISConnect::`vftable'
0x180005e5d  mov     [rbx+108h], rax
0x180005e64  mov     [rbx+110h], rbx
0x180005e6b  mov     [rbx+118h], rbx
0x180005e72  xor     edi, edi
0x180005e74  mov     [rbx+120h], edi
0x180005e7a  lea     rcx, [rbx+130h]; this
0x180005e81  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180005e86  nop
0x180005e87  mov     [rbx+180h], rdi
0x180005e8e  lea     rcx, [rbx+198h]; this
0x180005e95  call    ??0CSemExclusive@@QEAA@K@Z; CSemExclusive::CSemExclusive(ulong)
0x180005e9a  nop
0x180005e9b  xor     r9d, r9d; lpName
0x180005e9e  xor     r8d, r8d; bInitialState
0x180005ea1  lea     edx, [rdi+1]; bManualReset
0x180005ea4  xor     ecx, ecx; lpEventAttributes
0x180005ea6  call    cs:__imp_CreateEventA
0x180005eac  mov     [rbx+1D0h], rax
0x180005eb3  test    rax, rax
0x180005eb6  jnz     short loc_180005EC9
0x180005eb8  lea     r8d, [rdi+64h]; unsigned int
0x180005ebc  lea     rcx, aCreateeventRet; "CreateEvent returned a NULL handle."
0x180005ec3  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x180005ec8  nop
0x180005ec9  xor     r9d, r9d; lpName
0x180005ecc  xor     r8d, r8d; bInitialState
0x180005ecf  lea     edx, [r9+1]; bManualReset
0x180005ed3  xor     ecx, ecx; lpEventAttributes
0x180005ed5  call    cs:__imp_CreateEventA
0x180005edb  mov     [rbx+1E0h], rax
0x180005ee2  test    rax, rax
0x180005ee5  jnz     short loc_180005EF7
0x180005ee7  lea     r8d, [rax+64h]; unsigned int
0x180005eeb  lea     rcx, aCreateeventRet; "CreateEvent returned a NULL handle."
0x180005ef2  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x180005ef7  mov     [rbx+240h], rdi
0x180005efe  mov     [rbx+20h], edi
0x180005f01  mov     [rbx+8], rdi
0x180005f05  mov     [rbx+1D8h], rdi
0x180005f0c  mov     [rbx+10h], edi
0x180005f0f  mov     [rbx+1E8h], rdi
0x180005f16  mov     [rbx+18h], rdi
0x180005f1a  mov     [rbx+168h], rdi
0x180005f21  mov     [rbx+178h], edi
0x180005f27  mov     dword ptr [rbx+17Ch], 1
0x180005f31  mov     [rbx+170h], rdi
0x180005f38  mov     [rbx+190h], rdi
0x180005f3f  mov     [rbx+188h], rdi
0x180005f46  mov     [rbx+270h], rdi
0x180005f4d  mov     [rbx+124h], edi
0x180005f53  mov     [rbx+128h], rdi
0x180005f5a  mov     [rbx+1F0h], rdi
0x180005f61  mov     [rbx+1F8h], edi
0x180005f67  mov     [rbx+220h], rdi
0x180005f6e  mov     [rbx+228h], rdi
0x180005f75  mov     [rbx+230h], rdi
0x180005f7c  mov     [rbx+238h], rdi
0x180005f83  mov     [rbx+248h], rdi
0x180005f8a  mov     [rbx+250h], edi
0x180005f90  mov     [rbx+258h], rdi
0x180005f97  mov     [rbx+260h], rdi
0x180005f9e  mov     [rbx+268h], rdi
0x180005fa5  mov     [rbx+278h], edi
0x180005fab  mov     [rbx+280h], rdi
0x180005fb2  mov     [rbx+288h], rdi
0x180005fb9  mov     rax, rbx
0x180005fbc  mov     rbx, [rsp+28h+arg_8]
0x180005fc1  add     rsp, 20h
0x180005fc5  pop     rdi
0x180005fc6  retn
```
