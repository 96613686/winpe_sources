# WinHttpRequest::ReadDataTrigger(ulong)

- ea: `0x180034f54`
- end: `0x18003504d`
- name: `?ReadDataTrigger@WinHttpRequest@@AEAAJK@Z`
- size: `249`
- prototype: `int(WinHttpRequest *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18003a804`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x18003334c`
- `0x180034f54`
- `0x18003adac`
- `0x180043ef8`
- `0x180044d30`
- `0x18004654c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034fdd`
- `WINHTTP!WinHttpReadData` at `0x180034fd3`
- `WINHTTP!WinHttpReadData` at `0x180034fd3`

## string_xrefs

- `0x180034f78`: `WinHttpRequest::ReadDataTrigger`
- `0x180034f9f`: `WinHttpRequest::ReadDataTrigger`
- `0x180034ffa`: `WinHttpRequest::ReadDataTrigger`
- `0x18003502d`: `WinHttpRequest::ReadDataTrigger`
- `0x180034ff3`: `WinHttpReadData`
- `0x180034f71`: `%s: Trying to read %lu bytes of data.`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::ReadDataTrigger(HINTERNET *this, DWORD a2)
{
  unsigned int v2; // ebx
  void *v5; // rax
  void *v6; // rsi
  signed int LastError; // edi

  v2 = 0;
  if ( a2 )
  {
    Logger::TraceVerbose((wchar_t *)L"%s: Trying to read %lu bytes of data.", L"WinHttpRequest::ReadDataTrigger", a2);
    v5 = operator new[](a2 + 1, (const struct std::nothrow_t *)&std::nothrow);
    v6 = v5;
    if ( !v5 )
    {
      v2 = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpRequest::ReadDataTrigger");
LABEL_9:
      operator delete(v6);
      goto LABEL_10;
    }
    memset_0(v5, 0, a2 + 1);
    if ( !WinHttpReadData(this[1], v6, a2, 0) )
    {
      LastError = GetLastError();
      Logger::WriteWinhttpReadFailureEvent(LastError);
      if ( LastError )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"WinHttpRequest::ReadDataTrigger",
          L"WinHttpReadData",
          (unsigned int)LastError);
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        else
          v2 = LastError;
        goto LABEL_9;
      }
    }
  }
LABEL_10:
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"WinHttpRequest::ReadDataTrigger", v2);
  return v2;
}

```

## disassembly

```asm
0x180034f54  push    rbx
0x180034f56  push    rbp
0x180034f57  push    rsi
0x180034f58  push    rdi
0x180034f59  push    r14
0x180034f5b  sub     rsp, 20h
0x180034f5f  xor     ebx, ebx
0x180034f61  mov     edi, edx
0x180034f63  mov     r14, rcx
0x180034f66  test    edx, edx
0x180034f68  jz      loc_18003502A
0x180034f6e  mov     r8d, edx
0x180034f71  lea     rcx, aSTryingToReadL; "%s: Trying to read %lu bytes of data."
0x180034f78  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x180034f7f  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180034f84  lea     eax, [rdi+1]
0x180034f87  mov     ecx, eax; unsigned __int64
0x180034f89  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180034f90  mov     ebp, eax
0x180034f92  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180034f97  mov     rsi, rax
0x180034f9a  test    rax, rax
0x180034f9d  jnz     short loc_180034FB9
0x180034f9f  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x180034fa6  mov     ebx, 8007000Eh
0x180034fab  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180034fb2  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180034fb7  jmp     short loc_180035022
0x180034fb9  mov     r8, rbp; Size
0x180034fbc  xor     edx, edx; Val
0x180034fbe  mov     rcx, rsi; void *
0x180034fc1  call    memset_0
0x180034fc6  mov     rcx, [r14+8]; hRequest
0x180034fca  xor     r9d, r9d; lpdwNumberOfBytesRead
0x180034fcd  mov     r8d, edi; dwNumberOfBytesToRead
0x180034fd0  mov     rdx, rsi; lpBuffer
0x180034fd3  call    cs:__imp_WinHttpReadData
0x180034fd9  test    eax, eax
0x180034fdb  jnz     short loc_18003502A
0x180034fdd  call    cs:__imp_GetLastError
0x180034fe3  mov     ecx, eax; unsigned int
0x180034fe5  mov     edi, eax
0x180034fe7  call    ?WriteWinhttpReadFailureEvent@Logger@@SAJK@Z; Logger::WriteWinhttpReadFailureEvent(ulong)
0x180034fec  test    edi, edi
0x180034fee  jz      short loc_18003502A
0x180034ff0  mov     r9d, edi
0x180034ff3  lea     r8, aWinhttpreaddat_0; "WinHttpReadData"
0x180034ffa  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x180035001  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180035008  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003500d  test    edi, edi
0x18003500f  jg      short loc_180035015
0x180035011  mov     ebx, edi
0x180035013  jmp     short loc_18003501E
0x180035015  movzx   ebx, di
0x180035018  or      ebx, 80070000h
0x18003501e  test    ebx, ebx
0x180035020  jns     short loc_18003502A
0x180035022  mov     rcx, rsi; Block
0x180035025  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003502a  mov     r8d, ebx
0x18003502d  lea     rdx, aWinhttprequest_13; "WinHttpRequest::ReadDataTrigger"
0x180035034  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18003503b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180035040  mov     eax, ebx
0x180035042  add     rsp, 20h
0x180035046  pop     r14
0x180035048  pop     rdi
0x180035049  pop     rsi
0x18003504a  pop     rbp
0x18003504b  pop     rbx
0x18003504c  retn
```
