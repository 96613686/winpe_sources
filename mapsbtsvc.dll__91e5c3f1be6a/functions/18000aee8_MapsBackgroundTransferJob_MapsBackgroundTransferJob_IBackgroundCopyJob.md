# MapsBackgroundTransferJob::MapsBackgroundTransferJob(IBackgroundCopyJob *)

- ea: `0x18000aee8`
- end: `0x18000afb8`
- name: `??0MapsBackgroundTransferJob@@AEAA@PEAUIBackgroundCopyJob@@@Z`
- size: `208`
- prototype: `MapsBackgroundTransferJob *__fastcall(MapsBackgroundTransferJob *__hidden this, struct IBackgroundCopyJob *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c834`

## callees

- `0x180004198`
- `0x18000ad4c`
- `0x18000ae34`
- `0x18000ae88`
- `0x18000aeb8`
- `0x18000aee8`
- `0x180015010`

## pseudocode

```c
MapsBackgroundTransferJob *__fastcall MapsBackgroundTransferJob::MapsBackgroundTransferJob(
        MapsBackgroundTransferJob *this,
        struct IBackgroundCopyJob *a2)
{
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &MapsBackgroundTransferJob::`vftable';
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
    ((void (__fastcall *)(struct IBackgroundCopyJob *))a2->lpVtbl->AddRef)(a2);
  *((_QWORD *)this + 4) = 0;
  std::wstring::wstring((char *)this + 48);
  std::atomic<enum MAPSBTSVC_JOB_STATE>::atomic<enum MAPSBTSVC_JOB_STATE>((char *)this + 80);
  std::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>((char *)this + 608);
  std::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>((__int64)this + 672);
  *((_DWORD *)this + 184) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 94) = 0;
  *((_QWORD *)this + 95) = 0;
  *((_DWORD *)this + 194) = 0;
  *((_BYTE *)this + 780) = 0;
  ATL::CComAutoCriticalSection::CComAutoCriticalSection((MapsBackgroundTransferJob *)((char *)this + 784));
  *((_QWORD *)this + 96) = 0;
  return this;
}

```

## disassembly

```asm
0x18000aee8  mov     [rsp+arg_0], rcx
0x18000aeed  push    rbx
0x18000aeee  sub     rsp, 20h
0x18000aef2  mov     rbx, rcx
0x18000aef5  mov     qword ptr [rcx+8], 0
0x18000aefd  mov     qword ptr [rcx+10h], 0
0x18000af05  lea     rax, ??_7MapsBackgroundTransferJob@@6B@; const MapsBackgroundTransferJob::`vftable'
0x18000af0c  mov     [rcx], rax
0x18000af0f  mov     [rcx+18h], rdx
0x18000af13  test    rdx, rdx
0x18000af16  jz      short loc_18000AF28
0x18000af18  mov     rax, [rdx]
0x18000af1b  mov     rcx, rdx
0x18000af1e  mov     rax, [rax+8]
0x18000af22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af27  nop
0x18000af28  mov     qword ptr [rbx+20h], 0
0x18000af30  lea     rcx, [rbx+30h]
0x18000af34  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000af39  nop
0x18000af3a  lea     rcx, [rbx+50h]
0x18000af3e  call    ??0?$atomic@W4MAPSBTSVC_JOB_STATE@@@std@@QEAA@W4MAPSBTSVC_JOB_STATE@@@Z; std::atomic<MAPSBTSVC_JOB_STATE>::atomic<MAPSBTSVC_JOB_STATE>(MAPSBTSVC_JOB_STATE)
0x18000af43  lea     rcx, [rbx+260h]
0x18000af4a  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@URequestContext@MapsBackgroundTransferJob@@V?$deque@URequestContext@MapsBackgroundTransferJob@@V?$allocator@URequestContext@MapsBackgroundTransferJob@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>::unordered_map<std::wstring,std::queue<MapsBackgroundTransferJob::RequestContext>>(void)
0x18000af4f  nop
0x18000af50  lea     rcx, [rbx+2A0h]
0x18000af57  call    ??0?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::unordered_map<std::wstring,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(void)
0x18000af5c  mov     dword ptr [rbx+2E0h], 0
0x18000af66  mov     qword ptr [rbx+2E8h], 0
0x18000af71  mov     qword ptr [rbx+2F0h], 0
0x18000af7c  mov     qword ptr [rbx+2F8h], 0
0x18000af87  mov     dword ptr [rbx+308h], 0
0x18000af91  mov     byte ptr [rbx+30Ch], 0
0x18000af98  lea     rcx, [rbx+310h]; this
0x18000af9f  call    ??0CComAutoCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoCriticalSection::CComAutoCriticalSection(void)
0x18000afa4  mov     qword ptr [rbx+300h], 0
0x18000afaf  mov     rax, rbx
0x18000afb2  add     rsp, 20h
0x18000afb6  pop     rbx
0x18000afb7  retn
```
