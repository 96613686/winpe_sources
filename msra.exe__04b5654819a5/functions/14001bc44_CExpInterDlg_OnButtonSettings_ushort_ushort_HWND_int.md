# CExpInterDlg::OnButtonSettings(ushort,ushort,HWND__ *,int &)

- ea: `0x14001bc44`
- end: `0x14001bd8d`
- name: `?OnButtonSettings@CExpInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `329`
- prototype: `__int64 __fastcall(CExpInterDlg *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14001db80`

## callees

- `0x14000a858`
- `0x14001bc44`
- `0x14001efc8`
- `0x14002a3d0`
- `0x140034be8`
- `0x140037e7c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001bce9`
- `KERNEL32!GetCurrentThreadId` at `0x14001bce9`
- `KERNEL32!LeaveCriticalSection` at `0x14001bd28`
- `KERNEL32!LeaveCriticalSection` at `0x14001bd28`
- `KERNEL32!EnterCriticalSection` at `0x14001bcff`
- `KERNEL32!EnterCriticalSection` at `0x14001bcff`
- `USER32!GetActiveWindow` at `0x14001bcd2`
- `USER32!GetActiveWindow` at `0x14001bcd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CExpInterDlg::OnButtonSettings(HWND *this, __int64 a2, __int64 a3, HWND a4)
{
  HWND ActiveWindow; // rbx
  _QWORD v7[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v8; // [rsp+40h] [rbp-40h] BYREF
  DWORD CurrentThreadId; // [rsp+48h] [rbp-38h]
  __int64 v10; // [rsp+50h] [rbp-30h]
  AtlThunkData_t *Thunk; // [rsp+58h] [rbp-28h]
  __int64 v12; // [rsp+60h] [rbp-20h]
  int v13; // [rsp+68h] [rbp-18h]
  char *v14; // [rsp+78h] [rbp-8h]
  int v15; // [rsp+A0h] [rbp+20h] BYREF

  v7[1] = 0;
  Thunk = 0;
  v12 = 0;
  v13 = 0;
  v7[0] = &CExpSetDlg::`vftable';
  v14 = 0;
  v15 = 0;
  CSqmManager::RecordUIUsage((CSqmManager *)this, 0xE3u);
  IsToolbarButtonEnabled(this[10], 227, &v15);
  if ( v15 )
  {
    v14 = (char *)_AtlModule + 696;
    ActiveWindow = GetActiveWindow();
    v8 = v7;
    CurrentThreadId = GetCurrentThreadId();
    EnterCriticalSection(&stru_140063978);
    v10 = qword_1400639A0;
    qword_1400639A0 = (__int64)&v8;
    LeaveCriticalSection(&stru_140063978);
    if ( AtlAxDialogBoxW(hModule, (LPCWSTR)0x7D2, ActiveWindow) == 1 )
      CSessionLogger::RefreshLoggingSetting((CEventLogger *)((char *)_AtlModule + 728));
  }
  v7[0] = &CExpSetDlg::`vftable';
  if ( Thunk )
    AtlThunk_FreeData(Thunk);
  return 0;
}

```

## disassembly

```asm
0x14001bc44  mov     [rsp-8+arg_0], rbx
0x14001bc49  mov     [rsp-8+arg_8], r14
0x14001bc4e  mov     word ptr [rsp-8+arg_10], r8w
0x14001bc54  push    rbp
0x14001bc55  mov     rbp, rsp
0x14001bc58  sub     rsp, 80h
0x14001bc5f  mov     rbx, rcx
0x14001bc62  mov     [rbp+var_48], 0
0x14001bc6a  mov     [rbp+Thunk], 0
0x14001bc72  mov     [rbp+var_20], 0
0x14001bc7a  mov     [rbp+var_18], 0
0x14001bc81  lea     r14, ??_7CExpSetDlg@@6B@; const CExpSetDlg::`vftable'
0x14001bc88  mov     [rbp+var_50], r14
0x14001bc8c  mov     [rbp+var_8], 0
0x14001bc94  mov     [rbp+arg_10], 0
0x14001bc9b  mov     edx, 0E3h; unsigned int
0x14001bca0  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x14001bca5  lea     r8, [rbp+arg_10]; int *
0x14001bca9  mov     edx, 0E3h; int
0x14001bcae  mov     rcx, [rbx+50h]; HWND
0x14001bcb2  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x14001bcb7  cmp     [rbp+arg_10], 0
0x14001bcbb  jz      loc_14001BD62
0x14001bcc1  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001bcc8  add     rax, 2B8h
0x14001bcce  mov     [rbp+var_8], rax
0x14001bcd2  call    cs:__imp_GetActiveWindow
0x14001bcd9  nop     dword ptr [rax+rax+00h]
0x14001bcde  mov     rbx, rax
0x14001bce1  lea     rax, [rbp+var_50]
0x14001bce5  mov     [rbp+var_40], rax
0x14001bce9  call    cs:__imp_GetCurrentThreadId
0x14001bcf0  nop     dword ptr [rax+rax+00h]
0x14001bcf5  mov     [rbp+var_38], eax
0x14001bcf8  lea     rcx, stru_140063978; lpCriticalSection
0x14001bcff  call    cs:__imp_EnterCriticalSection
0x14001bd06  nop     dword ptr [rax+rax+00h]
0x14001bd0b  mov     rdx, cs:qword_1400639A0
0x14001bd12  mov     [rbp+var_30], rdx
0x14001bd16  lea     rax, [rbp+var_40]
0x14001bd1a  mov     cs:qword_1400639A0, rax
0x14001bd21  lea     rcx, stru_140063978; lpCriticalSection
0x14001bd28  call    cs:__imp_LeaveCriticalSection
0x14001bd2f  nop     dword ptr [rax+rax+00h]
0x14001bd34  mov     r8, rbx; hWndParent
0x14001bd37  mov     edx, 7D2h; lpName
0x14001bd3c  mov     rcx, cs:hModule; hInstance
0x14001bd43  call    AtlAxDialogBoxW
0x14001bd48  cmp     rax, 1
0x14001bd4c  jnz     short loc_14001BD62
0x14001bd4e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14001bd55  add     rcx, 2D8h; this
0x14001bd5c  call    ?RefreshLoggingSetting@CSessionLogger@@QEAAJXZ; CSessionLogger::RefreshLoggingSetting(void)
0x14001bd61  nop
0x14001bd62  mov     [rbp+var_50], r14
0x14001bd66  mov     rcx, [rbp+Thunk]; Thunk
0x14001bd6a  test    rcx, rcx
0x14001bd6d  jz      short loc_14001BD75
0x14001bd6f  call    AtlThunk_FreeData
0x14001bd74  nop
0x14001bd75  xor     eax, eax
0x14001bd77  lea     r11, [rsp+80h+var_s0]
0x14001bd7f  mov     rbx, [r11+10h]
0x14001bd83  mov     r14, [r11+18h]
0x14001bd87  mov     rsp, r11
0x14001bd8a  pop     rbp
0x14001bd8b  retn
```
