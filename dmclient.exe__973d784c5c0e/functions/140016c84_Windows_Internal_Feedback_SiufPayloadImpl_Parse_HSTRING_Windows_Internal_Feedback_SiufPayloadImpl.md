# Windows::Internal::Feedback::SiufPayloadImpl::Parse(HSTRING__ *,Windows::Internal::Feedback::SiufPayloadImpl * *)

- ea: `0x140016c84`
- end: `0x140016d62`
- name: `?Parse@SiufPayloadImpl@Feedback@Internal@Windows@@SAJPEAUHSTRING__@@PEAPEAV1234@@Z`
- size: `222`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Internal::Feedback::SiufPayloadImpl **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14000e290`

## callees

- `0x140002618`
- `0x14001691c`
- `0x140016c84`
- `0x140018850`
- `0x14001a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140016cff`
- `msvcrt!??3@YAXPEAX@Z` at `0x140016cff`

## string_xrefs

- `0x140016d0b`: `Failed to initialize and parse the json.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Feedback::SiufPayloadImpl::Parse(
        HSTRING a1,
        struct Windows::Internal::Feedback::SiufPayloadImpl **a2)
{
  Windows::Internal::Feedback::SiufPayloadImpl *v4; // rax
  struct Windows::Internal::Feedback::SiufPayloadImpl *v5; // rbx
  int v6; // edi
  __int64 v7; // rcx

  *a2 = 0;
  v4 = (Windows::Internal::Feedback::SiufPayloadImpl *)operator new(8u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = 0;
    v6 = Windows::Internal::Feedback::SiufPayloadImpl::Init(v4, a1);
    if ( v6 >= 0 )
    {
      *a2 = v5;
      return 0;
    }
    else
    {
      if ( v5 )
      {
        v7 = *(_QWORD *)v5;
        if ( *(_QWORD *)v5 )
        {
          *(_QWORD *)v5 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        operator delete(v5);
      }
      SuifTraceLogging::WriteErrorTraceFormat(
        v6,
        39,
        "Windows::Internal::Feedback::SiufPayloadImpl::Parse",
        (wchar_t *)L"Failed to initialize and parse the json.");
      return (unsigned int)v6;
    }
  }
  else
  {
    SuifTraceLogging::WriteErrorTraceFormat(
      -2147024882,
      32,
      "Windows::Internal::Feedback::SiufPayloadImpl::Parse",
      (wchar_t *)L"Insufficient memory to instantiate SiufPayloadImpl.");
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140016c84  mov     [rsp+arg_0], rbx
0x140016c89  mov     [rsp+arg_10], rsi
0x140016c8e  push    rdi
0x140016c8f  sub     rsp, 20h
0x140016c93  mov     rsi, rdx
0x140016c96  mov     rdi, rcx
0x140016c99  mov     qword ptr [rdx], 0
0x140016ca0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016ca7  mov     ecx, 8; unsigned __int64
0x140016cac  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016cb1  mov     rbx, rax
0x140016cb4  mov     [rsp+28h+arg_8], rax
0x140016cb9  test    rax, rax
0x140016cbc  jz      short loc_140016D30
0x140016cbe  mov     qword ptr [rax], 0
0x140016cc5  test    rax, rax
0x140016cc8  jz      short loc_140016D30
0x140016cca  mov     rdx, rdi; HSTRING
0x140016ccd  mov     rcx, rax; this
0x140016cd0  call    ?Init@SiufPayloadImpl@Feedback@Internal@Windows@@AEAAJPEAUHSTRING__@@@Z; Windows::Internal::Feedback::SiufPayloadImpl::Init(HSTRING__ *)
0x140016cd5  mov     edi, eax
0x140016cd7  test    eax, eax
0x140016cd9  jns     short loc_140016D29
0x140016cdb  test    rbx, rbx
0x140016cde  jz      short loc_140016D0B
0x140016ce0  mov     rcx, [rbx]
0x140016ce3  test    rcx, rcx
0x140016ce6  jz      short loc_140016CFC
0x140016ce8  mov     qword ptr [rbx], 0
0x140016cef  mov     rdx, [rcx]
0x140016cf2  mov     rax, [rdx+10h]
0x140016cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016cfb  nop
0x140016cfc  mov     rcx, rbx
0x140016cff  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140016d06  nop     dword ptr [rax+rax+00h]
0x140016d0b  lea     r9, aFailedToInitia; "Failed to initialize and parse the json"...
0x140016d12  lea     r8, aWindowsInterna; "Windows::Internal::Feedback::SiufPayloa"...
0x140016d19  mov     edx, 27h ; '''; int
0x140016d1e  mov     ecx, edi; int
0x140016d20  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140016d25  mov     eax, edi
0x140016d27  jmp     short loc_140016D51
0x140016d29  mov     [rsi], rbx
0x140016d2c  xor     eax, eax
0x140016d2e  jmp     short loc_140016D51
0x140016d30  lea     r9, aInsufficientMe; "Insufficient memory to instantiate Siuf"...
0x140016d37  lea     r8, aWindowsInterna; "Windows::Internal::Feedback::SiufPayloa"...
0x140016d3e  mov     edx, 20h ; ' '; int
0x140016d43  mov     ebx, 8007000Eh
0x140016d48  mov     ecx, ebx; int
0x140016d4a  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140016d4f  mov     eax, ebx
0x140016d51  mov     rbx, [rsp+28h+arg_0]
0x140016d56  mov     rsi, [rsp+28h+arg_10]
0x140016d5b  add     rsp, 20h
0x140016d5f  pop     rdi
0x140016d60  retn
```
