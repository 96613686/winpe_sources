# XPerfCore::CEtwTrace::CEtwTrace(XPerfCore::CEtwTraceGroup *,ushort const *)

- ea: `0x18002c4e0`
- end: `0x18002c771`
- name: `??0CEtwTrace@XPerfCore@@QEAA@PEAVCEtwTraceGroup@1@PEBG@Z`
- size: `657`
- prototype: `_QWORD(XPerfCore::CEtwTrace *__hidden this, struct XPerfCore::CEtwTraceGroup *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18005c98c`

## callees

- `0x18002c4e0`
- `0x1800397f0`
- `0x180039bbc`
- `0x1800cf032`
- `0x1800cf080`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18002c585`
- `msvcrt!_wcsdup` at `0x18002c585`
- `msvcrt!free` at `0x18002c73a`
- `msvcrt!free` at `0x18002c73a`
- `ADVAPI32!OpenTraceW` at `0x18002c5fc`
- `ADVAPI32!OpenTraceW` at `0x18002c5fc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
XPerfCore::CEtwTrace *__fastcall XPerfCore::CEtwTrace::CEtwTrace(
        XPerfCore::CEtwTrace *this,
        struct XPerfCore::CEtwTraceGroup *a2,
        const unsigned __int16 *a3)
{
  char v4; // si
  WCHAR *v5; // rdi
  __int64 v6; // rdi
  TRACEHANDLE v7; // rax
  _OWORD *v8; // rcx
  TRACE_LOGFILE_HEADER *p_LogfileHeader; // rax
  __int64 v10; // rcx
  int v11; // eax
  bool v12; // zf
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+30h] [rbp-1E8h] BYREF

  *((_BYTE *)this + 296) = 0;
  v4 = 1;
  *((_BYTE *)this + 312) = 1;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 50) = a2;
  *((_QWORD *)this + 51) = &XPerfCore::CDefaultTarget::Instance;
  *((_QWORD *)this + 52) = wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
  *((_QWORD *)this + 53) = &XPerfCore::CDefaultTarget::Instance;
  *((_QWORD *)this + 54) = WdiGetDiagnosticModuleInterfaceVersion;
  if ( !a3 )
    ATL::AtlThrowImpl(-2147024809);
  v5 = _wcsdup(a3);
  *(_QWORD *)this = v5;
  if ( !v5 )
    ATL::AtlThrowImpl(-2147024882);
  memset_0(&Logfile, 0, sizeof(Logfile));
  Logfile.LogFileName = v5;
  Logfile.LogFileMode = 0x10000000;
  v6 = 2;
  Logfile.LogfileHeader.ReservedFlags = 2;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)XPerfCore::CEtwTrace::BufferCallback;
  Logfile.EventCallback = (PEVENT_CALLBACK)XPerfCore::CEtwTrace::EventRecordCallback;
  Logfile.Context = this;
  v7 = OpenTraceW(&Logfile);
  *((_QWORD *)this + 1) = v7;
  if ( v7 == -1 )
    ATL::AtlThrowLastWin32();
  v8 = (_OWORD *)((char *)this + 16);
  p_LogfileHeader = &Logfile.LogfileHeader;
  do
  {
    *v8 = *(_OWORD *)&p_LogfileHeader->BufferSize;
    v8[1] = *(_OWORD *)&p_LogfileHeader->EndTime.LowPart;
    v8[2] = *(_OWORD *)&p_LogfileHeader->LogFileMode;
    v8[3] = *(_OWORD *)&p_LogfileHeader->EventsLost;
    v8[4] = *(_OWORD *)&p_LogfileHeader->LogFileName;
    v8[5] = *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[2];
    v8[6] = *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[10];
    v8[7] = *(_OWORD *)&p_LogfileHeader->TimeZone.StandardName[18];
    v8 += 8;
    p_LogfileHeader = (TRACE_LOGFILE_HEADER *)((char *)p_LogfileHeader + 128);
    --v6;
  }
  while ( v6 );
  *v8 = *(_OWORD *)&p_LogfileHeader->BufferSize;
  *((_QWORD *)v8 + 2) = p_LogfileHeader->EndTime.QuadPart;
  v10 = *((_QWORD *)this + 35);
  *(_QWORD *)((char *)this + 316) = v10;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 44) = 0;
  if ( *((_QWORD *)this + 4) - v10 <= 0 )
  {
    *((_QWORD *)this + 43) = 0;
    *((_QWORD *)this + 4) = v10;
  }
  else
  {
    *((_QWORD *)this + 43) = 100 * (*((_QWORD *)this + 4) - v10);
  }
  v11 = *((_DWORD *)this + 5);
  if ( (unsigned __int8)v11 < 6u || (_WORD)v11 == 6 && *((_WORD *)this + 12) <= 0x13BAu )
    v4 = 0;
  *((_BYTE *)this + 296) = v4;
  if ( ((*((_DWORD *)this + 15) - 4) & 0xFFFFFFFB) != 0 || !*((_DWORD *)this + 7) )
    goto LABEL_26;
  if ( *((_DWORD *)this + 72) == 1 )
  {
    v12 = *((_QWORD *)this + 34) == 0;
    goto LABEL_24;
  }
  if ( *((_DWORD *)this + 72) != 2 )
  {
    if ( *((_DWORD *)this + 72) != 3 )
      ATL::AtlThrowImpl(-2147418113);
    v12 = *((_DWORD *)this + 17) == 0;
LABEL_24:
    if ( !v12 )
      goto LABEL_25;
LABEL_26:
    ATL::AtlThrowImpl(-2147023504);
  }
LABEL_25:
  free(0);
  return this;
}

```

## disassembly

```asm
0x18002c4e0  mov     [rsp+arg_8], rbx
0x18002c4e5  push    rbp
0x18002c4e6  push    rsi
0x18002c4e7  push    rdi
0x18002c4e8  sub     rsp, 200h
0x18002c4ef  mov     rax, cs:__security_cookie
0x18002c4f6  xor     rax, rsp
0x18002c4f9  mov     [rsp+218h+var_28], rax
0x18002c501  mov     rbx, rcx
0x18002c504  xor     ebp, ebp
0x18002c506  mov     [rcx+128h], bpl
0x18002c50d  mov     sil, 1
0x18002c510  mov     [rcx+138h], sil
0x18002c517  mov     [rcx+148h], rbp
0x18002c51e  mov     [rcx+150h], rbp
0x18002c525  mov     [rcx+158h], rbp
0x18002c52c  mov     [rcx+160h], rbp
0x18002c533  mov     [rcx+168h], rbp
0x18002c53a  mov     [rcx+190h], rdx
0x18002c541  lea     rcx, ?Instance@CDefaultTarget@XPerfCore@@0V12@A; XPerfCore::CDefaultTarget XPerfCore::CDefaultTarget::Instance
0x18002c548  mov     [rbx+198h], rcx
0x18002c54f  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18002c556  mov     [rbx+1A0h], rax
0x18002c55d  mov     [rbx+1A8h], rcx
0x18002c564  lea     rax, WdiGetDiagnosticModuleInterfaceVersion
0x18002c56b  mov     [rbx+1B0h], rax
0x18002c572  test    r8, r8
0x18002c575  jnz     short loc_18002C582
0x18002c577  mov     ecx, 80070057h; int
0x18002c57c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c582  mov     rcx, r8; String
0x18002c585  call    cs:__imp__wcsdup
0x18002c58b  mov     rdi, rax
0x18002c58e  mov     [rbx], rax
0x18002c591  test    rax, rax
0x18002c594  jnz     short loc_18002C5A1
0x18002c596  mov     ecx, 8007000Eh; int
0x18002c59b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c5a1  mov     [rsp+218h+var_1F0], rdi
0x18002c5a6  xor     edx, edx; Val
0x18002c5a8  mov     r8d, 1C0h; Size
0x18002c5ae  lea     rcx, [rsp+218h+Logfile]; void *
0x18002c5b3  call    memset_0
0x18002c5b8  mov     [rsp+218h+Logfile.LogFileName], rdi
0x18002c5bd  mov     dword ptr [rsp+218h+Logfile.1Ch], 10000000h
0x18002c5c5  mov     edi, 2
0x18002c5ca  mov     [rsp+218h+Logfile.LogfileHeader.ReservedFlags], edi
0x18002c5d1  lea     rax, ?BufferCallback@CEtwTrace@XPerfCore@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; XPerfCore::CEtwTrace::BufferCallback(_EVENT_TRACE_LOGFILEW *)
0x18002c5d8  mov     [rsp+218h+Logfile.BufferCallback], rax
0x18002c5e0  lea     rax, ?EventRecordCallback@CEtwTrace@XPerfCore@@CAXPEAU_EVENT_RECORD@@@Z; XPerfCore::CEtwTrace::EventRecordCallback(_EVENT_RECORD *)
0x18002c5e7  mov     qword ptr [rsp+218h+Logfile.1A8h], rax
0x18002c5ef  mov     [rsp+218h+Logfile.Context], rbx
0x18002c5f7  lea     rcx, [rsp+218h+Logfile]; Logfile
0x18002c5fc  call    cs:__imp_OpenTraceW
0x18002c602  mov     [rbx+8], rax
0x18002c606  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c60a  jnz     short loc_18002C612
0x18002c60c  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18002c612  lea     rcx, [rbx+10h]
0x18002c616  lea     rax, [rsp+218h+Logfile.LogfileHeader]
0x18002c61e  mov     edx, 80h
0x18002c623  movups  xmm0, xmmword ptr [rax]
0x18002c626  movups  xmmword ptr [rcx], xmm0
0x18002c629  movups  xmm1, xmmword ptr [rax+10h]
0x18002c62d  movups  xmmword ptr [rcx+10h], xmm1
0x18002c631  movups  xmm0, xmmword ptr [rax+20h]
0x18002c635  movups  xmmword ptr [rcx+20h], xmm0
0x18002c639  movups  xmm1, xmmword ptr [rax+30h]
0x18002c63d  movups  xmmword ptr [rcx+30h], xmm1
0x18002c641  movups  xmm0, xmmword ptr [rax+40h]
0x18002c645  movups  xmmword ptr [rcx+40h], xmm0
0x18002c649  movups  xmm1, xmmword ptr [rax+50h]
0x18002c64d  movups  xmmword ptr [rcx+50h], xmm1
0x18002c651  movups  xmm0, xmmword ptr [rax+60h]
0x18002c655  movups  xmmword ptr [rcx+60h], xmm0
0x18002c659  movups  xmm1, xmmword ptr [rax+70h]
0x18002c65d  movups  xmmword ptr [rcx+70h], xmm1
0x18002c661  add     rcx, rdx
0x18002c664  add     rax, rdx
0x18002c667  sub     rdi, 1
0x18002c66b  jnz     short loc_18002C623
0x18002c66d  movups  xmm0, xmmword ptr [rax]
0x18002c670  movups  xmmword ptr [rcx], xmm0
0x18002c673  mov     rax, [rax+10h]
0x18002c677  mov     [rcx+10h], rax
0x18002c67b  mov     rcx, [rbx+118h]
0x18002c682  mov     rax, rcx
0x18002c685  shr     rax, 20h
0x18002c689  mov     dword ptr [rsp+218h+var_1F8], ecx
0x18002c68d  mov     dword ptr [rsp+218h+var_1F8+4], eax
0x18002c691  mov     rax, [rsp+218h+var_1F8]
0x18002c696  mov     [rbx+13Ch], rax
0x18002c69d  mov     [rbx+148h], rbp
0x18002c6a4  mov     [rbx+150h], rbp
0x18002c6ab  mov     [rbx+160h], rbp
0x18002c6b2  mov     rax, [rbx+20h]
0x18002c6b6  sub     rax, rcx
0x18002c6b9  test    rax, rax
0x18002c6bc  jle     short loc_18002C6CB
0x18002c6be  imul    rax, 64h ; 'd'
0x18002c6c2  mov     [rbx+158h], rax
0x18002c6c9  jmp     short loc_18002C6D6
0x18002c6cb  mov     [rbx+158h], rbp
0x18002c6d2  mov     [rbx+20h], rcx
0x18002c6d6  mov     eax, [rbx+14h]
0x18002c6d9  cmp     al, 6
0x18002c6db  jb      short loc_18002C6EE
0x18002c6dd  jnz     short loc_18002C6F1
0x18002c6df  shr     eax, 8
0x18002c6e2  test    al, al
0x18002c6e4  jnz     short loc_18002C6F1
0x18002c6e6  cmp     word ptr [rbx+18h], 13BAh
0x18002c6ec  ja      short loc_18002C6F1
0x18002c6ee  mov     sil, bpl
0x18002c6f1  mov     [rbx+128h], sil
0x18002c6f8  mov     eax, [rbx+3Ch]
0x18002c6fb  sub     eax, 4
0x18002c6fe  test    eax, 0FFFFFFFBh
0x18002c703  jnz     short loc_18002C766
0x18002c705  cmp     [rbx+1Ch], ebp
0x18002c708  jz      short loc_18002C766
0x18002c70a  mov     ecx, [rbx+120h]
0x18002c710  sub     ecx, 1
0x18002c713  jz      short loc_18002C72F
0x18002c715  sub     ecx, 1
0x18002c718  jz      short loc_18002C738
0x18002c71a  cmp     ecx, 1
0x18002c71d  jz      short loc_18002C72A
0x18002c71f  mov     ecx, 8000FFFFh; int
0x18002c724  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002c72a  cmp     [rbx+44h], ebp
0x18002c72d  jmp     short loc_18002C736
0x18002c72f  cmp     [rbx+110h], rbp
0x18002c736  jz      short loc_18002C766
0x18002c738  xor     ecx, ecx; Block
0x18002c73a  call    cs:__imp_free
0x18002c740  mov     rax, rbx
0x18002c743  mov     rcx, [rsp+218h+var_28]
0x18002c74b  xor     rcx, rsp; StackCookie
0x18002c74e  call    __security_check_cookie
0x18002c753  mov     rbx, [rsp+218h+arg_8]
0x18002c75b  add     rsp, 200h
0x18002c762  pop     rdi
0x18002c763  pop     rsi
0x18002c764  pop     rbp
0x18002c765  retn
0x18002c766  mov     ecx, 80070570h; int
0x18002c76b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
