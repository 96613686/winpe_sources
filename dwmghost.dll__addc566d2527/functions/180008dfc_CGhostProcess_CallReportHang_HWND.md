# CGhostProcess::CallReportHang(HWND__ *)

- ea: `0x180008dfc`
- end: `0x180008e99`
- name: `?CallReportHang@CGhostProcess@@QEAAHPEAUHWND__@@@Z`
- size: `157`
- prototype: `int(CGhostProcess *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800075e0`

## callees

- `0x180008dfc`
- `0x180009f60`
- `0x180009f70`
- `0x18000a9c4`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180008e56`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180008e56`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x180008e3c`
- `ext-ms-win-ntuser-window-l1-1-3!IsHungAppWindow` at `0x180008e3c`

## pseudocode

```c
__int64 __fastcall CGhostProcess::CallReportHang(CGhostProcess *this, HWND a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  unsigned int v5; // ebx
  DWORD dwProcessId; // [rsp+40h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  CLock::Acquire((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !*((_QWORD *)this + 16) && !*((_DWORD *)this + 28) && !*((_DWORD *)this + 16) && !*((_DWORD *)this + 30) )
  {
    if ( IsHungAppWindow(a2) )
    {
      dwProcessId = 0;
      if ( GetWindowThreadProcessId(a2, &dwProcessId) )
      {
        if ( dwProcessId == *((_DWORD *)this + 14) && (int)ReportHangInternal(a2) >= 0 )
          *((_DWORD *)this + 28) = 1;
      }
    }
  }
  v5 = *((_DWORD *)this + 28);
  CLock::Release(v2);
  return v5;
}

```

## disassembly

```asm
0x180008dfc  mov     [rsp+arg_8], rbx
0x180008e01  mov     [rsp+arg_10], rsi
0x180008e06  push    rdi
0x180008e07  sub     rsp, 30h
0x180008e0b  lea     rsi, [rcx+10h]
0x180008e0f  mov     rbx, rcx
0x180008e12  mov     rcx, rsi; lpCriticalSection
0x180008e15  mov     rdi, rdx
0x180008e18  call    ?Acquire@CLock@@QEAAXXZ; CLock::Acquire(void)
0x180008e1d  cmp     qword ptr [rbx+80h], 0
0x180008e25  jnz     short loc_180008E7C
0x180008e27  cmp     dword ptr [rbx+70h], 0
0x180008e2b  jnz     short loc_180008E7C
0x180008e2d  cmp     dword ptr [rbx+40h], 0
0x180008e31  jnz     short loc_180008E7C
0x180008e33  cmp     dword ptr [rbx+78h], 0
0x180008e37  jnz     short loc_180008E7C
0x180008e39  mov     rcx, rdi; hwnd
0x180008e3c  call    cs:__imp_IsHungAppWindow
0x180008e42  test    eax, eax
0x180008e44  jz      short loc_180008E7C
0x180008e46  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x180008e4b  mov     [rsp+38h+dwProcessId], 0
0x180008e53  mov     rcx, rdi; hWnd
0x180008e56  call    cs:__imp_GetWindowThreadProcessId
0x180008e5c  test    eax, eax
0x180008e5e  jz      short loc_180008E7C
0x180008e60  mov     eax, [rbx+38h]
0x180008e63  cmp     [rsp+38h+dwProcessId], eax
0x180008e67  jnz     short loc_180008E7C
0x180008e69  mov     rcx, rdi
0x180008e6c  call    ReportHangInternal
0x180008e71  test    eax, eax
0x180008e73  js      short loc_180008E7C
0x180008e75  mov     dword ptr [rbx+70h], 1
0x180008e7c  mov     ebx, [rbx+70h]
0x180008e7f  mov     rcx, rsi; lpCriticalSection
0x180008e82  call    ?Release@CLock@@QEAAXXZ; CLock::Release(void)
0x180008e87  mov     rsi, [rsp+38h+arg_10]
0x180008e8c  mov     eax, ebx
0x180008e8e  mov     rbx, [rsp+38h+arg_8]
0x180008e93  add     rsp, 30h
0x180008e97  pop     rdi
0x180008e98  retn
```
