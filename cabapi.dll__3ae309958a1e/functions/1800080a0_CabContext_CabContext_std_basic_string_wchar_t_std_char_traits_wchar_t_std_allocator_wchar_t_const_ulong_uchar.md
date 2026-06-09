# CabContext::CabContext(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,uchar * *,ulong *)

- ea: `0x1800080a0`
- end: `0x1800081cf`
- name: `??0CabContext@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KPEAPEAEPEAK@Z`
- size: `303`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800085ac`
- `0x1800088dc`
- `0x180008fd8`
- `0x180009c20`
- `0x180009da4`
- `0x180009eac`
- `0x18000a400`

## callees

- `0x180001570`
- `0x180007fd0`

## pseudocode

```c
__int64 __fastcall CabContext::CabContext(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax

  *(_QWORD *)a1 = &CabContext::`vftable';
  *(_DWORD *)(a1 + 8) = a3;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v8 = operator new(0x48u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *(_QWORD *)(a1 + 16) = v8;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  v9 = operator new(0x48u);
  *v9 = v9;
  v9[1] = v9;
  v9[2] = v9;
  *((_WORD *)v9 + 12) = 257;
  *(_QWORD *)(a1 + 32) = v9;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  v10 = operator new(0x60u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *(_QWORD *)(a1 + 48) = v10;
  *(_OWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 7;
  *(_WORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 120) = 7;
  *(_WORD *)(a1 + 96) = 0;
  std::wstring::wstring(a1 + 128, a2);
  *(_DWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = a4;
  *(_QWORD *)(a1 + 176) = a5;
  return a1;
}

```

## disassembly

```asm
0x1800080a0  mov     [rsp+arg_0], rcx
0x1800080a5  push    rsi
0x1800080a6  push    rdi
0x1800080a7  push    r14
0x1800080a9  sub     rsp, 30h
0x1800080ad  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800080b6  mov     [rsp+48h+arg_8], rbx
0x1800080bb  mov     rsi, r9
0x1800080be  mov     rdi, rdx
0x1800080c1  mov     r14, rcx
0x1800080c4  lea     rax, ??_7CabContext@@6B@; const CabContext::`vftable'
0x1800080cb  mov     [rcx], rax
0x1800080ce  mov     [rcx+8], r8d
0x1800080d2  mov     qword ptr [rcx+10h], 0
0x1800080da  mov     qword ptr [rcx+18h], 0
0x1800080e2  mov     ecx, 48h ; 'H'; Size
0x1800080e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800080ec  mov     [rax], rax
0x1800080ef  mov     [rax+8], rax
0x1800080f3  mov     [rax+10h], rax
0x1800080f7  mov     word ptr [rax+18h], 101h
0x1800080fd  mov     [r14+10h], rax
0x180008101  mov     qword ptr [r14+20h], 0
0x180008109  mov     qword ptr [r14+28h], 0
0x180008111  mov     ecx, 48h ; 'H'; Size
0x180008116  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000811b  mov     [rax], rax
0x18000811e  mov     [rax+8], rax
0x180008122  mov     [rax+10h], rax
0x180008126  mov     word ptr [rax+18h], 101h
0x18000812c  mov     [r14+20h], rax
0x180008130  mov     qword ptr [r14+30h], 0
0x180008138  mov     qword ptr [r14+38h], 0
0x180008140  mov     ecx, 60h ; '`'; Size
0x180008145  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000814a  mov     [rax], rax
0x18000814d  mov     [rax+8], rax
0x180008151  mov     [rax+10h], rax
0x180008155  mov     word ptr [rax+18h], 101h
0x18000815b  mov     [r14+30h], rax
0x18000815f  xorps   xmm0, xmm0
0x180008162  movups  xmmword ptr [r14+40h], xmm0
0x180008167  mov     qword ptr [r14+50h], 0
0x18000816f  mov     ecx, 7
0x180008174  mov     [r14+58h], rcx
0x180008178  xor     eax, eax
0x18000817a  mov     [r14+40h], ax
0x18000817f  movups  xmmword ptr [r14+60h], xmm0
0x180008184  mov     [r14+70h], rax
0x180008188  mov     [r14+78h], rcx
0x18000818c  mov     [r14+60h], ax
0x180008191  lea     rcx, [r14+80h]
0x180008198  mov     rdx, rdi
0x18000819b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800081a0  mov     dword ptr [r14+0A0h], 0
0x1800081ab  mov     [r14+0A8h], rsi
0x1800081b2  mov     rax, [rsp+48h+arg_20]
0x1800081b7  mov     [r14+0B0h], rax
0x1800081be  mov     rax, r14
0x1800081c1  mov     rbx, [rsp+48h+arg_8]
0x1800081c6  add     rsp, 30h
0x1800081ca  pop     r14
0x1800081cc  pop     rdi
0x1800081cd  pop     rsi
0x1800081ce  retn
```
