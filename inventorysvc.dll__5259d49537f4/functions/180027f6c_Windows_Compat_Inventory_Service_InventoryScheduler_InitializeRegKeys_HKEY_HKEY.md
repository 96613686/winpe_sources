# Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys(HKEY__ * *,HKEY__ * *)

- ea: `0x180027f6c`
- end: `0x1800280f7`
- name: `?InitializeRegKeys@InventoryScheduler@Service@Inventory@Compat@Windows@@CAXPEAPEAUHKEY__@@0@Z`
- size: `395`
- prototype: `void __fastcall(PHKEY phkResult, PHKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ff40`

## callees

- `0x180002bf0`
- `0x180006e54`
- `0x18000fc68`
- `0x1800152d0`
- `0x180026430`
- `0x180027f6c`
- `0x18002d068`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027fd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028001`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180027fd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028001`

## string_xrefs

- `0x180028069`: `onecore\base\appcompat\inventory\service\scheduler\inventoryscheduler.cpp`
- `0x1800280a7`: `onecore\base\appcompat\inventory\service\scheduler\inventoryscheduler.cpp`
- `0x1800280e5`: `onecore\base\appcompat\inventory\service\scheduler\inventoryscheduler.cpp`
- `0x180028049`: `Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys`
- `0x18002808e`: `Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys`
- `0x1800280cc`: `Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys`
- `0x180027faa`: `CompatTelRunner`
- `0x180027fa3`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController`
- `0x180027ff7`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\TelemetryController`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys(PHKEY phkResult, PHKEY a2)
{
  int PersistedLocation; // eax
  unsigned int v5; // ebx
  LSTATUS v6; // eax
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  int phkResulta; // [rsp+20h] [rbp-238h]
  unsigned int phkResultb; // [rsp+20h] [rbp-238h]
  unsigned int phkResultc; // [rsp+20h] [rbp-238h]
  WCHAR SubKey[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                        SubKey,
                        (unsigned int)a2,
                        L"CompatTelRunner",
                        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController",
                        1);
  v5 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys",
      312,
      "failed [%#x]",
      PersistedLocation);
    v10 = wil::verify_hresult<long>(v5);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\scheduler\\inventoryscheduler.cpp",
      (const char *)v10,
      phkResulta);
  }
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, phkResult);
  v7 = v6;
  if ( v6 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys",
      313,
      "failed [%d]",
      v6);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\scheduler\\inventoryscheduler.cpp",
      (const char *)v7,
      phkResultb);
  }
  v8 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\TelemetryController",
         0,
         0x20019u,
         a2);
  v9 = v8;
  if ( v8 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::Service::InventoryScheduler::InitializeRegKeys",
      314,
      "failed [%d]",
      v8);
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x13A,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\service\\scheduler\\inventoryscheduler.cpp",
      (const char *)v9,
      phkResultc);
  }
}

```

## disassembly

```asm
0x180027f6c  mov     [rsp+arg_10], rbx
0x180027f71  mov     [rsp+arg_18], rsi
0x180027f76  push    rdi
0x180027f77  sub     rsp, 250h
0x180027f7e  mov     rax, cs:__security_cookie
0x180027f85  xor     rax, rsp
0x180027f88  mov     [rsp+258h+var_18], rax
0x180027f90  mov     rdi, rcx
0x180027f93  mov     [rsp+258h+phkResult], 1; int
0x180027f9b  lea     rcx, [rsp+258h+SubKey]; unsigned __int16 *
0x180027fa0  mov     rsi, rdx
0x180027fa3  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180027faa  lea     r8, aCompattelrunne_0; "CompatTelRunner"
0x180027fb1  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180027fb6  mov     ebx, eax
0x180027fb8  test    eax, eax
0x180027fba  js      short loc_180028036
0x180027fbc  mov     qword ptr [rsp+258h+phkResult], rdi; phkResult
0x180027fc1  lea     rdx, [rsp+258h+SubKey]; lpSubKey
0x180027fc6  mov     rdi, 0FFFFFFFF80000002h
0x180027fcd  mov     r9d, 0F003Fh; samDesired
0x180027fd3  mov     rcx, rdi; hKey
0x180027fd6  xor     r8d, r8d; ulOptions
0x180027fd9  call    cs:__imp_RegOpenKeyExW
0x180027fdf  mov     ebx, eax
0x180027fe1  test    eax, eax
0x180027fe3  jnz     loc_18002807B
0x180027fe9  mov     r9d, 20019h; samDesired
0x180027fef  mov     qword ptr [rsp+258h+phkResult], rsi; phkResult
0x180027ff4  xor     r8d, r8d; ulOptions
0x180027ff7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180027ffe  mov     rcx, rdi; hKey
0x180028001  call    cs:__imp_RegOpenKeyExW
0x180028007  mov     ebx, eax
0x180028009  test    eax, eax
0x18002800b  jnz     loc_1800280B9
0x180028011  mov     rcx, [rsp+258h+var_18]
0x180028019  xor     rcx, rsp; StackCookie
0x18002801c  call    __security_check_cookie
0x180028021  lea     r11, [rsp+258h+var_8]
0x180028029  mov     rbx, [r11+20h]
0x18002802d  mov     rsi, [r11+28h]
0x180028031  mov     rsp, r11
0x180028034  pop     rdi
0x180028035  retn
0x180028036  mov     edi, 138h
0x18002803b  mov     [rsp+258h+phkResult], ebx; int
0x18002803f  mov     r8d, edi
0x180028042  lea     r9, aFailedX; "failed [%#x]"
0x180028049  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::Service::In"...
0x180028050  mov     ecx, 1
0x180028055  call    AslLogCallPrintf
0x18002805a  mov     ecx, ebx
0x18002805c  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180028061  mov     rcx, [rsp+258h]; this
0x180028069  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\se"...
0x180028070  mov     r9d, eax; char *
0x180028073  mov     edx, edi; void *
0x180028075  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002807b  mov     edi, 139h
0x180028080  mov     [rsp+258h+phkResult], ebx; unsigned int
0x180028084  mov     r8d, edi
0x180028087  lea     r9, aFailedD; "failed [%d]"
0x18002808e  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::Service::In"...
0x180028095  mov     ecx, 1
0x18002809a  call    AslLogCallPrintf
0x18002809f  mov     rcx, [rsp+258h]; this
0x1800280a7  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\se"...
0x1800280ae  mov     r9d, ebx; char *
0x1800280b1  mov     edx, edi; void *
0x1800280b3  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800280b9  mov     edi, 13Ah
0x1800280be  mov     [rsp+258h+phkResult], ebx; unsigned int
0x1800280c2  mov     r8d, edi
0x1800280c5  lea     r9, aFailedD; "failed [%d]"
0x1800280cc  lea     rdx, aWindowsCompatI_25; "Windows::Compat::Inventory::Service::In"...
0x1800280d3  mov     ecx, 1
0x1800280d8  call    AslLogCallPrintf
0x1800280dd  mov     rcx, [rsp+258h]; this
0x1800280e5  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\se"...
0x1800280ec  mov     r9d, ebx; char *
0x1800280ef  mov     edx, edi; void *
0x1800280f1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
