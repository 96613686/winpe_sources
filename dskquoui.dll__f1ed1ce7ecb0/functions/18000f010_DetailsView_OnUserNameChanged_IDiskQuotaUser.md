# DetailsView::OnUserNameChanged(IDiskQuotaUser *)

- ea: `0x18000f010`
- end: `0x18000f0e7`
- name: `?OnUserNameChanged@DetailsView@@UEAAJPEAUIDiskQuotaUser@@@Z`
- size: `215`
- prototype: `int(DetailsView *__hidden this, struct IDiskQuotaUser *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000f010`
- `0x18001119c`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f0c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f03d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f03d`
- `USER32!UpdateWindow` at `0x18000f0b1`
- `USER32!UpdateWindow` at `0x18000f0b1`
- `USER32!SendMessageTimeoutW` at `0x18000f0a2`
- `USER32!SendMessageTimeoutW` at `0x18000f0a2`

## pseudocode

```c
__int64 __fastcall DetailsView::OnUserNameChanged(DetailsView *this, struct IDiskQuotaUser *a2)
{
  unsigned int v4; // edi
  HWND v5; // rcx
  int v7; // [rsp+60h] [rbp+8h] BYREF
  ULONG_PTR dwResult; // [rsp+70h] [rbp+18h] BYREF

  v4 = -2147467259;
  (*(void (__fastcall **)(DetailsView *))(*(_QWORD *)this + 8LL))(this);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  if ( !*((_DWORD *)this + 167) )
  {
    if ( a2 )
    {
      v7 = -1;
      if ( PointerList::FindIndex((DetailsView *)((char *)this + 40), a2, &v7) )
      {
        v5 = (HWND)*((_QWORD *)this + 13);
        dwResult = 0;
        if ( SendMessageTimeoutW(v5, 0x1015u, v7, v7, 1u, 0x1388u, &dwResult) )
          UpdateWindow(*((HWND *)this + 13));
        v4 = 0;
      }
    }
    else
    {
      v4 = -2147024809;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 528));
  (*(void (__fastcall **)(DetailsView *))(*(_QWORD *)this + 16LL))(this);
  return v4;
}

```

## disassembly

```asm
0x18000f010  mov     [rsp+arg_8], rbx
0x18000f015  push    rbp
0x18000f016  push    rsi
0x18000f017  push    rdi
0x18000f018  sub     rsp, 40h
0x18000f01c  mov     rax, [rcx]
0x18000f01f  mov     rsi, rdx
0x18000f022  mov     rbx, rcx
0x18000f025  mov     edi, 80004005h
0x18000f02a  mov     rax, [rax+8]
0x18000f02e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f033  lea     rbp, [rbx+210h]
0x18000f03a  mov     rcx, rbp; lpCriticalSection
0x18000f03d  call    cs:__imp_EnterCriticalSection
0x18000f043  cmp     dword ptr [rbx+29Ch], 0
0x18000f04a  jnz     short loc_18000F0C0
0x18000f04c  test    rsi, rsi
0x18000f04f  jz      short loc_18000F0BB
0x18000f051  lea     rcx, [rbx+28h]; this
0x18000f055  mov     [rsp+58h+arg_0], 0FFFFFFFFh
0x18000f05d  lea     r8, [rsp+58h+arg_0]; int *
0x18000f062  mov     rdx, rsi; void *
0x18000f065  call    ?FindIndex@PointerList@@QEAAHPEAXPEAH@Z; PointerList::FindIndex(void *,int *)
0x18000f06a  test    eax, eax
0x18000f06c  jz      short loc_18000F0C0
0x18000f06e  movsxd  r8, [rsp+58h+arg_0]; wParam
0x18000f073  lea     rax, [rsp+58h+dwResult]
0x18000f078  mov     rcx, [rbx+68h]; hWnd
0x18000f07c  mov     r9, r8; lParam
0x18000f07f  mov     [rsp+58h+lpdwResult], rax; lpdwResult
0x18000f084  mov     edx, 1015h; Msg
0x18000f089  mov     [rsp+58h+uTimeout], 1388h; uTimeout
0x18000f091  mov     [rsp+58h+fuFlags], 1; fuFlags
0x18000f099  mov     [rsp+58h+dwResult], 0
0x18000f0a2  call    cs:__imp_SendMessageTimeoutW
0x18000f0a8  test    rax, rax
0x18000f0ab  jz      short loc_18000F0B7
0x18000f0ad  mov     rcx, [rbx+68h]; hWnd
0x18000f0b1  call    cs:__imp_UpdateWindow
0x18000f0b7  xor     edi, edi
0x18000f0b9  jmp     short loc_18000F0C0
0x18000f0bb  mov     edi, 80070057h
0x18000f0c0  mov     rcx, rbp; lpCriticalSection
0x18000f0c3  call    cs:__imp_LeaveCriticalSection
0x18000f0c9  mov     rcx, [rbx]
0x18000f0cc  mov     rax, [rcx+10h]
0x18000f0d0  mov     rcx, rbx
0x18000f0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0d8  mov     rbx, [rsp+58h+arg_8]
0x18000f0dd  mov     eax, edi
0x18000f0df  add     rsp, 40h
0x18000f0e3  pop     rdi
0x18000f0e4  pop     rsi
0x18000f0e5  pop     rbp
0x18000f0e6  retn
```
