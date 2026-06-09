# RegInsertPhoneList

- ea: `0x1800dc1cc`
- end: `0x1800dc6ea`
- name: `RegInsertPhoneList`
- size: `1310`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800da7ec`

## callees

- `0x18004e580`
- `0x18004e984`
- `0x1800dbed8`
- `0x1800dbefc`
- `0x1800dc1cc`
- `0x1800dc7dc`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dc302`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800dc302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc68c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dc68c`
- `ntdll!sprintf` at `0x1800dc2ce`
- `ntdll!sprintf` at `0x1800dc2ce`

## string_xrefs

- `0x1800dc3ab`: `Comment`

## pseudocode

```c
__int64 __fastcall RegInsertPhoneList(HKEY hKey, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rcx
  __int64 *v6; // rsi
  unsigned int v8; // ebx
  int v9; // r14d
  __int64 v10; // rsi
  __int64 v11; // rdi
  unsigned int v12; // eax
  unsigned int inserted; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  _BYTE *v20; // rcx
  __int64 v21; // rdx
  HKEY hKeya; // [rsp+50h] [rbp-20h] BYREF
  char Buffer[8]; // [rsp+58h] [rbp-18h] BYREF
  __int16 v24; // [rsp+60h] [rbp-10h]

  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids);
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(__int64 **)(a3 + 168);
  if ( v6 )
  {
    v8 = 0;
    hKeya = 0;
    v9 = 0;
    v10 = *v6;
    while ( 1 )
    {
      if ( !v10 )
        goto LABEL_83;
      v11 = *(_QWORD *)(v10 + 16);
      *(_QWORD *)Buffer = 0;
      v24 = 0;
      sprintf(Buffer, "%i", v9);
      v12 = RegCreateKeyExA(hKey, Buffer, 0, 0, 0, 0x20206u, 0, &hKeya, 0);
      v8 = v12;
      if ( v12 )
        break;
      inserted = RegInsertString(hKeya, "PhoneNumber", *(_QWORD *)(v11 + 16));
      v8 = inserted;
      if ( inserted )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, inserted);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 42;
LABEL_82:
        WPP_SF_d(*((_QWORD *)v20 + 2), v21, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v8);
        goto LABEL_83;
      }
      v14 = RegInsertString(hKeya, "AreaCode", *(_QWORD *)v11);
      v8 = v14;
      if ( v14 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v14);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 44;
        goto LABEL_82;
      }
      v15 = RegInsertLong(hKeya, "CountryCode", *(unsigned int *)(v11 + 8));
      v8 = v15;
      if ( v15 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v15);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 46;
        goto LABEL_82;
      }
      v16 = RegInsertLong(hKeya, "CountryID", *(unsigned int *)(v11 + 12));
      v8 = v16;
      if ( v16 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v16);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 48;
        goto LABEL_82;
      }
      v17 = RegInsertFlag(hKeya, "UseDialingRules", *(unsigned int *)(v11 + 24));
      v8 = v17;
      if ( v17 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v17);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 50;
        goto LABEL_82;
      }
      v18 = RegInsertString(hKeya, "Comment", *(_QWORD *)(v11 + 32));
      v8 = v18;
      if ( v18 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_83;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v18);
          v20 = WPP_GLOBAL_Control;
        }
        if ( v20 == (_BYTE *)&WPP_GLOBAL_Control || (v20[28] & 0x80) == 0 || v20[25] < 6u )
          goto LABEL_83;
        v21 = 52;
        goto LABEL_82;
      }
      v19 = RegInsertString(hKeya, "FriendlyName", *(_QWORD *)(v11 + 40));
      v8 = v19;
      if ( v19 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v19);
            v20 = WPP_GLOBAL_Control;
          }
          if ( v20 != (_BYTE *)&WPP_GLOBAL_Control && (v20[28] & 0x80) != 0 && v20[25] >= 6u )
          {
            v21 = 54;
            goto LABEL_82;
          }
        }
LABEL_83:
        RegCloseKey(hKeya);
        return v8;
      }
      v10 = *(_QWORD *)(v10 + 8);
      ++v9;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, v12);
    }
    return v8;
  }
  else
  {
    if ( v5 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v5 + 28) & 0x80) != 0 && *((_BYTE *)v5 + 25) >= 2u )
      {
        WPP_SF_d(v5[2], 38, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 87);
        v5 = WPP_GLOBAL_Control;
      }
      if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x80) != 0 && *((_BYTE *)v5 + 25) >= 6u )
        WPP_SF_d(v5[2], 39, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids, 87);
    }
    return 87;
  }
}

```

## disassembly

```asm
0x1800dc1cc  mov     [rsp-38h+arg_8], rbx
0x1800dc1d1  push    rbp
0x1800dc1d2  push    rsi
0x1800dc1d3  push    rdi
0x1800dc1d4  push    r12
0x1800dc1d6  push    r13
0x1800dc1d8  push    r14
0x1800dc1da  push    r15
0x1800dc1dc  mov     rbp, rsp
0x1800dc1df  sub     rsp, 70h
0x1800dc1e3  mov     rax, cs:__security_cookie
0x1800dc1ea  xor     rax, rsp
0x1800dc1ed  mov     [rbp+var_8], rax
0x1800dc1f1  mov     rsi, r8
0x1800dc1f4  mov     r15, rcx
0x1800dc1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc1fe  lea     r13, WPP_GLOBAL_Control
0x1800dc205  lea     rbx, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc20c  mov     r12b, 80h
0x1800dc20f  cmp     rcx, r13
0x1800dc212  jz      short loc_1800DC238
0x1800dc214  test    [rcx+1Ch], r12b
0x1800dc218  jz      short loc_1800DC238
0x1800dc21a  cmp     byte ptr [rcx+19h], 6
0x1800dc21e  jb      short loc_1800DC238
0x1800dc220  mov     rcx, [rcx+10h]
0x1800dc224  mov     edx, 25h ; '%'
0x1800dc229  mov     r8, rbx
0x1800dc22c  call    WPP_SF_
0x1800dc231  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc238  mov     rsi, [rsi+0A8h]
0x1800dc23f  test    rsi, rsi
0x1800dc242  jnz     short loc_1800DC29D
0x1800dc244  lea     edi, [rsi+57h]
0x1800dc247  cmp     rcx, r13
0x1800dc24a  jz      short loc_1800DC296
0x1800dc24c  test    [rcx+1Ch], r12b
0x1800dc250  jz      short loc_1800DC271
0x1800dc252  cmp     byte ptr [rcx+19h], 2
0x1800dc256  jb      short loc_1800DC271
0x1800dc258  mov     rcx, [rcx+10h]
0x1800dc25c  lea     edx, [rsi+26h]
0x1800dc25f  mov     r9d, edi
0x1800dc262  mov     r8, rbx
0x1800dc265  call    WPP_SF_d
0x1800dc26a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc271  cmp     rcx, r13
0x1800dc274  jz      short loc_1800DC296
0x1800dc276  test    [rcx+1Ch], r12b
0x1800dc27a  jz      short loc_1800DC296
0x1800dc27c  cmp     byte ptr [rcx+19h], 6
0x1800dc280  jb      short loc_1800DC296
0x1800dc282  mov     rcx, [rcx+10h]
0x1800dc286  mov     edx, 27h ; '''
0x1800dc28b  mov     r9d, edi
0x1800dc28e  mov     r8, rbx
0x1800dc291  call    WPP_SF_d
0x1800dc296  mov     eax, edi
0x1800dc298  jmp     loc_1800DC694
0x1800dc29d  xor     ebx, ebx
0x1800dc29f  mov     [rbp+hKey], rbx
0x1800dc2a3  xor     r14d, r14d
0x1800dc2a6  mov     rsi, [rsi]
0x1800dc2a9  test    rsi, rsi
0x1800dc2ac  jz      loc_1800DC688
0x1800dc2b2  mov     rdi, [rsi+10h]
0x1800dc2b6  lea     rdx, aI; "%i"
0x1800dc2bd  xor     eax, eax
0x1800dc2bf  lea     rcx, [rbp+Buffer]; Buffer
0x1800dc2c3  mov     r8d, r14d
0x1800dc2c6  mov     qword ptr [rbp+Buffer], rax
0x1800dc2ca  mov     [rbp+var_10], ax
0x1800dc2ce  call    cs:__imp_sprintf
0x1800dc2d4  xor     ecx, ecx
0x1800dc2d6  lea     rax, [rbp+hKey]
0x1800dc2da  mov     [rsp+70h+lpdwDisposition], rcx; lpdwDisposition
0x1800dc2df  lea     rdx, [rbp+Buffer]; lpSubKey
0x1800dc2e3  mov     [rsp+70h+phkResult], rax; phkResult
0x1800dc2e8  xor     r9d, r9d; lpClass
0x1800dc2eb  mov     [rsp+70h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800dc2f0  xor     r8d, r8d; Reserved
0x1800dc2f3  mov     [rsp+70h+samDesired], 20206h; samDesired
0x1800dc2fb  mov     [rsp+70h+dwOptions], ecx; dwOptions
0x1800dc2ff  mov     rcx, r15; hKey
0x1800dc302  call    cs:__imp_RegCreateKeyExA
0x1800dc308  mov     ebx, eax
0x1800dc30a  test    eax, eax
0x1800dc30c  jnz     loc_1800DC6B8
0x1800dc312  mov     r8, [rdi+10h]
0x1800dc316  lea     rdx, aPhonenumber_0; "PhoneNumber"
0x1800dc31d  mov     rcx, [rbp+hKey]
0x1800dc321  call    RegInsertString
0x1800dc326  mov     ebx, eax
0x1800dc328  test    eax, eax
0x1800dc32a  jnz     loc_1800DC628
0x1800dc330  mov     r8, [rdi]
0x1800dc333  lea     rdx, aAreacode; "AreaCode"
0x1800dc33a  mov     rcx, [rbp+hKey]
0x1800dc33e  call    RegInsertString
0x1800dc343  mov     ebx, eax
0x1800dc345  test    eax, eax
0x1800dc347  jnz     loc_1800DC5D5
0x1800dc34d  mov     r8d, [rdi+8]
0x1800dc351  lea     rdx, aCountrycode; "CountryCode"
0x1800dc358  mov     rcx, [rbp+hKey]
0x1800dc35c  call    RegInsertLong
0x1800dc361  mov     ebx, eax
0x1800dc363  test    eax, eax
0x1800dc365  jnz     loc_1800DC573
0x1800dc36b  mov     r8d, [rdi+0Ch]
0x1800dc36f  lea     rdx, aCountryid; "CountryID"
0x1800dc376  mov     rcx, [rbp+hKey]
0x1800dc37a  call    RegInsertLong
0x1800dc37f  mov     ebx, eax
0x1800dc381  test    eax, eax
0x1800dc383  jnz     loc_1800DC511
0x1800dc389  mov     r8d, [rdi+18h]
0x1800dc38d  lea     rdx, aUsedialingrule; "UseDialingRules"
0x1800dc394  mov     rcx, [rbp+hKey]
0x1800dc398  call    RegInsertFlag
0x1800dc39d  mov     ebx, eax
0x1800dc39f  test    eax, eax
0x1800dc3a1  jnz     loc_1800DC4AF
0x1800dc3a7  mov     r8, [rdi+20h]
0x1800dc3ab  lea     rdx, aComment; "Comment"
0x1800dc3b2  mov     rcx, [rbp+hKey]
0x1800dc3b6  call    RegInsertString
0x1800dc3bb  mov     ebx, eax
0x1800dc3bd  test    eax, eax
0x1800dc3bf  jnz     loc_1800DC44D
0x1800dc3c5  mov     r8, [rdi+28h]
0x1800dc3c9  lea     rdx, aFriendlyname; "FriendlyName"
0x1800dc3d0  mov     rcx, [rbp+hKey]
0x1800dc3d4  call    RegInsertString
0x1800dc3d9  mov     ebx, eax
0x1800dc3db  test    eax, eax
0x1800dc3dd  jnz     short loc_1800DC3EB
0x1800dc3df  mov     rsi, [rsi+8]
0x1800dc3e3  inc     r14d
0x1800dc3e6  jmp     loc_1800DC2A9
0x1800dc3eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc3f2  cmp     rcx, r13
0x1800dc3f5  jz      loc_1800DC688
0x1800dc3fb  test    [rcx+1Ch], r12b
0x1800dc3ff  jz      short loc_1800DC426
0x1800dc401  cmp     byte ptr [rcx+19h], 2
0x1800dc405  jb      short loc_1800DC426
0x1800dc407  mov     rcx, [rcx+10h]
0x1800dc40b  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc412  mov     edx, 35h ; '5'
0x1800dc417  mov     r9d, ebx
0x1800dc41a  call    WPP_SF_d
0x1800dc41f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc426  cmp     rcx, r13
0x1800dc429  jz      loc_1800DC688
0x1800dc42f  test    [rcx+1Ch], r12b
0x1800dc433  jz      loc_1800DC688
0x1800dc439  cmp     byte ptr [rcx+19h], 6
0x1800dc43d  jb      loc_1800DC688
0x1800dc443  mov     edx, 36h ; '6'
0x1800dc448  jmp     loc_1800DC675
0x1800dc44d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc454  cmp     rcx, r13
0x1800dc457  jz      loc_1800DC688
0x1800dc45d  test    [rcx+1Ch], r12b
0x1800dc461  jz      short loc_1800DC488
0x1800dc463  cmp     byte ptr [rcx+19h], 2
0x1800dc467  jb      short loc_1800DC488
0x1800dc469  mov     rcx, [rcx+10h]
0x1800dc46d  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc474  mov     edx, 33h ; '3'
0x1800dc479  mov     r9d, ebx
0x1800dc47c  call    WPP_SF_d
0x1800dc481  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc488  cmp     rcx, r13
0x1800dc48b  jz      loc_1800DC688
0x1800dc491  test    [rcx+1Ch], r12b
0x1800dc495  jz      loc_1800DC688
0x1800dc49b  cmp     byte ptr [rcx+19h], 6
0x1800dc49f  jb      loc_1800DC688
0x1800dc4a5  mov     edx, 34h ; '4'
0x1800dc4aa  jmp     loc_1800DC675
0x1800dc4af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc4b6  cmp     rcx, r13
0x1800dc4b9  jz      loc_1800DC688
0x1800dc4bf  test    [rcx+1Ch], r12b
0x1800dc4c3  jz      short loc_1800DC4EA
0x1800dc4c5  cmp     byte ptr [rcx+19h], 2
0x1800dc4c9  jb      short loc_1800DC4EA
0x1800dc4cb  mov     rcx, [rcx+10h]
0x1800dc4cf  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc4d6  mov     edx, 31h ; '1'
0x1800dc4db  mov     r9d, ebx
0x1800dc4de  call    WPP_SF_d
0x1800dc4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc4ea  cmp     rcx, r13
0x1800dc4ed  jz      loc_1800DC688
0x1800dc4f3  test    [rcx+1Ch], r12b
0x1800dc4f7  jz      loc_1800DC688
0x1800dc4fd  cmp     byte ptr [rcx+19h], 6
0x1800dc501  jb      loc_1800DC688
0x1800dc507  mov     edx, 32h ; '2'
0x1800dc50c  jmp     loc_1800DC675
0x1800dc511  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc518  cmp     rcx, r13
0x1800dc51b  jz      loc_1800DC688
0x1800dc521  test    [rcx+1Ch], r12b
0x1800dc525  jz      short loc_1800DC54C
0x1800dc527  cmp     byte ptr [rcx+19h], 2
0x1800dc52b  jb      short loc_1800DC54C
0x1800dc52d  mov     rcx, [rcx+10h]
0x1800dc531  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc538  mov     edx, 2Fh ; '/'
0x1800dc53d  mov     r9d, ebx
0x1800dc540  call    WPP_SF_d
0x1800dc545  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc54c  cmp     rcx, r13
0x1800dc54f  jz      loc_1800DC688
0x1800dc555  test    [rcx+1Ch], r12b
0x1800dc559  jz      loc_1800DC688
0x1800dc55f  cmp     byte ptr [rcx+19h], 6
0x1800dc563  jb      loc_1800DC688
0x1800dc569  mov     edx, 30h ; '0'
0x1800dc56e  jmp     loc_1800DC675
0x1800dc573  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc57a  cmp     rcx, r13
0x1800dc57d  jz      loc_1800DC688
0x1800dc583  test    [rcx+1Ch], r12b
0x1800dc587  jz      short loc_1800DC5AE
0x1800dc589  cmp     byte ptr [rcx+19h], 2
0x1800dc58d  jb      short loc_1800DC5AE
0x1800dc58f  mov     rcx, [rcx+10h]
0x1800dc593  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc59a  mov     edx, 2Dh ; '-'
0x1800dc59f  mov     r9d, ebx
0x1800dc5a2  call    WPP_SF_d
0x1800dc5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc5ae  cmp     rcx, r13
0x1800dc5b1  jz      loc_1800DC688
0x1800dc5b7  test    [rcx+1Ch], r12b
0x1800dc5bb  jz      loc_1800DC688
0x1800dc5c1  cmp     byte ptr [rcx+19h], 6
0x1800dc5c5  jb      loc_1800DC688
0x1800dc5cb  mov     edx, 2Eh ; '.'
0x1800dc5d0  jmp     loc_1800DC675
0x1800dc5d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc5dc  cmp     rcx, r13
0x1800dc5df  jz      loc_1800DC688
0x1800dc5e5  test    [rcx+1Ch], r12b
0x1800dc5e9  jz      short loc_1800DC610
0x1800dc5eb  cmp     byte ptr [rcx+19h], 2
0x1800dc5ef  jb      short loc_1800DC610
0x1800dc5f1  mov     rcx, [rcx+10h]
0x1800dc5f5  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc5fc  mov     edx, 2Bh ; '+'
0x1800dc601  mov     r9d, ebx
0x1800dc604  call    WPP_SF_d
0x1800dc609  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc610  cmp     rcx, r13
0x1800dc613  jz      short loc_1800DC688
0x1800dc615  test    [rcx+1Ch], r12b
0x1800dc619  jz      short loc_1800DC688
0x1800dc61b  cmp     byte ptr [rcx+19h], 6
0x1800dc61f  jb      short loc_1800DC688
0x1800dc621  mov     edx, 2Ch ; ','
0x1800dc626  jmp     short loc_1800DC675
0x1800dc628  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc62f  cmp     rcx, r13
0x1800dc632  jz      short loc_1800DC688
0x1800dc634  test    [rcx+1Ch], r12b
0x1800dc638  jz      short loc_1800DC65F
0x1800dc63a  cmp     byte ptr [rcx+19h], 2
0x1800dc63e  jb      short loc_1800DC65F
0x1800dc640  mov     rcx, [rcx+10h]
0x1800dc644  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc64b  mov     edx, 29h ; ')'
0x1800dc650  mov     r9d, ebx
0x1800dc653  call    WPP_SF_d
0x1800dc658  mov     rcx, cs:WPP_GLOBAL_Control
0x1800dc65f  cmp     rcx, r13
0x1800dc662  jz      short loc_1800DC688
0x1800dc664  test    [rcx+1Ch], r12b
0x1800dc668  jz      short loc_1800DC688
0x1800dc66a  cmp     byte ptr [rcx+19h], 6
0x1800dc66e  jb      short loc_1800DC688
0x1800dc670  mov     edx, 2Ah ; '*'
0x1800dc675  mov     rcx, [rcx+10h]
0x1800dc679  lea     r8, WPP_1a2c25c73f1633f64777688c8bb98551_Traceguids
0x1800dc680  mov     r9d, ebx
0x1800dc683  call    WPP_SF_d
0x1800dc688  mov     rcx, [rbp+hKey]; hKey
0x1800dc68c  call    cs:__imp_RegCloseKey
0x1800dc692  mov     eax, ebx
0x1800dc694  mov     rcx, [rbp+var_8]
0x1800dc698  xor     rcx, rsp; StackCookie
0x1800dc69b  call    __security_check_cookie
0x1800dc6a0  mov     rbx, [rsp+70h+arg_8]
0x1800dc6a8  add     rsp, 70h
0x1800dc6ac  pop     r15
0x1800dc6ae  pop     r14
  ... truncated ...
```
