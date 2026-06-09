# MIME_MAP_TABLE::SelectMimeMappingForFileExt(ushort const *,STRA *,int *,int *)

- ea: `0x180004be0`
- end: `0x180004d32`
- name: `?SelectMimeMappingForFileExt@MIME_MAP_TABLE@@QEAAJPEBGPEAVSTRA@@PEAH2@Z`
- size: `338`
- prototype: `int(MIME_MAP_TABLE *__hidden this, const unsigned __int16 *, struct STRA *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001310`

## callees

- `0x180004b30`
- `0x180004be0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004c19`
- `msvcrt!wcsrchr` at `0x180004c2a`
- `msvcrt!wcsrchr` at `0x180004c19`
- `msvcrt!wcsrchr` at `0x180004c2a`
- `msvcrt!_wcsicmp` at `0x180004d0f`
- `msvcrt!_wcsicmp` at `0x180004d0f`
- `msvcrt!wcschr` at `0x180004c48`
- `msvcrt!wcschr` at `0x180007384`
- `msvcrt!wcschr` at `0x180004c48`
- `msvcrt!wcschr` at `0x180007384`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180004c83`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180004c83`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004c8f`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180004c8f`

## pseudocode

```c
int __fastcall MIME_MAP_TABLE::SelectMimeMappingForFileExt(MIME_MAP_TABLE *this, wchar_t *a2, struct STRA *a3, int *a4)
{
  wchar_t *v8; // rdi
  wchar_t *v9; // rax
  wchar_t *v10; // rax
  int v11; // r8d
  const unsigned __int16 *v12; // rbx
  STATIC_WSTRING_HASH *v13; // r14
  struct STATIC_WSTRING_HASH_RECORD *Key; // rdi
  const char *Str; // rax
  int result; // eax
  unsigned int v17; // ecx
  const wchar_t *v18; // r8
  __int16 v19; // dx
  const wchar_t *v20; // rdx
  wchar_t *v21; // rax
  const wchar_t *v22; // rdx
  unsigned __int16 v23; // ax
  int v24; // eax
  int v25; // ecx

  *a4 = 0;
  if ( !a2 || !*a2 )
    return 0;
  v8 = wcsrchr(a2, 0x2Fu);
  v9 = wcsrchr(a2, 0x5Cu);
  if ( v8 > v9 )
    v9 = v8;
  if ( !v9 )
    v9 = a2;
  v10 = wcschr(v9, 0x2Eu);
  if ( v10 )
  {
    v12 = v10 + 1;
    if ( v10 == (wchar_t *)-2LL )
    {
      v13 = (MIME_MAP_TABLE *)((char *)this + 8);
      goto LABEL_12;
    }
  }
  else
  {
    v12 = (const unsigned __int16 *)&dword_18000BD4C;
  }
  v13 = (MIME_MAP_TABLE *)((char *)this + 8);
  do
  {
    Key = STATIC_WSTRING_HASH::FindKey(v13, v12, v11);
    if ( Key )
      goto LABEL_11;
    v21 = wcschr(v12, 0x2Eu);
    v12 = v21 + 1;
    if ( !v21 )
      v12 = 0;
  }
  while ( v12 );
LABEL_12:
  v17 = 0;
  if ( *((_DWORD *)v13 + 262) )
  {
    v22 = L"*";
    v23 = 42;
    do
    {
      ++v22;
      v17 = v23 + 101 * v17;
      v23 = *v22;
    }
    while ( *v22 );
  }
  else
  {
    v18 = L"*";
    v19 = 42;
    do
    {
      ++v18;
      v17 = (v19 & 0xFFDF) + 101 * v17;
      v19 = *v18;
    }
    while ( *v18 );
  }
  Key = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)v13 + v17 % 0x83);
  if ( !Key )
    return 0;
  do
  {
    v20 = *(const wchar_t **)Key;
    if ( !*((_DWORD *)v13 + 262) )
    {
      if ( !_wcsicmp(L"*", v20) )
        break;
      goto LABEL_18;
    }
    v24 = *v20;
    v25 = 42 - v24;
    if ( v24 == 42 )
      v25 = -v20[1];
    if ( !v25 )
      break;
LABEL_18:
    Key = (struct STATIC_WSTRING_HASH_RECORD *)*((_QWORD *)Key + 1);
  }
  while ( Key );
  if ( Key )
  {
LABEL_11:
    Str = STRA::QueryStr((struct STATIC_WSTRING_HASH_RECORD *)((char *)Key + 80));
    result = STRA::Copy(a3, Str);
    *a4 = 1;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180004be0  push    rbx
0x180004be2  push    rbp
0x180004be3  push    rsi
0x180004be4  push    rdi
0x180004be5  push    r14
0x180004be7  sub     rsp, 20h
0x180004beb  mov     dword ptr [r9], 0
0x180004bf2  mov     rsi, r9
0x180004bf5  mov     rbp, r8
0x180004bf8  mov     rbx, rdx
0x180004bfb  mov     r14, rcx
0x180004bfe  test    rdx, rdx
0x180004c01  jz      loc_180004D2B
0x180004c07  cmp     word ptr [rdx], 0
0x180004c0b  jz      loc_180004D2B
0x180004c11  mov     edx, 2Fh ; '/'; Ch
0x180004c16  mov     rcx, rbx; Str
0x180004c19  call    cs:__imp_wcsrchr
0x180004c1f  mov     edx, 5Ch ; '\'; Ch
0x180004c24  mov     rcx, rbx; Str
0x180004c27  mov     rdi, rax
0x180004c2a  call    cs:__imp_wcsrchr
0x180004c30  cmp     rdi, rax
0x180004c33  cmova   rax, rdi
0x180004c37  test    rax, rax
0x180004c3a  jz      loc_180007368
0x180004c40  mov     edx, 2Eh ; '.'; Ch
0x180004c45  mov     rcx, rax; Str
0x180004c48  call    cs:__imp_wcschr
0x180004c4e  test    rax, rax
0x180004c51  jz      loc_180007370
0x180004c57  lea     rbx, [rax+2]
0x180004c5b  test    rbx, rbx
0x180004c5e  jz      loc_1800073A3
0x180004c64  add     r14, 8
0x180004c68  mov     rdx, rbx; unsigned __int16 *
0x180004c6b  mov     rcx, r14; this
0x180004c6e  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180004c73  mov     rdi, rax
0x180004c76  test    rax, rax
0x180004c79  jz      loc_18000737C
0x180004c7f  lea     rcx, [rdi+50h]
0x180004c83  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180004c89  mov     rdx, rax
0x180004c8c  mov     rcx, rbp
0x180004c8f  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004c95  mov     dword ptr [rsi], 1
0x180004c9b  add     rsp, 20h
0x180004c9f  pop     r14
0x180004ca1  pop     rdi
0x180004ca2  pop     rsi
0x180004ca3  pop     rbp
0x180004ca4  pop     rbx
0x180004ca5  retn
0x180004ca6  xor     ecx, ecx
0x180004ca8  mov     ebx, 2Ah ; '*'
0x180004cad  cmp     [r14+418h], ecx
0x180004cb4  jnz     loc_1800073AC
0x180004cba  lea     r8, String1; "*"
0x180004cc1  movzx   edx, bx
0x180004cc4  and     edx, 0FFDFh
0x180004cca  imul    ecx, 65h ; 'e'
0x180004ccd  lea     r8, [r8+2]
0x180004cd1  add     ecx, edx
0x180004cd3  movzx   edx, word ptr [r8]
0x180004cd7  test    dx, dx
0x180004cda  jnz     short loc_180004CC4
0x180004cdc  mov     eax, 0FA232CF3h
0x180004ce1  mul     ecx
0x180004ce3  shr     edx, 7
0x180004ce6  imul    eax, edx, 83h
0x180004cec  sub     ecx, eax
0x180004cee  mov     rdi, [r14+rcx*8]
0x180004cf2  test    rdi, rdi
0x180004cf5  jz      short loc_180004D2B
0x180004cf7  cmp     dword ptr [r14+418h], 0
0x180004cff  mov     rdx, [rdi]; String2
0x180004d02  jnz     loc_1800073CF
0x180004d08  lea     rcx, String1; "*"
0x180004d0f  call    cs:__imp__wcsicmp
0x180004d15  test    eax, eax
0x180004d17  jz      loc_1800073EC
0x180004d1d  mov     rdi, [rdi+8]
0x180004d21  test    rdi, rdi
0x180004d24  jnz     short loc_180004CF7
0x180004d26  jmp     loc_1800073EC
0x180004d2b  xor     eax, eax
0x180004d2d  jmp     loc_180004C9B
0x180007368  mov     rax, rbx
0x18000736b  jmp     loc_180004C40
0x180007370  lea     rbx, dword_18000BD4C
0x180007377  jmp     loc_180004C64
0x18000737c  mov     edx, 2Eh ; '.'; Ch
0x180007381  mov     rcx, rbx; Str
0x180007384  call    cs:__imp_wcschr
0x18000738a  test    rax, rax
0x18000738d  lea     rbx, [rax+2]
0x180007391  cmovz   rbx, rax
0x180007395  test    rbx, rbx
0x180007398  jnz     loc_180004C68
0x18000739e  jmp     loc_180004CA6
0x1800073a3  add     r14, 8
0x1800073a7  jmp     loc_180004CA6
0x1800073ac  lea     rdx, String1; "*"
0x1800073b3  movzx   eax, bx
0x1800073b6  imul    ecx, 65h ; 'e'
0x1800073b9  lea     rdx, [rdx+2]
0x1800073bd  movzx   eax, ax
0x1800073c0  add     ecx, eax
0x1800073c2  movzx   eax, word ptr [rdx]
0x1800073c5  test    ax, ax
0x1800073c8  jnz     short loc_1800073B6
0x1800073ca  jmp     loc_180004CDC
0x1800073cf  movzx   eax, word ptr [rdx]
0x1800073d2  movzx   ecx, bx
0x1800073d5  sub     ecx, eax
0x1800073d7  jnz     short loc_1800073E4
0x1800073d9  xor     eax, eax
0x1800073db  movzx   ecx, ax
0x1800073de  movzx   eax, word ptr [rdx+2]
0x1800073e2  sub     ecx, eax
0x1800073e4  test    ecx, ecx
0x1800073e6  jnz     loc_180004D1D
0x1800073ec  test    rdi, rdi
0x1800073ef  jz      loc_180004D2B
0x1800073f5  jmp     loc_180004C7F
```
