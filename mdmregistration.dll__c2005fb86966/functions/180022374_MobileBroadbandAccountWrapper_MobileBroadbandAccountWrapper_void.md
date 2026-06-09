# MobileBroadbandAccountWrapper::~MobileBroadbandAccountWrapper(void)

- ea: `0x180022374`
- end: `0x1800223d4`
- name: `??1MobileBroadbandAccountWrapper@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(MobileBroadbandAccountWrapper *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180022e74`
- `0x18004c522`

## callees

- `0x180022374`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022386`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022386`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall MobileBroadbandAccountWrapper::~MobileBroadbandAccountWrapper(MobileBroadbandAccountWrapper *this)
{
  HSTRING v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  v2 = (HSTRING)*((_QWORD *)this + 3);
  if ( v2 )
    WindowsDeleteString(v2);
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
  {
    *((_QWORD *)this + 1) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    *(_QWORD *)this = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180022374  push    rbx
0x180022376  sub     rsp, 20h
0x18002237a  mov     rbx, rcx
0x18002237d  mov     rcx, [rcx+18h]; string
0x180022381  test    rcx, rcx
0x180022384  jz      short loc_180022393
0x180022386  call    cs:__imp_WindowsDeleteString
0x18002238d  nop     dword ptr [rax+rax+00h]
0x180022392  nop
0x180022393  mov     rcx, [rbx+8]
0x180022397  test    rcx, rcx
0x18002239a  jz      short loc_1800223B1
0x18002239c  mov     qword ptr [rbx+8], 0
0x1800223a4  mov     rax, [rcx]
0x1800223a7  mov     rax, [rax+10h]
0x1800223ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223b0  nop
0x1800223b1  mov     rcx, [rbx]
0x1800223b4  test    rcx, rcx
0x1800223b7  jz      short loc_1800223CD
0x1800223b9  mov     qword ptr [rbx], 0
0x1800223c0  mov     rax, [rcx]
0x1800223c3  mov     rax, [rax+10h]
0x1800223c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223cc  nop
0x1800223cd  add     rsp, 20h
0x1800223d1  pop     rbx
0x1800223d2  retn
```
