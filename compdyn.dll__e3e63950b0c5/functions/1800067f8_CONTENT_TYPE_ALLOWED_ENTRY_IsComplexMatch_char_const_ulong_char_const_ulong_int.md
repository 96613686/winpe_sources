# CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)

- ea: `0x1800067f8`
- end: `0x1800068a8`
- name: `?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z`
- size: `176`
- prototype: `__int64 __fastcall(char *, unsigned int, const char *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800024d0`
- `0x1800067f8`

## callees

- `0x1800067f8`

## import_xrefs

- `msvcrt!toupper` at `0x180006823`
- `msvcrt!toupper` at `0x18000682d`
- `msvcrt!toupper` at `0x180006823`
- `msvcrt!toupper` at `0x18000682d`

## pseudocode

```c
__int64 __fastcall CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(
        char *a1,
        unsigned int a2,
        const char *a3,
        unsigned int a4)
{
  char v4; // al
  const char *v8; // r14
  int v9; // ebx
  int v10; // edi
  unsigned int v11; // ebx

  v4 = *a1;
  v8 = a1;
  if ( *a1 )
  {
    while ( v4 != 42 )
    {
      v9 = *v8;
      v10 = toupper(*a3);
      if ( toupper(v9) != v10 )
        return 0;
      v4 = *++v8;
      --a2;
      ++a3;
      --a4;
      if ( !v4 )
        return *a3 == 0;
    }
    v11 = 0;
    if ( (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v8 + 1, a2 - 1, a3, a4, 0)
      || *a3 && (unsigned int)CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(v8, a2, a3 + 1, a4 - 1, 0) )
    {
      return 1;
    }
  }
  else
  {
    return *a3 == 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1800067f8  push    rbx
0x1800067fa  push    rbp
0x1800067fb  push    rsi
0x1800067fc  push    rdi
0x1800067fd  push    r14
0x1800067ff  push    r15
0x180006801  sub     rsp, 38h
0x180006805  movzx   eax, byte ptr [rcx]
0x180006808  mov     ebp, r9d
0x18000680b  mov     rsi, r8
0x18000680e  mov     r15d, edx
0x180006811  mov     r14, rcx
0x180006814  test    al, al
0x180006816  jz      short loc_18000684B
0x180006818  cmp     al, 2Ah ; '*'
0x18000681a  jz      short loc_180006865
0x18000681c  movsx   ecx, byte ptr [rsi]; C
0x18000681f  movsx   ebx, byte ptr [r14]
0x180006823  call    cs:__imp_toupper
0x180006829  mov     ecx, ebx; C
0x18000682b  mov     edi, eax
0x18000682d  call    cs:__imp_toupper
0x180006833  cmp     eax, edi
0x180006835  jnz     short loc_180006861
0x180006837  movzx   eax, byte ptr [r14+1]
0x18000683c  inc     r14
0x18000683f  dec     r15d
0x180006842  inc     rsi
0x180006845  dec     ebp
0x180006847  test    al, al
0x180006849  jnz     short loc_180006818
0x18000684b  xor     ebx, ebx
0x18000684d  cmp     [rsi], bl
0x18000684f  setz    bl
0x180006852  mov     eax, ebx
0x180006854  add     rsp, 38h
0x180006858  pop     r15
0x18000685a  pop     r14
0x18000685c  pop     rdi
0x18000685d  pop     rsi
0x18000685e  pop     rbp
0x18000685f  pop     rbx
0x180006860  retn
0x180006861  xor     eax, eax
0x180006863  jmp     short loc_180006854
0x180006865  xor     ebx, ebx
0x180006867  lea     edx, [r15-1]; unsigned int
0x18000686b  lea     rcx, [r14+1]; char *
0x18000686f  mov     [rsp+68h+var_48], ebx; int
0x180006873  mov     r9d, ebp; unsigned int
0x180006876  mov     r8, rsi; char *
0x180006879  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x18000687e  test    eax, eax
0x180006880  jnz     short loc_1800068A1
0x180006882  cmp     [rsi], bl
0x180006884  jz      short loc_180006852
0x180006886  lea     r9d, [rbp-1]; unsigned int
0x18000688a  mov     [rsp+68h+var_48], ebx; int
0x18000688e  lea     r8, [rsi+1]; char *
0x180006892  mov     edx, r15d; unsigned int
0x180006895  mov     rcx, r14; char *
0x180006898  call    ?IsComplexMatch@CONTENT_TYPE_ALLOWED_ENTRY@@SAHPEBDK0KH@Z; CONTENT_TYPE_ALLOWED_ENTRY::IsComplexMatch(char const *,ulong,char const *,ulong,int)
0x18000689d  test    eax, eax
0x18000689f  jz      short loc_180006852
0x1800068a1  mov     ebx, 1
0x1800068a6  jmp     short loc_180006852
```
