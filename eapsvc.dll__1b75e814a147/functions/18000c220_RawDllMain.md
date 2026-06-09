# RawDllMain

- ea: `0x18000c220`
- end: `0x18000c28b`
- name: `RawDllMain`
- size: `107`
- prototype: `__int64 __fastcall(_BOOL8, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000c220`
- `0x18000d780`
- `0x18000d858`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall RawDllMain(_BOOL8 a1, int a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rsi
  int v5; // edi
  __int64 v6; // r8

  v3 = 1;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
      v4 = 0;
      while ( 1 )
      {
        LOBYTE(a1) = 1;
        v5 = (*(&RunTimeInitializer::rawInitTermFns + v4))(a1);
        if ( v5 < 0 )
          break;
        if ( ++v4 )
          return v5 >= 0;
      }
      RunTimeInitializer::OnDetach(&RunTimeInitializer::rawInitTermFns, v4, v6);
      return v5 >= 0;
    }
  }
  else
  {
    RunTimeInitializer::OnDetach(&RunTimeInitializer::rawInitTermFns, 1, a3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000c220  push    rbx
0x18000c222  push    rsi
0x18000c223  push    rdi
0x18000c224  push    r14
0x18000c226  sub     rsp, 28h
0x18000c22a  mov     ebx, 1
0x18000c22f  test    edx, edx
0x18000c231  jz      short loc_18000C270
0x18000c233  cmp     edx, ebx
0x18000c235  jnz     short loc_18000C27F
0x18000c237  xor     esi, esi
0x18000c239  lea     r14, ?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000c240  mov     cl, bl; bool
0x18000c242  mov     rax, ds:(?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB - 1800181A8h)[r14+rsi*8]
0x18000c246  call    _guard_dispatch_icall$thunk$10345483385596137414; HeapAllocator::InitTerm(bool) ...
0x18000c24b  mov     edi, eax
0x18000c24d  test    eax, eax
0x18000c24f  js      short loc_18000C25B
0x18000c251  add     rsi, rbx
0x18000c254  cmp     rsi, rbx
0x18000c257  jb      short loc_18000C240
0x18000c259  jmp     short loc_18000C267
0x18000c25b  mov     rdx, rsi
0x18000c25e  mov     rcx, r14
0x18000c261  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000c266  nop
0x18000c267  not     edi
0x18000c269  shr     edi, 1Fh
0x18000c26c  mov     ebx, edi
0x18000c26e  jmp     short loc_18000C27F
0x18000c270  mov     rdx, rbx
0x18000c273  lea     rcx, ?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000c27a  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000c27f  mov     eax, ebx
0x18000c281  add     rsp, 28h
0x18000c285  pop     r14
0x18000c287  pop     rdi
0x18000c288  pop     rsi
0x18000c289  pop     rbx
0x18000c28a  retn
```
