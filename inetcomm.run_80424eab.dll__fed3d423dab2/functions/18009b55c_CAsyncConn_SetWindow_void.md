# CAsyncConn::SetWindow(void)

- ea: `0x18009b55c`
- end: `0x18009b61e`
- name: `?SetWindow@CAsyncConn@@QEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CAsyncConn *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800ad540`
- `0x1800b4cc0`
- `0x1800c0360`

## callees

- `0x180099c0c`
- `0x18009b55c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18009b5a1`
- `KERNEL32!GetCurrentThreadId` at `0x18009b5a1`
- `KERNEL32!LeaveCriticalSection` at `0x18009b60d`
- `KERNEL32!LeaveCriticalSection` at `0x18009b60d`
- `KERNEL32!EnterCriticalSection` at `0x18009b574`
- `KERNEL32!EnterCriticalSection` at `0x18009b574`
- `USER32!GetWindowThreadProcessId` at `0x18009b599`
- `USER32!GetWindowThreadProcessId` at `0x18009b599`
- `USER32!IsWindow` at `0x18009b586`
- `USER32!IsWindow` at `0x18009b5b7`
- `USER32!IsWindow` at `0x18009b586`
- `USER32!IsWindow` at `0x18009b5b7`
- `WS2_32!__imp_WSAAsyncSelect` at `0x18009b5ee`
- `WS2_32!__imp_WSAAsyncSelect` at `0x18009b5ee`
- `WS2_32!__imp_WSAGetLastError` at `0x18009b5f9`
- `WS2_32!__imp_WSAGetLastError` at `0x18009b5f9`

## pseudocode

```c
__int64 __fastcall CAsyncConn::SetWindow(CAsyncConn *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbp
  unsigned int v3; // esi
  HWND v4; // rcx
  DWORD WindowThreadProcessId; // ebx
  HWND v6; // rcx
  SOCKET v7; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v4 = (HWND)*((_QWORD *)this + 32);
  if ( !v4
    || !IsWindow(v4)
    || (WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)this + 32), 0),
        WindowThreadProcessId != GetCurrentThreadId()) )
  {
    v6 = (HWND)*((_QWORD *)this + 32);
    if ( v6 )
      IsWindow(v6);
    if ( CAsyncConn::CreateWnd(this) )
    {
      v7 = *((_QWORD *)this + 6);
      if ( v7 != -1 && WSAAsyncSelect(v7, *((HWND *)this + 32), 0x401u, 35) == -1 )
      {
        *((_DWORD *)this + 33) = WSAGetLastError();
        v3 = -2146644988;
      }
    }
    else
    {
      v3 = -2147467259;
    }
  }
  LeaveCriticalSection(v1);
  return v3;
}

```

## disassembly

```asm
0x18009b55c  push    rbx
0x18009b55e  push    rbp
0x18009b55f  push    rsi
0x18009b560  push    rdi
0x18009b561  sub     rsp, 28h
0x18009b565  lea     rbp, [rcx+88h]
0x18009b56c  mov     rdi, rcx
0x18009b56f  mov     rcx, rbp; lpCriticalSection
0x18009b572  xor     esi, esi
0x18009b574  call    cs:__imp_EnterCriticalSection
0x18009b57a  mov     rcx, [rdi+100h]; hWnd
0x18009b581  test    rcx, rcx
0x18009b584  jz      short loc_18009B5AB
0x18009b586  call    cs:__imp_IsWindow
0x18009b58c  test    eax, eax
0x18009b58e  jz      short loc_18009B5AB
0x18009b590  mov     rcx, [rdi+100h]; hWnd
0x18009b597  xor     edx, edx; lpdwProcessId
0x18009b599  call    cs:__imp_GetWindowThreadProcessId
0x18009b59f  mov     ebx, eax
0x18009b5a1  call    cs:__imp_GetCurrentThreadId
0x18009b5a7  cmp     ebx, eax
0x18009b5a9  jz      short loc_18009B60A
0x18009b5ab  mov     rcx, [rdi+100h]; hWnd
0x18009b5b2  test    rcx, rcx
0x18009b5b5  jz      short loc_18009B5BD
0x18009b5b7  call    cs:__imp_IsWindow
0x18009b5bd  mov     rcx, rdi; this
0x18009b5c0  call    ?CreateWnd@CAsyncConn@@AEAAPEAUHWND__@@XZ; CAsyncConn::CreateWnd(void)
0x18009b5c5  test    rax, rax
0x18009b5c8  jnz     short loc_18009B5D1
0x18009b5ca  mov     esi, 80004005h
0x18009b5cf  jmp     short loc_18009B60A
0x18009b5d1  mov     rcx, [rdi+30h]; s
0x18009b5d5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009b5d9  jz      short loc_18009B60A
0x18009b5db  mov     rdx, [rdi+100h]; hWnd
0x18009b5e2  mov     r9d, 23h ; '#'; lEvent
0x18009b5e8  mov     r8d, 401h; wMsg
0x18009b5ee  call    cs:__imp_WSAAsyncSelect
0x18009b5f4  cmp     eax, 0FFFFFFFFh
0x18009b5f7  jnz     short loc_18009B60A
0x18009b5f9  call    cs:__imp_WSAGetLastError
0x18009b5ff  mov     [rdi+84h], eax
0x18009b605  mov     esi, 800CCC04h
0x18009b60a  mov     rcx, rbp; lpCriticalSection
0x18009b60d  call    cs:__imp_LeaveCriticalSection
0x18009b613  mov     eax, esi
0x18009b615  add     rsp, 28h
0x18009b619  pop     rdi
0x18009b61a  pop     rsi
0x18009b61b  pop     rbp
0x18009b61c  pop     rbx
0x18009b61d  retn
```
