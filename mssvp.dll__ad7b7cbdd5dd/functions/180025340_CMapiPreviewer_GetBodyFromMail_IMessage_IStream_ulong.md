# CMapiPreviewer::GetBodyFromMail(IMessage *,IStream * *,ulong *)

- ea: `0x180025340`
- end: `0x180025555`
- name: `?GetBodyFromMail@CMapiPreviewer@@AEAAJPEAUIMessage@@PEAPEAUIStream@@PEAK@Z`
- size: `533`
- prototype: `int(CMapiPreviewer *__hidden this, struct IMessage *, struct IStream **, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180025a90`

## callees

- `0x180005210`
- `0x180006270`
- `0x180025340`
- `0x18002586c`
- `0x18003d010`

## import_xrefs

- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180025435`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_MAPIFreeBuffer` at `0x180025435`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_WrapCompressedRTFStream` at `0x180025498`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_WrapCompressedRTFStream` at `0x180025498`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMapiPreviewer::GetBodyFromMail(
        CMapiPreviewer *this,
        struct IMessage *a2,
        struct IStream **a3,
        unsigned int *a4)
{
  int v7; // esi
  int v8; // r12d
  int v9; // r13d
  HRESULT Props; // ebx
  _DWORD *v11; // rdx
  unsigned int v12; // r8d
  bool v13; // zf
  unsigned int v14; // esi
  unsigned int v16; // [rsp+40h] [rbp-30h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-28h] BYREF
  LPSTREAM lpCompressedRTFStream; // [rsp+50h] [rbp-20h] BYREF
  struct _SPropTagArray v19; // [rsp+58h] [rbp-18h] BYREF
  int v20; // [rsp+60h] [rbp-10h]
  int v21; // [rsp+64h] [rbp-Ch]

  *a3 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  v16 = 0;
  v19.cValues = 3;
  v19.aulPropTag[0] = 268435487;
  v20 = 269680898;
  v21 = 269025538;
  pv = 0;
  Props = CMapiPreviewer::GetProps(this, a2, &v19, &v16, (struct _SPropValue **)&pv);
  v11 = pv;
  v12 = 0;
  if ( Props >= 0 )
  {
    while ( v12 < v16 )
    {
      if ( *v11 == 268435466 )
      {
        if ( v11[2] == -2147024882 )
          v7 = 1;
      }
      else if ( *v11 == 268435486 || *v11 == 268435487 )
      {
        v7 = 1;
      }
      else
      {
        switch ( *v11 )
        {
          case 0x1009000A:
            if ( v11[2] != -2147024882 )
              goto LABEL_18;
LABEL_14:
            v8 = 1;
            goto LABEL_18;
          case 0x10090102:
            goto LABEL_14;
          case 0x1013000A:
            v13 = v11[2] == -2147024882;
            break;
          default:
            v13 = *v11 == 269680898;
            break;
        }
        if ( v13 )
          v9 = 1;
      }
LABEL_18:
      ++v12;
      v11 += 6;
    }
  }
  MAPIFreeBuffer(pv);
  if ( Props >= 0 )
  {
    if ( v8 || v9 )
    {
      lpCompressedRTFStream = 0;
      Props = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, _DWORD, LPSTREAM *))a2->lpVtbl->get_BCC)(
                a2,
                269025538,
                &IID_IStream,
                0,
                0,
                &lpCompressedRTFStream);
      if ( Props >= 0 )
      {
        Props = WrapCompressedRTFStream(lpCompressedRTFStream, 0, a3);
        if ( Props >= 0 )
          *a4 = 269025538;
      }
      ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>((__int64 *)&lpCompressedRTFStream);
    }
    if ( *a3 || !v7 )
    {
      if ( Props < 0 )
        return (unsigned int)Props;
    }
    else
    {
      v14 = 268435487;
      Props = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, _DWORD, struct IStream **))a2->lpVtbl->get_BCC)(
                a2,
                268435487,
                &IID_IStream,
                0,
                0,
                a3);
      if ( Props < 0 )
      {
        v14 = 268435486;
        Props = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, _DWORD, struct IStream **))a2->lpVtbl->get_BCC)(
                  a2,
                  268435486,
                  &IID_IStream,
                  0,
                  0,
                  a3);
        if ( Props < 0 )
          return (unsigned int)Props;
      }
      *a4 = v14;
    }
    if ( !*a3 )
      return (unsigned int)-2147467259;
  }
  return (unsigned int)Props;
}

```

## disassembly

```asm
0x180025340  mov     [rsp-38h+arg_0], rbx
0x180025345  push    rbp
0x180025346  push    rsi
0x180025347  push    rdi
0x180025348  push    r12
0x18002534a  push    r13
0x18002534c  push    r14
0x18002534e  push    r15
0x180025350  mov     rbp, rsp
0x180025353  sub     rsp, 70h
0x180025357  mov     rax, cs:__security_cookie
0x18002535e  xor     rax, rsp
0x180025361  mov     [rbp+var_8], rax
0x180025365  mov     r15, r9
0x180025368  mov     rdi, r8
0x18002536b  mov     r14, rdx
0x18002536e  xor     eax, eax
0x180025370  mov     [r8], rax
0x180025373  mov     esi, eax
0x180025375  mov     r12d, eax
0x180025378  mov     r13d, eax
0x18002537b  mov     [rbp+var_30], eax
0x18002537e  mov     [rbp+var_18.cValues], 3
0x180025385  mov     [rbp+var_18.aulPropTag], 1000001Fh
0x18002538c  mov     [rbp+var_10], 10130102h
0x180025393  mov     [rbp+var_C], 10090102h
0x18002539a  mov     [rbp+pv], rax
0x18002539e  lea     rax, [rbp+pv]
0x1800253a2  mov     [rsp+70h+var_50], rax; struct _SPropValue **
0x1800253a7  lea     r9, [rbp+var_30]; unsigned int *
0x1800253ab  lea     r8, [rbp+var_18]; struct _SPropTagArray *
0x1800253af  call    ?GetProps@CMapiPreviewer@@AEAAJPEAUIMessage@@PEAU_SPropTagArray@@AEAKAEAPEAU_SPropValue@@@Z; CMapiPreviewer::GetProps(IMessage *,_SPropTagArray *,ulong &,_SPropValue * &)
0x1800253b4  mov     ebx, eax
0x1800253b6  mov     rdx, [rbp+pv]
0x1800253ba  xor     r8d, r8d
0x1800253bd  test    eax, eax
0x1800253bf  js      short loc_180025431
0x1800253c1  mov     r11d, 0F8h
0x1800253c7  lea     r9d, [r8+1]
0x1800253cb  mov     r10d, 8007000Eh
0x1800253d1  cmp     r8d, [rbp+var_30]
0x1800253d5  jnb     short loc_180025431
0x1800253d7  mov     ecx, [rdx]
0x1800253d9  sub     ecx, 1000000Ah
0x1800253df  jz      short loc_180025420
0x1800253e1  sub     ecx, 14h
0x1800253e4  jz      short loc_18002541B
0x1800253e6  sub     ecx, r9d
0x1800253e9  jz      short loc_18002541B
0x1800253eb  sub     ecx, 8FFEBh
0x1800253f1  jz      short loc_180025410
0x1800253f3  sub     ecx, r11d
0x1800253f6  jz      short loc_180025416
0x1800253f8  sub     ecx, 9FF08h
0x1800253fe  jz      short loc_18002540A
0x180025400  cmp     ecx, r11d
0x180025403  jnz     short loc_180025428
0x180025405  mov     r13d, r9d
0x180025408  jmp     short loc_180025428
0x18002540a  cmp     [rdx+8], r10d
0x18002540e  jmp     short loc_180025403
0x180025410  cmp     [rdx+8], r10d
0x180025414  jnz     short loc_180025428
0x180025416  mov     r12d, r9d
0x180025419  jmp     short loc_180025428
0x18002541b  mov     esi, r9d
0x18002541e  jmp     short loc_180025428
0x180025420  cmp     [rdx+8], r10d
0x180025424  cmovz   esi, r9d
0x180025428  add     r8d, r9d
0x18002542b  add     rdx, 18h
0x18002542f  jmp     short loc_1800253D1
0x180025431  mov     rcx, [rbp+pv]; pv
0x180025435  call    cs:__imp_MAPIFreeBuffer
0x18002543b  test    ebx, ebx
0x18002543d  js      loc_18002552F
0x180025443  test    r12d, r12d
0x180025446  jnz     short loc_180025452
0x180025448  xor     r12d, r12d
0x18002544b  test    r13d, r13d
0x18002544e  jz      short loc_1800254B0
0x180025450  jmp     short loc_180025455
0x180025452  xor     r12d, r12d
0x180025455  mov     [rbp+lpCompressedRTFStream], r12
0x180025459  mov     rax, [r14]
0x18002545c  lea     rcx, [rbp+lpCompressedRTFStream]
0x180025460  mov     [rsp+70h+var_48], rcx
0x180025465  mov     dword ptr [rsp+70h+var_50], r12d
0x18002546a  xor     r9d, r9d
0x18002546d  lea     r8, IID_IStream
0x180025474  mov     r13d, 10090102h
0x18002547a  mov     edx, r13d
0x18002547d  mov     rcx, r14
0x180025480  mov     rax, [rax+38h]
0x180025484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025489  mov     ebx, eax
0x18002548b  test    eax, eax
0x18002548d  js      short loc_1800254A7
0x18002548f  mov     r8, rdi; lpUncompressedRTFStream
0x180025492  xor     edx, edx; ulFlags
0x180025494  mov     rcx, [rbp+lpCompressedRTFStream]; lpCompressedRTFStream
0x180025498  call    cs:__imp_WrapCompressedRTFStream
0x18002549e  mov     ebx, eax
0x1800254a0  test    eax, eax
0x1800254a2  js      short loc_1800254A7
0x1800254a4  mov     [r15], r13d
0x1800254a7  lea     rcx, [rbp+lpCompressedRTFStream]
0x1800254ab  call    ??1?$CComPtrBase@UIEnumSearchFolderInternal@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IEnumSearchFolderInternal>::~CComPtrBase<IEnumSearchFolderInternal>(void)
0x1800254b0  cmp     [rdi], r12
0x1800254b3  jnz     short loc_180025520
0x1800254b5  test    esi, esi
0x1800254b7  jz      short loc_180025520
0x1800254b9  mov     rax, [r14]
0x1800254bc  mov     [rsp+70h+var_48], rdi
0x1800254c1  mov     dword ptr [rsp+70h+var_50], r12d
0x1800254c6  xor     r9d, r9d
0x1800254c9  lea     r8, IID_IStream
0x1800254d0  mov     esi, 1000001Fh
0x1800254d5  mov     edx, esi
0x1800254d7  mov     rcx, r14
0x1800254da  mov     rax, [rax+38h]
0x1800254de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254e3  mov     ebx, eax
0x1800254e5  test    eax, eax
0x1800254e7  js      short loc_1800254EE
0x1800254e9  mov     [r15], esi
0x1800254ec  jmp     short loc_180025524
0x1800254ee  mov     rax, [r14]
0x1800254f1  mov     [rsp+70h+var_48], rdi
0x1800254f6  mov     dword ptr [rsp+70h+var_50], r12d
0x1800254fb  xor     r9d, r9d
0x1800254fe  lea     r8, IID_IStream
0x180025505  mov     esi, 1000001Eh
0x18002550a  mov     edx, esi
0x18002550c  mov     rcx, r14
0x18002550f  mov     rax, [rax+38h]
0x180025513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025518  mov     ebx, eax
0x18002551a  test    eax, eax
0x18002551c  js      short loc_18002552F
0x18002551e  jmp     short loc_1800254E9
0x180025520  test    ebx, ebx
0x180025522  js      short loc_18002552F
0x180025524  mov     eax, 80004005h
0x180025529  cmp     [rdi], r12
0x18002552c  cmovz   ebx, eax
0x18002552f  mov     eax, ebx
0x180025531  mov     rcx, [rbp+var_8]
0x180025535  xor     rcx, rsp; StackCookie
0x180025538  call    __security_check_cookie
0x18002553d  mov     rbx, [rsp+70h+arg_0]
0x180025545  add     rsp, 70h
0x180025549  pop     r15
0x18002554b  pop     r14
0x18002554d  pop     r13
0x18002554f  pop     r12
0x180025551  pop     rdi
0x180025552  pop     rsi
0x180025553  pop     rbp
0x180025554  retn
```
