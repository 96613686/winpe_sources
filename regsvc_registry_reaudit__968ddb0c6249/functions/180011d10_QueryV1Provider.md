# QueryV1Provider

- ea: `0x180011d10`
- end: `0x1800125fe`
- name: `QueryV1Provider`
- size: `2286`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004f00`

## callees

- `0x180005da0`
- `0x180008042`
- `0x180008050`
- `0x18000a0d4`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000ab64`
- `0x18000ac34`
- `0x18000b0e8`
- `0x18000b6d4`
- `0x18000c134`
- `0x18000c424`
- `0x18000c774`
- `0x180011930`
- `0x1800119b4`
- `0x1800119fc`
- `0x180011ad4`
- `0x180011b08`
- `0x180011b88`
- `0x180011bd8`
- `0x180011d10`
- `0x1800126c8`
- `0x18001277c`
- `0x180012d14`
- `0x180012df0`
- `0x180012fac`
- `0x180013094`
- `0x180013160`
- `0x1800131f0`
- `0x1800136b0`
- `0x18001e43d`

## import_xrefs

- `ntdll!RtlQueryPerformanceCounter` at `0x18001212f`
- `ntdll!RtlQueryPerformanceCounter` at `0x180012163`
- `ntdll!RtlQueryPerformanceCounter` at `0x18001212f`
- `ntdll!RtlQueryPerformanceCounter` at `0x180012163`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011db4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011db4`

## pseudocode

```c
__int64 __fastcall QueryV1Provider(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        char *a4,
        unsigned int a5,
        _DWORD *a6,
        _DWORD *a7)
{
  char *v7; // r14
  int v10; // r13d
  int v11; // eax
  unsigned int v12; // r14d
  int v13; // ebx
  __int64 v14; // rdx
  unsigned int *v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // ebx
  char *v18; // r9
  int v19; // r8d
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // r8
  _QWORD *v23; // rcx
  void *v24; // rax
  unsigned int v25; // eax
  int v26; // ecx
  int v27; // r8d
  int v28; // edx
  int v29; // ecx
  void *v30; // r14
  int v31; // ecx
  size_t Size; // [rsp+60h] [rbp-B8h] BYREF
  int v34; // [rsp+68h] [rbp-B0h]
  _DWORD v35[3]; // [rsp+6Ch] [rbp-ACh] BYREF
  void *started; // [rsp+78h] [rbp-A0h]
  int v37; // [rsp+80h] [rbp-98h]
  unsigned int v38; // [rsp+84h] [rbp-94h]
  __int64 v39; // [rsp+88h] [rbp-90h] BYREF
  __int64 v40; // [rsp+90h] [rbp-88h] BYREF
  __int64 v41; // [rsp+98h] [rbp-80h]
  __int64 v42; // [rsp+A0h] [rbp-78h]
  __int64 v43; // [rsp+A8h] [rbp-70h]
  __int64 v44; // [rsp+B0h] [rbp-68h]
  void *Src; // [rsp+B8h] [rbp-60h]
  void *Block; // [rsp+C0h] [rbp-58h]
  __int128 v47; // [rsp+C8h] [rbp-50h] BYREF
  __int128 v48; // [rsp+D8h] [rbp-40h]
  __int64 v49; // [rsp+E8h] [rbp-30h]
  BOOL v52; // [rsp+140h] [rbp+28h]
  unsigned int v53; // [rsp+140h] [rbp+28h]

  v7 = a4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids, a3);
  v10 = 0;
  v37 = 0;
  Size = a5;
  if ( !*(_QWORD *)(a2 + 88) || a3 <= 0xA && (v11 = 1554, _bittest(&v11, a3)) )
  {
    v12 = PerfpLockExtObject(a2);
    if ( v12 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
    }
    else
    {
      if ( !*(_QWORD *)(a2 + 88) )
      {
        v13 = *(_DWORD *)(a2 + 520);
        if ( GetCurrentThreadId() == v13 || *(_DWORD *)(a2 + 484) )
        {
LABEL_16:
          PerfpUnlockExtObject(a2);
          goto LABEL_114;
        }
        v16 = OpenExtObjectLibrary((struct EXT_OBJECT *)a2, v14, v15);
        v12 = v16;
        if ( v16 )
        {
          if ( v16 != 1058
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              17,
              (unsigned int)WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
              *(_QWORD *)(a2 + 392),
              v16);
          }
          goto LABEL_16;
        }
      }
      PerfpUnlockExtObject(a2);
    }
    v7 = a4;
  }
  if ( (lPerflibConfigFlags & 4) != 0 )
  {
    v17 = 4;
    v52 = 0;
  }
  else
  {
    v17 = 1;
    if ( (*(_DWORD *)(a2 + 380) & 0x20) != 0 )
      v17 = lExtCounterTestLevel;
    v52 = (*(_DWORD *)(a2 + 380) & 0x20) == 0;
  }
  v38 = v17;
  *(_QWORD *)&v35[1] = 0;
  if ( v17 >= 4 )
  {
    *(_QWORD *)&v35[1] = v7;
    v18 = v7;
  }
  else
  {
    v18 = (char *)operator new((unsigned int)(Size + 2048));
  }
  Block = v18;
  if ( v18 )
  {
    if ( v17 >= 4 )
    {
      v43 = 0;
      v41 = 0;
      v42 = 0;
    }
    else
    {
      v43 = (__int64)v18;
      *(_QWORD *)&v35[1] = v18 + 1024;
      v42 = (__int64)&v18[(unsigned int)Size + 1024];
      v41 = v42 + 1024;
      memset_0(v18, 165, 0x400u);
      memset_0((void *)v42, 165, 0x400u);
    }
    Src = *(void **)&v35[1];
    v44 = 0;
    started = 0;
    v34 = 0;
    v40 = 0;
    v39 = 0;
    v12 = PerfpLockExtObject(a2);
    v35[0] = v12;
    if ( v12 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
          *(_QWORD *)(a2 + 392));
      if ( (unsigned int)PerfpThrottleError(1015, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
        && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
      {
        McTemplateU0zz_EtwEventWriteTransfer(v20, PERFLIB_COLLECTION_HUNG, *(_QWORD *)(a2 + 392), *(_QWORD *)(a2 + 96));
      }
    }
    else
    {
      v34 = 1;
    }
    if ( !v12 && *(_QWORD *)(a2 + 40) )
    {
      if ( v52 )
      {
        v48 = 0;
        v49 = 0;
        v47 = 0u;
        *((_QWORD *)&v47 + 1) = *(_QWORD *)(a2 + 96);
        *(_QWORD *)&v48 = *(_QWORD *)(a2 + 392);
        DWORD2(v48) = *(_DWORD *)(a2 + 56);
        HIDWORD(v48) = 1015;
        v49 = a2;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
        started = StartPerflibFunctionTimer((struct OPEN_PROC_WAIT_INFO *)&v47);
        if ( !started && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
      }
      v53 = Size;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_SSdd(*((_QWORD *)WPP_GLOBAL_Control + 2), Size, v19, *(_QWORD *)(a2 + 392), a1, Size, SBYTE4(Size));
      RtlQueryPerformanceCounter(&v40);
      v12 = CallExtObj(a2, a1, (unsigned int)&v35[1], (unsigned int)&Size, (__int64)&Size + 4);
      v35[0] = v12;
      RtlQueryPerformanceCounter(&v39);
      v23 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_ddd(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, v12, Size, HIDWORD(Size));
        v23 = WPP_GLOBAL_Control;
      }
      v24 = started;
      if ( started )
      {
        if ( (*((_BYTE *)v23 + 28) & 0x40) != 0 && *((_BYTE *)v23 + 25) >= 4u )
        {
          WPP_SF_(v23[2], 24, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids);
          v24 = started;
        }
        KillPerflibFunctionTimer(v24);
        started = 0;
      }
      v25 = Size;
      *(_DWORD *)(a2 + 468) = Size;
      if ( v25 > *(_DWORD *)(a2 + 472) )
        *(_DWORD *)(a2 + 472) = v25;
      if ( v12 == 234 && v53 > *(_DWORD *)(a2 + 476) )
        *(_DWORD *)(a2 + 476) = v53;
      v44 = *(_QWORD *)&v35[1];
      *(_QWORD *)(a2 + 400) = GetTimeAsLongLong();
      PerfpUnlockExtObject(a2);
      v34 = 0;
      if ( (unsigned int)Size <= v53 )
      {
        if ( (unsigned __int8)ValidateObjectTypeCount((struct EXT_OBJECT *)a2, HIDWORD(Size), Size) )
          goto LABEL_80;
      }
      else
      {
        if ( (unsigned int)PerfpThrottleError(1020, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 2) != 0 )
        {
          McTemplateU0zzqq_EtwEventWriteTransfer(
            v26,
            (unsigned int)PERFLIB_INVALID_SIZE_RETURNED,
            *(_QWORD *)(a2 + 96),
            *(_QWORD *)(a2 + 392),
            v53,
            Size);
        }
        if ( (lPerflibConfigFlags & 4) == 0 && (*(_BYTE *)(a2 + 380) & 0x20) == 0 )
          DisablePerfLibrary((struct EXT_OBJECT *)a2, 1u, 0x3FCu, v53, (unsigned int)Size);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_Sdd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, v27, *(_QWORD *)(a2 + 392), Size, v53);
      }
    }
    Size = 0;
LABEL_80:
    if ( v12 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 464));
    }
    else if ( (_DWORD)Size )
    {
      _InterlockedIncrement((volatile signed __int32 *)(a2 + 448));
      *(_QWORD *)(a2 + 440) += v39 - v40;
      v10 = Size;
      if ( (Size & 7) != 0 && (lPerflibConfigFlags & 1) == 0 && (*(_BYTE *)(a2 + 380) & 8) == 0 )
      {
        if ( (unsigned int)PerfpThrottleError(1016, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
          && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
        {
          McTemplateU0zzpq_EtwEventWriteTransfer(v29, v28, *(_QWORD *)(a2 + 96), *(_QWORD *)(a2 + 392), v35[1], Size);
        }
        *(_DWORD *)(a2 + 380) |= 8u;
        v10 = Size;
      }
      if ( v17 < 4 )
      {
        v30 = Src;
        if ( (unsigned int)ValidateSafeBuffer(
                             (struct EXT_OBJECT *)a2,
                             HIDWORD(Size),
                             (__int64)Src,
                             v44,
                             v43,
                             v42,
                             v41,
                             v17,
                             (__int64)v35) )
        {
          v10 = Size;
          memmove_0(a4, v30, (unsigned int)Size);
        }
        else
        {
          v10 = 0;
          Size = 0;
        }
        v12 = v35[0];
      }
      v37 = v10;
LABEL_100:
      if ( v17 < 4 )
        operator delete(Block);
      goto LABEL_103;
    }
    if ( v34 )
    {
      PerfpUnlockExtObject(a2);
      v34 = 0;
    }
    HIDWORD(Size) = 0;
    goto LABEL_100;
  }
  v12 = 14;
LABEL_103:
  if ( v12 && v12 != 234 && v12 != 258 )
  {
    if ( (unsigned int)PerfpThrottleError(1014, *(HKEY *)(a2 + 104), (struct ERROR_LOG *)(a2 + 488))
      && (Microsoft_Windows_PerflibEnableBits & 4) != 0 )
    {
      McTemplateU0zzq_EtwEventWriteTransfer(
        v31,
        (unsigned int)PERFLIB_COLLECT_PROC_FAILURE,
        *(_QWORD *)(a2 + 392),
        *(_QWORD *)(a2 + 96),
        v12);
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids,
        HIDWORD(Size),
        v12);
  }
  if ( *(_QWORD *)(a2 + 432) )
    PerfpUpdateSection(a2);
LABEL_114:
  *a6 = v10;
  *a7 = HIDWORD(Size);
  return v12;
}

```

## disassembly

```asm
0x180011d10  mov     [rsp+arg_18], r9
0x180011d15  mov     [rsp+arg_8], rdx
0x180011d1a  mov     [rsp+arg_0], rcx
0x180011d1f  push    rbx
0x180011d20  push    rsi
0x180011d21  push    rdi
0x180011d22  push    r13
0x180011d24  push    r14
0x180011d26  sub     rsp, 0F0h
0x180011d2d  mov     r14, r9
0x180011d30  mov     ebx, r8d
0x180011d33  mov     rdi, rdx
0x180011d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d3d  test    byte ptr [rcx+1Ch], 2
0x180011d41  jz      short loc_180011D61
0x180011d43  cmp     byte ptr [rcx+19h], 4
0x180011d47  jb      short loc_180011D61
0x180011d49  mov     edx, 10h
0x180011d4e  mov     r9d, ebx
0x180011d51  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180011d58  mov     rcx, [rcx+10h]
0x180011d5c  call    WPP_SF_d
0x180011d61  xor     esi, esi
0x180011d63  mov     dword ptr [rsp+118h+Size+4], esi
0x180011d67  mov     r13d, esi
0x180011d6a  mov     [rsp+118h+var_98], esi
0x180011d71  mov     eax, dword ptr [rsp+118h+arg_20]
0x180011d78  mov     dword ptr [rsp+118h+Size], eax
0x180011d7c  cmp     [rdi+58h], rsi
0x180011d80  jz      short loc_180011D99
0x180011d82  cmp     ebx, 0Ah
0x180011d85  ja      loc_180011E5D
0x180011d8b  mov     eax, 612h
0x180011d90  bt      eax, ebx
0x180011d93  jnb     loc_180011E5D
0x180011d99  mov     rcx, rdi
0x180011d9c  call    PerfpLockExtObject
0x180011da1  mov     r14d, eax
0x180011da4  test    eax, eax
0x180011da6  jnz     short loc_180011E26
0x180011da8  cmp     [rdi+58h], rsi
0x180011dac  jnz     short loc_180011E1C
0x180011dae  mov     ebx, [rdi+208h]
0x180011db4  call    cs:__imp_GetCurrentThreadId
0x180011dba  cmp     eax, ebx
0x180011dbc  jz      short loc_180011E0F
0x180011dbe  cmp     [rdi+1E4h], esi
0x180011dc4  jnz     short loc_180011E0F
0x180011dc6  mov     rcx, rdi; struct EXT_OBJECT *
0x180011dc9  call    ?OpenExtObjectLibrary@@YAKPEAUEXT_OBJECT@@@Z; OpenExtObjectLibrary(EXT_OBJECT *)
0x180011dce  mov     r14d, eax
0x180011dd1  test    eax, eax
0x180011dd3  jz      short loc_180011E1C
0x180011dd5  cmp     eax, 422h
0x180011dda  jz      short loc_180011E0F
0x180011ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011de3  test    byte ptr [rcx+1Ch], 2
0x180011de7  jz      short loc_180011E0F
0x180011de9  cmp     byte ptr [rcx+19h], 2
0x180011ded  jb      short loc_180011E0F
0x180011def  mov     edx, 11h
0x180011df4  mov     dword ptr [rsp+118h+var_F8], eax
0x180011df8  mov     r9, [rdi+188h]
0x180011dff  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180011e06  mov     rcx, [rcx+10h]
0x180011e0a  call    WPP_SF_Sd
0x180011e0f  mov     rcx, rdi
0x180011e12  call    PerfpUnlockExtObject
0x180011e17  jmp     loc_1800125D3
0x180011e1c  mov     rcx, rdi
0x180011e1f  call    PerfpUnlockExtObject
0x180011e24  jmp     short loc_180011E55
0x180011e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e2d  test    byte ptr [rcx+1Ch], 20h
0x180011e31  jz      short loc_180011E55
0x180011e33  cmp     byte ptr [rcx+19h], 2
0x180011e37  jb      short loc_180011E55
0x180011e39  mov     edx, 12h
0x180011e3e  mov     r9, [rdi+188h]
0x180011e45  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180011e4c  mov     rcx, [rcx+10h]
0x180011e50  call    WPP_SF_S
0x180011e55  mov     r14, [rsp+118h+arg_18]
0x180011e5d  test    byte ptr cs:?lPerflibConfigFlags@@3JA, 4; long lPerflibConfigFlags
0x180011e64  jnz     short loc_180011E8A
0x180011e66  mov     eax, [rdi+17Ch]
0x180011e6c  bt      eax, 5
0x180011e70  mov     ebx, 1
0x180011e75  cmovb   ebx, cs:?lExtCounterTestLevel@@3JA; long lExtCounterTestLevel
0x180011e7c  mov     ecx, esi
0x180011e7e  setnb   cl
0x180011e81  mov     dword ptr [rsp+118h+arg_20], ecx
0x180011e88  jmp     short loc_180011E96
0x180011e8a  mov     ebx, 4
0x180011e8f  mov     dword ptr [rsp+118h+arg_20], esi
0x180011e96  mov     [rsp+118h+var_94], ebx
0x180011e9d  mov     qword ptr [rsp+118h+var_AC+4], rsi
0x180011ea2  cmp     ebx, 4
0x180011ea5  jnb     short loc_180011EBB
0x180011ea7  mov     ecx, dword ptr [rsp+118h+Size]
0x180011eab  add     ecx, 800h
0x180011eb1  call    ??2@YAPEAX_KUzerofill_t@@@Z; operator new(unsigned __int64,zerofill_t)
0x180011eb6  mov     r9, rax
0x180011eb9  jmp     short loc_180011EC3
0x180011ebb  mov     qword ptr [rsp+118h+var_AC+4], r14
0x180011ec0  mov     r9, r14
0x180011ec3  mov     [rsp+118h+Block], r9
0x180011ecb  test    r9, r9
0x180011ece  jz      loc_180012531
0x180011ed4  cmp     ebx, 4
0x180011ed7  jnb     short loc_180011F34
0x180011ed9  mov     [rsp+118h+var_70], r9
0x180011ee1  lea     rcx, [r9+400h]
0x180011ee8  mov     qword ptr [rsp+118h+var_AC+4], rcx
0x180011eed  mov     r14d, dword ptr [rsp+118h+Size]
0x180011ef2  add     r14, rcx
0x180011ef5  mov     [rsp+118h+var_78], r14
0x180011efd  lea     rax, [r14+400h]
0x180011f04  mov     [rsp+118h+var_80], rax
0x180011f0c  mov     edx, 0A5h; Val
0x180011f11  mov     r8d, 400h; Size
0x180011f17  mov     rcx, r9; void *
0x180011f1a  call    memset_0
0x180011f1f  mov     edx, 0A5h; Val
0x180011f24  mov     r8d, 400h; Size
0x180011f2a  mov     rcx, r14; void *
0x180011f2d  call    memset_0
0x180011f32  jmp     short loc_180011F4C
0x180011f34  mov     [rsp+118h+var_70], rsi
0x180011f3c  mov     [rsp+118h+var_80], rsi
0x180011f44  mov     [rsp+118h+var_78], rsi
0x180011f4c  mov     rax, qword ptr [rsp+118h+var_AC+4]
0x180011f51  mov     [rsp+118h+Src], rax
0x180011f59  mov     [rsp+118h+var_68], rsi
0x180011f61  mov     [rsp+118h+var_A0], rsi
0x180011f66  mov     [rsp+118h+var_B0], esi
0x180011f6a  mov     [rsp+118h+var_88], rsi
0x180011f72  mov     [rsp+118h+var_90], rsi
0x180011f7a  mov     rcx, rdi
0x180011f7d  call    PerfpLockExtObject
0x180011f82  mov     r14d, eax
0x180011f85  mov     dword ptr [rsp+118h+var_AC], eax
0x180011f89  test    eax, eax
0x180011f8b  jnz     short loc_180011F97
0x180011f8d  mov     [rsp+118h+var_B0], 1
0x180011f95  jmp     short loc_180011FFF
0x180011f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f9e  test    byte ptr [rcx+1Ch], 2
0x180011fa2  jz      short loc_180011FC6
0x180011fa4  cmp     byte ptr [rcx+19h], 2
0x180011fa8  jb      short loc_180011FC6
0x180011faa  mov     edx, 13h
0x180011faf  mov     r9, [rdi+188h]
0x180011fb6  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x180011fbd  mov     rcx, [rcx+10h]
0x180011fc1  call    WPP_SF_S
0x180011fc6  lea     r8, [rdi+1E8h]; struct ERROR_LOG *
0x180011fcd  mov     rdx, [rdi+68h]; HKEY
0x180011fd1  mov     ecx, 3F7h; unsigned int
0x180011fd6  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x180011fdb  test    eax, eax
0x180011fdd  jz      short loc_180011FFF
0x180011fdf  test    cs:Microsoft_Windows_PerflibEnableBits, 4
0x180011fe6  jz      short loc_180011FFF
0x180011fe8  mov     r9, [rdi+60h]
0x180011fec  mov     r8, [rdi+188h]
0x180011ff3  lea     rdx, PERFLIB_COLLECTION_HUNG
0x180011ffa  call    McTemplateU0zz_EtwEventWriteTransfer
0x180011fff  test    r14d, r14d
0x180012002  jnz     loc_180012328
0x180012008  cmp     [rdi+28h], rsi
0x18001200c  jz      loc_180012328
0x180012012  cmp     dword ptr [rsp+118h+arg_20], esi
0x180012019  jz      loc_1800120E0
0x18001201f  xorps   xmm0, xmm0
0x180012022  xor     eax, eax
0x180012024  movups  [rsp+118h+var_50], xmm0
0x18001202c  movups  [rsp+118h+var_40], xmm0
0x180012034  mov     [rsp+118h+var_30], rax
0x18001203c  mov     qword ptr [rsp+118h+var_50], rsi
0x180012044  mov     rax, [rdi+60h]
0x180012048  mov     qword ptr [rsp+118h+var_50+8], rax
0x180012050  mov     rax, [rdi+188h]
0x180012057  mov     qword ptr [rsp+118h+var_40], rax
0x18001205f  mov     eax, [rdi+38h]
0x180012062  mov     dword ptr [rsp+118h+var_40+8], eax
0x180012069  mov     dword ptr [rsp+118h+var_40+0Ch], 3F7h
0x180012074  mov     [rsp+118h+var_30], rdi
0x18001207c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012083  test    byte ptr [rcx+1Ch], 40h
0x180012087  jz      short loc_1800120A3
0x180012089  cmp     byte ptr [rcx+19h], 4
0x18001208d  jb      short loc_1800120A3
0x18001208f  lea     edx, [r14+14h]
0x180012093  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x18001209a  mov     rcx, [rcx+10h]
0x18001209e  call    WPP_SF_
0x1800120a3  lea     rcx, [rsp+118h+var_50]; struct OPEN_PROC_WAIT_INFO *
0x1800120ab  call    ?StartPerflibFunctionTimer@@YAPEAXPEAUOPEN_PROC_WAIT_INFO@@@Z; StartPerflibFunctionTimer(OPEN_PROC_WAIT_INFO *)
0x1800120b0  mov     [rsp+118h+var_A0], rax
0x1800120b5  test    rax, rax
0x1800120b8  jnz     short loc_1800120E0
0x1800120ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120c1  test    byte ptr [rcx+1Ch], 40h
0x1800120c5  jz      short loc_1800120E0
0x1800120c7  cmp     byte ptr [rcx+19h], 2
0x1800120cb  jb      short loc_1800120E0
0x1800120cd  lea     edx, [rax+15h]
0x1800120d0  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800120d7  mov     rcx, [rcx+10h]
0x1800120db  call    WPP_SF_
0x1800120e0  mov     edx, dword ptr [rsp+118h+Size]
0x1800120e4  mov     dword ptr [rsp+118h+arg_20], edx
0x1800120eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800120f2  mov     r14, [rsp+118h+arg_0]
0x1800120fa  test    byte ptr [rcx+1Ch], 8
0x1800120fe  jz      short loc_180012127
0x180012100  cmp     byte ptr [rcx+19h], 4
0x180012104  jb      short loc_180012127
0x180012106  mov     eax, dword ptr [rsp+118h+Size+4]
0x18001210a  mov     dword ptr [rsp+118h+var_E8], eax
0x18001210e  mov     dword ptr [rsp+118h+var_F0], edx
0x180012112  mov     [rsp+118h+var_F8], r14
0x180012117  mov     r9, [rdi+188h]
0x18001211e  mov     rcx, [rcx+10h]
0x180012122  call    WPP_SF_SSdd
0x180012127  lea     rcx, [rsp+118h+var_88]
0x18001212f  call    cs:__imp_RtlQueryPerformanceCounter
0x180012135  lea     rax, [rsp+118h+Size+4]
0x18001213a  mov     [rsp+118h+var_F8], rax
0x18001213f  lea     r9, [rsp+118h+Size]
0x180012144  lea     r8, [rsp+118h+var_AC+4]
0x180012149  mov     rdx, r14
0x18001214c  mov     rcx, rdi
0x18001214f  call    CallExtObj
0x180012154  mov     r14d, eax
0x180012157  mov     dword ptr [rsp+118h+var_AC], eax
0x18001215b  lea     rcx, [rsp+118h+var_90]
0x180012163  call    cs:__imp_RtlQueryPerformanceCounter
0x180012169  mov     rcx, cs:WPP_GLOBAL_Control
0x180012170  test    byte ptr [rcx+1Ch], 8
0x180012174  jz      short loc_18001219F
0x180012176  cmp     byte ptr [rcx+19h], 4
0x18001217a  jb      short loc_18001219F
0x18001217c  mov     eax, dword ptr [rsp+118h+Size+4]
0x180012180  mov     dword ptr [rsp+118h+var_F0], eax
0x180012184  mov     eax, dword ptr [rsp+118h+Size]
0x180012188  mov     dword ptr [rsp+118h+var_F8], eax
0x18001218c  mov     r9d, r14d
0x18001218f  mov     rcx, [rcx+10h]
0x180012193  call    WPP_SF_ddd
0x180012198  mov     rcx, cs:WPP_GLOBAL_Control
0x18001219f  mov     rax, [rsp+118h+var_A0]
0x1800121a4  test    rax, rax
0x1800121a7  jz      short loc_1800121DC
0x1800121a9  test    byte ptr [rcx+1Ch], 40h
0x1800121ad  jz      short loc_1800121CF
0x1800121af  cmp     byte ptr [rcx+19h], 4
0x1800121b3  jb      short loc_1800121CF
0x1800121b5  mov     edx, 18h
0x1800121ba  lea     r8, WPP_252b7c09ccd93e4a9f264741fd025fe9_Traceguids
0x1800121c1  mov     rcx, [rcx+10h]
0x1800121c5  call    WPP_SF_
0x1800121ca  mov     rax, [rsp+118h+var_A0]
0x1800121cf  mov     rcx, rax; Block
0x1800121d2  call    ?KillPerflibFunctionTimer@@YAKPEAX@Z; KillPerflibFunctionTimer(void *)
0x1800121d7  mov     [rsp+118h+var_A0], rsi
0x1800121dc  mov     eax, dword ptr [rsp+118h+Size]
0x1800121e0  mov     [rdi+1D4h], eax
0x1800121e6  cmp     eax, [rdi+1D8h]
0x1800121ec  jbe     short loc_1800121F4
0x1800121ee  mov     [rdi+1D8h], eax
0x1800121f4  cmp     r14d, 0EAh
0x1800121fb  jnz     short loc_180012212
0x1800121fd  mov     eax, dword ptr [rsp+118h+arg_20]
0x180012204  cmp     eax, [rdi+1DCh]
0x18001220a  jbe     short loc_180012212
0x18001220c  mov     [rdi+1DCh], eax
0x180012212  mov     rax, qword ptr [rsp+118h+var_AC+4]
0x180012217  mov     [rsp+118h+var_68], rax
0x18001221f  call    ?GetTimeAsLongLong@@YA_JXZ; GetTimeAsLongLong(void)
0x180012224  mov     [rdi+190h], rax
0x18001222b  mov     rcx, rdi
0x18001222e  call    PerfpUnlockExtObject
0x180012233  mov     [rsp+118h+var_B0], esi
0x180012237  mov     eax, dword ptr [rsp+118h+Size]
0x18001223b  cmp     eax, dword ptr [rsp+118h+arg_20]
0x180012242  jbe     loc_180012307
0x180012248  lea     r8, [rdi+1E8h]; struct ERROR_LOG *
0x18001224f  mov     rdx, [rdi+68h]; HKEY
0x180012253  mov     ecx, 3FCh; unsigned int
0x180012258  call    ?PerfpThrottleError@@YAKKPEAUHKEY__@@PEAUERROR_LOG@@@Z; PerfpThrottleError(ulong,HKEY__ *,ERROR_LOG *)
0x18001225d  test    eax, eax
0x18001225f  jz      short loc_180012294
0x180012261  test    cs:Microsoft_Windows_PerflibEnableBits, 2
0x180012268  jz      short loc_180012294
0x18001226a  mov     eax, dword ptr [rsp+118h+Size]
0x18001226e  mov     dword ptr [rsp+118h+var_F0], eax
0x180012272  mov     eax, dword ptr [rsp+118h+arg_20]
0x180012279  mov     dword ptr [rsp+118h+var_F8], eax
  ... truncated ...
```
