# std::basic_ostream<ushort,std::char_traits<ushort>>::_Osfx(void)

- ea: `0x180009260`
- end: `0x1800092b1`
- name: `?_Osfx@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAXXZ`
- size: `81`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180007018`
- `0x180007208`
- `0x1800075d8`
- `0x1800077d0`

## callees

- `0x180009260`
- `0x1800093d4`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::basic_ostream<unsigned short>::_Osfx(__int64 *a1)
{
  __int64 result; // rax
  __int64 v3; // rcx
  __int64 v4; // rcx

  result = *a1;
  v3 = *(int *)(*a1 + 4);
  if ( !*(_DWORD *)((char *)a1 + v3 + 16) && (*((_BYTE *)a1 + v3 + 24) & 2) != 0 )
  {
    v4 = *(__int64 *)((char *)a1 + v3 + 72);
    try
    {
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 104LL))(v4);
      if ( (_DWORD)result == -1 )
        result = std::basic_ios<unsigned short>::setstate((char *)a1 + *(int *)(*a1 + 4), 4);
    }
    catch ( ... )
    {
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009260  push    rbx
0x180009262  sub     rsp, 20h
0x180009266  mov     rbx, rcx
0x180009269  mov     rax, [rcx]
0x18000926c  movsxd  rcx, dword ptr [rax+4]
0x180009270  cmp     dword ptr [rcx+rbx+10h], 0
0x180009275  jnz     short loc_1800092AB
0x180009277  test    byte ptr [rcx+rbx+18h], 2
0x18000927c  jz      short loc_1800092AB
0x18000927e  mov     rcx, [rcx+rbx+48h]
0x180009283  mov     rax, [rcx]
0x180009286  mov     rax, [rax+68h]
0x18000928a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928f  cmp     eax, 0FFFFFFFFh
0x180009292  jnz     short loc_1800092AB
0x180009294  mov     rax, [rbx]
0x180009297  movsxd  rcx, dword ptr [rax+4]
0x18000929b  add     rcx, rbx
0x18000929e  xor     r8d, r8d
0x1800092a1  lea     edx, [r8+4]
0x1800092a5  call    ?setstate@?$basic_ios@GU?$char_traits@G@std@@@std@@QEAAXH_N@Z; std::basic_ios<ushort>::setstate(int,bool)
0x1800092aa  nop
0x1800092ab  add     rsp, 20h
0x1800092af  pop     rbx
0x1800092b0  retn
```
