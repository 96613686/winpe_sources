# Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>(CContentRequestDelegate * *)

- ea: `0x18001a1b8`
- end: `0x18001a285`
- name: `??$MakeAndInitialize@VCContentRequestDelegate@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCContentRequestDelegate@@@Z`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001a28c`

## callees

- `0x180001710`
- `0x18000f1f4`
- `0x180011954`
- `0x18001a1b8`
- `0x18001a6bc`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a216`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a225`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CContentRequestDelegate,CContentRequestDelegate,>(
        CContentRequestDelegate **a1)
{
  CContentRequestDelegate *v2; // rax
  signed int v3; // ebx
  CContentRequestDelegate *v4; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  CContentRequestDelegate *v8; // [rsp+30h] [rbp+8h] BYREF
  CContentRequestDelegate *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = (CContentRequestDelegate *)operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v2;
  if ( v2 )
  {
    v4 = CContentRequestDelegate::CContentRequestDelegate(v2);
    v8 = v4;
    v9 = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v4 + 9) = EventW;
    if ( EventW )
      goto LABEL_8;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(CContentRequestDelegate *))(*(_QWORD *)v4 + 8LL))(v4);
      *a1 = v4;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v8);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(&v9);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a1b8  mov     [rsp+arg_10], rbx
0x18001a1bd  mov     [rsp+arg_18], rsi
0x18001a1c2  push    rdi
0x18001a1c3  sub     rsp, 20h
0x18001a1c7  mov     rsi, rcx
0x18001a1ca  mov     qword ptr [rcx], 0
0x18001a1d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a1d8  mov     ecx, 58h ; 'X'; unsigned __int64
0x18001a1dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001a1e2  mov     [rsp+28h+arg_8], rax
0x18001a1e7  test    rax, rax
0x18001a1ea  jnz     short loc_18001A1F3
0x18001a1ec  mov     ebx, 8007000Eh
0x18001a1f1  jmp     short loc_18001A269
0x18001a1f3  mov     rcx, rax; this
0x18001a1f6  call    ??0CContentRequestDelegate@@QEAA@XZ; CContentRequestDelegate::CContentRequestDelegate(void)
0x18001a1fb  mov     rdi, rax
0x18001a1fe  mov     [rsp+28h+arg_0], rax
0x18001a203  mov     [rsp+28h+arg_8], 0
0x18001a20c  xor     r9d, r9d; lpName
0x18001a20f  xor     r8d, r8d; bInitialState
0x18001a212  xor     edx, edx; bManualReset
0x18001a214  xor     ecx, ecx; lpEventAttributes
0x18001a216  call    cs:__imp_CreateEventW
0x18001a21c  mov     [rdi+48h], rax
0x18001a220  test    rax, rax
0x18001a223  jnz     short loc_18001A24A
0x18001a225  call    cs:__imp_GetLastError
0x18001a22b  mov     ebx, eax
0x18001a22d  test    eax, eax
0x18001a22f  jle     short loc_18001A23A
0x18001a231  movzx   ebx, ax
0x18001a234  or      ebx, 80070000h
0x18001a23a  test    ebx, ebx
0x18001a23c  jns     short loc_18001A24A
0x18001a23e  lea     rcx, [rsp+28h+arg_0]
0x18001a243  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a248  jmp     short loc_18001A269
0x18001a24a  mov     rax, [rdi]
0x18001a24d  mov     rcx, rdi
0x18001a250  mov     rax, [rax+8]
0x18001a254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a259  nop
0x18001a25a  mov     [rsi], rdi
0x18001a25d  lea     rcx, [rsp+28h+arg_0]
0x18001a262  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x18001a267  xor     ebx, ebx
0x18001a269  lea     rcx, [rsp+28h+arg_8]
0x18001a26e  call    ??1?$MakeAllocator@VCThumbnailRequest@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(void)
0x18001a273  mov     eax, ebx
0x18001a275  mov     rbx, [rsp+28h+arg_10]
0x18001a27a  mov     rsi, [rsp+28h+arg_18]
0x18001a27f  add     rsp, 20h
0x18001a283  pop     rdi
0x18001a284  retn
```
