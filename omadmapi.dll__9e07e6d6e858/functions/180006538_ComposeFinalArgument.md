# ComposeFinalArgument

- ea: `0x180006538`
- end: `0x180006700`
- name: `ComposeFinalArgument`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006890`

## callees

- `0x180006538`
- `0x180006cd4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006616`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006616`
- `DMCmnUtils!CopyString` at `0x18000658d`
- `DMCmnUtils!CopyString` at `0x18000658d`

## pseudocode

```c
__int64 __fastcall ComposeFinalArgument(__int64 a1, const unsigned __int16 *a2, HLOCAL *a3)
{
  __int64 v3; // r9
  unsigned int v6; // ebx
  _WORD *v7; // rax
  int v8; // eax
  __int64 v9; // rbp
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  unsigned __int64 v12; // r15
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdi
  _WORD *v15; // r8
  _WORD *v16; // rax
  unsigned __int64 v17; // rdx
  _WORD *v18; // rcx
  HLOCAL hMem; // [rsp+50h] [rbp+8h] BYREF

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
  v9 = 2147483646;
  v10 = 2147483646;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v10;
  }
  while ( v10 );
  v6 = v10 == 0 ? 0x80070057 : 0;
  v11 = (2147483646 - v10) & -(__int64)(v10 != 0);
  if ( v10 )
  {
    v12 = (unsigned int)v3;
    v13 = (unsigned int)v3 + v11;
    if ( v13 < v11 || (v14 = v13 + 1, v13 + 1 < v13) )
    {
      v6 = -2147024362;
      goto LABEL_27;
    }
    if ( v14 > 0x7FFFFFFF )
      goto LABEL_2;
    hMem = LocalAlloc(0x40u, (unsigned int)(2 * v14));
    v15 = hMem;
    if ( !hMem )
    {
      v6 = -2147024882;
      goto LABEL_27;
    }
    if ( !v14 )
    {
      v6 = -2147024809;
      goto LABEL_27;
    }
    v16 = *a3;
    v17 = v14;
    do
    {
      if ( !v9 )
        break;
      if ( !*v16 )
        break;
      *v15++ = *v16++;
      --v9;
      --v17;
    }
    while ( v17 );
    v18 = v15 - 1;
    v6 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = v15;
    *v18 = 0;
    if ( v17 )
    {
      v8 = StringCchCatNW((unsigned __int16 *)hMem, v14, a2, v12);
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
0x180006538  mov     [rsp+arg_8], rbx
0x18000653d  mov     [rsp+arg_10], rbp
0x180006542  push    rsi
0x180006543  push    rdi
0x180006544  push    r12
0x180006546  push    r14
0x180006548  push    r15
0x18000654a  sub     rsp, 20h
0x18000654e  xor     r12d, r12d
0x180006551  mov     r9, rcx
0x180006554  sub     r9, rdx
0x180006557  mov     [rsp+48h+hMem], r12
0x18000655c  sar     r9, 1
0x18000655f  mov     r10d, 7FFFFFFFh
0x180006565  mov     rsi, r8
0x180006568  mov     r14, rdx
0x18000656b  cmp     r9d, r10d
0x18000656e  jbe     short loc_18000657A
0x180006570  mov     ebx, 80004005h
0x180006575  jmp     loc_1800066D5
0x18000657a  mov     rax, [r8]
0x18000657d  test    rax, rax
0x180006580  jnz     short loc_18000659E
0x180006582  lea     r8, [rsp+48h+hMem]
0x180006587  mov     edx, r9d
0x18000658a  mov     rcx, r14
0x18000658d  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180006594  nop     dword ptr [rax+rax+00h]
0x180006599  jmp     loc_18000669E
0x18000659e  mov     ebp, 7FFFFFFEh
0x1800065a3  mov     edx, ebp
0x1800065a5  cmp     [rax], r12w
0x1800065a9  jz      short loc_1800065B5
0x1800065ab  add     rax, 2
0x1800065af  sub     rdx, 1
0x1800065b3  jnz     short loc_1800065A5
0x1800065b5  mov     rax, rdx
0x1800065b8  mov     rcx, rbp
0x1800065bb  neg     rax
0x1800065be  mov     rax, rdx
0x1800065c1  sbb     ebx, ebx
0x1800065c3  sub     rcx, rdx
0x1800065c6  not     ebx
0x1800065c8  and     ebx, 80070057h
0x1800065ce  neg     rax
0x1800065d1  sbb     r8, r8
0x1800065d4  and     r8, rcx
0x1800065d7  test    rdx, rdx
0x1800065da  jz      loc_1800066D5
0x1800065e0  mov     r15d, r9d
0x1800065e3  lea     rax, [r15+r8]
0x1800065e7  cmp     rax, r8
0x1800065ea  jb      loc_1800066D0
0x1800065f0  lea     rdi, [rax+1]
0x1800065f4  cmp     rdi, rax
0x1800065f7  jb      loc_1800066D0
0x1800065fd  cmp     rdi, r10
0x180006600  ja      loc_180006570
0x180006606  test    edi, edi
0x180006608  js      loc_1800066C9
0x18000660e  lea     edx, [rdi+rdi]; uBytes
0x180006611  mov     ecx, 40h ; '@'; uFlags
0x180006616  call    cs:__imp_LocalAlloc
0x18000661d  nop     dword ptr [rax+rax+00h]
0x180006622  mov     [rsp+48h+hMem], rax
0x180006627  mov     r8, rax
0x18000662a  test    rax, rax
0x18000662d  jnz     short loc_180006639
0x18000662f  mov     ebx, 8007000Eh
0x180006634  jmp     loc_1800066D5
0x180006639  test    rdi, rdi
0x18000663c  jz      loc_1800066C2
0x180006642  mov     rax, [rsi]
0x180006645  mov     rdx, rdi
0x180006648  test    rbp, rbp
0x18000664b  jz      short loc_18000666A
0x18000664d  movzx   ecx, word ptr [rax]
0x180006650  test    cx, cx
0x180006653  jz      short loc_18000666A
0x180006655  mov     [r8], cx
0x180006659  add     rax, 2
0x18000665d  add     r8, 2
0x180006661  dec     rbp
0x180006664  sub     rdx, 1
0x180006668  jnz     short loc_180006648
0x18000666a  mov     rax, rdx
0x18000666d  lea     rcx, [r8-2]
0x180006671  neg     rax
0x180006674  sbb     ebx, ebx
0x180006676  not     ebx
0x180006678  and     ebx, 8007007Ah
0x18000667e  test    rdx, rdx
0x180006681  cmovnz  rcx, r8
0x180006685  mov     [rcx], r12w
0x180006689  jz      short loc_1800066D5
0x18000668b  mov     rcx, [rsp+48h+hMem]; unsigned __int16 *
0x180006690  mov     r9, r15; unsigned __int64
0x180006693  mov     r8, r14; unsigned __int16 *
0x180006696  mov     rdx, rdi; unsigned __int64
0x180006699  call    ?StringCchCatNW@@YAJPEAG_KPEBG1@Z; StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18000669e  mov     ebx, eax
0x1800066a0  test    eax, eax
0x1800066a2  js      short loc_1800066D5
0x1800066a4  mov     rcx, [rsi]; hMem
0x1800066a7  call    cs:__imp_LocalFree
0x1800066ae  nop     dword ptr [rax+rax+00h]
0x1800066b3  mov     rax, [rsp+48h+hMem]
0x1800066b8  mov     [rsi], rax
0x1800066bb  mov     [rsp+48h+hMem], r12
0x1800066c0  jmp     short loc_1800066D5
0x1800066c2  mov     ebx, 80070057h
0x1800066c7  jmp     short loc_1800066D5
0x1800066c9  mov     ebx, 82AA0003h
0x1800066ce  jmp     short loc_1800066D5
0x1800066d0  mov     ebx, 80070216h
0x1800066d5  mov     rcx, [rsp+48h+hMem]; hMem
0x1800066da  call    cs:__imp_LocalFree
0x1800066e1  nop     dword ptr [rax+rax+00h]
0x1800066e6  mov     rbp, [rsp+48h+arg_10]
0x1800066eb  mov     eax, ebx
0x1800066ed  mov     rbx, [rsp+48h+arg_8]
0x1800066f2  add     rsp, 20h
0x1800066f6  pop     r15
0x1800066f8  pop     r14
0x1800066fa  pop     r12
0x1800066fc  pop     rdi
0x1800066fd  pop     rsi
0x1800066fe  retn
```
