# Dfdll::CString::Equals(ushort const *,bool &)

- ea: `0x18000a21c`
- end: `0x18000a2aa`
- name: `?Equals@CString@Dfdll@@QEAAJPEBGAEA_N@Z`
- size: `142`
- prototype: `__int64 __fastcall(Dfdll::CString *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009e0c`
- `0x18000a2ac`

## callees

- `0x180009f9c`
- `0x18000a21c`

## pseudocode

```c
__int64 __fastcall Dfdll::CString::Equals(Dfdll::CString *this, const unsigned __int16 *a2, bool *a3)
{
  unsigned int v3; // ebx
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  unsigned int v8; // ecx
  int v9; // eax
  int v11; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v6 = a2;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  v8 = v7 == 0 ? 0x80070057 : 0;
  if ( !v7 )
    return v8;
  v11 = 0;
  v9 = Dfdll::CString::Compare(this, a2, v7 != 0 ? 0x7FFFFFFF - v7 : 0, &v11);
  if ( v9 < 0 )
    return (unsigned int)v9;
  else
    *a3 = v11 == 0;
  return v3;
}

```

## disassembly

```asm
0x18000a21c  mov     [rsp+arg_0], rbx
0x18000a221  push    rdi
0x18000a222  sub     rsp, 20h
0x18000a226  xor     ebx, ebx
0x18000a228  mov     rdi, r8
0x18000a22b  mov     r11, rcx
0x18000a22e  test    rdx, rdx
0x18000a231  jz      short loc_18000A296
0x18000a233  mov     r10d, 7FFFFFFFh
0x18000a239  mov     rax, rdx
0x18000a23c  mov     r9d, r10d
0x18000a23f  cmp     [rax], bx
0x18000a242  jz      short loc_18000A24E
0x18000a244  add     rax, 2
0x18000a248  sub     r9, 1
0x18000a24c  jnz     short loc_18000A23F
0x18000a24e  mov     rax, r9
0x18000a251  neg     rax
0x18000a254  mov     rax, r9
0x18000a257  sbb     ecx, ecx
0x18000a259  sub     r10, r9
0x18000a25c  not     ecx
0x18000a25e  and     ecx, 80070057h
0x18000a264  neg     rax
0x18000a267  sbb     r8, r8
0x18000a26a  and     r8, r10; unsigned int
0x18000a26d  test    r9, r9
0x18000a270  jz      short loc_18000A29B
0x18000a272  lea     r9, [rsp+28h+arg_8]; int *
0x18000a277  mov     [rsp+28h+arg_8], ebx
0x18000a27b  mov     rcx, r11; this
0x18000a27e  call    ?Compare@CString@Dfdll@@QEAAJPEBGIAEAH@Z; Dfdll::CString::Compare(ushort const *,uint,int &)
0x18000a283  test    eax, eax
0x18000a285  js      short loc_18000A292
0x18000a287  cmp     [rsp+28h+arg_8], ebx
0x18000a28b  setz    al
0x18000a28e  mov     [rdi], al
0x18000a290  jmp     short loc_18000A29D
0x18000a292  mov     ebx, eax
0x18000a294  jmp     short loc_18000A29D
0x18000a296  mov     ecx, 80070057h
0x18000a29b  mov     ebx, ecx
0x18000a29d  mov     eax, ebx
0x18000a29f  mov     rbx, [rsp+28h+arg_0]
0x18000a2a4  add     rsp, 20h
0x18000a2a8  pop     rdi
0x18000a2a9  retn
```
