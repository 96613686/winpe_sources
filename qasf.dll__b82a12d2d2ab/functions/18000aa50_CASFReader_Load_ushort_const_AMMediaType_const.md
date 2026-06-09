# CASFReader::Load(ushort const *,_AMMediaType const *)

- ea: `0x18000aa50`
- end: `0x18000aafc`
- name: `?Load@CASFReader@@UEAAJPEBGPEBU_AMMediaType@@@Z`
- size: `172`
- prototype: `int(CASFReader *__hidden this, const unsigned __int16 *, const struct _AMMediaType *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001014`
- `0x180002660`
- `0x18000aa50`
- `0x18000ab04`
- `0x18001f010`

## pseudocode

```c
__int64 __fastcall CASFReader::Load(CASFReader *this, unsigned __int16 *a2, const struct _AMMediaType *a3)
{
  __int64 v4; // rcx
  __int64 v7; // rax
  unsigned __int64 v8; // rbp
  unsigned __int16 *v9; // rax
  unsigned __int64 v10; // rdx

  v4 = *((_QWORD *)this + 44);
  if ( v4 )
    return (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, const struct _AMMediaType *))(*(_QWORD *)v4 + 24LL))(
             v4,
             a2,
             a3);
  if ( !a2 )
    return 2147500035LL;
  if ( *((_QWORD *)this + 15) )
    return 2147500037LL;
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v9 = (unsigned __int16 *)operator new[](saturated_mul(v7 + 1, 2u));
  *((_QWORD *)this + 15) = v9;
  if ( !v9 )
    return 2147942414LL;
  StringCchCopyW(v9, v8, a2);
  if ( *((_QWORD *)this - 3) )
    return CASFReader::LoadInternal((CASFReader *)((char *)this - 120), v10);
  else
    return 0;
}

```

## disassembly

```asm
0x18000aa50  push    rbx
0x18000aa52  push    rbp
0x18000aa53  push    rsi
0x18000aa54  push    rdi
0x18000aa55  push    r14
0x18000aa57  sub     rsp, 20h
0x18000aa5b  mov     rdi, rcx
0x18000aa5e  xor     r14d, r14d
0x18000aa61  mov     rcx, [rcx+160h]
0x18000aa68  mov     rbx, rdx
0x18000aa6b  test    rcx, rcx
0x18000aa6e  jz      short loc_18000AA7E
0x18000aa70  mov     rax, [rcx]
0x18000aa73  mov     rax, [rax+18h]
0x18000aa77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa7c  jmp     short loc_18000AAF1
0x18000aa7e  test    rbx, rbx
0x18000aa81  jnz     short loc_18000AA8A
0x18000aa83  mov     eax, 80004003h
0x18000aa88  jmp     short loc_18000AAF1
0x18000aa8a  cmp     [rdi+78h], r14
0x18000aa8e  jz      short loc_18000AA97
0x18000aa90  mov     eax, 80004005h
0x18000aa95  jmp     short loc_18000AAF1
0x18000aa97  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000aa9b  mov     rax, rcx
0x18000aa9e  inc     rax
0x18000aaa1  cmp     [rdx+rax*2], r14w
0x18000aaa6  jnz     short loc_18000AA9E
0x18000aaa8  lea     rbp, [rax+1]
0x18000aaac  mov     eax, 2
0x18000aab1  mul     rbp
0x18000aab4  cmovb   rax, rcx
0x18000aab8  mov     rcx, rax; unsigned __int64
0x18000aabb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000aac0  mov     [rdi+78h], rax
0x18000aac4  test    rax, rax
0x18000aac7  jnz     short loc_18000AAD0
0x18000aac9  mov     eax, 8007000Eh
0x18000aace  jmp     short loc_18000AAF1
0x18000aad0  mov     r8, rbx; unsigned __int16 *
0x18000aad3  mov     rdx, rbp; unsigned __int64
0x18000aad6  mov     rcx, rax; unsigned __int16 *
0x18000aad9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aade  cmp     [rdi-18h], r14
0x18000aae2  jnz     short loc_18000AAE8
0x18000aae4  xor     eax, eax
0x18000aae6  jmp     short loc_18000AAF1
0x18000aae8  lea     rcx, [rdi-78h]; this
0x18000aaec  call    ?LoadInternal@CASFReader@@QEAAJXZ; CASFReader::LoadInternal(void)
0x18000aaf1  add     rsp, 20h
0x18000aaf5  pop     r14
0x18000aaf7  pop     rdi
0x18000aaf8  pop     rsi
0x18000aaf9  pop     rbp
0x18000aafa  pop     rbx
0x18000aafb  retn
```
