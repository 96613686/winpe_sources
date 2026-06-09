# UnCompactHDMX

- ea: `0x18000c350`
- end: `0x18000c581`
- name: `UnCompactHDMX`
- size: `561`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000c874`

## callees

- `0x18000c350`
- `0x18001a060`
- `0x18001a2cc`
- `0x18001a348`
- `0x18001a3bc`
- `0x18001a76c`
- `0x18001a808`

## pseudocode

```c
__int16 __fastcall UnCompactHDMX(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned __int16 v9; // r12
  __int64 v13; // rsi
  __int16 result; // ax
  int v15; // r15d
  unsigned int v16; // edx
  unsigned int v17; // edi
  unsigned __int16 v18; // si
  unsigned int v19; // r15d
  unsigned __int16 v20; // di
  char v21[4]; // [rsp+30h] [rbp-28h] BYREF
  _WORD v22[2]; // [rsp+34h] [rbp-24h] BYREF
  _WORD v23[2]; // [rsp+38h] [rbp-20h] BYREF
  _WORD v24[2]; // [rsp+3Ch] [rbp-1Ch] BYREF
  int v25; // [rsp+40h] [rbp-18h] BYREF
  int v26; // [rsp+44h] [rbp-14h]
  _QWORD v27[2]; // [rsp+48h] [rbp-10h] BYREF
  unsigned int v29; // [rsp+D8h] [rbp+80h]

  v9 = 0;
  v22[0] = 0;
  v23[0] = 0;
  v27[0] = 0;
  v24[0] = 0;
  v21[0] = 0;
  v25 = 0;
  v13 = a1;
  *a8 = 0;
  result = ReadGeneric(a1, (__int64)v27, 8u, (unsigned __int8 *)HDMX_CONTROL, a3, v22);
  if ( !result )
  {
    v15 = HIDWORD(v27[0]);
    v26 = HIDWORD(v27[0]);
    HIDWORD(v27[0]) = (a5 + 3 + (unsigned __int16)GetGenericSize(&HDMX_DEVICE_REC_CONTROL)) & 0xFFFFFFFC;
    result = WriteGeneric((__int64)a2, (__int64)v27, 8u, (unsigned __int8 *)HDMX_CONTROL, a4, v23);
    if ( !result )
    {
      v16 = a3 + v22[0];
      *a8 += v23[0];
      v29 = v16;
      while ( v9 < SWORD1(v27[0]) )
      {
        v17 = v15 * v9 + v16;
        result = ReadGeneric(v13, (__int64)v24, 2u, (unsigned __int8 *)&HDMX_DEVICE_REC_CONTROL, v17, v22);
        if ( result )
          return result;
        result = WriteGeneric((__int64)a2, (__int64)v24, 2u, (unsigned __int8 *)&HDMX_DEVICE_REC_CONTROL, a4 + *a8, v23);
        if ( result )
          return result;
        v18 = 0;
        v19 = v17 + v22[0];
        *a8 += v23[0];
        v20 = 0;
        while ( v18 < a5 )
        {
          if ( v20 < a6 && v18 == *(_WORD *)(a7 + 2LL * v20) )
          {
            result = ReadByte(a1, v21, v19);
            if ( result )
              return result;
            result = WriteByte(a2, v21[0], a4 + *a8);
            if ( result )
              return result;
            ++v19;
            ++v20;
          }
          else
          {
            result = WriteByte(a2, 0, *a8 + a4);
            if ( result )
              return result;
          }
          ++*a8;
          ++v18;
        }
        result = ZeroLongWordAlign(a2, *a8 + a4, &v25);
        if ( result )
          return result;
        v16 = v29;
        v13 = a1;
        ++v9;
        v15 = v26;
        *a8 = v25 - a4;
      }
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000c350  mov     [rsp-40h+arg_0], rcx
0x18000c355  push    rbp
0x18000c356  push    rbx
0x18000c357  push    rsi
0x18000c358  push    rdi
0x18000c359  push    r12
0x18000c35b  push    r13
0x18000c35d  push    r14
0x18000c35f  push    r15
0x18000c361  mov     rbp, rsp
0x18000c364  sub     rsp, 58h
0x18000c368  mov     rbx, [rbp+arg_38]
0x18000c36f  lea     rax, [rbp+var_24]
0x18000c373  xor     r12d, r12d
0x18000c376  mov     [rsp+58h+var_30], rax
0x18000c37b  mov     edi, r8d
0x18000c37e  mov     [rbp+var_24], r12w
0x18000c383  mov     r14d, r9d
0x18000c386  mov     [rbp+var_20], r12w
0x18000c38b  mov     r13, rdx
0x18000c38e  mov     [rbp+var_10], r12
0x18000c392  lea     r8d, [r12+8]
0x18000c397  mov     [rbp+var_1C], r12w
0x18000c39c  lea     r9, HDMX_CONTROL
0x18000c3a3  mov     [rbp+var_28], r12b
0x18000c3a7  lea     rdx, [rbp+var_10]
0x18000c3ab  mov     [rbp+var_18], r12d
0x18000c3af  mov     rsi, rcx
0x18000c3b2  mov     [rbx], r12d
0x18000c3b5  mov     [rsp+58h+var_38], edi
0x18000c3b9  call    ReadGeneric
0x18000c3be  test    ax, ax
0x18000c3c1  jnz     loc_18000C570
0x18000c3c7  mov     r15d, dword ptr [rbp+var_10+4]
0x18000c3cb  lea     rcx, HDMX_DEVICE_REC_CONTROL
0x18000c3d2  mov     [rbp+var_14], r15d
0x18000c3d6  call    GetGenericSize
0x18000c3db  movzx   ecx, ax
0x18000c3de  lea     r8d, [r12+8]
0x18000c3e3  movzx   eax, [rbp+arg_20]
0x18000c3e7  lea     r9, HDMX_CONTROL
0x18000c3ee  add     eax, 3
0x18000c3f1  lea     rdx, [rbp+var_10]
0x18000c3f5  add     ecx, eax
0x18000c3f7  lea     rax, [rbp+var_20]
0x18000c3fb  and     ecx, 0FFFFFFFCh
0x18000c3fe  mov     [rsp+58h+var_30], rax
0x18000c403  mov     dword ptr [rbp+var_10+4], ecx
0x18000c406  mov     rcx, r13
0x18000c409  mov     [rsp+58h+var_38], r14d
0x18000c40e  call    WriteGeneric
0x18000c413  test    ax, ax
0x18000c416  jnz     loc_18000C570
0x18000c41c  movzx   edx, [rbp+var_24]
0x18000c420  movzx   eax, [rbp+var_20]
0x18000c424  add     edx, edi
0x18000c426  add     [rbx], eax
0x18000c428  mov     dword ptr [rbp+arg_38], edx
0x18000c42e  xor     r8d, r8d
0x18000c431  movsx   eax, word ptr [rbp+var_10+2]
0x18000c435  movzx   ecx, r12w
0x18000c439  cmp     ecx, eax
0x18000c43b  jge     loc_18000C56D
0x18000c441  imul    ecx, r15d
0x18000c445  lea     rax, [rbp+var_24]
0x18000c449  mov     [rsp+58h+var_30], rax
0x18000c44e  lea     r9, HDMX_DEVICE_REC_CONTROL
0x18000c455  mov     r8d, 2
0x18000c45b  lea     edi, [rcx+rdx]
0x18000c45e  mov     rcx, rsi
0x18000c461  lea     rdx, [rbp+var_1C]
0x18000c465  mov     [rsp+58h+var_38], edi
0x18000c469  call    ReadGeneric
0x18000c46e  test    ax, ax
0x18000c471  jnz     loc_18000C570
0x18000c477  mov     ecx, [rbx]
0x18000c479  lea     rax, [rbp+var_20]
0x18000c47d  add     ecx, r14d
0x18000c480  mov     [rsp+58h+var_30], rax
0x18000c485  mov     [rsp+58h+var_38], ecx
0x18000c489  lea     r9, HDMX_DEVICE_REC_CONTROL
0x18000c490  mov     rcx, r13
0x18000c493  lea     rdx, [rbp+var_1C]
0x18000c497  mov     r8d, 2
0x18000c49d  call    WriteGeneric
0x18000c4a2  xor     r10d, r10d
0x18000c4a5  test    ax, ax
0x18000c4a8  jnz     loc_18000C570
0x18000c4ae  movzx   r15d, [rbp+var_24]
0x18000c4b3  mov     esi, r10d
0x18000c4b6  movzx   eax, [rbp+var_20]
0x18000c4ba  add     r15d, edi
0x18000c4bd  add     [rbx], eax
0x18000c4bf  mov     edi, r10d
0x18000c4c2  mov     ecx, [rbx]
0x18000c4c4  mov     eax, ecx
0x18000c4c6  cmp     si, [rbp+arg_20]
0x18000c4ca  jnb     short loc_18000C536
0x18000c4cc  cmp     di, [rbp+arg_28]
0x18000c4d0  jnb     short loc_18000C517
0x18000c4d2  mov     rdx, [rbp+arg_30]
0x18000c4d6  movzx   eax, di
0x18000c4d9  cmp     si, [rdx+rax*2]
0x18000c4dd  jnz     short loc_18000C517
0x18000c4df  mov     rcx, [rbp+arg_0]
0x18000c4e3  lea     rdx, [rbp+var_28]
0x18000c4e7  mov     r8d, r15d
0x18000c4ea  call    ReadByte
0x18000c4ef  test    ax, ax
0x18000c4f2  jnz     short loc_18000C570
0x18000c4f4  mov     r8d, [rbx]
0x18000c4f7  mov     rcx, r13
0x18000c4fa  mov     dl, [rbp+var_28]
0x18000c4fd  add     r8d, r14d
0x18000c500  call    WriteByte
0x18000c505  test    ax, ax
0x18000c508  jnz     short loc_18000C570
0x18000c50a  mov     eax, 1
0x18000c50f  add     r15d, eax
0x18000c512  add     di, ax
0x18000c515  jmp     short loc_18000C52F
0x18000c517  lea     r8d, [rcx+r14]
0x18000c51b  xor     edx, edx
0x18000c51d  mov     rcx, r13
0x18000c520  call    WriteByte
0x18000c525  test    ax, ax
0x18000c528  jnz     short loc_18000C570
0x18000c52a  mov     eax, 1
0x18000c52f  add     [rbx], eax
0x18000c531  add     si, ax
0x18000c534  jmp     short loc_18000C4C2
0x18000c536  lea     edx, [rax+r14]
0x18000c53a  mov     rcx, r13
0x18000c53d  lea     r8, [rbp+var_18]
0x18000c541  call    ZeroLongWordAlign
0x18000c546  xor     r8d, r8d
0x18000c549  test    ax, ax
0x18000c54c  jnz     short loc_18000C570
0x18000c54e  mov     eax, [rbp+var_18]
0x18000c551  mov     edx, dword ptr [rbp+arg_38]
0x18000c557  sub     eax, r14d
0x18000c55a  mov     rsi, [rbp+arg_0]
0x18000c55e  inc     r12w
0x18000c562  mov     r15d, [rbp+var_14]
0x18000c566  mov     [rbx], eax
0x18000c568  jmp     loc_18000C431
0x18000c56d  mov     eax, r8d
0x18000c570  add     rsp, 58h
0x18000c574  pop     r15
0x18000c576  pop     r14
0x18000c578  pop     r13
0x18000c57a  pop     r12
0x18000c57c  pop     rdi
0x18000c57d  pop     rsi
0x18000c57e  pop     rbx
0x18000c57f  pop     rbp
0x18000c580  retn
```
