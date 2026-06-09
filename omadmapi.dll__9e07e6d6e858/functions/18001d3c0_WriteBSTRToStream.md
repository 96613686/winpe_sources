# WriteBSTRToStream

- ea: `0x18001d3c0`
- end: `0x18001d473`
- name: `WriteBSTRToStream`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d5b0`

## callees

- `0x18001d3c0`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_SysStringByteLen` at `0x18001d3ec`
- `OLEAUT32!__imp_SysStringByteLen` at `0x18001d3ec`

## pseudocode

```c
__int64 __fastcall WriteBSTRToStream(OLECHAR *a1, __int64 a2)
{
  int v4; // edx
  int v5; // eax
  unsigned int v6; // ecx
  UINT v8; // [rsp+48h] [rbp+10h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v8 = 0;
  v9 = 0;
  if ( a2 )
  {
    v8 = SysStringByteLen(a1);
    v4 = (*(__int64 (__fastcall **)(__int64, UINT *, __int64, int *))(*(_QWORD *)a2 + 32LL))(a2, &v8, 4, &v9);
    if ( v4 >= 0 )
    {
      if ( v9 == 4 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, int *))(*(_QWORD *)a2 + 32LL))(a2, a1, v8, &v9);
        v4 = v5;
        if ( v5 >= 0 )
        {
          v6 = v5;
          if ( v9 != v8 )
            return (unsigned int)-2147467259;
          return v6;
        }
      }
      else
      {
        return (unsigned int)-2147467259;
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d3c0  mov     [rsp+arg_0], rbx
0x18001d3c5  push    rdi
0x18001d3c6  sub     rsp, 30h
0x18001d3ca  mov     [rsp+38h+arg_8], 0
0x18001d3d2  mov     rbx, rdx
0x18001d3d5  mov     [rsp+38h+arg_10], 0
0x18001d3dd  mov     rdi, rcx
0x18001d3e0  test    rdx, rdx
0x18001d3e3  jnz     short loc_18001D3EC
0x18001d3e5  mov     edx, 80004003h
0x18001d3ea  jmp     short loc_18001D465
0x18001d3ec  call    cs:__imp_SysStringByteLen
0x18001d3f3  nop     dword ptr [rax+rax+00h]
0x18001d3f8  mov     [rsp+38h+arg_8], eax
0x18001d3fc  lea     r9, [rsp+38h+arg_10]
0x18001d401  mov     rax, [rbx]
0x18001d404  mov     r8d, 4
0x18001d40a  lea     rdx, [rsp+38h+arg_8]
0x18001d40f  mov     rcx, rbx
0x18001d412  mov     rax, [rax+20h]
0x18001d416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d41b  mov     edx, eax
0x18001d41d  test    eax, eax
0x18001d41f  js      short loc_18001D465
0x18001d421  cmp     [rsp+38h+arg_10], 4
0x18001d426  jz      short loc_18001D42F
0x18001d428  mov     edx, 80004005h
0x18001d42d  jmp     short loc_18001D465
0x18001d42f  mov     rax, [rbx]
0x18001d432  lea     r9, [rsp+38h+arg_10]
0x18001d437  mov     r8d, [rsp+38h+arg_8]
0x18001d43c  mov     rdx, rdi
0x18001d43f  mov     rcx, rbx
0x18001d442  mov     rax, [rax+20h]
0x18001d446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d44b  mov     edx, eax
0x18001d44d  test    eax, eax
0x18001d44f  js      short loc_18001D465
0x18001d451  mov     ecx, eax
0x18001d453  mov     edx, 80004005h
0x18001d458  mov     eax, [rsp+38h+arg_8]
0x18001d45c  cmp     [rsp+38h+arg_10], eax
0x18001d460  cmovnz  ecx, edx
0x18001d463  mov     edx, ecx
0x18001d465  mov     rbx, [rsp+38h+arg_0]
0x18001d46a  mov     eax, edx
0x18001d46c  add     rsp, 30h
0x18001d470  pop     rdi
0x18001d471  retn
```
