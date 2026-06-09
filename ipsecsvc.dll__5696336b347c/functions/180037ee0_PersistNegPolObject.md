# PersistNegPolObject

- ea: `0x180037ee0`
- end: `0x18003841b`
- name: `PersistNegPolObject`
- size: `1339`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038908`

## callees

- `0x18000e510`
- `0x180037ee0`
- `0x180038c44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800383ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180038078`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180038078`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037fc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038036`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800380b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038122`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038190`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800381fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800382c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038321`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800383b9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037fc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038036`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800380b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038122`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038190`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800381fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038269`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800382c3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038321`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800383b9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037f2c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180037f2c`

## pseudocode

```c
__int64 __fastcall PersistNegPolObject(HKEY a1, __int64 a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  const BYTE *lpData; // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  const BYTE *v12; // rcx
  __int64 v13; // rax
  const BYTE *v14; // rcx
  __int64 v15; // rax
  const BYTE *v16; // rcx
  __int64 v17; // rax
  const BYTE *v18; // rcx
  __int64 v19; // rax
  const BYTE *v20; // rcx
  const BYTE *v21; // rcx
  DWORD v23; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v3 = *(const WCHAR **)a2;
  v23 = 0;
  hKey = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, &v23);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 59;
LABEL_73:
      v8 = v4;
LABEL_74:
      WPP_SF_d(v6[2], v7, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v8);
    }
  }
  else
  {
    if ( !hKey )
    {
      v5 = 1359;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        return v5;
      v7 = 60;
      v8 = 1359;
      goto LABEL_74;
    }
    v4 = RegSetValueExW(hKey, L"className", 0, 1u, L"ipsecNegotiationPolicy", 0x2Eu);
    v5 = v4;
    if ( !v4 )
    {
      lpData = *(const BYTE **)(a2 + 80);
      v10 = -1;
      if ( lpData )
      {
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&lpData[2 * v11] );
        v4 = RegSetValueExW(hKey, L"description", 0, 1u, lpData, 2 * v11 + 2);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v7 = 62;
            goto LABEL_73;
          }
          goto LABEL_75;
        }
      }
      else
      {
        RegDeleteValueW(hKey, L"description");
      }
      v12 = *(const BYTE **)a2;
      if ( !*(_QWORD *)a2 )
        goto LABEL_28;
      v13 = -1;
      do
        ++v13;
      while ( *(_WORD *)&v12[2 * v13] );
      v4 = RegSetValueExW(hKey, L"name", 0, 1u, v12, 2 * v13 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 63;
          goto LABEL_73;
        }
      }
      else
      {
LABEL_28:
        v14 = *(const BYTE **)(a2 + 8);
        if ( !v14 )
          goto LABEL_35;
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v14[2 * v15] );
        v4 = RegSetValueExW(hKey, L"ipsecName", 0, 1u, v14, 2 * v15 + 2);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v7 = 64;
            goto LABEL_73;
          }
        }
        else
        {
LABEL_35:
          v16 = *(const BYTE **)(a2 + 16);
          if ( !v16 )
            goto LABEL_42;
          v17 = -1;
          do
            ++v17;
          while ( *(_WORD *)&v16[2 * v17] );
          v4 = RegSetValueExW(hKey, L"ipsecID", 0, 1u, v16, 2 * v17 + 2);
          v5 = v4;
          if ( v4 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v7 = 65;
              goto LABEL_73;
            }
          }
          else
          {
LABEL_42:
            v18 = *(const BYTE **)(a2 + 48);
            if ( !v18 )
              goto LABEL_49;
            v19 = -1;
            do
              ++v19;
            while ( *(_WORD *)&v18[2 * v19] );
            v4 = RegSetValueExW(hKey, L"ipsecNegotiationPolicyAction", 0, 1u, v18, 2 * v19 + 2);
            v5 = v4;
            if ( v4 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v7 = 66;
                goto LABEL_73;
              }
            }
            else
            {
LABEL_49:
              v20 = *(const BYTE **)(a2 + 56);
              if ( !v20 )
                goto LABEL_55;
              do
                ++v10;
              while ( *(_WORD *)&v20[2 * v10] );
              v4 = RegSetValueExW(hKey, L"ipsecNegotiationPolicyType", 0, 1u, v20, 2 * v10 + 2);
              v5 = v4;
              if ( v4 )
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v7 = 67;
                  goto LABEL_73;
                }
              }
              else
              {
LABEL_55:
                v4 = RegSetValueExW(hKey, L"ipsecDataType", 0, 4u, (const BYTE *)(a2 + 24), 4u);
                v5 = v4;
                if ( v4 )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v7 = 68;
                    goto LABEL_73;
                  }
                }
                else
                {
                  v21 = *(const BYTE **)(a2 + 32);
                  if ( v21
                    && (v4 = RegSetValueExW(hKey, L"ipsecData", 0, 3u, v21, *(_DWORD *)(a2 + 40)), (v5 = v4) != 0) )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v7 = 69;
                      goto LABEL_73;
                    }
                  }
                  else if ( *(_QWORD *)(a2 + 64)
                         && (v4 = RegWriteMultiValuedString(hKey, L"ipsecOwnersReference"), (v5 = v4) != 0) )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v7 = 70;
                      goto LABEL_73;
                    }
                  }
                  else
                  {
                    v4 = RegSetValueExW(hKey, L"whenChanged", 0, 4u, (const BYTE *)(a2 + 76), 4u);
                    v5 = v4;
                    if ( v4 )
                    {
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        v7 = 71;
                        goto LABEL_73;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_75;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 61;
      goto LABEL_73;
    }
  }
LABEL_75:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180037ee0  mov     r11, rsp
0x180037ee3  mov     [r11+8], rbx
0x180037ee7  push    rbp
0x180037ee8  push    rsi
0x180037ee9  push    rdi
0x180037eea  push    r14
0x180037eec  push    r15
0x180037eee  mov     rbp, rsp
0x180037ef1  sub     rsp, 50h
0x180037ef5  xor     r14d, r14d
0x180037ef8  lea     rax, [rbp+arg_8]
0x180037efc  mov     [r11-38h], rax
0x180037f00  mov     rdi, rdx
0x180037f03  mov     rdx, [rdx]; lpSubKey
0x180037f06  lea     rax, [rbp+hKey]
0x180037f0a  mov     [r11-40h], rax
0x180037f0e  xor     r9d, r9d; lpClass
0x180037f11  mov     [r11-48h], r14
0x180037f15  xor     r8d, r8d; Reserved
0x180037f18  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180037f20  mov     [r11-58h], r14d
0x180037f24  mov     [rbp+arg_8], r14d
0x180037f28  mov     [rbp+hKey], r14
0x180037f2c  call    cs:__imp_RegCreateKeyExW
0x180037f32  mov     ebx, eax
0x180037f34  test    eax, eax
0x180037f36  jz      short loc_180037F62
0x180037f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f3f  lea     rdx, WPP_GLOBAL_Control
0x180037f46  cmp     rcx, rdx
0x180037f49  jz      loc_1800383F6
0x180037f4f  test    byte ptr [rcx+1Ch], 10h
0x180037f53  jz      loc_1800383F6
0x180037f59  lea     edx, [r14+3Bh]
0x180037f5d  jmp     loc_1800383E3
0x180037f62  mov     rcx, [rbp+hKey]; hKey
0x180037f66  test    rcx, rcx
0x180037f69  jnz     short loc_180037F9E
0x180037f6b  mov     ebx, 54Fh
0x180037f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180037f77  lea     rdx, WPP_GLOBAL_Control
0x180037f7e  cmp     rcx, rdx
0x180037f81  jz      loc_180038405
0x180037f87  test    byte ptr [rcx+1Ch], 10h
0x180037f8b  jz      loc_180038405
0x180037f91  mov     edx, 3Ch ; '<'
0x180037f96  mov     r9d, ebx
0x180037f99  jmp     loc_1800383E6
0x180037f9e  lea     rax, aIpsecnegotiati_3; "ipsecNegotiationPolicy"
0x180037fa5  mov     [rsp+50h+samDesired], 2Eh ; '.'; cbData
0x180037fad  mov     r15d, 1
0x180037fb3  mov     [rsp+50h+lpData], rax; lpData
0x180037fb8  mov     r9d, r15d; dwType
0x180037fbb  lea     rdx, aClassname; "className"
0x180037fc2  xor     r8d, r8d; Reserved
0x180037fc5  call    cs:__imp_RegSetValueExW
0x180037fcb  mov     ebx, eax
0x180037fcd  test    eax, eax
0x180037fcf  jz      short loc_180037FFB
0x180037fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180037fd8  lea     rdx, WPP_GLOBAL_Control
0x180037fdf  cmp     rcx, rdx
0x180037fe2  jz      loc_1800383F6
0x180037fe8  test    byte ptr [rcx+1Ch], 10h
0x180037fec  jz      loc_1800383F6
0x180037ff2  lea     edx, [r15+3Ch]
0x180037ff6  jmp     loc_1800383E3
0x180037ffb  mov     rcx, [rdi+50h]
0x180037fff  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038003  test    rcx, rcx
0x180038006  jz      short loc_18003806D
0x180038008  mov     rax, rsi
0x18003800b  inc     rax
0x18003800e  cmp     [rcx+rax*2], r14w
0x180038013  jnz     short loc_18003800B
0x180038015  lea     eax, ds:2[rax*2]
0x18003801c  mov     r9d, r15d; dwType
0x18003801f  mov     [rsp+50h+samDesired], eax; cbData
0x180038023  lea     rdx, aDescription_0; "description"
0x18003802a  mov     [rsp+50h+lpData], rcx; lpData
0x18003802f  xor     r8d, r8d; Reserved
0x180038032  mov     rcx, [rbp+hKey]; hKey
0x180038036  call    cs:__imp_RegSetValueExW
0x18003803c  mov     ebx, eax
0x18003803e  test    eax, eax
0x180038040  jz      short loc_18003807E
0x180038042  mov     rcx, cs:WPP_GLOBAL_Control
0x180038049  lea     rdx, WPP_GLOBAL_Control
0x180038050  cmp     rcx, rdx
0x180038053  jz      loc_1800383F6
0x180038059  test    byte ptr [rcx+1Ch], 10h
0x18003805d  jz      loc_1800383F6
0x180038063  mov     edx, 3Eh ; '>'
0x180038068  jmp     loc_1800383E3
0x18003806d  mov     rcx, [rbp+hKey]; hKey
0x180038071  lea     rdx, aDescription_0; "description"
0x180038078  call    cs:__imp_RegDeleteValueW
0x18003807e  mov     rcx, [rdi]
0x180038081  test    rcx, rcx
0x180038084  jz      short loc_1800380EB
0x180038086  mov     rax, rsi
0x180038089  inc     rax
0x18003808c  cmp     [rcx+rax*2], r14w
0x180038091  jnz     short loc_180038089
0x180038093  lea     eax, ds:2[rax*2]
0x18003809a  mov     r9d, r15d; dwType
0x18003809d  mov     [rsp+50h+samDesired], eax; cbData
0x1800380a1  lea     rdx, aName; "name"
0x1800380a8  mov     [rsp+50h+lpData], rcx; lpData
0x1800380ad  xor     r8d, r8d; Reserved
0x1800380b0  mov     rcx, [rbp+hKey]; hKey
0x1800380b4  call    cs:__imp_RegSetValueExW
0x1800380ba  mov     ebx, eax
0x1800380bc  test    eax, eax
0x1800380be  jz      short loc_1800380EB
0x1800380c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800380c7  lea     rdx, WPP_GLOBAL_Control
0x1800380ce  cmp     rcx, rdx
0x1800380d1  jz      loc_1800383F6
0x1800380d7  test    byte ptr [rcx+1Ch], 10h
0x1800380db  jz      loc_1800383F6
0x1800380e1  mov     edx, 3Fh ; '?'
0x1800380e6  jmp     loc_1800383E3
0x1800380eb  mov     rcx, [rdi+8]
0x1800380ef  test    rcx, rcx
0x1800380f2  jz      short loc_180038159
0x1800380f4  mov     rax, rsi
0x1800380f7  inc     rax
0x1800380fa  cmp     [rcx+rax*2], r14w
0x1800380ff  jnz     short loc_1800380F7
0x180038101  lea     eax, ds:2[rax*2]
0x180038108  mov     r9d, r15d; dwType
0x18003810b  mov     [rsp+50h+samDesired], eax; cbData
0x18003810f  lea     rdx, aIpsecname_0; "ipsecName"
0x180038116  mov     [rsp+50h+lpData], rcx; lpData
0x18003811b  xor     r8d, r8d; Reserved
0x18003811e  mov     rcx, [rbp+hKey]; hKey
0x180038122  call    cs:__imp_RegSetValueExW
0x180038128  mov     ebx, eax
0x18003812a  test    eax, eax
0x18003812c  jz      short loc_180038159
0x18003812e  mov     rcx, cs:WPP_GLOBAL_Control
0x180038135  lea     rdx, WPP_GLOBAL_Control
0x18003813c  cmp     rcx, rdx
0x18003813f  jz      loc_1800383F6
0x180038145  test    byte ptr [rcx+1Ch], 10h
0x180038149  jz      loc_1800383F6
0x18003814f  mov     edx, 40h ; '@'
0x180038154  jmp     loc_1800383E3
0x180038159  mov     rcx, [rdi+10h]
0x18003815d  test    rcx, rcx
0x180038160  jz      short loc_1800381C7
0x180038162  mov     rax, rsi
0x180038165  inc     rax
0x180038168  cmp     [rcx+rax*2], r14w
0x18003816d  jnz     short loc_180038165
0x18003816f  lea     eax, ds:2[rax*2]
0x180038176  mov     r9d, r15d; dwType
0x180038179  mov     [rsp+50h+samDesired], eax; cbData
0x18003817d  lea     rdx, aIpsecid_0; "ipsecID"
0x180038184  mov     [rsp+50h+lpData], rcx; lpData
0x180038189  xor     r8d, r8d; Reserved
0x18003818c  mov     rcx, [rbp+hKey]; hKey
0x180038190  call    cs:__imp_RegSetValueExW
0x180038196  mov     ebx, eax
0x180038198  test    eax, eax
0x18003819a  jz      short loc_1800381C7
0x18003819c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381a3  lea     rdx, WPP_GLOBAL_Control
0x1800381aa  cmp     rcx, rdx
0x1800381ad  jz      loc_1800383F6
0x1800381b3  test    byte ptr [rcx+1Ch], 10h
0x1800381b7  jz      loc_1800383F6
0x1800381bd  mov     edx, 41h ; 'A'
0x1800381c2  jmp     loc_1800383E3
0x1800381c7  mov     rcx, [rdi+30h]
0x1800381cb  test    rcx, rcx
0x1800381ce  jz      short loc_180038235
0x1800381d0  mov     rax, rsi
0x1800381d3  inc     rax
0x1800381d6  cmp     [rcx+rax*2], r14w
0x1800381db  jnz     short loc_1800381D3
0x1800381dd  lea     eax, ds:2[rax*2]
0x1800381e4  mov     r9d, r15d; dwType
0x1800381e7  mov     [rsp+50h+samDesired], eax; cbData
0x1800381eb  lea     rdx, aIpsecnegotiati_4; "ipsecNegotiationPolicyAction"
0x1800381f2  mov     [rsp+50h+lpData], rcx; lpData
0x1800381f7  xor     r8d, r8d; Reserved
0x1800381fa  mov     rcx, [rbp+hKey]; hKey
0x1800381fe  call    cs:__imp_RegSetValueExW
0x180038204  mov     ebx, eax
0x180038206  test    eax, eax
0x180038208  jz      short loc_180038235
0x18003820a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038211  lea     rdx, WPP_GLOBAL_Control
0x180038218  cmp     rcx, rdx
0x18003821b  jz      loc_1800383F6
0x180038221  test    byte ptr [rcx+1Ch], 10h
0x180038225  jz      loc_1800383F6
0x18003822b  mov     edx, 42h ; 'B'
0x180038230  jmp     loc_1800383E3
0x180038235  mov     rcx, [rdi+38h]
0x180038239  test    rcx, rcx
0x18003823c  jz      short loc_1800382A0
0x18003823e  inc     rsi
0x180038241  cmp     [rcx+rsi*2], r14w
0x180038246  jnz     short loc_18003823E
0x180038248  lea     eax, ds:2[rsi*2]
0x18003824f  mov     r9d, r15d; dwType
0x180038252  mov     [rsp+50h+samDesired], eax; cbData
0x180038256  lea     rdx, aIpsecnegotiati_5; "ipsecNegotiationPolicyType"
0x18003825d  mov     [rsp+50h+lpData], rcx; lpData
0x180038262  xor     r8d, r8d; Reserved
0x180038265  mov     rcx, [rbp+hKey]; hKey
0x180038269  call    cs:__imp_RegSetValueExW
0x18003826f  mov     ebx, eax
0x180038271  test    eax, eax
0x180038273  jz      short loc_1800382A0
0x180038275  mov     rcx, cs:WPP_GLOBAL_Control
0x18003827c  lea     rdx, WPP_GLOBAL_Control
0x180038283  cmp     rcx, rdx
0x180038286  jz      loc_1800383F6
0x18003828c  test    byte ptr [rcx+1Ch], 10h
0x180038290  jz      loc_1800383F6
0x180038296  mov     edx, 43h ; 'C'
0x18003829b  jmp     loc_1800383E3
0x1800382a0  mov     rcx, [rbp+hKey]; hKey
0x1800382a4  lea     rax, [rdi+18h]
0x1800382a8  mov     esi, 4
0x1800382ad  lea     rdx, aIpsecdatatype_0; "ipsecDataType"
0x1800382b4  mov     [rsp+50h+samDesired], esi; cbData
0x1800382b8  mov     r9d, esi; dwType
0x1800382bb  xor     r8d, r8d; Reserved
0x1800382be  mov     [rsp+50h+lpData], rax; lpData
0x1800382c3  call    cs:__imp_RegSetValueExW
0x1800382c9  mov     ebx, eax
0x1800382cb  test    eax, eax
0x1800382cd  jz      short loc_1800382F8
0x1800382cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800382d6  lea     rdx, WPP_GLOBAL_Control
0x1800382dd  cmp     rcx, rdx
0x1800382e0  jz      loc_1800383F6
0x1800382e6  test    byte ptr [rcx+1Ch], 10h
0x1800382ea  jz      loc_1800383F6
0x1800382f0  lea     edx, [rsi+40h]
0x1800382f3  jmp     loc_1800383E3
0x1800382f8  mov     rcx, [rdi+20h]
0x1800382fc  test    rcx, rcx
0x1800382ff  jz      short loc_180038358
0x180038301  mov     eax, [rdi+28h]
0x180038304  lea     rdx, aIpsecdata_0; "ipsecData"
0x18003830b  mov     [rsp+50h+samDesired], eax; cbData
0x18003830f  mov     r9d, 3; dwType
0x180038315  mov     [rsp+50h+lpData], rcx; lpData
0x18003831a  xor     r8d, r8d; Reserved
0x18003831d  mov     rcx, [rbp+hKey]; hKey
0x180038321  call    cs:__imp_RegSetValueExW
0x180038327  mov     ebx, eax
0x180038329  test    eax, eax
0x18003832b  jz      short loc_180038358
0x18003832d  mov     rcx, cs:WPP_GLOBAL_Control
0x180038334  lea     rdx, WPP_GLOBAL_Control
0x18003833b  cmp     rcx, rdx
0x18003833e  jz      loc_1800383F6
0x180038344  test    byte ptr [rcx+1Ch], 10h
0x180038348  jz      loc_1800383F6
0x18003834e  mov     edx, 45h ; 'E'
0x180038353  jmp     loc_1800383E3
0x180038358  mov     r8, [rdi+40h]
0x18003835c  test    r8, r8
0x18003835f  jz      short loc_18003839B
0x180038361  mov     r9d, [rdi+48h]
0x180038365  lea     rdx, aIpsecownersref_0; "ipsecOwnersReference"
0x18003836c  mov     rcx, [rbp+hKey]; hKey
0x180038370  call    RegWriteMultiValuedString
0x180038375  mov     ebx, eax
0x180038377  test    eax, eax
0x180038379  jz      short loc_18003839B
0x18003837b  mov     rcx, cs:WPP_GLOBAL_Control
0x180038382  lea     rdx, WPP_GLOBAL_Control
0x180038389  cmp     rcx, rdx
0x18003838c  jz      short loc_1800383F6
0x18003838e  test    byte ptr [rcx+1Ch], 10h
0x180038392  jz      short loc_1800383F6
0x180038394  mov     edx, 46h ; 'F'
0x180038399  jmp     short loc_1800383E3
0x18003839b  mov     rcx, [rbp+hKey]; hKey
0x18003839f  lea     rax, [rdi+4Ch]
0x1800383a3  mov     [rsp+50h+samDesired], esi; cbData
0x1800383a7  lea     rdx, aWhenchanged_1; "whenChanged"
0x1800383ae  mov     r9d, esi; dwType
0x1800383b1  mov     [rsp+50h+lpData], rax; lpData
0x1800383b6  xor     r8d, r8d; Reserved
0x1800383b9  call    cs:__imp_RegSetValueExW
0x1800383bf  mov     ebx, eax
0x1800383c1  test    eax, eax
0x1800383c3  jz      short loc_1800383F6
0x1800383c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800383cc  lea     rdx, WPP_GLOBAL_Control
0x1800383d3  cmp     rcx, rdx
  ... truncated ...
```
