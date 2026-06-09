# PersistISAKMPObject

- ea: `0x180037500`
- end: `0x1800378e9`
- name: `PersistISAKMPObject`
- size: `1001`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038908`

## callees

- `0x18000e510`
- `0x180037500`
- `0x180038c44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800378cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800378cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800375e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037657`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800376c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037736`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037790`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800377ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037843`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800375e3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037657`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800376c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037736`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037790`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800377ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180037843`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003754d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003754d`

## pseudocode

```c
__int64 __fastcall PersistISAKMPObject(HKEY a1, __int64 a2)
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
  const BYTE *v15; // rcx
  DWORD v17; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF

  v3 = *(const WCHAR **)a2;
  hKey = 0;
  v17 = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, &v17);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 72;
LABEL_51:
      v8 = v4;
LABEL_52:
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
      v7 = 73;
      v8 = 1359;
      goto LABEL_52;
    }
    v4 = RegSetValueExW(hKey, L"className", 0, 1u, L"ipsecISAKMPPolicy", 0x24u);
    v5 = v4;
    if ( v4 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v7 = 74;
        goto LABEL_51;
      }
    }
    else
    {
      lpData = *(const BYTE **)a2;
      v10 = -1;
      if ( !*(_QWORD *)a2 )
        goto LABEL_20;
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)&lpData[2 * v11] );
      v4 = RegSetValueExW(hKey, L"name", 0, 1u, lpData, 2 * v11 + 2);
      v5 = v4;
      if ( v4 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          v7 = 75;
          goto LABEL_51;
        }
      }
      else
      {
LABEL_20:
        v12 = *(const BYTE **)(a2 + 8);
        if ( !v12 )
          goto LABEL_27;
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&v12[2 * v13] );
        v4 = RegSetValueExW(hKey, L"ipsecName", 0, 1u, v12, 2 * v13 + 2);
        v5 = v4;
        if ( v4 )
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            v7 = 76;
            goto LABEL_51;
          }
        }
        else
        {
LABEL_27:
          v14 = *(const BYTE **)(a2 + 16);
          if ( !v14 )
            goto LABEL_33;
          do
            ++v10;
          while ( *(_WORD *)&v14[2 * v10] );
          v4 = RegSetValueExW(hKey, L"ipsecID", 0, 1u, v14, 2 * v10 + 2);
          v5 = v4;
          if ( v4 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
            {
              v7 = 77;
              goto LABEL_51;
            }
          }
          else
          {
LABEL_33:
            v4 = RegSetValueExW(hKey, L"ipsecDataType", 0, 4u, (const BYTE *)(a2 + 24), 4u);
            v5 = v4;
            if ( v4 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v7 = 78;
                goto LABEL_51;
              }
            }
            else
            {
              v15 = *(const BYTE **)(a2 + 32);
              if ( v15 && (v4 = RegSetValueExW(hKey, L"ipsecData", 0, 3u, v15, *(_DWORD *)(a2 + 40)), (v5 = v4) != 0) )
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v7 = 79;
                  goto LABEL_51;
                }
              }
              else
              {
                v4 = RegSetValueExW(hKey, L"whenChanged", 0, 4u, (const BYTE *)(a2 + 60), 4u);
                v5 = v4;
                if ( v4 )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v7 = 80;
                    goto LABEL_51;
                  }
                }
                else if ( *(_QWORD *)(a2 + 48) )
                {
                  v4 = RegWriteMultiValuedString(hKey, L"ipsecOwnersReference");
                  v5 = v4;
                  if ( v4 )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v7 = 81;
                      goto LABEL_51;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180037500  mov     r11, rsp
0x180037503  mov     [r11+8], rbx
0x180037507  mov     [r11+20h], rsi
0x18003750b  push    rbp
0x18003750c  push    rdi
0x18003750d  push    r14
0x18003750f  mov     rbp, rsp
0x180037512  sub     rsp, 50h
0x180037516  xor     r14d, r14d
0x180037519  lea     rax, [rbp+arg_8]
0x18003751d  mov     [r11-28h], rax
0x180037521  mov     rdi, rdx
0x180037524  mov     rdx, [rdx]; lpSubKey
0x180037527  lea     rax, [rbp+hKey]
0x18003752b  mov     [r11-30h], rax
0x18003752f  xor     r9d, r9d; lpClass
0x180037532  mov     [r11-38h], r14
0x180037536  xor     r8d, r8d; Reserved
0x180037539  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180037541  mov     [r11-48h], r14d
0x180037545  mov     [rbp+hKey], r14
0x180037549  mov     [rbp+arg_8], r14d
0x18003754d  call    cs:__imp_RegCreateKeyExW
0x180037553  mov     ebx, eax
0x180037555  test    eax, eax
0x180037557  jz      short loc_180037583
0x180037559  mov     rcx, cs:WPP_GLOBAL_Control
0x180037560  lea     rdx, WPP_GLOBAL_Control
0x180037567  cmp     rcx, rdx
0x18003756a  jz      loc_1800378C3
0x180037570  test    byte ptr [rcx+1Ch], 10h
0x180037574  jz      loc_1800378C3
0x18003757a  lea     edx, [r14+48h]
0x18003757e  jmp     loc_1800378B0
0x180037583  mov     rcx, [rbp+hKey]; hKey
0x180037587  test    rcx, rcx
0x18003758a  jnz     short loc_1800375BF
0x18003758c  mov     ebx, 54Fh
0x180037591  mov     rcx, cs:WPP_GLOBAL_Control
0x180037598  lea     rdx, WPP_GLOBAL_Control
0x18003759f  cmp     rcx, rdx
0x1800375a2  jz      loc_1800378D2
0x1800375a8  test    byte ptr [rcx+1Ch], 10h
0x1800375ac  jz      loc_1800378D2
0x1800375b2  mov     edx, 49h ; 'I'
0x1800375b7  mov     r9d, ebx
0x1800375ba  jmp     loc_1800378B3
0x1800375bf  lea     rax, aIpsecisakmppol; "ipsecISAKMPPolicy"
0x1800375c6  mov     [rsp+50h+samDesired], 24h ; '$'; cbData
0x1800375ce  mov     r9d, 1; dwType
0x1800375d4  mov     [rsp+50h+lpData], rax; lpData
0x1800375d9  xor     r8d, r8d; Reserved
0x1800375dc  lea     rdx, aClassname; "className"
0x1800375e3  call    cs:__imp_RegSetValueExW
0x1800375e9  mov     ebx, eax
0x1800375eb  test    eax, eax
0x1800375ed  jz      short loc_18003761A
0x1800375ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800375f6  lea     rdx, WPP_GLOBAL_Control
0x1800375fd  cmp     rcx, rdx
0x180037600  jz      loc_1800378C3
0x180037606  test    byte ptr [rcx+1Ch], 10h
0x18003760a  jz      loc_1800378C3
0x180037610  mov     edx, 4Ah ; 'J'
0x180037615  jmp     loc_1800378B0
0x18003761a  mov     rcx, [rdi]
0x18003761d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180037621  test    rcx, rcx
0x180037624  jz      short loc_18003768E
0x180037626  mov     rax, rsi
0x180037629  inc     rax
0x18003762c  cmp     [rcx+rax*2], r14w
0x180037631  jnz     short loc_180037629
0x180037633  lea     eax, ds:2[rax*2]
0x18003763a  mov     r9d, 1; dwType
0x180037640  mov     [rsp+50h+samDesired], eax; cbData
0x180037644  lea     rdx, aName; "name"
0x18003764b  mov     [rsp+50h+lpData], rcx; lpData
0x180037650  xor     r8d, r8d; Reserved
0x180037653  mov     rcx, [rbp+hKey]; hKey
0x180037657  call    cs:__imp_RegSetValueExW
0x18003765d  mov     ebx, eax
0x18003765f  test    eax, eax
0x180037661  jz      short loc_18003768E
0x180037663  mov     rcx, cs:WPP_GLOBAL_Control
0x18003766a  lea     rdx, WPP_GLOBAL_Control
0x180037671  cmp     rcx, rdx
0x180037674  jz      loc_1800378C3
0x18003767a  test    byte ptr [rcx+1Ch], 10h
0x18003767e  jz      loc_1800378C3
0x180037684  mov     edx, 4Bh ; 'K'
0x180037689  jmp     loc_1800378B0
0x18003768e  mov     rcx, [rdi+8]
0x180037692  test    rcx, rcx
0x180037695  jz      short loc_1800376FF
0x180037697  mov     rax, rsi
0x18003769a  inc     rax
0x18003769d  cmp     [rcx+rax*2], r14w
0x1800376a2  jnz     short loc_18003769A
0x1800376a4  lea     eax, ds:2[rax*2]
0x1800376ab  mov     r9d, 1; dwType
0x1800376b1  mov     [rsp+50h+samDesired], eax; cbData
0x1800376b5  lea     rdx, aIpsecname_0; "ipsecName"
0x1800376bc  mov     [rsp+50h+lpData], rcx; lpData
0x1800376c1  xor     r8d, r8d; Reserved
0x1800376c4  mov     rcx, [rbp+hKey]; hKey
0x1800376c8  call    cs:__imp_RegSetValueExW
0x1800376ce  mov     ebx, eax
0x1800376d0  test    eax, eax
0x1800376d2  jz      short loc_1800376FF
0x1800376d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800376db  lea     rdx, WPP_GLOBAL_Control
0x1800376e2  cmp     rcx, rdx
0x1800376e5  jz      loc_1800378C3
0x1800376eb  test    byte ptr [rcx+1Ch], 10h
0x1800376ef  jz      loc_1800378C3
0x1800376f5  mov     edx, 4Ch ; 'L'
0x1800376fa  jmp     loc_1800378B0
0x1800376ff  mov     rcx, [rdi+10h]
0x180037703  test    rcx, rcx
0x180037706  jz      short loc_18003776D
0x180037708  inc     rsi
0x18003770b  cmp     [rcx+rsi*2], r14w
0x180037710  jnz     short loc_180037708
0x180037712  lea     eax, ds:2[rsi*2]
0x180037719  mov     r9d, 1; dwType
0x18003771f  mov     [rsp+50h+samDesired], eax; cbData
0x180037723  lea     rdx, aIpsecid_0; "ipsecID"
0x18003772a  mov     [rsp+50h+lpData], rcx; lpData
0x18003772f  xor     r8d, r8d; Reserved
0x180037732  mov     rcx, [rbp+hKey]; hKey
0x180037736  call    cs:__imp_RegSetValueExW
0x18003773c  mov     ebx, eax
0x18003773e  test    eax, eax
0x180037740  jz      short loc_18003776D
0x180037742  mov     rcx, cs:WPP_GLOBAL_Control
0x180037749  lea     rdx, WPP_GLOBAL_Control
0x180037750  cmp     rcx, rdx
0x180037753  jz      loc_1800378C3
0x180037759  test    byte ptr [rcx+1Ch], 10h
0x18003775d  jz      loc_1800378C3
0x180037763  mov     edx, 4Dh ; 'M'
0x180037768  jmp     loc_1800378B0
0x18003776d  mov     rcx, [rbp+hKey]; hKey
0x180037771  lea     rax, [rdi+18h]
0x180037775  mov     esi, 4
0x18003777a  lea     rdx, aIpsecdatatype_0; "ipsecDataType"
0x180037781  mov     [rsp+50h+samDesired], esi; cbData
0x180037785  mov     r9d, esi; dwType
0x180037788  xor     r8d, r8d; Reserved
0x18003778b  mov     [rsp+50h+lpData], rax; lpData
0x180037790  call    cs:__imp_RegSetValueExW
0x180037796  mov     ebx, eax
0x180037798  test    eax, eax
0x18003779a  jz      short loc_1800377C5
0x18003779c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800377a3  lea     rdx, WPP_GLOBAL_Control
0x1800377aa  cmp     rcx, rdx
0x1800377ad  jz      loc_1800378C3
0x1800377b3  test    byte ptr [rcx+1Ch], 10h
0x1800377b7  jz      loc_1800378C3
0x1800377bd  lea     edx, [rsi+4Ah]
0x1800377c0  jmp     loc_1800378B0
0x1800377c5  mov     rcx, [rdi+20h]
0x1800377c9  test    rcx, rcx
0x1800377cc  jz      short loc_180037825
0x1800377ce  mov     eax, [rdi+28h]
0x1800377d1  lea     rdx, aIpsecdata_0; "ipsecData"
0x1800377d8  mov     [rsp+50h+samDesired], eax; cbData
0x1800377dc  mov     r9d, 3; dwType
0x1800377e2  mov     [rsp+50h+lpData], rcx; lpData
0x1800377e7  xor     r8d, r8d; Reserved
0x1800377ea  mov     rcx, [rbp+hKey]; hKey
0x1800377ee  call    cs:__imp_RegSetValueExW
0x1800377f4  mov     ebx, eax
0x1800377f6  test    eax, eax
0x1800377f8  jz      short loc_180037825
0x1800377fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180037801  lea     rdx, WPP_GLOBAL_Control
0x180037808  cmp     rcx, rdx
0x18003780b  jz      loc_1800378C3
0x180037811  test    byte ptr [rcx+1Ch], 10h
0x180037815  jz      loc_1800378C3
0x18003781b  mov     edx, 4Fh ; 'O'
0x180037820  jmp     loc_1800378B0
0x180037825  mov     rcx, [rbp+hKey]; hKey
0x180037829  lea     rax, [rdi+3Ch]
0x18003782d  mov     [rsp+50h+samDesired], esi; cbData
0x180037831  lea     rdx, aWhenchanged_1; "whenChanged"
0x180037838  mov     r9d, esi; dwType
0x18003783b  mov     [rsp+50h+lpData], rax; lpData
0x180037840  xor     r8d, r8d; Reserved
0x180037843  call    cs:__imp_RegSetValueExW
0x180037849  mov     ebx, eax
0x18003784b  test    eax, eax
0x18003784d  jz      short loc_18003786F
0x18003784f  mov     rcx, cs:WPP_GLOBAL_Control
0x180037856  lea     rdx, WPP_GLOBAL_Control
0x18003785d  cmp     rcx, rdx
0x180037860  jz      short loc_1800378C3
0x180037862  test    byte ptr [rcx+1Ch], 10h
0x180037866  jz      short loc_1800378C3
0x180037868  mov     edx, 50h ; 'P'
0x18003786d  jmp     short loc_1800378B0
0x18003786f  mov     r8, [rdi+30h]
0x180037873  test    r8, r8
0x180037876  jz      short loc_1800378C3
0x180037878  mov     r9d, [rdi+38h]
0x18003787c  lea     rdx, aIpsecownersref_0; "ipsecOwnersReference"
0x180037883  mov     rcx, [rbp+hKey]; hKey
0x180037887  call    RegWriteMultiValuedString
0x18003788c  mov     ebx, eax
0x18003788e  test    eax, eax
0x180037890  jz      short loc_1800378C3
0x180037892  mov     rcx, cs:WPP_GLOBAL_Control
0x180037899  lea     rdx, WPP_GLOBAL_Control
0x1800378a0  cmp     rcx, rdx
0x1800378a3  jz      short loc_1800378C3
0x1800378a5  test    byte ptr [rcx+1Ch], 10h
0x1800378a9  jz      short loc_1800378C3
0x1800378ab  mov     edx, 51h ; 'Q'
0x1800378b0  mov     r9d, eax
0x1800378b3  mov     rcx, [rcx+10h]
0x1800378b7  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x1800378be  call    WPP_SF_d
0x1800378c3  mov     rcx, [rbp+hKey]; hKey
0x1800378c7  test    rcx, rcx
0x1800378ca  jz      short loc_1800378D2
0x1800378cc  call    cs:__imp_RegCloseKey
0x1800378d2  lea     r11, [rsp+50h+var_s0]
0x1800378d7  mov     eax, ebx
0x1800378d9  mov     rbx, [r11+20h]
0x1800378dd  mov     rsi, [r11+38h]
0x1800378e1  mov     rsp, r11
0x1800378e4  pop     r14
0x1800378e6  pop     rdi
0x1800378e7  pop     rbp
0x1800378e8  retn
```
