# LoadDiagnosticDll

- ea: `0x18001e510`
- end: `0x18001e65d`
- name: `LoadDiagnosticDll`
- size: `333`
- prototype: `__int64 __fastcall(HMODULE *)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180006dcc`
- `0x18001d24c`
- `0x18002d4a0`
- `0x18002d590`

## callees

- `0x18001e510`
- `0x18001ebac`
- `0x18004d0d2`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e561`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e57d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e57d`
- `rtutils!TracePrintfExA` at `0x18001e539`
- `rtutils!TracePrintfExA` at `0x18001e539`

## string_xrefs

- `0x18001e52d`: `LoadDiagnosticDll`
- `0x18001e554`: `RASMONTR.DLL`

## pseudocode

```c
__int64 __fastcall LoadDiagnosticDll(HMODULE *a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  void (**v4)(void); // rsi
  unsigned int v5; // edi

  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "LoadDiagnosticDll");
  if ( !a1 || *a1 )
  {
    v5 = 87;
  }
  else
  {
    Library = LoadLibraryExW(L"RASMONTR.DLL", 0, 0x800u);
    *a1 = Library;
    if ( !Library
      || (ProcAddress = GetProcAddress(Library, "GetDiagnosticFunctions"), (a1[1] = (HMODULE)ProcAddress) == 0) )
    {
      a1[1] = 0;
      memset_0(a1 + 2, 0, 0x40u);
LABEL_18:
      v5 = 1003;
      goto LABEL_21;
    }
    v4 = (void (**)(void))(a1 + 2);
    memset_0(a1 + 2, 0, 0x40u);
    v5 = ((__int64 (__fastcall *)(HMODULE *))a1[1])(a1 + 2);
    if ( !v5 && *v4 && a1[3] && a1[5] && a1[7] && a1[8] && a1[6] && a1[4] )
    {
      _InterlockedIncrement(&g_lDiagTabLoaded);
      if ( g_lDiagTabLoaded == 1 )
        (*v4)();
      return v5;
    }
    memset_0(a1 + 2, 0, 0x40u);
    a1[1] = 0;
    if ( !v5 )
      goto LABEL_18;
  }
LABEL_21:
  if ( *a1 )
    UnLoadDiagnosticDll(a1);
  return v5;
}

```

## disassembly

```asm
0x18001e510  mov     [rsp+arg_0], rbx
0x18001e515  mov     [rsp+arg_8], rsi
0x18001e51a  push    rdi
0x18001e51b  sub     rsp, 20h
0x18001e51f  mov     rbx, rcx
0x18001e522  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001e528  cmp     ecx, 0FFFFFFFFh
0x18001e52b  jz      short loc_18001E53F
0x18001e52d  lea     r8, aLoaddiagnostic; "LoadDiagnosticDll"
0x18001e534  mov     edx, 0Ch; dwFlags
0x18001e539  call    cs:__imp_TracePrintfExA
0x18001e53f  test    rbx, rbx
0x18001e542  jz      loc_18001E638
0x18001e548  cmp     qword ptr [rbx], 0
0x18001e54c  jnz     loc_18001E638
0x18001e552  xor     edx, edx; hFile
0x18001e554  lea     rcx, aRasmontrDll; "RASMONTR.DLL"
0x18001e55b  mov     r8d, 800h; dwFlags
0x18001e561  call    cs:__imp_LoadLibraryExW
0x18001e567  mov     [rbx], rax
0x18001e56a  test    rax, rax
0x18001e56d  jz      loc_18001E61F
0x18001e573  lea     rdx, aGetdiagnosticf; "GetDiagnosticFunctions"
0x18001e57a  mov     rcx, rax; hModule
0x18001e57d  call    cs:__imp_GetProcAddress
0x18001e583  mov     [rbx+8], rax
0x18001e587  test    rax, rax
0x18001e58a  jz      loc_18001E61F
0x18001e590  xor     edx, edx; Val
0x18001e592  lea     rsi, [rbx+10h]
0x18001e596  mov     rcx, rsi; void *
0x18001e599  lea     r8d, [rdx+40h]; Size
0x18001e59d  call    memset_0
0x18001e5a2  mov     rax, [rbx+8]
0x18001e5a6  mov     rcx, rsi
0x18001e5a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ae  mov     edi, eax
0x18001e5b0  test    eax, eax
0x18001e5b2  jnz     short loc_18001E5FE
0x18001e5b4  cmp     qword ptr [rsi], 0
0x18001e5b8  jz      short loc_18001E5FE
0x18001e5ba  cmp     qword ptr [rbx+18h], 0
0x18001e5bf  jz      short loc_18001E5FE
0x18001e5c1  cmp     qword ptr [rbx+28h], 0
0x18001e5c6  jz      short loc_18001E5FE
0x18001e5c8  cmp     qword ptr [rbx+38h], 0
0x18001e5cd  jz      short loc_18001E5FE
0x18001e5cf  cmp     qword ptr [rbx+40h], 0
0x18001e5d4  jz      short loc_18001E5FE
0x18001e5d6  cmp     qword ptr [rbx+30h], 0
0x18001e5db  jz      short loc_18001E5FE
0x18001e5dd  cmp     qword ptr [rbx+20h], 0
0x18001e5e2  jz      short loc_18001E5FE
0x18001e5e4  lock inc cs:g_lDiagTabLoaded
0x18001e5eb  cmp     cs:g_lDiagTabLoaded, 1
0x18001e5f2  jnz     short loc_18001E64B
0x18001e5f4  mov     rax, [rsi]
0x18001e5f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5fc  jmp     short loc_18001E64B
0x18001e5fe  xor     edx, edx; Val
0x18001e600  mov     rcx, rsi; void *
0x18001e603  lea     r8d, [rdx+40h]; Size
0x18001e607  call    memset_0
0x18001e60c  mov     qword ptr [rbx+8], 0
0x18001e614  test    edi, edi
0x18001e616  jnz     short loc_18001E63D
0x18001e618  mov     edi, 3EBh
0x18001e61d  jmp     short loc_18001E63D
0x18001e61f  xor     edx, edx; Val
0x18001e621  mov     qword ptr [rbx+8], 0
0x18001e629  lea     rcx, [rbx+10h]; void *
0x18001e62d  lea     r8d, [rdx+40h]; Size
0x18001e631  call    memset_0
0x18001e636  jmp     short loc_18001E618
0x18001e638  mov     edi, 57h ; 'W'
0x18001e63d  cmp     qword ptr [rbx], 0
0x18001e641  jz      short loc_18001E64B
0x18001e643  mov     rcx, rbx
0x18001e646  call    UnLoadDiagnosticDll
0x18001e64b  mov     rbx, [rsp+28h+arg_0]
0x18001e650  mov     eax, edi
0x18001e652  mov     rsi, [rsp+28h+arg_8]
0x18001e657  add     rsp, 20h
0x18001e65b  pop     rdi
0x18001e65c  retn
```
