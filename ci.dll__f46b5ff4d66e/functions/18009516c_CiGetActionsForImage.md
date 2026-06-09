# CiGetActionsForImage

- ea: `0x18009516c`
- end: `0x1800953de`
- name: `CiGetActionsForImage`
- size: `626`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f96c`
- `0x1800603a0`
- `0x180095950`
- `0x1800e55e0`

## callees

- `0x180010128`
- `0x180056008`
- `0x18009516c`
- `0x1800953e4`

## import_xrefs

- `ntoskrnl!PsIsSystemProcess` at `0x18009533d`
- `ntoskrnl!PsIsSystemProcess` at `0x18009533d`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x18009529c`
- `ntoskrnl!PsIsProtectedProcessLight` at `0x18009529c`

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
0x18009516c  push    rbx
0x18009516e  push    rbp
0x18009516f  push    rsi
0x180095170  push    rdi
0x180095171  push    r12
0x180095173  push    r14
0x180095175  sub     rsp, 28h
0x180095179  mov     [rsp+58h+arg_10], 0
0x180095181  mov     bl, r9b
0x180095184  mov     edi, r8d
0x180095187  mov     r14, rdx
0x18009518a  mov     rbp, rcx
0x18009518d  test    r8b, 40h
0x180095191  jz      loc_1800952B8
0x180095197  mov     eax, cs:g_CiOptions
0x18009519d  test    al, 8
0x18009519f  jnz     loc_18009531B
0x1800951a5  mov     r12d, 1
0x1800951ab  test    edi, 0E000000Fh
0x1800951b1  jnz     short loc_1800951C1
0x1800951b3  cmp     [rsp+58h+arg_20], 5
0x1800951bb  jnz     loc_180095286
0x1800951c1  xor     ecx, ecx
0x1800951c3  mov     eax, [rsp+58h+arg_10]
0x1800951c7  and     eax, 0FFFFFFFEh
0x1800951ca  or      eax, ecx
0x1800951cc  lea     ecx, [rax+rax]
0x1800951cf  xor     ecx, eax
0x1800951d1  lea     esi, ds:0[rax*8]
0x1800951d8  and     ecx, 2
0x1800951db  xor     ecx, eax
0x1800951dd  xor     esi, ecx
0x1800951df  and     esi, 8
0x1800951e2  xor     esi, ecx
0x1800951e4  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800951e9  mov     ecx, edi
0x1800951eb  test    eax, eax
0x1800951ed  jz      loc_180095333
0x1800951f3  mov     dl, bl
0x1800951f5  call    CipUsePageHashesForImage
0x1800951fa  movzx   eax, al
0x1800951fd  mov     ebx, esi
0x1800951ff  shl     eax, 2
0x180095202  xor     ebx, eax
0x180095204  and     ebx, 4
0x180095207  xor     ebx, esi
0x180095209  bts     ebx, 7
0x18009520d  test    bl, 8
0x180095210  jz      loc_1800952D2
0x180095216  test    edi, 20000015h
0x18009521c  jz      short loc_180095299
0x18009521e  test    dil, 2
0x180095222  jnz     loc_18009533A
0x180095228  mov     eax, cs:g_CiDeveloperMode
0x18009522e  bt      eax, 11h
0x180095232  jb      loc_180095356
0x180095238  bt      eax, 12h
0x18009523c  jb      loc_1800952EF
0x180095242  mov     r8d, ebx
0x180095245  bt      edi, 18h
0x180095249  jb      loc_18009536E
0x18009524f  bt      eax, 0Fh
0x180095253  jb      loc_18009539C
0x180095259  mov     eax, r8d
0x18009525c  shl     eax, 0Ch
0x18009525f  xor     eax, r8d
0x180095262  and     eax, 1000h
0x180095267  xor     eax, r8d
0x18009526a  mov     ecx, eax
0x18009526c  test    dil, 40h
0x180095270  jnz     loc_1800953CC
0x180095276  mov     eax, ecx
0x180095278  add     rsp, 28h
0x18009527c  pop     r14
0x18009527e  pop     r12
0x180095280  pop     rdi
0x180095281  pop     rsi
0x180095282  pop     rbp
0x180095283  pop     rbx
0x180095284  retn
0x180095286  mov     al, dil
0x180095289  not     al
0x18009528b  movzx   ecx, al
0x18009528e  shr     ecx, 6
0x180095291  and     ecx, r12d
0x180095294  jmp     loc_1800951C3
0x180095299  mov     rcx, rbp
0x18009529c  call    cs:__imp_PsIsProtectedProcessLight
0x1800952a3  nop     dword ptr [rax+rax+00h]
0x1800952a8  test    eax, eax
0x1800952aa  jz      loc_18009521E
0x1800952b0  or      ebx, 40h
0x1800952b3  jmp     loc_180095228
0x1800952b8  lea     r9, [rsp+58h+arg_10]
0x1800952bd  call    CipShouldConsiderAsUntrustedSource
0x1800952c2  test    al, al
0x1800952c4  jz      loc_180095197
0x1800952ca  or      edi, 40h
0x1800952cd  jmp     loc_180095197
0x1800952d2  xor     eax, eax
0x1800952d4  bt      edi, 1Dh
0x1800952d8  jb      short loc_1800952E2
0x1800952da  test    dil, 2
0x1800952de  cmovz   eax, r12d
0x1800952e2  and     ebx, 0FFFFFFF7h
0x1800952e5  shl     eax, 3
0x1800952e8  or      ebx, eax
0x1800952ea  jmp     loc_180095216
0x1800952ef  mov     rcx, cs:g_CipWhichLevelComparisons
0x1800952f6  or      ebx, 10h
0x1800952f9  movzx   r8d, [rsp+58h+arg_20]
0x180095302  and     r8d, 0Fh
0x180095306  mov     edx, [rcx+30h]
0x180095309  bt      edx, r8d
0x18009530d  jnb     loc_180095242
0x180095313  and     ebx, 0FFFFFFFCh
0x180095316  jmp     loc_180095242
0x18009531b  test    cs:g_CiTestFlags, 400h
0x180095325  jz      loc_1800951A5
0x18009532b  or      edi, 40h
0x18009532e  jmp     loc_1800951A5
0x180095333  xor     edx, edx
0x180095335  jmp     loc_1800951F5
0x18009533a  mov     rcx, rbp
0x18009533d  call    cs:__imp_PsIsSystemProcess
0x180095344  nop     dword ptr [rax+rax+00h]
0x180095349  test    al, al
0x18009534b  jz      loc_180095228
0x180095351  jmp     loc_1800952B0
0x180095356  or      ebx, 224h
0x18009535c  test    bl, 8
0x18009535f  jz      loc_180095238
0x180095365  bts     ebx, 0Ah
0x180095369  jmp     loc_180095238
0x18009536e  bt      eax, 16h
0x180095372  jnb     loc_18009524F
0x180095378  test    edi, 0E41FFF8Fh
0x18009537e  setz    dl
0x180095381  test    bl, 40h
0x180095384  setz    cl
0x180095387  bts     r8d, 0Bh
0x18009538c  test    cl, dl
0x18009538e  cmovz   r8d, ebx
0x180095392  btr     r8d, 7
0x180095397  jmp     loc_18009524F
0x18009539c  mov     rax, [r14+8]
0x1800953a0  or      r8d, 210h
0x1800953a7  test    dword ptr [rax+30h], 100h
0x1800953ae  jz      short loc_1800953C0
0x1800953b0  and     r8d, 0FFFFFF7Ch
0x1800953b7  or      r8d, 24h
0x1800953bb  jmp     loc_180095259
0x1800953c0  or      r8d, 0A4h
0x1800953c7  jmp     loc_180095259
0x1800953cc  shl     ecx, 0Ah
0x1800953cf  xor     ecx, eax
0x1800953d1  and     ecx, 2000h
0x1800953d7  xor     ecx, eax
0x1800953d9  jmp     loc_180095276
```
