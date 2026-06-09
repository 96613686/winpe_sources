# CreateTraceDecodingHandle

- ea: `0x18003f6ec`
- end: `0x18003f79f`
- name: `CreateTraceDecodingHandle`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b760`
- `0x18002b870`

## callees

- `0x180020c74`
- `0x18003ec20`
- `0x18003f6ec`
- `0x180042f7c`
- `0x18004c010`

## string_xrefs

- `0x18003f71d`: `\n	 exceeded max (%d) amount of open Handles`
- `0x18003f77a`: `\n	Failed Create Trace Handle`

## pseudocode

```c
FormatContext *CreateTraceDecodingHandle()
{
  FormatContext *v1; // rax
  FormatContext *v2; // rbx

  if ( _InterlockedIncrement(&dword_18006CE20) <= 0x10000 )
  {
    v1 = (FormatContext *)operator new(0x8D8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v1 )
    {
      v2 = FormatContext::FormatContext(v1);
      if ( v2 )
        return v2;
    }
    else
    {
      v2 = 0;
    }
    if ( TracePrinter )
    {
      if ( DebugExtPrint )
        TracePrinterExt((wchar_t *)L"\n\tFailed Create Trace Handle");
      else
        TracePrinter(L"\n\tFailed Create Trace Handle");
    }
    _InterlockedDecrement(&dword_18006CE20);
    return v2;
  }
  if ( TracePrinter )
  {
    if ( DebugExtPrint )
      TracePrinterExt((wchar_t *)L"\n\t exceeded max (%d) amount of open Handles");
    else
      TracePrinter(L"\n\t exceeded max (%d) amount of open Handles");
  }
  _InterlockedDecrement(&dword_18006CE20);
  return 0;
}

```

## disassembly

```asm
0x18003f6ec  push    rbx
0x18003f6ee  sub     rsp, 20h
0x18003f6f2  mov     eax, 1
0x18003f6f7  lock xadd cs:dword_18006CE20, eax
0x18003f6ff  inc     eax
0x18003f701  mov     edx, 10000h
0x18003f706  cmp     eax, edx
0x18003f708  jle     short loc_18003F73D
0x18003f70a  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003f711  test    rax, rax
0x18003f714  jz      short loc_18003F732
0x18003f716  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18003f71d  lea     rcx, aExceededMaxDAm; "\n\t exceeded max (%d) amount of open H"...
0x18003f724  jnz     short loc_18003F72D
0x18003f726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f72b  jmp     short loc_18003F732
0x18003f72d  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003f732  lock dec cs:dword_18006CE20
0x18003f739  xor     eax, eax
0x18003f73b  jmp     short loc_18003F799
0x18003f73d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003f744  mov     ecx, 8D8h; unsigned __int64
0x18003f749  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003f74e  test    rax, rax
0x18003f751  jz      short loc_18003F765
0x18003f753  mov     rcx, rax; this
0x18003f756  call    ??0FormatContext@@QEAA@XZ; FormatContext::FormatContext(void)
0x18003f75b  mov     rbx, rax
0x18003f75e  test    rax, rax
0x18003f761  jnz     short loc_18003F796
0x18003f763  jmp     short loc_18003F767
0x18003f765  xor     ebx, ebx
0x18003f767  mov     rax, cs:?TracePrinter@@3P6AKPEAGZZEA; ulong (*TracePrinter)(ushort *,...)
0x18003f76e  test    rax, rax
0x18003f771  jz      short loc_18003F78F
0x18003f773  cmp     cs:?DebugExtPrint@@3HA, 0; int DebugExtPrint
0x18003f77a  lea     rcx, aFailedCreateTr; "\n\tFailed Create Trace Handle"
0x18003f781  jnz     short loc_18003F78A
0x18003f783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f788  jmp     short loc_18003F78F
0x18003f78a  call    ?TracePrinterExt@@YAKPEBGZZ; TracePrinterExt(ushort const *,...)
0x18003f78f  lock dec cs:dword_18006CE20
0x18003f796  mov     rax, rbx
0x18003f799  add     rsp, 20h
0x18003f79d  pop     rbx
0x18003f79e  retn
```
