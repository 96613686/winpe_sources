# TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)

- ea: `0x1800088ec`
- end: `0x1800089c2`
- name: `?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z`
- size: `214`
- prototype: `void __fastcall(struct CallStackContext *, struct TracingFailureHash *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b64`
- `0x180008ce8`

## callees

- `0x1800088ec`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180008960`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180008960`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180008945`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180008945`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008994`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008994`

## pseudocode

```c
void __fastcall TracingFailureDetails::GenerateHashCodeForContext(
        struct CallStackContext *a1,
        struct TracingFailureHash *a2)
{
  __int64 v4; // rbx
  unsigned int i; // ebp
  unsigned int v6; // ecx
  const WCHAR *v7; // rdi
  const char *v8; // rsi
  const char *v9; // rcx
  HMODULE phModule; // [rsp+60h] [rbp+8h] BYREF

  *(_OWORD *)a2 = 0;
  v4 = 0xCBF29CE484222325uLL;
  for ( i = 0; ; ++i )
  {
    v6 = 124;
    if ( *((_DWORD *)a1 + 497) < 0x7Cu )
      v6 = *((_DWORD *)a1 + 497);
    if ( i >= v6 )
      break;
    phModule = 0;
    v7 = (const WCHAR *)*((_QWORD *)a1 + 2 * i);
    v8 = "UNLOADED";
    if ( GetModuleHandleExW(4u, v7, &phModule) )
      v8 = (const char *)v7;
    v9 = &v8[(unsigned int)strnlen(v8, 0x100u) + 1];
    while ( v8 < v9 )
      v4 = 0x100000001B3LL * (*(unsigned __int8 *)v8++ ^ (unsigned __int64)v4);
    if ( phModule )
      FreeLibrary(phModule);
  }
  *(_QWORD *)a2 = v4;
  *((_QWORD *)a2 + 1) = v4 ^ 0xAA55AA55AA55AA55uLL;
}

```

## disassembly

```asm
0x1800088ec  push    rbx
0x1800088ee  push    rbp
0x1800088ef  push    rsi
0x1800088f0  push    rdi
0x1800088f1  push    r14
0x1800088f3  push    r15
0x1800088f5  sub     rsp, 28h
0x1800088f9  xorps   xmm0, xmm0
0x1800088fc  mov     r14, rdx
0x1800088ff  movups  xmmword ptr [rdx], xmm0
0x180008902  mov     r15, rcx
0x180008905  mov     rbx, 0CBF29CE484222325h
0x18000890f  xor     ebp, ebp
0x180008911  mov     eax, [r15+7C4h]
0x180008918  mov     ecx, 7Ch ; '|'
0x18000891d  cmp     eax, ecx
0x18000891f  cmovb   ecx, eax
0x180008922  cmp     ebp, ecx
0x180008924  jnb     short loc_1800089A1
0x180008926  mov     eax, ebp
0x180008928  lea     r8, [rsp+58h+phModule]; phModule
0x18000892d  add     rax, rax
0x180008930  mov     [rsp+58h+phModule], 0
0x180008939  mov     ecx, 4; dwFlags
0x18000893e  mov     rdi, [r15+rax*8]
0x180008942  mov     rdx, rdi; lpModuleName
0x180008945  call    cs:__imp_GetModuleHandleExW
0x18000894b  lea     rsi, aUnloaded; "UNLOADED"
0x180008952  mov     edx, 100h; MaxCount
0x180008957  test    eax, eax
0x180008959  cmovnz  rsi, rdi
0x18000895d  mov     rcx, rsi; String
0x180008960  call    cs:__imp_strnlen
0x180008966  lea     ecx, [rax+1]
0x180008969  add     rcx, rsi
0x18000896c  jmp     short loc_180008985
0x18000896e  movzx   eax, byte ptr [rsi]
0x180008971  mov     rdx, 100000001B3h
0x18000897b  xor     rbx, rax
0x18000897e  imul    rbx, rdx
0x180008982  inc     rsi
0x180008985  cmp     rsi, rcx
0x180008988  jb      short loc_18000896E
0x18000898a  mov     rcx, [rsp+58h+phModule]; hLibModule
0x18000898f  test    rcx, rcx
0x180008992  jz      short loc_18000899A
0x180008994  call    cs:__imp_FreeLibrary
0x18000899a  inc     ebp
0x18000899c  jmp     loc_180008911
0x1800089a1  mov     rax, 0AA55AA55AA55AA55h
0x1800089ab  mov     [r14], rbx
0x1800089ae  xor     rbx, rax
0x1800089b1  mov     [r14+8], rbx
0x1800089b5  add     rsp, 28h
0x1800089b9  pop     r15
0x1800089bb  pop     r14
0x1800089bd  pop     rdi
0x1800089be  pop     rsi
0x1800089bf  pop     rbp
0x1800089c0  pop     rbx
0x1800089c1  retn
```
