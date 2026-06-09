# SetFalconServiceName(wchar_t const *)

- ea: `0x18000e1a0`
- end: `0x18000e23e`
- name: `?SetFalconServiceName@@YAXPEB_W@Z`
- size: `158`
- prototype: `void __fastcall(const wchar_t *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180003df0`
- `0x18000b95c`
- `0x18000ce4c`
- `0x18000e090`
- `0x18000e1a0`
- `0x18000ee9c`
- `0x180017cb8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000e1f1`
- `ADVAPI32!RegCloseKey` at `0x18000e1f1`
- `KERNEL32!LeaveCriticalSection` at `0x18000e227`
- `KERNEL32!LeaveCriticalSection` at `0x18000e227`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SetFalconServiceName(wchar_t *a1)
{
  int *v2; // [rsp+38h] [rbp+10h] BYREF
  _RTL_CRITICAL_SECTION *v3; // [rsp+40h] [rbp+18h]

  v2 = dword_1800425B8;
  CReadWriteLock::LockWrite((CReadWriteLock *)dword_1800425B8);
  StringCchCopyW((wchar_t *)L"MSMQ", 0x12Cu, a1);
  std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(
    &unk_180042590,
    &Class,
    0);
  if ( g_hKeyFalcon )
    RegCloseKey(g_hKeyFalcon);
  g_hKeyFalcon = 0;
  v3 = &stru_180042568;
  CCriticalSection::Lock((CCriticalSection *)&stru_180042568);
  CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::RemoveAll(&off_180041020);
  LeaveCriticalSection(&stru_180042568);
  CSW::~CSW((CSW *)&v2);
}

```

## disassembly

```asm
0x18000e1a0  push    rbx
0x18000e1a2  sub     rsp, 20h
0x18000e1a6  mov     rbx, rcx
0x18000e1a9  lea     rcx, dword_1800425B8; this
0x18000e1b0  mov     [rsp+28h+arg_8], rcx
0x18000e1b5  call    ?LockWrite@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockWrite(void)
0x18000e1ba  nop
0x18000e1bb  mov     r8, rbx; wchar_t *
0x18000e1be  mov     edx, 12Ch; unsigned __int64
0x18000e1c3  lea     rcx, aMsmq; "MSMQ"
0x18000e1ca  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000e1cf  xor     r8d, r8d
0x18000e1d2  lea     rdx, Class
0x18000e1d9  lea     rcx, unk_180042590
0x18000e1e0  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W_K@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::assign(wchar_t const *,unsigned __int64)
0x18000e1e5  mov     rcx, cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A; hKey
0x18000e1ec  test    rcx, rcx
0x18000e1ef  jz      short loc_18000E1F7
0x18000e1f1  call    cs:__imp_RegCloseKey
0x18000e1f7  mov     cs:?g_hKeyFalcon@@3VCAutoCloseRegHandle@@A, 0; CAutoCloseRegHandle g_hKeyFalcon
0x18000e202  lea     rbx, stru_180042568
0x18000e209  mov     [rsp+28h+arg_10], rbx
0x18000e20e  mov     rcx, rbx; this
0x18000e211  call    ?Lock@CCriticalSection@@AEAAXXZ; CCriticalSection::Lock(void)
0x18000e216  nop
0x18000e217  lea     rcx, off_180041020
0x18000e21e  call    ?RemoveAll@?$CMap@PEB_WPEB_WPEAUHKEY__@@AEAPEAU1@@@QEAAXXZ; CMap<wchar_t const *,wchar_t const *,HKEY__ *,HKEY__ * &>::RemoveAll(void)
0x18000e223  nop
0x18000e224  mov     rcx, rbx; lpCriticalSection
0x18000e227  call    cs:__imp_LeaveCriticalSection
0x18000e22d  nop
0x18000e22e  lea     rcx, [rsp+28h+arg_8]; this
0x18000e233  call    ??1CSW@@QEAA@XZ; CSW::~CSW(void)
0x18000e238  add     rsp, 20h
0x18000e23c  pop     rbx
0x18000e23d  retn
```
