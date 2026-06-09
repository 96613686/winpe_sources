# CDisplay::UpdateView(void)

- ea: `0x18003a3b4`
- end: `0x18003a4c8`
- name: `?UpdateView@CDisplay@@QEAAHXZ`
- size: `276`
- prototype: `__int64 __fastcall(CDisplay *__hidden this)`
- caller_count: `12`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18002cc44`
- `0x18002cfd0`
- `0x18003a300`
- `0x18005bdbc`
- `0x18005d520`
- `0x18005ebd4`
- `0x180071530`
- `0x180071890`
- `0x1800718c0`
- `0x180071980`
- `0x180071c60`
- `0x180071c90`

## callees

- `0x18000cf50`
- `0x18003a3b4`
- `0x18003a4d0`
- `0x18003a5a4`
- `0x180048e54`
- `0x180091140`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CDisplay::UpdateView(CDisplay *this)
{
  int v2; // ecx
  CTxtEdit **v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rdx
  struct tagRECT v7; // [rsp+20h] [rbp-28h] BYREF

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
        v7 = 0;
        CDisplay::GetViewRect(this, &v7, 0);
        CDisplay::UpdateViewRectState(this, &v7);
        if ( !*((_WORD *)this + 18) || !*((_WORD *)this + 19) )
          CDevDesc::SetDC((CDisplay *)((char *)this + 16), 0, -1, -1);
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
0x18003a3b4  mov     [rsp+arg_8], rbx
0x18003a3b9  mov     [rsp+arg_10], rsi
0x18003a3be  push    rdi
0x18003a3bf  sub     rsp, 40h
0x18003a3c3  mov     rax, cs:__security_cookie
0x18003a3ca  xor     rax, rsp
0x18003a3cd  mov     [rsp+48h+var_18], rax
0x18003a3d2  mov     rbx, rcx
0x18003a3d5  mov     ecx, [rcx+38h]
0x18003a3d8  test    cl, 20h
0x18003a3db  jnz     loc_18003A4A6
0x18003a3e1  lea     rdi, [rbx+10h]
0x18003a3e5  mov     rax, [rdi]
0x18003a3e8  test    byte ptr [rax+0B4h], 8
0x18003a3ef  jnz     short loc_18003A41A
0x18003a3f1  bts     ecx, 7
0x18003a3f5  xor     r8d, r8d
0x18003a3f8  mov     [rbx+38h], ecx
0x18003a3fb  xor     edx, edx
0x18003a3fd  mov     rcx, [rax+30h]
0x18003a401  mov     rax, [rcx]
0x18003a404  mov     rax, [rax+48h]
0x18003a408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a40d  mov     rcx, [rdi]; this
0x18003a410  call    ?TxUpdateWindow@CTxtEdit@@QEAAXXZ; CTxtEdit::TxUpdateWindow(void)
0x18003a415  jmp     loc_18003A4A6
0x18003a41a  mov     rax, [rax+40h]
0x18003a41e  xor     esi, esi
0x18003a420  mov     rdx, [rax+30h]
0x18003a424  test    rdx, rdx
0x18003a427  jz      short loc_18003A42F
0x18003a429  or      dword ptr [rdx+10h], 4
0x18003a42d  jmp     short loc_18003A4A6
0x18003a42f  bts     ecx, 0Ch
0x18003a433  lea     rdx, [rsp+48h+var_28]; struct tagRECT *
0x18003a438  mov     [rbx+38h], ecx
0x18003a43b  xorps   xmm0, xmm0
0x18003a43e  mov     rcx, rbx; this
0x18003a441  xor     r8d, r8d; struct tagRECT *
0x18003a444  movups  xmmword ptr [rsp+48h+var_28.left], xmm0
0x18003a449  call    ?GetViewRect@CDisplay@@QEAAXAEAUtagRECT@@PEBU2@@Z; CDisplay::GetViewRect(tagRECT &,tagRECT const *)
0x18003a44e  lea     rdx, [rsp+48h+var_28]; struct tagRECT *
0x18003a453  mov     rcx, rbx; this
0x18003a456  call    ?UpdateViewRectState@CDisplay@@AEAAXPEBUtagRECT@@@Z; CDisplay::UpdateViewRectState(tagRECT const *)
0x18003a45b  cmp     [rbx+24h], si
0x18003a45f  jz      short loc_18003A467
0x18003a461  cmp     [rbx+26h], si
0x18003a465  jnz     short loc_18003A478
0x18003a467  or      r8d, 0FFFFFFFFh; int
0x18003a46b  xor     edx, edx; HDC
0x18003a46d  mov     r9d, r8d; int
0x18003a470  mov     rcx, rdi; this
0x18003a473  call    ?SetDC@CDevDesc@@QEAAHPEAUHDC__@@JJ@Z; CDevDesc::SetDC(HDC__ *,long,long)
0x18003a478  mov     rax, [rbx]
0x18003a47b  xor     r8d, r8d
0x18003a47e  mov     rcx, rbx
0x18003a481  mov     rax, [rax+20h]
0x18003a485  lea     edx, [r8+1]
0x18003a489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a48e  mov     rax, [rdi]
0x18003a491  xor     r8d, r8d
0x18003a494  xor     edx, edx
0x18003a496  mov     rcx, [rax+30h]
0x18003a49a  mov     rax, [rcx]
0x18003a49d  mov     rax, [rax+48h]
0x18003a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a4a6  mov     eax, 1
0x18003a4ab  mov     rcx, [rsp+48h+var_18]
0x18003a4b0  xor     rcx, rsp; StackCookie
0x18003a4b3  call    __security_check_cookie
0x18003a4b8  mov     rbx, [rsp+48h+arg_8]
0x18003a4bd  mov     rsi, [rsp+48h+arg_10]
0x18003a4c2  add     rsp, 40h
0x18003a4c6  pop     rdi
0x18003a4c7  retn
```
