# DecMemAlloc

- ea: `0x180004760`
- end: `0x1800047d2`
- name: `DecMemAlloc`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003be0`
- `0x180004444`
- `0x1800044d0`
- `0x180005300`
- `0x1800062e0`
- `0x1800062ec`
- `0x180006600`
- `0x180009c10`

## callees

- `0x180004310`
- `0x180004760`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004789`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004789`

## pseudocode

```c
char *__fastcall DecMemAlloc(__int64 a1, unsigned int a2)
{
  char *v2; // rbx
  unsigned int v3; // r8d
  unsigned int v6; // ecx

  v2 = 0;
  v3 = (a2 + 3) & 0xFFFFFFFC;
  if ( a2 > v3 )
    goto LABEL_6;
  if ( *(_DWORD *)(a1 + 76) )
  {
    v6 = *(_DWORD *)(a1 + 104);
    if ( v6 < v3 )
      goto LABEL_6;
    v2 = *(char **)(a1 + 96);
    *(_QWORD *)(a1 + 96) = &v2[v3];
    *(_DWORD *)(a1 + 104) = v6 - v3;
  }
  else
  {
    v2 = (char *)LocalAlloc(0x40u, v3);
  }
  if ( !v2 )
LABEL_6:
    ASN1DecSetError(a1, 0xFFFFFC12);
  return v2;
}

```

## disassembly

```asm
0x180004760  mov     [rsp+arg_0], rbx
0x180004765  push    rdi
0x180004766  sub     rsp, 20h
0x18000476a  lea     r8d, [rdx+3]
0x18000476e  xor     ebx, ebx
0x180004770  and     r8d, 0FFFFFFFCh
0x180004774  mov     rdi, rcx
0x180004777  cmp     edx, r8d
0x18000477a  ja      short loc_1800047A5
0x18000477c  cmp     [rcx+4Ch], ebx
0x18000477f  jnz     short loc_1800047B4
0x180004781  mov     edx, r8d; uBytes
0x180004784  mov     ecx, 40h ; '@'; uFlags
0x180004789  call    cs:__imp_LocalAlloc
0x18000478f  mov     rbx, rax
0x180004792  test    rbx, rbx
0x180004795  jz      short loc_1800047A5
0x180004797  mov     rax, rbx
0x18000479a  mov     rbx, [rsp+28h+arg_0]
0x18000479f  add     rsp, 20h
0x1800047a3  pop     rdi
0x1800047a4  retn
0x1800047a5  mov     edx, 0FFFFFC12h
0x1800047aa  mov     rcx, rdi
0x1800047ad  call    ASN1DecSetError
0x1800047b2  jmp     short loc_180004797
0x1800047b4  mov     ecx, [rcx+68h]
0x1800047b7  cmp     ecx, r8d
0x1800047ba  jb      short loc_1800047A5
0x1800047bc  mov     rbx, [rdi+60h]
0x1800047c0  mov     eax, r8d
0x1800047c3  add     rax, rbx
0x1800047c6  sub     ecx, r8d
0x1800047c9  mov     [rdi+60h], rax
0x1800047cd  mov     [rdi+68h], ecx
0x1800047d0  jmp     short loc_180004792
```
