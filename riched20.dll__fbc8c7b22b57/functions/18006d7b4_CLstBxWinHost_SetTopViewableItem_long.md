# CLstBxWinHost::SetTopViewableItem(long)

- ea: `0x18006d7b4`
- end: `0x18006d955`
- name: `?SetTopViewableItem@CLstBxWinHost@@IEAAHJ@Z`
- size: `417`
- prototype: `__int64 __fastcall(CLstBxWinHost *__hidden this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180069b04`
- `0x18006b484`
- `0x18006b628`

## callees

- `0x180068c90`
- `0x18006d020`
- `0x18006d1c0`
- `0x18006d7b4`
- `0x180093c00`
- `0x180095010`

## import_xrefs

- `USER32!UpdateWindow` at `0x18006d925`
- `USER32!UpdateWindow` at `0x18006d925`

## pseudocode

```c
__int64 __fastcall CLstBxWinHost::SetTopViewableItem(CLstBxWinHost *this, int a2)
{
  int v2; // eax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  CLstBxWinHost *v8; // rcx
  int v9; // r8d
  int v10; // r14d
  int v11; // edx
  unsigned int v12; // ebx
  CLstBxWinHost *v13; // rcx
  int v14; // r8d
  unsigned int v15; // ebx
  void (__fastcall *v16)(CLstBxWinHost *, __int128 *); // rax
  void (__fastcall *v17)(CLstBxWinHost *, _QWORD, _QWORD, _QWORD, __int128 *, _QWORD, _QWORD, int); // rax
  __int128 v18; // [rsp+50h] [rbp-38h] BYREF

  v2 = *((_DWORD *)this + 48);
  if ( v2 )
  {
    if ( a2 >= v2 )
      return 0;
    v6 = *((_DWORD *)this + 32);
    if ( (v6 & 1) != 0 )
    {
      v15 = *((_DWORD *)this + 46) * (*((_DWORD *)this + 31) - a2);
      v16 = *(void (__fastcall **)(CLstBxWinHost *, __int128 *))(*(_QWORD *)this + 192LL);
      v18 = 0;
      v16(this, &v18);
      v17 = *(void (__fastcall **)(CLstBxWinHost *, _QWORD, _QWORD, _QWORD, __int128 *, _QWORD, _QWORD, int))(*(_QWORD *)this + 128LL);
      *((_DWORD *)this + 31) = a2;
      v17(this, 0, v15, 0, &v18, 0, 0, 7);
      (*(void (__fastcall **)(CLstBxWinHost *, __int64, __int64))(*(_QWORD *)this + 416LL))(this, 1, 1);
      UpdateWindow(*((HWND *)this + 2));
      return 1;
    }
    v7 = v6 >> 7;
    *((_DWORD *)this + 32) = v6 & 0xFFFFFF7F;
    if ( (v6 & 0x80) != 0 && (unsigned int)CLstBxWinHost::IsItemViewable(this, *((_DWORD *)this + 50)) )
      CLstBxWinHost::SetCursor(v8, 0, v9, 1);
    v10 = *((_DWORD *)this + 31);
    *((_DWORD *)this + 31) = a2;
    if ( !CLstBxWinHost::ScrollToView(this, a2) )
    {
      if ( *((int *)this + 52) >= 0 )
        return 1;
      *((_DWORD *)this + 31) = v10;
    }
    v11 = *((_DWORD *)this + 50);
    v12 = *((_DWORD *)this + 32) ^ ((unsigned __int8)*((_DWORD *)this + 32) ^ (unsigned __int8)((_BYTE)v7 << 7)) & 0x80;
    *((_DWORD *)this + 32) = v12;
    if ( ((unsigned __int8)(v12 >> 7) & (unsigned __int8)CLstBxWinHost::IsItemViewable(this, v11) & 1) != 0 )
      CLstBxWinHost::SetCursor(v13, 0, v14, 0);
    return 1;
  }
  *((_DWORD *)this + 31) = 0;
  return 1;
}

```

## disassembly

```asm
0x18006d7b4  mov     [rsp+arg_10], rbx
0x18006d7b9  push    rbp
0x18006d7ba  push    rdi
0x18006d7bb  push    r14
0x18006d7bd  sub     rsp, 70h
0x18006d7c1  mov     rax, cs:__security_cookie
0x18006d7c8  xor     rax, rsp
0x18006d7cb  mov     [rsp+88h+var_28], rax
0x18006d7d0  mov     eax, [rcx+0C0h]
0x18006d7d6  mov     ebp, edx
0x18006d7d8  mov     rdi, rcx
0x18006d7db  test    eax, eax
0x18006d7dd  jnz     short loc_18006D7E7
0x18006d7df  mov     [rcx+7Ch], eax
0x18006d7e2  jmp     loc_18006D931
0x18006d7e7  cmp     ebp, eax
0x18006d7e9  jl      short loc_18006D7F2
0x18006d7eb  xor     eax, eax
0x18006d7ed  jmp     loc_18006D936
0x18006d7f2  mov     eax, [rcx+80h]
0x18006d7f8  test    al, 1
0x18006d7fa  jnz     loc_18006D89E
0x18006d800  mov     ebx, eax
0x18006d802  btr     eax, 7
0x18006d806  shr     ebx, 7
0x18006d809  mov     [rcx+80h], eax
0x18006d80f  test    bl, 1
0x18006d812  jz      short loc_18006D832
0x18006d814  mov     r8d, [rcx+0C8h]
0x18006d81b  mov     edx, r8d; int
0x18006d81e  call    ?IsItemViewable@CLstBxWinHost@@QEBAHJ@Z; CLstBxWinHost::IsItemViewable(long)
0x18006d823  test    eax, eax
0x18006d825  jz      short loc_18006D832
0x18006d827  xor     edx, edx; HDC
0x18006d829  lea     r9d, [rdx+1]; int
0x18006d82d  call    ?SetCursor@CLstBxWinHost@@QEAAXPEAUHDC__@@HH@Z; CLstBxWinHost::SetCursor(HDC__ *,int,int)
0x18006d832  mov     r14d, [rdi+7Ch]
0x18006d836  mov     edx, ebp; int
0x18006d838  mov     rcx, rdi; this
0x18006d83b  mov     [rdi+7Ch], ebp
0x18006d83e  call    ?ScrollToView@CLstBxWinHost@@IEAAHJ@Z; CLstBxWinHost::ScrollToView(long)
0x18006d843  test    eax, eax
0x18006d845  jnz     short loc_18006D857
0x18006d847  cmp     [rdi+0D0h], eax
0x18006d84d  jge     loc_18006D931
0x18006d853  mov     [rdi+7Ch], r14d
0x18006d857  mov     eax, [rdi+80h]
0x18006d85d  mov     rcx, rdi; this
0x18006d860  mov     r8d, [rdi+0C8h]
0x18006d867  mov     edx, r8d; int
0x18006d86a  shl     ebx, 7
0x18006d86d  xor     ebx, eax
0x18006d86f  and     ebx, 80h
0x18006d875  xor     ebx, eax
0x18006d877  mov     [rdi+80h], ebx
0x18006d87d  call    ?IsItemViewable@CLstBxWinHost@@QEBAHJ@Z; CLstBxWinHost::IsItemViewable(long)
0x18006d882  shr     ebx, 7
0x18006d885  and     eax, ebx
0x18006d887  test    al, 1
0x18006d889  jz      loc_18006D931
0x18006d88f  xor     r9d, r9d; int
0x18006d892  xor     edx, edx; HDC
0x18006d894  call    ?SetCursor@CLstBxWinHost@@QEAAXPEAUHDC__@@HH@Z; CLstBxWinHost::SetCursor(HDC__ *,int,int)
0x18006d899  jmp     loc_18006D931
0x18006d89e  mov     rax, [rcx]
0x18006d8a1  lea     rdx, [rsp+88h+var_38]
0x18006d8a6  mov     ebx, [rcx+7Ch]
0x18006d8a9  xorps   xmm0, xmm0
0x18006d8ac  sub     ebx, ebp
0x18006d8ae  imul    ebx, [rcx+0B8h]
0x18006d8b5  mov     rax, [rax+0C0h]
0x18006d8bc  movups  [rsp+88h+var_38], xmm0
0x18006d8c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d8c6  mov     rax, [rdi]
0x18006d8c9  lea     rcx, [rsp+88h+var_38]
0x18006d8ce  mov     [rsp+88h+var_50], 7
0x18006d8d6  xor     r9d, r9d
0x18006d8d9  mov     [rsp+88h+var_58], 0
0x18006d8e2  mov     r8d, ebx
0x18006d8e5  mov     [rsp+88h+var_60], 0
0x18006d8ee  xor     edx, edx
0x18006d8f0  mov     rax, [rax+80h]
0x18006d8f7  mov     [rsp+88h+var_68], rcx
0x18006d8fc  mov     rcx, rdi
0x18006d8ff  mov     [rdi+7Ch], ebp
0x18006d902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d907  mov     rax, [rdi]
0x18006d90a  mov     edx, 1
0x18006d90f  mov     r8d, edx
0x18006d912  mov     rcx, rdi
0x18006d915  mov     rax, [rax+1A0h]
0x18006d91c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d921  mov     rcx, [rdi+10h]; hWnd
0x18006d925  call    cs:__imp_UpdateWindow
0x18006d92c  nop     dword ptr [rax+rax+00h]
0x18006d931  mov     eax, 1
0x18006d936  mov     rcx, [rsp+88h+var_28]
0x18006d93b  xor     rcx, rsp; StackCookie
0x18006d93e  call    __security_check_cookie
0x18006d943  mov     rbx, [rsp+88h+arg_10]
0x18006d94b  add     rsp, 70h
0x18006d94f  pop     r14
0x18006d951  pop     rdi
0x18006d952  pop     rbp
0x18006d953  retn
```
