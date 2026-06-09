# IP_MODULE::GetSiteContext(IHttpSite *,SITE_CONTEXT * *)

- ea: `0x1800057cc`
- end: `0x180005aaf`
- name: `?GetSiteContext@IP_MODULE@@CAJPEAVIHttpSite@@PEAPEAVSITE_CONTEXT@@@Z`
- size: `739`
- prototype: `__int64 __fastcall(struct IHttpSite *, struct SITE_CONTEXT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800062b0`

## callees

- `0x180001008`
- `0x180001948`
- `0x180001a2c`
- `0x180002efc`
- `0x1800053b0`
- `0x1800057cc`
- `0x180005d74`
- `0x180005e7c`
- `0x1800067c0`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a84`
- `iisutil!PuDbgPrint` at `0x180005a0f`
- `iisutil!PuDbgPrint` at `0x180005a0f`

## string_xrefs

- `0x1800059d5`: `servercommon\inetsrv\iis\iisrearc\iis70\dynamiciprestriction\dipmodule.cpp`

## pseudocode

```c
__int64 __fastcall IP_MODULE::GetSiteContext(struct IHttpSite *a1, struct SITE_CONTEXT **a2)
{
  _BYTE *v4; // rax
  int appended; // edi
  __int64 v6; // r8
  int Item; // eax
  char *v8; // rbx
  int v9; // eax
  struct SITE_CONTEXT *v10; // rsi
  struct STTABLE_ITEM *v12[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v13; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v14; // [rsp+48h] [rbp-B8h]
  unsigned int v15; // [rsp+50h] [rbp-B0h]
  char v16; // [rsp+5Ch] [rbp-A4h] BYREF
  void **v17; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp-58h]
  unsigned int v19; // [rsp+B0h] [rbp-50h]
  char v20; // [rsp+BCh] [rbp-44h] BYREF

  v12[0] = 0;
  STBUFF::STBUFF((STBUFF *)&v13);
  *a2 = 0;
  v4 = (_BYTE *)(*(__int64 (__fastcall **)(struct IHttpSite *))(*(_QWORD *)a1 + 8LL))(a1);
  if ( !v4 )
  {
    appended = -2147024809;
    goto LABEL_27;
  }
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&v4[2 * v6] );
  appended = STBUFF::AppendData((STBUFF *)&v13, v4, 2 * (int)v6, 0);
  if ( appended >= 0 )
  {
    Item = STTABLE::GetItem(g_pSiteHashTable, (struct STBUFF *)&v13, v12);
    appended = Item;
    if ( Item >= 0 )
    {
      if ( v12[0] )
        *a2 = v12[0];
      goto LABEL_27;
    }
    if ( Item != -2147024894 )
      goto LABEL_27;
    v8 = (char *)operator new(0xE8u);
    if ( !v8 )
    {
      appended = -2147024882;
      goto LABEL_27;
    }
    *((_DWORD *)v8 + 6) = 1;
    *(_QWORD *)v8 = &STTABLE_ITEM::`vftable';
    STBUFF::STBUFF((STBUFF *)(v8 + 32));
    *((_QWORD *)v8 + 16) = 0;
    *((_QWORD *)v8 + 2) = v8 + 8;
    *((_QWORD *)v8 + 1) = v8 + 8;
    *(_QWORD *)v8 = &SITE_CONTEXT::`vftable';
    STBUFF::STBUFF((STBUFF *)(v8 + 136));
    *((_BYTE *)v14 + v15) = 0;
    *((_BYTE *)v14 + v15 + 1) = 0;
    appended = SITE_CONTEXT::Initialize((SITE_CONTEXT *)v8, (const unsigned __int16 *)v14);
    if ( appended < 0 )
      goto LABEL_24;
    v9 = STTABLE::Insert(g_pSiteHashTable, (struct STTABLE_ITEM *)v8);
    appended = v9;
    if ( v9 >= 0 )
    {
      STBUFF::STBUFF((STBUFF *)&v17);
      *((_BYTE *)v14 + v15) = 0;
      *((_BYTE *)v14 + v15 + 1) = 0;
      STBUFF::UnicodeToAnsi((STBUFF *)&v17, (unsigned __int16 *)v14);
      if ( (g_dwDebugFlags & 3) != 0 )
      {
        *((_BYTE *)hMem + v19) = 0;
        *((_BYTE *)hMem + v19 + 1) = 0;
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\dynamiciprestriction\\dipmodule.cpp",
          816,
          "IP_MODULE::GetSiteContext",
          "Added record for Site %s.\n",
          (const char *)hMem);
      }
      v17 = &STBUFF::`vftable';
      v10 = (struct SITE_CONTEXT *)v8;
      if ( hMem != &v20 )
        LocalFree(hMem);
LABEL_22:
      *a2 = v10;
      if ( appended >= 0 || !v8 )
        goto LABEL_27;
      goto LABEL_24;
    }
    if ( v9 != -2147024713 )
    {
LABEL_24:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 6, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(void *, __int64))v8)(v8, 1);
      goto LABEL_27;
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 6, 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(void *, __int64))v8)(v8, 1);
    appended = STTABLE::GetItem(g_pSiteHashTable, (struct STBUFF *)&v13, v12);
    if ( appended >= 0 )
    {
      v10 = v12[0];
      v8 = 0;
      goto LABEL_22;
    }
  }
LABEL_27:
  v13 = &STBUFF::`vftable';
  if ( v14 != &v16 )
    LocalFree(v14);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800057cc  mov     [rsp-8+arg_10], rbx
0x1800057d1  push    rbp
0x1800057d2  push    rsi
0x1800057d3  push    rdi
0x1800057d4  push    r14
0x1800057d6  push    r15
0x1800057d8  lea     rbp, [rsp-10h]
0x1800057dd  sub     rsp, 110h
0x1800057e4  mov     rax, cs:__security_cookie
0x1800057eb  xor     rax, rsp
0x1800057ee  mov     [rbp+30h+var_30], rax
0x1800057f2  mov     rbx, rcx
0x1800057f5  xor     r15d, r15d
0x1800057f8  lea     rcx, [rsp+130h+var_F0]; this
0x1800057fd  mov     [rsp+130h+var_100], r15
0x180005802  mov     r14, rdx
0x180005805  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x18000580a  mov     [r14], r15
0x18000580d  mov     rcx, rbx
0x180005810  mov     rax, [rbx]
0x180005813  mov     rax, [rax+8]
0x180005817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581c  test    rax, rax
0x18000581f  jnz     short loc_18000582B
0x180005821  mov     edi, 80070057h
0x180005826  jmp     loc_180005A69
0x18000582b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000582f  inc     r8
0x180005832  cmp     [rax+r8*2], r15w
0x180005837  jnz     short loc_18000582F
0x180005839  add     r8d, r8d; unsigned int
0x18000583c  lea     rcx, [rsp+130h+var_F0]; this
0x180005841  xor     r9d, r9d; unsigned int
0x180005844  mov     rdx, rax; void *
0x180005847  call    ?AppendData@STBUFF@@QEAAJPEAXKK@Z; STBUFF::AppendData(void *,ulong,ulong)
0x18000584c  mov     edi, eax
0x18000584e  test    eax, eax
0x180005850  js      loc_180005A69
0x180005856  mov     rcx, cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA; this
0x18000585d  lea     r8, [rsp+130h+var_100]; struct STTABLE_ITEM **
0x180005862  lea     rdx, [rsp+130h+var_F0]; struct STBUFF *
0x180005867  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x18000586c  mov     edi, eax
0x18000586e  test    eax, eax
0x180005870  js      short loc_180005888
0x180005872  mov     rax, [rsp+130h+var_100]
0x180005877  test    rax, rax
0x18000587a  jz      loc_180005A69
0x180005880  mov     [r14], rax
0x180005883  jmp     loc_180005A69
0x180005888  cmp     eax, 80070002h
0x18000588d  jnz     loc_180005A69
0x180005893  mov     ecx, 0E8h; Size
0x180005898  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000589d  mov     rbx, rax
0x1800058a0  test    rax, rax
0x1800058a3  jz      loc_180005A64
0x1800058a9  lea     rax, ??_7STTABLE_ITEM@@6B@; const STTABLE_ITEM::`vftable'
0x1800058b0  mov     dword ptr [rbx+18h], 1
0x1800058b7  lea     rcx, [rbx+20h]; this
0x1800058bb  mov     [rbx], rax
0x1800058be  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800058c3  lea     rax, [rbx+8]
0x1800058c7  mov     [rbx+80h], r15
0x1800058ce  mov     [rax+8], rax
0x1800058d2  lea     rcx, [rbx+88h]; this
0x1800058d9  mov     [rax], rax
0x1800058dc  lea     rax, ??_7SITE_CONTEXT@@6B@; const SITE_CONTEXT::`vftable'
0x1800058e3  mov     [rbx], rax
0x1800058e6  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x1800058eb  mov     ecx, [rsp+130h+var_E0]
0x1800058ef  mov     rax, [rsp+130h+var_E8]
0x1800058f4  mov     [rcx+rax], r15b
0x1800058f8  mov     ecx, [rsp+130h+var_E0]
0x1800058fc  mov     rax, [rsp+130h+var_E8]
0x180005901  inc     ecx
0x180005903  mov     [rcx+rax], r15b
0x180005907  mov     rcx, rbx; this
0x18000590a  mov     rdx, [rsp+130h+var_E8]; unsigned __int16 *
0x18000590f  call    ?Initialize@SITE_CONTEXT@@QEAAJPEBG@Z; SITE_CONTEXT::Initialize(ushort const *)
0x180005914  mov     edi, eax
0x180005916  test    eax, eax
0x180005918  js      loc_180005A42
0x18000591e  mov     rcx, cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA; this
0x180005925  mov     rdx, rbx; struct STTABLE_ITEM *
0x180005928  call    ?Insert@STTABLE@@QEAAJPEAVSTTABLE_ITEM@@@Z; STTABLE::Insert(STTABLE_ITEM *)
0x18000592d  mov     edi, eax
0x18000592f  test    eax, eax
0x180005931  jns     short loc_18000598B
0x180005933  cmp     eax, 800700B7h
0x180005938  jnz     loc_180005A42
0x18000593e  or      eax, 0FFFFFFFFh
0x180005941  lock xadd [rbx+18h], eax
0x180005946  cmp     eax, 1
0x180005949  jnz     short loc_18000595E
0x18000594b  mov     rax, [rbx]
0x18000594e  mov     edx, 1
0x180005953  mov     rcx, rbx
0x180005956  mov     rax, [rax]
0x180005959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000595e  mov     rcx, cs:?g_pSiteHashTable@@3PEAVSTTABLE@@EA; this
0x180005965  lea     r8, [rsp+130h+var_100]; struct STTABLE_ITEM **
0x18000596a  lea     rdx, [rsp+130h+var_F0]; struct STBUFF *
0x18000596f  call    ?GetItem@STTABLE@@QEAAJPEAVSTBUFF@@PEAPEAVSTTABLE_ITEM@@@Z; STTABLE::GetItem(STBUFF *,STTABLE_ITEM * *)
0x180005974  mov     edi, eax
0x180005976  test    eax, eax
0x180005978  js      loc_180005A69
0x18000597e  mov     rsi, [rsp+130h+var_100]
0x180005983  mov     rbx, r15
0x180005986  jmp     loc_180005A36
0x18000598b  lea     rcx, [rbp+30h+var_90]; this
0x18000598f  call    ??0STBUFF@@QEAA@H@Z; STBUFF::STBUFF(int)
0x180005994  mov     ecx, [rsp+130h+var_E0]
0x180005998  mov     rax, [rsp+130h+var_E8]
0x18000599d  mov     [rcx+rax], r15b
0x1800059a1  mov     ecx, [rsp+130h+var_E0]
0x1800059a5  mov     rax, [rsp+130h+var_E8]
0x1800059aa  inc     ecx
0x1800059ac  mov     [rcx+rax], r15b
0x1800059b0  lea     rcx, [rbp+30h+var_90]; this
0x1800059b4  mov     rdx, [rsp+130h+var_E8]; unsigned __int16 *
0x1800059b9  call    ?UnicodeToAnsi@STBUFF@@QEAAJPEAG@Z; STBUFF::UnicodeToAnsi(ushort *)
0x1800059be  test    byte ptr cs:g_dwDebugFlags, 3
0x1800059c5  jz      short loc_180005A15
0x1800059c7  mov     ecx, [rbp+30h+var_80]
0x1800059ca  lea     r9, aIpModuleGetsit; "IP_MODULE::GetSiteContext"
0x1800059d1  mov     rax, [rbp+30h+hMem]
0x1800059d5  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800059dc  mov     r8d, 330h
0x1800059e2  mov     [rcx+rax], r15b
0x1800059e6  mov     ecx, [rbp+30h+var_80]
0x1800059e9  mov     rax, [rbp+30h+hMem]
0x1800059ed  inc     ecx
0x1800059ef  mov     [rcx+rax], r15b
0x1800059f3  mov     rax, [rbp+30h+hMem]
0x1800059f7  mov     rcx, cs:g_pDebug
0x1800059fe  mov     [rsp+130h+var_108], rax
0x180005a03  lea     rax, aAddedRecordFor_0; "Added record for Site %s.\n"
0x180005a0a  mov     [rsp+130h+var_110], rax
0x180005a0f  call    cs:__imp_PuDbgPrint
0x180005a15  mov     rcx, [rbp+30h+hMem]; hMem
0x180005a19  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180005a20  mov     [rbp+30h+var_90], rax
0x180005a24  mov     rsi, rbx
0x180005a27  lea     rax, [rbp+30h+var_74]
0x180005a2b  cmp     rcx, rax
0x180005a2e  jz      short loc_180005A36
0x180005a30  call    cs:__imp_LocalFree
0x180005a36  mov     [r14], rsi
0x180005a39  test    edi, edi
0x180005a3b  jns     short loc_180005A69
0x180005a3d  test    rbx, rbx
0x180005a40  jz      short loc_180005A69
0x180005a42  or      eax, 0FFFFFFFFh
0x180005a45  lock xadd [rbx+18h], eax
0x180005a4a  cmp     eax, 1
0x180005a4d  jnz     short loc_180005A69
0x180005a4f  mov     rax, [rbx]
0x180005a52  mov     edx, 1
0x180005a57  mov     rcx, rbx
0x180005a5a  mov     rax, [rax]
0x180005a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a62  jmp     short loc_180005A69
0x180005a64  mov     edi, 8007000Eh
0x180005a69  mov     rcx, [rsp+130h+var_E8]; hMem
0x180005a6e  lea     rax, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x180005a75  mov     [rsp+130h+var_F0], rax
0x180005a7a  lea     rax, [rsp+130h+var_D4]
0x180005a7f  cmp     rcx, rax
0x180005a82  jz      short loc_180005A8A
0x180005a84  call    cs:__imp_LocalFree
0x180005a8a  mov     eax, edi
0x180005a8c  mov     rcx, [rbp+30h+var_30]
0x180005a90  xor     rcx, rsp; StackCookie
0x180005a93  call    __security_check_cookie
0x180005a98  mov     rbx, [rsp+130h+arg_10]
0x180005aa0  add     rsp, 110h
0x180005aa7  pop     r15
0x180005aa9  pop     r14
0x180005aab  pop     rdi
0x180005aac  pop     rsi
0x180005aad  pop     rbp
0x180005aae  retn
```
