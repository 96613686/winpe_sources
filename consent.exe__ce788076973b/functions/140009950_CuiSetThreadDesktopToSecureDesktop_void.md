# CuiSetThreadDesktopToSecureDesktop(void)

- ea: `0x140009950`
- end: `0x140009a1a`
- name: `?CuiSetThreadDesktopToSecureDesktop@@YAKXZ`
- size: `202`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a080`
- `0x14001adb0`

## callees

- `0x140009950`
- `0x14000fbec`

## import_xrefs

- `USER32!SetThreadDesktop` at `0x140009980`
- `USER32!SetThreadDesktop` at `0x140009980`
- `USER32!CloseDesktop` at `0x1400099c6`
- `USER32!CloseDesktop` at `0x1400099c6`
- `USER32!OpenDesktopW` at `0x140009968`
- `USER32!OpenDesktopW` at `0x140009968`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000998a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000998a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400099d9`

## pseudocode

```c
__int64 CuiSetThreadDesktopToSecureDesktop(void)
{
  HDESK v0; // rax
  HDESK v1; // rbx
  DWORD LastError; // edi
  DWORD v4; // ebx

  v0 = OpenDesktopW(L"winlogon", 0, 0, 0x2000000u);
  v1 = v0;
  if ( v0 )
  {
    LastError = 0;
    if ( !SetThreadDesktop(v0) )
    {
      LastError = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, LastError);
    }
    CloseDesktop(v1);
    return LastError;
  }
  else
  {
    v4 = GetLastError();
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 39, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v4);
    return v4;
  }
}

```

## disassembly

```asm
0x140009950  push    rbx
0x140009952  sub     rsp, 20h
0x140009956  mov     r9d, 2000000h; dwDesiredAccess
0x14000995c  lea     rcx, aWinlogon_0; "winlogon"
0x140009963  xor     r8d, r8d; fInherit
0x140009966  xor     edx, edx; dwFlags
0x140009968  call    cs:__imp_OpenDesktopW
0x14000996e  mov     rbx, rax
0x140009971  test    rax, rax
0x140009974  jz      short loc_1400099D9
0x140009976  mov     [rsp+28h+arg_0], rdi
0x14000997b  mov     rcx, rax; hDesktop
0x14000997e  xor     edi, edi
0x140009980  call    cs:__imp_SetThreadDesktop
0x140009986  test    eax, eax
0x140009988  jnz     short loc_1400099C3
0x14000998a  call    cs:__imp_GetLastError
0x140009990  mov     edi, eax
0x140009992  mov     rcx, cs:WPP_GLOBAL_Control
0x140009999  lea     rax, WPP_GLOBAL_Control
0x1400099a0  cmp     rcx, rax
0x1400099a3  jz      short loc_1400099C3
0x1400099a5  test    byte ptr [rcx+1Ch], 4
0x1400099a9  jz      short loc_1400099C3
0x1400099ab  mov     rcx, [rcx+10h]
0x1400099af  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x1400099b6  mov     edx, 26h ; '&'
0x1400099bb  mov     r9d, edi
0x1400099be  call    WPP_SF_D
0x1400099c3  mov     rcx, rbx; hDesktop
0x1400099c6  call    cs:__imp_CloseDesktop
0x1400099cc  mov     eax, edi
0x1400099ce  mov     rdi, [rsp+28h+arg_0]
0x1400099d3  add     rsp, 20h
0x1400099d7  pop     rbx
0x1400099d8  retn
0x1400099d9  call    cs:__imp_GetLastError
0x1400099df  mov     ebx, eax
0x1400099e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400099e8  lea     rax, WPP_GLOBAL_Control
0x1400099ef  cmp     rcx, rax
0x1400099f2  jz      short loc_140009A12
0x1400099f4  test    byte ptr [rcx+1Ch], 4
0x1400099f8  jz      short loc_140009A12
0x1400099fa  mov     rcx, [rcx+10h]
0x1400099fe  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140009a05  mov     edx, 27h ; '''
0x140009a0a  mov     r9d, ebx
0x140009a0d  call    WPP_SF_D
0x140009a12  mov     eax, ebx
0x140009a14  add     rsp, 20h
0x140009a18  pop     rbx
0x140009a19  retn
```
