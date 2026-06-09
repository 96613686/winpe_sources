# CPageFile::AllocPhysPage(ulong *)

- ea: `0x1800112a0`
- end: `0x18001148a`
- name: `?AllocPhysPage@CPageFile@@QEAAKPEAK@Z`
- size: `490`
- prototype: `__int64 __fastcall(CPageFile *this, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fd30`

## callees

- `0x1800012b8`
- `0x1800112a0`
- `0x18002b7c2`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x1800113d4`
- `wbemcomn!GetMemLogObject` at `0x180011422`
- `wbemcomn!GetMemLogObject` at `0x1800113d4`
- `wbemcomn!GetMemLogObject` at `0x180011422`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800113e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011430`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800113e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180011430`

## pseudocode

```c
__int64 __fastcall CPageFile::AllocPhysPage(CPageFile *this, unsigned int *a2)
{
  __int64 v2; // r11
  unsigned int v5; // r8d
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r10d
  __int64 v12; // rcx
  __int64 v13; // rbx
  CMemoryLog *MemLogObject; // rax
  CVarObjHeap *v15; // rcx
  __int64 v16; // rdx
  unsigned int v17; // ecx
  CMemoryLog *v18; // rax

  v2 = *((_QWORD *)this + 44);
  if ( *((_QWORD *)this + 45) == v2 )
  {
    v5 = *((_DWORD *)this + 106);
    if ( v5 != 0x3FFFFFFF )
    {
      *((_DWORD *)this + 106) = v5 + 1;
      *a2 = v5;
      return 0;
    }
    *a2 = -1;
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, 112);
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 112;
    }
    v16 = 91;
    goto LABEL_22;
  }
  v7 = *((_QWORD *)this + 47);
  v8 = (*((_QWORD *)this + 48) - v7) >> 2;
  if ( v8 )
  {
    v9 = 0x3FFFFFFF;
    v10 = 0;
    v11 = 0x3FFFFFFF;
    v12 = 0;
    do
    {
      if ( !*(_DWORD *)(v7 + 4 * v12) && v11 > *(_DWORD *)(v2 + 4 * v12) )
      {
        v11 = *(_DWORD *)(v2 + 4 * v12);
        v9 = v10;
      }
      v12 = ++v10;
    }
    while ( v10 != v8 );
    if ( v11 != 0x3FFFFFFF )
    {
      v13 = 4LL * v9;
      *a2 = *(_DWORD *)(v13 + v2);
      memmove_0(
        (void *)(v13 + *((_QWORD *)this + 44)),
        (const void *)(v13 + *((_QWORD *)this + 44) + 4),
        (*((_QWORD *)this + 45) - (v13 + *((_QWORD *)this + 44) + 4)) & 0xFFFFFFFFFFFFFFFCuLL);
      *((_QWORD *)this + 45) -= 4LL;
      memmove_0(
        (void *)(v13 + *((_QWORD *)this + 47)),
        (const void *)(v13 + *((_QWORD *)this + 47) + 4),
        (*((_QWORD *)this + 48) - (v13 + *((_QWORD *)this + 47) + 4)) & 0xFFFFFFFFFFFFFFFCuLL);
      *((_QWORD *)this + 48) -= 4LL;
      return 0;
    }
  }
  v17 = *((_DWORD *)this + 106);
  if ( v17 != 0x3FFFFFFF )
  {
    *((_DWORD *)this + 106) = v17 + 1;
    *a2 = v17;
    return 0;
  }
  *a2 = -1;
  v18 = GetMemLogObject();
  CMemoryLog::Write(v18, 112);
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = 92;
LABEL_22:
    WPP_SF_d(*((_QWORD *)v15 + 2), v16, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids, 112);
  }
  return 112;
}

```

## disassembly

```asm
0x1800112a0  mov     [rsp+arg_0], rbx
0x1800112a5  mov     [rsp+arg_8], rsi
0x1800112aa  push    rdi
0x1800112ab  sub     rsp, 20h
0x1800112af  mov     r11, [rcx+160h]
0x1800112b6  mov     rsi, rdx
0x1800112b9  mov     rdi, rcx
0x1800112bc  cmp     [rcx+168h], r11
0x1800112c3  jnz     short loc_1800112F8
0x1800112c5  mov     r8d, [rcx+1A8h]
0x1800112cc  cmp     r8d, 3FFFFFFFh
0x1800112d3  jz      loc_1800113CE
0x1800112d9  lea     eax, [r8+1]
0x1800112dd  mov     [rcx+1A8h], eax
0x1800112e3  mov     [rdx], r8d
0x1800112e6  xor     eax, eax
0x1800112e8  mov     rbx, [rsp+28h+arg_0]
0x1800112ed  mov     rsi, [rsp+28h+arg_8]
0x1800112f2  add     rsp, 20h
0x1800112f6  pop     rdi
0x1800112f7  retn
0x1800112f8  mov     r8, [rcx+178h]
0x1800112ff  mov     rdx, [rcx+180h]
0x180011306  sub     rdx, r8
0x180011309  sar     rdx, 2
0x18001130d  test    rdx, rdx
0x180011310  jz      loc_18001140E
0x180011316  mov     ebx, 3FFFFFFFh
0x18001131b  xor     eax, eax
0x18001131d  mov     r10d, ebx
0x180011320  xor     ecx, ecx
0x180011322  cmp     dword ptr [r8+rcx*4], 0
0x180011327  jz      loc_1800113B7
0x18001132d  inc     eax
0x18001132f  mov     ecx, eax
0x180011331  cmp     rcx, rdx
0x180011334  jnz     short loc_180011322
0x180011336  cmp     r10d, 3FFFFFFFh
0x18001133d  jz      loc_18001140E
0x180011343  mov     eax, ebx
0x180011345  lea     rbx, ds:0[rax*4]
0x18001134d  mov     eax, [rbx+r11]
0x180011351  mov     [rsi], eax
0x180011353  mov     rcx, [rdi+160h]
0x18001135a  mov     r8, [rdi+168h]
0x180011361  add     rcx, rbx; void *
0x180011364  lea     rdx, [rcx+4]; Src
0x180011368  sub     r8, rdx
0x18001136b  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18001136f  call    memmove_0
0x180011374  add     qword ptr [rdi+168h], 0FFFFFFFFFFFFFFFCh
0x18001137c  mov     rcx, [rdi+178h]
0x180011383  mov     r8, [rdi+180h]
0x18001138a  add     rcx, rbx; void *
0x18001138d  lea     rdx, [rcx+4]; Src
0x180011391  sub     r8, rdx
0x180011394  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x180011398  call    memmove_0
0x18001139d  add     qword ptr [rdi+180h], 0FFFFFFFFFFFFFFFCh
0x1800113a5  mov     rbx, [rsp+28h+arg_0]
0x1800113aa  xor     eax, eax
0x1800113ac  mov     rsi, [rsp+28h+arg_8]
0x1800113b1  add     rsp, 20h
0x1800113b5  pop     rdi
0x1800113b6  retn
0x1800113b7  mov     r9d, [r11+rcx*4]
0x1800113bb  cmp     r10d, r9d
0x1800113be  jbe     loc_18001132D
0x1800113c4  mov     r10d, r9d
0x1800113c7  mov     ebx, eax
0x1800113c9  jmp     loc_18001132D
0x1800113ce  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800113d4  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800113da  mov     rcx, rax
0x1800113dd  mov     edx, 70h ; 'p'
0x1800113e2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800113e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800113ef  lea     rax, WPP_GLOBAL_Control
0x1800113f6  cmp     rcx, rax
0x1800113f9  jz      short loc_180011470
0x1800113fb  test    byte ptr [rcx+1Ch], 1
0x1800113ff  jz      short loc_180011470
0x180011401  cmp     byte ptr [rcx+19h], 2
0x180011405  jb      short loc_180011470
0x180011407  mov     edx, 5Bh ; '['
0x18001140c  jmp     short loc_18001145A
0x18001140e  mov     ecx, [rdi+1A8h]
0x180011414  cmp     ecx, 3FFFFFFFh
0x18001141a  jnz     short loc_18001147A
0x18001141c  mov     dword ptr [rsi], 0FFFFFFFFh
0x180011422  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180011428  mov     rcx, rax
0x18001142b  mov     edx, 70h ; 'p'
0x180011430  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180011436  mov     rcx, cs:WPP_GLOBAL_Control
0x18001143d  lea     rax, WPP_GLOBAL_Control
0x180011444  cmp     rcx, rax
0x180011447  jz      short loc_180011470
0x180011449  test    byte ptr [rcx+1Ch], 1
0x18001144d  jz      short loc_180011470
0x18001144f  cmp     byte ptr [rcx+19h], 2
0x180011453  jb      short loc_180011470
0x180011455  mov     edx, 5Ch ; '\'
0x18001145a  mov     rcx, [rcx+10h]
0x18001145e  lea     r8, WPP_31b36d4bfc4e3648c683eda83ca95384_Traceguids
0x180011465  mov     r9d, 70h ; 'p'
0x18001146b  call    WPP_SF_d
0x180011470  mov     eax, 70h ; 'p'
0x180011475  jmp     loc_1800112E8
0x18001147a  lea     eax, [rcx+1]
0x18001147d  mov     [rdi+1A8h], eax
0x180011483  mov     [rsi], ecx
0x180011485  jmp     loc_1800112E6
```
