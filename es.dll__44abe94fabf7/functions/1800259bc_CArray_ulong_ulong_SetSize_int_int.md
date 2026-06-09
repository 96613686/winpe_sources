# CArray<ulong,ulong>::SetSize(int,int)

- ea: `0x1800259bc`
- end: `0x180025af6`
- name: `?SetSize@?$CArray@KK@@QEAAJHH@Z`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180025900`

## callees

- `0x1800259bc`
- `0x1800434ba`
- `0x1800434c6`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025adb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800259d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025adb`

## pseudocode

```c
__int64 __fastcall CArray<unsigned long,unsigned long>::SetSize(char **a1, int a2)
{
  __int64 v2; // rdi
  char *v4; // rcx
  char *v5; // rax
  int v6; // r8d
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  int v10; // esi
  char *v11; // rax
  char *v12; // r14

  v2 = a2;
  v4 = *a1;
  if ( !a2 )
  {
    if ( v4 )
    {
      CoTaskMemFree(v4);
      *a1 = 0;
    }
    a1[1] = 0;
    return 0;
  }
  if ( v4 )
  {
    v6 = *((_DWORD *)a1 + 3);
    if ( a2 <= v6 )
    {
      if ( a2 > *((_DWORD *)a1 + 2) )
        memset_0(&v4[4 * *((int *)a1 + 2)], 0, 4LL * (a2 - *((_DWORD *)a1 + 2)));
      goto LABEL_20;
    }
    v7 = *((_DWORD *)a1 + 4);
    if ( !v7 )
    {
      v8 = *((_DWORD *)a1 + 2) / 8;
      v7 = 4;
      if ( v8 >= 4 )
      {
        v7 = *((_DWORD *)a1 + 2) / 8;
        if ( v8 > 1024 )
          v7 = 1024;
      }
    }
    v9 = v6 + v7;
    v10 = a2;
    if ( a2 < v9 )
      v10 = v9;
    v11 = (char *)CoTaskMemAlloc(4LL * v10);
    v12 = v11;
    if ( v11 )
    {
      memcpy_0(v11, *a1, 4LL * *((int *)a1 + 2));
      memset_0(&v12[4 * *((int *)a1 + 2)], 0, 4LL * ((int)v2 - *((_DWORD *)a1 + 2)));
      CoTaskMemFree(*a1);
      *a1 = v12;
      *((_DWORD *)a1 + 3) = v10;
      goto LABEL_20;
    }
    return 2147942414LL;
  }
  v5 = (char *)CoTaskMemAlloc(4LL * a2);
  *a1 = v5;
  if ( !v5 )
    return 2147942414LL;
  memset_0(v5, 0, 4 * v2);
  *((_DWORD *)a1 + 3) = v2;
LABEL_20:
  *((_DWORD *)a1 + 2) = v2;
  return 0;
}

```

## disassembly

```asm
0x1800259bc  push    rbx
0x1800259be  push    rsi
0x1800259bf  push    rdi
0x1800259c0  push    r14
0x1800259c2  sub     rsp, 28h
0x1800259c6  movsxd  rdi, edx
0x1800259c9  mov     rbx, rcx
0x1800259cc  mov     rcx, [rcx]; pv
0x1800259cf  test    edx, edx
0x1800259d1  jnz     short loc_1800259F2
0x1800259d3  test    rcx, rcx
0x1800259d6  jz      short loc_1800259E5
0x1800259d8  call    cs:__imp_CoTaskMemFree
0x1800259de  mov     qword ptr [rbx], 0
0x1800259e5  mov     qword ptr [rbx+8], 0
0x1800259ed  jmp     loc_180025AEA
0x1800259f2  test    rcx, rcx
0x1800259f5  jnz     short loc_180025A28
0x1800259f7  mov     rsi, rdi
0x1800259fa  shl     rsi, 2
0x1800259fe  mov     rcx, rsi; cb
0x180025a01  call    cs:__imp_CoTaskMemAlloc
0x180025a07  mov     [rbx], rax
0x180025a0a  test    rax, rax
0x180025a0d  jz      loc_180025AA3
0x180025a13  mov     r8, rsi; Size
0x180025a16  xor     edx, edx; Val
0x180025a18  mov     rcx, rax; void *
0x180025a1b  call    memset_0
0x180025a20  mov     [rbx+0Ch], edi
0x180025a23  jmp     loc_180025AE7
0x180025a28  mov     r8d, [rbx+0Ch]
0x180025a2c  cmp     edi, r8d
0x180025a2f  jg      short loc_180025A5A
0x180025a31  cmp     edi, [rbx+8]
0x180025a34  jle     loc_180025AE7
0x180025a3a  mov     eax, edi
0x180025a3c  xor     edx, edx; Val
0x180025a3e  sub     eax, [rbx+8]
0x180025a41  movsxd  r8, eax
0x180025a44  movsxd  rax, dword ptr [rbx+8]
0x180025a48  shl     r8, 2; Size
0x180025a4c  lea     rcx, [rcx+rax*4]; void *
0x180025a50  call    memset_0
0x180025a55  jmp     loc_180025AE7
0x180025a5a  mov     eax, [rbx+10h]
0x180025a5d  test    eax, eax
0x180025a5f  jnz     short loc_180025A84
0x180025a61  mov     eax, [rbx+8]
0x180025a64  mov     ecx, 8
0x180025a69  cdq
0x180025a6a  idiv    ecx
0x180025a6c  mov     ecx, eax
0x180025a6e  mov     eax, 4
0x180025a73  cmp     ecx, eax
0x180025a75  jl      short loc_180025A84
0x180025a77  mov     edx, 400h
0x180025a7c  mov     eax, ecx
0x180025a7e  cmp     ecx, edx
0x180025a80  jle     short loc_180025A84
0x180025a82  mov     eax, edx
0x180025a84  add     eax, r8d
0x180025a87  mov     esi, edi
0x180025a89  cmp     edi, eax
0x180025a8b  cmovl   esi, eax
0x180025a8e  movsxd  rcx, esi
0x180025a91  shl     rcx, 2; cb
0x180025a95  call    cs:__imp_CoTaskMemAlloc
0x180025a9b  mov     r14, rax
0x180025a9e  test    rax, rax
0x180025aa1  jnz     short loc_180025AAA
0x180025aa3  mov     eax, 8007000Eh
0x180025aa8  jmp     short loc_180025AEC
0x180025aaa  movsxd  r8, dword ptr [rbx+8]
0x180025aae  mov     rcx, r14; void *
0x180025ab1  mov     rdx, [rbx]; Src
0x180025ab4  shl     r8, 2; Size
0x180025ab8  call    memcpy_0
0x180025abd  mov     eax, edi
0x180025abf  xor     edx, edx; Val
0x180025ac1  sub     eax, [rbx+8]
0x180025ac4  movsxd  r8, eax
0x180025ac7  movsxd  rax, dword ptr [rbx+8]
0x180025acb  shl     r8, 2; Size
0x180025acf  lea     rcx, [r14+rax*4]; void *
0x180025ad3  call    memset_0
0x180025ad8  mov     rcx, [rbx]; pv
0x180025adb  call    cs:__imp_CoTaskMemFree
0x180025ae1  mov     [rbx], r14
0x180025ae4  mov     [rbx+0Ch], esi
0x180025ae7  mov     [rbx+8], edi
0x180025aea  xor     eax, eax
0x180025aec  add     rsp, 28h
0x180025af0  pop     r14
0x180025af2  pop     rdi
0x180025af3  pop     rsi
0x180025af4  pop     rbx
0x180025af5  retn
```
