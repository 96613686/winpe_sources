# Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::ConcatFormat(ushort const *,...)

- ea: `0x180004c10`
- end: `0x180005153`
- name: `?ConcatFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ`
- size: `1347`
- prototype: `__int64(_QWORD *, const wchar_t *, ...)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001d3c`
- `0x180002650`
- `0x180004000`
- `0x180009488`
- `0x180016250`

## callees

- `0x180004c10`
- `0x180005b90`
- `0x180005df0`
- `0x1800103a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004e59`
- `api-ms-win-crt-private-l1-1-0!_o__get_errno` at `0x180004e59`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180004dfc`
- `api-ms-win-crt-private-l1-1-0!_o__set_errno` at `0x180004dfc`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004dde`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000500f`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180004dde`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000500f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004eb3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000506f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004d95`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f2f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f4c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000506f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d87`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004dc4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ea5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff9`

## pseudocode

```c
__int64 Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::ConcatFormat(
        _QWORD *a1,
        const wchar_t *a2,
        ...)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rbx
  __int64 v6; // rbp
  int v7; // r12d
  _WORD *v8; // r15
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // r14
  __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // r8
  unsigned __int64 v16; // rdi
  HANDLE v17; // rax
  _WORD *v18; // rax
  HANDLE ProcessHeap; // rax
  _WORD *v20; // rax
  unsigned __int64 v21; // rdi
  int v22; // eax
  int v23; // ecx
  HANDLE v24; // rax
  HANDLE v26; // rax
  _WORD *v27; // rax
  unsigned __int64 v28; // r8
  _WORD *v29; // r9
  unsigned __int64 v30; // rcx
  _WORD *v31; // rdx
  _WORD *v32; // rcx
  _WORD *v33; // rbx
  HANDLE v34; // rax
  LPVOID v35; // rax
  __int64 v36; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v37[2]; // [rsp+28h] [rbp-60h] BYREF
  __int64 v38; // [rsp+38h] [rbp-50h]
  va_list Args; // [rsp+A0h] [rbp+18h] BYREF

  va_start(Args, a2);
  v36 = 0;
  if ( !*a1 || !*(_WORD *)*a1 )
    return Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
             a1,
             a2,
             Args);
  v4 = 32;
  v5 = 0;
  v6 = -1;
  v7 = -2147024809;
  v8 = 0;
  v37[0] = 0;
  v37[1] = 0;
  v38 = 0;
  while ( 1 )
  {
    v9 = v4 + 1;
    if ( v4 + 1 < v4 )
    {
LABEL_9:
      v7 = -2147024362;
      goto LABEL_10;
    }
    if ( v5 == -1 )
    {
      if ( v8 )
      {
        v5 = 1;
        v38 = 1;
      }
      else
      {
        v5 = 0;
        v38 = 0;
      }
    }
    v10 = v5;
    if ( v5 )
    {
      if ( v9 <= v5 )
        goto LABEL_36;
      v36 = 0;
      v11 = 2 * v5;
      v5 *= 2LL;
      if ( !is_mul_ok(v10, 2u) )
        goto LABEL_9;
      if ( v11 - v10 > 0x800 )
        v5 = v10 + 2048;
      if ( v9 > v5 )
        v5 = v9;
      ProcessHeap = GetProcessHeap();
      if ( v8 )
        v20 = HeapReAlloc(ProcessHeap, 0, v8, 2 * v5);
      else
        v20 = HeapAlloc(ProcessHeap, 0, 2 * v5);
      if ( !v20 )
        goto LABEL_80;
      v8 = v20;
      v37[0] = v20;
    }
    else
    {
      v36 = 0;
      if ( !is_mul_ok(v9, 2u) )
        goto LABEL_9;
      v17 = GetProcessHeap();
      v18 = HeapAlloc(v17, 0, 2 * v9);
      if ( !v18 )
      {
LABEL_80:
        v7 = -2147024882;
        goto LABEL_10;
      }
      v8 = v18;
      v37[0] = v18;
      v5 = v9;
      *v18 = 0;
    }
    v38 = v5;
LABEL_36:
    _o__set_errno(0);
    if ( v5 - 1 > 0x7FFFFFFE )
    {
      v23 = -2147024809;
      if ( v5 )
      {
        *v8 = 0;
        goto LABEL_10;
      }
    }
    else
    {
      v21 = v5 - 1;
      v22 = vsnwprintf(v8, v5 - 1, a2, Args);
      if ( v22 < 0 || v22 > v21 )
      {
        v23 = -2147024774;
        v8[v21] = 0;
      }
      else
      {
        v23 = 0;
        if ( v22 == v21 )
          v8[v21] = 0;
      }
    }
    if ( v23 != -2147024774 )
      break;
    LODWORD(v36) = 0;
    _o__get_errno(&v36);
    if ( (_DWORD)v36 == 22 )
      goto LABEL_10;
    v4 = v5 + 32;
    if ( v5 + 32 < v5 )
    {
      v7 = -2147024362;
LABEL_43:
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)v37);
      v8 = (_WORD *)v37[0];
      goto LABEL_44;
    }
  }
  v7 = v23;
LABEL_10:
  if ( v7 < 0 )
    goto LABEL_43;
  if ( v8 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v8[v12] );
  }
  else
  {
    v12 = 0;
  }
  v7 = 0;
  if ( v8 )
  {
    v13 = a1[1];
    if ( v13 == -1 )
    {
      if ( *a1 )
      {
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)(*a1 + 2 * v13) );
      }
      else
      {
        v13 = 0;
      }
      a1[1] = v13;
    }
    v14 = v13 + v12 + 1;
    if ( v14 < v13 + v12 )
      goto LABEL_25;
    v15 = a1[2];
    if ( v15 == -1 )
    {
      if ( v13 == -1 )
      {
        if ( *a1 )
        {
          do
            ++v6;
          while ( *(_WORD *)(*a1 + 2 * v6) );
        }
        else
        {
          v6 = 0;
        }
        a1[1] = v6;
      }
      else
      {
        v6 = v13;
      }
      if ( *a1 )
        v15 = v6 + 1;
      else
        v15 = 0;
      a1[2] = v15;
    }
    if ( v15 )
    {
      if ( v14 > v15 )
      {
        v16 = 2 * v15;
        if ( !is_mul_ok(v15, 2u) )
        {
LABEL_25:
          v7 = -2147024362;
          goto LABEL_44;
        }
        if ( v15 > 0x800 )
          v16 = v15 + 2048;
        if ( v14 > v16 )
          v16 = v13 + v12 + 1;
        v33 = (_WORD *)*a1;
        v34 = GetProcessHeap();
        if ( v33 )
          v35 = HeapReAlloc(v34, 0, v33, 2 * v16);
        else
          v35 = HeapAlloc(v34, 0, 2 * v16);
        if ( !v35 )
        {
          v7 = -2147024882;
          goto LABEL_44;
        }
        a1[2] = v16;
        *a1 = v35;
LABEL_58:
        v28 = v12 + 1;
        if ( v12 != -1 )
        {
          v29 = (_WORD *)(*a1 + 2LL * a1[1]);
          if ( v28 > 0x7FFFFFFF )
          {
            *v29 = 0;
          }
          else
          {
            if ( v12 > 0x7FFFFFFE )
            {
              *v29 = 0;
              a1[1] += v12;
              goto LABEL_44;
            }
            v30 = v12;
            v31 = v8;
            do
            {
              if ( !v30 )
                break;
              if ( !*v31 )
                break;
              *v29++ = *v31++;
              --v30;
              --v28;
            }
            while ( v28 );
            v32 = v29 - 1;
            if ( v28 )
              v32 = v29;
            *v32 = 0;
          }
        }
        a1[1] += v12;
        goto LABEL_44;
      }
    }
    else
    {
      if ( !is_mul_ok(v14, 2u) )
        goto LABEL_25;
      v26 = GetProcessHeap();
      v27 = HeapAlloc(v26, 0, 2 * v14);
      if ( v27 )
      {
        a1[2] = v14;
        *a1 = v27;
        *v27 = 0;
        goto LABEL_58;
      }
      v7 = -2147024882;
    }
    if ( v7 < 0 )
      goto LABEL_44;
    goto LABEL_58;
  }
LABEL_44:
  if ( v8 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004c10  mov     r11, rsp
0x180004c13  mov     [r11+10h], rdx
0x180004c17  mov     [r11+18h], r8
0x180004c1b  mov     [r11+20h], r9
0x180004c1f  push    r13
0x180004c21  push    r14
0x180004c23  sub     rsp, 78h
0x180004c27  mov     r13, rcx
0x180004c2a  mov     r14, rdx
0x180004c2d  xor     edx, edx
0x180004c2f  lea     rcx, [r11+18h]
0x180004c33  mov     [r11-68h], rdx
0x180004c37  mov     rax, [r13+0]
0x180004c3b  test    rax, rax
0x180004c3e  jz      loc_1800050DA
0x180004c44  cmp     [rax], dx
0x180004c47  jz      loc_1800050DA
0x180004c4d  mov     [r11-18h], rbx
0x180004c51  mov     eax, 20h ; ' '
0x180004c56  mov     [r11-20h], rbp
0x180004c5a  mov     ebx, edx
0x180004c5c  mov     [r11-28h], rsi
0x180004c60  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180004c67  mov     [r11-30h], rdi
0x180004c6b  mov     esi, edx
0x180004c6d  mov     [r11-38h], r12
0x180004c71  mov     r12d, 80070057h
0x180004c77  mov     [r11-40h], r15
0x180004c7b  mov     r15d, edx
0x180004c7e  mov     [r11-60h], rdx
0x180004c82  mov     [r11-58h], rdx
0x180004c86  mov     [r11-50h], rdx
0x180004c8a  lea     rdi, [rax+1]
0x180004c8e  cmp     rdi, rax
0x180004c91  jb      short loc_180004CCA
0x180004c93  cmp     rbx, rbp
0x180004c96  jz      loc_180005034
0x180004c9c  mov     rcx, rbx
0x180004c9f  test    rbx, rbx
0x180004ca2  jz      loc_180004D6E
0x180004ca8  cmp     rdi, rbx
0x180004cab  jbe     loc_180004DFA
0x180004cb1  mov     eax, 2
0x180004cb6  mov     [rsp+88h+var_68], rdx
0x180004cbb  mul     rcx
0x180004cbe  mov     rbx, rax
0x180004cc1  test    rdx, rdx
0x180004cc4  jz      loc_180004ECF
0x180004cca  mov     r12d, 80070216h
0x180004cd0  test    r12d, r12d
0x180004cd3  js      loc_180004E7D
0x180004cd9  test    r15, r15
0x180004cdc  jz      loc_180005130
0x180004ce2  mov     r14, rbp
0x180004ce5  inc     r14
0x180004ce8  cmp     word ptr [r15+r14*2], 0
0x180004cee  jnz     short loc_180004CE5
0x180004cf0  xor     r12d, r12d
0x180004cf3  test    r15, r15
0x180004cf6  jz      loc_180004E8C
0x180004cfc  mov     rcx, [r13+8]
0x180004d00  cmp     rcx, rbp
0x180004d03  jnz     short loc_180004D23
0x180004d05  mov     rax, [r13+0]
0x180004d09  test    rax, rax
0x180004d0c  jz      loc_1800050D3
0x180004d12  mov     rcx, rbp
0x180004d15  inc     rcx
0x180004d18  cmp     [rax+rcx*2], r12w
0x180004d1d  jnz     short loc_180004D15
0x180004d1f  mov     [r13+8], rcx
0x180004d23  lea     rax, [rcx+r14]
0x180004d27  lea     rbx, [rax+1]
0x180004d2b  cmp     rbx, rax
0x180004d2e  jb      short loc_180004D63
0x180004d30  mov     r8, [r13+10h]
0x180004d34  cmp     r8, rbp
0x180004d37  jz      loc_180005082
0x180004d3d  test    r8, r8
0x180004d40  jz      loc_180004F0D
0x180004d46  cmp     rbx, r8
0x180004d49  jbe     loc_180004F5D
0x180004d4f  mov     eax, 2
0x180004d54  mul     r8
0x180004d57  mov     rdi, rax
0x180004d5a  test    rdx, rdx
0x180004d5d  jz      loc_180004FDB
0x180004d63  mov     r12d, 80070216h
0x180004d69  jmp     loc_180004E8C
0x180004d6e  mov     eax, 2
0x180004d73  mov     [rsp+88h+var_68], rdx
0x180004d78  mul     rdi
0x180004d7b  mov     rbx, rax
0x180004d7e  test    rdx, rdx
0x180004d81  jnz     loc_180004CCA
0x180004d87  call    cs:__imp_GetProcessHeap
0x180004d8d  mov     r8, rbx; dwBytes
0x180004d90  xor     edx, edx; dwFlags
0x180004d92  mov     rcx, rax; hHeap
0x180004d95  call    cs:__imp_HeapAlloc
0x180004d9b  mov     rcx, rax
0x180004d9e  test    rax, rax
0x180004da1  jz      loc_180005077
0x180004da7  mov     r15, rax
0x180004daa  mov     [rsp+88h+var_60], rax
0x180004daf  xor     eax, eax
0x180004db1  mov     rbx, rdi
0x180004db4  mov     [rcx], ax
0x180004db7  jmp     short loc_180004DF5
0x180004db9  cmp     rdi, rbx
0x180004dbc  cmova   rbx, rdi
0x180004dc0  lea     rdi, [rbx+rbx]
0x180004dc4  call    cs:__imp_GetProcessHeap
0x180004dca  xor     edx, edx; dwFlags
0x180004dcc  mov     rcx, rax; hHeap
0x180004dcf  test    r15, r15
0x180004dd2  jz      loc_180004F49
0x180004dd8  mov     r9, rdi; dwBytes
0x180004ddb  mov     r8, r15; lpMem
0x180004dde  call    cs:__imp_HeapReAlloc
0x180004de4  test    rax, rax
0x180004de7  jz      loc_180005077
0x180004ded  mov     r15, rax
0x180004df0  mov     [rsp+88h+var_60], rax
0x180004df5  mov     [rsp+88h+var_50], rbx
0x180004dfa  xor     ecx, ecx
0x180004dfc  call    cs:__imp__o__set_errno
0x180004e02  lea     rax, [rbx-1]
0x180004e06  cmp     rax, 7FFFFFFEh
0x180004e0c  ja      loc_18000510A
0x180004e12  lea     rdi, [rbx-1]
0x180004e16  mov     r8, r14; Format
0x180004e19  mov     rdx, rdi; BufferCount
0x180004e1c  lea     r9, [rsp+88h+Args]; Args
0x180004e24  mov     rcx, r15; Buffer
0x180004e27  call    _vsnwprintf
0x180004e2c  test    eax, eax
0x180004e2e  jns     loc_180004EEA
0x180004e34  xor     eax, eax
0x180004e36  mov     ecx, 8007007Ah
0x180004e3b  mov     [r15+rdi*2], ax
0x180004e40  cmp     ecx, 8007007Ah
0x180004e46  jnz     loc_180005128
0x180004e4c  lea     rcx, [rsp+88h+var_68]
0x180004e51  mov     dword ptr [rsp+88h+var_68], 0
0x180004e59  call    cs:__imp__o__get_errno
0x180004e5f  cmp     dword ptr [rsp+88h+var_68], 16h
0x180004e64  jz      loc_180004CD0
0x180004e6a  lea     rax, [rbx+20h]
0x180004e6e  cmp     rax, rbx
0x180004e71  jnb     loc_180005121
0x180004e77  mov     r12d, 80070216h
0x180004e7d  lea     rcx, [rsp+88h+var_60]
0x180004e82  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180004e87  mov     r15, [rsp+88h+var_60]
0x180004e8c  mov     rdi, [rsp+88h+var_30]
0x180004e91  mov     rsi, [rsp+88h+var_28]
0x180004e96  mov     rbp, [rsp+88h+var_20]
0x180004e9b  mov     rbx, [rsp+88h+var_18]
0x180004ea0  test    r15, r15
0x180004ea3  jz      short loc_180004EB9
0x180004ea5  call    cs:__imp_GetProcessHeap
0x180004eab  mov     r8, r15; lpMem
0x180004eae  xor     edx, edx; dwFlags
0x180004eb0  mov     rcx, rax; hHeap
0x180004eb3  call    cs:__imp_HeapFree
0x180004eb9  mov     r15, [rsp+88h+var_40]
0x180004ebe  mov     eax, r12d
0x180004ec1  mov     r12, [rsp+88h+var_38]
0x180004ec6  add     rsp, 78h
0x180004eca  pop     r14
0x180004ecc  pop     r13
0x180004ece  retn
0x180004ecf  sub     rax, rcx
0x180004ed2  cmp     rax, 800h
0x180004ed8  jbe     loc_180004DB9
0x180004ede  lea     rbx, [rcx+800h]
0x180004ee5  jmp     loc_180004DB9
0x180004eea  movsxd  rdx, eax
0x180004eed  cmp     rdx, rdi
0x180004ef0  ja      loc_180004E34
0x180004ef6  xor     ecx, ecx
0x180004ef8  cmp     rdx, rdi
0x180004efb  jnz     loc_180004E40
0x180004f01  xor     eax, eax
0x180004f03  mov     [r15+rdi*2], ax
0x180004f08  jmp     loc_180004E40
0x180004f0d  mov     eax, 2
0x180004f12  mul     rbx
0x180004f15  mov     rdi, rax
0x180004f18  test    rdx, rdx
0x180004f1b  jnz     loc_180004D63
0x180004f21  call    cs:__imp_GetProcessHeap
0x180004f27  mov     r8, rdi; dwBytes
0x180004f2a  xor     edx, edx; dwFlags
0x180004f2c  mov     rcx, rax; hHeap
0x180004f2f  call    cs:__imp_HeapAlloc
0x180004f35  test    rax, rax
0x180004f38  jz      short loc_180004F57
0x180004f3a  xor     ecx, ecx
0x180004f3c  mov     [r13+10h], rbx
0x180004f40  mov     [r13+0], rax
0x180004f44  mov     [rax], cx
0x180004f47  jmp     short loc_180004F66
0x180004f49  mov     r8, rdi; dwBytes
0x180004f4c  call    cs:__imp_HeapAlloc
0x180004f52  jmp     loc_180004DE4
0x180004f57  mov     r12d, 8007000Eh
0x180004f5d  test    r12d, r12d
0x180004f60  js      loc_180004E8C
0x180004f66  lea     r8, [r14+1]
0x180004f6a  test    r8, r8
0x180004f6d  jz      short loc_180004FD2
0x180004f6f  mov     rcx, [r13+8]
0x180004f73  mov     rax, [r13+0]
0x180004f77  lea     r9, [rax+rcx*2]
0x180004f7b  cmp     r8, 7FFFFFFFh
0x180004f82  ja      loc_180005148
0x180004f88  cmp     r14, 7FFFFFFEh
0x180004f8f  ja      loc_1800050C4
0x180004f95  mov     rcx, r14
0x180004f98  mov     rdx, r15
0x180004f9b  nop     dword ptr [rax+rax+00h]
0x180004fa0  test    rcx, rcx
0x180004fa3  jz      short loc_180004FC2
0x180004fa5  movzx   eax, word ptr [rdx]
0x180004fa8  test    ax, ax
0x180004fab  jz      short loc_180004FC2
0x180004fad  mov     [r9], ax
0x180004fb1  add     rdx, 2
0x180004fb5  add     r9, 2
0x180004fb9  dec     rcx
0x180004fbc  sub     r8, 1
0x180004fc0  jnz     short loc_180004FA0
0x180004fc2  test    r8, r8
0x180004fc5  lea     rcx, [r9-2]
0x180004fc9  cmovnz  rcx, r9
0x180004fcd  xor     eax, eax
0x180004fcf  mov     [rcx], ax
0x180004fd2  add     [r13+8], r14
0x180004fd6  jmp     loc_180004E8C
0x180004fdb  mov     rcx, rax
0x180004fde  sub     rcx, r8
0x180004fe1  cmp     rcx, 800h
0x180004fe8  ja      short loc_18000502B
0x180004fea  cmp     rbx, rdi
0x180004fed  cmova   rdi, rbx
0x180004ff1  mov     rbx, [r13+0]
0x180004ff5  lea     rsi, [rdi+rdi]
0x180004ff9  call    cs:__imp_GetProcessHeap
0x180004fff  xor     edx, edx; dwFlags
0x180005001  mov     rcx, rax; hHeap
0x180005004  test    rbx, rbx
0x180005007  jz      short loc_18000506C
0x180005009  mov     r9, rsi; dwBytes
0x18000500c  mov     r8, rbx; lpMem
0x18000500f  call    cs:__imp_HeapReAlloc
0x180005015  test    rax, rax
0x180005018  jz      loc_1800050B9
0x18000501e  mov     [r13+10h], rdi
0x180005022  mov     [r13+0], rax
0x180005026  jmp     loc_180004F66
0x18000502b  lea     rdi, [r8+800h]
0x180005032  jmp     short loc_180004FEA
0x180005034  cmp     rsi, rbp
0x180005037  jnz     short loc_180005055
0x180005039  test    r15, r15
0x18000503c  jz      loc_1800050F1
0x180005042  mov     rsi, rbp
0x180005045  inc     rsi
0x180005048  cmp     word ptr [r15+rsi*2], 0
0x18000504e  jnz     short loc_180005045
0x180005050  mov     [rsp+88h+var_58], rsi
0x180005055  test    r15, r15
0x180005058  jz      loc_1800050F9
0x18000505e  lea     rbx, [rsi+1]
0x180005062  mov     [rsp+88h+var_50], rbx
0x180005067  jmp     loc_180004C9C
0x18000506c  mov     r8, rsi; dwBytes
0x18000506f  call    cs:__imp_HeapAlloc
0x180005075  jmp     short loc_180005015
0x180005077  mov     r12d, 8007000Eh
0x18000507d  jmp     loc_180004CD0
0x180005082  cmp     rcx, rbp
0x180005085  jnz     loc_180005138
0x18000508b  mov     rax, [r13+0]
0x18000508f  test    rax, rax
0x180005092  jz      short loc_180005106
0x180005094  inc     rbp
0x180005097  cmp     [rax+rbp*2], r12w
0x18000509c  jnz     short loc_180005094
0x18000509e  mov     [r13+8], rbp
0x1800050a2  cmp     [r13+0], r12
0x1800050a6  jz      loc_180005140
0x1800050ac  lea     r8, [rbp+1]
0x1800050b0  mov     [r13+10h], r8
0x1800050b4  jmp     loc_180004D3D
0x1800050b9  mov     r12d, 8007000Eh
0x1800050bf  jmp     loc_180004E8C
0x1800050c4  xor     eax, eax
  ... truncated ...
```
