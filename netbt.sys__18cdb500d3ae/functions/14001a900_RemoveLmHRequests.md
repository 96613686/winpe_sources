# RemoveLmHRequests

- ea: `0x14001a900`
- end: `0x14001aa03`
- name: `RemoveLmHRequests`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001a7c8`

## callees

- `0x140007be8`
- `0x14001a900`

## pseudocode

```c
__int64 *__fastcall RemoveLmHRequests(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char v5; // si
  __int64 v6; // rcx
  __int64 *result; // rax
  _QWORD *v11; // rax
  __int64 **v12; // r8
  __int64 **v13; // r8
  __int64 *v14; // rcx

  v5 = 0;
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    if ( *(_DWORD *)(v6 + 56) || *(_QWORD *)(v6 + 40) == a4 )
    {
      *(_QWORD *)(a1 + 24) = 0;
      v11 = *(_QWORD **)(a2 + 8);
      if ( *v11 != a2 )
LABEL_5:
        __fastfail(3u);
      *(_QWORD *)v6 = a2;
      *(_QWORD *)(v6 + 8) = v11;
      *v11 = v6;
      *(_QWORD *)(a2 + 8) = v6;
      NbtCancelCancelRoutine(*(_QWORD *)(*(_QWORD *)(v6 + 24) + 24LL));
    }
    else
    {
      v5 = 1;
      *(_DWORD *)(v6 + 56) = 1;
    }
  }
  result = *(__int64 **)(a1 + 8);
  if ( result != (__int64 *)(a1 + 8) )
  {
    while ( 1 )
    {
      v14 = (__int64 *)*result;
      if ( *((_DWORD *)result + 14) || result[5] == a4 )
      {
        if ( (__int64 *)v14[1] != result )
          goto LABEL_5;
        v12 = (__int64 **)result[1];
        if ( *v12 != result )
          goto LABEL_5;
        *v12 = v14;
        v14[1] = (__int64)v12;
        v13 = *(__int64 ***)(a2 + 8);
        if ( *v13 != (__int64 *)a2 )
          goto LABEL_5;
        *result = a2;
        result[1] = (__int64)v13;
        *v13 = result;
        *(_QWORD *)(a2 + 8) = result;
      }
      else
      {
        *((_DWORD *)result + 14) = 1;
      }
      result = v14;
      if ( v14 == (__int64 *)(a1 + 8) )
        goto LABEL_19;
    }
  }
  if ( v5 )
  {
LABEL_19:
    if ( a3 )
      *(_WORD *)(a3 + 256) |= 1u;
  }
  return result;
}

```

## disassembly

```asm
0x14001a900  push    rbx
0x14001a902  push    rbp
0x14001a903  push    rsi
0x14001a904  push    rdi
0x14001a905  push    r12
0x14001a907  push    r14
0x14001a909  sub     rsp, 28h
0x14001a90d  mov     rbp, rcx
0x14001a910  xor     sil, sil
0x14001a913  mov     rcx, [rcx+18h]
0x14001a917  mov     r14, r9
0x14001a91a  mov     rdi, r8
0x14001a91d  mov     rbx, rdx
0x14001a920  mov     r12d, 1
0x14001a926  test    rcx, rcx
0x14001a929  jnz     loc_14001A9BA
0x14001a92f  lea     rdx, [rbp+8]
0x14001a933  mov     rax, [rdx]
0x14001a936  cmp     rax, rdx
0x14001a939  jnz     loc_14001A9D2
0x14001a93f  test    sil, sil
0x14001a942  jnz     loc_14001A9ED
0x14001a948  add     rsp, 28h
0x14001a94c  pop     r14
0x14001a94e  pop     r12
0x14001a950  pop     rdi
0x14001a951  pop     rsi
0x14001a952  pop     rbp
0x14001a953  pop     rbx
0x14001a954  retn
0x14001a956  mov     ecx, 3
0x14001a95b  int     29h; Win8: RtlFailFast(ecx)
0x14001a95d  mov     qword ptr [rbp+18h], 0
0x14001a965  mov     rax, [rdx+8]
0x14001a969  cmp     [rax], rbx
0x14001a96c  jnz     short loc_14001A956
0x14001a96e  mov     [rcx], rbx
0x14001a971  mov     [rcx+8], rax
0x14001a975  mov     [rax], rcx
0x14001a978  mov     [rdx+8], rcx
0x14001a97c  mov     rcx, [rcx+18h]
0x14001a980  mov     rcx, [rcx+18h]
0x14001a984  call    NbtCancelCancelRoutine
0x14001a989  jmp     short loc_14001A92F
0x14001a98b  cmp     [rcx+8], rax
0x14001a98f  jnz     short loc_14001A956
0x14001a991  mov     r8, [rax+8]
0x14001a995  cmp     [r8], rax
0x14001a998  jnz     short loc_14001A956
0x14001a99a  mov     [r8], rcx
0x14001a99d  mov     [rcx+8], r8
0x14001a9a1  mov     r8, [rbx+8]
0x14001a9a5  cmp     [r8], rbx
0x14001a9a8  jnz     short loc_14001A956
0x14001a9aa  mov     [rax], rbx
0x14001a9ad  mov     [rax+8], r8
0x14001a9b1  mov     [r8], rax
0x14001a9b4  mov     [rbx+8], rax
0x14001a9b8  jmp     short loc_14001A9E5
0x14001a9ba  cmp     dword ptr [rcx+38h], 0
0x14001a9be  jnz     short loc_14001A95D
0x14001a9c0  cmp     [rcx+28h], r14
0x14001a9c4  jz      short loc_14001A95D
0x14001a9c6  mov     sil, r12b
0x14001a9c9  mov     [rcx+38h], r12d
0x14001a9cd  jmp     loc_14001A92F
0x14001a9d2  cmp     dword ptr [rax+38h], 0
0x14001a9d6  mov     rcx, [rax]
0x14001a9d9  jnz     short loc_14001A98B
0x14001a9db  cmp     [rax+28h], r14
0x14001a9df  jz      short loc_14001A98B
0x14001a9e1  mov     [rax+38h], r12d
0x14001a9e5  mov     rax, rcx
0x14001a9e8  cmp     rcx, rdx
0x14001a9eb  jnz     short loc_14001A9D2
0x14001a9ed  test    rdi, rdi
0x14001a9f0  jz      loc_14001A948
0x14001a9f6  or      [rdi+100h], r12w
0x14001a9fe  jmp     loc_14001A948
```
