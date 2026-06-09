# SxStartTracing(ushort const *,ushort const *,ulong,unsigned __int64 *,ushort * *)

- ea: `0x1800677b4`
- end: `0x180067a37`
- name: `?SxStartTracing@@YAJPEBG0KPEA_KPEAPEAG@Z`
- size: `643`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64 *, struct _EVENT_TRACE_PROPERTIES *Properties)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a4b0`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180011ac4`
- `0x180023708`
- `0x18002ce84`
- `0x180038c3c`
- `0x180066dfc`
- `0x180066fc8`
- `0x1800677b4`

## import_xrefs

- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18006795b`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18006795b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180067a07`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SxStartTracing(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int64 *a4,
        struct _EVENT_TRACE_PROPERTIES *Properties)
{
  struct _EVENT_TRACE_PROPERTIES *v7; // rbx
  __int16 v8; // ax
  bool v9; // sf
  int v10; // eax
  const unsigned __int16 *v11; // r8
  signed int started; // eax
  unsigned int v13; // ebx
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-50h] BYREF
  int v16; // [rsp+40h] [rbp-40h] BYREF
  int v17; // [rsp+44h] [rbp-3Ch]
  const unsigned __int16 *v18; // [rsp+A0h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+B0h] [rbp+30h] BYREF
  unsigned int v20; // [rsp+B8h] [rbp+38h] BYREF

  v19 = a3;
  v18 = a1;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "SxStartTracing", 0x214u, 1u);
  v7 = 0;
  v15[0] = (unsigned __int16 *)&qword_18006F470;
  Properties = 0;
  LODWORD(v18) = 0;
  v19 = 0;
  v20 = 0;
  v15[1] = 0;
  if ( !a4 )
  {
    v17 = 35979812;
    goto LABEL_24;
  }
  *a4 = -1;
  LOWORD(v17) = 549;
  if ( !a2 )
  {
    HIWORD(v17) = 550;
LABEL_24:
    v16 = -2147024809;
    goto LABEL_25;
  }
  v16 = 0;
  LOWORD(v17) = 550;
  v16 = SxGet0XLogFileCount(a2, (unsigned int *)&v18, &v19, &v20);
  v8 = 559;
  if ( v16 < 0 )
    goto LABEL_8;
  LOWORD(v17) = 559;
  if ( (_DWORD)v18 )
  {
    if ( !v19 )
    {
      v16 = CBsString::Format((CBsString *)v15, L"%s.0.1.%s", a2, L"etl");
      v9 = v16 < 0;
      v8 = 577;
      goto LABEL_12;
    }
    goto LABEL_21;
  }
  if ( v19 )
  {
LABEL_21:
    v16 = CBsString::Format((CBsString *)v15, L"%s.0.%d.%s", a2);
    v9 = v16 < 0;
    v8 = 572;
    goto LABEL_12;
  }
  v16 = CBsString::Format((CBsString *)v15, L"%s.0.%s", a2, L"etl");
  v9 = v16 < 0;
  v8 = 563;
LABEL_12:
  if ( !v9 )
  {
    LOWORD(v17) = v8;
    v10 = SxAllocateEventTraceProp(&Properties);
    v7 = Properties;
    v9 = v10 < 0;
    v16 = v10;
    v8 = 580;
    if ( !v9 )
    {
      v11 = v15[0];
      LOWORD(v17) = 580;
      Properties->LogFileMode = 2;
      v7->BufferSize = 64;
      v7->MinimumBuffers = 3;
      v7->MaximumBuffers = 6;
      v7->MaximumFileSize = 10;
      v7->FlushTimer = 15;
      v16 = StringCchCopyW((unsigned __int16 *)((char *)v7 + v7->LogFileNameOffset), 0x104u, v11);
      v8 = 588;
      if ( v16 >= 0 )
      {
        LOWORD(v17) = 588;
        started = StartTraceW(a4, L"BuiltInDefragTracing", v7);
        if ( started == 183 )
          goto LABEL_25;
        if ( started > 0 )
          started = (unsigned __int16)started | 0x80070000;
        v16 = started;
        v9 = started < 0;
        v8 = 594;
        if ( !v9 )
        {
          LOWORD(v17) = 594;
          goto LABEL_25;
        }
      }
    }
  }
LABEL_8:
  HIWORD(v17) = v8;
LABEL_25:
  CoTaskMemFree(v7);
  v13 = v16;
  CBsString::_Release((CBsString *)v15);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v13;
}

```

## disassembly

```asm
0x1800677b4  mov     [rsp-18h+arg_8], rbx
0x1800677b9  mov     [rsp-18h+arg_10], r8d
0x1800677be  mov     [rsp-18h+arg_0], rcx
0x1800677c3  push    rbp
0x1800677c4  push    rsi
0x1800677c5  push    rdi
0x1800677c6  mov     rbp, rsp
0x1800677c9  sub     rsp, 80h
0x1800677d0  mov     rsi, r9
0x1800677d3  mov     rdi, rdx
0x1800677d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800677dd  lea     rax, WPP_GLOBAL_Control
0x1800677e4  cmp     rcx, rax
0x1800677e7  jz      short loc_180067807
0x1800677e9  test    dword ptr [rcx+1Ch], 20000000h
0x1800677f0  jz      short loc_180067807
0x1800677f2  mov     rcx, [rcx+10h]
0x1800677f6  lea     r8, WPP_864f1fbbf0f13efebf2774ab68c23e38_Traceguids
0x1800677fd  mov     edx, 15h
0x180067802  call    WPP_SF_
0x180067807  mov     r9d, 1; unsigned __int16
0x18006780d  lea     rdx, aSxstarttracing; "SxStartTracing"
0x180067814  mov     r8d, 214h; unsigned __int16
0x18006781a  lea     rcx, [rbp+var_40]; this
0x18006781e  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180067823  xor     ebx, ebx
0x180067825  lea     rax, qword_18006F470
0x18006782c  mov     [rbp+var_50], rax
0x180067830  mov     [rbp+Properties], rbx
0x180067834  mov     dword ptr [rbp+arg_0], ebx
0x180067837  mov     [rbp+arg_10], ebx
0x18006783a  mov     [rbp+arg_18], ebx
0x18006783d  mov     [rbp+var_48], rbx
0x180067841  test    rsi, rsi
0x180067844  jz      loc_1800679F6
0x18006784a  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180067851  mov     eax, 225h
0x180067856  mov     word ptr [rbp+var_3C], ax
0x18006785a  mov     eax, 226h
0x18006785f  test    rdi, rdi
0x180067862  jnz     short loc_18006786D
0x180067864  mov     word ptr [rbp+var_3C+2], ax
0x180067868  jmp     loc_1800679FD
0x18006786d  lea     r9, [rbp+arg_18]; unsigned int *
0x180067871  mov     [rbp+var_40], ebx
0x180067874  lea     r8, [rbp+arg_10]; unsigned int *
0x180067878  mov     word ptr [rbp+var_3C], ax
0x18006787c  lea     rdx, [rbp+arg_0]; unsigned int *
0x180067880  mov     rcx, rdi; unsigned __int16 *
0x180067883  call    ?SxGet0XLogFileCount@@YAJPEBGPEAK11@Z; SxGet0XLogFileCount(ushort const *,ulong *,ulong *,ulong *)
0x180067888  mov     [rbp+var_40], eax
0x18006788b  test    eax, eax
0x18006788d  mov     eax, 22Fh
0x180067892  jns     short loc_18006789D
0x180067894  mov     word ptr [rbp+var_3C+2], ax
0x180067898  jmp     loc_180067A04
0x18006789d  mov     word ptr [rbp+var_3C], ax
0x1800678a1  mov     eax, [rbp+arg_10]
0x1800678a4  cmp     dword ptr [rbp+arg_0], ebx
0x1800678a7  jnz     loc_18006798E
0x1800678ad  test    eax, eax
0x1800678af  jnz     loc_180067992
0x1800678b5  lea     r9, aEtl; "etl"
0x1800678bc  mov     r8, rdi
0x1800678bf  lea     rdx, aS0S; "%s.0.%s"
0x1800678c6  lea     rcx, [rbp+var_50]; this
0x1800678ca  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800678cf  mov     [rbp+var_40], eax
0x1800678d2  test    eax, eax
0x1800678d4  mov     eax, 233h
0x1800678d9  js      short loc_180067894
0x1800678db  lea     rcx, [rbp+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800678df  mov     word ptr [rbp+var_3C], ax
0x1800678e3  call    ?SxAllocateEventTraceProp@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; SxAllocateEventTraceProp(_EVENT_TRACE_PROPERTIES * *)
0x1800678e8  mov     rbx, [rbp+Properties]
0x1800678ec  test    eax, eax
0x1800678ee  mov     [rbp+var_40], eax
0x1800678f1  mov     eax, 244h
0x1800678f6  js      short loc_180067894
0x1800678f8  mov     r8, [rbp+var_50]; unsigned __int16 *
0x1800678fc  mov     edx, 104h; unsigned __int64
0x180067901  mov     word ptr [rbp+var_3C], ax
0x180067905  mov     dword ptr [rbx+40h], 2
0x18006790c  mov     dword ptr [rbx+30h], 40h ; '@'
0x180067913  mov     dword ptr [rbx+34h], 3
0x18006791a  mov     dword ptr [rbx+38h], 6
0x180067921  mov     dword ptr [rbx+3Ch], 0Ah
0x180067928  mov     dword ptr [rbx+44h], 0Fh
0x18006792f  mov     ecx, [rbx+70h]
0x180067932  add     rcx, rbx; unsigned __int16 *
0x180067935  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006793a  mov     [rbp+var_40], eax
0x18006793d  test    eax, eax
0x18006793f  mov     eax, 24Ch
0x180067944  js      loc_180067894
0x18006794a  mov     r8, rbx; Properties
0x18006794d  mov     word ptr [rbp+var_3C], ax
0x180067951  lea     rdx, InstanceName; "BuiltInDefragTracing"
0x180067958  mov     rcx, rsi; TraceHandle
0x18006795b  call    cs:__imp_StartTraceW
0x180067961  cmp     eax, 0B7h
0x180067966  jz      loc_180067A04
0x18006796c  test    eax, eax
0x18006796e  jle     short loc_180067978
0x180067970  movzx   eax, ax
0x180067973  or      eax, 80070000h
0x180067978  mov     [rbp+var_40], eax
0x18006797b  test    eax, eax
0x18006797d  mov     eax, 252h
0x180067982  js      loc_180067894
0x180067988  mov     word ptr [rbp+var_3C], ax
0x18006798c  jmp     short loc_180067A04
0x18006798e  test    eax, eax
0x180067990  jz      short loc_1800679CD
0x180067992  mov     r9d, [rbp+arg_18]
0x180067996  cmp     r9d, 7
0x18006799a  jnb     short loc_18006799F
0x18006799c  inc     r9d
0x18006799f  lea     rax, aEtl; "etl"
0x1800679a6  mov     r8, rdi
0x1800679a9  lea     rdx, aS0DS; "%s.0.%d.%s"
0x1800679b0  mov     [rsp+80h+var_60], rax
0x1800679b5  lea     rcx, [rbp+var_50]; this
0x1800679b9  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800679be  mov     [rbp+var_40], eax
0x1800679c1  test    eax, eax
0x1800679c3  mov     eax, 23Ch
0x1800679c8  jmp     loc_1800678D9
0x1800679cd  lea     r9, aEtl; "etl"
0x1800679d4  mov     r8, rdi
0x1800679d7  lea     rdx, aS01S; "%s.0.1.%s"
0x1800679de  lea     rcx, [rbp+var_50]; this
0x1800679e2  call    ?Format@CBsString@@QEAAJPEBGZZ; CBsString::Format(ushort const *,...)
0x1800679e7  mov     [rbp+var_40], eax
0x1800679ea  test    eax, eax
0x1800679ec  mov     eax, 241h
0x1800679f1  jmp     loc_1800678D9
0x1800679f6  mov     [rbp+var_3C], 2250224h
0x1800679fd  mov     [rbp+var_40], 80070057h
0x180067a04  mov     rcx, rbx; pv
0x180067a07  call    cs:__imp_CoTaskMemFree
0x180067a0d  mov     ebx, [rbp+var_40]
0x180067a10  lea     rcx, [rbp+var_50]; this
0x180067a14  call    ?_Release@CBsString@@AEAAXXZ; CBsString::_Release(void)
0x180067a19  lea     rcx, [rbp+var_40]; this
0x180067a1d  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180067a22  mov     eax, ebx
0x180067a24  mov     rbx, [rsp+80h+arg_8]
0x180067a2c  add     rsp, 80h
0x180067a33  pop     rdi
0x180067a34  pop     rsi
0x180067a35  pop     rbp
0x180067a36  retn
```
