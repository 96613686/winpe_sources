# RawDllMain

- ea: `0x18000ad40`
- end: `0x18000adac`
- name: `RawDllMain`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x18000ad40`
- `0x18000d2d0`
- `0x18000d384`
- `0x18000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ad40  push    rbx
0x18000ad42  push    rsi
0x18000ad43  push    rdi
0x18000ad44  push    r14
0x18000ad46  sub     rsp, 28h
0x18000ad4a  mov     ebx, 1
0x18000ad4f  test    edx, edx
0x18000ad51  jz      short loc_18000AD90
0x18000ad53  cmp     edx, ebx
0x18000ad55  jnz     short loc_18000AD9F
0x18000ad57  xor     esi, esi
0x18000ad59  lea     r14, ?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000ad60  mov     cl, bl; bool
0x18000ad62  mov     rax, ds:(?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB - 1800100D0h)[r14+rsi*8]
0x18000ad66  call    _guard_dispatch_icall$thunk$10345483385596137414; HeapAllocator::InitTerm(bool) ...
0x18000ad6b  mov     edi, eax
0x18000ad6d  test    eax, eax
0x18000ad6f  js      short loc_18000AD7B
0x18000ad71  add     rsi, rbx
0x18000ad74  cmp     rsi, rbx
0x18000ad77  jb      short loc_18000AD60
0x18000ad79  jmp     short loc_18000AD87
0x18000ad7b  mov     rdx, rsi
0x18000ad7e  mov     rcx, r14
0x18000ad81  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000ad86  nop
0x18000ad87  not     edi
0x18000ad89  shr     edi, 1Fh
0x18000ad8c  mov     ebx, edi
0x18000ad8e  jmp     short loc_18000AD9F
0x18000ad90  mov     rdx, rbx
0x18000ad93  lea     rcx, ?rawInitTermFns@RunTimeInitializer@@0QBQ6AJ_N@_EB
0x18000ad9a  call    ?OnDetach@RunTimeInitializer@@CAXPEBQ6AJ_N@_E_K@Z; RunTimeInitializer::OnDetach(long (*const *)(bool),...)
0x18000ad9f  mov     eax, ebx
0x18000ada1  add     rsp, 28h
0x18000ada5  pop     r14
0x18000ada7  pop     rdi
0x18000ada8  pop     rsi
0x18000ada9  pop     rbx
0x18000adaa  retn
```
