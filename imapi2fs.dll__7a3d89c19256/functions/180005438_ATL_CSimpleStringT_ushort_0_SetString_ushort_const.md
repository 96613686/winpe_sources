# ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)

- ea: `0x180005438`
- end: `0x180005505`
- name: `?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z`
- size: `205`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: ``

## callers

- `0x180003840`
- `0x180003a80`
- `0x18000578c`
- `0x180007e80`
- `0x18000d024`
- `0x18002dc04`
- `0x18002fb40`
- `0x1800320d4`
- `0x180036c18`
- `0x180036dc8`
- `0x180041f24`
- `0x18004a8c8`
- `0x18004aab0`
- `0x18005cc64`

## callees

- `0x180005438`
- `0x180005568`
- `0x180005cb4`
- `0x18002d064`
- `0x180088010`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800054a2`
- `msvcrt!memmove_s` at `0x1800054a2`
- `msvcrt!memcpy_s` at `0x1800054ad`
- `msvcrt!memcpy_s` at `0x1800054ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CSimpleStringT<unsigned short,0>::SetString(char **a1, char *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // r14
  unsigned __int64 v6; // rsi
  char *v7; // rcx
  rsize_t v8; // rdx
  ATL::CStringData *v9; // rcx
  __int64 v10; // rbx

  if ( !a2 )
    goto LABEL_11;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&a2[2 * v4] );
  if ( (_DWORD)v4 )
  {
    v5 = *((unsigned int *)*a1 - 4);
    v6 = (a2 - *a1) >> 1;
    if ( (int)((*((_DWORD *)*a1 - 3) - v4) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
    v7 = *a1;
    v8 = 2LL * (int)v4;
    if ( v6 > v5 )
      memcpy_s(v7, v8, a2, v8);
    else
      memmove_s(v7, v8, &v7[2 * v6], v8);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)v4);
  }
  else
  {
LABEL_11:
    v9 = (ATL::CStringData *)(*a1 - 24);
    if ( *((_DWORD *)v9 + 2) )
    {
      if ( *((int *)v9 + 4) >= 0 )
      {
        v10 = *(_QWORD *)v9;
        ATL::CStringData::Release(v9);
        *a1 = (char *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10) + 24);
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
0x180005438  push    rbx
0x18000543a  push    rbp
0x18000543b  push    rsi
0x18000543c  push    rdi
0x18000543d  push    r14
0x18000543f  sub     rsp, 20h
0x180005443  mov     rbp, rdx
0x180005446  mov     rdi, rcx
0x180005449  xor     edx, edx
0x18000544b  test    rbp, rbp
0x18000544e  jz      short loc_1800054BF
0x180005450  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005454  inc     rbx
0x180005457  cmp     [rbp+rbx*2+0], dx
0x18000545c  jnz     short loc_180005454
0x18000545e  test    ebx, ebx
0x180005460  jz      short loc_1800054BF
0x180005462  mov     rax, [rcx]
0x180005465  mov     r14d, [rax-10h]
0x180005469  mov     rsi, rbp
0x18000546c  sub     rsi, rax
0x18000546f  sar     rsi, 1
0x180005472  mov     ecx, 1
0x180005477  sub     ecx, [rax-8]
0x18000547a  mov     eax, [rax-0Ch]
0x18000547d  sub     eax, ebx
0x18000547f  or      ecx, eax
0x180005481  jge     short loc_18000548D
0x180005483  mov     edx, ebx
0x180005485  mov     rcx, rdi
0x180005488  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18000548d  mov     rcx, [rdi]; Destination
0x180005490  movsxd  rdx, ebx
0x180005493  add     rdx, rdx; DestinationSize
0x180005496  mov     r9, rdx; SourceSize
0x180005499  cmp     rsi, r14
0x18000549c  ja      short loc_1800054AA
0x18000549e  lea     r8, [rcx+rsi*2]; Source
0x1800054a2  call    cs:__imp_memmove_s
0x1800054a8  jmp     short loc_1800054B3
0x1800054aa  mov     r8, rbp; Source
0x1800054ad  call    cs:__imp_memcpy_s
0x1800054b3  mov     edx, ebx
0x1800054b5  mov     rcx, rdi
0x1800054b8  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800054bd  jmp     short loc_1800054FA
0x1800054bf  mov     rcx, [rcx]
0x1800054c2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800054c6  cmp     [rcx+8], edx
0x1800054c9  jz      short loc_1800054FA
0x1800054cb  cmp     [rcx+10h], edx
0x1800054ce  jge     short loc_1800054DC
0x1800054d0  xor     edx, edx
0x1800054d2  mov     rcx, rdi
0x1800054d5  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x1800054da  jmp     short loc_1800054FA
0x1800054dc  mov     rbx, [rcx]
0x1800054df  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800054e4  mov     rax, [rbx]
0x1800054e7  mov     rcx, rbx
0x1800054ea  mov     rax, [rax+18h]
0x1800054ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f3  add     rax, 18h
0x1800054f7  mov     [rdi], rax
0x1800054fa  add     rsp, 20h
0x1800054fe  pop     r14
0x180005500  pop     rdi
0x180005501  pop     rsi
0x180005502  pop     rbp
0x180005503  pop     rbx
0x180005504  retn
```
