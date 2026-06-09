# RtlCultureNameToLCID

- ea: `0x18000b730`
- end: `0x18000b93b`
- name: `RtlCultureNameToLCID`
- size: `523`
- prototype: ``
- caller_count: `34`
- callee_count: `10`
- tags: ``

## callers

- `0x1800094d0`
- `0x180009be0`
- `0x18000aff0`
- `0x18000be70`
- `0x18000c7b0`
- `0x18000d290`
- `0x18000d3e0`
- `0x1800122d0`
- `0x180012664`
- `0x1800145b0`
- `0x180014f80`
- `0x180071f80`
- `0x1800738a0`
- `0x1800743b0`
- `0x18007a2c0`
- `0x1800ad6c0`
- `0x1800aec20`
- `0x1800bc688`
- `0x1800bcb1c`
- `0x1800bcd10`
- `0x1800dad74`
- `0x1800dfb4c`
- `0x1800dfe64`
- `0x1800e2b60`
- `0x1800fc980`
- `0x180100508`
- `0x180100e20`
- `0x18010c8f4`
- `0x18010fef8`
- `0x180124b40`
- `0x180142c30`
- `0x180143270`
- `0x18014d800`
- `0x18014dca8`

## callees

- `0x18000b730`
- `0x18000b950`
- `0x18000ba2c`
- `0x1800c3e4c`
- `0x1800c4fec`
- `0x18010fc0c`
- `0x180126460`
- `0x180128800`
- `0x180162810`
- `0x180164280`

## pseudocode

```c
char __fastcall RtlCultureNameToLCID(unsigned __int16 *a1, int *a2)
{
  char v2; // r9
  size_t v4; // r8
  const void *v5; // rdx
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rsi
  __int64 v10; // rdi
  int i; // ebx
  wchar_t *v12; // rcx
  unsigned __int16 j; // dx
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v17; // rbx
  int NameIndex; // eax
  char matched; // al
  wchar_t String2[88]; // [rsp+20h] [rbp-D8h] BYREF

  v2 = 0;
  if ( !a1 )
    return v2;
  if ( !a2 )
    return v2;
  v4 = *a1;
  if ( !(_WORD)v4 )
    return v2;
  v5 = (const void *)*((_QWORD *)a1 + 1);
  if ( !v5 || (unsigned int)(v4 + 2) > 0x55 )
    return v2;
  v6 = *a1;
  memmove(String2, v5, v4);
  v7 = v6 >> 1;
  if ( v7 >= 85 )
    _report_rangecheckfailure();
  v8 = g_RegInfo;
  String2[v7] = 0;
  if ( v8 )
  {
    v9 = *(_QWORD *)(v8 + 24);
    if ( v9 )
    {
      if ( *(_QWORD *)(v9 + 16) && String2[0] )
      {
        v10 = *(_QWORD *)(v8 + 32);
        if ( v10 )
        {
          for ( i = 0; i < *(unsigned __int16 *)(v10 + 6); ++i )
          {
            v12 = (wchar_t *)(*(_QWORD *)(v10 + 24) + 2LL * *(__int16 *)(*(_QWORD *)(v10 + 16) + 2LL * i));
            if ( v12 == String2 || !wcsicmp(v12, String2) )
            {
              if ( i < 0 )
                break;
              goto LABEL_18;
            }
          }
        }
        LOWORD(i) = -1;
LABEL_18:
        if ( (i & 0x8000u) == 0 )
        {
          for ( j = 0; j < *(_WORD *)(v9 + 6); ++j )
          {
            v14 = 28LL * j;
            v15 = *(_QWORD *)(v9 + 16);
            if ( *(_WORD *)(v14 + v15 + 6) == (_WORD)i )
            {
              *a2 = *(unsigned __int16 *)(v14 + v15 + 4);
              return 1;
            }
          }
        }
      }
    }
  }
  v17 = pTblPtrs;
  if ( !pTblPtrs )
  {
    if ( !(unsigned __int8)RtlpLoadNlsData() )
      return 0;
    v17 = pTblPtrs;
  }
  NameIndex = RtlpNlsGetNameIndex(String2);
  if ( NameIndex < 0 )
  {
    if ( (unsigned __int8)RtlpIsCustomLocale(String2) )
    {
      if ( !(unsigned __int8)RtlpMatchUILanguage(String2) )
      {
        matched = RtlpMatchUserLanguage(String2);
        v2 = 1;
        if ( matched )
          *a2 = 3072;
        else
          *a2 = 4096;
        return v2;
      }
      *a2 = 5120;
      return 1;
    }
    return 0;
  }
  *a2 = *(_DWORD *)(*(_QWORD *)(v17 + 24) + 8LL * NameIndex + 4) & 0x7FFFFFFF;
  return 1;
}

```

## disassembly

```asm
0x18000b730  mov     [rsp+arg_10], rbx
0x18000b735  push    rsi
0x18000b736  push    rdi
0x18000b737  push    r14
0x18000b739  sub     rsp, 0E0h
0x18000b740  mov     rax, cs:__security_cookie
0x18000b747  xor     rax, rsp
0x18000b74a  mov     [rsp+0F8h+var_28], rax
0x18000b752  xor     r9b, r9b
0x18000b755  mov     r14, rdx
0x18000b758  test    rcx, rcx
0x18000b75b  jz      loc_18000B89C
0x18000b761  test    rdx, rdx
0x18000b764  jz      loc_18000B89C
0x18000b76a  movzx   r8d, word ptr [rcx]; Size
0x18000b76e  xor     eax, eax
0x18000b770  cmp     ax, r8w
0x18000b774  jz      loc_18000B89C
0x18000b77a  mov     rdx, [rcx+8]; Src
0x18000b77e  test    rdx, rdx
0x18000b781  jz      loc_18000B89C
0x18000b787  lea     eax, [r8+2]
0x18000b78b  cmp     eax, 55h ; 'U'
0x18000b78e  ja      loc_18000B89C
0x18000b794  lea     rcx, [rsp+0F8h+String2]; void *
0x18000b799  mov     ebx, r8d
0x18000b79c  call    memmove
0x18000b7a1  shr     rbx, 1
0x18000b7a4  add     rbx, rbx
0x18000b7a7  cmp     rbx, 0AAh
0x18000b7ae  jnb     loc_18000B900
0x18000b7b4  mov     rdi, cs:g_RegInfo
0x18000b7bb  xor     eax, eax
0x18000b7bd  mov     [rsp+rbx+0F8h+String2], ax
0x18000b7c2  test    rdi, rdi
0x18000b7c5  jz      loc_18000B86D
0x18000b7cb  mov     rsi, [rdi+18h]
0x18000b7cf  test    rsi, rsi
0x18000b7d2  jz      loc_18000B86D
0x18000b7d8  cmp     [rsi+10h], rax
0x18000b7dc  jz      loc_18000B86D
0x18000b7e2  test    rdi, rdi
0x18000b7e5  jz      loc_18000B86D
0x18000b7eb  cmp     [rsp+0F8h+String2], ax
0x18000b7f0  jz      short loc_18000B86D
0x18000b7f2  mov     rdi, [rdi+20h]
0x18000b7f6  test    rdi, rdi
0x18000b7f9  jz      short loc_18000B866
0x18000b7fb  xor     ebx, ebx
0x18000b7fd  movzx   eax, word ptr [rdi+6]
0x18000b801  cmp     ebx, eax
0x18000b803  jge     short loc_18000B866
0x18000b805  mov     rax, [rdi+10h]
0x18000b809  movsxd  rcx, ebx
0x18000b80c  movsx   rdx, word ptr [rax+rcx*2]
0x18000b811  mov     rax, [rdi+18h]
0x18000b815  lea     rcx, [rax+rdx*2]; String1
0x18000b819  lea     rax, [rsp+0F8h+String2]
0x18000b81e  cmp     rcx, rax
0x18000b821  jz      short loc_18000B835
0x18000b823  lea     rdx, [rsp+0F8h+String2]; String2
0x18000b828  call    _wcsicmp
0x18000b82d  test    eax, eax
0x18000b82f  jz      short loc_18000B835
0x18000b831  inc     ebx
0x18000b833  jmp     short loc_18000B7FD
0x18000b835  test    ebx, ebx
0x18000b837  js      short loc_18000B866
0x18000b839  test    bx, bx
0x18000b83c  js      short loc_18000B86D
0x18000b83e  xor     edx, edx
0x18000b840  cmp     dx, [rsi+6]
0x18000b844  jnb     short loc_18000B86D
0x18000b846  movzx   eax, dx
0x18000b849  imul    r8, rax, 1Ch
0x18000b84d  mov     rax, [rsi+10h]
0x18000b851  cmp     [r8+rax+6], bx
0x18000b857  jnz     short loc_18000B8D3
0x18000b859  movzx   eax, word ptr [r8+rax+4]
0x18000b85f  mov     [r14], eax
0x18000b862  mov     al, 1
0x18000b864  jmp     short loc_18000B8A0
0x18000b866  mov     ebx, 0FFFFFFFFh
0x18000b86b  jmp     short loc_18000B839
0x18000b86d  mov     rbx, cs:pTblPtrs
0x18000b874  test    rbx, rbx
0x18000b877  jz      short loc_18000B8C5
0x18000b879  lea     rcx, [rsp+0F8h+String2]
0x18000b87e  call    RtlpNlsGetNameIndex
0x18000b883  test    eax, eax
0x18000b885  js      short loc_18000B8DB
0x18000b887  movsxd  rcx, eax
0x18000b88a  mov     rax, [rbx+18h]
0x18000b88e  mov     edx, [rax+rcx*8+4]
0x18000b892  btr     edx, 1Fh
0x18000b896  mov     [r14], edx
0x18000b899  mov     r9b, 1
0x18000b89c  movzx   eax, r9b
0x18000b8a0  mov     rcx, [rsp+0F8h+var_28]
0x18000b8a8  xor     rcx, rsp; StackCookie
0x18000b8ab  call    __security_check_cookie
0x18000b8b0  mov     rbx, [rsp+0F8h+arg_10]
0x18000b8b8  add     rsp, 0E0h
0x18000b8bf  pop     r14
0x18000b8c1  pop     rdi
0x18000b8c2  pop     rsi
0x18000b8c3  retn
0x18000b8c5  call    RtlpLoadNlsData
0x18000b8ca  test    al, al
0x18000b8cc  jnz     short loc_18000B92F
0x18000b8ce  xor     r9b, r9b
0x18000b8d1  jmp     short loc_18000B89C
0x18000b8d3  inc     dx
0x18000b8d6  jmp     loc_18000B840
0x18000b8db  lea     rcx, [rsp+0F8h+String2]; String
0x18000b8e0  call    RtlpIsCustomLocale
0x18000b8e5  test    al, al
0x18000b8e7  jz      short loc_18000B8CE
0x18000b8e9  lea     rcx, [rsp+0F8h+String2]; SourceString
0x18000b8ee  call    RtlpMatchUILanguage
0x18000b8f3  test    al, al
0x18000b8f5  jz      short loc_18000B906
0x18000b8f7  mov     dword ptr [r14], 1400h
0x18000b8fe  jmp     short loc_18000B899
0x18000b900  call    __report_rangecheckfailure
0x18000b906  lea     rcx, [rsp+0F8h+String2]; String
0x18000b90b  call    RtlpMatchUserLanguage
0x18000b910  mov     r9b, 1
0x18000b913  test    al, al
0x18000b915  jnz     short loc_18000B923
0x18000b917  mov     dword ptr [r14], 1000h
0x18000b91e  jmp     loc_18000B89C
0x18000b923  mov     dword ptr [r14], 0C00h
0x18000b92a  jmp     loc_18000B89C
0x18000b92f  mov     rbx, cs:pTblPtrs
0x18000b936  jmp     loc_18000B879
```
