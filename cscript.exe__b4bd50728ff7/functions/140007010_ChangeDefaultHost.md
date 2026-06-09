# ChangeDefaultHost

- ea: `0x140007010`
- end: `0x1400071e3`
- name: `ChangeDefaultHost`
- size: `467`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003e2c`

## callees

- `0x140007010`
- `0x140007c74`
- `0x140009fb8`
- `0x1400161d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExA` at `0x140007121`
- `ADVAPI32!RegQueryValueExA` at `0x140007121`
- `ADVAPI32!RegOpenKeyExA` at `0x1400070e2`
- `ADVAPI32!RegOpenKeyExA` at `0x1400070e2`
- `ADVAPI32!RegEnumKeyExA` at `0x14000709f`
- `ADVAPI32!RegEnumKeyExA` at `0x14000709f`
- `ADVAPI32!RegCloseKey` at `0x14000712e`
- `ADVAPI32!RegCloseKey` at `0x14000712e`

## string_xrefs

- `0x140007053`: `Open2`

## pseudocode

```c
LSTATUS __fastcall ChangeDefaultHost(int a1)
{
  LSTATUS result; // eax
  DWORD i; // ebx
  bool v3; // cc
  LSTATUS v4; // edi
  __int64 v5; // rax
  int v6; // eax
  int v7; // ecx
  DWORD cchName; // [rsp+40h] [rbp-248h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-240h] BYREF
  CHAR Name[272]; // [rsp+50h] [rbp-238h] BYREF
  BYTE Data[272]; // [rsp+160h] [rbp-128h] BYREF

  phkResult = 0;
  if ( a1 != 87 && a1 != 67 )
    return -2147024809;
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    result = RegEnumKeyExA(HKEY_CLASSES_ROOT, i, Name, &cchName, 0, 0, 0, 0);
    if ( result == 259 )
      break;
    v3 = result <= 0;
    if ( result )
      goto LABEL_15;
    if ( Name[0] == 46 )
    {
      result = RegOpenKeyExA(HKEY_CLASSES_ROOT, Name, 0, 0x20019u, &phkResult);
      v3 = result <= 0;
      if ( result )
      {
LABEL_15:
        if ( !v3 )
          return (unsigned __int16)result | 0x80070000;
        return result;
      }
      cchName = 260;
      v4 = RegQueryValueExA(phkResult, byte_140019BD0, 0, 0, Data, &cchName);
      RegCloseKey(phkResult);
      if ( !v4 && cchName )
      {
        v5 = cchName - 1;
        if ( (unsigned int)v5 >= 0x104 )
          _report_rangecheckfailure();
        Name[v5] = 0;
        result = ChangeDefaultHostCore((LPCSTR)Data);
        if ( result < 0 )
          return result;
      }
    }
  }
  result = ChangeDefaultHostCore("WSFFile");
  if ( result >= 0 )
  {
    v6 = ChangeDefaultHostCore("WSHFile");
    v7 = 0;
    if ( v6 < 0 )
      return v6;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x140007010  mov     [rsp+arg_10], rbp
0x140007015  push    rsi
0x140007016  sub     rsp, 280h
0x14000701d  mov     rax, cs:__security_cookie
0x140007024  xor     rax, rsp
0x140007027  mov     [rsp+288h+var_18], rax
0x14000702f  xor     ebp, ebp
0x140007031  mov     [rsp+288h+phkResult], rbp
0x140007036  cmp     ecx, 57h ; 'W'
0x140007039  jz      short loc_14000704A
0x14000703b  cmp     ecx, 43h ; 'C'
0x14000703e  jz      short loc_140007053
0x140007040  mov     eax, 80070057h
0x140007045  jmp     loc_1400071C2
0x14000704a  lea     rsi, aOpen; "Open"
0x140007051  jmp     short loc_14000705A
0x140007053  lea     rsi, aOpen2; "Open2"
0x14000705a  mov     [rsp+288h+arg_0], rbx
0x140007062  mov     ebx, ebp
0x140007064  mov     [rsp+288h+arg_8], rdi
0x14000706c  nop     dword ptr [rax+00h]
0x140007070  mov     [rsp+288h+lpftLastWriteTime], rbp; lpftLastWriteTime
0x140007075  lea     r9, [rsp+288h+cchName]; lpcchName
0x14000707a  mov     [rsp+288h+lpcchClass], rbp; lpcchClass
0x14000707f  lea     r8, [rsp+288h+Name]; lpName
0x140007084  mov     [rsp+288h+lpClass], rbp; lpClass
0x140007089  mov     edx, ebx; dwIndex
0x14000708b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140007092  mov     [rsp+288h+lpReserved], rbp; lpReserved
0x140007097  mov     [rsp+288h+cchName], 104h
0x14000709f  call    cs:__imp_RegEnumKeyExA
0x1400070a5  cmp     eax, 103h
0x1400070aa  jz      loc_140007181
0x1400070b0  test    eax, eax
0x1400070b2  jnz     loc_140007175
0x1400070b8  cmp     [rsp+288h+Name], 2Eh ; '.'
0x1400070bd  jnz     loc_140007168
0x1400070c3  lea     rax, [rsp+288h+phkResult]
0x1400070c8  mov     r9d, 20019h; samDesired
0x1400070ce  xor     r8d, r8d; ulOptions
0x1400070d1  mov     [rsp+288h+lpReserved], rax; phkResult
0x1400070d6  lea     rdx, [rsp+288h+Name]; lpSubKey
0x1400070db  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1400070e2  call    cs:__imp_RegOpenKeyExA
0x1400070e8  test    eax, eax
0x1400070ea  jnz     loc_140007175
0x1400070f0  mov     rcx, [rsp+288h+phkResult]; hKey
0x1400070f5  lea     rax, [rsp+288h+cchName]
0x1400070fa  mov     [rsp+288h+lpClass], rax; lpcbData
0x1400070ff  lea     rdx, byte_140019BD0; lpValueName
0x140007106  lea     rax, [rsp+288h+Data]
0x14000710e  mov     [rsp+288h+cchName], 104h
0x140007116  xor     r9d, r9d; lpType
0x140007119  mov     [rsp+288h+lpReserved], rax; lpData
0x14000711e  xor     r8d, r8d; lpReserved
0x140007121  call    cs:__imp_RegQueryValueExA
0x140007127  mov     rcx, [rsp+288h+phkResult]; hKey
0x14000712c  mov     edi, eax
0x14000712e  call    cs:__imp_RegCloseKey
0x140007134  test    edi, edi
0x140007136  jnz     short loc_140007168
0x140007138  mov     eax, [rsp+288h+cchName]
0x14000713c  test    eax, eax
0x14000713e  jz      short loc_140007168
0x140007140  dec     eax
0x140007142  cmp     eax, 104h
0x140007147  jnb     short loc_14000716F
0x140007149  mov     r8d, 1
0x14000714f  mov     [rsp+rax+288h+Name], bpl
0x140007154  mov     rdx, rsi
0x140007157  lea     rcx, [rsp+288h+Data]; lpSubKey
0x14000715f  call    ChangeDefaultHostCore
0x140007164  test    eax, eax
0x140007166  js      short loc_1400071B2
0x140007168  inc     ebx
0x14000716a  jmp     loc_140007070
0x14000716f  call    __report_rangecheckfailure
0x140007175  jle     short loc_1400071B2
0x140007177  movzx   eax, ax
0x14000717a  or      eax, 80070000h
0x14000717f  jmp     short loc_1400071B2
0x140007181  xor     r8d, r8d
0x140007184  lea     rcx, aWsffile; "WSFFile"
0x14000718b  mov     rdx, rsi
0x14000718e  call    ChangeDefaultHostCore
0x140007193  test    eax, eax
0x140007195  js      short loc_1400071B2
0x140007197  xor     r8d, r8d
0x14000719a  lea     rcx, aWshfile; "WSHFile"
0x1400071a1  mov     rdx, rsi
0x1400071a4  call    ChangeDefaultHostCore
0x1400071a9  test    eax, eax
0x1400071ab  mov     ecx, ebp
0x1400071ad  cmovs   ecx, eax
0x1400071b0  mov     eax, ecx
0x1400071b2  mov     rdi, [rsp+288h+arg_8]
0x1400071ba  mov     rbx, [rsp+288h+arg_0]
0x1400071c2  mov     rcx, [rsp+288h+var_18]
0x1400071ca  xor     rcx, rsp; StackCookie
0x1400071cd  call    __security_check_cookie
0x1400071d2  mov     rbp, [rsp+288h+arg_10]
0x1400071da  add     rsp, 280h
0x1400071e1  pop     rsi
0x1400071e2  retn
```
