# W3_REQUEST::BuildFullUrl(STRA &,STRA *,ushort const *,int)

- ea: `0x180028f18`
- end: `0x180029104`
- name: `?BuildFullUrl@W3_REQUEST@@QEAAJAEAVSTRA@@PEAV2@PEBGH@Z`
- size: `492`
- prototype: `int __fastcall(W3_REQUEST *this, struct STRA *, struct STRA *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024b80`

## callees

- `0x180016b40`
- `0x180028f18`

## import_xrefs

- `msvcrt!_wtoi` at `0x180029037`
- `msvcrt!_wtoi` at `0x18002905b`
- `msvcrt!_wtoi` at `0x180029037`
- `msvcrt!_wtoi` at `0x18002905b`
- `msvcrt!wcschr` at `0x180028fe2`
- `msvcrt!wcschr` at `0x18002900e`
- `msvcrt!wcschr` at `0x180028fe2`
- `msvcrt!wcschr` at `0x18002900e`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180028f66`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180028f66`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180028fa2`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180028fa2`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800290a8`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x1800290a8`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180028fbe`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180028fbe`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180029092`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180029092`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBGK@Z` at `0x1800290d7`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBGK@Z` at `0x1800290d7`

## pseudocode

```c
int __fastcall W3_REQUEST::BuildFullUrl(
        W3_REQUEST *this,
        struct STRA *a2,
        struct STRA *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int result; // eax
  const char *v10; // rdx
  const char *v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // rax
  wchar_t *v14; // rbx
  wchar_t *v15; // rax
  const unsigned __int16 *v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  unsigned int v19; // r8d
  __int64 v20; // rax
  const unsigned __int16 *v21; // rdx
  int appended; // eax
  int v23; // ecx
  unsigned __int16 v24; // [rsp+50h] [rbp+18h] BYREF

  if ( !a3 )
    return -2147024809;
  v10 = "https://";
  if ( !*(_QWORD *)(*((_QWORD *)this + 5) + 840LL) )
    v10 = "http://";
  result = STRA::Copy(a3, v10);
  if ( result >= 0 )
  {
    v24 = 0;
    v11 = W3_REQUEST::QueryHeader(this, HttpHeaderHost, &v24);
    if ( v11 )
    {
      result = STRA::Append(a3, v11, v24);
LABEL_24:
      if ( result >= 0 )
      {
        result = STRA::Append(a3, a2);
        if ( result >= 0 )
        {
          if ( a5 && (v20 = *((_QWORD *)this + 5), (v21 = *(const unsigned __int16 **)(v20 + 96)) != 0) )
          {
            appended = STRA::AppendWTruncate(a3, v21, *(unsigned __int16 *)(v20 + 70) >> 1);
            v23 = 0;
            if ( appended < 0 )
              return appended;
            return v23;
          }
          else
          {
            return 0;
          }
        }
      }
      return result;
    }
    if ( a4 )
    {
      result = STRA::AppendW(a3, a4);
      goto LABEL_24;
    }
    v12 = *(const wchar_t **)(*((_QWORD *)this + 5) + 80LL);
    if ( *v12 == 91 )
    {
      v13 = wcschr(v12, 0x5Du);
      if ( !v13 )
        goto LABEL_22;
      v14 = 0;
      v15 = v13 + 1;
      if ( *v15 == 58 )
        v14 = v15;
    }
    else
    {
      v14 = wcschr(v12, 0x3Au);
    }
    if ( v14
      && (*(_QWORD *)(*((_QWORD *)this + 5) + 840LL) && _wtoi(v14 + 1) == 443
       || !*(_QWORD *)(*((_QWORD *)this + 5) + 840LL) && _wtoi(v14 + 1) == 80) )
    {
      v16 = *(const unsigned __int16 **)(*((_QWORD *)this + 5) + 80LL);
      v17 = v14 - v16;
LABEL_23:
      result = STRA::AppendW(a3, v16, v17);
      goto LABEL_24;
    }
LABEL_22:
    v18 = *((_QWORD *)this + 5);
    v19 = *(unsigned __int16 *)(v18 + 66);
    v16 = *(const unsigned __int16 **)(v18 + 80);
    v17 = v19 >> 1;
    goto LABEL_23;
  }
  return result;
}

```

## disassembly

```asm
0x180028f18  mov     [rsp+arg_0], rbx
0x180028f1d  mov     [rsp+arg_8], rbp
0x180028f22  push    rsi
0x180028f23  push    rdi
0x180028f24  push    r14
0x180028f26  sub     rsp, 20h
0x180028f2a  mov     rbx, r9
0x180028f2d  mov     rsi, r8
0x180028f30  mov     r14, rdx
0x180028f33  mov     rdi, rcx
0x180028f36  test    r8, r8
0x180028f39  jnz     short loc_180028F45
0x180028f3b  mov     eax, 80070057h
0x180028f40  jmp     loc_1800290F0
0x180028f45  mov     rax, [rcx+28h]
0x180028f49  lea     rdx, aHttps; "https://"
0x180028f50  lea     rcx, aHttp_0; "http://"
0x180028f57  cmp     qword ptr [rax+348h], 0
0x180028f5f  cmovz   rdx, rcx
0x180028f63  mov     rcx, rsi
0x180028f66  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180028f6d  nop     dword ptr [rax+rax+00h]
0x180028f72  test    eax, eax
0x180028f74  js      loc_1800290F0
0x180028f7a  xor     eax, eax
0x180028f7c  lea     r8, [rsp+38h+arg_10]; unsigned __int16 *
0x180028f81  mov     rcx, rdi; this
0x180028f84  mov     [rsp+38h+arg_10], ax
0x180028f89  lea     edx, [rax+1Ch]; enum _HTTP_HEADER_ID
0x180028f8c  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180028f91  test    rax, rax
0x180028f94  jz      short loc_180028FB3
0x180028f96  movzx   r8d, [rsp+38h+arg_10]
0x180028f9c  mov     rdx, rax
0x180028f9f  mov     rcx, rsi
0x180028fa2  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180028fa9  nop     dword ptr [rax+rax+00h]
0x180028fae  jmp     loc_18002909E
0x180028fb3  test    rbx, rbx
0x180028fb6  jz      short loc_180028FCF
0x180028fb8  mov     rdx, rbx
0x180028fbb  mov     rcx, rsi
0x180028fbe  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x180028fc5  nop     dword ptr [rax+rax+00h]
0x180028fca  jmp     loc_18002909E
0x180028fcf  mov     rax, [rdi+28h]
0x180028fd3  mov     rcx, [rax+50h]; Str
0x180028fd7  cmp     word ptr [rcx], 5Bh ; '['
0x180028fdb  jnz     short loc_180029009
0x180028fdd  mov     edx, 5Dh ; ']'; Ch
0x180028fe2  call    cs:__imp_wcschr
0x180028fe9  nop     dword ptr [rax+rax+00h]
0x180028fee  test    rax, rax
0x180028ff1  jz      loc_18002907F
0x180028ff7  xor     ebx, ebx
0x180028ff9  add     rax, 2
0x180028ffd  lea     edx, [rbx+3Ah]
0x180029000  cmp     [rax], dx
0x180029003  cmovz   rbx, rax
0x180029007  jmp     short loc_18002901D
0x180029009  mov     edx, 3Ah ; ':'; Ch
0x18002900e  call    cs:__imp_wcschr
0x180029015  nop     dword ptr [rax+rax+00h]
0x18002901a  mov     rbx, rax
0x18002901d  test    rbx, rbx
0x180029020  jz      short loc_18002907F
0x180029022  mov     rcx, [rdi+28h]
0x180029026  lea     rbp, [rbx+2]
0x18002902a  cmp     qword ptr [rcx+348h], 0
0x180029032  jz      short loc_18002904A
0x180029034  mov     rcx, rbp; String
0x180029037  call    cs:__imp__wtoi
0x18002903e  nop     dword ptr [rax+rax+00h]
0x180029043  cmp     eax, 1BBh
0x180029048  jz      short loc_18002906C
0x18002904a  mov     rax, [rdi+28h]
0x18002904e  cmp     qword ptr [rax+348h], 0
0x180029056  jnz     short loc_18002907F
0x180029058  mov     rcx, rbp; String
0x18002905b  call    cs:__imp__wtoi
0x180029062  nop     dword ptr [rax+rax+00h]
0x180029067  cmp     eax, 50h ; 'P'
0x18002906a  jnz     short loc_18002907F
0x18002906c  mov     rax, [rdi+28h]
0x180029070  mov     rdx, [rax+50h]
0x180029074  sub     rbx, rdx
0x180029077  sar     rbx, 1
0x18002907a  mov     r8d, ebx
0x18002907d  jmp     short loc_18002908F
0x18002907f  mov     rdx, [rdi+28h]
0x180029083  movzx   r8d, word ptr [rdx+42h]
0x180029088  mov     rdx, [rdx+50h]
0x18002908c  shr     r8d, 1
0x18002908f  mov     rcx, rsi
0x180029092  call    cs:__imp_?AppendW@STRA@@QEAAJPEBGK@Z; STRA::AppendW(ushort const *,ulong)
0x180029099  nop     dword ptr [rax+rax+00h]
0x18002909e  test    eax, eax
0x1800290a0  js      short loc_1800290F0
0x1800290a2  mov     rdx, r14
0x1800290a5  mov     rcx, rsi
0x1800290a8  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x1800290af  nop     dword ptr [rax+rax+00h]
0x1800290b4  test    eax, eax
0x1800290b6  js      short loc_1800290F0
0x1800290b8  cmp     [rsp+38h+arg_20], 0
0x1800290bd  jz      short loc_1800290EE
0x1800290bf  mov     rax, [rdi+28h]
0x1800290c3  mov     rdx, [rax+60h]
0x1800290c7  test    rdx, rdx
0x1800290ca  jz      short loc_1800290EE
0x1800290cc  movzx   r8d, word ptr [rax+46h]
0x1800290d1  mov     rcx, rsi
0x1800290d4  shr     r8d, 1
0x1800290d7  call    cs:__imp_?AppendWTruncate@STRA@@QEAAJPEBGK@Z; STRA::AppendWTruncate(ushort const *,ulong)
0x1800290de  nop     dword ptr [rax+rax+00h]
0x1800290e3  xor     ecx, ecx
0x1800290e5  test    eax, eax
0x1800290e7  cmovs   ecx, eax
0x1800290ea  mov     eax, ecx
0x1800290ec  jmp     short loc_1800290F0
0x1800290ee  xor     eax, eax
0x1800290f0  mov     rbx, [rsp+38h+arg_0]
0x1800290f5  mov     rbp, [rsp+38h+arg_8]
0x1800290fa  add     rsp, 20h
0x1800290fe  pop     r14
0x180029100  pop     rdi
0x180029101  pop     rsi
0x180029102  retn
```
