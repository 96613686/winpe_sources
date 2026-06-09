# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)

- ea: `0x18004aec8`
- end: `0x18004af63`
- name: `?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z`
- size: `155`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180005a74`
- `0x18000cb00`
- `0x18000ef40`
- `0x18000f650`

## callees

- `0x180005cb4`
- `0x180005cec`
- `0x180018db4`
- `0x180036bec`
- `0x18004aec8`

## import_xrefs

- `msvcrt!memmove_s` at `0x18004af2f`
- `msvcrt!memmove_s` at `0x18004af2f`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
        _QWORD *a1,
        int a2,
        int a3)
{
  int v3; // edi
  int v5; // ebx
  int v6; // esi
  __int64 Buffer; // rax
  errno_t v8; // eax

  v3 = 0;
  if ( a2 >= 0 )
    v3 = a2;
  v5 = 0;
  if ( a3 >= 0 )
    v5 = a3;
  if ( 0x7FFFFFFF - v5 < v3 )
    ATL::AtlThrowImpl(-2147024809);
  v6 = *(_DWORD *)(*a1 - 16LL);
  if ( v5 + v3 > v6 )
    v5 = v6 - v3;
  if ( v5 > 0 )
  {
    Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(a1);
    v8 = memmove_s(
           (void *const)(Buffer + 2LL * v3),
           2LL * (v6 - v3 - v5 + 1),
           (const void *const)(Buffer + 2 * (v3 + (__int64)v5)),
           2LL * (v6 - v3 - v5 + 1));
    ATL::AtlCrtErrorCheck(v8);
    ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, (unsigned int)(v6 - v5));
  }
  return *(unsigned int *)(*a1 - 16LL);
}

```

## disassembly

```asm
0x18004aec8  push    rbx
0x18004aeca  push    rsi
0x18004aecb  push    rdi
0x18004aecc  push    r14
0x18004aece  sub     rsp, 28h
0x18004aed2  xor     edi, edi
0x18004aed4  mov     eax, 7FFFFFFFh
0x18004aed9  test    edx, edx
0x18004aedb  mov     r14, rcx
0x18004aede  cmovns  edi, edx
0x18004aee1  xor     ebx, ebx
0x18004aee3  test    r8d, r8d
0x18004aee6  cmovns  ebx, r8d
0x18004aeea  sub     eax, ebx
0x18004aeec  cmp     eax, edi
0x18004aeee  jl      short loc_18004AF58
0x18004aef0  mov     rax, [r14]
0x18004aef3  lea     ecx, [rbx+rdi]
0x18004aef6  mov     esi, [rax-10h]
0x18004aef9  cmp     ecx, esi
0x18004aefb  jle     short loc_18004AF01
0x18004aefd  mov     ebx, esi
0x18004aeff  sub     ebx, edi
0x18004af01  test    ebx, ebx
0x18004af03  jle     short loc_18004AF48
0x18004af05  mov     rcx, r14
0x18004af08  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18004af0d  movsxd  r9, edi
0x18004af10  mov     ecx, esi
0x18004af12  sub     ecx, edi
0x18004af14  sub     ecx, ebx
0x18004af16  inc     ecx
0x18004af18  movsxd  rdx, ecx
0x18004af1b  add     rdx, rdx; DestinationSize
0x18004af1e  movsxd  rcx, ebx
0x18004af21  add     rcx, r9
0x18004af24  lea     r8, [rax+rcx*2]; Source
0x18004af28  lea     rcx, [rax+r9*2]; Destination
0x18004af2c  mov     r9, rdx; SourceSize
0x18004af2f  call    cs:__imp_memmove_s
0x18004af35  mov     ecx, eax; int
0x18004af37  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18004af3c  sub     esi, ebx
0x18004af3e  mov     rcx, r14
0x18004af41  mov     edx, esi
0x18004af43  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18004af48  mov     rax, [r14]
0x18004af4b  mov     eax, [rax-10h]
0x18004af4e  add     rsp, 28h
0x18004af52  pop     r14
0x18004af54  pop     rdi
0x18004af55  pop     rsi
0x18004af56  pop     rbx
0x18004af57  retn
0x18004af58  mov     ecx, 80070057h; int
0x18004af5d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
