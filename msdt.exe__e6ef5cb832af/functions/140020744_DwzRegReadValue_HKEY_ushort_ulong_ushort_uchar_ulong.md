# DwzRegReadValue(HKEY__ *,ushort *,ulong *,ushort *,uchar * *,ulong *)

- ea: `0x140020744`
- end: `0x14002084b`
- name: `?DwzRegReadValue@@YAJPEAUHKEY__@@PEAGPEAK1PEAPEAE2@Z`
- size: `263`
- prototype: `int(HKEY, unsigned __int16 *, unsigned int *, unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14002029c`
- `0x1400352a8`
- `0x140038e30`

## callees

- `0x140020420`
- `0x140020744`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140020777`
- `ADVAPI32!RegOpenKeyExW` at `0x140020777`
- `ADVAPI32!RegQueryValueExW` at `0x1400207f0`
- `ADVAPI32!RegQueryValueExW` at `0x1400207f0`
- `ADVAPI32!RegCloseKey` at `0x140020833`
- `ADVAPI32!RegCloseKey` at `0x140020833`

## string_xrefs

- `0x140020793`: `DwzRegReadValue`

## pseudocode

```c
__int64 __fastcall DwzRegReadValue(
        HKEY a1,
        unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int16 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  LSTATUS v8; // eax
  signed int v9; // ebx
  LSTATUS v10; // eax
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF

  hKey = 0;
  cbData = 0;
  v8 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( !hKey )
      return 1;
    cbData = *a6;
    v10 = RegQueryValueExW(hKey, a4, 0, a3, *a5, &cbData);
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( v9 >= 0 )
    {
      if ( *a3 != 4 )
        *a6 = cbData;
    }
    else
    {
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzRegReadValue", 253, v9);
    }
  }
  else
  {
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "DwzRegReadValue", 233, v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140020744  push    rbx
0x140020746  push    rbp
0x140020747  push    rsi
0x140020748  push    rdi
0x140020749  sub     rsp, 48h
0x14002074d  mov     rbp, r9
0x140020750  mov     [rsp+68h+hKey], 0
0x140020759  mov     rsi, r8
0x14002075c  mov     [rsp+68h+cbData], 0
0x140020764  lea     rax, [rsp+68h+hKey]
0x140020769  mov     r9d, 20019h; samDesired
0x14002076f  xor     r8d, r8d; ulOptions
0x140020772  mov     [rsp+68h+phkResult], rax; phkResult
0x140020777  call    cs:__imp_RegOpenKeyExW
0x14002077e  nop     dword ptr [rax+rax+00h]
0x140020783  mov     ebx, eax
0x140020785  test    eax, eax
0x140020787  jns     short loc_1400207AD
0x140020789  mov     dword ptr [rsp+68h+phkResult], eax
0x14002078d  mov     r9d, 0E9h
0x140020793  lea     r8, aDwzregreadvalu; "DwzRegReadValue"
0x14002079a  mov     ecx, 1; Level
0x14002079f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x1400207a6  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x1400207ab  jmp     short loc_140020829
0x1400207ad  mov     rcx, [rsp+68h+hKey]; hKey
0x1400207b2  test    rcx, rcx
0x1400207b5  jnz     short loc_1400207BF
0x1400207b7  lea     ebx, [rcx+1]
0x1400207ba  jmp     loc_14002083F
0x1400207bf  mov     rdi, [rsp+68h+arg_28]
0x1400207c7  mov     r9, rsi; lpType
0x1400207ca  xor     r8d, r8d; lpReserved
0x1400207cd  mov     eax, [rdi]
0x1400207cf  mov     [rsp+68h+cbData], eax
0x1400207d3  lea     rax, [rsp+68h+cbData]
0x1400207d8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1400207dd  mov     rax, [rsp+68h+arg_20]
0x1400207e5  mov     rdx, [rax]
0x1400207e8  mov     [rsp+68h+phkResult], rdx; lpData
0x1400207ed  mov     rdx, rbp; lpValueName
0x1400207f0  call    cs:__imp_RegQueryValueExW
0x1400207f7  nop     dword ptr [rax+rax+00h]
0x1400207fc  mov     ebx, eax
0x1400207fe  test    eax, eax
0x140020800  jle     short loc_14002080B
0x140020802  movzx   ebx, ax
0x140020805  or      ebx, 80070000h
0x14002080b  test    ebx, ebx
0x14002080d  jns     short loc_14002081E
0x14002080f  mov     dword ptr [rsp+68h+phkResult], ebx
0x140020813  mov     r9d, 0FDh
0x140020819  jmp     loc_140020793
0x14002081e  cmp     dword ptr [rsi], 4
0x140020821  jz      short loc_140020829
0x140020823  mov     eax, [rsp+68h+cbData]
0x140020827  mov     [rdi], eax
0x140020829  mov     rcx, [rsp+68h+hKey]; hKey
0x14002082e  test    rcx, rcx
0x140020831  jz      short loc_14002083F
0x140020833  call    cs:__imp_RegCloseKey
0x14002083a  nop     dword ptr [rax+rax+00h]
0x14002083f  mov     eax, ebx
0x140020841  add     rsp, 48h
0x140020845  pop     rdi
0x140020846  pop     rsi
0x140020847  pop     rbp
0x140020848  pop     rbx
0x140020849  retn
```
