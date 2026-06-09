# DiscpCreateDiscoveredTarget

- ea: `0x180008af8`
- end: `0x180008e7b`
- name: `DiscpCreateDiscoveredTarget`
- size: `899`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009618`

## callees

- `0x180001cfe`
- `0x180005d2c`
- `0x180008af8`
- `0x180018f24`

## import_xrefs

- `ISCSIUM!DiscpValidateiSCSIString` at `0x180008bc8`
- `ISCSIUM!DiscpValidateiSCSIString` at `0x180008bc8`
- `ISCSIUM!DiscpAllocMemory` at `0x180008c14`
- `ISCSIUM!DiscpAllocMemory` at `0x180008ca8`
- `ISCSIUM!DiscpAllocMemory` at `0x180008c14`
- `ISCSIUM!DiscpAllocMemory` at `0x180008ca8`
- `ISCSIUM!DiscpCopyString` at `0x180008bac`
- `ISCSIUM!DiscpCopyString` at `0x180008bfd`
- `ISCSIUM!DiscpCopyString` at `0x180008d83`
- `ISCSIUM!DiscpCopyString` at `0x180008bac`
- `ISCSIUM!DiscpCopyString` at `0x180008bfd`
- `ISCSIUM!DiscpCopyString` at `0x180008d83`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e10`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e1f`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e3c`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e4b`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e10`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e1f`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e3c`
- `ISCSIUM!DiscpFreeMemory` at `0x180008e4b`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008b5f`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008c56`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ce6`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008d34`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008b5f`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008c56`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008ce6`
- `ISCSIUM!DiscpAlignDataStruct` at `0x180008d34`

## pseudocode

```c
__int64 __fastcall DiscpCreateDiscoveredTarget(_QWORD *a1, unsigned int *a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r13d
  unsigned int v5; // edi
  __int64 v6; // r14
  unsigned int Target; // ebx
  void *v8; // rax
  unsigned int v9; // r12d
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r15
  __int64 v14; // rbx
  unsigned int i; // esi
  __int64 v16; // rcx
  unsigned int v18; // [rsp+68h] [rbp-29h] BYREF
  int v19; // [rsp+6Ch] [rbp-25h] BYREF
  _WORD *v20; // [rsp+70h] [rbp-21h] BYREF
  _WORD *v21; // [rsp+78h] [rbp-19h] BYREF
  __int64 v22; // [rsp+80h] [rbp-11h] BYREF
  __int64 v23; // [rsp+88h] [rbp-9h] BYREF
  _DWORD *v24; // [rsp+90h] [rbp-1h] BYREF
  __int64 v25; // [rsp+98h] [rbp+7h]

  v4 = 0;
  v25 = *(_QWORD *)(a3 + 40);
  v5 = 0;
  v6 = 0;
  v18 = *a2;
  v24 = (_DWORD *)*a1;
  v20 = v24;
  v21 = 0;
  v23 = 0;
  v22 = 0;
  v19 = 0;
  if ( (unsigned int)DiscpAlignDataStruct(&v24, &v18, 4)
    || (v20 = v24, v18 <= 4)
    || (v5 = *v24, v18 -= 4, v20 = v24 + 1, v21 = 0, (unsigned int)DiscpCopyString(&v21, &v19, &v20, 224, &v18))
    || !*v21
    || (unsigned int)DiscpValidateiSCSIString()
    || !v5
    || (v23 = 0, (Target = DiscpCopyString(&v23, &v19, &v20, 255, &v18)) != 0) )
  {
LABEL_30:
    Target = -268500967;
  }
  else
  {
    v8 = (void *)DiscpAllocMemory(8 * v5);
    v6 = (__int64)v8;
    if ( v8 )
    {
      memset_0(v8, 0, 8LL * v5);
      v9 = 0;
      while ( !Target )
      {
        Target = DiscpAlignDataStruct(&v20, &v18, 4);
        if ( !Target )
        {
          if ( v18 < 4 )
            goto LABEL_30;
          v10 = *(unsigned int *)v20;
          v20 += 2;
          v18 -= 4;
          if ( !(_DWORD)v10 )
            goto LABEL_30;
          if ( (unsigned __int64)(1026 * v10) > 0xFFFFFFFF )
            goto LABEL_30;
          v11 = (unsigned int)(1026 * v10 + 8);
          if ( (unsigned int)v11 < 8 )
            goto LABEL_30;
          v12 = DiscpAllocMemory(v11);
          v13 = v12;
          if ( v12 )
          {
            *(_QWORD *)(v6 + 8LL * v9) = v12;
            *(_DWORD *)v12 = v10;
            *(_BYTE *)(v12 + 4) = 0;
            Target = 0;
            do
            {
              if ( Target )
                break;
              if ( (unsigned int)DiscpAlignDataStruct(&v20, &v18, 4) )
                goto LABEL_30;
              if ( v18 < 2 )
                goto LABEL_30;
              v14 = v13 + 1026LL * v4 + 8;
              *(_WORD *)(v14 + 1024) = *v20++;
              v18 -= 2;
              if ( (unsigned int)DiscpAlignDataStruct(&v20, &v18, 4) )
                goto LABEL_30;
              v22 = v14 + 512;
              DiscpGetIPAddressFromDataBlock(&v22, &v20, &v18, 256);
              v22 = v13 + 1026LL * v4++ + 8;
              Target = DiscpCopyString(&v22, &v19, &v20, 256, &v18);
            }
            while ( v4 < (unsigned int)v10 );
            v4 = 0;
          }
          else
          {
            Target = 8;
          }
        }
        if ( ++v9 >= v5 )
        {
          if ( !Target )
            Target = DiscpCreateTarget((_DWORD)v21, v23, v25, 0, 0, 0, v5, v6, *(_DWORD *)(a3 + 32), 5, a4);
          break;
        }
      }
    }
    else
    {
      Target = 8;
    }
  }
  if ( v21 )
    DiscpFreeMemory(v21);
  if ( v23 )
    DiscpFreeMemory(v23);
  if ( v6 )
  {
    for ( i = 0; i < v5; ++i )
    {
      v16 = *(_QWORD *)(v6 + 8LL * i);
      if ( v16 )
        DiscpFreeMemory(v16);
    }
    DiscpFreeMemory(v6);
  }
  *a1 = v20;
  *a2 = v18;
  return Target;
}

```

## disassembly

```asm
0x180008af8  mov     rax, rsp
0x180008afb  mov     [rax+20h], r9
0x180008aff  mov     [rax+18h], r8
0x180008b03  mov     [rax+10h], rdx
0x180008b07  mov     [rax+8], rcx
0x180008b0b  push    rbp
0x180008b0c  push    rbx
0x180008b0d  push    rsi
0x180008b0e  push    rdi
0x180008b0f  push    r12
0x180008b11  push    r13
0x180008b13  push    r14
0x180008b15  push    r15
0x180008b17  lea     rbp, [rax-5Fh]
0x180008b1b  sub     rsp, 0A8h
0x180008b22  mov     rax, [r8+28h]
0x180008b26  xor     r13d, r13d
0x180008b29  mov     [rbp+57h+var_50], rax
0x180008b2d  mov     edi, r13d
0x180008b30  mov     eax, [rdx]
0x180008b32  mov     r14d, r13d
0x180008b35  mov     [rbp+57h+var_80], eax
0x180008b38  lea     rdx, [rbp+57h+var_80]
0x180008b3c  mov     rax, [rcx]
0x180008b3f  lea     r8d, [r13+4]
0x180008b43  lea     rcx, [rbp+57h+var_58]
0x180008b47  mov     [rbp+57h+var_58], rax
0x180008b4b  mov     [rbp+57h+var_78], rax
0x180008b4f  mov     [rbp+57h+var_70], r13
0x180008b53  mov     [rbp+57h+var_60], r13
0x180008b57  mov     [rbp+57h+var_68], r13
0x180008b5b  mov     [rbp+57h+var_7C], r13d
0x180008b5f  call    cs:__imp_DiscpAlignDataStruct
0x180008b65  test    eax, eax
0x180008b67  jnz     loc_180008DFF
0x180008b6d  cmp     [rbp+57h+var_80], 4
0x180008b71  mov     rcx, [rbp+57h+var_58]
0x180008b75  mov     [rbp+57h+var_78], rcx
0x180008b79  jbe     loc_180008DFF
0x180008b7f  mov     edi, [rcx]
0x180008b81  lea     rax, [rcx+4]
0x180008b85  add     [rbp+57h+var_80], 0FFFFFFFCh
0x180008b89  lea     r8, [rbp+57h+var_78]
0x180008b8d  mov     [rbp+57h+var_78], rax
0x180008b91  lea     rdx, [rbp+57h+var_7C]
0x180008b95  lea     rax, [rbp+57h+var_80]
0x180008b99  mov     [rbp+57h+var_70], r13
0x180008b9d  mov     r9d, 0E0h
0x180008ba3  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180008ba8  lea     rcx, [rbp+57h+var_70]
0x180008bac  call    cs:__imp_DiscpCopyString
0x180008bb2  test    eax, eax
0x180008bb4  jnz     loc_180008DFF
0x180008bba  mov     rcx, [rbp+57h+var_70]
0x180008bbe  cmp     [rcx], r13w
0x180008bc2  jz      loc_180008DFF
0x180008bc8  call    cs:__imp_DiscpValidateiSCSIString
0x180008bce  test    eax, eax
0x180008bd0  jnz     loc_180008DFF
0x180008bd6  test    edi, edi
0x180008bd8  jz      loc_180008DFF
0x180008bde  lea     rax, [rbp+57h+var_80]
0x180008be2  mov     [rbp+57h+var_60], r13
0x180008be6  mov     r9d, 0FFh
0x180008bec  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180008bf1  lea     r8, [rbp+57h+var_78]
0x180008bf5  lea     rdx, [rbp+57h+var_7C]
0x180008bf9  lea     rcx, [rbp+57h+var_60]
0x180008bfd  call    cs:__imp_DiscpCopyString
0x180008c03  mov     ebx, eax
0x180008c05  test    eax, eax
0x180008c07  jnz     loc_180008DFF
0x180008c0d  lea     ecx, ds:0[rdi*8]
0x180008c14  call    cs:__imp_DiscpAllocMemory
0x180008c1a  mov     r14, rax
0x180008c1d  test    rax, rax
0x180008c20  jz      loc_180008DF8
0x180008c26  mov     r8d, edi
0x180008c29  xor     edx, edx; Val
0x180008c2b  shl     r8, 3; Size
0x180008c2f  mov     rcx, rax; void *
0x180008c32  call    memset_0
0x180008c37  mov     r12d, r13d
0x180008c3a  test    edi, edi
0x180008c3c  jz      loc_180008DAA
0x180008c42  test    ebx, ebx
0x180008c44  jnz     loc_180008E07
0x180008c4a  lea     r8d, [rbx+4]
0x180008c4e  lea     rdx, [rbp+57h+var_80]
0x180008c52  lea     rcx, [rbp+57h+var_78]
0x180008c56  call    cs:__imp_DiscpAlignDataStruct
0x180008c5c  mov     ebx, eax
0x180008c5e  test    eax, eax
0x180008c60  jnz     loc_180008D9A
0x180008c66  cmp     [rbp+57h+var_80], 4
0x180008c6a  jb      loc_180008DFF
0x180008c70  mov     rax, [rbp+57h+var_78]
0x180008c74  mov     esi, [rax]
0x180008c76  add     [rbp+57h+var_78], 4
0x180008c7b  add     [rbp+57h+var_80], 0FFFFFFFCh
0x180008c7f  test    esi, esi
0x180008c81  jz      loc_180008DFF
0x180008c87  imul    rcx, rsi, 402h
0x180008c8e  mov     eax, 0FFFFFFFFh
0x180008c93  cmp     rcx, rax
0x180008c96  ja      loc_180008DFF
0x180008c9c  add     ecx, 8
0x180008c9f  cmp     ecx, 8
0x180008ca2  jb      loc_180008DFF
0x180008ca8  call    cs:__imp_DiscpAllocMemory
0x180008cae  mov     r15, rax
0x180008cb1  test    rax, rax
0x180008cb4  jz      loc_180008DF1
0x180008cba  mov     ecx, r12d
0x180008cbd  mov     [r14+rcx*8], rax
0x180008cc1  mov     [rax], esi
0x180008cc3  mov     [rax+4], r13b
0x180008cc7  test    esi, esi
0x180008cc9  jz      loc_180008D97
0x180008ccf  mov     ebx, r13d
0x180008cd2  test    ebx, ebx
0x180008cd4  jnz     loc_180008D97
0x180008cda  lea     r8d, [rbx+4]
0x180008cde  lea     rdx, [rbp+57h+var_80]
0x180008ce2  lea     rcx, [rbp+57h+var_78]
0x180008ce6  call    cs:__imp_DiscpAlignDataStruct
0x180008cec  test    eax, eax
0x180008cee  jnz     loc_180008DFF
0x180008cf4  cmp     [rbp+57h+var_80], 2
0x180008cf8  jb      loc_180008DFF
0x180008cfe  mov     eax, r13d
0x180008d01  lea     rdx, [rbp+57h+var_80]
0x180008d05  imul    rbx, rax, 402h
0x180008d0c  mov     rax, [rbp+57h+var_78]
0x180008d10  mov     r8d, 4
0x180008d16  add     rbx, 8
0x180008d1a  add     rbx, r15
0x180008d1d  movzx   ecx, word ptr [rax]
0x180008d20  mov     [rbx+400h], cx
0x180008d27  lea     rcx, [rbp+57h+var_78]
0x180008d2b  add     [rbp+57h+var_78], 2
0x180008d30  add     [rbp+57h+var_80], 0FFFFFFFEh
0x180008d34  call    cs:__imp_DiscpAlignDataStruct
0x180008d3a  test    eax, eax
0x180008d3c  jnz     loc_180008DFF
0x180008d42  lea     rax, [rbx+200h]
0x180008d49  mov     r9d, 100h
0x180008d4f  lea     r8, [rbp+57h+var_80]
0x180008d53  mov     [rbp+57h+var_68], rax
0x180008d57  lea     rdx, [rbp+57h+var_78]
0x180008d5b  lea     rcx, [rbp+57h+var_68]
0x180008d5f  call    DiscpGetIPAddressFromDataBlock
0x180008d64  lea     rax, [rbp+57h+var_80]
0x180008d68  mov     [rbp+57h+var_68], rbx
0x180008d6c  mov     r9d, 100h
0x180008d72  mov     qword ptr [rsp+0E0h+var_C0], rax
0x180008d77  lea     r8, [rbp+57h+var_78]
0x180008d7b  lea     rdx, [rbp+57h+var_7C]
0x180008d7f  lea     rcx, [rbp+57h+var_68]
0x180008d83  call    cs:__imp_DiscpCopyString
0x180008d89  inc     r13d
0x180008d8c  mov     ebx, eax
0x180008d8e  cmp     r13d, esi
0x180008d91  jb      loc_180008CD2
0x180008d97  xor     r13d, r13d
0x180008d9a  inc     r12d
0x180008d9d  cmp     r12d, edi
0x180008da0  jb      loc_180008C42
0x180008da6  test    ebx, ebx
0x180008da8  jnz     short loc_180008E07
0x180008daa  mov     rax, [rbp+57h+arg_18]
0x180008dae  xor     r9d, r9d
0x180008db1  mov     r8, [rbp+57h+var_50]
0x180008db5  mov     rdx, [rbp+57h+var_60]
0x180008db9  mov     rcx, [rbp+57h+var_70]
0x180008dbd  mov     [rsp+50h], rax
0x180008dc2  mov     rax, [rbp+57h+arg_10]
0x180008dc6  mov     dword ptr [rsp+0E0h+var_98], 5
0x180008dce  mov     eax, [rax+20h]
0x180008dd1  mov     [rsp+0E0h+var_A0], eax
0x180008dd5  mov     qword ptr [rsp+0E0h+var_A8], r14
0x180008dda  mov     dword ptr [rsp+0E0h+var_B0], edi
0x180008dde  mov     [rsp+0E0h+var_B8], r13d
0x180008de3  mov     qword ptr [rsp+0E0h+var_C0], r13
0x180008de8  call    DiscpCreateTarget
0x180008ded  mov     ebx, eax
0x180008def  jmp     short loc_180008E07
0x180008df1  mov     ebx, 8
0x180008df6  jmp     short loc_180008D9A
0x180008df8  mov     ebx, 8
0x180008dfd  jmp     short loc_180008E07
0x180008dff  mov     ebx, 0EFFF0019h
0x180008e04  xor     r13d, r13d
0x180008e07  mov     rcx, [rbp+57h+var_70]
0x180008e0b  test    rcx, rcx
0x180008e0e  jz      short loc_180008E16
0x180008e10  call    cs:__imp_DiscpFreeMemory
0x180008e16  mov     rcx, [rbp+57h+var_60]
0x180008e1a  test    rcx, rcx
0x180008e1d  jz      short loc_180008E25
0x180008e1f  call    cs:__imp_DiscpFreeMemory
0x180008e25  test    r14, r14
0x180008e28  jz      short loc_180008E51
0x180008e2a  mov     esi, r13d
0x180008e2d  test    edi, edi
0x180008e2f  jz      short loc_180008E48
0x180008e31  mov     eax, esi
0x180008e33  mov     rcx, [r14+rax*8]
0x180008e37  test    rcx, rcx
0x180008e3a  jz      short loc_180008E42
0x180008e3c  call    cs:__imp_DiscpFreeMemory
0x180008e42  inc     esi
0x180008e44  cmp     esi, edi
0x180008e46  jb      short loc_180008E31
0x180008e48  mov     rcx, r14
0x180008e4b  call    cs:__imp_DiscpFreeMemory
0x180008e51  mov     rcx, [rbp+57h+arg_0]
0x180008e55  mov     rax, [rbp+57h+var_78]
0x180008e59  mov     [rcx], rax
0x180008e5c  mov     eax, [rbp+57h+var_80]
0x180008e5f  mov     rcx, [rbp+57h+arg_8]
0x180008e63  mov     [rcx], eax
0x180008e65  mov     eax, ebx
0x180008e67  add     rsp, 0A8h
0x180008e6e  pop     r15
0x180008e70  pop     r14
0x180008e72  pop     r13
0x180008e74  pop     r12
0x180008e76  pop     rdi
0x180008e77  pop     rsi
0x180008e78  pop     rbx
0x180008e79  pop     rbp
0x180008e7a  retn
```
