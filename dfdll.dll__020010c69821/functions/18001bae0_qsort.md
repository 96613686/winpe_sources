# qsort

- ea: `0x18001bae0`
- end: `0x18001be14`
- name: `qsort`
- size: `820`
- prototype: `void __cdecl(void *Base, size_t NumOfElements, size_t SizeOfElements, _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180019980`

## callees

- `0x180012bd0`
- `0x180012bf0`
- `0x180019450`
- `0x180019570`
- `0x18001ba10`
- `0x18001bae0`

## pseudocode

```c
void __cdecl qsort(
        void *Base,
        size_t NumOfElements,
        size_t SizeOfElements,
        _CoreCrtNonSecureSearchSortCompareFunction CompareFunction)
{
  _BYTE *v6; // r12
  char *v7; // r15
  __int64 v8; // r13
  size_t v9; // rsi
  char *v10; // rsi
  size_t v11; // r8
  char *v12; // rdx
  char *v13; // r9
  char v14; // cl
  size_t v15; // r8
  char *v16; // rdx
  __int64 v17; // r9
  char v18; // cl
  size_t v19; // r8
  char *v20; // rdx
  signed __int64 v21; // r9
  char v22; // cl
  unsigned __int64 v23; // rbx
  char *v24; // rdi
  char *v25; // rdx
  unsigned __int64 v26; // r9
  char v27; // cl
  char *v28; // rdi
  _QWORD v29[124]; // [rsp+20h] [rbp-438h]

  v6 = Base;
  if ( (Base || !NumOfElements) && SizeOfElements && CompareFunction )
  {
    if ( NumOfElements >= 2 )
    {
      v7 = (char *)Base + SizeOfElements * (NumOfElements - 1);
      v8 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          v9 = (v7 - v6) / SizeOfElements + 1;
          if ( v9 <= 8 )
          {
            shortsort(v6, v7, SizeOfElements, CompareFunction);
            goto LABEL_10;
          }
          v10 = &v6[SizeOfElements * (v9 >> 1)];
          if ( ((int (__fastcall *)(_BYTE *, char *))CompareFunction)(v6, v10) > 0 )
          {
            v11 = SizeOfElements;
            v12 = v10;
            if ( v6 != v10 )
            {
              v13 = (char *)(v6 - v10);
              do
              {
                v14 = v12[(_QWORD)v13];
                v12[(_QWORD)v13] = *v12;
                *v12++ = v14;
                --v11;
              }
              while ( v11 );
            }
          }
          if ( ((int (__fastcall *)(_BYTE *, char *, size_t))CompareFunction)(v6, v7, v11) > 0 )
          {
            v15 = SizeOfElements;
            v16 = v7;
            if ( v6 != v7 )
            {
              v17 = v6 - v7;
              do
              {
                v18 = v16[v17];
                v16[v17] = *v16;
                *v16++ = v18;
                --v15;
              }
              while ( v15 );
            }
          }
          if ( ((int (__fastcall *)(char *, char *, size_t))CompareFunction)(v10, v7, v15) > 0 )
          {
            v19 = SizeOfElements;
            v20 = v7;
            if ( v10 != v7 )
            {
              v21 = v10 - v7;
              do
              {
                v22 = v20[v21];
                v20[v21] = *v20;
                *v20++ = v22;
                --v19;
              }
              while ( v19 );
            }
          }
          v23 = (unsigned __int64)v6;
          v24 = v7;
          while ( 1 )
          {
            if ( (unsigned __int64)v10 > v23 )
            {
              while ( 1 )
              {
                v23 += SizeOfElements;
                if ( v23 >= (unsigned __int64)v10 )
                  break;
                if ( ((int (__fastcall *)(unsigned __int64, char *, size_t))CompareFunction)(v23, v10, v19) > 0 )
                {
                  if ( (unsigned __int64)v10 > v23 )
                    goto LABEL_31;
                  goto LABEL_29;
                }
              }
            }
            do
LABEL_29:
              v23 += SizeOfElements;
            while ( v23 <= (unsigned __int64)v7
                 && ((int (__fastcall *)(unsigned __int64, char *, size_t))CompareFunction)(v23, v10, v19) <= 0 );
            do
LABEL_31:
              v24 -= SizeOfElements;
            while ( v24 > v10 && ((int (__fastcall *)(char *, char *))CompareFunction)(v24, v10) > 0 );
            if ( (unsigned __int64)v24 < v23 )
              break;
            v19 = SizeOfElements;
            v25 = v24;
            if ( (char *)v23 != v24 )
            {
              v26 = v23 - (_QWORD)v24;
              do
              {
                v27 = v25[v26];
                v25[v26] = *v25;
                *v25++ = v27;
                --v19;
              }
              while ( v19 );
            }
            if ( v10 == v24 )
              v10 = (char *)v23;
          }
          v28 = &v24[SizeOfElements];
          if ( v10 < v28 )
          {
            while ( 1 )
            {
              v28 -= SizeOfElements;
              if ( v28 <= v10 )
                break;
              if ( ((unsigned int (__fastcall *)(char *, char *))CompareFunction)(v28, v10) )
              {
                if ( v10 < v28 )
                  goto LABEL_45;
                goto LABEL_43;
              }
            }
          }
          do
LABEL_43:
            v28 -= SizeOfElements;
          while ( v28 > v6 && !((unsigned int (__fastcall *)(char *, char *))CompareFunction)(v28, v10) );
LABEL_45:
          if ( v28 - v6 >= (__int64)&v7[-v23] )
            break;
          if ( v23 < (unsigned __int64)v7 )
          {
            v29[v8] = v23;
            v29[v8++ + 62] = v7;
          }
          if ( v6 >= v28 )
          {
LABEL_10:
            if ( --v8 < 0 )
              return;
            v6 = (_BYTE *)v29[v8];
            v7 = (char *)v29[v8 + 62];
          }
          else
          {
            v7 = v28;
          }
        }
        if ( v6 < v28 )
        {
          v29[v8] = v6;
          v29[v8++ + 62] = v28;
        }
        if ( v23 >= (unsigned __int64)v7 )
          goto LABEL_10;
        v6 = (_BYTE *)v23;
      }
    }
  }
  else
  {
    *errno() = 22;
    invalid_parameter_noinfo();
  }
}

```

## disassembly

```asm
0x18001bae0  push    rbp
0x18001bae2  push    r12
0x18001bae4  push    r14
0x18001bae6  sub     rsp, 440h
0x18001baed  mov     rax, cs:__security_cookie
0x18001baf4  xor     rax, rsp
0x18001baf7  mov     [rsp+458h+var_58], rax
0x18001baff  mov     r14, r9
0x18001bb02  mov     rbp, r8
0x18001bb05  mov     r12, rcx
0x18001bb08  test    rcx, rcx
0x18001bb0b  jnz     short loc_18001BB27
0x18001bb0d  test    rdx, rdx
0x18001bb10  jz      short loc_18001BB27
0x18001bb12  call    _errno
0x18001bb17  mov     dword ptr [rax], 16h
0x18001bb1d  call    _invalid_parameter_noinfo
0x18001bb22  jmp     loc_18001BDF7
0x18001bb27  test    r8, r8
0x18001bb2a  jz      short loc_18001BB12
0x18001bb2c  test    r9, r9
0x18001bb2f  jz      short loc_18001BB12
0x18001bb31  cmp     rdx, 2
0x18001bb35  jb      loc_18001BDF7
0x18001bb3b  mov     [rsp+458h+var_20], rbx
0x18001bb43  mov     [rsp+458h+var_28], rsi
0x18001bb4b  mov     [rsp+458h+var_30], rdi
0x18001bb53  mov     [rsp+458h+var_38], r13
0x18001bb5b  mov     [rsp+458h+var_40], r15
0x18001bb63  lea     r15, [rdx-1]
0x18001bb67  imul    r15, rbp
0x18001bb6b  add     r15, rcx
0x18001bb6e  xor     r13d, r13d
0x18001bb71  xor     edx, edx
0x18001bb73  mov     rax, r15
0x18001bb76  sub     rax, r12
0x18001bb79  div     rbp
0x18001bb7c  lea     rsi, [rax+1]
0x18001bb80  cmp     rsi, 8
0x18001bb84  ja      short loc_18001BBB0
0x18001bb86  mov     r9, r14
0x18001bb89  mov     r8, rbp
0x18001bb8c  mov     rdx, r15
0x18001bb8f  mov     rcx, r12
0x18001bb92  call    shortsort
0x18001bb97  sub     r13, 1
0x18001bb9b  js      loc_18001BDCF
0x18001bba1  mov     r12, [rsp+r13*8+458h+var_438]
0x18001bba6  mov     r15, [rsp+r13*8+458h+var_248]
0x18001bbae  jmp     short $recurse$163
0x18001bbb0  shr     rsi, 1
0x18001bbb3  mov     rcx, r14
0x18001bbb6  imul    rsi, rbp
0x18001bbba  add     rsi, r12
0x18001bbbd  call    cs:__guard_check_icall_fptr
0x18001bbc3  mov     rdx, rsi
0x18001bbc6  mov     rcx, r12
0x18001bbc9  call    r14
0x18001bbcc  test    eax, eax
0x18001bbce  jle     short loc_18001BBF9
0x18001bbd0  mov     r8, rbp
0x18001bbd3  mov     rdx, rsi
0x18001bbd6  cmp     r12, rsi
0x18001bbd9  jz      short loc_18001BBF9
0x18001bbdb  mov     r9, r12
0x18001bbde  sub     r9, rsi
0x18001bbe1  movzx   eax, byte ptr [rdx]
0x18001bbe4  movzx   ecx, byte ptr [r9+rdx]
0x18001bbe9  mov     [r9+rdx], al
0x18001bbed  mov     [rdx], cl
0x18001bbef  lea     rdx, [rdx+1]
0x18001bbf3  sub     r8, 1
0x18001bbf7  jnz     short loc_18001BBE1
0x18001bbf9  mov     rcx, r14
0x18001bbfc  call    cs:__guard_check_icall_fptr
0x18001bc02  mov     rdx, r15
0x18001bc05  mov     rcx, r12
0x18001bc08  call    r14
0x18001bc0b  test    eax, eax
0x18001bc0d  jle     short loc_18001BC38
0x18001bc0f  mov     r8, rbp
0x18001bc12  mov     rdx, r15
0x18001bc15  cmp     r12, r15
0x18001bc18  jz      short loc_18001BC38
0x18001bc1a  mov     r9, r12
0x18001bc1d  sub     r9, r15
0x18001bc20  movzx   eax, byte ptr [rdx]
0x18001bc23  movzx   ecx, byte ptr [r9+rdx]
0x18001bc28  mov     [r9+rdx], al
0x18001bc2c  mov     [rdx], cl
0x18001bc2e  lea     rdx, [rdx+1]
0x18001bc32  sub     r8, 1
0x18001bc36  jnz     short loc_18001BC20
0x18001bc38  mov     rcx, r14
0x18001bc3b  call    cs:__guard_check_icall_fptr
0x18001bc41  mov     rdx, r15
0x18001bc44  mov     rcx, rsi
0x18001bc47  call    r14
0x18001bc4a  test    eax, eax
0x18001bc4c  jle     short loc_18001BC78
0x18001bc4e  mov     r8, rbp
0x18001bc51  mov     rdx, r15
0x18001bc54  cmp     rsi, r15
0x18001bc57  jz      short loc_18001BC78
0x18001bc59  mov     r9, rsi
0x18001bc5c  sub     r9, r15
0x18001bc5f  nop
0x18001bc60  movzx   eax, byte ptr [rdx]
0x18001bc63  movzx   ecx, byte ptr [r9+rdx]
0x18001bc68  mov     [r9+rdx], al
0x18001bc6c  mov     [rdx], cl
0x18001bc6e  lea     rdx, [rdx+1]
0x18001bc72  sub     r8, 1
0x18001bc76  jnz     short loc_18001BC60
0x18001bc78  mov     rbx, r12
0x18001bc7b  mov     rdi, r15
0x18001bc7e  xchg    ax, ax
0x18001bc80  cmp     rsi, rbx
0x18001bc83  jbe     short loc_18001BCA8
0x18001bc85  add     rbx, rbp
0x18001bc88  cmp     rbx, rsi
0x18001bc8b  jnb     short loc_18001BCA8
0x18001bc8d  mov     rcx, r14
0x18001bc90  call    cs:__guard_check_icall_fptr
0x18001bc96  mov     rdx, rsi
0x18001bc99  mov     rcx, rbx
0x18001bc9c  call    r14
0x18001bc9f  test    eax, eax
0x18001bca1  jle     short loc_18001BC85
0x18001bca3  cmp     rsi, rbx
0x18001bca6  ja      short loc_18001BCC6
0x18001bca8  add     rbx, rbp
0x18001bcab  cmp     rbx, r15
0x18001bcae  ja      short loc_18001BCC6
0x18001bcb0  mov     rcx, r14
0x18001bcb3  call    cs:__guard_check_icall_fptr
0x18001bcb9  mov     rdx, rsi
0x18001bcbc  mov     rcx, rbx
0x18001bcbf  call    r14
0x18001bcc2  test    eax, eax
0x18001bcc4  jle     short loc_18001BCA8
0x18001bcc6  sub     rdi, rbp
0x18001bcc9  cmp     rdi, rsi
0x18001bccc  jbe     short loc_18001BCE4
0x18001bcce  mov     rcx, r14
0x18001bcd1  call    cs:__guard_check_icall_fptr
0x18001bcd7  mov     rdx, rsi
0x18001bcda  mov     rcx, rdi
0x18001bcdd  call    r14
0x18001bce0  test    eax, eax
0x18001bce2  jg      short loc_18001BCC6
0x18001bce4  cmp     rdi, rbx
0x18001bce7  jb      short loc_18001BD29
0x18001bce9  mov     r8, rbp
0x18001bcec  mov     rdx, rdi
0x18001bcef  cmp     rbx, rdi
0x18001bcf2  jz      short loc_18001BD18
0x18001bcf4  mov     r9, rbx
0x18001bcf7  sub     r9, rdi
0x18001bcfa  nop     word ptr [rax+rax+00h]
0x18001bd00  movzx   eax, byte ptr [rdx]
0x18001bd03  movzx   ecx, byte ptr [r9+rdx]
0x18001bd08  mov     [r9+rdx], al
0x18001bd0c  mov     [rdx], cl
0x18001bd0e  lea     rdx, [rdx+1]
0x18001bd12  sub     r8, 1
0x18001bd16  jnz     short loc_18001BD00
0x18001bd18  cmp     rsi, rdi
0x18001bd1b  jnz     loc_18001BC80
0x18001bd21  mov     rsi, rbx
0x18001bd24  jmp     loc_18001BC80
0x18001bd29  add     rdi, rbp
0x18001bd2c  cmp     rsi, rdi
0x18001bd2f  jnb     short loc_18001BD54
0x18001bd31  sub     rdi, rbp
0x18001bd34  cmp     rdi, rsi
0x18001bd37  jbe     short loc_18001BD54
0x18001bd39  mov     rcx, r14
0x18001bd3c  call    cs:__guard_check_icall_fptr
0x18001bd42  mov     rdx, rsi
0x18001bd45  mov     rcx, rdi
0x18001bd48  call    r14
0x18001bd4b  test    eax, eax
0x18001bd4d  jz      short loc_18001BD31
0x18001bd4f  cmp     rsi, rdi
0x18001bd52  jb      short loc_18001BD72
0x18001bd54  sub     rdi, rbp
0x18001bd57  cmp     rdi, r12
0x18001bd5a  jbe     short loc_18001BD72
0x18001bd5c  mov     rcx, r14
0x18001bd5f  call    cs:__guard_check_icall_fptr
0x18001bd65  mov     rdx, rsi
0x18001bd68  mov     rcx, rdi
0x18001bd6b  call    r14
0x18001bd6e  test    eax, eax
0x18001bd70  jz      short loc_18001BD54
0x18001bd72  mov     rcx, r15
0x18001bd75  mov     rax, rdi
0x18001bd78  sub     rcx, rbx
0x18001bd7b  sub     rax, r12
0x18001bd7e  cmp     rax, rcx
0x18001bd81  jl      short loc_18001BDA9
0x18001bd83  cmp     r12, rdi
0x18001bd86  jnb     short loc_18001BD98
0x18001bd88  mov     [rsp+r13*8+458h+var_438], r12
0x18001bd8d  mov     [rsp+r13*8+458h+var_248], rdi
0x18001bd95  inc     r13
0x18001bd98  cmp     rbx, r15
0x18001bd9b  jnb     loc_18001BB97
0x18001bda1  mov     r12, rbx
0x18001bda4  jmp     $recurse$163
0x18001bda9  cmp     rbx, r15
0x18001bdac  jnb     short loc_18001BDBE
0x18001bdae  mov     [rsp+r13*8+458h+var_438], rbx
0x18001bdb3  mov     [rsp+r13*8+458h+var_248], r15
0x18001bdbb  inc     r13
0x18001bdbe  cmp     r12, rdi
0x18001bdc1  jnb     loc_18001BB97
0x18001bdc7  mov     r15, rdi
0x18001bdca  jmp     $recurse$163
0x18001bdcf  mov     r13, [rsp+458h+var_38]
0x18001bdd7  mov     rdi, [rsp+458h+var_30]
0x18001bddf  mov     rsi, [rsp+458h+var_28]
0x18001bde7  mov     rbx, [rsp+458h+var_20]
0x18001bdef  mov     r15, [rsp+458h+var_40]
0x18001bdf7  mov     rcx, [rsp+458h+var_58]
0x18001bdff  xor     rcx, rsp; StackCookie
0x18001be02  call    __security_check_cookie
0x18001be07  add     rsp, 440h
0x18001be0e  pop     r14
0x18001be10  pop     r12
0x18001be12  pop     rbp
0x18001be13  retn
```
