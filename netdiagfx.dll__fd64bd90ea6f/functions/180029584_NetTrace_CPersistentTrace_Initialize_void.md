# NetTrace::CPersistentTrace::Initialize(void)

- ea: `0x180029584`
- end: `0x18002964b`
- name: `?Initialize@CPersistentTrace@NetTrace@@QEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(NetTrace::CPersistentTrace *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180029ea0`

## callees

- `0x180021094`
- `0x180029584`
- `0x18002c802`
- `0x18002c840`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800295f3`
- `ntdll!RtlNtStatusToDosError` at `0x1800295f3`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800295eb`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800295eb`

## string_xrefs

- `0x1800295e4`: `ETWAutoLoggerPath`

## pseudocode

```c
int __fastcall NetTrace::CPersistentTrace::Initialize(HKEY *this)
{
  int result; // eax
  NTSTATUS PersistedStateLocation; // eax
  bool v4; // zf
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  if ( !*(_DWORD *)this )
    return 0;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"ETWAutoLoggerPath",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger",
                             0,
                             SubKey,
                             520,
                             0);
  result = RtlNtStatusToDosError(PersistedStateLocation);
  v4 = result == 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v4 = result == 0;
  }
  if ( v4 )
  {
    result = ATL::CRegKey::Open(this + 1, HKEY_LOCAL_MACHINE, SubKey, 0x20019u);
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
  }
  *(_DWORD *)this = result;
  return result;
}

```

## disassembly

```asm
0x180029584  push    rbx
0x180029586  sub     rsp, 260h
0x18002958d  mov     rax, cs:__security_cookie
0x180029594  xor     rax, rsp
0x180029597  mov     [rsp+268h+var_18], rax
0x18002959f  mov     rbx, rcx
0x1800295a2  xor     edx, edx; Val
0x1800295a4  lea     rcx, [rsp+268h+SubKey]; void *
0x1800295a9  mov     r8d, 208h; Size
0x1800295af  call    memset_0
0x1800295b4  cmp     dword ptr [rbx], 0
0x1800295b7  jnz     short loc_1800295BD
0x1800295b9  xor     eax, eax
0x1800295bb  jmp     short loc_180029632
0x1800295bd  mov     [rsp+268h+var_238], 0
0x1800295c6  lea     rax, [rsp+268h+SubKey]
0x1800295cb  mov     [rsp+268h+var_240], 208h
0x1800295d3  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x1800295da  xor     r9d, r9d
0x1800295dd  mov     [rsp+268h+var_248], rax
0x1800295e2  xor     edx, edx
0x1800295e4  lea     rcx, aEtwautologgerp; "ETWAutoLoggerPath"
0x1800295eb  call    cs:__imp_RtlGetPersistedStateLocation
0x1800295f1  mov     ecx, eax; Status
0x1800295f3  call    cs:__imp_RtlNtStatusToDosError
0x1800295f9  test    eax, eax
0x1800295fb  jle     short loc_180029607
0x1800295fd  movzx   eax, ax
0x180029600  or      eax, 80070000h
0x180029605  test    eax, eax
0x180029607  jnz     short loc_180029630
0x180029609  lea     rcx, [rbx+8]; this
0x18002960d  mov     r9d, 20019h; unsigned int
0x180029613  lea     r8, [rsp+268h+SubKey]; lpSubKey
0x180029618  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002961f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180029624  test    eax, eax
0x180029626  jle     short loc_180029630
0x180029628  movzx   eax, ax
0x18002962b  or      eax, 80070000h
0x180029630  mov     [rbx], eax
0x180029632  mov     rcx, [rsp+268h+var_18]
0x18002963a  xor     rcx, rsp; StackCookie
0x18002963d  call    __security_check_cookie
0x180029642  add     rsp, 260h
0x180029649  pop     rbx
0x18002964a  retn
```
