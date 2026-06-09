# BinToHex(uchar *,ulong,ushort * *)

- ea: `0x18001c720`
- end: `0x18001c8b2`
- name: `?BinToHex@@YAJPEAEKPEAPEAG@Z`
- size: `402`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000cde4`

## callees

- `0x18000bd24`
- `0x18000f78c`
- `0x18001c720`
- `0x18001f652`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001c7db`
- `ole32!CoTaskMemAlloc` at `0x18001c7db`
- `ole32!CoTaskMemFree` at `0x18001c841`
- `ole32!CoTaskMemFree` at `0x18001c841`

## pseudocode

```c
__int64 __fastcall BinToHex(unsigned __int8 *a1, unsigned int a2, unsigned __int16 **a3)
{
  __int64 v6; // rax
  const unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned int v9; // ecx
  __int64 v10; // r8
  SIZE_T v11; // r15
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r14
  __int64 result; // rax
  int v15; // r15d
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // [rsp+20h] [rbp-58h] BYREF
  ATL::CAtlException *v18; // [rsp+28h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+30h] [rbp-48h] BYREF
  __int16 v20; // [rsp+34h] [rbp-44h]

  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v7 = (const unsigned __int16 *)(v6 + 24);
  v17 = (const unsigned __int16 *)(v6 + 24);
  v8 = 0;
  try
  {
    while ( v8 < a2 )
    {
      v9 = a1[v8];
      v20 = 0;
      LOWORD(v19) = a0123456789abcd[(unsigned __int64)v9 >> 4];
      HIWORD(v19) = a0123456789abcd[v9 & 0xF];
      v10 = -1;
      do
        ++v10;
      while ( *((_WORD *)&v19 + v10) );
      ATL::CSimpleStringT<unsigned short,0>::Append(&v17, &v19);
      ++v8;
      v7 = v17;
    }
    v11 = (unsigned int)(2 * *((_DWORD *)v7 - 4) + 2);
    v12 = (unsigned __int16 *)CoTaskMemAlloc(v11);
    v13 = v12;
    if ( v12 )
    {
      memset_0(v12, 0, v11);
      v15 = StringCchCopyW(v13, v11 >> 1, v7);
      if ( v15 < 0 )
        CoTaskMemFree(v13);
      else
        *a3 = v13;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
      result = (unsigned int)v15;
    }
    else
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 - 2, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v7 - 3) + 8LL))(*((_QWORD *)v7 - 3));
      result = 2147942414LL;
    }
  }
  catch ( ATL::CAtlException *v18 )
  {
    v19 = *(_DWORD *)v18;
    v16 = v17 - 12;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v17 - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 8LL))(*(_QWORD *)v16);
    return v19;
  }
  while ( v8 < a2 )
  {
    v9 = a1[v8];
    v20 = 0;
    LOWORD(v19) = a0123456789abcd[(unsigned __int64)v9 >> 4];
    HIWORD(v19) = a0123456789abcd[v9 & 0xF];
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)&v19 + v10) );
    ATL::CSimpleStringT<unsigned short,0>::Append(&v17, &v19);
    ++v8;
    v7 = v17;
  }
}

```

## disassembly

```asm
0x18001c720  push    rbx
0x18001c722  push    rdi
0x18001c723  push    r12
0x18001c725  push    r13
0x18001c727  push    r14
0x18001c729  push    r15
0x18001c72b  sub     rsp, 48h
0x18001c72f  mov     rax, cs:__security_cookie
0x18001c736  xor     rax, rsp
0x18001c739  mov     [rsp+78h+var_40], rax
0x18001c73e  mov     r12, r8
0x18001c741  mov     r15d, edx
0x18001c744  mov     r13, rcx
0x18001c747  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c74e  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c755  mov     rax, [rax+18h]
0x18001c759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c75e  lea     rbx, [rax+18h]
0x18001c762  mov     [rsp+78h+var_58], rbx
0x18001c767  xor     edi, edi
0x18001c769  mov     r14d, edi
0x18001c76c  lea     rdx, a0123456789abcd; "0123456789ABCDEF"
0x18001c773  cmp     r14d, r15d
0x18001c776  jnb     short loc_18001C7CC
0x18001c778  mov     eax, r14d
0x18001c77b  movzx   ecx, byte ptr [rax+r13]
0x18001c780  mov     [rsp+78h+var_44], di
0x18001c785  mov     eax, ecx
0x18001c787  shr     rax, 4
0x18001c78b  movzx   eax, word ptr [rdx+rax*2]
0x18001c78f  mov     word ptr [rsp+78h+var_48], ax
0x18001c794  and     ecx, 0Fh
0x18001c797  movzx   eax, word ptr [rdx+rcx*2]
0x18001c79b  mov     word ptr [rsp+78h+var_48+2], ax
0x18001c7a0  lea     rax, [rsp+78h+var_48]
0x18001c7a5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c7a9  inc     r8
0x18001c7ac  cmp     [rax+r8*2], di
0x18001c7b1  jnz     short loc_18001C7A9
0x18001c7b3  lea     rdx, [rsp+78h+var_48]
0x18001c7b8  lea     rcx, [rsp+78h+var_58]
0x18001c7bd  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18001c7c2  inc     r14d
0x18001c7c5  mov     rbx, [rsp+78h+var_58]
0x18001c7ca  jmp     short loc_18001C76C
0x18001c7cc  mov     eax, [rbx-10h]
0x18001c7cf  lea     eax, ds:2[rax*2]
0x18001c7d6  mov     r15d, eax
0x18001c7d9  mov     ecx, eax; cb
0x18001c7db  call    cs:__imp_CoTaskMemAlloc
0x18001c7e1  mov     r14, rax
0x18001c7e4  test    rax, rax
0x18001c7e7  jnz     short loc_18001C813
0x18001c7e9  lea     rdx, [rbx-18h]
0x18001c7ed  or      eax, 0FFFFFFFFh
0x18001c7f0  lock xadd [rdx+10h], eax
0x18001c7f5  sub     eax, 1
0x18001c7f8  jg      short loc_18001C809
0x18001c7fa  mov     rcx, [rdx]
0x18001c7fd  mov     rax, [rcx]
0x18001c800  mov     rax, [rax+8]
0x18001c804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c809  mov     eax, 8007000Eh
0x18001c80e  jmp     loc_18001C896
0x18001c813  mov     r8, r15; Size
0x18001c816  xor     edx, edx; Val
0x18001c818  mov     rcx, r14; void *
0x18001c81b  call    memset_0
0x18001c820  shr     r15, 1
0x18001c823  mov     r8, rbx; unsigned __int16 *
0x18001c826  mov     rdx, r15; unsigned __int64
0x18001c829  mov     rcx, r14; unsigned __int16 *
0x18001c82c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c831  mov     r15d, eax
0x18001c834  test    eax, eax
0x18001c836  js      short loc_18001C83E
0x18001c838  mov     [r12], r14
0x18001c83c  jmp     short loc_18001C848
0x18001c83e  mov     rcx, r14; pv
0x18001c841  call    cs:__imp_CoTaskMemFree
0x18001c847  nop
0x18001c848  lea     rdx, [rbx-18h]
0x18001c84c  or      eax, 0FFFFFFFFh
0x18001c84f  lock xadd [rdx+10h], eax
0x18001c854  sub     eax, 1
0x18001c857  jg      short loc_18001C868
0x18001c859  mov     rcx, [rdx]
0x18001c85c  mov     rax, [rcx]
0x18001c85f  mov     rax, [rax+8]
0x18001c863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c868  mov     eax, r15d
0x18001c86b  jmp     short loc_18001C896
0x18001c86d  mov     rdx, [rsp+78h+var_58]
0x18001c872  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18001c876  or      eax, 0FFFFFFFFh
0x18001c879  lock xadd [rdx+10h], eax
0x18001c87e  sub     eax, 1
0x18001c881  jg      short loc_18001C892
0x18001c883  mov     rcx, [rdx]
0x18001c886  mov     rax, [rcx]
0x18001c889  mov     rax, [rax+8]
0x18001c88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c892  mov     eax, [rsp+78h+var_48]
0x18001c896  mov     rcx, [rsp+78h+var_40]
0x18001c89b  xor     rcx, rsp; StackCookie
0x18001c89e  call    __security_check_cookie
0x18001c8a3  add     rsp, 48h
0x18001c8a7  pop     r15
0x18001c8a9  pop     r14
0x18001c8ab  pop     r13
0x18001c8ad  pop     r12
0x18001c8af  pop     rdi
0x18001c8b0  pop     rbx
0x18001c8b1  retn
```
