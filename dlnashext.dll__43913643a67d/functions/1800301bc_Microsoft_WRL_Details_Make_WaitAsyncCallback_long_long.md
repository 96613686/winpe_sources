# Microsoft::WRL::Details::Make<WaitAsyncCallback,long *>(long * &&)

- ea: `0x1800301bc`
- end: `0x1800302a9`
- name: `??$Make@VWaitAsyncCallback@@PEAJ@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWaitAsyncCallback@@@12@$$QEAPEAJ@Z`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010af0`

## callees

- `0x18000e11c`
- `0x18000f1f4`
- `0x180011954`
- `0x1800301bc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030249`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030258`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<WaitAsyncCallback,long *>(_QWORD *a1, signed int **a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  signed int *v6; // rsi
  HANDLE EventW; // rax
  signed int LastError; // eax
  _QWORD *v10; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  v4 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = v4;
  v5 = v4;
  if ( v4 )
  {
    v6 = *a2;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(v4);
    *v5 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFAsyncCallback>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v5 = &WaitAsyncCallback::`vftable';
    v5[2] = 0;
    *v6 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    v5[3] = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *v6 = LastError;
    }
    if ( *a1 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    *a1 = v5;
    v10 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(&v10);
  return a1;
}

```

## disassembly

```asm
0x1800301bc  mov     [rsp+arg_8], rbx
0x1800301c1  mov     [rsp+arg_10], rsi
0x1800301c6  push    rdi
0x1800301c7  sub     rsp, 20h
0x1800301cb  mov     rsi, rdx
0x1800301ce  mov     qword ptr [rcx], 0
0x1800301d5  mov     rdi, rcx
0x1800301d8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800301df  mov     ecx, 20h ; ' '; unsigned __int64
0x1800301e4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800301e9  mov     [rsp+28h+arg_0], rax
0x1800301ee  mov     rbx, rax
0x1800301f1  test    rax, rax
0x1800301f4  jz      loc_18003028C
0x1800301fa  mov     rsi, [rsi]
0x1800301fd  mov     rcx, rax
0x180030200  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x180030205  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMFAsyncCallback@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMFAsyncCallback>::`vftable'
0x18003020c  mov     [rbx], rcx
0x18003020f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180030216  test    rcx, rcx
0x180030219  jz      short loc_180030227
0x18003021b  mov     rdx, [rcx]
0x18003021e  mov     rax, [rdx+8]
0x180030222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030227  lea     rax, ??_7WaitAsyncCallback@@6B@; const WaitAsyncCallback::`vftable'
0x18003022e  xor     r9d, r9d; lpName
0x180030231  mov     [rbx], rax
0x180030234  xor     r8d, r8d; bInitialState
0x180030237  mov     qword ptr [rbx+10h], 0
0x18003023f  xor     edx, edx; bManualReset
0x180030241  xor     ecx, ecx; lpEventAttributes
0x180030243  mov     dword ptr [rsi], 0
0x180030249  call    cs:__imp_CreateEventW
0x18003024f  mov     [rbx+18h], rax
0x180030253  test    rax, rax
0x180030256  jnz     short loc_18003026C
0x180030258  call    cs:__imp_GetLastError
0x18003025e  test    eax, eax
0x180030260  jle     short loc_18003026A
0x180030262  movzx   eax, ax
0x180030265  or      eax, 80070000h
0x18003026a  mov     [rsi], eax
0x18003026c  mov     rcx, [rdi]
0x18003026f  test    rcx, rcx
0x180030272  jz      short loc_180030280
0x180030274  mov     rax, [rcx]
0x180030277  mov     rax, [rax+10h]
0x18003027b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030280  mov     [rdi], rbx
0x180030283  mov     [rsp+28h+arg_0], 0
0x18003028c  lea     rcx, [rsp+28h+arg_0]
0x180030291  call    ??1?$MakeAllocator@VCThumbnailRequest@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(void)
0x180030296  mov     rbx, [rsp+28h+arg_8]
0x18003029b  mov     rax, rdi
0x18003029e  mov     rsi, [rsp+28h+arg_10]
0x1800302a3  add     rsp, 20h
0x1800302a7  pop     rdi
0x1800302a8  retn
```
