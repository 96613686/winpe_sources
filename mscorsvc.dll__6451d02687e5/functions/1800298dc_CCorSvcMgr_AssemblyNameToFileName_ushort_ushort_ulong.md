# CCorSvcMgr::AssemblyNameToFileName(ushort *,ushort *,ulong)

- ea: `0x1800298dc`
- end: `0x180029cb0`
- name: `?AssemblyNameToFileName@CCorSvcMgr@@AEAAXPEAG0K@Z`
- size: `980`
- prototype: `void __fastcall(CCorSvcMgr *this, unsigned __int16 *, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180028bdc`

## callees

- `0x1800298dc`
- `0x1800304ec`
- `0x180030568`
- `0x180034fd4`
- `0x18003f280`

## import_xrefs

- `fusion!CreateAssemblyCache` at `0x180029924`
- `fusion!CreateAssemblyCache` at `0x180029924`
- `fusion!InitializeFusion` at `0x180029911`
- `fusion!InitializeFusion` at `0x180029911`
- `fusion!CreateAssemblyNameObject` at `0x1800299a0`
- `fusion!CreateAssemblyNameObject` at `0x1800299a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CCorSvcMgr::AssemblyNameToFileName(
        CCorSvcMgr *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        int a4)
{
  IAssemblyCache **v6; // rdi
  int v7; // eax
  HRESULT AssemblyCache; // eax
  int v9; // eax
  HRESULT v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  LPASSEMBLYNAME *v15; // rsi
  BOOL v16; // ebx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  LPASSEMBLYNAME *v21; // r14
  int v22; // eax
  int v23; // eax
  unsigned int v24; // [rsp+34h] [rbp-4Ch] BYREF
  LPASSEMBLYNAME *p_ppAssemblyNameObj; // [rsp+38h] [rbp-48h] BYREF
  BOOL v26; // [rsp+40h] [rbp-40h]
  LPASSEMBLYNAME ppAssemblyNameObj; // [rsp+48h] [rbp-38h] BYREF
  int v28; // [rsp+50h] [rbp-30h]
  int v29; // [rsp+58h] [rbp-28h] BYREF
  __int64 v30; // [rsp+5Ch] [rbp-24h]
  int v31; // [rsp+64h] [rbp-1Ch]
  unsigned __int16 *v32; // [rsp+68h] [rbp-18h]
  __int64 v33; // [rsp+70h] [rbp-10h]
  unsigned int v34; // [rsp+C0h] [rbp+40h] BYREF
  int v35; // [rsp+D8h] [rbp+58h] BYREF

  v35 = a4;
  v6 = (IAssemblyCache **)((char *)this + 96);
  if ( !*((_QWORD *)this + 12) )
  {
    v7 = InitializeFusion();
    if ( v7 < 0 )
      ThrowHR(v7);
    AssemblyCache = CreateAssemblyCache(v6, 0);
    if ( AssemblyCache < 0 )
      ThrowHR(AssemblyCache);
  }
  v30 = 0;
  v31 = 0;
  v33 = 260;
  v29 = 32;
  v32 = a3;
  v9 = ((__int64 (__fastcall *)(IAssemblyCache *, _QWORD, unsigned __int16 *, int *))(*v6)->lpVtbl->QueryAssemblyInfo)(
         *v6,
         0,
         a2,
         &v29);
  if ( v9 == -2147024894 )
  {
    v28 = 0;
    p_ppAssemblyNameObj = &ppAssemblyNameObj;
    ppAssemblyNameObj = 0;
    v10 = CreateAssemblyNameObject(&ppAssemblyNameObj, a2, 1u, 0);
    if ( v10 < 0 )
      ThrowHR(v10);
    v11 = v28;
    if ( ppAssemblyNameObj )
      v11 = 1;
    v28 = v11;
    LODWORD(p_ppAssemblyNameObj) = -1163005939;
    v24 = 4;
    v12 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, __int64, LPASSEMBLYNAME **, unsigned int *))ppAssemblyNameObj->lpVtbl->GetProperty)(
            ppAssemblyNameObj,
            27,
            &p_ppAssemblyNameObj,
            &v24);
    if ( v12 < 0 )
      ThrowHR(v12);
    if ( v24 )
      ThrowHR(-2147024894);
    v35 = 4;
    v13 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, __int64, int *, __int64))ppAssemblyNameObj->lpVtbl->SetProperty)(
            ppAssemblyNameObj,
            27,
            &v35,
            4);
    if ( v13 < 0 )
      ThrowHR(v13);
    v24 = 0;
    v14 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, _QWORD, unsigned int *, __int64))ppAssemblyNameObj->lpVtbl->GetDisplayName)(
            ppAssemblyNameObj,
            0,
            &v24,
            1191);
    if ( v14 != -2147024774 )
      ThrowHR(v14);
    v34 = v24;
    v15 = (LPASSEMBLYNAME *)operator new(saturated_mul(v24, 2u));
    p_ppAssemblyNameObj = v15;
    v16 = v15 != 0;
    v26 = v16;
    v17 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, LPASSEMBLYNAME *, unsigned int *, __int64))ppAssemblyNameObj->lpVtbl->GetDisplayName)(
            ppAssemblyNameObj,
            v15,
            &v34,
            1191);
    if ( v17 < 0 )
      ThrowHR(v17);
    v30 = 0;
    v31 = 0;
    v33 = 260;
    v29 = 32;
    v32 = a3;
    v18 = ((__int64 (__fastcall *)(IAssemblyCache *, _QWORD, LPASSEMBLYNAME *, int *))(*v6)->lpVtbl->QueryAssemblyInfo)(
            *v6,
            0,
            v15,
            &v29);
    if ( v18 == -2147024894 )
    {
      v35 = 1;
      v19 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, __int64, int *, __int64))ppAssemblyNameObj->lpVtbl->SetProperty)(
              ppAssemblyNameObj,
              27,
              &v35,
              4);
      if ( v19 < 0 )
        ThrowHR(v19);
      v24 = 0;
      v20 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, _QWORD, unsigned int *, __int64))ppAssemblyNameObj->lpVtbl->GetDisplayName)(
              ppAssemblyNameObj,
              0,
              &v24,
              1191);
      if ( v20 != -2147024774 )
        ThrowHR(v20);
      v34 = v24;
      v21 = (LPASSEMBLYNAME *)operator new(saturated_mul(v24, 2u));
      if ( v15 )
      {
        operator delete(v15);
        v16 = 0;
        v26 = 0;
      }
      v15 = v21;
      p_ppAssemblyNameObj = v21;
      if ( v21 )
        v16 = 1;
      v26 = v16;
      v22 = ((__int64 (__fastcall *)(LPASSEMBLYNAME, LPASSEMBLYNAME *, unsigned int *, __int64))ppAssemblyNameObj->lpVtbl->GetDisplayName)(
              ppAssemblyNameObj,
              v21,
              &v34,
              1191);
      if ( v22 < 0 )
        ThrowHR(v22);
      v30 = 0;
      v31 = 0;
      v33 = 260;
      v29 = 32;
      v32 = a3;
      v23 = ((__int64 (__fastcall *)(IAssemblyCache *, _QWORD, LPASSEMBLYNAME *, int *))(*v6)->lpVtbl->QueryAssemblyInfo)(
              *v6,
              0,
              v21,
              &v29);
      if ( v23 < 0 )
        ThrowHR(v23);
    }
    else if ( v18 < 0 )
    {
      ThrowHR(v18);
    }
    if ( v16 )
    {
      operator delete(v15);
      v26 = 0;
    }
    if ( v28 )
    {
      if ( ppAssemblyNameObj )
        ((void (__fastcall *)(LPASSEMBLYNAME))ppAssemblyNameObj->lpVtbl->Release)(ppAssemblyNameObj);
      v28 = 0;
    }
  }
  else if ( v9 < 0 )
  {
    ThrowHR(v9);
  }
}

```

## disassembly

```asm
0x1800298dc  mov     [rsp-38h+arg_8], rbx
0x1800298e1  mov     [rsp-38h+arg_18], r9d
0x1800298e6  push    rbp
0x1800298e7  push    rsi
0x1800298e8  push    rdi
0x1800298e9  push    r12
0x1800298eb  push    r13
0x1800298ed  push    r14
0x1800298ef  push    r15
0x1800298f1  mov     rbp, rsp
0x1800298f4  sub     rsp, 80h
0x1800298fb  mov     r15, r8
0x1800298fe  mov     rbx, rdx
0x180029901  xor     r12d, r12d
0x180029904  mov     [rbp+var_50], r12d
0x180029908  lea     rdi, [rcx+60h]
0x18002990c  cmp     [rdi], r12
0x18002990f  jnz     short loc_180029932
0x180029911  call    cs:__imp_InitializeFusion
0x180029917  test    eax, eax
0x180029919  js      loc_180029C57
0x18002991f  xor     edx, edx; dwReserved
0x180029921  mov     rcx, rdi; ppAsmCache
0x180029924  call    cs:__imp_CreateAssemblyCache
0x18002992a  test    eax, eax
0x18002992c  js      loc_180029C5F
0x180029932  mov     [rbp+var_24], r12
0x180029936  mov     [rbp+var_1C], r12d
0x18002993a  mov     [rbp+var_10], 104h
0x180029942  mov     [rbp+var_28], 20h ; ' '
0x180029949  mov     [rbp+var_18], r15
0x18002994d  mov     rcx, [rdi]
0x180029950  mov     rax, [rcx]
0x180029953  lea     r9, [rbp+var_28]
0x180029957  mov     r8, rbx
0x18002995a  xor     edx, edx
0x18002995c  mov     rax, [rax+20h]
0x180029960  call    cs:__guard_dispatch_icall_fptr
0x180029966  mov     r14d, 80070002h
0x18002996c  cmp     eax, r14d
0x18002996f  jnz     loc_180029C39
0x180029975  mov     [rbp+ppAssemblyNameObj], r12
0x180029979  mov     [rbp+var_30], r12d
0x18002997d  lea     rax, [rbp+ppAssemblyNameObj]
0x180029981  mov     [rbp+var_48], rax
0x180029985  mov     [rbp+ppAssemblyNameObj], r12
0x180029989  mov     r13d, 1
0x18002998f  mov     [rbp+var_50], r13d
0x180029993  xor     r9d, r9d; pvReserved
0x180029996  mov     r8d, r13d; dwFlags
0x180029999  mov     rdx, rbx; szAssemblyName
0x18002999c  lea     rcx, [rbp+ppAssemblyNameObj]; ppAssemblyNameObj
0x1800299a0  call    cs:__imp_CreateAssemblyNameObject
0x1800299a6  test    eax, eax
0x1800299a8  js      loc_180029C67
0x1800299ae  mov     eax, r13d
0x1800299b1  and     eax, 0FFFFFFFEh
0x1800299b4  mov     [rbp+var_50], eax
0x1800299b7  mov     eax, [rbp+var_30]
0x1800299ba  mov     rcx, [rbp+ppAssemblyNameObj]
0x1800299be  test    rcx, rcx
0x1800299c1  cmovnz  eax, r13d
0x1800299c5  mov     [rbp+var_30], eax
0x1800299c8  mov     dword ptr [rbp+var_48], 0BAADF00Dh
0x1800299cf  lea     ebx, [r13+3]
0x1800299d3  mov     [rbp+var_4C], ebx
0x1800299d6  mov     rax, [rcx]
0x1800299d9  lea     r9, [rbp+var_4C]
0x1800299dd  lea     r8, [rbp+var_48]
0x1800299e1  lea     esi, [rbx+17h]
0x1800299e4  mov     edx, esi
0x1800299e6  mov     rax, [rax+20h]
0x1800299ea  call    cs:__guard_dispatch_icall_fptr
0x1800299f0  test    eax, eax
0x1800299f2  js      loc_180029C6F
0x1800299f8  cmp     [rbp+var_4C], r12d
0x1800299fc  jnz     loc_180029C77
0x180029a02  mov     [rbp+arg_18], ebx
0x180029a05  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029a09  mov     rax, [rcx]
0x180029a0c  mov     r9d, ebx
0x180029a0f  lea     r8, [rbp+arg_18]
0x180029a13  mov     edx, esi
0x180029a15  mov     rax, [rax+18h]
0x180029a19  call    cs:__guard_dispatch_icall_fptr
0x180029a1f  test    eax, eax
0x180029a21  js      loc_180029C80
0x180029a27  mov     [rbp+var_4C], r12d
0x180029a2b  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029a2f  mov     rax, [rcx]
0x180029a32  mov     r9d, 4A7h
0x180029a38  lea     r8, [rbp+var_4C]
0x180029a3c  xor     edx, edx
0x180029a3e  mov     rax, [rax+30h]
0x180029a42  call    cs:__guard_dispatch_icall_fptr
0x180029a48  cmp     eax, 8007007Ah
0x180029a4d  jnz     loc_180029C88
0x180029a53  mov     eax, [rbp+var_4C]
0x180029a56  mov     [rbp+arg_0], eax
0x180029a59  mov     ecx, eax
0x180029a5b  lea     eax, [rbx-2]
0x180029a5e  mul     rcx
0x180029a61  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029a68  cmovo   rax, rcx
0x180029a6c  mov     rcx, rax; dwBytes
0x180029a6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029a74  mov     rsi, rax
0x180029a77  mov     [rbp+var_48], rax
0x180029a7b  mov     [rbp+var_40], r12d
0x180029a7f  mov     ebx, r12d
0x180029a82  test    rax, rax
0x180029a85  cmovnz  ebx, r13d
0x180029a89  mov     [rbp+var_40], ebx
0x180029a8c  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029a90  mov     rax, [rcx]
0x180029a93  mov     r9d, 4A7h
0x180029a99  lea     r8, [rbp+arg_0]
0x180029a9d  mov     rdx, rsi
0x180029aa0  mov     rax, [rax+30h]
0x180029aa4  call    cs:__guard_dispatch_icall_fptr
0x180029aaa  test    eax, eax
0x180029aac  js      loc_180029C90
0x180029ab2  mov     [rbp+var_24], r12
0x180029ab6  mov     [rbp+var_1C], r12d
0x180029aba  mov     [rbp+var_10], 104h
0x180029ac2  mov     [rbp+var_28], 20h ; ' '
0x180029ac9  mov     [rbp+var_18], r15
0x180029acd  mov     rcx, [rdi]
0x180029ad0  mov     rax, [rcx]
0x180029ad3  lea     r9, [rbp+var_28]
0x180029ad7  mov     r8, rsi
0x180029ada  xor     edx, edx
0x180029adc  mov     rax, [rax+20h]
0x180029ae0  call    cs:__guard_dispatch_icall_fptr
0x180029ae6  cmp     eax, r14d
0x180029ae9  jnz     loc_180029BEA
0x180029aef  mov     [rbp+arg_18], r13d
0x180029af3  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029af7  mov     rax, [rcx]
0x180029afa  lea     r9d, [r13+3]
0x180029afe  lea     r8, [rbp+arg_18]
0x180029b02  lea     edx, [r13+1Ah]
0x180029b06  mov     rax, [rax+18h]
0x180029b0a  call    cs:__guard_dispatch_icall_fptr
0x180029b10  test    eax, eax
0x180029b12  js      loc_180029C98
0x180029b18  mov     [rbp+var_4C], r12d
0x180029b1c  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029b20  mov     rax, [rcx]
0x180029b23  mov     r9d, 4A7h
0x180029b29  lea     r8, [rbp+var_4C]
0x180029b2d  xor     edx, edx
0x180029b2f  mov     rax, [rax+30h]
0x180029b33  call    cs:__guard_dispatch_icall_fptr
0x180029b39  cmp     eax, 8007007Ah
0x180029b3e  jnz     loc_180029CA0
0x180029b44  mov     ecx, [rbp+var_4C]
0x180029b47  mov     [rbp+arg_0], ecx
0x180029b4a  lea     eax, [r13+1]
0x180029b4e  mul     rcx
0x180029b51  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180029b58  cmovo   rax, rcx
0x180029b5c  mov     rcx, rax; dwBytes
0x180029b5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029b64  mov     r14, rax
0x180029b67  test    ebx, ebx
0x180029b69  jz      short loc_180029B79
0x180029b6b  mov     rcx, rsi; lpMem
0x180029b6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029b73  mov     ebx, r12d
0x180029b76  mov     [rbp+var_40], ebx
0x180029b79  mov     rsi, r14
0x180029b7c  mov     [rbp+var_48], r14
0x180029b80  test    r14, r14
0x180029b83  cmovnz  ebx, r13d
0x180029b87  mov     [rbp+var_40], ebx
0x180029b8a  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029b8e  mov     rax, [rcx]
0x180029b91  mov     r9d, 4A7h
0x180029b97  lea     r8, [rbp+arg_0]
0x180029b9b  mov     rdx, r14
0x180029b9e  mov     rax, [rax+30h]
0x180029ba2  call    cs:__guard_dispatch_icall_fptr
0x180029ba8  test    eax, eax
0x180029baa  js      loc_180029CA8
0x180029bb0  mov     [rbp+var_24], r12
0x180029bb4  mov     [rbp+var_1C], r12d
0x180029bb8  mov     [rbp+var_10], 104h
0x180029bc0  mov     [rbp+var_28], 20h ; ' '
0x180029bc7  mov     [rbp+var_18], r15
0x180029bcb  mov     rcx, [rdi]
0x180029bce  mov     rax, [rcx]
0x180029bd1  lea     r9, [rbp+var_28]
0x180029bd5  mov     r8, r14
0x180029bd8  xor     edx, edx
0x180029bda  mov     rax, [rax+20h]
0x180029bde  call    cs:__guard_dispatch_icall_fptr
0x180029be4  test    eax, eax
0x180029be6  js      short loc_180029C47
0x180029be8  jmp     short loc_180029BEE
0x180029bea  test    eax, eax
0x180029bec  js      short loc_180029C3F
0x180029bee  test    ebx, ebx
0x180029bf0  jz      short loc_180029BFE
0x180029bf2  mov     rcx, rsi; lpMem
0x180029bf5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180029bfa  mov     [rbp+var_40], r12d
0x180029bfe  cmp     [rbp+var_30], r12d
0x180029c02  jz      short loc_180029C1E
0x180029c04  mov     rcx, [rbp+ppAssemblyNameObj]
0x180029c08  test    rcx, rcx
0x180029c0b  jz      short loc_180029C1A
0x180029c0d  mov     rax, [rcx]
0x180029c10  mov     rax, [rax+10h]
0x180029c14  call    cs:__guard_dispatch_icall_fptr
0x180029c1a  mov     [rbp+var_30], r12d
0x180029c1e  mov     rbx, [rsp+80h+arg_8]
0x180029c26  add     rsp, 80h
0x180029c2d  pop     r15
0x180029c2f  pop     r14
0x180029c31  pop     r13
0x180029c33  pop     r12
0x180029c35  pop     rdi
0x180029c36  pop     rsi
0x180029c37  pop     rbp
0x180029c38  retn
0x180029c39  test    eax, eax
0x180029c3b  js      short loc_180029C4F
0x180029c3d  jmp     short loc_180029C1E
0x180029c3f  mov     ecx, eax; int
0x180029c41  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c47  mov     ecx, eax; int
0x180029c49  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c4f  mov     ecx, eax; int
0x180029c51  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c57  mov     ecx, eax; int
0x180029c59  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c5f  mov     ecx, eax; int
0x180029c61  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c67  mov     ecx, eax; int
0x180029c69  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c6f  mov     ecx, eax; int
0x180029c71  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c77  mov     ecx, r14d; int
0x180029c7a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c80  mov     ecx, eax; int
0x180029c82  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c88  mov     ecx, eax; int
0x180029c8a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c90  mov     ecx, eax; int
0x180029c92  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029c98  mov     ecx, eax; int
0x180029c9a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029ca0  mov     ecx, eax; int
0x180029ca2  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180029ca8  mov     ecx, eax; int
0x180029caa  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
```
