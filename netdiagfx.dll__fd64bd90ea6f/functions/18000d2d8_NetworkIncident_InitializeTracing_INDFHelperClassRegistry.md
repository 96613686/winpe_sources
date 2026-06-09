# NetworkIncident::InitializeTracing(INDFHelperClassRegistry *)

- ea: `0x18000d2d8`
- end: `0x18000d543`
- name: `?InitializeTracing@NetworkIncident@@QEAAJPEAUINDFHelperClassRegistry@@@Z`
- size: `619`
- prototype: `__int64 __fastcall(NetworkIncident *this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018ae4`

## callees

- `0x1800017f4`
- `0x1800084e4`
- `0x180009254`
- `0x18000c454`
- `0x18000d2d8`
- `0x18001df4c`
- `0x180023704`
- `0x1800239f4`
- `0x180023a2c`
- `0x180028848`
- `0x18002b2ac`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `ntdll!WinSqmSetDWORD` at `0x18000d36f`
- `ntdll!WinSqmSetDWORD` at `0x18000d4ee`
- `ntdll!WinSqmSetDWORD` at `0x18000d36f`
- `ntdll!WinSqmSetDWORD` at `0x18000d4ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d41c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d518`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d41c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d518`
- `RPCRT4!UuidCreateSequential` at `0x18000d33b`
- `RPCRT4!UuidCreateSequential` at `0x18000d33b`

## pseudocode

```c
__int64 __fastcall NetworkIncident::InitializeTracing(NetworkIncident *this, struct IUnknown *a2)
{
  NetworkIncident *v3; // r15
  _QWORD *v4; // r14
  CTraceController *v5; // rdi
  int v6; // ebx
  int v7; // ecx
  OLECHAR *v8; // rax
  NetTrace::CTraceSession *v9; // rax
  OLECHAR *v10; // rsi
  const unsigned __int16 *v11; // rdx
  __int64 v13; // [rsp+0h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+20h] [rbp-68h] BYREF
  BSTR v15; // [rsp+28h] [rbp-60h] BYREF
  NetworkIncident *v16; // [rsp+30h] [rbp-58h]
  _QWORD *v17; // [rsp+38h] [rbp-50h]
  const ATL::CAtlException *v18; // [rsp+40h] [rbp-48h] BYREF
  UUID Uuid; // [rsp+48h] [rbp-40h] BYREF
  struct _GUID v20; // [rsp+58h] [rbp-30h] BYREF

  v3 = this;
  v16 = this;
  v20 = 0;
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 10) + 72LL))(*((_QWORD *)this + 10), &v20);
  v4 = (_QWORD *)((char *)v3 + 168);
  v17 = (_QWORD *)((char *)v3 + 168);
  Uuid = 0;
  if ( UuidCreateSequential(&Uuid) >= 0 && (int)UTSQMSession::Start((NetworkIncident *)((char *)v3 + 168), &Uuid) >= 0 )
  {
    *((UUID *)v3 + 11) = Uuid;
    WinSqmSetDWORD(*v4, 4049, 1);
  }
  v5 = (NetworkIncident *)((char *)v3 + 128);
  *(_QWORD *)&Uuid.Data1 = (char *)v3 + 128;
  v6 = -2147467261;
  if ( a2 )
  {
    v7 = -2147467261;
    if ( v3 != (NetworkIncident *)-128LL )
    {
      v8 = (OLECHAR *)operator new(0x98u);
      v15 = v8;
      if ( v8 )
      {
        v9 = NetTrace::CTraceSession::CTraceSession((NetTrace::CTraceSession *)v8);
        *(_QWORD *)v5 = v9;
        v7 = -2147024882;
        if ( v9 )
        {
          if ( *((struct IUnknown **)v3 + 18) != a2 )
            ATL::AtlComPtrAssign((struct IUnknown **)v3 + 18, a2);
          v7 = 0;
        }
      }
      else
      {
        *(_QWORD *)v5 = 0;
        v7 = -2147024882;
      }
    }
    *((_DWORD *)v3 + 38) = v7;
  }
  else
  {
    v7 = -2147024809;
  }
  v10 = 0;
  v15 = 0;
  if ( v7 )
  {
    v6 = v7;
    goto LABEL_30;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, &v20);
    ATL::CComBSTR::operator=(&v15, &bstrString);
    SysFreeString(bstrString);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v18) )
    {
      v11 = (const unsigned __int16 *)&v13;
      LODWORD(bstrString) = *(_DWORD *)v18;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D425);
      v6 = (int)bstrString;
      if ( (_DWORD)bstrString )
      {
        v10 = v15;
        goto LABEL_30;
      }
      v6 = -2147467261;
      v3 = v16;
      v4 = v17;
      v5 = *(CTraceController **)&Uuid.Data1;
    }
  }
  v10 = v15;
  if ( v15 )
  {
    v6 = *((_DWORD *)v5 + 6);
    if ( v6 )
      goto LABEL_30;
    v6 = (***(__int64 (__fastcall ****)(_QWORD, BSTR))v5)(*(_QWORD *)v5, v15);
  }
  if ( !v6 )
  {
    v6 = CTraceController::SetTraceFilePrefix(v5, v11);
    if ( !v6 )
    {
      *((_QWORD *)v3 + 20) = v4;
      v6 = CTraceController::AddProvider(v5, &NETDIAG_EVT_GUID, 0x400000000000uLL, 5u);
      if ( !v6 )
      {
        v6 = CTraceController::AddProvider(v5, &g_NdfTelemetryProviderGuid, 0xE00000000000uLL, 5u);
        if ( !v6 )
        {
          v6 = CTraceController::Start(v5);
          if ( v6 >= 0 )
            *((_QWORD *)v3 + 24) = *(_QWORD *)ATL::CTime::GetTickCount(&Uuid);
          else
            WinSqmSetDWORD(*v4, 4052, 1);
        }
      }
    }
  }
LABEL_30:
  SysFreeString(v10);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d2d8  mov     [rsp+arg_10], rbx
0x18000d2dd  mov     [rsp+arg_18], rsi
0x18000d2e2  push    rdi
0x18000d2e3  push    r14
0x18000d2e5  push    r15
0x18000d2e7  sub     rsp, 70h
0x18000d2eb  mov     rax, cs:__security_cookie
0x18000d2f2  xor     rax, rsp
0x18000d2f5  mov     [rsp+88h+var_20], rax
0x18000d2fa  mov     rsi, rdx
0x18000d2fd  mov     r15, rcx
0x18000d300  mov     [rsp+88h+var_58], rcx
0x18000d305  xorps   xmm0, xmm0
0x18000d308  movups  xmmword ptr [rsp+88h+var_30.Data1], xmm0
0x18000d30d  mov     rcx, [rcx+50h]
0x18000d311  mov     rax, [rcx]
0x18000d314  lea     rdx, [rsp+88h+var_30]
0x18000d319  mov     rax, [rax+48h]
0x18000d31d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d322  lea     r14, [r15+0A8h]
0x18000d329  mov     [rsp+88h+var_50], r14
0x18000d32e  xorps   xmm0, xmm0
0x18000d331  movups  xmmword ptr [rsp+88h+Uuid.Data1], xmm0
0x18000d336  lea     rcx, [rsp+88h+Uuid]; Uuid
0x18000d33b  call    cs:__imp_UuidCreateSequential
0x18000d341  test    eax, eax
0x18000d343  js      short loc_18000D375
0x18000d345  lea     rdx, [rsp+88h+Uuid]; struct _GUID *
0x18000d34a  mov     rcx, r14; this
0x18000d34d  call    ?Start@UTSQMSession@@QEAAJAEBU_GUID@@@Z; UTSQMSession::Start(_GUID const &)
0x18000d352  test    eax, eax
0x18000d354  js      short loc_18000D375
0x18000d356  movups  xmm0, xmmword ptr [rsp+88h+Uuid.Data1]
0x18000d35b  movdqu  xmmword ptr [r14+8], xmm0
0x18000d361  mov     edx, 0FD1h
0x18000d366  mov     r8d, 1
0x18000d36c  mov     rcx, [r14]
0x18000d36f  call    cs:__imp_WinSqmSetDWORD
0x18000d375  lea     rdi, [r15+80h]
0x18000d37c  mov     qword ptr [rsp+88h+Uuid.Data1], rdi
0x18000d381  mov     ebx, 80004003h
0x18000d386  test    rsi, rsi
0x18000d389  jnz     short loc_18000D392
0x18000d38b  mov     ecx, 80070057h
0x18000d390  jmp     short loc_18000D3E8
0x18000d392  mov     ecx, ebx
0x18000d394  test    rdi, rdi
0x18000d397  jz      short loc_18000D3E5
0x18000d399  mov     ecx, 98h; Size
0x18000d39e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d3a3  mov     [rsp+88h+var_60], rax
0x18000d3a8  test    rax, rax
0x18000d3ab  jz      short loc_18000D3D9
0x18000d3ad  mov     rcx, rax; this
0x18000d3b0  call    ??0CTraceSession@NetTrace@@QEAA@XZ; NetTrace::CTraceSession::CTraceSession(void)
0x18000d3b5  mov     [rdi], rax
0x18000d3b8  mov     ecx, 8007000Eh
0x18000d3bd  test    rax, rax
0x18000d3c0  jz      short loc_18000D3E5
0x18000d3c2  lea     rcx, [rdi+10h]; struct IUnknown **
0x18000d3c6  cmp     [rcx], rsi
0x18000d3c9  jnz     short loc_18000D3CF
0x18000d3cb  xor     ecx, ecx
0x18000d3cd  jmp     short loc_18000D3E5
0x18000d3cf  mov     rdx, rsi; struct IUnknown *
0x18000d3d2  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000d3d7  jmp     short loc_18000D3CB
0x18000d3d9  mov     qword ptr [rdi], 0
0x18000d3e0  mov     ecx, 8007000Eh
0x18000d3e5  mov     [rdi+18h], ecx
0x18000d3e8  xor     esi, esi
0x18000d3ea  mov     [rsp+88h+var_60], rsi
0x18000d3ef  test    ecx, ecx
0x18000d3f1  jnz     loc_18000D513
0x18000d3f7  lea     rdx, [rsp+88h+var_30]; struct _GUID *
0x18000d3fc  lea     rcx, [rsp+88h+bstrString]; this
0x18000d401  call    ??0CComBSTR@ATL@@QEAA@AEBU_GUID@@@Z; ATL::CComBSTR::CComBSTR(_GUID const &)
0x18000d406  nop
0x18000d407  lea     rdx, [rsp+88h+bstrString]
0x18000d40c  lea     rcx, [rsp+88h+var_60]
0x18000d411  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x18000d416  nop
0x18000d417  mov     rcx, [rsp+88h+bstrString]; bstrString
0x18000d41c  call    cs:__imp_SysFreeString
0x18000d422  nop
0x18000d423  jmp     short loc_18000D445
0x18000d425  mov     ebx, dword ptr [rsp+88h+bstrString]
0x18000d429  test    ebx, ebx
0x18000d42b  jnz     loc_18000D50C
0x18000d431  mov     ebx, 80004003h
0x18000d436  mov     r15, [rsp+88h+var_58]
0x18000d43b  mov     r14, [rsp+88h+var_50]
0x18000d440  mov     rdi, qword ptr [rsp+88h+Uuid.Data1]
0x18000d445  mov     rsi, [rsp+88h+var_60]
0x18000d44a  test    rsi, rsi
0x18000d44d  jz      short loc_18000D46D
0x18000d44f  mov     ebx, [rdi+18h]
0x18000d452  test    ebx, ebx
0x18000d454  jnz     loc_18000D515
0x18000d45a  mov     rcx, [rdi]
0x18000d45d  mov     rax, [rcx]
0x18000d460  mov     rdx, rsi
0x18000d463  mov     rax, [rax]
0x18000d466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d46b  mov     ebx, eax
0x18000d46d  test    ebx, ebx
0x18000d46f  jnz     loc_18000D515
0x18000d475  mov     rcx, rdi; this
0x18000d478  call    ?SetTraceFilePrefix@CTraceController@@QEAAJPEBG@Z; CTraceController::SetTraceFilePrefix(ushort const *)
0x18000d47d  mov     ebx, eax
0x18000d47f  test    eax, eax
0x18000d481  jnz     loc_18000D515
0x18000d487  mov     [r15+0A0h], r14
0x18000d48e  mov     r9b, 5; unsigned __int8
0x18000d491  mov     r8, 400000000000h; unsigned __int64
0x18000d49b  lea     rdx, NETDIAG_EVT_GUID; struct _GUID *
0x18000d4a2  mov     rcx, rdi; this
0x18000d4a5  call    ?AddProvider@CTraceController@@AEAAJAEBU_GUID@@_KE@Z; CTraceController::AddProvider(_GUID const &,unsigned __int64,uchar)
0x18000d4aa  mov     ebx, eax
0x18000d4ac  test    eax, eax
0x18000d4ae  jnz     short loc_18000D515
0x18000d4b0  mov     r9b, 5; unsigned __int8
0x18000d4b3  mov     r8, 0E00000000000h; unsigned __int64
0x18000d4bd  lea     rdx, ?g_NdfTelemetryProviderGuid@@3U_GUID@@A; struct _GUID *
0x18000d4c4  mov     rcx, rdi; this
0x18000d4c7  call    ?AddProvider@CTraceController@@AEAAJAEBU_GUID@@_KE@Z; CTraceController::AddProvider(_GUID const &,unsigned __int64,uchar)
0x18000d4cc  mov     ebx, eax
0x18000d4ce  test    eax, eax
0x18000d4d0  jnz     short loc_18000D515
0x18000d4d2  mov     rcx, rdi; this
0x18000d4d5  call    ?Start@CTraceController@@QEAAJXZ; CTraceController::Start(void)
0x18000d4da  mov     ebx, eax
0x18000d4dc  test    eax, eax
0x18000d4de  jns     short loc_18000D4F6
0x18000d4e0  mov     edx, 0FD4h
0x18000d4e5  mov     r8d, 1
0x18000d4eb  mov     rcx, [r14]
0x18000d4ee  call    cs:__imp_WinSqmSetDWORD
0x18000d4f4  jmp     short loc_18000D515
0x18000d4f6  lea     rcx, [rsp+88h+Uuid]
0x18000d4fb  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x18000d500  mov     rcx, [rax]
0x18000d503  mov     [r15+0C0h], rcx
0x18000d50a  jmp     short loc_18000D515
0x18000d50c  mov     rsi, [rsp+88h+var_60]
0x18000d511  jmp     short loc_18000D515
0x18000d513  mov     ebx, ecx
0x18000d515  mov     rcx, rsi; bstrString
0x18000d518  call    cs:__imp_SysFreeString
0x18000d51e  mov     eax, ebx
0x18000d520  mov     rcx, [rsp+88h+var_20]
0x18000d525  xor     rcx, rsp; StackCookie
0x18000d528  call    __security_check_cookie
0x18000d52d  lea     r11, [rsp+88h+var_18]
0x18000d532  mov     rbx, [r11+30h]
0x18000d536  mov     rsi, [r11+38h]
0x18000d53a  mov     rsp, r11
0x18000d53d  pop     r15
0x18000d53f  pop     r14
0x18000d541  pop     rdi
0x18000d542  retn
```
