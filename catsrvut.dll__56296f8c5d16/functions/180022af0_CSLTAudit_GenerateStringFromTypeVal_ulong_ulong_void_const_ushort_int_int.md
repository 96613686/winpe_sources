# CSLTAudit::GenerateStringFromTypeVal(ulong,ulong,void const *,ushort * *,int,int *)

- ea: `0x180022af0`
- end: `0x180022d12`
- name: `?GenerateStringFromTypeVal@CSLTAudit@@EEAAJKKPEBXPEAPEAGHPEAH@Z`
- size: `546`
- prototype: `__int64 __fastcall(CSLTAudit *__hidden this, unsigned int, unsigned int, const void *, unsigned __int16 **, int, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x18000717c`
- `0x180022af0`
- `0x180055822`
- `0x18005583a`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022cef`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022c7b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180022c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022be9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ca0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ba7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022be9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022c13`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022ca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSLTAudit::GenerateStringFromTypeVal(
        CSLTAudit *this,
        int a2,
        __int64 a3,
        unsigned int *a4,
        unsigned __int16 **a5,
        int a6,
        int *a7)
{
  unsigned int *v7; // rdi
  int v9; // edx
  int v10; // edx
  int v11; // edx
  int v12; // edx
  __int64 v13; // rax
  unsigned __int64 v14; // rsi
  unsigned __int16 *v15; // rax
  const unsigned __int16 *v16; // r8
  unsigned __int64 v17; // rdx
  int v18; // eax
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // rax
  int v21; // edi
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rcx
  GUID Buf2; // [rsp+20h] [rbp-38h] BYREF

  v7 = a4;
  *a5 = 0;
  if ( a7 )
    *a7 = 0;
  if ( a6 == 1 )
    return (*(__int64 (__fastcall **)(CSLTAudit *, unsigned __int16 **))(*(_QWORD *)this + 48LL))(this, a5);
  v9 = a2 - 19;
  if ( !v9 )
  {
    v22 = (unsigned __int16 *)CoTaskMemAlloc(0x28u);
    *a5 = v22;
    *(_OWORD *)v22 = 0;
    *((_OWORD *)v22 + 1) = 0;
    *((_QWORD *)v22 + 4) = 0;
    v23 = *a5;
    if ( v7 )
      v18 = StringCchPrintfW(v23, 0x14u, L"%d", *v7);
    else
      v18 = StringCchPrintfW(v23, 0x14u, L"<null>");
    goto LABEL_34;
  }
  v10 = v9 - 53;
  if ( v10 )
  {
    v11 = v10 - 56;
    if ( v11 )
    {
      v12 = v11 - 2;
      if ( !v12 )
      {
        if ( a4 )
        {
          v13 = -1;
          do
            ++v13;
          while ( *((_WORD *)a4 + v13) );
          v14 = v13 + 1;
        }
        else
        {
          v14 = 8;
        }
        v15 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v14, 2u));
        *a5 = v15;
        if ( v15 )
        {
          memset_0(v15, 0, 2 * v14);
          if ( !v7 )
            v7 = (unsigned int *)L"<null>";
          v16 = (const unsigned __int16 *)v7;
          v17 = v14;
          goto LABEL_20;
        }
        return 2147942414LL;
      }
      if ( v12 != 5 )
        return 2147549183LL;
    }
    v19 = (unsigned __int16 *)CoTaskMemAlloc(0x14u);
    *a5 = v19;
    if ( v19 )
    {
      *(_OWORD *)v19 = 0;
      *((_DWORD *)v19 + 4) = 0;
      v16 = L"<Opaque>";
      v17 = 10;
LABEL_20:
      v18 = StringCchCopyW(*a5, v17, v16);
LABEL_34:
      v21 = v18;
      goto LABEL_35;
    }
    return 2147942414LL;
  }
  v20 = (unsigned __int16 *)CoTaskMemAlloc(0x50u);
  *a5 = v20;
  if ( !v20 )
    return 2147942414LL;
  memset_0(v20, 0, 0x50u);
  if ( v7 )
  {
    Buf2 = *(GUID *)v7;
    if ( a7 && !memcmp_0(&GUID_NULL, &Buf2, 0x10u) )
      *a7 = 1;
    v18 = StringFromGUID2(&Buf2, *a5, 40);
    goto LABEL_34;
  }
  v21 = 0;
  StringCchCopyW(*a5, 0x28u, L"<null>");
LABEL_35:
  if ( v21 < 0 )
  {
    if ( *a5 )
      CoTaskMemFree(*a5);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180022af0  mov     [rsp+arg_8], rbx
0x180022af5  push    rbp
0x180022af6  push    rsi
0x180022af7  push    rdi
0x180022af8  sub     rsp, 40h
0x180022afc  mov     rax, cs:__security_cookie
0x180022b03  xor     rax, rsp
0x180022b06  mov     [rsp+58h+var_28], rax
0x180022b0b  mov     rdi, r9
0x180022b0e  mov     rbx, [rsp+58h+arg_20]
0x180022b16  mov     rsi, [rsp+58h+arg_30]
0x180022b1e  xor     ebp, ebp
0x180022b20  mov     [rbx], rbp
0x180022b23  test    rsi, rsi
0x180022b26  jz      short loc_180022B2A
0x180022b28  mov     [rsi], ebp
0x180022b2a  cmp     [rsp+58h+arg_28], 1
0x180022b32  jnz     short loc_180022B48
0x180022b34  mov     rax, [rcx]
0x180022b37  mov     rdx, rbx
0x180022b3a  mov     rax, [rax+30h]
0x180022b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b43  jmp     loc_180022CF8
0x180022b48  sub     edx, 13h
0x180022b4b  jz      loc_180022C9B
0x180022b51  sub     edx, 35h ; '5'
0x180022b54  jz      loc_180022C0E
0x180022b5a  sub     edx, 38h ; '8'
0x180022b5d  jz      loc_180022BE4
0x180022b63  sub     edx, 2
0x180022b66  jz      short loc_180022B77
0x180022b68  cmp     edx, 5
0x180022b6b  jz      short loc_180022BE4
0x180022b6d  mov     eax, 8000FFFFh
0x180022b72  jmp     loc_180022CF8
0x180022b77  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180022b7b  test    rdi, rdi
0x180022b7e  jz      short loc_180022B93
0x180022b80  mov     rax, rcx
0x180022b83  inc     rax
0x180022b86  cmp     [r9+rax*2], bp
0x180022b8b  jnz     short loc_180022B83
0x180022b8d  lea     rsi, [rax+1]
0x180022b91  jmp     short loc_180022B98
0x180022b93  mov     esi, 8
0x180022b98  mov     eax, 2
0x180022b9d  mul     rsi
0x180022ba0  cmovb   rax, rcx
0x180022ba4  mov     rcx, rax; cb
0x180022ba7  call    cs:__imp_CoTaskMemAlloc
0x180022bad  mov     [rbx], rax
0x180022bb0  test    rax, rax
0x180022bb3  jz      short loc_180022C21
0x180022bb5  lea     r8, [rsi+rsi]; Size
0x180022bb9  xor     edx, edx; Val
0x180022bbb  mov     rcx, rax; void *
0x180022bbe  call    memset_0
0x180022bc3  lea     r8, aNull_0; "<null>"
0x180022bca  test    rdi, rdi
0x180022bcd  cmovz   rdi, r8
0x180022bd1  mov     r8, rdi; unsigned __int16 *
0x180022bd4  mov     rdx, rsi; unsigned __int64
0x180022bd7  mov     rcx, [rbx]; unsigned __int16 *
0x180022bda  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022bdf  jmp     loc_180022CE1
0x180022be4  mov     ecx, 14h; cb
0x180022be9  call    cs:__imp_CoTaskMemAlloc
0x180022bef  mov     [rbx], rax
0x180022bf2  test    rax, rax
0x180022bf5  jz      short loc_180022C21
0x180022bf7  xorps   xmm0, xmm0
0x180022bfa  xor     ecx, ecx
0x180022bfc  movups  xmmword ptr [rax], xmm0
0x180022bff  mov     [rax+10h], ecx
0x180022c02  lea     r8, aOpaque; "<Opaque>"
0x180022c09  lea     edx, [rcx+0Ah]
0x180022c0c  jmp     short loc_180022BD7
0x180022c0e  mov     ecx, 50h ; 'P'; cb
0x180022c13  call    cs:__imp_CoTaskMemAlloc
0x180022c19  mov     [rbx], rax
0x180022c1c  test    rax, rax
0x180022c1f  jnz     short loc_180022C2B
0x180022c21  mov     eax, 8007000Eh
0x180022c26  jmp     loc_180022CF8
0x180022c2b  xor     edx, edx; Val
0x180022c2d  lea     r8d, [rdx+50h]; Size
0x180022c31  mov     rcx, rax; void *
0x180022c34  call    memset_0
0x180022c39  test    rdi, rdi
0x180022c3c  jz      short loc_180022C83
0x180022c3e  movups  xmm0, xmmword ptr [rdi]
0x180022c41  movdqu  [rsp+58h+Buf2], xmm0
0x180022c47  test    rsi, rsi
0x180022c4a  jz      short loc_180022C6D
0x180022c4c  mov     r8d, 10h; Size
0x180022c52  lea     rdx, [rsp+58h+Buf2]; Buf2
0x180022c57  lea     rcx, GUID_NULL; Buf1
0x180022c5e  call    memcmp_0
0x180022c63  test    eax, eax
0x180022c65  jnz     short loc_180022C6D
0x180022c67  mov     dword ptr [rsi], 1
0x180022c6d  mov     r8d, 28h ; '('; cchMax
0x180022c73  mov     rdx, [rbx]; lpsz
0x180022c76  lea     rcx, [rsp+58h+Buf2]; rguid
0x180022c7b  call    cs:__imp_StringFromGUID2
0x180022c81  jmp     short loc_180022CE1
0x180022c83  mov     edi, ebp
0x180022c85  lea     r8, aNull_0; "<null>"
0x180022c8c  mov     edx, 28h ; '('; unsigned __int64
0x180022c91  mov     rcx, [rbx]; unsigned __int16 *
0x180022c94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022c99  jmp     short loc_180022CE3
0x180022c9b  mov     ecx, 28h ; '('; cb
0x180022ca0  call    cs:__imp_CoTaskMemAlloc
0x180022ca6  mov     [rbx], rax
0x180022ca9  xorps   xmm0, xmm0
0x180022cac  xor     ecx, ecx
0x180022cae  movups  xmmword ptr [rax], xmm0
0x180022cb1  movups  xmmword ptr [rax+10h], xmm0
0x180022cb5  mov     [rax+20h], rcx
0x180022cb9  lea     edx, [rcx+14h]; unsigned __int64
0x180022cbc  mov     rcx, [rbx]; unsigned __int16 *
0x180022cbf  test    rdi, rdi
0x180022cc2  jz      short loc_180022CD5
0x180022cc4  mov     r9d, [rdi]
0x180022cc7  lea     r8, aD; "%d"
0x180022cce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022cd3  jmp     short loc_180022CE1
0x180022cd5  lea     r8, aNull_0; "<null>"
0x180022cdc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180022ce1  mov     edi, eax
0x180022ce3  test    edi, edi
0x180022ce5  jns     short loc_180022CF6
0x180022ce7  mov     rcx, [rbx]; pv
0x180022cea  test    rcx, rcx
0x180022ced  jz      short loc_180022CF6
0x180022cef  call    cs:__imp_CoTaskMemFree
0x180022cf5  nop
0x180022cf6  mov     eax, edi
0x180022cf8  mov     rcx, [rsp+58h+var_28]
0x180022cfd  xor     rcx, rsp; StackCookie
0x180022d00  call    __security_check_cookie
0x180022d05  mov     rbx, [rsp+58h+arg_8]
0x180022d0a  add     rsp, 40h
0x180022d0e  pop     rdi
0x180022d0f  pop     rsi
0x180022d10  pop     rbp
0x180022d11  retn
```
