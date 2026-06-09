# ReadRegDWORD(ushort *,ushort *,ulong *)

- ea: `0x180078538`
- end: `0x180078609`
- name: `?ReadRegDWORD@@YAJPEAG0PEAK@Z`
- size: `209`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180023de4`
- `0x180023e94`

## callees

- `0x180078538`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800785c4`
- `ADVAPI32!RegQueryValueExW` at `0x1800785c4`
- `ADVAPI32!RegOpenKeyExW` at `0x18007857f`
- `ADVAPI32!RegOpenKeyExW` at `0x18007857f`
- `ADVAPI32!RegCloseKey` at `0x1800785ef`
- `ADVAPI32!RegCloseKey` at `0x1800785ef`

## string_xrefs

- `0x180078571`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`

## pseudocode

```c
__int64 __fastcall ReadRegDWORD(unsigned __int16 *a1, unsigned __int16 *a2, unsigned int *a3)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  LSTATUS v6; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  unsigned int Data; // [rsp+48h] [rbp+10h] BYREF
  int v11; // [rsp+4Ch] [rbp+14h]
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v11 = HIDWORD(a2);
  v9 = HIDWORD(a1);
  hKey = 0;
  Data = 0;
  cbData = 4;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
         0,
         0x20019u,
         &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v6 = RegQueryValueExW(hKey, L"ReturnLicInterval", 0, 0, (LPBYTE)&Data, &cbData);
    v5 = v6;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
  }
  *a3 = Data;
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180078538  mov     rax, rsp
0x18007853b  mov     [rax+20h], rbx
0x18007853f  mov     [rax+10h], rdx
0x180078543  mov     [rax+8], rcx
0x180078547  push    rdi
0x180078548  sub     rsp, 30h
0x18007854c  and     qword ptr [rax+18h], 0
0x180078551  mov     rdi, r8
0x180078554  and     dword ptr [rax+10h], 0
0x180078558  mov     r9d, 20019h; samDesired
0x18007855e  mov     dword ptr [rax+8], 4
0x180078565  lea     rax, [rax+18h]
0x180078569  xor     r8d, r8d; ulOptions
0x18007856c  mov     [rsp+38h+phkResult], rax; phkResult
0x180078571  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180078578  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007857f  call    cs:__imp_RegOpenKeyExW
0x180078586  nop     dword ptr [rax+rax+00h]
0x18007858b  mov     ebx, eax
0x18007858d  test    eax, eax
0x18007858f  jle     short loc_18007859A
0x180078591  movzx   ebx, ax
0x180078594  or      ebx, 80070000h
0x18007859a  test    ebx, ebx
0x18007859c  js      short loc_1800785DF
0x18007859e  mov     rcx, [rsp+38h+hKey]; hKey
0x1800785a3  lea     rax, [rsp+38h+cbData]
0x1800785a8  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800785ad  lea     rdx, aReturnlicinter; "ReturnLicInterval"
0x1800785b4  lea     rax, [rsp+38h+Data]
0x1800785b9  xor     r9d, r9d; lpType
0x1800785bc  xor     r8d, r8d; lpReserved
0x1800785bf  mov     [rsp+38h+phkResult], rax; lpData
0x1800785c4  call    cs:__imp_RegQueryValueExW
0x1800785cb  nop     dword ptr [rax+rax+00h]
0x1800785d0  mov     ebx, eax
0x1800785d2  test    eax, eax
0x1800785d4  jle     short loc_1800785DF
0x1800785d6  movzx   ebx, ax
0x1800785d9  or      ebx, 80070000h
0x1800785df  mov     ecx, [rsp+38h+Data]
0x1800785e3  mov     [rdi], ecx
0x1800785e5  mov     rcx, [rsp+38h+hKey]; hKey
0x1800785ea  test    rcx, rcx
0x1800785ed  jz      short loc_1800785FB
0x1800785ef  call    cs:__imp_RegCloseKey
0x1800785f6  nop     dword ptr [rax+rax+00h]
0x1800785fb  mov     eax, ebx
0x1800785fd  mov     rbx, [rsp+38h+arg_18]
0x180078602  add     rsp, 30h
0x180078606  pop     rdi
0x180078607  retn
```
