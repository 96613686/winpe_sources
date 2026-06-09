# operator<<(TSTR &,WriteError const &)

- ea: `0x180002474`
- end: `0x180002608`
- name: `??6@YAAEAVTSTR@@AEAV0@AEBVWriteError@@@Z`
- size: `404`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800026d0`

## callees

- `0x180002474`
- `0x180002610`
- `0x180002f60`
- `0x180003078`
- `0x1800036c0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180002597`
- `KERNEL32!FormatMessageW` at `0x180002597`

## pseudocode

```c
_QWORD *__fastcall operator<<(_QWORD *Src, unsigned int *a2)
{
  _WORD *v4; // rdx
  __int64 v5; // r8
  void *v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rdx
  DWORD nSize; // ebp
  _QWORD *v10; // rcx
  WCHAR *lpBuffer; // rbx
  signed int v12; // edx
  int v13; // eax
  unsigned __int64 v14; // r8
  _QWORD *v15; // rcx
  __int64 v17; // [rsp+40h] [rbp-38h] BYREF
  int v18; // [rsp+48h] [rbp-30h]

  std::wstring::append(Src, L"[Error");
  if ( *((_QWORD *)a2 + 1) )
  {
    std::wstring::append(Src, L" ");
    v4 = (_WORD *)*((_QWORD *)a2 + 1);
    if ( v4 )
    {
      if ( *v4 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v4[v5] );
      }
      std::wstring::append(Src, v4);
    }
  }
  std::wstring::append(Src, L": hr=0x");
  v17 = *a2;
  v18 = -1;
  v6 = operator<<(Src, &v17);
  std::wstring::append(v6, L" - ");
  if ( *a2 == 1 )
  {
    std::wstring::append(Src, L"S_FALSE");
  }
  else
  {
    v7 = *((_DWORD *)Src + 8);
    if ( v7 == -1 )
      v7 = *((_DWORD *)Src + 4);
    v8 = Src[3];
    nSize = ~v7 + *((_DWORD *)Src + 6);
    *((_DWORD *)Src + 8) = *((_DWORD *)Src + 4);
    if ( v8 < 8 )
      v10 = Src;
    else
      v10 = (_QWORD *)*Src;
    lpBuffer = (WCHAR *)v10 + Src[2];
    std::wstring::resize(Src);
    v12 = FormatMessageW(0x1000u, 0, *a2, 0x400u, lpBuffer, nSize, 0);
    if ( v12 > 2 )
      v12 -= 2;
    v13 = *((_DWORD *)Src + 8);
    if ( v13 != -1 )
    {
      v14 = (unsigned int)(v13 + v12);
      if ( Src[2] <= v14 )
        std::wstring::_Xran();
      if ( Src[3] < 8u )
        v15 = Src;
      else
        v15 = (_QWORD *)*Src;
      *((_WORD *)v15 + v14) = 0;
      std::wstring::resize(Src);
      *((_DWORD *)Src + 8) = -1;
    }
  }
  std::wstring::append(Src, L"]");
  return Src;
}

```

## disassembly

```asm
0x180002474  push    rbx
0x180002476  push    rbp
0x180002477  push    rsi
0x180002478  push    rdi
0x180002479  push    r14
0x18000247b  sub     rsp, 50h
0x18000247f  mov     rsi, rdx
0x180002482  mov     r8d, 6
0x180002488  lea     rdx, aError; "[Error"
0x18000248f  mov     rdi, rcx
0x180002492  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002497  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18000249b  xor     r14d, r14d
0x18000249e  cmp     [rsi+8], r14
0x1800024a2  jz      short loc_1800024E0
0x1800024a4  lea     r8d, [rbp+2]
0x1800024a8  mov     rcx, rdi; Src
0x1800024ab  lea     rdx, asc_18001BF08; " "
0x1800024b2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800024b7  mov     rdx, [rsi+8]; void *
0x1800024bb  test    rdx, rdx
0x1800024be  jz      short loc_1800024E0
0x1800024c0  cmp     [rdx], r14w
0x1800024c4  jnz     short loc_1800024CB
0x1800024c6  mov     r8d, r14d
0x1800024c9  jmp     short loc_1800024D8
0x1800024cb  mov     r8, rbp
0x1800024ce  inc     r8
0x1800024d1  cmp     [rdx+r8*2], r14w
0x1800024d6  jnz     short loc_1800024CE
0x1800024d8  mov     rcx, rdi; Src
0x1800024db  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800024e0  mov     ebx, 7
0x1800024e5  lea     rdx, aHr0x; ": hr=0x"
0x1800024ec  mov     r8d, ebx
0x1800024ef  mov     rcx, rdi; Src
0x1800024f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800024f7  mov     eax, [rsi]
0x1800024f9  lea     rdx, [rsp+78h+var_38]
0x1800024fe  mov     rcx, rdi; Src
0x180002501  mov     [rsp+78h+var_38], rax
0x180002506  mov     [rsp+78h+var_30], ebp
0x18000250a  call    ??6@YAAEAVTSTR@@AEAV0@AEBVWriteHex@@@Z; operator<<(TSTR &,WriteHex const &)
0x18000250f  mov     rcx, rax; Src
0x180002512  lea     r8d, [rbx-4]
0x180002516  lea     rdx, asc_18001BF10; " - "
0x18000251d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002522  cmp     dword ptr [rsi], 1
0x180002525  jnz     short loc_18000253E
0x180002527  mov     r8d, ebx
0x18000252a  lea     rdx, aSFalse; "S_FALSE"
0x180002531  mov     rcx, rdi; Src
0x180002534  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x180002539  jmp     loc_1800025DF
0x18000253e  mov     eax, [rdi+20h]
0x180002541  mov     ecx, [rdi+18h]
0x180002544  cmp     eax, 0FFFFFFFFh
0x180002547  jnz     short loc_18000254C
0x180002549  mov     eax, [rdi+10h]
0x18000254c  mov     rdx, [rdi+18h]
0x180002550  not     eax
0x180002552  lea     ebp, [rax+rcx]
0x180002555  mov     eax, [rdi+10h]
0x180002558  mov     [rdi+20h], eax
0x18000255b  cmp     rdx, 8
0x18000255f  jb      short loc_180002566
0x180002561  mov     rcx, [rdi]
0x180002564  jmp     short loc_180002569
0x180002566  mov     rcx, rdi
0x180002569  mov     rax, [rdi+10h]
0x18000256d  lea     rbx, [rcx+rax*2]
0x180002571  mov     rcx, rdi
0x180002574  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::resize(unsigned __int64)
0x180002579  mov     r8d, [rsi]; dwMessageId
0x18000257c  mov     r9d, 400h; dwLanguageId
0x180002582  mov     [rsp+78h+Arguments], r14; Arguments
0x180002587  xor     edx, edx; lpSource
0x180002589  mov     [rsp+78h+nSize], ebp; nSize
0x18000258d  mov     ecx, 1000h; dwFlags
0x180002592  mov     [rsp+78h+lpBuffer], rbx; lpBuffer
0x180002597  call    cs:__imp_FormatMessageW
0x18000259d  mov     edx, eax
0x18000259f  cmp     eax, 2
0x1800025a2  jle     short loc_1800025A7
0x1800025a4  sub     edx, 2
0x1800025a7  mov     eax, [rdi+20h]
0x1800025aa  cmp     eax, 0FFFFFFFFh
0x1800025ad  jz      short loc_1800025DF
0x1800025af  lea     r8d, [rax+rdx]
0x1800025b3  cmp     [rdi+10h], r8
0x1800025b7  jbe     short loc_180002602
0x1800025b9  cmp     qword ptr [rdi+18h], 8
0x1800025be  jb      short loc_1800025C5
0x1800025c0  mov     rcx, [rdi]
0x1800025c3  jmp     short loc_1800025C8
0x1800025c5  mov     rcx, rdi
0x1800025c8  mov     [rcx+r8*2], r14w
0x1800025cd  mov     rcx, rdi
0x1800025d0  add     edx, [rdi+20h]
0x1800025d3  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K@Z; std::wstring::resize(unsigned __int64)
0x1800025d8  mov     dword ptr [rdi+20h], 0FFFFFFFFh
0x1800025df  mov     r8d, 1
0x1800025e5  lea     rdx, asc_18001BF38; "]"
0x1800025ec  mov     rcx, rdi; Src
0x1800025ef  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800025f4  mov     rax, rdi
0x1800025f7  add     rsp, 50h
0x1800025fb  pop     r14
0x1800025fd  pop     rdi
0x1800025fe  pop     rsi
0x1800025ff  pop     rbp
0x180002600  pop     rbx
0x180002601  retn
0x180002602  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
```
