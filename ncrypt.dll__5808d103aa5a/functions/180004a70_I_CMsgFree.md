# I_CMsgFree

- ea: `0x180004a70`
- end: `0x180004aff`
- name: `I_CMsgFree`
- size: `143`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003a68`
- `0x1800053ac`
- `0x180006090`
- `0x180007958`

## callees

- `0x180004a70`
- `0x180004b08`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall I_CMsgFree(__int64 a1)
{
  unsigned int v3; // eax
  int v4; // eax
  __int64 v5; // rcx

  if ( !*(_DWORD *)(a1 + 4) )
  {
    if ( *(_QWORD *)(a1 + 208) )
      (*(void (**)(void))(a1 + 32))();
    if ( *(_QWORD *)(a1 + 56) )
      (*(void (**)(void))(a1 + 32))();
  }
  CNG_DestroyBCryptKeyAndAlgorithmInfo((void *)(a1 + 88));
  if ( *(_QWORD *)(a1 + 72) )
  {
    while ( 1 )
    {
      v4 = *(_DWORD *)(a1 + 80);
      v5 = *(_QWORD *)(a1 + 72);
      if ( !v4 )
        break;
      v3 = v4 - 1;
      *(_DWORD *)(a1 + 80) = v3;
      (*(void (__fastcall **)(_QWORD))(a1 + 32))(*(_QWORD *)(v5 + 8LL * v3));
    }
    *(_DWORD *)(a1 + 80) = -1;
    (*(void (__fastcall **)(__int64))(a1 + 32))(v5);
  }
  return (*(__int64 (__fastcall **)(__int64))(a1 + 32))(a1);
}

```

## disassembly

```asm
0x180004a70  mov     [rsp+arg_0], rbx
0x180004a75  push    rdi
0x180004a76  sub     rsp, 20h
0x180004a7a  cmp     dword ptr [rcx+4], 0
0x180004a7e  mov     rbx, rcx
0x180004a81  jz      short loc_180004AA9
0x180004a83  lea     rcx, [rbx+58h]; void *
0x180004a87  call    CNG_DestroyBCryptKeyAndAlgorithmInfo
0x180004a8c  cmp     qword ptr [rbx+48h], 0
0x180004a91  jnz     short loc_180004AE4
0x180004a93  mov     rax, [rbx+20h]
0x180004a97  mov     rcx, rbx
0x180004a9a  mov     rbx, [rsp+28h+arg_0]
0x180004a9f  add     rsp, 20h
0x180004aa3  pop     rdi
0x180004aa4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa9  mov     rcx, [rcx+0D0h]
0x180004ab0  test    rcx, rcx
0x180004ab3  jz      short loc_180004ABE
0x180004ab5  mov     rax, [rbx+20h]
0x180004ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abe  mov     rcx, [rbx+38h]
0x180004ac2  test    rcx, rcx
0x180004ac5  jz      short loc_180004A83
0x180004ac7  mov     rax, [rbx+20h]
0x180004acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad0  jmp     short loc_180004A83
0x180004ad2  dec     eax
0x180004ad4  mov     [rbx+50h], eax
0x180004ad7  mov     rcx, [rcx+rax*8]
0x180004adb  mov     rax, [rbx+20h]
0x180004adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae4  mov     eax, [rbx+50h]
0x180004ae7  mov     rcx, [rbx+48h]
0x180004aeb  test    eax, eax
0x180004aed  jnz     short loc_180004AD2
0x180004aef  dec     eax
0x180004af1  mov     [rbx+50h], eax
0x180004af4  mov     rax, [rbx+20h]
0x180004af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004afd  jmp     short loc_180004A93
```
