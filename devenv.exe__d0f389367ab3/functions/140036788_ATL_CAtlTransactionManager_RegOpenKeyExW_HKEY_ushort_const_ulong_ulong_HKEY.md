# ATL::CAtlTransactionManager::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x140036788`
- end: `0x14003683f`
- name: `?RegOpenKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKKPEAPEAU3@@Z`
- size: `183`
- prototype: `int(ATL::CAtlTransactionManager *__hidden this, HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a060`
- `0x140011b10`
- `0x140035738`

## callees

- `0x140036788`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14003681d`
- `ADVAPI32!RegOpenKeyExW` at `0x14003681d`
- `KERNEL32!GetModuleHandleW` at `0x1400367b5`
- `KERNEL32!GetModuleHandleW` at `0x1400367b5`
- `KERNEL32!GetProcAddress` at `0x1400367ca`
- `KERNEL32!GetProcAddress` at `0x1400367ca`

## string_xrefs

- `0x1400367ae`: `Advapi32.dll`
- `0x1400367c0`: `RegOpenKeyTransactedW`

## pseudocode

```c
LSTATUS __fastcall ATL::CAtlTransactionManager::RegOpenKeyExW(
        ATL::CAtlTransactionManager *this,
        HKEY a2,
        const unsigned __int16 *a3,
        DWORD a4,
        REGSAM samDesired,
        HKEY *phkResult)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax

  if ( *(_QWORD *)this )
  {
    ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
    if ( ModuleHandleW )
    {
      ProcAddress = GetProcAddress(ModuleHandleW, "RegOpenKeyTransactedW");
      if ( ProcAddress )
        return ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD, HKEY *, _QWORD, _QWORD))ProcAddress)(
                 a2,
                 a3,
                 a4,
                 samDesired,
                 phkResult,
                 *(_QWORD *)this,
                 0);
    }
  }
  else if ( *((_DWORD *)this + 2) )
  {
    return RegOpenKeyExW(a2, a3, a4, samDesired, phkResult);
  }
  return 1;
}

```

## disassembly

```asm
0x140036788  mov     [rsp+arg_0], rbx
0x14003678d  mov     [rsp+arg_8], rbp
0x140036792  mov     [rsp+arg_10], rsi
0x140036797  push    rdi
0x140036798  sub     rsp, 40h
0x14003679c  cmp     qword ptr [rcx], 0
0x1400367a0  mov     edi, r9d
0x1400367a3  mov     rsi, r8
0x1400367a6  mov     rbp, rdx
0x1400367a9  mov     rbx, rcx
0x1400367ac  jz      short loc_1400367FF
0x1400367ae  lea     rcx, aAdvapi32Dll_1
0x1400367b5  call    cs:__imp_GetModuleHandleW
0x1400367bb  test    rax, rax
0x1400367be  jz      short loc_140036825
0x1400367c0  lea     rdx, aRegopenkeytran
0x1400367c7  mov     rcx, rax; hModule
0x1400367ca  call    cs:__imp_GetProcAddress
0x1400367d0  test    rax, rax
0x1400367d3  jz      short loc_140036825
0x1400367d5  mov     rcx, [rbx]
0x1400367d8  mov     r8d, edi
0x1400367db  and     [rsp+48h+var_18], 0
0x1400367e1  mov     rdx, rsi
0x1400367e4  mov     r9d, [rsp+48h+samDesired]
0x1400367e9  mov     [rsp+48h+var_20], rcx
0x1400367ee  mov     rcx, [rsp+48h+arg_28]
0x1400367f3  mov     [rsp+48h+phkResult], rcx
0x1400367f8  mov     rcx, rbp
0x1400367fb  call    rax
0x1400367fd  jmp     short loc_14003682A
0x1400367ff  cmp     dword ptr [rcx+8], 0
0x140036803  jz      short loc_140036825
0x140036805  mov     rax, [rsp+48h+arg_28]
0x14003680a  mov     r8d, edi; ulOptions
0x14003680d  mov     r9d, [rsp+48h+samDesired]; samDesired
0x140036812  mov     rdx, rsi; lpSubKey
0x140036815  mov     rcx, rbp; hKey
0x140036818  mov     [rsp+48h+phkResult], rax; phkResult
0x14003681d  call    cs:__imp_RegOpenKeyExW
0x140036823  jmp     short loc_14003682A
0x140036825  mov     eax, 1
0x14003682a  mov     rbx, [rsp+48h+arg_0]
0x14003682f  mov     rbp, [rsp+48h+arg_8]
0x140036834  mov     rsi, [rsp+48h+arg_10]
0x140036839  add     rsp, 40h
0x14003683d  pop     rdi
0x14003683e  retn
```
