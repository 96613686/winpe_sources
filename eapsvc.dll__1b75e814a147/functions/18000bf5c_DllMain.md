# DllMain

- ea: `0x18000bf5c`
- end: `0x18000bfd2`
- name: `DllMain`
- size: `118`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001dd4`

## callees

- `0x18000b4d0`
- `0x18000bc60`
- `0x18000bf5c`
- `0x18000d858`
- `0x18000e6c0`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bf73`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000bf73`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // esi
  _BOOL8 v4; // rcx
  __int64 v5; // rdi
  int v6; // ebx
  __int64 v7; // r8

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      v5 = 0;
      while ( 1 )
      {
        LOBYTE(v4) = 1;
        v6 = RunTimeInitializer::initTermFns[v5](v4);
        if ( v6 < 0 )
          break;
        if ( (unsigned __int64)++v5 >= 3 )
          return v6 >= 0;
      }
      RunTimeInitializer::OnDetach(RunTimeInitializer::initTermFns, v5, v7);
      return v6 >= 0;
    }
  }
  else
  {
    RunTimeInitializer::OnDetach(RunTimeInitializer::initTermFns, 3, lpvReserved);
  }
  return v3;
}

```

## disassembly

```asm
0x18000bf5c  push    rbx
0x18000bf5e  push    rsi
0x18000bf5f  push    rdi
0x18000bf60  push    r14
0x18000bf62  sub     rsp, 28h
0x18000bf66  mov     esi, 1
0x18000bf6b  test    edx, edx
0x18000bf6d  jz      short loc_18000BFB5
0x18000bf6f  cmp     edx, esi
0x18000bf71  jnz     short loc_18000BFC6
0x18000bf73  call    cs:__imp_DisableThreadLibraryCalls
0x18000bf79  nop
0x18000bf7a  xor     edi, edi
0x18000bf7c  lea     r14, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000bf83  mov     cl, sil; bool
0x18000bf86  mov     rax, ds:(?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB - 180018190h)[r14+rdi*8]
0x18000bf8a  call    _guard_dispatch_icall$thunk$10345483385596137414; InitTerm(bool)
0x18000bf8f  mov     ebx, eax
0x18000bf91  test    eax, eax
0x18000bf93  js      short loc_18000BFA0
0x18000bf95  add     rdi, rsi
0x18000bf98  cmp     rdi, 3
0x18000bf9c  jb      short loc_18000BF83
0x18000bf9e  jmp     short loc_18000BFAC
0x18000bfa0  mov     rdx, rdi
0x18000bfa3  mov     rcx, r14
0x18000bfa6  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000bfab  nop
0x18000bfac  not     ebx
0x18000bfae  shr     ebx, 1Fh
0x18000bfb1  mov     esi, ebx
0x18000bfb3  jmp     short loc_18000BFC6
0x18000bfb5  mov     edx, 3
0x18000bfba  lea     rcx, ?initTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000bfc1  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000bfc6  mov     eax, esi
0x18000bfc8  add     rsp, 28h
0x18000bfcc  pop     r14
0x18000bfce  pop     rdi
0x18000bfcf  pop     rsi
0x18000bfd0  pop     rbx
0x18000bfd1  retn
```
