# CGpuManager::EnableDisableHWGpuInSessions(void)

- ea: `0x18001dbb0`
- end: `0x18001dd84`
- name: `?EnableDisableHWGpuInSessions@CGpuManager@@QEAAXXZ`
- size: `468`
- prototype: `void __fastcall(CGpuManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002ae4c`
- `0x180051464`

## callees

- `0x1800074c0`
- `0x180017da0`
- `0x18001dbb0`
- `0x18001e3e8`
- `0x18001e8e0`
- `0x18001ea44`
- `0x18007a85c`
- `0x180082608`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001dd5f`
- `msvcp_win!_Mtx_unlock` at `0x18001dd5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dc4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001dc4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc1f`

## string_xrefs

- `0x18001dc41`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18001dcb9`: `OpenKey failed: 0x%x in %s`
- `0x18001dcff`: `ReadRegDWord failed: 0x%x in %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CGpuManager::EnableDisableHWGpuInSessions(CGpuManager *this)
{
  LSTATUS v2; // eax
  bool v3; // sf
  int v4; // eax
  bool v5; // sf
  signed int v6; // eax
  bool v7; // sf
  signed int v8; // eax
  bool v9; // sf
  unsigned int v10; // edi
  int inited; // eax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-40h]
  _QWORD v13[2]; // [rsp+30h] [rbp-30h] BYREF
  int v14; // [rsp+40h] [rbp-20h]
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  int v16; // [rsp+50h] [rbp-10h]
  int v17; // [rsp+54h] [rbp-Ch]
  unsigned int v18; // [rsp+88h] [rbp+28h] BYREF
  char *v19; // [rsp+90h] [rbp+30h] BYREF

  v13[0] = &CRegistry::`vftable';
  v13[1] = 0;
  v14 = 0;
  hKey = 0;
  v16 = -1;
  v17 = -1;
  v18 = 0;
  LODWORD(v19) = 0;
  if ( (int)CSLQuery::IsWVDEnabled((int *)&v19) >= 0 )
    v18 = (_DWORD)v19 != 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
         0,
         0x20019u,
         &hKey);
  v3 = v2 < 0;
  if ( v2 )
  {
    hKey = 0;
    if ( v2 > 0 )
      v3 = 1;
  }
  if ( v3 )
    goto LABEL_10;
  v4 = CRegistry::ReadRegDWord((CRegistry *)v13, L"bEnumerateHWBeforeSW", &v18);
  v5 = v4 < 0;
  if ( v4 > 0 )
    v5 = 1;
  if ( v5 )
  {
LABEL_10:
    v6 = CRegistry::OpenKey(
           (CRegistry *)v13,
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
           0x20019u,
           phkResult);
    v7 = v6 < 0;
    if ( v6 > 0 )
    {
      v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = v6 < 0;
    }
    if ( v7 )
    {
      _DbgPrintMessage(8, "OpenKey failed: 0x%x in %s", (unsigned int)v6, "CGpuManager::EnableDisableHWGpuInSessions");
      goto LABEL_25;
    }
    v8 = CRegistry::ReadRegDWord((CRegistry *)v13, L"fUseHardwareGPU", &v18);
    if ( v8 != 2 )
    {
      v9 = v8 < 0;
      if ( v8 > 0 )
      {
        v8 = (unsigned __int16)v8 | 0x80070000;
        v9 = v8 < 0;
      }
      if ( v9 )
      {
        _DbgPrintMessage(
          8,
          "ReadRegDWord failed: 0x%x in %s",
          (unsigned int)v8,
          "CGpuManager::EnableDisableHWGpuInSessions");
        goto LABEL_25;
      }
    }
  }
  v19 = (char *)this + 1608;
  std::_Mutex_base::lock((CGpuManager *)((char *)this + 1608));
  v10 = v18;
  if ( *((_DWORD *)this + 400) || v18 != 1 || (inited = CGpuManager::InitGpuList(this), inited >= 0) )
    *((_DWORD *)this + 400) = v10;
  else
    _DbgPrintMessage(8, "InitGpuList failed: 0x%x in %s", inited, "CGpuManager::EnableDisableHWGpuInSessions");
  _Mtx_unlock((CGpuManager *)((char *)this + 1608));
LABEL_25:
  CRegistry::~CRegistry((CRegistry *)v13);
}

```

## disassembly

```asm
0x18001dbb0  mov     [rsp-18h+arg_0], rbx
0x18001dbb5  mov     [rsp-18h+arg_18], rsi
0x18001dbba  push    rbp
0x18001dbbb  push    rdi
0x18001dbbc  push    r15
0x18001dbbe  mov     rbp, rsp
0x18001dbc1  sub     rsp, 60h
0x18001dbc5  mov     rsi, rcx
0x18001dbc8  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18001dbcf  mov     [rbp+var_30], rax
0x18001dbd3  mov     [rbp+var_28], 0
0x18001dbdb  mov     [rbp+var_20], 0
0x18001dbe2  mov     [rbp+hKey], 0
0x18001dbea  or      eax, 0FFFFFFFFh
0x18001dbed  mov     [rbp+var_10], eax
0x18001dbf0  mov     [rbp+var_C], eax
0x18001dbf3  xor     ebx, ebx
0x18001dbf5  mov     [rbp+arg_8], ebx
0x18001dbf8  mov     dword ptr [rbp+arg_10], ebx
0x18001dbfb  lea     rcx, [rbp+arg_10]; int *
0x18001dbff  call    ?IsWVDEnabled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsWVDEnabled(int *)
0x18001dc04  lea     r15d, [rbx+1]
0x18001dc08  test    eax, eax
0x18001dc0a  js      short loc_18001DC16
0x18001dc0c  cmp     dword ptr [rbp+arg_10], ebx
0x18001dc0f  cmovnz  ebx, r15d
0x18001dc13  mov     [rbp+arg_8], ebx
0x18001dc16  mov     rcx, [rbp+hKey]; hKey
0x18001dc1a  test    rcx, rcx
0x18001dc1d  jz      short loc_18001DC2D
0x18001dc1f  call    cs:__imp_RegCloseKey
0x18001dc25  mov     [rbp+hKey], 0
0x18001dc2d  lea     rax, [rbp+hKey]
0x18001dc31  mov     [rsp+60h+phkResult], rax; unsigned __int16 *
0x18001dc36  mov     edi, 20019h
0x18001dc3b  mov     r9d, edi; samDesired
0x18001dc3e  xor     r8d, r8d; ulOptions
0x18001dc41  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18001dc48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001dc4f  call    cs:__imp_RegOpenKeyExW
0x18001dc55  mov     ebx, 80070000h
0x18001dc5a  test    eax, eax
0x18001dc5c  jz      short loc_18001DC6F
0x18001dc5e  mov     [rbp+hKey], 0
0x18001dc66  jle     short loc_18001DC6F
0x18001dc68  movzx   eax, ax
0x18001dc6b  or      eax, ebx
0x18001dc6d  test    eax, eax
0x18001dc6f  js      short loc_18001DC92
0x18001dc71  lea     r8, [rbp+arg_8]; unsigned int *
0x18001dc75  lea     rdx, aBenumeratehwbe; "bEnumerateHWBeforeSW"
0x18001dc7c  lea     rcx, [rbp+var_30]; this
0x18001dc80  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18001dc85  test    eax, eax
0x18001dc87  jle     short loc_18001DC90
0x18001dc89  movzx   eax, ax
0x18001dc8c  or      eax, ebx
0x18001dc8e  test    eax, eax
0x18001dc90  jns     short loc_18001DD08
0x18001dc92  mov     r9d, edi; unsigned int
0x18001dc95  lea     r8, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x18001dc9c  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001dca3  lea     rcx, [rbp+var_30]; this
0x18001dca7  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18001dcac  test    eax, eax
0x18001dcae  jle     short loc_18001DCB7
0x18001dcb0  movzx   eax, ax
0x18001dcb3  or      eax, ebx
0x18001dcb5  test    eax, eax
0x18001dcb7  jns     short loc_18001DCD9
0x18001dcb9  lea     rdx, aOpenkeyFailed0; "OpenKey failed: 0x%x in %s"
0x18001dcc0  mov     r8d, eax
0x18001dcc3  lea     r9, aCgpumanagerEna; "CGpuManager::EnableDisableHWGpuInSessio"...
0x18001dcca  mov     ecx, 8; int
0x18001dccf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001dcd4  jmp     loc_18001DD66
0x18001dcd9  lea     r8, [rbp+arg_8]; unsigned int *
0x18001dcdd  lea     rdx, aFusehardwaregp; "fUseHardwareGPU"
0x18001dce4  lea     rcx, [rbp+var_30]; this
0x18001dce8  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18001dced  cmp     eax, 2
0x18001dcf0  jz      short loc_18001DD08
0x18001dcf2  test    eax, eax
0x18001dcf4  jle     short loc_18001DCFD
0x18001dcf6  movzx   eax, ax
0x18001dcf9  or      eax, ebx
0x18001dcfb  test    eax, eax
0x18001dcfd  jns     short loc_18001DD08
0x18001dcff  lea     rdx, aReadregdwordFa; "ReadRegDWord failed: 0x%x in %s"
0x18001dd06  jmp     short loc_18001DCC0
0x18001dd08  lea     rbx, [rsi+648h]
0x18001dd0f  mov     [rbp+arg_10], rbx
0x18001dd13  mov     rcx, rbx; this
0x18001dd16  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001dd1b  nop
0x18001dd1c  mov     edi, [rbp+arg_8]
0x18001dd1f  cmp     dword ptr [rsi+640h], 0
0x18001dd26  jnz     short loc_18001DD56
0x18001dd28  cmp     edi, r15d
0x18001dd2b  jnz     short loc_18001DD56
0x18001dd2d  mov     rcx, rsi; this
0x18001dd30  call    ?InitGpuList@CGpuManager@@AEAAJXZ; CGpuManager::InitGpuList(void)
0x18001dd35  test    eax, eax
0x18001dd37  jns     short loc_18001DD56
0x18001dd39  lea     r9, aCgpumanagerEna; "CGpuManager::EnableDisableHWGpuInSessio"...
0x18001dd40  mov     r8d, eax
0x18001dd43  lea     rdx, aInitgpulistFai; "InitGpuList failed: 0x%x in %s"
0x18001dd4a  mov     ecx, 8; int
0x18001dd4f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001dd54  jmp     short loc_18001DD5C
0x18001dd56  mov     [rsi+640h], edi
0x18001dd5c  mov     rcx, rbx; _Mtx_t
0x18001dd5f  call    cs:__imp__Mtx_unlock
0x18001dd65  nop
0x18001dd66  lea     rcx, [rbp+var_30]; this
0x18001dd6a  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001dd6f  lea     r11, [rsp+60h+var_s0]
0x18001dd74  mov     rbx, [r11+20h]
0x18001dd78  mov     rsi, [r11+38h]
0x18001dd7c  mov     rsp, r11
0x18001dd7f  pop     r15
0x18001dd81  pop     rdi
0x18001dd82  pop     rbp
0x18001dd83  retn
```
