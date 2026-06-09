# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)

- ea: `0x180004990`
- end: `0x180004bfe`
- name: `?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `622`
- prototype: `__int64(wchar_t **, const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800017e4`
- `0x180001d3c`
- `0x180002650`
- `0x180003914`
- `0x180004000`
- `0x180006de0`
- `0x180008910`
- `0x180009488`
- `0x180009d10`

## callees

- `0x180004990`
- `0x180005b90`
- `0x1800103a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004b05`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004b05`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180004aad`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180004aad`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004a8e`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004a8e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b8f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004a4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004b8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a74`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a3c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a74`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
        wchar_t **a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rcx
  int v5; // ebx
  unsigned __int64 v6; // rbp
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rsi
  HANDLE v9; // rax
  wchar_t *v10; // rax
  wchar_t *v11; // rbp
  HANDLE ProcessHeap; // rax
  wchar_t *v13; // rax
  unsigned __int64 v14; // rsi
  wchar_t *v15; // r14
  size_t v16; // rsi
  int v17; // eax
  int v18; // ecx
  unsigned __int64 v19; // rax
  wchar_t *v21; // r8
  __int64 v22[3]; // [rsp+20h] [rbp-58h] BYREF
  va_list va; // [rsp+90h] [rbp+18h] BYREF

  va_start(va, a2);
  v22[0] = 0;
  v4 = 32;
  v5 = -2147024809;
  while ( 1 )
  {
    v6 = v4 + 1;
    if ( v4 + 1 < v4 )
    {
LABEL_7:
      v5 = -2147024362;
      goto LABEL_8;
    }
    v7 = (unsigned __int64)a1[2];
    if ( v7 == -1 )
    {
      v21 = a1[1];
      if ( v21 == (wchar_t *)-1LL )
      {
        if ( *a1 )
        {
          do
            v21 = (wchar_t *)((char *)v21 + 1);
          while ( (*a1)[(_QWORD)v21] );
        }
        else
        {
          v21 = 0;
        }
        a1[1] = v21;
      }
      if ( *a1 )
        v7 = (unsigned __int64)v21 + 1;
      else
        v7 = 0;
      a1[2] = (wchar_t *)v7;
    }
    if ( v7 )
    {
      if ( v6 > v7 )
      {
        v22[0] = 0;
        v8 = 2 * v7;
        if ( !is_mul_ok(v7, 2u) )
          goto LABEL_7;
        if ( v7 > 0x800 )
          v8 = v7 + 2048;
        if ( v6 > v8 )
          v8 = v4 + 1;
        v11 = *a1;
        ProcessHeap = GetProcessHeap();
        if ( v11 )
          v13 = (wchar_t *)HeapReAlloc(ProcessHeap, 0, v11, 2 * v8);
        else
          v13 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 2 * v8);
        if ( !v13 )
          goto LABEL_42;
        a1[2] = (wchar_t *)v8;
        *a1 = v13;
      }
    }
    else
    {
      v22[0] = 0;
      if ( !is_mul_ok(v6, 2u) )
        goto LABEL_7;
      v9 = GetProcessHeap();
      v10 = (wchar_t *)HeapAlloc(v9, 0, 2 * v6);
      if ( !v10 )
      {
LABEL_42:
        v5 = -2147024882;
        goto LABEL_8;
      }
      a1[2] = (wchar_t *)v6;
      *a1 = v10;
      *v10 = 0;
    }
    v14 = (unsigned __int64)a1[2];
    v15 = *a1;
    _o__set_errno(0);
    if ( v14 )
    {
      if ( v14 > 0x7FFFFFFF )
      {
        *v15 = 0;
        goto LABEL_8;
      }
      v16 = v14 - 1;
      v17 = vsnwprintf(v15, v16, a2, va);
      if ( v17 < 0 || v17 > v16 )
      {
        v15[v16] = 0;
        v18 = -2147024774;
      }
      else
      {
        v18 = 0;
        if ( v17 == v16 )
          v15[v16] = 0;
      }
    }
    else
    {
      v18 = -2147024809;
    }
    if ( v18 != -2147024774 )
      break;
    LODWORD(v22[0]) = 0;
    _o__get_errno(v22);
    if ( LODWORD(v22[0]) == 22 )
      goto LABEL_8;
    v19 = (unsigned __int64)a1[2];
    v4 = v19 + 32;
    if ( v19 + 32 < v19 )
    {
      v5 = -2147024362;
      goto LABEL_27;
    }
  }
  v5 = v18;
LABEL_8:
  if ( v5 >= 0 )
  {
    a1[1] = (wchar_t *)-1LL;
    return (unsigned int)v5;
  }
LABEL_27:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)a1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180004990  mov     rax, rsp
0x180004993  mov     [rax+10h], rdx
0x180004997  mov     [rax+18h], r8
0x18000499b  mov     [rax+20h], r9
0x18000499f  push    rbx
0x1800049a0  push    rbp
0x1800049a1  push    rdi
0x1800049a2  push    r12
0x1800049a4  push    r13
0x1800049a6  push    r15
0x1800049a8  sub     rsp, 48h
0x1800049ac  xor     r12d, r12d
0x1800049af  mov     [rax-38h], rsi
0x1800049b3  mov     rdi, rcx
0x1800049b6  mov     [rax-58h], r12
0x1800049ba  mov     r15, rdx
0x1800049bd  mov     [rax-40h], r14
0x1800049c1  lea     r13, [rax+18h]
0x1800049c5  mov     ecx, 20h ; ' '
0x1800049ca  mov     ebx, 80070057h
0x1800049cf  lea     rbp, [rcx+1]
0x1800049d3  cmp     rbp, rcx
0x1800049d6  jb      short loc_180004A0D
0x1800049d8  mov     r8, [rdi+10h]
0x1800049dc  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800049e0  jz      loc_180004B9A
0x1800049e6  test    r8, r8
0x1800049e9  jz      short loc_180004A27
0x1800049eb  cmp     rbp, r8
0x1800049ee  jbe     loc_180004AA4
0x1800049f4  mov     eax, 2
0x1800049f9  mov     [rsp+78h+var_58], r12
0x1800049fe  mul     r8
0x180004a01  mov     rsi, rax
0x180004a04  test    rdx, rdx
0x180004a07  jz      loc_180004B4E
0x180004a0d  mov     ebx, 80070216h
0x180004a12  test    ebx, ebx
0x180004a14  js      loc_180004B2C
0x180004a1a  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x180004a22  jmp     loc_180004B34
0x180004a27  mov     eax, 2
0x180004a2c  mov     [rsp+78h+var_58], r12
0x180004a31  mul     rbp
0x180004a34  mov     rsi, rax
0x180004a37  test    rdx, rdx
0x180004a3a  jnz     short loc_180004A0D
0x180004a3c  call    cs:__imp_GetProcessHeap
0x180004a42  mov     r8, rsi; dwBytes
0x180004a45  xor     edx, edx; dwFlags
0x180004a47  mov     rcx, rax; hHeap
0x180004a4a  call    cs:__imp_HeapAlloc
0x180004a50  test    rax, rax
0x180004a53  jz      loc_180004BCF
0x180004a59  mov     [rdi+10h], rbp
0x180004a5d  mov     [rdi], rax
0x180004a60  mov     [rax], r12w
0x180004a64  jmp     short loc_180004AA4
0x180004a66  cmp     rbp, rsi
0x180004a69  cmova   rsi, rbp
0x180004a6d  mov     rbp, [rdi]
0x180004a70  lea     r14, [rsi+rsi]
0x180004a74  call    cs:__imp_GetProcessHeap
0x180004a7a  xor     edx, edx; dwFlags
0x180004a7c  mov     rcx, rax; hHeap
0x180004a7f  test    rbp, rbp
0x180004a82  jz      loc_180004B8C
0x180004a88  mov     r9, r14; dwBytes
0x180004a8b  mov     r8, rbp; lpMem
0x180004a8e  call    cs:__imp_HeapReAlloc
0x180004a94  test    rax, rax
0x180004a97  jz      loc_180004BCF
0x180004a9d  mov     [rdi+10h], rsi
0x180004aa1  mov     [rdi], rax
0x180004aa4  mov     rsi, [rdi+10h]
0x180004aa8  xor     ecx, ecx
0x180004aaa  mov     r14, [rdi]
0x180004aad  call    cs:__imp__o__set_errno
0x180004ab3  test    rsi, rsi
0x180004ab6  jz      loc_180004BE3
0x180004abc  cmp     rsi, 7FFFFFFFh
0x180004ac3  ja      loc_180004BEE
0x180004ac9  dec     rsi
0x180004acc  mov     r9, r13; Args
0x180004acf  mov     rdx, rsi; BufferCount
0x180004ad2  mov     r8, r15; Format
0x180004ad5  mov     rcx, r14; Buffer
0x180004ad8  call    _vsnwprintf
0x180004add  test    eax, eax
0x180004adf  jns     loc_180004B6D
0x180004ae5  mov     [r14+rsi*2], r12w
0x180004aea  mov     ecx, 8007007Ah
0x180004aef  cmp     ecx, 8007007Ah
0x180004af5  jnz     loc_180004BF7
0x180004afb  lea     rcx, [rsp+78h+var_58]
0x180004b00  mov     dword ptr [rsp+78h+var_58], r12d
0x180004b05  call    cs:__imp__o__get_errno
0x180004b0b  cmp     dword ptr [rsp+78h+var_58], 16h
0x180004b10  jz      loc_180004A12
0x180004b16  mov     rax, [rdi+10h]
0x180004b1a  lea     rcx, [rax+20h]
0x180004b1e  cmp     rcx, rax
0x180004b21  jnb     loc_1800049CF
0x180004b27  mov     ebx, 80070216h
0x180004b2c  mov     rcx, rdi
0x180004b2f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004b34  mov     r14, [rsp+78h+var_40]
0x180004b39  mov     eax, ebx
0x180004b3b  mov     rsi, [rsp+78h+var_38]
0x180004b40  add     rsp, 48h
0x180004b44  pop     r15
0x180004b46  pop     r13
0x180004b48  pop     r12
0x180004b4a  pop     rdi
0x180004b4b  pop     rbp
0x180004b4c  pop     rbx
0x180004b4d  retn
0x180004b4e  mov     rcx, rax
0x180004b51  sub     rcx, r8
0x180004b54  cmp     rcx, 800h
0x180004b5b  jbe     loc_180004A66
0x180004b61  lea     rsi, [r8+800h]
0x180004b68  jmp     loc_180004A66
0x180004b6d  movsxd  rdx, eax
0x180004b70  cmp     rdx, rsi
0x180004b73  ja      loc_180004AE5
0x180004b79  mov     ecx, r12d
0x180004b7c  jnz     loc_180004AEF
0x180004b82  mov     [r14+rsi*2], r12w
0x180004b87  jmp     loc_180004AEF
0x180004b8c  mov     r8, r14; dwBytes
0x180004b8f  call    cs:__imp_HeapAlloc
0x180004b95  jmp     loc_180004A94
0x180004b9a  mov     r8, [rdi+8]
0x180004b9e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180004ba2  jnz     short loc_180004BBE
0x180004ba4  mov     rax, [rdi]
0x180004ba7  test    rax, rax
0x180004baa  jz      short loc_180004BD9
0x180004bac  nop     dword ptr [rax+00h]
0x180004bb0  inc     r8
0x180004bb3  cmp     [rax+r8*2], r12w
0x180004bb8  jnz     short loc_180004BB0
0x180004bba  mov     [rdi+8], r8
0x180004bbe  cmp     [rdi], r12
0x180004bc1  jz      short loc_180004BDE
0x180004bc3  inc     r8
0x180004bc6  mov     [rdi+10h], r8
0x180004bca  jmp     loc_1800049E6
0x180004bcf  mov     ebx, 8007000Eh
0x180004bd4  jmp     loc_180004A12
0x180004bd9  mov     r8, r12
0x180004bdc  jmp     short loc_180004BBA
0x180004bde  mov     r8, r12
0x180004be1  jmp     short loc_180004BC6
0x180004be3  mov     ecx, ebx
0x180004be5  test    rsi, rsi
0x180004be8  jz      loc_180004AEF
0x180004bee  mov     [r14], r12w
0x180004bf2  jmp     loc_180004A12
0x180004bf7  mov     ebx, ecx
0x180004bf9  jmp     loc_180004A12
```
