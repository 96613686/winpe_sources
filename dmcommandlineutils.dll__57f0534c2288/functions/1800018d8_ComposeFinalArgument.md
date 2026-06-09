# ComposeFinalArgument

- ea: `0x1800018d8`
- end: `0x180001a90`
- name: `ComposeFinalArgument`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c04`

## callees

- `0x1800018d8`
- `0x180002044`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800019a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800019a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a74`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a41`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001a74`
- `DMCmnUtils!CopyString` at `0x180001924`
- `DMCmnUtils!CopyString` at `0x180001924`

## pseudocode

```c
__int64 __fastcall ComposeFinalArgument(__int64 a1, const unsigned __int16 *a2, HLOCAL *a3)
{
  __int64 v3; // r9
  unsigned int v6; // ebx
  _WORD *v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdi
  _WORD *v14; // r8
  _WORD *v15; // rcx
  __int64 v16; // rax
  unsigned __int64 v17; // rdx
  _WORD *v18; // rcx
  HLOCAL hMem; // [rsp+60h] [rbp+8h] BYREF

  hMem = 0;
  v3 = (a1 - (__int64)a2) >> 1;
  if ( (unsigned int)v3 > 0x7FFFFFFF )
  {
LABEL_2:
    v6 = -2147467259;
    goto LABEL_27;
  }
  v7 = *a3;
  if ( !*a3 )
  {
    v8 = CopyString(a2, v3, (unsigned __int16 **)&hMem);
    goto LABEL_23;
  }
  v9 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v9;
  }
  while ( v9 );
  v6 = v9 == 0 ? 0x80070057 : 0;
  v10 = (0x7FFFFFFF - v9) & -(__int64)(v9 != 0);
  if ( v9 )
  {
    v11 = (unsigned int)v3;
    v12 = (unsigned int)v3 + v10;
    if ( v12 < v10 || (v13 = v12 + 1, v12 + 1 < v12) )
    {
      v6 = -2147024362;
      goto LABEL_27;
    }
    if ( v13 > 0x7FFFFFFF )
      goto LABEL_2;
    hMem = LocalAlloc(0x40u, (unsigned int)(2 * v13));
    v14 = hMem;
    if ( !hMem )
    {
      v6 = -2147024882;
      goto LABEL_27;
    }
    if ( !v13 )
    {
      v6 = -2147024809;
      goto LABEL_27;
    }
    v15 = *a3;
    v16 = 2147483646;
    v17 = v13;
    do
    {
      if ( !v16 )
        break;
      if ( !*v15 )
        break;
      *v14++ = *v15++;
      --v16;
      --v17;
    }
    while ( v17 );
    v18 = v14 - 1;
    v6 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = v14;
    *v18 = 0;
    if ( v17 )
    {
      v8 = StringCchCatNW((unsigned __int16 *)hMem, v13, a2, v11);
LABEL_23:
      v6 = v8;
      if ( v8 >= 0 )
      {
        LocalFree(*a3);
        *a3 = hMem;
        hMem = 0;
      }
    }
  }
LABEL_27:
  LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x1800018d8  push    rbx
0x1800018da  push    rbp
0x1800018db  push    rsi
0x1800018dc  push    rdi
0x1800018dd  push    r14
0x1800018df  push    r15
0x1800018e1  sub     rsp, 28h
0x1800018e5  xor     r15d, r15d
0x1800018e8  mov     r9, rcx
0x1800018eb  sub     r9, rdx
0x1800018ee  mov     [rsp+58h+hMem], r15
0x1800018f3  sar     r9, 1
0x1800018f6  mov     r10d, 7FFFFFFFh
0x1800018fc  mov     rsi, r8
0x1800018ff  mov     rbp, rdx
0x180001902  cmp     r9d, r10d
0x180001905  jbe     short loc_180001911
0x180001907  mov     ebx, 80004005h
0x18000190c  jmp     loc_180001A6F
0x180001911  mov     rax, [r8]
0x180001914  test    rax, rax
0x180001917  jnz     short loc_180001935
0x180001919  lea     r8, [rsp+58h+hMem]
0x18000191e  mov     edx, r9d
0x180001921  mov     rcx, rbp
0x180001924  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x18000192b  nop     dword ptr [rax+rax+00h]
0x180001930  jmp     loc_180001A38
0x180001935  mov     rdx, r10
0x180001938  cmp     [rax], r15w
0x18000193c  jz      short loc_180001948
0x18000193e  add     rax, 2
0x180001942  sub     rdx, 1
0x180001946  jnz     short loc_180001938
0x180001948  mov     rax, rdx
0x18000194b  mov     rcx, r10
0x18000194e  neg     rax
0x180001951  mov     rax, rdx
0x180001954  sbb     ebx, ebx
0x180001956  sub     rcx, rdx
0x180001959  not     ebx
0x18000195b  and     ebx, 80070057h
0x180001961  neg     rax
0x180001964  sbb     r8, r8
0x180001967  and     r8, rcx
0x18000196a  test    rdx, rdx
0x18000196d  jz      loc_180001A6F
0x180001973  mov     r14d, r9d
0x180001976  lea     rax, [r14+r8]
0x18000197a  cmp     rax, r8
0x18000197d  jb      loc_180001A6A
0x180001983  lea     rdi, [rax+1]
0x180001987  cmp     rdi, rax
0x18000198a  jb      loc_180001A6A
0x180001990  cmp     rdi, r10
0x180001993  ja      loc_180001907
0x180001999  test    edi, edi
0x18000199b  js      loc_180001A63
0x1800019a1  lea     edx, [rdi+rdi]; uBytes
0x1800019a4  mov     ecx, 40h ; '@'; uFlags
0x1800019a9  call    cs:__imp_LocalAlloc
0x1800019b0  nop     dword ptr [rax+rax+00h]
0x1800019b5  mov     [rsp+58h+hMem], rax
0x1800019ba  mov     r8, rax
0x1800019bd  test    rax, rax
0x1800019c0  jnz     short loc_1800019CC
0x1800019c2  mov     ebx, 8007000Eh
0x1800019c7  jmp     loc_180001A6F
0x1800019cc  test    rdi, rdi
0x1800019cf  jz      loc_180001A5C
0x1800019d5  mov     rcx, [rsi]
0x1800019d8  mov     eax, 7FFFFFFEh
0x1800019dd  mov     rdx, rdi
0x1800019e0  test    rax, rax
0x1800019e3  jz      short loc_180001A04
0x1800019e5  movzx   r9d, word ptr [rcx]
0x1800019e9  test    r9w, r9w
0x1800019ed  jz      short loc_180001A04
0x1800019ef  mov     [r8], r9w
0x1800019f3  add     rcx, 2
0x1800019f7  add     r8, 2
0x1800019fb  dec     rax
0x1800019fe  sub     rdx, 1
0x180001a02  jnz     short loc_1800019E0
0x180001a04  mov     rax, rdx
0x180001a07  lea     rcx, [r8-2]
0x180001a0b  neg     rax
0x180001a0e  sbb     ebx, ebx
0x180001a10  not     ebx
0x180001a12  and     ebx, 8007007Ah
0x180001a18  test    rdx, rdx
0x180001a1b  cmovnz  rcx, r8
0x180001a1f  mov     [rcx], r15w
0x180001a23  jz      short loc_180001A6F
0x180001a25  mov     rcx, [rsp+58h+hMem]; unsigned __int16 *
0x180001a2a  mov     r9, r14; unsigned __int64
0x180001a2d  mov     r8, rbp; unsigned __int16 *
0x180001a30  mov     rdx, rdi; unsigned __int64
0x180001a33  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180001a38  mov     ebx, eax
0x180001a3a  test    eax, eax
0x180001a3c  js      short loc_180001A6F
0x180001a3e  mov     rcx, [rsi]; hMem
0x180001a41  call    cs:__imp_LocalFree
0x180001a48  nop     dword ptr [rax+rax+00h]
0x180001a4d  mov     rax, [rsp+58h+hMem]
0x180001a52  mov     [rsi], rax
0x180001a55  mov     [rsp+58h+hMem], r15
0x180001a5a  jmp     short loc_180001A6F
0x180001a5c  mov     ebx, 80070057h
0x180001a61  jmp     short loc_180001A6F
0x180001a63  mov     ebx, 82AA0003h
0x180001a68  jmp     short loc_180001A6F
0x180001a6a  mov     ebx, 80070216h
0x180001a6f  mov     rcx, [rsp+58h+hMem]; hMem
0x180001a74  call    cs:__imp_LocalFree
0x180001a7b  nop     dword ptr [rax+rax+00h]
0x180001a80  mov     eax, ebx
0x180001a82  add     rsp, 28h
0x180001a86  pop     r15
0x180001a88  pop     r14
0x180001a8a  pop     rdi
0x180001a8b  pop     rsi
0x180001a8c  pop     rbp
0x180001a8d  pop     rbx
0x180001a8e  retn
```
