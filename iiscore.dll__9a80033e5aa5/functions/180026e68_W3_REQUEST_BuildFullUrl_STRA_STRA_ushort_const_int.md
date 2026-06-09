# W3_REQUEST::BuildFullUrl(STRA &,STRA *,ushort const *,int)

- ea: `0x180026e68`
- end: `0x180027013`
- name: `?BuildFullUrl@W3_REQUEST@@QEAAJAEAVSTRA@@PEAV2@PEBGH@Z`
- size: `427`
- prototype: `__int64 __usercall@<rax>(W3_REQUEST *__hidden this@<rcx>, struct STRA *@<rdx>, struct STRA *@<r8>, const unsigned __int16 *@<r9>, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022e70`

## callees

- `0x1800159e0`
- `0x180026e68`

## import_xrefs

- `msvcrt!_wtoi` at `0x180026f65`
- `msvcrt!_wtoi` at `0x180026f83`
- `msvcrt!_wtoi` at `0x180026f65`
- `msvcrt!_wtoi` at `0x180026f83`
- `msvcrt!wcschr` at `0x180026f20`
- `msvcrt!wcschr` at `0x180026f42`
- `msvcrt!wcschr` at `0x180026f20`
- `msvcrt!wcschr` at `0x180026f42`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180026eb6`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180026eb6`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026eec`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180026eec`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180026fc4`
- `iisutil!?Append@STRA@@QEAAJAEBV1@@Z` at `0x180026fc4`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180026f02`
- `iisutil!?AppendW@STRA@@QEAAJPEBG@Z` at `0x180026f02`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180026fb4`
- `iisutil!?AppendW@STRA@@QEAAJPEBGK@Z` at `0x180026fb4`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180026fed`
- `iisutil!?AppendWTruncate@STRA@@QEAAJPEBGK@Z` at `0x180026fed`

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
    v11 = W3_REQUEST::QueryHeader(this, 0x1Cu, &v24);
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
0x180026e68  mov     [rsp+arg_0], rbx
0x180026e6d  mov     [rsp+arg_8], rbp
0x180026e72  push    rsi
0x180026e73  push    rdi
0x180026e74  push    r14
0x180026e76  sub     rsp, 20h
0x180026e7a  mov     rbx, r9
0x180026e7d  mov     rsi, r8
0x180026e80  mov     r14, rdx
0x180026e83  mov     rdi, rcx
0x180026e86  test    r8, r8
0x180026e89  jnz     short loc_180026E95
0x180026e8b  mov     eax, 80070057h
0x180026e90  jmp     loc_180027000
0x180026e95  mov     rax, [rcx+28h]
0x180026e99  lea     rdx, aHttps; "https://"
0x180026ea0  lea     rcx, aHttp_0; "http://"
0x180026ea7  cmp     qword ptr [rax+348h], 0
0x180026eaf  cmovz   rdx, rcx
0x180026eb3  mov     rcx, rsi
0x180026eb6  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180026ebc  test    eax, eax
0x180026ebe  js      loc_180027000
0x180026ec4  xor     eax, eax
0x180026ec6  lea     r8, [rsp+38h+arg_10]; unsigned __int16 *
0x180026ecb  mov     rcx, rdi; this
0x180026ece  mov     [rsp+38h+arg_10], ax
0x180026ed3  lea     edx, [rax+1Ch]; enum _HTTP_HEADER_ID
0x180026ed6  call    ?QueryHeader@W3_REQUEST@@QEBAPEBDW4_HTTP_HEADER_ID@@PEAG@Z; W3_REQUEST::QueryHeader(_HTTP_HEADER_ID,ushort *)
0x180026edb  test    rax, rax
0x180026ede  jz      short loc_180026EF7
0x180026ee0  movzx   r8d, [rsp+38h+arg_10]
0x180026ee6  mov     rdx, rax
0x180026ee9  mov     rcx, rsi
0x180026eec  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x180026ef2  jmp     loc_180026FBA
0x180026ef7  test    rbx, rbx
0x180026efa  jz      short loc_180026F0D
0x180026efc  mov     rdx, rbx
0x180026eff  mov     rcx, rsi
0x180026f02  call    cs:__imp_?AppendW@STRA@@QEAAJPEBG@Z; STRA::AppendW(ushort const *)
0x180026f08  jmp     loc_180026FBA
0x180026f0d  mov     rax, [rdi+28h]
0x180026f11  mov     rcx, [rax+50h]; Str
0x180026f15  cmp     word ptr [rcx], 5Bh ; '['
0x180026f19  jnz     short loc_180026F3D
0x180026f1b  mov     edx, 5Dh ; ']'; Ch
0x180026f20  call    cs:__imp_wcschr
0x180026f26  test    rax, rax
0x180026f29  jz      short loc_180026FA1
0x180026f2b  xor     ebx, ebx
0x180026f2d  add     rax, 2
0x180026f31  lea     edx, [rbx+3Ah]
0x180026f34  cmp     [rax], dx
0x180026f37  cmovz   rbx, rax
0x180026f3b  jmp     short loc_180026F4B
0x180026f3d  mov     edx, 3Ah ; ':'; Ch
0x180026f42  call    cs:__imp_wcschr
0x180026f48  mov     rbx, rax
0x180026f4b  test    rbx, rbx
0x180026f4e  jz      short loc_180026FA1
0x180026f50  mov     rcx, [rdi+28h]
0x180026f54  lea     rbp, [rbx+2]
0x180026f58  cmp     qword ptr [rcx+348h], 0
0x180026f60  jz      short loc_180026F72
0x180026f62  mov     rcx, rbp; String
0x180026f65  call    cs:__imp__wtoi
0x180026f6b  cmp     eax, 1BBh
0x180026f70  jz      short loc_180026F8E
0x180026f72  mov     rax, [rdi+28h]
0x180026f76  cmp     qword ptr [rax+348h], 0
0x180026f7e  jnz     short loc_180026FA1
0x180026f80  mov     rcx, rbp; String
0x180026f83  call    cs:__imp__wtoi
0x180026f89  cmp     eax, 50h ; 'P'
0x180026f8c  jnz     short loc_180026FA1
0x180026f8e  mov     rax, [rdi+28h]
0x180026f92  mov     rdx, [rax+50h]
0x180026f96  sub     rbx, rdx
0x180026f99  sar     rbx, 1
0x180026f9c  mov     r8d, ebx
0x180026f9f  jmp     short loc_180026FB1
0x180026fa1  mov     rdx, [rdi+28h]
0x180026fa5  movzx   r8d, word ptr [rdx+42h]
0x180026faa  mov     rdx, [rdx+50h]
0x180026fae  shr     r8d, 1
0x180026fb1  mov     rcx, rsi
0x180026fb4  call    cs:__imp_?AppendW@STRA@@QEAAJPEBGK@Z; STRA::AppendW(ushort const *,ulong)
0x180026fba  test    eax, eax
0x180026fbc  js      short loc_180027000
0x180026fbe  mov     rdx, r14
0x180026fc1  mov     rcx, rsi
0x180026fc4  call    cs:__imp_?Append@STRA@@QEAAJAEBV1@@Z; STRA::Append(STRA const &)
0x180026fca  test    eax, eax
0x180026fcc  js      short loc_180027000
0x180026fce  cmp     [rsp+38h+arg_20], 0
0x180026fd3  jz      short loc_180026FFE
0x180026fd5  mov     rax, [rdi+28h]
0x180026fd9  mov     rdx, [rax+60h]
0x180026fdd  test    rdx, rdx
0x180026fe0  jz      short loc_180026FFE
0x180026fe2  movzx   r8d, word ptr [rax+46h]
0x180026fe7  mov     rcx, rsi
0x180026fea  shr     r8d, 1
0x180026fed  call    cs:__imp_?AppendWTruncate@STRA@@QEAAJPEBGK@Z; STRA::AppendWTruncate(ushort const *,ulong)
0x180026ff3  xor     ecx, ecx
0x180026ff5  test    eax, eax
0x180026ff7  cmovs   ecx, eax
0x180026ffa  mov     eax, ecx
0x180026ffc  jmp     short loc_180027000
0x180026ffe  xor     eax, eax
0x180027000  mov     rbx, [rsp+38h+arg_0]
0x180027005  mov     rbp, [rsp+38h+arg_8]
0x18002700a  add     rsp, 20h
0x18002700e  pop     r14
0x180027010  pop     rdi
0x180027011  pop     rsi
0x180027012  retn
```
