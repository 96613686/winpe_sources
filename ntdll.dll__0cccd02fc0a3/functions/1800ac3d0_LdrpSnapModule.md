# LdrpSnapModule

- ea: `0x1800ac3d0`
- end: `0x1800ac98c`
- name: `LdrpSnapModule`
- size: `1468`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025698`
- `0x18011a39c`

## callees

- `0x18001eb80`
- `0x180025ed0`
- `0x180025f0c`
- `0x180025f50`
- `0x180029120`
- `0x180029b70`
- `0x180041690`
- `0x180050260`
- `0x180050ed0`
- `0x180066020`
- `0x180067250`
- `0x1800ac3d0`
- `0x1800ac994`
- `0x1800aca30`
- `0x1800acb14`
- `0x1800d4320`
- `0x1800d9520`
- `0x18015ae38`
- `0x18015e810`
- `0x180162000`
- `0x18016f030`

## string_xrefs

- `0x1800ac861`: `Import '%s' of DLL '%wZ' is redirected to 0x%p`
- `0x1800ac7ff`: `DLL "%wZ" does not contain an export table\n`

## pseudocode

```c
__int64 __fastcall LdrpSnapModule(__int64 a1)
{
  __int64 v2; // r13
  __int64 v3; // r12
  __int64 v4; // rax
  __int64 v5; // r14
  __int64 v6; // r15
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 *v9; // rax
  __int64 *v10; // r14
  __int64 v11; // r12
  _DWORD *v12; // rdx
  __int64 v13; // rcx
  char *v14; // r8
  __int64 v15; // r9
  __int64 v16; // rax
  unsigned int *v17; // r14
  int v18; // ebx
  __int64 v19; // r12
  unsigned __int64 v20; // r14
  int v21; // ecx
  int v22; // eax
  __int64 v23; // rax
  __int64 *v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // eax
  __int64 v29; // r14
  __int64 v30; // rax
  int v31; // [rsp+44h] [rbp-114h]
  unsigned int v32; // [rsp+48h] [rbp-110h] BYREF
  unsigned int v33; // [rsp+4Ch] [rbp-10Ch]
  __int64 *v34; // [rsp+50h] [rbp-108h]
  char ArgList[8]; // [rsp+58h] [rbp-100h]
  int v36; // [rsp+60h] [rbp-F8h]
  unsigned int *v37; // [rsp+68h] [rbp-F0h]
  _DWORD *v38; // [rsp+70h] [rbp-E8h]
  __int64 v39; // [rsp+78h] [rbp-E0h]
  unsigned __int64 v40; // [rsp+80h] [rbp-D8h]
  char *v41; // [rsp+88h] [rbp-D0h]
  __int64 v42; // [rsp+90h] [rbp-C8h]
  __int64 v43; // [rsp+98h] [rbp-C0h]
  __int64 v44; // [rsp+A0h] [rbp-B8h]
  __int64 v45; // [rsp+A8h] [rbp-B0h]
  __int64 v46; // [rsp+B0h] [rbp-A8h]
  __int64 v47; // [rsp+B8h] [rbp-A0h]
  __int64 v48; // [rsp+C0h] [rbp-98h]
  __int64 v49; // [rsp+C8h] [rbp-90h]
  _QWORD v50[8]; // [rsp+D0h] [rbp-88h] BYREF

  v48 = a1;
  v32 = 0;
  v40 = 0;
  v2 = *(_QWORD *)(a1 + 56);
  v3 = *(_QWORD *)(v2 + 48);
  v49 = v3;
  v47 = v2 + 72;
  LdrpLogDllState(v3, v2 + 72, 5286);
  LdrpHandlePendingModuleReplaced(a1);
  memset_thunk_772440563353939046(v50, 0, 0x40u);
  v31 = 0;
  v33 = 0;
  while ( 1 )
  {
    v4 = *(unsigned int *)(a1 + 128);
    if ( (unsigned int)v4 >= *(_DWORD *)(a1 + 104) )
    {
      v18 = LdrpDoPostSnapWork(a1);
      if ( v18 >= 0 )
      {
        LdrpLogDllState(*(_QWORD *)(v2 + 48), v2 + 72, 5287);
        *(_DWORD *)(*(_QWORD *)(v2 + 152) + 56LL) = 5;
      }
      goto LABEL_36;
    }
    _mm_lfence();
    v5 = (unsigned int)v4;
    v6 = LdrpHandleReplacedModule(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v4));
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v5) != v6 )
    {
      LdrpFreeReplacedModule();
      *(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * v5) = v6;
    }
    v7 = *(_QWORD *)(a1 + 136);
    v8 = *(unsigned int *)(v7 + 20 * v5);
    v9 = (__int64 *)(v3 + *(unsigned int *)(v7 + 20 * v5 + 16));
    v34 = v9;
    if ( !(_DWORD)v8 || (v10 = (__int64 *)(v3 + v8), (unsigned int)v8 > *(_DWORD *)(v2 + 64)) )
      v10 = v9;
    if ( v6 )
      break;
LABEL_27:
    ++*(_DWORD *)(a1 + 128);
  }
  v11 = *(_QWORD *)(v6 + 48);
  v39 = v11;
  LOBYTE(v8) = 1;
  v12 = (_DWORD *)RtlImageDirectoryEntryToData(v11, v8, 0, &v32);
  v38 = v12;
  if ( v12 )
  {
    v13 = 0;
    do
    {
      if ( !v50[v13] )
        break;
      if ( v11 == v50[v13] )
        break;
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < 8 );
    if ( (_DWORD)v13 == 8 || !v50[v13] )
    {
      RtlGuardCheckImageBase(v11, 0);
      v50[v31] = v11;
      v31 = ((_BYTE)v31 + 1) & 7;
      v12 = v38;
    }
    v14 = (char *)v12 + v32;
    v41 = v14;
    v15 = v11 + (unsigned int)v12[7];
    v42 = v15;
    v36 = v12[6];
    v46 = v11 + (unsigned int)v12[8];
    v45 = v11 + (unsigned int)v12[9];
    v16 = *(unsigned int *)(a1 + 132);
    v17 = (unsigned int *)&v10[v16];
    v34 = (__int64 *)((char *)v34 + v16 * 8);
    while ( 1 )
    {
      v37 = v17;
      if ( !*(_QWORD *)v17 )
      {
        *(_DWORD *)(a1 + 132) = 0;
        v3 = v49;
        goto LABEL_27;
      }
      v18 = -1073741702;
      v19 = *(_QWORD *)v17 >> 63;
      v20 = -4530927;
      v21 = *v37;
      if ( (_BYTE)v19 )
        break;
      v25 = *v37;
      v43 = v25;
      v44 = *(_QWORD *)(v2 + 48);
      v26 = v44 + v25 + 2;
      *(_QWORD *)ArgList = v26;
      if ( (*(_DWORD *)(a1 + 32) & 0x2000000) != 0 )
      {
        v20 = LdrpCheckRedirection(v2, v6, v26);
        if ( v20 != -4530927 )
        {
          LdrpLogInternal(
            (int)"minkernel\\ldr\\ldrsnap.c",
            3511,
            (int)"LdrpSnapModule",
            2,
            "Import '%s' of DLL '%wZ' is redirected to 0x%p",
            ArgList[0]);
          goto LABEL_22;
        }
        LOBYTE(v26) = ArgList[0];
      }
      v22 = LdrpNameToOrdinal(v26, v46, v45);
      if ( v22 >= 0 )
      {
        v12 = v38;
        v14 = v41;
        v15 = v42;
        goto LABEL_19;
      }
LABEL_21:
      if ( v18 < 0 )
      {
        if ( v18 == -1073741702 || v18 == -1073741515 )
        {
          if ( (unsigned int)CompatCachepLookupCdb(*(wchar_t **)(v2 + 80))
            || (unsigned int)CompatCachepLookupCdb(*(wchar_t **)(v6 + 80)) )
          {
            v29 = v2 + 72;
            LdrpLogLoadFailureEtwEvent(v2 + 72, v6 + 72, 1, (unsigned int)LoadFailure, 0);
            LdrpLogLoadFailureEtwEvent(v2 + 72, v6 + 72, 1, (unsigned int)LoadFailureOperational, 1);
          }
          else
          {
            v29 = v47;
          }
          if ( (_BYTE)v19 )
          {
            v18 = -1073741512;
            v30 = v33;
          }
          else
          {
            v18 = -1073741511;
            v30 = *(_QWORD *)ArgList;
          }
          LdrpReportError(v29, v30, ((unsigned __int8)v19 ^ 1u) - 1073741512);
        }
        goto LABEL_36;
      }
LABEL_22:
      v23 = RtlpHpRedirectHeapExport(v20);
      v24 = v34;
      *v34 = v23;
      v17 = v37 + 2;
      v34 = v24 + 1;
      ++*(_DWORD *)(a1 + 132);
      v12 = v38;
      v14 = v41;
      v15 = v42;
    }
    *(_QWORD *)ArgList = 0;
    v33 = (unsigned __int16)v21;
    v22 = (unsigned __int16)v21 - v12[4];
LABEL_19:
    if ( (unsigned int)v22 < v12[5] )
    {
      if ( *(_DWORD *)(v15 + 4LL * v22) )
      {
        v20 = v39 + *(unsigned int *)(v15 + 4LL * v22);
        v18 = 0;
        if ( v20 < (unsigned __int64)v14 && v20 > (unsigned __int64)v12 )
        {
          v27 = LdrpResolveForwarder((char *)v20);
          v18 = v27;
          if ( v27 == 259 )
            return 0;
          if ( v27 >= 0 )
            v20 = v40;
        }
      }
    }
    goto LABEL_21;
  }
  LdrpLogInternal(
    (int)"minkernel\\ldr\\ldrsnap.c",
    3413,
    (int)"LdrpSnapModule",
    0,
    "DLL \"%wZ\" does not contain an export table\n",
    v6 + 72);
  v18 = -1073741701;
LABEL_36:
  if ( *(_QWORD *)(a1 + 192) )
  {
    NtUnmapViewOfSection(-1);
    *(_QWORD *)(a1 + 192) = 0;
  }
  if ( v18 < 0 )
    LdrpLogError((unsigned int)v18, 25, 0, a1);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1800ac3d0  push    rbx
0x1800ac3d2  push    rsi
0x1800ac3d3  push    r12
0x1800ac3d5  push    r13
0x1800ac3d7  push    r14
0x1800ac3d9  push    r15
0x1800ac3db  sub     rsp, 128h
0x1800ac3e2  mov     rax, cs:__security_cookie
0x1800ac3e9  xor     rax, rsp
0x1800ac3ec  mov     [rsp+158h+var_48], rax
0x1800ac3f4  mov     rsi, rcx
0x1800ac3f7  mov     [rsp+158h+var_98], rcx
0x1800ac3ff  mov     [rsp+158h+var_110], 0
0x1800ac407  mov     [rsp+158h+var_D8], 0
0x1800ac413  mov     r13, [rcx+38h]
0x1800ac417  mov     r12, [r13+30h]
0x1800ac41b  mov     [rsp+158h+var_90], r12
0x1800ac423  lea     r14, [r13+48h]
0x1800ac427  mov     [rsp+158h+var_A0], r14
0x1800ac42f  mov     r8d, 14A6h
0x1800ac435  mov     rdx, r14
0x1800ac438  mov     rcx, r12
0x1800ac43b  call    LdrpLogDllState
0x1800ac440  mov     rcx, rsi
0x1800ac443  call    LdrpHandlePendingModuleReplaced
0x1800ac448  xor     edx, edx; Val
0x1800ac44a  lea     r8d, [rdx+40h]; Size
0x1800ac44e  lea     rcx, [rsp+158h+var_88]; void *
0x1800ac456  call    memset$thunk$772440563353939046
0x1800ac45b  mov     [rsp+158h+var_114], 0
0x1800ac463  xor     ebx, ebx
0x1800ac465  xor     eax, eax
0x1800ac467  mov     [rsp+158h+var_10C], eax
0x1800ac46b  mov     eax, [rsi+80h]
0x1800ac471  cmp     eax, [rsi+68h]
0x1800ac474  jnb     loc_1800AC735
0x1800ac47a  lfence
0x1800ac47d  mov     r14d, eax
0x1800ac480  mov     rcx, [rsi+58h]
0x1800ac484  mov     rcx, [rcx+rax*8]
0x1800ac488  call    LdrpHandleReplacedModule
0x1800ac48d  mov     r15, rax
0x1800ac490  mov     rax, [rsi+58h]
0x1800ac494  mov     rcx, [rax+r14*8]
0x1800ac498  cmp     rcx, r15
0x1800ac49b  jnz     loc_1800AC7DC
0x1800ac4a1  lea     rcx, [r14+r14*4]
0x1800ac4a5  mov     rax, [rsi+88h]
0x1800ac4ac  mov     edx, [rax+rcx*4]
0x1800ac4af  mov     eax, [rax+rcx*4+10h]
0x1800ac4b3  add     rax, r12
0x1800ac4b6  mov     [rsp+158h+var_108], rax
0x1800ac4bb  test    edx, edx
0x1800ac4bd  jz      loc_1800AC7EE
0x1800ac4c3  cmp     edx, [r13+40h]
0x1800ac4c7  lea     r14, [r12+rdx]
0x1800ac4cb  ja      loc_1800AC7EE
0x1800ac4d1  test    r15, r15
0x1800ac4d4  jz      loc_1800AC6D2
0x1800ac4da  mov     r12, [r15+30h]
0x1800ac4de  mov     [rsp+158h+var_E0], r12
0x1800ac4e3  xor     r8d, r8d
0x1800ac4e6  lea     r9, [rsp+158h+var_110]
0x1800ac4eb  mov     dl, 1
0x1800ac4ed  mov     rcx, r12
0x1800ac4f0  call    RtlImageDirectoryEntryToData
0x1800ac4f5  mov     rdx, rax
0x1800ac4f8  mov     [rsp+158h+var_E8], rax
0x1800ac4fd  test    rax, rax
0x1800ac500  jz      loc_1800AC7F6
0x1800ac506  xor     ecx, ecx
0x1800ac508  cmp     [rsp+rcx*8+158h+var_88], 0
0x1800ac511  jz      short loc_1800AC524
0x1800ac513  cmp     r12, [rsp+rcx*8+158h+var_88]
0x1800ac51b  jz      short loc_1800AC524
0x1800ac51d  inc     ecx
0x1800ac51f  cmp     ecx, 8
0x1800ac522  jb      short loc_1800AC508
0x1800ac524  cmp     ecx, 8
0x1800ac527  jz      loc_1800AC7B3
0x1800ac52d  cmp     [rsp+rcx*8+158h+var_88], 0
0x1800ac536  jz      loc_1800AC7B3
0x1800ac53c  mov     r8d, [rsp+158h+var_110]
0x1800ac541  add     r8, rdx
0x1800ac544  mov     [rsp+158h+var_D0], r8
0x1800ac54c  mov     r9d, [rdx+1Ch]
0x1800ac550  add     r9, r12
0x1800ac553  mov     [rsp+158h+var_C8], r9
0x1800ac55b  mov     eax, [rdx+18h]
0x1800ac55e  mov     [rsp+158h+var_F8], eax
0x1800ac562  mov     eax, [rdx+20h]
0x1800ac565  add     rax, r12
0x1800ac568  mov     [rsp+158h+var_A8], rax
0x1800ac570  mov     eax, [rdx+24h]
0x1800ac573  add     rax, r12
0x1800ac576  mov     [rsp+158h+var_B0], rax
0x1800ac57e  mov     eax, [rsi+84h]
0x1800ac584  shl     rax, 3
0x1800ac588  add     r14, rax
0x1800ac58b  add     [rsp+158h+var_108], rax
0x1800ac590  mov     [rsp+158h+var_F0], r14
0x1800ac595  mov     r12, [r14]
0x1800ac598  test    r12, r12
0x1800ac59b  jz      loc_1800AC6C0
0x1800ac5a1  mov     ebx, 0C000007Ah
0x1800ac5a6  mov     [rsp+158h+var_118], ebx
0x1800ac5aa  shr     r12, 3Fh
0x1800ac5ae  mov     r14, 0FFFFFFFFFFBADD11h
0x1800ac5b5  mov     rax, [rsp+158h+var_F0]
0x1800ac5ba  mov     ecx, [rax]
0x1800ac5bc  test    r12b, r12b
0x1800ac5bf  jz      short loc_1800AC62E
0x1800ac5c1  xor     eax, eax
0x1800ac5c3  mov     qword ptr [rsp+158h+var_100], rax
0x1800ac5c8  movzx   eax, cx
0x1800ac5cb  mov     [rsp+158h+var_10C], eax
0x1800ac5cf  sub     eax, [rdx+10h]
0x1800ac5d2  cmp     eax, [rdx+14h]
0x1800ac5d5  jnb     short loc_1800AC5E4
0x1800ac5d7  cdqe
0x1800ac5d9  cmp     dword ptr [r9+rax*4], 0
0x1800ac5de  jnz     loc_1800AC6DD
0x1800ac5e4  test    ebx, ebx
0x1800ac5e6  js      loc_1800AC8A3
0x1800ac5ec  mov     rcx, r14
0x1800ac5ef  call    RtlpHpRedirectHeapExport
0x1800ac5f4  mov     rcx, [rsp+158h+var_108]
0x1800ac5f9  mov     [rcx], rax
0x1800ac5fc  mov     r14, [rsp+158h+var_F0]
0x1800ac601  add     r14, 8
0x1800ac605  add     rcx, 8
0x1800ac609  mov     [rsp+158h+var_108], rcx
0x1800ac60e  inc     dword ptr [rsi+84h]
0x1800ac614  mov     rdx, [rsp+158h+var_E8]
0x1800ac619  mov     r8, [rsp+158h+var_D0]
0x1800ac621  mov     r9, [rsp+158h+var_C8]
0x1800ac629  jmp     loc_1800AC590
0x1800ac62e  mov     rax, rcx
0x1800ac631  mov     [rsp+158h+var_C0], rcx
0x1800ac639  mov     rcx, [r13+30h]
0x1800ac63d  mov     [rsp+158h+var_B8], rcx
0x1800ac645  add     rax, 2
0x1800ac649  add     rax, rcx
0x1800ac64c  mov     qword ptr [rsp+158h+var_100], rax
0x1800ac651  test    dword ptr [rsi+20h], 2000000h
0x1800ac658  jnz     loc_1800AC830
0x1800ac65e  mov     rcx, [rsp+158h+var_C0]
0x1800ac666  mov     rdx, [rsp+158h+var_B8]
0x1800ac66e  movzx   edx, word ptr [rcx+rdx]
0x1800ac672  mov     rcx, [rsp+158h+var_B0]
0x1800ac67a  mov     qword ptr [rsp+158h+ArgList], rcx; __int64
0x1800ac67f  mov     rcx, [rsp+158h+var_A8]
0x1800ac687  mov     [rsp+158h+Format], rcx; __int64
0x1800ac68c  mov     r9d, [rsp+158h+var_F8]
0x1800ac691  mov     r8, [rsp+158h+var_E0]
0x1800ac696  mov     rcx, rax; ArgList
0x1800ac699  call    LdrpNameToOrdinal
0x1800ac69e  test    eax, eax
0x1800ac6a0  js      loc_1800AC5E4
0x1800ac6a6  mov     rdx, [rsp+158h+var_E8]
0x1800ac6ab  mov     r8, [rsp+158h+var_D0]
0x1800ac6b3  mov     r9, [rsp+158h+var_C8]
0x1800ac6bb  jmp     loc_1800AC5D2
0x1800ac6c0  mov     dword ptr [rsi+84h], 0
0x1800ac6ca  mov     r12, [rsp+158h+var_90]
0x1800ac6d2  inc     dword ptr [rsi+80h]
0x1800ac6d8  jmp     loc_1800AC46B
0x1800ac6dd  mov     r14d, [r9+rax*4]
0x1800ac6e1  add     r14, [rsp+158h+var_E0]
0x1800ac6e6  xor     ebx, ebx
0x1800ac6e8  mov     [rsp+158h+var_118], ebx
0x1800ac6ec  cmp     r14, r8
0x1800ac6ef  jnb     loc_1800AC5E4
0x1800ac6f5  cmp     r14, rdx
0x1800ac6f8  jbe     loc_1800AC5E4
0x1800ac6fe  lea     r9, [rsp+158h+var_D8]
0x1800ac706  mov     r8, r13
0x1800ac709  mov     rdx, r15
0x1800ac70c  mov     rcx, r14; Str
0x1800ac70f  call    LdrpResolveForwarder
0x1800ac714  mov     ebx, eax
0x1800ac716  mov     [rsp+158h+var_118], eax
0x1800ac71a  cmp     eax, 103h
0x1800ac71f  jz      loc_1800AC89C
0x1800ac725  test    eax, eax
0x1800ac727  cmovns  r14, [rsp+158h+var_D8]
0x1800ac730  jmp     loc_1800AC5E4
0x1800ac735  test    ebx, ebx
0x1800ac737  js      short loc_1800AC768
0x1800ac739  mov     rcx, rsi
0x1800ac73c  call    LdrpDoPostSnapWork
0x1800ac741  mov     ebx, eax
0x1800ac743  test    eax, eax
0x1800ac745  js      short loc_1800AC768
0x1800ac747  mov     r8d, 14A7h
0x1800ac74d  lea     rdx, [r13+48h]
0x1800ac751  mov     rcx, [r13+30h]
0x1800ac755  call    LdrpLogDllState
0x1800ac75a  mov     rax, [r13+98h]
0x1800ac761  mov     dword ptr [rax+38h], 5
0x1800ac768  mov     rdx, [rsi+0C0h]
0x1800ac76f  test    rdx, rdx
0x1800ac772  jnz     loc_1800AC973
0x1800ac778  test    ebx, ebx
0x1800ac77a  jns     short loc_1800AC78E
0x1800ac77c  mov     edx, 19h
0x1800ac781  mov     r9, rsi
0x1800ac784  xor     r8d, r8d
0x1800ac787  mov     ecx, ebx
0x1800ac789  call    LdrpLogError
0x1800ac78e  mov     eax, ebx
0x1800ac790  mov     rcx, [rsp+158h+var_48]
0x1800ac798  xor     rcx, rsp; StackCookie
0x1800ac79b  call    __security_check_cookie
0x1800ac7a0  add     rsp, 128h
0x1800ac7a7  pop     r15
0x1800ac7a9  pop     r14
0x1800ac7ab  pop     r13
0x1800ac7ad  pop     r12
0x1800ac7af  pop     rsi
0x1800ac7b0  pop     rbx
0x1800ac7b1  retn
0x1800ac7b3  xor     edx, edx
0x1800ac7b5  mov     rcx, r12
0x1800ac7b8  call    RtlGuardCheckImageBase
0x1800ac7bd  mov     ecx, [rsp+158h+var_114]
0x1800ac7c1  mov     [rsp+rcx*8+158h+var_88], r12
0x1800ac7c9  inc     ecx
0x1800ac7cb  and     ecx, 7
0x1800ac7ce  mov     [rsp+158h+var_114], ecx
0x1800ac7d2  mov     rdx, [rsp+158h+var_E8]
0x1800ac7d7  jmp     loc_1800AC53C
0x1800ac7dc  call    LdrpFreeReplacedModule
0x1800ac7e1  mov     rax, [rsi+58h]
0x1800ac7e5  mov     [rax+r14*8], r15
0x1800ac7e9  jmp     loc_1800AC4A1
0x1800ac7ee  mov     r14, rax
0x1800ac7f1  jmp     loc_1800AC4D1
0x1800ac7f6  lea     rax, [r15+48h]
0x1800ac7fa  mov     qword ptr [rsp+158h+ArgList], rax; ArgList
0x1800ac7ff  lea     rax, aDllWzDoesNotCo; "DLL \"%wZ\" does not contain an export "...
0x1800ac806  mov     [rsp+158h+Format], rax; Format
0x1800ac80b  xor     r9d, r9d; int
0x1800ac80e  lea     r8, aLdrpsnapmodule; "LdrpSnapModule"
0x1800ac815  mov     edx, 0D55h; int
0x1800ac81a  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800ac821  call    LdrpLogInternal
0x1800ac826  mov     ebx, 0C000007Bh
0x1800ac82b  jmp     loc_1800AC768
0x1800ac830  mov     r8, rax
0x1800ac833  mov     rdx, r15
0x1800ac836  mov     rcx, r13
0x1800ac839  call    LdrpCheckRedirection
0x1800ac83e  mov     r14, rax
0x1800ac841  cmp     rax, 0FFFFFFFFFFBADD11h
0x1800ac847  jz      short loc_1800AC892
0x1800ac849  mov     [rsp+158h+var_120], rax
0x1800ac84e  lea     rax, [r13+48h]
0x1800ac852  mov     [rsp+158h+var_128], rax
0x1800ac857  mov     rax, qword ptr [rsp+158h+var_100]
0x1800ac85c  mov     qword ptr [rsp+158h+ArgList], rax; ArgList
0x1800ac861  lea     rax, aImportSOfDllWz; "Import '%s' of DLL '%wZ' is redirected "...
0x1800ac868  mov     [rsp+158h+Format], rax; Format
0x1800ac86d  mov     r9d, 2; int
0x1800ac873  lea     r8, aLdrpsnapmodule; "LdrpSnapModule"
0x1800ac87a  mov     edx, 0DB7h; int
0x1800ac87f  lea     rcx, aMinkernelLdrLd_4; "minkernel\\ldr\\ldrsnap.c"
0x1800ac886  call    LdrpLogInternal
0x1800ac88b  xor     ebx, ebx
0x1800ac88d  jmp     loc_1800AC5EC
0x1800ac892  mov     rax, qword ptr [rsp+158h+var_100]
0x1800ac897  jmp     loc_1800AC65E
0x1800ac89c  xor     eax, eax
0x1800ac89e  jmp     loc_1800AC790
0x1800ac8a3  cmp     ebx, 0C000007Ah
0x1800ac8a9  jz      short loc_1800AC8B7
0x1800ac8ab  cmp     ebx, 0C0000135h
0x1800ac8b1  jnz     loc_1800AC768
0x1800ac8b7  mov     ebx, 80h
0x1800ac8bc  mov     edx, ebx
0x1800ac8be  mov     rcx, [r13+50h]; Str
0x1800ac8c2  call    CompatCachepLookupCdb
0x1800ac8c7  test    eax, eax
0x1800ac8c9  jnz     short loc_1800AC8E4
0x1800ac8cb  mov     edx, ebx
0x1800ac8cd  mov     rcx, [r15+50h]; Str
0x1800ac8d1  call    CompatCachepLookupCdb
0x1800ac8d6  test    eax, eax
0x1800ac8d8  jnz     short loc_1800AC8E4
0x1800ac8da  mov     r14, [rsp+158h+var_A0]
0x1800ac8e2  jmp     short loc_1800AC925
0x1800ac8e4  mov     byte ptr [rsp+158h+Format], 0
0x1800ac8e9  lea     r9, LoadFailure
0x1800ac8f0  mov     r8d, 1
0x1800ac8f6  lea     rdx, [r15+48h]
0x1800ac8fa  lea     r14, [r13+48h]
0x1800ac8fe  mov     rcx, r14
0x1800ac901  call    LdrpLogLoadFailureEtwEvent
0x1800ac906  mov     byte ptr [rsp+158h+Format], 1
0x1800ac90b  lea     r9, LoadFailureOperational
  ... truncated ...
```
