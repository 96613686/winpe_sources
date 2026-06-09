# DwmTransitionOwnedWindow

- ea: `0x180014bc0`
- end: `0x180014c7d`
- name: `DwmTransitionOwnedWindow`
- size: `189`
- prototype: `HRESULT __stdcall(HWND hwnd, enum DWMTRANSITION_OWNEDWINDOW_TARGET target)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005b5c`
- `0x180008fb0`
- `0x18000c2ec`
- `0x180014bc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014c00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014c00`
- `USER32!GetWindowThreadProcessId` at `0x180014bfa`
- `USER32!GetWindowThreadProcessId` at `0x180014bfa`
- `USER32!GetWindow` at `0x180014c14`
- `USER32!GetWindow` at `0x180014c14`
- `USER32!GetAncestor` at `0x180014c27`
- `USER32!GetAncestor` at `0x180014c27`

## pseudocode

```c
HRESULT __stdcall DwmTransitionOwnedWindow(HWND hwnd, enum DWMTRANSITION_OWNEDWINDOW_TARGET target)
{
  __int16 v2; // di
  HRESULT v4; // ebx
  DWORD dwProcessId; // [rsp+40h] [rbp+18h] BYREF

  v2 = target;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0pd_EtwEventWriteTransfer(hwnd, ApiTransitionOwnedWindow_Start, hwnd, (unsigned int)target);
  dwProcessId = 0;
  GetWindowThreadProcessId(hwnd, &dwProcessId);
  if ( dwProcessId == GetCurrentProcessId() && GetWindow(hwnd, 4u) && GetAncestor(hwnd, 2u) == hwnd )
    v4 = DwmpTransitionWindow(hwnd, v2 & 0xFFF | 0x80000000);
  else
    v4 = -2147024809;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(Microsoft_Windows_Dwm_Api_Provider_Context, ApiTransitionOwnedWindow_Stop);
  return v4;
}

```

## disassembly

```asm
0x180014bc0  mov     [rsp+arg_0], rbx
0x180014bc5  push    rdi
0x180014bc6  sub     rsp, 20h
0x180014bca  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180014bd1  mov     edi, edx
0x180014bd3  mov     rbx, rcx
0x180014bd6  jz      short loc_180014BEA
0x180014bd8  mov     r9d, edx
0x180014bdb  mov     r8, rcx
0x180014bde  lea     rdx, ApiTransitionOwnedWindow_Start
0x180014be5  call    McTemplateU0pd_EtwEventWriteTransfer
0x180014bea  lea     rdx, [rsp+28h+dwProcessId]; lpdwProcessId
0x180014bef  mov     [rsp+28h+dwProcessId], 0
0x180014bf7  mov     rcx, rbx; hWnd
0x180014bfa  call    cs:__imp_GetWindowThreadProcessId
0x180014c00  call    cs:__imp_GetCurrentProcessId
0x180014c06  cmp     [rsp+28h+dwProcessId], eax
0x180014c0a  jnz     short loc_180014C4C
0x180014c0c  mov     edx, 4; uCmd
0x180014c11  mov     rcx, rbx; hWnd
0x180014c14  call    cs:__imp_GetWindow
0x180014c1a  test    rax, rax
0x180014c1d  jz      short loc_180014C4C
0x180014c1f  mov     edx, 2; gaFlags
0x180014c24  mov     rcx, rbx; hwnd
0x180014c27  call    cs:__imp_GetAncestor
0x180014c2d  cmp     rax, rbx
0x180014c30  jnz     short loc_180014C4C
0x180014c32  and     edi, 0FFFh
0x180014c38  mov     rcx, rbx
0x180014c3b  or      edi, 80000000h
0x180014c41  mov     edx, edi
0x180014c43  call    DwmpTransitionWindow
0x180014c48  mov     ebx, eax
0x180014c4a  jmp     short loc_180014C51
0x180014c4c  mov     ebx, 80070057h
0x180014c51  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180014c58  jz      short loc_180014C70
0x180014c5a  mov     r8d, ebx
0x180014c5d  lea     rdx, ApiTransitionOwnedWindow_Stop
0x180014c64  lea     rcx, Microsoft_Windows_Dwm_Api_Provider_Context
0x180014c6b  call    McTemplateU0q_EtwEventWriteTransfer
0x180014c70  mov     eax, ebx
0x180014c72  mov     rbx, [rsp+28h+arg_0]
0x180014c77  add     rsp, 20h
0x180014c7b  pop     rdi
0x180014c7c  retn
```
