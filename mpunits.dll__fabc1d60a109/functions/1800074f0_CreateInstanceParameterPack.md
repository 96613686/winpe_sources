# CreateInstanceParameterPack

- ea: `0x1800074f0`
- end: `0x180007565`
- name: `CreateInstanceParameterPack`
- size: `117`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18001ae1c`
- `0x180020a3c`
- `0x180023128`
- `0x180027f84`
- `0x180031370`
- `0x180034b48`
- `0x180036dc8`
- `0x1800387f0`

## callees

- `0x1800074f0`
- `0x180045010`

## import_xrefs

- `miutils!Instance_Construct` at `0x180007507`
- `miutils!Instance_Construct` at `0x180007507`

## pseudocode

```c
__int64 __fastcall CreateInstanceParameterPack(__int64 a1, __int64 *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  unsigned int v6; // edi
  __int64 v7; // [rsp+48h] [rbp+10h] BYREF

  result = Instance_Construct(&ParamPack_Instance_rtti, a2);
  if ( !(_DWORD)result )
  {
    v5 = *a2;
    v7 = a1;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, __int64, int))(v5 + 80))(a2, 0, &v7, 15, 0x40000000);
    if ( v6 )
    {
      if ( *a2 )
        (*(void (__fastcall **)(__int64 *))(*a2 + 8))(a2);
      return v6;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800074f0  mov     [rsp+arg_0], rbx
0x1800074f5  push    rdi
0x1800074f6  sub     rsp, 30h
0x1800074fa  mov     rdi, rcx
0x1800074fd  mov     rbx, rdx
0x180007500  lea     rcx, ParamPack_Instance_rtti
0x180007507  call    cs:__imp_Instance_Construct
0x18000750d  test    eax, eax
0x18000750f  jnz     short loc_18000755A
0x180007511  mov     rax, [rbx]
0x180007514  lea     r8, [rsp+38h+arg_8]
0x180007519  mov     [rsp+38h+arg_8], rdi
0x18000751e  mov     r9d, 0Fh
0x180007524  xor     edx, edx
0x180007526  mov     [rsp+38h+var_18], 40000000h
0x18000752e  mov     rcx, rbx
0x180007531  mov     rax, [rax+50h]
0x180007535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000753a  mov     edi, eax
0x18000753c  test    eax, eax
0x18000753e  jz      short loc_180007558
0x180007540  mov     rax, [rbx]
0x180007543  test    rax, rax
0x180007546  jz      short loc_180007554
0x180007548  mov     rax, [rax+8]
0x18000754c  mov     rcx, rbx
0x18000754f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007554  mov     eax, edi
0x180007556  jmp     short loc_18000755A
0x180007558  xor     eax, eax
0x18000755a  mov     rbx, [rsp+38h+arg_0]
0x18000755f  add     rsp, 30h
0x180007563  pop     rdi
0x180007564  retn
```
