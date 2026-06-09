# HalpTimerConfigureInterrupt

- ea: `0x14058ee00`
- end: `0x14058f235`
- name: `HalpTimerConfigureInterrupt`
- size: `1077`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14053e67c`
- `0x14053eb84`
- `0x14058ea00`
- `0x140591b4c`

## callees

- `0x140229a70`
- `0x140337544`
- `0x1403a3d20`
- `0x1403a3f4c`
- `0x1403a4a00`
- `0x1403a4a2c`
- `0x1403a7f3c`
- `0x1404bdf4c`
- `0x1404df454`
- `0x1404f540c`
- `0x14053e730`
- `0x1405897c4`
- `0x14058ee00`
- `0x14059030c`
- `0x1406dc8c0`
- `0x1406eb0e0`
- `0x1406f7380`

## string_xrefs

- `0x14058efca`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x14058f027`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x14058f1f0`: `minkernel\hals\lib\timers\common\timersup.c`

## pseudocode

```c
__int64 __fastcall HalpTimerConfigureInterrupt(
        __int64 a1,
        unsigned int a2,
        char a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        __int128 *a7,
        __int64 a8)
{
  __int128 v11; // xmm0
  __int64 v12; // rcx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  __int64 InternalData; // rax
  int v17; // r8d
  int v18; // r9d
  int v19; // ebx
  unsigned int *v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r9
  __int64 v25; // rcx
  int v26; // eax
  int v27; // eax
  int v28; // edi
  int *v29; // rbx
  unsigned int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  char v33; // bl
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 v39; // [rsp+40h] [rbp-A9h] BYREF
  _DWORD v40[2]; // [rsp+48h] [rbp-A1h] BYREF
  __int64 v41; // [rsp+50h] [rbp-99h] BYREF
  int FirstSetRightGroupAffinity; // [rsp+58h] [rbp-91h]
  int v43; // [rsp+5Ch] [rbp-8Dh]
  __int128 *v44; // [rsp+60h] [rbp-89h]
  __int128 v45; // [rsp+68h] [rbp-81h] BYREF
  unsigned int v46[2]; // [rsp+80h] [rbp-69h] BYREF
  char v47; // [rsp+88h] [rbp-61h]
  int v48; // [rsp+8Ch] [rbp-5Dh] BYREF
  int v49; // [rsp+90h] [rbp-59h] BYREF
  __int128 v50; // [rsp+98h] [rbp-51h]
  int v51; // [rsp+A8h] [rbp-41h]
  int v52; // [rsp+ACh] [rbp-3Dh]
  int v53; // [rsp+B0h] [rbp-39h]
  unsigned int v54; // [rsp+B4h] [rbp-35h]
  _BYTE v55[40]; // [rsp+B8h] [rbp-31h] BYREF

  v41 = 6;
  v43 = 0;
  v39 = 0;
  v45 = 0;
  memset_0(v46, 0, 0x58u);
  v11 = *a7;
  v46[1] = a2;
  v47 = a3;
  v51 = a6 & 0x3FFFFFFF | 0x40000000;
  v50 = v11;
  FirstSetRightGroupAffinity = KeFindFirstSetRightGroupAffinity(a7);
  v44 = &v45;
  LODWORD(v45) = a6 & 0x3FFFFFFF;
  v15 = *(_DWORD *)(a1 + 224);
  if ( (v15 & 0x800) != 0 )
  {
    InternalData = HalpTimerGetInternalData(a1);
    guard_dispatch_icall_no_overrides(InternalData);
    LOBYTE(v17) = a3;
    HalpInterruptSetIdtEntry(a2, a8, v17, v18, a5);
    return 0;
  }
  v19 = -1073741637;
  if ( (v15 & 0x400) == 0 )
    goto LABEL_11;
  LOBYTE(v12) = 1;
  if ( !(unsigned __int8)HalpInterruptIsMsiSupported(v12) || (*(_DWORD *)(a1 + 184) & 0x50) == 0x40 )
    goto LABEL_11;
  LOBYTE(v13) = a3;
  HalpInterruptSetIdtEntry(a2, a8, v13, v14, a5);
  if ( (*(_DWORD *)(a1 + 184) & 0x40) != 0 )
    goto LABEL_9;
  v20 = *(unsigned int **)(a1 + 288);
  v46[0] = 3;
  v49 = 1;
  v48 = 0;
  v19 = HalpInterruptRemap(*v20, v20[1], (__int64)(v20 + 2), 0, v46, 1u);
  if ( v19 >= 0 )
  {
    v21 = v52;
    *(_DWORD *)(a1 + 184) |= 0x40u;
    *(_DWORD *)(a1 + 236) = v21;
    *(_DWORD *)(a1 + 232) = v53;
    *(_QWORD *)(a1 + 240) = v54;
LABEL_9:
    v22 = HalpTimerGetInternalData(a1);
    v23 = guard_dispatch_icall_no_overrides(v22);
    v19 = v23;
    if ( v23 >= 0 )
    {
      *(_DWORD *)(a1 + 184) |= 0x10u;
      return 0;
    }
    HalpTimerSetProblemEx(a1, 24, v23, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 2309);
    LOBYTE(v24) = 1;
    HalpTimerUnmapInterrupt(v25, a2, a6, v24);
  }
LABEL_11:
  v26 = *(_DWORD *)(a1 + 224);
  if ( (v26 & 0x200) != 0 )
  {
    v27 = HalpInterruptGsiToLine(*(unsigned int *)(a1 + 88), &v39);
    v28 = v27;
    if ( v27 < 0 )
    {
      HalpTimerSetProblemEx(a1, 16, v27, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 384);
      return (unsigned int)v28;
    }
    v29 = (int *)(a1 + 92);
  }
  else
  {
    if ( (v26 & 0x100) == 0 )
    {
      HalpTimerSetProblemEx(a1, 17, v19, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 399);
      return (unsigned int)-1073741811;
    }
    v30 = *(_DWORD *)(a1 + 84);
    if ( v30 >= 8 )
    {
      LODWORD(v39) = 45057;
      v30 -= 8;
    }
    else
    {
      LODWORD(v39) = 45056;
    }
    v29 = (int *)(a1 + 92);
    HIDWORD(v39) = v30;
    if ( !*(_DWORD *)(a1 + 92) )
    {
      *v29 = 1;
      *(_DWORD *)(a1 + 96) = 1;
    }
  }
  LOBYTE(v13) = a3;
  HalpInterruptSetIdtEntry(a2, a8, v13, v14, a5);
  if ( (*(_DWORD *)(a1 + 184) & 0x10) == 0 )
    goto LABEL_27;
  v31 = HalpTimerGetInternalData(a1);
  v32 = guard_dispatch_icall_no_overrides(v31);
  v28 = v32;
  if ( v32 < 0 )
  {
    HalpTimerSetProblemEx(a1, 24, v32, (unsigned int)"minkernel\\hals\\lib\\timers\\common\\timersup.c", 426);
    return (unsigned int)v28;
  }
  *(_DWORD *)(a1 + 184) &= ~0x10u;
  if ( (*(_DWORD *)(a1 + 184) & 0x10) == 0 )
  {
LABEL_27:
    if ( a2 == 209 )
    {
      HalpTimerCriticalClockSource = v39;
      HalpTimerCriticalClockSourceCount = 1;
    }
  }
  v49 = *(_DWORD *)(a1 + 96);
  v48 = *v29;
  v46[0] = 0;
  HalpInterruptApplyOverrides(&v39, &v48, &v49);
  v28 = HalpInterruptLineToGsi(&v39, v55);
  if ( v28 >= 0 )
  {
    if ( (*(_DWORD *)(a1 + 184) & 0x40) == 0 )
    {
      v28 = HalpInterruptRemap(
              **(_DWORD **)(a1 + 288),
              *(_DWORD *)(*(_QWORD *)(a1 + 288) + 4LL),
              *(_QWORD *)(a1 + 288) + 8LL,
              0,
              v46,
              1u);
      if ( v28 < 0 )
        return (unsigned int)v28;
      *(_DWORD *)(a1 + 184) |= 0x40u;
    }
    v40[0] = -1;
    v40[1] = 1;
    v33 = HalpAcquireHighLevelLock(&HalpInterruptLock);
    v34 = HalpInterruptSetLineState((unsigned __int64 *)&v39, a2, a3, v49, v48, (__int64)&v41, (__int64)v40);
    LOBYTE(v35) = v33;
    v28 = v34;
    HalpReleaseHighLevelLock(&HalpInterruptLock, v35, v36, v37);
    if ( v28 >= 0 )
      return 0;
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x14058ee00  push    rbp
0x14058ee02  push    rbx
0x14058ee03  push    rsi
0x14058ee04  push    rdi
0x14058ee05  push    r12
0x14058ee07  push    r14
0x14058ee09  push    r15
0x14058ee0b  lea     rbp, [rsp-7]
0x14058ee10  sub     rsp, 0F0h
0x14058ee17  mov     rax, cs:__security_cookie
0x14058ee1e  xor     rax, rsp
0x14058ee21  mov     [rbp+37h+var_40], rax
0x14058ee25  mov     rdi, [rbp+37h+arg_30]
0x14058ee29  xor     eax, eax
0x14058ee2b  mov     r15b, r8b
0x14058ee2e  mov     [rsp+120h+var_D0], 6
0x14058ee37  mov     r14d, edx
0x14058ee3a  mov     [rsp+120h+var_C4], eax
0x14058ee3e  mov     rsi, rcx
0x14058ee41  mov     [rsp+120h+var_E0], rax
0x14058ee46  xorps   xmm0, xmm0
0x14058ee49  lea     r8d, [rax+58h]; Size
0x14058ee4d  xor     edx, edx; Val
0x14058ee4f  lea     rcx, [rbp+37h+var_A0]; void *
0x14058ee53  movups  [rsp+120h+var_B8], xmm0
0x14058ee58  call    memset_0
0x14058ee5d  movups  xmm0, xmmword ptr [rdi]
0x14058ee60  mov     ebx, [rbp+37h+arg_28]
0x14058ee63  mov     rcx, rdi
0x14058ee66  and     ebx, 3FFFFFFFh
0x14058ee6c  mov     [rbp+37h+var_9C], r14d
0x14058ee70  mov     eax, ebx
0x14058ee72  mov     [rbp+37h+var_98], r15b
0x14058ee76  bts     eax, 1Eh
0x14058ee7a  mov     [rbp+37h+var_78], eax
0x14058ee7d  movdqu  [rbp+37h+var_88], xmm0
0x14058ee82  call    KeFindFirstSetRightGroupAffinity
0x14058ee87  mov     [rsp+120h+var_C8], eax
0x14058ee8b  lea     rax, [rsp+120h+var_B8]
0x14058ee90  mov     [rsp+120h+var_C0], rax
0x14058ee95  mov     eax, dword ptr [rsp+120h+var_B8]
0x14058ee99  and     eax, 0C0000000h
0x14058ee9e  or      eax, ebx
0x14058eea0  mov     dword ptr [rsp+120h+var_B8], eax
0x14058eea4  mov     eax, [rsi+0E0h]
0x14058eeaa  bt      eax, 0Bh
0x14058eeae  jnb     short loc_14058EEE7
0x14058eeb0  mov     rcx, rsi
0x14058eeb3  call    HalpTimerGetInternalData
0x14058eeb8  mov     rcx, rax
0x14058eebb  mov     edx, r14d
0x14058eebe  mov     rax, [rsi+0A8h]
0x14058eec5  call    _guard_dispatch_icall_no_overrides
0x14058eeca  mov     rax, [rbp+37h+arg_20]
0x14058eece  mov     r8b, r15b
0x14058eed1  mov     rdx, [rbp+37h+arg_38]
0x14058eed5  mov     ecx, r14d
0x14058eed8  mov     [rsp+120h+var_100], rax
0x14058eedd  call    HalpInterruptSetIdtEntry
0x14058eee2  jmp     loc_14058F1EC
0x14058eee7  mov     r12, [rbp+37h+arg_20]
0x14058eeeb  mov     ebx, 0C00000BBh
0x14058eef0  mov     edi, 1
0x14058eef5  bt      eax, 0Ah
0x14058eef9  jnb     loc_14058EFF8
0x14058eeff  mov     cl, dil
0x14058ef02  call    HalpInterruptIsMsiSupported
0x14058ef07  test    al, al
0x14058ef09  jz      loc_14058EFF8
0x14058ef0f  mov     eax, [rsi+0B8h]
0x14058ef15  and     al, 50h
0x14058ef17  cmp     al, 40h ; '@'
0x14058ef19  jz      loc_14058EFF8
0x14058ef1f  mov     rdx, [rbp+37h+arg_38]
0x14058ef23  mov     r8b, r15b
0x14058ef26  mov     ecx, r14d
0x14058ef29  mov     [rsp+120h+var_100], r12
0x14058ef2e  call    HalpInterruptSetIdtEntry
0x14058ef33  mov     eax, [rsi+0B8h]
0x14058ef39  test    al, 40h
0x14058ef3b  jnz     short loc_14058EF9C
0x14058ef3d  mov     rcx, [rsi+120h]
0x14058ef44  lea     rax, [rbp+37h+var_A0]
0x14058ef48  mov     [rbp+37h+var_A0], 3
0x14058ef4f  xor     r9d, r9d
0x14058ef52  mov     [rbp+37h+var_90], edi
0x14058ef55  mov     [rbp+37h+var_94], 0
0x14058ef5c  mov     edx, [rcx+4]
0x14058ef5f  lea     r8, [rcx+8]
0x14058ef63  mov     ecx, [rcx]
0x14058ef65  mov     dword ptr [rsp+120h+var_F8], edi
0x14058ef69  mov     [rsp+120h+var_100], rax
0x14058ef6e  call    HalpInterruptRemap
0x14058ef73  mov     ebx, eax
0x14058ef75  test    eax, eax
0x14058ef77  js      short loc_14058EFF8
0x14058ef79  mov     eax, [rbp+37h+var_74]
0x14058ef7c  or      dword ptr [rsi+0B8h], 40h
0x14058ef83  mov     [rsi+0ECh], eax
0x14058ef89  mov     eax, [rbp+37h+var_70]
0x14058ef8c  mov     [rsi+0E8h], eax
0x14058ef92  mov     eax, [rbp+37h+var_6C]
0x14058ef95  mov     [rsi+0F0h], rax
0x14058ef9c  mov     rcx, rsi
0x14058ef9f  call    HalpTimerGetInternalData
0x14058efa4  mov     r9d, [rsi+0F0h]
0x14058efab  mov     rcx, rax
0x14058efae  mov     rax, [rsi+98h]
0x14058efb5  mov     dl, dil
0x14058efb8  mov     r8, [rsi+0E8h]
0x14058efbf  call    _guard_dispatch_icall_no_overrides
0x14058efc4  mov     ebx, eax
0x14058efc6  test    eax, eax
0x14058efc8  jns     short loc_14058F03B
0x14058efca  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x14058efd1  mov     dword ptr [rsp+120h+var_100], 905h
0x14058efd9  mov     r8d, eax
0x14058efdc  mov     edx, 18h
0x14058efe1  mov     rcx, rsi
0x14058efe4  call    HalpTimerSetProblemEx
0x14058efe9  mov     r8d, [rbp+37h+arg_28]
0x14058efed  mov     r9b, dil
0x14058eff0  mov     edx, r14d
0x14058eff3  call    HalpTimerUnmapInterrupt
0x14058eff8  mov     eax, [rsi+0E0h]
0x14058effe  bt      eax, 9
0x14058f002  jnb     short loc_14058F04D
0x14058f004  mov     ecx, [rsi+58h]
0x14058f007  lea     rdx, [rsp+120h+var_E0]
0x14058f00c  call    HalpInterruptGsiToLine
0x14058f011  mov     edi, eax
0x14058f013  test    eax, eax
0x14058f015  jns     short loc_14058F047
0x14058f017  mov     dword ptr [rsp+120h+var_100], 180h
0x14058f01f  mov     edx, 10h
0x14058f024  mov     r8d, eax
0x14058f027  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x14058f02e  mov     rcx, rsi
0x14058f031  call    HalpTimerSetProblemEx
0x14058f036  jmp     loc_14058F214
0x14058f03b  or      dword ptr [rsi+0B8h], 10h
0x14058f042  jmp     loc_14058F1EC
0x14058f047  lea     rbx, [rsi+5Ch]
0x14058f04b  jmp     short loc_14058F086
0x14058f04d  bt      eax, 8
0x14058f051  jnb     loc_14058F1F0
0x14058f057  mov     eax, [rsi+54h]
0x14058f05a  cmp     eax, 8
0x14058f05d  jnb     short loc_14058F069
0x14058f05f  mov     dword ptr [rsp+120h+var_E0], 0B000h
0x14058f067  jmp     short loc_14058F074
0x14058f069  mov     dword ptr [rsp+120h+var_E0], 0B001h
0x14058f071  add     eax, 0FFFFFFF8h
0x14058f074  lea     rbx, [rsi+5Ch]
0x14058f078  mov     dword ptr [rsp+120h+var_E0+4], eax
0x14058f07c  cmp     dword ptr [rbx], 0
0x14058f07f  jnz     short loc_14058F086
0x14058f081  mov     [rbx], edi
0x14058f083  mov     [rsi+60h], edi
0x14058f086  mov     rdx, [rbp+37h+arg_38]
0x14058f08a  mov     r8b, r15b
0x14058f08d  mov     ecx, r14d
0x14058f090  mov     [rsp+120h+var_100], r12
0x14058f095  call    HalpInterruptSetIdtEntry
0x14058f09a  mov     eax, [rsi+0B8h]
0x14058f0a0  test    al, 10h
0x14058f0a2  jz      short loc_14058F0EC
0x14058f0a4  mov     rcx, rsi
0x14058f0a7  xor     r8d, r8d
0x14058f0aa  call    HalpTimerGetInternalData
0x14058f0af  mov     rcx, rax
0x14058f0b2  xor     r9d, r9d
0x14058f0b5  mov     rax, [rsi+98h]
0x14058f0bc  xor     edx, edx
0x14058f0be  call    _guard_dispatch_icall_no_overrides
0x14058f0c3  mov     edi, eax
0x14058f0c5  test    eax, eax
0x14058f0c7  jns     short loc_14058F0DB
0x14058f0c9  mov     dword ptr [rsp+120h+var_100], 1AAh
0x14058f0d1  mov     edx, 18h
0x14058f0d6  jmp     loc_14058F024
0x14058f0db  and     dword ptr [rsi+0B8h], 0FFFFFFEFh
0x14058f0e2  mov     eax, [rsi+0B8h]
0x14058f0e8  test    al, 10h
0x14058f0ea  jnz     short loc_14058F10B
0x14058f0ec  cmp     r14d, 0D1h
0x14058f0f3  jnz     short loc_14058F10B
0x14058f0f5  mov     rax, [rsp+120h+var_E0]
0x14058f0fa  mov     cs:HalpTimerCriticalClockSource, rax
0x14058f101  mov     cs:HalpTimerCriticalClockSourceCount, 1
0x14058f10b  mov     eax, [rsi+60h]
0x14058f10e  lea     r8, [rbp+37h+var_90]
0x14058f112  mov     [rbp+37h+var_90], eax
0x14058f115  lea     rdx, [rbp+37h+var_94]
0x14058f119  mov     eax, [rbx]
0x14058f11b  lea     rcx, [rsp+120h+var_E0]
0x14058f120  mov     [rbp+37h+var_94], eax
0x14058f123  mov     [rbp+37h+var_A0], 0
0x14058f12a  call    HalpInterruptApplyOverrides
0x14058f12f  lea     rdx, [rbp+37h+var_68]
0x14058f133  lea     rcx, [rsp+120h+var_E0]
0x14058f138  call    HalpInterruptLineToGsi
0x14058f13d  mov     edi, eax
0x14058f13f  test    eax, eax
0x14058f141  js      loc_14058F214
0x14058f147  mov     eax, [rsi+0B8h]
0x14058f14d  test    al, 40h
0x14058f14f  jnz     short loc_14058F18B
0x14058f151  mov     rcx, [rsi+120h]
0x14058f158  lea     rax, [rbp+37h+var_A0]
0x14058f15c  mov     dword ptr [rsp+120h+var_F8], 1
0x14058f164  xor     r9d, r9d
0x14058f167  mov     [rsp+120h+var_100], rax
0x14058f16c  mov     edx, [rcx+4]
0x14058f16f  lea     r8, [rcx+8]
0x14058f173  mov     ecx, [rcx]
0x14058f175  call    HalpInterruptRemap
0x14058f17a  mov     edi, eax
0x14058f17c  test    eax, eax
0x14058f17e  js      loc_14058F214
0x14058f184  or      dword ptr [rsi+0B8h], 40h
0x14058f18b  lea     rcx, HalpInterruptLock; SpinLock
0x14058f192  mov     [rsp+120h+var_D8], 0FFFFFFFFh
0x14058f19a  mov     [rsp+120h+var_D4], 1
0x14058f1a2  call    HalpAcquireHighLevelLock
0x14058f1a7  mov     edx, [rbp+37h+var_94]
0x14058f1aa  lea     rcx, [rsp+120h+var_E0]
0x14058f1af  mov     r9d, [rbp+37h+var_90]
0x14058f1b3  mov     bl, al
0x14058f1b5  lea     rax, [rsp+120h+var_D8]
0x14058f1ba  mov     r8b, r15b
0x14058f1bd  mov     [rsp+120h+var_F0], rax
0x14058f1c2  lea     rax, [rsp+120h+var_D0]
0x14058f1c7  mov     [rsp+120h+var_F8], rax
0x14058f1cc  mov     dword ptr [rsp+120h+var_100], edx
0x14058f1d0  mov     edx, r14d
0x14058f1d3  call    HalpInterruptSetLineState
0x14058f1d8  mov     dl, bl
0x14058f1da  lea     rcx, HalpInterruptLock
0x14058f1e1  mov     edi, eax
0x14058f1e3  call    HalpReleaseHighLevelLock
0x14058f1e8  test    edi, edi
0x14058f1ea  js      short loc_14058F214
0x14058f1ec  xor     edi, edi
0x14058f1ee  jmp     short loc_14058F214
0x14058f1f0  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x14058f1f7  mov     dword ptr [rsp+120h+var_100], 18Fh
0x14058f1ff  mov     r8d, ebx
0x14058f202  mov     edx, 11h
0x14058f207  mov     rcx, rsi
0x14058f20a  call    HalpTimerSetProblemEx
0x14058f20f  mov     edi, 0C000000Dh
0x14058f214  mov     eax, edi
0x14058f216  mov     rcx, [rbp+37h+var_40]
0x14058f21a  xor     rcx, rsp; StackCookie
0x14058f21d  call    __security_check_cookie
0x14058f222  add     rsp, 0F0h
0x14058f229  pop     r15
0x14058f22b  pop     r14
0x14058f22d  pop     r12
0x14058f22f  pop     rdi
0x14058f230  pop     rsi
0x14058f231  pop     rbx
0x14058f232  pop     rbp
0x14058f233  retn
```
