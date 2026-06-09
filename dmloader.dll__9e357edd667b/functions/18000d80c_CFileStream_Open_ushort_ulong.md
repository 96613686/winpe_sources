# CFileStream::Open(ushort *,ulong)

- ea: `0x18000d80c`
- end: `0x18000d8d9`
- name: `?Open@CFileStream@@QEAAJPEAGK@Z`
- size: `205`
- prototype: `__int64 __fastcall(CFileStream *this, unsigned __int16 *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009844`
- `0x18000ae74`
- `0x18000b45c`
- `0x18000bbc4`
- `0x18000d060`

## callees

- `0x18000d80c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18000d8b0`
- `api-ms-win-crt-private-l1-1-0!_o__wfsopen` at `0x18000d8b0`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000d82c`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18000d82c`

## pseudocode

```c
__int64 __fastcall CFileStream::Open(CFileStream *this, unsigned __int16 *a2, int a3)
{
  FILE *v4; // rcx
  __int64 v7; // rcx
  unsigned __int16 *v8; // r8
  _WORD *v9; // rax
  __int64 v10; // rdx
  _WORD *v11; // rcx
  int v12; // r8d
  const wchar_t *v13; // rdx

  v4 = (FILE *)*((_QWORD *)this + 68);
  if ( v4 )
    fclose(v4);
  v7 = 259;
  *((_QWORD *)this + 68) = 0;
  v8 = a2;
  v9 = (_WORD *)((char *)this + 20);
  v10 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*v8 )
      break;
    *v9++ = *v8++;
    --v7;
    --v10;
  }
  while ( v10 );
  v11 = v9 - 1;
  if ( v10 )
    v11 = v9;
  *v11 = 0;
  *((_WORD *)this + 269) = 0;
  if ( a3 == 0x80000000 )
  {
    v12 = 32;
    v13 = L"rb";
LABEL_13:
    *((_QWORD *)this + 68) = _wfsopen(a2, v13, v12);
    return *((_QWORD *)this + 68) == 0 ? 0x88781182 : 0;
  }
  if ( a3 == 0x40000000 )
  {
    v12 = 64;
    v13 = L"wb";
    goto LABEL_13;
  }
  return *((_QWORD *)this + 68) == 0 ? 0x88781182 : 0;
}

```

## disassembly

```asm
0x18000d80c  push    rbx
0x18000d80e  push    rbp
0x18000d80f  push    rsi
0x18000d810  push    rdi
0x18000d811  sub     rsp, 28h
0x18000d815  mov     rbx, rcx
0x18000d818  xor     ebp, ebp
0x18000d81a  mov     rcx, [rcx+220h]; Stream
0x18000d821  mov     esi, r8d
0x18000d824  mov     rdi, rdx
0x18000d827  test    rcx, rcx
0x18000d82a  jz      short loc_18000D832
0x18000d82c  call    cs:__imp_fclose
0x18000d832  mov     ecx, 103h
0x18000d837  mov     [rbx+220h], rbp
0x18000d83e  mov     r8, rdi
0x18000d841  lea     rax, [rbx+14h]
0x18000d845  lea     edx, [rcx+1]
0x18000d848  test    rcx, rcx
0x18000d84b  jz      short loc_18000D86C
0x18000d84d  movzx   r9d, word ptr [r8]
0x18000d851  test    r9w, r9w
0x18000d855  jz      short loc_18000D86C
0x18000d857  mov     [rax], r9w
0x18000d85b  add     r8, 2
0x18000d85f  add     rax, 2
0x18000d863  dec     rcx
0x18000d866  sub     rdx, 1
0x18000d86a  jnz     short loc_18000D848
0x18000d86c  test    rdx, rdx
0x18000d86f  lea     rcx, [rax-2]
0x18000d873  cmovnz  rcx, rax
0x18000d877  mov     [rcx], bp
0x18000d87a  mov     [rbx+21Ah], bp
0x18000d881  cmp     esi, 80000000h
0x18000d887  jnz     short loc_18000D898
0x18000d889  mov     r8d, 20h ; ' '
0x18000d88f  lea     rdx, aRb; "rb"
0x18000d896  jmp     short loc_18000D8AD
0x18000d898  cmp     esi, 40000000h
0x18000d89e  jnz     short loc_18000D8BD
0x18000d8a0  mov     r8d, 40h ; '@'; ShFlag
0x18000d8a6  lea     rdx, Mode; "wb"
0x18000d8ad  mov     rcx, rdi; FileName
0x18000d8b0  call    cs:__imp__wfsopen
0x18000d8b6  mov     [rbx+220h], rax
0x18000d8bd  mov     rax, [rbx+220h]
0x18000d8c4  neg     rax
0x18000d8c7  sbb     eax, eax
0x18000d8c9  not     eax
0x18000d8cb  and     eax, 88781182h
0x18000d8d0  add     rsp, 28h
0x18000d8d4  pop     rdi
0x18000d8d5  pop     rsi
0x18000d8d6  pop     rbp
0x18000d8d7  pop     rbx
0x18000d8d8  retn
```
