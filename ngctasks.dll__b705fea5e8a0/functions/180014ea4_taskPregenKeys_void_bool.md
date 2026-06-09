# taskPregenKeys(void *,bool *)

- ea: `0x180014ea4`
- end: `0x180015058`
- name: `?taskPregenKeys@@YAJPEAXPEA_N@Z`
- size: `436`
- prototype: `__int64 __fastcall(unsigned __int64, bool *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800110c4`

## callees

- `0x180002e70`
- `0x180006330`
- `0x18000cc34`
- `0x18000ec2c`
- `0x18000fe1c`
- `0x180010178`
- `0x180011440`
- `0x18001159c`
- `0x180014490`
- `0x180014ea4`
- `0x180015060`

## import_xrefs

- `ngcpopkeysrv!NgcPregenKey` at `0x180014ff1`
- `ngcpopkeysrv!NgcPregenKey` at `0x180014ff1`

## string_xrefs

- `0x180014f6c`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180014fd0`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`
- `0x180015004`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall taskPregenKeys(unsigned __int64 a1, bool *a2)
{
  struct _GUID *v4; // r9
  int v5; // eax
  unsigned int v6; // ebx
  bool v7; // bl
  char v8; // al
  int v9; // eax
  int v10; // eax
  int v12; // [rsp+20h] [rbp-39h]
  bool v13; // [rsp+30h] [rbp-29h] BYREF
  int v14; // [rsp+34h] [rbp-25h] BYREF
  int v15; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v16[24]; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v17[2]; // [rsp+58h] [rbp-1h] BYREF
  int v18; // [rsp+68h] [rbp+Fh] BYREF
  char v19; // [rsp+6Ch] [rbp+13h]
  char v20; // [rsp+70h] [rbp+17h] BYREF
  struct _GUID v21; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v14 = 0;
  v18 = 0;
  v19 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v18);
  if ( (unsigned int)dword_180031038 > 5 )
  {
    v15 = v14;
    if ( !v19 || _tlgGuidIsZero(&v21) )
      LODWORD(v4) = 0;
    else
      v4 = &v21;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180031038,
      (unsigned int)byte_18002978B,
      (unsigned int)&v20,
      (_DWORD)v4,
      (__int64)&v15);
  }
  v17[0] = &v18;
  v17[1] = &v14;
  wil::ScopeExitIgnore__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___(v16, v17);
  v13 = 0;
  v5 = SynchronizeSrkHash(&v13);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v13;
    v8 = AcquireExclusiveRunning((HANDLE)(a1 & -(__int64)v13), L"Volatile-KeyPreGen-EXCLUSIVE");
    *a2 = v8;
    if ( v8 )
    {
      if ( v7 )
      {
        v9 = SynchronizeSrkHash(0);
        v6 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29D,
            (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
            (const char *)(unsigned int)v9,
            v12);
          wil::details::ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___::operator()(v16);
          goto LABEL_16;
        }
      }
      v10 = NgcPregenKey(0xFFFFFFFFLL);
      v6 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A1,
          (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
          (const char *)(unsigned int)v10,
          v12);
        wil::details::ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___::operator()(v16);
        goto LABEL_16;
      }
    }
    wil::details::ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___::operator()(v16);
    v6 = 0;
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28F,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (const char *)(unsigned int)v5,
    v12);
  wil::details::ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___::operator()(v16);
LABEL_16:
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(&v18);
  return v6;
}

```

## disassembly

```asm
0x180014ea4  mov     [rsp-8+arg_10], rbx
0x180014ea9  push    rbp
0x180014eaa  push    rsi
0x180014eab  push    rdi
0x180014eac  lea     rbp, [rsp-47h]
0x180014eb1  sub     rsp, 0A0h
0x180014eb8  mov     rax, cs:__security_cookie
0x180014ebf  xor     rax, rsp
0x180014ec2  mov     [rbp+57h+var_20], rax
0x180014ec6  mov     rsi, rdx
0x180014ec9  mov     rdi, rcx
0x180014ecc  mov     [rbp+57h+var_7C], 0
0x180014ed3  mov     [rbp+57h+var_48], 0
0x180014eda  mov     [rbp+57h+var_44], 0
0x180014ede  lea     rcx, [rbp+57h+var_48]
0x180014ee2  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x180014ee7  mov     eax, cs:dword_180031038
0x180014eed  cmp     eax, 5
0x180014ef0  jbe     short loc_180014F34
0x180014ef2  mov     eax, [rbp+57h+var_7C]
0x180014ef5  mov     [rbp+57h+var_78], eax
0x180014ef8  cmp     [rbp+57h+var_44], 0
0x180014efc  jz      short loc_180014F11
0x180014efe  lea     rcx, [rbp+57h+var_30]; struct _GUID *
0x180014f02  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180014f07  test    al, al
0x180014f09  jnz     short loc_180014F11
0x180014f0b  lea     r9, [rbp+57h+var_30]
0x180014f0f  jmp     short loc_180014F14
0x180014f11  xor     r9d, r9d
0x180014f14  lea     rax, [rbp+57h+var_78]
0x180014f18  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180014f1d  lea     r8, [rbp+57h+var_40]
0x180014f21  lea     rdx, byte_18002978B
0x180014f28  lea     rcx, dword_180031038
0x180014f2f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180014f34  lea     rax, [rbp+57h+var_48]
0x180014f38  mov     [rbp+57h+var_58], rax
0x180014f3c  lea     rax, [rbp+57h+var_7C]
0x180014f40  mov     [rbp+57h+var_50], rax
0x180014f44  lea     rdx, [rbp+57h+var_58]
0x180014f48  lea     rcx, [rbp+57h+var_70]
0x180014f4c  call    wil__ScopeExitIgnore__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f___
0x180014f51  nop
0x180014f52  mov     [rbp+57h+var_80], 0
0x180014f56  lea     rcx, [rbp+57h+var_80]; bool *
0x180014f5a  call    ?SynchronizeSrkHash@@YAJPEA_N@Z; SynchronizeSrkHash(bool *)
0x180014f5f  mov     ebx, eax
0x180014f61  test    eax, eax
0x180014f63  jns     short loc_180014F8D
0x180014f65  mov     rcx, [rbp+5Fh]; this
0x180014f69  mov     r9d, eax; char *
0x180014f6c  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014f73  mov     edx, 28Fh; void *
0x180014f78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f7d  nop
0x180014f7e  lea     rcx, [rbp+57h+var_70]
0x180014f82  call    wil__details__ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f_____operator__
0x180014f87  nop
0x180014f88  jmp     loc_18001502E
0x180014f8d  mov     bl, [rbp+57h+var_80]
0x180014f90  mov     al, bl
0x180014f92  neg     al
0x180014f94  sbb     rcx, rcx
0x180014f97  and     rcx, rdi; hHandle
0x180014f9a  lea     rdx, aVolatileKeypre; "Volatile-KeyPreGen-EXCLUSIVE"
0x180014fa1  call    AcquireExclusiveRunning
0x180014fa6  mov     [rsi], al
0x180014fa8  test    al, al
0x180014faa  jnz     short loc_180014FB8
0x180014fac  lea     rcx, [rbp+57h+var_70]
0x180014fb0  call    wil__details__ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f_____operator__
0x180014fb5  nop
0x180014fb6  jmp     short loc_18001502C
0x180014fb8  test    bl, bl
0x180014fba  jz      short loc_180014FEE
0x180014fbc  xor     ecx, ecx; bool *
0x180014fbe  call    ?SynchronizeSrkHash@@YAJPEA_N@Z; SynchronizeSrkHash(bool *)
0x180014fc3  mov     ebx, eax
0x180014fc5  test    eax, eax
0x180014fc7  jns     short loc_180014FEE
0x180014fc9  mov     rcx, [rbp+5Fh]; this
0x180014fcd  mov     r9d, eax; char *
0x180014fd0  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014fd7  mov     edx, 29Dh; void *
0x180014fdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fe1  nop
0x180014fe2  lea     rcx, [rbp+57h+var_70]
0x180014fe6  call    wil__details__ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f_____operator__
0x180014feb  nop
0x180014fec  jmp     short loc_18001502E
0x180014fee  or      ecx, 0FFFFFFFFh
0x180014ff1  call    cs:__imp_NgcPregenKey
0x180014ff7  mov     ebx, eax
0x180014ff9  test    eax, eax
0x180014ffb  jns     short loc_180015022
0x180014ffd  mov     rcx, [rbp+5Fh]; this
0x180015001  mov     r9d, eax; char *
0x180015004  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001500b  mov     edx, 2A1h; void *
0x180015010  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015015  nop
0x180015016  lea     rcx, [rbp+57h+var_70]
0x18001501a  call    wil__details__ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f_____operator__
0x18001501f  nop
0x180015020  jmp     short loc_18001502E
0x180015022  lea     rcx, [rbp+57h+var_70]
0x180015026  call    wil__details__ScopeExitFnGuard__lambda_2c1a5bf7ac07f85bc4335a74d9b4d21f_____operator__
0x18001502b  nop
0x18001502c  xor     ebx, ebx
0x18001502e  lea     rcx, [rbp+57h+var_48]
0x180015032  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>(void)
0x180015037  mov     eax, ebx
0x180015039  mov     rcx, [rbp+57h+var_20]
0x18001503d  xor     rcx, rsp; StackCookie
0x180015040  call    __security_check_cookie
0x180015045  mov     rbx, [rsp+0B0h+arg_10]
0x18001504d  add     rsp, 0A0h
0x180015054  pop     rdi
0x180015055  pop     rsi
0x180015056  pop     rbp
0x180015057  retn
```
