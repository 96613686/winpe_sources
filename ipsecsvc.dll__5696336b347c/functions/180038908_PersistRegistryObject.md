# PersistRegistryObject

- ea: `0x180038908`
- end: `0x180038c3b`
- name: `PersistRegistryObject`
- size: `819`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180035714`

## callees

- `0x18000e510`
- `0x180037098`
- `0x180037500`
- `0x1800378f0`
- `0x180037ee0`
- `0x180038424`
- `0x180038908`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038c1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180038c1f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038969`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038969`

## string_xrefs

- `0x18003892a`: `SYSTEM\CurrentControlSet\Services\PolicyAgent\Parameters\Cache`

## pseudocode

```c
__int64 __fastcall PersistRegistryObject(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int v3; // edi
  _BYTE *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r14
  unsigned int v7; // ebp
  __int64 v8; // rsi
  HKEY v9; // r15
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r14
  unsigned int v13; // ebp
  __int64 v14; // rsi
  HKEY v15; // r15
  unsigned int v16; // eax
  __int64 v17; // r14
  unsigned int v18; // ebp
  __int64 v19; // rsi
  HKEY v20; // r15
  unsigned int v21; // eax
  __int64 v22; // r14
  unsigned int v23; // ebp
  __int64 v24; // rsi
  HKEY v25; // r15
  unsigned int v26; // eax
  DWORD v28; // [rsp+88h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+18h] BYREF

  hKey = 0;
  v28 = 0;
  v2 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\PolicyAgent\\Parameters\\Cache",
         0,
         0,
         0,
         0xF003Fu,
         0,
         &hKey,
         &v28);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_56;
    v5 = 12;
    goto LABEL_54;
  }
  v6 = *(_QWORD *)(a1 + 88);
  if ( v6 )
  {
    v7 = *(_DWORD *)(a1 + 80);
    v8 = 0;
    v9 = hKey;
    while ( (unsigned int)v8 < v7 )
    {
      v10 = PersistFilterObject(v9, *(_QWORD *)(v6 + 8 * v8));
      v3 = v10;
      if ( v10 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          goto LABEL_56;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v10);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || (v4[28] & 0x10) == 0 )
          goto LABEL_56;
        v5 = 13;
LABEL_16:
        v11 = v3;
        goto LABEL_55;
      }
      v8 = (unsigned int)(v8 + 1);
    }
  }
  v12 = *(_QWORD *)(a1 + 104);
  if ( v12 )
  {
    v13 = *(_DWORD *)(a1 + 96);
    v14 = 0;
    v15 = hKey;
    while ( (unsigned int)v14 < v13 )
    {
      v16 = PersistNegPolObject(v15, *(_QWORD *)(v12 + 8 * v14));
      v3 = v16;
      if ( v16 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v16);
            v4 = WPP_GLOBAL_Control;
          }
          if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 0x10) != 0 )
          {
            v5 = 14;
            goto LABEL_16;
          }
        }
        goto LABEL_56;
      }
      v14 = (unsigned int)(v14 + 1);
    }
  }
  v17 = *(_QWORD *)(a1 + 72);
  if ( v17 )
  {
    v18 = *(_DWORD *)(a1 + 60);
    v19 = 0;
    v20 = hKey;
    while ( (unsigned int)v19 < v18 )
    {
      v21 = PersistNFAObject(v20, *(_QWORD *)(v17 + 8 * v19));
      v3 = v21;
      if ( v21 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v21);
            v4 = WPP_GLOBAL_Control;
          }
          if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 0x10) != 0 )
          {
            v5 = 15;
            goto LABEL_16;
          }
        }
        goto LABEL_56;
      }
      v19 = (unsigned int)(v19 + 1);
    }
  }
  v22 = *(_QWORD *)(a1 + 120);
  if ( v22 )
  {
    v23 = *(_DWORD *)(a1 + 112);
    v24 = 0;
    v25 = hKey;
    while ( (unsigned int)v24 < v23 )
    {
      v26 = PersistISAKMPObject(v25, *(_QWORD *)(v22 + 8 * v24));
      v3 = v26;
      if ( v26 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v26);
            v4 = WPP_GLOBAL_Control;
          }
          if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 0x10) != 0 )
          {
            v5 = 16;
            goto LABEL_16;
          }
        }
        goto LABEL_56;
      }
      v24 = (unsigned int)(v24 + 1);
    }
  }
  v2 = PersistPolicyObject(hKey, a1);
  v3 = v2;
  if ( v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v5 = 17;
LABEL_54:
      v11 = v2;
LABEL_55:
      WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_536406ce45663b69fb8864445bd745b5_Traceguids, v11);
    }
  }
LABEL_56:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180038908  mov     r11, rsp
0x18003890b  mov     [r11+8], rbx
0x18003890f  push    rbp
0x180038910  push    rsi
0x180038911  push    rdi
0x180038912  push    r14
0x180038914  push    r15
0x180038916  sub     rsp, 50h
0x18003891a  lea     rax, [r11+10h]
0x18003891e  mov     qword ptr [r11+18h], 0
0x180038926  mov     [r11-38h], rax
0x18003892a  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Po"...
0x180038931  lea     rax, [r11+18h]
0x180038935  mov     dword ptr [r11+10h], 0
0x18003893d  mov     [r11-40h], rax
0x180038941  mov     rbx, rcx
0x180038944  mov     qword ptr [r11-48h], 0
0x18003894c  xor     r9d, r9d; lpClass
0x18003894f  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x180038957  xor     r8d, r8d; Reserved
0x18003895a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038961  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180038969  call    cs:__imp_RegCreateKeyExW
0x18003896f  mov     edi, eax
0x180038971  test    eax, eax
0x180038973  jz      short loc_1800389A0
0x180038975  mov     rcx, cs:WPP_GLOBAL_Control
0x18003897c  lea     rbx, WPP_GLOBAL_Control
0x180038983  cmp     rcx, rbx
0x180038986  jz      loc_180038C12
0x18003898c  test    byte ptr [rcx+1Ch], 10h
0x180038990  jz      loc_180038C12
0x180038996  mov     edx, 0Ch
0x18003899b  jmp     loc_180038BFF
0x1800389a0  mov     r14, [rbx+58h]
0x1800389a4  test    r14, r14
0x1800389a7  jz      loc_180038A30
0x1800389ad  mov     ebp, [rbx+50h]
0x1800389b0  xor     esi, esi
0x1800389b2  mov     r15, [rsp+78h+hKey]
0x1800389ba  cmp     esi, ebp
0x1800389bc  jnb     short loc_180038A30
0x1800389be  mov     rdx, [r14+rsi*8]
0x1800389c2  mov     rcx, r15
0x1800389c5  call    PersistFilterObject
0x1800389ca  mov     edi, eax
0x1800389cc  test    eax, eax
0x1800389ce  jnz     short loc_1800389D4
0x1800389d0  inc     esi
0x1800389d2  jmp     short loc_1800389BA
0x1800389d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800389db  lea     rbx, WPP_GLOBAL_Control
0x1800389e2  cmp     rcx, rbx
0x1800389e5  jz      loc_180038C12
0x1800389eb  test    byte ptr [rcx+1Ch], 10h
0x1800389ef  jz      short loc_180038A10
0x1800389f1  mov     rcx, [rcx+10h]
0x1800389f5  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x1800389fc  mov     edx, 13h
0x180038a01  mov     r9d, edi
0x180038a04  call    WPP_SF_d
0x180038a09  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a10  cmp     rcx, rbx
0x180038a13  jz      loc_180038C12
0x180038a19  test    byte ptr [rcx+1Ch], 10h
0x180038a1d  jz      loc_180038C12
0x180038a23  mov     edx, 0Dh
0x180038a28  mov     r9d, edi
0x180038a2b  jmp     loc_180038C02
0x180038a30  mov     r14, [rbx+68h]
0x180038a34  test    r14, r14
0x180038a37  jz      loc_180038ABD
0x180038a3d  mov     ebp, [rbx+60h]
0x180038a40  xor     esi, esi
0x180038a42  mov     r15, [rsp+78h+hKey]
0x180038a4a  cmp     esi, ebp
0x180038a4c  jnb     short loc_180038ABD
0x180038a4e  mov     rdx, [r14+rsi*8]
0x180038a52  mov     rcx, r15
0x180038a55  call    PersistNegPolObject
0x180038a5a  mov     edi, eax
0x180038a5c  test    eax, eax
0x180038a5e  jnz     short loc_180038A64
0x180038a60  inc     esi
0x180038a62  jmp     short loc_180038A4A
0x180038a64  mov     rcx, cs:WPP_GLOBAL_Control
0x180038a6b  lea     rbx, WPP_GLOBAL_Control
0x180038a72  cmp     rcx, rbx
0x180038a75  jz      loc_180038C12
0x180038a7b  test    byte ptr [rcx+1Ch], 10h
0x180038a7f  jz      short loc_180038AA0
0x180038a81  mov     rcx, [rcx+10h]
0x180038a85  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038a8c  mov     edx, 12h
0x180038a91  mov     r9d, edi
0x180038a94  call    WPP_SF_d
0x180038a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180038aa0  cmp     rcx, rbx
0x180038aa3  jz      loc_180038C12
0x180038aa9  test    byte ptr [rcx+1Ch], 10h
0x180038aad  jz      loc_180038C12
0x180038ab3  mov     edx, 0Eh
0x180038ab8  jmp     loc_180038A28
0x180038abd  mov     r14, [rbx+48h]
0x180038ac1  test    r14, r14
0x180038ac4  jz      loc_180038B4A
0x180038aca  mov     ebp, [rbx+3Ch]
0x180038acd  xor     esi, esi
0x180038acf  mov     r15, [rsp+78h+hKey]
0x180038ad7  cmp     esi, ebp
0x180038ad9  jnb     short loc_180038B4A
0x180038adb  mov     rdx, [r14+rsi*8]
0x180038adf  mov     rcx, r15
0x180038ae2  call    PersistNFAObject
0x180038ae7  mov     edi, eax
0x180038ae9  test    eax, eax
0x180038aeb  jnz     short loc_180038AF1
0x180038aed  inc     esi
0x180038aef  jmp     short loc_180038AD7
0x180038af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180038af8  lea     rbx, WPP_GLOBAL_Control
0x180038aff  cmp     rcx, rbx
0x180038b02  jz      loc_180038C12
0x180038b08  test    byte ptr [rcx+1Ch], 10h
0x180038b0c  jz      short loc_180038B2D
0x180038b0e  mov     rcx, [rcx+10h]
0x180038b12  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038b19  mov     edx, 14h
0x180038b1e  mov     r9d, edi
0x180038b21  call    WPP_SF_d
0x180038b26  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b2d  cmp     rcx, rbx
0x180038b30  jz      loc_180038C12
0x180038b36  test    byte ptr [rcx+1Ch], 10h
0x180038b3a  jz      loc_180038C12
0x180038b40  mov     edx, 0Fh
0x180038b45  jmp     loc_180038A28
0x180038b4a  mov     r14, [rbx+78h]
0x180038b4e  test    r14, r14
0x180038b51  jz      short loc_180038BCB
0x180038b53  mov     ebp, [rbx+70h]
0x180038b56  xor     esi, esi
0x180038b58  mov     r15, [rsp+78h+hKey]
0x180038b60  cmp     esi, ebp
0x180038b62  jnb     short loc_180038BCB
0x180038b64  mov     rdx, [r14+rsi*8]
0x180038b68  mov     rcx, r15
0x180038b6b  call    PersistISAKMPObject
0x180038b70  mov     edi, eax
0x180038b72  test    eax, eax
0x180038b74  jnz     short loc_180038B7A
0x180038b76  inc     esi
0x180038b78  jmp     short loc_180038B60
0x180038b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180038b81  lea     rbx, WPP_GLOBAL_Control
0x180038b88  cmp     rcx, rbx
0x180038b8b  jz      loc_180038C12
0x180038b91  test    byte ptr [rcx+1Ch], 10h
0x180038b95  jz      short loc_180038BB6
0x180038b97  mov     rcx, [rcx+10h]
0x180038b9b  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038ba2  mov     edx, 15h
0x180038ba7  mov     r9d, edi
0x180038baa  call    WPP_SF_d
0x180038baf  mov     rcx, cs:WPP_GLOBAL_Control
0x180038bb6  cmp     rcx, rbx
0x180038bb9  jz      short loc_180038C12
0x180038bbb  test    byte ptr [rcx+1Ch], 10h
0x180038bbf  jz      short loc_180038C12
0x180038bc1  mov     edx, 10h
0x180038bc6  jmp     loc_180038A28
0x180038bcb  mov     rcx, [rsp+78h+hKey]
0x180038bd3  mov     rdx, rbx
0x180038bd6  call    PersistPolicyObject
0x180038bdb  mov     edi, eax
0x180038bdd  test    eax, eax
0x180038bdf  jz      short loc_180038C12
0x180038be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180038be8  lea     rbx, WPP_GLOBAL_Control
0x180038bef  cmp     rcx, rbx
0x180038bf2  jz      short loc_180038C12
0x180038bf4  test    byte ptr [rcx+1Ch], 10h
0x180038bf8  jz      short loc_180038C12
0x180038bfa  mov     edx, 11h
0x180038bff  mov     r9d, eax
0x180038c02  mov     rcx, [rcx+10h]
0x180038c06  lea     r8, WPP_536406ce45663b69fb8864445bd745b5_Traceguids
0x180038c0d  call    WPP_SF_d
0x180038c12  mov     rcx, [rsp+78h+hKey]; hKey
0x180038c1a  test    rcx, rcx
0x180038c1d  jz      short loc_180038C25
0x180038c1f  call    cs:__imp_RegCloseKey
0x180038c25  mov     rbx, [rsp+78h+arg_0]
0x180038c2d  mov     eax, edi
0x180038c2f  add     rsp, 50h
0x180038c33  pop     r15
0x180038c35  pop     r14
0x180038c37  pop     rdi
0x180038c38  pop     rsi
0x180038c39  pop     rbp
0x180038c3a  retn
```
