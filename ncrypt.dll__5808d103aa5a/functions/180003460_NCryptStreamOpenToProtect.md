# NCryptStreamOpenToProtect

- ea: `0x180003460`
- end: `0x180003823`
- name: `NCryptStreamOpenToProtect`
- size: `963`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003150`
- `0x180003460`
- `0x18000382c`
- `0x180003a50`
- `0x180003a68`
- `0x180005f90`
- `0x180006be4`
- `0x18000d02c`
- `0x18000e120`
- `0x180016128`
- `0x18001f175`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptGenRandom` at `0x1800035ba`
- `bcrypt!BCryptGenRandom` at `0x1800035ba`

## string_xrefs

- `0x1800036bb`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x180003734`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`
- `0x1800037fe`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\stream.c`

## pseudocode

```c
__int64 __fastcall NCryptStreamOpenToProtect(_DWORD *a1, int a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  char *v8; // rdi
  _QWORD *v9; // r12
  unsigned int Settings; // eax
  unsigned int BCryptOidInfo; // ebx
  __int64 v12; // r15
  int v13; // edx
  __int64 v14; // rbx
  char *v15; // rax
  int v16; // edx
  __int128 v17; // xmm0
  int v18; // r8d
  __int64 v19; // rax
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int64 v23; // r9
  __int64 v24; // rcx
  char v25; // [rsp+30h] [rbp-61h]
  HLOCAL hMem; // [rsp+50h] [rbp-41h] BYREF
  __int64 v27; // [rsp+58h] [rbp-39h] BYREF
  __int64 v28; // [rsp+60h] [rbp-31h] BYREF
  _DWORD v29[4]; // [rsp+70h] [rbp-21h] BYREF
  char *v30; // [rsp+80h] [rbp-11h]
  char *v31; // [rsp+88h] [rbp-9h]
  unsigned int v32; // [rsp+F0h] [rbp+5Fh] BYREF
  __int64 v33; // [rsp+100h] [rbp+6Fh]

  v33 = a3;
  v28 = 0;
  v27 = 0;
  v8 = 0;
  memset_0(v29, 0, 0x40u);
  hMem = 0;
  v32 = 0;
  v9 = a5;
  v29[0] = 64;
  if ( !a5 || !a4 || !*a4 )
  {
    BCryptOidInfo = -2146893785;
    v23 = 157;
    v24 = 2148073511LL;
    goto LABEL_40;
  }
  if ( !a1 || *a1 != 40 )
  {
    BCryptOidInfo = -2146893786;
    v23 = 166;
    v24 = 2148073510LL;
    goto LABEL_40;
  }
  if ( (a2 & 0xDFFFFF3F) != 0 )
  {
    BCryptOidInfo = -2146893815;
    v23 = 178;
    v24 = 2148073481LL;
LABEL_40:
    DebugTraceError(v24, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c", v23);
    goto LABEL_19;
  }
  Settings = KeyProtRouter_GetSettings(&v27);
  BCryptOidInfo = Settings;
  if ( Settings )
  {
    v23 = 191;
    goto LABEL_36;
  }
  v12 = v27;
  BCryptOidInfo = CNG_FindBCryptOidInfo(
                    *(const void **)(*(_QWORD *)(v27 + 8) + 40LL),
                    *(_DWORD *)(*(_QWORD *)(v27 + 8) + 32LL),
                    1u,
                    &v28);
  if ( !BCryptOidInfo )
  {
    v14 = (unsigned int)(*(_DWORD *)(v28 + 56) + 7) >> 3;
    v15 = (char *)I_DefaultExtrenalAlloc(v14 + 192);
    v8 = v15;
    if ( !v15 )
    {
      BCryptOidInfo = -2146893810;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
          (unsigned int)"Status",
          14,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
          217);
      goto LABEL_19;
    }
    memset_0(v15, 0, v14 + 192);
    *(_QWORD *)v8 = 192;
    *((_QWORD *)v8 + 1) = &NCryptDefaultAllocPara;
    v17 = *(_OWORD *)a4;
    *(_QWORD *)(v8 + 36) = 1;
    *((_QWORD *)v8 + 9) = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)v8 + 7) = v33;
    *((_OWORD *)v8 + 1) = v17;
    *((_QWORD *)v8 + 16) = v8 + 192;
    *((_DWORD *)v8 + 30) = v14;
    *((_DWORD *)v8 + 16) = a2;
    Settings = BCryptGenRandom(0, (PUCHAR)v8 + 192, v14, 2u);
    BCryptOidInfo = Settings;
    if ( !Settings )
    {
      v19 = *(_QWORD *)(v12 + 8);
      v30 = v8 + 80;
      v31 = v8 + 120;
      *((_QWORD *)v8 + 11) = *(_QWORD *)(v19 + 40);
      v20 = *(unsigned int *)(*(_QWORD *)(v12 + 8) + 32LL);
      *((_DWORD *)v8 + 20) = v20;
      *((_QWORD *)v8 + 14) = *(_QWORD *)(v12 + 8);
      BCryptOidInfo = NCryptMsgCreate(v20, (__int64)&NCryptDefaultAllocPara, v18, v29, 0, 0, (_QWORD *)v8 + 9);
      if ( BCryptOidInfo )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 14;
          goto LABEL_18;
        }
      }
      else
      {
        BCryptOidInfo = I_AddRecipientsAndEncodeMessage(
                          *((_QWORD *)v8 + 9),
                          (__int64)a1,
                          *((_QWORD *)v8 + 16),
                          *((_DWORD *)v8 + 30),
                          (__int64)&NCryptDefaultAllocPara,
                          *((_QWORD *)v8 + 7),
                          (__int64)&hMem,
                          (__int64)&v32,
                          *((_DWORD *)v8 + 16));
        if ( !BCryptOidInfo )
        {
          Settings = ((__int64 (__fastcall *)(_QWORD, HLOCAL, _QWORD, _QWORD))*a4)(a4[1], hMem, v32, 0);
          BCryptOidInfo = Settings;
          if ( !Settings )
          {
            *v9 = v8;
            v8 = 0;
            goto LABEL_19;
          }
          v23 = 303;
          goto LABEL_36;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v25 = 31;
LABEL_18:
          WPP_SF_sDsd(
            v21[2],
            v13,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
            (unsigned int)"Status",
            BCryptOidInfo,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\stream.c",
            v25);
          goto LABEL_19;
        }
      }
      goto LABEL_19;
    }
    v23 = 244;
LABEL_36:
    v24 = Settings;
    goto LABEL_40;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v25 = -53;
    goto LABEL_18;
  }
LABEL_19:
  if ( hMem )
    I_DefaultExtrenalFree(hMem);
  if ( v8 )
    I_StreamFree(v8);
  return BCryptOidInfo;
}

```

## disassembly

```asm
0x180003460  mov     [rsp-8+arg_8], rbx
0x180003465  mov     [rsp-8+arg_10], r8
0x18000346a  push    rbp
0x18000346b  push    rsi
0x18000346c  push    rdi
0x18000346d  push    r12
0x18000346f  push    r13
0x180003471  push    r14
0x180003473  push    r15
0x180003475  lea     rbp, [rsp-1Fh]
0x18000347a  sub     rsp, 0B0h
0x180003481  xor     r12d, r12d
0x180003484  mov     r13d, edx
0x180003487  mov     r14, rcx
0x18000348a  mov     [rbp+4Fh+var_80], r12
0x18000348e  xor     edx, edx; Val
0x180003490  mov     [rbp+4Fh+var_88], r12
0x180003494  lea     rcx, [rbp+4Fh+var_70]; void *
0x180003498  mov     rsi, r9
0x18000349b  lea     ebx, [r12+40h]
0x1800034a0  mov     edi, r12d
0x1800034a3  mov     r8d, ebx; Size
0x1800034a6  call    memset_0
0x1800034ab  mov     [rbp+4Fh+hMem], r12
0x1800034af  mov     [rbp+4Fh+arg_0], r12d
0x1800034b3  mov     r12, [rbp+4Fh+arg_20]
0x1800034b7  mov     [rbp+4Fh+var_70], ebx
0x1800034ba  test    r12, r12
0x1800034bd  jz      loc_1800037EE
0x1800034c3  test    rsi, rsi
0x1800034c6  jz      loc_1800037EE
0x1800034cc  cmp     [rsi], rdi
0x1800034cf  jz      loc_1800037EE
0x1800034d5  test    r14, r14
0x1800034d8  jz      loc_1800037DC
0x1800034de  cmp     dword ptr [r14], 28h ; '('
0x1800034e2  jnz     loc_1800037DC
0x1800034e8  test    r13d, 0DFFFFF3Fh
0x1800034ef  jnz     loc_1800037B0
0x1800034f5  lea     rcx, [rbp+4Fh+var_88]
0x1800034f9  call    KeyProtRouter_GetSettings
0x1800034fe  mov     ebx, eax
0x180003500  test    eax, eax
0x180003502  jnz     loc_1800037C2
0x180003508  mov     r15, [rbp+4Fh+var_88]
0x18000350c  lea     r9, [rbp+4Fh+var_80]
0x180003510  lea     r8d, [rdi+1]
0x180003514  mov     rcx, [r15+8]
0x180003518  mov     edx, [rcx+20h]
0x18000351b  mov     rcx, [rcx+28h]
0x18000351f  call    CNG_FindBCryptOidInfo
0x180003524  mov     ebx, eax
0x180003526  test    eax, eax
0x180003528  jnz     loc_18000374A
0x18000352e  mov     rax, [rbp+4Fh+var_80]
0x180003532  mov     ecx, [rax+38h]
0x180003535  add     ecx, 7
0x180003538  shr     ecx, 3
0x18000353b  mov     ebx, ecx
0x18000353d  add     rcx, 0C0h
0x180003544  call    I_DefaultExtrenalAlloc
0x180003549  mov     rdi, rax
0x18000354c  test    rax, rax
0x18000354f  jz      loc_18000370E
0x180003555  lea     r8, [rbx+0C0h]; Size
0x18000355c  xor     edx, edx; Val
0x18000355e  mov     rcx, rax; void *
0x180003561  call    memset_0
0x180003566  lea     rax, NCryptDefaultAllocPara
0x18000356d  mov     qword ptr [rdi], 0C0h
0x180003574  mov     [rdi+8], rax
0x180003578  lea     rdx, [rdi+0C0h]; pbBuffer
0x18000357f  movups  xmm0, xmmword ptr [rsi]
0x180003582  xor     eax, eax
0x180003584  mov     qword ptr [rdi+24h], 1
0x18000358c  mov     [rdi+48h], rax
0x180003590  mov     r9d, 2; dwFlags
0x180003596  mov     [rdi+30h], rax
0x18000359a  mov     r8d, ebx; cbBuffer
0x18000359d  mov     rax, [rbp+4Fh+arg_10]
0x1800035a1  xor     ecx, ecx; hAlgorithm
0x1800035a3  mov     [rdi+38h], rax
0x1800035a7  movdqu  xmmword ptr [rdi+10h], xmm0
0x1800035ac  mov     [rdi+80h], rdx
0x1800035b3  mov     [rdi+78h], ebx
0x1800035b6  mov     [rdi+40h], r13d
0x1800035ba  call    cs:__imp_BCryptGenRandom
0x1800035c0  mov     ebx, eax
0x1800035c2  test    eax, eax
0x1800035c4  jnz     loc_1800037D4
0x1800035ca  mov     rax, [r15+8]
0x1800035ce  lea     rdx, [rdi+50h]
0x1800035d2  mov     [rbp+4Fh+var_60], rdx
0x1800035d6  lea     r13, [rdi+78h]
0x1800035da  lea     r9, [rbp+4Fh+var_70]
0x1800035de  mov     [rbp+4Fh+var_58], r13
0x1800035e2  mov     rcx, [rax+28h]
0x1800035e6  mov     [rdi+58h], rcx
0x1800035ea  mov     rax, [r15+8]
0x1800035ee  mov     ecx, [rax+20h]
0x1800035f1  mov     [rdx], ecx
0x1800035f3  lea     rdx, NCryptDefaultAllocPara
0x1800035fa  mov     rax, [r15+8]
0x1800035fe  lea     r15, [rdi+48h]
0x180003602  mov     [rsp+0E0h+var_B0], r15
0x180003607  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x18000360b  mov     [rsp+0E0h+var_C0], 0
0x180003614  mov     [rdi+70h], rax
0x180003618  call    NCryptMsgCreate
0x18000361d  mov     ebx, eax
0x18000361f  test    eax, eax
0x180003621  jnz     loc_180003782
0x180003627  mov     eax, [rdi+40h]
0x18000362a  mov     rdx, r14
0x18000362d  mov     r9d, [r13+0]
0x180003631  mov     r8, [rdi+80h]
0x180003638  mov     rcx, [r15]
0x18000363b  mov     [rsp+0E0h+var_A0], eax
0x18000363f  lea     rax, [rbp+4Fh+arg_0]
0x180003643  mov     [rsp+0E0h+var_A8], rax
0x180003648  lea     rax, [rbp+4Fh+hMem]
0x18000364c  mov     [rsp+0E0h+var_B0], rax
0x180003651  mov     rax, [rdi+38h]
0x180003655  mov     [rsp+0E0h+var_B8], rax
0x18000365a  lea     rax, NCryptDefaultAllocPara
0x180003661  mov     [rsp+0E0h+var_C0], rax
0x180003666  call    I_AddRecipientsAndEncodeMessage
0x18000366b  mov     ebx, eax
0x18000366d  test    eax, eax
0x18000366f  jnz     short loc_18000369A
0x180003671  mov     r8d, [rbp+4Fh+arg_0]
0x180003675  xor     r9d, r9d
0x180003678  mov     rdx, [rbp+4Fh+hMem]
0x18000367c  mov     rcx, [rsi+8]
0x180003680  mov     rax, [rsi]
0x180003683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003688  mov     ebx, eax
0x18000368a  test    eax, eax
0x18000368c  jnz     loc_1800037CA
0x180003692  mov     [r12], rdi
0x180003696  xor     edi, edi
0x180003698  jmp     short loc_1800036DB
0x18000369a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036a1  lea     rax, WPP_GLOBAL_Control
0x1800036a8  cmp     rcx, rax
0x1800036ab  jz      short loc_1800036DB
0x1800036ad  test    byte ptr [rcx+1Ch], 1
0x1800036b1  jz      short loc_1800036DB
0x1800036b3  mov     dword ptr [rsp+0E0h+var_B0], 11Fh
0x1800036bb  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800036c2  mov     [rsp+0E0h+var_B8], r8
0x1800036c7  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x1800036cb  mov     rcx, [rcx+10h]
0x1800036cf  lea     r9, aStatus; "Status"
0x1800036d6  call    WPP_SF_sDsd
0x1800036db  mov     rcx, [rbp+4Fh+hMem]; hMem
0x1800036df  test    rcx, rcx
0x1800036e2  jnz     loc_180003778
0x1800036e8  test    rdi, rdi
0x1800036eb  jnz     loc_180003816
0x1800036f1  mov     eax, ebx
0x1800036f3  mov     rbx, [rsp+0E0h+arg_8]
0x1800036fb  add     rsp, 0B0h
0x180003702  pop     r15
0x180003704  pop     r14
0x180003706  pop     r13
0x180003708  pop     r12
0x18000370a  pop     rdi
0x18000370b  pop     rsi
0x18000370c  pop     rbp
0x18000370d  retn
0x18000370e  mov     ebx, 8009000Eh
0x180003713  mov     rcx, cs:WPP_GLOBAL_Control
0x18000371a  lea     rax, WPP_GLOBAL_Control
0x180003721  cmp     rcx, rax
0x180003724  jz      short loc_1800036DB
0x180003726  test    byte ptr [rcx+1Ch], 1
0x18000372a  jz      short loc_1800036DB
0x18000372c  mov     dword ptr [rsp+0E0h+var_B0], 0D9h
0x180003734  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000373b  mov     [rsp+0E0h+var_B8], r8
0x180003740  mov     dword ptr [rsp+0E0h+var_C0], 8009000Eh
0x180003748  jmp     short loc_1800036CB
0x18000374a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003751  lea     rax, WPP_GLOBAL_Control
0x180003758  cmp     rcx, rax
0x18000375b  jz      loc_1800036DB
0x180003761  test    byte ptr [rcx+1Ch], 1
0x180003765  jz      loc_1800036DB
0x18000376b  mov     dword ptr [rsp+0E0h+var_B0], 0CBh
0x180003773  jmp     loc_1800036BB
0x180003778  call    I_DefaultExtrenalFree
0x18000377d  jmp     loc_1800036E8
0x180003782  mov     rcx, cs:WPP_GLOBAL_Control
0x180003789  lea     rax, WPP_GLOBAL_Control
0x180003790  cmp     rcx, rax
0x180003793  jz      loc_1800036DB
0x180003799  test    byte ptr [rcx+1Ch], 1
0x18000379d  jz      loc_1800036DB
0x1800037a3  mov     dword ptr [rsp+0E0h+var_B0], 10Eh
0x1800037ab  jmp     loc_1800036BB
0x1800037b0  mov     ebx, 80090009h
0x1800037b5  mov     r9d, 0B2h
0x1800037bb  mov     ecx, 80090009h
0x1800037c0  jmp     short loc_1800037FE
0x1800037c2  mov     r9d, 0BFh
0x1800037c8  jmp     short loc_1800037D0
0x1800037ca  mov     r9d, 12Fh
0x1800037d0  mov     ecx, eax
0x1800037d2  jmp     short loc_1800037FE
0x1800037d4  mov     r9d, 0F4h
0x1800037da  jmp     short loc_1800037D0
0x1800037dc  mov     ebx, 80090026h
0x1800037e1  mov     r9d, 0A6h
0x1800037e7  mov     ecx, 80090026h
0x1800037ec  jmp     short loc_1800037FE
0x1800037ee  mov     ebx, 80090027h
0x1800037f3  mov     r9d, 9Dh
0x1800037f9  mov     ecx, 80090027h
0x1800037fe  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003805  lea     rdx, aStatus; "Status"
0x18000380c  call    DebugTraceError
0x180003811  jmp     loc_1800036DB
0x180003816  mov     rcx, rdi
0x180003819  call    I_StreamFree
0x18000381e  jmp     loc_1800036F1
```
