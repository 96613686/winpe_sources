# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x180003ef0`
- end: `0x180004139`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `585`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180002767`
- `0x180003ccc`
- `0x180003ef0`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!fwrite` at `0x18000409d`
- `msvcrt!fwrite` at `0x18000409d`
- `msvcrt!fputc` at `0x180003fbd`
- `msvcrt!fputc` at `0x1800040ed`
- `msvcrt!fputc` at `0x180003fbd`
- `msvcrt!fputc` at `0x1800040ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v4; // ebx
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  _QWORD *v10; // rdx
  __int64 v11; // rcx
  char *p_Buffer; // rdx
  char *v13; // rdx
  void *v14; // r8
  int v15; // eax
  int v16; // eax
  _BYTE *v17; // rax
  signed __int64 v18; // r15
  const void *v19; // rcx
  char v20; // [rsp+58h] [rbp-19h] BYREF
  char v21[7]; // [rsp+59h] [rbp-18h] BYREF
  _BYTE *v22; // [rsp+60h] [rbp-11h] BYREF
  _QWORD v23[2]; // [rsp+68h] [rbp-9h] BYREF
  void *Buffer; // [rsp+78h] [rbp+7h] BYREF
  char v25; // [rsp+80h] [rbp+Fh]
  unsigned __int64 v26; // [rsp+88h] [rbp+17h]
  unsigned __int64 v27; // [rsp+90h] [rbp+1Fh]

  v23[1] = -2;
  v4 = -1;
  if ( a2 == -1 )
    return 0;
  v6 = *(_QWORD **)(a1 + 64);
  if ( *v6 && (v7 = *(int **)(a1 + 88), *v6 < (unsigned __int64)(*v6 + *v7)) )
  {
    --*v7;
    v8 = *(_QWORD **)(a1 + 64);
    v9 = (_BYTE *)(*v8)++;
    *v9 = a2;
    return a2;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 144) )
    {
      v10 = *(_QWORD **)(a1 + 24);
      if ( *v10 == a1 + 128 )
      {
        v11 = *(_QWORD *)(a1 + 112);
        *v10 = *(_QWORD *)(a1 + 104);
        **(_QWORD **)(a1 + 56) = v11;
        **(_DWORD **)(a1 + 80) = 0;
      }
      if ( *(_QWORD *)(a1 + 120) )
      {
        v20 = a2;
        v23[0] = 0;
        v22 = 0;
        v27 = 15;
        Buffer = 0;
        v26 = 8;
        v25 = 0;
        while ( 1 )
        {
          p_Buffer = (char *)&Buffer;
          if ( v27 >= 0x10 )
            p_Buffer = (char *)Buffer;
          v13 = &p_Buffer[v26];
          v14 = &Buffer;
          if ( v27 >= 0x10 )
            v14 = Buffer;
          v15 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, char *, _QWORD *, void *, char *, _BYTE **))(**(_QWORD **)(a1 + 120) + 56LL))(
                  *(_QWORD *)(a1 + 120),
                  a1 + 132,
                  &v20,
                  v21,
                  v23,
                  v14,
                  v13,
                  &v22);
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( v16 )
              break;
          }
          v17 = &Buffer;
          if ( v27 >= 0x10 )
            v17 = Buffer;
          v18 = v22 - v17;
          if ( v22 != v17 )
          {
            v19 = &Buffer;
            if ( v27 >= 0x10 )
              v19 = Buffer;
            if ( v18 != fwrite(v19, 1u, v22 - v17, *(FILE **)(a1 + 144)) )
              goto LABEL_35;
          }
          *(_BYTE *)(a1 + 129) = 1;
          if ( (char *)v23[0] != &v20 )
          {
            v4 = a2;
            goto LABEL_35;
          }
          if ( !v18 )
          {
            if ( v26 >= 0x20 )
              goto LABEL_35;
            std::string::append(&Buffer, 8, 0);
          }
        }
        if ( v16 == 2 && fputc(v20, *(FILE **)(a1 + 144)) != -1 )
          v4 = a2;
LABEL_35:
        if ( v27 >= 0x10 )
          operator delete(Buffer);
      }
      else if ( fputc((char)a2, *(FILE **)(a1 + 144)) != -1 )
      {
        return a2;
      }
    }
    return v4;
  }
}

```

## disassembly

```asm
0x180003ef0  mov     rax, rsp
0x180003ef3  push    rbp
0x180003ef4  push    r12
0x180003ef6  push    r13
0x180003ef8  push    r14
0x180003efa  push    r15
0x180003efc  lea     rbp, [rax-5Fh]
0x180003f00  sub     rsp, 0A0h
0x180003f07  mov     [rbp+57h+var_58], 0FFFFFFFFFFFFFFFEh
0x180003f0f  mov     [rax+18h], rbx
0x180003f13  mov     [rax+20h], rdi
0x180003f17  mov     rax, cs:__security_cookie
0x180003f1e  xor     rax, rsp
0x180003f21  mov     [rbp+57h+var_30], rax
0x180003f25  mov     r14d, edx
0x180003f28  mov     rdi, rcx
0x180003f2b  or      ebx, 0FFFFFFFFh
0x180003f2e  cmp     edx, ebx
0x180003f30  jnz     short loc_180003F39
0x180003f32  xor     eax, eax
0x180003f34  jmp     loc_180004110
0x180003f39  mov     rax, [rcx+40h]
0x180003f3d  cmp     qword ptr [rax], 0
0x180003f41  jz      short loc_180003F74
0x180003f43  mov     rdx, [rcx+58h]
0x180003f47  movsxd  r8, dword ptr [rdx]
0x180003f4a  mov     rcx, r8
0x180003f4d  add     rcx, [rax]
0x180003f50  cmp     [rax], rcx
0x180003f53  jnb     short loc_180003F74
0x180003f55  lea     ecx, [r8-1]
0x180003f59  mov     [rdx], ecx
0x180003f5b  mov     rdx, [rdi+40h]
0x180003f5f  mov     r8, [rdx]
0x180003f62  lea     rcx, [r8+1]
0x180003f66  mov     [rdx], rcx
0x180003f69  mov     [r8], r14b
0x180003f6c  mov     eax, r14d
0x180003f6f  jmp     loc_180004110
0x180003f74  cmp     qword ptr [rdi+90h], 0
0x180003f7c  jz      loc_18000410E
0x180003f82  mov     rdx, [rdi+18h]
0x180003f86  lea     rax, [rdi+80h]
0x180003f8d  cmp     [rdx], rax
0x180003f90  jnz     short loc_180003FAB
0x180003f92  mov     rcx, [rdi+70h]
0x180003f96  mov     rax, [rdi+68h]
0x180003f9a  mov     [rdx], rax
0x180003f9d  mov     rax, [rdi+38h]
0x180003fa1  mov     [rax], rcx
0x180003fa4  mov     rax, [rdi+50h]
0x180003fa8  and     dword ptr [rax], 0
0x180003fab  cmp     qword ptr [rdi+78h], 0
0x180003fb0  jnz     short loc_180003FCE
0x180003fb2  movsx   ecx, r14b; Character
0x180003fb6  mov     rdx, [rdi+90h]; Stream
0x180003fbd  call    cs:__imp_fputc
0x180003fc3  cmp     eax, ebx
0x180003fc5  cmovnz  ebx, r14d
0x180003fc9  jmp     loc_18000410E
0x180003fce  mov     [rbp+57h+var_70], r14b
0x180003fd2  and     [rbp+57h+var_60], 0
0x180003fd7  and     [rbp+57h+var_68], 0
0x180003fdc  mov     ecx, 0Fh
0x180003fe1  mov     [rbp+57h+var_38], rcx
0x180003fe5  mov     byte ptr [rbp+57h+Buffer], 0
0x180003fe9  xor     eax, eax
0x180003feb  mov     [rbp+57h+Buffer], rax
0x180003fef  lea     rax, [rbp+57h+var_48]
0x180003ff3  lea     r13d, [rcx-7]
0x180003ff7  mov     [rbp+57h+var_40], r13
0x180003ffb  mov     byte ptr [rax], 0
0x180003ffe  mov     r10, [rdi+78h]
0x180004002  lea     rdx, [rbp+57h+Buffer]
0x180004006  cmp     [rbp+57h+var_38], 10h
0x18000400b  cmovnb  rdx, [rbp+57h+Buffer]
0x180004010  add     rdx, [rbp+57h+var_40]
0x180004014  lea     r8, [rbp+57h+Buffer]
0x180004018  cmp     [rbp+57h+var_38], 10h
0x18000401d  cmovnb  r8, [rbp+57h+Buffer]
0x180004022  mov     rax, [r10]
0x180004025  lea     rcx, [rbp+57h+var_68]
0x180004029  mov     [rsp+0C0h+var_88], rcx
0x18000402e  mov     [rsp+0C0h+var_90], rdx
0x180004033  mov     [rsp+0C0h+var_98], r8
0x180004038  lea     rcx, [rbp+57h+var_60]
0x18000403c  mov     [rsp+0C0h+var_A0], rcx
0x180004041  lea     r9, [rbp+57h+var_6F]
0x180004045  lea     r8, [rbp+57h+var_70]
0x180004049  lea     rdx, [rdi+84h]
0x180004050  mov     rcx, r10
0x180004053  mov     rax, [rax+38h]
0x180004057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000405c  test    eax, eax
0x18000405e  jz      short loc_180004065
0x180004060  sub     eax, 1
0x180004063  jnz     short loc_1800040DD
0x180004065  lea     rax, [rbp+57h+Buffer]
0x180004069  mov     r9, [rbp+57h+Buffer]
0x18000406d  mov     r11, [rbp+57h+var_38]
0x180004071  cmp     r11, 10h
0x180004075  cmovnb  rax, r9
0x180004079  mov     r15, [rbp+57h+var_68]
0x18000407d  sub     r15, rax
0x180004080  jz      short loc_1800040A8
0x180004082  lea     rcx, [rbp+57h+Buffer]
0x180004086  cmp     r11, 10h
0x18000408a  cmovnb  rcx, r9; Buffer
0x18000408e  mov     r9, [rdi+90h]; Stream
0x180004095  mov     r8, r15; ElementCount
0x180004098  mov     edx, 1; ElementSize
0x18000409d  call    cs:__imp_fwrite
0x1800040a3  cmp     r15, rax
0x1800040a6  jnz     short loc_1800040FE
0x1800040a8  mov     byte ptr [rdi+81h], 1
0x1800040af  lea     rax, [rbp+57h+var_70]
0x1800040b3  cmp     [rbp+57h+var_60], rax
0x1800040b7  jnz     short loc_1800040FB
0x1800040b9  test    r15, r15
0x1800040bc  jnz     loc_180003FFE
0x1800040c2  cmp     [rbp+57h+var_40], 20h ; ' '
0x1800040c7  jnb     short loc_1800040FE
0x1800040c9  xor     r8d, r8d
0x1800040cc  mov     rdx, r13
0x1800040cf  lea     rcx, [rbp+57h+Buffer]
0x1800040d3  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z; std::string::append(unsigned __int64,char)
0x1800040d8  jmp     loc_180003FFE
0x1800040dd  cmp     eax, 2
0x1800040e0  jnz     short loc_1800040FE
0x1800040e2  movsx   ecx, [rbp+57h+var_70]; Character
0x1800040e6  mov     rdx, [rdi+90h]; Stream
0x1800040ed  call    cs:__imp_fputc
0x1800040f3  cmp     eax, ebx
0x1800040f5  cmovnz  ebx, r14d
0x1800040f9  jmp     short loc_1800040FE
0x1800040fb  mov     ebx, r14d
0x1800040fe  cmp     [rbp+57h+var_38], 10h
0x180004103  jb      short loc_18000410E
0x180004105  mov     rcx, [rbp+57h+Buffer]; void *
0x180004109  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x18000410e  mov     eax, ebx
0x180004110  mov     rcx, [rbp+57h+var_30]
0x180004114  xor     rcx, rsp; StackCookie
0x180004117  call    __security_check_cookie
0x18000411c  lea     r11, [rsp+0C0h+var_20]
0x180004124  mov     rbx, [r11+40h]
0x180004128  mov     rdi, [r11+48h]
0x18000412c  mov     rsp, r11
0x18000412f  pop     r15
0x180004131  pop     r14
0x180004133  pop     r13
0x180004135  pop     r12
0x180004137  pop     rbp
0x180004138  retn
```
