# CAllocatorPresenter::PaintBorder(void)

- ea: `0x1800bc9a0`
- end: `0x1800bcbe5`
- name: `?PaintBorder@CAllocatorPresenter@@AEAAJXZ`
- size: `581`
- prototype: `__int64 __fastcall(CAllocatorPresenter *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800bd27c`
- `0x1800bd580`
- `0x1800bd6a0`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x1800bc9a0`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800bcbb2`
- `KERNEL32!LeaveCriticalSection` at `0x1800bcbb2`
- `KERNEL32!EnterCriticalSection` at `0x1800bc9cf`
- `KERNEL32!EnterCriticalSection` at `0x1800bc9cf`
- `USER32!IntersectRect` at `0x1800bca73`
- `USER32!IntersectRect` at `0x1800bcb30`
- `USER32!IntersectRect` at `0x1800bca73`
- `USER32!IntersectRect` at `0x1800bcb30`
- `USER32!MapWindowPoints` at `0x1800bca54`
- `USER32!MapWindowPoints` at `0x1800bcb11`
- `USER32!MapWindowPoints` at `0x1800bca54`
- `USER32!MapWindowPoints` at `0x1800bcb11`
- `USER32!OffsetRect` at `0x1800bcaaa`
- `USER32!OffsetRect` at `0x1800bcb67`
- `USER32!OffsetRect` at `0x1800bcaaa`
- `USER32!OffsetRect` at `0x1800bcb67`
- `USER32!IsRectEmpty` at `0x1800bca83`
- `USER32!IsRectEmpty` at `0x1800bcb40`
- `USER32!IsRectEmpty` at `0x1800bca83`
- `USER32!IsRectEmpty` at `0x1800bcb40`

## pseudocode

```c
__int64 __fastcall CAllocatorPresenter::PaintBorder(CAllocatorPresenter *this)
{
  __int64 v2; // r14
  unsigned int v3; // edi
  __int128 v4; // xmm0
  HWND v5; // rcx
  HWND v6; // rcx
  int v8; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v9[100]; // [rsp+44h] [rbp-65h] BYREF
  int v10; // [rsp+A8h] [rbp-1h]
  struct tagRECT rcDst; // [rsp+C0h] [rbp+17h] BYREF
  struct tagPOINT Points[2]; // [rsp+D0h] [rbp+27h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( (*((_BYTE *)this + 34652) & 8) != 0 || *((_DWORD *)this + 8651) != 1 )
  {
    v3 = 0;
  }
  else
  {
    v2 = *((_QWORD *)this + 4287);
    if ( v2 )
    {
      v3 = 0;
      rcDst = 0;
      memset_0(v9, 0, 0x7Cu);
      v4 = *(_OWORD *)((char *)this + 34540);
      v5 = (HWND)*((_QWORD *)this + 4326);
      v8 = 128;
      v10 = *(_DWORD *)(v2 + 2128);
      *(_OWORD *)&Points[0].x = v4;
      MapWindowPoints(v5, 0, Points, 2u);
      IntersectRect(&rcDst, (const RECT *)Points, (const RECT *)(*((_QWORD *)this + 4287) + 24LL));
      if ( IsRectEmpty(&rcDst)
        || (OffsetRect(
              &rcDst,
              -*(_DWORD *)(*((_QWORD *)this + 4287) + 24LL),
              -*(_DWORD *)(*((_QWORD *)this + 4287) + 28LL)),
            (v3 = (*(__int64 (__fastcall **)(_QWORD, struct tagRECT *, _QWORD, _QWORD, int, int *))(**(_QWORD **)(*((_QWORD *)this + 4287) + 2120LL)
                                                                                                  + 40LL))(
                    *(_QWORD *)(*((_QWORD *)this + 4287) + 2120LL),
                    &rcDst,
                    0,
                    0,
                    16778240,
                    &v8)) == 0) )
      {
        v6 = (HWND)*((_QWORD *)this + 4326);
        *(_OWORD *)&Points[0].x = *(_OWORD *)((char *)this + 34556);
        MapWindowPoints(v6, 0, Points, 2u);
        IntersectRect(&rcDst, (const RECT *)Points, (const RECT *)(*((_QWORD *)this + 4287) + 24LL));
        if ( !IsRectEmpty(&rcDst) )
        {
          OffsetRect(
            &rcDst,
            -*(_DWORD *)(*((_QWORD *)this + 4287) + 24LL),
            -*(_DWORD *)(*((_QWORD *)this + 4287) + 28LL));
          v3 = (*(__int64 (__fastcall **)(_QWORD, struct tagRECT *, _QWORD, _QWORD, int, int *))(**(_QWORD **)(*((_QWORD *)this + 4287) + 2120LL)
                                                                                               + 40LL))(
                 *(_QWORD *)(*((_QWORD *)this + 4287) + 2120LL),
                 &rcDst,
                 0,
                 0,
                 16778240,
                 &v8);
        }
      }
    }
    else
    {
      v3 = -2147467259;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return v3;
}

```

## disassembly

```asm
0x1800bc9a0  mov     [rsp-8+arg_8], rbx
0x1800bc9a5  mov     [rsp-8+arg_10], rsi
0x1800bc9aa  push    rbp
0x1800bc9ab  push    rdi
0x1800bc9ac  push    r14
0x1800bc9ae  lea     rbp, [rsp-47h]
0x1800bc9b3  sub     rsp, 0F0h
0x1800bc9ba  mov     rax, cs:__security_cookie
0x1800bc9c1  xor     rax, rsp
0x1800bc9c4  mov     [rbp+57h+var_20], rax
0x1800bc9c8  mov     rbx, rcx
0x1800bc9cb  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800bc9cf  call    cs:__imp_EnterCriticalSection
0x1800bc9d6  nop     dword ptr [rax+rax+00h]
0x1800bc9db  test    byte ptr [rbx+875Ch], 8
0x1800bc9e2  jnz     loc_1800BCBAC
0x1800bc9e8  cmp     dword ptr [rbx+872Ch], 1
0x1800bc9ef  jnz     loc_1800BCBAC
0x1800bc9f5  mov     r14, [rbx+85F8h]
0x1800bc9fc  test    r14, r14
0x1800bc9ff  jnz     short loc_1800BCA0B
0x1800bca01  mov     edi, 80004005h
0x1800bca06  jmp     loc_1800BCBAE
0x1800bca0b  xorps   xmm0, xmm0
0x1800bca0e  lea     rcx, [rbp+57h+var_BC]; void *
0x1800bca12  xor     edi, edi
0x1800bca14  xor     edx, edx; Val
0x1800bca16  movups  xmmword ptr [rbp+57h+rcDst.left], xmm0
0x1800bca1a  lea     r8d, [rdi+7Ch]; Size
0x1800bca1e  call    memset_0
0x1800bca23  movups  xmm0, xmmword ptr [rbx+86ECh]
0x1800bca2a  mov     rcx, [rbx+8730h]; hWndFrom
0x1800bca31  lea     r8, [rbp+57h+Points]; lpPoints
0x1800bca35  mov     [rbp+57h+var_C0], 80h
0x1800bca3c  xor     edx, edx; hWndTo
0x1800bca3e  mov     eax, [r14+850h]
0x1800bca45  lea     r14d, [rdi+2]
0x1800bca49  mov     r9d, r14d; cPoints
0x1800bca4c  mov     [rbp+57h+var_58], eax
0x1800bca4f  movdqu  xmmword ptr [rbp+57h+Points.x], xmm0
0x1800bca54  call    cs:__imp_MapWindowPoints
0x1800bca5b  nop     dword ptr [rax+rax+00h]
0x1800bca60  mov     r8, [rbx+85F8h]
0x1800bca67  lea     rdx, [rbp+57h+Points]; lprcSrc1
0x1800bca6b  add     r8, 18h; lprcSrc2
0x1800bca6f  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800bca73  call    cs:__imp_IntersectRect
0x1800bca7a  nop     dword ptr [rax+rax+00h]
0x1800bca7f  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800bca83  call    cs:__imp_IsRectEmpty
0x1800bca8a  nop     dword ptr [rax+rax+00h]
0x1800bca8f  test    eax, eax
0x1800bca91  jnz     short loc_1800BCAF5
0x1800bca93  mov     rax, [rbx+85F8h]
0x1800bca9a  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800bca9e  mov     r8d, [rax+1Ch]
0x1800bcaa2  mov     edx, [rax+18h]
0x1800bcaa5  neg     r8d; dy
0x1800bcaa8  neg     edx; dx
0x1800bcaaa  call    cs:__imp_OffsetRect
0x1800bcab1  nop     dword ptr [rax+rax+00h]
0x1800bcab6  mov     rax, [rbx+85F8h]
0x1800bcabd  lea     rdx, [rbp+57h+var_C0]
0x1800bcac1  mov     [rsp+100h+var_D8], rdx
0x1800bcac6  xor     r9d, r9d
0x1800bcac9  xor     r8d, r8d
0x1800bcacc  mov     [rsp+100h+var_E0], 1000400h
0x1800bcad4  lea     rdx, [rbp+57h+rcDst]
0x1800bcad8  mov     rcx, [rax+848h]
0x1800bcadf  mov     rax, [rcx]
0x1800bcae2  mov     rax, [rax+28h]
0x1800bcae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcaeb  mov     edi, eax
0x1800bcaed  test    eax, eax
0x1800bcaef  jnz     loc_1800BCBAE
0x1800bcaf5  movups  xmm0, xmmword ptr [rbx+86FCh]
0x1800bcafc  mov     rcx, [rbx+8730h]; hWndFrom
0x1800bcb03  lea     r8, [rbp+57h+Points]; lpPoints
0x1800bcb07  mov     r9d, r14d; cPoints
0x1800bcb0a  xor     edx, edx; hWndTo
0x1800bcb0c  movdqu  xmmword ptr [rbp+57h+Points.x], xmm0
0x1800bcb11  call    cs:__imp_MapWindowPoints
0x1800bcb18  nop     dword ptr [rax+rax+00h]
0x1800bcb1d  mov     r8, [rbx+85F8h]
0x1800bcb24  lea     rdx, [rbp+57h+Points]; lprcSrc1
0x1800bcb28  add     r8, 18h; lprcSrc2
0x1800bcb2c  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x1800bcb30  call    cs:__imp_IntersectRect
0x1800bcb37  nop     dword ptr [rax+rax+00h]
0x1800bcb3c  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800bcb40  call    cs:__imp_IsRectEmpty
0x1800bcb47  nop     dword ptr [rax+rax+00h]
0x1800bcb4c  test    eax, eax
0x1800bcb4e  jnz     short loc_1800BCBAE
0x1800bcb50  mov     rax, [rbx+85F8h]
0x1800bcb57  lea     rcx, [rbp+57h+rcDst]; lprc
0x1800bcb5b  mov     r8d, [rax+1Ch]
0x1800bcb5f  mov     edx, [rax+18h]
0x1800bcb62  neg     r8d; dy
0x1800bcb65  neg     edx; dx
0x1800bcb67  call    cs:__imp_OffsetRect
0x1800bcb6e  nop     dword ptr [rax+rax+00h]
0x1800bcb73  mov     rax, [rbx+85F8h]
0x1800bcb7a  lea     rdx, [rbp+57h+var_C0]
0x1800bcb7e  mov     [rsp+100h+var_D8], rdx
0x1800bcb83  xor     r9d, r9d
0x1800bcb86  xor     r8d, r8d
0x1800bcb89  mov     [rsp+100h+var_E0], 1000400h
0x1800bcb91  lea     rdx, [rbp+57h+rcDst]
0x1800bcb95  mov     rcx, [rax+848h]
0x1800bcb9c  mov     rax, [rcx]
0x1800bcb9f  mov     rax, [rax+28h]
0x1800bcba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcba8  mov     edi, eax
0x1800bcbaa  jmp     short loc_1800BCBAE
0x1800bcbac  xor     edi, edi
0x1800bcbae  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800bcbb2  call    cs:__imp_LeaveCriticalSection
0x1800bcbb9  nop     dword ptr [rax+rax+00h]
0x1800bcbbe  mov     eax, edi
0x1800bcbc0  mov     rcx, [rbp+57h+var_20]
0x1800bcbc4  xor     rcx, rsp; StackCookie
0x1800bcbc7  call    __security_check_cookie
0x1800bcbcc  lea     r11, [rsp+100h+var_10]
0x1800bcbd4  mov     rbx, [r11+28h]
0x1800bcbd8  mov     rsi, [r11+30h]
0x1800bcbdc  mov     rsp, r11
0x1800bcbdf  pop     r14
0x1800bcbe1  pop     rdi
0x1800bcbe2  pop     rbp
0x1800bcbe3  retn
```
