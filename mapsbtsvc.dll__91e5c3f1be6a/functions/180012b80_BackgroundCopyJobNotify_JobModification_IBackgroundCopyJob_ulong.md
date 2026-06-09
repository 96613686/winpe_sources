# BackgroundCopyJobNotify::JobModification(IBackgroundCopyJob *,ulong)

- ea: `0x180012b80`
- end: `0x180012bf7`
- name: `?JobModification@BackgroundCopyJobNotify@@UEAAJPEAUIBackgroundCopyJob@@K@Z`
- size: `119`
- prototype: `__int64 __fastcall(BackgroundCopyJobNotify *this, struct IBackgroundCopyJob *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180005b9c`
- `0x18000d77c`
- `0x180011130`
- `0x180012b80`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012bbc`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x180012bbc`

## string_xrefs

- `0x180012bad`: `BackgroundCopyJobNotify::JobModification`

## pseudocode

```c
__int64 __fastcall BackgroundCopyJobNotify::JobModification(
        BackgroundCopyJobNotify *this,
        struct IBackgroundCopyJob *a2)
{
  int v3; // eax
  std::_Ref_count_base *v4; // rbx
  MapsBackgroundTransferJob *v6; // [rsp+20h] [rbp-18h] BYREF
  std::_Ref_count_base *v7; // [rsp+28h] [rbp-10h]

  std::weak_ptr<MapsBackgroundTransferJob>::lock((char *)this + 8, &v6);
  if ( v6 )
  {
    v3 = MapsBackgroundTransferJob::PollState(v6);
    if ( v3 < 0 )
      ZTraceReportPropagation(v3, "BackgroundCopyJobNotify::JobModification", 119, this);
  }
  v4 = v7;
  if ( v7 && _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v4)(v4);
    std::_Ref_count_base::_Decwref(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180012b80  push    rbx
0x180012b82  sub     rsp, 30h
0x180012b86  mov     rbx, rcx
0x180012b89  lea     rdx, [rsp+38h+var_18]
0x180012b8e  add     rcx, 8
0x180012b92  call    ?lock@?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEBA?AV?$shared_ptr@VMapsBackgroundTransferJob@@@2@XZ; std::weak_ptr<MapsBackgroundTransferJob>::lock(void)
0x180012b97  mov     rcx, [rsp+38h+var_18]; this
0x180012b9c  test    rcx, rcx
0x180012b9f  jz      short loc_180012BC2
0x180012ba1  call    ?PollState@MapsBackgroundTransferJob@@QEAAJXZ; MapsBackgroundTransferJob::PollState(void)
0x180012ba6  test    eax, eax
0x180012ba8  jns     short loc_180012BC2
0x180012baa  mov     r9, rbx
0x180012bad  lea     rdx, aBackgroundcopy_2; "BackgroundCopyJobNotify::JobModificatio"...
0x180012bb4  mov     r8d, 77h ; 'w'
0x180012bba  mov     ecx, eax
0x180012bbc  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x180012bc2  mov     rbx, [rsp+38h+var_10]
0x180012bc7  test    rbx, rbx
0x180012bca  jz      short loc_180012BEF
0x180012bcc  or      eax, 0FFFFFFFFh
0x180012bcf  lock xadd [rbx+8], eax
0x180012bd4  cmp     eax, 1
0x180012bd7  jnz     short loc_180012BEF
0x180012bd9  mov     rax, [rbx]
0x180012bdc  mov     rcx, rbx
0x180012bdf  mov     rax, [rax]
0x180012be2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012be7  mov     rcx, rbx; this
0x180012bea  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180012bef  xor     eax, eax
0x180012bf1  add     rsp, 30h
0x180012bf5  pop     rbx
0x180012bf6  retn
```
