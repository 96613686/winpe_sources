# HalpTimerConfigureInterrupt

- ea: `0x140587890`
- end: `0x140587cc5`
- name: `HalpTimerConfigureInterrupt`
- size: `1077`
- prototype: ``
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140536fcc`
- `0x1405374d4`
- `0x140587490`
- `0x14058a5dc`

## callees

- `0x140240f10`
- `0x14024113c`
- `0x140241bf0`
- `0x140241c1c`
- `0x14024512c`
- `0x140245e6c`
- `0x140247d30`
- `0x1404ae7fc`
- `0x1404cfd54`
- `0x1404e5d1c`
- `0x140537080`
- `0x140582254`
- `0x140587890`
- `0x140588d9c`
- `0x1406d9d70`
- `0x1406e8590`
- `0x1406f4880`

## string_xrefs

- `0x140587a5a`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x140587ab7`: `minkernel\hals\lib\timers\common\timersup.c`
- `0x140587c80`: `minkernel\hals\lib\timers\common\timersup.c`

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
    v33 = HalpAcquireHighLevelLock(&HalpDeviceBlockUnblockPushLock.Timer.DueTime.QuadPart);
    v34 = HalpInterruptSetLineState((unsigned __int64 *)&v39, a2, a3, v49, v48, (__int64)&v41, (__int64)v40);
    LOBYTE(v35) = v33;
    v28 = v34;
    HalpReleaseHighLevelLock(&HalpDeviceBlockUnblockPushLock.Timer.DueTime, v35, v36, v37);
    if ( v28 >= 0 )
      return 0;
  }
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x140587890  push    rbp
0x140587892  push    rbx
0x140587893  push    rsi
0x140587894  push    rdi
0x140587895  push    r12
0x140587897  push    r14
0x140587899  push    r15
0x14058789b  lea     rbp, [rsp-7]
0x1405878a0  sub     rsp, 0F0h
0x1405878a7  mov     rax, cs:__security_cookie
0x1405878ae  xor     rax, rsp
0x1405878b1  mov     [rbp+37h+var_40], rax
0x1405878b5  mov     rdi, [rbp+37h+arg_30]
0x1405878b9  xor     eax, eax
0x1405878bb  mov     r15b, r8b
0x1405878be  mov     [rsp+120h+var_D0], 6
0x1405878c7  mov     r14d, edx
0x1405878ca  mov     [rsp+120h+var_C4], eax
0x1405878ce  mov     rsi, rcx
0x1405878d1  mov     [rsp+120h+var_E0], rax
0x1405878d6  xorps   xmm0, xmm0
0x1405878d9  lea     r8d, [rax+58h]; Size
0x1405878dd  xor     edx, edx; Val
0x1405878df  lea     rcx, [rbp+37h+var_A0]; void *
0x1405878e3  movups  [rsp+120h+var_B8], xmm0
0x1405878e8  call    memset_0
0x1405878ed  movups  xmm0, xmmword ptr [rdi]
0x1405878f0  mov     ebx, [rbp+37h+arg_28]
0x1405878f3  mov     rcx, rdi
0x1405878f6  and     ebx, 3FFFFFFFh
0x1405878fc  mov     [rbp+37h+var_9C], r14d
0x140587900  mov     eax, ebx
0x140587902  mov     [rbp+37h+var_98], r15b
0x140587906  bts     eax, 1Eh
0x14058790a  mov     [rbp+37h+var_78], eax
0x14058790d  movdqu  [rbp+37h+var_88], xmm0
0x140587912  call    KeFindFirstSetRightGroupAffinity
0x140587917  mov     [rsp+120h+var_C8], eax
0x14058791b  lea     rax, [rsp+120h+var_B8]
0x140587920  mov     [rsp+120h+var_C0], rax
0x140587925  mov     eax, dword ptr [rsp+120h+var_B8]
0x140587929  and     eax, 0C0000000h
0x14058792e  or      eax, ebx
0x140587930  mov     dword ptr [rsp+120h+var_B8], eax
0x140587934  mov     eax, [rsi+0E0h]
0x14058793a  bt      eax, 0Bh
0x14058793e  jnb     short loc_140587977
0x140587940  mov     rcx, rsi
0x140587943  call    HalpTimerGetInternalData
0x140587948  mov     rcx, rax
0x14058794b  mov     edx, r14d
0x14058794e  mov     rax, [rsi+0A8h]
0x140587955  call    _guard_dispatch_icall_no_overrides
0x14058795a  mov     rax, [rbp+37h+arg_20]
0x14058795e  mov     r8b, r15b
0x140587961  mov     rdx, [rbp+37h+arg_38]
0x140587965  mov     ecx, r14d
0x140587968  mov     [rsp+120h+var_100], rax
0x14058796d  call    HalpInterruptSetIdtEntry
0x140587972  jmp     loc_140587C7C
0x140587977  mov     r12, [rbp+37h+arg_20]
0x14058797b  mov     ebx, 0C00000BBh
0x140587980  mov     edi, 1
0x140587985  bt      eax, 0Ah
0x140587989  jnb     loc_140587A88
0x14058798f  mov     cl, dil
0x140587992  call    HalpInterruptIsMsiSupported
0x140587997  test    al, al
0x140587999  jz      loc_140587A88
0x14058799f  mov     eax, [rsi+0B8h]
0x1405879a5  and     al, 50h
0x1405879a7  cmp     al, 40h ; '@'
0x1405879a9  jz      loc_140587A88
0x1405879af  mov     rdx, [rbp+37h+arg_38]
0x1405879b3  mov     r8b, r15b
0x1405879b6  mov     ecx, r14d
0x1405879b9  mov     [rsp+120h+var_100], r12
0x1405879be  call    HalpInterruptSetIdtEntry
0x1405879c3  mov     eax, [rsi+0B8h]
0x1405879c9  test    al, 40h
0x1405879cb  jnz     short loc_140587A2C
0x1405879cd  mov     rcx, [rsi+120h]
0x1405879d4  lea     rax, [rbp+37h+var_A0]
0x1405879d8  mov     [rbp+37h+var_A0], 3
0x1405879df  xor     r9d, r9d
0x1405879e2  mov     [rbp+37h+var_90], edi
0x1405879e5  mov     [rbp+37h+var_94], 0
0x1405879ec  mov     edx, [rcx+4]
0x1405879ef  lea     r8, [rcx+8]
0x1405879f3  mov     ecx, [rcx]
0x1405879f5  mov     dword ptr [rsp+120h+var_F8], edi
0x1405879f9  mov     [rsp+120h+var_100], rax
0x1405879fe  call    HalpInterruptRemap
0x140587a03  mov     ebx, eax
0x140587a05  test    eax, eax
0x140587a07  js      short loc_140587A88
0x140587a09  mov     eax, [rbp+37h+var_74]
0x140587a0c  or      dword ptr [rsi+0B8h], 40h
0x140587a13  mov     [rsi+0ECh], eax
0x140587a19  mov     eax, [rbp+37h+var_70]
0x140587a1c  mov     [rsi+0E8h], eax
0x140587a22  mov     eax, [rbp+37h+var_6C]
0x140587a25  mov     [rsi+0F0h], rax
0x140587a2c  mov     rcx, rsi
0x140587a2f  call    HalpTimerGetInternalData
0x140587a34  mov     r9d, [rsi+0F0h]
0x140587a3b  mov     rcx, rax
0x140587a3e  mov     rax, [rsi+98h]
0x140587a45  mov     dl, dil
0x140587a48  mov     r8, [rsi+0E8h]
0x140587a4f  call    _guard_dispatch_icall_no_overrides
0x140587a54  mov     ebx, eax
0x140587a56  test    eax, eax
0x140587a58  jns     short loc_140587ACB
0x140587a5a  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140587a61  mov     dword ptr [rsp+120h+var_100], 905h
0x140587a69  mov     r8d, eax
0x140587a6c  mov     edx, 18h
0x140587a71  mov     rcx, rsi
0x140587a74  call    HalpTimerSetProblemEx
0x140587a79  mov     r8d, [rbp+37h+arg_28]
0x140587a7d  mov     r9b, dil
0x140587a80  mov     edx, r14d
0x140587a83  call    HalpTimerUnmapInterrupt
0x140587a88  mov     eax, [rsi+0E0h]
0x140587a8e  bt      eax, 9
0x140587a92  jnb     short loc_140587ADD
0x140587a94  mov     ecx, [rsi+58h]
0x140587a97  lea     rdx, [rsp+120h+var_E0]
0x140587a9c  call    HalpInterruptGsiToLine
0x140587aa1  mov     edi, eax
0x140587aa3  test    eax, eax
0x140587aa5  jns     short loc_140587AD7
0x140587aa7  mov     dword ptr [rsp+120h+var_100], 180h
0x140587aaf  mov     edx, 10h
0x140587ab4  mov     r8d, eax
0x140587ab7  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140587abe  mov     rcx, rsi
0x140587ac1  call    HalpTimerSetProblemEx
0x140587ac6  jmp     loc_140587CA4
0x140587acb  or      dword ptr [rsi+0B8h], 10h
0x140587ad2  jmp     loc_140587C7C
0x140587ad7  lea     rbx, [rsi+5Ch]
0x140587adb  jmp     short loc_140587B16
0x140587add  bt      eax, 8
0x140587ae1  jnb     loc_140587C80
0x140587ae7  mov     eax, [rsi+54h]
0x140587aea  cmp     eax, 8
0x140587aed  jnb     short loc_140587AF9
0x140587aef  mov     dword ptr [rsp+120h+var_E0], 0B000h
0x140587af7  jmp     short loc_140587B04
0x140587af9  mov     dword ptr [rsp+120h+var_E0], 0B001h
0x140587b01  add     eax, 0FFFFFFF8h
0x140587b04  lea     rbx, [rsi+5Ch]
0x140587b08  mov     dword ptr [rsp+120h+var_E0+4], eax
0x140587b0c  cmp     dword ptr [rbx], 0
0x140587b0f  jnz     short loc_140587B16
0x140587b11  mov     [rbx], edi
0x140587b13  mov     [rsi+60h], edi
0x140587b16  mov     rdx, [rbp+37h+arg_38]
0x140587b1a  mov     r8b, r15b
0x140587b1d  mov     ecx, r14d
0x140587b20  mov     [rsp+120h+var_100], r12
0x140587b25  call    HalpInterruptSetIdtEntry
0x140587b2a  mov     eax, [rsi+0B8h]
0x140587b30  test    al, 10h
0x140587b32  jz      short loc_140587B7C
0x140587b34  mov     rcx, rsi
0x140587b37  xor     r8d, r8d
0x140587b3a  call    HalpTimerGetInternalData
0x140587b3f  mov     rcx, rax
0x140587b42  xor     r9d, r9d
0x140587b45  mov     rax, [rsi+98h]
0x140587b4c  xor     edx, edx
0x140587b4e  call    _guard_dispatch_icall_no_overrides
0x140587b53  mov     edi, eax
0x140587b55  test    eax, eax
0x140587b57  jns     short loc_140587B6B
0x140587b59  mov     dword ptr [rsp+120h+var_100], 1AAh
0x140587b61  mov     edx, 18h
0x140587b66  jmp     loc_140587AB4
0x140587b6b  and     dword ptr [rsi+0B8h], 0FFFFFFEFh
0x140587b72  mov     eax, [rsi+0B8h]
0x140587b78  test    al, 10h
0x140587b7a  jnz     short loc_140587B9B
0x140587b7c  cmp     r14d, 0D1h
0x140587b83  jnz     short loc_140587B9B
0x140587b85  mov     rax, [rsp+120h+var_E0]
0x140587b8a  mov     cs:HalpTimerCriticalClockSource, rax
0x140587b91  mov     cs:HalpTimerCriticalClockSourceCount, 1
0x140587b9b  mov     eax, [rsi+60h]
0x140587b9e  lea     r8, [rbp+37h+var_90]
0x140587ba2  mov     [rbp+37h+var_90], eax
0x140587ba5  lea     rdx, [rbp+37h+var_94]
0x140587ba9  mov     eax, [rbx]
0x140587bab  lea     rcx, [rsp+120h+var_E0]
0x140587bb0  mov     [rbp+37h+var_94], eax
0x140587bb3  mov     [rbp+37h+var_A0], 0
0x140587bba  call    HalpInterruptApplyOverrides
0x140587bbf  lea     rdx, [rbp+37h+var_68]
0x140587bc3  lea     rcx, [rsp+120h+var_E0]
0x140587bc8  call    HalpInterruptLineToGsi
0x140587bcd  mov     edi, eax
0x140587bcf  test    eax, eax
0x140587bd1  js      loc_140587CA4
0x140587bd7  mov     eax, [rsi+0B8h]
0x140587bdd  test    al, 40h
0x140587bdf  jnz     short loc_140587C1B
0x140587be1  mov     rcx, [rsi+120h]
0x140587be8  lea     rax, [rbp+37h+var_A0]
0x140587bec  mov     dword ptr [rsp+120h+var_F8], 1
0x140587bf4  xor     r9d, r9d
0x140587bf7  mov     [rsp+120h+var_100], rax
0x140587bfc  mov     edx, [rcx+4]
0x140587bff  lea     r8, [rcx+8]
0x140587c03  mov     ecx, [rcx]
0x140587c05  call    HalpInterruptRemap
0x140587c0a  mov     edi, eax
0x140587c0c  test    eax, eax
0x140587c0e  js      loc_140587CA4
0x140587c14  or      dword ptr [rsi+0B8h], 40h
0x140587c1b  lea     rcx, HalpDeviceBlockUnblockPushLock.Timer.DueTime; SpinLock
0x140587c22  mov     [rsp+120h+var_D8], 0FFFFFFFFh
0x140587c2a  mov     [rsp+120h+var_D4], 1
0x140587c32  call    HalpAcquireHighLevelLock
0x140587c37  mov     edx, [rbp+37h+var_94]
0x140587c3a  lea     rcx, [rsp+120h+var_E0]
0x140587c3f  mov     r9d, [rbp+37h+var_90]
0x140587c43  mov     bl, al
0x140587c45  lea     rax, [rsp+120h+var_D8]
0x140587c4a  mov     r8b, r15b
0x140587c4d  mov     [rsp+120h+var_F0], rax
0x140587c52  lea     rax, [rsp+120h+var_D0]
0x140587c57  mov     [rsp+120h+var_F8], rax
0x140587c5c  mov     dword ptr [rsp+120h+var_100], edx
0x140587c60  mov     edx, r14d
0x140587c63  call    HalpInterruptSetLineState
0x140587c68  mov     dl, bl
0x140587c6a  lea     rcx, HalpDeviceBlockUnblockPushLock.Timer.DueTime
0x140587c71  mov     edi, eax
0x140587c73  call    HalpReleaseHighLevelLock
0x140587c78  test    edi, edi
0x140587c7a  js      short loc_140587CA4
0x140587c7c  xor     edi, edi
0x140587c7e  jmp     short loc_140587CA4
0x140587c80  lea     r9, aMinkernelHalsL_17; "minkernel\\hals\\lib\\timers\\common\\t"...
0x140587c87  mov     dword ptr [rsp+120h+var_100], 18Fh
0x140587c8f  mov     r8d, ebx
0x140587c92  mov     edx, 11h
0x140587c97  mov     rcx, rsi
0x140587c9a  call    HalpTimerSetProblemEx
0x140587c9f  mov     edi, 0C000000Dh
0x140587ca4  mov     eax, edi
0x140587ca6  mov     rcx, [rbp+37h+var_40]
0x140587caa  xor     rcx, rsp; StackCookie
0x140587cad  call    __security_check_cookie
0x140587cb2  add     rsp, 0F0h
0x140587cb9  pop     r15
0x140587cbb  pop     r14
0x140587cbd  pop     r12
0x140587cbf  pop     rdi
0x140587cc0  pop     rsi
0x140587cc1  pop     rbx
0x140587cc2  pop     rbp
0x140587cc3  retn
```
