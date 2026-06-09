# DecMemReAlloc

- ea: `0x1800062ec`
- end: `0x180006381`
- name: `DecMemReAlloc`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x180001010`
- `0x180002c20`
- `0x180003be0`
- `0x180004a60`
- `0x180005300`
- `0x180009c10`

## callees

- `0x180004310`
- `0x180004760`
- `0x1800062ec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000631e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000631e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000636e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000636e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006379`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006379`

## pseudocode

```c
char *__fastcall DecMemReAlloc(__int64 a1, void *a2, unsigned int a3)
{
  char *v3; // rbx
  unsigned int v6; // eax
  HLOCAL v7; // rax

  v3 = 0;
  if ( !*(_DWORD *)(a1 + 76) )
  {
    v6 = (a3 + 3) & 0xFFFFFFFC;
    if ( a3 <= v6 )
    {
      v7 = a2 ? LocalReAlloc(a2, v6, 0x42u) : LocalAlloc(0x40u, v6);
      if ( v7 )
        return (char *)v7;
    }
    LocalFree(a2);
LABEL_10:
    ASN1DecSetError(a1, 0xFFFFFC12);
    return v3;
  }
  if ( a2 )
    goto LABEL_10;
  v3 = DecMemAlloc(a1, a3);
  if ( !v3 )
    goto LABEL_10;
  return v3;
}

```

## disassembly

```asm
0x1800062ec  mov     [rsp+arg_0], rbx
0x1800062f1  mov     [rsp+arg_8], rsi
0x1800062f6  push    rdi
0x1800062f7  sub     rsp, 20h
0x1800062fb  xor     ebx, ebx
0x1800062fd  mov     rdi, rdx
0x180006300  mov     rsi, rcx
0x180006303  cmp     [rcx+4Ch], ebx
0x180006306  jnz     short loc_180006351
0x180006308  lea     eax, [r8+3]
0x18000630c  and     eax, 0FFFFFFFCh
0x18000630f  cmp     r8d, eax
0x180006312  ja      short loc_180006376
0x180006314  mov     edx, eax; uBytes
0x180006316  test    rdi, rdi
0x180006319  jnz     short loc_180006365
0x18000631b  lea     ecx, [rbx+40h]; uFlags
0x18000631e  call    cs:__imp_LocalAlloc
0x180006324  test    rax, rax
0x180006327  jz      short loc_180006376
0x180006329  mov     rbx, rax
0x18000632c  jmp     short loc_18000633E
0x18000632e  mov     edx, r8d
0x180006331  call    DecMemAlloc
0x180006336  mov     rbx, rax
0x180006339  test    rax, rax
0x18000633c  jz      short loc_180006356
0x18000633e  mov     rsi, [rsp+28h+arg_8]
0x180006343  mov     rax, rbx
0x180006346  mov     rbx, [rsp+28h+arg_0]
0x18000634b  add     rsp, 20h
0x18000634f  pop     rdi
0x180006350  retn
0x180006351  test    rdi, rdi
0x180006354  jz      short loc_18000632E
0x180006356  mov     edx, 0FFFFFC12h
0x18000635b  mov     rcx, rsi
0x18000635e  call    ASN1DecSetError
0x180006363  jmp     short loc_18000633E
0x180006365  mov     r8d, 42h ; 'B'; uFlags
0x18000636b  mov     rcx, rdi; hMem
0x18000636e  call    cs:__imp_LocalReAlloc
0x180006374  jmp     short loc_180006324
0x180006376  mov     rcx, rdi; hMem
0x180006379  call    cs:__imp_LocalFree
0x18000637f  jmp     short loc_180006356
```
