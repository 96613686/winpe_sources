# FREB_XML_SERIALIZER::AddString(char const *,ulong)

- ea: `0x1800092e0`
- end: `0x180009359`
- name: `?AddString@FREB_XML_SERIALIZER@@QEAAXPEBDK@Z`
- size: `121`
- prototype: `void __fastcall(FREB_XML_SERIALIZER *this, const char *Src, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004ae4`
- `0x180009520`
- `0x180009948`

## callees

- `0x1800092e0`
- `0x180009690`
- `0x18000ac46`

## pseudocode

```c
void __fastcall FREB_XML_SERIALIZER::AddString(FREB_XML_SERIALIZER *this, const char *Src, int a3)
{
  __int64 v5; // rbx
  unsigned __int8 *Memory; // rax

  if ( Src && !*((_DWORD *)this + 7) )
  {
    if ( a3 )
    {
      if ( !Src[a3 - 1] )
        --a3;
      LODWORD(v5) = a3;
    }
    else
    {
      v5 = -1;
      do
        ++v5;
      while ( Src[v5] );
    }
    Memory = FREB_XML_SERIALIZER::AllocateMemory(this, v5);
    if ( Memory )
      memcpy_0(Memory, Src, (unsigned int)v5);
    else
      *((_DWORD *)this + 7) = -2147024888;
  }
}

```

## disassembly

```asm
0x1800092e0  test    rdx, rdx
0x1800092e3  jz      short locret_180009358
0x1800092e5  mov     [rsp+arg_0], rbx
0x1800092ea  mov     [rsp+arg_8], rsi
0x1800092ef  push    rdi
0x1800092f0  sub     rsp, 20h
0x1800092f4  cmp     dword ptr [rcx+1Ch], 0
0x1800092f8  mov     rsi, rdx
0x1800092fb  mov     rdi, rcx
0x1800092fe  jnz     short loc_180009349
0x180009300  test    r8d, r8d
0x180009303  jnz     short loc_180009314
0x180009305  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180009309  inc     rbx
0x18000930c  cmp     byte ptr [rdx+rbx], 0
0x180009310  jnz     short loc_180009309
0x180009312  jmp     short loc_180009323
0x180009314  lea     ecx, [r8-1]
0x180009318  cmp     byte ptr [rcx+rdx], 0
0x18000931c  cmovz   r8d, ecx
0x180009320  mov     ebx, r8d
0x180009323  mov     edx, ebx; unsigned int
0x180009325  mov     rcx, rdi; this
0x180009328  call    ?AllocateMemory@FREB_XML_SERIALIZER@@QEAAPEAEK@Z; FREB_XML_SERIALIZER::AllocateMemory(ulong)
0x18000932d  test    rax, rax
0x180009330  jnz     short loc_18000933B
0x180009332  mov     dword ptr [rdi+1Ch], 80070008h
0x180009339  jmp     short loc_180009349
0x18000933b  mov     r8d, ebx; Size
0x18000933e  mov     rdx, rsi; Src
0x180009341  mov     rcx, rax; void *
0x180009344  call    memcpy_0
0x180009349  mov     rbx, [rsp+28h+arg_0]
0x18000934e  mov     rsi, [rsp+28h+arg_8]
0x180009353  add     rsp, 20h
0x180009357  pop     rdi
0x180009358  retn
```
