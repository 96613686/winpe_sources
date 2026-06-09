# CAsyncConn::ResetWindow(void)

- ea: `0x18009b1cc`
- end: `0x18009b23e`
- name: `?ResetWindow@CAsyncConn@@QEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(CAsyncConn *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800ad2d0`
- `0x1800b4700`
- `0x1800bff00`

## callees

- `0x18009b1cc`
- `0x1800c8680`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18009b211`
- `KERNEL32!GetCurrentThreadId` at `0x18009b211`
- `KERNEL32!LeaveCriticalSection` at `0x18009b226`
- `KERNEL32!LeaveCriticalSection` at `0x18009b226`
- `KERNEL32!EnterCriticalSection` at `0x18009b1ec`
- `KERNEL32!EnterCriticalSection` at `0x18009b1ec`
- `USER32!GetWindowThreadProcessId` at `0x18009b209`
- `USER32!GetWindowThreadProcessId` at `0x18009b209`
- `USER32!IsWindow` at `0x18009b1fa`
- `USER32!IsWindow` at `0x18009b1fa`

## pseudocode

```c
__int64 __fastcall CAsyncConn::ResetWindow(CAsyncConn *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  HWND *v2; // rdi
  DWORD WindowThreadProcessId; // ebx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v2 = (HWND *)((char *)this + 256);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( *v2 )
  {
    if ( IsWindow(*v2) )
    {
      WindowThreadProcessId = GetWindowThreadProcessId(*v2, 0);
      if ( WindowThreadProcessId == GetCurrentThreadId() )
        OE_SafeDestroyWindow(v2);
    }
  }
  LeaveCriticalSection(v1);
  return 0;
}

```

## disassembly

```asm
0x18009b1cc  mov     [rsp+arg_0], rbx
0x18009b1d1  mov     [rsp+arg_8], rsi
0x18009b1d6  push    rdi
0x18009b1d7  sub     rsp, 20h
0x18009b1db  lea     rsi, [rcx+88h]
0x18009b1e2  lea     rdi, [rcx+100h]
0x18009b1e9  mov     rcx, rsi; lpCriticalSection
0x18009b1ec  call    cs:__imp_EnterCriticalSection
0x18009b1f2  mov     rcx, [rdi]; hWnd
0x18009b1f5  test    rcx, rcx
0x18009b1f8  jz      short loc_18009B223
0x18009b1fa  call    cs:__imp_IsWindow
0x18009b200  test    eax, eax
0x18009b202  jz      short loc_18009B223
0x18009b204  mov     rcx, [rdi]; hWnd
0x18009b207  xor     edx, edx; lpdwProcessId
0x18009b209  call    cs:__imp_GetWindowThreadProcessId
0x18009b20f  mov     ebx, eax
0x18009b211  call    cs:__imp_GetCurrentThreadId
0x18009b217  cmp     ebx, eax
0x18009b219  jnz     short loc_18009B223
0x18009b21b  mov     rcx, rdi; HWND *
0x18009b21e  call    ?OE_SafeDestroyWindow@@YAXPEAPEAUHWND__@@@Z; OE_SafeDestroyWindow(HWND__ * *)
0x18009b223  mov     rcx, rsi; lpCriticalSection
0x18009b226  call    cs:__imp_LeaveCriticalSection
0x18009b22c  mov     rbx, [rsp+28h+arg_0]
0x18009b231  xor     eax, eax
0x18009b233  mov     rsi, [rsp+28h+arg_8]
0x18009b238  add     rsp, 20h
0x18009b23c  pop     rdi
0x18009b23d  retn
```
