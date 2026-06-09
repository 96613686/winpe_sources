# TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)

- ea: `0x1800027d4`
- end: `0x1800028a9`
- name: `?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z`
- size: `213`
- prototype: `void __fastcall(struct CallStackContext *, struct TracingFailureHash *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800026d8`
- `0x180004ed8`

## callees

- `0x1800027d4`
- `0x180004ce8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180002852`
- `api-ms-win-crt-string-l1-1-0!strnlen` at `0x180002852`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002837`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180002837`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002873`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180002873`

## pseudocode

```c
void __fastcall TracingFailureDetails::GenerateHashCodeForContext(
        struct CallStackContext *a1,
        struct TracingFailureHash *a2)
{
  unsigned int i; // esi
  unsigned int v5; // ecx
  const WCHAR *v6; // rbx
  char *v7; // rdi
  int v8; // eax
  unsigned __int64 v9; // rax
  HMODULE phModule; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  v11 = 0xCBF29CE484222325uLL;
  *(_OWORD *)a2 = 0;
  for ( i = 0; ; ++i )
  {
    v5 = 124;
    if ( *((_DWORD *)a1 + 497) < 0x7Cu )
      v5 = *((_DWORD *)a1 + 497);
    if ( i >= v5 )
      break;
    phModule = 0;
    v6 = (const WCHAR *)*((_QWORD *)a1 + 2 * i);
    v7 = "UNLOADED";
    if ( GetModuleHandleExW(4u, v6, &phModule) )
      v7 = (char *)v6;
    v8 = strnlen(v7, 0x100u);
    HashFNV::HashData((HashFNV *)&v11, (unsigned __int8 *)v7, v8 + 1);
    if ( phModule )
      FreeLibrary(phModule);
  }
  v9 = v11;
  *(_QWORD *)a2 = v11;
  *((_QWORD *)a2 + 1) = v9 ^ 0xAA55AA55AA55AA55uLL;
}

```

## disassembly

```asm
0x1800027d4  mov     [rsp+arg_10], rbx
0x1800027d9  mov     [rsp+arg_18], rbp
0x1800027de  push    rsi
0x1800027df  push    rdi
0x1800027e0  push    r14
0x1800027e2  sub     rsp, 20h
0x1800027e6  mov     rax, 0CBF29CE484222325h
0x1800027f0  xorps   xmm0, xmm0
0x1800027f3  mov     [rsp+38h+arg_8], rax
0x1800027f8  mov     r14, rdx
0x1800027fb  movups  xmmword ptr [rdx], xmm0
0x1800027fe  mov     rbp, rcx
0x180002801  xor     esi, esi
0x180002803  mov     eax, [rbp+7C4h]
0x180002809  mov     ecx, 7Ch ; '|'
0x18000280e  cmp     eax, ecx
0x180002810  cmovb   ecx, eax
0x180002813  cmp     esi, ecx
0x180002815  jnb     short loc_18000287D
0x180002817  mov     eax, esi
0x180002819  lea     r8, [rsp+38h+phModule]; phModule
0x18000281e  add     rax, rax
0x180002821  mov     [rsp+38h+phModule], 0
0x18000282a  mov     ecx, 4; dwFlags
0x18000282f  mov     rbx, [rbp+rax*8+0]
0x180002834  mov     rdx, rbx; lpModuleName
0x180002837  call    cs:__imp_GetModuleHandleExW
0x18000283d  lea     rdi, aUnloaded; "UNLOADED"
0x180002844  mov     edx, 100h; MaxCount
0x180002849  test    eax, eax
0x18000284b  cmovnz  rdi, rbx
0x18000284f  mov     rcx, rdi; String
0x180002852  call    cs:__imp_strnlen
0x180002858  mov     rdx, rdi; unsigned __int8 *
0x18000285b  lea     rcx, [rsp+38h+arg_8]; this
0x180002860  lea     r8d, [rax+1]; unsigned int
0x180002864  call    ?HashData@HashFNV@@QEAA_KPEAEK@Z; HashFNV::HashData(uchar *,ulong)
0x180002869  mov     rcx, [rsp+38h+phModule]; hLibModule
0x18000286e  test    rcx, rcx
0x180002871  jz      short loc_180002879
0x180002873  call    cs:__imp_FreeLibrary
0x180002879  inc     esi
0x18000287b  jmp     short loc_180002803
0x18000287d  mov     rax, [rsp+38h+arg_8]
0x180002882  mov     rcx, 0AA55AA55AA55AA55h
0x18000288c  mov     rbx, [rsp+38h+arg_10]
0x180002891  mov     rbp, [rsp+38h+arg_18]
0x180002896  mov     [r14], rax
0x180002899  xor     rax, rcx
0x18000289c  mov     [r14+8], rax
0x1800028a0  add     rsp, 20h
0x1800028a4  pop     r14
0x1800028a6  pop     rdi
0x1800028a7  pop     rsi
0x1800028a8  retn
```
