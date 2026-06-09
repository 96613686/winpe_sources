# BackgroundCopyJobNotify::JobError(IBackgroundCopyJob *,IBackgroundCopyError *)

- ea: `0x180012a70`
- end: `0x180012b79`
- name: `?JobError@BackgroundCopyJobNotify@@UEAAJPEAUIBackgroundCopyJob@@PEAUIBackgroundCopyError@@@Z`
- size: `265`
- prototype: `__int64 __fastcall(BackgroundCopyJobNotify *this, struct IBackgroundCopyJob *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002900`
- `0x180003458`
- `0x180009860`
- `0x180012230`
- `0x180012a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b09`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180012aff`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180012aff`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180012b57`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x180012b57`

## string_xrefs

- `0x180012b50`: `BackgroundCopyJobNotify::JobError`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::JobError(
        BackgroundCopyJobNotify *this,
        struct IBackgroundCopyJob *a2,
        struct IUnknown *a3)
{
  struct IUnknown **v5; // rax
  struct IUnknown **v6; // rbx
  signed int LastError; // eax
  int v8; // r8d
  int v9; // ecx
  struct IUnknown **v11; // [rsp+48h] [rbp+20h] BYREF

  v5 = (struct IUnknown **)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v5;
  if ( !v5 )
  {
    v11 = 0;
    v8 = 92;
    v9 = -2147024882;
LABEL_12:
    ZTraceReportOrigination(v9, "BackgroundCopyJobNotify::JobError", v8, this);
    goto LABEL_13;
  }
  *v5 = 0;
  v5[1] = 0;
  v5[2] = 0;
  v5[3] = 0;
  v5[4] = 0;
  *(_DWORD *)v5 = 0;
  v11 = v5;
  if ( v5[2] != a3 )
    ATL::AtlComPtrAssign(v5 + 2, a3);
  std::weak_ptr<MapsBackgroundTransferJob>::operator=<MapsBackgroundTransferJob,0>(v6 + 3, (char *)this + 8);
  if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)BackgroundCopyJobNotify::HandleJobCallbackThreadProc, v6, 0) )
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
    v8 = 100;
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
0x180012a70  mov     [rsp+arg_0], rbx
0x180012a75  mov     [rsp+arg_8], rsi
0x180012a7a  push    rdi
0x180012a7b  sub     rsp, 20h
0x180012a7f  mov     rsi, rcx
0x180012a82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012a89  mov     ecx, 28h ; '('; unsigned __int64
0x180012a8e  mov     rdi, r8
0x180012a91  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012a96  mov     rbx, rax
0x180012a99  test    rax, rax
0x180012a9c  jz      loc_180012B39
0x180012aa2  mov     qword ptr [rax], 0
0x180012aa9  lea     rcx, [rax+10h]; struct IUnknown **
0x180012aad  mov     qword ptr [rax+8], 0
0x180012ab5  mov     qword ptr [rax+10h], 0
0x180012abd  mov     qword ptr [rax+18h], 0
0x180012ac5  mov     qword ptr [rax+20h], 0
0x180012acd  mov     dword ptr [rax], 0
0x180012ad3  mov     [rsp+28h+arg_18], rax
0x180012ad8  cmp     [rcx], rdi
0x180012adb  jz      short loc_180012AE5
0x180012add  mov     rdx, rdi; struct IUnknown *
0x180012ae0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180012ae5  lea     rdx, [rsi+8]
0x180012ae9  lea     rcx, [rbx+18h]
0x180012aed  call    ??$?4VMapsBackgroundTransferJob@@$0A@@?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEAAAEAV01@AEBV?$shared_ptr@VMapsBackgroundTransferJob@@@1@@Z; std::weak_ptr<MapsBackgroundTransferJob>::operator=<MapsBackgroundTransferJob,0>(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x180012af2  xor     r8d, r8d; Flags
0x180012af5  lea     rcx, ?HandleJobCallbackThreadProc@BackgroundCopyJobNotify@@CAKPEAX@Z; Function
0x180012afc  mov     rdx, rbx; Context
0x180012aff  call    cs:__imp_QueueUserWorkItem
0x180012b05  test    eax, eax
0x180012b07  jnz     short loc_180012B2E
0x180012b09  call    cs:__imp_GetLastError
0x180012b0f  test    eax, eax
0x180012b11  jz      short loc_180012B1F
0x180012b13  jle     short loc_180012B24
0x180012b15  movzx   eax, ax
0x180012b18  or      eax, 80070000h
0x180012b1d  jmp     short loc_180012B24
0x180012b1f  mov     eax, 80390004h
0x180012b24  mov     r8d, 64h ; 'd'
0x180012b2a  mov     ecx, eax
0x180012b2c  jmp     short loc_180012B4D
0x180012b2e  mov     [rsp+28h+arg_18], 0
0x180012b37  jmp     short loc_180012B5D
0x180012b39  mov     [rsp+28h+arg_18], 0
0x180012b42  mov     r8d, 5Ch ; '\'
0x180012b48  mov     ecx, 8007000Eh
0x180012b4d  mov     r9, rsi
0x180012b50  lea     rdx, aBackgroundcopy_3; "BackgroundCopyJobNotify::JobError"
0x180012b57  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x180012b5d  lea     rcx, [rsp+28h+arg_18]
0x180012b62  call    ??1?$unique_ptr@UWorkerThreadParam@BackgroundCopyJobNotify@@U?$default_delete@UWorkerThreadParam@BackgroundCopyJobNotify@@@std@@@std@@QEAA@XZ; std::unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>::~unique_ptr<BackgroundCopyJobNotify::WorkerThreadParam>(void)
0x180012b67  mov     rbx, [rsp+28h+arg_0]
0x180012b6c  xor     eax, eax
0x180012b6e  mov     rsi, [rsp+28h+arg_8]
0x180012b73  add     rsp, 20h
0x180012b77  pop     rdi
0x180012b78  retn
```
