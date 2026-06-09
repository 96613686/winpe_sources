# CTxtEdit::StopMagellanScroll(void)

- ea: `0x18005ed34`
- end: `0x18005ede7`
- name: `?StopMagellanScroll@CTxtEdit@@AEAAHXZ`
- size: `179`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x1800483bc`
- `0x18005d210`
- `0x18005d798`
- `0x18005d98c`
- `0x18005df08`
- `0x18005df90`
- `0x18005dfb4`
- `0x18005e75c`

## callees

- `0x18003aeb0`
- `0x180056994`
- `0x18005ed34`
- `0x180092010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18005ed9b`
- `GDI32!DeleteObject` at `0x18005ed9b`

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
0x18005ed34  mov     [rsp+arg_0], rbx
0x18005ed39  push    rdi
0x18005ed3a  sub     rsp, 20h
0x18005ed3e  lea     rdi, [rcx+18h]
0x18005ed42  mov     rbx, rcx
0x18005ed45  movzx   eax, word ptr [rdi]
0x18005ed48  test    al, 2
0x18005ed4a  jnz     short loc_18005ED53
0x18005ed4c  xor     eax, eax
0x18005ed4e  jmp     loc_18005EDDC
0x18005ed53  mov     ecx, 0FFFDh
0x18005ed58  mov     edx, 1B3h
0x18005ed5d  and     ax, cx
0x18005ed60  mov     [rdi], ax
0x18005ed63  mov     rcx, [rbx+30h]
0x18005ed67  mov     rax, [rcx]
0x18005ed6a  mov     rax, [rax+78h]
0x18005ed6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ed73  mov     rcx, [rbx+40h]; this
0x18005ed77  test    rcx, rcx
0x18005ed7a  jz      short loc_18005ED92
0x18005ed7c  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x18005ed81  mov     rdx, rcx; struct CDisplay *
0x18005ed84  xor     r9d, r9d; HDC
0x18005ed87  mov     rcx, rdi; this
0x18005ed8a  xor     r8d, r8d; int
0x18005ed8d  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x18005ed92  mov     rcx, [rdi+8]; ho
0x18005ed96  test    rcx, rcx
0x18005ed99  jz      short loc_18005EDAF
0x18005ed9b  call    cs:__imp_DeleteObject
0x18005eda1  xor     eax, eax
0x18005eda3  mov     qword ptr [rdi+8], 0
0x18005edab  mov     [rdi+2], ax
0x18005edaf  test    byte ptr [rbx+0B4h], 2
0x18005edb6  jz      short loc_18005EDCD
0x18005edb8  mov     rcx, [rbx+30h]
0x18005edbc  xor     edx, edx
0x18005edbe  mov     rax, [rcx]
0x18005edc1  mov     rax, [rax+88h]
0x18005edc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005edcd  and     dword ptr [rbx+0B4h], 0FEFFFDFDh
0x18005edd7  mov     eax, 1
0x18005eddc  mov     rbx, [rsp+28h+arg_0]
0x18005ede1  add     rsp, 20h
0x18005ede5  pop     rdi
0x18005ede6  retn
```
