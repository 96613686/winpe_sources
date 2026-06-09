# RtlpHpHeapCreate

- ea: `0x180100fa8`
- end: `0x180101418`
- name: `RtlpHpHeapCreate`
- size: `1136`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006a124`
- `0x180100f60`

## callees

- `0x1800526f0`
- `0x18006b408`
- `0x180076610`
- `0x18007a17c`
- `0x1800babb4`
- `0x1800c4df4`
- `0x1800cb5c8`
- `0x1800e68cc`
- `0x1800e90e8`
- `0x1800ed3a4`
- `0x1800fad30`
- `0x180100fa8`
- `0x180105cc0`
- `0x180105e24`
- `0x18010c0e8`
- `0x18010c138`
- `0x18010f7f4`
- `0x180118bd0`
- `0x18011e730`
- `0x180156f94`

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
  ProcessorCount = dword_1801CA234;
  if ( !dword_1801CA234 )
  {
    ProcessorCount = RtlpHpEnvQueryProcessorCount();
    v9 = _InterlockedCompareExchange(&dword_1801CA234, ProcessorCount, 0);
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
    RtlpHpVsContextInitialize(v7 + 704, (unsigned int)&v34, ProcessorCount, v15, (__int64)&qword_1801CA1F8 + 4);
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
      (__int64)&qword_1801CA1F8 + 5,
      v7);
    *(_QWORD *)(v7 + 112) = 0;
    if ( (int)RtlpHpLfhContextStart(v7 + 960) >= 0
      && (int)RtlpHpVsContextStart(v7 + 704) >= 0
      && ((a1 & 0x400000) != 0 || (int)RtlpHpLfhContextEnable(v7 + 960, &qword_1801CA1F8) >= 0)
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
0x180100fa8  mov     [rsp-8+arg_0], rbx
0x180100fad  mov     [rsp-8+arg_10], r8
0x180100fb2  push    rbp
0x180100fb3  push    rsi
0x180100fb4  push    rdi
0x180100fb5  push    r12
0x180100fb7  push    r13
0x180100fb9  push    r14
0x180100fbb  push    r15
0x180100fbd  lea     rbp, [rsp-27h]
0x180100fc2  sub     rsp, 0B0h
0x180100fc9  mov     rax, 7FFFFFFFFFFFFFFFh
0x180100fd3  mov     dword ptr [rbp+57h+arg_8], 0
0x180100fda  mov     r13, r9
0x180100fdd  mov     r12, rdx
0x180100fe0  mov     r15d, ecx
0x180100fe3  cmp     rdx, rax
0x180100fe6  jbe     short loc_180100FEF
0x180100fe8  xor     esi, esi
0x180100fea  jmp     loc_1801013F9
0x180100fef  mov     ebx, 1
0x180100ff4  mov     rcx, r13
0x180100ff7  mov     edx, ebx
0x180100ff9  call    RtlpHpRegisterEnvironment
0x180100ffe  test    eax, eax
0x180101000  js      short loc_180100FE8
0x180101002  mov     r14d, cs:dword_1801CA234
0x180101009  test    r14d, r14d
0x18010100c  jnz     short loc_180101025
0x18010100e  call    RtlpHpEnvQueryProcessorCount
0x180101013  mov     r14d, eax
0x180101016  xor     eax, eax
0x180101018  lock cmpxchg cs:dword_1801CA234, r14d
0x180101021  cmovnz  r14d, eax
0x180101025  lea     rcx, [rbp+57h+arg_8]
0x180101029  call    RtlpQueryPhysicalMemoryPolicy
0x18010102e  test    eax, eax
0x180101030  js      short loc_18010103A
0x180101032  cmp     dword ptr [rbp+57h+arg_8], 0Ah
0x180101036  cmovle  r14d, ebx
0x18010103a  movups  xmm0, xmmword ptr [r13+0]
0x18010103f  bt      r15d, 19h
0x180101044  lea     r8, [rbp+57h+var_90]
0x180101048  mov     ecx, r15d
0x18010104b  cmovb   r14d, ebx
0x18010104f  mov     edx, r14d
0x180101052  movdqu  [rbp+57h+var_90], xmm0
0x180101057  call    RtlpHpHeapAllocate
0x18010105c  mov     rsi, rax
0x18010105f  test    rax, rax
0x180101062  jnz     short loc_180101073
0x180101064  xor     edx, edx
0x180101066  mov     rcx, r13
0x180101069  call    RtlpHpRegisterEnvironment
0x18010106e  jmp     loc_1801013F9
0x180101073  movups  xmm0, xmmword ptr [r13+0]
0x180101078  xor     ecx, ecx
0x18010107a  mov     dword ptr [rax+10h], 0DDEEDDEEh
0x180101081  mov     [rax+14h], r15d
0x180101085  lea     r9, [rbp+57h+var_90]
0x180101089  movdqu  xmmword ptr [rax], xmm0
0x18010108d  mov     qword ptr [rax+110h], 0
0x180101098  lea     r8, [rsi+320h]
0x18010109f  mov     al, [r13+1]
0x1801010a3  lea     edx, [rcx+10h]
0x1801010a6  sub     al, 2
0x1801010a8  mov     [rbp+57h+arg_8], rsi
0x1801010ac  cmp     al, 2
0x1801010ae  lea     rbx, [rsi+0A8h]
0x1801010b5  movdqu  [rbp+57h+var_90], xmm0
0x1801010ba  cmovbe  ecx, edx
0x1801010bd  lea     rdx, [rsi+80h]
0x1801010c4  mov     edi, ecx
0x1801010c6  or      edi, 4
0x1801010c9  bt      r15d, 1Ah
0x1801010ce  cmovnb  edi, ecx
0x1801010d1  lea     rcx, [rsi+2C0h]
0x1801010d8  mov     dword ptr [rsp+0E0h+var_98], edi
0x1801010dc  mov     [rsp+0E0h+var_A0], r9
0x1801010e1  lea     r9, [rsi+3C0h]
0x1801010e8  mov     [rsp+0E0h+var_A8], rbx
0x1801010ed  mov     [rsp+0E0h+var_B0], rdx
0x1801010f2  mov     edx, 100000h
0x1801010f7  mov     [rsp+0E0h+var_B8], r8
0x1801010fc  mov     r8, rsi
0x1801010ff  mov     [rsp+0E0h+var_C0], rcx
0x180101104  lea     rcx, [rsi+140h]
0x18010110b  call    RtlpHpSegContextInitialize
0x180101110  movups  xmm0, xmmword ptr [r13+0]
0x180101115  mov     dword ptr [rsp+0E0h+var_98], edi
0x180101119  lea     rdx, [rbp+57h+var_90]
0x18010111d  mov     [rsp+0E0h+var_A0], rdx
0x180101122  lea     rax, [rbx+10h]
0x180101126  mov     [rsp+0E0h+var_A8], rax
0x18010112b  lea     rdi, [rsi+80h]
0x180101132  mov     [rsp+0E0h+var_B0], rdi
0x180101137  lea     rbx, [rsi+140h]
0x18010113e  mov     [rsp+0E0h+var_B8], 0
0x180101147  lea     rcx, [rbx+0C0h]
0x18010114e  xor     r9d, r9d
0x180101151  mov     [rsp+0E0h+var_C0], 0
0x18010115a  mov     r8, rsi
0x18010115d  mov     edx, 1000000h
0x180101162  movdqu  [rbp+57h+var_90], xmm0
0x180101167  call    RtlpHpSegContextInitialize
0x18010116c  xor     r9d, r9d
0x18010116f  mov     [rsi+48h], r9
0x180101173  mov     [rsi+50h], r9
0x180101177  test    dword ptr [rsi+14h], 20000000h
0x18010117e  mov     [rsi+40h], r9
0x180101182  mov     [rsi+0E8h], r9
0x180101189  jz      short loc_1801011A2
0x18010118b  lea     rcx, RtlpStackTraceDatabaseLogPrefix
0x180101192  call    RtlpGetHeapInterceptorIndex
0x180101197  movzx   edx, ax
0x18010119a  mov     rcx, rsi
0x18010119d  call    RtlpHpHeapSetInterceptor
0x1801011a2  movzx   eax, byte ptr [r13+0]
0x1801011a7  lea     rdx, [rbp+57h+var_80]
0x1801011ab  and     eax, 1
0x1801011ae  mov     [rbp+57h+var_40], rdi
0x1801011b2  mov     [rbp+57h+var_78], eax
0x1801011b5  lea     rdi, [rsi+2C0h]
0x1801011bc  xorps   xmm0, xmm0
0x1801011bf  mov     [rbp+57h+var_80], rbx
0x1801011c3  movups  [rbp+57h+var_70], xmm0
0x1801011c7  lea     rax, RtlpHpSegVsAllocate
0x1801011ce  mov     r8d, r14d
0x1801011d1  mov     qword ptr [rbp+57h+var_70], rax
0x1801011d5  lea     rbx, RtlpHpSegLfhExtendContext
0x1801011dc  movups  [rbp+57h+var_60], xmm0
0x1801011e0  lea     rax, RtlpHpSegSuballocatorFree
0x1801011e7  mov     [rbp+57h+var_74], r9d
0x1801011eb  mov     qword ptr [rbp+57h+var_70+8], rax
0x1801011ef  mov     rcx, rdi
0x1801011f2  lea     rax, RtlpHpSegSuballocatorCommit
0x1801011f9  mov     qword ptr [rbp+57h+var_60], rax
0x1801011fd  lea     rax, RtlpHpSegSuballocatorDecommit
0x180101204  mov     qword ptr [rbp+57h+var_60+8], rax
0x180101208  lea     rax, qword_1801CA1F8+4
0x18010120f  movups  [rbp+57h+var_50], xmm0
0x180101213  mov     [rsp+0E0h+var_C0], rax
0x180101218  mov     qword ptr [rbp+57h+var_50], rbx
0x18010121c  call    RtlpHpVsContextInitialize
0x180101221  xorps   xmm0, xmm0
0x180101224  lea     rax, RtlpHpSegLfhAllocate
0x18010122b  movups  [rbp+57h+var_70], xmm0
0x18010122f  mov     qword ptr [rbp+57h+var_70], rax
0x180101233  lea     rdx, [rbp+57h+var_80]
0x180101237  movups  [rbp+57h+var_60], xmm0
0x18010123b  lea     rax, RtlpHpSegSuballocatorFree
0x180101242  mov     r8d, r14d
0x180101245  mov     qword ptr [rbp+57h+var_70+8], rax
0x180101249  lea     rax, RtlpHpSegSuballocatorCommit
0x180101250  mov     qword ptr [rbp+57h+var_60], rax
0x180101254  lea     rax, RtlpHpSegSuballocatorDecommit
0x18010125b  movups  [rbp+57h+var_50], xmm0
0x18010125f  mov     qword ptr [rbp+57h+var_50], rbx
0x180101263  lea     rbx, [rsi+3C0h]
0x18010126a  mov     qword ptr [rbp+57h+var_60+8], rax
0x18010126e  mov     rcx, rbx
0x180101271  lea     rax, RtlpHpSegTlsCleanup
0x180101278  mov     qword ptr [rbp+57h+var_50+8], rax
0x18010127c  call    RtlpHpLfhContextInitialize
0x180101281  mov     r9d, [rsi+150h]
0x180101288  lea     rax, RtlpHpSegPgAllocate
0x18010128f  xorps   xmm0, xmm0
0x180101292  mov     [rsp+0E0h+var_B0], rsi
0x180101297  movups  [rbp+57h+var_70], xmm0
0x18010129b  mov     qword ptr [rbp+57h+var_70], rax
0x18010129f  lea     rcx, qword_1801CA1F8+5
0x1801012a6  movups  [rbp+57h+var_60], xmm0
0x1801012aa  mov     [rsp+0E0h+var_B8], rcx
0x1801012af  lea     rax, RtlpHpSegSuballocatorFree
0x1801012b6  mov     qword ptr [rbp+57h+var_70+8], rax
0x1801012ba  lea     r8, [rbp+57h+var_90]
0x1801012be  lea     rax, RtlpHpSegSuballocatorCommit
0x1801012c5  mov     qword ptr [rbp+57h+var_60], rax
0x1801012c9  lea     rdx, [rbp+57h+var_80]
0x1801012cd  lea     rax, RtlpHpSegSuballocatorDecommit
0x1801012d4  movups  [rbp+57h+var_50], xmm0
0x1801012d8  mov     qword ptr [rbp+57h+var_60+8], rax
0x1801012dc  lea     rcx, [rsi+320h]
0x1801012e3  movups  xmm0, xmmword ptr [r13+0]
0x1801012e8  movzx   eax, byte ptr [r13+1]
0x1801012ed  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1801012f1  movdqu  [rbp+57h+var_90], xmm0
0x1801012f6  call    RtlpHpPgContextInitialize
0x1801012fb  mov     rcx, rbx
0x1801012fe  mov     qword ptr [rsi+70h], 0
0x180101306  call    RtlpHpLfhContextStart
0x18010130b  test    eax, eax
0x18010130d  js      short loc_18010134C
0x18010130f  mov     rcx, rdi
0x180101312  call    RtlpHpVsContextStart
0x180101317  test    eax, eax
0x180101319  js      short loc_18010134C
0x18010131b  bt      r15d, 16h
0x180101320  jb      short loc_180101335
0x180101322  lea     rdx, qword_1801CA1F8
0x180101329  mov     rcx, rbx
0x18010132c  call    RtlpHpLfhContextEnable
0x180101331  test    eax, eax
0x180101333  js      short loc_18010134C
0x180101335  mov     r8, [rbp+57h+arg_10]
0x180101339  lea     rcx, [rsi+140h]
0x180101340  mov     rdx, r12
0x180101343  call    RtlpHpSegContextReserve
0x180101348  test    eax, eax
0x18010134a  jns     short loc_18010135C
0x18010134c  mov     rcx, [rbp+57h+arg_8]
0x180101350  xor     esi, esi
0x180101352  call    RtlpHpHeapDestroy
0x180101357  jmp     loc_1801013F9
0x18010135c  call    RtlGetCurrentServiceSessionId
0x180101361  test    eax, eax
0x180101363  jz      short loc_18010137E
0x180101365  mov     rax, gs:60h
0x18010136e  mov     rcx, [rax+90h]
0x180101375  add     rcx, 22Eh
0x18010137c  jmp     short loc_180101383
0x18010137e  mov     ecx, 7FFE0388h
0x180101383  cmp     byte ptr [rcx], 0
0x180101386  jz      short loc_18010139D
0x180101388  mov     rdx, [rsi+100h]
0x18010138f  mov     r8d, r15d
0x180101392  sub     rdx, rsi
0x180101395  mov     rcx, rsi
0x180101398  call    RtlpHeapLogRangeCreate
0x18010139d  mov     rcx, rsi
0x1801013a0  call    RtlpHpHeapLoggingStateSync
0x1801013a5  test    byte ptr [rsi+14h], 80h
0x1801013a9  jz      short loc_1801013F9
0x1801013ab  call    RtlGetCurrentServiceSessionId
0x1801013b0  test    eax, eax
0x1801013b2  jz      short loc_1801013CD
0x1801013b4  mov     rax, gs:60h
0x1801013bd  mov     rcx, [rax+90h]
0x1801013c4  add     rcx, 226h
0x1801013cb  jmp     short loc_1801013D2
0x1801013cd  mov     ecx, 7FFE0380h
0x1801013d2  movzx   ecx, byte ptr [rcx]
0x1801013d5  mov     edx, r15d
0x1801013d8  mov     r9, [rsi+0F8h]
0x1801013df  mov     r8, [rsi+100h]
0x1801013e6  sub     r9, rsi
0x1801013e9  mov     [rsp+0E0h+var_C0], rcx
0x1801013ee  sub     r8, rsi
0x1801013f1  mov     rcx, rsi
0x1801013f4  call    RtlpLogHeapCreateEvent
0x1801013f9  mov     rbx, [rsp+0E0h+arg_0]
0x180101401  mov     rax, rsi
0x180101404  add     rsp, 0B0h
0x18010140b  pop     r15
0x18010140d  pop     r14
0x18010140f  pop     r13
0x180101411  pop     r12
0x180101413  pop     rdi
0x180101414  pop     rsi
0x180101415  pop     rbp
0x180101416  retn
```
