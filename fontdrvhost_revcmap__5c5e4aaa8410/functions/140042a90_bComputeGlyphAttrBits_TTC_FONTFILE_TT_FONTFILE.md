# bComputeGlyphAttrBits(_TTC_FONTFILE *,_TT_FONTFILE *)

- ea: `0x140042a90`
- end: `0x140042d0b`
- name: `?bComputeGlyphAttrBits@@YAHPEAU_TTC_FONTFILE@@PEAU_TT_FONTFILE@@@Z`
- size: `635`
- prototype: `__int64 __fastcall(struct _TTC_FONTFILE *, struct _TT_FONTFILE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140007104`

## callees

- `0x140042a90`
- `0x14007680c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x140042ac7`
- `KERNEL32!GlobalAlloc` at `0x140042ac7`
- `KERNEL32!WideCharToMultiByte` at `0x140042ccc`
- `KERNEL32!WideCharToMultiByte` at `0x140042ccc`

## pseudocode

```c
__int64 __fastcall bComputeGlyphAttrBits(struct _TTC_FONTFILE *a1, struct _TT_FONTFILE *a2)
{
  __int64 v2; // rdi
  struct _TTC_FONTFILE *v3; // rsi
  unsigned int v4; // ebp
  __int64 result; // rax
  unsigned int *v6; // rbx
  __int64 v7; // r15
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned __int16 *v11; // rbp
  unsigned __int64 v12; // r14
  __int64 v13; // rdx
  unsigned int *v14; // rsi
  __int64 v15; // r13
  unsigned int v16; // edi
  _DWORD *v17; // r12
  unsigned int j; // eax
  unsigned int v19; // eax
  int i; // [rsp+40h] [rbp-68h]
  unsigned int v21; // [rsp+44h] [rbp-64h]
  __int64 v22; // [rsp+48h] [rbp-60h]
  unsigned __int64 v23; // [rsp+50h] [rbp-58h]
  WCHAR WideCharStr; // [rsp+C0h] [rbp+18h] BYREF
  CHAR MultiByteStr; // [rsp+C8h] [rbp+20h] BYREF

  v2 = *((_QWORD *)a1 + 6);
  v3 = a1;
  v4 = ((unsigned int)(*(_DWORD *)(v2 + 640) + 7) >> 3) + 12;
  result = (__int64)GlobalAlloc(0, v4);
  v6 = (unsigned int *)result;
  if ( result )
  {
    memset_0((void *)result, 0, v4);
    *v6 = v4;
    v7 = 0;
    v8 = *(_DWORD *)(v2 + 640);
    v6[2] = 1;
    v6[1] = v8;
    for ( i = 0; (unsigned int)v7 < *((_DWORD *)v3 + 3); i = v7 )
    {
      if ( *((_DWORD *)v3 + 4 * (unsigned int)v7 + 11) == 1 )
      {
        v9 = *((_QWORD *)v3 + 2 * v7 + 6);
        v10 = *(_QWORD *)(v9 + 88);
        v11 = (unsigned __int16 *)(v10 + 16);
        v12 = v10 + 16 + 16LL * *(unsigned int *)(v10 + 12);
        v23 = v12;
        if ( v10 + 16 < v12 )
        {
          v13 = *(_QWORD *)(v9 + 96);
          v14 = 0;
          v22 = v13;
          v15 = (v13 + 16) & -(__int64)(v13 != 0);
          do
          {
            v16 = *v11;
            if ( v13 )
              v14 = *(unsigned int **)(v15 + 8);
            if ( *v11 != 0xFFFF )
            {
              v17 = (_DWORD *)*((_QWORD *)v11 + 1);
              v21 = v16 + v11[1] - 1;
              if ( v16 <= v21 )
              {
                do
                {
                  WideCharStr = v16;
                  if ( (unsigned __int16)v16 >= (unsigned __int16)VerticalUnicodes
                    && (unsigned __int16)v16 <= (unsigned __int16)word_1400B4356 )
                  {
                    for ( j = 0; j < 0xE; ++j )
                    {
                      if ( (unsigned __int16)v16 >= *((_WORD *)&VerticalUnicodes + 2 * (int)j)
                        && (unsigned __int16)v16 <= (unsigned __int16)word_1400B4322[2 * j] )
                      {
                        goto LABEL_21;
                      }
                    }
                  }
                  if ( WideCharToMultiByte(*((_DWORD *)a2 + 94), 0, &WideCharStr, 1, &MultiByteStr, 2, 0, 0) > 1 )
                  {
LABEL_21:
                    if ( *v17 < v6[1] )
                    {
                      *((_BYTE *)v6 + ((unsigned __int64)(unsigned int)*v17 >> 3) + 12) |= *((_BYTE *)&glyphBits
                                                                                           + (*v17 & 7));
                      if ( v22 )
                      {
                        v19 = *v14;
                        if ( *v17 != *v14 && v19 < v6[1] )
                          *((_BYTE *)v6 + ((unsigned __int64)*v14 >> 3) + 12) |= *((_BYTE *)&glyphBits + (v19 & 7));
                      }
                    }
                  }
                  ++v17;
                  ++v16;
                  ++v14;
                }
                while ( v16 <= v21 );
                v12 = v23;
                v13 = v22;
              }
            }
            v11 += 8;
            v15 += 16;
          }
          while ( (unsigned __int64)v11 < v12 );
          v3 = a1;
          LODWORD(v7) = i;
        }
      }
      v7 = (unsigned int)(v7 + 1);
    }
    *((_QWORD *)v3 + 4) = v6;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x140042a90  mov     [rsp+arg_8], rdx
0x140042a95  mov     [rsp+arg_0], rcx
0x140042a9a  push    rbx
0x140042a9b  push    rbp
0x140042a9c  push    rsi
0x140042a9d  push    rdi
0x140042a9e  push    r12
0x140042aa0  push    r13
0x140042aa2  push    r14
0x140042aa4  push    r15
0x140042aa6  sub     rsp, 68h
0x140042aaa  mov     rdi, [rcx+30h]
0x140042aae  mov     rsi, rcx
0x140042ab1  xor     ecx, ecx; uFlags
0x140042ab3  mov     ebp, [rdi+280h]
0x140042ab9  add     ebp, 7
0x140042abc  shr     ebp, 3
0x140042abf  add     ebp, 0Ch
0x140042ac2  mov     edx, ebp; dwBytes
0x140042ac4  mov     r14d, ebp
0x140042ac7  call    cs:__imp_GlobalAlloc
0x140042acd  mov     rbx, rax
0x140042ad0  test    rax, rax
0x140042ad3  jz      loc_140042D06
0x140042ad9  mov     r8d, r14d; Size
0x140042adc  xor     edx, edx; Val
0x140042ade  mov     rcx, rax; void *
0x140042ae1  call    memset_0
0x140042ae6  mov     [rbx], ebp
0x140042ae8  xor     r15d, r15d
0x140042aeb  mov     eax, [rdi+280h]
0x140042af1  mov     r8d, 1
0x140042af7  mov     [rbx+8], r8d
0x140042afb  mov     [rbx+4], eax
0x140042afe  mov     [rsp+0A8h+var_68], r15d
0x140042b03  cmp     [rsi+0Ch], r15d
0x140042b07  jbe     loc_140042BAD
0x140042b0d  lea     r9, cs:140000000h
0x140042b14  mov     eax, r15d
0x140042b17  add     rax, rax
0x140042b1a  cmp     [rsi+rax*8+2Ch], r8d
0x140042b1f  jnz     short loc_140042B9B
0x140042b21  lea     rax, [r15+3]
0x140042b25  add     rax, rax
0x140042b28  mov     rcx, [rsi+rax*8]
0x140042b2c  mov     rax, [rcx+58h]
0x140042b30  mov     r14d, [rax+0Ch]
0x140042b34  lea     rbp, [rax+10h]
0x140042b38  shl     r14, 4
0x140042b3c  add     r14, rbp
0x140042b3f  mov     [rsp+0A8h+var_58], r14
0x140042b44  cmp     rbp, r14
0x140042b47  jnb     short loc_140042B9B
0x140042b49  mov     rdx, [rcx+60h]
0x140042b4d  xor     esi, esi
0x140042b4f  mov     r15, [rsp+0A8h+arg_8]
0x140042b57  mov     rax, rdx
0x140042b5a  neg     rax
0x140042b5d  mov     [rsp+0A8h+var_60], rdx
0x140042b62  sbb     r13, r13
0x140042b65  lea     rcx, [rdx+10h]
0x140042b69  and     r13, rcx
0x140042b6c  movzx   edi, word ptr [rbp+0]
0x140042b70  test    rdx, rdx
0x140042b73  jz      short loc_140042B79
0x140042b75  mov     rsi, [r13+8]
0x140042b79  cmp     edi, 0FFFFh
0x140042b7f  jb      short loc_140042BC5
0x140042b81  add     rbp, 10h
0x140042b85  add     r13, 10h
0x140042b89  cmp     rbp, r14
0x140042b8c  jb      short loc_140042B6C
0x140042b8e  mov     rsi, [rsp+0A8h+arg_0]
0x140042b96  mov     r15d, [rsp+0A8h+var_68]
0x140042b9b  add     r15d, r8d
0x140042b9e  mov     [rsp+0A8h+var_68], r15d
0x140042ba3  cmp     r15d, [rsi+0Ch]
0x140042ba7  jb      loc_140042B14
0x140042bad  mov     [rsi+20h], rbx
0x140042bb1  mov     eax, r8d
0x140042bb4  add     rsp, 68h
0x140042bb8  pop     r15
0x140042bba  pop     r14
0x140042bbc  pop     r13
0x140042bbe  pop     r12
0x140042bc0  pop     rdi
0x140042bc1  pop     rsi
0x140042bc2  pop     rbp
0x140042bc3  pop     rbx
0x140042bc4  retn
0x140042bc5  movzx   eax, word ptr [rbp+2]
0x140042bc9  mov     r12, [rbp+8]
0x140042bcd  dec     eax
0x140042bcf  add     eax, edi
0x140042bd1  mov     [rsp+0A8h+var_64], eax
0x140042bd5  cmp     edi, eax
0x140042bd7  ja      short loc_140042B81
0x140042bd9  mov     r14, [rsp+0A8h+var_60]
0x140042bde  cmp     di, cs:?VerticalUnicodes@@3PAU_VERTICAL_UNICODE@@A; _VERTICAL_UNICODE near * VerticalUnicodes
0x140042be5  mov     [rsp+0A8h+WideCharStr], di
0x140042bed  jb      loc_140042C91
0x140042bf3  cmp     di, cs:word_1400B4356
0x140042bfa  ja      loc_140042C91
0x140042c00  xor     eax, eax
0x140042c02  cmp     eax, 0Eh
0x140042c05  jnb     loc_140042C91
0x140042c0b  movsxd  rcx, eax
0x140042c0e  cmp     di, rva ?VerticalUnicodes@@3PAU_VERTICAL_UNICODE@@A[r9+rcx*4]; _VERTICAL_UNICODE near * VerticalUnicodes ...
0x140042c17  jb      short loc_140042C24
0x140042c19  cmp     di, rva word_1400B4322[r9+rcx*4]
0x140042c22  jbe     short loc_140042C30
0x140042c24  add     eax, r8d
0x140042c27  jmp     short loc_140042C02
0x140042c29  lea     r9, cs:140000000h
0x140042c30  mov     eax, [r12]
0x140042c34  cmp     eax, [rbx+4]
0x140042c37  jnb     short loc_140042C5F
0x140042c39  mov     ecx, eax
0x140042c3b  and     eax, 7
0x140042c3e  shr     rcx, 3
0x140042c42  mov     al, [rax+r9+9D190h]
0x140042c4a  or      [rcx+rbx+0Ch], al
0x140042c4e  test    r14, r14
0x140042c51  jz      short loc_140042C5F
0x140042c53  mov     eax, [rsi]
0x140042c55  cmp     [r12], eax
0x140042c59  jnz     loc_140042CE2
0x140042c5f  add     r12, 4
0x140042c63  lea     r9, cs:140000000h
0x140042c6a  add     edi, r8d
0x140042c6d  add     rsi, 4
0x140042c71  cmp     edi, [rsp+0A8h+var_64]
0x140042c75  jbe     loc_140042BDE
0x140042c7b  mov     r14, [rsp+0A8h+var_58]
0x140042c80  lea     r9, cs:140000000h
0x140042c87  mov     rdx, [rsp+0A8h+var_60]
0x140042c8c  jmp     loc_140042B81
0x140042c91  mov     ecx, [r15+178h]; CodePage
0x140042c98  lea     rax, [rsp+0A8h+MultiByteStr]
0x140042ca0  mov     [rsp+0A8h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x140042ca9  mov     r9d, r8d; cchWideChar
0x140042cac  mov     [rsp+0A8h+lpDefaultChar], 0; lpDefaultChar
0x140042cb5  lea     r8, [rsp+0A8h+WideCharStr]; lpWideCharStr
0x140042cbd  mov     [rsp+0A8h+cbMultiByte], 2; cbMultiByte
0x140042cc5  xor     edx, edx; dwFlags
0x140042cc7  mov     [rsp+0A8h+lpMultiByteStr], rax; lpMultiByteStr
0x140042ccc  call    cs:__imp_WideCharToMultiByte
0x140042cd2  mov     r8d, 1
0x140042cd8  cmp     eax, r8d
0x140042cdb  jle     short loc_140042C5F
0x140042cdd  jmp     loc_140042C29
0x140042ce2  cmp     eax, [rbx+4]
0x140042ce5  jnb     loc_140042C5F
0x140042ceb  mov     rcx, rax
0x140042cee  and     eax, 7
0x140042cf1  shr     rcx, 3
0x140042cf5  mov     al, [rax+r9+9D190h]
0x140042cfd  or      [rcx+rbx+0Ch], al
0x140042d01  jmp     loc_140042C5F
0x140042d06  jmp     loc_140042BB4
```
