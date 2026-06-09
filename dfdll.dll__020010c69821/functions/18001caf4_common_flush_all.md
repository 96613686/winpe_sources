# common_flush_all

- ea: `0x18001caf4`
- end: `0x18001cbd8`
- name: `common_flush_all`
- size: `228`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001ca9c`
- `0x18001cae8`

## callees

- `0x180018bd8`
- `0x180018c38`
- `0x18001b45c`
- `0x18001b468`
- `0x18001ca9c`
- `0x18001caf4`

## pseudocode

```c
__int64 __fastcall common_flush_all(int a1)
{
  char *v2; // rdi
  char *v3; // r14
  __int64 v4; // rbx
  int v5; // eax
  int v6; // edx
  __int64 result; // rax
  unsigned int v8; // [rsp+20h] [rbp-38h]
  unsigned int v9; // [rsp+24h] [rbp-34h]

  v9 = 0;
  v8 = 0;
  _acrt_lock(8);
  v2 = (char *)_piob;
  v3 = (char *)_piob + 8 * nstream;
  while ( v2 != v3 )
  {
    v4 = *(_QWORD *)v2;
    if ( *(_QWORD *)v2 )
    {
      lock_file((FILE *)v4);
      if ( (*(_DWORD *)(v4 + 20) & 0x2000) != 0 )
      {
        if ( a1 == 1 )
        {
          if ( fflush_nolock((FILE *)v4) != -1 )
            ++v9;
        }
        else if ( !a1 && (*(_DWORD *)(v4 + 20) & 2) != 0 )
        {
          v5 = fflush_nolock((FILE *)v4);
          v6 = v8;
          if ( v5 == -1 )
            v6 = -1;
          v8 = v6;
        }
      }
      unlock_file((FILE *)v4);
    }
    v2 += 8;
  }
  _acrt_unlock(8);
  result = v8;
  if ( a1 == 1 )
    return v9;
  return result;
}

```

## disassembly

```asm
0x18001caf4  mov     rax, rsp
0x18001caf7  mov     [rax+8], rbx
0x18001cafb  mov     [rax+18h], rsi
0x18001caff  push    rdi
0x18001cb00  push    r14
0x18001cb02  push    r15
0x18001cb04  sub     rsp, 40h
0x18001cb08  mov     esi, ecx
0x18001cb0a  and     dword ptr [rax-34h], 0
0x18001cb0e  and     dword ptr [rax-38h], 0
0x18001cb12  mov     ecx, 8
0x18001cb17  call    __acrt_lock
0x18001cb1c  nop
0x18001cb1d  mov     rdi, cs:__piob
0x18001cb24  movsxd  rax, cs:_nstream
0x18001cb2b  lea     r14, [rdi+rax*8]
0x18001cb2f  or      r15d, 0FFFFFFFFh
0x18001cb33  mov     [rsp+58h+var_30], rdi
0x18001cb38  cmp     rdi, r14
0x18001cb3b  jz      short loc_18001CBAE
0x18001cb3d  mov     rbx, [rdi]
0x18001cb40  mov     [rsp+58h+arg_8], rbx
0x18001cb45  mov     [rsp+58h+var_28], rbx
0x18001cb4a  test    rbx, rbx
0x18001cb4d  jnz     short loc_18001CB51
0x18001cb4f  jmp     short loc_18001CBA8
0x18001cb51  mov     rcx, rbx; Stream
0x18001cb54  call    _lock_file
0x18001cb59  nop
0x18001cb5a  mov     eax, [rbx+14h]
0x18001cb5d  shr     eax, 0Dh
0x18001cb60  test    al, 1
0x18001cb62  jz      short loc_18001CBA0
0x18001cb64  cmp     esi, 1
0x18001cb67  jnz     short loc_18001CB7C
0x18001cb69  mov     rcx, rbx; Stream
0x18001cb6c  call    _fflush_nolock
0x18001cb71  cmp     eax, r15d
0x18001cb74  jz      short loc_18001CBA0
0x18001cb76  inc     [rsp+58h+var_34]
0x18001cb7a  jmp     short loc_18001CBA0
0x18001cb7c  test    esi, esi
0x18001cb7e  jnz     short loc_18001CBA0
0x18001cb80  mov     eax, [rbx+14h]
0x18001cb83  shr     eax, 1
0x18001cb85  test    al, 1
0x18001cb87  jz      short loc_18001CBA0
0x18001cb89  mov     rcx, rbx; Stream
0x18001cb8c  call    _fflush_nolock
0x18001cb91  mov     edx, [rsp+58h+var_38]
0x18001cb95  cmp     eax, r15d
0x18001cb98  cmovz   edx, r15d
0x18001cb9c  mov     [rsp+58h+var_38], edx
0x18001cba0  mov     rcx, rbx; Stream
0x18001cba3  call    _unlock_file
0x18001cba8  add     rdi, 8
0x18001cbac  jmp     short loc_18001CB33
0x18001cbae  mov     ecx, 8
0x18001cbb3  call    __acrt_unlock
0x18001cbb8  mov     eax, [rsp+58h+var_38]
0x18001cbbc  cmp     esi, 1
0x18001cbbf  cmovz   eax, [rsp+58h+var_34]
0x18001cbc4  mov     rbx, [rsp+58h+arg_0]
0x18001cbc9  mov     rsi, [rsp+58h+arg_10]
0x18001cbce  add     rsp, 40h
0x18001cbd2  pop     r15
0x18001cbd4  pop     r14
0x18001cbd6  pop     rdi
0x18001cbd7  retn
0x18001f7fa  push    rbp
0x18001f7fc  sub     rsp, 20h
0x18001f800  mov     rbp, rdx
0x18001f803  mov     rcx, [rbp+68h]; Stream
0x18001f807  call    _unlock_file
0x18001f80c  nop
0x18001f80d  add     rsp, 20h
0x18001f811  pop     rbp
0x18001f812  retn
0x18001f814  push    rbp
0x18001f816  sub     rsp, 20h
0x18001f81a  mov     rbp, rdx
0x18001f81d  mov     ecx, 8
0x18001f822  add     rsp, 20h
0x18001f826  pop     rbp
0x18001f827  jmp     __acrt_unlock
```
