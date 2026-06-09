# Windows::Internal::Feedback::SiufPayloadImpl::Parse(HSTRING__ *,Windows::Internal::Feedback::SiufPayloadImpl * *)

- ea: `0x140017d90`
- end: `0x140017e67`
- name: `?Parse@SiufPayloadImpl@Feedback@Internal@Windows@@SAJPEAUHSTRING__@@PEAPEAV1234@@Z`
- size: `215`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Internal::Feedback::SiufPayloadImpl **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14000dd30`

## callees

- `0x1400025f8`
- `0x140017b80`
- `0x140017d90`
- `0x140017fbc`
- `0x140019010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140017e0b`
- `msvcrt!??3@YAXPEAX@Z` at `0x140017e0b`

## string_xrefs

- `0x140017e11`: `Failed to initialize and parse the json.`

## pseudocode

```c
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
0x140017d90  mov     [rsp+arg_0], rbx
0x140017d95  mov     [rsp+arg_10], rsi
0x140017d9a  push    rdi
0x140017d9b  sub     rsp, 20h
0x140017d9f  mov     rsi, rdx
0x140017da2  mov     rdi, rcx
0x140017da5  mov     qword ptr [rdx], 0
0x140017dac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017db3  mov     ecx, 8; unsigned __int64
0x140017db8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140017dbd  mov     rbx, rax
0x140017dc0  mov     [rsp+28h+arg_8], rax
0x140017dc5  test    rax, rax
0x140017dc8  jz      short loc_140017E36
0x140017dca  mov     qword ptr [rax], 0
0x140017dd1  test    rax, rax
0x140017dd4  jz      short loc_140017E36
0x140017dd6  mov     rdx, rdi; HSTRING
0x140017dd9  mov     rcx, rax; this
0x140017ddc  call    ?Init@SiufPayloadImpl@Feedback@Internal@Windows@@AEAAJPEAUHSTRING__@@@Z; Windows::Internal::Feedback::SiufPayloadImpl::Init(HSTRING__ *)
0x140017de1  mov     edi, eax
0x140017de3  test    eax, eax
0x140017de5  jns     short loc_140017E2F
0x140017de7  test    rbx, rbx
0x140017dea  jz      short loc_140017E11
0x140017dec  mov     rcx, [rbx]
0x140017def  test    rcx, rcx
0x140017df2  jz      short loc_140017E08
0x140017df4  mov     qword ptr [rbx], 0
0x140017dfb  mov     rdx, [rcx]
0x140017dfe  mov     rax, [rdx+10h]
0x140017e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017e07  nop
0x140017e08  mov     rcx, rbx
0x140017e0b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140017e11  lea     r9, aFailedToInitia; "Failed to initialize and parse the json"...
0x140017e18  lea     r8, aWindowsInterna; "Windows::Internal::Feedback::SiufPayloa"...
0x140017e1f  mov     edx, 27h ; '''; int
0x140017e24  mov     ecx, edi; int
0x140017e26  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017e2b  mov     eax, edi
0x140017e2d  jmp     short loc_140017E57
0x140017e2f  mov     [rsi], rbx
0x140017e32  xor     eax, eax
0x140017e34  jmp     short loc_140017E57
0x140017e36  lea     r9, aInsufficientMe; "Insufficient memory to instantiate Siuf"...
0x140017e3d  lea     r8, aWindowsInterna; "Windows::Internal::Feedback::SiufPayloa"...
0x140017e44  mov     edx, 20h ; ' '; int
0x140017e49  mov     ebx, 8007000Eh
0x140017e4e  mov     ecx, ebx; int
0x140017e50  call    ?WriteErrorTraceFormat@SuifTraceLogging@@SAXJHPEBDPEBGZZ; SuifTraceLogging::WriteErrorTraceFormat(long,int,char const *,ushort const *,...)
0x140017e55  mov     eax, ebx
0x140017e57  mov     rbx, [rsp+28h+arg_0]
0x140017e5c  mov     rsi, [rsp+28h+arg_10]
0x140017e61  add     rsp, 20h
0x140017e65  pop     rdi
0x140017e66  retn
```
