# HalpInterruptRemap

- ea: `0x1405897c4`
- end: `0x140589c47`
- name: `HalpInterruptRemap`
- size: `1155`
- prototype: ``
- caller_count: `4`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1405893d4`
- `0x14058ee00`
- `0x14059aa78`
- `0x140747a60`

## callees

- `0x1403a2f60`
- `0x1403a3d20`
- `0x1403a3f4c`
- `0x1403a47e0`
- `0x1403a5678`
- `0x1403a56c4`
- `0x1403a85c4`
- `0x1403a8678`
- `0x1404be3b4`
- `0x1405897c4`
- `0x140589c50`
- `0x140589d18`
- `0x14074aac0`
- `0x14074af1c`
- `0x140b8fb94`
- `0x140b8fcb4`

## string_xrefs

- `0x14058987f`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x14058990a`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x14058998b`: `minkernel\hals\lib\interrupts\common\connect.c`
- `0x140589a73`: `minkernel\hals\lib\interrupts\common\connect.c`

## pseudocode

```c
__int64 __fastcall HalpInterruptRemap(
        unsigned int a1,
        unsigned int a2,
        __int64 a3,
        char a4,
        unsigned int *a5,
        unsigned int a6)
{
  unsigned int *v6; // rsi
  unsigned int v7; // r13d
  __int64 v8; // r10
  char v9; // al
  unsigned int *v10; // r12
  unsigned int *v11; // r14
  unsigned __int64 v12; // r8
  __int64 v13; // r15
  unsigned int v14; // r11d
  __int128 *v15; // rcx
  unsigned int v16; // edi
  unsigned int v17; // eax
  int BestRouting; // ebx
  int v20; // edx
  int v21; // r8d
  unsigned int i; // ebx
  __int64 v23; // rcx
  int v24; // edx
  unsigned int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // r15
  __int64 v30; // rdx
  unsigned int v31; // edx
  int v32; // eax
  int v33; // [rsp+30h] [rbp-71h]
  int v34; // [rsp+48h] [rbp-59h] BYREF
  __int128 v35; // [rsp+50h] [rbp-51h] BYREF
  unsigned int *v36; // [rsp+60h] [rbp-41h]
  __int128 v37; // [rsp+68h] [rbp-39h] BYREF
  __int128 v38; // [rsp+78h] [rbp-29h] BYREF
  __int128 v39; // [rsp+88h] [rbp-19h]
  __int64 v40; // [rsp+98h] [rbp-9h]
  unsigned int v42; // [rsp+100h] [rbp+5Fh]
  char v44; // [rsp+110h] [rbp+6Fh]

  v44 = a4;
  v42 = a2;
  v6 = a5;
  v7 = a6;
  v37 = 0;
  v8 = a3;
  *(_QWORD *)&v35 = 1;
  v9 = *((_BYTE *)a5 + 8);
  v10 = a5 + 10;
  v11 = a5 + 6;
  v12 = (unsigned __int64)*((unsigned __int8 *)a5 + 4) >> 4;
  v13 = 0;
  v38 = 0;
  v14 = a1;
  *(_QWORD *)((char *)&v35 + 4) = 0;
  v15 = &HalpHwToSwIrqlMap;
  v34 = -1;
  *((_BYTE *)&HalpHwToSwIrqlMap + v12) = v9;
  v16 = -1;
  v36 = v10;
  v40 = 0;
  LODWORD(v37) = v6[3];
  DWORD2(v37) = v6[4];
  LODWORD(v40) = v6[1];
  v17 = *v6;
  *((_QWORD *)&v35 + 1) = v11;
  HIDWORD(v37) = 16;
  *(_QWORD *)&v38 = 0x1FFFFFFFFLL;
  v39 = 0;
  if ( !v17 )
  {
    v27 = v6[14];
    a5 = 0;
    if ( (int)HalpInterruptGsiToLine(v27, &a5) >= 0 )
    {
      HalpInterruptApplyOverrides(&a5, &v37, (char *)&v37 + 8);
      if ( (_DWORD)v37 == 3 )
      {
        BYTE4(v37) = 1;
        DWORD2(v37) = 0;
        LODWORD(v37) = 2;
      }
      else if ( (_DWORD)v37 == 4 )
      {
        BYTE4(v37) = 1;
        DWORD2(v37) = 0;
        LODWORD(v37) = 1;
      }
      else
      {
        BYTE4(v37) = 0;
      }
      v29 = HalpInterruptLookupController((unsigned int)a5);
      if ( v29 )
      {
        BestRouting = HalpInterruptDestinationToTarget(v28, &v35, (char *)&v38 + 8);
        if ( BestRouting < 0 )
        {
          v33 = 2898;
          goto LABEL_17;
        }
        BestRouting = HalpInterruptFindBestRouting(&a5, v38, &v38);
        if ( BestRouting < 0 )
          return (unsigned int)BestRouting;
        HalpInterruptRemapUpdateDeliveryMode(v6, &v37);
        if ( (*(_DWORD *)(HalpInterruptController + 244) & 0x100) != 0
          && (unsigned int)HalpInterruptModel(HalpInterruptController, v30) == 1 )
        {
          v31 = *v10;
          if ( (*v10 & 0x40000000) == 0 )
          {
            BestRouting = HalpIrtAllocateIndex(&v34, 1, a1, v42, a3, v44, v6);
            if ( BestRouting < 0 )
            {
              HalpInterruptSetProblemEx(
                0,
                31,
                BestRouting,
                -1,
                (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c",
                2939);
              goto LABEL_8;
            }
            v16 = v34;
            v31 = *v10 & 0xC0000000 | v34 & 0x3FFFFFFF;
            *v10 = v31;
          }
          HalpIommuUpdateRemappingTableEntry(0, v31 & 0x3FFFFFFF, &v37);
          v32 = *v10 & 0x3FFFFFFF;
          DWORD2(v38) = 7;
          LODWORD(v39) = v32;
          v11 = v6 + 6;
        }
        if ( qword_140FB9B48 )
        {
          BestRouting = HalpHvMapIoApicDeviceInterrupt(*(unsigned int *)(v29 + 256), &v37, v11);
          if ( BestRouting < 0 )
          {
            v33 = 2969;
            goto LABEL_25;
          }
        }
        HIDWORD(v37) &= ~0x10u;
        v26 = HalpInterruptSetRemappedLineStateInternal(v29, &a5, &v37);
        goto LABEL_51;
      }
      HalpInterruptSetProblemEx(0, 17, 1, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2883);
    }
    else
    {
      HalpInterruptSetProblemEx(0, 18, 0, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2838);
    }
    return (unsigned int)-1073741811;
  }
  if ( v17 != 3 )
  {
    BestRouting = -1073741823;
    HalpInterruptSetProblemEx(0, 19, 2, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", 2994);
    return (unsigned int)BestRouting;
  }
  if ( (*(_DWORD *)(HalpInterruptController + 244) & 0x100) == 0 )
  {
LABEL_22:
    if ( qword_140FB9B48 )
    {
      BestRouting = HalpHvMapDeviceMsiRange(v14, a2, v8, a4, (__int64)v6, v7);
      if ( BestRouting < 0 )
      {
        v33 = 2795;
LABEL_25:
        v21 = BestRouting;
        v20 = 31;
        goto LABEL_18;
      }
      return 0;
    }
    v26 = HalpPopulateMsiMessages(&v35, v6, v7);
LABEL_51:
    BestRouting = v26;
    if ( v26 < 0 )
      goto LABEL_9;
    return 0;
  }
  if ( (*v10 & 0x40000000) != 0 )
  {
    v16 = *v10 & 0x3FFFFFFF;
    goto LABEL_15;
  }
  BestRouting = HalpIrtAllocateIndex(&v34, v7, v14, a2, v8, a4, v6);
  if ( BestRouting >= 0 )
  {
    v16 = v34;
LABEL_15:
    BestRouting = HalpInterruptDestinationToTarget(v15, &v35, (char *)&v38 + 8);
    if ( BestRouting < 0 )
    {
      v33 = 2762;
LABEL_17:
      v20 = 19;
      v21 = 1;
LABEL_18:
      HalpInterruptSetProblemEx(0, v20, v21, -1, (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c", v33);
      goto LABEL_9;
    }
    HalpInterruptRemapUpdateDeliveryMode(v6, &v37);
    for ( i = 0; i < v7; ++v13 )
    {
      v23 = 88 * v13;
      v24 = v6[22 * v13 + 10] ^ (v6[22 * v13 + 10] ^ (i + v16)) & 0x3FFFFFFF;
      v25 = v6[22 * v13 + 1];
      *(unsigned int *)((char *)v6 + v23 + 40) = v24;
      LOBYTE(v23) = 1;
      LODWORD(v40) = v25;
      HalpIommuUpdateRemappingTableEntry(v23, v24 & 0x3FFFFFFF, &v37);
      ++i;
    }
    v14 = a1;
    a2 = v42;
    LODWORD(v8) = a3;
    a4 = v44;
    goto LABEL_22;
  }
  HalpInterruptSetProblemEx(
    0,
    31,
    BestRouting,
    -1,
    (__int64)"minkernel\\hals\\lib\\interrupts\\common\\connect.c",
    2746);
LABEL_8:
  v16 = v34;
LABEL_9:
  if ( v16 != -1 && (*v10 & 0x40000000) == 0 )
    HalpIrtFreeIndex(v16, v7, *v6);
  return (unsigned int)BestRouting;
}

```

## disassembly

```asm
0x1405897c4  mov     rax, rsp
0x1405897c7  mov     [rax+20h], r9b
0x1405897cb  mov     [rax+18h], r8
0x1405897cf  mov     [rax+10h], edx
0x1405897d2  mov     [rax+8], ecx
0x1405897d5  push    rbp
0x1405897d6  push    rbx
0x1405897d7  push    rsi
0x1405897d8  push    rdi
0x1405897d9  push    r12
0x1405897db  push    r13
0x1405897dd  push    r14
0x1405897df  push    r15
0x1405897e1  lea     rbp, [rax-4Fh]
0x1405897e5  sub     rsp, 0A8h
0x1405897ec  mov     rsi, [rbp+47h+arg_20]
0x1405897f0  or      ebx, 0FFFFFFFFh
0x1405897f3  mov     r13d, [rbp+47h+arg_28]
0x1405897f7  xorps   xmm0, xmm0
0x1405897fa  movups  [rbp+47h+var_80], xmm0
0x1405897fe  mov     r10, r8
0x140589801  mov     [rbp+47h+var_98], 1
0x140589809  mov     al, [rsi+8]
0x14058980c  lea     r12, [rsi+28h]
0x140589810  movzx   r8d, byte ptr [rsi+4]
0x140589815  lea     r14, [rsi+18h]
0x140589819  shr     r8, 4
0x14058981d  xor     r15d, r15d
0x140589820  movups  [rbp+47h+var_70], xmm0
0x140589824  mov     r11d, ecx
0x140589827  mov     [rbp+47h+var_98+4], r15
0x14058982b  lea     rcx, HalpHwToSwIrqlMap
0x140589832  mov     [rbp+47h+var_A0], ebx
0x140589835  mov     [r8+rcx], al
0x140589839  mov     edi, ebx
0x14058983b  xor     eax, eax
0x14058983d  mov     [rbp+47h+var_88], r12
0x140589841  mov     [rbp+47h+var_50], rax
0x140589845  mov     eax, [rsi+0Ch]
0x140589848  mov     dword ptr [rbp+47h+var_80], eax
0x14058984b  mov     eax, [rsi+10h]
0x14058984e  mov     dword ptr [rbp+47h+var_80+8], eax
0x140589851  mov     eax, [rsi+4]
0x140589854  mov     dword ptr [rbp+47h+var_50], eax
0x140589857  mov     eax, [rsi]
0x140589859  mov     [rbp+47h+var_90], r14
0x14058985d  mov     dword ptr [rbp+47h+var_80+0Ch], 10h
0x140589864  mov     dword ptr [rbp+47h+var_70+4], 1
0x14058986b  mov     dword ptr [rbp+47h+var_70], ebx
0x14058986e  movups  [rbp+47h+var_60], xmm0
0x140589872  test    eax, eax
0x140589874  jz      loc_140589A50
0x14058987a  cmp     eax, 3
0x14058987d  jz      short loc_1405898B0
0x14058987f  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140589886  mov     [rsp+0E0h+var_B8], 0BB2h
0x14058988e  or      r9d, 0FFFFFFFFh
0x140589892  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140589897  lea     edx, [r15+13h]
0x14058989b  xor     ecx, ecx
0x14058989d  lea     r8d, [r15+2]
0x1405898a1  mov     ebx, 0C0000001h
0x1405898a6  call    HalpInterruptSetProblemEx
0x1405898ab  jmp     loc_140589948
0x1405898b0  mov     rax, cs:HalpInterruptController
0x1405898b7  test    dword ptr [rax+0F4h], 100h
0x1405898c1  jz      loc_1405899FF
0x1405898c7  mov     edi, [r12]
0x1405898cb  mov     r14d, 3FFFFFFFh
0x1405898d1  bt      edi, 1Eh
0x1405898d5  jb      loc_140589964
0x1405898db  mov     qword ptr [rsp+0E0h+var_B8+8], rsi
0x1405898e0  lea     rcx, [rbp+47h+var_A0]
0x1405898e4  mov     byte ptr [rsp+0E0h+var_B8], r9b
0x1405898e9  mov     r8d, r11d
0x1405898ec  mov     r9d, edx
0x1405898ef  mov     qword ptr [rsp+0E0h+var_C0], r10
0x1405898f4  mov     edx, r13d
0x1405898f7  call    HalpIrtAllocateIndex
0x1405898fc  mov     ebx, eax
0x1405898fe  test    eax, eax
0x140589900  jns     short loc_14058995F
0x140589902  mov     [rsp+0E0h+var_B8], 0ABAh
0x14058990a  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140589911  or      r9d, 0FFFFFFFFh
0x140589915  mov     r8d, ebx
0x140589918  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14058991d  mov     edx, 1Fh
0x140589922  xor     ecx, ecx
0x140589924  call    HalpInterruptSetProblemEx
0x140589929  mov     edi, [rbp+47h+var_A0]
0x14058992c  cmp     edi, 0FFFFFFFFh
0x14058992f  jz      short loc_140589948
0x140589931  test    dword ptr [r12], 40000000h
0x140589939  jnz     short loc_140589948
0x14058993b  mov     r8d, [rsi]
0x14058993e  mov     edx, r13d
0x140589941  mov     ecx, edi
0x140589943  call    HalpIrtFreeIndex
0x140589948  mov     eax, ebx
0x14058994a  add     rsp, 0A8h
0x140589951  pop     r15
0x140589953  pop     r14
0x140589955  pop     r13
0x140589957  pop     r12
0x140589959  pop     rdi
0x14058995a  pop     rsi
0x14058995b  pop     rbx
0x14058995c  pop     rbp
0x14058995d  retn
0x14058995f  mov     edi, [rbp+47h+var_A0]
0x140589962  jmp     short loc_140589967
0x140589964  and     edi, r14d
0x140589967  lea     r8, [rbp+47h+var_70+8]
0x14058996b  lea     rdx, [rbp+47h+var_98]
0x14058996f  call    HalpInterruptDestinationToTarget
0x140589974  mov     ebx, eax
0x140589976  test    eax, eax
0x140589978  jns     short loc_1405899A4
0x14058997a  mov     [rsp+0E0h+var_B8], 0ACAh
0x140589982  mov     edx, 13h
0x140589987  lea     r8d, [rdx-12h]
0x14058998b  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140589992  or      r9d, 0FFFFFFFFh
0x140589996  xor     ecx, ecx
0x140589998  mov     qword ptr [rsp+0E0h+var_C0], rax
0x14058999d  call    HalpInterruptSetProblemEx
0x1405899a2  jmp     short loc_14058992C
0x1405899a4  lea     rdx, [rbp+47h+var_80]
0x1405899a8  mov     rcx, rsi
0x1405899ab  call    HalpInterruptRemapUpdateDeliveryMode
0x1405899b0  mov     ebx, r15d
0x1405899b3  test    r13d, r13d
0x1405899b6  jz      short loc_1405899F0
0x1405899b8  imul    rcx, r15, 58h ; 'X'
0x1405899bc  lea     edx, [rbx+rdi]
0x1405899bf  lea     r8, [rbp+47h+var_80]
0x1405899c3  mov     eax, [rcx+rsi+28h]
0x1405899c7  xor     edx, eax
0x1405899c9  and     edx, r14d
0x1405899cc  xor     edx, eax
0x1405899ce  mov     eax, [rcx+rsi+4]
0x1405899d2  mov     [rcx+rsi+28h], edx
0x1405899d6  and     edx, r14d
0x1405899d9  mov     cl, 1
0x1405899db  mov     dword ptr [rbp+47h+var_50], eax
0x1405899de  call    HalpIommuUpdateRemappingTableEntry
0x1405899e3  inc     ebx
0x1405899e5  inc     r15
0x1405899e8  cmp     ebx, r13d
0x1405899eb  jb      short loc_1405899B8
0x1405899ed  xor     r15d, r15d
0x1405899f0  mov     r11d, [rbp+47h+arg_0]
0x1405899f4  mov     edx, [rbp+47h+arg_8]
0x1405899f7  mov     r10, [rbp+47h+arg_10]
0x1405899fb  mov     r9b, [rbp+47h+arg_18]
0x1405899ff  cmp     cs:qword_140FB9B48, r15
0x140589a06  jz      short loc_140589A3C
0x140589a08  mov     [rsp+0E0h+var_B8], r13d
0x140589a0d  mov     r8, r10
0x140589a10  mov     ecx, r11d
0x140589a13  mov     qword ptr [rsp+0E0h+var_C0], rsi
0x140589a18  call    HalpHvMapDeviceMsiRange
0x140589a1d  mov     ebx, eax
0x140589a1f  test    eax, eax
0x140589a21  jns     loc_140589C3F
0x140589a27  mov     [rsp+0E0h+var_B8], 0AEBh
0x140589a2f  mov     r8d, ebx
0x140589a32  mov     edx, 1Fh
0x140589a37  jmp     loc_14058998B
0x140589a3c  mov     r8d, r13d
0x140589a3f  lea     rcx, [rbp+47h+var_98]
0x140589a43  mov     rdx, rsi
0x140589a46  call    HalpPopulateMsiMessages
0x140589a4b  jmp     loc_140589C35
0x140589a50  mov     ecx, [rsi+38h]
0x140589a53  lea     rdx, [rbp+47h+arg_20]
0x140589a57  mov     [rbp+47h+arg_20], r15
0x140589a5b  call    HalpInterruptGsiToLine
0x140589a60  test    eax, eax
0x140589a62  jns     short loc_140589A93
0x140589a64  xor     r8d, r8d
0x140589a67  mov     [rsp+0E0h+var_B8], 0B16h
0x140589a6f  lea     edx, [r8+12h]
0x140589a73  lea     rax, aMinkernelHalsL_8; "minkernel\\hals\\lib\\interrupts\\commo"...
0x140589a7a  xor     ecx, ecx
0x140589a7c  mov     r9d, ebx
0x140589a7f  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140589a84  call    HalpInterruptSetProblemEx
0x140589a89  mov     ebx, 0C000000Dh
0x140589a8e  jmp     loc_140589948
0x140589a93  lea     r8, [rbp+47h+var_80+8]
0x140589a97  lea     rdx, [rbp+47h+var_80]
0x140589a9b  lea     rcx, [rbp+47h+arg_20]
0x140589a9f  call    HalpInterruptApplyOverrides
0x140589aa4  cmp     dword ptr [rbp+47h+var_80], 3
0x140589aa8  jnz     short loc_140589ABB
0x140589aaa  mov     byte ptr [rbp+47h+var_80+4], 1
0x140589aae  mov     dword ptr [rbp+47h+var_80+8], r15d
0x140589ab2  mov     dword ptr [rbp+47h+var_80], 2
0x140589ab9  jmp     short loc_140589AD6
0x140589abb  cmp     dword ptr [rbp+47h+var_80], 4
0x140589abf  jnz     short loc_140589AD2
0x140589ac1  mov     byte ptr [rbp+47h+var_80+4], 1
0x140589ac5  mov     dword ptr [rbp+47h+var_80+8], r15d
0x140589ac9  mov     dword ptr [rbp+47h+var_80], 1
0x140589ad0  jmp     short loc_140589AD6
0x140589ad2  mov     byte ptr [rbp+47h+var_80+4], r15b
0x140589ad6  mov     ecx, dword ptr [rbp+47h+arg_20]
0x140589ad9  call    HalpInterruptLookupController
0x140589ade  mov     r15, rax
0x140589ae1  test    rax, rax
0x140589ae4  jnz     short loc_140589AFA
0x140589ae6  mov     [rsp+0E0h+var_B8], 0B43h
0x140589aee  lea     edx, [rax+11h]
0x140589af1  lea     r8d, [rax+1]
0x140589af5  jmp     loc_140589A73
0x140589afa  lea     r8, [rbp+47h+var_70+8]
0x140589afe  lea     rdx, [rbp+47h+var_98]
0x140589b02  call    HalpInterruptDestinationToTarget
0x140589b07  mov     ebx, eax
0x140589b09  test    eax, eax
0x140589b0b  jns     short loc_140589B1A
0x140589b0d  mov     [rsp+0E0h+var_B8], 0B52h
0x140589b15  jmp     loc_140589982
0x140589b1a  mov     rdx, qword ptr [rbp+47h+var_70]
0x140589b1e  lea     r8, [rbp+47h+var_70]
0x140589b22  lea     rcx, [rbp+47h+arg_20]
0x140589b26  call    HalpInterruptFindBestRouting
0x140589b2b  mov     ebx, eax
0x140589b2d  test    eax, eax
0x140589b2f  js      loc_140589948
0x140589b35  lea     rdx, [rbp+47h+var_80]
0x140589b39  mov     rcx, rsi
0x140589b3c  call    HalpInterruptRemapUpdateDeliveryMode
0x140589b41  mov     rcx, cs:HalpInterruptController
0x140589b48  test    dword ptr [rcx+0F4h], 100h
0x140589b52  jz      loc_140589BEE
0x140589b58  call    HalpInterruptModel
0x140589b5d  cmp     eax, 1
0x140589b60  jnz     loc_140589BEE
0x140589b66  mov     edx, [r12]
0x140589b6a  mov     r14d, 3FFFFFFFh
0x140589b70  bt      edx, 1Eh
0x140589b74  jb      short loc_140589BCB
0x140589b76  mov     al, [rbp+47h+arg_18]
0x140589b79  lea     rcx, [rbp+47h+var_A0]
0x140589b7d  mov     r9d, [rbp+47h+arg_8]
0x140589b81  mov     edx, 1
0x140589b86  mov     r8d, [rbp+47h+arg_0]
0x140589b8a  mov     qword ptr [rsp+0E0h+var_B8+8], rsi
0x140589b8f  mov     byte ptr [rsp+0E0h+var_B8], al
0x140589b93  mov     rax, [rbp+47h+arg_10]
0x140589b97  mov     qword ptr [rsp+0E0h+var_C0], rax
0x140589b9c  call    HalpIrtAllocateIndex
0x140589ba1  mov     ebx, eax
0x140589ba3  test    eax, eax
0x140589ba5  jns     short loc_140589BB4
0x140589ba7  mov     [rsp+0E0h+var_B8], 0B7Bh
0x140589baf  jmp     loc_14058990A
0x140589bb4  mov     eax, [r12]
0x140589bb8  mov     edi, [rbp+47h+var_A0]
0x140589bbb  and     eax, 0C0000000h
0x140589bc0  mov     edx, edi
0x140589bc2  and     edx, r14d
0x140589bc5  or      edx, eax
0x140589bc7  mov     [r12], edx
0x140589bcb  and     edx, r14d
0x140589bce  lea     r8, [rbp+47h+var_80]
0x140589bd2  xor     ecx, ecx
0x140589bd4  call    HalpIommuUpdateRemappingTableEntry
0x140589bd9  mov     eax, [r12]
0x140589bdd  and     eax, r14d
0x140589be0  mov     dword ptr [rbp+47h+var_70+8], 7
0x140589be7  mov     dword ptr [rbp+47h+var_60], eax
0x140589bea  lea     r14, [rsi+18h]
0x140589bee  cmp     cs:qword_140FB9B48, 0
0x140589bf6  jz      short loc_140589C1E
0x140589bf8  mov     ecx, [r15+100h]
0x140589bff  lea     rdx, [rbp+47h+var_80]
0x140589c03  mov     r8, r14
0x140589c06  call    HalpHvMapIoApicDeviceInterrupt
0x140589c0b  mov     ebx, eax
0x140589c0d  test    eax, eax
0x140589c0f  jns     short loc_140589C1E
0x140589c11  mov     [rsp+0E0h+var_B8], 0B99h
0x140589c19  jmp     loc_140589A2F
0x140589c1e  and     dword ptr [rbp+47h+var_80+0Ch], 0FFFFFFEFh
0x140589c22  lea     r8, [rbp+47h+var_80]
0x140589c26  lea     rdx, [rbp+47h+arg_20]
0x140589c2a  mov     rcx, r15
0x140589c2d  call    HalpInterruptSetRemappedLineStateInternal
0x140589c32  xor     r15d, r15d
0x140589c35  mov     ebx, eax
0x140589c37  test    eax, eax
0x140589c39  js      loc_14058992C
0x140589c3f  mov     ebx, r15d
0x140589c42  jmp     loc_140589948
```
