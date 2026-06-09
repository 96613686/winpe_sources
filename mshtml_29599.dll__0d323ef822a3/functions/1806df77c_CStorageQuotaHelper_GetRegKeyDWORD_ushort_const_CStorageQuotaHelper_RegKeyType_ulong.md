# CStorageQuotaHelper::_GetRegKeyDWORD(ushort const *,CStorageQuotaHelper::RegKeyType,ulong *)

- ea: `0x1806df77c`
- end: `0x1806dfa95`
- name: `?_GetRegKeyDWORD@CStorageQuotaHelper@@AEAAJPEBGW4RegKeyType@1@PEAK@Z`
- size: `793`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1806df21c`
- `0x1806df520`
- `0x1806df714`
- `0x18075af04`
- `0x180a24694`
- `0x180a24e90`

## callees

- `0x1806df77c`
- `0x180a25c70`
- `0x180a25d64`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806df919`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806df919`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806df8d8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806df94a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806df8d8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806df94a`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1806df854`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1806df854`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df899`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df904`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df976`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df899`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df904`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806df976`
- `iertutil!__imp_GetValue` at `0x1806dfa7c`
- `iertutil!__imp_GetValue` at `0x1806dfa7c`
- `iertutil!__imp_GetExtValue` at `0x1806df9f1`
- `iertutil!__imp_GetExtValue` at `0x1806df9f1`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806df79f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806df79f`

## pseudocode

```c
__int64 __fastcall CStorageQuotaHelper::_GetRegKeyDWORD(CStorageQuotaHelper *a1, const WCHAR *a2, __int64 a3, BYTE *a4)
{
  int v6; // edi
  int ValueW; // ebx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  LSTATUS v11; // eax
  const WCHAR *v12; // rdx
  HKEY v13; // rcx
  const WCHAR *v14; // rdx
  HKEY v15; // rcx
  int v16; // edi
  int v17; // edi
  int v18; // edi
  _QWORD *v19; // rcx
  _QWORD *v21; // rcx
  int v22; // edi
  int v23; // edi
  int v24; // edi
  DWORD dwDisposition; // [rsp+50h] [rbp-20h] BYREF
  DWORD pcbData; // [rsp+54h] [rbp-1Ch] BYREF
  HKEY hkey; // [rsp+58h] [rbp-18h] BYREF
  LPCWSTR lpValue; // [rsp+60h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-8h] BYREF

  v6 = a3;
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870915, a2, a3, a4) )
  {
    ValueW = -2147467259;
    if ( v6 > 5 )
    {
      v22 = v6 - 6;
      if ( !v22 )
      {
        v21 = (_QWORD *)*((_QWORD *)a1 + 18);
        return (unsigned int)GetValue(*v21, 1, 1, a4, 4, 0, 0);
      }
      v23 = v22 - 1;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          if ( v24 != 1 )
            return (unsigned int)ValueW;
          v21 = (_QWORD *)*((_QWORD *)a1 + 22);
        }
        else
        {
          v21 = (_QWORD *)*((_QWORD *)a1 + 21);
        }
        return (unsigned int)GetValue(*v21, 1, 1, a4, 4, 0, 0);
      }
      v19 = (_QWORD *)*((_QWORD *)a1 + 20);
    }
    else if ( v6 == 5 )
    {
      v19 = (_QWORD *)*((_QWORD *)a1 + 16);
    }
    else if ( v6 )
    {
      v16 = v6 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            if ( v18 != 1 )
              return (unsigned int)ValueW;
            v19 = (_QWORD *)*((_QWORD *)a1 + 15);
          }
          else
          {
            v19 = (_QWORD *)*((_QWORD *)a1 + 19);
          }
          return (unsigned int)GetExtValue(*v19, 8, 1, a4, 4, 0, 0, 1, a2);
        }
        v21 = (_QWORD *)*((_QWORD *)a1 + 17);
        return (unsigned int)GetValue(*v21, 1, 1, a4, 4, 0, 0);
      }
      v19 = (_QWORD *)*((_QWORD *)a1 + 14);
    }
    else
    {
      v19 = (_QWORD *)*((_QWORD *)a1 + 13);
    }
    return (unsigned int)GetExtValue(*v19, 8, 1, a4, 4, 0, 0, 1, a2);
  }
  lpValue = 0;
  dwDisposition = 0;
  hkey = 0;
  ValueW = CStorageQuotaHelper::_InitializeAppContainerRegKey(a1, 0x2001Fu);
  if ( !ValueW )
  {
    if ( *((_QWORD *)a1 + 23) )
    {
      if ( *((_QWORD *)a1 + 24) )
      {
        if ( *((_QWORD *)a1 + 25) )
        {
          hKey = 0;
          ValueW = CStorageQuotaHelper::_MapRegKeyTypeToStringForApp(a1, (unsigned int)v6, &lpValue, &hKey);
          if ( !ValueW )
          {
            if ( a2 )
            {
              v9 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x2001Fu, 0, &hkey, &dwDisposition);
              ValueW = v9;
              if ( v9 > 0 )
                ValueW = (unsigned __int16)v9 | 0x80070000;
              if ( ValueW >= 0 )
              {
                if ( dwDisposition != 1 )
                  goto LABEL_15;
                v10 = hkey;
                *(_DWORD *)a4 = 0;
                v11 = RegSetValueExW(v10, 0, 0, 4u, a4, 4u);
                ValueW = v11;
                if ( v11 > 0 )
                  ValueW = (unsigned __int16)v11 | 0x80070000;
                if ( ValueW >= 0 )
                {
LABEL_15:
                  pcbData = 4;
                  ValueW = RegGetValueW(hkey, 0, lpValue, 0x18u, 0, a4, &pcbData);
                  if ( ValueW == 2 )
                  {
                    v12 = lpValue;
                    v13 = hkey;
                    *(_DWORD *)a4 = 0;
                    ValueW = RegSetValueExW(v13, v12, 0, 4u, a4, 4u);
                  }
                  if ( ValueW > 0 )
                    ValueW = (unsigned __int16)ValueW | 0x80070000;
                }
                RegCloseKey(hkey);
              }
            }
            else
            {
              pcbData = 4;
              ValueW = RegGetValueW(hKey, 0, lpValue, 0x18u, 0, a4, &pcbData);
              if ( ValueW == 2 )
              {
                v14 = lpValue;
                v15 = hKey;
                *(_DWORD *)a4 = 0;
                ValueW = RegSetValueExW(v15, v14, 0, 4u, a4, 4u);
              }
              if ( ValueW > 0 )
                return (unsigned __int16)ValueW | 0x80070000;
            }
          }
        }
      }
    }
  }
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1806df77c  push    rbp
0x1806df77e  push    rbx
0x1806df77f  push    rsi
0x1806df780  push    rdi
0x1806df781  push    r12
0x1806df783  push    r14
0x1806df785  push    r15
0x1806df787  mov     rbp, rsp
0x1806df78a  sub     rsp, 70h
0x1806df78e  mov     rsi, rcx
0x1806df791  mov     r14, r9
0x1806df794  mov     ecx, 20000003h
0x1806df799  mov     edi, r8d
0x1806df79c  mov     r15, rdx
0x1806df79f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1806df7a5  xor     r12d, r12d
0x1806df7a8  test    al, al
0x1806df7aa  jz      loc_1806DF994
0x1806df7b0  mov     edx, 2001Fh; unsigned int
0x1806df7b5  mov     [rbp+lpValue], r12
0x1806df7b9  mov     rcx, rsi; this
0x1806df7bc  mov     [rbp+dwDisposition], r12d
0x1806df7c0  mov     [rbp+hkey], r12
0x1806df7c4  call    ?_InitializeAppContainerRegKey@CStorageQuotaHelper@@AEAAJK@Z; CStorageQuotaHelper::_InitializeAppContainerRegKey(ulong)
0x1806df7c9  mov     ebx, eax
0x1806df7cb  test    eax, eax
0x1806df7cd  jnz     loc_1806DFA84
0x1806df7d3  cmp     [rsi+0B8h], r12
0x1806df7da  jz      loc_1806DFA84
0x1806df7e0  cmp     [rsi+0C0h], r12
0x1806df7e7  jz      loc_1806DFA84
0x1806df7ed  cmp     [rsi+0C8h], r12
0x1806df7f4  jz      loc_1806DFA84
0x1806df7fa  lea     r9, [rbp+hKey]
0x1806df7fe  mov     [rbp+hKey], r12
0x1806df802  lea     r8, [rbp+lpValue]
0x1806df806  mov     edx, edi
0x1806df808  mov     rcx, rsi
0x1806df80b  call    ?_MapRegKeyTypeToStringForApp@CStorageQuotaHelper@@AEAAJW4RegKeyType@1@PEAPEBGPEAPEAUHKEY__@@@Z; CStorageQuotaHelper::_MapRegKeyTypeToStringForApp(CStorageQuotaHelper::RegKeyType,ushort const * *,HKEY__ * *)
0x1806df810  mov     ebx, eax
0x1806df812  test    eax, eax
0x1806df814  jnz     loc_1806DFA84
0x1806df81a  mov     rcx, [rbp+hKey]; hkey
0x1806df81e  test    r15, r15
0x1806df821  jz      loc_1806DF924
0x1806df827  lea     rax, [rbp+dwDisposition]
0x1806df82b  xor     r9d, r9d; lpClass
0x1806df82e  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1806df833  xor     r8d, r8d; Reserved
0x1806df836  lea     rax, [rbp+hkey]
0x1806df83a  mov     rdx, r15; lpSubKey
0x1806df83d  mov     [rsp+70h+phkResult], rax; phkResult
0x1806df842  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1806df847  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1806df84f  mov     [rsp+70h+dwOptions], r12d; dwOptions
0x1806df854  call    cs:__imp_RegCreateKeyExW
0x1806df85a  mov     ebx, eax
0x1806df85c  mov     edi, 80070000h
0x1806df861  test    eax, eax
0x1806df863  jle     short loc_1806DF86A
0x1806df865  movzx   ebx, ax
0x1806df868  or      ebx, edi
0x1806df86a  test    ebx, ebx
0x1806df86c  js      loc_1806DFA84
0x1806df872  mov     edx, 1
0x1806df877  cmp     [rbp+dwDisposition], edx
0x1806df87a  jnz     short loc_1806DF8AE
0x1806df87c  mov     rcx, [rbp+hkey]; hKey
0x1806df880  lea     r9d, [rdx+3]; dwType
0x1806df884  xor     edx, edx; lpValueName
0x1806df886  mov     [rsp+70h+samDesired], 4; cbData
0x1806df88e  xor     r8d, r8d; Reserved
0x1806df891  mov     [r14], r12d
0x1806df894  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806df899  call    cs:__imp_RegSetValueExW
0x1806df89f  mov     ebx, eax
0x1806df8a1  test    eax, eax
0x1806df8a3  jle     short loc_1806DF8AA
0x1806df8a5  movzx   ebx, ax
0x1806df8a8  or      ebx, edi
0x1806df8aa  test    ebx, ebx
0x1806df8ac  js      short loc_1806DF915
0x1806df8ae  mov     r8, [rbp+lpValue]; lpValue
0x1806df8b2  lea     rax, [rbp+pcbData]
0x1806df8b6  mov     rcx, [rbp+hkey]; hkey
0x1806df8ba  mov     r9d, 18h; dwFlags
0x1806df8c0  mov     [rsp+70h+lpSecurityAttributes], rax; pcbData
0x1806df8c5  xor     edx, edx; lpSubKey
0x1806df8c7  mov     qword ptr [rsp+70h+samDesired], r14; pvData
0x1806df8cc  mov     qword ptr [rsp+70h+dwOptions], r12; pdwType
0x1806df8d1  mov     [rbp+pcbData], 4
0x1806df8d8  call    cs:__imp_RegGetValueW
0x1806df8de  mov     ebx, eax
0x1806df8e0  cmp     eax, 2
0x1806df8e3  jnz     short loc_1806DF90C
0x1806df8e5  mov     rdx, [rbp+lpValue]; lpValueName
0x1806df8e9  lea     r9d, [rax+2]; dwType
0x1806df8ed  mov     rcx, [rbp+hkey]; hKey
0x1806df8f1  xor     r8d, r8d; Reserved
0x1806df8f4  mov     [rsp+70h+samDesired], 4; cbData
0x1806df8fc  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806df901  mov     [r14], r12d
0x1806df904  call    cs:__imp_RegSetValueExW
0x1806df90a  mov     ebx, eax
0x1806df90c  test    ebx, ebx
0x1806df90e  jle     short loc_1806DF915
0x1806df910  movzx   ebx, bx
0x1806df913  or      ebx, edi
0x1806df915  mov     rcx, [rbp+hkey]; hKey
0x1806df919  call    cs:__imp_RegCloseKey
0x1806df91f  jmp     loc_1806DFA84
0x1806df924  mov     r8, [rbp+lpValue]; lpValue
0x1806df928  lea     rax, [rbp+pcbData]
0x1806df92c  mov     [rsp+70h+lpSecurityAttributes], rax; pcbData
0x1806df931  mov     r9d, 18h; dwFlags
0x1806df937  mov     qword ptr [rsp+70h+samDesired], r14; pvData
0x1806df93c  xor     edx, edx; lpSubKey
0x1806df93e  mov     qword ptr [rsp+70h+dwOptions], r12; pdwType
0x1806df943  mov     [rbp+pcbData], 4
0x1806df94a  call    cs:__imp_RegGetValueW
0x1806df950  mov     ebx, eax
0x1806df952  cmp     eax, 2
0x1806df955  jnz     short loc_1806DF97E
0x1806df957  mov     rdx, [rbp+lpValue]; lpValueName
0x1806df95b  lea     r9d, [rax+2]; dwType
0x1806df95f  mov     rcx, [rbp+hKey]; hKey
0x1806df963  xor     r8d, r8d; Reserved
0x1806df966  mov     [rsp+70h+samDesired], 4; cbData
0x1806df96e  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806df973  mov     [r14], r12d
0x1806df976  call    cs:__imp_RegSetValueExW
0x1806df97c  mov     ebx, eax
0x1806df97e  test    ebx, ebx
0x1806df980  jle     loc_1806DFA84
0x1806df986  movzx   ebx, bx
0x1806df989  or      ebx, 80070000h
0x1806df98f  jmp     loc_1806DFA84
0x1806df994  mov     ebx, 80004005h
0x1806df999  cmp     edi, 5
0x1806df99c  jg      loc_1806DFA23
0x1806df9a2  jz      short loc_1806DFA1A
0x1806df9a4  test    edi, edi
0x1806df9a6  jz      short loc_1806DFA14
0x1806df9a8  sub     edi, 1
0x1806df9ab  jz      short loc_1806DFA0E
0x1806df9ad  sub     edi, 1
0x1806df9b0  jz      short loc_1806DFA05
0x1806df9b2  sub     edi, 1
0x1806df9b5  jz      short loc_1806DF9FC
0x1806df9b7  cmp     edi, 1
0x1806df9ba  jnz     loc_1806DFA84
0x1806df9c0  mov     rcx, [rsi+78h]
0x1806df9c4  mov     rcx, [rcx]
0x1806df9c7  mov     edx, 1
0x1806df9cc  mov     [rsp+70h+lpdwDisposition], r15
0x1806df9d1  mov     r8d, edx
0x1806df9d4  mov     dword ptr [rsp+70h+phkResult], edx
0x1806df9d8  mov     r9, r14
0x1806df9db  mov     [rsp+70h+lpSecurityAttributes], r12
0x1806df9e0  mov     qword ptr [rsp+70h+samDesired], r12
0x1806df9e5  lea     edx, [r8+7]
0x1806df9e9  mov     [rsp+70h+dwOptions], 4
0x1806df9f1  call    cs:__imp_GetExtValue
0x1806df9f7  jmp     loc_1806DFA82
0x1806df9fc  mov     rcx, [rsi+98h]
0x1806dfa03  jmp     short loc_1806DF9C4
0x1806dfa05  mov     rcx, [rsi+88h]
0x1806dfa0c  jmp     short loc_1806DFA5C
0x1806dfa0e  mov     rcx, [rsi+70h]
0x1806dfa12  jmp     short loc_1806DF9C4
0x1806dfa14  mov     rcx, [rsi+68h]
0x1806dfa18  jmp     short loc_1806DF9C4
0x1806dfa1a  mov     rcx, [rsi+80h]
0x1806dfa21  jmp     short loc_1806DF9C4
0x1806dfa23  sub     edi, 6
0x1806dfa26  jz      short loc_1806DFA55
0x1806dfa28  sub     edi, 1
0x1806dfa2b  jz      short loc_1806DFA49
0x1806dfa2d  sub     edi, 1
0x1806dfa30  jz      short loc_1806DFA40
0x1806dfa32  cmp     edi, 1
0x1806dfa35  jnz     short loc_1806DFA84
0x1806dfa37  mov     rcx, [rsi+0B0h]
0x1806dfa3e  jmp     short loc_1806DFA5C
0x1806dfa40  mov     rcx, [rsi+0A8h]
0x1806dfa47  jmp     short loc_1806DFA5C
0x1806dfa49  mov     rcx, [rsi+0A0h]
0x1806dfa50  jmp     loc_1806DF9C4
0x1806dfa55  mov     rcx, [rsi+90h]
0x1806dfa5c  mov     rcx, [rcx]
0x1806dfa5f  mov     edx, 1
0x1806dfa64  mov     [rsp+70h+lpSecurityAttributes], r12
0x1806dfa69  mov     r8d, edx
0x1806dfa6c  mov     qword ptr [rsp+70h+samDesired], r12
0x1806dfa71  mov     r9, r14
0x1806dfa74  mov     [rsp+70h+dwOptions], 4
0x1806dfa7c  call    cs:__imp_GetValue
0x1806dfa82  mov     ebx, eax
0x1806dfa84  mov     eax, ebx
0x1806dfa86  add     rsp, 70h
0x1806dfa8a  pop     r15
0x1806dfa8c  pop     r14
0x1806dfa8e  pop     r12
0x1806dfa90  pop     rdi
0x1806dfa91  pop     rsi
0x1806dfa92  pop     rbx
0x1806dfa93  pop     rbp
0x1806dfa94  retn
```
