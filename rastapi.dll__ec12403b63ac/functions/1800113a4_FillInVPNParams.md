# FillInVPNParams

- ea: `0x1800113a4`
- end: `0x180011522`
- name: `FillInVPNParams`
- size: `382`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180014f2c`

## callees

- `0x1800113a4`
- `0x180029266`

## import_xrefs

- `msvcrt!_stricmp` at `0x1800113d1`
- `msvcrt!_stricmp` at `0x1800113ec`
- `msvcrt!_stricmp` at `0x180011460`
- `msvcrt!_stricmp` at `0x1800113d1`
- `msvcrt!_stricmp` at `0x1800113ec`
- `msvcrt!_stricmp` at `0x180011460`
- `msvcrt!_strcmpi` at `0x180011489`
- `msvcrt!_strcmpi` at `0x180011489`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800114c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800114c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800114a3`

## string_xrefs

- `0x180011456`: `Compartment`

## pseudocode

```c
__int64 __fastcall FillInVPNParams(__int64 a1, _DWORD *a2)
{
  unsigned __int16 v2; // si
  _DWORD *v3; // rbx
  __int64 v6; // rax
  _BYTE *v7; // rcx
  unsigned __int64 v8; // rax
  _BYTE *v9; // r8
  __int64 v10; // rdx
  _BYTE *v11; // rax
  void *v12; // rcx
  HLOCAL v13; // rax

  v2 = 0;
  v3 = a2 + 2;
  if ( !*a2 )
    return 0;
  while ( !_stricmp((const char *)v3, "PhoneNumber") )
  {
    v6 = 260;
LABEL_6:
    if ( v3[8] != 1 )
      return 604;
    v7 = (_BYTE *)(v6 + a1);
    v8 = (unsigned int)v3[10];
    if ( v8 <= 0x7FFFFFFE )
    {
      v9 = (_BYTE *)*((_QWORD *)v3 + 6);
      v10 = 100;
      do
      {
        if ( !v8 )
          break;
        if ( !*v9 )
          break;
        *v7++ = *v9++;
        --v8;
        --v10;
      }
      while ( v10 );
      v11 = v7 - 1;
      if ( v10 )
        v11 = v7;
      *v11 = 0;
    }
    else
    {
      *v7 = 0;
    }
LABEL_24:
    ++v2;
    v3 += 14;
    if ( (unsigned int)v2 >= *a2 )
      return 0;
  }
  if ( !_stricmp((const char *)v3, "ConnectBps") )
  {
    v6 = 360;
    goto LABEL_6;
  }
  if ( !_stricmp((const char *)v3, "Compartment") )
  {
    *(_DWORD *)(a1 + 1196) = v3[10];
    goto LABEL_24;
  }
  if ( v3[8] == 2 && !_strcmpi((const char *)v3, "DevSpecificInfo") )
  {
    v12 = *(void **)(a1 + 864);
    if ( v12 )
    {
      LocalFree(v12);
      *(_QWORD *)(a1 + 864) = 0;
      *(_DWORD *)(a1 + 872) = 0;
    }
    v13 = LocalAlloc(0x40u, (unsigned int)v3[11]);
    *(_QWORD *)(a1 + 864) = v13;
    if ( !v13 )
      return 8;
    *(_DWORD *)(a1 + 872) = v3[11];
    memcpy_0(v13, (char *)v3 + (unsigned int)v3[10], (unsigned int)v3[11]);
    goto LABEL_24;
  }
  return 604;
}

```

## disassembly

```asm
0x1800113a4  push    rbx
0x1800113a6  push    rbp
0x1800113a7  push    rsi
0x1800113a8  push    rdi
0x1800113a9  push    r15
0x1800113ab  sub     rsp, 20h
0x1800113af  xor     esi, esi
0x1800113b1  lea     rbx, [rdx+8]
0x1800113b5  mov     rbp, rdx
0x1800113b8  mov     rdi, rcx
0x1800113bb  cmp     [rdx], esi
0x1800113bd  jbe     loc_180011507
0x1800113c3  lea     r15d, [rsi+1]
0x1800113c7  lea     rdx, aPhonenumber; "PhoneNumber"
0x1800113ce  mov     rcx, rbx; String1
0x1800113d1  call    cs:__imp__stricmp
0x1800113d7  test    eax, eax
0x1800113d9  jnz     short loc_1800113E2
0x1800113db  mov     eax, 104h
0x1800113e0  jmp     short loc_1800113FB
0x1800113e2  lea     rdx, aConnectbps; "ConnectBps"
0x1800113e9  mov     rcx, rbx; String1
0x1800113ec  call    cs:__imp__stricmp
0x1800113f2  test    eax, eax
0x1800113f4  jnz     short loc_180011456
0x1800113f6  mov     eax, 168h
0x1800113fb  cmp     [rbx+20h], r15d
0x1800113ff  jnz     loc_18001151B
0x180011405  lea     rcx, [rax+rdi]
0x180011409  mov     eax, [rbx+28h]
0x18001140c  cmp     rax, 7FFFFFFEh
0x180011412  jbe     short loc_18001141C
0x180011414  mov     byte ptr [rcx], 0
0x180011417  jmp     loc_1800114F3
0x18001141c  mov     r8, [rbx+30h]
0x180011420  mov     edx, 64h ; 'd'
0x180011425  test    rax, rax
0x180011428  jz      short loc_180011443
0x18001142a  mov     r9b, [r8]
0x18001142d  test    r9b, r9b
0x180011430  jz      short loc_180011443
0x180011432  mov     [rcx], r9b
0x180011435  add     r8, r15
0x180011438  add     rcx, r15
0x18001143b  sub     rax, r15
0x18001143e  sub     rdx, r15
0x180011441  jnz     short loc_180011425
0x180011443  test    rdx, rdx
0x180011446  lea     rax, [rcx-1]
0x18001144a  cmovnz  rax, rcx
0x18001144e  mov     byte ptr [rax], 0
0x180011451  jmp     loc_1800114F3
0x180011456  lea     rdx, aCompartment; "Compartment"
0x18001145d  mov     rcx, rbx; String1
0x180011460  call    cs:__imp__stricmp
0x180011466  test    eax, eax
0x180011468  jnz     short loc_180011475
0x18001146a  mov     eax, [rbx+28h]
0x18001146d  mov     [rdi+4ACh], eax
0x180011473  jmp     short loc_1800114F3
0x180011475  cmp     dword ptr [rbx+20h], 2
0x180011479  jnz     loc_18001151B
0x18001147f  lea     rdx, aDevspecificinf; "DevSpecificInfo"
0x180011486  mov     rcx, rbx; String1
0x180011489  call    cs:__imp__strcmpi
0x18001148f  test    eax, eax
0x180011491  jnz     loc_18001151B
0x180011497  mov     rcx, [rdi+360h]; hMem
0x18001149e  test    rcx, rcx
0x1800114a1  jz      short loc_1800114BE
0x1800114a3  call    cs:__imp_LocalFree
0x1800114a9  mov     qword ptr [rdi+360h], 0
0x1800114b4  mov     dword ptr [rdi+368h], 0
0x1800114be  mov     edx, [rbx+2Ch]; uBytes
0x1800114c1  mov     ecx, 40h ; '@'; uFlags
0x1800114c6  call    cs:__imp_LocalAlloc
0x1800114cc  mov     [rdi+360h], rax
0x1800114d3  test    rax, rax
0x1800114d6  jz      short loc_180011514
0x1800114d8  mov     ecx, [rbx+2Ch]
0x1800114db  mov     [rdi+368h], ecx
0x1800114e1  mov     rcx, rax; void *
0x1800114e4  mov     edx, [rbx+28h]
0x1800114e7  mov     r8d, [rbx+2Ch]; Size
0x1800114eb  add     rdx, rbx; Src
0x1800114ee  call    memcpy_0
0x1800114f3  add     si, r15w
0x1800114f7  add     rbx, 38h ; '8'
0x1800114fb  movzx   eax, si
0x1800114fe  cmp     eax, [rbp+0]
0x180011501  jb      loc_1800113C7
0x180011507  xor     eax, eax
0x180011509  add     rsp, 20h
0x18001150d  pop     r15
0x18001150f  pop     rdi
0x180011510  pop     rsi
0x180011511  pop     rbp
0x180011512  pop     rbx
0x180011513  retn
0x180011514  mov     eax, 8
0x180011519  jmp     short loc_180011509
0x18001151b  mov     eax, 25Ch
0x180011520  jmp     short loc_180011509
```
