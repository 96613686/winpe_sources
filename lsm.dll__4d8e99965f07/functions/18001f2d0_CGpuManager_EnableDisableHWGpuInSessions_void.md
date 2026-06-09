# CGpuManager::EnableDisableHWGpuInSessions(void)

- ea: `0x18001f2d0`
- end: `0x18001f4b7`
- name: `?EnableDisableHWGpuInSessions@CGpuManager@@QEAAXXZ`
- size: `487`
- prototype: `void __fastcall(CGpuManager *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cf00`
- `0x180054be4`

## callees

- `0x1800077a0`
- `0x18000af60`
- `0x18000bcc8`
- `0x18001f2d0`
- `0x18001fb7c`
- `0x180020094`
- `0x18007f064`
- `0x18008724c`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001f48b`
- `msvcp_win!_Mtx_unlock` at `0x18001f48b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f375`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f375`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f33f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f33f`

## string_xrefs

- `0x18001f367`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x18001f3e5`: `OpenKey failed: 0x%x in %s`
- `0x18001f42b`: `ReadRegDWord failed: 0x%x in %s`

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
0x18001f2d0  mov     [rsp-18h+arg_0], rbx
0x18001f2d5  mov     [rsp-18h+arg_18], rsi
0x18001f2da  push    rbp
0x18001f2db  push    rdi
0x18001f2dc  push    r15
0x18001f2de  mov     rbp, rsp
0x18001f2e1  sub     rsp, 60h
0x18001f2e5  mov     rsi, rcx
0x18001f2e8  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18001f2ef  mov     [rbp+var_30], rax
0x18001f2f3  mov     [rbp+var_28], 0
0x18001f2fb  mov     [rbp+var_20], 0
0x18001f302  mov     [rbp+hKey], 0
0x18001f30a  or      eax, 0FFFFFFFFh
0x18001f30d  mov     [rbp+var_10], eax
0x18001f310  mov     [rbp+var_C], eax
0x18001f313  xor     ebx, ebx
0x18001f315  mov     [rbp+arg_8], ebx
0x18001f318  mov     dword ptr [rbp+arg_10], ebx
0x18001f31b  lea     rcx, [rbp+arg_10]; int *
0x18001f31f  call    ?IsWVDEnabled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsWVDEnabled(int *)
0x18001f324  lea     r15d, [rbx+1]
0x18001f328  test    eax, eax
0x18001f32a  js      short loc_18001F336
0x18001f32c  cmp     dword ptr [rbp+arg_10], ebx
0x18001f32f  cmovnz  ebx, r15d
0x18001f333  mov     [rbp+arg_8], ebx
0x18001f336  mov     rcx, [rbp+hKey]; hKey
0x18001f33a  test    rcx, rcx
0x18001f33d  jz      short loc_18001F353
0x18001f33f  call    cs:__imp_RegCloseKey
0x18001f346  nop     dword ptr [rax+rax+00h]
0x18001f34b  mov     [rbp+hKey], 0
0x18001f353  lea     rax, [rbp+hKey]
0x18001f357  mov     [rsp+60h+phkResult], rax; unsigned __int16 *
0x18001f35c  mov     edi, 20019h
0x18001f361  mov     r9d, edi; samDesired
0x18001f364  xor     r8d, r8d; ulOptions
0x18001f367  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows "...
0x18001f36e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f375  call    cs:__imp_RegOpenKeyExW
0x18001f37c  nop     dword ptr [rax+rax+00h]
0x18001f381  mov     ebx, 80070000h
0x18001f386  test    eax, eax
0x18001f388  jz      short loc_18001F39B
0x18001f38a  mov     [rbp+hKey], 0
0x18001f392  jle     short loc_18001F39B
0x18001f394  movzx   eax, ax
0x18001f397  or      eax, ebx
0x18001f399  test    eax, eax
0x18001f39b  js      short loc_18001F3BE
0x18001f39d  lea     r8, [rbp+arg_8]; unsigned int *
0x18001f3a1  lea     rdx, aBenumeratehwbe; "bEnumerateHWBeforeSW"
0x18001f3a8  lea     rcx, [rbp+var_30]; this
0x18001f3ac  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18001f3b1  test    eax, eax
0x18001f3b3  jle     short loc_18001F3BC
0x18001f3b5  movzx   eax, ax
0x18001f3b8  or      eax, ebx
0x18001f3ba  test    eax, eax
0x18001f3bc  jns     short loc_18001F434
0x18001f3be  mov     r9d, edi; unsigned int
0x18001f3c1  lea     r8, aSystemCurrentc_8; "System\\CurrentControlSet\\Control\\Ter"...
0x18001f3c8  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x18001f3cf  lea     rcx, [rbp+var_30]; this
0x18001f3d3  call    ?OpenKey@CRegistry@@QEAAKPEAUHKEY__@@PEBGK1@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong,ushort const *)
0x18001f3d8  test    eax, eax
0x18001f3da  jle     short loc_18001F3E3
0x18001f3dc  movzx   eax, ax
0x18001f3df  or      eax, ebx
0x18001f3e1  test    eax, eax
0x18001f3e3  jns     short loc_18001F405
0x18001f3e5  lea     rdx, aOpenkeyFailed0; "OpenKey failed: 0x%x in %s"
0x18001f3ec  mov     r8d, eax
0x18001f3ef  lea     r9, aCgpumanagerEna; "CGpuManager::EnableDisableHWGpuInSessio"...
0x18001f3f6  mov     ecx, 8; int
0x18001f3fb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f400  jmp     loc_18001F498
0x18001f405  lea     r8, [rbp+arg_8]; unsigned int *
0x18001f409  lea     rdx, aFusehardwaregp; "fUseHardwareGPU"
0x18001f410  lea     rcx, [rbp+var_30]; this
0x18001f414  call    ?ReadRegDWord@CRegistry@@QEAAKPEBGPEAK@Z; CRegistry::ReadRegDWord(ushort const *,ulong *)
0x18001f419  cmp     eax, 2
0x18001f41c  jz      short loc_18001F434
0x18001f41e  test    eax, eax
0x18001f420  jle     short loc_18001F429
0x18001f422  movzx   eax, ax
0x18001f425  or      eax, ebx
0x18001f427  test    eax, eax
0x18001f429  jns     short loc_18001F434
0x18001f42b  lea     rdx, aReadregdwordFa; "ReadRegDWord failed: 0x%x in %s"
0x18001f432  jmp     short loc_18001F3EC
0x18001f434  lea     rbx, [rsi+648h]
0x18001f43b  mov     [rbp+arg_10], rbx
0x18001f43f  mov     rcx, rbx; this
0x18001f442  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001f447  nop
0x18001f448  mov     edi, [rbp+arg_8]
0x18001f44b  cmp     dword ptr [rsi+640h], 0
0x18001f452  jnz     short loc_18001F482
0x18001f454  cmp     edi, r15d
0x18001f457  jnz     short loc_18001F482
0x18001f459  mov     rcx, rsi; this
0x18001f45c  call    ?InitGpuList@CGpuManager@@AEAAJXZ; CGpuManager::InitGpuList(void)
0x18001f461  test    eax, eax
0x18001f463  jns     short loc_18001F482
0x18001f465  lea     r9, aCgpumanagerEna; "CGpuManager::EnableDisableHWGpuInSessio"...
0x18001f46c  mov     r8d, eax
0x18001f46f  lea     rdx, aInitgpulistFai; "InitGpuList failed: 0x%x in %s"
0x18001f476  mov     ecx, 8; int
0x18001f47b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001f480  jmp     short loc_18001F488
0x18001f482  mov     [rsi+640h], edi
0x18001f488  mov     rcx, rbx; _Mtx_t
0x18001f48b  call    cs:__imp__Mtx_unlock
0x18001f492  nop     dword ptr [rax+rax+00h]
0x18001f497  nop
0x18001f498  lea     rcx, [rbp+var_30]; this
0x18001f49c  call    ??1CRegistry@@UEAA@XZ; CRegistry::~CRegistry(void)
0x18001f4a1  lea     r11, [rsp+60h+var_s0]
0x18001f4a6  mov     rbx, [r11+20h]
0x18001f4aa  mov     rsi, [r11+38h]
0x18001f4ae  mov     rsp, r11
0x18001f4b1  pop     r15
0x18001f4b3  pop     rdi
0x18001f4b4  pop     rbp
0x18001f4b5  retn
```
