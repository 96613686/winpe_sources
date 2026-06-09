# CDialogActivateGuard::_GetActivationDelay(void)

- ea: `0x18003e190`
- end: `0x18003e226`
- name: `?_GetActivationDelay@CDialogActivateGuard@@AEAA_KXZ`
- size: `150`
- prototype: `unsigned __int64 __fastcall(CDialogActivateGuard *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003de24`

## callees

- `0x18003e190`

## import_xrefs

- `USER32!GetDoubleClickTime` at `0x18003e1a7`
- `USER32!GetDoubleClickTime` at `0x18003e1b6`
- `USER32!GetDoubleClickTime` at `0x18003e1a7`
- `USER32!GetDoubleClickTime` at `0x18003e1b6`
- `SHLWAPI!SHRegGetValueW` at `0x18003e205`
- `SHLWAPI!SHRegGetValueW` at `0x18003e205`

## string_xrefs

- `0x18003e1ca`: `SecurityDialogActivationDelay`

## pseudocode

```c
__int64 __fastcall CDialogActivateGuard::_GetActivationDelay(CDialogActivateGuard *this)
{
  __int64 v1; // rbx
  UINT DoubleClickTime; // eax
  UINT v4; // edx
  DWORD pcbData; // [rsp+50h] [rbp+8h] BYREF
  __int64 pvData; // [rsp+58h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 1);
  if ( v1 == -1 )
  {
    DoubleClickTime = GetDoubleClickTime();
    v4 = 300;
    if ( DoubleClickTime >= 0x12C )
      v4 = GetDoubleClickTime();
    v1 = v4;
    pvData = v4;
    pcbData = 8;
    if ( !SHRegGetValueW(
            HKEY_CURRENT_USER,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
            L"SecurityDialogActivationDelay",
            64,
            0,
            &pvData,
            &pcbData) )
      v1 = pvData;
    *((_QWORD *)this + 1) = v1;
  }
  return v1;
}

```

## disassembly

```asm
0x18003e190  mov     [rsp+arg_10], rbx
0x18003e195  push    rdi
0x18003e196  sub     rsp, 40h
0x18003e19a  mov     rbx, [rcx+8]
0x18003e19e  mov     rdi, rcx
0x18003e1a1  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18003e1a5  jnz     short loc_18003E218
0x18003e1a7  call    cs:__imp_GetDoubleClickTime
0x18003e1ad  mov     edx, 12Ch
0x18003e1b2  cmp     eax, edx
0x18003e1b4  jb      short loc_18003E1BE
0x18003e1b6  call    cs:__imp_GetDoubleClickTime
0x18003e1bc  mov     edx, eax
0x18003e1be  mov     ebx, edx
0x18003e1c0  lea     rax, [rsp+48h+arg_0]
0x18003e1c5  mov     [rsp+48h+pcbData], rax; pcbData
0x18003e1ca  lea     r8, pszValue; "SecurityDialogActivationDelay"
0x18003e1d1  lea     rax, [rsp+48h+arg_8]
0x18003e1d6  mov     [rsp+48h+arg_8], rbx
0x18003e1db  mov     [rsp+48h+pvData], rax; pvData
0x18003e1e0  lea     rdx, pszSubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003e1e7  mov     r9d, 40h ; '@'; srrfFlags
0x18003e1ed  mov     [rsp+48h+pdwType], 0; pdwType
0x18003e1f6  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18003e1fd  mov     [rsp+48h+arg_0], 8
0x18003e205  call    cs:__imp_SHRegGetValueW
0x18003e20b  test    eax, eax
0x18003e20d  jnz     short loc_18003E214
0x18003e20f  mov     rbx, [rsp+48h+arg_8]
0x18003e214  mov     [rdi+8], rbx
0x18003e218  mov     rax, rbx
0x18003e21b  mov     rbx, [rsp+48h+arg_10]
0x18003e220  add     rsp, 40h
0x18003e224  pop     rdi
0x18003e225  retn
```
