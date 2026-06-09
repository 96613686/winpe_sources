# CSlowLinkConfigInfo::_ParseParameterValueString(ushort const *,CSlowLinkConfigInfo::INFO *)

- ea: `0x180060bb4`
- end: `0x180060dea`
- name: `?_ParseParameterValueString@CSlowLinkConfigInfo@@AEAAHPEBGPEAUINFO@1@@Z`
- size: `566`
- prototype: `int(CSlowLinkConfigInfo *__hidden this, const unsigned __int16 *, struct CSlowLinkConfigInfo::INFO *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011070`
- `0x180011298`

## callees

- `0x180039610`
- `0x18003a114`
- `0x180060b6c`
- `0x180060bb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180060d68`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180060d68`
- `KERNEL32!CompareStringW` at `0x180060c5a`
- `KERNEL32!CompareStringW` at `0x180060c97`
- `KERNEL32!CompareStringW` at `0x180060c5a`
- `KERNEL32!CompareStringW` at `0x180060c97`

## pseudocode

```c
_BOOL8 __fastcall CSlowLinkConfigInfo::_ParseParameterValueString(
        CSlowLinkConfigInfo *this,
        unsigned __int16 *a2,
        struct CSlowLinkConfigInfo::INFO *a3)
{
  BOOL v5; // ebp
  int v6; // edi
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // r15
  const unsigned __int16 *v10; // rax
  unsigned __int16 v11; // cx
  unsigned __int16 *v12; // rax
  bool v13; // zf
  unsigned __int16 v14; // ax
  unsigned __int16 *v15; // rdi
  __int64 v17; // [rsp+30h] [rbp-78h] BYREF
  WCHAR lpString2[12]; // [rsp+38h] [rbp-70h] BYREF
  WCHAR String2[8]; // [rsp+50h] [rbp-58h] BYREF

  v5 = 0;
  wcscpy(String2, L"latency");
  v6 = 0;
  *(_OWORD *)lpString2 = *(_OWORD *)L"throughput";
  *(_QWORD *)a3 = 0;
  wcscpy(&lpString2[7], L"put");
  while ( *(_QWORD *)a3 != 3 )
  {
    if ( v6 )
      goto LABEL_32;
    a2 = (unsigned __int16 *)CSlowLinkConfigInfo::_EatWhitespace(this, a2);
    if ( !a2 )
      return v6 == 0;
    if ( CompareStringW(0x7Fu, 1u, a2, 7, String2, -1) == 2 )
    {
      v7 = 2;
      v8 = 7;
      v9 = 16;
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a2, 10, lpString2, -1) != 2 )
        goto LABEL_29;
      v8 = 10;
      v7 = 1;
      v9 = 8;
    }
    a2 = (unsigned __int16 *)CSlowLinkConfigInfo::_EatWhitespace(this, &a2[v8]);
    if ( !a2
      || *a2 != 61
      || (v10 = CSlowLinkConfigInfo::_EatWhitespace(this, a2 + 1), (a2 = (unsigned __int16 *)v10) == 0) )
    {
LABEL_29:
      v6 = 1;
      goto LABEL_30;
    }
    v17 = 0;
    if ( swscanf_s(v10, L"%I64i ,", &v17) == 1 )
    {
      v11 = *a2;
      v12 = a2;
      while ( v11 && v11 != 44 )
        v11 = *++v12;
      this = (CSlowLinkConfigInfo *)*v12;
      if ( (_WORD)this )
      {
        if ( (_WORD)this == 44 )
          this = (CSlowLinkConfigInfo *)*++v12;
      }
      else
      {
        this = 0;
      }
      LOWORD(this) = -(__int16)this;
      a2 = (unsigned __int16 *)((unsigned __int64)v12 & -(__int64)((_WORD)this != 0));
      v13 = a2 == 0;
    }
    else
    {
      if ( swscanf_s(a2, L"%I64i", &v17) != 1 )
        goto LABEL_29;
      v14 = *a2;
      v15 = a2;
      while ( v14 && !(unsigned int)_o_iswspace(v14) )
        v14 = *++v15;
      a2 = (unsigned __int16 *)((unsigned __int64)v15 & -(__int64)(*v15 != 0));
      v13 = a2 == 0;
    }
    v5 = v13;
    *(_QWORD *)((char *)a3 + v9) = v17;
    *(_QWORD *)a3 |= v7;
    v6 = 0;
LABEL_30:
    if ( v5 )
      break;
  }
  if ( !v6 )
    return v6 == 0;
LABEL_32:
  *(_OWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  return v6 == 0;
}

```

## disassembly

```asm
0x180060bb4  mov     [rsp+arg_0], rbx
0x180060bb9  push    rbp
0x180060bba  push    rsi
0x180060bbb  push    rdi
0x180060bbc  push    r12
0x180060bbe  push    r13
0x180060bc0  push    r14
0x180060bc2  push    r15
0x180060bc4  sub     rsp, 70h
0x180060bc8  mov     rax, cs:__security_cookie
0x180060bcf  xor     rax, rsp
0x180060bd2  mov     [rsp+0A8h+var_48], rax
0x180060bd7  movups  xmm0, xmmword ptr cs:aLatency; "latency"
0x180060bde  xor     r12d, r12d
0x180060be1  mov     rsi, r8
0x180060be4  movups  xmm1, xmmword ptr cs:aThroughput; "throughput"
0x180060beb  mov     rbx, rdx
0x180060bee  mov     ebp, r12d
0x180060bf1  movdqu  xmmword ptr [rsp+0A8h+String2], xmm0
0x180060bf7  lea     r13d, [r12+1]
0x180060bfc  mov     edi, r12d
0x180060bff  movsd   xmm0, qword ptr cs:aThroughput+0Eh; "put"
0x180060c07  movups  xmmword ptr [rsp+0A8h+var_70], xmm1
0x180060c0c  mov     [r8], r12
0x180060c0f  movsd   qword ptr [rsp+0A8h+var_70+0Eh], xmm0
0x180060c15  cmp     qword ptr [rsi], 3
0x180060c19  jz      loc_180060DAD
0x180060c1f  test    edi, edi
0x180060c21  jnz     loc_180060DB1
0x180060c27  mov     rdx, rbx; unsigned __int16 *
0x180060c2a  call    ?_EatWhitespace@CSlowLinkConfigInfo@@AEAAPEBGPEBG@Z; CSlowLinkConfigInfo::_EatWhitespace(ushort const *)
0x180060c2f  mov     rbx, rax
0x180060c32  test    rax, rax
0x180060c35  jz      loc_180060DBD
0x180060c3b  lea     rax, [rsp+0A8h+String2]
0x180060c40  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180060c48  lea     r9d, [rdi+7]; cchCount1
0x180060c4c  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180060c51  mov     r8, rbx; lpString1
0x180060c54  lea     ecx, [rdi+7Fh]; Locale
0x180060c57  mov     edx, r13d; dwCmpFlags
0x180060c5a  call    cs:__imp_CompareStringW
0x180060c60  mov     edi, 2
0x180060c65  cmp     eax, edi
0x180060c67  jnz     short loc_180060C75
0x180060c69  mov     r14d, edi
0x180060c6c  lea     eax, [rdi+0Ch]
0x180060c6f  lea     r15d, [rdi+0Eh]
0x180060c73  jmp     short loc_180060CB1
0x180060c75  mov     r9d, 0Ah; cchCount1
0x180060c7b  mov     [rsp+0A8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180060c83  lea     rax, [rsp+0A8h+var_70]
0x180060c88  mov     r8, rbx; lpString1
0x180060c8b  mov     edx, r13d; dwCmpFlags
0x180060c8e  mov     [rsp+0A8h+lpString2], rax; lpString2
0x180060c93  lea     ecx, [r9+75h]; Locale
0x180060c97  call    cs:__imp_CompareStringW
0x180060c9d  cmp     eax, edi
0x180060c9f  jnz     loc_180060DA2
0x180060ca5  mov     eax, 14h
0x180060caa  mov     r14, r13
0x180060cad  lea     r15d, [rax-0Ch]
0x180060cb1  lea     rdx, [rax+rbx]; unsigned __int16 *
0x180060cb5  call    ?_EatWhitespace@CSlowLinkConfigInfo@@AEAAPEBGPEBG@Z; CSlowLinkConfigInfo::_EatWhitespace(ushort const *)
0x180060cba  mov     rbx, rax
0x180060cbd  test    rax, rax
0x180060cc0  jz      loc_180060DA2
0x180060cc6  mov     eax, 3Dh ; '='
0x180060ccb  cmp     ax, [rbx]
0x180060cce  jnz     loc_180060DA2
0x180060cd4  lea     rdx, [rbx+2]; unsigned __int16 *
0x180060cd8  call    ?_EatWhitespace@CSlowLinkConfigInfo@@AEAAPEBGPEBG@Z; CSlowLinkConfigInfo::_EatWhitespace(ushort const *)
0x180060cdd  mov     rbx, rax
0x180060ce0  test    rax, rax
0x180060ce3  jz      loc_180060DA2
0x180060ce9  lea     r8, [rsp+0A8h+var_78]
0x180060cee  mov     [rsp+0A8h+var_78], r12
0x180060cf3  lea     rdx, aI64i_0; "%I64i ,"
0x180060cfa  mov     rcx, rax; Buffer
0x180060cfd  call    swscanf_s
0x180060d02  cmp     eax, r13d
0x180060d05  jnz     short loc_180060D44
0x180060d07  movzx   ecx, word ptr [rbx]
0x180060d0a  mov     rax, rbx
0x180060d0d  jmp     short loc_180060D1B
0x180060d0f  cmp     cx, 2Ch ; ','
0x180060d13  jz      short loc_180060D20
0x180060d15  add     rax, rdi
0x180060d18  movzx   ecx, word ptr [rax]
0x180060d1b  test    cx, cx
0x180060d1e  jnz     short loc_180060D0F
0x180060d20  movzx   ecx, word ptr [rax]
0x180060d23  test    cx, cx
0x180060d26  jz      short loc_180060D36
0x180060d28  cmp     cx, 2Ch ; ','
0x180060d2c  jnz     short loc_180060D39
0x180060d2e  add     rax, rdi
0x180060d31  movzx   ecx, word ptr [rax]
0x180060d34  jmp     short loc_180060D39
0x180060d36  mov     ecx, r12d
0x180060d39  neg     cx
0x180060d3c  sbb     rbx, rbx
0x180060d3f  and     rbx, rax
0x180060d42  jmp     short loc_180060D8A
0x180060d44  lea     r8, [rsp+0A8h+var_78]
0x180060d49  mov     rcx, rbx; Buffer
0x180060d4c  lea     rdx, aI64i; "%I64i"
0x180060d53  call    swscanf_s
0x180060d58  cmp     eax, r13d
0x180060d5b  jnz     short loc_180060DA2
0x180060d5d  movzx   eax, word ptr [rbx]
0x180060d60  mov     rdi, rbx
0x180060d63  jmp     short loc_180060D79
0x180060d65  movzx   ecx, ax
0x180060d68  call    cs:__imp__o_iswspace
0x180060d6e  test    eax, eax
0x180060d70  jnz     short loc_180060D7E
0x180060d72  add     rdi, 2
0x180060d76  movzx   eax, word ptr [rdi]
0x180060d79  test    ax, ax
0x180060d7c  jnz     short loc_180060D65
0x180060d7e  movzx   eax, word ptr [rdi]
0x180060d81  neg     ax
0x180060d84  sbb     rbx, rbx
0x180060d87  and     rbx, rdi
0x180060d8a  mov     rax, [rsp+0A8h+var_78]
0x180060d8f  mov     ebp, r12d
0x180060d92  setz    bpl
0x180060d96  mov     [rsi+r15], rax
0x180060d9a  or      [rsi], r14
0x180060d9d  mov     edi, r12d
0x180060da0  jmp     short loc_180060DA5
0x180060da2  mov     edi, r13d
0x180060da5  test    ebp, ebp
0x180060da7  jz      loc_180060C15
0x180060dad  test    edi, edi
0x180060daf  jz      short loc_180060DBD
0x180060db1  xorps   xmm0, xmm0
0x180060db4  xor     eax, eax
0x180060db6  movups  xmmword ptr [rsi], xmm0
0x180060db9  mov     [rsi+10h], rax
0x180060dbd  test    edi, edi
0x180060dbf  mov     eax, r12d
0x180060dc2  setz    al
0x180060dc5  mov     rcx, [rsp+0A8h+var_48]
0x180060dca  xor     rcx, rsp; StackCookie
0x180060dcd  call    __security_check_cookie
0x180060dd2  mov     rbx, [rsp+0A8h+arg_0]
0x180060dda  add     rsp, 70h
0x180060dde  pop     r15
0x180060de0  pop     r14
0x180060de2  pop     r13
0x180060de4  pop     r12
0x180060de6  pop     rdi
0x180060de7  pop     rsi
0x180060de8  pop     rbp
0x180060de9  retn
```
