# GetMetaDataDirectory(ushort const *)

- ea: `0x180004498`
- end: `0x18000451f`
- name: `?GetMetaDataDirectory@@YAPEAGPEBG@Z`
- size: `135`
- prototype: `char *__fastcall(const unsigned __int16 *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005700`

## callees

- `0x1800042e0`
- `0x180004498`
- `0x1800068b0`
- `0x180009030`
- `0x1800174fc`

## pseudocode

```c
char *__fastcall GetMetaDataDirectory(const unsigned __int16 *Src)
{
  __int64 v2; // rbx
  char *v3; // rax
  char *v4; // rdi
  size_t v6; // rbx

  if ( Src )
  {
    v2 = -1;
    do
      ++v2;
    while ( Src[v2] );
  }
  else
  {
    LODWORD(v2) = 0;
  }
  v3 = (char *)PkiNonzeroAlloc(2LL * (unsigned int)(v2 + 9));
  v4 = v3;
  if ( v3 )
  {
    v6 = 2LL * (unsigned int)v2;
    memcpy_0(v3, Src, v6);
    *(_OWORD *)&v4[v6] = *(_OWORD *)L"MetaData";
    *(_WORD *)&v4[v6 + 16] = aMetadata[8];
    if ( !(unsigned int)I_CryptRecursiveCreateLowIntegrityDirectory((LPCWSTR)v4) )
    {
      PkiFree(v4);
      return 0;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180004498  push    rbx
0x18000449a  push    rbp
0x18000449b  push    rsi
0x18000449c  push    rdi
0x18000449d  sub     rsp, 28h
0x1800044a1  xor     ebp, ebp
0x1800044a3  mov     rsi, rcx
0x1800044a6  test    rcx, rcx
0x1800044a9  jz      short loc_18000451B
0x1800044ab  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800044af  inc     rbx
0x1800044b2  cmp     [rcx+rbx*2], bp
0x1800044b6  jnz     short loc_1800044AF
0x1800044b8  lea     ecx, [rbx+9]
0x1800044bb  add     rcx, rcx; uBytes
0x1800044be  call    PkiNonzeroAlloc
0x1800044c3  mov     rdi, rax
0x1800044c6  test    rax, rax
0x1800044c9  jnz     short loc_1800044D7
0x1800044cb  mov     rax, rdi
0x1800044ce  add     rsp, 28h
0x1800044d2  pop     rdi
0x1800044d3  pop     rsi
0x1800044d4  pop     rbp
0x1800044d5  pop     rbx
0x1800044d6  retn
0x1800044d7  mov     ecx, ebx
0x1800044d9  mov     rdx, rsi; Src
0x1800044dc  lea     rbx, [rcx+rcx]
0x1800044e0  mov     rcx, rdi; void *
0x1800044e3  mov     r8, rbx; Size
0x1800044e6  call    memcpy_0
0x1800044eb  movups  xmm0, xmmword ptr cs:aMetadata; "MetaData"
0x1800044f2  mov     rcx, rdi; lpFileName
0x1800044f5  movups  xmmword ptr [rbx+rdi], xmm0
0x1800044f9  movzx   eax, word ptr cs:aMetadata+10h; ""
0x180004500  mov     [rbx+rdi+10h], ax
0x180004505  call    I_CryptRecursiveCreateLowIntegrityDirectory
0x18000450a  test    eax, eax
0x18000450c  jnz     short loc_1800044CB
0x18000450e  mov     rcx, rdi; hMem
0x180004511  call    PkiFree
0x180004516  mov     rdi, rbp
0x180004519  jmp     short loc_1800044CB
0x18000451b  mov     ebx, ebp
0x18000451d  jmp     short loc_1800044B8
```
