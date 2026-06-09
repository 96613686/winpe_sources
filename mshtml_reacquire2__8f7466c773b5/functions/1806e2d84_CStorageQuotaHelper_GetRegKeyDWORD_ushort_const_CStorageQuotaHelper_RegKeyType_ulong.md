# CStorageQuotaHelper::_GetRegKeyDWORD(ushort const *,CStorageQuotaHelper::RegKeyType,ulong *)

- ea: `0x1806e2d84`
- end: `0x1806e30da`
- name: `?_GetRegKeyDWORD@CStorageQuotaHelper@@AEAAJPEBGW4RegKeyType@1@PEAK@Z`
- size: `854`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1806e2810`
- `0x1806e2b28`
- `0x1806e2d1c`
- `0x180763d28`
- `0x180a372c8`
- `0x180a37b04`

## callees

- `0x1806e2d84`
- `0x180a3894c`
- `0x180a38a64`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806e2f3f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCloseKey` at `0x1806e2f3f`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806e2ef2`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806e2f76`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806e2ef2`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1806e2f76`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1806e2e62`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegCreateKeyExW` at `0x1806e2e62`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2ead`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2f24`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2fa8`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2ead`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2f24`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegSetValueExW` at `0x1806e2fa8`
- `iertutil!__imp_GetValue` at `0x1806e30ba`
- `iertutil!__imp_GetValue` at `0x1806e30ba`
- `iertutil!__imp_GetExtValue` at `0x1806e3029`
- `iertutil!__imp_GetExtValue` at `0x1806e3029`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806e2da7`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1806e2da7`

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
0x1806e2d84  push    rbp
0x1806e2d86  push    rbx
0x1806e2d87  push    rsi
0x1806e2d88  push    rdi
0x1806e2d89  push    r12
0x1806e2d8b  push    r14
0x1806e2d8d  push    r15
0x1806e2d8f  mov     rbp, rsp
0x1806e2d92  sub     rsp, 70h
0x1806e2d96  mov     rsi, rcx
0x1806e2d99  mov     r14, r9
0x1806e2d9c  mov     ecx, 20000003h
0x1806e2da1  mov     edi, r8d
0x1806e2da4  mov     r15, rdx
0x1806e2da7  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1806e2dae  nop     dword ptr [rax+rax+00h]
0x1806e2db3  xor     r12d, r12d
0x1806e2db6  test    al, al
0x1806e2db8  jz      loc_1806E2FCC
0x1806e2dbe  mov     edx, 2001Fh; unsigned int
0x1806e2dc3  mov     [rbp+lpValue], r12
0x1806e2dc7  mov     rcx, rsi; this
0x1806e2dca  mov     [rbp+dwDisposition], r12d
0x1806e2dce  mov     [rbp+hkey], r12
0x1806e2dd2  call    ?_InitializeAppContainerRegKey@CStorageQuotaHelper@@AEAAJK@Z; CStorageQuotaHelper::_InitializeAppContainerRegKey(ulong)
0x1806e2dd7  mov     ebx, eax
0x1806e2dd9  test    eax, eax
0x1806e2ddb  jnz     loc_1806E30C8
0x1806e2de1  cmp     [rsi+0B8h], r12
0x1806e2de8  jz      loc_1806E30C8
0x1806e2dee  cmp     [rsi+0C0h], r12
0x1806e2df5  jz      loc_1806E30C8
0x1806e2dfb  cmp     [rsi+0C8h], r12
0x1806e2e02  jz      loc_1806E30C8
0x1806e2e08  lea     r9, [rbp+hKey]
0x1806e2e0c  mov     [rbp+hKey], r12
0x1806e2e10  lea     r8, [rbp+lpValue]
0x1806e2e14  mov     edx, edi
0x1806e2e16  mov     rcx, rsi
0x1806e2e19  call    ?_MapRegKeyTypeToStringForApp@CStorageQuotaHelper@@AEAAJW4RegKeyType@1@PEAPEBGPEAPEAUHKEY__@@@Z; CStorageQuotaHelper::_MapRegKeyTypeToStringForApp(CStorageQuotaHelper::RegKeyType,ushort const * *,HKEY__ * *)
0x1806e2e1e  mov     ebx, eax
0x1806e2e20  test    eax, eax
0x1806e2e22  jnz     loc_1806E30C8
0x1806e2e28  mov     rcx, [rbp+hKey]; hkey
0x1806e2e2c  test    r15, r15
0x1806e2e2f  jz      loc_1806E2F50
0x1806e2e35  lea     rax, [rbp+dwDisposition]
0x1806e2e39  xor     r9d, r9d; lpClass
0x1806e2e3c  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x1806e2e41  xor     r8d, r8d; Reserved
0x1806e2e44  lea     rax, [rbp+hkey]
0x1806e2e48  mov     rdx, r15; lpSubKey
0x1806e2e4b  mov     [rsp+70h+phkResult], rax; phkResult
0x1806e2e50  mov     [rsp+70h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1806e2e55  mov     [rsp+70h+samDesired], 2001Fh; samDesired
0x1806e2e5d  mov     [rsp+70h+dwOptions], r12d; dwOptions
0x1806e2e62  call    cs:__imp_RegCreateKeyExW
0x1806e2e69  nop     dword ptr [rax+rax+00h]
0x1806e2e6e  mov     ebx, eax
0x1806e2e70  mov     edi, 80070000h
0x1806e2e75  test    eax, eax
0x1806e2e77  jle     short loc_1806E2E7E
0x1806e2e79  movzx   ebx, ax
0x1806e2e7c  or      ebx, edi
0x1806e2e7e  test    ebx, ebx
0x1806e2e80  js      loc_1806E30C8
0x1806e2e86  mov     edx, 1
0x1806e2e8b  cmp     [rbp+dwDisposition], edx
0x1806e2e8e  jnz     short loc_1806E2EC8
0x1806e2e90  mov     rcx, [rbp+hkey]; hKey
0x1806e2e94  lea     r9d, [rdx+3]; dwType
0x1806e2e98  xor     edx, edx; lpValueName
0x1806e2e9a  mov     [rsp+70h+samDesired], 4; cbData
0x1806e2ea2  xor     r8d, r8d; Reserved
0x1806e2ea5  mov     [r14], r12d
0x1806e2ea8  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806e2ead  call    cs:__imp_RegSetValueExW
0x1806e2eb4  nop     dword ptr [rax+rax+00h]
0x1806e2eb9  mov     ebx, eax
0x1806e2ebb  test    eax, eax
0x1806e2ebd  jle     short loc_1806E2EC4
0x1806e2ebf  movzx   ebx, ax
0x1806e2ec2  or      ebx, edi
0x1806e2ec4  test    ebx, ebx
0x1806e2ec6  js      short loc_1806E2F3B
0x1806e2ec8  mov     r8, [rbp+lpValue]; lpValue
0x1806e2ecc  lea     rax, [rbp+pcbData]
0x1806e2ed0  mov     rcx, [rbp+hkey]; hkey
0x1806e2ed4  mov     r9d, 18h; dwFlags
0x1806e2eda  mov     [rsp+70h+lpSecurityAttributes], rax; pcbData
0x1806e2edf  xor     edx, edx; lpSubKey
0x1806e2ee1  mov     qword ptr [rsp+70h+samDesired], r14; pvData
0x1806e2ee6  mov     qword ptr [rsp+70h+dwOptions], r12; pdwType
0x1806e2eeb  mov     [rbp+pcbData], 4
0x1806e2ef2  call    cs:__imp_RegGetValueW
0x1806e2ef9  nop     dword ptr [rax+rax+00h]
0x1806e2efe  mov     ebx, eax
0x1806e2f00  cmp     eax, 2
0x1806e2f03  jnz     short loc_1806E2F32
0x1806e2f05  mov     rdx, [rbp+lpValue]; lpValueName
0x1806e2f09  lea     r9d, [rax+2]; dwType
0x1806e2f0d  mov     rcx, [rbp+hkey]; hKey
0x1806e2f11  xor     r8d, r8d; Reserved
0x1806e2f14  mov     [rsp+70h+samDesired], 4; cbData
0x1806e2f1c  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806e2f21  mov     [r14], r12d
0x1806e2f24  call    cs:__imp_RegSetValueExW
0x1806e2f2b  nop     dword ptr [rax+rax+00h]
0x1806e2f30  mov     ebx, eax
0x1806e2f32  test    ebx, ebx
0x1806e2f34  jle     short loc_1806E2F3B
0x1806e2f36  movzx   ebx, bx
0x1806e2f39  or      ebx, edi
0x1806e2f3b  mov     rcx, [rbp+hkey]; hKey
0x1806e2f3f  call    cs:__imp_RegCloseKey
0x1806e2f46  nop     dword ptr [rax+rax+00h]
0x1806e2f4b  jmp     loc_1806E30C8
0x1806e2f50  mov     r8, [rbp+lpValue]; lpValue
0x1806e2f54  lea     rax, [rbp+pcbData]
0x1806e2f58  mov     [rsp+70h+lpSecurityAttributes], rax; pcbData
0x1806e2f5d  mov     r9d, 18h; dwFlags
0x1806e2f63  mov     qword ptr [rsp+70h+samDesired], r14; pvData
0x1806e2f68  xor     edx, edx; lpSubKey
0x1806e2f6a  mov     qword ptr [rsp+70h+dwOptions], r12; pdwType
0x1806e2f6f  mov     [rbp+pcbData], 4
0x1806e2f76  call    cs:__imp_RegGetValueW
0x1806e2f7d  nop     dword ptr [rax+rax+00h]
0x1806e2f82  mov     ebx, eax
0x1806e2f84  cmp     eax, 2
0x1806e2f87  jnz     short loc_1806E2FB6
0x1806e2f89  mov     rdx, [rbp+lpValue]; lpValueName
0x1806e2f8d  lea     r9d, [rax+2]; dwType
0x1806e2f91  mov     rcx, [rbp+hKey]; hKey
0x1806e2f95  xor     r8d, r8d; Reserved
0x1806e2f98  mov     [rsp+70h+samDesired], 4; cbData
0x1806e2fa0  mov     qword ptr [rsp+70h+dwOptions], r14; lpData
0x1806e2fa5  mov     [r14], r12d
0x1806e2fa8  call    cs:__imp_RegSetValueExW
0x1806e2faf  nop     dword ptr [rax+rax+00h]
0x1806e2fb4  mov     ebx, eax
0x1806e2fb6  test    ebx, ebx
0x1806e2fb8  jle     loc_1806E30C8
0x1806e2fbe  movzx   ebx, bx
0x1806e2fc1  or      ebx, 80070000h
0x1806e2fc7  jmp     loc_1806E30C8
0x1806e2fcc  mov     ebx, 80004005h
0x1806e2fd1  cmp     edi, 5
0x1806e2fd4  jg      loc_1806E3061
0x1806e2fda  jz      short loc_1806E3058
0x1806e2fdc  test    edi, edi
0x1806e2fde  jz      short loc_1806E3052
0x1806e2fe0  sub     edi, 1
0x1806e2fe3  jz      short loc_1806E304C
0x1806e2fe5  sub     edi, 1
0x1806e2fe8  jz      short loc_1806E3043
0x1806e2fea  sub     edi, 1
0x1806e2fed  jz      short loc_1806E303A
0x1806e2fef  cmp     edi, 1
0x1806e2ff2  jnz     loc_1806E30C8
0x1806e2ff8  mov     rcx, [rsi+78h]
0x1806e2ffc  mov     rcx, [rcx]
0x1806e2fff  mov     edx, 1
0x1806e3004  mov     [rsp+70h+lpdwDisposition], r15
0x1806e3009  mov     r8d, edx
0x1806e300c  mov     dword ptr [rsp+70h+phkResult], edx
0x1806e3010  mov     r9, r14
0x1806e3013  mov     [rsp+70h+lpSecurityAttributes], r12
0x1806e3018  mov     qword ptr [rsp+70h+samDesired], r12
0x1806e301d  lea     edx, [r8+7]
0x1806e3021  mov     [rsp+70h+dwOptions], 4
0x1806e3029  call    cs:__imp_GetExtValue
0x1806e3030  nop     dword ptr [rax+rax+00h]
0x1806e3035  jmp     loc_1806E30C6
0x1806e303a  mov     rcx, [rsi+98h]
0x1806e3041  jmp     short loc_1806E2FFC
0x1806e3043  mov     rcx, [rsi+88h]
0x1806e304a  jmp     short loc_1806E309A
0x1806e304c  mov     rcx, [rsi+70h]
0x1806e3050  jmp     short loc_1806E2FFC
0x1806e3052  mov     rcx, [rsi+68h]
0x1806e3056  jmp     short loc_1806E2FFC
0x1806e3058  mov     rcx, [rsi+80h]
0x1806e305f  jmp     short loc_1806E2FFC
0x1806e3061  sub     edi, 6
0x1806e3064  jz      short loc_1806E3093
0x1806e3066  sub     edi, 1
0x1806e3069  jz      short loc_1806E3087
0x1806e306b  sub     edi, 1
0x1806e306e  jz      short loc_1806E307E
0x1806e3070  cmp     edi, 1
0x1806e3073  jnz     short loc_1806E30C8
0x1806e3075  mov     rcx, [rsi+0B0h]
0x1806e307c  jmp     short loc_1806E309A
0x1806e307e  mov     rcx, [rsi+0A8h]
0x1806e3085  jmp     short loc_1806E309A
0x1806e3087  mov     rcx, [rsi+0A0h]
0x1806e308e  jmp     loc_1806E2FFC
0x1806e3093  mov     rcx, [rsi+90h]
0x1806e309a  mov     rcx, [rcx]
0x1806e309d  mov     edx, 1
0x1806e30a2  mov     [rsp+70h+lpSecurityAttributes], r12
0x1806e30a7  mov     r8d, edx
0x1806e30aa  mov     qword ptr [rsp+70h+samDesired], r12
0x1806e30af  mov     r9, r14
0x1806e30b2  mov     [rsp+70h+dwOptions], 4
0x1806e30ba  call    cs:__imp_GetValue
0x1806e30c1  nop     dword ptr [rax+rax+00h]
0x1806e30c6  mov     ebx, eax
0x1806e30c8  mov     eax, ebx
0x1806e30ca  add     rsp, 70h
0x1806e30ce  pop     r15
0x1806e30d0  pop     r14
0x1806e30d2  pop     r12
0x1806e30d4  pop     rdi
0x1806e30d5  pop     rsi
0x1806e30d6  pop     rbx
0x1806e30d7  pop     rbp
0x1806e30d8  retn
```
