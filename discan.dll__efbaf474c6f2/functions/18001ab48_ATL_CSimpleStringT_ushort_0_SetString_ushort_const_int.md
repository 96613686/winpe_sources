# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)

- ea: `0x18001ab48`
- end: `0x18001ac1a`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z`
- size: `210`
- prototype: `void __fastcall(__int64 *, const void *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180018bd4`

## callees

- `0x180003640`
- `0x1800161f0`
- `0x18001a5fc`
- `0x18001ab10`
- `0x18001ab48`
- `0x180039010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001abff`
- `msvcrt!memcpy_s` at `0x18001abff`
- `msvcrt!memmove_s` at `0x18001abf0`
- `msvcrt!memmove_s` at `0x18001abf0`

## pseudocode

```c
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(__int64 *a1, const void *a2, int a3)
{
  __int64 v3; // rbx
  ATL::CStringData *v6; // rcx
  __int64 v7; // rbx
  unsigned __int64 v8; // r14
  unsigned __int64 v9; // rsi
  char *v10; // rcx
  rsize_t v11; // rdx

  v3 = a3;
  if ( a3 )
  {
    if ( !a2 )
      ATL::AtlThrowImpl(-2147024809);
    v8 = *(unsigned int *)(*a1 - 16);
    v9 = ((__int64)a2 - *a1) >> 1;
    if ( ((*(_DWORD *)(*a1 - 12) - a3) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, a3);
    v10 = (char *)*a1;
    v11 = 2 * v3;
    if ( v9 > v8 )
      memcpy_s(v10, v11, a2, 2 * v3);
    else
      memmove_s(v10, v11, &v10[2 * v9], 2 * v3);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v3);
  }
  else
  {
    v6 = (ATL::CStringData *)(*a1 - 24);
    if ( *((_DWORD *)v6 + 2) )
    {
      if ( *((int *)v6 + 4) >= 0 )
      {
        v7 = *(_QWORD *)v6;
        ATL::CStringData::Release(v6);
        *a1 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x18001ab48  push    rbx
0x18001ab4a  push    rbp
0x18001ab4b  push    rsi
0x18001ab4c  push    rdi
0x18001ab4d  push    r14
0x18001ab4f  sub     rsp, 20h
0x18001ab53  movsxd  rbx, r8d
0x18001ab56  mov     rbp, rdx
0x18001ab59  mov     rdi, rcx
0x18001ab5c  test    r8d, r8d
0x18001ab5f  jnz     short loc_18001ABA0
0x18001ab61  mov     rcx, [rcx]
0x18001ab64  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ab68  cmp     [rcx+8], r8d
0x18001ab6c  jz      short loc_18001AB9E
0x18001ab6e  cmp     [rcx+10h], r8d
0x18001ab72  jge     short loc_18001AB80
0x18001ab74  xor     edx, edx
0x18001ab76  mov     rcx, rdi
0x18001ab79  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001ab7e  jmp     short loc_18001AB9E
0x18001ab80  mov     rbx, [rcx]
0x18001ab83  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ab88  mov     rax, [rbx]
0x18001ab8b  mov     rcx, rbx
0x18001ab8e  mov     rax, [rax+18h]
0x18001ab92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab97  add     rax, 18h
0x18001ab9b  mov     [rdi], rax
0x18001ab9e  jmp     short loc_18001AC0F
0x18001aba0  test    rbp, rbp
0x18001aba3  jnz     short loc_18001ABB0
0x18001aba5  mov     ecx, 80070057h; int
0x18001abaa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001abb0  mov     rax, [rcx]
0x18001abb3  mov     r14d, [rax-10h]
0x18001abb7  mov     rsi, rbp
0x18001abba  sub     rsi, rax
0x18001abbd  sar     rsi, 1
0x18001abc0  mov     ecx, 1
0x18001abc5  sub     ecx, [rax-8]
0x18001abc8  mov     eax, [rax-0Ch]
0x18001abcb  sub     eax, ebx
0x18001abcd  or      ecx, eax
0x18001abcf  jge     short loc_18001ABDB
0x18001abd1  mov     edx, ebx
0x18001abd3  mov     rcx, rdi
0x18001abd6  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18001abdb  mov     rcx, [rdi]; Destination
0x18001abde  mov     rdx, rbx
0x18001abe1  add     rdx, rdx; DestinationSize
0x18001abe4  cmp     rsi, r14
0x18001abe7  ja      short loc_18001ABF9
0x18001abe9  lea     r8, [rcx+rsi*2]; Source
0x18001abed  mov     r9, rdx; SourceSize
0x18001abf0  call    cs:__imp_memmove_s
0x18001abf6  nop
0x18001abf7  jmp     short loc_18001AC05
0x18001abf9  mov     r9, rdx; SourceSize
0x18001abfc  mov     r8, rbp; Source
0x18001abff  call    cs:__imp_memcpy_s
0x18001ac05  mov     edx, ebx
0x18001ac07  mov     rcx, rdi
0x18001ac0a  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18001ac0f  add     rsp, 20h
0x18001ac13  pop     r14
0x18001ac15  pop     rdi
0x18001ac16  pop     rsi
0x18001ac17  pop     rbp
0x18001ac18  pop     rbx
0x18001ac19  retn
```
