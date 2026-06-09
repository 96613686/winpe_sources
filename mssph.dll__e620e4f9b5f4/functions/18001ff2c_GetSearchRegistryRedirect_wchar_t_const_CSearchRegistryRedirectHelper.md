# GetSearchRegistryRedirect(wchar_t const *,CSearchRegistryRedirectHelper * *)

- ea: `0x18001ff2c`
- end: `0x18001ffcf`
- name: `?GetSearchRegistryRedirect@@YA_NPEB_WPEAPEAVCSearchRegistryRedirectHelper@@@Z`
- size: `163`
- prototype: `bool __fastcall(const wchar_t *, struct CSearchRegistryRedirectHelper **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006300`
- `0x18000a100`
- `0x18000cbac`

## callees

- `0x18001ff2c`
- `0x180023aac`
- `0x180024e14`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ff9f`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18001ff9f`

## pseudocode

```c
bool __fastcall GetSearchRegistryRedirect(const wchar_t *a1, struct CSearchRegistryRedirectHelper **a2)
{
  __int64 v3; // rdi
  unsigned int i; // ebx
  bool result; // al

  *a2 = 0;
  v3 = 2;
  for ( i = 0; i < 2; ++i )
  {
    if ( !wcscmp_0(off_180035360[69 * i], L"WSearch") )
    {
      v3 = i;
      if ( i < 2uLL )
        goto LABEL_7;
      break;
    }
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_7:
  if ( !InitOnceExecuteOnce(
          (PINIT_ONCE)&qword_180036448[v3],
          lambda_cd2099a84e29dd60a3ce15c92771ff9c_::_lambda_invoker_cdecl_,
          (PVOID)v3,
          0) )
    return 0;
  result = 1;
  *a2 = (struct CSearchRegistryRedirectHelper *)&qword_180035378[69 * v3];
  return result;
}

```

## disassembly

```asm
0x18001ff2c  push    rbx
0x18001ff2e  push    rsi
0x18001ff2f  push    rdi
0x18001ff30  push    r14
0x18001ff32  push    r15
0x18001ff34  sub     rsp, 20h
0x18001ff38  mov     r14, rdx
0x18001ff3b  mov     qword ptr [rdx], 0
0x18001ff42  mov     edi, 2
0x18001ff47  lea     r15, __ImageBase
0x18001ff4e  xor     ebx, ebx
0x18001ff50  cmp     ebx, edi
0x18001ff52  jnb     short loc_18001FF82
0x18001ff54  mov     esi, ebx
0x18001ff56  lea     rdx, aWsearch; "WSearch"
0x18001ff5d  imul    rcx, rsi, 228h
0x18001ff64  mov     rcx, [rcx+r15+35360h]; String1
0x18001ff6c  call    wcscmp_0
0x18001ff71  test    eax, eax
0x18001ff73  jz      short loc_18001FF79
0x18001ff75  inc     ebx
0x18001ff77  jmp     short loc_18001FF50
0x18001ff79  mov     rdi, rsi
0x18001ff7c  cmp     rsi, 2
0x18001ff80  jb      short loc_18001FF87
0x18001ff82  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001ff87  lea     rcx, rva qword_180036448[r15]
0x18001ff8e  xor     r9d, r9d; Context
0x18001ff91  lea     rcx, [rcx+rdi*8]; InitOnce
0x18001ff95  mov     r8, rdi; Parameter
0x18001ff98  lea     rdx, _lambda_cd2099a84e29dd60a3ce15c92771ff9c____lambda_invoker_cdecl_; InitFn
0x18001ff9f  call    cs:__imp_InitOnceExecuteOnce
0x18001ffa5  test    eax, eax
0x18001ffa7  jz      short loc_18001FFC1
0x18001ffa9  imul    rcx, rdi, 228h
0x18001ffb0  lea     rdx, qword_180035378
0x18001ffb7  mov     al, 1
0x18001ffb9  add     rcx, rdx
0x18001ffbc  mov     [r14], rcx
0x18001ffbf  jmp     short loc_18001FFC3
0x18001ffc1  xor     al, al
0x18001ffc3  add     rsp, 20h
0x18001ffc7  pop     r15
0x18001ffc9  pop     r14
0x18001ffcb  pop     rdi
0x18001ffcc  pop     rsi
0x18001ffcd  pop     rbx
0x18001ffce  retn
```
