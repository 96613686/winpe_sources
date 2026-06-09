# _QueryFeatureControlPolicySetting

- ea: `0x180023670`
- end: `0x18002381e`
- name: `_QueryFeatureControlPolicySetting`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002331c`

## callees

- `0x180023670`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800236a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800236a3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800236e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023738`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800237da`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800236e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023738`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180023789`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800237da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002380b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002380b`

## pseudocode

```c
char __fastcall QueryFeatureControlPolicySetting(HKEY a1, const WCHAR *a2, const WCHAR *a3, int a4, BOOL *a5)
{
  char v7; // bl
  BOOL v8; // ecx
  DWORD pcbData; // [rsp+40h] [rbp-20h] BYREF
  _WORD v11[2]; // [rsp+44h] [rbp-1Ch] BYREF
  unsigned int pvData; // [rsp+48h] [rbp-18h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-10h] BYREF

  hkey = 0;
  v7 = 0;
  if ( !RegOpenKeyExW(a1, a2, 0, 1u, &hkey) )
  {
    pvData = 0;
    pcbData = 4;
    if ( RegGetValueW(hkey, 0, a3, 0x10u, 0, &pvData, &pcbData) )
    {
      if ( !a4 )
      {
LABEL_9:
        pcbData = 4;
        if ( RegGetValueW(hkey, 0, L"*", 0x10u, 0, &pvData, &pcbData) )
        {
          if ( !a4 )
          {
LABEL_18:
            RegCloseKey(hkey);
            return v7;
          }
        }
        else
        {
          v8 = pvData;
          if ( !a4 || pvData <= 1 )
            goto LABEL_17;
        }
        pcbData = 4;
        if ( RegGetValueW(hkey, 0, L"*", 2u, 0, v11, &pcbData) || (unsigned __int16)(v11[0] - 48) > 1u )
          goto LABEL_18;
LABEL_16:
        v8 = v11[0] == 49;
LABEL_17:
        v7 = 1;
        *a5 = v8;
        goto LABEL_18;
      }
    }
    else
    {
      v8 = pvData;
      if ( !a4 || pvData <= 1 )
        goto LABEL_17;
    }
    pcbData = 4;
    if ( !RegGetValueW(hkey, 0, a3, 2u, 0, v11, &pcbData) && (unsigned __int16)(v11[0] - 48) <= 1u )
      goto LABEL_16;
    goto LABEL_9;
  }
  return v7;
}

```

## disassembly

```asm
0x180023670  push    rbp
0x180023672  push    rbx
0x180023673  push    rsi
0x180023674  push    rdi
0x180023675  push    r15
0x180023677  mov     rbp, rsp
0x18002367a  sub     rsp, 60h
0x18002367e  mov     edi, r9d
0x180023681  mov     [rbp+hkey], 0
0x180023689  mov     rsi, r8
0x18002368c  lea     rax, [rbp+hkey]
0x180023690  mov     r15d, 1
0x180023696  mov     [rsp+60h+phkResult], rax; phkResult
0x18002369b  mov     r9d, r15d; samDesired
0x18002369e  xor     r8d, r8d; ulOptions
0x1800236a1  xor     bl, bl
0x1800236a3  call    cs:__imp_RegOpenKeyExW
0x1800236a9  test    eax, eax
0x1800236ab  jnz     loc_180023811
0x1800236b1  mov     rcx, [rbp+hkey]; hkey
0x1800236b5  lea     r9d, [r15+0Fh]; dwFlags
0x1800236b9  mov     [rbp+var_18], eax
0x1800236bc  mov     r8, rsi; lpValue
0x1800236bf  lea     rax, [rbp+var_20]
0x1800236c3  mov     [rbp+var_20], 4
0x1800236ca  mov     [rsp+60h+pcbData], rax; pcbData
0x1800236cf  xor     edx, edx; lpSubKey
0x1800236d1  lea     rax, [rbp+var_18]
0x1800236d5  mov     [rsp+60h+pvData], rax; pvData
0x1800236da  mov     [rsp+60h+phkResult], 0; pdwType
0x1800236e3  call    cs:__imp_RegGetValueW
0x1800236e9  test    eax, eax
0x1800236eb  jnz     short loc_180023703
0x1800236ed  mov     ecx, [rbp+var_18]
0x1800236f0  test    edi, edi
0x1800236f2  jz      loc_1800237FE
0x1800236f8  cmp     ecx, r15d
0x1800236fb  jbe     loc_1800237FE
0x180023701  jmp     short loc_180023707
0x180023703  test    edi, edi
0x180023705  jz      short loc_180023754
0x180023707  mov     rcx, [rbp+hkey]; hkey
0x18002370b  lea     rax, [rbp+var_20]
0x18002370f  mov     [rsp+60h+pcbData], rax; pcbData
0x180023714  mov     r9d, 2; dwFlags
0x18002371a  lea     rax, [rbp+var_1C]
0x18002371e  mov     [rbp+var_20], 4
0x180023725  mov     [rsp+60h+pvData], rax; pvData
0x18002372a  mov     r8, rsi; lpValue
0x18002372d  xor     edx, edx; lpSubKey
0x18002372f  mov     [rsp+60h+phkResult], 0; pdwType
0x180023738  call    cs:__imp_RegGetValueW
0x18002373e  test    eax, eax
0x180023740  jnz     short loc_180023754
0x180023742  movzx   eax, [rbp+var_1C]
0x180023746  sub     ax, 30h ; '0'
0x18002374a  cmp     ax, r15w
0x18002374e  jbe     loc_1800237F2
0x180023754  mov     rcx, [rbp+hkey]; hkey
0x180023758  lea     rax, [rbp+var_20]
0x18002375c  mov     [rsp+60h+pcbData], rax; pcbData
0x180023761  lea     r8, Value; "*"
0x180023768  lea     rax, [rbp+var_18]
0x18002376c  mov     [rbp+var_20], 4
0x180023773  mov     [rsp+60h+pvData], rax; pvData
0x180023778  mov     r9d, 10h; dwFlags
0x18002377e  xor     edx, edx; lpSubKey
0x180023780  mov     [rsp+60h+phkResult], 0; pdwType
0x180023789  call    cs:__imp_RegGetValueW
0x18002378f  test    eax, eax
0x180023791  jnz     short loc_1800237A1
0x180023793  mov     ecx, [rbp+var_18]
0x180023796  test    edi, edi
0x180023798  jz      short loc_1800237FE
0x18002379a  cmp     ecx, r15d
0x18002379d  jbe     short loc_1800237FE
0x18002379f  jmp     short loc_1800237A5
0x1800237a1  test    edi, edi
0x1800237a3  jz      short loc_180023807
0x1800237a5  mov     rcx, [rbp+hkey]; hkey
0x1800237a9  lea     rax, [rbp+var_20]
0x1800237ad  mov     [rsp+60h+pcbData], rax; pcbData
0x1800237b2  lea     r8, Value; "*"
0x1800237b9  lea     rax, [rbp+var_1C]
0x1800237bd  mov     [rbp+var_20], 4
0x1800237c4  mov     [rsp+60h+pvData], rax; pvData
0x1800237c9  mov     r9d, 2; dwFlags
0x1800237cf  xor     edx, edx; lpSubKey
0x1800237d1  mov     [rsp+60h+phkResult], 0; pdwType
0x1800237da  call    cs:__imp_RegGetValueW
0x1800237e0  test    eax, eax
0x1800237e2  jnz     short loc_180023807
0x1800237e4  movzx   eax, [rbp+var_1C]
0x1800237e8  sub     ax, 30h ; '0'
0x1800237ec  cmp     ax, r15w
0x1800237f0  ja      short loc_180023807
0x1800237f2  xor     ecx, ecx
0x1800237f4  lea     eax, [rcx+31h]
0x1800237f7  cmp     ax, [rbp+var_1C]
0x1800237fb  setz    cl
0x1800237fe  mov     rax, [rbp+arg_20]
0x180023802  mov     bl, r15b
0x180023805  mov     [rax], ecx
0x180023807  mov     rcx, [rbp+hkey]; hKey
0x18002380b  call    cs:__imp_RegCloseKey
0x180023811  mov     al, bl
0x180023813  add     rsp, 60h
0x180023817  pop     r15
0x180023819  pop     rdi
0x18002381a  pop     rsi
0x18002381b  pop     rbx
0x18002381c  pop     rbp
0x18002381d  retn
```
