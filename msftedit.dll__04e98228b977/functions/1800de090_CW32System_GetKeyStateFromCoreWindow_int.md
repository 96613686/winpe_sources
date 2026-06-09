# CW32System::GetKeyStateFromCoreWindow(int)

- ea: `0x1800de090`
- end: `0x1800de270`
- name: `?GetKeyStateFromCoreWindow@CW32System@@SAFH@Z`
- size: `480`
- prototype: `__int16 __fastcall(int nVirtKey)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18006ad18`
- `0x1800de090`
- `0x1800f1028`
- `0x18013fea4`
- `0x180147934`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800de0ef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800de0ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de0b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de1d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de0b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de1d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800de252`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800de0d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800de0d0`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800de10e`
- `ext-ms-win-ntuser-keyboard-l1-1-0!GetKeyState` at `0x1800de10e`

## pseudocode

```c
__int64 __fastcall CW32System::GetKeyStateFromCoreWindow(unsigned int nVirtKey)
{
  unsigned __int16 KeyState; // bx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64 *); // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // [rsp+20h] [rbp-10h] BYREF
  int v11; // [rsp+68h] [rbp+38h] BYREF
  HSTRING string; // [rsp+70h] [rbp+40h] BYREF
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF

  v10 = 0;
  v13 = 0;
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  if ( WindowsCreateString(L"Windows.UI.Core.CoreWindow", 0x1Au, &string) >= 0
    && (int)RoGetActivationFactory(string, &GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1, &v10) >= 0
    && (v6 = v10,
        v7 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v10 + 48LL),
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13),
        v7(v6, &v13) >= 0)
    && v13
    && (v11 = 0, (*(int (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v13 + 168LL))(v13, nVirtKey, &v11) >= 0)
    && (v11 & 1) != 0 )
  {
    WindowsDeleteString(string);
    v8 = v13;
    string = 0;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return 4294934528LL;
  }
  else
  {
    if ( (unsigned __int8)IsGetKeyStatePresent() )
    {
      KeyState = GetKeyState(nVirtKey);
      WindowsDeleteString(string);
      v3 = v13;
      string = 0;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      }
    }
    else
    {
      v11 = nVirtKey;
      if ( !IsTrackedKey(&v11)
        || (KeyState = 0x8000, (CW32System::GetKeyMask(nVirtKey) & CW32System::_wKeyboardFlags) == 0) )
      {
        KeyState = 0;
      }
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v13);
    }
    v4 = v10;
    if ( v10 )
    {
      v10 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    return KeyState;
  }
}

```

## disassembly

```asm
0x1800de090  push    rbp
0x1800de092  push    rbx
0x1800de093  push    rsi
0x1800de094  push    rdi
0x1800de095  push    r14
0x1800de097  mov     rbp, rsp
0x1800de09a  sub     rsp, 30h
0x1800de09e  xor     r14d, r14d
0x1800de0a1  mov     esi, ecx
0x1800de0a3  xor     ecx, ecx; string
0x1800de0a5  mov     [rbp+var_10], r14
0x1800de0a9  mov     [rbp+arg_18], r14
0x1800de0ad  mov     [rbp+string], r14
0x1800de0b1  call    cs:__imp_WindowsDeleteString
0x1800de0b8  nop     dword ptr [rax+rax+00h]
0x1800de0bd  lea     r8, [rbp+string]; string
0x1800de0c1  mov     [rbp+string], r14
0x1800de0c5  lea     edx, [r14+1Ah]; length
0x1800de0c9  lea     rcx, ?RuntimeClass_Windows_UI_Core_CoreWindow@@3QBGB; "Windows.UI.Core.CoreWindow"
0x1800de0d0  call    cs:__imp_WindowsCreateString
0x1800de0d7  nop     dword ptr [rax+rax+00h]
0x1800de0dc  test    eax, eax
0x1800de0de  js      short loc_1800DE0FF
0x1800de0e0  mov     rcx, [rbp+string]
0x1800de0e4  lea     r8, [rbp+var_10]
0x1800de0e8  lea     rdx, _GUID_4d239005_3c2a_41b1_9022_536bb9cf93b1
0x1800de0ef  call    cs:__imp_RoGetActivationFactory
0x1800de0f6  nop     dword ptr [rax+rax+00h]
0x1800de0fb  test    eax, eax
0x1800de0fd  jns     short loc_1800DE172
0x1800de0ff  call    IsGetKeyStatePresent
0x1800de104  test    al, al
0x1800de106  jz      loc_1800DE225
0x1800de10c  mov     ecx, esi; nVirtKey
0x1800de10e  call    cs:__imp_GetKeyState
0x1800de115  nop     dword ptr [rax+rax+00h]
0x1800de11a  mov     rcx, [rbp+string]; string
0x1800de11e  movzx   ebx, ax
0x1800de121  call    cs:__imp_WindowsDeleteString
0x1800de128  nop     dword ptr [rax+rax+00h]
0x1800de12d  mov     rcx, [rbp+arg_18]
0x1800de131  mov     [rbp+string], r14
0x1800de135  test    rcx, rcx
0x1800de138  jz      short loc_1800DE14A
0x1800de13a  mov     [rbp+arg_18], r14
0x1800de13e  mov     rdx, [rcx]
0x1800de141  mov     rax, [rdx+10h]
0x1800de145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de14a  mov     rcx, [rbp+var_10]
0x1800de14e  test    rcx, rcx
0x1800de151  jz      short loc_1800DE163
0x1800de153  mov     [rbp+var_10], r14
0x1800de157  mov     rax, [rcx]
0x1800de15a  mov     rax, [rax+10h]
0x1800de15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de163  movzx   eax, bx
0x1800de166  add     rsp, 30h
0x1800de16a  pop     r14
0x1800de16c  pop     rdi
0x1800de16d  pop     rsi
0x1800de16e  pop     rbx
0x1800de16f  pop     rbp
0x1800de170  retn
0x1800de172  mov     rdi, [rbp+var_10]
0x1800de176  lea     rcx, [rbp+arg_18]
0x1800de17a  mov     rax, [rdi]
0x1800de17d  mov     rbx, [rax+30h]
0x1800de181  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800de186  lea     rdx, [rbp+arg_18]
0x1800de18a  mov     rcx, rdi
0x1800de18d  mov     rax, rbx
0x1800de190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de195  test    eax, eax
0x1800de197  js      loc_1800DE0FF
0x1800de19d  mov     rcx, [rbp+arg_18]
0x1800de1a1  test    rcx, rcx
0x1800de1a4  jz      loc_1800DE0FF
0x1800de1aa  mov     [rbp+arg_8], r14d
0x1800de1ae  lea     r8, [rbp+arg_8]
0x1800de1b2  mov     rax, [rcx]
0x1800de1b5  mov     edx, esi
0x1800de1b7  mov     rax, [rax+0A8h]
0x1800de1be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de1c3  test    eax, eax
0x1800de1c5  js      loc_1800DE0FF
0x1800de1cb  test    byte ptr [rbp+arg_8], 1
0x1800de1cf  jz      loc_1800DE0FF
0x1800de1d5  mov     rcx, [rbp+string]; string
0x1800de1d9  call    cs:__imp_WindowsDeleteString
0x1800de1e0  nop     dword ptr [rax+rax+00h]
0x1800de1e5  mov     rcx, [rbp+arg_18]
0x1800de1e9  mov     [rbp+string], r14
0x1800de1ed  test    rcx, rcx
0x1800de1f0  jz      short loc_1800DE202
0x1800de1f2  mov     [rbp+arg_18], r14
0x1800de1f6  mov     rax, [rcx]
0x1800de1f9  mov     rax, [rax+10h]
0x1800de1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de202  mov     rcx, [rbp+var_10]
0x1800de206  test    rcx, rcx
0x1800de209  jz      short loc_1800DE21B
0x1800de20b  mov     [rbp+var_10], r14
0x1800de20f  mov     rax, [rcx]
0x1800de212  mov     rax, [rax+10h]
0x1800de216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800de21b  mov     eax, 0FFFF8000h
0x1800de220  jmp     loc_1800DE166
0x1800de225  lea     rcx, [rbp+arg_8]; int *
0x1800de229  mov     [rbp+arg_8], esi
0x1800de22c  call    ?IsTrackedKey@@YA_NAEBH@Z; IsTrackedKey(int const &)
0x1800de231  test    al, al
0x1800de233  jz      short loc_1800DE24B
0x1800de235  movzx   ecx, si; unsigned __int16
0x1800de238  call    ?GetKeyMask@CW32System@@SAGG@Z; CW32System::GetKeyMask(ushort)
0x1800de23d  test    cs:?_wKeyboardFlags@CW32System@@0GA, ax; ushort CW32System::_wKeyboardFlags
0x1800de244  mov     ebx, 0FFFF8000h
0x1800de249  jnz     short loc_1800DE24E
0x1800de24b  mov     ebx, r14d
0x1800de24e  mov     rcx, [rbp+string]; string
0x1800de252  call    cs:__imp_WindowsDeleteString
0x1800de259  nop     dword ptr [rax+rax+00h]
0x1800de25e  lea     rcx, [rbp+arg_18]
0x1800de262  mov     [rbp+string], r14
0x1800de266  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800de26b  jmp     loc_1800DE14A
```
