# ReadPolicyObjectFromRegistry

- ea: `0x180039c80`
- end: `0x180039f5c`
- name: `ReadPolicyObjectFromRegistry`
- size: `732`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180007c5c`
- `0x18000bd9c`
- `0x18002c0b4`

## callees

- `0x18000e510`
- `0x1800394e4`
- `0x180039614`
- `0x180039788`
- `0x180039ae0`
- `0x180039c80`
- `0x18003b650`
- `0x180042ab0`
- `0x180042e20`

## pseudocode

```c
__int64 __fastcall ReadPolicyObjectFromRegistry(HKEY hKey, unsigned __int16 *a2, __int64 a3, LPVOID *a4)
{
  int v4; // esi
  _QWORD *v7; // rdi
  unsigned int NFAObjectsFromRegistry; // ebx
  int v9; // r8d
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  LPVOID v13; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v14; // [rsp+68h] [rbp-21h] BYREF
  unsigned int v15; // [rsp+6Ch] [rbp-1Dh] BYREF
  int v16; // [rsp+70h] [rbp-19h] BYREF
  int v17; // [rsp+74h] [rbp-15h] BYREF
  int v18; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v19[3]; // [rsp+7Ch] [rbp-Dh] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-1h] BYREF
  __int64 v21; // [rsp+90h] [rbp+7h] BYREF
  __int64 v22; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v23; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v24[7]; // [rsp+A8h] [rbp+1Fh] BYREF

  v4 = a3;
  v13 = 0;
  v16 = 0;
  v21 = 0;
  v14 = 0;
  lpMem = 0;
  v7 = 0;
  v15 = 0;
  v22 = 0;
  v17 = 0;
  v23 = 0;
  v18 = 0;
  v24[0] = 0;
  memset(v19, 0, sizeof(v19));
  NFAObjectsFromRegistry = UnMarshallRegistryPolicyObject(hKey, a3, a2, 1, &v13);
  if ( NFAObjectsFromRegistry )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v11 = 11;
    goto LABEL_22;
  }
  NFAObjectsFromRegistry = ReadNFAObjectsFromRegistry(
                             (_DWORD)hKey,
                             v4,
                             v9,
                             *((_QWORD *)v13 + 8),
                             *((_DWORD *)v13 + 14),
                             (__int64)&v21,
                             (__int64)&v16,
                             (__int64)&v19[1],
                             (__int64)&v14,
                             (__int64)&lpMem,
                             (__int64)&v15);
  if ( NFAObjectsFromRegistry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids,
        NFAObjectsFromRegistry);
    v7 = *(_QWORD **)&v19[1];
    goto LABEL_23;
  }
  v7 = *(_QWORD **)&v19[1];
  NFAObjectsFromRegistry = ReadFilterObjectsFromRegistry((_DWORD)hKey, v4, v19[1], v14, (__int64)&v22, (__int64)&v17);
  if ( NFAObjectsFromRegistry )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v11 = 13;
    goto LABEL_22;
  }
  NFAObjectsFromRegistry = ReadNegPolObjectsFromRegistry(
                             (_DWORD)hKey,
                             v4,
                             (_DWORD)lpMem,
                             v15,
                             (__int64)&v23,
                             (__int64)&v18);
  if ( NFAObjectsFromRegistry )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_23;
    v11 = 14;
    goto LABEL_22;
  }
  NFAObjectsFromRegistry = ReadISAKMPObjectsFromRegistry(hKey, (__int64)v24, (__int64)v19);
  if ( !NFAObjectsFromRegistry )
  {
    *((_QWORD *)v13 + 9) = v21;
    *((_DWORD *)v13 + 15) = v16;
    *((_DWORD *)v13 + 20) = v17;
    *((_QWORD *)v13 + 11) = v22;
    *((_QWORD *)v13 + 13) = v23;
    *((_DWORD *)v13 + 24) = v18;
    *((_DWORD *)v13 + 28) = v19[0];
    *((_QWORD *)v13 + 15) = v24[0];
    *a4 = v13;
    goto LABEL_27;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v11 = 15;
LABEL_22:
    WPP_SF_d(v10[2], v11, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids, NFAObjectsFromRegistry);
  }
LABEL_23:
  if ( v13 )
    FreeIpsecPolicyObject((LPVOID *)v13);
  *a4 = 0;
LABEL_27:
  if ( v7 )
    FreeNFAReferences(v7, v14);
  if ( lpMem )
    FreeNFAReferences(lpMem, v15);
  return NFAObjectsFromRegistry;
}

```

## disassembly

```asm
0x180039c80  push    rbp
0x180039c82  push    rbx
0x180039c83  push    rsi
0x180039c84  push    rdi
0x180039c85  push    r12
0x180039c87  push    r14
0x180039c89  push    r15
0x180039c8b  lea     rbp, [rsp-27h]
0x180039c90  sub     rsp, 0B0h
0x180039c97  xor     r12d, r12d
0x180039c9a  lea     rax, [rbp+57h+var_80]
0x180039c9e  mov     rsi, r8
0x180039ca1  mov     [rbp+57h+var_80], r12
0x180039ca5  mov     r15, r9
0x180039ca8  mov     [rbp+57h+var_70], r12d
0x180039cac  mov     r8, rdx
0x180039caf  mov     [rbp+57h+var_50], r12
0x180039cb3  lea     r9d, [r12+1]
0x180039cb8  mov     qword ptr [rbp+57h+var_64+4], r12
0x180039cbc  mov     rdx, rsi
0x180039cbf  mov     [rbp+57h+var_78], r12d
0x180039cc3  mov     r14, rcx
0x180039cc6  mov     [rbp+57h+lpMem], r12
0x180039cca  mov     edi, r12d
0x180039ccd  mov     [rbp+57h+var_74], r12d
0x180039cd1  mov     [rbp+57h+var_48], r12
0x180039cd5  mov     [rbp+57h+var_6C], r12d
0x180039cd9  mov     [rbp+57h+var_40], r12
0x180039cdd  mov     [rbp+57h+var_68], r12d
0x180039ce1  mov     [rbp+57h+var_38], r12
0x180039ce5  mov     dword ptr [rbp+57h+var_64], r12d
0x180039ce9  mov     [rsp+0E0h+var_C0], rax; __int64
0x180039cee  call    UnMarshallRegistryPolicyObject
0x180039cf3  mov     ebx, eax
0x180039cf5  test    eax, eax
0x180039cf7  jz      short loc_180039D24
0x180039cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d00  lea     rax, WPP_GLOBAL_Control
0x180039d07  cmp     rcx, rax
0x180039d0a  jz      loc_180039EB5
0x180039d10  test    byte ptr [rcx+1Ch], 10h
0x180039d14  jz      loc_180039EB5
0x180039d1a  lea     edx, [r12+0Bh]
0x180039d1f  jmp     loc_180039EA2
0x180039d24  mov     r9, [rbp+57h+var_80]
0x180039d28  lea     rax, [rbp+57h+var_74]
0x180039d2c  mov     [rsp+0E0h+var_90], rax
0x180039d31  mov     rdx, rsi
0x180039d34  lea     rax, [rbp+57h+lpMem]
0x180039d38  mov     rcx, r14
0x180039d3b  mov     [rsp+0E0h+var_98], rax
0x180039d40  lea     rax, [rbp+57h+var_78]
0x180039d44  mov     [rsp+0E0h+var_A0], rax
0x180039d49  lea     rax, [rbp+57h+var_64+4]
0x180039d4d  mov     [rsp+0E0h+var_A8], rax
0x180039d52  lea     rax, [rbp+57h+var_70]
0x180039d56  mov     [rsp+0E0h+var_B0], rax
0x180039d5b  lea     rax, [rbp+57h+var_50]
0x180039d5f  mov     [rsp+0E0h+var_B8], rax
0x180039d64  mov     eax, [r9+38h]
0x180039d68  mov     r9, [r9+40h]
0x180039d6c  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180039d70  call    ReadNFAObjectsFromRegistry
0x180039d75  mov     ebx, eax
0x180039d77  test    eax, eax
0x180039d79  jz      short loc_180039DB5
0x180039d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d82  lea     rax, WPP_GLOBAL_Control
0x180039d89  cmp     rcx, rax
0x180039d8c  jz      short loc_180039DAC
0x180039d8e  test    byte ptr [rcx+1Ch], 10h
0x180039d92  jz      short loc_180039DAC
0x180039d94  mov     rcx, [rcx+10h]
0x180039d98  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039d9f  mov     edx, 0Ch
0x180039da4  mov     r9d, ebx
0x180039da7  call    WPP_SF_d
0x180039dac  mov     rdi, qword ptr [rbp+57h+var_64+4]
0x180039db0  jmp     loc_180039EB5
0x180039db5  mov     rdi, qword ptr [rbp+57h+var_64+4]
0x180039db9  lea     rax, [rbp+57h+var_6C]
0x180039dbd  mov     r9d, [rbp+57h+var_78]
0x180039dc1  mov     r8, rdi
0x180039dc4  mov     [rsp+0E0h+var_B8], rax
0x180039dc9  mov     rdx, rsi
0x180039dcc  lea     rax, [rbp+57h+var_48]
0x180039dd0  mov     rcx, r14
0x180039dd3  mov     [rsp+0E0h+var_C0], rax
0x180039dd8  call    ReadFilterObjectsFromRegistry
0x180039ddd  mov     ebx, eax
0x180039ddf  test    eax, eax
0x180039de1  jz      short loc_180039E0E
0x180039de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180039dea  lea     rax, WPP_GLOBAL_Control
0x180039df1  cmp     rcx, rax
0x180039df4  jz      loc_180039EB5
0x180039dfa  test    byte ptr [rcx+1Ch], 10h
0x180039dfe  jz      loc_180039EB5
0x180039e04  mov     edx, 0Dh
0x180039e09  jmp     loc_180039EA2
0x180039e0e  mov     r9d, [rbp+57h+var_74]
0x180039e12  lea     rax, [rbp+57h+var_68]
0x180039e16  mov     r8, [rbp+57h+lpMem]
0x180039e1a  mov     rdx, rsi
0x180039e1d  mov     [rsp+0E0h+var_B8], rax
0x180039e22  mov     rcx, r14
0x180039e25  lea     rax, [rbp+57h+var_40]
0x180039e29  mov     [rsp+0E0h+var_C0], rax
0x180039e2e  call    ReadNegPolObjectsFromRegistry
0x180039e33  mov     ebx, eax
0x180039e35  test    eax, eax
0x180039e37  jz      short loc_180039E59
0x180039e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e40  lea     rax, WPP_GLOBAL_Control
0x180039e47  cmp     rcx, rax
0x180039e4a  jz      short loc_180039EB5
0x180039e4c  test    byte ptr [rcx+1Ch], 10h
0x180039e50  jz      short loc_180039EB5
0x180039e52  mov     edx, 0Eh
0x180039e57  jmp     short loc_180039EA2
0x180039e59  mov     r8, [rbp+57h+var_80]
0x180039e5d  lea     rax, [rbp+57h+var_64]
0x180039e61  mov     [rsp+0E0h+var_B8], rax; __int64
0x180039e66  add     r8, 30h ; '0'
0x180039e6a  lea     rax, [rbp+57h+var_38]
0x180039e6e  mov     rdx, rsi
0x180039e71  mov     rcx, r14; hKey
0x180039e74  mov     [rsp+0E0h+var_C0], rax; __int64
0x180039e79  call    ReadISAKMPObjectsFromRegistry
0x180039e7e  mov     ebx, eax
0x180039e80  test    eax, eax
0x180039e82  jz      short loc_180039EC8
0x180039e84  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e8b  lea     rax, WPP_GLOBAL_Control
0x180039e92  cmp     rcx, rax
0x180039e95  jz      short loc_180039EB5
0x180039e97  test    byte ptr [rcx+1Ch], 10h
0x180039e9b  jz      short loc_180039EB5
0x180039e9d  mov     edx, 0Fh
0x180039ea2  mov     rcx, [rcx+10h]
0x180039ea6  lea     r8, WPP_b9d01e43600b30fd3b2c38173d655c9c_Traceguids
0x180039ead  mov     r9d, ebx
0x180039eb0  call    WPP_SF_d
0x180039eb5  mov     rcx, [rbp+57h+var_80]; lpMem
0x180039eb9  test    rcx, rcx
0x180039ebc  jz      short loc_180039EC3
0x180039ebe  call    FreeIpsecPolicyObject
0x180039ec3  mov     [r15], r12
0x180039ec6  jmp     short loc_180039F27
0x180039ec8  mov     rcx, [rbp+57h+var_80]
0x180039ecc  mov     rax, [rbp+57h+var_50]
0x180039ed0  mov     [rcx+48h], rax
0x180039ed4  mov     rcx, [rbp+57h+var_80]
0x180039ed8  mov     eax, [rbp+57h+var_70]
0x180039edb  mov     [rcx+3Ch], eax
0x180039ede  mov     rcx, [rbp+57h+var_80]
0x180039ee2  mov     eax, [rbp+57h+var_6C]
0x180039ee5  mov     [rcx+50h], eax
0x180039ee8  mov     rcx, [rbp+57h+var_80]
0x180039eec  mov     rax, [rbp+57h+var_48]
0x180039ef0  mov     [rcx+58h], rax
0x180039ef4  mov     rcx, [rbp+57h+var_80]
0x180039ef8  mov     rax, [rbp+57h+var_40]
0x180039efc  mov     [rcx+68h], rax
0x180039f00  mov     rcx, [rbp+57h+var_80]
0x180039f04  mov     eax, [rbp+57h+var_68]
0x180039f07  mov     [rcx+60h], eax
0x180039f0a  mov     rdx, [rbp+57h+var_80]
0x180039f0e  mov     eax, dword ptr [rbp+57h+var_64]
0x180039f11  mov     [rdx+70h], eax
0x180039f14  mov     rax, [rbp+57h+var_38]
0x180039f18  mov     rdx, [rbp+57h+var_80]
0x180039f1c  mov     [rdx+78h], rax
0x180039f20  mov     rax, [rbp+57h+var_80]
0x180039f24  mov     [r15], rax
0x180039f27  test    rdi, rdi
0x180039f2a  jz      short loc_180039F37
0x180039f2c  mov     edx, [rbp+57h+var_78]
0x180039f2f  mov     rcx, rdi; lpMem
0x180039f32  call    FreeNFAReferences
0x180039f37  mov     rcx, [rbp+57h+lpMem]; lpMem
0x180039f3b  test    rcx, rcx
0x180039f3e  jz      short loc_180039F48
0x180039f40  mov     edx, [rbp+57h+var_74]
0x180039f43  call    FreeNFAReferences
0x180039f48  mov     eax, ebx
0x180039f4a  add     rsp, 0B0h
0x180039f51  pop     r15
0x180039f53  pop     r14
0x180039f55  pop     r12
0x180039f57  pop     rdi
0x180039f58  pop     rsi
0x180039f59  pop     rbx
0x180039f5a  pop     rbp
0x180039f5b  retn
```
