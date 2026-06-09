# STRW::UrlUnescapeA(void)

- ea: `0x180012590`
- end: `0x180012828`
- name: `?UrlUnescapeA@STRW@@QEAAJXZ`
- size: `664`
- prototype: `__int64 __fastcall(STRW *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000eeb0`
- `0x180011d30`
- `0x18001d4c0`
- `0x18001ea8c`
- `0x180034b20`
- `0x180036900`
- `0x180037bf8`

## callees

- `0x180012590`
- `0x1800cc9a2`
- `0x1800cc9ba`
- `0x1800cd010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180012705`
- `KERNEL32!HeapAlloc` at `0x180012705`
- `KERNEL32!GetProcessHeap` at `0x1800126f7`
- `KERNEL32!GetProcessHeap` at `0x180012795`
- `KERNEL32!GetProcessHeap` at `0x1800126f7`
- `KERNEL32!GetProcessHeap` at `0x180012795`
- `KERNEL32!HeapFree` at `0x1800127a3`
- `KERNEL32!HeapFree` at `0x1800127a3`
- `urlmon!CreateUri` at `0x1800125c9`
- `urlmon!CreateUri` at `0x1800125c9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1800127ff`

## pseudocode

```c
__int64 __fastcall STRW::UrlUnescapeA(STRW *this)
{
  __int64 result; // rax
  const WCHAR *v3; // rcx
  HRESULT v4; // ebx
  HRESULT v5; // eax
  IUri *v6; // rcx
  _WORD *v7; // rbp
  unsigned int v8; // ebx
  __int64 v9; // rsi
  int v10; // edx
  _WORD *v11; // rcx
  SIZE_T v12; // r8
  unsigned __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // edx
  SIZE_T v16; // r14
  HANDLE ProcessHeap; // rax
  _BYTE *v18; // rax
  _BYTE *v19; // r15
  size_t v20; // r8
  __int64 v21; // rcx
  _BYTE *v22; // rax
  SIZE_T v23; // rdx
  __int64 v24; // rcx
  _BYTE *i; // rax
  SIZE_T v26; // rcx
  void *v27; // rbx
  HANDLE v28; // rax
  IUri *ppURI; // [rsp+60h] [rbp+8h] BYREF
  void *Src; // [rsp+68h] [rbp+10h] BYREF

  result = 0;
  if ( *(_DWORD *)this )
  {
    v3 = (const WCHAR *)*((_QWORD *)this + 1);
    Src = 0;
    ppURI = 0;
    v4 = CreateUri(v3, 0x3002B85u, 0, &ppURI);
    if ( v4 < 0 )
      return (unsigned int)v4;
    v5 = ((__int64 (__fastcall *)(IUri *, void **))ppURI->lpVtbl->GetAbsoluteUri)(ppURI, &Src);
    v6 = ppURI;
    v4 = v5;
    if ( ppURI )
    {
      ppURI = 0;
      ((void (__fastcall *)(IUri *))v6->lpVtbl->Release)(v6);
    }
    if ( v4 < 0 )
      return (unsigned int)v4;
    memset_0(*((void **)this + 1), 0, 2LL * *(unsigned int *)this);
    v7 = Src;
    v8 = 0;
    *(_DWORD *)this = 0;
    if ( !v7 )
      return v8;
    v9 = -1;
    do
      ++v9;
    while ( v7[v9] );
    if ( v9 )
    {
      v10 = v9;
      v11 = v7;
      if ( (_DWORD)v9 )
      {
        while ( *v11 )
        {
          ++v11;
          if ( !--v10 )
            goto LABEL_13;
        }
        v8 = -2147024809;
        goto LABEL_39;
      }
LABEL_13:
      v12 = *((_QWORD *)this + 2);
      v13 = 2 * v9 + 2;
      if ( v12 >= v13 )
        goto LABEL_36;
      ppURI = 0;
      v14 = 2 * v13;
      if ( is_mul_ok(v13, 2u) )
      {
        v15 = 0;
      }
      else
      {
        v14 = -1;
        v15 = -2147024362;
      }
      v16 = 2 * v9 + 2;
      if ( v15 >= 0 )
        v16 = v14;
      if ( v16 < 0x100 )
        v16 = 256;
      if ( v16 > v12 && v16 >= v13 )
      {
        ProcessHeap = GetProcessHeap();
        v18 = HeapAlloc(ProcessHeap, 0, v16);
        v19 = v18;
        if ( v18 )
        {
          v20 = *((_QWORD *)this + 2);
          if ( v20 )
          {
            memcpy_0(v18, *((const void **)this + 1), v20);
            v21 = *((_QWORD *)this + 2);
            v22 = &v19[v21];
            v23 = v16 - v21;
            if ( v16 != v21 )
            {
              do
              {
                *v22++ = 0;
                --v23;
              }
              while ( v23 );
            }
            v24 = *((_QWORD *)this + 2);
            for ( i = (_BYTE *)*((_QWORD *)this + 1); v24; --v24 )
              *i++ = 0;
          }
          else
          {
            v26 = v16;
            do
            {
              *v18++ = 0;
              --v26;
            }
            while ( v26 );
          }
          if ( *((_DWORD *)this + 6) )
          {
            v27 = (void *)*((_QWORD *)this + 1);
            v28 = GetProcessHeap();
            HeapFree(v28, 0, v27);
          }
          *((_DWORD *)this + 6) = 1;
          v8 = 0;
          *((_QWORD *)this + 1) = v19;
          *((_QWORD *)this + 2) = v16;
LABEL_36:
          memcpy_0((void *)(*((_QWORD *)this + 1) + 2LL * *(unsigned int *)this), v7, 2 * v9);
          *(_DWORD *)this += v9;
          v7 = Src;
          goto LABEL_39;
        }
        v7 = Src;
      }
      v8 = -2147024882;
    }
LABEL_39:
    if ( v7 )
      SysFreeString(v7);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x180012590  push    rdi
0x180012592  push    r12
0x180012594  sub     rsp, 48h
0x180012598  xor     r12d, r12d
0x18001259b  mov     rdi, rcx
0x18001259e  mov     eax, r12d
0x1800125a1  cmp     [rcx], eax
0x1800125a3  jz      loc_180012811
0x1800125a9  mov     rcx, [rcx+8]; pwzURI
0x1800125ad  lea     r9, [rsp+58h+ppURI]; ppURI
0x1800125b2  xor     r8d, r8d; dwReserved
0x1800125b5  mov     [rsp+58h+arg_10], rbx
0x1800125ba  mov     edx, 3002B85h; dwFlags
0x1800125bf  mov     [rsp+58h+Src], r12
0x1800125c4  mov     [rsp+58h+ppURI], r12
0x1800125c9  call    cs:__imp_CreateUri
0x1800125cf  mov     ebx, eax
0x1800125d1  test    eax, eax
0x1800125d3  js      loc_180012819
0x1800125d9  mov     rcx, [rsp+58h+ppURI]
0x1800125de  lea     rdx, [rsp+58h+Src]
0x1800125e3  mov     rax, [rcx]
0x1800125e6  mov     rax, [rax+38h]
0x1800125ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ef  mov     rcx, [rsp+58h+ppURI]
0x1800125f4  mov     ebx, eax
0x1800125f6  test    rcx, rcx
0x1800125f9  jz      short loc_18001260C
0x1800125fb  mov     [rsp+58h+ppURI], r12
0x180012600  mov     rax, [rcx]
0x180012603  mov     rax, [rax+10h]
0x180012607  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001260c  test    ebx, ebx
0x18001260e  js      loc_180012819
0x180012614  mov     r8d, [rdi]
0x180012617  xor     edx, edx; Val
0x180012619  mov     rcx, [rdi+8]; void *
0x18001261d  add     r8, r8; Size
0x180012620  mov     [rsp+58h+var_18], rbp
0x180012625  call    memset_0
0x18001262a  mov     rbp, [rsp+58h+Src]
0x18001262f  mov     ebx, r12d
0x180012632  mov     [rdi], r12d
0x180012635  test    rbp, rbp
0x180012638  jz      loc_180012805
0x18001263e  mov     [rsp+58h+var_20], rsi
0x180012643  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001264a  nop     word ptr [rax+rax+00h]
0x180012650  inc     rsi
0x180012653  cmp     [rbp+rsi*2+0], bx
0x180012658  jnz     short loc_180012650
0x18001265a  test    rsi, rsi
0x18001265d  jz      loc_1800127F2
0x180012663  mov     edx, esi
0x180012665  mov     rcx, rbp
0x180012668  test    esi, esi
0x18001266a  jz      short loc_18001267F
0x18001266c  nop     dword ptr [rax+00h]
0x180012670  cmp     r12w, [rcx]
0x180012674  jz      short loc_1800126BA
0x180012676  add     rcx, 2
0x18001267a  add     edx, 0FFFFFFFFh
0x18001267d  jnz     short loc_180012670
0x18001267f  mov     r8, [rdi+10h]
0x180012683  mov     [rsp+58h+var_28], r13
0x180012688  lea     r13, [rsi+rsi]
0x18001268c  lea     rcx, [r13+2]
0x180012690  mov     [rsp+58h+var_30], r14
0x180012695  mov     [rsp+58h+var_38], r15
0x18001269a  cmp     r8, rcx
0x18001269d  jnb     loc_1800127BB
0x1800126a3  mov     eax, 2
0x1800126a8  mov     [rsp+58h+ppURI], r12
0x1800126ad  mul     rcx
0x1800126b0  test    rdx, rdx
0x1800126b3  jnz     short loc_1800126C4
0x1800126b5  mov     edx, r12d
0x1800126b8  jmp     short loc_1800126D0
0x1800126ba  mov     ebx, 80070057h
0x1800126bf  jmp     loc_1800127F2
0x1800126c4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800126cb  mov     edx, 80070216h
0x1800126d0  test    edx, edx
0x1800126d2  mov     r14, rcx
0x1800126d5  cmovns  r14, rax
0x1800126d9  mov     eax, 100h
0x1800126de  cmp     r14, rax
0x1800126e1  cmovb   r14, rax
0x1800126e5  cmp     r14, r8
0x1800126e8  jbe     loc_1800127DE
0x1800126ee  cmp     r14, rcx
0x1800126f1  jb      loc_1800127DE
0x1800126f7  call    cs:__imp_GetProcessHeap
0x1800126fd  mov     r8, r14; dwBytes
0x180012700  xor     edx, edx; dwFlags
0x180012702  mov     rcx, rax; hHeap
0x180012705  call    cs:__imp_HeapAlloc
0x18001270b  mov     r15, rax
0x18001270e  test    rax, rax
0x180012711  jz      loc_1800127D9
0x180012717  mov     r8, [rdi+10h]; Size
0x18001271b  test    r8, r8
0x18001271e  jz      short loc_18001276E
0x180012720  mov     rdx, [rdi+8]; Src
0x180012724  mov     rcx, rax; void *
0x180012727  call    memcpy_0
0x18001272c  mov     rcx, [rdi+10h]
0x180012730  mov     rdx, r14
0x180012733  lea     rax, [rcx+r15]
0x180012737  sub     rdx, rcx
0x18001273a  jz      short loc_18001274C
0x18001273c  nop     dword ptr [rax+00h]
0x180012740  mov     [rax], bl
0x180012742  lea     rax, [rax+1]
0x180012746  sub     rdx, 1
0x18001274a  jnz     short loc_180012740
0x18001274c  mov     rcx, [rdi+10h]
0x180012750  mov     rax, [rdi+8]
0x180012754  test    rcx, rcx
0x180012757  jz      short loc_18001278C
0x180012759  nop     dword ptr [rax+00000000h]
0x180012760  mov     [rax], bl
0x180012762  lea     rax, [rax+1]
0x180012766  sub     rcx, 1
0x18001276a  jnz     short loc_180012760
0x18001276c  jmp     short loc_18001278C
0x18001276e  mov     rcx, r14
0x180012771  test    r14, r14
0x180012774  jz      short loc_18001278C
0x180012776  nop     word ptr [rax+rax+00000000h]
0x180012780  mov     [rax], bl
0x180012782  lea     rax, [rax+1]
0x180012786  sub     rcx, 1
0x18001278a  jnz     short loc_180012780
0x18001278c  cmp     [rdi+18h], ebx
0x18001278f  jz      short loc_1800127A9
0x180012791  mov     rbx, [rdi+8]
0x180012795  call    cs:__imp_GetProcessHeap
0x18001279b  mov     r8, rbx; lpMem
0x18001279e  xor     edx, edx; dwFlags
0x1800127a0  mov     rcx, rax; hHeap
0x1800127a3  call    cs:__imp_HeapFree
0x1800127a9  mov     dword ptr [rdi+18h], 1
0x1800127b0  mov     ebx, r12d
0x1800127b3  mov     [rdi+8], r15
0x1800127b7  mov     [rdi+10h], r14
0x1800127bb  mov     ecx, [rdi]
0x1800127bd  mov     r8, r13; Size
0x1800127c0  mov     rax, [rdi+8]
0x1800127c4  mov     rdx, rbp; Src
0x1800127c7  lea     rcx, [rax+rcx*2]; void *
0x1800127cb  call    memcpy_0
0x1800127d0  add     [rdi], esi
0x1800127d2  mov     rbp, [rsp+58h+Src]
0x1800127d7  jmp     short loc_1800127E3
0x1800127d9  mov     rbp, [rsp+58h+Src]
0x1800127de  mov     ebx, 8007000Eh
0x1800127e3  mov     r14, [rsp+58h+var_30]
0x1800127e8  mov     r13, [rsp+58h+var_28]
0x1800127ed  mov     r15, [rsp+58h+var_38]
0x1800127f2  mov     rsi, [rsp+58h+var_20]
0x1800127f7  test    rbp, rbp
0x1800127fa  jz      short loc_180012805
0x1800127fc  mov     rcx, rbp; bstrString
0x1800127ff  call    cs:__imp_SysFreeString
0x180012805  mov     rbp, [rsp+58h+var_18]
0x18001280a  mov     eax, ebx
0x18001280c  mov     rbx, [rsp+58h+arg_10]
0x180012811  add     rsp, 48h
0x180012815  pop     r12
0x180012817  pop     rdi
0x180012818  retn
0x180012819  mov     eax, ebx
0x18001281b  mov     rbx, [rsp+58h+arg_10]
0x180012820  add     rsp, 48h
0x180012824  pop     r12
0x180012826  pop     rdi
0x180012827  retn
```
