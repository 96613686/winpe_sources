# OpenTraceW

- ea: `0x180007060`
- end: `0x1800074f7`
- name: `OpenTraceW`
- size: `1175`
- prototype: `TRACEHANDLE __stdcall(PEVENT_TRACE_LOGFILEW Logfile)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002870`

## callees

- `0x180001008`
- `0x180001560`
- `0x180001eb2`
- `0x180002ec4`
- `0x180003c24`
- `0x180003fa8`
- `0x18000485c`
- `0x180004ea8`
- `0x1800052b4`
- `0x180007060`
- `0x18000ef18`
- `0x18000f098`
- `0x18000fdf8`
- `0x18000fe48`
- `0x1800157b0`

## import_xrefs

- `ntdll!NtQueryLicenseValue` at `0x18000736e`
- `ntdll!NtQueryLicenseValue` at `0x18000736e`
- `ntdll!RtlInitUnicodeString` at `0x180007349`
- `ntdll!RtlInitUnicodeString` at `0x180007349`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000749e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000749e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007107`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180007107`

## pseudocode

```c
TRACEHANDLE __stdcall OpenTraceW(PEVENT_TRACE_LOGFILEW Logfile)
{
  unsigned int v2; // r14d
  unsigned int v3; // edi
  char v4; // si
  unsigned int MaximumProcessors; // eax
  const WCHAR *LoggerName; // rcx
  struct _TRACELOG_CONTEXT *TraceHandle; // rax
  struct _TRACELOG_CONTEXT *v8; // rax
  __int64 (__fastcall *v9)(); // rcx
  unsigned int v10; // eax
  struct _TRACELOG_CONTEXT *v11; // rcx
  __int64 v12; // r8
  TRACE_LOGFILE_HEADER *p_LogfileHeader; // rdx
  _OWORD *v14; // rax
  __int128 v15; // xmm1
  TRACEHANDLE v16; // rbx
  DWORD dwErrCode; // [rsp+30h] [rbp-D0h] BYREF
  struct _TRACELOG_CONTEXT *v19; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-A8h] BYREF
  int v25; // [rsp+68h] [rbp-98h] BYREF
  char v26; // [rsp+6Ch] [rbp-94h]
  GUID ActivityId; // [rsp+70h] [rbp-90h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v29[3]; // [rsp+1110h] [rbp+1010h] BYREF
  char v30; // [rsp+1128h] [rbp+1028h]

  v21 = 0;
  v20 = 0;
  v2 = 0;
  v3 = 0;
  memset_0(&Properties, 0, 0x1078u);
  dwErrCode = 87;
  v19 = 0;
  v22 = -1;
  v25 = 0;
  v26 = 0;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    EventActivityIdControl(3u, &ActivityId);
  else
    ActivityId = 0;
  v25 = 1;
  if ( (unsigned int)dword_18001D020 > 5 && (qword_18001D030 & 0x10) != 0 && (qword_18001D038 & 0x10) == qword_18001D038 )
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_18001D020,
      (unsigned __int8 *)&word_180018AB6,
      (__int64)&ActivityId,
      0,
      2,
      (__int64)v29);
  v30 = 1;
  v29[0] = &v25;
  v29[1] = &dwErrCode;
  v29[2] = &v22;
  if ( !Logfile )
    goto LABEL_44;
  if ( (Logfile->LogFileMode & 0x100) == 0 )
  {
    v4 = 0;
    MaximumProcessors = 0;
LABEL_20:
    TraceHandle = EtwpAllocateTraceHandle(MaximumProcessors);
    v19 = TraceHandle;
    if ( !TraceHandle )
    {
      dwErrCode = 14;
      goto LABEL_45;
    }
    v22 = *((_QWORD *)TraceHandle + 2);
    dwErrCode = EtwpCopyLogfileInfo(TraceHandle, Logfile);
    if ( !dwErrCode )
    {
      if ( (Logfile->LogFileMode & 0x1000) != 0 )
        *((_DWORD *)v19 + 8) |= 2u;
      v8 = v19;
      if ( (Logfile->LogFileMode & 0x10000000) != 0 )
      {
        *((_DWORD *)v19 + 8) |= 0x10000000u;
        v9 = (__int64 (__fastcall *)())EtwpMapEventToEventRecord;
        v8 = v19;
      }
      else
      {
        v9 = EtwpMapEventToEventTraceAdapter;
      }
      *((_QWORD *)v8 + 68) = v9;
      if ( !v4 )
      {
        *((_BYTE *)v19 + 552) = 0;
        dwErrCode = EtwpProcessLogHeader(&v19, 1u, 1);
        if ( dwErrCode )
          goto LABEL_44;
        v11 = v19;
        Logfile->IsKernelTrace = *((_DWORD *)v19 + 128);
        Logfile->LogFileMode = *((_DWORD *)v11 + 27);
        goto LABEL_41;
      }
      *((_BYTE *)v19 + 552) = 1;
      dwErrCode = EtwpGenerateLogHeaderForRealtime(&Properties, v3, (struct _TRACE_LOGFILE_HEADER *)((char *)v19 + 200));
      if ( !dwErrCode
        && ((*((_DWORD *)v19 + 8) & 0x100) == 0
         || (dwErrCode = EtwpGenerateHeaderEventForRealtime(
                           v2,
                           (struct _TRACE_LOGFILE_HEADER *)((char *)v19 + 200),
                           (struct _SYSTEM_TRACE_HEADER **)v19 + 80,
                           (unsigned int *)v19 + 158)) == 0) )
      {
        v10 = dword_18001D1B4;
        v20 = dword_18001D1B4;
        if ( dword_18001D1B4 == -1 )
        {
          v23 = 0;
          v21 = 0;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"Kernel-ProductInfo");
          if ( (int)NtQueryLicenseValue(&DestinationString, &v23, &v20, 4, &v21) < 0 )
          {
LABEL_38:
            v11 = v19;
LABEL_41:
            v12 = 2;
            p_LogfileHeader = &Logfile->LogfileHeader;
            v14 = (_OWORD *)((char *)v11 + 200);
            do
            {
              *(_OWORD *)&p_LogfileHeader->BufferSize = *v14;
              *(_OWORD *)&p_LogfileHeader->EndTime.LowPart = v14[1];
              *(_OWORD *)&p_LogfileHeader->LogFileMode = v14[2];
              *(_OWORD *)&p_LogfileHeader->EventsLost = v14[3];
              *(_OWORD *)&p_LogfileHeader->LogFileName = v14[4];
              *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[2] = v14[5];
              *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[10] = v14[6];
              v15 = v14[7];
              v14 += 8;
              *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[18] = v15;
              p_LogfileHeader = (TRACE_LOGFILE_HEADER *)((char *)p_LogfileHeader + 128);
              --v12;
            }
            while ( v12 );
            *(_OWORD *)&p_LogfileHeader->BufferSize = *v14;
            p_LogfileHeader->EndTime.QuadPart = *((_QWORD *)v14 + 2);
            Logfile->CurrentEvent.MofLength = *((_DWORD *)v11 + 158);
            Logfile->CurrentEvent.MofData = (PVOID)*((_QWORD *)v11 + 80);
            goto LABEL_44;
          }
          v10 = v20;
          dword_18001D1B4 = v20;
        }
        if ( v10 == 194 && (Logfile->LogFileMode & 0x8000000) != 0 )
        {
          *((_DWORD *)v19 + 233) = Logfile->BufferSize;
          *((_QWORD *)v19 + 115) = *(_QWORD *)&Logfile->Filled;
        }
        goto LABEL_38;
      }
    }
LABEL_44:
    if ( !dwErrCode )
      goto LABEL_48;
    goto LABEL_45;
  }
  LoggerName = Logfile->LoggerName;
  if ( LoggerName )
  {
    v4 = 1;
    dwErrCode = EtwpQueryRealTimeTraceProperties(LoggerName, &Properties, &v20, &v21);
    if ( dwErrCode )
    {
      dwErrCode = 0;
    }
    else
    {
      v2 = v21;
      v3 = v20;
    }
    MaximumProcessors = EtwpQueryMaximumProcessors();
    if ( v3 > MaximumProcessors )
      MaximumProcessors = v3;
    goto LABEL_20;
  }
  dwErrCode = 123;
LABEL_45:
  if ( v22 != -1 )
    EtwpFreeTraceHandle(v22);
  v22 = -1;
LABEL_48:
  SetLastError(dwErrCode);
  v16 = v22;
  lambda_672f30a2b4c3e78079b9ebb124984960_::operator()(v29);
  if ( v25 == 1 )
  {
    v25 = 2;
    _tlgWriteActivityAutoStop<16,5>(&dword_18001D020, &ActivityId);
  }
  return v16;
}

```

## disassembly

```asm
0x180007060  push    rbp
0x180007062  push    rbx
0x180007063  push    rsi
0x180007064  push    rdi
0x180007065  push    r14
0x180007067  push    r15
0x180007069  lea     rbp, [rsp-1048h]
0x180007071  mov     eax, 1148h
0x180007076  call    _alloca_probe
0x18000707b  sub     rsp, rax
0x18000707e  mov     rax, cs:__security_cookie
0x180007085  xor     rax, rsp
0x180007088  mov     [rbp+1070h+var_40], rax
0x18000708f  xor     r15d, r15d
0x180007092  mov     rbx, rcx
0x180007095  lea     rcx, [rbp+1070h+Properties]; void *
0x180007099  mov     [rsp+1170h+var_112C], r15d
0x18000709e  xor     edx, edx; Val
0x1800070a0  mov     [rsp+1170h+var_1130], r15d
0x1800070a5  mov     r8d, 1078h; Size
0x1800070ab  mov     r14d, r15d
0x1800070ae  mov     edi, r15d
0x1800070b1  call    memset_0
0x1800070b6  mov     eax, cs:dword_18001D020
0x1800070bc  mov     [rsp+1170h+dwErrCode], 57h ; 'W'
0x1800070c4  mov     [rsp+1170h+var_1138], r15
0x1800070c9  mov     [rsp+1170h+var_1128], 0FFFFFFFFFFFFFFFFh
0x1800070d2  mov     [rsp+1170h+var_1108], r15d
0x1800070d7  mov     [rsp+1170h+var_1104], r15b
0x1800070dc  cmp     eax, 5
0x1800070df  jbe     short loc_18000710F
0x1800070e1  mov     rcx, cs:qword_18001D038
0x1800070e8  mov     rax, cs:qword_18001D030
0x1800070ef  test    al, 10h
0x1800070f1  jz      short loc_18000710F
0x1800070f3  mov     rax, rcx
0x1800070f6  and     eax, 10h
0x1800070f9  cmp     rax, rcx
0x1800070fc  jnz     short loc_18000710F
0x1800070fe  lea     rdx, [rsp+1170h+ActivityId]; ActivityId
0x180007103  lea     ecx, [r15+3]; ControlCode
0x180007107  call    cs:__imp_EventActivityIdControl
0x18000710d  jmp     short loc_180007117
0x18000710f  xorps   xmm0, xmm0
0x180007112  movups  xmmword ptr [rsp+1170h+ActivityId.Data1], xmm0
0x180007117  mov     eax, cs:dword_18001D020
0x18000711d  mov     [rsp+1170h+var_1108], 1
0x180007125  cmp     eax, 5
0x180007128  jbe     short loc_18000719B
0x18000712a  mov     rcx, cs:qword_18001D038
0x180007131  mov     rax, cs:qword_18001D030
0x180007138  test    al, 10h
0x18000713a  jz      short loc_18000719B
0x18000713c  mov     rax, rcx
0x18000713f  and     eax, 10h
0x180007142  cmp     rax, rcx
0x180007145  jnz     short loc_18000719B
0x180007147  cmp     [rsp+1170h+var_1104], r15b
0x18000714c  jz      short loc_18000716C
0x18000714e  cmp     [rbp+1070h+var_10F0], r15d
0x180007152  jnz     short loc_180007166
0x180007154  cmp     [rbp+1070h+var_10EC], r15d
0x180007158  jnz     short loc_180007166
0x18000715a  cmp     [rbp+1070h+var_10E8], r15d
0x18000715e  jnz     short loc_180007166
0x180007160  cmp     [rbp+1070h+var_10E4], r15d
0x180007164  jz      short loc_18000716C
0x180007166  lea     r9, [rbp+1070h+var_10F0]
0x18000716a  jmp     short loc_18000716F
0x18000716c  mov     r9, r15
0x18000716f  lea     rax, [rbp+1070h+var_60]
0x180007176  mov     [rsp+1170h+var_1148], rax
0x18000717b  lea     r8, [rsp+1170h+ActivityId]
0x180007180  lea     rdx, word_180018AB6
0x180007187  mov     dword ptr [rsp+1170h+var_1150], 2
0x18000718f  lea     rcx, dword_18001D020
0x180007196  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000719b  mov     [rbp+1070h+var_48], 1
0x1800071a2  lea     rax, [rsp+1170h+var_1108]
0x1800071a7  mov     [rbp+1070h+var_60], rax
0x1800071ae  lea     rax, [rsp+1170h+dwErrCode]
0x1800071b3  mov     [rbp+1070h+var_58], rax
0x1800071ba  lea     rax, [rsp+1170h+var_1128]
0x1800071bf  mov     [rbp+1070h+var_50], rax
0x1800071c6  test    rbx, rbx
0x1800071c9  jz      loc_18000747A
0x1800071cf  test    dword ptr [rbx+1Ch], 100h
0x1800071d6  jnz     short loc_1800071E0
0x1800071d8  mov     sil, r15b
0x1800071db  mov     eax, r15d
0x1800071de  jmp     short loc_18000722F
0x1800071e0  mov     rcx, [rbx+8]; InstanceName
0x1800071e4  test    rcx, rcx
0x1800071e7  jnz     short loc_1800071F6
0x1800071e9  mov     [rsp+1170h+dwErrCode], 7Bh ; '{'
0x1800071f1  jmp     loc_180007481
0x1800071f6  lea     r9, [rsp+1170h+var_112C]; unsigned int *
0x1800071fb  mov     sil, 1
0x1800071fe  lea     r8, [rsp+1170h+var_1130]; unsigned int *
0x180007203  lea     rdx, [rbp+1070h+Properties]; Properties
0x180007207  call    ?EtwpQueryRealTimeTraceProperties@@YAKPEAGPEAU_REALTIME_TRACE_PROPERTIES@@PEAK2@Z; EtwpQueryRealTimeTraceProperties(ushort *,_REALTIME_TRACE_PROPERTIES *,ulong *,ulong *)
0x18000720c  mov     [rsp+1170h+dwErrCode], eax
0x180007210  test    eax, eax
0x180007212  jz      short loc_18000721B
0x180007214  mov     [rsp+1170h+dwErrCode], r15d
0x180007219  jmp     short loc_180007224
0x18000721b  mov     r14d, [rsp+1170h+var_112C]
0x180007220  mov     edi, [rsp+1170h+var_1130]
0x180007224  call    ?EtwpQueryMaximumProcessors@@YAKXZ; EtwpQueryMaximumProcessors(void)
0x180007229  cmp     edi, eax
0x18000722b  jbe     short loc_18000722F
0x18000722d  mov     eax, edi
0x18000722f  mov     ecx, eax; unsigned int
0x180007231  call    ?EtwpAllocateTraceHandle@@YAPEAU_TRACELOG_CONTEXT@@K@Z; EtwpAllocateTraceHandle(ulong)
0x180007236  mov     [rsp+1170h+var_1138], rax
0x18000723b  mov     rcx, rax; struct _TRACELOG_CONTEXT *
0x18000723e  test    rax, rax
0x180007241  jnz     short loc_180007250
0x180007243  mov     [rsp+1170h+dwErrCode], 0Eh
0x18000724b  jmp     loc_180007481
0x180007250  mov     rax, [rax+10h]
0x180007254  mov     rdx, rbx; struct _EVENT_TRACE_LOGFILEW *
0x180007257  mov     [rsp+1170h+var_1128], rax
0x18000725c  call    ?EtwpCopyLogfileInfo@@YAKPEAU_TRACELOG_CONTEXT@@PEAU_EVENT_TRACE_LOGFILEW@@@Z; EtwpCopyLogfileInfo(_TRACELOG_CONTEXT *,_EVENT_TRACE_LOGFILEW *)
0x180007261  mov     [rsp+1170h+dwErrCode], eax
0x180007265  test    eax, eax
0x180007267  jnz     loc_18000747A
0x18000726d  test    dword ptr [rbx+1Ch], 1000h
0x180007274  jz      short loc_18000727F
0x180007276  mov     rax, [rsp+1170h+var_1138]
0x18000727b  or      dword ptr [rax+20h], 2
0x18000727f  mov     rax, [rsp+1170h+var_1138]
0x180007284  mov     ecx, 10000000h
0x180007289  test    [rbx+1Ch], ecx
0x18000728c  jz      short loc_18000729F
0x18000728e  or      [rax+20h], ecx
0x180007291  lea     rcx, ?EtwpMapEventToEventRecord@@YAKPEAU_TRACELOG_CONTEXT@@PEAXPEAU_ETW_EVENT_INFO@@KPEAU_WMI_BUFFER_HEADER@@@Z; EtwpMapEventToEventRecord(_TRACELOG_CONTEXT *,void *,_ETW_EVENT_INFO *,ulong,_WMI_BUFFER_HEADER *)
0x180007298  mov     rax, [rsp+1170h+var_1138]
0x18000729d  jmp     short loc_1800072A6
0x18000729f  lea     rcx, EtwpMapEventToEventTraceAdapter
0x1800072a6  mov     [rax+220h], rcx
0x1800072ad  mov     rax, [rsp+1170h+var_1138]
0x1800072b2  test    sil, sil
0x1800072b5  jz      loc_1800073BD
0x1800072bb  mov     byte ptr [rax+228h], 1
0x1800072c2  lea     rcx, [rbp+1070h+Properties]; struct _EVENT_TRACE_PROPERTIES *
0x1800072c6  mov     r8, [rsp+1170h+var_1138]
0x1800072cb  mov     edx, edi; unsigned int
0x1800072cd  add     r8, 0C8h; struct _TRACE_LOGFILE_HEADER *
0x1800072d4  call    ?EtwpGenerateLogHeaderForRealtime@@YAKPEAU_EVENT_TRACE_PROPERTIES@@KPEAU_TRACE_LOGFILE_HEADER@@@Z; EtwpGenerateLogHeaderForRealtime(_EVENT_TRACE_PROPERTIES *,ulong,_TRACE_LOGFILE_HEADER *)
0x1800072d9  mov     [rsp+1170h+dwErrCode], eax
0x1800072dd  test    eax, eax
0x1800072df  jnz     loc_18000747A
0x1800072e5  mov     rdx, [rsp+1170h+var_1138]
0x1800072ea  test    dword ptr [rdx+20h], 100h
0x1800072f1  jz      short loc_18000731C
0x1800072f3  lea     r9, [rdx+278h]; unsigned int *
0x1800072fa  mov     ecx, r14d; unsigned int
0x1800072fd  lea     r8, [rdx+280h]; struct _SYSTEM_TRACE_HEADER **
0x180007304  add     rdx, 0C8h; struct _TRACE_LOGFILE_HEADER *
0x18000730b  call    ?EtwpGenerateHeaderEventForRealtime@@YAKKPEAU_TRACE_LOGFILE_HEADER@@PEAPEAU_SYSTEM_TRACE_HEADER@@PEAK@Z; EtwpGenerateHeaderEventForRealtime(ulong,_TRACE_LOGFILE_HEADER *,_SYSTEM_TRACE_HEADER * *,ulong *)
0x180007310  mov     [rsp+1170h+dwErrCode], eax
0x180007314  test    eax, eax
0x180007316  jnz     loc_18000747A
0x18000731c  mov     eax, cs:dword_18001D1B4
0x180007322  mov     [rsp+1170h+var_1130], eax
0x180007326  cmp     eax, 0FFFFFFFFh
0x180007329  jnz     short loc_180007382
0x18000732b  xorps   xmm0, xmm0
0x18000732e  mov     [rsp+1170h+var_1120], r15d
0x180007333  lea     rdx, SourceString; "Kernel-ProductInfo"
0x18000733a  mov     [rsp+1170h+var_112C], r15d
0x18000733f  lea     rcx, [rsp+1170h+DestinationString]; DestinationString
0x180007344  movups  xmmword ptr [rsp+1170h+DestinationString.Length], xmm0
0x180007349  call    cs:__imp_RtlInitUnicodeString
0x18000734f  lea     rax, [rsp+1170h+var_112C]
0x180007354  mov     r9d, 4
0x18000735a  lea     r8, [rsp+1170h+var_1130]
0x18000735f  mov     [rsp+1170h+var_1150], rax
0x180007364  lea     rdx, [rsp+1170h+var_1120]
0x180007369  lea     rcx, [rsp+1170h+DestinationString]
0x18000736e  call    cs:__imp_NtQueryLicenseValue
0x180007374  test    eax, eax
0x180007376  js      short loc_1800073B6
0x180007378  mov     eax, [rsp+1170h+var_1130]
0x18000737c  mov     cs:dword_18001D1B4, eax
0x180007382  cmp     eax, 0C2h
0x180007387  jnz     short loc_1800073B6
0x180007389  test    dword ptr [rbx+1Ch], 8000000h
0x180007390  jz      short loc_1800073B6
0x180007392  mov     rax, [rsp+1170h+var_1138]
0x180007397  mov     ecx, [rbx+198h]
0x18000739d  mov     [rax+3A4h], ecx
0x1800073a3  mov     rax, [rsp+1170h+var_1138]
0x1800073a8  mov     rcx, [rbx+19Ch]
0x1800073af  mov     [rax+398h], rcx
0x1800073b6  mov     rcx, [rsp+1170h+var_1138]
0x1800073bb  jmp     short loc_1800073F9
0x1800073bd  mov     r8b, 1; unsigned __int8
0x1800073c0  mov     [rax+228h], r15b
0x1800073c7  mov     edx, 1; unsigned int
0x1800073cc  lea     rcx, [rsp+1170h+var_1138]; struct _TRACELOG_CONTEXT **
0x1800073d1  call    ?EtwpProcessLogHeader@@YAKPEAPEAU_TRACELOG_CONTEXT@@KE@Z; EtwpProcessLogHeader(_TRACELOG_CONTEXT * *,ulong,uchar)
0x1800073d6  mov     [rsp+1170h+dwErrCode], eax
0x1800073da  test    eax, eax
0x1800073dc  jnz     loc_18000747A
0x1800073e2  mov     rcx, [rsp+1170h+var_1138]
0x1800073e7  mov     eax, [rcx+200h]
0x1800073ed  mov     [rbx+1B0h], eax
0x1800073f3  mov     eax, [rcx+6Ch]
0x1800073f6  mov     [rbx+1Ch], eax
0x1800073f9  mov     r8d, 2
0x1800073ff  lea     rdx, [rbx+78h]
0x180007403  lea     rax, [rcx+0C8h]
0x18000740a  lea     r9d, [r8+7Eh]
0x18000740e  movups  xmm0, xmmword ptr [rax]
0x180007411  movups  xmmword ptr [rdx], xmm0
0x180007414  movups  xmm1, xmmword ptr [rax+10h]
0x180007418  movups  xmmword ptr [rdx+10h], xmm1
0x18000741c  movups  xmm0, xmmword ptr [rax+20h]
0x180007420  movups  xmmword ptr [rdx+20h], xmm0
0x180007424  movups  xmm1, xmmword ptr [rax+30h]
0x180007428  movups  xmmword ptr [rdx+30h], xmm1
0x18000742c  movups  xmm0, xmmword ptr [rax+40h]
0x180007430  movups  xmmword ptr [rdx+40h], xmm0
0x180007434  movups  xmm1, xmmword ptr [rax+50h]
0x180007438  movups  xmmword ptr [rdx+50h], xmm1
0x18000743c  movups  xmm0, xmmword ptr [rax+60h]
0x180007440  movups  xmmword ptr [rdx+60h], xmm0
0x180007444  movups  xmm1, xmmword ptr [rax+70h]
0x180007448  add     rax, r9
0x18000744b  movups  xmmword ptr [rdx+70h], xmm1
0x18000744f  add     rdx, r9
0x180007452  sub     r8, 1
0x180007456  jnz     short loc_18000740E
0x180007458  movups  xmm0, xmmword ptr [rax]
0x18000745b  movups  xmmword ptr [rdx], xmm0
0x18000745e  mov     rax, [rax+10h]
0x180007462  mov     [rdx+10h], rax
0x180007466  mov     eax, [rcx+278h]
0x18000746c  mov     [rbx+70h], eax
0x18000746f  mov     rax, [rcx+280h]
0x180007476  mov     [rbx+68h], rax
0x18000747a  cmp     [rsp+1170h+dwErrCode], r15d
0x18000747f  jz      short loc_18000749A
0x180007481  mov     rcx, [rsp+1170h+var_1128]; unsigned __int64
0x180007486  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000748a  jz      short loc_180007491
0x18000748c  call    ?EtwpFreeTraceHandle@@YAK_K@Z; EtwpFreeTraceHandle(unsigned __int64)
0x180007491  mov     [rsp+1170h+var_1128], 0FFFFFFFFFFFFFFFFh
0x18000749a  mov     ecx, [rsp+1170h+dwErrCode]; dwErrCode
0x18000749e  call    cs:__imp_SetLastError
0x1800074a4  mov     rbx, [rsp+1170h+var_1128]
0x1800074a9  lea     rcx, [rbp+1070h+var_60]
0x1800074b0  call    _lambda_672f30a2b4c3e78079b9ebb124984960___operator__
0x1800074b5  cmp     [rsp+1170h+var_1108], 1
0x1800074ba  jnz     short loc_1800074D5
0x1800074bc  lea     rdx, [rsp+1170h+ActivityId]
0x1800074c1  mov     [rsp+1170h+var_1108], 2
0x1800074c9  lea     rcx, dword_18001D020
0x1800074d0  call    ??$_tlgWriteActivityAutoStop@$0BA@$04@@YAXPEBU_tlgProvider_t@@PEBU_GUID@@@Z; _tlgWriteActivityAutoStop<16,5>(_tlgProvider_t const *,_GUID const *)
0x1800074d5  mov     rax, rbx
0x1800074d8  mov     rcx, [rbp+1070h+var_40]
0x1800074df  xor     rcx, rsp; StackCookie
0x1800074e2  call    __security_check_cookie
0x1800074e7  add     rsp, 1148h
0x1800074ee  pop     r15
0x1800074f0  pop     r14
0x1800074f2  pop     rdi
0x1800074f3  pop     rsi
0x1800074f4  pop     rbx
0x1800074f5  pop     rbp
0x1800074f6  retn
```
