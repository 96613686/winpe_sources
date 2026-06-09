# AuthDialogCallbackProc(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64)

- ea: `0x180002e10`
- end: `0x180002ef7`
- name: `?AuthDialogCallbackProc@@YAJPEAUHWND__@@I_K_J1@Z`
- size: `231`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int, unsigned __int64, __int64, unsigned __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002e10`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002e63`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002e63`
- `ntdll!WinSqmAddToStream` at `0x180002ea4`
- `ntdll!WinSqmAddToStream` at `0x180002ea4`
- `USER32!SetForegroundWindow` at `0x180002eac`
- `USER32!SetForegroundWindow` at `0x180002eac`
- `USER32!SetWindowPos` at `0x180002ee4`
- `USER32!SetWindowPos` at `0x180002ee4`
- `USER32!SetActiveWindow` at `0x180002eb9`
- `USER32!SetActiveWindow` at `0x180002eb9`

## pseudocode

```c
__int64 __fastcall AuthDialogCallbackProc(HWND hWnd, int a2, __int64 a3, __int64 a4)
{
  LPVOID v7; // [rsp+40h] [rbp-28h] BYREF
  int v8; // [rsp+48h] [rbp-20h] BYREF
  const wchar_t *v9; // [rsp+50h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 == 3 )
    {
      v8 = 0;
      v9 = 0;
      v7 = 0;
      if ( CoCreateInstance(
             &GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee,
             0,
             1u,
             &GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee,
             &v7) >= 0 )
        (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v7 + 24LL))(v7, a4);
      v8 = 2;
      v9 = L"HELP_ENTRY_ID_HARDWARE_AND_DRIVERS_DRIVER";
      WinSqmAddToStream(0, 911, 1, &v8);
    }
  }
  else if ( !SetForegroundWindow(hWnd) )
  {
    SetActiveWindow(hWnd);
    SetWindowPos(hWnd, HWND_MESSAGE|0x2LL, 200, 200, 500, 200, 0x43u);
  }
  return 0;
}

```

## disassembly

```asm
0x180002e10  mov     r11, rsp
0x180002e13  mov     [r11+8], rbx
0x180002e17  push    rdi
0x180002e18  sub     rsp, 60h
0x180002e1c  mov     rdi, r9
0x180002e1f  mov     rbx, rcx
0x180002e22  test    edx, edx
0x180002e24  jz      loc_180002EAC
0x180002e2a  cmp     edx, 3
0x180002e2d  jnz     loc_180002EEA
0x180002e33  xor     eax, eax
0x180002e35  mov     [rsp+68h+var_20], 0
0x180002e3d  lea     ebx, [rdx-2]
0x180002e40  mov     [r11-18h], rax
0x180002e44  mov     [r11-28h], rax
0x180002e48  lea     r9, _GUID_8cec5884_07a1_11d9_b15e_000d56bfe6ee; riid
0x180002e4f  lea     rax, [r11-28h]
0x180002e53  mov     r8d, ebx; dwClsContext
0x180002e56  xor     edx, edx; pUnkOuter
0x180002e58  mov     [r11-48h], rax
0x180002e5c  lea     rcx, _GUID_8cec58e7_07a1_11d9_b15e_000d56bfe6ee; rclsid
0x180002e63  call    cs:__imp_CoCreateInstance
0x180002e69  test    eax, eax
0x180002e6b  js      short loc_180002E81
0x180002e6d  mov     rcx, [rsp+68h+var_28]
0x180002e72  mov     rdx, rdi
0x180002e75  mov     rax, [rcx]
0x180002e78  mov     rax, [rax+18h]
0x180002e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e81  lea     rax, aHelpEntryIdHar; "HELP_ENTRY_ID_HARDWARE_AND_DRIVERS_DRIV"...
0x180002e88  mov     [rsp+68h+var_20], 2
0x180002e90  lea     r9, [rsp+68h+var_20]
0x180002e95  mov     [rsp+68h+var_18], rax
0x180002e9a  mov     r8d, ebx
0x180002e9d  mov     edx, 38Fh
0x180002ea2  xor     ecx, ecx
0x180002ea4  call    cs:__imp_WinSqmAddToStream
0x180002eaa  jmp     short loc_180002EEA
0x180002eac  call    cs:__imp_SetForegroundWindow
0x180002eb2  test    eax, eax
0x180002eb4  jnz     short loc_180002EEA
0x180002eb6  mov     rcx, rbx; hWnd
0x180002eb9  call    cs:__imp_SetActiveWindow
0x180002ebf  mov     r8d, 0C8h; X
0x180002ec5  mov     [rsp+68h+uFlags], 43h ; 'C'; uFlags
0x180002ecd  mov     [rsp+68h+cy], r8d; cy
0x180002ed2  mov     r9d, r8d; Y
0x180002ed5  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x180002ed9  mov     [rsp+68h+var_48], 1F4h; cx
0x180002ee1  mov     rcx, rbx; hWnd
0x180002ee4  call    cs:__imp_SetWindowPos
0x180002eea  mov     rbx, [rsp+68h+arg_0]
0x180002eef  xor     eax, eax
0x180002ef1  add     rsp, 60h
0x180002ef5  pop     rdi
0x180002ef6  retn
```
