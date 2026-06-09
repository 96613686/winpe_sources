# GetStructFromRegistry

- ea: `0x180008290`
- end: `0x180008465`
- name: `GetStructFromRegistry`
- size: `469`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, int, __int64, int, __int64, unsigned __int8 *, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180017720`
- `0x180018480`
- `0x1800189b0`

## callees

- `0x1800076ac`
- `0x180008290`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000843e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800083c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000843e`

## pseudocode

```c
__int64 __fastcall GetStructFromRegistry(
        HKEY hKey,
        int a2,
        int a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        unsigned int a7,
        _DWORD *a8,
        unsigned __int8 *a9,
        unsigned int a10)
{
  int v10; // ebx
  int v11; // r14d
  unsigned int v12; // r13d
  int v14; // eax
  HKEY v15; // r10
  __int64 v16; // rdi
  __int64 v17; // rax
  _DWORD *v18; // rsi
  unsigned __int64 v19; // r12
  int v20; // r15d
  unsigned int *v21; // rdx
  HLOCAL v22; // rcx
  int i; // [rsp+50h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-40h] BYREF
  int v28; // [rsp+B0h] [rbp+18h]

  v28 = a3;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  hMem = 0;
  v14 = a2;
  v15 = hKey;
  for ( i = 0; v12 < a5; ++v12 )
  {
    v16 = 32LL * v12;
    if ( !v14 || (a3 & *(_DWORD *)(v16 + a4 + 8)) != 0 )
    {
      v17 = *(unsigned int *)(v16 + a4 + 24);
      v18 = (_DWORD *)(a6 + *(unsigned int *)(v16 + a4 + 20));
      if ( (int)v17 >= -1 )
      {
        v19 = a7;
        v21 = 0;
        v20 = a6;
      }
      else
      {
        v19 = a7;
        v20 = a6;
        LODWORD(v17) = v17 & 0x7FFFFFFF;
        v21 = (unsigned int *)(v17 + a6);
        if ( (unsigned __int64)(unsigned int)v17 + 4 > a7 )
          goto LABEL_6;
      }
      v10 = QueryRegValue(
              v15,
              *(LPCWSTR *)(v16 + a4),
              *(_DWORD *)(v16 + a4 + 12),
              a9,
              a10,
              *(_DWORD *)(v16 + a4 + 16),
              (unsigned __int8 **)&hMem,
              v21,
              &i);
      if ( v10 < 0 )
        goto LABEL_23;
      if ( i )
      {
        v11 |= *(_DWORD *)(v16 + a4 + 8);
        if ( *(_DWORD *)(v16 + a4 + 16) == 4 )
        {
          if ( (unsigned __int64)(unsigned int)((_DWORD)v18 - v20) + 4 > v19 )
            goto LABEL_6;
          v22 = hMem;
          *v18 = *(_DWORD *)hMem;
          LocalFree(v22);
        }
        else
        {
          if ( (unsigned __int64)(unsigned int)((_DWORD)v18 - v20) + 8 > v19 )
          {
LABEL_6:
            v10 = -2147467259;
            goto LABEL_23;
          }
          *(_QWORD *)v18 = hMem;
        }
        hMem = 0;
      }
      v14 = a2;
      a3 = v28;
      v15 = hKey;
    }
  }
  if ( v14 )
  {
    if ( a8 )
      *a8 = v11;
    if ( a3 != v11 )
      v10 = 1;
  }
LABEL_23:
  LocalFree(hMem);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008290  mov     rax, rsp
0x180008293  mov     [rax+20h], rbx
0x180008297  mov     [rax+18h], r8d
0x18000829b  mov     [rax+10h], edx
0x18000829e  mov     [rax+8], rcx
0x1800082a2  push    rbp
0x1800082a3  push    rsi
0x1800082a4  push    rdi
0x1800082a5  push    r12
0x1800082a7  push    r13
0x1800082a9  push    r14
0x1800082ab  push    r15
0x1800082ad  sub     rsp, 60h
0x1800082b1  xor     ebx, ebx
0x1800082b3  xor     r14d, r14d
0x1800082b6  xor     r13d, r13d
0x1800082b9  mov     [rsp+98h+hMem], rbx
0x1800082be  mov     rbp, r9
0x1800082c1  mov     eax, edx
0x1800082c3  mov     r10, rcx
0x1800082c6  mov     [rsp+98h+var_48], ebx
0x1800082ca  lea     edi, [rbx+1]
0x1800082cd  cmp     [rsp+98h+arg_20], ebx
0x1800082d4  jbe     loc_18000841F
0x1800082da  mov     edi, r13d
0x1800082dd  shl     rdi, 5
0x1800082e1  test    eax, eax
0x1800082e3  jz      short loc_1800082F0
0x1800082e5  test    [rdi+rbp+8], r8d
0x1800082ea  jz      loc_180008409
0x1800082f0  mov     esi, [rdi+rbp+14h]
0x1800082f4  mov     rcx, [rsp+98h+arg_28]
0x1800082fc  mov     eax, [rdi+rbp+18h]
0x180008300  add     rsi, rcx
0x180008303  cmp     eax, 0FFFFFFFFh
0x180008306  jz      short loc_180008337
0x180008308  test    eax, eax
0x18000830a  jns     short loc_180008337
0x18000830c  mov     r12d, [rsp+98h+arg_30]
0x180008314  mov     r15d, ecx
0x180008317  btr     eax, 1Fh
0x18000831b  lea     rdx, [rax+rcx]
0x18000831f  mov     ecx, edx
0x180008321  sub     ecx, r15d
0x180008324  add     rcx, 4
0x180008328  cmp     rcx, r12
0x18000832b  jbe     short loc_180008344
0x18000832d  mov     ebx, 80004005h
0x180008332  jmp     loc_180008439
0x180008337  mov     r12d, [rsp+98h+arg_30]
0x18000833f  xor     edx, edx
0x180008341  mov     r15d, ecx
0x180008344  mov     r9, [rsp+98h+arg_40]; unsigned __int8 *
0x18000834c  lea     rax, [rsp+98h+var_48]
0x180008351  mov     r8d, [rdi+rbp+0Ch]; int
0x180008356  mov     rcx, r10; hKey
0x180008359  mov     [rsp+98h+var_58], rax; int *
0x18000835e  lea     rax, [rsp+98h+hMem]
0x180008363  mov     [rsp+98h+var_60], rdx; unsigned int *
0x180008368  mov     rdx, [rdi+rbp]; lpValueName
0x18000836c  mov     [rsp+98h+var_68], rax; unsigned __int8 **
0x180008371  mov     eax, [rdi+rbp+10h]
0x180008375  mov     [rsp+98h+var_70], eax; unsigned int
0x180008379  mov     eax, [rsp+98h+arg_48]
0x180008380  mov     [rsp+98h+var_78], eax; unsigned int
0x180008384  call    ?QueryRegValue@@YAJPEAUHKEY__@@PEBGHPEAEKKPEAPEAEPEAKPEAH@Z; QueryRegValue(HKEY__ *,ushort const *,int,uchar *,ulong,ulong,uchar * *,ulong *,int *)
0x180008389  mov     ebx, eax
0x18000838b  test    eax, eax
0x18000838d  js      loc_180008439
0x180008393  cmp     [rsp+98h+var_48], 0
0x180008398  jz      short loc_1800083F2
0x18000839a  or      r14d, [rdi+rbp+8]
0x18000839f  cmp     dword ptr [rdi+rbp+10h], 4
0x1800083a4  jnz     short loc_1800083CF
0x1800083a6  mov     edx, esi
0x1800083a8  sub     edx, r15d
0x1800083ab  add     rdx, 4
0x1800083af  cmp     rdx, r12
0x1800083b2  ja      loc_18000832D
0x1800083b8  mov     rcx, [rsp+98h+hMem]; hMem
0x1800083bd  mov     eax, [rcx]
0x1800083bf  mov     [rsi], eax
0x1800083c1  call    cs:__imp_LocalFree
0x1800083c8  nop     dword ptr [rax+rax+00h]
0x1800083cd  jmp     short loc_1800083E9
0x1800083cf  mov     ecx, esi
0x1800083d1  sub     ecx, r15d
0x1800083d4  add     rcx, 8
0x1800083d8  cmp     rcx, r12
0x1800083db  ja      loc_18000832D
0x1800083e1  mov     rax, [rsp+98h+hMem]
0x1800083e6  mov     [rsi], rax
0x1800083e9  mov     [rsp+98h+hMem], 0
0x1800083f2  mov     eax, [rsp+98h+arg_8]
0x1800083f9  mov     r8d, [rsp+98h+arg_10]
0x180008401  mov     r10, [rsp+98h+arg_0]
0x180008409  mov     edi, 1
0x18000840e  add     r13d, edi
0x180008411  cmp     r13d, [rsp+98h+arg_20]
0x180008419  jb      loc_1800082DA
0x18000841f  test    eax, eax
0x180008421  jz      short loc_180008439
0x180008423  mov     rax, [rsp+98h+arg_38]
0x18000842b  test    rax, rax
0x18000842e  jz      short loc_180008433
0x180008430  mov     [rax], r14d
0x180008433  cmp     r8d, r14d
0x180008436  cmovnz  ebx, edi
0x180008439  mov     rcx, [rsp+98h+hMem]; hMem
0x18000843e  call    cs:__imp_LocalFree
0x180008445  nop     dword ptr [rax+rax+00h]
0x18000844a  mov     eax, ebx
0x18000844c  mov     rbx, [rsp+98h+arg_18]
0x180008454  add     rsp, 60h
0x180008458  pop     r15
0x18000845a  pop     r14
0x18000845c  pop     r13
0x18000845e  pop     r12
0x180008460  pop     rdi
0x180008461  pop     rsi
0x180008462  pop     rbp
0x180008463  retn
```
