# IDispatchInvoke(CSession *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18001154c`
- end: `0x18001179f`
- name: `?IDispatchInvoke@@YAJPEAVCSession@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `595`
- prototype: `__int64 __fastcall(struct ThreadGlobals **, struct IDispatch *, unsigned int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `5`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000f678`
- `0x18000ff30`
- `0x1800107c0`
- `0x180013350`
- `0x18004d2d0`

## callees

- `0x18001154c`
- `0x180011ecc`
- `0x180011f90`
- `0x180012ee8`
- `0x180022010`
- `0x180033640`
- `0x1800414d0`
- `0x180050aa8`
- `0x180050dfc`
- `0x18005f648`
- `0x180096010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x180011701`
- `KERNEL32!TlsGetValue` at `0x180011701`

## pseudocode

```c
__int64 __fastcall IDispatchInvoke(
        struct ThreadGlobals **a1,
        struct IDispatch *a2,
        unsigned int a3,
        const struct _GUID *a4,
        unsigned int a5,
        unsigned __int16 a6,
        struct tagDISPPARAMS *a7,
        struct tagVARIANT *a8,
        struct tagEXCEPINFO *a9,
        unsigned int *a10)
{
  bool v10; // r14
  struct IDispatch *v14; // rdx
  CSession *v15; // rcx
  int v16; // r8d
  struct ThreadGlobals *v17; // rcx
  JAmsi *v18; // rcx
  int v19; // edi
  struct ThreadGlobals *Value; // rax
  __int64 v21; // rdi
  const struct _GUID *v22; // r8
  const struct _GUID *v23; // r9
  struct GL *v24; // rcx
  int v25; // eax
  int v27; // [rsp+20h] [rbp-88h]
  _QWORD v28[2]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v29; // [rsp+60h] [rbp-48h]

  v10 = 0;
  if ( a1 )
  {
    if ( CSession::IsScriptTraceInfoEnabled((CSession *)a1) )
    {
      v10 = CSession::IsResponseDotWrite(v15, v14, v16);
      if ( !v10 )
        CSession::SendRuntimeScriptInfoToHost((CSession *)a1, SCRIPTTRACEINFO_COMCALLSTART);
    }
  }
  if ( (unsigned int)FStackAvailable(a1[123], 0x10000u) )
  {
    v17 = a1[5];
    if ( !v17
      || (v18 = (struct ThreadGlobals *)((char *)v17 + 216)) == 0
      || *((_DWORD *)v18 + 1) != 1
      || (v19 = JAmsi::JAmsiProcessor(v18, a2, a3, a7, (struct CSession *)a1), v19 >= 0) )
    {
      Value = a1[123];
      v28[0] = Value;
      if ( Value || (Value = (struct ThreadGlobals *)TlsGetValue(g_luTls), (v28[0] = Value) != 0) )
      {
        v21 = *((_QWORD *)Value + 3);
        v29 = v21;
        v28[1] = 0;
        if ( v21 )
          *((_QWORD *)Value + 3) = 0;
        ClearFPUStatus();
      }
      else
      {
        v21 = v29;
      }
      if ( *((int *)a1 + 251) < 0 )
      {
        v25 = TrapIDispatchInvoke(a2, a3, v22, a5, a6, a7, a8, a9, a10);
      }
      else if ( v21 && (v24 = *(struct GL **)(v21 + 704)) != 0 )
      {
        v25 = CatchIDispatchInvoke(v24, a2, a3, v23, a5, a6, a7, a8, a9, a10);
      }
      else
      {
        LOWORD(v27) = a6;
        v25 = ((__int64 (__fastcall *)(struct IDispatch *, _QWORD, GUID *, _QWORD, int, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))a2->lpVtbl->Invoke)(
                a2,
                a3,
                &GUID_NULL,
                a5,
                v27,
                a7,
                a8,
                a9,
                a10);
      }
      v19 = v25;
      TLS_NoDestructor::Close((TLS_NoDestructor *)v28);
    }
  }
  else
  {
    v19 = -2147024882;
  }
  if ( !v10 )
    CSession::SendRuntimeScriptInfoToHost((CSession *)a1, SCRIPTTRACEINFO_COMCALLEND);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18001154c  push    rbx
0x18001154e  push    rbp
0x18001154f  push    rsi
0x180011550  push    rdi
0x180011551  push    r14
0x180011553  push    r15
0x180011555  sub     rsp, 78h
0x180011559  xor     r14b, r14b
0x18001155c  mov     ebp, r8d
0x18001155f  mov     rsi, rdx
0x180011562  mov     rbx, rcx
0x180011565  test    rcx, rcx
0x180011568  jz      short loc_180011577
0x18001156a  call    ?IsScriptTraceInfoEnabled@CSession@@QEAA_NXZ; CSession::IsScriptTraceInfoEnabled(void)
0x18001156f  test    al, al
0x180011571  jnz     loc_18001171F
0x180011577  mov     rcx, [rbx+3D8h]; struct ThreadGlobals *
0x18001157e  mov     edx, 10000h; unsigned int
0x180011583  call    ?FStackAvailable@@YAHPEAVThreadGlobals@@I@Z; FStackAvailable(ThreadGlobals *,uint)
0x180011588  test    eax, eax
0x18001158a  jz      loc_180011741
0x180011590  mov     rcx, [rbx+28h]
0x180011594  mov     r15, [rsp+0A8h+arg_30]
0x18001159c  test    rcx, rcx
0x18001159f  jz      short loc_1800115CD
0x1800115a1  add     rcx, 0D8h; this
0x1800115a8  jz      short loc_1800115CD
0x1800115aa  cmp     dword ptr [rcx+4], 1
0x1800115ae  jnz     short loc_1800115CD
0x1800115b0  mov     r9, r15; struct tagDISPPARAMS *
0x1800115b3  mov     [rsp+0A8h+var_88], rbx; struct CSession *
0x1800115b8  mov     r8d, ebp; int
0x1800115bb  mov     rdx, rsi; struct IDispatch *
0x1800115be  call    ?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z; JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)
0x1800115c3  mov     edi, eax
0x1800115c5  test    eax, eax
0x1800115c7  js      loc_18001168D
0x1800115cd  mov     rax, [rbx+3D8h]
0x1800115d4  mov     [rsp+0A8h+var_58], rax
0x1800115d9  test    rax, rax
0x1800115dc  jz      loc_1800116FB
0x1800115e2  mov     rdi, [rax+18h]
0x1800115e6  mov     [rsp+0A8h+var_48], rdi
0x1800115eb  mov     [rsp+0A8h+var_50], 0
0x1800115f4  test    rdi, rdi
0x1800115f7  jz      short loc_180011601
0x1800115f9  mov     qword ptr [rax+18h], 0
0x180011601  call    ?ClearFPUStatus@@YAXXZ; ClearFPUStatus(void)
0x180011606  cmp     dword ptr [rbx+3ECh], 0
0x18001160d  jl      loc_1800116AE
0x180011613  test    rdi, rdi
0x180011616  jz      short loc_180011628
0x180011618  mov     rcx, [rdi+2C0h]; struct GL *
0x18001161f  test    rcx, rcx
0x180011622  jnz     loc_18001174B
0x180011628  mov     rcx, [rsp+0A8h+arg_48]
0x180011630  lea     r8, GUID_NULL
0x180011637  mov     rax, [rsi]
0x18001163a  mov     edx, ebp
0x18001163c  mov     r9d, [rsp+0A8h+arg_20]
0x180011644  mov     [rsp+0A8h+var_68], rcx
0x180011649  mov     rcx, [rsp+0A8h+arg_40]
0x180011651  mov     rax, [rax+30h]
0x180011655  mov     [rsp+0A8h+var_70], rcx
0x18001165a  mov     rcx, [rsp+0A8h+arg_38]
0x180011662  mov     [rsp+0A8h+var_78], rcx
0x180011667  movzx   ecx, [rsp+0A8h+arg_28]
0x18001166f  mov     [rsp+0A8h+var_80], r15
0x180011674  mov     word ptr [rsp+0A8h+var_88], cx
0x180011679  mov     rcx, rsi
0x18001167c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011681  lea     rcx, [rsp+0A8h+var_58]; this
0x180011686  mov     edi, eax
0x180011688  call    ?Close@TLS_NoDestructor@@QEAAXXZ; TLS_NoDestructor::Close(void)
0x18001168d  test    r14b, r14b
0x180011690  jnz     short loc_18001169F
0x180011692  mov     edx, 3; enum tagSCRIPTTRACEINFO
0x180011697  mov     rcx, rbx; this
0x18001169a  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x18001169f  mov     eax, edi
0x1800116a1  add     rsp, 78h
0x1800116a5  pop     r15
0x1800116a7  pop     r14
0x1800116a9  pop     rdi
0x1800116aa  pop     rsi
0x1800116ab  pop     rbp
0x1800116ac  pop     rbx
0x1800116ad  retn
0x1800116ae  mov     rax, [rsp+0A8h+arg_48]
0x1800116b6  mov     edx, ebp; int
0x1800116b8  mov     r9d, [rsp+0A8h+arg_20]; unsigned int
0x1800116c0  mov     rcx, rsi; struct IDispatch *
0x1800116c3  mov     [rsp+0A8h+var_68], rax; unsigned int *
0x1800116c8  mov     rax, [rsp+0A8h+arg_40]
0x1800116d0  mov     [rsp+0A8h+var_70], rax; struct tagEXCEPINFO *
0x1800116d5  mov     rax, [rsp+0A8h+arg_38]
0x1800116dd  mov     [rsp+0A8h+var_78], rax; struct tagVARIANT *
0x1800116e2  movzx   eax, [rsp+0A8h+arg_28]
0x1800116ea  mov     [rsp+0A8h+var_80], r15; struct tagDISPPARAMS *
0x1800116ef  mov     word ptr [rsp+0A8h+var_88], ax; unsigned __int16
0x1800116f4  call    ?TrapIDispatchInvoke@@YAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; TrapIDispatchInvoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x1800116f9  jmp     short loc_180011681
0x1800116fb  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180011701  call    cs:__imp_TlsGetValue
0x180011707  mov     [rsp+0A8h+var_58], rax
0x18001170c  test    rax, rax
0x18001170f  jnz     loc_1800115E2
0x180011715  mov     rdi, [rsp+0A8h+var_48]
0x18001171a  jmp     loc_180011606
0x18001171f  call    ?IsResponseDotWrite@CSession@@QEAA_NPEAUIDispatch@@J@Z; CSession::IsResponseDotWrite(IDispatch *,long)
0x180011724  mov     r14b, al
0x180011727  test    al, al
0x180011729  jnz     loc_180011577
0x18001172f  mov     edx, 2; enum tagSCRIPTTRACEINFO
0x180011734  mov     rcx, rbx; this
0x180011737  call    ?SendRuntimeScriptInfoToHost@CSession@@QEAAJW4tagSCRIPTTRACEINFO@@@Z; CSession::SendRuntimeScriptInfoToHost(tagSCRIPTTRACEINFO)
0x18001173c  jmp     loc_180011577
0x180011741  mov     edi, 8007000Eh
0x180011746  jmp     loc_18001168D
0x18001174b  mov     rax, [rsp+0A8h+arg_48]
0x180011753  mov     r8d, ebp; int
0x180011756  mov     [rsp+0A8h+var_60], rax; unsigned int *
0x18001175b  mov     rdx, rsi; struct IDispatch *
0x18001175e  mov     rax, [rsp+0A8h+arg_40]
0x180011766  mov     [rsp+0A8h+var_68], rax; struct tagEXCEPINFO *
0x18001176b  mov     rax, [rsp+0A8h+arg_38]
0x180011773  mov     [rsp+0A8h+var_70], rax; struct tagVARIANT *
0x180011778  movzx   eax, [rsp+0A8h+arg_28]
0x180011780  mov     [rsp+0A8h+var_78], r15; struct tagDISPPARAMS *
0x180011785  mov     word ptr [rsp+0A8h+var_80], ax; unsigned __int16
0x18001178a  mov     eax, [rsp+0A8h+arg_20]
0x180011791  mov     dword ptr [rsp+0A8h+var_88], eax; unsigned int
0x180011795  call    ?CatchIDispatchInvoke@@YAJPEAVGL@@PEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; CatchIDispatchInvoke(GL *,IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x18001179a  jmp     loc_180011681
```
