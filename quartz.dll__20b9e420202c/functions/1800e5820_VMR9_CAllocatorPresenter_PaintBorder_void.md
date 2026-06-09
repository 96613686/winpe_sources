# VMR9::CAllocatorPresenter::PaintBorder(void)

- ea: `0x1800e5820`
- end: `0x1800e5a20`
- name: `?PaintBorder@CAllocatorPresenter@VMR9@@AEAAJXZ`
- size: `512`
- prototype: `__int64 __fastcall(VMR9::CAllocatorPresenter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800e5cbc`
- `0x1800e5f80`
- `0x1800e60b0`

## callees

- `0x1800388a0`
- `0x1800e5820`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800e59fc`
- `KERNEL32!LeaveCriticalSection` at `0x1800e59fc`
- `KERNEL32!EnterCriticalSection` at `0x1800e5841`
- `KERNEL32!EnterCriticalSection` at `0x1800e5841`
- `USER32!IntersectRect` at `0x1800e58ca`
- `USER32!IntersectRect` at `0x1800e5980`
- `USER32!IntersectRect` at `0x1800e58ca`
- `USER32!IntersectRect` at `0x1800e5980`
- `USER32!MapWindowPoints` at `0x1800e589a`
- `USER32!MapWindowPoints` at `0x1800e58fb`
- `USER32!MapWindowPoints` at `0x1800e5961`
- `USER32!MapWindowPoints` at `0x1800e59b1`
- `USER32!MapWindowPoints` at `0x1800e589a`
- `USER32!MapWindowPoints` at `0x1800e58fb`
- `USER32!MapWindowPoints` at `0x1800e5961`
- `USER32!MapWindowPoints` at `0x1800e59b1`
- `USER32!IsRectEmpty` at `0x1800e58da`
- `USER32!IsRectEmpty` at `0x1800e5990`
- `USER32!IsRectEmpty` at `0x1800e58da`
- `USER32!IsRectEmpty` at `0x1800e5990`

## pseudocode

```c
__int64 __fastcall VMR9::CAllocatorPresenter::PaintBorder(VMR9::CAllocatorPresenter *this)
{
  __int128 v2; // xmm1
  HWND v3; // rcx
  __int64 v4; // r8
  unsigned int v5; // edi
  HWND v6; // rcx
  struct tagRECT rcDst; // [rsp+30h] [rbp-48h] BYREF
  struct tagPOINT Points[2]; // [rsp+40h] [rbp-38h] BYREF
  __m128i si128; // [rsp+50h] [rbp-28h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( (*((_BYTE *)this + 24056) & 1) != 0 || *((_DWORD *)this + 6008) != 1 )
  {
    v5 = 0;
  }
  else
  {
    v2 = *((_OWORD *)this + 1498);
    v3 = (HWND)*((_QWORD *)this + 3005);
    rcDst = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(_OWORD *)&Points[0].x = v2;
    MapWindowPoints(v3, 0, Points, 2u);
    v4 = *((_QWORD *)this + 2976);
    if ( v4 )
    {
      v5 = 0;
      IntersectRect(&rcDst, (const RECT *)Points, (const RECT *)(v4 + 4));
      if ( IsRectEmpty(&rcDst)
        || (MapWindowPoints(0, *((HWND *)this + 3005), (LPPOINT)&rcDst, 2u),
            (v5 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, struct tagRECT *, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2976) + 1472LL)
                                                                                                 + 136LL))(
                    *(_QWORD *)(*((_QWORD *)this + 2976) + 1472LL),
                    &si128,
                    &rcDst,
                    *((_QWORD *)this + 3005),
                    0)) == 0) )
      {
        v6 = (HWND)*((_QWORD *)this + 3005);
        *(_OWORD *)&Points[0].x = *((_OWORD *)this + 1499);
        MapWindowPoints(v6, 0, Points, 2u);
        IntersectRect(&rcDst, (const RECT *)Points, (const RECT *)(*((_QWORD *)this + 2976) + 4LL));
        if ( !IsRectEmpty(&rcDst) )
        {
          MapWindowPoints(0, *((HWND *)this + 3005), (LPPOINT)&rcDst, 2u);
          v5 = (*(__int64 (__fastcall **)(_QWORD, __m128i *, struct tagRECT *, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 2976) + 1472LL)
                                                                                              + 136LL))(
                 *(_QWORD *)(*((_QWORD *)this + 2976) + 1472LL),
                 &si128,
                 &rcDst,
                 *((_QWORD *)this + 3005),
                 0);
        }
      }
    }
    else
    {
      v5 = -2147418113;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return v5;
}

```

## disassembly

```asm
0x1800e5820  push    rbp
0x1800e5822  push    rbx
0x1800e5823  push    rsi
0x1800e5824  push    rdi
0x1800e5825  mov     rbp, rsp
0x1800e5828  sub     rsp, 78h
0x1800e582c  mov     rax, cs:__security_cookie
0x1800e5833  xor     rax, rsp
0x1800e5836  mov     [rbp+var_18], rax
0x1800e583a  mov     rbx, rcx
0x1800e583d  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800e5841  call    cs:__imp_EnterCriticalSection
0x1800e5848  nop     dword ptr [rax+rax+00h]
0x1800e584d  test    byte ptr [rbx+5DF8h], 1
0x1800e5854  jnz     loc_1800E59F6
0x1800e585a  cmp     dword ptr [rbx+5DE0h], 1
0x1800e5861  jnz     loc_1800E59F6
0x1800e5867  movups  xmm1, xmmword ptr [rbx+5DA0h]
0x1800e586e  mov     rcx, [rbx+5DE8h]; hWndFrom
0x1800e5875  lea     r8, [rbp+Points]; lpPoints
0x1800e5879  xorps   xmm0, xmm0
0x1800e587c  mov     r9d, 2; cPoints
0x1800e5882  movups  xmmword ptr [rbp+rcDst.left], xmm0
0x1800e5886  xor     edx, edx; hWndTo
0x1800e5888  movdqa  xmm0, cs:__xmm@00000008000000080000000000000000
0x1800e5890  movdqu  [rbp+var_28], xmm0
0x1800e5895  movdqu  xmmword ptr [rbp+Points.x], xmm1
0x1800e589a  call    cs:__imp_MapWindowPoints
0x1800e58a1  nop     dword ptr [rax+rax+00h]
0x1800e58a6  mov     r8, [rbx+5D00h]
0x1800e58ad  test    r8, r8
0x1800e58b0  jnz     short loc_1800E58BC
0x1800e58b2  mov     edi, 8000FFFFh
0x1800e58b7  jmp     loc_1800E59F8
0x1800e58bc  add     r8, 4; lprcSrc2
0x1800e58c0  lea     rdx, [rbp+Points]; lprcSrc1
0x1800e58c4  lea     rcx, [rbp+rcDst]; lprcDst
0x1800e58c8  xor     edi, edi
0x1800e58ca  call    cs:__imp_IntersectRect
0x1800e58d1  nop     dword ptr [rax+rax+00h]
0x1800e58d6  lea     rcx, [rbp+rcDst]; lprc
0x1800e58da  call    cs:__imp_IsRectEmpty
0x1800e58e1  nop     dword ptr [rax+rax+00h]
0x1800e58e6  test    eax, eax
0x1800e58e8  jnz     short loc_1800E5942
0x1800e58ea  mov     rdx, [rbx+5DE8h]; hWndTo
0x1800e58f1  lea     r9d, [rdi+2]; cPoints
0x1800e58f5  lea     r8, [rbp+rcDst]; lpPoints
0x1800e58f9  xor     ecx, ecx; hWndFrom
0x1800e58fb  call    cs:__imp_MapWindowPoints
0x1800e5902  nop     dword ptr [rax+rax+00h]
0x1800e5907  mov     rax, [rbx+5D00h]
0x1800e590e  lea     r8, [rbp+rcDst]
0x1800e5912  mov     r9, [rbx+5DE8h]
0x1800e5919  lea     rdx, [rbp+var_28]
0x1800e591d  mov     [rsp+78h+var_58], rdi
0x1800e5922  mov     rcx, [rax+5C0h]
0x1800e5929  mov     rax, [rcx]
0x1800e592c  mov     rax, [rax+88h]
0x1800e5933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5938  mov     edi, eax
0x1800e593a  test    eax, eax
0x1800e593c  jnz     loc_1800E59F8
0x1800e5942  movups  xmm0, xmmword ptr [rbx+5DB0h]
0x1800e5949  mov     rcx, [rbx+5DE8h]; hWndFrom
0x1800e5950  lea     r8, [rbp+Points]; lpPoints
0x1800e5954  mov     r9d, 2; cPoints
0x1800e595a  xor     edx, edx; hWndTo
0x1800e595c  movdqu  xmmword ptr [rbp+Points.x], xmm0
0x1800e5961  call    cs:__imp_MapWindowPoints
0x1800e5968  nop     dword ptr [rax+rax+00h]
0x1800e596d  mov     r8, [rbx+5D00h]
0x1800e5974  lea     rdx, [rbp+Points]; lprcSrc1
0x1800e5978  add     r8, 4; lprcSrc2
0x1800e597c  lea     rcx, [rbp+rcDst]; lprcDst
0x1800e5980  call    cs:__imp_IntersectRect
0x1800e5987  nop     dword ptr [rax+rax+00h]
0x1800e598c  lea     rcx, [rbp+rcDst]; lprc
0x1800e5990  call    cs:__imp_IsRectEmpty
0x1800e5997  nop     dword ptr [rax+rax+00h]
0x1800e599c  test    eax, eax
0x1800e599e  jnz     short loc_1800E59F8
0x1800e59a0  mov     rdx, [rbx+5DE8h]; hWndTo
0x1800e59a7  lea     r9d, [rax+2]; cPoints
0x1800e59ab  lea     r8, [rbp+rcDst]; lpPoints
0x1800e59af  xor     ecx, ecx; hWndFrom
0x1800e59b1  call    cs:__imp_MapWindowPoints
0x1800e59b8  nop     dword ptr [rax+rax+00h]
0x1800e59bd  mov     rax, [rbx+5D00h]
0x1800e59c4  lea     r8, [rbp+rcDst]
0x1800e59c8  mov     r9, [rbx+5DE8h]
0x1800e59cf  lea     rdx, [rbp+var_28]
0x1800e59d3  mov     [rsp+78h+var_58], 0
0x1800e59dc  mov     rcx, [rax+5C0h]
0x1800e59e3  mov     rax, [rcx]
0x1800e59e6  mov     rax, [rax+88h]
0x1800e59ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e59f2  mov     edi, eax
0x1800e59f4  jmp     short loc_1800E59F8
0x1800e59f6  xor     edi, edi
0x1800e59f8  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800e59fc  call    cs:__imp_LeaveCriticalSection
0x1800e5a03  nop     dword ptr [rax+rax+00h]
0x1800e5a08  mov     eax, edi
0x1800e5a0a  mov     rcx, [rbp+var_18]
0x1800e5a0e  xor     rcx, rsp; StackCookie
0x1800e5a11  call    __security_check_cookie
0x1800e5a16  add     rsp, 78h
0x1800e5a1a  pop     rdi
0x1800e5a1b  pop     rsi
0x1800e5a1c  pop     rbx
0x1800e5a1d  pop     rbp
0x1800e5a1e  retn
```
