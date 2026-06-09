# CAdvancedSettingsWriter::_s_CommitNcdAutoSetup(ADVANCED_SETTING_WRITER_VALUE const &)

- ea: `0x18001510c`
- end: `0x1800151f5`
- name: `?_s_CommitNcdAutoSetup@CAdvancedSettingsWriter@@CAXAEBUADVANCED_SETTING_WRITER_VALUE@@@Z`
- size: `233`
- prototype: `void __fastcall(const struct ADVANCED_SETTING_WRITER_VALUE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012fe0`

## callees

- `0x180012c30`
- `0x180014e6c`
- `0x18001510c`
- `0x180018a80`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015166`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180015166`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180015184`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180015184`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001519f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18001519f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800151c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800151d0`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800151c7`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800151d0`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800151be`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1800151be`

## pseudocode

```c
void __fastcall CAdvancedSettingsWriter::_s_CommitNcdAutoSetup(
        const struct ADVANCED_SETTING_WRITER_VALUE *a1,
        __int64 a2)
{
  unsigned __int8 v2; // si
  HKEY v3; // rcx
  unsigned int v4; // r9d
  SC_HANDLE v5; // rax
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rax
  SC_HANDLE v8; // rbx
  unsigned int v9; // [rsp+28h] [rbp-50h]
  struct _SECURITY_ATTRIBUTES *v10; // [rsp+30h] [rbp-48h]
  int v11; // [rsp+40h] [rbp-38h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-30h] BYREF

  v2 = ValueFromButton_bool_(&qword_18001EC80, a2, *((unsigned int *)a1 + 1));
  v11 = v2;
  _RegSetKeyValueWithSDDL(
    v3,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\NcdAutoSetup\\Private",
    L"AutoSetup",
    v4,
    &v11,
    v9,
    v10);
  v5 = OpenSCManagerW(0, 0, 1u);
  v6 = v5;
  if ( v5 )
  {
    v7 = OpenServiceW(v5, L"NcdAutoSetup", 0x30u);
    v8 = v7;
    if ( v7 )
    {
      if ( v2 )
      {
        StartServiceW(v7, 0, 0);
      }
      else
      {
        memset(&ServiceStatus, 0, sizeof(ServiceStatus));
        ControlService(v7, 1u, &ServiceStatus);
      }
      CloseServiceHandle(v8);
    }
    CloseServiceHandle(v6);
  }
}

```

## disassembly

```asm
0x18001510c  mov     [rsp+arg_0], rbx
0x180015111  mov     [rsp+arg_8], rsi
0x180015116  push    rdi
0x180015117  sub     rsp, 70h
0x18001511b  mov     rax, cs:__security_cookie
0x180015122  xor     rax, rsp
0x180015125  mov     [rsp+78h+var_10], rax
0x18001512a  mov     r8d, [rcx+4]
0x18001512e  lea     rcx, qword_18001EC80
0x180015135  call    _ValueFromButton_bool_
0x18001513a  movzx   esi, al
0x18001513d  lea     r8, Value; "AutoSetup"
0x180015144  lea     rax, [rsp+78h+var_38]
0x180015149  mov     [rsp+78h+var_38], esi
0x18001514d  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180015154  mov     [rsp+78h+var_58], rax; void *
0x180015159  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x18001515e  xor     edx, edx; lpDatabaseName
0x180015160  xor     ecx, ecx; lpMachineName
0x180015162  lea     r8d, [rdx+1]; dwDesiredAccess
0x180015166  call    cs:__imp_OpenSCManagerW
0x18001516c  mov     rdi, rax
0x18001516f  test    rax, rax
0x180015172  jz      short loc_1800151D6
0x180015174  mov     r8d, 30h ; '0'; dwDesiredAccess
0x18001517a  lea     rdx, ServiceName; "NcdAutoSetup"
0x180015181  mov     rcx, rax; hSCManager
0x180015184  call    cs:__imp_OpenServiceW
0x18001518a  mov     rbx, rax
0x18001518d  test    rax, rax
0x180015190  jz      short loc_1800151CD
0x180015192  mov     rcx, rax; hService
0x180015195  test    sil, sil
0x180015198  jz      short loc_1800151A7
0x18001519a  xor     r8d, r8d; lpServiceArgVectors
0x18001519d  xor     edx, edx; dwNumServiceArgs
0x18001519f  call    cs:__imp_StartServiceW
0x1800151a5  jmp     short loc_1800151C4
0x1800151a7  xorps   xmm0, xmm0
0x1800151aa  lea     r8, [rsp+78h+ServiceStatus]; lpServiceStatus
0x1800151af  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x1800151b4  mov     edx, 1; dwControl
0x1800151b9  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800151be  call    cs:__imp_ControlService
0x1800151c4  mov     rcx, rbx; hSCObject
0x1800151c7  call    cs:__imp_CloseServiceHandle
0x1800151cd  mov     rcx, rdi; hSCObject
0x1800151d0  call    cs:__imp_CloseServiceHandle
0x1800151d6  mov     rcx, [rsp+78h+var_10]
0x1800151db  xor     rcx, rsp; StackCookie
0x1800151de  call    __security_check_cookie
0x1800151e3  lea     r11, [rsp+78h+var_8]
0x1800151e8  mov     rbx, [r11+10h]
0x1800151ec  mov     rsi, [r11+18h]
0x1800151f0  mov     rsp, r11
0x1800151f3  pop     rdi
0x1800151f4  retn
```
