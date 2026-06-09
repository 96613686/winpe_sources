# CPDFPackage::AddCLSIDsToList(_GUID * *,ulong *)

- ea: `0x180044bf0`
- end: `0x180044d8c`
- name: `?AddCLSIDsToList@CPDFPackage@@QEAAJPEAPEAU_GUID@@PEAK@Z`
- size: `412`
- prototype: `__int64 __fastcall(CPDFPackage *this, LPVOID *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800474b0`

## callees

- `0x180044bf0`
- `0x18005551a`
- `0x180055526`
- `0x180055550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044d49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044d49`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044cec`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180044cec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044d26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180044d26`

## string_xrefs

- `0x180044c52`: `Install`
- `0x180044cc9`: `Install`

## pseudocode

```c
__int64 __fastcall CPDFPackage::AddCLSIDsToList(CPDFPackage *this, LPVOID *a2, unsigned int *a3)
{
  _QWORD *v3; // r14
  unsigned int v4; // r15d
  int v7; // r12d
  __int64 v9; // rdi
  __int64 v10; // rcx
  int v11; // eax
  int v12; // ecx
  struct _GUID *v13; // rax
  int v14; // edi
  _QWORD *v15; // rax
  __int64 v16; // rbp
  _QWORD *v17; // r14
  __int64 v18; // rdx
  struct _GUID *v19; // rax
  GUID pclsid; // [rsp+20h] [rbp-58h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 9);
  v4 = 0;
  *a2 = 0;
  *a3 = 0;
  v7 = *((_DWORD *)this + 22);
  if ( v7 <= 0 )
    goto LABEL_13;
  LODWORD(v9) = 0;
  pclsid = GUID_NULL;
  if ( !v3 )
    goto LABEL_13;
  do
  {
    v10 = v3[2];
    v3 = (_QWORD *)*v3;
    v11 = wcscmp_0(*(const wchar_t **)(v10 + 128), L"Install");
    v12 = v9 + 1;
    if ( v11 )
      v12 = v9;
    v9 = v12;
  }
  while ( v3 );
  if ( v12 <= 0 )
    goto LABEL_13;
  v13 = (struct _GUID *)CoTaskMemAlloc(saturated_mul(v12, 0x10u));
  *a2 = v13;
  if ( !v13 )
    return 2147942414LL;
  memset_0(v13, 0, 16 * v9);
  *a3 = v9;
  v14 = 0;
  v15 = (_QWORD *)*((_QWORD *)this + 9);
  if ( !v15 )
  {
LABEL_13:
    if ( *a2 || v7 <= 0 )
      return v4;
    v19 = (struct _GUID *)CoTaskMemAlloc(0x10u);
    *a2 = v19;
    if ( v19 )
    {
      *v19 = 0;
      *a3 = 1;
      return v4;
    }
    return 2147942414LL;
  }
  while ( 1 )
  {
    v16 = v15[2];
    v17 = (_QWORD *)*v15;
    if ( !wcscmp_0(*(const wchar_t **)(v16 + 128), L"Install") )
      break;
LABEL_12:
    v15 = v17;
    if ( !v17 )
      goto LABEL_13;
  }
  v4 = CLSIDFromString(*(LPCOLESTR *)(v16 + 8), &pclsid);
  if ( !v4 )
  {
    v18 = 2LL * v14++;
    *(GUID *)((char *)*a2 + 8 * v18) = pclsid;
    goto LABEL_12;
  }
  *a3 = 0;
  if ( *a2 )
  {
    CoTaskMemFree(*a2);
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180044bf0  mov     [rsp+arg_18], rbx
0x180044bf5  push    rbp
0x180044bf6  push    rsi
0x180044bf7  push    rdi
0x180044bf8  push    r12
0x180044bfa  push    r13
0x180044bfc  push    r14
0x180044bfe  push    r15
0x180044c00  sub     rsp, 40h
0x180044c04  mov     rax, cs:__security_cookie
0x180044c0b  xor     rax, rsp
0x180044c0e  mov     [rsp+78h+var_48], rax
0x180044c13  mov     r14, [rcx+48h]
0x180044c17  xor     r15d, r15d
0x180044c1a  mov     [rdx], r15
0x180044c1d  mov     rsi, r8
0x180044c20  mov     [r8], r15d
0x180044c23  mov     rbx, rdx
0x180044c26  mov     r12d, [rcx+58h]
0x180044c2a  mov     r13, rcx
0x180044c2d  test    r12d, r12d
0x180044c30  jle     loc_180044D16
0x180044c36  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180044c3d  xor     edi, edi
0x180044c3f  movdqu  xmmword ptr [rsp+78h+pclsid.Data1], xmm0
0x180044c45  test    r14, r14
0x180044c48  jz      loc_180044D16
0x180044c4e  mov     rcx, [r14+10h]
0x180044c52  lea     rdx, aInstall; "Install"
0x180044c59  mov     r14, [r14]
0x180044c5c  mov     rcx, [rcx+80h]; String1
0x180044c63  call    wcscmp_0
0x180044c68  test    eax, eax
0x180044c6a  lea     ecx, [rdi+1]
0x180044c6d  cmovnz  ecx, edi
0x180044c70  movsxd  rdi, ecx
0x180044c73  test    r14, r14
0x180044c76  jnz     short loc_180044C4E
0x180044c78  test    ecx, ecx
0x180044c7a  jle     loc_180044D16
0x180044c80  lea     rcx, [r14-1]
0x180044c84  mov     rbp, rdi
0x180044c87  lea     eax, [r14+10h]
0x180044c8b  mul     rdi
0x180044c8e  cmovb   rax, rcx
0x180044c92  mov     rcx, rax; cb
0x180044c95  call    cs:__imp_CoTaskMemAlloc
0x180044c9b  mov     [rbx], rax
0x180044c9e  test    rax, rax
0x180044ca1  jz      loc_180044D34
0x180044ca7  shl     rbp, 4
0x180044cab  xor     edx, edx; Val
0x180044cad  mov     r8, rbp; Size
0x180044cb0  mov     rcx, rax; void *
0x180044cb3  call    memset_0
0x180044cb8  mov     [rsi], edi
0x180044cba  xor     edi, edi
0x180044cbc  mov     rax, [r13+48h]
0x180044cc0  test    rax, rax
0x180044cc3  jz      short loc_180044D16
0x180044cc5  mov     rbp, [rax+10h]
0x180044cc9  lea     rdx, aInstall; "Install"
0x180044cd0  mov     r14, [rax]
0x180044cd3  mov     rcx, [rbp+80h]; String1
0x180044cda  call    wcscmp_0
0x180044cdf  test    eax, eax
0x180044ce1  jnz     short loc_180044D0E
0x180044ce3  mov     rcx, [rbp+8]; lpsz
0x180044ce7  lea     rdx, [rsp+78h+pclsid]; pclsid
0x180044cec  call    cs:__imp_CLSIDFromString
0x180044cf2  mov     r15d, eax
0x180044cf5  test    eax, eax
0x180044cf7  jnz     short loc_180044D3B
0x180044cf9  mov     rcx, [rbx]
0x180044cfc  movups  xmm0, xmmword ptr [rsp+78h+pclsid.Data1]
0x180044d01  movsxd  rdx, edi
0x180044d04  add     rdx, rdx
0x180044d07  inc     edi
0x180044d09  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x180044d0e  mov     rax, r14
0x180044d11  test    r14, r14
0x180044d14  jnz     short loc_180044CC5
0x180044d16  cmp     qword ptr [rbx], 0
0x180044d1a  jnz     short loc_180044D64
0x180044d1c  test    r12d, r12d
0x180044d1f  jle     short loc_180044D64
0x180044d21  mov     ecx, 10h; cb
0x180044d26  call    cs:__imp_CoTaskMemAlloc
0x180044d2c  mov     [rbx], rax
0x180044d2f  test    rax, rax
0x180044d32  jnz     short loc_180044D58
0x180044d34  mov     eax, 8007000Eh
0x180044d39  jmp     short loc_180044D67
0x180044d3b  mov     dword ptr [rsi], 0
0x180044d41  mov     rcx, [rbx]; pv
0x180044d44  test    rcx, rcx
0x180044d47  jz      short loc_180044D64
0x180044d49  call    cs:__imp_CoTaskMemFree
0x180044d4f  mov     qword ptr [rbx], 0
0x180044d56  jmp     short loc_180044D64
0x180044d58  xorps   xmm0, xmm0
0x180044d5b  movups  xmmword ptr [rax], xmm0
0x180044d5e  mov     dword ptr [rsi], 1
0x180044d64  mov     eax, r15d
0x180044d67  mov     rcx, [rsp+78h+var_48]
0x180044d6c  xor     rcx, rsp; StackCookie
0x180044d6f  call    __security_check_cookie
0x180044d74  mov     rbx, [rsp+78h+arg_18]
0x180044d7c  add     rsp, 40h
0x180044d80  pop     r15
0x180044d82  pop     r14
0x180044d84  pop     r13
0x180044d86  pop     r12
0x180044d88  pop     rdi
0x180044d89  pop     rsi
0x180044d8a  pop     rbp
0x180044d8b  retn
```
