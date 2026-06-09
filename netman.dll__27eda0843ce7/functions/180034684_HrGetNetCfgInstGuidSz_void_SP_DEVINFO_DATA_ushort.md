# HrGetNetCfgInstGuidSz(void *,_SP_DEVINFO_DATA *,ushort *)

- ea: `0x180034684`
- end: `0x1800347d5`
- name: `?HrGetNetCfgInstGuidSz@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAG@Z`
- size: `337`
- prototype: `int(void *, struct _SP_DEVINFO_DATA *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800345e8`

## callees

- `0x180001710`
- `0x18000538c`
- `0x180032c3c`
- `0x180034684`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18003478a`
- `ADVAPI32!RegCloseKey` at `0x18003478a`
- `ADVAPI32!RegQueryValueExW` at `0x180034755`
- `ADVAPI32!RegQueryValueExW` at `0x180034755`
- `KERNEL32!GetLastError` at `0x1800346db`
- `KERNEL32!GetLastError` at `0x1800346db`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x1800346c5`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x1800346c5`

## pseudocode

```c
__int64 __fastcall HrGetNetCfgInstGuidSz(void *a1, struct _SP_DEVINFO_DATA *a2, BYTE *a3)
{
  HKEY v4; // rdi
  signed int LastError; // eax
  unsigned int v6; // ebx
  PVOID *v7; // rcx
  LSTATUS v8; // eax
  __int64 v9; // rcx
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-24h] BYREF

  cbData = 0;
  Type = 0;
  v4 = SetupDiOpenDevRegKey(a1, a2, 1u, 0, 2u, 0x20019u);
  if ( v4 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_16:
          if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 )
            WPP_SF_d(v7[2], 11, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids, v6);
          return v6;
        }
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids, v6);
LABEL_15:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_16;
      }
    }
  }
  else
  {
    cbData = 78;
    v8 = RegQueryValueExW(v4, L"NetCfgInstanceId", 0, &Type, a3, &cbData);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( !v6 && Type != 1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v9);
      if ( Type != 1 )
        v6 = -2147023092;
    }
    RegCloseKey(v4);
    if ( (v6 & 0x80000000) != 0 )
      goto LABEL_15;
  }
  return v6;
}

```

## disassembly

```asm
0x180034684  push    rbx
0x180034686  push    rbp
0x180034687  push    rdi
0x180034688  sub     rsp, 40h
0x18003468c  mov     rax, cs:__security_cookie
0x180034693  xor     rax, rsp
0x180034696  mov     [rsp+58h+var_20], rax
0x18003469b  xor     r9d, r9d; HwProfile
0x18003469e  mov     [rsp+58h+samDesired], 20019h; samDesired
0x1800346a6  mov     rbx, r8
0x1800346a9  mov     [rsp+58h+cbData], 0
0x1800346b1  mov     [rsp+58h+Type], 0
0x1800346b9  mov     [rsp+58h+KeyType], 2; KeyType
0x1800346c1  lea     r8d, [r9+1]; Scope
0x1800346c5  call    cs:__imp_SetupDiOpenDevRegKey
0x1800346cb  lea     rbp, WPP_GLOBAL_Control
0x1800346d2  mov     rdi, rax
0x1800346d5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800346d9  jnz     short loc_18003472C
0x1800346db  call    cs:__imp_GetLastError
0x1800346e1  mov     ebx, eax
0x1800346e3  test    eax, eax
0x1800346e5  jle     short loc_1800346F0
0x1800346e7  movzx   ebx, ax
0x1800346ea  or      ebx, 80070000h
0x1800346f0  test    ebx, ebx
0x1800346f2  jns     loc_1800347BE
0x1800346f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800346ff  cmp     rcx, rbp
0x180034702  jz      loc_1800347BE
0x180034708  test    byte ptr [rcx+1Ch], 1
0x18003470c  jz      loc_18003479B
0x180034712  mov     rcx, [rcx+10h]
0x180034716  lea     r8, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids
0x18003471d  mov     edx, 0Ah
0x180034722  mov     r9d, ebx
0x180034725  call    WPP_SF_d
0x18003472a  jmp     short loc_180034794
0x18003472c  lea     rax, [rsp+58h+cbData]
0x180034731  mov     [rsp+58h+cbData], 4Eh ; 'N'
0x180034739  mov     qword ptr [rsp+58h+samDesired], rax; lpcbData
0x18003473e  lea     r9, [rsp+58h+Type]; lpType
0x180034743  xor     r8d, r8d; lpReserved
0x180034746  mov     qword ptr [rsp+58h+KeyType], rbx; lpData
0x18003474b  lea     rdx, ValueName; "NetCfgInstanceId"
0x180034752  mov     rcx, rdi; hKey
0x180034755  call    cs:__imp_RegQueryValueExW
0x18003475b  mov     ebx, eax
0x18003475d  test    eax, eax
0x18003475f  jle     short loc_18003476A
0x180034761  movzx   ebx, ax
0x180034764  or      ebx, 80070000h
0x18003476a  test    ebx, ebx
0x18003476c  jnz     short loc_180034787
0x18003476e  cmp     [rsp+58h+Type], 1
0x180034773  jz      short loc_180034787
0x180034775  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003477a  cmp     [rsp+58h+Type], 1
0x18003477f  mov     eax, 8007070Ch
0x180034784  cmovnz  ebx, eax
0x180034787  mov     rcx, rdi; hKey
0x18003478a  call    cs:__imp_RegCloseKey
0x180034790  test    ebx, ebx
0x180034792  jns     short loc_1800347BE
0x180034794  mov     rcx, cs:WPP_GLOBAL_Control
0x18003479b  cmp     rcx, rbp
0x18003479e  jz      short loc_1800347BE
0x1800347a0  test    byte ptr [rcx+1Ch], 1
0x1800347a4  jz      short loc_1800347BE
0x1800347a6  mov     rcx, [rcx+10h]
0x1800347aa  lea     r8, WPP_127a71f7b91d3825fada0ff6fce676d2_Traceguids
0x1800347b1  mov     edx, 0Bh
0x1800347b6  mov     r9d, ebx
0x1800347b9  call    WPP_SF_d
0x1800347be  mov     eax, ebx
0x1800347c0  mov     rcx, [rsp+58h+var_20]
0x1800347c5  xor     rcx, rsp; StackCookie
0x1800347c8  call    __security_check_cookie
0x1800347cd  add     rsp, 40h
0x1800347d1  pop     rdi
0x1800347d2  pop     rbp
0x1800347d3  pop     rbx
0x1800347d4  retn
```
