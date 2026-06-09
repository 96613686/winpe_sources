# SplPipeline::SplFilterPipelineCallObject::Finish_Print(long *)

- ea: `0x140010d60`
- end: `0x140010e51`
- name: `?Finish_Print@SplFilterPipelineCallObject@SplPipeline@@UEAAJPEAJ@Z`
- size: `241`
- prototype: `__int64 __fastcall(SplPipeline::SplFilterPipelineCallObject *__hidden this, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000fe88`
- `0x140010d60`
- `0x140056e3c`
- `0x140063010`

## import_xrefs

- `ADVAPI32!EventEnabled` at `0x140010e02`
- `ADVAPI32!EventEnabled` at `0x140010e02`
- `ADVAPI32!EventWrite` at `0x140010e23`
- `ADVAPI32!EventWrite` at `0x140010e23`
- `KERNEL32!ExitProcess` at `0x140010e4a`
- `KERNEL32!ExitProcess` at `0x140010e4a`

## pseudocode

```c
__int64 __fastcall SplPipeline::SplFilterPipelineCallObject::Finish_Print(
        SplPipeline::SplFilterPipelineCallObject *this,
        int *a2)
{
  unsigned int v5; // edi
  int v6; // eax
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147500035LL;
  if ( *((_DWORD *)this + 8) )
  {
    v7 = 0;
    v6 = (**(__int64 (__fastcall ***)(SplPipeline::SplFilterPipelineCallObject *, GUID *, __int64 *))this)(
           this,
           &IID_ISynchronize,
           &v7);
    v5 = v6;
    if ( v6 < 0 )
    {
      SplLogPipelineEvent(&MSG_PRINT_PIPELINE_COM_QI_SIGNAL_FAILED, v6);
      ExitProcess(1u);
    }
    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 24LL))(v7, 0, 0xFFFFFFFFLL);
    *a2 = *((_DWORD *)this + 9);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v7);
  }
  else
  {
    v5 = -2147417833;
  }
  if ( *((_BYTE *)this + 228) )
  {
    if ( EventEnabled(*((_QWORD *)this + 21), (PCEVENT_DESCRIPTOR)this + 12) )
    {
      EventWrite(*((_QWORD *)this + 21), (PCEVENT_DESCRIPTOR)this + 12, 1u, (PEVENT_DATA_DESCRIPTOR)this + 13);
      *((_BYTE *)this + 228) = 0;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x140010d60  mov     [rsp+arg_0], rbx
0x140010d65  mov     [rsp+arg_10], rsi
0x140010d6a  push    rdi
0x140010d6b  sub     rsp, 20h
0x140010d6f  mov     rsi, rdx
0x140010d72  mov     rbx, rcx
0x140010d75  test    rdx, rdx
0x140010d78  jnz     short loc_140010D8F
0x140010d7a  mov     eax, 80004003h
0x140010d7f  mov     rbx, [rsp+28h+arg_0]
0x140010d84  mov     rsi, [rsp+28h+arg_10]
0x140010d89  add     rsp, 20h
0x140010d8d  pop     rdi
0x140010d8e  retn
0x140010d8f  cmp     dword ptr [rcx+20h], 0
0x140010d93  jnz     short loc_140010D9C
0x140010d95  mov     edi, 80010117h
0x140010d9a  jmp     short loc_140010DE8
0x140010d9c  mov     [rsp+28h+arg_8], 0
0x140010da5  mov     rax, [rcx]
0x140010da8  lea     r8, [rsp+28h+arg_8]
0x140010dad  lea     rdx, IID_ISynchronize
0x140010db4  mov     rax, [rax]
0x140010db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dbc  mov     edi, eax
0x140010dbe  test    eax, eax
0x140010dc0  js      short loc_140010E37
0x140010dc2  mov     rcx, [rsp+28h+arg_8]
0x140010dc7  mov     rdx, [rcx]
0x140010dca  mov     rax, [rdx+18h]
0x140010dce  or      r8d, 0FFFFFFFFh
0x140010dd2  xor     edx, edx
0x140010dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010dd9  mov     ecx, [rbx+24h]
0x140010ddc  mov     [rsi], ecx
0x140010dde  lea     rcx, [rsp+28h+arg_8]
0x140010de3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140010de8  cmp     byte ptr [rbx+0E4h], 0
0x140010def  jz      short loc_140010E30
0x140010df1  lea     rsi, [rbx+0C0h]
0x140010df8  mov     rdx, rsi; EventDescriptor
0x140010dfb  mov     rcx, [rbx+0A8h]; RegHandle
0x140010e02  call    cs:__imp_EventEnabled
0x140010e08  test    al, al
0x140010e0a  jz      short loc_140010E30
0x140010e0c  lea     r9, [rbx+0D0h]; UserData
0x140010e13  mov     r8d, 1; UserDataCount
0x140010e19  mov     rdx, rsi; EventDescriptor
0x140010e1c  mov     rcx, [rbx+0A8h]; RegHandle
0x140010e23  call    cs:__imp_EventWrite
0x140010e29  mov     byte ptr [rbx+0E4h], 0
0x140010e30  mov     eax, edi
0x140010e32  jmp     loc_140010D7F
0x140010e37  mov     edx, eax; int
0x140010e39  lea     rcx, MSG_PRINT_PIPELINE_COM_QI_SIGNAL_FAILED; struct _EVENT_DESCRIPTOR *
0x140010e40  call    ?SplLogPipelineEvent@@YAXPEBU_EVENT_DESCRIPTOR@@J@Z; SplLogPipelineEvent(_EVENT_DESCRIPTOR const *,long)
0x140010e45  mov     ecx, 1; uExitCode
0x140010e4a  call    cs:__imp_ExitProcess
```
