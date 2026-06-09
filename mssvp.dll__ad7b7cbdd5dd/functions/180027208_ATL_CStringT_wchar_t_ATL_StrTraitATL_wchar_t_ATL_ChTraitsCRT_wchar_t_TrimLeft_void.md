# ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimLeft(void)

- ea: `0x180027208`
- end: `0x18002729f`
- name: `?TrimLeft@?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180027178`

## callees

- `0x180005b54`
- `0x18000be84`
- `0x18001cdfc`
- `0x180027208`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180027275`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x180027275`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180027226`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180027226`

## pseudocode

```c
void *const *__fastcall ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::TrimLeft(
        void *const *a1)
{
  unsigned __int16 *i; // rdi
  __int64 v3; // r8
  __int64 v4; // r9
  _BYTE *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  errno_t v9; // eax
  __int64 v10; // r8
  __int64 v11; // r9

  for ( i = (unsigned __int16 *)*a1; (unsigned int)_o_iswspace(*i); ++i )
    ;
  v5 = *a1;
  if ( i != *(unsigned __int16 **)a1 )
  {
    v6 = *((unsigned int *)v5 - 4);
    v7 = ((char *)i - v5) >> 1;
    if ( (int)((*((_DWORD *)v5 - 3) - v6) | (1 - *((_DWORD *)v5 - 2))) < 0 )
      ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(a1, v6, v3, v4);
    v8 = *((_DWORD *)*a1 - 4) - v7;
    v9 = memmove_s(*a1, 2LL * (int)(v8 + 1), (char *)*a1 + 2 * (int)v7, 2LL * (int)(v8 + 1));
    ATL::AtlCrtErrorCheck(v9);
    ATL::CSimpleStringT<wchar_t,0>::SetLength(a1, v8, v10, v11);
  }
  return a1;
}

```

## disassembly

```asm
0x180027208  mov     [rsp+arg_0], rbx
0x18002720d  mov     [rsp+arg_8], rsi
0x180027212  push    rdi
0x180027213  sub     rsp, 20h
0x180027217  mov     rdi, [rcx]
0x18002721a  mov     rsi, rcx
0x18002721d  jmp     short loc_180027223
0x18002721f  add     rdi, 2
0x180027223  movzx   ecx, word ptr [rdi]
0x180027226  call    cs:__imp__o_iswspace
0x18002722c  test    eax, eax
0x18002722e  jnz     short loc_18002721F
0x180027230  mov     rax, [rsi]
0x180027233  cmp     rdi, rax
0x180027236  jz      short loc_18002728C
0x180027238  mov     edx, [rax-10h]
0x18002723b  sub     rdi, rax
0x18002723e  mov     ecx, 1
0x180027243  sar     rdi, 1
0x180027246  sub     ecx, [rax-8]
0x180027249  mov     eax, [rax-0Ch]
0x18002724c  sub     eax, edx
0x18002724e  or      ecx, eax
0x180027250  jge     short loc_18002725A
0x180027252  mov     rcx, rsi
0x180027255  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x18002725a  mov     rcx, [rsi]; Destination
0x18002725d  mov     ebx, [rcx-10h]
0x180027260  sub     ebx, edi
0x180027262  lea     eax, [rbx+1]
0x180027265  movsxd  rdx, eax
0x180027268  movsxd  rax, edi
0x18002726b  add     rdx, rdx; DestinationSize
0x18002726e  mov     r9, rdx; SourceSize
0x180027271  lea     r8, [rcx+rax*2]; Source
0x180027275  call    cs:__imp_memmove_s
0x18002727b  mov     ecx, eax; int
0x18002727d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180027282  mov     edx, ebx
0x180027284  mov     rcx, rsi
0x180027287  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x18002728c  mov     rbx, [rsp+28h+arg_0]
0x180027291  mov     rax, rsi
0x180027294  mov     rsi, [rsp+28h+arg_8]
0x180027299  add     rsp, 20h
0x18002729d  pop     rdi
0x18002729e  retn
```
