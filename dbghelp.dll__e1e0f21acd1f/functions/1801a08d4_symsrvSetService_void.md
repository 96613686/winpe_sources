# symsrvSetService(void)

- ea: `0x1801a08d4`
- end: `0x1801a0999`
- name: `?symsrvSetService@@YAXXZ`
- size: `197`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1801a03ec`

## callees

- `0x180022d28`
- `0x180027430`
- `0x1801a08d4`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0913`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0940`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0969`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0913`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0940`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1801a0969`

## string_xrefs

- `0x1801a090c`: `DBGHELP_SERVICE`

## pseudocode

```c
void symsrvSetService(void)
{
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( GetEnvironmentVariableW(L"DBGHELP_SERVICE", Buffer, 0x105u) )
    symsrvSetOptions(0x100000u, 1u);
  if ( GetEnvironmentVariableW(L"DBGHELP_WININET", Buffer, 0x105u) )
    symsrvSetOptions(0x1000000u, 1u);
  if ( GetEnvironmentVariableW(L"DBGHELP_WINHTTP", Buffer, 0x105u) )
    symsrvSetOptions(0x800000u, 1u);
}

```

## disassembly

```asm
0x1801a08d4  push    rbx
0x1801a08d6  sub     rsp, 240h
0x1801a08dd  mov     rax, cs:__security_cookie
0x1801a08e4  xor     rax, rsp
0x1801a08e7  mov     [rsp+248h+var_18], rax
0x1801a08ef  xor     edx, edx; Val
0x1801a08f1  lea     rcx, [rsp+248h+Buffer]; void *
0x1801a08f6  mov     r8d, 20Ah; Size
0x1801a08fc  call    memset_0
0x1801a0901  mov     r8d, 105h; nSize
0x1801a0907  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x1801a090c  lea     rcx, aDbghelpService; "DBGHELP_SERVICE"
0x1801a0913  call    cs:__imp_GetEnvironmentVariableW
0x1801a0919  mov     ebx, 1
0x1801a091e  test    eax, eax
0x1801a0920  jz      short loc_1801A092E
0x1801a0922  mov     edx, ebx; unsigned __int64
0x1801a0924  mov     ecx, 100000h; unsigned __int64
0x1801a0929  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a092e  mov     r8d, 105h; nSize
0x1801a0934  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x1801a0939  lea     rcx, aDbghelpWininet; "DBGHELP_WININET"
0x1801a0940  call    cs:__imp_GetEnvironmentVariableW
0x1801a0946  test    eax, eax
0x1801a0948  jz      short loc_1801A0957
0x1801a094a  mov     rdx, rbx; unsigned __int64
0x1801a094d  mov     ecx, 1000000h; unsigned __int64
0x1801a0952  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a0957  mov     r8d, 105h; nSize
0x1801a095d  lea     rdx, [rsp+248h+Buffer]; lpBuffer
0x1801a0962  lea     rcx, aDbghelpWinhttp; "DBGHELP_WINHTTP"
0x1801a0969  call    cs:__imp_GetEnvironmentVariableW
0x1801a096f  test    eax, eax
0x1801a0971  jz      short loc_1801A0980
0x1801a0973  mov     rdx, rbx; unsigned __int64
0x1801a0976  mov     ecx, 800000h; unsigned __int64
0x1801a097b  call    ?symsrvSetOptions@@YAX_K0@Z; symsrvSetOptions(unsigned __int64,unsigned __int64)
0x1801a0980  mov     rcx, [rsp+248h+var_18]
0x1801a0988  xor     rcx, rsp; StackCookie
0x1801a098b  call    __security_check_cookie
0x1801a0990  add     rsp, 240h
0x1801a0997  pop     rbx
0x1801a0998  retn
```
