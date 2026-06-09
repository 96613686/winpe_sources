# CiGetActionsForImage

- ea: `0x18008c95c`
- end: `0x18008cbae`
- name: `CiGetActionsForImage`
- size: `594`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005fffc`
- `0x180060af4`
- `0x18008d750`
- `0x1800e5fd0`

## callees

- `0x1800100a4`
- `0x18001d110`
- `0x18002c0d0`
- `0x180057008`
- `0x180061100`
- `0x18008c95c`
- `0x1800e1984`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x18008ca79`
- `ntoskrnl!PsIsSystemProcess` at `0x18008ca79`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x18008ca60`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x18008ca60`

## pseudocode

```c
__int64 __fastcall CiGetActionsForImage(__int64 a1, __int64 a2, __int64 a3, char a4, char a5)
{
  unsigned int v6; // esi
  int v9; // ecx
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // edi
  __int64 v13; // rdx
  char v14; // al
  __int128 *v15; // rcx
  unsigned int v16; // ebx
  BOOL v17; // eax
  unsigned int v18; // edi
  int v19; // edx
  int v20; // ebx
  unsigned int v21; // ecx
  __int64 result; // rax
  _DWORD v23[4]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v24[64]; // [rsp+30h] [rbp-78h] BYREF

  v23[0] = 0;
  v6 = a3;
  if ( (a3 & 0x40) == 0 && (unsigned __int8)CipShouldConsiderAsUntrustedSource(a1, a2, a3, v23) )
    v6 |= 0x40u;
  if ( (g_CiOptions & 8) != 0 && (g_CiTestFlags & 0x400) != 0 )
    v6 |= 0x40u;
  if ( (v6 & 0xE000000F) != 0 || a5 == 5 )
    v9 = 0;
  else
    v9 = ((unsigned __int8)~(_BYTE)v6 >> 6) & 1;
  v10 = v9 | v23[0] & 0xFFFFFFFE;
  v11 = v10 ^ ((unsigned __int8)(v9 | v23[0] & 0xFE) ^ (unsigned __int8)(2 * (v9 | v23[0] & 0xFE))) & 2;
  v12 = v11 ^ ((unsigned __int8)v11 ^ (unsigned __int8)(8 * v10)) & 8;
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
    LOBYTE(v13) = a4;
  else
    v13 = 0;
  v14 = CipUsePageHashesForImage(v6, v13);
  v16 = v12 ^ ((unsigned __int8)(4 * v14) ^ (unsigned __int8)v12) & 4 | 0x80;
  if ( (((unsigned __int8)v12 ^ ((unsigned __int8)(4 * v14) ^ (unsigned __int8)v12) & 4) & 8) == 0 )
  {
    v17 = 0;
    if ( (v6 & 0x20000000) == 0 )
      v17 = (v6 & 2) == 0;
    v16 = (8 * v17) | v16 & 0xFFFFFFF7;
  }
  v18 = v16;
  if ( (v6 & 0x20000015) == 0 && (unsigned int)PsIsProtectedProcessLight(a1)
    || (v6 & 2) != 0 && (unsigned __int8)PsIsSystemProcess(a1) )
  {
    v16 |= 0x40u;
    v18 |= 0x40u;
  }
  if ( (g_CiDeveloperMode & 0x20000) != 0 )
  {
    v16 = v18 | 0x224;
    if ( (v18 & 8) != 0 )
      v16 = v18 | 0x624;
    v18 = v16;
  }
  if ( (g_CiDeveloperMode & 0x40000) != 0 )
  {
    v15 = g_CipWhichLevelComparisons;
    v16 = v18 | 0x10;
    v19 = *((_DWORD *)g_CipWhichLevelComparisons + 12);
    if ( _bittest(&v19, a5 & 0xF) )
      v16 = v18 & 0xFFFFFFEC | 0x10;
    v18 = v16;
  }
  if ( (v6 & 0x1000000) != 0 && (g_CiDeveloperMode & 0x400000) != 0 )
  {
    v20 = v18;
    if ( (v6 & 0xE41FFF8F) == 0 && (v18 & 0x40) == 0 )
      v20 = v18 | 0x800;
    v16 = v20 & 0xFFFFFF7F;
    v18 = v16;
  }
  if ( (g_CiDeveloperMode & 0x8000) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 48LL) & 0x100) != 0 )
      v16 = v18 & 0xFFFFFD48 | 0x234;
    else
      v16 = v18 | 0x2B4;
  }
  v23[0] = 0;
  if ( (unsigned int)Feature_CodeIntegrity_VCimEvaluation__private_IsEnabledDeviceUsageNoInline(v15)
    && (g_CiPolicyState & 0x1000000) != 0
    && (int)CipGetVCimRootHash(a2, v24, v23) >= 0 )
  {
    v16 = v16 & 0xFFF7FF58 | 0x80024;
  }
  v21 = v16 & 0xFFFFEFFF | ((v16 & 1) << 12);
  result = v21;
  if ( (v6 & 0x40) != 0 )
    return v21 ^ ((unsigned __int16)v21 ^ (unsigned __int16)((_WORD)v21 << 10)) & 0x2000;
  return result;
}

```

## disassembly

```asm
0x18008c95c  mov     [rsp+arg_10], rbx
0x18008c961  push    rbp
0x18008c962  push    rsi
0x18008c963  push    rdi
0x18008c964  push    r12
0x18008c966  push    r14
0x18008c968  sub     rsp, 80h
0x18008c96f  mov     rax, cs:__security_cookie
0x18008c976  xor     rax, rsp
0x18008c979  mov     [rsp+0A8h+var_38], rax
0x18008c97e  mov     [rsp+0A8h+var_88], 0
0x18008c986  mov     bl, r9b
0x18008c989  mov     esi, r8d
0x18008c98c  mov     r14, rdx
0x18008c98f  mov     rbp, rcx
0x18008c992  test    r8b, 40h
0x18008c996  jnz     short loc_18008C9A9
0x18008c998  lea     r9, [rsp+0A8h+var_88]
0x18008c99d  call    CipShouldConsiderAsUntrustedSource
0x18008c9a2  test    al, al
0x18008c9a4  jz      short loc_18008C9A9
0x18008c9a6  or      esi, 40h
0x18008c9a9  mov     eax, cs:g_CiOptions
0x18008c9af  test    al, 8
0x18008c9b1  jz      short loc_18008C9C2
0x18008c9b3  test    cs:g_CiTestFlags, 400h
0x18008c9bd  jz      short loc_18008C9C2
0x18008c9bf  or      esi, 40h
0x18008c9c2  mov     r12d, 1
0x18008c9c8  test    esi, 0E000000Fh
0x18008c9ce  jz      short loc_18008C9D4
0x18008c9d0  xor     ecx, ecx
0x18008c9d2  jmp     short loc_18008C9EC
0x18008c9d4  cmp     [rsp+0A8h+arg_20], 5
0x18008c9dc  jz      short loc_18008C9D0
0x18008c9de  mov     al, sil
0x18008c9e1  not     al
0x18008c9e3  movzx   ecx, al
0x18008c9e6  shr     ecx, 6
0x18008c9e9  and     ecx, r12d
0x18008c9ec  mov     eax, [rsp+0A8h+var_88]
0x18008c9f0  and     eax, 0FFFFFFFEh
0x18008c9f3  or      eax, ecx
0x18008c9f5  lea     ecx, [rax+rax]
0x18008c9f8  xor     ecx, eax
0x18008c9fa  lea     edi, ds:0[rax*8]
0x18008ca01  and     ecx, 2
0x18008ca04  xor     ecx, eax
0x18008ca06  xor     edi, ecx
0x18008ca08  and     edi, 8
0x18008ca0b  xor     edi, ecx
0x18008ca0d  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x18008ca12  mov     ecx, esi
0x18008ca14  test    eax, eax
0x18008ca16  jz      short loc_18008CA1C
0x18008ca18  mov     dl, bl
0x18008ca1a  jmp     short loc_18008CA1E
0x18008ca1c  xor     edx, edx
0x18008ca1e  call    CipUsePageHashesForImage
0x18008ca23  movzx   eax, al
0x18008ca26  mov     ebx, edi
0x18008ca28  shl     eax, 2
0x18008ca2b  xor     ebx, eax
0x18008ca2d  and     ebx, 4
0x18008ca30  xor     ebx, edi
0x18008ca32  bts     ebx, 7
0x18008ca36  test    bl, 8
0x18008ca39  jnz     short loc_18008CA53
0x18008ca3b  xor     eax, eax
0x18008ca3d  bt      esi, 1Dh
0x18008ca41  jb      short loc_18008CA4B
0x18008ca43  test    sil, 2
0x18008ca47  cmovz   eax, r12d
0x18008ca4b  and     ebx, 0FFFFFFF7h
0x18008ca4e  shl     eax, 3
0x18008ca51  or      ebx, eax
0x18008ca53  mov     edi, ebx
0x18008ca55  test    esi, 20000015h
0x18008ca5b  jnz     short loc_18008CA70
0x18008ca5d  mov     rcx, rbp
0x18008ca60  call    cs:__imp_PsIsProtectedProcessLight
0x18008ca67  nop     dword ptr [rax+rax+00h]
0x18008ca6c  test    eax, eax
0x18008ca6e  jnz     short loc_18008CA89
0x18008ca70  test    sil, 2
0x18008ca74  jz      short loc_18008CA90
0x18008ca76  mov     rcx, rbp
0x18008ca79  call    cs:__imp_PsIsSystemProcess
0x18008ca80  nop     dword ptr [rax+rax+00h]
0x18008ca85  test    al, al
0x18008ca87  jz      short loc_18008CA90
0x18008ca89  mov     ebx, edi
0x18008ca8b  or      ebx, 40h
0x18008ca8e  mov     edi, ebx
0x18008ca90  mov     eax, cs:g_CiDeveloperMode
0x18008ca96  bt      eax, 11h
0x18008ca9a  jnb     short loc_18008CAAF
0x18008ca9c  mov     ebx, edi
0x18008ca9e  or      ebx, 224h
0x18008caa4  test    bl, 8
0x18008caa7  jz      short loc_18008CAAD
0x18008caa9  bts     ebx, 0Ah
0x18008caad  mov     edi, ebx
0x18008caaf  bt      eax, 12h
0x18008cab3  jnb     short loc_18008CADC
0x18008cab5  mov     rcx, cs:g_CipWhichLevelComparisons
0x18008cabc  mov     ebx, edi
0x18008cabe  movzx   r8d, [rsp+0A8h+arg_20]
0x18008cac7  or      ebx, 10h
0x18008caca  and     r8d, 0Fh
0x18008cace  mov     edx, [rcx+30h]
0x18008cad1  bt      edx, r8d
0x18008cad5  jnb     short loc_18008CADA
0x18008cad7  and     ebx, 0FFFFFFFCh
0x18008cada  mov     edi, ebx
0x18008cadc  bt      esi, 18h
0x18008cae0  jnb     short loc_18008CB02
0x18008cae2  bt      eax, 16h
0x18008cae6  jnb     short loc_18008CB02
0x18008cae8  mov     ebx, edi
0x18008caea  test    esi, 0E41FFF8Fh
0x18008caf0  jnz     short loc_18008CAFC
0x18008caf2  test    dil, 40h
0x18008caf6  jnz     short loc_18008CAFC
0x18008caf8  bts     ebx, 0Bh
0x18008cafc  btr     ebx, 7
0x18008cb00  mov     edi, ebx
0x18008cb02  mov     ebp, 0FFFFFF7Ch
0x18008cb07  bt      eax, 0Fh
0x18008cb0b  jnb     short loc_18008CB2F
0x18008cb0d  mov     rax, [r14+8]
0x18008cb11  mov     ebx, edi
0x18008cb13  or      ebx, 210h
0x18008cb19  test    dword ptr [rax+30h], 100h
0x18008cb20  jz      short loc_18008CB29
0x18008cb22  and     ebx, ebp
0x18008cb24  or      ebx, 24h
0x18008cb27  jmp     short loc_18008CB2F
0x18008cb29  or      ebx, 0A4h
0x18008cb2f  mov     [rsp+0A8h+var_88], 0
0x18008cb37  call    Feature_CodeIntegrity_VCimEvaluation__private_IsEnabledDeviceUsageNoInline
0x18008cb3c  test    eax, eax
0x18008cb3e  jz      short loc_18008CB67
0x18008cb40  test    byte ptr cs:g_CiPolicyState+3, r12b
0x18008cb47  jz      short loc_18008CB67
0x18008cb49  lea     r8, [rsp+0A8h+var_88]
0x18008cb4e  mov     rcx, r14
0x18008cb51  lea     rdx, [rsp+0A8h+var_78]
0x18008cb56  call    CipGetVCimRootHash
0x18008cb5b  test    eax, eax
0x18008cb5d  js      short loc_18008CB67
0x18008cb5f  and     ebx, ebp
0x18008cb61  or      ebx, 80024h
0x18008cb67  mov     ecx, ebx
0x18008cb69  btr     ebx, 0Ch
0x18008cb6d  and     ecx, r12d
0x18008cb70  shl     ecx, 0Ch
0x18008cb73  or      ecx, ebx
0x18008cb75  mov     eax, ecx
0x18008cb77  test    sil, 40h
0x18008cb7b  jz      short loc_18008CB89
0x18008cb7d  shl     eax, 0Ah
0x18008cb80  xor     eax, ecx
0x18008cb82  and     eax, 2000h
0x18008cb87  xor     eax, ecx
0x18008cb89  mov     rcx, [rsp+0A8h+var_38]
0x18008cb8e  xor     rcx, rsp; StackCookie
0x18008cb91  call    __security_check_cookie
0x18008cb96  mov     rbx, [rsp+0A8h+arg_10]
0x18008cb9e  add     rsp, 80h
0x18008cba5  pop     r14
0x18008cba7  pop     r12
0x18008cba9  pop     rdi
0x18008cbaa  pop     rsi
0x18008cbab  pop     rbp
0x18008cbac  retn
```
