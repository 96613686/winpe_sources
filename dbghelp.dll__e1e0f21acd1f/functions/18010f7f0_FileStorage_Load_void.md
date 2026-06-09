# FileStorage::Load(void)

- ea: `0x18010f7f0`
- end: `0x18010f8b6`
- name: `?Load@FileStorage@@AEAA_NXZ`
- size: `198`
- prototype: `bool __fastcall(FileStorage *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180110910`
- `0x180110940`

## callees

- `0x180027430`
- `0x1800acbc0`
- `0x18010f7f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010f86b`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18010f86b`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18010f811`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x18010f811`

## pseudocode

```c
char __fastcall FileStorage::Load(FileStorage *this)
{
  int v2; // edx
  __int64 v3; // rbp
  char *v4; // rcx
  void *v5; // rcx

  if ( *((_BYTE *)this + 64) )
    return 1;
  v2 = *((_DWORD *)this + 21);
  *((_BYTE *)this + 64) = 1;
  if ( fseek(*((FILE **)this + 9), v2, 0) )
    return 1;
  v3 = *((int *)this + 20);
  if ( (int)v3 < 0
    || (int)v3 > *((_DWORD *)this + 2) + *((_DWORD *)this + 6) - *((_DWORD *)this + 4)
    && !(unsigned int)dia::Buffer::grow((FileStorage *)((char *)this + 8), v3)
    || (v4 = (char *)*((_QWORD *)this + 2),
        *((_QWORD *)this + 2) = &v4[v3],
        fread(v4, *((unsigned int *)this + 20), 1u, *((FILE **)this + 9)) != 1) )
  {
    v5 = (void *)*((_QWORD *)this + 1);
    if ( v5 )
    {
      memset_0(v5, 0, *((_DWORD *)this + 4) - (int)v5);
      *((_QWORD *)this + 2) = *((_QWORD *)this + 1);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18010f7f0  push    rdi
0x18010f7f2  sub     rsp, 20h
0x18010f7f6  cmp     byte ptr [rcx+40h], 0
0x18010f7fa  mov     rdi, rcx
0x18010f7fd  jnz     loc_18010F8AE
0x18010f803  mov     edx, [rcx+54h]; Offset
0x18010f806  xor     r8d, r8d; Origin
0x18010f809  mov     byte ptr [rcx+40h], 1
0x18010f80d  mov     rcx, [rcx+48h]; Stream
0x18010f811  call    cs:__imp_fseek
0x18010f817  test    eax, eax
0x18010f819  jnz     loc_18010F8AE
0x18010f81f  mov     [rsp+28h+arg_0], rbx
0x18010f824  mov     [rsp+28h+arg_8], rbp
0x18010f829  movsxd  rbp, dword ptr [rdi+50h]
0x18010f82d  mov     [rsp+28h+arg_10], rsi
0x18010f832  test    ebp, ebp
0x18010f834  js      short loc_18010F877
0x18010f836  mov     eax, [rdi+18h]
0x18010f839  sub     eax, [rdi+10h]
0x18010f83c  add     eax, [rdi+8]
0x18010f83f  cmp     ebp, eax
0x18010f841  jle     short loc_18010F852
0x18010f843  mov     edx, ebp; int
0x18010f845  lea     rcx, [rdi+8]; this
0x18010f849  call    ?grow@Buffer@dia@@IEAAHJ@Z; dia::Buffer::grow(long)
0x18010f84e  test    eax, eax
0x18010f850  jz      short loc_18010F877
0x18010f852  mov     rcx, [rdi+10h]; Buffer
0x18010f856  mov     r8d, 1; ElementCount
0x18010f85c  lea     rax, [rcx+rbp]
0x18010f860  mov     [rdi+10h], rax
0x18010f864  mov     edx, [rdi+50h]; ElementSize
0x18010f867  mov     r9, [rdi+48h]; Stream
0x18010f86b  call    cs:__imp_fread
0x18010f871  cmp     rax, 1
0x18010f875  jz      short loc_18010F897
0x18010f877  mov     rcx, [rdi+8]; void *
0x18010f87b  test    rcx, rcx
0x18010f87e  jz      short loc_18010F897
0x18010f880  mov     eax, [rdi+10h]
0x18010f883  xor     edx, edx; Val
0x18010f885  sub     eax, ecx
0x18010f887  movsxd  r8, eax; Size
0x18010f88a  call    memset_0
0x18010f88f  mov     rax, [rdi+8]
0x18010f893  mov     [rdi+10h], rax
0x18010f897  mov     rbp, [rsp+28h+arg_8]
0x18010f89c  mov     al, 1
0x18010f89e  mov     rbx, [rsp+28h+arg_0]
0x18010f8a3  mov     rsi, [rsp+28h+arg_10]
0x18010f8a8  add     rsp, 20h
0x18010f8ac  pop     rdi
0x18010f8ad  retn
0x18010f8ae  mov     al, 1
0x18010f8b0  add     rsp, 20h
0x18010f8b4  pop     rdi
0x18010f8b5  retn
```
