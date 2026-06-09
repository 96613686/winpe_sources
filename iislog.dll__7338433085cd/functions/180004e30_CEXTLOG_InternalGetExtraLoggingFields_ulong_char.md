# CEXTLOG::InternalGetExtraLoggingFields(ulong *,char *)

- ea: `0x180004e30`
- end: `0x180004f5f`
- name: `?InternalGetExtraLoggingFields@CEXTLOG@@MEAAXPEAKPEAD@Z`
- size: `303`
- prototype: `void(CEXTLOG *__hidden this, unsigned int *, char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180004e30`

## import_xrefs

- `msvcrt!strcpy_s` at `0x180004e67`
- `msvcrt!strcpy_s` at `0x180004ea9`
- `msvcrt!strcpy_s` at `0x180004eec`
- `msvcrt!strcpy_s` at `0x180004f2b`
- `msvcrt!strcpy_s` at `0x180004e67`
- `msvcrt!strcpy_s` at `0x180004ea9`
- `msvcrt!strcpy_s` at `0x180004eec`
- `msvcrt!strcpy_s` at `0x180004f2b`

## string_xrefs

- `0x180004e99`: `User-Agent:`

## pseudocode

```c
void __fastcall CEXTLOG::InternalGetExtraLoggingFields(CEXTLOG *this, unsigned int *a2, char *a3)
{
  unsigned int v3; // edi
  __int64 v4; // rbp
  char *v8; // rbx
  __int64 v9; // rax
  unsigned int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned int v15; // ebp

  v3 = 0;
  v4 = -1;
  v8 = a3;
  if ( (*((_DWORD *)this + 394) & 0x100000) != 0 )
  {
    strcpy_s(a3, *a2, "Host:");
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = v9 + 1;
    if ( v10 >= *a2 )
      goto LABEL_21;
    v3 = v10;
    v8 = &a3[v10];
  }
  if ( (*((_DWORD *)this + 394) & 0x10000) != 0 )
  {
    strcpy_s(v8, (rsize_t)&a3[*a2 - (_QWORD)v8], "User-Agent:");
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v12 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v12 + v3 >= *a2 )
      goto LABEL_21;
    v8 += v12;
    v3 += v12;
  }
  if ( (*((_DWORD *)this + 394) & 0x20000) != 0 )
  {
    strcpy_s(v8, (rsize_t)&a3[*a2 - (_QWORD)v8], "Cookie:");
    v13 = -1;
    do
      ++v13;
    while ( v8[v13] );
    v14 = (unsigned int)(v13 + 1);
    if ( (unsigned int)v14 + v3 >= *a2 )
      goto LABEL_21;
    v8 += v14;
    v3 += v14;
  }
  if ( (*((_DWORD *)this + 394) & 0x40000) != 0 )
  {
    strcpy_s(v8, (rsize_t)&a3[*a2 - (_QWORD)v8], "Referer:");
    do
      ++v4;
    while ( v8[v4] );
    v15 = v4 + 1;
    if ( v3 + v15 < *a2 )
    {
      v3 += v15;
      v8 += v15;
    }
  }
LABEL_21:
  *v8 = 0;
  *a2 = v3 + 1;
}

```

## disassembly

```asm
0x180004e30  push    rbx
0x180004e32  push    rbp
0x180004e33  push    rsi
0x180004e34  push    rdi
0x180004e35  push    r14
0x180004e37  push    r15
0x180004e39  sub     rsp, 28h
0x180004e3d  xor     edi, edi
0x180004e3f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004e43  test    dword ptr [rcx+628h], 100000h
0x180004e4d  mov     r14, r8
0x180004e50  mov     rsi, rdx
0x180004e53  mov     r15, rcx
0x180004e56  mov     rbx, r8
0x180004e59  jz      short loc_180004E8A
0x180004e5b  mov     edx, [rdx]; SizeInBytes
0x180004e5d  lea     r8, aHost; "Host:"
0x180004e64  mov     rcx, rbx; Destination
0x180004e67  call    cs:__imp_strcpy_s
0x180004e6d  mov     rax, rbp
0x180004e70  inc     rax
0x180004e73  cmp     [r14+rax], dil
0x180004e77  jnz     short loc_180004E70
0x180004e79  inc     eax
0x180004e7b  cmp     eax, [rsi]
0x180004e7d  jnb     loc_180004F4A
0x180004e83  mov     ebx, eax
0x180004e85  mov     edi, eax
0x180004e87  add     rbx, r14
0x180004e8a  test    dword ptr [r15+628h], 10000h
0x180004e95  jz      short loc_180004ECD
0x180004e97  mov     edx, [rsi]
0x180004e99  lea     r8, aUserAgent; "User-Agent:"
0x180004ea0  sub     rdx, rbx
0x180004ea3  mov     rcx, rbx; Destination
0x180004ea6  add     rdx, r14; SizeInBytes
0x180004ea9  call    cs:__imp_strcpy_s
0x180004eaf  mov     rax, rbp
0x180004eb2  inc     rax
0x180004eb5  cmp     byte ptr [rbx+rax], 0
0x180004eb9  jnz     short loc_180004EB2
0x180004ebb  inc     eax
0x180004ebd  lea     ecx, [rax+rdi]
0x180004ec0  cmp     ecx, [rsi]
0x180004ec2  jnb     loc_180004F4A
0x180004ec8  add     rbx, rax
0x180004ecb  mov     edi, ecx
0x180004ecd  test    dword ptr [r15+628h], 20000h
0x180004ed8  jz      short loc_180004F0C
0x180004eda  mov     edx, [rsi]
0x180004edc  lea     r8, aCookie; "Cookie:"
0x180004ee3  sub     rdx, rbx
0x180004ee6  mov     rcx, rbx; Destination
0x180004ee9  add     rdx, r14; SizeInBytes
0x180004eec  call    cs:__imp_strcpy_s
0x180004ef2  mov     rax, rbp
0x180004ef5  inc     rax
0x180004ef8  cmp     byte ptr [rbx+rax], 0
0x180004efc  jnz     short loc_180004EF5
0x180004efe  inc     eax
0x180004f00  lea     ecx, [rax+rdi]
0x180004f03  cmp     ecx, [rsi]
0x180004f05  jnb     short loc_180004F4A
0x180004f07  add     rbx, rax
0x180004f0a  mov     edi, ecx
0x180004f0c  test    dword ptr [r15+628h], 40000h
0x180004f17  jz      short loc_180004F4A
0x180004f19  mov     edx, [rsi]
0x180004f1b  lea     r8, aReferer; "Referer:"
0x180004f22  sub     rdx, rbx
0x180004f25  mov     rcx, rbx; Destination
0x180004f28  add     rdx, r14; SizeInBytes
0x180004f2b  call    cs:__imp_strcpy_s
0x180004f31  inc     rbp
0x180004f34  cmp     byte ptr [rbx+rbp], 0
0x180004f38  jnz     short loc_180004F31
0x180004f3a  inc     ebp
0x180004f3c  lea     ecx, [rdi+rbp]
0x180004f3f  cmp     ecx, [rsi]
0x180004f41  jnb     short loc_180004F4A
0x180004f43  mov     eax, ebp
0x180004f45  mov     edi, ecx
0x180004f47  add     rbx, rax
0x180004f4a  lea     eax, [rdi+1]
0x180004f4d  mov     byte ptr [rbx], 0
0x180004f50  mov     [rsi], eax
0x180004f52  add     rsp, 28h
0x180004f56  pop     r15
0x180004f58  pop     r14
0x180004f5a  pop     rdi
0x180004f5b  pop     rsi
0x180004f5c  pop     rbp
0x180004f5d  pop     rbx
0x180004f5e  retn
```
