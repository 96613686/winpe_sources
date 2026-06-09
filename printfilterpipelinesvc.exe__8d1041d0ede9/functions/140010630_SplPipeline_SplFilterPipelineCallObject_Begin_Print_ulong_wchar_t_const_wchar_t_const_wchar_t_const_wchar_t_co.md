# SplPipeline::SplFilterPipelineCallObject::Begin_Print(ulong,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,unsigned __int64)

- ea: `0x140010630`
- end: `0x1400107f9`
- name: `?Begin_Print@SplFilterPipelineCallObject@SplPipeline@@UEAAJKPEB_W00000H_K@Z`
- size: `457`
- prototype: `__int64 __fastcall(SplPipeline::SplFilterPipelineCallObject *this, unsigned int, wchar_t *, wchar_t *, WCHAR *, WCHAR *pPrinterName, wchar_t *, wchar_t *, unsigned int, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000fe88`
- `0x140010630`
- `0x14001093c`
- `0x140012404`
- `0x140056e3c`
- `0x140063010`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x140010678`
- `ADVAPI32!EventEnabled` at `0x140010678`
- `ADVAPI32!EventWrite` at `0x1400106a4`
- `ADVAPI32!EventWrite` at `0x1400106a4`
- `KERNEL32!ExitProcess` at `0x1400107ae`
- `KERNEL32!ExitProcess` at `0x1400107f2`
- `KERNEL32!ExitProcess` at `0x1400107ae`
- `KERNEL32!ExitProcess` at `0x1400107f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall SplPipeline::SplFilterPipelineCallObject::Begin_Print(
        SplPipeline::SplFilterPipelineCallObject *this,
        unsigned int a2,
        wchar_t *a3,
        wchar_t *a4,
        WCHAR *a5,
        WCHAR *pPrinterName,
        wchar_t *a7,
        wchar_t *a8,
        unsigned int a9,
        unsigned __int64 a10)
{
  char *v14; // rbx
  const EVENT_DESCRIPTOR *v15; // r14
  unsigned int v16; // ebx
  int v17; // eax
  int v18; // eax
  struct SplException::TSystemException *v20; // rdi
  __int64 v21; // [rsp+0h] [rbp-98h] BYREF
  int v22; // [rsp+50h] [rbp-48h]
  __int64 v23; // [rsp+58h] [rbp-40h] BYREF
  SplException::TSystemException *v24; // [rsp+60h] [rbp-38h] BYREF
  char v26; // [rsp+A8h] [rbp+10h]

  *((_DWORD *)this + 40) = a2;
  v14 = (char *)this + 224;
  *((_DWORD *)this + 56) = a2;
  v15 = (const EVENT_DESCRIPTOR *)((char *)this + 176);
  if ( EventEnabled(*((_QWORD *)this + 21), (PCEVENT_DESCRIPTOR)this + 11) )
  {
    *((_QWORD *)this + 26) = v14;
    *((_QWORD *)this + 27) = 4;
    EventWrite(*((_QWORD *)this + 21), v15, 1u, (PEVENT_DATA_DESCRIPTOR)this + 13);
    *((_BYTE *)this + 228) = 1;
  }
  if ( *((_DWORD *)this + 8) )
  {
    return (unsigned int)-2147417835;
  }
  else
  {
    *((_DWORD *)this + 8) = 1;
    v23 = 0;
    v17 = (**(__int64 (__fastcall ***)(SplPipeline::SplFilterPipelineCallObject *, GUID *, __int64 *))this)(
            this,
            &IID_ISynchronize,
            &v23);
    v16 = v17;
    v22 = v17;
    if ( v17 < 0 )
    {
      SplLogPipelineEvent(&MSG_PRINT_PIPELINE_COM_SIGNAL_FAILED, v17);
      ExitProcess(1u);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
    v26 = 0;
    try
    {
      SplPipeline::SplFilterPipelineCallObject::SetupPipeline(
        this,
        (const wchar_t *)a2,
        a3,
        a4,
        a5,
        pPrinterName,
        a7,
        a8,
        a9,
        a10);
    }
    catch ( SplException::TSystemException *v24 )
    {
      if ( !*((_BYTE *)this + 112) )
      {
        *((_BYTE *)this + 112) = 1;
        v26 = 1;
      }
      v20 = v24;
      if ( *((int *)this + 9) >= 0 )
        *((_DWORD *)this + 9) = SplException::SetErrorInfoFromException(
                                  v24,
                                  (struct SplException::TSystemException *)&v21);
      if ( SplException::gpfnExceptionLogger )
        SplException::gpfnExceptionLogger(v20);
      if ( v26 )
      {
        SplPipeline::SplFilterPipelineCallObject::CleanSpoolerHandles(this);
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
        v16 = v18;
        if ( v18 < 0 )
        {
          SplLogPipelineEvent(&MSG_PRINT_PIPELINE_COM_SIGNAL_FAILED, v18);
          ExitProcess(1u);
        }
      }
      else
      {
        v16 = v22;
      }
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  }
  return v16;
}

```

## disassembly

```asm
0x140010630  mov     [rsp+arg_10], rbx
0x140010635  mov     [rsp+arg_18], rsi
0x14001063a  mov     [rsp+arg_0], rcx
0x14001063f  push    rdi
0x140010640  push    r12
0x140010642  push    r13
0x140010644  push    r14
0x140010646  push    r15
0x140010648  sub     rsp, 70h
0x14001064c  mov     r12, r9
0x14001064f  mov     r13, r8
0x140010652  mov     r15d, edx
0x140010655  mov     rsi, rcx
0x140010658  mov     [rcx+0A0h], edx
0x14001065e  lea     rbx, [rcx+0E0h]
0x140010665  mov     [rbx], edx
0x140010667  lea     r14, [rcx+0B0h]
0x14001066e  mov     rdx, r14; EventDescriptor
0x140010671  mov     rcx, [rcx+0A8h]; RegHandle
0x140010678  call    cs:__imp_EventEnabled
0x14001067e  xor     edi, edi
0x140010680  test    al, al
0x140010682  jz      short loc_1400106B1
0x140010684  lea     r9, [rsi+0D0h]; UserData
0x14001068b  mov     [r9], rbx
0x14001068e  mov     qword ptr [r9+8], 4
0x140010696  lea     r8d, [rdi+1]; UserDataCount
0x14001069a  mov     rdx, r14; EventDescriptor
0x14001069d  mov     rcx, [rsi+0A8h]; RegHandle
0x1400106a4  call    cs:__imp_EventWrite
0x1400106aa  mov     byte ptr [rsi+0E4h], 1
0x1400106b1  cmp     [rsi+20h], edi
0x1400106b4  jz      short loc_1400106C0
0x1400106b6  mov     ebx, 80010115h
0x1400106bb  jmp     loc_1400107C3
0x1400106c0  mov     dword ptr [rsi+20h], 1
0x1400106c7  mov     [rsp+98h+var_40], rdi
0x1400106cc  mov     rax, [rsi]
0x1400106cf  lea     r8, [rsp+98h+var_40]
0x1400106d4  lea     rdx, IID_ISynchronize
0x1400106db  mov     rcx, rsi
0x1400106de  mov     rax, [rax]
0x1400106e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400106e6  mov     ebx, eax
0x1400106e8  mov     [rsp+98h+var_48], eax
0x1400106ec  test    eax, eax
0x1400106ee  js      loc_1400107DF
0x1400106f4  mov     rcx, [rsp+98h+var_40]
0x1400106f9  mov     rdx, [rcx]
0x1400106fc  mov     rax, [rdx+28h]
0x140010700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010705  mov     [rsp+98h+arg_8], dil
0x14001070d  mov     rax, [rsp+98h+arg_48]
0x140010715  mov     [rsp+98h+var_50], rax; unsigned __int64
0x14001071a  mov     eax, [rsp+98h+arg_40]
0x140010721  mov     [rsp+98h+var_58], eax; int
0x140010725  mov     rax, [rsp+98h+arg_38]
0x14001072d  mov     [rsp+98h+var_60], rax; wchar_t *
0x140010732  mov     rax, [rsp+98h+arg_30]
0x14001073a  mov     [rsp+98h+var_68], rax; wchar_t *
0x14001073f  mov     rax, [rsp+98h+arg_28]
0x140010747  mov     [rsp+98h+pPrinterName], rax; pPrinterName
0x14001074c  mov     rax, [rsp+98h+arg_20]
0x140010754  mov     [rsp+98h+var_78], rax; wchar_t *
0x140010759  mov     r9, r12; wchar_t *
0x14001075c  mov     r8, r13; wchar_t *
0x14001075f  mov     edx, r15d; unsigned int
0x140010762  mov     rcx, rsi; this
0x140010765  call    ?SetupPipeline@SplFilterPipelineCallObject@SplPipeline@@AEAAXKPEB_W00000H_K@Z; SplPipeline::SplFilterPipelineCallObject::SetupPipeline(ulong,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,unsigned __int64)
0x14001076a  nop
0x14001076b  jmp     short loc_1400107B9
0x14001076d  xor     edi, edi
0x14001076f  cmp     [rsp+98h+arg_8], dil
0x140010777  jz      short loc_1400107B5
0x140010779  mov     rcx, [rsp+98h+arg_0]; this
0x140010781  call    ?CleanSpoolerHandles@SplFilterPipelineCallObject@SplPipeline@@AEAAXXZ; SplPipeline::SplFilterPipelineCallObject::CleanSpoolerHandles(void)
0x140010786  mov     rcx, [rsp+98h+var_40]
0x14001078b  mov     rax, [rcx]
0x14001078e  mov     rax, [rax+20h]
0x140010792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010797  mov     ebx, eax
0x140010799  test    eax, eax
0x14001079b  jns     short loc_1400107B9
0x14001079d  mov     edx, eax; int
0x14001079f  lea     rcx, MSG_PRINT_PIPELINE_COM_SIGNAL_FAILED; struct _EVENT_DESCRIPTOR *
0x1400107a6  call    ?SplLogPipelineEvent@@YAXPEBU_EVENT_DESCRIPTOR@@J@Z; SplLogPipelineEvent(_EVENT_DESCRIPTOR const *,long)
0x1400107ab  lea     ecx, [rdi+1]; uExitCode
0x1400107ae  call    cs:__imp_ExitProcess
0x1400107b5  mov     ebx, [rsp+98h+var_48]
0x1400107b9  lea     rcx, [rsp+98h+var_40]
0x1400107be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400107c3  mov     eax, ebx
0x1400107c5  lea     r11, [rsp+98h+var_28]
0x1400107ca  mov     rbx, [r11+40h]
0x1400107ce  mov     rsi, [r11+48h]
0x1400107d2  mov     rsp, r11
0x1400107d5  pop     r15
0x1400107d7  pop     r14
0x1400107d9  pop     r13
0x1400107db  pop     r12
0x1400107dd  pop     rdi
0x1400107de  retn
0x1400107df  mov     edx, eax; int
0x1400107e1  lea     rcx, MSG_PRINT_PIPELINE_COM_SIGNAL_FAILED; struct _EVENT_DESCRIPTOR *
0x1400107e8  call    ?SplLogPipelineEvent@@YAXPEBU_EVENT_DESCRIPTOR@@J@Z; SplLogPipelineEvent(_EVENT_DESCRIPTOR const *,long)
0x1400107ed  mov     ecx, 1; uExitCode
0x1400107f2  call    cs:__imp_ExitProcess
```
