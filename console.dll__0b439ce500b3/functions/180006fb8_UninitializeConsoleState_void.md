# UninitializeConsoleState(void)

- ea: `0x180006fb8`
- end: `0x180007053`
- name: `?UninitializeConsoleState@@YAXXZ`
- size: `155`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007c60`
- `0x18000f100`

## callees

- `0x180006fb8`
- `0x1800070a4`
- `0x180008aac`
- `0x18001886c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fda`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006fda`

## string_xrefs

- `0x180007006`: `onecore\windows\core\console\open\src\propsheet\util.cpp`

## pseudocode

```c
void UninitializeConsoleState(void)
{
  void *v0; // rcx
  int v1; // eax
  HINSTANCE v2; // rbx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( g_fHostedInFileProperties )
  {
    v0 = (void *)*((_QWORD *)gpStateInfo + 25);
    if ( v0 )
    {
      CoTaskMemFree(v0);
      *((_QWORD *)gpStateInfo + 25) = 0;
    }
  }
  v1 = TrueTypeFontList::s_Destroy();
  if ( v1 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\windows\\core\\console\\open\\src\\propsheet\\util.cpp",
      (const char *)(unsigned int)v1,
      v3);
  v2 = ghInstance;
  IsolationAwareUnregisterClassW(L"cpColor", ghInstance);
  IsolationAwareUnregisterClassW(L"WOAWinPreview", v2);
  IsolationAwareUnregisterClassW(L"WOAFontPreview", v2);
}

```

## disassembly

```asm
0x180006fb8  push    rbx; int
0x180006fba  sub     rsp, 20h
0x180006fbe  cmp     cs:?g_fHostedInFileProperties@@3HA, 0; int g_fHostedInFileProperties
0x180006fc5  jz      short loc_180006FF8
0x180006fc7  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180006fce  mov     rcx, [rax+0C8h]; pv
0x180006fd5  test    rcx, rcx
0x180006fd8  jz      short loc_180006FF8
0x180006fda  call    cs:__imp_CoTaskMemFree
0x180006fe1  nop     dword ptr [rax+rax+00h]
0x180006fe6  mov     rax, cs:?gpStateInfo@@3PEAU_CONSOLE_STATE_INFO@@EA; _CONSOLE_STATE_INFO * gpStateInfo
0x180006fed  mov     qword ptr [rax+0C8h], 0
0x180006ff8  call    ?s_Destroy@TrueTypeFontList@@SAJXZ; TrueTypeFontList::s_Destroy(void)
0x180006ffd  test    eax, eax
0x180006fff  jns     short loc_18000701A
0x180007001  mov     rcx, [rsp+28h]; this
0x180007006  lea     r8, aOnecoreWindows_6; "onecore\\windows\\core\\console\\open\\"...
0x18000700d  mov     r9d, eax; char *
0x180007010  mov     edx, 53h ; 'S'; void *
0x180007015  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18000701a  mov     rbx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * ghInstance
0x180007021  lea     rcx, aCpcolor; "cpColor"
0x180007028  mov     rdx, rbx; hInstance
0x18000702b  call    IsolationAwareUnregisterClassW
0x180007030  mov     rdx, rbx; hInstance
0x180007033  lea     rcx, aWoawinpreview; "WOAWinPreview"
0x18000703a  call    IsolationAwareUnregisterClassW
0x18000703f  mov     rdx, rbx; hInstance
0x180007042  lea     rcx, aWoafontpreview; "WOAFontPreview"
0x180007049  add     rsp, 20h
0x18000704d  pop     rbx
0x18000704e  jmp     IsolationAwareUnregisterClassW
```
