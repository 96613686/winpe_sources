# CCOMComponentRegistrar::AddCLSIDInternal(_GUID const &,ushort const *,ulong,long,long,long,CompInfo1 * *,_GUID const &)

- ea: `0x18002d1a0`
- end: `0x18002d395`
- name: `?AddCLSIDInternal@CCOMComponentRegistrar@@EEAAJAEBU_GUID@@PEBGKJJJPEAPEAUCompInfo1@@0@Z`
- size: `501`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *this, const struct _GUID *, OLECHAR *, int, int, int, int, struct CompInfo1 **, const struct _GUID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002ce98`
- `0x18002d1a0`
- `0x18003188c`
- `0x180055880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d2e0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002d2e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d23c`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18002d2f8`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18002d2f8`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18002d253`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18002d253`

## pseudocode

```c
__int64 __fastcall CCOMComponentRegistrar::AddCLSIDInternal(
        CCOMComponentRegistrar *this,
        const struct _GUID *a2,
        OLECHAR *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        struct CompInfo1 **a8,
        const struct _GUID *a9)
{
  int v9; // esi
  struct CompInfo1 **v13; // rdi
  int v14; // r14d
  int i; // edx
  char *v16; // rbx
  __int64 v17; // rax
  char *v18; // rax
  __int64 *v19; // rdx
  __int64 v20; // rsi
  OLECHAR *v21; // rdx
  unsigned int v22; // edx
  __int64 v24; // [rsp+0h] [rbp-138h] BYREF
  int v25; // [rsp+20h] [rbp-118h]
  int v26; // [rsp+28h] [rbp-110h] BYREF
  char *v27; // [rsp+30h] [rbp-108h]
  struct CompInfo1 **v28; // [rsp+38h] [rbp-100h]
  char *v29; // [rsp+40h] [rbp-F8h]
  OLECHAR sz[80]; // [rsp+50h] [rbp-E8h] BYREF

  v9 = a4;
  v25 = a4;
  v13 = a8;
  v28 = a8;
  *a8 = 0;
  v14 = 1;
  v26 = 1;
  v27 = 0;
  for ( i = 0; i < *((_DWORD *)this + 30); ++i )
  {
    v16 = *(char **)(*((_QWORD *)this + 14) + 8LL * i);
    v17 = *(_QWORD *)&a2->Data1 - *(_QWORD *)v16;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)v16 )
      v17 = *(_QWORD *)a2->Data4 - *((_QWORD *)v16 + 1);
    if ( !v17 )
    {
      v27 = *(char **)(*((_QWORD *)this + 14) + 8LL * i);
      goto LABEL_14;
    }
  }
  v14 = 0;
  v18 = (char *)CoTaskMemAlloc(0x70u);
  v16 = v18;
  v29 = v18;
  if ( v18 )
  {
    CString::CString((CString *)(v18 + 16));
    *((_QWORD *)v16 + 5) = &CArray<_GUID,_GUID &>::`vftable';
    *((_QWORD *)v16 + 6) = 0;
    *(_QWORD *)(v16 + 60) = 0;
    *((_DWORD *)v16 + 14) = 0;
  }
  else
  {
    v16 = 0;
  }
  v27 = v16;
  if ( !v16 )
  {
LABEL_25:
    CPtr<CompInfo1>::~CPtr<CompInfo1>((__int64)&v26, (unsigned int)v19);
    return 2147942414LL;
  }
  v20 = *((int *)this + 30);
  if ( (int)v20 >= 0 )
  {
    try
    {
      CArray<CompInfo1 *,CompInfo1 * const &>::SetSize((char *)this + 104, (unsigned int)(v20 + 1));
      *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v20) = v16;
    }
    catch ( ... )
    {
      v19 = &v24;
      goto LABEL_25;
    }
  }
  *(struct _GUID *)(v16 + 76) = *a9;
  v13 = v28;
  v9 = v25;
LABEL_14:
  *(struct _GUID *)v16 = *a2;
  if ( a3 && *a3 )
  {
    v21 = a3;
  }
  else
  {
    if ( !StringFromGUID2(a2, sz, 80) )
      sz[0] = 0;
    v21 = sz;
  }
  CString::operator=(v16 + 16, v21);
  *((_DWORD *)v16 + 9) = v9;
  *((_DWORD *)v16 + 6) = a6;
  *((_DWORD *)v16 + 7) = a7;
  if ( !v14
    || *((int *)v16 + 8) < 0
    || (_mm_lfence(), (*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 10) + 8LL * *((int *)v16 + 8)) + 12LL) & 0x2000) == 0) )
  {
    *((_DWORD *)v16 + 8) = a5;
  }
  *((_DWORD *)v16 + 18) = 0;
  v26 = 0;
  *v13 = (struct CompInfo1 *)v16;
  CPtr<CompInfo1>::~CPtr<CompInfo1>((__int64)&v26, v22);
  return 0;
}

```

## disassembly

```asm
0x18002d1a0  push    rbx
0x18002d1a2  push    rsi
0x18002d1a3  push    rdi
0x18002d1a4  push    r12
0x18002d1a6  push    r13
0x18002d1a8  push    r14
0x18002d1aa  push    r15
0x18002d1ac  sub     rsp, 100h
0x18002d1b3  mov     rax, cs:__security_cookie
0x18002d1ba  xor     rax, rsp
0x18002d1bd  mov     [rsp+138h+var_48], rax
0x18002d1c5  mov     esi, r9d
0x18002d1c8  mov     [rsp+138h+var_118], r9d
0x18002d1cd  mov     r12, r8
0x18002d1d0  mov     r15, rdx
0x18002d1d3  mov     r13, rcx
0x18002d1d6  mov     rdi, [rsp+138h+arg_38]
0x18002d1de  mov     [rsp+138h+var_100], rdi
0x18002d1e3  mov     qword ptr [rdi], 0
0x18002d1ea  mov     r14d, 1
0x18002d1f0  mov     [rsp+138h+var_110], r14d
0x18002d1f5  mov     [rsp+138h+var_108], 0
0x18002d1fe  xor     edx, edx
0x18002d200  cmp     edx, [r13+78h]
0x18002d204  jge     short loc_18002D235
0x18002d206  movsxd  rcx, edx
0x18002d209  mov     rax, [r13+70h]
0x18002d20d  mov     rbx, [rax+rcx*8]
0x18002d211  mov     rax, [r15]
0x18002d214  sub     rax, [rbx]
0x18002d217  jnz     short loc_18002D221
0x18002d219  mov     rax, [r15+8]
0x18002d21d  sub     rax, [rbx+8]
0x18002d221  test    rax, rax
0x18002d224  jz      short loc_18002D22B
0x18002d226  add     edx, r14d
0x18002d229  jmp     short loc_18002D200
0x18002d22b  mov     [rsp+138h+var_108], rbx
0x18002d230  jmp     loc_18002D2B7
0x18002d235  xor     r14d, r14d
0x18002d238  lea     ecx, [r14+70h]; cb
0x18002d23c  call    cs:__imp_CoTaskMemAlloc
0x18002d242  mov     rbx, rax
0x18002d245  mov     [rsp+138h+var_F8], rax
0x18002d24a  test    rax, rax
0x18002d24d  jz      short loc_18002D272
0x18002d24f  lea     rcx, [rax+10h]
0x18002d253  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18002d259  lea     rax, ??_7?$CArray@U_GUID@@AEAU1@@@6B@; const CArray<_GUID,_GUID &>::`vftable'
0x18002d260  mov     [rbx+28h], rax
0x18002d264  mov     [rbx+30h], r14
0x18002d268  mov     [rbx+3Ch], r14
0x18002d26c  mov     [rbx+38h], r14d
0x18002d270  jmp     short loc_18002D274
0x18002d272  xor     ebx, ebx
0x18002d274  mov     [rsp+138h+var_108], rbx
0x18002d279  test    rbx, rbx
0x18002d27c  jz      loc_18002D363
0x18002d282  movsxd  rsi, dword ptr [r13+78h]
0x18002d286  test    esi, esi
0x18002d288  js      short loc_18002D29E
0x18002d28a  lea     edx, [rsi+1]
0x18002d28d  lea     rcx, [r13+68h]
0x18002d291  call    ?SetSize@?$CArray@PEAUCompInfo1@@AEBQEAU1@@@QEAAXHH@Z; CArray<CompInfo1 *,CompInfo1 * const &>::SetSize(int,int)
0x18002d296  mov     rax, [r13+70h]
0x18002d29a  mov     [rax+rsi*8], rbx
0x18002d29e  mov     rax, [rsp+138h+arg_40]
0x18002d2a6  movups  xmm0, xmmword ptr [rax]
0x18002d2a9  movdqu  xmmword ptr [rbx+4Ch], xmm0
0x18002d2ae  mov     rdi, [rsp+138h+var_100]
0x18002d2b3  mov     esi, [rsp+138h+var_118]
0x18002d2b7  movups  xmm0, xmmword ptr [r15]
0x18002d2bb  movdqu  xmmword ptr [rbx], xmm0
0x18002d2bf  test    r12, r12
0x18002d2c2  jz      short loc_18002D2D2
0x18002d2c4  xor     eax, eax
0x18002d2c6  cmp     [r12], ax
0x18002d2cb  jz      short loc_18002D2D2
0x18002d2cd  mov     rdx, r12
0x18002d2d0  jmp     short loc_18002D2F4
0x18002d2d2  mov     r8d, 50h ; 'P'; cchMax
0x18002d2d8  lea     rdx, [rsp+138h+sz]; lpsz
0x18002d2dd  mov     rcx, r15; rguid
0x18002d2e0  call    cs:__imp_StringFromGUID2
0x18002d2e6  test    eax, eax
0x18002d2e8  jnz     short loc_18002D2EF
0x18002d2ea  mov     [rsp+138h+sz], ax
0x18002d2ef  lea     rdx, [rsp+138h+sz]
0x18002d2f4  lea     rcx, [rbx+10h]
0x18002d2f8  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18002d2fe  mov     [rbx+24h], esi
0x18002d301  mov     eax, [rsp+138h+arg_28]
0x18002d308  mov     [rbx+18h], eax
0x18002d30b  mov     eax, [rsp+138h+arg_30]
0x18002d312  mov     [rbx+1Ch], eax
0x18002d315  test    r14d, r14d
0x18002d318  jz      short loc_18002D339
0x18002d31a  movsxd  rax, dword ptr [rbx+20h]
0x18002d31e  test    eax, eax
0x18002d320  js      short loc_18002D339
0x18002d322  lfence
0x18002d325  mov     rcx, rax
0x18002d328  mov     rax, [r13+50h]
0x18002d32c  mov     rcx, [rax+rcx*8]
0x18002d330  test    dword ptr [rcx+0Ch], 2000h
0x18002d337  jnz     short loc_18002D343
0x18002d339  mov     eax, [rsp+138h+arg_20]
0x18002d340  mov     [rbx+20h], eax
0x18002d343  mov     dword ptr [rbx+48h], 0
0x18002d34a  mov     [rsp+138h+var_110], 0
0x18002d352  mov     [rdi], rbx
0x18002d355  lea     rcx, [rsp+138h+var_110]
0x18002d35a  call    ??1?$CPtr@UCompInfo1@@@@QEAA@XZ; CPtr<CompInfo1>::~CPtr<CompInfo1>(void)
0x18002d35f  xor     eax, eax
0x18002d361  jmp     short loc_18002D372
0x18002d363  lea     rcx, [rsp+138h+var_110]
0x18002d368  call    ??1?$CPtr@UCompInfo1@@@@QEAA@XZ; CPtr<CompInfo1>::~CPtr<CompInfo1>(void)
0x18002d36d  mov     eax, 8007000Eh
0x18002d372  mov     rcx, [rsp+138h+var_48]
0x18002d37a  xor     rcx, rsp; StackCookie
0x18002d37d  call    __security_check_cookie
0x18002d382  add     rsp, 100h
0x18002d389  pop     r15
0x18002d38b  pop     r14
0x18002d38d  pop     r13
0x18002d38f  pop     r12
0x18002d391  pop     rdi
0x18002d392  pop     rsi
0x18002d393  pop     rbx
0x18002d394  retn
```
