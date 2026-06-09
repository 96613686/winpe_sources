# GetRegistryDwordDefault

- ea: `0x140070684`
- end: `0x140070753`
- name: `GetRegistryDwordDefault`
- size: `207`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400236a0`
- `0x1400247d0`
- `0x140039350`
- `0x140050adc`
- `0x14007a880`
- `0x14007aab0`
- `0x14007ad30`
- `0x14007b000`
- `0x14007c450`
- `0x14007d030`
- `0x14007d36c`
- `0x14007d650`
- `0x14007e1e8`

## callees

- `0x140070684`
- `0x140071ec8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1400706fd`
- `ADVAPI32!RegSetValueExW` at `0x1400706fd`
- `ADVAPI32!RegQueryValueExW` at `0x1400706d3`
- `ADVAPI32!RegQueryValueExW` at `0x1400706d3`
- `KERNEL32!SetLastError` at `0x140070738`
- `KERNEL32!SetLastError` at `0x140070738`

## string_xrefs

- `0x140070709`: `RegSetValueEx() failed[%s], ec=%d`

## pseudocode

```c
__int64 __fastcall GetRegistryDwordDefault(HKEY hKey, LPCWSTR lpValueName, BYTE *lpData, int a4)
{
  DWORD v8; // ecx
  unsigned int v9; // ebx
  DWORD cbData[10]; // [rsp+30h] [rbp-28h] BYREF
  DWORD Type; // [rsp+70h] [rbp+18h] BYREF

  cbData[0] = 4;
  Type = 0;
  if ( lpData )
  {
    v9 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, cbData);
    if ( v9 == 2 )
    {
      *(_DWORD *)lpData = a4;
      v9 = RegSetValueExW(hKey, lpValueName, 0, 4u, lpData, 4u);
      if ( v9 )
      {
        fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v9);
LABEL_10:
        v8 = v9;
        goto LABEL_11;
      }
    }
    else if ( v9 || Type != 4 )
    {
      fax_dprintf(L"RegQueryValueEx() failed[%s], ec=%d", lpValueName, v9);
      goto LABEL_10;
    }
    return 1;
  }
  v8 = 87;
LABEL_11:
  SetLastError(v8);
  return 0;
}

```

## disassembly

```asm
0x140070684  mov     rax, rsp
0x140070687  mov     [rax+8], rbx
0x14007068b  mov     [rax+10h], rbp
0x14007068f  push    rsi
0x140070690  push    rdi
0x140070691  push    r14
0x140070693  sub     rsp, 40h
0x140070697  mov     dword ptr [rax-28h], 4
0x14007069e  mov     r14d, r9d
0x1400706a1  mov     dword ptr [rax+18h], 0
0x1400706a8  mov     rsi, r8
0x1400706ab  mov     rdi, rdx
0x1400706ae  mov     rbp, rcx
0x1400706b1  test    r8, r8
0x1400706b4  jnz     short loc_1400706BC
0x1400706b6  lea     ecx, [r8+57h]; hKey
0x1400706ba  jmp     short loc_140070738
0x1400706bc  lea     rax, [rsp+58h+cbData]
0x1400706c1  xor     r8d, r8d; lpReserved
0x1400706c4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1400706c9  lea     r9, [rsp+58h+Type]; lpType
0x1400706ce  mov     [rsp+58h+lpData], rsi; lpData
0x1400706d3  call    cs:__imp_RegQueryValueExW
0x1400706d9  mov     ebx, eax
0x1400706db  cmp     eax, 2
0x1400706de  jnz     short loc_140070719
0x1400706e0  mov     dword ptr [rsp+58h+lpcbData], 4; cbData
0x1400706e8  lea     r9d, [rax+2]; dwType
0x1400706ec  xor     r8d, r8d; Reserved
0x1400706ef  mov     [rsp+58h+lpData], rsi; lpData
0x1400706f4  mov     rdx, rdi; lpValueName
0x1400706f7  mov     [rsi], r14d
0x1400706fa  mov     rcx, rbp; hKey
0x1400706fd  call    cs:__imp_RegSetValueExW
0x140070703  mov     ebx, eax
0x140070705  test    eax, eax
0x140070707  jz      short loc_140070712
0x140070709  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x140070710  jmp     short loc_14007072B
0x140070712  mov     eax, 1
0x140070717  jmp     short loc_140070740
0x140070719  test    ebx, ebx
0x14007071b  jnz     short loc_140070724
0x14007071d  cmp     [rsp+58h+Type], 4
0x140070722  jz      short loc_140070712
0x140070724  lea     rcx, aRegqueryvaluee_0; "RegQueryValueEx() failed[%s], ec=%d"
0x14007072b  mov     r8d, ebx
0x14007072e  mov     rdx, rdi
0x140070731  call    fax_dprintf
0x140070736  mov     ecx, ebx; dwErrCode
0x140070738  call    cs:__imp_SetLastError
0x14007073e  xor     eax, eax
0x140070740  mov     rbx, [rsp+58h+arg_0]
0x140070745  mov     rbp, [rsp+58h+arg_8]
0x14007074a  add     rsp, 40h
0x14007074e  pop     r14
0x140070750  pop     rdi
0x140070751  pop     rsi
0x140070752  retn
```
