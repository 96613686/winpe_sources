# DsrCmdTaskSchedulerHelper::ScheduleTask(IRegisteredTask * const,ushort const *,ushort const *,ushort const *)

- ea: `0x18009dcf0`
- end: `0x18009df4b`
- name: `?ScheduleTask@DsrCmdTaskSchedulerHelper@@CAJQEAUIRegisteredTask@@PEBG11@Z`
- size: `603`
- prototype: `__int64 __fastcall(struct IRegisteredTask *const, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180033984`

## callees

- `0x1800084f4`
- `0x180012c7c`
- `0x1800307c4`
- `0x18003334c`
- `0x180046ae8`
- `0x180046b3c`
- `0x18009dcd0`
- `0x18009dcf0`
- `0x18009df54`
- `0x1800bf010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18009ddb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ddec`
- `OLEAUT32!__imp_SysAllocString` at `0x18009de02`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ddb9`
- `OLEAUT32!__imp_SysAllocString` at `0x18009ddec`
- `OLEAUT32!__imp_SysAllocString` at `0x18009de02`
- `OLEAUT32!__imp_SysFreeString` at `0x18009dee8`
- `OLEAUT32!__imp_SysFreeString` at `0x18009def1`
- `OLEAUT32!__imp_SysFreeString` at `0x18009defa`
- `OLEAUT32!__imp_SysFreeString` at `0x18009dee8`
- `OLEAUT32!__imp_SysFreeString` at `0x18009def1`
- `OLEAUT32!__imp_SysFreeString` at `0x18009defa`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18009dd34`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18009dd34`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009df2b`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009df2b`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18009dd53`
- `OLEAUT32!__imp_SafeArrayLock` at `0x18009dd53`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009de53`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009df1e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009de53`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x18009df1e`

## string_xrefs

- `0x18009de9d`: `Cannot start Task: 0x%08x\n`
- `0x18009ded2`: `Cannot start Task: 0x%08x\n`
- `0x18009dd83`: `pRegisteredTask`
- `0x18009dd9d`: `pRegisteredTask`
- `0x18009dd8a`: `DsrCmdTaskSchedulerHelper::ScheduleTask`
- `0x18009dda4`: `DsrCmdTaskSchedulerHelper::ScheduleTask`
- `0x18009ddd0`: `DsrCmdTaskSchedulerHelper::ScheduleTask`

## pseudocode

```c
__int64 __fastcall DsrCmdTaskSchedulerHelper::ScheduleTask(
        struct IRegisteredTask *const a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  SAFEARRAY *v5; // rax
  SAFEARRAY *v6; // rsi
  SAFEARRAY *v7; // rbx
  HRESULT v8; // edi
  OLECHAR *v9; // r12
  OLECHAR *v10; // r15
  OLECHAR *v11; // r14
  unsigned int v12; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 CurrentRef; // rax
  SAFEARRAY *v23; // [rsp+20h] [rbp-50h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+28h] [rbp-48h] BYREF
  __int64 v25; // [rsp+30h] [rbp-40h] BYREF
  OLECHAR *v26; // [rsp+38h] [rbp-38h] BYREF
  OLECHAR *v27; // [rsp+40h] [rbp-30h] BYREF
  __int128 v28; // [rsp+50h] [rbp-20h] BYREF
  __int64 v29; // [rsp+60h] [rbp-10h]

  v25 = 0;
  rgsabound = (SAFEARRAYBOUND)3LL;
  v5 = SafeArrayCreate(8u, 1u, &rgsabound);
  v6 = v5;
  v7 = v5;
  v23 = v5;
  if ( !v5 )
  {
    v8 = -2147024882;
    goto LABEL_4;
  }
  v8 = SafeArrayLock(v5);
  if ( v8 < 0 )
LABEL_4:
    ATL::AtlThrowImpl(v8);
  v28 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  if ( a1 )
  {
    v9 = SysAllocString(a2);
    rgsabound = (SAFEARRAYBOUND)v9;
    if ( v9 && (v10 = SysAllocString(a3), (v26 = v10) != 0) && (v11 = SysAllocString(a4), (v27 = v11) != 0) )
    {
      ATL::CComSafeArray<unsigned short *,8>::SetAt(&v23, 0, &rgsabound);
      ATL::CComSafeArray<unsigned short *,8>::SetAt(&v23, 1, &v26);
      ATL::CComSafeArray<unsigned short *,8>::SetAt(&v23, 2, &v27);
      LOWORD(v28) = 8200;
      SafeArrayUnlock(v7);
      v7 = 0;
      v23 = 0;
      *((_QWORD *)&v28 + 1) = v6;
      v29 = 0;
      v12 = ((__int64 (__fastcall *)(struct IRegisteredTask *const, __int128 *, __int64 *))a1->lpVtbl->Run)(
              a1,
              &v28,
              &v25);
      v6 = 0;
      if ( (v12 & 0x80000000) != 0 )
      {
        if ( **(_BYTE **)CmdOptions::GetCurrentRef(v14, v13) )
        {
          wprintf(L"Cannot start Task: 0x%08x\n", v12);
          if ( *(_BYTE *)(*(_QWORD *)CmdOptions::GetCurrentRef(v16, v15) + 12LL) )
          {
            if ( *(_QWORD *)(*(_QWORD *)CmdOptions::GetCurrentRef(v18, v17) + 184LL) )
            {
              CurrentRef = CmdOptions::GetCurrentRef(v20, v19);
              fwprintf_s(*(FILE *const *)(*(_QWORD *)CurrentRef + 184LL), L"Cannot start Task: 0x%08x\n", v12);
            }
          }
        }
      }
    }
    else
    {
      v12 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DsrCmdTaskSchedulerHelper::ScheduleTask");
    }
  }
  else
  {
    v12 = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DsrCmdTaskSchedulerHelper::ScheduleTask",
      L"pRegisteredTask");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DsrCmdTaskSchedulerHelper::ScheduleTask", L"pRegisteredTask");
  }
  SysFreeString(v9);
  SysFreeString(v10);
  SysFreeString(v11);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v6 && SafeArrayUnlock(v7) >= 0 )
    SafeArrayDestroy(v7);
  return v12;
}

```

## disassembly

```asm
0x18009dcf0  mov     rax, rsp
0x18009dcf3  mov     [rax+8], rbx
0x18009dcf7  mov     [rax+20h], r9
0x18009dcfb  mov     [rax+18h], r8
0x18009dcff  mov     [rax+10h], rdx
0x18009dd03  push    rbp
0x18009dd04  push    rsi
0x18009dd05  push    rdi
0x18009dd06  push    r12
0x18009dd08  push    r13
0x18009dd0a  push    r14
0x18009dd0c  push    r15
0x18009dd0e  mov     rbp, rsp
0x18009dd11  sub     rsp, 70h
0x18009dd15  mov     r13, rcx
0x18009dd18  mov     [rbp+var_40], 0
0x18009dd20  mov     qword ptr [rbp+rgsabound.cElements], 3
0x18009dd28  mov     ecx, 8; vt
0x18009dd2d  lea     r8, [rbp+rgsabound]; rgsabound
0x18009dd31  lea     edx, [rcx-7]; cDims
0x18009dd34  call    cs:__imp_SafeArrayCreate
0x18009dd3a  mov     rsi, rax
0x18009dd3d  mov     rbx, rax
0x18009dd40  mov     [rbp+var_50], rax
0x18009dd44  test    rax, rax
0x18009dd47  jnz     short loc_18009DD50
0x18009dd49  mov     edi, 8007000Eh
0x18009dd4e  jmp     short loc_18009DD5F
0x18009dd50  mov     rcx, rbx; psa
0x18009dd53  call    cs:__imp_SafeArrayLock
0x18009dd59  mov     edi, eax
0x18009dd5b  test    eax, eax
0x18009dd5d  jns     short loc_18009DD67
0x18009dd5f  mov     ecx, edi; int
0x18009dd61  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18009dd67  xorps   xmm0, xmm0
0x18009dd6a  xor     edi, edi
0x18009dd6c  movups  [rbp+var_20], xmm0
0x18009dd70  xor     r12d, r12d
0x18009dd73  xor     r15d, r15d
0x18009dd76  xor     r14d, r14d
0x18009dd79  test    r13, r13
0x18009dd7c  jnz     short loc_18009DDB5
0x18009dd7e  mov     edi, 80070057h
0x18009dd83  lea     r8, aPregisteredtas; "pRegisteredTask"
0x18009dd8a  lea     rdx, aDsrcmdtasksche; "DsrCmdTaskSchedulerHelper::ScheduleTask"
0x18009dd91  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18009dd98  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009dd9d  lea     rdx, aPregisteredtas; "pRegisteredTask"
0x18009dda4  lea     rcx, aDsrcmdtasksche; "DsrCmdTaskSchedulerHelper::ScheduleTask"
0x18009ddab  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18009ddb0  jmp     loc_18009DEE5
0x18009ddb5  mov     rcx, [rbp+psz]; psz
0x18009ddb9  call    cs:__imp_SysAllocString
0x18009ddbf  mov     r12, rax
0x18009ddc2  mov     qword ptr [rbp+rgsabound.cElements], rax
0x18009ddc6  test    rax, rax
0x18009ddc9  jnz     short loc_18009DDE8
0x18009ddcb  mov     edi, 8007000Eh
0x18009ddd0  lea     rdx, aDsrcmdtasksche; "DsrCmdTaskSchedulerHelper::ScheduleTask"
0x18009ddd7  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x18009ddde  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x18009dde3  jmp     loc_18009DEE5
0x18009dde8  mov     rcx, [rbp+arg_10]; psz
0x18009ddec  call    cs:__imp_SysAllocString
0x18009ddf2  mov     r15, rax
0x18009ddf5  mov     [rbp+var_38], rax
0x18009ddf9  test    rax, rax
0x18009ddfc  jz      short loc_18009DDCB
0x18009ddfe  mov     rcx, [rbp+arg_18]; psz
0x18009de02  call    cs:__imp_SysAllocString
0x18009de08  mov     r14, rax
0x18009de0b  mov     [rbp+var_30], rax
0x18009de0f  test    rax, rax
0x18009de12  jz      short loc_18009DDCB
0x18009de14  lea     r8, [rbp+rgsabound]
0x18009de18  xor     edx, edx
0x18009de1a  lea     rcx, [rbp+var_50]
0x18009de1e  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x18009de23  lea     r8, [rbp+var_38]
0x18009de27  mov     edx, 1
0x18009de2c  lea     rcx, [rbp+var_50]
0x18009de30  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x18009de35  lea     r8, [rbp+var_30]
0x18009de39  mov     edx, 2
0x18009de3e  lea     rcx, [rbp+var_50]
0x18009de42  call    ?SetAt@?$CComSafeArray@PEAG$07@ATL@@QEAAJJAEBQEAGH@Z; ATL::CComSafeArray<ushort *,8>::SetAt(long,ushort * const &,int)
0x18009de47  mov     eax, 2008h
0x18009de4c  mov     word ptr [rbp+var_20], ax
0x18009de50  mov     rcx, rbx; psa
0x18009de53  call    cs:__imp_SafeArrayUnlock
0x18009de59  xor     ebx, ebx
0x18009de5b  mov     [rbp+var_50], rbx
0x18009de5f  mov     qword ptr [rbp+var_20+8], rsi
0x18009de63  movups  xmm0, [rbp+var_20]
0x18009de67  movaps  [rbp+var_20], xmm0
0x18009de6b  mov     [rbp+var_10], rdi
0x18009de6f  mov     rax, [r13+0]
0x18009de73  lea     r8, [rbp+var_40]
0x18009de77  lea     rdx, [rbp+var_20]
0x18009de7b  mov     rcx, r13
0x18009de7e  mov     rax, [rax+60h]
0x18009de82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009de87  mov     edi, eax
0x18009de89  xor     esi, esi
0x18009de8b  test    eax, eax
0x18009de8d  jns     short loc_18009DEE5
0x18009de8f  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009de94  mov     rcx, [rax]
0x18009de97  cmp     [rcx], bl
0x18009de99  jz      short loc_18009DEE5
0x18009de9b  mov     edx, edi
0x18009de9d  lea     rcx, aCannotStartTas; "Cannot start Task: 0x%08x\n"
0x18009dea4  call    wprintf
0x18009dea9  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009deae  mov     rax, [rax]
0x18009deb1  cmp     [rax+0Ch], bl
0x18009deb4  jz      short loc_18009DEE5
0x18009deb6  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009debb  mov     rax, [rax]
0x18009debe  cmp     [rax+0B8h], rbx
0x18009dec5  jz      short loc_18009DEE5
0x18009dec7  call    ?GetCurrentRef@CmdOptions@@CAAEAV?$shared_ptr@VCmdOptions@@@std@@XZ; CmdOptions::GetCurrentRef(void)
0x18009decc  mov     rcx, [rax]
0x18009decf  mov     r8d, edi
0x18009ded2  lea     rdx, aCannotStartTas; "Cannot start Task: 0x%08x\n"
0x18009ded9  mov     rcx, [rcx+0B8h]; Stream
0x18009dee0  call    fwprintf_s
0x18009dee5  mov     rcx, r12; bstrString
0x18009dee8  call    cs:__imp_SysFreeString
0x18009deee  mov     rcx, r15; bstrString
0x18009def1  call    cs:__imp_SysFreeString
0x18009def7  mov     rcx, r14; bstrString
0x18009defa  call    cs:__imp_SysFreeString
0x18009df00  mov     rcx, [rbp+var_40]
0x18009df04  test    rcx, rcx
0x18009df07  jz      short loc_18009DF16
0x18009df09  mov     rax, [rcx]
0x18009df0c  mov     rax, [rax+10h]
0x18009df10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009df15  nop
0x18009df16  test    rsi, rsi
0x18009df19  jz      short loc_18009DF31
0x18009df1b  mov     rcx, rbx; psa
0x18009df1e  call    cs:__imp_SafeArrayUnlock
0x18009df24  test    eax, eax
0x18009df26  js      short loc_18009DF31
0x18009df28  mov     rcx, rbx; psa
0x18009df2b  call    cs:__imp_SafeArrayDestroy
0x18009df31  mov     eax, edi
0x18009df33  mov     rbx, [rsp+70h+arg_0]
0x18009df3b  add     rsp, 70h
0x18009df3f  pop     r15
0x18009df41  pop     r14
0x18009df43  pop     r13
0x18009df45  pop     r12
0x18009df47  pop     rdi
0x18009df48  pop     rsi
0x18009df49  pop     rbp
0x18009df4a  retn
```
