# WebRequest::QueryAllResponseHeaders(void)

- ea: `0x140022998`
- end: `0x140022a9b`
- name: `?QueryAllResponseHeaders@WebRequest@@IEAA?AV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@XZ`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140022bd8`
- `0x140028954`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x140007bf8`
- `0x140022714`
- `0x140022998`
- `0x140030010`

## string_xrefs

- `0x1400229bf`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall WebRequest::QueryAllResponseHeaders(__int64 a1, _QWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v10; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp+10h]

  v11 = a2;
  v4 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
  v5 = v4;
  v10 = (volatile signed __int32 *)v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v6 = operator new(0x30u);
    *v6 = v6;
    v6[1] = v6;
    v6[2] = v6;
    *((_WORD *)v6 + 12) = 257;
    *v5 = v6;
  }
  else
  {
    v5 = 0;
  }
  *a2 = v5;
  if ( (unsigned int)(*(_DWORD *)(a1 + 88) - 3) <= 1 )
  {
    v7 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, volatile signed __int32 **, __int64))(*(_QWORD *)a1 + 96LL))(
                     a1,
                     &v10,
                     22);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (_QWORD *)(a1 + 136),
      v7);
    v8 = v10 - 6;
    if ( _InterlockedExchangeAdd(v10 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v8 + 8LL))(*(_QWORD *)v8);
    WebRequest::ParseRawHttpHeaders(a2, a1 + 136);
  }
  return a2;
}

```

## disassembly

```asm
0x140022998  mov     rax, rsp
0x14002299b  mov     [rax+18h], rbx
0x14002299f  mov     [rax+20h], rsi
0x1400229a3  mov     [rax+10h], rdx
0x1400229a7  push    rdi
0x1400229a8  sub     rsp, 40h
0x1400229ac  mov     rdi, rdx
0x1400229af  mov     rsi, rcx
0x1400229b2  mov     dword ptr [rax-18h], 0
0x1400229b9  mov     r9d, 1F3h; int
0x1400229bf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x1400229c6  mov     edx, 1; int
0x1400229cb  lea     ecx, [rdx+0Fh]; unsigned __int64
0x1400229ce  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x1400229d3  mov     rbx, rax
0x1400229d6  mov     [rsp+48h+arg_0], rax
0x1400229db  test    rax, rax
0x1400229de  jz      short loc_140022A0F
0x1400229e0  mov     qword ptr [rax], 0
0x1400229e7  mov     qword ptr [rax+8], 0
0x1400229ef  mov     ecx, 30h ; '0'; Size
0x1400229f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400229f9  mov     [rax], rax
0x1400229fc  mov     [rax+8], rax
0x140022a00  mov     [rax+10h], rax
0x140022a04  mov     word ptr [rax+18h], 101h
0x140022a0a  mov     [rbx], rax
0x140022a0d  jmp     short loc_140022A11
0x140022a0f  xor     ebx, ebx
0x140022a11  mov     [rdi], rbx
0x140022a14  mov     [rsp+48h+var_18], 1
0x140022a1c  mov     eax, [rsi+58h]
0x140022a1f  sub     eax, 3
0x140022a22  cmp     eax, 1
0x140022a25  ja      short loc_140022A87
0x140022a27  mov     rax, [rsi]
0x140022a2a  xor     r9d, r9d
0x140022a2d  lea     r8d, [r9+16h]
0x140022a31  lea     rdx, [rsp+48h+arg_0]
0x140022a36  mov     rcx, rsi
0x140022a39  mov     rax, [rax+60h]
0x140022a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022a42  nop
0x140022a43  mov     rdx, rax
0x140022a46  lea     rcx, [rsi+88h]
0x140022a4d  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140022a52  nop
0x140022a53  mov     rdx, [rsp+48h+arg_0]
0x140022a58  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140022a5c  or      eax, 0FFFFFFFFh
0x140022a5f  lock xadd [rdx+10h], eax
0x140022a64  sub     eax, 1
0x140022a67  jg      short loc_140022A78
0x140022a69  mov     rcx, [rdx]
0x140022a6c  mov     rax, [rcx]
0x140022a6f  mov     rax, [rax+8]
0x140022a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022a78  lea     rdx, [rsi+88h]
0x140022a7f  mov     rcx, rdi
0x140022a82  call    ?ParseRawHttpHeaders@WebRequest@@SAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::ParseRawHttpHeaders(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140022a87  mov     rax, rdi
0x140022a8a  mov     rbx, [rsp+48h+arg_10]
0x140022a8f  mov     rsi, [rsp+48h+arg_18]
0x140022a94  add     rsp, 40h
0x140022a98  pop     rdi
0x140022a99  retn
```
