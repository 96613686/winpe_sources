# CTxtEdit::StopMagellanScroll(void)

- ea: `0x180060458`
- end: `0x180060512`
- name: `?StopMagellanScroll@CTxtEdit@@AEAAHXZ`
- size: `186`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180049214`
- `0x18005e8d4`
- `0x18005ee7c`
- `0x18005f078`
- `0x18005f600`
- `0x18005f68c`
- `0x18005f6b0`
- `0x18005fe74`

## callees

- `0x18001e720`
- `0x180057f28`
- `0x180060458`
- `0x180095010`

## import_xrefs

- `GDI32!DeleteObject` at `0x1800604bf`
- `GDI32!DeleteObject` at `0x1800604bf`

## pseudocode

```c
__int64 __fastcall CTxtEdit::StopMagellanScroll(CTxtEdit *this)
{
  HGDIOBJ *v1; // rdi
  __int16 v3; // ax
  CDisplay *v5; // rcx
  struct CDisplay *v6; // rcx
  HGDIOBJ v7; // rcx

  v1 = (HGDIOBJ *)((char *)this + 24);
  v3 = *((_WORD *)this + 12);
  if ( (v3 & 2) == 0 )
    return 0;
  *(_WORD *)v1 = v3 & 0xFFFD;
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 120LL))(*((_QWORD *)this + 6), 435);
  v5 = (CDisplay *)*((_QWORD *)this + 8);
  if ( v5 )
  {
    CDisplay::FinishSmoothVScroll(v5);
    CMagellan::InvertMagellanDownBMP(v1, v6, 0, 0);
  }
  v7 = v1[1];
  if ( v7 )
  {
    DeleteObject(v7);
    v1[1] = 0;
    *((_WORD *)v1 + 1) = 0;
  }
  if ( (*((_BYTE *)this + 180) & 2) != 0 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 136LL))(*((_QWORD *)this + 6), 0);
  *((_DWORD *)this + 45) &= 0xFEFFFDFD;
  return 1;
}

```

## disassembly

```asm
0x180060458  mov     [rsp+arg_0], rbx
0x18006045d  push    rdi
0x18006045e  sub     rsp, 20h
0x180060462  lea     rdi, [rcx+18h]
0x180060466  mov     rbx, rcx
0x180060469  movzx   eax, word ptr [rdi]
0x18006046c  test    al, 2
0x18006046e  jnz     short loc_180060477
0x180060470  xor     eax, eax
0x180060472  jmp     loc_180060506
0x180060477  mov     ecx, 0FFFDh
0x18006047c  mov     edx, 1B3h
0x180060481  and     ax, cx
0x180060484  mov     [rdi], ax
0x180060487  mov     rcx, [rbx+30h]
0x18006048b  mov     rax, [rcx]
0x18006048e  mov     rax, [rax+78h]
0x180060492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060497  mov     rcx, [rbx+40h]; this
0x18006049b  test    rcx, rcx
0x18006049e  jz      short loc_1800604B6
0x1800604a0  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x1800604a5  mov     rdx, rcx; struct CDisplay *
0x1800604a8  xor     r9d, r9d; HDC
0x1800604ab  mov     rcx, rdi; this
0x1800604ae  xor     r8d, r8d; int
0x1800604b1  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x1800604b6  mov     rcx, [rdi+8]; ho
0x1800604ba  test    rcx, rcx
0x1800604bd  jz      short loc_1800604D9
0x1800604bf  call    cs:__imp_DeleteObject
0x1800604c6  nop     dword ptr [rax+rax+00h]
0x1800604cb  xor     eax, eax
0x1800604cd  mov     qword ptr [rdi+8], 0
0x1800604d5  mov     [rdi+2], ax
0x1800604d9  test    byte ptr [rbx+0B4h], 2
0x1800604e0  jz      short loc_1800604F7
0x1800604e2  mov     rcx, [rbx+30h]
0x1800604e6  xor     edx, edx
0x1800604e8  mov     rax, [rcx]
0x1800604eb  mov     rax, [rax+88h]
0x1800604f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800604f7  and     dword ptr [rbx+0B4h], 0FEFFFDFDh
0x180060501  mov     eax, 1
0x180060506  mov     rbx, [rsp+28h+arg_0]
0x18006050b  add     rsp, 20h
0x18006050f  pop     rdi
0x180060510  retn
```
