# VmbusRecvAsyncCompletion

- ea: `0x140056180`
- end: `0x1400567c3`
- name: `VmbusRecvAsyncCompletion`
- size: `1603`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x14001a2a0`
- `0x14001a354`
- `0x14003838c`
- `0x140039fd8`
- `0x14003e14c`
- `0x140053e40`
- `0x1400552f0`
- `0x14005540c`
- `0x140056060`
- `0x140056180`
- `0x140056bb0`
- `0x140056d20`
- `0x140059dc0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056271`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140056271`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400565ad`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400565ad`
- `ntoskrnl!IoGetActivityIdThread` at `0x140056314`
- `ntoskrnl!IoGetActivityIdThread` at `0x140056314`
- `ntoskrnl!EtwProviderEnabled` at `0x1400562ba`
- `ntoskrnl!EtwProviderEnabled` at `0x1400562e8`
- `ntoskrnl!EtwProviderEnabled` at `0x1400562ba`
- `ntoskrnl!EtwProviderEnabled` at `0x1400562e8`
- `rdbss!RxFreeMdl` at `0x14005658f`
- `rdbss!RxFreeMdl` at `0x14005658f`

## pseudocode

```c
__int64 __fastcall VmbusRecvAsyncCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // ebx
  unsigned __int8 v4; // r13
  __int64 v5; // rsi
  __int64 v6; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rbx
  _DWORD *v10; // rdi
  _DWORD *v11; // rax
  unsigned int v12; // ebx
  int v13; // r13d
  unsigned int v14; // eax
  __int64 v15; // rdx
  __int128 *ActivityIdThread; // r12
  unsigned int v17; // r9d
  _DWORD *v18; // r13
  __int64 v19; // r8
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int64 v22; // rdx
  int v23; // ecx
  unsigned int v24; // r15d
  __int64 v25; // r8
  unsigned __int32 v26; // r9d
  __int64 v27; // r9
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  _QWORD *v31; // rbx
  unsigned int v32; // eax
  __int64 v33; // r8
  int v34; // edi
  int v35; // ebx
  __int64 v36; // rdx
  _DWORD *Priority; // [rsp+28h] [rbp-71h]
  __int64 v38; // [rsp+30h] [rbp-69h]
  unsigned int v39; // [rsp+38h] [rbp-61h]
  __int64 v40; // [rsp+38h] [rbp-61h]
  _DWORD *v41; // [rsp+40h] [rbp-59h]
  bool v42; // [rsp+60h] [rbp-39h]
  __int128 v44; // [rsp+78h] [rbp-21h] BYREF
  _DWORD v45[2]; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v46[28]; // [rsp+90h] [rbp-9h]
  unsigned int v47; // [rsp+ACh] [rbp+13h]

  v3 = *(_DWORD *)(a2 + 48);
  v4 = 1;
  v5 = *(_QWORD *)(a3 + 128);
  v6 = a3;
  v42 = 1;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, a2, v3);
    }
    if ( (v3 == -1073741536 || v3 == -1073741493) && *(_DWORD *)(v6 + 12) == 1 )
    {
      v8 = 0;
    }
    else
    {
      __debugbreak();
      v8 = -1073741628;
    }
    goto LABEL_52;
  }
  if ( *(_DWORD *)(v5 + 8) == 1 )
  {
    v9 = *(_QWORD *)(a2 + 8);
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
    {
      v10 = *(_DWORD **)(v9 + 24);
    }
    else
    {
      v11 = MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
      v9 = *(_QWORD *)(a2 + 8);
      v10 = v11;
    }
    v44 = 0;
    if ( (byte_1400712C4 & 0x20) == 0 )
      goto LABEL_27;
    v12 = *(_DWORD *)(v9 + 40);
    v13 = *(unsigned __int16 *)(a3 + 320);
    if ( !EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x200000000uLL) )
    {
      v6 = a3;
      goto LABEL_28;
    }
    if ( !EtwProviderEnabled(REMOTEFS_SMB_Context, 0, 0x800000000000uLL) && v12 >= 0x40 && *v10 == 1112364030 )
    {
      v14 = v10[5] + 576;
      if ( v14 > v12 )
        v14 = v12;
      v12 = v14;
    }
    ActivityIdThread = (__int128 *)IoGetActivityIdThread();
    if ( !ActivityIdThread )
    {
      ActivityIdThread = &v44;
      v44 = (unsigned __int64)_InterlockedIncrement64(&Correlation);
    }
    if ( v12 < 0xF000 )
    {
      v41 = v10;
      v39 = v12;
      HIDWORD(v38) = (unsigned __int64)(a3 + 428) >> 32;
      Template_qqbqb_ex(REMOTEFS_SMB_Context, v15, 0x200000000LL, ActivityIdThread, v13);
LABEL_27:
      v6 = a3;
      goto LABEL_28;
    }
    v20 = *(_OWORD *)(a3 + 428);
    v45[0] = v13;
    v21 = *(_OWORD *)(a3 + 440);
    *(_OWORD *)v46 = v20;
    Priority = v45;
    *(_OWORD *)&v46[12] = v21;
    v47 = v12;
    v45[1] = 28;
    v23 = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v15, 0x240000000LL, ActivityIdThread, 40);
    while ( 1 )
    {
      if ( v23 < 0 )
        goto LABEL_27;
      if ( v12 < 0xF000 )
        break;
      v25 = 0x200000000LL;
      v24 = 61440;
      if ( v12 == 61440 )
        goto LABEL_39;
LABEL_40:
      HIDWORD(Priority) = HIDWORD(v10);
      v23 = Template_qqbjqb_ex(REMOTEFS_SMB_Context, v22, v25, ActivityIdThread, v24);
      v10 = (_DWORD *)((char *)v10 + v24);
      v12 -= v24;
      if ( !v12 )
        goto LABEL_27;
    }
    v24 = v12;
LABEL_39:
    v25 = 0x280000000LL;
    goto LABEL_40;
  }
LABEL_28:
  *(_DWORD *)(v5 + 24) += *(_DWORD *)(a2 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LODWORD(v38) = *(_DWORD *)(v5 + 20);
    LODWORD(Priority) = *(_DWORD *)(v5 + 24);
    WPP_SF_qDDD(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned int)Priority,
      a3,
      a2,
      *(_DWORD *)(a2 + 56),
      Priority,
      v38,
      v39,
      v41);
  }
  v17 = *(_DWORD *)(v5 + 24);
  v18 = (_DWORD *)(v5 + 20);
  v19 = *(unsigned int *)(v5 + 20);
  if ( v17 < (unsigned int)v19 )
    goto LABEL_33;
  if ( !*(_DWORD *)(v5 + 8) )
  {
    v26 = _byteswap_ulong(*(_DWORD *)(v5 + 12));
    *(_DWORD *)(v5 + 12) = v26;
    v27 = v26 & 0xFF000000;
    if ( (_DWORD)v27 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v29 = 18;
LABEL_49:
        WPP_SF_d(v28->AttachedDevice, v29, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v27);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    *(_BYTE *)(v5 + 15) = 0;
    v27 = *(unsigned int *)(v5 + 12);
    if ( (unsigned int)(v27 - 16) > 0xFFFF0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v29 = 19;
        goto LABEL_49;
      }
LABEL_50:
      __debugbreak();
    }
    v31 = (_QWORD *)(v5 + 32);
    *(_DWORD *)(v5 + 8) = 1;
    *(_DWORD *)(v5 + 16) = 0;
    *(_DWORD *)(v5 + 24) = 0;
    v40 = v5 + 32;
    v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)(v6 + 392) + 16LL))(v6, 0, 0);
    if ( v32 != -1073741802 || *v18 > *(_DWORD *)(v5 + 12) || !*v18 || !*v31 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        LODWORD(v40) = *(_DWORD *)(v5 + 12);
        WPP_SF_LLqLL(WPP_GLOBAL_Control->AttachedDevice, 0, v33, v32, 0, *v31, (unsigned int)*v18, v40);
      }
      goto LABEL_50;
    }
LABEL_33:
    v8 = -1073741802;
    goto LABEL_86;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LODWORD(v38) = *(_DWORD *)(v5 + 16);
    LODWORD(Priority) = *(_DWORD *)(v5 + 12);
    WPP_SF_LLLL(
      WPP_GLOBAL_Control->AttachedDevice,
      21,
      WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids,
      (unsigned int)v19,
      v17,
      Priority,
      v38);
    v19 = (unsigned int)*v18;
  }
  v34 = *(_DWORD *)(v5 + 16) + *(_DWORD *)(v5 + 24);
  v35 = *(_DWORD *)(v5 + 12);
  v36 = *(_QWORD *)(v5 + 40);
  *(_DWORD *)(v5 + 16) = v34;
  v42 = v34 == v35;
  (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)(a3 + 392) + 24LL))(a3, v36, v19, 0);
  if ( v34 == v35 )
  {
    *v18 = 4;
    *(_DWORD *)(v5 + 24) = 0;
    *(_QWORD *)(v5 + 32) = 0;
    *(_QWORD *)(v5 + 40) = 0;
    *(_DWORD *)(v5 + 8) = 0;
    goto LABEL_33;
  }
  v8 = 0;
LABEL_86:
  v4 = v42;
  if ( *(_BYTE *)(a2 + 65) )
  {
    v6 = a3;
    if ( v42 )
    {
      v8 = VmbusRecvAsync((PVOID)a3);
      if ( v8 == 259 )
        v8 = 0;
    }
  }
  else
  {
    v6 = a3;
  }
LABEL_52:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v8, v4);
  }
  *(_DWORD *)(a2 + 48) = v8;
  if ( (int)(v8 + 0x80000000) >= 0 && v8 != -1073741802 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids, v8);
    }
    RxVmbusDisconnectEvent((PVOID)v6);
  }
  RxFreeMdl(*(_QWORD *)(a2 + 8));
  if ( *(_BYTE *)(a2 + 65) )
    RxVmbusFreeIrp(a2);
  ExReleaseRundownProtection((PEX_RUNDOWN_REF)v5);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140056180  mov     [rsp-8+arg_0], rbx
0x140056185  push    rbp
0x140056186  push    rsi
0x140056187  push    rdi
0x140056188  push    r12
0x14005618a  push    r13
0x14005618c  push    r14
0x14005618e  push    r15
0x140056190  lea     rbp, [rsp-27h]
0x140056195  sub     rsp, 0C0h
0x14005619c  mov     rax, cs:__security_cookie
0x1400561a3  xor     rax, rsp
0x1400561a6  mov     [rbp+57h+var_40], rax
0x1400561aa  mov     ebx, [rdx+30h]
0x1400561ad  mov     r13b, 1
0x1400561b0  mov     rsi, [r8+80h]
0x1400561b7  mov     rdi, r8
0x1400561ba  mov     [rbp+57h+var_90], r13b
0x1400561be  mov     r14, rdx
0x1400561c1  mov     [rbp+57h+pContext], r8
0x1400561c5  mov     [rbp+57h+var_80], 0
0x1400561cc  test    ebx, ebx
0x1400561ce  jns     short loc_14005623B
0x1400561d0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400561d7  lea     r12, WPP_GLOBAL_Control
0x1400561de  mov     r15d, 200h
0x1400561e4  cmp     rcx, r12
0x1400561e7  jz      short loc_140056211
0x1400561e9  test    [rcx+2Ch], r15d
0x1400561ed  jz      short loc_140056211
0x1400561ef  cmp     [rcx+29h], r13b
0x1400561f3  jb      short loc_140056211
0x1400561f5  mov     rcx, [rcx+18h]
0x1400561f9  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140056200  mov     edx, 10h
0x140056205  mov     [rsp+0F0h+BugCheckOnFailure], ebx
0x140056209  mov     r9, r14
0x14005620c  call    WPP_SF_qD
0x140056211  cmp     ebx, 0C0000120h
0x140056217  jz      short loc_140056221
0x140056219  cmp     ebx, 0C000014Bh
0x14005621f  jnz     short loc_140056230
0x140056221  mov     eax, [rdi+0Ch]
0x140056224  cmp     eax, 1
0x140056227  jnz     short loc_140056230
0x140056229  xor     ebx, ebx
0x14005622b  jmp     loc_140056503
0x140056230  int     3; Trap to Debugger
0x140056231  mov     ebx, 0C00000C4h
0x140056236  jmp     loc_140056503
0x14005623b  cmp     dword ptr [rsi+8], 1
0x14005623f  jnz     loc_140056389
0x140056245  mov     rbx, [rdx+8]
0x140056249  test    byte ptr [rbx+0Ah], 5
0x14005624d  jz      short loc_140056255
0x14005624f  mov     rdi, [rbx+18h]
0x140056253  jmp     short loc_140056284
0x140056255  xor     r9d, r9d; RequestedAddress
0x140056258  mov     [rsp+0F0h+Priority], 40000010h; Priority
0x140056260  xor     edx, edx; AccessMode
0x140056262  mov     [rsp+0F0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14005626a  mov     rcx, rbx; MemoryDescriptorList
0x14005626d  lea     r8d, [r9+1]; CacheType
0x140056271  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140056278  nop     dword ptr [rax+rax+00h]
0x14005627d  mov     rbx, [r14+8]
0x140056281  mov     rdi, rax
0x140056284  test    cs:byte_1400712C4, 20h
0x14005628b  xorps   xmm0, xmm0
0x14005628e  movups  [rbp+57h+var_78], xmm0
0x140056292  jz      loc_140056385
0x140056298  mov     r15, [rbp+57h+pContext]
0x14005629c  xor     edx, edx; Level
0x14005629e  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x1400562a5  mov     r8, 200000000h; Keyword
0x1400562af  mov     ebx, [rbx+28h]
0x1400562b2  movzx   r13d, word ptr [r15+140h]
0x1400562ba  call    cs:__imp_EtwProviderEnabled
0x1400562c1  nop     dword ptr [rax+rax+00h]
0x1400562c6  test    al, al
0x1400562c8  jz      loc_14005649E
0x1400562ce  mov     rcx, cs:REMOTEFS_SMB_Context; RegHandle
0x1400562d5  xor     edx, edx; Level
0x1400562d7  mov     r8, 800000000000h; Keyword
0x1400562e1  add     r15, 1ACh
0x1400562e8  call    cs:__imp_EtwProviderEnabled
0x1400562ef  nop     dword ptr [rax+rax+00h]
0x1400562f4  test    al, al
0x1400562f6  jnz     short loc_140056314
0x1400562f8  cmp     ebx, 40h ; '@'
0x1400562fb  jb      short loc_140056314
0x1400562fd  cmp     dword ptr [rdi], 424D53FEh
0x140056303  jnz     short loc_140056314
0x140056305  mov     eax, [rdi+14h]
0x140056308  add     eax, 240h
0x14005630d  cmp     eax, ebx
0x14005630f  cmova   eax, ebx
0x140056312  mov     ebx, eax
0x140056314  call    cs:__imp_IoGetActivityIdThread
0x14005631b  nop     dword ptr [rax+rax+00h]
0x140056320  mov     r12, rax
0x140056323  test    rax, rax
0x140056326  jnz     short loc_140056348
0x140056328  xorps   xmm0, xmm0
0x14005632b  lea     eax, [r12+1]
0x140056330  movups  [rbp+57h+var_78], xmm0
0x140056334  lock xadd cs:Correlation, rax
0x14005633d  inc     rax
0x140056340  lea     r12, [rbp+57h+var_78]
0x140056344  mov     qword ptr [rbp+57h+var_78], rax
0x140056348  mov     rcx, cs:REMOTEFS_SMB_Context
0x14005634f  mov     eax, r13d
0x140056352  mov     r13d, 0F000h
0x140056358  mov     r9, r12
0x14005635b  cmp     ebx, r13d
0x14005635e  jnb     loc_1400563F9
0x140056364  mov     [rsp+0F0h+var_B0], rdi
0x140056369  mov     r8, 200000000h
0x140056373  mov     dword ptr [rsp+0F0h+var_B8], ebx
0x140056377  mov     [rsp+0F0h+var_C0], r15
0x14005637c  mov     [rsp+0F0h+BugCheckOnFailure], eax
0x140056380  call    Template_qqbqb_ex
0x140056385  mov     rdi, [rbp+57h+pContext]
0x140056389  mov     eax, [r14+38h]
0x14005638d  add     [rsi+18h], eax
0x140056390  mov     edx, [rsi+18h]
0x140056393  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005639a  lea     r12, WPP_GLOBAL_Control
0x1400563a1  mov     r15d, 200h
0x1400563a7  cmp     rcx, r12
0x1400563aa  jz      short loc_1400563D7
0x1400563ac  test    [rcx+2Ch], r15d
0x1400563b0  jz      short loc_1400563D7
0x1400563b2  cmp     byte ptr [rcx+29h], 4
0x1400563b6  jb      short loc_1400563D7
0x1400563b8  mov     eax, [rsi+14h]
0x1400563bb  mov     r9, r14
0x1400563be  mov     rcx, [rcx+18h]
0x1400563c2  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1400563c6  mov     eax, [r14+38h]
0x1400563ca  mov     [rsp+0F0h+Priority], edx
0x1400563ce  mov     [rsp+0F0h+BugCheckOnFailure], eax
0x1400563d2  call    WPP_SF_qDDD
0x1400563d7  mov     r9d, [rsi+18h]
0x1400563db  lea     r13, [rsi+14h]
0x1400563df  mov     r8d, [r13+0]
0x1400563e3  xor     r10d, r10d
0x1400563e6  cmp     r9d, r8d
0x1400563e9  jnb     loc_1400564A6
0x1400563ef  mov     ebx, 0C0000016h
0x1400563f4  jmp     loc_14005678E
0x1400563f9  movups  xmm0, xmmword ptr [r15]
0x1400563fd  mov     [rbp+57h+var_68], eax
0x140056400  lea     rax, [rbp+57h+var_68]
0x140056404  movups  xmm1, xmmword ptr [r15+0Ch]
0x140056409  mov     [rbp+57h+var_50], 0
0x140056411  mov     r8, 240000000h
0x14005641b  movups  [rbp+57h+var_60], xmm0
0x14005641f  mov     [rbp+57h+var_48], 0
0x140056426  mov     qword ptr [rsp+0F0h+Priority], rax
0x14005642b  movups  [rbp+57h+var_60+0Ch], xmm1
0x14005642f  mov     [rbp+57h+var_44], ebx
0x140056432  mov     [rbp+57h+var_64], 1Ch
0x140056439  mov     [rsp+0F0h+BugCheckOnFailure], 28h ; '('
0x140056441  call    Template_qqbjqb_ex
0x140056446  mov     ecx, eax
0x140056448  test    ecx, ecx
0x14005644a  js      loc_140056385
0x140056450  cmp     ebx, r13d
0x140056453  jnb     short loc_14005645A
0x140056455  mov     r15d, ebx
0x140056458  jmp     short loc_140056469
0x14005645a  mov     r8, 200000000h
0x140056464  mov     r15d, r13d
0x140056467  jnz     short loc_140056473
0x140056469  mov     r8, 280000000h
0x140056473  mov     rcx, cs:REMOTEFS_SMB_Context
0x14005647a  mov     r9, r12
0x14005647d  mov     qword ptr [rsp+0F0h+Priority], rdi
0x140056482  mov     [rsp+0F0h+BugCheckOnFailure], r15d
0x140056487  call    Template_qqbjqb_ex
0x14005648c  mov     ecx, eax
0x14005648e  mov     eax, r15d
0x140056491  add     rdi, rax
0x140056494  sub     ebx, r15d
0x140056497  jnz     short loc_140056448
0x140056499  jmp     loc_140056385
0x14005649e  mov     rdi, r15
0x1400564a1  jmp     loc_140056389
0x1400564a6  cmp     [rsi+8], r10d
0x1400564aa  jnz     loc_1400566F3
0x1400564b0  mov     r9d, [rsi+0Ch]
0x1400564b4  bswap   r9d
0x1400564b7  mov     [rsi+0Ch], r9d
0x1400564bb  and     r9d, 0FF000000h
0x1400564c2  jz      loc_1400565E6
0x1400564c8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400564cf  cmp     rcx, r12
0x1400564d2  jz      short loc_1400564F5
0x1400564d4  test    [rcx+2Ch], r15d
0x1400564d8  jz      short loc_1400564F5
0x1400564da  cmp     byte ptr [rcx+29h], 1
0x1400564de  jb      short loc_1400564F5
0x1400564e0  mov     edx, 12h
0x1400564e5  mov     rcx, [rcx+18h]
0x1400564e9  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x1400564f0  call    WPP_SF_d
0x1400564f5  int     3; Trap to Debugger
0x1400564f6  mov     r13b, [rbp+57h+var_90]
0x1400564fa  mov     ebx, 0C00000C4h
0x1400564ff  mov     rdi, [rbp+57h+pContext]
0x140056503  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005650a  cmp     rcx, r12
0x14005650d  jz      short loc_14005653B
0x14005650f  test    [rcx+2Ch], r15d
0x140056513  jz      short loc_14005653B
0x140056515  cmp     byte ptr [rcx+29h], 4
0x140056519  jb      short loc_14005653B
0x14005651b  mov     rcx, [rcx+18h]
0x14005651f  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140056526  movzx   eax, r13b
0x14005652a  mov     edx, 16h
0x14005652f  mov     r9d, ebx
0x140056532  mov     [rsp+0F0h+BugCheckOnFailure], eax
0x140056536  call    WPP_SF_Dd
0x14005653b  mov     ecx, 80000000h
0x140056540  mov     [r14+30h], ebx
0x140056544  lea     eax, [rbx+rcx]
0x140056547  test    ecx, eax
0x140056549  jnz     short loc_14005658B
0x14005654b  cmp     ebx, 0C0000016h
0x140056551  jz      short loc_14005658B
0x140056553  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14005655a  cmp     rcx, r12
0x14005655d  jz      short loc_140056583
0x14005655f  test    [rcx+2Ch], r15d
0x140056563  jz      short loc_140056583
0x140056565  cmp     byte ptr [rcx+29h], 1
0x140056569  jb      short loc_140056583
0x14005656b  mov     rcx, [rcx+18h]
0x14005656f  lea     r8, WPP_1aa408cf43a53df084d1ad3a10e953fa_Traceguids
0x140056576  mov     edx, 17h
0x14005657b  mov     r9d, ebx
0x14005657e  call    WPP_SF_d
0x140056583  mov     rcx, rdi; pContext
0x140056586  call    RxVmbusDisconnectEvent
0x14005658b  mov     rcx, [r14+8]
0x14005658f  call    cs:__imp_RxFreeMdl
0x140056596  nop     dword ptr [rax+rax+00h]
0x14005659b  cmp     byte ptr [r14+41h], 0
0x1400565a0  jz      short loc_1400565AA
0x1400565a2  mov     rcx, r14
0x1400565a5  call    RxVmbusFreeIrp
0x1400565aa  mov     rcx, rsi; RunRef
0x1400565ad  call    cs:__imp_ExReleaseRundownProtection
0x1400565b4  nop     dword ptr [rax+rax+00h]
0x1400565b9  mov     eax, 0C0000016h
0x1400565be  mov     rcx, [rbp+57h+var_40]
0x1400565c2  xor     rcx, rsp; StackCookie
0x1400565c5  call    __security_check_cookie
0x1400565ca  mov     rbx, [rsp+0F0h+arg_0]
0x1400565d2  add     rsp, 0C0h
0x1400565d9  pop     r15
0x1400565db  pop     r14
0x1400565dd  pop     r13
0x1400565df  pop     r12
0x1400565e1  pop     rdi
0x1400565e2  pop     rsi
0x1400565e3  pop     rbp
0x1400565e4  retn
0x1400565e6  mov     [rsi+0Fh], r10b
0x1400565ea  mov     r9d, [rsi+0Ch]
0x1400565ee  lea     eax, [r9-10h]
0x1400565f2  cmp     eax, 0FFFF0h
0x1400565f7  ja      loc_1400566C5
0x1400565fd  mov     [rsp+0F0h+var_A8], r13
0x140056602  lea     rcx, [rsi+28h]
0x140056606  mov     [rsp+0F0h+var_B0], rcx
0x14005660b  lea     rbx, [rsi+20h]
0x14005660f  mov     dword ptr [rsi+8], 1
0x140056616  lea     rcx, [rbp+57h+var_80]
0x14005661a  mov     [rsi+10h], r10d
0x14005661e  xor     r8d, r8d
0x140056621  mov     [rsi+18h], r10d
0x140056625  xor     edx, edx
0x140056627  mov     rax, [rdi+188h]
0x14005662e  mov     [rsp+0F0h+var_B8], rbx
0x140056633  mov     [rsp+0F0h+var_C0], r10
0x140056638  mov     qword ptr [rsp+0F0h+Priority], rcx
0x14005663d  mov     rcx, rdi
0x140056640  mov     rax, [rax+10h]
0x140056644  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], r10
0x140056649  call    _guard_dispatch_icall
0x14005664e  mov     edx, [rbp+57h+var_80]
0x140056651  mov     r9d, eax
0x140056654  cmp     eax, 0C0000016h
0x140056659  jnz     short loc_140056678
0x14005665b  xor     r10d, r10d
0x14005665e  test    edx, edx
0x140056660  jnz     short loc_140056678
  ... truncated ...
```
