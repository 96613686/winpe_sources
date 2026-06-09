# RtlpHpHeapCreate

- ea: `0x180101588`
- end: `0x1801019f8`
- name: `RtlpHpHeapCreate`
- size: `1136`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180086bd4`
- `0x180101540`

## callees

- `0x180055db8`
- `0x180059b1c`
- `0x18006f0d0`
- `0x180087eb8`
- `0x1800bee60`
- `0x1800cd158`
- `0x1800e6c4c`
- `0x1800e9748`
- `0x1800ede84`
- `0x1800faf18`
- `0x1800fba70`
- `0x180101588`
- `0x180106af0`
- `0x180106c54`
- `0x18010d3e4`
- `0x18010d468`
- `0x180110b54`
- `0x1801196c0`
- `0x18011f220`
- `0x1801578f4`

## pseudocode

```c
__int64 __fastcall RtlpHpHeapCreate(unsigned int a1, unsigned __int64 a2, __int64 a3, __int128 *a4)
{
  __int64 v7; // rsi
  unsigned __int32 ProcessorCount; // r14d
  signed __int32 v9; // eax
  __int64 v10; // rax
  __int128 v11; // xmm0
  int v12; // ecx
  unsigned __int8 v13; // al
  int v14; // edi
  int v15; // r9d
  bool v16; // zf
  unsigned __int16 HeapInterceptorIndex; // ax
  int v18; // eax
  int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r9
  __int64 v29; // rcx
  int v31; // [rsp+20h] [rbp-69h]
  __int64 v32; // [rsp+48h] [rbp-41h]
  __int128 v33; // [rsp+50h] [rbp-39h] BYREF
  __int64 v34; // [rsp+60h] [rbp-29h] BYREF
  int v35; // [rsp+68h] [rbp-21h]
  int v36; // [rsp+6Ch] [rbp-1Dh]
  __int64 (__fastcall *v37)(); // [rsp+70h] [rbp-19h]
  __int64 (__fastcall *v38)(); // [rsp+78h] [rbp-11h]
  __int64 (__fastcall *v39)(); // [rsp+80h] [rbp-9h]
  __int64 (__fastcall *v40)(); // [rsp+88h] [rbp-1h]
  __int128 v41; // [rsp+90h] [rbp+7h]
  __int64 v42; // [rsp+A0h] [rbp+17h]
  __int64 v43; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v44; // [rsp+100h] [rbp+77h]

  v44 = a3;
  LODWORD(v43) = 0;
  if ( a2 > 0x7FFFFFFFFFFFFFFFLL || (int)RtlpHpRegisterEnvironment(a4, 1) < 0 )
    return 0;
  ProcessorCount = dword_1801CA220;
  if ( !dword_1801CA220 )
  {
    ProcessorCount = RtlpHpEnvQueryProcessorCount();
    v9 = _InterlockedCompareExchange(&dword_1801CA220, ProcessorCount, 0);
    if ( v9 )
      ProcessorCount = v9;
  }
  if ( (int)RtlpQueryPhysicalMemoryPolicy(&v43) >= 0 && (int)v43 <= 10 )
    ProcessorCount = 1;
  if ( (a1 & 0x2000000) != 0 )
    ProcessorCount = 1;
  v33 = *a4;
  v10 = RtlpHpHeapAllocate(a1, ProcessorCount, &v33);
  v7 = v10;
  if ( v10 )
  {
    v11 = *a4;
    v12 = 0;
    *(_DWORD *)(v10 + 16) = -571548178;
    *(_DWORD *)(v10 + 20) = a1;
    *(_OWORD *)v10 = v11;
    *(_QWORD *)(v10 + 272) = 0;
    v13 = *((_BYTE *)a4 + 1) - 2;
    v43 = v7;
    v33 = v11;
    if ( v13 <= 2u )
      v12 = 16;
    v14 = v12 | 4;
    if ( (a1 & 0x4000000) == 0 )
      v14 = v12;
    RtlpHpSegContextInitialize(
      v7 + 320,
      0x100000,
      v7,
      v7 + 960,
      v7 + 704,
      v7 + 800,
      v7 + 128,
      v7 + 168,
      (__int64)&v33,
      v14);
    LODWORD(v32) = v14;
    v33 = *a4;
    RtlpHpSegContextInitialize(v7 + 512, 0x1000000, v7, 0, 0, 0, v7 + 128, v7 + 184, (__int64)&v33, v32);
    v15 = 0;
    *(_QWORD *)(v7 + 72) = 0;
    *(_QWORD *)(v7 + 80) = 0;
    v16 = (*(_DWORD *)(v7 + 20) & 0x20000000) == 0;
    *(_QWORD *)(v7 + 64) = 0;
    *(_QWORD *)(v7 + 232) = 0;
    if ( !v16 )
    {
      HeapInterceptorIndex = RtlpGetHeapInterceptorIndex(RtlpStackTraceDatabaseLogPrefix);
      RtlpHpHeapSetInterceptor(v7, HeapInterceptorIndex);
    }
    v18 = *(_BYTE *)a4 & 1;
    v42 = v7 + 128;
    v35 = v18;
    v34 = v7 + 320;
    v37 = RtlpHpSegVsAllocate;
    v36 = v15;
    v38 = RtlpHpSegSuballocatorFree;
    v39 = RtlpHpSegSuballocatorCommit;
    v40 = RtlpHpSegSuballocatorDecommit;
    *((_QWORD *)&v41 + 1) = 0;
    *(_QWORD *)&v41 = RtlpHpSegLfhExtendContext;
    RtlpHpVsContextInitialize(v7 + 704, (unsigned int)&v34, ProcessorCount, v15, (__int64)&qword_1801CA1E8 + 4);
    v37 = RtlpHpSegLfhAllocate;
    v38 = RtlpHpSegSuballocatorFree;
    v39 = RtlpHpSegSuballocatorCommit;
    *(_QWORD *)&v41 = RtlpHpSegLfhExtendContext;
    v40 = RtlpHpSegSuballocatorDecommit;
    *((_QWORD *)&v41 + 1) = RtlpHpSegTlsCleanup;
    RtlpHpLfhContextInitialize(v7 + 960, &v34, ProcessorCount);
    v19 = *(_DWORD *)(v7 + 336);
    v37 = RtlpHpSegPgAllocate;
    v38 = RtlpHpSegSuballocatorFree;
    v39 = RtlpHpSegSuballocatorCommit;
    v41 = 0;
    v40 = RtlpHpSegSuballocatorDecommit;
    v31 = *((unsigned __int8 *)a4 + 1);
    v33 = *a4;
    RtlpHpPgContextInitialize(
      v7 + 800,
      (unsigned int)&v34,
      (unsigned int)&v33,
      v19,
      v31,
      (__int64)&qword_1801CA1E8 + 5,
      v7);
    *(_QWORD *)(v7 + 112) = 0;
    if ( (int)RtlpHpLfhContextStart(v7 + 960) >= 0
      && (int)RtlpHpVsContextStart(v7 + 704) >= 0
      && ((a1 & 0x400000) != 0 || (int)RtlpHpLfhContextEnable(v7 + 960, &qword_1801CA1E8) >= 0)
      && (int)RtlpHpSegContextReserve(v7 + 320, a2, v44) >= 0 )
    {
      if ( (unsigned int)RtlGetCurrentServiceSessionId(v21, v20, v22, v23) )
        v24 = (__int64)NtCurrentPeb()->SharedData + 558;
      else
        v24 = 2147353480;
      if ( *(_BYTE *)v24 )
        RtlpHeapLogRangeCreate(v7, *(_QWORD *)(v7 + 256) - v7, a1);
      RtlpHpHeapLoggingStateSync(v7);
      if ( *(char *)(v7 + 20) < 0 )
      {
        if ( (unsigned int)RtlGetCurrentServiceSessionId(v26, v25, v27, v28) )
          v29 = (__int64)NtCurrentPeb()->SharedData + 550;
        else
          v29 = 2147353472;
        RtlpLogHeapCreateEvent(v7, a1, *(_QWORD *)(v7 + 256) - v7, *(_DWORD *)(v7 + 248) - v7, *(unsigned __int8 *)v29);
      }
    }
    else
    {
      v7 = 0;
      RtlpHpHeapDestroy(v43);
    }
  }
  else
  {
    RtlpHpRegisterEnvironment(a4, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x180101588  mov     [rsp-8+arg_0], rbx
0x18010158d  mov     [rsp-8+arg_10], r8
0x180101592  push    rbp
0x180101593  push    rsi
0x180101594  push    rdi
0x180101595  push    r12
0x180101597  push    r13
0x180101599  push    r14
0x18010159b  push    r15
0x18010159d  lea     rbp, [rsp-27h]
0x1801015a2  sub     rsp, 0B0h
0x1801015a9  mov     rax, 7FFFFFFFFFFFFFFFh
0x1801015b3  mov     dword ptr [rbp+57h+arg_8], 0
0x1801015ba  mov     r13, r9
0x1801015bd  mov     r12, rdx
0x1801015c0  mov     r15d, ecx
0x1801015c3  cmp     rdx, rax
0x1801015c6  jbe     short loc_1801015CF
0x1801015c8  xor     esi, esi
0x1801015ca  jmp     loc_1801019D9
0x1801015cf  mov     ebx, 1
0x1801015d4  mov     rcx, r13
0x1801015d7  mov     edx, ebx
0x1801015d9  call    RtlpHpRegisterEnvironment
0x1801015de  test    eax, eax
0x1801015e0  js      short loc_1801015C8
0x1801015e2  mov     r14d, cs:dword_1801CA220
0x1801015e9  test    r14d, r14d
0x1801015ec  jnz     short loc_180101605
0x1801015ee  call    RtlpHpEnvQueryProcessorCount
0x1801015f3  mov     r14d, eax
0x1801015f6  xor     eax, eax
0x1801015f8  lock cmpxchg cs:dword_1801CA220, r14d
0x180101601  cmovnz  r14d, eax
0x180101605  lea     rcx, [rbp+57h+arg_8]
0x180101609  call    RtlpQueryPhysicalMemoryPolicy
0x18010160e  test    eax, eax
0x180101610  js      short loc_18010161A
0x180101612  cmp     dword ptr [rbp+57h+arg_8], 0Ah
0x180101616  cmovle  r14d, ebx
0x18010161a  movups  xmm0, xmmword ptr [r13+0]
0x18010161f  bt      r15d, 19h
0x180101624  lea     r8, [rbp+57h+var_90]
0x180101628  mov     ecx, r15d
0x18010162b  cmovb   r14d, ebx
0x18010162f  mov     edx, r14d
0x180101632  movdqu  [rbp+57h+var_90], xmm0
0x180101637  call    RtlpHpHeapAllocate
0x18010163c  mov     rsi, rax
0x18010163f  test    rax, rax
0x180101642  jnz     short loc_180101653
0x180101644  xor     edx, edx
0x180101646  mov     rcx, r13
0x180101649  call    RtlpHpRegisterEnvironment
0x18010164e  jmp     loc_1801019D9
0x180101653  movups  xmm0, xmmword ptr [r13+0]
0x180101658  xor     ecx, ecx
0x18010165a  mov     dword ptr [rax+10h], 0DDEEDDEEh
0x180101661  mov     [rax+14h], r15d
0x180101665  lea     r9, [rbp+57h+var_90]
0x180101669  movdqu  xmmword ptr [rax], xmm0
0x18010166d  mov     qword ptr [rax+110h], 0
0x180101678  lea     r8, [rsi+320h]
0x18010167f  mov     al, [r13+1]
0x180101683  lea     edx, [rcx+10h]
0x180101686  sub     al, 2
0x180101688  mov     [rbp+57h+arg_8], rsi
0x18010168c  cmp     al, 2
0x18010168e  lea     rbx, [rsi+0A8h]
0x180101695  movdqu  [rbp+57h+var_90], xmm0
0x18010169a  cmovbe  ecx, edx
0x18010169d  lea     rdx, [rsi+80h]
0x1801016a4  mov     edi, ecx
0x1801016a6  or      edi, 4
0x1801016a9  bt      r15d, 1Ah
0x1801016ae  cmovnb  edi, ecx
0x1801016b1  lea     rcx, [rsi+2C0h]
0x1801016b8  mov     dword ptr [rsp+0E0h+var_98], edi
0x1801016bc  mov     [rsp+0E0h+var_A0], r9
0x1801016c1  lea     r9, [rsi+3C0h]
0x1801016c8  mov     [rsp+0E0h+var_A8], rbx
0x1801016cd  mov     [rsp+0E0h+var_B0], rdx
0x1801016d2  mov     edx, 100000h
0x1801016d7  mov     [rsp+0E0h+var_B8], r8
0x1801016dc  mov     r8, rsi
0x1801016df  mov     [rsp+0E0h+var_C0], rcx
0x1801016e4  lea     rcx, [rsi+140h]
0x1801016eb  call    RtlpHpSegContextInitialize
0x1801016f0  movups  xmm0, xmmword ptr [r13+0]
0x1801016f5  mov     dword ptr [rsp+0E0h+var_98], edi
0x1801016f9  lea     rdx, [rbp+57h+var_90]
0x1801016fd  mov     [rsp+0E0h+var_A0], rdx
0x180101702  lea     rax, [rbx+10h]
0x180101706  mov     [rsp+0E0h+var_A8], rax
0x18010170b  lea     rdi, [rsi+80h]
0x180101712  mov     [rsp+0E0h+var_B0], rdi
0x180101717  lea     rbx, [rsi+140h]
0x18010171e  mov     [rsp+0E0h+var_B8], 0
0x180101727  lea     rcx, [rbx+0C0h]
0x18010172e  xor     r9d, r9d
0x180101731  mov     [rsp+0E0h+var_C0], 0
0x18010173a  mov     r8, rsi
0x18010173d  mov     edx, 1000000h
0x180101742  movdqu  [rbp+57h+var_90], xmm0
0x180101747  call    RtlpHpSegContextInitialize
0x18010174c  xor     r9d, r9d
0x18010174f  mov     [rsi+48h], r9
0x180101753  mov     [rsi+50h], r9
0x180101757  test    dword ptr [rsi+14h], 20000000h
0x18010175e  mov     [rsi+40h], r9
0x180101762  mov     [rsi+0E8h], r9
0x180101769  jz      short loc_180101782
0x18010176b  lea     rcx, RtlpStackTraceDatabaseLogPrefix
0x180101772  call    RtlpGetHeapInterceptorIndex
0x180101777  movzx   edx, ax
0x18010177a  mov     rcx, rsi
0x18010177d  call    RtlpHpHeapSetInterceptor
0x180101782  movzx   eax, byte ptr [r13+0]
0x180101787  lea     rdx, [rbp+57h+var_80]
0x18010178b  and     eax, 1
0x18010178e  mov     [rbp+57h+var_40], rdi
0x180101792  mov     [rbp+57h+var_78], eax
0x180101795  lea     rdi, [rsi+2C0h]
0x18010179c  xorps   xmm0, xmm0
0x18010179f  mov     [rbp+57h+var_80], rbx
0x1801017a3  movups  [rbp+57h+var_70], xmm0
0x1801017a7  lea     rax, RtlpHpSegVsAllocate
0x1801017ae  mov     r8d, r14d
0x1801017b1  mov     qword ptr [rbp+57h+var_70], rax
0x1801017b5  lea     rbx, RtlpHpSegLfhExtendContext
0x1801017bc  movups  [rbp+57h+var_60], xmm0
0x1801017c0  lea     rax, RtlpHpSegSuballocatorFree
0x1801017c7  mov     [rbp+57h+var_74], r9d
0x1801017cb  mov     qword ptr [rbp+57h+var_70+8], rax
0x1801017cf  mov     rcx, rdi
0x1801017d2  lea     rax, RtlpHpSegSuballocatorCommit
0x1801017d9  mov     qword ptr [rbp+57h+var_60], rax
0x1801017dd  lea     rax, RtlpHpSegSuballocatorDecommit
0x1801017e4  mov     qword ptr [rbp+57h+var_60+8], rax
0x1801017e8  lea     rax, qword_1801CA1E8+4
0x1801017ef  movups  [rbp+57h+var_50], xmm0
0x1801017f3  mov     [rsp+0E0h+var_C0], rax
0x1801017f8  mov     qword ptr [rbp+57h+var_50], rbx
0x1801017fc  call    RtlpHpVsContextInitialize
0x180101801  xorps   xmm0, xmm0
0x180101804  lea     rax, RtlpHpSegLfhAllocate
0x18010180b  movups  [rbp+57h+var_70], xmm0
0x18010180f  mov     qword ptr [rbp+57h+var_70], rax
0x180101813  lea     rdx, [rbp+57h+var_80]
0x180101817  movups  [rbp+57h+var_60], xmm0
0x18010181b  lea     rax, RtlpHpSegSuballocatorFree
0x180101822  mov     r8d, r14d
0x180101825  mov     qword ptr [rbp+57h+var_70+8], rax
0x180101829  lea     rax, RtlpHpSegSuballocatorCommit
0x180101830  mov     qword ptr [rbp+57h+var_60], rax
0x180101834  lea     rax, RtlpHpSegSuballocatorDecommit
0x18010183b  movups  [rbp+57h+var_50], xmm0
0x18010183f  mov     qword ptr [rbp+57h+var_50], rbx
0x180101843  lea     rbx, [rsi+3C0h]
0x18010184a  mov     qword ptr [rbp+57h+var_60+8], rax
0x18010184e  mov     rcx, rbx
0x180101851  lea     rax, RtlpHpSegTlsCleanup
0x180101858  mov     qword ptr [rbp+57h+var_50+8], rax
0x18010185c  call    RtlpHpLfhContextInitialize
0x180101861  mov     r9d, [rsi+150h]
0x180101868  lea     rax, RtlpHpSegPgAllocate
0x18010186f  xorps   xmm0, xmm0
0x180101872  mov     [rsp+0E0h+var_B0], rsi
0x180101877  movups  [rbp+57h+var_70], xmm0
0x18010187b  mov     qword ptr [rbp+57h+var_70], rax
0x18010187f  lea     rcx, qword_1801CA1E8+5
0x180101886  movups  [rbp+57h+var_60], xmm0
0x18010188a  mov     [rsp+0E0h+var_B8], rcx
0x18010188f  lea     rax, RtlpHpSegSuballocatorFree
0x180101896  mov     qword ptr [rbp+57h+var_70+8], rax
0x18010189a  lea     r8, [rbp+57h+var_90]
0x18010189e  lea     rax, RtlpHpSegSuballocatorCommit
0x1801018a5  mov     qword ptr [rbp+57h+var_60], rax
0x1801018a9  lea     rdx, [rbp+57h+var_80]
0x1801018ad  lea     rax, RtlpHpSegSuballocatorDecommit
0x1801018b4  movups  [rbp+57h+var_50], xmm0
0x1801018b8  mov     qword ptr [rbp+57h+var_60+8], rax
0x1801018bc  lea     rcx, [rsi+320h]
0x1801018c3  movups  xmm0, xmmword ptr [r13+0]
0x1801018c8  movzx   eax, byte ptr [r13+1]
0x1801018cd  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1801018d1  movdqu  [rbp+57h+var_90], xmm0
0x1801018d6  call    RtlpHpPgContextInitialize
0x1801018db  mov     rcx, rbx
0x1801018de  mov     qword ptr [rsi+70h], 0
0x1801018e6  call    RtlpHpLfhContextStart
0x1801018eb  test    eax, eax
0x1801018ed  js      short loc_18010192C
0x1801018ef  mov     rcx, rdi
0x1801018f2  call    RtlpHpVsContextStart
0x1801018f7  test    eax, eax
0x1801018f9  js      short loc_18010192C
0x1801018fb  bt      r15d, 16h
0x180101900  jb      short loc_180101915
0x180101902  lea     rdx, qword_1801CA1E8
0x180101909  mov     rcx, rbx
0x18010190c  call    RtlpHpLfhContextEnable
0x180101911  test    eax, eax
0x180101913  js      short loc_18010192C
0x180101915  mov     r8, [rbp+57h+arg_10]
0x180101919  lea     rcx, [rsi+140h]
0x180101920  mov     rdx, r12
0x180101923  call    RtlpHpSegContextReserve
0x180101928  test    eax, eax
0x18010192a  jns     short loc_18010193C
0x18010192c  mov     rcx, [rbp+57h+arg_8]
0x180101930  xor     esi, esi
0x180101932  call    RtlpHpHeapDestroy
0x180101937  jmp     loc_1801019D9
0x18010193c  call    RtlGetCurrentServiceSessionId
0x180101941  test    eax, eax
0x180101943  jz      short loc_18010195E
0x180101945  mov     rax, gs:60h
0x18010194e  mov     rcx, [rax+90h]
0x180101955  add     rcx, 22Eh
0x18010195c  jmp     short loc_180101963
0x18010195e  mov     ecx, 7FFE0388h
0x180101963  cmp     byte ptr [rcx], 0
0x180101966  jz      short loc_18010197D
0x180101968  mov     rdx, [rsi+100h]
0x18010196f  mov     r8d, r15d
0x180101972  sub     rdx, rsi
0x180101975  mov     rcx, rsi
0x180101978  call    RtlpHeapLogRangeCreate
0x18010197d  mov     rcx, rsi
0x180101980  call    RtlpHpHeapLoggingStateSync
0x180101985  test    byte ptr [rsi+14h], 80h
0x180101989  jz      short loc_1801019D9
0x18010198b  call    RtlGetCurrentServiceSessionId
0x180101990  test    eax, eax
0x180101992  jz      short loc_1801019AD
0x180101994  mov     rax, gs:60h
0x18010199d  mov     rcx, [rax+90h]
0x1801019a4  add     rcx, 226h
0x1801019ab  jmp     short loc_1801019B2
0x1801019ad  mov     ecx, 7FFE0380h
0x1801019b2  movzx   ecx, byte ptr [rcx]
0x1801019b5  mov     edx, r15d
0x1801019b8  mov     r9, [rsi+0F8h]
0x1801019bf  mov     r8, [rsi+100h]
0x1801019c6  sub     r9, rsi
0x1801019c9  mov     [rsp+0E0h+var_C0], rcx
0x1801019ce  sub     r8, rsi
0x1801019d1  mov     rcx, rsi
0x1801019d4  call    RtlpLogHeapCreateEvent
0x1801019d9  mov     rbx, [rsp+0E0h+arg_0]
0x1801019e1  mov     rax, rsi
0x1801019e4  add     rsp, 0B0h
0x1801019eb  pop     r15
0x1801019ed  pop     r14
0x1801019ef  pop     r13
0x1801019f1  pop     r12
0x1801019f3  pop     rdi
0x1801019f4  pop     rsi
0x1801019f5  pop     rbp
0x1801019f6  retn
```
