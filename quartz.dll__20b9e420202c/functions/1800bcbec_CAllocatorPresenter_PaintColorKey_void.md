# CAllocatorPresenter::PaintColorKey(void)

- ea: `0x1800bcbec`
- end: `0x1800bcd6b`
- name: `?PaintColorKey@CAllocatorPresenter@@AEAAJXZ`
- size: `383`
- prototype: `__int64 __fastcall(CAllocatorPresenter *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800bd0f0`
- `0x1800bd27c`
- `0x1800bda00`

## callees

- `0x1800388a0`
- `0x180039250`
- `0x1800bc94c`
- `0x1800bcbec`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800bcd40`
- `KERNEL32!LeaveCriticalSection` at `0x1800bcd40`
- `KERNEL32!EnterCriticalSection` at `0x1800bcc11`
- `KERNEL32!EnterCriticalSection` at `0x1800bcc11`
- `USER32!IntersectRect` at `0x1800bccaf`
- `USER32!IntersectRect` at `0x1800bccaf`
- `USER32!OffsetRect` at `0x1800bccf0`
- `USER32!OffsetRect` at `0x1800bccf0`
- `USER32!IsRectEmpty` at `0x1800bcc34`
- `USER32!IsRectEmpty` at `0x1800bccc5`
- `USER32!IsRectEmpty` at `0x1800bcc34`
- `USER32!IsRectEmpty` at `0x1800bccc5`

## pseudocode

```c
__int64 __fastcall CAllocatorPresenter::PaintColorKey(CAllocatorPresenter *this)
{
  unsigned int v2; // edi
  __int64 v3; // r8
  unsigned int v4; // edi
  _DWORD v6[32]; // [rsp+40h] [rbp-C8h] BYREF
  struct tagRECT rcDst; // [rsp+C0h] [rbp-48h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( (*((_BYTE *)this + 34652) & 8) != 0 || IsRectEmpty((const RECT *)((char *)this + 34492)) )
  {
    v4 = 0;
  }
  else
  {
    v2 = *((_DWORD *)this + 8662);
    if ( v2 == -1 )
    {
      v2 = CAllocatorPresenter::MapColorToMonitor(
             *((struct CAMDDrawMonitorInfo **)this + 4287),
             *((_DWORD *)this + 8655));
      *((_DWORD *)this + 8662) = v2;
    }
    memset_0(v6, 0, sizeof(v6));
    v3 = *((_QWORD *)this + 4287);
    v6[0] = 128;
    v6[26] = v2;
    rcDst = 0;
    IntersectRect(&rcDst, (const RECT *)((char *)this + 34492), (const RECT *)(v3 + 24));
    v4 = 0;
    if ( !IsRectEmpty(&rcDst) )
    {
      OffsetRect(&rcDst, -*(_DWORD *)(*((_QWORD *)this + 4287) + 24LL), -*(_DWORD *)(*((_QWORD *)this + 4287) + 28LL));
      v4 = (*(__int64 (__fastcall **)(_QWORD, struct tagRECT *, _QWORD, _QWORD, int, _DWORD *))(**(_QWORD **)(*((_QWORD *)this + 4287) + 2120LL)
                                                                                              + 40LL))(
             *(_QWORD *)(*((_QWORD *)this + 4287) + 2120LL),
             &rcDst,
             0,
             0,
             16778240,
             v6);
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  return v4;
}

```

## disassembly

```asm
0x1800bcbec  push    rbx
0x1800bcbee  push    rbp
0x1800bcbef  push    rsi
0x1800bcbf0  push    rdi
0x1800bcbf1  sub     rsp, 0E8h
0x1800bcbf8  mov     rax, cs:__security_cookie
0x1800bcbff  xor     rax, rsp
0x1800bcc02  mov     [rsp+108h+var_38], rax
0x1800bcc0a  mov     rbx, rcx
0x1800bcc0d  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800bcc11  call    cs:__imp_EnterCriticalSection
0x1800bcc18  nop     dword ptr [rax+rax+00h]
0x1800bcc1d  test    byte ptr [rbx+875Ch], 8
0x1800bcc24  jnz     loc_1800BCD3A
0x1800bcc2a  lea     rbp, [rbx+86BCh]
0x1800bcc31  mov     rcx, rbp; lprc
0x1800bcc34  call    cs:__imp_IsRectEmpty
0x1800bcc3b  nop     dword ptr [rax+rax+00h]
0x1800bcc40  test    eax, eax
0x1800bcc42  jnz     loc_1800BCD3A
0x1800bcc48  mov     edi, [rbx+8758h]
0x1800bcc4e  cmp     edi, 0FFFFFFFFh
0x1800bcc51  jnz     short loc_1800BCC6D
0x1800bcc53  mov     edx, [rbx+873Ch]; unsigned int
0x1800bcc59  mov     rcx, [rbx+85F8h]; struct CAMDDrawMonitorInfo *
0x1800bcc60  call    ?MapColorToMonitor@CAllocatorPresenter@@CAKAEAUCAMDDrawMonitorInfo@@K@Z; CAllocatorPresenter::MapColorToMonitor(CAMDDrawMonitorInfo &,ulong)
0x1800bcc65  mov     edi, eax
0x1800bcc67  mov     [rbx+8758h], eax
0x1800bcc6d  xor     edx, edx; Val
0x1800bcc6f  lea     rcx, [rsp+108h+var_C8]; void *
0x1800bcc74  mov     r8d, 80h; Size
0x1800bcc7a  call    memset_0
0x1800bcc7f  mov     r8, [rbx+85F8h]
0x1800bcc86  lea     rcx, [rsp+108h+rcDst]; lprcDst
0x1800bcc8e  xorps   xmm0, xmm0
0x1800bcc91  mov     [rsp+108h+var_C8], 80h
0x1800bcc99  add     r8, 18h; lprcSrc2
0x1800bcc9d  mov     [rsp+108h+var_60], edi
0x1800bcca4  mov     rdx, rbp; lprcSrc1
0x1800bcca7  movups  xmmword ptr [rsp+108h+rcDst.left], xmm0
0x1800bccaf  call    cs:__imp_IntersectRect
0x1800bccb6  nop     dword ptr [rax+rax+00h]
0x1800bccbb  lea     rcx, [rsp+108h+rcDst]; lprc
0x1800bccc3  xor     edi, edi
0x1800bccc5  call    cs:__imp_IsRectEmpty
0x1800bcccc  nop     dword ptr [rax+rax+00h]
0x1800bccd1  test    eax, eax
0x1800bccd3  jnz     short loc_1800BCD3C
0x1800bccd5  mov     rax, [rbx+85F8h]
0x1800bccdc  lea     rcx, [rsp+108h+rcDst]; lprc
0x1800bcce4  mov     r8d, [rax+1Ch]
0x1800bcce8  mov     edx, [rax+18h]
0x1800bcceb  neg     r8d; dy
0x1800bccee  neg     edx; dx
0x1800bccf0  call    cs:__imp_OffsetRect
0x1800bccf7  nop     dword ptr [rax+rax+00h]
0x1800bccfc  mov     rax, [rbx+85F8h]
0x1800bcd03  lea     rdx, [rsp+108h+var_C8]
0x1800bcd08  mov     [rsp+108h+var_E0], rdx
0x1800bcd0d  xor     r9d, r9d
0x1800bcd10  xor     r8d, r8d
0x1800bcd13  mov     [rsp+108h+var_E8], 1000400h
0x1800bcd1b  lea     rdx, [rsp+108h+rcDst]
0x1800bcd23  mov     rcx, [rax+848h]
0x1800bcd2a  mov     rax, [rcx]
0x1800bcd2d  mov     rax, [rax+28h]
0x1800bcd31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcd36  mov     edi, eax
0x1800bcd38  jmp     short loc_1800BCD3C
0x1800bcd3a  xor     edi, edi
0x1800bcd3c  lea     rcx, [rbx+48h]; lpCriticalSection
0x1800bcd40  call    cs:__imp_LeaveCriticalSection
0x1800bcd47  nop     dword ptr [rax+rax+00h]
0x1800bcd4c  mov     eax, edi
0x1800bcd4e  mov     rcx, [rsp+108h+var_38]
0x1800bcd56  xor     rcx, rsp; StackCookie
0x1800bcd59  call    __security_check_cookie
0x1800bcd5e  add     rsp, 0E8h
0x1800bcd65  pop     rdi
0x1800bcd66  pop     rsi
0x1800bcd67  pop     rbp
0x1800bcd68  pop     rbx
0x1800bcd69  retn
```
