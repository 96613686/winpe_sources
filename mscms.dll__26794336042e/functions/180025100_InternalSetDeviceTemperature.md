# InternalSetDeviceTemperature

- ea: `0x180025100`
- end: `0x18002555f`
- name: `InternalSetDeviceTemperature`
- size: `1119`
- prototype: `__int64 __fastcall(HDC)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180013000`
- `0x1800167b0`
- `0x180025100`
- `0x18002e5f0`
- `0x18002e670`
- `0x18002ea90`
- `0x18002f2f4`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800252f5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800252f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025250`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025250`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025554`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025374`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025554`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025506`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180025506`

## pseudocode

```c
__int64 __fastcall InternalSetDeviceTemperature(HDC a1, float a2, int a3, unsigned int a4)
{
  unsigned int v7; // esi
  int v8; // r8d
  unsigned int v9; // r9d
  __int64 v10; // r8
  __int64 v11; // rcx
  __int16 v12; // ax
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *v15; // rdi
  _DWORD *v16; // rax
  struct _RTL_CRITICAL_SECTION *v17; // rbx
  __int64 v18; // rax
  __int64 v19; // r9
  struct _GUID UserData_8; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-C0h]
  unsigned int v23; // [rsp+58h] [rbp-B0h] BYREF
  int v24; // [rsp+5Ch] [rbp-ACh] BYREF
  float v25; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD v26[3]; // [rsp+64h] [rbp-A4h] BYREF
  _WORD v27[768]; // [rsp+78h] [rbp-90h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+678h] [rbp+570h] BYREF
  __int16 *v29; // [rsp+688h] [rbp+580h]
  int v30; // [rsp+690h] [rbp+588h]
  int v31; // [rsp+694h] [rbp+58Ch]
  _DWORD *v32; // [rsp+698h] [rbp+590h]
  __int64 v33; // [rsp+6A0h] [rbp+598h]
  float *v34; // [rsp+6A8h] [rbp+5A0h]
  __int64 v35; // [rsp+6B0h] [rbp+5A8h]
  int *v36; // [rsp+6B8h] [rbp+5B0h]
  __int64 v37; // [rsp+6C0h] [rbp+5B8h]
  int *v38; // [rsp+6C8h] [rbp+5C0h]
  __int64 v39; // [rsp+6D0h] [rbp+5C8h]
  _WORD v40[768]; // [rsp+6D8h] [rbp+5D0h] BYREF

  v7 = 0;
  if ( a1 )
  {
    memset_0(v27, 0, sizeof(v27));
    CreateTemperatureGammaRamp(a2, (struct GammaLut *)v27, v8);
    memset_0(v40, 0, sizeof(v40));
    v9 = 0;
    v10 = 0;
    do
    {
      v11 = 3 * v10;
      v40[v11] = v27[v10];
      v12 = v27[v10 + 256];
      v10 += 2;
      v40[v11 + 1] = v12;
      v40[v11 + 2] = v27[v10 + 510];
      v13 = v9 + 1;
      v9 += 2;
      v14 = 3 * v13;
      v40[v14] = v27[v13];
      v40[v14 + 1] = v27[v13 + 256];
      v40[v14 + 2] = v27[v13 + 512];
    }
    while ( v9 < 0x100 );
    UserData_8 = (struct _GUID)xmmword_18008C728;
    LOBYTE(v7) = (int)ModernColorSetGDILutFromHDC(a1, &UserData_8, (struct UINT16Triple (*)[256])v40) >= 0;
  }
  UserData_8 = 0;
  v22 = 0;
  EnterCriticalSection(&telemetryCritsec);
  if ( internalSetDeviceTemperatureAggregateTelemetry )
    goto LABEL_14;
  v15 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 )
  {
    *v15 = &CAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,unsigned long,InternalSetDeviceTemperatureProperties *,1,0>::`vftable';
    v15[1] = 0;
    *((_BYTE *)v15 + 16) = 0;
    v15[3] = 0;
    v16 = operator new(0x48u);
    *(_QWORD *)v16 = &InternalSetDeviceTemperatureAggregateValues::`vftable';
    v16[2] = 2139095039;
    v16[3] = -8388609;
    v16[4] = 0;
    *((_QWORD *)v16 + 5) = 0;
    *((_QWORD *)v16 + 3) = 0;
    *((_QWORD *)v16 + 4) = 0;
    *((_OWORD *)v16 + 3) = 0;
    *((_QWORD *)v16 + 8) = 0;
    v15[1] = v16;
    *((_BYTE *)v15 + 17) = 1;
    v17 = (struct _RTL_CRITICAL_SECTION *)operator new(0x28u);
    InitializeCriticalSection(v17);
    v15[3] = v17;
    *v15 = &DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,unsigned long,InternalSetDeviceTemperatureProperties *,1,0>::`vftable';
    *((_BYTE *)v15 + 32) = 1;
    v15[5] = 0;
    v15[6] = 0;
  }
  else
  {
    v15 = 0;
  }
  if ( internalSetDeviceTemperatureAggregateTelemetry )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)internalSetDeviceTemperatureAggregateTelemetry + 32LL))(
      internalSetDeviceTemperatureAggregateTelemetry,
      1);
  if ( !v15 )
  {
LABEL_21:
    internalSetDeviceTemperatureAggregateTelemetry = 0;
    LeaveCriticalSection(&telemetryCritsec);
    goto LABEL_15;
  }
  internalSetDeviceTemperatureAggregateTelemetry = (__int64)v15;
  v18 = *v15;
  if ( !v15[1] )
  {
    (*(void (__fastcall **)(_QWORD *, __int64))(v18 + 32))(v15, 1);
    goto LABEL_21;
  }
  (*(void (__fastcall **)(_QWORD *, __int64))(v18 + 40))(v15, 3600000);
LABEL_14:
  LeaveCriticalSection(&telemetryCritsec);
  *(float *)UserData_8.Data4 = a2;
  LOBYTE(v19) = 1;
  v22 = __PAIR64__(v7, a4);
  *(_DWORD *)&UserData_8.Data4[4] = a3;
  *(_QWORD *)&UserData_8.Data1 = a1;
  (*(void (__fastcall **)(__int64, _QWORD, struct _GUID *, __int64, char))(*(_QWORD *)internalSetDeviceTemperatureAggregateTelemetry
                                                                         + 56LL))(
    internalSetDeviceTemperatureAggregateTelemetry,
    0,
    &UserData_8,
    v19,
    1);
LABEL_15:
  if ( (unsigned int)dword_18009E048 > 5 && (qword_18009E058 & 2) != 0 && (qword_18009E060 & 2) == qword_18009E060 )
  {
    v25 = a2;
    v38 = (int *)&v23;
    v23 = a4;
    v36 = &v24;
    v24 = a3;
    v34 = &v25;
    v26[0] = v7;
    v32 = v26;
    UserData.Ptr = (ULONGLONG)off_18009E050;
    v39 = 4;
    v37 = 4;
    v35 = 4;
    v33 = 4;
    *(_QWORD *)&UserData_8.Data1 = 0x50B000000LL;
    *(_QWORD *)UserData_8.Data4 = 2;
    UserData.Size = *(unsigned __int16 *)off_18009E050;
    v29 = word_180092002;
    UserData.Reserved = 2;
    v30 = 91;
    v31 = 1;
    v26[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_18009E068, (PCEVENT_DESCRIPTOR)&UserData_8, 0, 0, 6u, &UserData);
  }
  return v7;
}

```

## disassembly

```asm
0x180025100  mov     r11, rsp
0x180025103  push    rbp
0x180025104  push    rsi
0x180025105  push    r12
0x180025107  push    r13
0x180025109  push    r15
0x18002510b  lea     rbp, [r11-0C38h]
0x180025112  sub     rsp, 0D10h
0x180025119  movaps  xmmword ptr [r11-58h], xmm6
0x18002511e  mov     rax, cs:__security_cookie
0x180025125  xor     rax, rsp
0x180025128  mov     [rbp+0C30h+var_60], rax
0x18002512f  xor     r13d, r13d
0x180025132  mov     [r11-40h], r14
0x180025136  mov     r12d, r9d
0x180025139  mov     r15d, r8d
0x18002513c  movaps  xmm6, xmm1
0x18002513f  mov     r14, rcx
0x180025142  mov     esi, r13d
0x180025145  test    rcx, rcx
0x180025148  jz      loc_180025232
0x18002514e  xor     edx, edx; Val
0x180025150  lea     rcx, [rsp+0D30h+var_CC0]; void *
0x180025155  mov     r8d, 600h; Size
0x18002515b  call    memset_0
0x180025160  lea     rdx, [rsp+0D30h+var_CC0]; struct GammaLut *
0x180025165  movaps  xmm0, xmm6; float
0x180025168  call    ?CreateTemperatureGammaRamp@@YAXMPEAUGammaLut@@H@Z; CreateTemperatureGammaRamp(float,GammaLut *,int)
0x18002516d  xor     edx, edx; Val
0x18002516f  lea     rcx, [rbp+0C30h+var_660]; void *
0x180025176  mov     r8d, 600h; Size
0x18002517c  call    memset_0
0x180025181  mov     r9d, r13d
0x180025184  mov     r8d, r13d
0x180025187  nop     word ptr [rax+rax+00000000h]
0x180025190  movzx   eax, word ptr [rsp+r8*2+0D30h+var_CC0]
0x180025196  lea     rcx, [r8+r8*2]
0x18002519a  mov     [rbp+rcx*2+0C30h+var_660], ax
0x1800251a2  movzx   eax, [rbp+r8*2+0C30h+var_AC0]
0x1800251ab  lea     r8, [r8+2]
0x1800251af  mov     [rbp+rcx*2+0C30h+var_65E], ax
0x1800251b7  movzx   eax, [rbp+r8*2+0C30h+var_8C4]
0x1800251c0  mov     [rbp+rcx*2+0C30h+var_65C], ax
0x1800251c8  lea     eax, [r9+1]
0x1800251cc  mov     edx, eax
0x1800251ce  add     r9d, 2
0x1800251d2  lea     rcx, [rax+rax*2]
0x1800251d6  movzx   eax, word ptr [rsp+rax*2+0D30h+var_CC0]
0x1800251db  mov     [rbp+rcx*2+0C30h+var_660], ax
0x1800251e3  movzx   eax, [rbp+rdx*2+0C30h+var_AC0]
0x1800251eb  mov     [rbp+rcx*2+0C30h+var_65E], ax
0x1800251f3  movzx   eax, [rbp+rdx*2+0C30h+var_8C0]
0x1800251fb  mov     [rbp+rcx*2+0C30h+var_65C], ax
0x180025203  cmp     r9d, 100h
0x18002520a  jb      short loc_180025190
0x18002520c  movups  xmm0, cs:xmmword_18008C728
0x180025213  lea     r8, [rbp+0C30h+var_660]; struct UINT16Triple (*)[256]
0x18002521a  mov     rcx, r14; HDC
0x18002521d  lea     rdx, [rsp+0D30h+UserData+8]; struct _GUID
0x180025222  movaps  xmmword ptr [rsp+0D30h+UserData+8], xmm0
0x180025227  call    ?ModernColorSetGDILutFromHDC@@YAJPEAUHDC__@@U_GUID@@AEAY0BAA@UUINT16Triple@@@Z; ModernColorSetGDILutFromHDC(HDC__ *,_GUID,UINT16Triple (&)[256])
0x18002522c  test    eax, eax
0x18002522e  setns   sil
0x180025232  xorps   xmm0, xmm0
0x180025235  mov     [rsp+0D30h+var_30], rdi
0x18002523d  xor     eax, eax
0x18002523f  lea     rcx, telemetryCritsec; lpCriticalSection
0x180025246  movups  xmmword ptr [rsp+0D30h+UserData+8], xmm0
0x18002524b  mov     [rsp+0D30h+var_CF0], rax
0x180025250  call    cs:__imp_EnterCriticalSection
0x180025256  cmp     cs:?internalSetDeviceTemperatureAggregateTelemetry@@3V?$TAutoPtr@V?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@@NCoreLibrary@@A, r13; NCoreLibrary::TAutoPtr<DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>> internalSetDeviceTemperatureAggregateTelemetry
0x18002525d  jnz     loc_18002536D
0x180025263  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002526a  mov     ecx, 38h ; '8'; unsigned __int64
0x18002526f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180025274  mov     rdi, rax
0x180025277  test    rax, rax
0x18002527a  jz      loc_18002531F
0x180025280  lea     rax, ??_7?$CAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@6B@; const CAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>::`vftable'
0x180025287  mov     [rsp+0D08h], rbx
0x18002528f  mov     ecx, 48h ; 'H'; Size
0x180025294  mov     [rdi], rax
0x180025297  mov     [rdi+8], r13
0x18002529b  mov     [rdi+10h], r13b
0x18002529f  mov     [rdi+18h], r13
0x1800252a3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800252a8  lea     rcx, ??_7InternalSetDeviceTemperatureAggregateValues@@6B@; const InternalSetDeviceTemperatureAggregateValues::`vftable'
0x1800252af  xorps   xmm0, xmm0
0x1800252b2  mov     [rax], rcx
0x1800252b5  xor     ecx, ecx
0x1800252b7  mov     dword ptr [rax+8], 7F7FFFFFh
0x1800252be  mov     dword ptr [rax+0Ch], 0FF7FFFFFh
0x1800252c5  mov     [rax+10h], r13d
0x1800252c9  mov     [rax+28h], r13
0x1800252cd  mov     [rax+18h], r13
0x1800252d1  mov     [rax+20h], r13
0x1800252d5  movups  xmmword ptr [rax+30h], xmm0
0x1800252d9  mov     [rax+40h], rcx
0x1800252dd  mov     ecx, 28h ; '('; Size
0x1800252e2  mov     [rdi+8], rax
0x1800252e6  mov     byte ptr [rdi+11h], 1
0x1800252ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800252ef  mov     rcx, rax; lpCriticalSection
0x1800252f2  mov     rbx, rax
0x1800252f5  call    cs:__imp_InitializeCriticalSection
0x1800252fb  lea     rax, ??_7?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@6B@; const DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>::`vftable'
0x180025302  mov     [rdi+18h], rbx
0x180025306  mov     rbx, [rsp+0D08h]
0x18002530e  mov     [rdi], rax
0x180025311  mov     byte ptr [rdi+20h], 1
0x180025315  mov     [rdi+28h], r13
0x180025319  mov     [rdi+30h], r13
0x18002531d  jmp     short loc_180025322
0x18002531f  mov     rdi, r13
0x180025322  mov     rcx, cs:?internalSetDeviceTemperatureAggregateTelemetry@@3V?$TAutoPtr@V?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@@NCoreLibrary@@A; NCoreLibrary::TAutoPtr<DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>> internalSetDeviceTemperatureAggregateTelemetry
0x180025329  test    rcx, rcx
0x18002532c  jz      short loc_18002533F
0x18002532e  mov     rax, [rcx]
0x180025331  mov     edx, 1
0x180025336  mov     rax, [rax+20h]
0x18002533a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002533f  test    rdi, rdi
0x180025342  jz      loc_180025543
0x180025348  mov     cs:?internalSetDeviceTemperatureAggregateTelemetry@@3V?$TAutoPtr@V?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@@NCoreLibrary@@A, rdi; NCoreLibrary::TAutoPtr<DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>> internalSetDeviceTemperatureAggregateTelemetry
0x18002534f  mov     rcx, rdi
0x180025352  mov     rax, [rdi]
0x180025355  cmp     [rdi+8], r13
0x180025359  jz      loc_180025535
0x18002535f  mov     rax, [rax+28h]
0x180025363  mov     edx, 36EE80h
0x180025368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002536d  lea     rcx, telemetryCritsec; lpCriticalSection
0x180025374  call    cs:__imp_LeaveCriticalSection
0x18002537a  mov     rcx, cs:?internalSetDeviceTemperatureAggregateTelemetry@@3V?$TAutoPtr@V?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@@NCoreLibrary@@A; NCoreLibrary::TAutoPtr<DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>> internalSetDeviceTemperatureAggregateTelemetry
0x180025381  lea     r8, [rsp+0D30h+UserData+8]
0x180025386  movss   dword ptr [rsp+0D30h+var_CF8], xmm6
0x18002538c  mov     r9b, 1
0x18002538f  mov     dword ptr [rsp+0D30h+var_CF0], r12d
0x180025394  xor     edx, edx
0x180025396  mov     dword ptr [rsp+0D30h+var_CF8+4], r15d
0x18002539b  mov     dword ptr [rsp+0D30h+var_CF0+4], esi
0x18002539f  mov     [rsp+0D30h+UserData+8], r14
0x1800253a4  mov     rax, [rcx]
0x1800253a7  mov     byte ptr [rsp+0D30h+UserDataCount], 1
0x1800253ac  mov     rax, [rax+38h]
0x1800253b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253b5  mov     eax, cs:dword_18009E048
0x1800253bb  mov     r14, [rsp+0D30h+var_38]
0x1800253c3  mov     rdi, [rsp+0D30h+var_30]
0x1800253cb  cmp     eax, 5
0x1800253ce  jbe     loc_18002550C
0x1800253d4  mov     rcx, cs:qword_18009E060
0x1800253db  mov     rax, cs:qword_18009E058
0x1800253e2  test    al, 2
0x1800253e4  jz      loc_18002550C
0x1800253ea  mov     rax, rcx
0x1800253ed  and     eax, 2
0x1800253f0  cmp     rax, rcx
0x1800253f3  jnz     loc_18002550C
0x1800253f9  movss   [rsp+0D30h+var_CD8], xmm6
0x1800253ff  lea     rax, [rsp+0D30h+var_CE0]
0x180025404  mov     [rbp+0C30h+var_670], rax
0x18002540b  lea     rcx, _TraceLoggingMetadataEnd
0x180025412  mov     [rsp+0D30h+var_CE0], r12d
0x180025417  lea     rax, [rsp+0D30h+var_CDC]
0x18002541c  mov     [rbp+0C30h+var_680], rax
0x180025423  lea     rdx, [rsp+0D30h+UserData+8]; EventDescriptor
0x180025428  mov     [rsp+0D30h+var_CDC], r15d
0x18002542d  lea     rax, [rsp+0D30h+var_CD8]
0x180025432  mov     [rbp+0C30h+var_690], rax
0x180025439  xor     r9d, r9d; RelatedActivityId
0x18002543c  lea     rax, [rsp+5Ch]
0x180025441  mov     [rsp+5Ch], esi
0x180025445  mov     [rbp+0C30h+var_6A0], rax
0x18002544c  xor     r8d, r8d; ActivityId
0x18002544f  movzx   eax, cs:word_180091FF8
0x180025456  mov     dword ptr [rsp+0D30h+UserData+0Ch], eax
0x18002545a  mov     rax, cs:off_18009E050
0x180025461  mov     [rbp+0C30h+var_6C0.Ptr], rax
0x180025468  mov     [rbp+0C30h+var_668], 4
0x180025473  mov     [rbp+0C30h+var_678], 4
0x18002547e  mov     [rbp+0C30h+var_688], 4
0x180025489  mov     [rbp+0C30h+var_698], 4
0x180025494  mov     dword ptr [rsp+0D30h+UserData+8], 0B000000h
0x18002549c  mov     [rsp+0D30h+var_CF8], 2
0x1800254a5  movzx   eax, word ptr [rax]
0x1800254a8  mov     [rbp+0C30h+var_6C0.Size], eax
0x1800254ae  lea     rax, word_180092002
0x1800254b5  mov     [rbp+0C30h+var_6B0], rax
0x1800254bc  lea     rax, _TraceLoggingMetadata
0x1800254c3  sub     ecx, eax
0x1800254c5  mov     dword ptr [rbp+0C30h+var_6C0.0Ch], 2
0x1800254cf  mov     [rbp+0C30h+var_6A8], 5Bh ; '['
0x1800254d9  lea     rax, [rbp+0C30h+var_6C0]
0x1800254e0  mov     [rbp+0C30h+var_6A4], 1
0x1800254ea  mov     [rsp+60h], ecx
0x1800254ee  mov     ecx, [rsp+60h]
0x1800254f2  mov     rcx, cs:qword_18009E068; RegHandle
0x1800254f9  mov     [rsp+0D30h+UserData], rax; UserData
0x1800254fe  mov     [rsp+0D30h+UserDataCount], 6; UserDataCount
0x180025506  call    cs:__imp_EventWriteTransfer
0x18002550c  mov     eax, esi
0x18002550e  mov     rcx, [rbp+0C30h+var_60]
0x180025515  xor     rcx, rsp; StackCookie
0x180025518  call    __security_check_cookie
0x18002551d  movaps  xmm6, [rsp+0D30h+var_58+8]
0x180025525  add     rsp, 0D10h
0x18002552c  pop     r15
0x18002552e  pop     r13
0x180025530  pop     r12
0x180025532  pop     rsi
0x180025533  pop     rbp
0x180025534  retn
0x180025535  mov     rax, [rax+20h]
0x180025539  mov     edx, 1
0x18002553e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025543  mov     rax, r13
0x180025546  lea     rcx, telemetryCritsec; lpCriticalSection
0x18002554d  mov     cs:?internalSetDeviceTemperatureAggregateTelemetry@@3V?$TAutoPtr@V?$DelayedAggregateTelemetry@VInternalSetDeviceTemperatureAggregateValues@@KPEAUInternalSetDeviceTemperatureProperties@@$00$0A@@@@NCoreLibrary@@A, rax; NCoreLibrary::TAutoPtr<DelayedAggregateTelemetry<InternalSetDeviceTemperatureAggregateValues,ulong,InternalSetDeviceTemperatureProperties *,1,0>> internalSetDeviceTemperatureAggregateTelemetry
0x180025554  call    cs:__imp_LeaveCriticalSection
0x18002555a  jmp     loc_1800253B5
```
