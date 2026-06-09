# Microsoft::WRL::Details::Make<FveEasNetworkStatusChangeNotificationHandler,IFveEasNetworkStatusChangeAction * * &,Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> &>(IFveEasNetworkStatusChangeAction * * &,Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> &)

- ea: `0x1800152a4`
- end: `0x180015340`
- name: `??$Make@VFveEasNetworkStatusChangeNotificationHandler@@AEAPEAPEAVIFveEasNetworkStatusChangeAction@@AEAV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VFveEasNetworkStatusChangeNotificationHandler@@@12@AEAPEAPEAVIFveEasNetworkStatusChangeAction@@AEAV?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@12@@Z`
- size: `156`
- prototype: `__int64 *__fastcall(__int64 *, _QWORD *, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180018620`

## callees

- `0x180002bc4`
- `0x1800152a4`
- `0x18001535c`
- `0x180015400`
- `0x18002d010`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::Details::Make<FveEasNetworkStatusChangeNotificationHandler,IFveEasNetworkStatusChangeAction * * &,Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics> &>(
        __int64 *a1,
        _QWORD *a2,
        void **a3)
{
  void *v6; // rdi
  void *v7; // rcx
  __int64 v8; // rdi
  void *v10; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v6 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v6;
  if ( v6 )
  {
    v7 = *a3;
    v10 = v7;
    if ( v7 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
    v8 = FveEasNetworkStatusChangeNotificationHandler::FveEasNetworkStatusChangeNotificationHandler(v6, *a2, &v10);
    if ( *a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v8;
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<FveEasNetworkStatusChangeNotificationHandler>::~MakeAllocator<FveEasNetworkStatusChangeNotificationHandler>(&v10);
  return a1;
}

```

## disassembly

```asm
0x1800152a4  push    rbx
0x1800152a6  push    rsi
0x1800152a7  push    rdi
0x1800152a8  push    r14
0x1800152aa  sub     rsp, 28h
0x1800152ae  mov     rsi, r8
0x1800152b1  mov     r14, rdx
0x1800152b4  mov     rbx, rcx
0x1800152b7  mov     qword ptr [rcx], 0
0x1800152be  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800152c5  mov     ecx, 30h ; '0'; unsigned __int64
0x1800152ca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800152cf  mov     rdi, rax
0x1800152d2  mov     [rsp+48h+arg_0], rax
0x1800152d7  test    rax, rax
0x1800152da  jz      short loc_180015329
0x1800152dc  mov     rcx, [rsi]
0x1800152df  mov     [rsp+48h+arg_0], rcx
0x1800152e4  test    rcx, rcx
0x1800152e7  jz      short loc_1800152F6
0x1800152e9  mov     rdx, [rcx]
0x1800152ec  mov     rax, [rdx+8]
0x1800152f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152f5  nop
0x1800152f6  lea     r8, [rsp+48h+arg_0]
0x1800152fb  mov     rdx, [r14]
0x1800152fe  mov     rcx, rdi
0x180015301  call    ??0FveEasNetworkStatusChangeNotificationHandler@@QEAA@PEAPEAVIFveEasNetworkStatusChangeAction@@V?$ComPtr@UINetworkInformationStatics@Connectivity@Networking@Windows@@@WRL@Microsoft@@@Z; FveEasNetworkStatusChangeNotificationHandler::FveEasNetworkStatusChangeNotificationHandler(IFveEasNetworkStatusChangeAction * *,Microsoft::WRL::ComPtr<Windows::Networking::Connectivity::INetworkInformationStatics>)
0x180015306  mov     rdi, rax
0x180015309  mov     rcx, [rbx]
0x18001530c  test    rcx, rcx
0x18001530f  jz      short loc_18001531D
0x180015311  mov     rdx, [rcx]
0x180015314  mov     rax, [rdx+10h]
0x180015318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001531d  mov     [rbx], rdi
0x180015320  mov     [rsp+48h+arg_0], 0
0x180015329  lea     rcx, [rsp+48h+arg_0]
0x18001532e  call    ??1?$MakeAllocator@VFveEasNetworkStatusChangeNotificationHandler@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<FveEasNetworkStatusChangeNotificationHandler>::~MakeAllocator<FveEasNetworkStatusChangeNotificationHandler>(void)
0x180015333  mov     rax, rbx
0x180015336  add     rsp, 28h
0x18001533a  pop     r14
0x18001533c  pop     rdi
0x18001533d  pop     rsi
0x18001533e  pop     rbx
0x18001533f  retn
```
