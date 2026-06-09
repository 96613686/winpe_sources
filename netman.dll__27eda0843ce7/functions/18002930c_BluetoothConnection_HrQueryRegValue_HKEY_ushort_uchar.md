# BluetoothConnection::HrQueryRegValue(HKEY__ *,ushort *,uchar * *)

- ea: `0x18002930c`
- end: `0x18002941b`
- name: `?HrQueryRegValue@BluetoothConnection@@AEAAJPEAUHKEY__@@PEAGPEAPEAE@Z`
- size: `271`
- prototype: `int(BluetoothConnection *__hidden this, HKEY, unsigned __int16 *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028250`
- `0x180029424`

## callees

- `0x180001710`
- `0x18000538c`
- `0x18002930c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x180029356`
- `ADVAPI32!RegQueryValueExW` at `0x180029399`
- `ADVAPI32!RegQueryValueExW` at `0x180029356`
- `ADVAPI32!RegQueryValueExW` at `0x180029399`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002936b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002936b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800293a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800293a8`

## pseudocode

```c
__int64 __fastcall BluetoothConnection::HrQueryRegValue(
        BluetoothConnection *this,
        HKEY a2,
        unsigned __int16 *a3,
        LPVOID *a4)
{
  LSTATUS Value; // eax
  LSTATUS v8; // ebx
  unsigned __int8 *lpData; // rax
  __int64 v10; // r9
  SIZE_T cb; // [rsp+30h] [rbp-28h] BYREF

  LODWORD(cb) = 0;
  Value = RegQueryValueExW(a2, a3, 0, 0, 0, (LPDWORD)&cb);
  v8 = Value;
  if ( a4 && !Value )
  {
    lpData = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
    *a4 = lpData;
    if ( lpData )
    {
      v8 = RegQueryValueExW(a2, a3, 0, 0, lpData, (LPDWORD)&cb);
      if ( v8 )
      {
        CoTaskMemFree(*a4);
        *a4 = 0;
      }
    }
    else
    {
      v8 = 8;
    }
  }
  v10 = (unsigned int)v8;
  if ( v8 > 0 )
    v10 = (unsigned __int16)v8 | 0x80070000;
  if ( (int)v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids, v10);
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002930c  mov     r11, rsp
0x18002930f  mov     [r11+8], rbx
0x180029313  push    rbp
0x180029314  push    rsi
0x180029315  push    rdi
0x180029316  sub     rsp, 40h
0x18002931a  mov     rax, cs:__security_cookie
0x180029321  xor     rax, rsp
0x180029324  mov     [rsp+58h+var_20], rax
0x180029329  mov     rbp, r8
0x18002932c  mov     dword ptr [rsp+58h+cb], 0
0x180029334  mov     rsi, rdx
0x180029337  lea     rax, [r11-28h]
0x18002933b  mov     rdi, r9
0x18002933e  mov     [r11-30h], rax
0x180029342  mov     rdx, rbp; lpValueName
0x180029345  mov     qword ptr [r11-38h], 0
0x18002934d  mov     rcx, rsi; hKey
0x180029350  xor     r9d, r9d; lpType
0x180029353  xor     r8d, r8d; lpReserved
0x180029356  call    cs:__imp_RegQueryValueExW
0x18002935c  mov     ebx, eax
0x18002935e  test    rdi, rdi
0x180029361  jz      short loc_1800293B5
0x180029363  test    eax, eax
0x180029365  jnz     short loc_1800293B5
0x180029367  mov     ecx, dword ptr [rsp+58h+cb]; cb
0x18002936b  call    cs:__imp_CoTaskMemAlloc
0x180029371  mov     [rdi], rax
0x180029374  test    rax, rax
0x180029377  jnz     short loc_18002937E
0x180029379  lea     ebx, [rax+8]
0x18002937c  jmp     short loc_1800293B5
0x18002937e  lea     rcx, [rsp+58h+cb]
0x180029383  xor     r9d, r9d; lpType
0x180029386  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18002938b  xor     r8d, r8d; lpReserved
0x18002938e  mov     rcx, rsi; hKey
0x180029391  mov     [rsp+58h+lpData], rax; lpData
0x180029396  mov     rdx, rbp; lpValueName
0x180029399  call    cs:__imp_RegQueryValueExW
0x18002939f  mov     ebx, eax
0x1800293a1  test    eax, eax
0x1800293a3  jz      short loc_1800293B5
0x1800293a5  mov     rcx, [rdi]; pv
0x1800293a8  call    cs:__imp_CoTaskMemFree
0x1800293ae  mov     qword ptr [rdi], 0
0x1800293b5  movzx   edi, bx
0x1800293b8  mov     r9d, ebx
0x1800293bb  or      edi, 80070000h
0x1800293c1  test    ebx, ebx
0x1800293c3  cmovg   r9d, edi
0x1800293c7  test    r9d, r9d
0x1800293ca  jns     short loc_1800293FA
0x1800293cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800293d3  lea     rax, WPP_GLOBAL_Control
0x1800293da  cmp     rcx, rax
0x1800293dd  jz      short loc_1800293FA
0x1800293df  test    byte ptr [rcx+1Ch], 1
0x1800293e3  jz      short loc_1800293FA
0x1800293e5  mov     rcx, [rcx+10h]
0x1800293e9  lea     r8, WPP_1e61fdb25b22367b1398e324dc81d9b9_Traceguids
0x1800293f0  mov     edx, 0Bh
0x1800293f5  call    WPP_SF_d
0x1800293fa  test    ebx, ebx
0x1800293fc  cmovg   ebx, edi
0x1800293ff  mov     eax, ebx
0x180029401  mov     rcx, [rsp+58h+var_20]
0x180029406  xor     rcx, rsp; StackCookie
0x180029409  call    __security_check_cookie
0x18002940e  mov     rbx, [rsp+58h+arg_0]
0x180029413  add     rsp, 40h
0x180029417  pop     rdi
0x180029418  pop     rsi
0x180029419  pop     rbp
0x18002941a  retn
```
