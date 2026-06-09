# CCOMComponentRegistrar::AddFile(ushort * *,long,ulong)

- ea: `0x18002d3a0`
- end: `0x18002d5a0`
- name: `?AddFile@CCOMComponentRegistrar@@EEAAJPEAPEAGJK@Z`
- size: `512`
- prototype: `__int64 __fastcall(CCOMComponentRegistrar *this, unsigned __int16 **, int, __int16)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18002d3a0`
- `0x1800319dc`
- `0x18005583a`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002d422`
- `msvcrt!_wcsicmp` at `0x18002d444`
- `msvcrt!_wcsicmp` at `0x18002d509`
- `msvcrt!_wcsicmp` at `0x18002d527`
- `msvcrt!_wcsicmp` at `0x18002d422`
- `msvcrt!_wcsicmp` at `0x18002d444`
- `msvcrt!_wcsicmp` at `0x18002d509`
- `msvcrt!_wcsicmp` at `0x18002d527`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d577`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002d586`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d3d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d479`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d3d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002d479`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18002d4d9`
- `MfcSubs!??4CString@@QEAAAEBV0@PEBG@Z` at `0x18002d4d9`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18002d49c`
- `MfcSubs!??0CString@@QEAA@XZ` at `0x18002d49c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCOMComponentRegistrar::AddFile(
        CCOMComponentRegistrar *this,
        unsigned __int16 **a2,
        int a3,
        __int16 a4)
{
  int *v7; // rsi
  int v9; // ebp
  int v10; // ebx
  int i; // edi
  unsigned __int16 *v12; // rcx
  unsigned __int64 v13; // rax
  unsigned __int16 *v14; // r14
  __int64 v15; // rax
  int j; // r14d
  char *v17; // rax
  char *v18; // rdi
  unsigned __int16 *v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int16 *v21; // rbx
  __int64 v22; // rbp

  v7 = (int *)CoTaskMemAlloc(saturated_mul(a3, 4u));
  if ( !v7 )
    return 2147942414LL;
  v9 = a3 - 1;
  v10 = 0;
  for ( i = 0; i < a3; ++i )
  {
    v12 = a2[i];
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    if ( v13 < 4 )
    {
      v15 = v10++;
    }
    else
    {
      v14 = &v12[v13];
      if ( !_wcsicmp(v14 - 4, L".DLL") || _wcsicmp(v14 - 4, L".TLB") )
        v15 = v10++;
      else
        v15 = v9--;
    }
    v7[v15] = i;
  }
  for ( j = 0; j < a3; ++j )
  {
    v17 = (char *)CoTaskMemAlloc(0x40u);
    v18 = v17;
    if ( !v17 )
    {
      CoTaskMemFree(v7);
      return 2147942414LL;
    }
    memset_0(v17, 0, 0x40u);
    CString::CString((CString *)v18);
    *((_QWORD *)v18 + 2) = &CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::`vftable';
    *((_QWORD *)v18 + 3) = 0;
    *(_QWORD *)(v18 + 36) = 0;
    *((_DWORD *)v18 + 8) = 0;
    *((_QWORD *)v18 + 6) = 0;
    *((_DWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 7) = 0;
    CString::operator=(v18, a2[v7[j]]);
    v19 = a2[v7[j]];
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    if ( v20 < 4 )
      goto LABEL_23;
    v21 = &v19[v20];
    if ( !_wcsicmp(v21 - 4, L".DLL") )
    {
      *((_DWORD *)v18 + 2) = 1;
      goto LABEL_24;
    }
    if ( _wcsicmp(v21 - 4, L".TLB") )
LABEL_23:
      *((_DWORD *)v18 + 2) = 0;
    else
      *((_DWORD *)v18 + 2) = 2;
LABEL_24:
    if ( (a4 & 0x200) != 0 )
      *((_DWORD *)v18 + 3) |= 0x200000u;
    v22 = *((int *)this + 22);
    if ( (int)v22 >= 0 )
    {
      CArray<FileInfo1 *,FileInfo1 * const &>::SetSize((char *)this + 72, (unsigned int)(v22 + 1));
      *(_QWORD *)(*((_QWORD *)this + 10) + 8 * v22) = v18;
    }
  }
  CoTaskMemFree(v7);
  return 0;
}

```

## disassembly

```asm
0x18002d3a0  mov     [rsp+arg_0], rcx
0x18002d3a5  push    rbx
0x18002d3a6  push    rbp
0x18002d3a7  push    rsi
0x18002d3a8  push    rdi
0x18002d3a9  push    r12
0x18002d3ab  push    r13
0x18002d3ad  push    r14
0x18002d3af  push    r15
0x18002d3b1  sub     rsp, 28h
0x18002d3b5  mov     r13d, r9d
0x18002d3b8  movsxd  r15, r8d
0x18002d3bb  mov     r12, rdx
0x18002d3be  mov     eax, 4
0x18002d3c3  mul     r15
0x18002d3c6  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18002d3cd  cmovb   rax, r14
0x18002d3d1  mov     rcx, rax; cb
0x18002d3d4  call    cs:__imp_CoTaskMemAlloc
0x18002d3da  mov     rsi, rax
0x18002d3dd  xor     edx, edx
0x18002d3df  test    rax, rax
0x18002d3e2  jnz     short loc_18002D3EE
0x18002d3e4  mov     eax, 8007000Eh
0x18002d3e9  jmp     loc_18002D58F
0x18002d3ee  lea     ebp, [r15-1]
0x18002d3f2  mov     ebx, edx
0x18002d3f4  mov     edi, edx
0x18002d3f6  test    r15d, r15d
0x18002d3f9  jle     short loc_18002D466
0x18002d3fb  mov     eax, edi
0x18002d3fd  mov     rcx, [r12+rax*8]
0x18002d401  mov     rax, r14
0x18002d404  inc     rax
0x18002d407  cmp     [rcx+rax*2], dx
0x18002d40b  jnz     short loc_18002D404
0x18002d40d  cmp     rax, 4
0x18002d411  jb      short loc_18002D457
0x18002d413  lea     r14, [rcx+rax*2]
0x18002d417  lea     rdx, aDll; ".DLL"
0x18002d41e  lea     rcx, [r14-8]; String1
0x18002d422  call    cs:__imp__wcsicmp
0x18002d428  xor     edx, edx
0x18002d42a  test    eax, eax
0x18002d42c  jnz     short loc_18002D439
0x18002d42e  movsxd  rax, ebx
0x18002d431  inc     ebx
0x18002d433  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002d437  jmp     short loc_18002D45C
0x18002d439  lea     rdx, aTlb; ".TLB"
0x18002d440  lea     rcx, [r14-8]; String1
0x18002d444  call    cs:__imp__wcsicmp
0x18002d44a  xor     edx, edx
0x18002d44c  test    eax, eax
0x18002d44e  jnz     short loc_18002D42E
0x18002d450  movsxd  rax, ebp
0x18002d453  dec     ebp
0x18002d455  jmp     short loc_18002D433
0x18002d457  movsxd  rax, ebx
0x18002d45a  inc     ebx
0x18002d45c  mov     [rsi+rax*4], edi
0x18002d45f  inc     edi
0x18002d461  cmp     edi, r15d
0x18002d464  jl      short loc_18002D3FB
0x18002d466  xor     ebp, ebp
0x18002d468  mov     r14d, ebp
0x18002d46b  cmp     r14d, r15d
0x18002d46e  jge     loc_18002D583
0x18002d474  mov     ecx, 40h ; '@'; cb
0x18002d479  call    cs:__imp_CoTaskMemAlloc
0x18002d47f  mov     rdi, rax
0x18002d482  test    rax, rax
0x18002d485  jz      loc_18002D574
0x18002d48b  xor     edx, edx; Val
0x18002d48d  lea     r8d, [rdx+40h]; Size
0x18002d491  mov     rcx, rax; void *
0x18002d494  call    memset_0
0x18002d499  mov     rcx, rdi
0x18002d49c  call    cs:__imp_??0CString@@QEAA@XZ; CString::CString(void)
0x18002d4a2  lea     rax, ??_7?$CArray@V?$CPtr@VCComPlusTypelib@@@@PEAVCComPlusTypelib@@@@6B@; const CArray<CPtr<CComPlusTypelib>,CComPlusTypelib *>::`vftable'
0x18002d4a9  mov     [rdi+10h], rax
0x18002d4ad  mov     [rdi+18h], rbp
0x18002d4b1  mov     qword ptr [rdi+24h], 0
0x18002d4b9  mov     [rdi+20h], ebp
0x18002d4bc  mov     [rdi+30h], rbp
0x18002d4c0  mov     [rdi+0Ch], ebp
0x18002d4c3  mov     qword ptr [rdi+38h], 0
0x18002d4cb  movsxd  rbx, r14d
0x18002d4ce  movsxd  rdx, dword ptr [rsi+rbx*4]
0x18002d4d2  mov     rdx, [r12+rdx*8]
0x18002d4d6  mov     rcx, rdi
0x18002d4d9  call    cs:__imp_??4CString@@QEAAAEBV0@PEBG@Z; CString::operator=(ushort const *)
0x18002d4df  movsxd  rax, dword ptr [rsi+rbx*4]
0x18002d4e3  mov     rcx, [r12+rax*8]
0x18002d4e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002d4eb  inc     rax
0x18002d4ee  cmp     [rcx+rax*2], bp
0x18002d4f2  jnz     short loc_18002D4EB
0x18002d4f4  cmp     rax, 4
0x18002d4f8  jb      short loc_18002D53A
0x18002d4fa  lea     rbx, [rcx+rax*2]
0x18002d4fe  lea     rdx, aDll; ".DLL"
0x18002d505  lea     rcx, [rbx-8]; String1
0x18002d509  call    cs:__imp__wcsicmp
0x18002d50f  test    eax, eax
0x18002d511  jnz     short loc_18002D51C
0x18002d513  mov     dword ptr [rdi+8], 1
0x18002d51a  jmp     short loc_18002D53D
0x18002d51c  lea     rdx, aTlb; ".TLB"
0x18002d523  lea     rcx, [rbx-8]; String1
0x18002d527  call    cs:__imp__wcsicmp
0x18002d52d  test    eax, eax
0x18002d52f  jnz     short loc_18002D53A
0x18002d531  mov     dword ptr [rdi+8], 2
0x18002d538  jmp     short loc_18002D53D
0x18002d53a  mov     [rdi+8], ebp
0x18002d53d  bt      r13d, 9
0x18002d542  jnb     short loc_18002D549
0x18002d544  bts     dword ptr [rdi+0Ch], 15h
0x18002d549  mov     rbx, [rsp+68h+arg_0]
0x18002d54e  movsxd  rbp, dword ptr [rbx+58h]
0x18002d552  test    ebp, ebp
0x18002d554  js      short loc_18002D56A
0x18002d556  lea     edx, [rbp+1]
0x18002d559  lea     rcx, [rbx+48h]
0x18002d55d  call    ?SetSize@?$CArray@PEAUFileInfo1@@AEBQEAU1@@@QEAAXHH@Z; CArray<FileInfo1 *,FileInfo1 * const &>::SetSize(int,int)
0x18002d562  mov     rax, [rbx+50h]
0x18002d566  mov     [rax+rbp*8], rdi
0x18002d56a  inc     r14d
0x18002d56d  xor     ebp, ebp
0x18002d56f  jmp     loc_18002D46B
0x18002d574  mov     rcx, rsi; pv
0x18002d577  call    cs:__imp_CoTaskMemFree
0x18002d57d  nop
0x18002d57e  jmp     loc_18002D3E4
0x18002d583  mov     rcx, rsi; pv
0x18002d586  call    cs:__imp_CoTaskMemFree
0x18002d58c  nop
0x18002d58d  xor     eax, eax
0x18002d58f  add     rsp, 28h
0x18002d593  pop     r15
0x18002d595  pop     r14
0x18002d597  pop     r13
0x18002d599  pop     r12
0x18002d59b  pop     rdi
0x18002d59c  pop     rsi
0x18002d59d  pop     rbp
0x18002d59e  pop     rbx
0x18002d59f  retn
```
