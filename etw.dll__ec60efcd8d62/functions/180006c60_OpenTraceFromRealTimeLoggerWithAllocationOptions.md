# OpenTraceFromRealTimeLoggerWithAllocationOptions

- ea: `0x180006c60`
- end: `0x180007051`
- name: `OpenTraceFromRealTimeLoggerWithAllocationOptions`
- size: `1009`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180006c40`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001eb2`
- `0x180002ec4`
- `0x180003d94`
- `0x180003fa8`
- `0x1800049dc`
- `0x180004ea8`
- `0x180006c60`
- `0x18000ef18`
- `0x18000f098`
- `0x18000fdf8`
- `0x18000fe48`
- `0x1800157b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006fec`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006d0f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180006d0f`

## pseudocode

```c
unsigned __int64 __fastcall OpenTraceFromRealTimeLoggerWithAllocationOptions(
        const WCHAR *a1,
        const struct ETW_OPEN_TRACE_OPTIONS *a2,
        unsigned __int64 a3,
        __int64 a4,
        _OWORD *a5)
{
  _OWORD *v5; // rdi
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  DWORD v13; // ecx
  struct _TRACELOG_CONTEXT *v14; // rbx
  unsigned int MaximumProcessors; // eax
  unsigned int v16; // r14d
  struct _TRACELOG_CONTEXT *TraceHandle; // rax
  int v18; // eax
  __int64 v19; // rdx
  _OWORD *v20; // rax
  __int128 v21; // xmm1
  unsigned __int64 v22; // rbx
  ULONG HeaderEventForRealtime; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v31; // [rsp+70h] [rbp-90h]
  int v32; // [rsp+78h] [rbp-88h] BYREF
  char v33; // [rsp+7Ch] [rbp-84h]
  GUID ActivityId; // [rsp+80h] [rbp-80h] BYREF
  _EVENT_TRACE_PROPERTIES Properties; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v36[32]; // [rsp+1120h] [rbp+1020h] BYREF
  __int64 *v37; // [rsp+1140h] [rbp+1040h]
  int v38; // [rsp+1148h] [rbp+1048h]
  int v39; // [rsp+114Ch] [rbp+104Ch]
  int *v40; // [rsp+1150h] [rbp+1050h]
  __int64 v41; // [rsp+1158h] [rbp+1058h]
  __int64 *v42; // [rsp+1160h] [rbp+1060h]
  __int64 v43; // [rsp+1168h] [rbp+1068h]

  v5 = a5;
  HeaderEventForRealtime = 0;
  v27 = 0;
  v26 = 0;
  v25 = -1;
  memset_0(&Properties, 0, 0x1078u);
  v32 = 0;
  v33 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v32 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
  {
    v29 = a4;
    v28 = a3;
    v43 = 8;
    v42 = &v29;
    v40 = &v28;
    v41 = 4;
    if ( a1 )
    {
      v10 = (__int64 *)a1;
      v11 = -1;
      do
        ++v11;
      while ( a1[v11] );
      v12 = 2 * v11 + 2;
    }
    else
    {
      v10 = &qword_180017B18;
      v12 = 2;
    }
    v38 = v12;
    v37 = v10;
    v39 = 0;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)byte_180018985,
      (__int64)&ActivityId,
      0,
      5,
      (__int64)v36);
  }
  v31 = 1;
  v30[0] = &v32;
  v30[1] = &HeaderEventForRealtime;
  v30[2] = &v25;
  if ( !a1 )
  {
    v13 = 123;
LABEL_17:
    HeaderEventForRealtime = v13;
LABEL_32:
    if ( v25 != -1 )
    {
      EtwpFreeTraceHandle(v25);
      v13 = HeaderEventForRealtime;
    }
    v25 = -1;
    goto LABEL_39;
  }
  if ( !a2 )
  {
    v13 = 87;
    goto LABEL_17;
  }
  v14 = 0;
  HeaderEventForRealtime = EtwpQueryRealTimeTraceProperties(a1, &Properties, &v26, &v27);
  v13 = HeaderEventForRealtime;
  if ( !HeaderEventForRealtime )
  {
    MaximumProcessors = EtwpQueryMaximumProcessors();
    v16 = v26;
    if ( v26 > MaximumProcessors )
      MaximumProcessors = v26;
    TraceHandle = EtwpAllocateTraceHandle(MaximumProcessors);
    v14 = TraceHandle;
    if ( !TraceHandle )
    {
      v13 = 14;
      HeaderEventForRealtime = 14;
      goto LABEL_32;
    }
    v25 = *((_QWORD *)TraceHandle + 2);
    HeaderEventForRealtime = EtwpCopyLogfileInfoFromOptions(TraceHandle, a2, 0, a1);
    v13 = HeaderEventForRealtime;
    if ( !HeaderEventForRealtime )
    {
      *((_DWORD *)v14 + 27) |= 0x100u;
      HeaderEventForRealtime = EtwpGenerateLogHeaderForRealtime(
                                 &Properties,
                                 v16,
                                 (struct _TRACE_LOGFILE_HEADER *)((char *)v14 + 200));
      v13 = HeaderEventForRealtime;
      if ( !HeaderEventForRealtime )
      {
        HeaderEventForRealtime = EtwpGenerateHeaderEventForRealtime(
                                   v27,
                                   (struct _TRACE_LOGFILE_HEADER *)((char *)v14 + 200),
                                   (struct _SYSTEM_TRACE_HEADER **)v14 + 80,
                                   (unsigned int *)v14 + 158);
        v13 = HeaderEventForRealtime;
        if ( !HeaderEventForRealtime )
        {
          v18 = -1;
          *((_BYTE *)v14 + 552) = 1;
          if ( a3 < 0xFFFFFFFF )
            v18 = a3;
          *((_DWORD *)v14 + 233) = v18;
          *((_QWORD *)v14 + 115) = a4;
          v13 = HeaderEventForRealtime;
        }
      }
    }
  }
  if ( v13 )
    goto LABEL_32;
  if ( a5 )
  {
    v19 = 2;
    v20 = (_OWORD *)((char *)v14 + 200);
    do
    {
      *v5 = *v20;
      v5[1] = v20[1];
      v5[2] = v20[2];
      v5[3] = v20[3];
      v5[4] = v20[4];
      v5[5] = v20[5];
      v5[6] = v20[6];
      v21 = v20[7];
      v20 += 8;
      v5[7] = v21;
      v5 += 8;
      --v19;
    }
    while ( v19 );
    *v5 = *v20;
    *((_QWORD *)v5 + 2) = *((_QWORD *)v20 + 2);
  }
LABEL_39:
  SetLastError(v13);
  v22 = v25;
  lambda_9df24178b30265c7642c034c363ca207_::operator()(v30);
  if ( v32 == 1 )
  {
    v32 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v22;
}

```

## disassembly

```asm
0x180006c60  mov     [rsp-8+arg_10], rbx
0x180006c65  push    rbp
0x180006c66  push    rsi
0x180006c67  push    rdi
0x180006c68  push    r12
0x180006c6a  push    r13
0x180006c6c  push    r14
0x180006c6e  push    r15
0x180006c70  lea     rbp, [rsp-1080h]
0x180006c78  mov     eax, 1180h
0x180006c7d  call    _alloca_probe
0x180006c82  sub     rsp, rax
0x180006c85  mov     rax, cs:__security_cookie
0x180006c8c  xor     rax, rsp
0x180006c8f  mov     [rbp+10B0h+var_40], rax
0x180006c96  mov     rdi, [rbp+10B0h+arg_20]
0x180006c9d  xor     r14d, r14d
0x180006ca0  mov     r15, r8
0x180006ca3  mov     [rsp+11B0h+var_1180], r14d
0x180006ca8  mov     r12, rdx
0x180006cab  mov     [rsp+11B0h+var_116C], r14d
0x180006cb0  mov     rsi, rcx
0x180006cb3  mov     [rsp+11B0h+var_1170], r14d
0x180006cb8  xor     edx, edx; Val
0x180006cba  mov     [rsp+11B0h+var_1178], 0FFFFFFFFFFFFFFFFh
0x180006cc3  mov     r8d, 1078h; Size
0x180006cc9  lea     rcx, [rbp+10B0h+Properties]; void *
0x180006ccd  mov     r13, r9
0x180006cd0  call    memset_0
0x180006cd5  mov     eax, cs:dword_18001D020
0x180006cdb  mov     [rsp+11B0h+var_1138], r14d
0x180006ce0  mov     [rsp+11B0h+var_1134], r14b
0x180006ce5  cmp     eax, 5
0x180006ce8  jbe     short loc_180006D17
0x180006cea  mov     rcx, cs:qword_18001D038
0x180006cf1  mov     rax, cs:qword_18001D030
0x180006cf8  test    al, 10h
0x180006cfa  jz      short loc_180006D17
0x180006cfc  mov     rax, rcx
0x180006cff  and     eax, 10h
0x180006d02  cmp     rax, rcx
0x180006d05  jnz     short loc_180006D17
0x180006d07  lea     rdx, [rbp+10B0h+ActivityId]; ActivityId
0x180006d0b  lea     ecx, [r14+3]; ControlCode
0x180006d0f  call    cs:__imp_EventActivityIdControl
0x180006d15  jmp     short loc_180006D1E
0x180006d17  xorps   xmm0, xmm0
0x180006d1a  movups  xmmword ptr [rbp+10B0h+ActivityId.Data1], xmm0
0x180006d1e  mov     eax, cs:dword_18001D020
0x180006d24  mov     ebx, 1
0x180006d29  mov     [rsp+11B0h+var_1138], ebx
0x180006d2d  cmp     eax, 5
0x180006d30  jbe     loc_180006E25
0x180006d36  mov     rcx, cs:qword_18001D038
0x180006d3d  mov     rax, cs:qword_18001D030
0x180006d44  test    al, 10h
0x180006d46  jz      loc_180006E25
0x180006d4c  mov     rax, rcx
0x180006d4f  and     eax, 10h
0x180006d52  cmp     rax, rcx
0x180006d55  jnz     loc_180006E25
0x180006d5b  mov     [rsp+11B0h+var_1160], r13
0x180006d60  mov     [rsp+11B0h+var_1168], r15d
0x180006d65  cmp     [rsp+11B0h+var_1134], r14b
0x180006d6a  jz      short loc_180006D8A
0x180006d6c  cmp     [rbp+10B0h+var_1120], r14d
0x180006d70  jnz     short loc_180006D84
0x180006d72  cmp     [rbp+10B0h+var_111C], r14d
0x180006d76  jnz     short loc_180006D84
0x180006d78  cmp     [rbp+10B0h+var_1118], r14d
0x180006d7c  jnz     short loc_180006D84
0x180006d7e  cmp     [rbp+10B0h+var_1114], r14d
0x180006d82  jz      short loc_180006D8A
0x180006d84  lea     r9, [rbp+10B0h+var_1120]
0x180006d88  jmp     short loc_180006D8D
0x180006d8a  mov     r9, r14
0x180006d8d  mov     [rbp+10B0h+var_48], 8
0x180006d98  lea     rax, [rsp+11B0h+var_1160]
0x180006d9d  mov     [rbp+10B0h+var_50], rax
0x180006da4  lea     rax, [rsp+11B0h+var_1168]
0x180006da9  mov     [rbp+10B0h+var_60], rax
0x180006db0  mov     [rbp+10B0h+var_58], 4
0x180006dbb  test    rsi, rsi
0x180006dbe  jz      short loc_180006DDA
0x180006dc0  mov     rcx, rsi
0x180006dc3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006dc7  inc     rax
0x180006dca  cmp     [rsi+rax*2], r14w
0x180006dcf  jnz     short loc_180006DC7
0x180006dd1  lea     eax, ds:2[rax*2]
0x180006dd8  jmp     short loc_180006DE6
0x180006dda  lea     rcx, qword_180017B18
0x180006de1  mov     eax, 2
0x180006de6  mov     [rbp+10B0h+var_68], eax
0x180006dec  lea     r8, [rbp+10B0h+ActivityId]
0x180006df0  lea     rax, [rbp+10B0h+var_90]
0x180006df7  mov     [rbp+10B0h+var_70], rcx
0x180006dfe  mov     [rsp+11B0h+var_1188], rax
0x180006e03  lea     rdx, byte_180018985
0x180006e0a  lea     rcx, dword_18001D020
0x180006e11  mov     [rsp+11B0h+var_1190], 5
0x180006e19  mov     [rbp+10B0h+var_64], r14d
0x180006e20  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180006e25  mov     [rsp+11B0h+var_1140], bl
0x180006e29  lea     rax, [rsp+11B0h+var_1138]
0x180006e2e  mov     [rsp+11B0h+var_1158], rax
0x180006e33  lea     rax, [rsp+11B0h+var_1180]
0x180006e38  mov     [rsp+11B0h+var_1150], rax
0x180006e3d  lea     rax, [rsp+11B0h+var_1178]
0x180006e42  mov     [rsp+11B0h+var_1148], rax
0x180006e47  test    rsi, rsi
0x180006e4a  jnz     short loc_180006E5A
0x180006e4c  lea     ecx, [rsi+7Bh]
0x180006e4f  mov     [rsp+11B0h+var_1180], ecx
0x180006e53  mov     esi, ebx
0x180006e55  jmp     loc_180006F5E
0x180006e5a  test    r12, r12
0x180006e5d  jnz     short loc_180006E66
0x180006e5f  lea     ecx, [r12+57h]
0x180006e64  jmp     short loc_180006E4F
0x180006e66  lea     r9, [rsp+11B0h+var_116C]; unsigned int *
0x180006e6b  mov     rcx, rsi; InstanceName
0x180006e6e  lea     r8, [rsp+11B0h+var_1170]; unsigned int *
0x180006e73  mov     rbx, r14
0x180006e76  lea     rdx, [rbp+10B0h+Properties]; Properties
0x180006e7a  call    ?EtwpQueryRealTimeTraceProperties@@YAKPEAGPEAU_REALTIME_TRACE_PROPERTIES@@PEAK2@Z; EtwpQueryRealTimeTraceProperties(ushort *,_REALTIME_TRACE_PROPERTIES *,ulong *,ulong *)
0x180006e7f  mov     [rsp+11B0h+var_1180], eax
0x180006e83  mov     ecx, eax; dwErrCode
0x180006e85  test    eax, eax
0x180006e87  jnz     loc_180006F55
0x180006e8d  call    ?EtwpQueryMaximumProcessors@@YAKXZ; EtwpQueryMaximumProcessors(void)
0x180006e92  mov     r14d, [rsp+11B0h+var_1170]
0x180006e97  cmp     r14d, eax
0x180006e9a  cmova   eax, r14d
0x180006e9e  mov     ecx, eax; unsigned int
0x180006ea0  call    ?EtwpAllocateTraceHandle@@YAPEAU_TRACELOG_CONTEXT@@K@Z; EtwpAllocateTraceHandle(ulong)
0x180006ea5  mov     rbx, rax
0x180006ea8  test    rax, rax
0x180006eab  jnz     short loc_180006EBC
0x180006ead  lea     ecx, [rax+0Eh]
0x180006eb0  mov     [rsp+11B0h+var_1180], ecx
0x180006eb4  lea     esi, [rax+1]
0x180006eb7  jmp     loc_180006F5E
0x180006ebc  mov     rax, [rax+10h]
0x180006ec0  mov     r9, rsi; unsigned __int16 *
0x180006ec3  xor     r8d, r8d; unsigned __int16 *
0x180006ec6  mov     [rsp+11B0h+var_1178], rax
0x180006ecb  mov     rdx, r12; struct ETW_OPEN_TRACE_OPTIONS *
0x180006ece  mov     rcx, rbx; struct _TRACELOG_CONTEXT *
0x180006ed1  call    ?EtwpCopyLogfileInfoFromOptions@@YAKPEAU_TRACELOG_CONTEXT@@PEBUETW_OPEN_TRACE_OPTIONS@@PEBG2@Z; EtwpCopyLogfileInfoFromOptions(_TRACELOG_CONTEXT *,ETW_OPEN_TRACE_OPTIONS const *,ushort const *,ushort const *)
0x180006ed6  mov     [rsp+11B0h+var_1180], eax
0x180006eda  mov     ecx, eax
0x180006edc  test    eax, eax
0x180006ede  jnz     short loc_180006F55
0x180006ee0  bts     dword ptr [rbx+6Ch], 8
0x180006ee5  lea     rsi, [rbx+0C8h]
0x180006eec  mov     r8, rsi; struct _TRACE_LOGFILE_HEADER *
0x180006eef  lea     rcx, [rbp+10B0h+Properties]; struct _EVENT_TRACE_PROPERTIES *
0x180006ef3  mov     edx, r14d; unsigned int
0x180006ef6  call    ?EtwpGenerateLogHeaderForRealtime@@YAKPEAU_EVENT_TRACE_PROPERTIES@@KPEAU_TRACE_LOGFILE_HEADER@@@Z; EtwpGenerateLogHeaderForRealtime(_EVENT_TRACE_PROPERTIES *,ulong,_TRACE_LOGFILE_HEADER *)
0x180006efb  mov     [rsp+11B0h+var_1180], eax
0x180006eff  mov     ecx, eax
0x180006f01  test    eax, eax
0x180006f03  jnz     short loc_180006F55
0x180006f05  mov     ecx, [rsp+11B0h+var_116C]; unsigned int
0x180006f09  lea     r9, [rbx+278h]; unsigned int *
0x180006f10  lea     r8, [rbx+280h]; struct _SYSTEM_TRACE_HEADER **
0x180006f17  mov     rdx, rsi; struct _TRACE_LOGFILE_HEADER *
0x180006f1a  call    ?EtwpGenerateHeaderEventForRealtime@@YAKKPEAU_TRACE_LOGFILE_HEADER@@PEAPEAU_SYSTEM_TRACE_HEADER@@PEAK@Z; EtwpGenerateHeaderEventForRealtime(ulong,_TRACE_LOGFILE_HEADER *,_SYSTEM_TRACE_HEADER * *,ulong *)
0x180006f1f  mov     [rsp+11B0h+var_1180], eax
0x180006f23  mov     ecx, eax
0x180006f25  mov     esi, 1
0x180006f2a  test    eax, eax
0x180006f2c  jnz     short loc_180006F5A
0x180006f2e  mov     eax, 0FFFFFFFFh
0x180006f33  mov     [rbx+228h], sil
0x180006f3a  cmp     r15, rax
0x180006f3d  jnb     short loc_180006F42
0x180006f3f  mov     eax, r15d
0x180006f42  mov     [rbx+3A4h], eax
0x180006f48  mov     [rbx+398h], r13
0x180006f4f  mov     ecx, [rsp+11B0h+var_1180]
0x180006f53  jmp     short loc_180006F5A
0x180006f55  mov     esi, 1
0x180006f5a  test    ecx, ecx
0x180006f5c  jz      short loc_180006F7F
0x180006f5e  cmp     [rsp+11B0h+var_1178], 0FFFFFFFFFFFFFFFFh
0x180006f64  jz      short loc_180006F74
0x180006f66  mov     rcx, [rsp+11B0h+var_1178]; unsigned __int64
0x180006f6b  call    ?EtwpFreeTraceHandle@@YAK_K@Z; EtwpFreeTraceHandle(unsigned __int64)
0x180006f70  mov     ecx, [rsp+11B0h+var_1180]
0x180006f74  mov     [rsp+11B0h+var_1178], 0FFFFFFFFFFFFFFFFh
0x180006f7d  jmp     short loc_180006FEC
0x180006f7f  test    rdi, rdi
0x180006f82  jz      short loc_180006FEC
0x180006f84  mov     edx, 2
0x180006f89  lea     rax, [rbx+0C8h]
0x180006f90  lea     r8d, [rdx+7Eh]
0x180006f94  movups  xmm0, xmmword ptr [rax]
0x180006f97  movups  xmmword ptr [rdi], xmm0
0x180006f9a  movups  xmm1, xmmword ptr [rax+10h]
0x180006f9e  movups  xmmword ptr [rdi+10h], xmm1
0x180006fa2  movups  xmm0, xmmword ptr [rax+20h]
0x180006fa6  movups  xmmword ptr [rdi+20h], xmm0
0x180006faa  movups  xmm1, xmmword ptr [rax+30h]
0x180006fae  movups  xmmword ptr [rdi+30h], xmm1
0x180006fb2  movups  xmm0, xmmword ptr [rax+40h]
0x180006fb6  movups  xmmword ptr [rdi+40h], xmm0
0x180006fba  movups  xmm1, xmmword ptr [rax+50h]
0x180006fbe  movups  xmmword ptr [rdi+50h], xmm1
0x180006fc2  movups  xmm0, xmmword ptr [rax+60h]
0x180006fc6  movups  xmmword ptr [rdi+60h], xmm0
0x180006fca  movups  xmm1, xmmword ptr [rax+70h]
0x180006fce  add     rax, r8
0x180006fd1  movups  xmmword ptr [rdi+70h], xmm1
0x180006fd5  add     rdi, r8
0x180006fd8  sub     rdx, 1
0x180006fdc  jnz     short loc_180006F94
0x180006fde  movups  xmm0, xmmword ptr [rax]
0x180006fe1  movups  xmmword ptr [rdi], xmm0
0x180006fe4  mov     rax, [rax+10h]
0x180006fe8  mov     [rdi+10h], rax
0x180006fec  call    cs:__imp_SetLastError
0x180006ff2  mov     rbx, [rsp+11B0h+var_1178]
0x180006ff7  test    sil, sil
0x180006ffa  jz      short loc_180007006
0x180006ffc  lea     rcx, [rsp+11B0h+var_1158]
0x180007001  call    _lambda_9df24178b30265c7642c034c363ca207___operator__
0x180007006  cmp     [rsp+11B0h+var_1138], esi
0x18000700a  jnz     short loc_180007024
0x18000700c  lea     rdx, [rbp+10B0h+ActivityId]
0x180007010  mov     [rsp+11B0h+var_1138], 2
0x180007018  lea     rcx, dword_18001D020
0x18000701f  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x180007024  mov     rax, rbx
0x180007027  mov     rcx, [rbp+10B0h+var_40]
0x18000702e  xor     rcx, rsp; StackCookie
0x180007031  call    __security_check_cookie
0x180007036  mov     rbx, [rsp+11B0h+arg_10]
0x18000703e  add     rsp, 1180h
0x180007045  pop     r15
0x180007047  pop     r14
0x180007049  pop     r13
0x18000704b  pop     r12
0x18000704d  pop     rdi
0x18000704e  pop     rsi
0x18000704f  pop     rbp
0x180007050  retn
```
