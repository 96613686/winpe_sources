# PersistPolicyObject

- ea: `0x180038424`
- end: `0x1800388ff`
- name: `PersistPolicyObject`
- size: `1243`
- prototype: `__int64 __fastcall(HKEY, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180038908`

## callees

- `0x18000e510`
- `0x180038424`
- `0x180038c44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800388e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800388e3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800385bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800385bc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003857a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800385f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038666`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800386d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038730`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038790`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800387fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003889d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038508`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003857a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800385f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038666`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800386d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038730`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180038790`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800387fb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003889d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038470`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038470`

## pseudocode

```c
__int64 __fastcall PersistPolicyObject(HKEY a1, __int64 a2)
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
  const BYTE *v19; // rcx
  DWORD v21; // [rsp+88h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+40h] BYREF

  v3 = *(const WCHAR **)a2;
  hKey = 0;
  v21 = 0;
  v4 = RegCreateKeyExW(a1, v3, 0, 0, 0, 0xF003Fu, 0, &hKey, &v21);
  v5 = v4;
  if ( v4 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 22;
LABEL_66:
      v8 = v4;
LABEL_67:
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
      v7 = 23;
      v8 = 1359;
      goto LABEL_67;
    }
    v4 = RegSetValueExW(hKey, L"className", 0, 1u, L"ipsecPolicy", 0x18u);
    v5 = v4;
    if ( !v4 )
    {
      lpData = *(const BYTE **)(a2 + 136);
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
            v7 = 25;
            goto LABEL_66;
          }
          goto LABEL_68;
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
          v7 = 26;
          goto LABEL_66;
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
            v7 = 27;
            goto LABEL_66;
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
              v7 = 28;
              goto LABEL_66;
            }
          }
          else
          {
LABEL_42:
            v4 = RegSetValueExW(hKey, L"ipsecDataType", 0, 4u, (const BYTE *)(a2 + 24), 4u);
            v5 = v4;
            if ( v4 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                v7 = 29;
                goto LABEL_66;
              }
            }
            else
            {
              v18 = *(const BYTE **)(a2 + 32);
              if ( v18 && (v4 = RegSetValueExW(hKey, L"ipsecData", 0, 3u, v18, *(_DWORD *)(a2 + 40)), (v5 = v4) != 0) )
              {
                v6 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                {
                  v7 = 30;
                  goto LABEL_66;
                }
              }
              else
              {
                v19 = *(const BYTE **)(a2 + 48);
                if ( !v19 )
                  goto LABEL_73;
                do
                  ++v10;
                while ( *(_WORD *)&v19[2 * v10] );
                v4 = RegSetValueExW(hKey, L"ipsecISAKMPReference", 0, 1u, v19, 2 * v10 + 2);
                v5 = v4;
                if ( v4 )
                {
                  v6 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                  {
                    v7 = 31;
                    goto LABEL_66;
                  }
                }
                else
                {
LABEL_73:
                  if ( *(_QWORD *)(a2 + 64)
                    && (v4 = RegWriteMultiValuedString(hKey, L"ipsecNFAReference"), (v5 = v4) != 0) )
                  {
                    v6 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      v7 = 32;
                      goto LABEL_66;
                    }
                  }
                  else
                  {
                    v4 = RegSetValueExW(hKey, L"whenChanged", 0, 4u, (const BYTE *)(a2 + 128), 4u);
                    v5 = v4;
                    if ( v4 )
                    {
                      v6 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                      {
                        v7 = 33;
                        goto LABEL_66;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
      goto LABEL_68;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = 24;
      goto LABEL_66;
    }
  }
LABEL_68:
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180038424  mov     r11, rsp
0x180038427  mov     [r11+8], rbx
0x18003842b  push    rbp
0x18003842c  push    rsi
0x18003842d  push    rdi
0x18003842e  push    r12
0x180038430  push    r14
0x180038432  mov     rbp, rsp
0x180038435  sub     rsp, 50h
0x180038439  xor     r14d, r14d
0x18003843c  lea     rax, [rbp+arg_8]
0x180038440  mov     [r11-38h], rax
0x180038444  mov     rdi, rdx
0x180038447  mov     rdx, [rdx]; lpSubKey
0x18003844a  lea     rax, [rbp+hKey]
0x18003844e  mov     [r11-40h], rax
0x180038452  xor     r9d, r9d; lpClass
0x180038455  mov     [r11-48h], r14
0x180038459  xor     r8d, r8d; Reserved
0x18003845c  mov     [rsp+50h+samDesired], 0F003Fh; samDesired
0x180038464  mov     [r11-58h], r14d
0x180038468  mov     [rbp+hKey], r14
0x18003846c  mov     [rbp+arg_8], r14d
0x180038470  call    cs:__imp_RegCreateKeyExW
0x180038476  mov     ebx, eax
0x180038478  test    eax, eax
0x18003847a  jz      short loc_1800384A6
0x18003847c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038483  lea     rdx, WPP_GLOBAL_Control
0x18003848a  cmp     rcx, rdx
0x18003848d  jz      loc_1800388DA
0x180038493  test    byte ptr [rcx+1Ch], 10h
0x180038497  jz      loc_1800388DA
0x18003849d  lea     edx, [r14+16h]
0x1800384a1  jmp     loc_1800388C7
0x1800384a6  mov     rcx, [rbp+hKey]; hKey
0x1800384aa  test    rcx, rcx
0x1800384ad  jnz     short loc_1800384E2
0x1800384af  mov     ebx, 54Fh
0x1800384b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800384bb  lea     rdx, WPP_GLOBAL_Control
0x1800384c2  cmp     rcx, rdx
0x1800384c5  jz      loc_1800388E9
0x1800384cb  test    byte ptr [rcx+1Ch], 10h
0x1800384cf  jz      loc_1800388E9
0x1800384d5  mov     edx, 17h
0x1800384da  mov     r9d, ebx
0x1800384dd  jmp     loc_1800388CA
0x1800384e2  mov     esi, 18h
0x1800384e7  lea     rax, aIpsecpolicy; "ipsecPolicy"
0x1800384ee  mov     [rsp+50h+samDesired], esi; cbData
0x1800384f2  lea     rdx, aClassname; "className"
0x1800384f9  xor     r8d, r8d; Reserved
0x1800384fc  mov     [rsp+50h+lpData], rax; lpData
0x180038501  lea     r12d, [rsi-17h]
0x180038505  mov     r9d, r12d; dwType
0x180038508  call    cs:__imp_RegSetValueExW
0x18003850e  mov     ebx, eax
0x180038510  test    eax, eax
0x180038512  jz      short loc_18003853C
0x180038514  mov     rcx, cs:WPP_GLOBAL_Control
0x18003851b  lea     rdx, WPP_GLOBAL_Control
0x180038522  cmp     rcx, rdx
0x180038525  jz      loc_1800388DA
0x18003852b  test    byte ptr [rcx+1Ch], 10h
0x18003852f  jz      loc_1800388DA
0x180038535  mov     edx, esi
0x180038537  jmp     loc_1800388C7
0x18003853c  mov     rcx, [rdi+88h]
0x180038543  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038547  test    rcx, rcx
0x18003854a  jz      short loc_1800385B1
0x18003854c  mov     rax, rsi
0x18003854f  inc     rax
0x180038552  cmp     [rcx+rax*2], r14w
0x180038557  jnz     short loc_18003854F
0x180038559  lea     eax, ds:2[rax*2]
0x180038560  mov     r9d, r12d; dwType
0x180038563  mov     [rsp+50h+samDesired], eax; cbData
0x180038567  lea     rdx, aDescription_0; "description"
0x18003856e  mov     [rsp+50h+lpData], rcx; lpData
0x180038573  xor     r8d, r8d; Reserved
0x180038576  mov     rcx, [rbp+hKey]; hKey
0x18003857a  call    cs:__imp_RegSetValueExW
0x180038580  mov     ebx, eax
0x180038582  test    eax, eax
0x180038584  jz      short loc_1800385C2
0x180038586  mov     rcx, cs:WPP_GLOBAL_Control
0x18003858d  lea     rdx, WPP_GLOBAL_Control
0x180038594  cmp     rcx, rdx
0x180038597  jz      loc_1800388DA
0x18003859d  test    byte ptr [rcx+1Ch], 10h
0x1800385a1  jz      loc_1800388DA
0x1800385a7  mov     edx, 19h
0x1800385ac  jmp     loc_1800388C7
0x1800385b1  mov     rcx, [rbp+hKey]; hKey
0x1800385b5  lea     rdx, aDescription_0; "description"
0x1800385bc  call    cs:__imp_RegDeleteValueW
0x1800385c2  mov     rcx, [rdi]
0x1800385c5  test    rcx, rcx
0x1800385c8  jz      short loc_18003862F
0x1800385ca  mov     rax, rsi
0x1800385cd  inc     rax
0x1800385d0  cmp     [rcx+rax*2], r14w
0x1800385d5  jnz     short loc_1800385CD
0x1800385d7  lea     eax, ds:2[rax*2]
0x1800385de  mov     r9d, r12d; dwType
0x1800385e1  mov     [rsp+50h+samDesired], eax; cbData
0x1800385e5  lea     rdx, aName; "name"
0x1800385ec  mov     [rsp+50h+lpData], rcx; lpData
0x1800385f1  xor     r8d, r8d; Reserved
0x1800385f4  mov     rcx, [rbp+hKey]; hKey
0x1800385f8  call    cs:__imp_RegSetValueExW
0x1800385fe  mov     ebx, eax
0x180038600  test    eax, eax
0x180038602  jz      short loc_18003862F
0x180038604  mov     rcx, cs:WPP_GLOBAL_Control
0x18003860b  lea     rdx, WPP_GLOBAL_Control
0x180038612  cmp     rcx, rdx
0x180038615  jz      loc_1800388DA
0x18003861b  test    byte ptr [rcx+1Ch], 10h
0x18003861f  jz      loc_1800388DA
0x180038625  mov     edx, 1Ah
0x18003862a  jmp     loc_1800388C7
0x18003862f  mov     rcx, [rdi+8]
0x180038633  test    rcx, rcx
0x180038636  jz      short loc_18003869D
0x180038638  mov     rax, rsi
0x18003863b  inc     rax
0x18003863e  cmp     [rcx+rax*2], r14w
0x180038643  jnz     short loc_18003863B
0x180038645  lea     eax, ds:2[rax*2]
0x18003864c  mov     r9d, r12d; dwType
0x18003864f  mov     [rsp+50h+samDesired], eax; cbData
0x180038653  lea     rdx, aIpsecname_0; "ipsecName"
0x18003865a  mov     [rsp+50h+lpData], rcx; lpData
0x18003865f  xor     r8d, r8d; Reserved
0x180038662  mov     rcx, [rbp+hKey]; hKey
0x180038666  call    cs:__imp_RegSetValueExW
0x18003866c  mov     ebx, eax
0x18003866e  test    eax, eax
0x180038670  jz      short loc_18003869D
0x180038672  mov     rcx, cs:WPP_GLOBAL_Control
0x180038679  lea     rdx, WPP_GLOBAL_Control
0x180038680  cmp     rcx, rdx
0x180038683  jz      loc_1800388DA
0x180038689  test    byte ptr [rcx+1Ch], 10h
0x18003868d  jz      loc_1800388DA
0x180038693  mov     edx, 1Bh
0x180038698  jmp     loc_1800388C7
0x18003869d  mov     rcx, [rdi+10h]
0x1800386a1  test    rcx, rcx
0x1800386a4  jz      short loc_18003870B
0x1800386a6  mov     rax, rsi
0x1800386a9  inc     rax
0x1800386ac  cmp     [rcx+rax*2], r14w
0x1800386b1  jnz     short loc_1800386A9
0x1800386b3  lea     eax, ds:2[rax*2]
0x1800386ba  mov     r9d, r12d; dwType
0x1800386bd  mov     [rsp+50h+samDesired], eax; cbData
0x1800386c1  lea     rdx, aIpsecid_0; "ipsecID"
0x1800386c8  mov     [rsp+50h+lpData], rcx; lpData
0x1800386cd  xor     r8d, r8d; Reserved
0x1800386d0  mov     rcx, [rbp+hKey]; hKey
0x1800386d4  call    cs:__imp_RegSetValueExW
0x1800386da  mov     ebx, eax
0x1800386dc  test    eax, eax
0x1800386de  jz      short loc_18003870B
0x1800386e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800386e7  lea     rdx, WPP_GLOBAL_Control
0x1800386ee  cmp     rcx, rdx
0x1800386f1  jz      loc_1800388DA
0x1800386f7  test    byte ptr [rcx+1Ch], 10h
0x1800386fb  jz      loc_1800388DA
0x180038701  mov     edx, 1Ch
0x180038706  jmp     loc_1800388C7
0x18003870b  mov     rcx, [rbp+hKey]; hKey
0x18003870f  lea     rax, [rdi+18h]
0x180038713  mov     [rsp+50h+samDesired], 4; cbData
0x18003871b  lea     rdx, aIpsecdatatype_0; "ipsecDataType"
0x180038722  mov     r9d, 4; dwType
0x180038728  mov     [rsp+50h+lpData], rax; lpData
0x18003872d  xor     r8d, r8d; Reserved
0x180038730  call    cs:__imp_RegSetValueExW
0x180038736  mov     ebx, eax
0x180038738  test    eax, eax
0x18003873a  jz      short loc_180038767
0x18003873c  mov     rcx, cs:WPP_GLOBAL_Control
0x180038743  lea     rdx, WPP_GLOBAL_Control
0x18003874a  cmp     rcx, rdx
0x18003874d  jz      loc_1800388DA
0x180038753  test    byte ptr [rcx+1Ch], 10h
0x180038757  jz      loc_1800388DA
0x18003875d  mov     edx, 1Dh
0x180038762  jmp     loc_1800388C7
0x180038767  mov     rcx, [rdi+20h]
0x18003876b  test    rcx, rcx
0x18003876e  jz      short loc_1800387C7
0x180038770  mov     eax, [rdi+28h]
0x180038773  lea     rdx, aIpsecdata_0; "ipsecData"
0x18003877a  mov     [rsp+50h+samDesired], eax; cbData
0x18003877e  mov     r9d, 3; dwType
0x180038784  mov     [rsp+50h+lpData], rcx; lpData
0x180038789  xor     r8d, r8d; Reserved
0x18003878c  mov     rcx, [rbp+hKey]; hKey
0x180038790  call    cs:__imp_RegSetValueExW
0x180038796  mov     ebx, eax
0x180038798  test    eax, eax
0x18003879a  jz      short loc_1800387C7
0x18003879c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800387a3  lea     rdx, WPP_GLOBAL_Control
0x1800387aa  cmp     rcx, rdx
0x1800387ad  jz      loc_1800388DA
0x1800387b3  test    byte ptr [rcx+1Ch], 10h
0x1800387b7  jz      loc_1800388DA
0x1800387bd  mov     edx, 1Eh
0x1800387c2  jmp     loc_1800388C7
0x1800387c7  mov     rcx, [rdi+30h]
0x1800387cb  test    rcx, rcx
0x1800387ce  jz      short loc_180038832
0x1800387d0  inc     rsi
0x1800387d3  cmp     [rcx+rsi*2], r14w
0x1800387d8  jnz     short loc_1800387D0
0x1800387da  lea     eax, ds:2[rsi*2]
0x1800387e1  mov     r9d, r12d; dwType
0x1800387e4  mov     [rsp+50h+samDesired], eax; cbData
0x1800387e8  lea     rdx, aIpsecisakmpref_0; "ipsecISAKMPReference"
0x1800387ef  mov     [rsp+50h+lpData], rcx; lpData
0x1800387f4  xor     r8d, r8d; Reserved
0x1800387f7  mov     rcx, [rbp+hKey]; hKey
0x1800387fb  call    cs:__imp_RegSetValueExW
0x180038801  mov     ebx, eax
0x180038803  test    eax, eax
0x180038805  jz      short loc_180038832
0x180038807  mov     rcx, cs:WPP_GLOBAL_Control
0x18003880e  lea     rdx, WPP_GLOBAL_Control
0x180038815  cmp     rcx, rdx
0x180038818  jz      loc_1800388DA
0x18003881e  test    byte ptr [rcx+1Ch], 10h
0x180038822  jz      loc_1800388DA
0x180038828  mov     edx, 1Fh
0x18003882d  jmp     loc_1800388C7
0x180038832  mov     r8, [rdi+40h]
0x180038836  test    r8, r8
0x180038839  jz      short loc_180038875
0x18003883b  mov     r9d, [rdi+38h]
0x18003883f  lea     rdx, aIpsecnfarefere_0; "ipsecNFAReference"
0x180038846  mov     rcx, [rbp+hKey]; hKey
0x18003884a  call    RegWriteMultiValuedString
0x18003884f  mov     ebx, eax
0x180038851  test    eax, eax
0x180038853  jz      short loc_180038875
0x180038855  mov     rcx, cs:WPP_GLOBAL_Control
0x18003885c  lea     rdx, WPP_GLOBAL_Control
0x180038863  cmp     rcx, rdx
0x180038866  jz      short loc_1800388DA
0x180038868  test    byte ptr [rcx+1Ch], 10h
0x18003886c  jz      short loc_1800388DA
0x18003886e  mov     edx, 20h ; ' '
0x180038873  jmp     short loc_1800388C7
0x180038875  mov     rcx, [rbp+hKey]; hKey
0x180038879  lea     rax, [rdi+80h]
0x180038880  mov     [rsp+50h+samDesired], 4; cbData
0x180038888  lea     rdx, aWhenchanged_1; "whenChanged"
0x18003888f  mov     r9d, 4; dwType
0x180038895  mov     [rsp+50h+lpData], rax; lpData
0x18003889a  xor     r8d, r8d; Reserved
0x18003889d  call    cs:__imp_RegSetValueExW
0x1800388a3  mov     ebx, eax
0x1800388a5  test    eax, eax
0x1800388a7  jz      short loc_1800388DA
0x1800388a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800388b0  lea     rdx, WPP_GLOBAL_Control
0x1800388b7  cmp     rcx, rdx
0x1800388ba  jz      short loc_1800388DA
0x1800388bc  test    byte ptr [rcx+1Ch], 10h
0x1800388c0  jz      short loc_1800388DA
0x1800388c2  mov     edx, 21h ; '!'
0x1800388c7  mov     r9d, eax
0x1800388ca  mov     rcx, [rcx+10h]
0x1800388ce  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x1800388d5  call    WPP_SF_d
0x1800388da  mov     rcx, [rbp+hKey]; hKey
0x1800388de  test    rcx, rcx
0x1800388e1  jz      short loc_1800388E9
0x1800388e3  call    cs:__imp_RegCloseKey
0x1800388e9  mov     eax, ebx
0x1800388eb  mov     rbx, [rsp+50h+arg_0]
0x1800388f3  add     rsp, 50h
0x1800388f7  pop     r14
0x1800388f9  pop     r12
0x1800388fb  pop     rdi
0x1800388fc  pop     rsi
0x1800388fd  pop     rbp
0x1800388fe  retn
```
