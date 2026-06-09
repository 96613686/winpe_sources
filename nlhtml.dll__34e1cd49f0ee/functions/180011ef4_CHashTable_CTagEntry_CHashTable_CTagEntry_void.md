# CHashTable<CTagEntry *>::~CHashTable<CTagEntry *>(void)

- ea: `0x180011ef4`
- end: `0x180011f4e`
- name: `??1?$CHashTable@PEAVCTagEntry@@@@UEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800217f0`
- `0x180024c20`

## callees

- `0x180011ef4`
- `0x180014544`

## pseudocode

```c
void __fastcall CHashTable<CTagEntry *>::~CHashTable<CTagEntry *>(_QWORD *a1)
{
  __int64 i; // rdi
  _QWORD *v3; // rcx
  _QWORD *v4; // rbx

  *a1 = &CHashTable<CTagEntry *>::`vftable';
  for ( i = 0; i != 199; ++i )
  {
    v3 = (_QWORD *)a1[i + 1];
    if ( v3 )
    {
      do
      {
        v4 = (_QWORD *)v3[2];
        operator delete(v3);
        v3 = v4;
      }
      while ( v4 );
    }
  }
}

```

## disassembly

```asm
0x180011ef4  mov     [rsp+arg_0], rbx
0x180011ef9  mov     [rsp+arg_8], rsi
0x180011efe  push    rdi
0x180011eff  sub     rsp, 20h
0x180011f03  lea     rax, ??_7?$CHashTable@PEAVCTagEntry@@@@6B@; const CHashTable<CTagEntry *>::`vftable'
0x180011f0a  mov     rsi, rcx
0x180011f0d  mov     [rcx], rax
0x180011f10  xor     edi, edi
0x180011f12  mov     rcx, [rsi+rdi*8+8]; Block
0x180011f17  test    rcx, rcx
0x180011f1a  jz      short loc_180011F32
0x180011f1c  mov     rbx, [rcx+10h]
0x180011f20  mov     edx, 18h
0x180011f25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180011f2a  mov     rcx, rbx
0x180011f2d  test    rbx, rbx
0x180011f30  jnz     short loc_180011F1C
0x180011f32  inc     rdi
0x180011f35  cmp     rdi, 0C7h
0x180011f3c  jnz     short loc_180011F12
0x180011f3e  mov     rbx, [rsp+28h+arg_0]
0x180011f43  mov     rsi, [rsp+28h+arg_8]
0x180011f48  add     rsp, 20h
0x180011f4c  pop     rdi
0x180011f4d  retn
```
