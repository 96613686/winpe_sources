# CMessageWebPage::_SetContentId(TREENODEINFO *,char *,ulong)

- ea: `0x180061ef4`
- end: `0x1800621ca`
- name: `?_SetContentId@CMessageWebPage@@AEAAJPEAUTREENODEINFO@@PEADK@Z`
- size: `726`
- prototype: `int(CMessageWebPage *__hidden this, struct TREENODEINFO *, char *, unsigned int)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18006120c`
- `0x180061994`

## callees

- `0x18000b270`
- `0x180011b40`
- `0x180012cd0`
- `0x180022420`
- `0x18002d690`
- `0x18005403c`
- `0x180055cd4`
- `0x180061ef4`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszToANSI` at `0x180061fef`
- `MSOERT2!PszToANSI` at `0x180061fef`
- `MSOERT2!PszAllocA` at `0x180062085`
- `MSOERT2!PszAllocA` at `0x1800620f0`
- `MSOERT2!PszAllocA` at `0x180062085`
- `MSOERT2!PszAllocA` at `0x1800620f0`
- `KERNEL32!LeaveCriticalSection` at `0x180061fa2`
- `KERNEL32!LeaveCriticalSection` at `0x180061fa2`
- `KERNEL32!EnterCriticalSection` at `0x180061f61`
- `KERNEL32!EnterCriticalSection` at `0x180061f61`
- `ole32!StringFromGUID2` at `0x180061fd5`
- `ole32!StringFromGUID2` at `0x180061fd5`
- `ole32!CoCreateGuid` at `0x180061fb6`
- `ole32!CoCreateGuid` at `0x180061fb6`

## pseudocode

```c
__int64 __fastcall CMessageWebPage::_SetContentId(CMessageWebPage *this, struct TREENODEINFO *a2, char *a3)
{
  __int64 v3; // rsi
  BOOL v7; // ebx
  HRESULT v8; // ebx
  const char *v9; // rdi
  char *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned int v13; // r14d
  char *v14; // rax
  char *v15; // rsi
  __int64 v16; // rax
  unsigned int v17; // esi
  char *v18; // rax
  char *v19; // rbx
  void *v20; // rdx
  int PropA; // eax
  char *v22; // r10
  struct tagPROPSYMBOL *v24; // [rsp+30h] [rbp-D0h] BYREF
  char *v25; // [rsp+38h] [rbp-C8h] BYREF
  char *v26; // [rsp+40h] [rbp-C0h] BYREF
  struct tagPROPERTY *v27; // [rsp+48h] [rbp-B8h] BYREF
  GUID pguid; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v29[140]; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+ECh] [rbp-14h]
  OLECHAR sz[64]; // [rsp+100h] [rbp+0h] BYREF

  v3 = *((_QWORD *)a2 + 16);
  v26 = 0;
  v25 = 0;
  v24 = 0;
  v7 = 1;
  pguid = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 1392));
  if ( (int)CPropertySymbolCache::_HrOpenSymbolWithLockOption(g_pSymCache, (const char *)0x14, 0, &v24, 1) >= 0 )
    v7 = (int)CMimePropertyContainer::_HrFindProperty((CMimePropertyContainer *)v3, v24, &v27) < 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 1392));
  if ( v7 )
  {
    v8 = CoCreateGuid(&pguid);
    if ( v8 >= 0 )
    {
      if ( !StringFromGUID2(&pguid, sz, 64) )
        return (unsigned int)-2147467259;
      v9 = (const char *)PszToANSI(0, sz);
      if ( !v9 )
        return (unsigned int)-2147024882;
      memset_0(v29, 0, 0x98u);
      MimeOleGetCharsetInfo(*((_QWORD *)this + 6), v29);
      if ( v30 == 50932 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v9[v16] );
        v17 = v16 + 3;
        v18 = (char *)PszAllocA((unsigned int)(v16 + 3));
        v19 = v18;
        if ( v18 )
        {
          StringCchPrintfA(v18, v17, "%s/.", v9);
          ((void (__fastcall *)(LPMALLOC, const char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
          v9 = v19;
        }
      }
      else if ( !(unsigned int)CMimePropertyContainer::GetPropA(
                                 *((CMimePropertyContainer **)a2 + 16),
                                 "att:generated-filename",
                                 &v25) )
      {
        v10 = v25;
        v11 = -1;
        if ( v25 )
        {
          v12 = -1;
          do
            ++v12;
          while ( v25[v12] );
        }
        else
        {
          LODWORD(v12) = 0;
        }
        do
          ++v11;
        while ( v9[v11] );
        v13 = v11 + v12 + 2;
        v14 = (char *)PszAllocA(v13);
        v15 = v14;
        if ( v14 )
        {
          StringCchPrintfA(v14, v13, "%s/%s", v9, v10);
          ((void (__fastcall *)(LPMALLOC, const char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
          v9 = v15;
        }
        ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v10);
      }
      StringCchCopyA(a3, 0xFFu, v9);
      v8 = CMimePropertyContainer::SetPropA(*((CMimePropertyContainer **)a2 + 16), (const char *)0x14, a3);
      if ( v9 )
      {
        v20 = (void *)v9;
LABEL_30:
        ((void (__fastcall *)(LPMALLOC, void *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v20);
      }
    }
  }
  else
  {
    PropA = CMimePropertyContainer::GetPropA(*((CMimePropertyContainer **)a2 + 16), (const char *)0x14, &v26);
    v22 = v26;
    v8 = PropA;
    if ( PropA >= 0 )
      StringCchCopyA(a3, 0xFFu, v26);
    if ( v22 )
    {
      v20 = v22;
      goto LABEL_30;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180061ef4  push    rbp
0x180061ef6  push    rbx
0x180061ef7  push    rsi
0x180061ef8  push    rdi
0x180061ef9  push    r12
0x180061efb  push    r14
0x180061efd  push    r15
0x180061eff  lea     rbp, [rsp-90h]
0x180061f07  sub     rsp, 190h
0x180061f0e  mov     rax, cs:__security_cookie
0x180061f15  xor     rax, rsp
0x180061f18  mov     [rbp+0C0h+var_40], rax
0x180061f1f  mov     rsi, [rdx+80h]
0x180061f26  mov     r14, rcx
0x180061f29  xorps   xmm0, xmm0
0x180061f2c  mov     [rsp+1C0h+var_180], 0
0x180061f35  mov     r12, r8
0x180061f38  mov     [rsp+1C0h+var_188], 0
0x180061f41  mov     r15, rdx
0x180061f44  mov     [rsp+1C0h+var_190], 0
0x180061f4d  lea     rdi, [rsi+570h]
0x180061f54  mov     ebx, 1
0x180061f59  mov     rcx, rdi; lpCriticalSection
0x180061f5c  movups  xmmword ptr [rsp+1C0h+pguid.Data1], xmm0
0x180061f61  call    cs:__imp_EnterCriticalSection
0x180061f67  mov     rcx, cs:?g_pSymCache@@3PEAVCPropertySymbolCache@@EA; this
0x180061f6e  lea     r9, [rsp+1C0h+var_190]; struct tagPROPSYMBOL **
0x180061f73  xor     r8d, r8d; int
0x180061f76  mov     [rsp+1C0h+var_1A0], ebx; int
0x180061f7a  lea     edx, [rbx+13h]; char *
0x180061f7d  call    ?_HrOpenSymbolWithLockOption@CPropertySymbolCache@@AEAAJPEBDHPEAPEAUtagPROPSYMBOL@@H@Z; CPropertySymbolCache::_HrOpenSymbolWithLockOption(char const *,int,tagPROPSYMBOL * *,int)
0x180061f82  test    eax, eax
0x180061f84  js      short loc_180061F9F
0x180061f86  mov     rdx, [rsp+1C0h+var_190]; struct tagPROPSYMBOL *
0x180061f8b  lea     r8, [rsp+1C0h+var_178]; struct tagPROPERTY **
0x180061f90  mov     rcx, rsi; this
0x180061f93  call    ?_HrFindProperty@CMimePropertyContainer@@AEAAJPEAUtagPROPSYMBOL@@PEAPEAUtagPROPERTY@@@Z; CMimePropertyContainer::_HrFindProperty(tagPROPSYMBOL *,tagPROPERTY * *)
0x180061f98  xor     ecx, ecx
0x180061f9a  test    eax, eax
0x180061f9c  cmovns  ebx, ecx
0x180061f9f  mov     rcx, rdi; lpCriticalSection
0x180061fa2  call    cs:__imp_LeaveCriticalSection
0x180061fa8  cmp     ebx, 1
0x180061fab  jnz     loc_18006215B
0x180061fb1  lea     rcx, [rsp+1C0h+pguid]; pguid
0x180061fb6  call    cs:__imp_CoCreateGuid
0x180061fbc  mov     ebx, eax
0x180061fbe  test    eax, eax
0x180061fc0  js      loc_1800621A7
0x180061fc6  mov     r8d, 40h ; '@'; cchMax
0x180061fcc  lea     rdx, [rbp+0C0h+sz]; lpsz
0x180061fd0  lea     rcx, [rsp+1C0h+pguid]; rguid
0x180061fd5  call    cs:__imp_StringFromGUID2
0x180061fdb  test    eax, eax
0x180061fdd  jnz     short loc_180061FE9
0x180061fdf  mov     ebx, 80004005h
0x180061fe4  jmp     loc_1800621A7
0x180061fe9  lea     rdx, [rbp+0C0h+sz]
0x180061fed  xor     ecx, ecx
0x180061fef  call    cs:__imp_PszToANSI
0x180061ff5  mov     rdi, rax
0x180061ff8  test    rax, rax
0x180061ffb  jnz     short loc_180062007
0x180061ffd  mov     ebx, 8007000Eh
0x180062002  jmp     loc_1800621A7
0x180062007  xor     edx, edx; Val
0x180062009  lea     rcx, [rsp+1C0h+var_160]; void *
0x18006200e  mov     r8d, 98h; Size
0x180062014  call    memset_0
0x180062019  mov     rcx, [r14+30h]
0x18006201d  lea     rdx, [rsp+1C0h+var_160]
0x180062022  call    MimeOleGetCharsetInfo
0x180062027  cmp     [rbp+0C0h+var_D4], 0C6F4h
0x18006202e  jz      loc_1800620DE
0x180062034  mov     rcx, [r15+80h]; this
0x18006203b  lea     r8, [rsp+1C0h+var_188]; char **
0x180062040  lea     rdx, STR_ATT_GENFNAME; "att:generated-filename"
0x180062047  call    ?GetPropA@CMimePropertyContainer@@QEAAJPEBDPEAPEAD@Z; CMimePropertyContainer::GetPropA(char const *,char * *)
0x18006204c  test    eax, eax
0x18006204e  jnz     loc_18006212B
0x180062054  mov     rbx, [rsp+1C0h+var_188]
0x180062059  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006205d  test    rbx, rbx
0x180062060  jz      short loc_180062070
0x180062062  mov     rcx, rax
0x180062065  inc     rcx
0x180062068  cmp     byte ptr [rbx+rcx], 0
0x18006206c  jnz     short loc_180062065
0x18006206e  jmp     short loc_180062072
0x180062070  xor     ecx, ecx
0x180062072  inc     rax
0x180062075  cmp     byte ptr [rdi+rax], 0
0x180062079  jnz     short loc_180062072
0x18006207b  lea     r14d, [rcx+2]
0x18006207f  add     r14d, eax
0x180062082  mov     ecx, r14d
0x180062085  call    cs:__imp_PszAllocA
0x18006208b  mov     rsi, rax
0x18006208e  test    rax, rax
0x180062091  jz      short loc_1800620C6
0x180062093  mov     edx, r14d; unsigned __int64
0x180062096  lea     r8, aSS_2; "%s/%s"
0x18006209d  mov     r9, rdi
0x1800620a0  mov     qword ptr [rsp+1C0h+var_1A0], rbx
0x1800620a5  mov     rcx, rax; char *
0x1800620a8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800620ad  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800620b4  mov     rdx, rdi
0x1800620b7  mov     r8, [rcx]
0x1800620ba  mov     rax, [r8+28h]
0x1800620be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620c3  mov     rdi, rsi
0x1800620c6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800620cd  mov     rdx, rbx
0x1800620d0  mov     rax, [rcx]
0x1800620d3  mov     rax, [rax+28h]
0x1800620d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620dc  jmp     short loc_18006212B
0x1800620de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800620e2  inc     rax
0x1800620e5  cmp     byte ptr [rdi+rax], 0
0x1800620e9  jnz     short loc_1800620E2
0x1800620eb  lea     esi, [rax+3]
0x1800620ee  mov     ecx, esi
0x1800620f0  call    cs:__imp_PszAllocA
0x1800620f6  mov     rbx, rax
0x1800620f9  test    rax, rax
0x1800620fc  jz      short loc_18006212B
0x1800620fe  mov     edx, esi; unsigned __int64
0x180062100  lea     r8, aS_3; "%s/."
0x180062107  mov     r9, rdi
0x18006210a  mov     rcx, rax; char *
0x18006210d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180062112  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180062119  mov     rdx, [rcx]
0x18006211c  mov     rax, [rdx+28h]
0x180062120  mov     rdx, rdi
0x180062123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062128  mov     rdi, rbx
0x18006212b  mov     r8, rdi; char *
0x18006212e  mov     edx, 0FFh; unsigned __int64
0x180062133  mov     rcx, r12; char *
0x180062136  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006213b  mov     rcx, [r15+80h]; this
0x180062142  mov     r8, r12; char *
0x180062145  mov     edx, 14h; char *
0x18006214a  call    ?SetPropA@CMimePropertyContainer@@QEAAJPEBD0@Z; CMimePropertyContainer::SetPropA(char const *,char const *)
0x18006214f  mov     ebx, eax
0x180062151  test    rdi, rdi
0x180062154  jz      short loc_1800621A7
0x180062156  mov     rdx, rdi
0x180062159  jmp     short loc_180062194
0x18006215b  mov     rcx, [r15+80h]; this
0x180062162  lea     r8, [rsp+1C0h+var_180]; char **
0x180062167  mov     edx, 14h; char *
0x18006216c  call    ?GetPropA@CMimePropertyContainer@@QEAAJPEBDPEAPEAD@Z; CMimePropertyContainer::GetPropA(char const *,char * *)
0x180062171  mov     r10, [rsp+1C0h+var_180]
0x180062176  mov     ebx, eax
0x180062178  test    eax, eax
0x18006217a  js      short loc_18006218C
0x18006217c  mov     r8, r10; char *
0x18006217f  mov     edx, 0FFh; unsigned __int64
0x180062184  mov     rcx, r12; char *
0x180062187  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18006218c  test    r10, r10
0x18006218f  jz      short loc_1800621A7
0x180062191  mov     rdx, r10
0x180062194  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18006219b  mov     rax, [rcx]
0x18006219e  mov     rax, [rax+28h]
0x1800621a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800621a7  mov     eax, ebx
0x1800621a9  mov     rcx, [rbp+0C0h+var_40]
0x1800621b0  xor     rcx, rsp; StackCookie
0x1800621b3  call    __security_check_cookie
0x1800621b8  add     rsp, 190h
0x1800621bf  pop     r15
0x1800621c1  pop     r14
0x1800621c3  pop     r12
0x1800621c5  pop     rdi
0x1800621c6  pop     rsi
0x1800621c7  pop     rbx
0x1800621c8  pop     rbp
0x1800621c9  retn
```
