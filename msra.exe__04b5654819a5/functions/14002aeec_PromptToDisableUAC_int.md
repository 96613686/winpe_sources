# PromptToDisableUAC(int *)

- ea: `0x14002aeec`
- end: `0x14002b037`
- name: `?PromptToDisableUAC@@YAJPEAH@Z`
- size: `331`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002bd4c`
- `0x14002cd78`

## callees

- `0x14002a418`
- `0x14002aeec`
- `0x140034ce4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14002b020`
- `ADVAPI32!RegCloseKey` at `0x14002b020`
- `ADVAPI32!RegOpenKeyExW` at `0x14002afa8`
- `ADVAPI32!RegOpenKeyExW` at `0x14002afa8`
- `ADVAPI32!RegQueryValueExW` at `0x14002affb`
- `ADVAPI32!RegQueryValueExW` at `0x14002affb`

## string_xrefs

- `0x14002af3d`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall PromptToDisableUAC(int *a1)
{
  unsigned int v2; // ebx
  signed int v3; // eax
  CEventLogger *v4; // rcx
  CEventLogger *v5; // rcx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  int v8; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  cbData = 0;
  Data = 0;
  Type = 4;
  v8 = 0;
  if ( a1 )
  {
    v3 = IsUserAdmin(&v8);
    v2 = v3;
    if ( v3 < 0 )
    {
      CEventLogger::LogError(
        v4,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x10F1u,
        L"PromptToDisableUAC",
        v3);
      goto LABEL_13;
    }
    if ( v8 == 1 )
    {
      v2 = 0;
    }
    else
    {
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System",
             0,
             1u,
             &hKey) )
      {
        v2 = -2147467259;
        CEventLogger::LogError(
          v5,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x1105u,
          L"PromptToDisableUAC",
          0x80004005);
        goto LABEL_13;
      }
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"EnableUIADesktopToggle", 0, &Type, (LPBYTE)&Data, &cbData) )
      {
        *a1 = Data == 0;
        goto LABEL_13;
      }
    }
    *a1 = 1;
    goto LABEL_13;
  }
  v2 = -2147467261;
  CEventLogger::LogError(
    0,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0x10EBu,
    L"PromptToDisableUAC",
    0x80004003);
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x14002aeec  push    rbp
0x14002aeee  push    rbx
0x14002aeef  push    rdi
0x14002aef0  mov     rbp, rsp
0x14002aef3  sub     rsp, 40h
0x14002aef7  mov     [rbp+hKey], 0
0x14002aeff  mov     rdi, rcx
0x14002af02  mov     [rbp+cbData], 0
0x14002af09  mov     [rbp+Data], 0
0x14002af10  mov     [rbp+Type], 4
0x14002af17  mov     [rbp+arg_0], 0
0x14002af1e  test    rcx, rcx
0x14002af21  jnz     short loc_14002AF5A
0x14002af23  mov     ebx, 80004003h
0x14002af28  mov     dword ptr [rsp+40h+lpcbData], 80004003h; unsigned int
0x14002af30  mov     r9d, 10EBh; unsigned int
0x14002af36  lea     rax, aPrompttodisabl; "PromptToDisableUAC"
0x14002af3d  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002af44  mov     [rsp+40h+phkResult], rax; unsigned __int16 *
0x14002af49  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002af50  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002af55  jmp     loc_14002B017
0x14002af5a  lea     rcx, [rbp+arg_0]; int *
0x14002af5e  call    ?IsUserAdmin@@YAJPEAH@Z; IsUserAdmin(int *)
0x14002af63  mov     ebx, eax
0x14002af65  test    eax, eax
0x14002af67  jns     short loc_14002AF75
0x14002af69  mov     dword ptr [rsp+40h+lpcbData], eax
0x14002af6d  mov     r9d, 10F1h
0x14002af73  jmp     short loc_14002AF36
0x14002af75  cmp     [rbp+arg_0], 1
0x14002af79  jnz     short loc_14002AF88
0x14002af7b  xor     ebx, ebx
0x14002af7d  mov     dword ptr [rdi], 1
0x14002af83  jmp     loc_14002B017
0x14002af88  lea     rax, [rbp+hKey]
0x14002af8c  mov     r9d, 1; samDesired
0x14002af92  xor     r8d, r8d; ulOptions
0x14002af95  mov     [rsp+40h+phkResult], rax; phkResult
0x14002af9a  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x14002afa1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14002afa8  call    cs:__imp_RegOpenKeyExW
0x14002afaf  nop     dword ptr [rax+rax+00h]
0x14002afb4  test    eax, eax
0x14002afb6  jz      short loc_14002AFD0
0x14002afb8  mov     ebx, 80004005h
0x14002afbd  mov     dword ptr [rsp+40h+lpcbData], 80004005h
0x14002afc5  mov     r9d, 1105h
0x14002afcb  jmp     loc_14002AF36
0x14002afd0  mov     rcx, [rbp+hKey]; hKey
0x14002afd4  lea     rax, [rbp+cbData]
0x14002afd8  mov     [rsp+40h+lpcbData], rax; lpcbData
0x14002afdd  lea     r9, [rbp+Type]; lpType
0x14002afe1  lea     rax, [rbp+Data]
0x14002afe5  mov     [rbp+cbData], 4
0x14002afec  xor     r8d, r8d; lpReserved
0x14002afef  mov     [rsp+40h+phkResult], rax; lpData
0x14002aff4  lea     rdx, ValueName; "EnableUIADesktopToggle"
0x14002affb  call    cs:__imp_RegQueryValueExW
0x14002b002  nop     dword ptr [rax+rax+00h]
0x14002b007  test    eax, eax
0x14002b009  jnz     loc_14002AF7D
0x14002b00f  cmp     [rbp+Data], eax
0x14002b012  setz    al
0x14002b015  mov     [rdi], eax
0x14002b017  mov     rcx, [rbp+hKey]; hKey
0x14002b01b  test    rcx, rcx
0x14002b01e  jz      short loc_14002B02C
0x14002b020  call    cs:__imp_RegCloseKey
0x14002b027  nop     dword ptr [rax+rax+00h]
0x14002b02c  mov     eax, ebx
0x14002b02e  add     rsp, 40h
0x14002b032  pop     rdi
0x14002b033  pop     rbx
0x14002b034  pop     rbp
0x14002b035  retn
```
