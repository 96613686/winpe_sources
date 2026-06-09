# CVidCtl::SetExtents(void)

- ea: `0x1800d1dac`
- end: `0x1800d1ecb`
- name: `?SetExtents@CVidCtl@@IEAAXXZ`
- size: `287`
- prototype: `void __fastcall(CVidCtl *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800c4134`
- `0x1800cf7f0`

## callees

- `0x180004640`
- `0x180085e2c`
- `0x1800c7514`
- `0x1800cb4c0`
- `0x1800d1dac`
- `0x1800f8010`

## import_xrefs

- `USER32!CopyRect` at `0x1800d1e6a`
- `USER32!CopyRect` at `0x1800d1e6a`
- `USER32!PostMessageW` at `0x1800d1eae`
- `USER32!PostMessageW` at `0x1800d1eae`

## pseudocode

```c
void __fastcall CVidCtl::SetExtents(CVidCtl *this)
{
  __int64 v1; // rbx
  struct tagSIZE *v2; // r14
  __int64 v3; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  struct tagRECT rcDst; // [rsp+30h] [rbp-58h] BYREF
  char v8; // [rsp+40h] [rbp-48h]
  __int64 v9; // [rsp+48h] [rbp-40h]

  v1 = *((_QWORD *)this + 8);
  v2 = (struct tagSIZE *)((char *)this + 56);
  v3 = *((_QWORD *)this + 7);
  v5 = *((_QWORD *)this + 88);
  if ( v5 )
  {
    rcDst = 0;
    if ( (*(int (__fastcall **)(__int64, struct tagRECT *))(*(_QWORD *)v5 + 224LL))(v5, &rcDst) >= 0 )
    {
      v2->cx = rcDst.right - rcDst.left;
      *((_DWORD *)this + 15) = rcDst.bottom - rcDst.top;
    }
    else
    {
      CVidCtl::GetSourceSize(this, v2);
    }
  }
  if ( (*((_DWORD *)this + 26) & 0x200) != 0 )
  {
    CVidCtl::ComputeDisplaySize(this);
    if ( v3 != *v2 || v1 != *((_QWORD *)this + 8) )
    {
      CopyRect(&rcDst, (const RECT *)((char *)this + 72));
      v8 = 1;
      v9 = -1;
      if ( !(unsigned __int8)CScalingRect::operator==((RECT *)this + 25) )
      {
        v6 = *((_QWORD *)this + 56);
        if ( v6 )
          PostMessageW(*(HWND *)(v6 + 8), 0x401u, 0, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x1800d1dac  push    rbx
0x1800d1dae  push    rsi
0x1800d1daf  push    rdi
0x1800d1db0  push    r14
0x1800d1db2  sub     rsp, 68h
0x1800d1db6  mov     rax, cs:__security_cookie
0x1800d1dbd  xor     rax, rsp
0x1800d1dc0  mov     [rsp+88h+var_38], rax
0x1800d1dc5  mov     rbx, [rcx+40h]
0x1800d1dc9  lea     r14, [rcx+38h]
0x1800d1dcd  mov     rdi, [r14]
0x1800d1dd0  mov     rsi, rcx
0x1800d1dd3  mov     rcx, [rcx+2C0h]
0x1800d1dda  mov     [rsp+88h+var_68], rdi
0x1800d1ddf  mov     [rsp+88h+var_60], rbx
0x1800d1de4  test    rcx, rcx
0x1800d1de7  jz      short loc_1800D1E2D
0x1800d1de9  xorps   xmm0, xmm0
0x1800d1dec  lea     rdx, [rsp+88h+rcDst]
0x1800d1df1  movdqu  xmmword ptr [rsp+88h+rcDst.left], xmm0
0x1800d1df7  mov     rax, [rcx]
0x1800d1dfa  mov     rax, [rax+0E0h]
0x1800d1e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e06  test    eax, eax
0x1800d1e08  jns     short loc_1800D1E17
0x1800d1e0a  mov     rdx, r14; struct tagSIZE *
0x1800d1e0d  mov     rcx, rsi; this
0x1800d1e10  call    ?GetSourceSize@CVidCtl@@IEAAXAEAUtagSIZE@@@Z; CVidCtl::GetSourceSize(tagSIZE &)
0x1800d1e15  jmp     short loc_1800D1E2D
0x1800d1e17  mov     eax, [rsp+88h+rcDst.right]
0x1800d1e1b  sub     eax, [rsp+88h+rcDst.left]
0x1800d1e1f  mov     [r14], eax
0x1800d1e22  mov     eax, [rsp+88h+rcDst.bottom]
0x1800d1e26  sub     eax, [rsp+88h+rcDst.top]
0x1800d1e2a  mov     [rsi+3Ch], eax
0x1800d1e2d  test    dword ptr [rsi+68h], 200h
0x1800d1e34  jz      short loc_1800D1EB4
0x1800d1e36  mov     rcx, rsi; this
0x1800d1e39  call    ?ComputeDisplaySize@CVidCtl@@IEAAXXZ; CVidCtl::ComputeDisplaySize(void)
0x1800d1e3e  mov     rax, [r14]
0x1800d1e41  cmp     edi, eax
0x1800d1e43  jnz     short loc_1800D1E61
0x1800d1e45  shr     rax, 20h
0x1800d1e49  cmp     dword ptr [rsp+88h+var_68+4], eax
0x1800d1e4d  jnz     short loc_1800D1E61
0x1800d1e4f  mov     rax, [rsi+40h]
0x1800d1e53  cmp     ebx, eax
0x1800d1e55  jnz     short loc_1800D1E61
0x1800d1e57  shr     rax, 20h
0x1800d1e5b  cmp     dword ptr [rsp+88h+var_60+4], eax
0x1800d1e5f  jz      short loc_1800D1EB4
0x1800d1e61  lea     rdx, [rsi+48h]; lprcSrc
0x1800d1e65  lea     rcx, [rsp+88h+rcDst]; lprcDst
0x1800d1e6a  call    cs:__imp_CopyRect
0x1800d1e70  lea     rcx, [rsi+190h]; lprc1
0x1800d1e77  mov     [rsp+88h+var_48], 1
0x1800d1e7c  lea     rdx, [rsp+88h+rcDst]
0x1800d1e81  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800d1e8a  call    ??8CScalingRect@@QEBA_NAEBV0@@Z; CScalingRect::operator==(CScalingRect const &)
0x1800d1e8f  test    al, al
0x1800d1e91  jnz     short loc_1800D1EB4
0x1800d1e93  mov     rcx, [rsi+1C0h]
0x1800d1e9a  test    rcx, rcx
0x1800d1e9d  jz      short loc_1800D1EB4
0x1800d1e9f  mov     rcx, [rcx+8]; hWnd
0x1800d1ea3  xor     r9d, r9d; lParam
0x1800d1ea6  xor     r8d, r8d; wParam
0x1800d1ea9  mov     edx, 401h; Msg
0x1800d1eae  call    cs:__imp_PostMessageW
0x1800d1eb4  mov     rcx, [rsp+88h+var_38]
0x1800d1eb9  xor     rcx, rsp; StackCookie
0x1800d1ebc  call    __security_check_cookie
0x1800d1ec1  add     rsp, 68h
0x1800d1ec5  pop     r14
0x1800d1ec7  pop     rdi
0x1800d1ec8  pop     rsi
0x1800d1ec9  pop     rbx
0x1800d1eca  retn
```
