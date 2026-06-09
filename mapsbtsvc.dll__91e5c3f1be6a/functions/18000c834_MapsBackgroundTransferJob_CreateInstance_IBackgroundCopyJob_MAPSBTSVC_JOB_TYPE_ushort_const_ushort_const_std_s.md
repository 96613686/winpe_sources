# MapsBackgroundTransferJob::CreateInstance(IBackgroundCopyJob *,MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *,std::shared_ptr<MapsBackgroundTransferJob> *)

- ea: `0x18000c834`
- end: `0x18000c996`
- name: `?CreateInstance@MapsBackgroundTransferJob@@SAJPEAUIBackgroundCopyJob@@W4MAPSBTSVC_JOB_TYPE@@PEBG2PEAV?$shared_ptr@VMapsBackgroundTransferJob@@@std@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct IBackgroundCopyJob *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180002900`
- `0x1800047ec`
- `0x180005b9c`
- `0x180009754`
- `0x180009834`
- `0x18000aee8`
- `0x18000c834`
- `0x18000cfec`
- `0x180015010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c8ee`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000c8ee`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c942`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000c942`

## string_xrefs

- `0x18000c8e2`: `MapsBackgroundTransferJob::CreateInstance`
- `0x18000c939`: `MapsBackgroundTransferJob::CreateInstance`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::CreateInstance(
        struct IBackgroundCopyJob *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  MapsBackgroundTransferJob *v7; // rax
  __int64 v8; // rax
  MapsBackgroundTransferJob *v9; // rsi
  volatile signed __int32 *v10; // rdi
  std::_Ref_count_base *v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int v14; // ebx
  MapsBackgroundTransferJob *v16; // [rsp+30h] [rbp-58h] BYREF
  std::_Ref_count_base *v17; // [rsp+38h] [rbp-50h]
  _OWORD v18[4]; // [rsp+40h] [rbp-48h] BYREF

  v18[0] = 0;
  v7 = (MapsBackgroundTransferJob *)operator new(0x338u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v7;
  if ( v7 )
    v7 = MapsBackgroundTransferJob::MapsBackgroundTransferJob(v7, a1);
  v8 = std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(&v16, v7);
  v9 = *(MapsBackgroundTransferJob **)v8;
  *(_QWORD *)v8 = 0;
  *(_QWORD *)&v18[0] = v9;
  v10 = *(volatile signed __int32 **)(v8 + 8);
  *(_QWORD *)(v8 + 8) = 0;
  *((_QWORD *)&v18[0] + 1) = v10;
  v11 = v17;
  if ( v17 && _InterlockedExchangeAdd((volatile signed __int32 *)v17 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(std::_Ref_count_base *))v11)(v11);
    std::_Ref_count_base::_Decwref(v11);
  }
  if ( v9 )
  {
    std::weak_ptr<MapsBackgroundTransferJob>::weak_ptr<MapsBackgroundTransferJob>(&v16, v18);
    v14 = MapsBackgroundTransferJob::Initialize(v9, a4);
    if ( v17 )
      std::_Ref_count_base::_Decwref(v17);
    if ( v14 >= 0 )
    {
      v13 = 0;
      std::shared_ptr<MapsBackgroundTransferJob>::operator=(a5, v18);
      goto LABEL_14;
    }
    v12 = ZTraceReportPropagationNoThis(v14, "MapsBackgroundTransferJob::CreateInstance", 159);
  }
  else
  {
    v12 = ZTraceReportOriginationNoThis(-2147024882, "MapsBackgroundTransferJob::CreateInstance", 157);
  }
  v13 = v12;
LABEL_14:
  if ( v10 && _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v10);
  }
  return v13;
}

```

## disassembly

```asm
0x18000c834  push    rbx
0x18000c836  push    rbp
0x18000c837  push    rsi
0x18000c838  push    rdi
0x18000c839  push    r14
0x18000c83b  push    r15
0x18000c83d  sub     rsp, 58h
0x18000c841  mov     rbp, r9
0x18000c844  mov     r14, r8
0x18000c847  mov     r15d, edx
0x18000c84a  mov     rbx, rcx
0x18000c84d  xorps   xmm0, xmm0
0x18000c850  movdqu  [rsp+88h+var_48], xmm0
0x18000c856  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000c85d  mov     ecx, 338h; unsigned __int64
0x18000c862  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000c867  mov     [rsp+88h+var_58], rax
0x18000c86c  test    rax, rax
0x18000c86f  jz      short loc_18000C87D
0x18000c871  mov     rdx, rbx; struct IBackgroundCopyJob *
0x18000c874  mov     rcx, rax; this
0x18000c877  call    ??0MapsBackgroundTransferJob@@AEAA@PEAUIBackgroundCopyJob@@@Z; MapsBackgroundTransferJob::MapsBackgroundTransferJob(IBackgroundCopyJob *)
0x18000c87c  nop
0x18000c87d  mov     rdx, rax
0x18000c880  lea     rcx, [rsp+88h+var_58]
0x18000c885  call    ??$?0VMapsBackgroundTransferJob@@$0A@@?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@PEAVMapsBackgroundTransferJob@@@Z; std::shared_ptr<MapsBackgroundTransferJob>::shared_ptr<MapsBackgroundTransferJob>(MapsBackgroundTransferJob *)
0x18000c88a  mov     rsi, [rax]
0x18000c88d  mov     qword ptr [rax], 0
0x18000c894  mov     qword ptr [rsp+88h+var_48], rsi
0x18000c899  mov     rdi, [rax+8]
0x18000c89d  mov     qword ptr [rax+8], 0
0x18000c8a5  mov     qword ptr [rsp+88h+var_48+8], rdi
0x18000c8aa  mov     rbx, [rsp+88h+var_50]
0x18000c8af  test    rbx, rbx
0x18000c8b2  jz      short loc_18000C8D7
0x18000c8b4  or      eax, 0FFFFFFFFh
0x18000c8b7  lock xadd [rbx+8], eax
0x18000c8bc  cmp     eax, 1
0x18000c8bf  jnz     short loc_18000C8D7
0x18000c8c1  mov     rax, [rbx]
0x18000c8c4  mov     rcx, rbx
0x18000c8c7  mov     rax, [rax]
0x18000c8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8cf  mov     rcx, rbx; this
0x18000c8d2  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000c8d7  test    rsi, rsi
0x18000c8da  jnz     short loc_18000C8F8
0x18000c8dc  mov     r8d, 9Dh
0x18000c8e2  lea     rdx, aMapsbackground_19; "MapsBackgroundTransferJob::CreateInstan"...
0x18000c8e9  mov     ecx, 8007000Eh
0x18000c8ee  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000c8f4  mov     ebx, eax
0x18000c8f6  jmp     short loc_18000C95F
0x18000c8f8  lea     rdx, [rsp+88h+var_48]
0x18000c8fd  lea     rcx, [rsp+88h+var_58]
0x18000c902  call    ??0?$weak_ptr@VMapsBackgroundTransferJob@@@std@@QEAA@AEBV01@@Z; std::weak_ptr<MapsBackgroundTransferJob>::weak_ptr<MapsBackgroundTransferJob>(std::weak_ptr<MapsBackgroundTransferJob> const &)
0x18000c907  nop
0x18000c908  mov     [rsp+88h+var_68], rbp; __int64
0x18000c90d  mov     r9, r14
0x18000c910  mov     r8d, r15d
0x18000c913  mov     rdx, rax
0x18000c916  mov     rcx, rsi; this
0x18000c919  call    ?Initialize@MapsBackgroundTransferJob@@AEAAJAEBV?$weak_ptr@VMapsBackgroundTransferJob@@@std@@W4MAPSBTSVC_JOB_TYPE@@PEBG2@Z; MapsBackgroundTransferJob::Initialize(std::weak_ptr<MapsBackgroundTransferJob> const &,MAPSBTSVC_JOB_TYPE,ushort const *,ushort const *)
0x18000c91e  mov     ebx, eax
0x18000c920  mov     rcx, [rsp+88h+var_50]; this
0x18000c925  test    rcx, rcx
0x18000c928  jz      short loc_18000C92F
0x18000c92a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000c92f  test    ebx, ebx
0x18000c931  jns     short loc_18000C94A
0x18000c933  mov     r8d, 9Fh
0x18000c939  lea     rdx, aMapsbackground_19; "MapsBackgroundTransferJob::CreateInstan"...
0x18000c940  mov     ecx, ebx
0x18000c942  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000c948  jmp     short loc_18000C8F4
0x18000c94a  xor     ebx, ebx
0x18000c94c  lea     rdx, [rsp+88h+var_48]
0x18000c951  mov     rcx, [rsp+88h+arg_20]
0x18000c959  call    ??4?$shared_ptr@VMapsBackgroundTransferJob@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<MapsBackgroundTransferJob>::operator=(std::shared_ptr<MapsBackgroundTransferJob> const &)
0x18000c95e  nop
0x18000c95f  test    rdi, rdi
0x18000c962  jz      short loc_18000C987
0x18000c964  or      eax, 0FFFFFFFFh
0x18000c967  lock xadd [rdi+8], eax
0x18000c96c  cmp     eax, 1
0x18000c96f  jnz     short loc_18000C987
0x18000c971  mov     rax, [rdi]
0x18000c974  mov     rcx, rdi
0x18000c977  mov     rax, [rax]
0x18000c97a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c97f  mov     rcx, rdi; this
0x18000c982  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18000c987  mov     eax, ebx
0x18000c989  add     rsp, 58h
0x18000c98d  pop     r15
0x18000c98f  pop     r14
0x18000c991  pop     rdi
0x18000c992  pop     rsi
0x18000c993  pop     rbp
0x18000c994  pop     rbx
0x18000c995  retn
```
