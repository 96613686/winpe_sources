# CDisplay::UpdateView(void)

- ea: `0x180040e04`
- end: `0x180040f0a`
- name: `?UpdateView@CDisplay@@QEAAHXZ`
- size: `262`
- prototype: `__int64 __fastcall(CDisplay *__hidden this)`
- caller_count: `12`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x180027794`
- `0x180027b20`
- `0x180040d50`
- `0x18005d438`
- `0x18005ec00`
- `0x1800602f4`
- `0x180073430`
- `0x180073790`
- `0x1800737c0`
- `0x180073890`
- `0x180073b70`
- `0x180073bb0`

## callees

- `0x18000c260`
- `0x18003b500`
- `0x180040e04`
- `0x18004103c`
- `0x180042bb0`
- `0x18004a0e4`
- `0x180093c00`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CDisplay::UpdateView(CDisplay *this)
{
  int v2; // ecx
  CTxtEdit **v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdx
  CDevDesc *v6; // rcx
  struct tagRECT v8; // [rsp+20h] [rbp-28h] BYREF

  v2 = *((_DWORD *)this + 14);
  if ( (v2 & 0x20) == 0 )
  {
    v3 = (CTxtEdit **)((char *)this + 16);
    v4 = *((_QWORD *)this + 2);
    if ( (*(_BYTE *)(v4 + 180) & 8) != 0 )
    {
      v5 = *(_QWORD *)(*(_QWORD *)(v4 + 64) + 48LL);
      if ( v5 )
      {
        *(_DWORD *)(v5 + 16) |= 4u;
      }
      else
      {
        *((_DWORD *)this + 14) = v2 | 0x1000;
        v8 = 0;
        CDisplay::GetViewRect(this, &v8, 0);
        CDisplay::UpdateViewRectState(this, &v8);
        if ( !(unsigned int)CDevDesc::IsValid((CDisplay *)((char *)this + 16)) )
          CDevDesc::SetDC(v6, 0, -1, -1);
        (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)this + 32LL))(this, 1);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)*v3 + 6) + 72LL))(*((_QWORD *)*v3 + 6), 0, 0);
      }
    }
    else
    {
      *((_DWORD *)this + 14) = v2 | 0x80;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v4 + 48) + 72LL))(*(_QWORD *)(v4 + 48), 0, 0);
      CTxtEdit::TxUpdateWindow(*v3);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180040e04  mov     [rsp+arg_8], rbx
0x180040e09  push    rdi
0x180040e0a  sub     rsp, 40h
0x180040e0e  mov     rax, cs:__security_cookie
0x180040e15  xor     rax, rsp
0x180040e18  mov     [rsp+48h+var_18], rax
0x180040e1d  mov     rbx, rcx
0x180040e20  mov     ecx, [rcx+38h]
0x180040e23  test    cl, 20h
0x180040e26  jnz     loc_180040EEC
0x180040e2c  lea     rdi, [rbx+10h]
0x180040e30  mov     rax, [rdi]
0x180040e33  test    byte ptr [rax+0B4h], 8
0x180040e3a  jnz     short loc_180040E65
0x180040e3c  bts     ecx, 7
0x180040e40  xor     r8d, r8d
0x180040e43  mov     [rbx+38h], ecx
0x180040e46  xor     edx, edx
0x180040e48  mov     rcx, [rax+30h]
0x180040e4c  mov     rax, [rcx]
0x180040e4f  mov     rax, [rax+48h]
0x180040e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e58  mov     rcx, [rdi]; this
0x180040e5b  call    ?TxUpdateWindow@CTxtEdit@@QEAAXXZ; CTxtEdit::TxUpdateWindow(void)
0x180040e60  jmp     loc_180040EEC
0x180040e65  mov     rax, [rax+40h]
0x180040e69  mov     rdx, [rax+30h]
0x180040e6d  test    rdx, rdx
0x180040e70  jz      short loc_180040E78
0x180040e72  or      dword ptr [rdx+10h], 4
0x180040e76  jmp     short loc_180040EEC
0x180040e78  bts     ecx, 0Ch
0x180040e7c  lea     rdx, [rsp+48h+var_28]; struct tagRECT *
0x180040e81  mov     [rbx+38h], ecx
0x180040e84  xorps   xmm0, xmm0
0x180040e87  mov     rcx, rbx; this
0x180040e8a  xor     r8d, r8d; struct tagRECT *
0x180040e8d  movups  xmmword ptr [rsp+48h+var_28.left], xmm0
0x180040e92  call    ?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z; CDisplay::GetViewRect(tagRECT &,tagRECT const *)
0x180040e97  lea     rdx, [rsp+48h+var_28]; struct tagRECT *
0x180040e9c  mov     rcx, rbx; this
0x180040e9f  call    ?UpdateViewRectState@CDisplay@@AEAAXPEBUtagRECT@@@Z; CDisplay::UpdateViewRectState(tagRECT const *)
0x180040ea4  mov     rcx, rdi; this
0x180040ea7  call    ?IsValid@CDevDesc@@QEBAHXZ; CDevDesc::IsValid(void)
0x180040eac  test    eax, eax
0x180040eae  jnz     short loc_180040EBE
0x180040eb0  or      r8d, 0FFFFFFFFh; int
0x180040eb4  xor     edx, edx; HDC
0x180040eb6  mov     r9d, r8d; int
0x180040eb9  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x180040ebe  mov     rax, [rbx]
0x180040ec1  xor     r8d, r8d
0x180040ec4  mov     rcx, rbx
0x180040ec7  mov     rax, [rax+20h]
0x180040ecb  lea     edx, [r8+1]
0x180040ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ed4  mov     rax, [rdi]
0x180040ed7  xor     r8d, r8d
0x180040eda  xor     edx, edx
0x180040edc  mov     rcx, [rax+30h]
0x180040ee0  mov     rax, [rcx]
0x180040ee3  mov     rax, [rax+48h]
0x180040ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040eec  mov     eax, 1
0x180040ef1  mov     rcx, [rsp+48h+var_18]
0x180040ef6  xor     rcx, rsp; StackCookie
0x180040ef9  call    __security_check_cookie
0x180040efe  mov     rbx, [rsp+48h+arg_8]
0x180040f03  add     rsp, 40h
0x180040f07  pop     rdi
0x180040f08  retn
```
