# Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor(Rdp::Avenc::IGpuFrameProcessor * *,IPropertyStore *)

- ea: `0x1800621f0`
- end: `0x1800624b4`
- name: `?CreateGpuFrameProcessor@CYuvMonitorContext@Yuv@Avenc@Rdp@@UEAAJPEAPEAUIGpuFrameProcessor@34@PEAUIPropertyStore@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvMonitorContext *__hidden this, struct Rdp::Avenc::IGpuFrameProcessor **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000406c`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x1800153f8`
- `0x180061c28`
- `0x1800621f0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006246e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006246e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006240c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006240c`

## string_xrefs

- `0x1800622d5`: `Create Gpu Yuv frame processor`
- `0x1800623ef`: `CreateGpuYuvFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x1800622e4`: `Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor`
- `0x1800623e8`: `Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor(
        Rdp::Avenc::Yuv::CYuvMonitorContext *this,
        struct Rdp::Avenc::IGpuFrameProcessor **a2,
        struct IPropertyStore *a3)
{
  __int64 v4; // rax
  int v5; // r8d
  int v6; // r9d
  struct Rdp::Avenc::IGpuFrameProcessor *v7; // r12
  char *v8; // rcx
  __int64 v9; // rbx
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-B8h]
  bool v13[8]; // [rsp+28h] [rbp-B0h]
  const char *v14; // [rsp+30h] [rbp-A8h]
  __int64 v15; // [rsp+30h] [rbp-A8h]
  __int64 v16; // [rsp+38h] [rbp-A0h]
  __int64 v17; // [rsp+40h] [rbp-98h]
  __int64 v18; // [rsp+48h] [rbp-90h]
  __int64 v19; // [rsp+50h] [rbp-88h]
  int v20; // [rsp+80h] [rbp-58h] BYREF
  int v21; // [rsp+84h] [rbp-54h] BYREF
  char *v22; // [rsp+88h] [rbp-50h] BYREF
  const char *v23; // [rsp+90h] [rbp-48h] BYREF
  const char *v24; // [rsp+98h] [rbp-40h] BYREF
  _QWORD v25[2]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  Rdp::Avenc::Yuv::CGpuYuvFrameProcessor *v28; // [rsp+F8h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
        (const char *)0x80004003LL,
        v12);
    LOBYTE(v12) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
      (const char *)0x8000FFFFLL,
      v12,
      (bool)"Monitor context is not started",
      v14);
    v28 = (Rdp::Avenc::Yuv::CGpuYuvFrameProcessor *)operator new(0xA0u);
    v4 = Rdp::Avenc::Yuv::CGpuYuvFrameProcessor::CGpuYuvFrameProcessor(
           v28,
           (Rdp::Avenc::Yuv::CYuvMonitorContext *)((char *)this - 80));
    v7 = (struct Rdp::Avenc::IGpuFrameProcessor *)v4;
    v25[1] = v4;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v22 = (char *)this + 40;
      LODWORD(v28) = *(_DWORD *)(*((_QWORD *)this + 4) + 152LL);
      v20 = *((_DWORD *)this + 14);
      v23 = "Create Gpu Yuv frame processor";
      v24 = "Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor";
      v21 = 116;
      v25[0] = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)word_1800B4C8A,
        v5,
        v6,
        (__int64)v25,
        (__int64)&v21,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v28,
        (__int64)&v22);
    }
    LODWORD(v19) = *((unsigned __int8 *)this + 50);
    LODWORD(v18) = *((unsigned __int8 *)this + 49);
    LODWORD(v17) = *((unsigned __int8 *)this + 48);
    LODWORD(v16) = *((unsigned __int16 *)this + 23);
    LODWORD(v15) = *((unsigned __int16 *)this + 22);
    *(_DWORD *)v13 = *((_DWORD *)this + 10);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"CreateGpuYuvFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Yuv::CYuvMonitorContext::CreateGpuFrameProcessor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
      0x76u,
      *(_QWORD *)v13,
      v15,
      v16,
      v17,
      v18,
      v19,
      *((unsigned __int8 *)this + 51),
      *((unsigned __int8 *)this + 52),
      *((unsigned __int8 *)this + 53),
      *((unsigned __int8 *)this + 54),
      *((unsigned __int8 *)this + 55));
    AcquireSRWLockExclusive((PSRWLOCK)this + 16);
    if ( v7 )
      v8 = (char *)v7 + 80;
    else
      v8 = 0;
    v9 = *((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v8;
    if ( v8 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 8LL))(v8);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v7 )
      v7 = (struct Rdp::Avenc::IGpuFrameProcessor *)((char *)v7 + 152);
    *a2 = v7;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 16);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x7D,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvmonitorcontext.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800621f0  mov     [rsp+arg_0], rbx
0x1800621f5  mov     [rsp+arg_10], rsi
0x1800621fa  mov     [rsp+arg_8], rdx
0x1800621ff  push    rdi
0x180062200  push    r12
0x180062202  push    r13
0x180062204  push    r14
0x180062206  push    r15
0x180062208  sub     rsp, 0B0h
0x18006220f  mov     rax, rdx
0x180062212  mov     r15, rcx
0x180062215  mov     rcx, [rsp+0D8h]; this
0x18006221d  test    rax, rax
0x180062220  jz      loc_18006249D
0x180062226  cmp     byte ptr [r15+10h], 0
0x18006222b  setz    al
0x18006222e  mov     rcx, [rsp+0D8h]; this
0x180062236  lea     rdx, aMonitorContext; "Monitor context is not started"
0x18006223d  mov     qword ptr [rsp+0D8h+var_B0], rdx; bool
0x180062242  mov     byte ptr [rsp+0D8h+var_B8], al; int
0x180062246  mov     r9d, 8000FFFFh; char *
0x18006224c  lea     r13, aOnecoreuapTerm_38; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180062253  mov     r8, r13; unsigned int
0x180062256  mov     edx, 6Dh ; 'm'; void *
0x18006225b  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180062260  mov     ecx, 0A0h; Size
0x180062265  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006226a  mov     [rsp+0D8h+arg_18], rax
0x180062272  lea     rdx, [r15-50h]; struct Rdp::Avenc::Yuv::CYuvMonitorContext *
0x180062276  mov     rcx, rax; this
0x180062279  call    ??0CGpuYuvFrameProcessor@Yuv@Avenc@Rdp@@QEAA@PEAVCYuvMonitorContext@123@@Z; Rdp::Avenc::Yuv::CGpuYuvFrameProcessor::CGpuYuvFrameProcessor(Rdp::Avenc::Yuv::CYuvMonitorContext *)
0x18006227e  mov     r12, rax
0x180062281  mov     [rsp+0D8h+var_30], rax
0x180062289  test    rax, rax
0x18006228c  jz      short loc_18006229E
0x18006228e  mov     rcx, [rax]
0x180062291  mov     rax, [rcx+8]
0x180062295  mov     rcx, r12
0x180062298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006229d  nop
0x18006229e  mov     eax, cs:dword_1800C1058
0x1800622a4  cmp     eax, 4
0x1800622a7  jbe     loc_180062374
0x1800622ad  lea     rax, [r15+28h]
0x1800622b1  mov     [rsp+0D8h+var_50], rax
0x1800622b9  mov     rax, [r15+20h]
0x1800622bd  mov     ecx, [rax+98h]
0x1800622c3  mov     dword ptr [rsp+0D8h+arg_18], ecx
0x1800622ca  mov     eax, [r15+38h]
0x1800622ce  mov     [rsp+0D8h+var_58], eax
0x1800622d5  lea     rax, aCreateGpuYuvFr; "Create Gpu Yuv frame processor"
0x1800622dc  mov     [rsp+0D8h+var_48], rax
0x1800622e4  lea     rax, aRdpAvencYuvCyu_6; "Rdp::Avenc::Yuv::CYuvMonitorContext::Cr"...
0x1800622eb  mov     [rsp+0D8h+var_40], rax
0x1800622f3  mov     [rsp+0D8h+var_54], 74h ; 't'
0x1800622fe  mov     [rsp+0D8h+var_38], r13
0x180062306  lea     rax, [rsp+0D8h+var_50]
0x18006230e  mov     [rsp+0D8h+var_88], rax
0x180062313  lea     rax, [rsp+0D8h+arg_18]
0x18006231b  mov     [rsp+0D8h+var_90], rax
0x180062320  lea     rax, [rsp+0D8h+var_58]
0x180062328  mov     [rsp+0D8h+var_98], rax
0x18006232d  lea     rax, [rsp+0D8h+var_48]
0x180062335  mov     [rsp+0D8h+var_A0], rax
0x18006233a  lea     rax, [rsp+0D8h+var_40]
0x180062342  mov     [rsp+0D8h+var_A8], rax
0x180062347  lea     rax, [rsp+0D8h+var_54]
0x18006234f  mov     qword ptr [rsp+0D8h+var_B0], rax
0x180062354  lea     rax, [rsp+0D8h+var_38]
0x18006235c  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180062361  lea     rdx, word_1800B4C8A
0x180062368  lea     rcx, dword_1800C1058
0x18006236f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180062374  lea     r8, [r15+28h]
0x180062378  movzx   eax, byte ptr [r15+37h]
0x18006237d  movzx   ecx, byte ptr [r15+36h]
0x180062382  movzx   edx, byte ptr [r15+35h]
0x180062387  movzx   r9d, byte ptr [r15+34h]
0x18006238c  movzx   r10d, byte ptr [r15+33h]
0x180062391  movzx   r11d, byte ptr [r15+32h]
0x180062396  movzx   ebx, byte ptr [r15+31h]
0x18006239b  movzx   edi, byte ptr [r15+30h]
0x1800623a0  movzx   esi, word ptr [r15+2Eh]
0x1800623a5  movzx   r14d, word ptr [r15+2Ch]
0x1800623aa  mov     [rsp+0D8h+var_60], eax
0x1800623ae  mov     [rsp+0D8h+var_68], ecx
0x1800623b2  mov     [rsp+0D8h+var_70], edx
0x1800623b6  mov     [rsp+0D8h+var_78], r9d
0x1800623bb  mov     [rsp+0D8h+var_80], r10d
0x1800623c0  mov     dword ptr [rsp+0D8h+var_88], r11d
0x1800623c5  mov     dword ptr [rsp+0D8h+var_90], ebx
0x1800623c9  mov     dword ptr [rsp+0D8h+var_98], edi
0x1800623cd  mov     dword ptr [rsp+0D8h+var_A0], esi
0x1800623d1  mov     dword ptr [rsp+0D8h+var_A8], r14d
0x1800623d6  mov     eax, [r8]
0x1800623d9  mov     dword ptr [rsp+0D8h+var_B0], eax
0x1800623dd  mov     [rsp+0D8h+var_B8], 76h ; 'v'; unsigned int
0x1800623e5  mov     r9, r13; char *
0x1800623e8  lea     r8, aRdpAvencYuvCyu_6; "Rdp::Avenc::Yuv::CYuvMonitorContext::Cr"...
0x1800623ef  lea     rdx, aCreategpuyuvfr; "CreateGpuYuvFrameProcessor: Id {%08lX-%"...
0x1800623f6  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800623fd  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180062402  lea     rdi, [r15+80h]
0x180062409  mov     rcx, rdi; SRWLock
0x18006240c  call    cs:__imp_AcquireSRWLockExclusive
0x180062412  test    r12, r12
0x180062415  jz      short loc_18006241E
0x180062417  lea     rcx, [r12+50h]
0x18006241c  jmp     short loc_180062420
0x18006241e  xor     ecx, ecx
0x180062420  mov     rbx, [r15+90h]
0x180062427  mov     [r15+90h], rcx
0x18006242e  test    rcx, rcx
0x180062431  jz      short loc_18006243F
0x180062433  mov     rax, [rcx]
0x180062436  mov     rax, [rax+8]
0x18006243a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006243f  test    rbx, rbx
0x180062442  jz      short loc_180062454
0x180062444  mov     rax, [rbx]
0x180062447  mov     rcx, rbx
0x18006244a  mov     rax, [rax+10h]
0x18006244e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062453  nop
0x180062454  test    r12, r12
0x180062457  jz      short loc_180062460
0x180062459  add     r12, 98h
0x180062460  mov     rax, [rsp+0D8h+arg_8]
0x180062468  mov     [rax], r12
0x18006246b  mov     rcx, rdi; SRWLock
0x18006246e  call    cs:__imp_ReleaseSRWLockExclusive
0x180062474  nop
0x180062475  xor     eax, eax
0x180062477  jmp     short loc_180062480
0x180062479  mov     eax, dword ptr [rsp+0D8h+arg_8]
0x180062480  lea     r11, [rsp+0D8h+var_28]
0x180062488  mov     rbx, [r11+30h]
0x18006248c  mov     rsi, [r11+40h]
0x180062490  mov     rsp, r11
0x180062493  pop     r15
0x180062495  pop     r14
0x180062497  pop     r13
0x180062499  pop     r12
0x18006249b  pop     rdi
0x18006249c  retn
0x18006249d  mov     r9d, 80004003h; char *
0x1800624a3  lea     r8, aOnecoreuapTerm_38; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800624aa  lea     edx, [rax+6Ch]; void *
0x1800624ad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
