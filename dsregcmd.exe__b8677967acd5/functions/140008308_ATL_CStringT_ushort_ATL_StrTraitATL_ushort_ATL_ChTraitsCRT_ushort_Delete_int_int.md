# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Delete(int,int)

- ea: `0x140008308`
- end: `0x1400083e9`
- name: `?Delete@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHH@Z`
- size: `225`
- prototype: `__int64 __fastcall(__int64 *, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140009b24`
- `0x140027d80`

## callees

- `0x14000274e`
- `0x140005c58`
- `0x140006020`
- `0x140008308`
- `0x14002c40c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400083c2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1400083c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Delete(
        __int64 *a1,
        int a2,
        int a3)
{
  int v3; // r14d
  int v5; // edi
  __int64 v6; // rcx
  int v7; // ebx
  size_t v8; // r8
  __int64 v9; // rcx
  const void *v10; // rdx
  int v11; // ebx

  v3 = 0;
  if ( a2 >= 0 )
    v3 = a2;
  v5 = 0;
  if ( a3 >= 0 )
    v5 = a3;
  if ( 0x7FFFFFFF - v5 < v3 )
    goto LABEL_20;
  v6 = *a1;
  v7 = *(_DWORD *)(v6 - 16);
  if ( v5 + v3 > v7 )
    v5 = v7 - v3;
  if ( v5 > 0 )
  {
    if ( *(int *)(v6 - 8) > 1 )
      ATL::CSimpleStringT<unsigned short,0>::Fork(a1, (unsigned int)v7);
    v8 = 2LL * (v7 - v3 - v5 + 1);
    if ( v8 )
    {
      v9 = *a1;
      v10 = (const void *)v3;
      if ( !(*a1 + 2LL * v3) || (v10 = (const void *)(v9 + 2 * (v3 + (__int64)v5))) == 0 )
      {
        *(_DWORD *)_o__errno(v9, v10, v8) = 22;
        invalid_parameter_noinfo();
        ATL::AtlThrowImpl(0x80070057);
      }
      memmove_0((void *)(*a1 + 2LL * v3), v10, v8);
    }
    v11 = v7 - v5;
    if ( v11 >= 0 && v11 <= *(_DWORD *)(*a1 - 12) )
    {
      *(_DWORD *)(*a1 - 16) = v11;
      *(_WORD *)(*a1 + 2LL * v11) = 0;
      return *(unsigned int *)(*a1 - 16);
    }
LABEL_20:
    ATL::AtlThrowImpl(0x80070057);
  }
  return *(unsigned int *)(*a1 - 16);
}

```

## disassembly

```asm
0x140008308  push    rbx
0x14000830a  push    rbp
0x14000830b  push    rsi
0x14000830c  push    rdi
0x14000830d  push    r14
0x14000830f  sub     rsp, 20h
0x140008313  xor     r14d, r14d
0x140008316  mov     eax, 7FFFFFFFh
0x14000831b  test    edx, edx
0x14000831d  mov     rsi, rcx
0x140008320  cmovns  r14d, edx
0x140008324  xor     edi, edi
0x140008326  test    r8d, r8d
0x140008329  cmovns  edi, r8d
0x14000832d  sub     eax, edi
0x14000832f  cmp     eax, r14d
0x140008332  jl      loc_1400083DE
0x140008338  mov     rcx, [rcx]
0x14000833b  lea     eax, [rdi+r14]
0x14000833f  mov     ebx, [rcx-10h]
0x140008342  cmp     eax, ebx
0x140008344  jle     short loc_14000834B
0x140008346  mov     edi, ebx
0x140008348  sub     edi, r14d
0x14000834b  test    edi, edi
0x14000834d  jle     short loc_1400083B1
0x14000834f  mov     ebp, ebx
0x140008351  sub     ebp, r14d
0x140008354  cmp     dword ptr [rcx-8], 1
0x140008358  jle     short loc_140008364
0x14000835a  mov     edx, ebx
0x14000835c  mov     rcx, rsi
0x14000835f  call    ?Fork@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Fork(int)
0x140008364  sub     ebp, edi
0x140008366  inc     ebp
0x140008368  movsxd  r8, ebp
0x14000836b  add     r8, r8; Size
0x14000836e  jz      short loc_140008396
0x140008370  mov     rcx, [rsi]
0x140008373  movsxd  rdx, r14d
0x140008376  lea     r9, [rcx+rdx*2]
0x14000837a  test    r9, r9
0x14000837d  jz      short loc_1400083C2
0x14000837f  movsxd  rax, edi
0x140008382  add     rax, rdx
0x140008385  lea     rdx, [rcx+rax*2]; Src
0x140008389  test    rdx, rdx
0x14000838c  jz      short loc_1400083C2
0x14000838e  mov     rcx, r9; void *
0x140008391  call    memmove_0
0x140008396  sub     ebx, edi
0x140008398  js      short loc_1400083DE
0x14000839a  mov     rax, [rsi]
0x14000839d  cmp     ebx, [rax-0Ch]
0x1400083a0  jg      short loc_1400083DE
0x1400083a2  mov     [rax-10h], ebx
0x1400083a5  xor     eax, eax
0x1400083a7  mov     rcx, [rsi]
0x1400083aa  movsxd  rdx, ebx
0x1400083ad  mov     [rcx+rdx*2], ax
0x1400083b1  mov     rax, [rsi]
0x1400083b4  mov     eax, [rax-10h]
0x1400083b7  add     rsp, 20h
0x1400083bb  pop     r14
0x1400083bd  pop     rdi
0x1400083be  pop     rsi
0x1400083bf  pop     rbp
0x1400083c0  pop     rbx
0x1400083c1  retn
0x1400083c2  call    cs:__imp__o__errno
0x1400083c8  mov     dword ptr [rax], 16h
0x1400083ce  call    _invalid_parameter_noinfo
0x1400083d3  mov     ecx, 80070057h; unsigned int
0x1400083d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400083de  mov     ecx, 80070057h; unsigned int
0x1400083e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
