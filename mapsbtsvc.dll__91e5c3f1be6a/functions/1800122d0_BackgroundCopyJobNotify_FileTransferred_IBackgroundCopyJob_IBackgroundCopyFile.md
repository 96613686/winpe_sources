# BackgroundCopyJobNotify::FileTransferred(IBackgroundCopyJob *,IBackgroundCopyFile *)

- ea: `0x1800122d0`
- end: `0x180012405`
- name: `?FileTransferred@BackgroundCopyJobNotify@@UEAAJPEAUIBackgroundCopyJob@@PEAUIBackgroundCopyFile@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(BackgroundCopyJobNotify *this, struct IBackgroundCopyJob *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002900`
- `0x180003458`
- `0x180009860`
- `0x180012230`
- `0x1800122d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012395`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001238b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18001238b`
- `ZTrace_Maps!ZTraceHelper` at `0x180012378`
- `ZTrace_Maps!ZTraceHelper` at `0x180012378`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800123e3`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x1800123e3`

## string_xrefs

- `0x18001236c`: `BackgroundCopyJobNotify::FileTransferred`
- `0x1800123dc`: `BackgroundCopyJobNotify::FileTransferred`
- `0x180012352`: `File transferred | ThreadParam: %p`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::FileTransferred(
        BackgroundCopyJobNotify *this,
        struct IBackgroundCopyJob *a2,
        struct IUnknown *a3)
{
  struct IUnknown **v5; // rax
  struct IUnknown **v6; // rbx
  signed int LastError; // eax
  int v8; // r8d
  int v9; // ecx
  struct IUnknown **v11; // [rsp+58h] [rbp+20h] BYREF

  v5 = (struct IUnknown **)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v11 = 0;
    v8 = 136;
    v9 = -2147024882;
LABEL_12:
    ZTraceReportOrigination(v9, "BackgroundCopyJobNotify::FileTransferred", v8, this);
    goto LABEL_13;
  }
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  *(_DWORD *)v5 = 1;
  v11 = v5;
  if ( v5[1] != a3 )
    ATL::AtlComPtrAssign(v5 + 1, a3);
  std::weak_ptr<MapsBackgroundTransferJob>::operator=<MapsBackgroundTransferJob,0>(v6 + 3, (char *)this + 8);
  ZTraceHelper(5, "BackgroundCopyJobNotify::FileTransferred", 142, this, "File transferred | ThreadParam: %p", v6);
  if ( !QueueUserWorkItem(BackgroundCopyJobNotify::HandleJobCallbackThreadProc, v6, 0) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v8 = 147;
    v9 = LastError;
    goto LABEL_12;
  }
  v11 = 0;
LABEL_13:
  std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800122d0  mov     [rsp+arg_0], rbx
0x1800122d5  mov     [rsp+arg_8], rsi
0x1800122da  push    rdi
0x1800122db  sub     rsp, 30h
0x1800122df  mov     rdi, rcx
0x1800122e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800122e9  mov     ecx, 28h ; '('; unsigned __int64
0x1800122ee  mov     rsi, r8
0x1800122f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800122f6  mov     rbx, rax
0x1800122f9  test    rax, rax
0x1800122fc  jz      loc_1800123C5
0x180012302  mov     qword ptr [rax], 0
0x180012309  lea     rcx, [rax+8]; struct IUnknown **
0x18001230d  mov     qword ptr [rax+8], 0
0x180012315  mov     qword ptr [rax+10h], 0
0x18001231d  mov     qword ptr [rax+18h], 0
0x180012325  mov     qword ptr [rax+20h], 0
0x18001232d  mov     dword ptr [rax], 1
0x180012333  mov     [rsp+38h+arg_18], rax
0x180012338  cmp     [rcx], rsi
0x18001233b  jz      short loc_180012345
0x18001233d  mov     rdx, rsi; struct IUnknown *
0x180012340  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180012345  lea     rdx, [rdi+8]
0x180012349  lea     rcx, [rbx+18h]
0x18001234d  call    ??$?4VMapsBackgroundTransferJob@@$0A@@?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMapsBackgroundTransferJob@@@1@@Z; std::weak_ptr<MapsBackgroundTransferJob>::operator=<MapsBackgroundTransferJob,0>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x180012352  lea     rax, aFileTransferre; "File transferred | ThreadParam: %p"
0x180012359  mov     [rsp+38h+var_10], rbx
0x18001235e  mov     r9, rdi
0x180012361  mov     [rsp+38h+var_18], rax
0x180012366  mov     r8d, 8Eh
0x18001236c  lea     rdx, aBackgroundcopy_0; "BackgroundCopyJobNotify::FileTransferre"...
0x180012373  mov     ecx, 5
0x180012378  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001237e  xor     r8d, r8d; Flags
0x180012381  lea     rcx, ?HandleJobCallbackThreadProc@BackgroundCopyJobNotify@@CAKPEAX@Z; Function
0x180012388  mov     rdx, rbx; Context
0x18001238b  call    cs:__imp_QueueUserWorkItem
0x180012391  test    eax, eax
0x180012393  jnz     short loc_1800123BA
0x180012395  call    cs:__imp_GetLastError
0x18001239b  test    eax, eax
0x18001239d  jz      short loc_1800123AB
0x18001239f  jle     short loc_1800123B0
0x1800123a1  movzx   eax, ax
0x1800123a4  or      eax, 80070000h
0x1800123a9  jmp     short loc_1800123B0
0x1800123ab  mov     eax, 80390004h
0x1800123b0  mov     r8d, 93h
0x1800123b6  mov     ecx, eax
0x1800123b8  jmp     short loc_1800123D9
0x1800123ba  mov     [rsp+38h+arg_18], 0
0x1800123c3  jmp     short loc_1800123E9
0x1800123c5  mov     [rsp+38h+arg_18], 0
0x1800123ce  mov     r8d, 88h
0x1800123d4  mov     ecx, 8007000Eh
0x1800123d9  mov     r9, rdi
0x1800123dc  lea     rdx, aBackgroundcopy_0; "BackgroundCopyJobNotify::FileTransferre"...
0x1800123e3  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x1800123e9  lea     rcx, [rsp+38h+arg_18]
0x1800123ee  call    ??1?$unique_ptr@UWorkerThreadParam@BackgroundCopyJobNotify@@U?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@@std@@QEAA@XZ; std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(void)
0x1800123f3  mov     rbx, [rsp+38h+arg_0]
0x1800123f8  xor     eax, eax
0x1800123fa  mov     rsi, [rsp+38h+arg_8]
0x1800123ff  add     rsp, 30h
0x180012403  pop     rdi
0x180012404  retn
```
