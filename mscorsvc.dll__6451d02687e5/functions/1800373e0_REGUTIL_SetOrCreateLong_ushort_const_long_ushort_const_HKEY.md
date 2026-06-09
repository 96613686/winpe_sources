# REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)

- ea: `0x1800373e0`
- end: `0x18003746f`
- name: `?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName, int, const unsigned __int16 *, HKEY)`
- caller_count: `7`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800035bc`
- `0x1800039ac`
- `0x180003a54`
- `0x180003c90`
- `0x180004cac`
- `0x180016920`
- `0x18001b57c`

## callees

- `0x1800373e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180037461`
- `ADVAPI32!RegCloseKey` at `0x180037461`
- `ADVAPI32!RegSetValueExW` at `0x180037454`
- `ADVAPI32!RegSetValueExW` at `0x180037454`
- `ADVAPI32!RegCreateKeyExW` at `0x180037425`
- `ADVAPI32!RegCreateKeyExW` at `0x180037425`

## pseudocode

```c
__int64 __fastcall REGUTIL::SetOrCreateLong(LPCWSTR lpValueName, int a2, unsigned __int16 *a3, HKEY a4)
{
  unsigned int v6; // ebx
  int Data; // [rsp+68h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = (HKEY)a3;
  Data = a2;
  if ( RegCreateKeyExW(a4, &psz, 0, 0, 0, 0x20006u, 0, &hKey, 0) )
    return 0xFFFFFFFFLL;
  v6 = RegSetValueExW(hKey, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
  RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800373e0  mov     r11, rsp
0x1800373e3  mov     [r11+18h], r8
0x1800373e7  mov     [rsp+Data], edx
0x1800373eb  push    rbx
0x1800373ec  sub     rsp, 50h
0x1800373f0  and     qword ptr [r11-18h], 0
0x1800373f5  lea     rdx, psz; lpSubKey
0x1800373fc  mov     rbx, rcx
0x1800373ff  mov     rax, r9
0x180037402  lea     rcx, [r11+18h]
0x180037406  xor     r9d, r9d; lpClass
0x180037409  mov     [r11-20h], rcx
0x18003740d  xor     r8d, r8d; Reserved
0x180037410  and     qword ptr [r11-28h], 0
0x180037415  mov     rcx, rax; hKey
0x180037418  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180037420  and     dword ptr [rsp+58h+lpData], 0
0x180037425  call    cs:__imp_RegCreateKeyExW
0x18003742b  test    eax, eax
0x18003742d  jz      short loc_180037434
0x18003742f  or      eax, 0FFFFFFFFh
0x180037432  jmp     short loc_180037469
0x180037434  mov     rcx, [rsp+58h+hKey]; hKey
0x180037439  lea     rax, [rsp+58h+Data]
0x18003743e  mov     r9d, 4; dwType
0x180037444  xor     r8d, r8d; Reserved
0x180037447  mov     [rsp+58h+samDesired], r9d; cbData
0x18003744c  mov     rdx, rbx; lpValueName
0x18003744f  mov     [rsp+58h+lpData], rax; lpData
0x180037454  call    cs:__imp_RegSetValueExW
0x18003745a  mov     rcx, [rsp+58h+hKey]; hKey
0x18003745f  mov     ebx, eax
0x180037461  call    cs:__imp_RegCloseKey
0x180037467  mov     eax, ebx
0x180037469  add     rsp, 50h
0x18003746d  pop     rbx
0x18003746e  retn
```
