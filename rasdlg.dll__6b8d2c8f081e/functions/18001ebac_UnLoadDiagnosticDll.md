# UnLoadDiagnosticDll

- ea: `0x18001ebac`
- end: `0x18001ec2d`
- name: `UnLoadDiagnosticDll`
- size: `129`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180007498`
- `0x18001e510`
- `0x18002962c`
- `0x18002d4a0`
- `0x18002d590`

## callees

- `0x18001ebac`
- `0x18004d0d2`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ebfd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ebfd`
- `rtutils!TracePrintfExA` at `0x18001ebd0`
- `rtutils!TracePrintfExA` at `0x18001ebd0`

## string_xrefs

- `0x18001ebc4`: `UnLoadDiagnosticDll`

## pseudocode

```c
__int64 __fastcall UnLoadDiagnosticDll(__int64 a1)
{
  unsigned int v2; // edi
  void (*v3)(void); // rax

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "UnLoadDiagnosticDll");
  if ( a1 && *(_QWORD *)a1 )
  {
    v2 = 0;
    if ( !_InterlockedDecrement(&g_lDiagTabLoaded) )
    {
      v3 = *(void (**)(void))(a1 + 24);
      if ( v3 )
        v3();
    }
    FreeLibrary(*(HMODULE *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    memset_0((void *)(a1 + 16), 0, 0x40u);
  }
  else
  {
    return 87;
  }
  return v2;
}

```

## disassembly

```asm
0x18001ebac  mov     [rsp+arg_0], rbx
0x18001ebb1  push    rdi
0x18001ebb2  sub     rsp, 20h
0x18001ebb6  mov     rbx, rcx
0x18001ebb9  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001ebbf  cmp     ecx, 0FFFFFFFFh
0x18001ebc2  jz      short loc_18001EBD6
0x18001ebc4  lea     r8, aUnloaddiagnost; "UnLoadDiagnosticDll"
0x18001ebcb  mov     edx, 0Ch; dwFlags
0x18001ebd0  call    cs:__imp_TracePrintfExA
0x18001ebd6  test    rbx, rbx
0x18001ebd9  jz      short loc_18001EC1B
0x18001ebdb  cmp     qword ptr [rbx], 0
0x18001ebdf  jz      short loc_18001EC1B
0x18001ebe1  xor     edi, edi
0x18001ebe3  lock dec cs:g_lDiagTabLoaded
0x18001ebea  jnz     short loc_18001EBFA
0x18001ebec  mov     rax, [rbx+18h]
0x18001ebf0  test    rax, rax
0x18001ebf3  jz      short loc_18001EBFA
0x18001ebf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebfa  mov     rcx, [rbx]; hLibModule
0x18001ebfd  call    cs:__imp_FreeLibrary
0x18001ec03  xor     edx, edx; Val
0x18001ec05  mov     [rbx], rdi
0x18001ec08  lea     rcx, [rbx+10h]; void *
0x18001ec0c  mov     [rbx+8], rdi
0x18001ec10  lea     r8d, [rdx+40h]; Size
0x18001ec14  call    memset_0
0x18001ec19  jmp     short loc_18001EC20
0x18001ec1b  mov     edi, 57h ; 'W'
0x18001ec20  mov     rbx, [rsp+28h+arg_0]
0x18001ec25  mov     eax, edi
0x18001ec27  add     rsp, 20h
0x18001ec2b  pop     rdi
0x18001ec2c  retn
```
