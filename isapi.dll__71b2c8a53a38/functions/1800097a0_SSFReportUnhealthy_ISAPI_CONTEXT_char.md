# SSFReportUnhealthy(ISAPI_CONTEXT *,char *)

- ea: `0x1800097a0`
- end: `0x180009977`
- name: `?SSFReportUnhealthy@@YAJPEAVISAPI_CONTEXT@@PEAD@Z`
- size: `471`
- prototype: `__int64 __fastcall(struct ISAPI_CONTEXT *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ef0`

## callees

- `0x1800097a0`
- `0x180012482`
- `0x1800124c0`
- `0x180013010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180009858`
- `iisutil!PuDbgPrint` at `0x180009938`
- `iisutil!PuDbgPrint` at `0x180009858`
- `iisutil!PuDbgPrint` at `0x180009938`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009892`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009943`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009892`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009943`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098c6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800098c6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800097f9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800097f9`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180009881`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180009881`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000989f`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000989f`

## string_xrefs

- `0x180009846`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`
- `0x18000991a`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\server_support.cxx`

## pseudocode

```c
__int64 __fastcall SSFReportUnhealthy(struct ISAPI_CONTEXT *a1, char *a2)
{
  __int64 v4; // r14
  __int64 v5; // r15
  __int64 v6; // rbx
  unsigned int v7; // edi
  int v8; // edi
  unsigned int v10; // ebx
  __int64 (__fastcall *v11)(__int64, __int64, _QWORD, unsigned __int16 *, unsigned int); // rbp
  unsigned __int16 *Str; // rax
  int v13; // eax
  unsigned int v14; // ebx
  _BYTE v15[64]; // [rsp+40h] [rbp-478h] BYREF
  unsigned __int16 v16[512]; // [rsp+80h] [rbp-438h] BYREF

  memset_0(v16, 0, sizeof(v16));
  STRU::STRU((STRU *)v15, v16, 0x200u);
  v4 = *((_QWORD *)a1 + 24);
  v5 = *(_QWORD *)(*((_QWORD *)a1 + 25) + 24LL);
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x4000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3728,
      "SSFReportUnhealthy",
      "\r\n  HSE_REQ_REPORT_UNHEALTHY[%p]: Function Entry\r\n    Reason: '%s'\r\n  <END>\r\n\r\n",
      a1,
      a2);
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(v5 + 2 * v6) );
  if ( a2 )
  {
    v8 = STRU::CopyA((STRU *)v15, a2);
    if ( v8 < 0 )
    {
      STRU::~STRU((STRU *)v15);
      return (unsigned int)v8;
    }
    v7 = 2 * STRU::QueryCCH((STRU *)v15) + 2;
  }
  else
  {
    v7 = 0;
  }
  v10 = 2 * v6 + 2;
  v11 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned __int16 *, unsigned int))(*(_QWORD *)v4 + 152LL);
  if ( v7 )
    Str = STRU::QueryStr((STRU *)v15);
  else
    Str = 0;
  v13 = v11(v4, v5, v10, Str, v7);
  v14 = v13;
  if ( v13 < 0 && (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x100000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\server_support.cxx",
      3771,
      "SSFReportUnhealthy",
      "\r\n  HSE_REQ_REPORT_UNHEALTHY[%p]: Failed\r\n    Error: 0x%08x\r\n  <END>\r\n\r\n",
      a1,
      v13);
  STRU::~STRU((STRU *)v15);
  return v14;
}

```

## disassembly

```asm
0x1800097a0  mov     [rsp+arg_10], rbx
0x1800097a5  mov     [rsp+arg_18], rbp
0x1800097aa  push    rsi
0x1800097ab  push    rdi
0x1800097ac  push    r12
0x1800097ae  push    r14
0x1800097b0  push    r15
0x1800097b2  sub     rsp, 490h
0x1800097b9  mov     rax, cs:__security_cookie
0x1800097c0  xor     rax, rsp
0x1800097c3  mov     [rsp+4B8h+var_38], rax
0x1800097cb  mov     rdi, rdx
0x1800097ce  mov     rsi, rcx
0x1800097d1  xor     edx, edx; Val
0x1800097d3  lea     rcx, [rsp+4B8h+var_438]; void *
0x1800097db  mov     r8d, 400h; Size
0x1800097e1  call    memset_0
0x1800097e6  mov     r8d, 200h
0x1800097ec  lea     rdx, [rsp+4B8h+var_438]
0x1800097f4  lea     rcx, [rsp+4B8h+var_478]
0x1800097f9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800097ff  mov     rax, [rsi+0C8h]
0x180009806  mov     r14, [rsi+0C0h]
0x18000980d  mov     r15, [rax+18h]
0x180009811  mov     eax, cs:g_dwDebugFlags
0x180009817  test    al, 3
0x180009819  setnz   cl
0x18000981c  bt      eax, 1Ah
0x180009820  setb    al
0x180009823  test    al, cl
0x180009825  jz      short loc_18000985E
0x180009827  mov     rcx, cs:g_pDebug
0x18000982e  lea     rax, aHseReqReportUn_1; "\r\n  HSE_REQ_REPORT_UNHEALTHY[%p]: Fun"...
0x180009835  mov     [rsp+4B8h+var_488], rdi
0x18000983a  lea     r9, aSsfreportunhea; "SSFReportUnhealthy"
0x180009841  mov     [rsp+4B8h+var_490], rsi
0x180009846  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000984d  mov     r8d, 0E90h
0x180009853  mov     [rsp+4B8h+var_498], rax
0x180009858  call    cs:__imp_PuDbgPrint
0x18000985e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009862  xor     r12d, r12d
0x180009865  inc     rbx
0x180009868  cmp     [r15+rbx*2], r12w
0x18000986d  jnz     short loc_180009865
0x18000986f  test    rdi, rdi
0x180009872  jnz     short loc_180009879
0x180009874  mov     edi, r12d
0x180009877  jmp     short loc_1800098AC
0x180009879  mov     rdx, rdi
0x18000987c  lea     rcx, [rsp+4B8h+var_478]
0x180009881  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180009887  lea     rcx, [rsp+4B8h+var_478]
0x18000988c  mov     edi, eax
0x18000988e  test    eax, eax
0x180009890  jns     short loc_18000989F
0x180009892  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009898  mov     eax, edi
0x18000989a  jmp     loc_18000994B
0x18000989f  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x1800098a5  lea     edi, ds:2[rax*2]
0x1800098ac  mov     rax, [r14]
0x1800098af  lea     ebx, ds:2[rbx*2]
0x1800098b6  mov     rbp, [rax+98h]
0x1800098bd  test    edi, edi
0x1800098bf  jz      short loc_1800098CE
0x1800098c1  lea     rcx, [rsp+4B8h+var_478]
0x1800098c6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800098cc  jmp     short loc_1800098D1
0x1800098ce  mov     rax, r12
0x1800098d1  mov     r9, rax
0x1800098d4  mov     dword ptr [rsp+4B8h+var_498], edi
0x1800098d8  mov     rax, rbp
0x1800098db  mov     r8d, ebx
0x1800098de  mov     rdx, r15
0x1800098e1  mov     rcx, r14
0x1800098e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098e9  mov     ebx, eax
0x1800098eb  test    eax, eax
0x1800098ed  jns     short loc_18000993E
0x1800098ef  mov     ecx, cs:g_dwDebugFlags
0x1800098f5  test    cl, 3
0x1800098f8  setnz   r8b
0x1800098fc  bt      ecx, 14h
0x180009900  setb    cl
0x180009903  test    cl, r8b
0x180009906  jz      short loc_18000993E
0x180009908  mov     rcx, cs:g_pDebug
0x18000990f  lea     r9, aSsfreportunhea; "SSFReportUnhealthy"
0x180009916  mov     dword ptr [rsp+4B8h+var_488], eax
0x18000991a  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180009921  lea     rax, aHseReqReportUn; "\r\n  HSE_REQ_REPORT_UNHEALTHY[%p]: Fai"...
0x180009928  mov     [rsp+4B8h+var_490], rsi
0x18000992d  mov     r8d, 0EBBh
0x180009933  mov     [rsp+4B8h+var_498], rax
0x180009938  call    cs:__imp_PuDbgPrint
0x18000993e  lea     rcx, [rsp+4B8h+var_478]
0x180009943  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009949  mov     eax, ebx
0x18000994b  mov     rcx, [rsp+4B8h+var_38]
0x180009953  xor     rcx, rsp; StackCookie
0x180009956  call    __security_check_cookie
0x18000995b  lea     r11, [rsp+4B8h+var_28]
0x180009963  mov     rbx, [r11+40h]
0x180009967  mov     rbp, [r11+48h]
0x18000996b  mov     rsp, r11
0x18000996e  pop     r15
0x180009970  pop     r14
0x180009972  pop     r12
0x180009974  pop     rdi
0x180009975  pop     rsi
0x180009976  retn
```
