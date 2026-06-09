# CCommunityTransport::InitNewW(ushort const *,ICommunityCallback *)

- ea: `0x1800b0230`
- end: `0x1800b03c2`
- name: `?InitNewW@CCommunityTransport@@UEAAJPEBGPEAUICommunityCallback@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(CCommunityTransport *__hidden this, ACCESS_MASK fDesiredAccess, struct ICommunityCallback *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180002098`
- `0x1800299d0`
- `0x1800a6108`
- `0x1800b0230`
- `0x1800b03c8`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!CreateLogFile` at `0x1800b0345`
- `MSOERT2!CreateLogFile` at `0x1800b0345`
- `KERNEL32!LeaveCriticalSection` at `0x1800b039d`
- `KERNEL32!LeaveCriticalSection` at `0x1800b039d`
- `KERNEL32!EnterCriticalSection` at `0x1800b0287`
- `KERNEL32!EnterCriticalSection` at `0x1800b0287`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b0305`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b0305`

## pseudocode

```c
__int64 __fastcall CCommunityTransport::InitNewW(
        CCommunityTransport *this,
        __int64 fDesiredAccess,
        struct ICommunityCallback *a3)
{
  CAsyncHttp **v7; // rdi
  __int64 v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rbp
  _QWORD *v10; // r12
  OLECHAR *v11; // rcx
  CAsyncHttp *v12; // rax
  CAsyncHttp *v13; // rax
  unsigned int v14; // ebx

  if ( *((_DWORD *)this + 976) )
    return 2148322315LL;
  v7 = (CAsyncHttp **)((char *)this + 40);
  v8 = *((_QWORD *)this + 5);
  if ( v8 && *(_DWORD *)(v8 + 104) && *(_DWORD *)(v8 + 104) != 10 )
    return 2148322307LL;
  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 3928);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 3928));
  if ( *((_QWORD *)this + 437) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 437) = 0;
  }
  if ( *((_QWORD *)this + 440) )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    *((_QWORD *)this + 440) = 0;
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 56);
  v10 = (_QWORD *)((char *)this + 48);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>((char *)this + 48);
  v11 = (OLECHAR *)*((_QWORD *)this + 489);
  if ( v11 )
  {
    SysFreeString(v11);
    *((_QWORD *)this + 489) = 0;
  }
  CCommunityTransport::InitVars(this);
  if ( fDesiredAccess )
    CreateLogFile(
      (LPCWSTR)g_hInst,
      fDesiredAccess,
      (DWORD)"HTTP",
      (LPSECURITY_ATTRIBUTES)0xFFFFFFFFLL,
      (_DWORD)this + 56,
      3u);
  if ( *v7 )
    goto LABEL_18;
  v12 = (CAsyncHttp *)operator new(0xAF0u);
  if ( v12 )
  {
    v13 = CAsyncHttp::CAsyncHttp(
            v12,
            *((struct ILogFile **)this + 7),
            (struct IAsyncHttpCB *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)));
    *v7 = v13;
    if ( v13 )
    {
LABEL_18:
      v14 = 0;
      if ( a3 )
      {
        *v10 = a3;
        (*(void (__fastcall **)(struct ICommunityCallback *))(*(_QWORD *)a3 + 8LL))(a3);
      }
      goto LABEL_20;
    }
  }
  else
  {
    *v7 = 0;
  }
  v14 = -2147024882;
LABEL_20:
  LeaveCriticalSection(v9);
  return v14;
}

```

## disassembly

```asm
0x1800b0230  push    rbx
0x1800b0232  push    rbp
0x1800b0233  push    rsi
0x1800b0234  push    rdi
0x1800b0235  push    r12
0x1800b0237  push    r14
0x1800b0239  push    r15
0x1800b023b  sub     rsp, 30h
0x1800b023f  cmp     dword ptr [rcx+0F40h], 0
0x1800b0246  mov     rsi, r8
0x1800b0249  mov     r15, rdx
0x1800b024c  mov     rbx, rcx
0x1800b024f  jz      short loc_1800B025B
0x1800b0251  mov     eax, 800CCC0Bh
0x1800b0256  jmp     loc_1800B03A5
0x1800b025b  lea     rdi, [rcx+28h]
0x1800b025f  mov     rax, [rdi]
0x1800b0262  test    rax, rax
0x1800b0265  jz      short loc_1800B027D
0x1800b0267  cmp     dword ptr [rax+68h], 0
0x1800b026b  jz      short loc_1800B027D
0x1800b026d  cmp     dword ptr [rax+68h], 0Ah
0x1800b0271  jz      short loc_1800B027D
0x1800b0273  mov     eax, 800CCC03h
0x1800b0278  jmp     loc_1800B03A5
0x1800b027d  lea     rbp, [rcx+0F58h]
0x1800b0284  mov     rcx, rbp; lpCriticalSection
0x1800b0287  call    cs:__imp_EnterCriticalSection
0x1800b028d  mov     rdx, [rbx+0DA8h]
0x1800b0294  test    rdx, rdx
0x1800b0297  jz      short loc_1800B02B7
0x1800b0299  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800b02a0  mov     rax, [rcx]
0x1800b02a3  mov     rax, [rax+28h]
0x1800b02a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b02ac  mov     qword ptr [rbx+0DA8h], 0
0x1800b02b7  mov     rdx, [rbx+0DC0h]
0x1800b02be  test    rdx, rdx
0x1800b02c1  jz      short loc_1800B02E1
0x1800b02c3  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800b02ca  mov     rax, [rcx]
0x1800b02cd  mov     rax, [rax+28h]
0x1800b02d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b02d6  mov     qword ptr [rbx+0DC0h], 0
0x1800b02e1  lea     r14, [rbx+38h]
0x1800b02e5  mov     rcx, r14
0x1800b02e8  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800b02ed  lea     r12, [rbx+30h]
0x1800b02f1  mov     rcx, r12
0x1800b02f4  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x1800b02f9  mov     rcx, [rbx+0F48h]; bstrString
0x1800b0300  test    rcx, rcx
0x1800b0303  jz      short loc_1800B0316
0x1800b0305  call    cs:__imp_SysFreeString
0x1800b030b  mov     qword ptr [rbx+0F48h], 0
0x1800b0316  mov     rcx, rbx; this
0x1800b0319  call    ?InitVars@CCommunityTransport@@AEAAXXZ; CCommunityTransport::InitVars(void)
0x1800b031e  test    r15, r15
0x1800b0321  jz      short loc_1800B034B
0x1800b0323  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; pszLogFileName
0x1800b032a  lea     r8, aHttp; "HTTP"
0x1800b0331  mov     [rsp+68h+fFlagsAndAttributes], 3; fFlagsAndAttributes
0x1800b0339  or      r9d, 0FFFFFFFFh; psaLogFile
0x1800b033d  mov     rdx, r15; fDesiredAccess
0x1800b0340  mov     qword ptr [rsp+68h+fCreateDisposition], r14; fCreateDisposition
0x1800b0345  call    cs:__imp_CreateLogFile
0x1800b034b  cmp     qword ptr [rdi], 0
0x1800b034f  jnz     short loc_1800B0380
0x1800b0351  mov     ecx, 0AF0h; Size
0x1800b0356  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b035b  test    rax, rax
0x1800b035e  jz      short loc_1800B03B4
0x1800b0360  mov     rdx, [r14]; struct ILogFile *
0x1800b0363  lea     rcx, [rbx+10h]
0x1800b0367  neg     rbx
0x1800b036a  sbb     r8, r8
0x1800b036d  and     r8, rcx; struct IAsyncHttpCB *
0x1800b0370  mov     rcx, rax; this
0x1800b0373  call    ??0CAsyncHttp@@QEAA@PEAUILogFile@@PEAUIAsyncHttpCB@@@Z; CAsyncHttp::CAsyncHttp(ILogFile *,IAsyncHttpCB *)
0x1800b0378  mov     [rdi], rax
0x1800b037b  test    rax, rax
0x1800b037e  jz      short loc_1800B03BB
0x1800b0380  xor     ebx, ebx
0x1800b0382  test    rsi, rsi
0x1800b0385  jz      short loc_1800B039A
0x1800b0387  mov     [r12], rsi
0x1800b038b  mov     rcx, rsi
0x1800b038e  mov     rdx, [rsi]
0x1800b0391  mov     rax, [rdx+8]
0x1800b0395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b039a  mov     rcx, rbp; lpCriticalSection
0x1800b039d  call    cs:__imp_LeaveCriticalSection
0x1800b03a3  mov     eax, ebx
0x1800b03a5  add     rsp, 30h
0x1800b03a9  pop     r15
0x1800b03ab  pop     r14
0x1800b03ad  pop     r12
0x1800b03af  pop     rdi
0x1800b03b0  pop     rsi
0x1800b03b1  pop     rbp
0x1800b03b2  pop     rbx
0x1800b03b3  retn
0x1800b03b4  mov     qword ptr [rdi], 0
0x1800b03bb  mov     ebx, 8007000Eh
0x1800b03c0  jmp     short loc_1800B039A
```
