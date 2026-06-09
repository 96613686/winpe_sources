# NAMMGR::StriEq(char const *,char const *)

- ea: `0x18005b988`
- end: `0x18005ba8f`
- name: `?StriEq@NAMMGR@@QEAAHPEBD0@Z`
- size: `263`
- prototype: `int(NAMMGR *__hidden this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005b394`

## callees

- `0x18004d900`
- `0x180059e04`
- `0x18005b988`

## import_xrefs

- `KERNELBASE!CompareStringA` at `0x18005ba64`
- `KERNELBASE!CompareStringA` at `0x18005ba64`

## pseudocode

```c
__int64 __fastcall NAMMGR::StriEq(NAMMGR *this, const char *a2, const char *lpString2)
{
  const char *v4; // rsi
  __int64 v5; // rcx
  const char *v6; // rdi
  __int64 i; // rcx
  __int64 v8; // r9
  __int64 v9; // rdx
  char v11[256]; // [rsp+30h] [rbp-128h] BYREF

  v4 = lpString2;
  v5 = *((_QWORD *)this + 11);
  v6 = a2;
  if ( *(_DWORD *)(v5 + 1704) )
    return CompareStringA(*(_DWORD *)(v5 + 264), 0x30001u, a2, -1, lpString2, -1) != 2;
  if ( (*((_BYTE *)this + 82) & 2) == 0 )
  {
    GetInsensitiveCompTbl(*(_DWORD *)(v5 + 264), (enum tagSYSKIND)*(unsigned __int16 *)(v5 + 260), v11);
    for ( i = 0; i != 256; ++i )
      *((_DWORD *)this + i + 24) = (unsigned __int8)v11[i];
    *((_BYTE *)this + 82) |= 2u;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v6[v9] );
  do
    ++v8;
  while ( v4[v8] );
  if ( (unsigned int)v9 != v8 )
    return 1;
  while ( 1 )
  {
    if ( *((_DWORD *)this + *(unsigned __int8 *)v6 + 24) != *((_DWORD *)this + *(unsigned __int8 *)v4 + 24) )
      return (_DWORD)v9 != 0;
    if ( !(_DWORD)v9 )
      break;
    ++v6;
    ++v4;
    LODWORD(v9) = v9 - 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18005b988  push    rbx
0x18005b98a  push    rsi
0x18005b98b  push    rdi
0x18005b98c  sub     rsp, 140h
0x18005b993  mov     rax, cs:__security_cookie
0x18005b99a  xor     rax, rsp
0x18005b99d  mov     [rsp+158h+var_28], rax
0x18005b9a5  mov     rbx, rcx
0x18005b9a8  mov     rsi, r8
0x18005b9ab  mov     rcx, [rcx+58h]
0x18005b9af  mov     rdi, rdx
0x18005b9b2  cmp     dword ptr [rcx+6A8h], 0
0x18005b9b9  jnz     loc_18005BA48
0x18005b9bf  test    byte ptr [rbx+52h], 2
0x18005b9c3  jnz     short loc_18005B9F7
0x18005b9c5  movzx   edx, word ptr [rcx+104h]; enum tagSYSKIND
0x18005b9cc  lea     r8, [rsp+158h+var_128]; char *
0x18005b9d1  mov     ecx, [rcx+108h]; unsigned int
0x18005b9d7  call    ?GetInsensitiveCompTbl@@YAXKW4tagSYSKIND@@PEAD@Z; GetInsensitiveCompTbl(ulong,tagSYSKIND,char *)
0x18005b9dc  xor     ecx, ecx
0x18005b9de  movzx   eax, [rsp+rcx+158h+var_128]
0x18005b9e3  mov     [rbx+rcx*4+60h], eax
0x18005b9e7  inc     rcx
0x18005b9ea  cmp     rcx, 100h
0x18005b9f1  jnz     short loc_18005B9DE
0x18005b9f3  or      byte ptr [rbx+52h], 2
0x18005b9f7  or      r9, 0FFFFFFFFFFFFFFFFh
0x18005b9fb  mov     rdx, r9
0x18005b9fe  inc     rdx
0x18005ba01  cmp     byte ptr [rdi+rdx], 0
0x18005ba05  jnz     short loc_18005B9FE
0x18005ba07  inc     r9
0x18005ba0a  cmp     byte ptr [rsi+r9], 0
0x18005ba0f  jnz     short loc_18005BA07
0x18005ba11  mov     eax, edx
0x18005ba13  cmp     rax, r9
0x18005ba16  jz      short loc_18005BA2B
0x18005ba18  mov     eax, 1
0x18005ba1d  jmp     short loc_18005BA74
0x18005ba1f  test    edx, edx
0x18005ba21  jz      short loc_18005BA44
0x18005ba23  inc     rdi
0x18005ba26  inc     rsi
0x18005ba29  dec     edx
0x18005ba2b  movzx   eax, byte ptr [rsi]
0x18005ba2e  movzx   ecx, byte ptr [rdi]
0x18005ba31  mov     eax, [rbx+rax*4+60h]
0x18005ba35  cmp     [rbx+rcx*4+60h], eax
0x18005ba39  jz      short loc_18005BA1F
0x18005ba3b  xor     eax, eax
0x18005ba3d  test    edx, edx
0x18005ba3f  setnz   al
0x18005ba42  jmp     short loc_18005BA74
0x18005ba44  xor     eax, eax
0x18005ba46  jmp     short loc_18005BA74
0x18005ba48  mov     ecx, [rcx+108h]; Locale
0x18005ba4e  or      r9, 0FFFFFFFFFFFFFFFFh; cchCount1
0x18005ba52  mov     [rsp+158h+cchCount2], r9d; cchCount2
0x18005ba57  mov     r8, rdi; lpString1
0x18005ba5a  mov     edx, 30001h; dwCmpFlags
0x18005ba5f  mov     [rsp+158h+lpString2], rsi; lpString2
0x18005ba64  call    cs:__imp_CompareStringA
0x18005ba6a  xor     ecx, ecx
0x18005ba6c  cmp     eax, 2
0x18005ba6f  setnz   cl
0x18005ba72  mov     eax, ecx
0x18005ba74  mov     rcx, [rsp+158h+var_28]
0x18005ba7c  xor     rcx, rsp; StackCookie
0x18005ba7f  call    __security_check_cookie
0x18005ba84  add     rsp, 140h
0x18005ba8b  pop     rdi
0x18005ba8c  pop     rsi
0x18005ba8d  pop     rbx
0x18005ba8e  retn
```
