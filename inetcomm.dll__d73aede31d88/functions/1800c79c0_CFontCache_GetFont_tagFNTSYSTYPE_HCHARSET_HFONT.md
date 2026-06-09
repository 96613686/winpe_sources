# CFontCache::GetFont(tagFNTSYSTYPE,HCHARSET__ *,HFONT__ * *)

- ea: `0x1800c79c0`
- end: `0x1800c7bad`
- name: `?GetFont@CFontCache@@UEAAJW4tagFNTSYSTYPE@@PEAUHCHARSET__@@PEAPEAUHFONT__@@@Z`
- size: `493`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180023a48`
- `0x18002d690`
- `0x1800c79c0`
- `0x1800c7bd4`
- `0x1800c81d4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x1800c7b57`
- `GDI32!CreateFontIndirectA` at `0x1800c7b57`
- `GDI32!GetObjectA` at `0x1800c7b1d`
- `GDI32!GetObjectA` at `0x1800c7b1d`
- `KERNEL32!IsValidCodePage` at `0x1800c7b48`
- `KERNEL32!IsValidCodePage` at `0x1800c7b48`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7b77`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7ba2`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7b77`
- `KERNEL32!LeaveCriticalSection` at `0x1800c7ba2`
- `KERNEL32!EnterCriticalSection` at `0x1800c7a78`
- `KERNEL32!EnterCriticalSection` at `0x1800c7a78`

## pseudocode

```c
__int64 __fastcall CFontCache::GetFont(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  __int64 v5; // r12
  __int64 v8; // rcx
  unsigned int v10; // ebx
  int v11; // eax
  struct FONTCACHEENTRY_tag *v12; // rcx
  __int64 v13; // rcx
  HFONT v14; // rax
  struct FONTCACHEENTRY_tag *v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+38h] [rbp-C8h] BYREF
  struct tagLOGFONTA pv; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v18[136]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v19; // [rsp+108h] [rbp+8h]

  v5 = a2;
  memset_0(v18, 0, 0x98u);
  v15 = 0;
  v16 = 0;
  if ( !a3 )
  {
    v8 = a1 - 32;
    return CFontCache::GetSysFont(v8, (unsigned int)v5, a4);
  }
  *a4 = 0;
  MimeOleGetCharsetInfo(a3, v18);
  v10 = v19;
  if ( v19 == 50932 )
  {
    v10 = 932;
  }
  else if ( v19 == 50949 )
  {
    v10 = 949;
  }
  if ( *(_QWORD *)(a1 - 32 + 64) && v10 == *(_DWORD *)(a1 + 1156) )
  {
LABEL_10:
    v8 = a1 - 32;
    return CFontCache::GetSysFont(v8, (unsigned int)v5, a4);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1072));
  do
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct FONTCACHEENTRY_tag **, int *))(**(_QWORD **)(a1 + 24) + 64LL))(
            *(_QWORD *)(a1 + 24),
            0,
            &v15,
            &v16);
    v12 = v15;
  }
  while ( v11 >= 0 && *(_DWORD *)v15 != v10 );
  if ( !v15 )
  {
    if ( (int)CreateFontCacheEntry(&v15) < 0
      || (*(int (__fastcall **)(_QWORD, struct FONTCACHEENTRY_tag *, int *))(**(_QWORD **)(a1 + 24) + 48LL))(
           *(_QWORD *)(a1 + 24),
           v15,
           &v16) < 0 )
    {
      goto LABEL_25;
    }
    *(_DWORD *)v15 = v10;
    v12 = v15;
  }
  if ( !*((_QWORD *)v12 + v5 + 5) )
  {
    v13 = *(_QWORD *)(a1 + 32);
    memset(&pv, 0, sizeof(pv));
    if ( GetObjectA(*(HANDLE *)(v13 + 8 * v5 + 40), 60, &pv)
      && (int)CFontCache::SetGDIAndFaceNameInLF((CFontCache *)(a1 - 32), v10, v19, &pv) >= 0
      && (v10 == 1200 || IsValidCodePage(v10)) )
    {
      v14 = CreateFontIndirectA(&pv);
      *((_QWORD *)v15 + v5 + 5) = v14;
      v12 = v15;
      goto LABEL_24;
    }
LABEL_25:
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1072));
    goto LABEL_10;
  }
LABEL_24:
  *a4 = *((_QWORD *)v12 + v5 + 5);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1072));
  return 0;
}

```

## disassembly

```asm
0x1800c79c0  push    rbp
0x1800c79c2  push    rbx
0x1800c79c3  push    rsi
0x1800c79c4  push    rdi
0x1800c79c5  push    r12
0x1800c79c7  push    r13
0x1800c79c9  push    r14
0x1800c79cb  push    r15
0x1800c79cd  lea     rbp, [rsp-38h]
0x1800c79d2  sub     rsp, 138h
0x1800c79d9  mov     rax, cs:__security_cookie
0x1800c79e0  xor     rax, rsp
0x1800c79e3  mov     [rbp+70h+var_50], rax
0x1800c79e7  mov     rbx, r8
0x1800c79ea  movsxd  r12, edx
0x1800c79ed  mov     rdi, rcx
0x1800c79f0  xor     edx, edx; Val
0x1800c79f2  mov     r8d, 98h; Size
0x1800c79f8  lea     rcx, [rbp+70h+var_F0]; void *
0x1800c79fc  mov     r14, r9
0x1800c79ff  call    memset_0
0x1800c7a04  xor     esi, esi
0x1800c7a06  mov     [rsp+170h+var_140], rsi
0x1800c7a0b  mov     [rsp+170h+var_138], esi
0x1800c7a0f  test    rbx, rbx
0x1800c7a12  jnz     short loc_1800C7A28
0x1800c7a14  lea     rcx, [rdi-20h]
0x1800c7a18  mov     edx, r12d
0x1800c7a1b  mov     r8, r14
0x1800c7a1e  call    ?GetSysFont@CFontCache@@AEAAJW4tagFNTSYSTYPE@@PEAPEAUHFONT__@@@Z; CFontCache::GetSysFont(tagFNTSYSTYPE,HFONT__ * *)
0x1800c7a23  jmp     loc_1800C7B7F
0x1800c7a28  lea     rdx, [rbp+70h+var_F0]
0x1800c7a2c  mov     [r14], rsi
0x1800c7a2f  mov     rcx, rbx
0x1800c7a32  call    MimeOleGetCharsetInfo
0x1800c7a37  mov     ebx, [rbp+70h+var_68]
0x1800c7a3a  cmp     ebx, 0C6F4h
0x1800c7a40  jnz     short loc_1800C7A49
0x1800c7a42  mov     ebx, 3A4h
0x1800c7a47  jmp     short loc_1800C7A57
0x1800c7a49  cmp     ebx, 0C705h
0x1800c7a4f  mov     eax, 3B5h
0x1800c7a54  cmovz   ebx, eax
0x1800c7a57  lea     r15, [rdi-20h]
0x1800c7a5b  cmp     [r15+40h], rsi
0x1800c7a5f  jz      short loc_1800C7A6E
0x1800c7a61  cmp     ebx, [rdi+484h]
0x1800c7a67  jnz     short loc_1800C7A6E
0x1800c7a69  mov     rcx, r15
0x1800c7a6c  jmp     short loc_1800C7A18
0x1800c7a6e  lea     r13, [rdi+430h]
0x1800c7a75  mov     rcx, r13; lpCriticalSection
0x1800c7a78  call    cs:__imp_EnterCriticalSection
0x1800c7a7e  mov     rcx, [rdi+18h]
0x1800c7a82  lea     r9, [rsp+170h+var_138]
0x1800c7a87  lea     r8, [rsp+170h+var_140]
0x1800c7a8c  xor     edx, edx
0x1800c7a8e  mov     rax, [rcx]
0x1800c7a91  mov     rax, [rax+40h]
0x1800c7a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7a9a  mov     rcx, [rsp+170h+var_140]
0x1800c7a9f  test    eax, eax
0x1800c7aa1  js      short loc_1800C7AA7
0x1800c7aa3  cmp     [rcx], ebx
0x1800c7aa5  jnz     short loc_1800C7A7E
0x1800c7aa7  test    rcx, rcx
0x1800c7aaa  jnz     short loc_1800C7AEC
0x1800c7aac  lea     rcx, [rsp+170h+var_140]; struct FONTCACHEENTRY_tag **
0x1800c7ab1  call    ?CreateFontCacheEntry@@YAJPEAPEAUFONTCACHEENTRY_tag@@@Z; CreateFontCacheEntry(FONTCACHEENTRY_tag * *)
0x1800c7ab6  test    eax, eax
0x1800c7ab8  js      loc_1800C7B9F
0x1800c7abe  mov     rcx, [rdi+18h]
0x1800c7ac2  lea     r8, [rsp+170h+var_138]
0x1800c7ac7  mov     rdx, [rsp+170h+var_140]
0x1800c7acc  mov     rax, [rcx]
0x1800c7acf  mov     rax, [rax+30h]
0x1800c7ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7ad8  test    eax, eax
0x1800c7ada  js      loc_1800C7B9F
0x1800c7ae0  mov     rax, [rsp+170h+var_140]
0x1800c7ae5  mov     [rax], ebx
0x1800c7ae7  mov     rcx, [rsp+170h+var_140]
0x1800c7aec  cmp     [rcx+r12*8+28h], rsi
0x1800c7af1  jnz     short loc_1800C7B6C
0x1800c7af3  mov     rcx, [rdi+20h]
0x1800c7af7  lea     r8, [rsp+170h+pv]; pv
0x1800c7afc  xorps   xmm0, xmm0
0x1800c7aff  mov     edx, 3Ch ; '<'; c
0x1800c7b04  movups  [rsp+170h+var_110], xmm0
0x1800c7b09  movups  [rsp+170h+pv], xmm0
0x1800c7b0e  movups  [rsp+170h+var_120], xmm0
0x1800c7b13  movups  [rsp+170h+var_110+0Ch], xmm0
0x1800c7b18  mov     rcx, [rcx+r12*8+28h]; h
0x1800c7b1d  call    cs:__imp_GetObjectA
0x1800c7b23  test    eax, eax
0x1800c7b25  jz      short loc_1800C7B9F
0x1800c7b27  mov     r8d, [rbp+70h+var_68]; unsigned int
0x1800c7b2b  lea     r9, [rsp+170h+pv]; struct tagLOGFONTA *
0x1800c7b30  mov     edx, ebx; unsigned int
0x1800c7b32  mov     rcx, r15; this
0x1800c7b35  call    ?SetGDIAndFaceNameInLF@CFontCache@@AEAAJIKPEAUtagLOGFONTA@@@Z; CFontCache::SetGDIAndFaceNameInLF(uint,ulong,tagLOGFONTA *)
0x1800c7b3a  test    eax, eax
0x1800c7b3c  js      short loc_1800C7B9F
0x1800c7b3e  cmp     ebx, 4B0h
0x1800c7b44  jz      short loc_1800C7B52
0x1800c7b46  mov     ecx, ebx; CodePage
0x1800c7b48  call    cs:__imp_IsValidCodePage
0x1800c7b4e  test    eax, eax
0x1800c7b50  jz      short loc_1800C7B9F
0x1800c7b52  lea     rcx, [rsp+170h+pv]; lplf
0x1800c7b57  call    cs:__imp_CreateFontIndirectA
0x1800c7b5d  mov     rcx, [rsp+170h+var_140]
0x1800c7b62  mov     [rcx+r12*8+28h], rax
0x1800c7b67  mov     rcx, [rsp+170h+var_140]
0x1800c7b6c  mov     rax, [rcx+r12*8+28h]
0x1800c7b71  mov     rcx, r13; lpCriticalSection
0x1800c7b74  mov     [r14], rax
0x1800c7b77  call    cs:__imp_LeaveCriticalSection
0x1800c7b7d  xor     eax, eax
0x1800c7b7f  mov     rcx, [rbp+70h+var_50]
0x1800c7b83  xor     rcx, rsp; StackCookie
0x1800c7b86  call    __security_check_cookie
0x1800c7b8b  add     rsp, 138h
0x1800c7b92  pop     r15
0x1800c7b94  pop     r14
0x1800c7b96  pop     r13
0x1800c7b98  pop     r12
0x1800c7b9a  pop     rdi
0x1800c7b9b  pop     rsi
0x1800c7b9c  pop     rbx
0x1800c7b9d  pop     rbp
0x1800c7b9e  retn
0x1800c7b9f  mov     rcx, r13; lpCriticalSection
0x1800c7ba2  call    cs:__imp_LeaveCriticalSection
0x1800c7ba8  jmp     loc_1800C7A69
```
