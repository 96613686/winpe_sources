# CiGetActionsForImage

- ea: `0x18009679c`
- end: `0x180096a0e`
- name: `CiGetActionsForImage`
- size: `626`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006005c`
- `0x180060b54`
- `0x180096f80`
- `0x1800e5a50`

## callees

- `0x180010094`
- `0x180057008`
- `0x18009679c`
- `0x180096a14`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x18009696d`
- `ntoskrnl!PsIsSystemProcess` at `0x18009696d`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800968cc`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x1800968cc`

## pseudocode

```c
__int64 __fastcall CiGetActionsForImage(__int64 a1, struct _FILE_OBJECT *a2, int a3, char a4, char a5)
{
  unsigned int v6; // edi
  int v9; // ecx
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // esi
  __int64 v13; // rdx
  char v14; // al
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  int v17; // eax
  unsigned int v18; // ecx
  BOOL v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r8d
  int v24; // [rsp+70h] [rbp+18h] BYREF

  v24 = 0;
  v6 = a3;
  if ( (a3 & 0x40) == 0 && CipShouldConsiderAsUntrustedSource(a1, a2, a3, &v24) )
    v6 |= 0x40u;
  if ( (g_CiOptions & 8) != 0 && (g_CiTestFlags & 0x400) != 0 )
    v6 |= 0x40u;
  if ( (v6 & 0xE000000F) != 0 || a5 == 5 )
    v9 = 0;
  else
    v9 = ((unsigned __int8)~(_BYTE)v6 >> 6) & 1;
  v10 = v9 | v24 & 0xFFFFFFFE;
  v11 = v10 ^ ((unsigned __int8)(v9 | v24 & 0xFE) ^ (unsigned __int8)(2 * (v9 | v24 & 0xFE))) & 2;
  v12 = v11 ^ ((unsigned __int8)v11 ^ (unsigned __int8)(8 * v10)) & 8;
  if ( (unsigned int)Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline() )
    LOBYTE(v13) = a4;
  else
    v13 = 0;
  v14 = CipUsePageHashesForImage(v6, v13);
  v15 = v12 ^ ((unsigned __int8)(4 * v14) ^ (unsigned __int8)v12) & 4 | 0x80;
  if ( (((unsigned __int8)v12 ^ ((unsigned __int8)(4 * v14) ^ (unsigned __int8)v12) & 4) & 8) == 0 )
  {
    v20 = 0;
    if ( (v6 & 0x20000000) == 0 )
      v20 = (v6 & 2) == 0;
    v15 = (8 * v20) | v15 & 0xFFFFFFF7;
  }
  if ( (v6 & 0x20000015) == 0 && (unsigned int)PsIsProtectedProcessLight(a1)
    || (v6 & 2) != 0 && (unsigned __int8)PsIsSystemProcess(a1) )
  {
    v15 |= 0x40u;
  }
  if ( (g_CiDeveloperMode & 0x20000) != 0 )
  {
    v15 |= 0x224u;
    if ( (v15 & 8) != 0 )
      v15 |= 0x400u;
  }
  if ( (g_CiDeveloperMode & 0x40000) != 0 )
  {
    v15 |= 0x10u;
    v21 = *((_DWORD *)g_CipWhichLevelComparisons + 12);
    if ( _bittest(&v21, a5 & 0xF) )
      v15 &= 0xFFFFFFFC;
  }
  v16 = v15;
  if ( (v6 & 0x1000000) != 0 && (g_CiDeveloperMode & 0x400000) != 0 )
  {
    v22 = v15 | 0x800;
    if ( (v6 & 0xE41FFF8F) != 0 || (v15 & 0x40) != 0 )
      v22 = v15;
    v16 = v22 & 0xFFFFFF7F;
  }
  if ( (g_CiDeveloperMode & 0x8000) != 0 )
  {
    v23 = v16 | 0x210;
    if ( (a2->DeviceObject->Flags & 0x100) != 0 )
      v16 = v23 & 0xFFFFFF58 | 0x24;
    else
      v16 = v23 | 0xA4;
  }
  v18 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)((_WORD)v16 << 12)) & 0x1000;
  if ( (v6 & 0x40) != 0 )
  {
    v17 = v16 ^ ((unsigned __int16)v16 ^ (unsigned __int16)((_WORD)v16 << 12)) & 0x1000;
    return v17 ^ ((unsigned __int16)v17 ^ (unsigned __int16)((_WORD)v18 << 10)) & 0x2000u;
  }
  return v18;
}

```

## disassembly

```asm
0x18009679c  push    rbx
0x18009679e  push    rbp
0x18009679f  push    rsi
0x1800967a0  push    rdi
0x1800967a1  push    r12
0x1800967a3  push    r14
0x1800967a5  sub     rsp, 28h
0x1800967a9  mov     [rsp+58h+arg_10], 0
0x1800967b1  mov     bl, r9b
0x1800967b4  mov     edi, r8d
0x1800967b7  mov     r14, rdx
0x1800967ba  mov     rbp, rcx
0x1800967bd  test    r8b, 40h
0x1800967c1  jz      loc_1800968E8
0x1800967c7  mov     eax, cs:g_CiOptions
0x1800967cd  test    al, 8
0x1800967cf  jnz     loc_18009694B
0x1800967d5  mov     r12d, 1
0x1800967db  test    edi, 0E000000Fh
0x1800967e1  jnz     short loc_1800967F1
0x1800967e3  cmp     [rsp+58h+arg_20], 5
0x1800967eb  jnz     loc_1800968B6
0x1800967f1  xor     ecx, ecx
0x1800967f3  mov     eax, [rsp+58h+arg_10]
0x1800967f7  and     eax, 0FFFFFFFEh
0x1800967fa  or      eax, ecx
0x1800967fc  lea     ecx, [rax+rax]
0x1800967ff  xor     ecx, eax
0x180096801  lea     esi, ds:0[rax*8]
0x180096808  and     ecx, 2
0x18009680b  xor     ecx, eax
0x18009680d  xor     esi, ecx
0x18009680f  and     esi, 8
0x180096812  xor     esi, ecx
0x180096814  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x180096819  mov     ecx, edi
0x18009681b  test    eax, eax
0x18009681d  jz      loc_180096963
0x180096823  mov     dl, bl
0x180096825  call    CipUsePageHashesForImage
0x18009682a  movzx   eax, al
0x18009682d  mov     ebx, esi
0x18009682f  shl     eax, 2
0x180096832  xor     ebx, eax
0x180096834  and     ebx, 4
0x180096837  xor     ebx, esi
0x180096839  bts     ebx, 7
0x18009683d  test    bl, 8
0x180096840  jz      loc_180096902
0x180096846  test    edi, 20000015h
0x18009684c  jz      short loc_1800968C9
0x18009684e  test    dil, 2
0x180096852  jnz     loc_18009696A
0x180096858  mov     eax, cs:g_CiDeveloperMode
0x18009685e  bt      eax, 11h
0x180096862  jb      loc_180096986
0x180096868  bt      eax, 12h
0x18009686c  jb      loc_18009691F
0x180096872  mov     r8d, ebx
0x180096875  bt      edi, 18h
0x180096879  jb      loc_18009699E
0x18009687f  bt      eax, 0Fh
0x180096883  jb      loc_1800969CC
0x180096889  mov     eax, r8d
0x18009688c  shl     eax, 0Ch
0x18009688f  xor     eax, r8d
0x180096892  and     eax, 1000h
0x180096897  xor     eax, r8d
0x18009689a  mov     ecx, eax
0x18009689c  test    dil, 40h
0x1800968a0  jnz     loc_1800969FC
0x1800968a6  mov     eax, ecx
0x1800968a8  add     rsp, 28h
0x1800968ac  pop     r14
0x1800968ae  pop     r12
0x1800968b0  pop     rdi
0x1800968b1  pop     rsi
0x1800968b2  pop     rbp
0x1800968b3  pop     rbx
0x1800968b4  retn
0x1800968b6  mov     al, dil
0x1800968b9  not     al
0x1800968bb  movzx   ecx, al
0x1800968be  shr     ecx, 6
0x1800968c1  and     ecx, r12d
0x1800968c4  jmp     loc_1800967F3
0x1800968c9  mov     rcx, rbp
0x1800968cc  call    cs:__imp_PsIsProtectedProcessLight
0x1800968d3  nop     dword ptr [rax+rax+00h]
0x1800968d8  test    eax, eax
0x1800968da  jz      loc_18009684E
0x1800968e0  or      ebx, 40h
0x1800968e3  jmp     loc_180096858
0x1800968e8  lea     r9, [rsp+58h+arg_10]
0x1800968ed  call    CipShouldConsiderAsUntrustedSource
0x1800968f2  test    al, al
0x1800968f4  jz      loc_1800967C7
0x1800968fa  or      edi, 40h
0x1800968fd  jmp     loc_1800967C7
0x180096902  xor     eax, eax
0x180096904  bt      edi, 1Dh
0x180096908  jb      short loc_180096912
0x18009690a  test    dil, 2
0x18009690e  cmovz   eax, r12d
0x180096912  and     ebx, 0FFFFFFF7h
0x180096915  shl     eax, 3
0x180096918  or      ebx, eax
0x18009691a  jmp     loc_180096846
0x18009691f  mov     rcx, cs:g_CipWhichLevelComparisons
0x180096926  or      ebx, 10h
0x180096929  movzx   r8d, [rsp+58h+arg_20]
0x180096932  and     r8d, 0Fh
0x180096936  mov     edx, [rcx+30h]
0x180096939  bt      edx, r8d
0x18009693d  jnb     loc_180096872
0x180096943  and     ebx, 0FFFFFFFCh
0x180096946  jmp     loc_180096872
0x18009694b  test    cs:g_CiTestFlags, 400h
0x180096955  jz      loc_1800967D5
0x18009695b  or      edi, 40h
0x18009695e  jmp     loc_1800967D5
0x180096963  xor     edx, edx
0x180096965  jmp     loc_180096825
0x18009696a  mov     rcx, rbp
0x18009696d  call    cs:__imp_PsIsSystemProcess
0x180096974  nop     dword ptr [rax+rax+00h]
0x180096979  test    al, al
0x18009697b  jz      loc_180096858
0x180096981  jmp     loc_1800968E0
0x180096986  or      ebx, 224h
0x18009698c  test    bl, 8
0x18009698f  jz      loc_180096868
0x180096995  bts     ebx, 0Ah
0x180096999  jmp     loc_180096868
0x18009699e  bt      eax, 16h
0x1800969a2  jnb     loc_18009687F
0x1800969a8  test    edi, 0E41FFF8Fh
0x1800969ae  setz    dl
0x1800969b1  test    bl, 40h
0x1800969b4  setz    cl
0x1800969b7  bts     r8d, 0Bh
0x1800969bc  test    cl, dl
0x1800969be  cmovz   r8d, ebx
0x1800969c2  btr     r8d, 7
0x1800969c7  jmp     loc_18009687F
0x1800969cc  mov     rax, [r14+8]
0x1800969d0  or      r8d, 210h
0x1800969d7  test    dword ptr [rax+30h], 100h
0x1800969de  jz      short loc_1800969F0
0x1800969e0  and     r8d, 0FFFFFF7Ch
0x1800969e7  or      r8d, 24h
0x1800969eb  jmp     loc_180096889
0x1800969f0  or      r8d, 0A4h
0x1800969f7  jmp     loc_180096889
0x1800969fc  shl     ecx, 0Ah
0x1800969ff  xor     ecx, eax
0x180096a01  and     ecx, 2000h
0x180096a07  xor     ecx, eax
0x180096a09  jmp     loc_1800968A6
```
