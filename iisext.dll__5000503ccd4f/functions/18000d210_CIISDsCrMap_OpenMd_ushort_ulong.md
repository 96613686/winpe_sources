# CIISDsCrMap::OpenMd(ushort *,ulong)

- ea: `0x18000d210`
- end: `0x18000d305`
- name: `?OpenMd@CIISDsCrMap@@QEAAJPEAGK@Z`
- size: `245`
- prototype: `__int64 __fastcall(CIISDsCrMap *this, unsigned __int16 *)`
- caller_count: `10`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ac50`
- `0x18000b22c`
- `0x18000b6b0`
- `0x18000b7a8`
- `0x18000bd80`
- `0x18000c0ac`
- `0x18000d4c0`
- `0x18000d5dc`
- `0x18000d81c`
- `0x18000d930`

## callees

- `0x180003de8`
- `0x18000d210`
- `0x1800111a2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18000d2ba`
- `msvcrt!wcscpy_s` at `0x18000d2ba`
- `KERNEL32!LocalFree` at `0x18000d2e7`
- `KERNEL32!LocalFree` at `0x18000d2e7`
- `KERNEL32!LocalAlloc` at `0x18000d257`
- `KERNEL32!LocalAlloc` at `0x18000d257`

## pseudocode

```c
__int64 __fastcall CIISDsCrMap::OpenMd(CIISDsCrMap *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  __int64 v4; // rcx
  __int64 v5; // rbx
  __int64 v7; // r15
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rdi
  int v11; // ebx

  v2 = -1;
  v4 = *((_QWORD *)this + 15);
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v4 + 2 * v5) );
  do
    ++v2;
  while ( a2[v2] );
  v7 = (unsigned int)v5 + v2 + 2;
  v8 = (unsigned __int16 *)LocalAlloc(0, 2 * v7);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  memcpy_0(v8, *((const void **)this + 15), 2LL * (unsigned int)v5);
  if ( (_DWORD)v5 && *(_WORD *)(*((_QWORD *)this + 15) + 2LL * (unsigned int)(v5 - 1)) != 47 && *a2 && *a2 != 47 )
  {
    v9[(unsigned int)v5] = 47;
    LODWORD(v5) = v5 + 1;
  }
  wcscpy_s(&v9[(unsigned int)v5], v7 - (unsigned int)v5, a2);
  v11 = OpenAdminBaseKey(
          *((unsigned __int16 **)this + 16),
          v9,
          3u,
          (struct IMSAdminBaseW **)this + 7,
          (unsigned int *)this + 16);
  LocalFree(v9);
  if ( v11 < 0 )
    *((_DWORD *)this + 16) = 0;
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d210  push    rbx
0x18000d212  push    rbp
0x18000d213  push    rsi
0x18000d214  push    rdi
0x18000d215  push    r12
0x18000d217  push    r14
0x18000d219  push    r15
0x18000d21b  sub     rsp, 30h
0x18000d21f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d223  mov     rsi, rcx
0x18000d226  mov     rcx, [rcx+78h]
0x18000d22a  mov     rbx, rax
0x18000d22d  xor     r12d, r12d
0x18000d230  mov     rbp, rdx
0x18000d233  inc     rbx
0x18000d236  cmp     [rcx+rbx*2], r12w
0x18000d23b  jnz     short loc_18000D233
0x18000d23d  mov     r14d, ebx
0x18000d240  inc     rax
0x18000d243  cmp     [rdx+rax*2], r12w
0x18000d248  jnz     short loc_18000D240
0x18000d24a  lea     r15, [rax+2]
0x18000d24e  xor     ecx, ecx; uFlags
0x18000d250  add     r15, r14
0x18000d253  lea     rdx, [r15+r15]; uBytes
0x18000d257  call    cs:__imp_LocalAlloc
0x18000d25d  mov     rdi, rax
0x18000d260  test    rax, rax
0x18000d263  jnz     short loc_18000D26F
0x18000d265  mov     eax, 8007000Eh
0x18000d26a  jmp     loc_18000D2F6
0x18000d26f  mov     rdx, [rsi+78h]; Src
0x18000d273  add     r14, r14
0x18000d276  mov     r8, r14; Size
0x18000d279  mov     rcx, rdi; void *
0x18000d27c  call    memcpy_0
0x18000d281  test    ebx, ebx
0x18000d283  jz      short loc_18000D2AB
0x18000d285  mov     rax, [rsi+78h]
0x18000d289  lea     ecx, [rbx-1]
0x18000d28c  mov     edx, 2Fh ; '/'
0x18000d291  cmp     [rax+rcx*2], dx
0x18000d295  jz      short loc_18000D2AB
0x18000d297  cmp     [rbp+0], r12w
0x18000d29c  jz      short loc_18000D2AB
0x18000d29e  cmp     [rbp+0], dx
0x18000d2a2  jz      short loc_18000D2AB
0x18000d2a4  mov     [r14+rdi], dx
0x18000d2a9  inc     ebx
0x18000d2ab  mov     eax, ebx
0x18000d2ad  mov     r8, rbp; Source
0x18000d2b0  sub     r15, rax
0x18000d2b3  mov     rdx, r15; SizeInWords
0x18000d2b6  lea     rcx, [rdi+rax*2]; Destination
0x18000d2ba  call    cs:__imp_wcscpy_s
0x18000d2c0  mov     rcx, [rsi+80h]; unsigned __int16 *
0x18000d2c7  lea     r14, [rsi+40h]
0x18000d2cb  lea     r9, [rsi+38h]; struct IMSAdminBaseW **
0x18000d2cf  mov     [rsp+68h+var_48], r14; unsigned int *
0x18000d2d4  mov     r8d, 3; unsigned int
0x18000d2da  mov     rdx, rdi; unsigned __int16 *
0x18000d2dd  call    ?OpenAdminBaseKey@@YAJPEAG0KPEAPEAUIMSAdminBaseW@@PEAK@Z; OpenAdminBaseKey(ushort *,ushort *,ulong,IMSAdminBaseW * *,ulong *)
0x18000d2e2  mov     rcx, rdi; hMem
0x18000d2e5  mov     ebx, eax
0x18000d2e7  call    cs:__imp_LocalFree
0x18000d2ed  test    ebx, ebx
0x18000d2ef  jns     short loc_18000D2F4
0x18000d2f1  mov     [r14], r12d
0x18000d2f4  mov     eax, ebx
0x18000d2f6  add     rsp, 30h
0x18000d2fa  pop     r15
0x18000d2fc  pop     r14
0x18000d2fe  pop     r12
0x18000d300  pop     rdi
0x18000d301  pop     rsi
0x18000d302  pop     rbp
0x18000d303  pop     rbx
0x18000d304  retn
```
