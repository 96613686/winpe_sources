# CWindow::accLocation(long *,long *,long *,long *,tagVARIANT)

- ea: `0x1800180f0`
- end: `0x180018255`
- name: `?accLocation@CWindow@@UEAAJPEAJ000UtagVARIANT@@@Z`
- size: `357`
- prototype: `__int64 __fastcall(CWindow *__hidden this, int *, int *, int *, int *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800397a0`

## callees

- `0x180008870`
- `0x1800180f0`
- `0x18001e4c0`
- `0x180049010`

## import_xrefs

- `USER32!SetRectEmpty` at `0x180018167`
- `USER32!SetRectEmpty` at `0x180018167`
- `USER32!GetWindowRect` at `0x180018174`
- `USER32!GetWindowRect` at `0x180018174`

## pseudocode

```c
__int64 __fastcall CWindow::accLocation(CWindow *this, int *a2, int *a3, int *a4, int *a5, struct tagVARIANT *a6)
{
  __int64 v9; // rax
  LONG lVal; // r9d
  HWND v12; // rdi
  LONG top; // edx
  int v14; // eax
  __int64 result; // rax
  unsigned int v16; // edx
  unsigned int v17; // ecx
  HWND v18; // r8
  void *v19; // rcx
  IRecordInfo *pRecInfo; // xmm1_8
  __int64 (__fastcall *v21)(void *, int *, int *, int *, int *, __int128 *); // rax
  unsigned int v22; // ebx
  void *v23; // [rsp+40h] [rbp-49h] BYREF
  __int128 v24; // [rsp+50h] [rbp-39h] BYREF
  IRecordInfo *v25; // [rsp+60h] [rbp-29h]
  struct tagRECT rc; // [rsp+70h] [rbp-19h] BYREF

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v9 = *(_QWORD *)this;
  rc = 0;
  if ( !(*(unsigned int (__fastcall **)(CWindow *, struct tagVARIANT *))(v9 + 240))(this, a6) )
    return 2147942487LL;
  lVal = a6->lVal;
  v12 = (HWND)*((_QWORD *)this + 10);
  if ( lVal )
  {
    v16 = *((_DWORD *)this + 17);
    v17 = *((_DWORD *)this + 25);
    v18 = (HWND)*((_QWORD *)this + 10);
    v23 = 0;
    result = AccessibleObjectFromWindowTimeout(v17, v16, v18, lVal, &IID_IAccessible, &v23);
    if ( (int)result >= 0 )
    {
      v19 = v23;
      if ( v23 )
      {
        a6->lVal = 0;
        pRecInfo = a6->pRecInfo;
        v21 = *(__int64 (__fastcall **)(void *, int *, int *, int *, int *, __int128 *))(*(_QWORD *)v19 + 176LL);
        v24 = *(_OWORD *)&a6->vt;
        v25 = pRecInfo;
        v22 = v21(v19, a2, a3, a4, a5, &v24);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
        return v22;
      }
      else
      {
        return 1;
      }
    }
  }
  else
  {
    SetRectEmpty(&rc);
    GetWindowRect(v12, &rc);
    top = rc.top;
    v14 = rc.right - rc.left;
    *a2 = rc.left;
    *a3 = top;
    *a4 = v14;
    *a5 = rc.bottom - top;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800180f0  push    rbp
0x1800180f2  push    rbx
0x1800180f3  push    rsi
0x1800180f4  push    rdi
0x1800180f5  push    r12
0x1800180f7  push    r13
0x1800180f9  push    r14
0x1800180fb  push    r15
0x1800180fd  lea     rbp, [rsp-0Fh]
0x180018102  sub     rsp, 98h
0x180018109  mov     rax, cs:__security_cookie
0x180018110  xor     rax, rsp
0x180018113  mov     [rbp+47h+var_50], rax
0x180018117  mov     r13, [rbp+47h+arg_20]
0x18001811b  xor     edi, edi
0x18001811d  mov     rsi, [rbp+47h+arg_28]
0x180018121  mov     r14, rdx
0x180018124  mov     [rdx], edi
0x180018126  xorps   xmm0, xmm0
0x180018129  mov     [r8], edi
0x18001812c  mov     rdx, rsi
0x18001812f  mov     [r9], edi
0x180018132  mov     r12, r9
0x180018135  mov     [r13+0], edi
0x180018139  mov     r15, r8
0x18001813c  mov     rax, [rcx]
0x18001813f  mov     rbx, rcx
0x180018142  movups  xmmword ptr [rbp+47h+rc.left], xmm0
0x180018146  mov     rax, [rax+0F0h]
0x18001814d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018152  test    eax, eax
0x180018154  jz      short loc_1800181BA
0x180018156  mov     r9d, [rsi+8]
0x18001815a  mov     rdi, [rbx+50h]
0x18001815e  test    r9d, r9d
0x180018161  jnz     short loc_1800181C1
0x180018163  lea     rcx, [rbp+47h+rc]; lprc
0x180018167  call    cs:__imp_SetRectEmpty
0x18001816d  lea     rdx, [rbp+47h+rc]; lpRect
0x180018171  mov     rcx, rdi; hWnd
0x180018174  call    cs:__imp_GetWindowRect
0x18001817a  mov     ecx, [rbp+47h+rc.left]
0x18001817d  mov     edx, [rbp+47h+rc.top]
0x180018180  mov     eax, [rbp+47h+rc.right]
0x180018183  sub     eax, ecx
0x180018185  mov     [r14], ecx
0x180018188  mov     [r15], edx
0x18001818b  mov     [r12], eax
0x18001818f  mov     eax, [rbp+47h+rc.bottom]
0x180018192  sub     eax, edx
0x180018194  mov     [r13+0], eax
0x180018198  xor     eax, eax
0x18001819a  mov     rcx, [rbp+47h+var_50]
0x18001819e  xor     rcx, rsp; StackCookie
0x1800181a1  call    __security_check_cookie
0x1800181a6  add     rsp, 98h
0x1800181ad  pop     r15
0x1800181af  pop     r14
0x1800181b1  pop     r13
0x1800181b3  pop     r12
0x1800181b5  pop     rdi
0x1800181b6  pop     rsi
0x1800181b7  pop     rbx
0x1800181b8  pop     rbp
0x1800181b9  retn
0x1800181ba  mov     eax, 80070057h
0x1800181bf  jmp     short loc_18001819A
0x1800181c1  mov     edx, [rbx+44h]
0x1800181c4  lea     rax, [rbp+47h+var_90]
0x1800181c8  mov     ecx, [rbx+64h]
0x1800181cb  mov     r8, rdi
0x1800181ce  mov     [rsp+0D0h+var_A8], rax
0x1800181d3  lea     rax, IID_IAccessible
0x1800181da  mov     [rsp+0D0h+var_B0], rax
0x1800181df  mov     [rbp+47h+var_90], 0
0x1800181e7  call    AccessibleObjectFromWindowTimeout
0x1800181ec  test    eax, eax
0x1800181ee  js      short loc_18001819A
0x1800181f0  mov     rcx, [rbp+47h+var_90]
0x1800181f4  test    rcx, rcx
0x1800181f7  jnz     short loc_1800181FE
0x1800181f9  lea     eax, [rcx+1]
0x1800181fc  jmp     short loc_18001819A
0x1800181fe  mov     dword ptr [rsi+8], 0
0x180018205  lea     rdx, [rbp+47h+var_80]
0x180018209  mov     rax, [rcx]
0x18001820c  mov     r9, r12
0x18001820f  movups  xmm0, xmmword ptr [rsi]
0x180018212  mov     r8, r15
0x180018215  mov     [rsp+0D0h+var_A8], rdx
0x18001821a  movsd   xmm1, qword ptr [rsi+10h]
0x18001821f  mov     rdx, r14
0x180018222  mov     rax, [rax+0B0h]
0x180018229  movaps  [rbp+47h+var_80], xmm0
0x18001822d  movsd   [rbp+47h+var_70], xmm1
0x180018232  mov     [rsp+0D0h+var_B0], r13
0x180018237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001823c  mov     rcx, [rbp+47h+var_90]
0x180018240  mov     ebx, eax
0x180018242  mov     rdx, [rcx]
0x180018245  mov     rax, [rdx+10h]
0x180018249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001824e  mov     eax, ebx
0x180018250  jmp     loc_18001819A
```
