# CNovInterDlg::OnButtonSettings(ushort,ushort,HWND__ *,int &)

- ea: `0x140020c24`
- end: `0x140020e05`
- name: `?OnButtonSettings@CNovInterDlg@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `481`
- prototype: `__int64 __fastcall(CNovInterDlg *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140023830`

## callees

- `0x14000a858`
- `0x14001efc8`
- `0x14001fb14`
- `0x140020c24`
- `0x140025138`
- `0x14002a3d0`
- `0x140034be8`
- `0x140036dc8`
- `0x140037168`
- `0x140037e7c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140020cc1`
- `KERNEL32!GetCurrentThreadId` at `0x140020cc1`
- `KERNEL32!LeaveCriticalSection` at `0x140020d00`
- `KERNEL32!LeaveCriticalSection` at `0x140020d00`
- `KERNEL32!EnterCriticalSection` at `0x140020cd7`
- `KERNEL32!EnterCriticalSection` at `0x140020cd7`
- `GDI32!DeleteObject` at `0x140020dd8`
- `GDI32!DeleteObject` at `0x140020dd8`
- `USER32!GetActiveWindow` at `0x140020caa`
- `USER32!GetActiveWindow` at `0x140020caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CNovInterDlg::OnButtonSettings(HWND *this, __int64 a2, __int64 a3, HWND a4)
{
  HWND ActiveWindow; // rbx
  _QWORD v7[2]; // [rsp+38h] [rbp-41h] BYREF
  _QWORD *v8; // [rsp+48h] [rbp-31h] BYREF
  DWORD CurrentThreadId; // [rsp+50h] [rbp-29h]
  __int64 v10; // [rsp+58h] [rbp-21h]
  AtlThunkData_t *Thunk; // [rsp+60h] [rbp-19h]
  __int64 v12; // [rsp+68h] [rbp-11h]
  int v13; // [rsp+70h] [rbp-9h]
  char *v14; // [rsp+90h] [rbp+17h]
  HGDIOBJ ho; // [rsp+98h] [rbp+1Fh]
  int v16; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v17; // [rsp+E8h] [rbp+6Fh] BYREF
  int v18; // [rsp+F0h] [rbp+77h] BYREF
  int v19; // [rsp+F4h] [rbp+7Bh]

  v19 = HIDWORD(a4);
  v7[1] = 0;
  Thunk = 0;
  v12 = 0;
  v13 = 0;
  v7[0] = &CNovSetDlg::`vftable';
  ho = 0;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  CSqmManager::RecordUIUsage((CSqmManager *)this, 0xE3u);
  IsToolbarButtonEnabled(this[9], 227, &v16);
  if ( v16 )
  {
    v14 = (char *)_AtlModule + 696;
    ActiveWindow = GetActiveWindow();
    v8 = v7;
    CurrentThreadId = GetCurrentThreadId();
    EnterCriticalSection(&stru_140063978);
    v10 = qword_1400639A0;
    qword_1400639A0 = (__int64)&v8;
    LeaveCriticalSection(&stru_140063978);
    if ( AtlAxDialogBoxW(hModule, (LPCWSTR)0x7D3, ActiveWindow) == 1 )
    {
      if ( *((_DWORD *)this + 22) == 4 )
      {
        CSettingsManager::GetSettingFromRegistry((char *)_AtlModule + 696, 2, &v18);
        CNovInterDlg::EnablePanicKey((CNovInterDlg *)this, v18 != 0);
      }
      if ( (int)CSettingsManager::GetGroupPolicySetting((char *)_AtlModule + 696, 7, &v17) >= 0
        || (int)CSettingsManager::GetSettingFromRegistry((char *)_AtlModule + 696, 1, &v17) >= 0 )
      {
        if ( *((_DWORD *)this + 22) && *((_DWORD *)this + 22) != 5 )
          CNovInterDlg::SetScreenSharingExperience((CNovInterDlg *)this, v17, 0);
        CSessionLogger::RefreshLoggingSetting((CEventLogger *)((char *)_AtlModule + 728));
      }
    }
  }
  v7[0] = &CNovSetDlg::`vftable';
  if ( ho )
    DeleteObject(ho);
  if ( Thunk )
    AtlThunk_FreeData(Thunk);
  return 0;
}

```

## disassembly

```asm
0x140020c24  mov     rax, rsp
0x140020c27  mov     [rax+20h], r9
0x140020c2b  mov     [rax+18h], r8w
0x140020c30  mov     [rax+10h], dx
0x140020c34  push    rbp
0x140020c35  push    rbx
0x140020c36  push    rsi
0x140020c37  push    rdi
0x140020c38  push    r14
0x140020c3a  lea     rbp, [rax-57h]
0x140020c3e  sub     rsp, 0A0h
0x140020c45  mov     rdi, rcx
0x140020c48  xor     esi, esi
0x140020c4a  mov     [rbp+4Fh+var_88], rsi
0x140020c4e  mov     [rbp+4Fh+Thunk], rsi
0x140020c52  mov     [rbp+4Fh+var_60], rsi
0x140020c56  mov     [rbp+4Fh+var_58], esi
0x140020c59  lea     r14, ??_7CNovSetDlg@@6B@; const CNovSetDlg::`vftable'
0x140020c60  mov     [rbp+4Fh+var_90], r14
0x140020c64  mov     [rbp+4Fh+ho], rsi
0x140020c68  mov     [rbp+4Fh+var_38], rsi
0x140020c6c  mov     [rbp+4Fh+arg_10], esi
0x140020c6f  mov     [rbp+4Fh+arg_18], esi
0x140020c72  mov     [rbp+4Fh+arg_8], esi
0x140020c75  mov     ebx, 0E3h
0x140020c7a  mov     edx, ebx; unsigned int
0x140020c7c  call    ?RecordUIUsage@CSqmManager@@QEAAXK@Z; CSqmManager::RecordUIUsage(ulong)
0x140020c81  lea     r8, [rbp+4Fh+arg_8]; int *
0x140020c85  mov     edx, ebx; int
0x140020c87  mov     rcx, [rdi+48h]; HWND
0x140020c8b  call    ?IsToolbarButtonEnabled@@YAJPEAUHWND__@@HPEAH@Z; IsToolbarButtonEnabled(HWND__ *,int,int *)
0x140020c90  cmp     [rbp+4Fh+arg_8], esi
0x140020c93  jz      loc_140020DCB
0x140020c99  mov     rax, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140020ca0  add     rax, 2B8h
0x140020ca6  mov     [rbp+4Fh+var_38], rax
0x140020caa  call    cs:__imp_GetActiveWindow
0x140020cb1  nop     dword ptr [rax+rax+00h]
0x140020cb6  mov     rbx, rax
0x140020cb9  lea     rax, [rbp+4Fh+var_90]
0x140020cbd  mov     [rbp+4Fh+var_80], rax
0x140020cc1  call    cs:__imp_GetCurrentThreadId
0x140020cc8  nop     dword ptr [rax+rax+00h]
0x140020ccd  mov     [rbp+4Fh+var_78], eax
0x140020cd0  lea     rcx, stru_140063978; lpCriticalSection
0x140020cd7  call    cs:__imp_EnterCriticalSection
0x140020cde  nop     dword ptr [rax+rax+00h]
0x140020ce3  mov     rdx, cs:qword_1400639A0
0x140020cea  mov     [rbp+4Fh+var_70], rdx
0x140020cee  lea     rax, [rbp+4Fh+var_80]
0x140020cf2  mov     cs:qword_1400639A0, rax
0x140020cf9  lea     rcx, stru_140063978; lpCriticalSection
0x140020d00  call    cs:__imp_LeaveCriticalSection
0x140020d07  nop     dword ptr [rax+rax+00h]
0x140020d0c  mov     r8, rbx; hWndParent
0x140020d0f  mov     edx, 7D3h; lpName
0x140020d14  mov     rcx, cs:hModule; hInstance
0x140020d1b  call    AtlAxDialogBoxW
0x140020d20  cmp     rax, 1
0x140020d24  jnz     loc_140020DCB
0x140020d2a  cmp     dword ptr [rdi+58h], 4
0x140020d2e  jnz     short loc_140020D5E
0x140020d30  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140020d37  add     rcx, 2B8h
0x140020d3e  lea     r8, [rbp+4Fh+arg_18]
0x140020d42  lea     edx, [rsi+2]
0x140020d45  call    ?GetSettingFromRegistry@CSettingsManager@@QEAAJW4_RASettingDWORD@@PEAK@Z; CSettingsManager::GetSettingFromRegistry(_RASettingDWORD,ulong *)
0x140020d4a  mov     rcx, rdi; this
0x140020d4d  cmp     [rbp+4Fh+arg_18], esi
0x140020d50  jz      short loc_140020D57
0x140020d52  lea     edx, [rsi+1]
0x140020d55  jmp     short loc_140020D59
0x140020d57  xor     edx, edx; int
0x140020d59  call    ?EnablePanicKey@CNovInterDlg@@AEAAXH@Z; CNovInterDlg::EnablePanicKey(int)
0x140020d5e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140020d65  add     rcx, 2B8h
0x140020d6c  lea     r8, [rbp+4Fh+arg_10]
0x140020d70  mov     edx, 7
0x140020d75  call    ?GetGroupPolicySetting@CSettingsManager@@QEAAJW4_RAGroupPolicySettingDWORD@@PEAK@Z; CSettingsManager::GetGroupPolicySetting(_RAGroupPolicySettingDWORD,ulong *)
0x140020d7a  test    eax, eax
0x140020d7c  jns     short loc_140020D9E
0x140020d7e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140020d85  add     rcx, 2B8h
0x140020d8c  lea     r8, [rbp+4Fh+arg_10]
0x140020d90  mov     edx, 1
0x140020d95  call    ?GetSettingFromRegistry@CSettingsManager@@QEAAJW4_RASettingDWORD@@PEAK@Z; CSettingsManager::GetSettingFromRegistry(_RASettingDWORD,ulong *)
0x140020d9a  test    eax, eax
0x140020d9c  js      short loc_140020DCB
0x140020d9e  cmp     [rdi+58h], esi
0x140020da1  jz      short loc_140020DB7
0x140020da3  cmp     dword ptr [rdi+58h], 5
0x140020da7  jz      short loc_140020DB7
0x140020da9  xor     r8d, r8d; int
0x140020dac  mov     edx, [rbp+4Fh+arg_10]; unsigned int
0x140020daf  mov     rcx, rdi; this
0x140020db2  call    ?SetScreenSharingExperience@CNovInterDlg@@QEAAJIH@Z; CNovInterDlg::SetScreenSharingExperience(uint,int)
0x140020db7  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140020dbe  add     rcx, 2D8h; this
0x140020dc5  call    ?RefreshLoggingSetting@CSessionLogger@@QEAAJXZ; CSessionLogger::RefreshLoggingSetting(void)
0x140020dca  nop
0x140020dcb  mov     [rbp+4Fh+var_90], r14
0x140020dcf  mov     rcx, [rbp+4Fh+ho]; ho
0x140020dd3  test    rcx, rcx
0x140020dd6  jz      short loc_140020DE5
0x140020dd8  call    cs:__imp_DeleteObject
0x140020ddf  nop     dword ptr [rax+rax+00h]
0x140020de4  nop
0x140020de5  mov     rcx, [rbp+4Fh+Thunk]; Thunk
0x140020de9  test    rcx, rcx
0x140020dec  jz      short loc_140020DF4
0x140020dee  call    AtlThunk_FreeData
0x140020df3  nop
0x140020df4  xor     eax, eax
0x140020df6  add     rsp, 0A0h
0x140020dfd  pop     r14
0x140020dff  pop     rdi
0x140020e00  pop     rsi
0x140020e01  pop     rbx
0x140020e02  pop     rbp
0x140020e03  retn
```
