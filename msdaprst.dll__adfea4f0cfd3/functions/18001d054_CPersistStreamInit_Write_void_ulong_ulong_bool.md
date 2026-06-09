# CPersistStreamInit::Write(void *,ulong,ulong *,bool)

- ea: `0x18001d054`
- end: `0x18001d1c0`
- name: `?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z`
- size: `364`
- prototype: `__int64 __usercall@<rax>(CPersistStreamInit *__hidden this@<rcx>, void *Src@<rdx>, size_t Size@<r8>, unsigned int *@<r9>, bool)`
- caller_count: `12`
- callee_count: `7`
- tags: ``

## callers

- `0x18001b558`
- `0x18001c400`
- `0x18001cd30`
- `0x18001d1c8`
- `0x18001d828`
- `0x18001db24`
- `0x18001ea04`
- `0x18001f1bc`
- `0x18001f520`
- `0x18001f680`
- `0x18001f7c8`
- `0x18001fe94`

## callees

- `0x18001b008`
- `0x18001b608`
- `0x18001c0a0`
- `0x18001d054`
- `0x18001fe94`
- `0x18002f092`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::Write(
        CPersistStreamInit *this,
        _BYTE *Src,
        size_t Size,
        unsigned int *a4,
        bool a5)
{
  size_t v5; // rdi
  int v6; // esi
  bool v10; // zf
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // edx

  v5 = (unsigned int)Size;
  v6 = 0;
  *a4 = Size;
  if ( *((_BYTE *)this + 64) )
  {
    if ( (_DWORD)Size == 1 )
    {
      v10 = *Src == 10;
    }
    else
    {
      if ( (_DWORD)Size != 2 || *Src != 13 )
        goto LABEL_15;
      v10 = Src[1] == 10;
    }
  }
  else
  {
    if ( (_DWORD)Size != 2 )
    {
      if ( (_DWORD)Size != 4 || *(_WORD *)Src != 13 || *((_WORD *)Src + 1) != 10 )
        goto LABEL_15;
      goto LABEL_14;
    }
    v10 = *(_WORD *)Src == 10;
  }
  if ( v10 )
LABEL_14:
    *((_DWORD *)this + 13) = 0;
LABEL_15:
  v11 = *((_DWORD *)this + 13);
  if ( (v11 + (unsigned int)Size > 0x6E || v11 + (unsigned int)Size < v11) && a5 )
  {
    v6 = CPersistStreamInit::WriteTag(this, 0x28u, a4);
    if ( v6 < 0 )
      return (unsigned int)v6;
    v6 = CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
    if ( v6 < 0 )
      return (unsigned int)v6;
    *((_DWORD *)this + 13) = 0;
  }
  v12 = *((_DWORD *)this + 2068);
  if ( v12 + (unsigned int)v5 <= 0x2000 && v12 + (unsigned int)v5 >= v12
    || (v6 = CPersistStreamInit::FlushBuffer(this), v6 >= 0) )
  {
    if ( (unsigned int)v5 <= 0x2000 )
    {
      memcpy_0((char *)this + *((unsigned int *)this + 2068) + 80, Src, v5);
      *((_DWORD *)this + 2068) += v5;
    }
    else
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *, _QWORD, unsigned int *))(**((_QWORD **)this + 3) + 32LL))(
             *((_QWORD *)this + 3),
             Src,
             (unsigned int)v5,
             a4);
    }
    v13 = *((_DWORD *)this + 13) + *a4;
    if ( v13 >= *((_DWORD *)this + 13) )
    {
      *((_DWORD *)this + 13) = v13;
    }
    else
    {
      v6 = -2147467259;
      if ( (bidGblFlags & 2) != 0 && off_180049B48[0] )
        bidTraceW(off_1800491F0[0], 3259392, off_180049B48[0], 2147500037LL, 3183);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001d054  push    rbx
0x18001d056  push    rbp
0x18001d057  push    rsi
0x18001d058  push    rdi
0x18001d059  push    r14
0x18001d05b  sub     rsp, 30h
0x18001d05f  mov     edi, r8d
0x18001d062  xor     esi, esi
0x18001d064  mov     [r9], edi
0x18001d067  mov     r14, r9
0x18001d06a  mov     rbp, rdx
0x18001d06d  mov     rbx, rcx
0x18001d070  cmp     [rcx+40h], sil
0x18001d074  jz      short loc_18001D092
0x18001d076  cmp     edi, 1
0x18001d079  jnz     short loc_18001D080
0x18001d07b  cmp     byte ptr [rdx], 0Ah
0x18001d07e  jmp     short loc_18001D08E
0x18001d080  cmp     edi, 2
0x18001d083  jnz     short loc_18001D0B2
0x18001d085  cmp     byte ptr [rdx], 0Dh
0x18001d088  jnz     short loc_18001D0B2
0x18001d08a  cmp     byte ptr [rdx+1], 0Ah
0x18001d08e  jz      short loc_18001D0AF
0x18001d090  jmp     short loc_18001D0B2
0x18001d092  cmp     edi, 2
0x18001d095  jnz     short loc_18001D09D
0x18001d097  cmp     word ptr [rdx], 0Ah
0x18001d09b  jmp     short loc_18001D08E
0x18001d09d  cmp     edi, 4
0x18001d0a0  jnz     short loc_18001D0B2
0x18001d0a2  cmp     word ptr [rdx], 0Dh
0x18001d0a6  jnz     short loc_18001D0B2
0x18001d0a8  cmp     word ptr [rdx+2], 0Ah
0x18001d0ad  jnz     short loc_18001D0B2
0x18001d0af  mov     [rcx+34h], esi
0x18001d0b2  mov     eax, [rcx+34h]
0x18001d0b5  lea     ecx, [rax+rdi]
0x18001d0b8  cmp     ecx, 6Eh ; 'n'
0x18001d0bb  ja      short loc_18001D0C1
0x18001d0bd  cmp     ecx, eax
0x18001d0bf  jnb     short loc_18001D0FE
0x18001d0c1  cmp     [rsp+58h+arg_20], sil
0x18001d0c9  jz      short loc_18001D0FE
0x18001d0cb  mov     r8, r14; unsigned int *
0x18001d0ce  mov     dl, 28h ; '('; unsigned __int8
0x18001d0d0  mov     rcx, rbx; this
0x18001d0d3  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d0d8  mov     esi, eax
0x18001d0da  test    eax, eax
0x18001d0dc  js      loc_18001D1B2
0x18001d0e2  mov     edx, [rbx+30h]; unsigned int
0x18001d0e5  mov     rcx, rbx; this
0x18001d0e8  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001d0ed  mov     esi, eax
0x18001d0ef  test    eax, eax
0x18001d0f1  js      loc_18001D1B2
0x18001d0f7  mov     dword ptr [rbx+34h], 0
0x18001d0fe  mov     eax, [rbx+2050h]
0x18001d104  lea     ecx, [rax+rdi]
0x18001d107  cmp     ecx, 2000h
0x18001d10d  ja      short loc_18001D113
0x18001d10f  cmp     ecx, eax
0x18001d111  jnb     short loc_18001D125
0x18001d113  mov     rcx, rbx; this
0x18001d116  call    ?FlushBuffer@CPersistStreamInit@@AEAAJXZ; CPersistStreamInit::FlushBuffer(void)
0x18001d11b  mov     esi, eax
0x18001d11d  test    eax, eax
0x18001d11f  js      loc_18001D1B2
0x18001d125  mov     rdx, rbp; Src
0x18001d128  cmp     edi, 2000h
0x18001d12e  jbe     short loc_18001D14A
0x18001d130  mov     rcx, [rbx+18h]
0x18001d134  mov     r9, r14
0x18001d137  mov     r8d, edi
0x18001d13a  mov     rax, [rcx]
0x18001d13d  mov     rax, [rax+20h]
0x18001d141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d146  mov     esi, eax
0x18001d148  jmp     short loc_18001D165
0x18001d14a  mov     ecx, [rbx+2050h]
0x18001d150  mov     r8, rdi; Size
0x18001d153  add     rcx, 50h ; 'P'
0x18001d157  add     rcx, rbx; void *
0x18001d15a  call    memcpy_0
0x18001d15f  add     [rbx+2050h], edi
0x18001d165  mov     edx, [r14]
0x18001d168  add     edx, [rbx+34h]
0x18001d16b  cmp     edx, [rbx+34h]
0x18001d16e  jnb     short loc_18001D1AF
0x18001d170  test    byte ptr cs:_bidGblFlags, 2
0x18001d177  mov     esi, 80004005h
0x18001d17c  jz      short loc_18001D1B2
0x18001d17e  mov     rax, cs:off_180049B48; "<CPersistStreamInit::Write|ADO|ERR>  HR"...
0x18001d185  test    rax, rax
0x18001d188  jz      short loc_18001D1B2
0x18001d18a  mov     r8, cs:off_180049B48; "<CPersistStreamInit::Write|ADO|ERR>  HR"...
0x18001d191  mov     r9d, esi
0x18001d194  mov     rcx, cs:off_1800491F0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001d19b  mov     edx, 31BC00h
0x18001d1a0  mov     [rsp+58h+var_38], 0C6Fh
0x18001d1a8  call    _bidTraceW
0x18001d1ad  jmp     short loc_18001D1B2
0x18001d1af  mov     [rbx+34h], edx
0x18001d1b2  mov     eax, esi
0x18001d1b4  add     rsp, 30h
0x18001d1b8  pop     r14
0x18001d1ba  pop     rdi
0x18001d1bb  pop     rsi
0x18001d1bc  pop     rbp
0x18001d1bd  pop     rbx
0x18001d1be  retn
```
