# PROTOCOL_BINDING_TABLE::InsertOrUpdateNoLock(IAppHostSite *,ushort const *,ushort const *,PROTOCOL_BINDING_ENTRY * *)

- ea: `0x1800588e8`
- end: `0x180058b5c`
- name: `?InsertOrUpdateNoLock@PROTOCOL_BINDING_TABLE@@QEAAJPEAUIAppHostSite@@PEBG1PEAPEAVPROTOCOL_BINDING_ENTRY@@@Z`
- size: `628`
- prototype: `__int64 __fastcall(PROTOCOL_BINDING_TABLE *this, struct IAppHostSite *, const unsigned __int16 *, wchar_t *, struct PROTOCOL_BINDING_ENTRY **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180058b64`

## callees

- `0x18003fec0`
- `0x180050f2c`
- `0x18005796c`
- `0x1800587e4`
- `0x1800588e8`
- `0x18006101a`
- `0x180061060`
- `0x180062010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180058aea`
- `OLEAUT32!__imp_SysFreeString` at `0x180058b0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180058aea`
- `OLEAUT32!__imp_SysFreeString` at `0x180058b0b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b1f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b33`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b1f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058b33`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005897a`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18005897a`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800589de`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058a54`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800589de`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180058a54`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800589fa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800589fa`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180058947`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005896f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180058947`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005896f`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058a6d`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058a6d`

## pseudocode

```c
__int64 __fastcall PROTOCOL_BINDING_TABLE::InsertOrUpdateNoLock(
        PROTOCOL_BINDING_TABLE *this,
        struct IAppHostSite *a2,
        const unsigned __int16 *a3,
        wchar_t *a4,
        struct PROTOCOL_BINDING_ENTRY **a5)
{
  __int64 v9; // rax
  int inserted; // ebx
  int v11; // r8d
  __int64 Key; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  struct PROTOCOL_BINDING_ENTRY *v15; // rdi
  OLECHAR *v16; // rcx
  unsigned int v18; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v20; // [rsp+40h] [rbp-C0h] BYREF
  struct PROTOCOL_BINDING_ENTRY *v21; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v23; // [rsp+70h] [rbp-90h]
  unsigned int v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[32]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v26; // [rsp+A8h] [rbp-58h]
  _BYTE v27[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v28; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v29[256]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v30[256]; // [rsp+300h] [rbp+200h] BYREF

  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v25, v29, 0x100u);
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v27, v30, 0x100u);
  STRU::STRU((STRU *)v22);
  v9 = *(_QWORD *)a2;
  v18 = 0;
  bstrString = 0;
  v20 = 0;
  inserted = (*(__int64 (__fastcall **)(struct IAppHostSite *, unsigned int *))(v9 + 64))(a2, &v18);
  if ( inserted < 0 )
    goto LABEL_15;
  inserted = (*(__int64 (__fastcall **)(struct IAppHostSite *, BSTR *))(*(_QWORD *)a2 + 56LL))(a2, &bstrString);
  if ( inserted < 0 )
    goto LABEL_15;
  inserted = STRU::Copy((STRU *)v22, a3);
  if ( inserted < 0 )
    goto LABEL_15;
  inserted = STRU::Append((STRU *)v22, L"://");
  if ( inserted < 0 )
    goto LABEL_15;
  inserted = BindingStringToUrlPrefix(a4, v23, v24, v18, (struct STRU *)v25, (const unsigned __int16 **)&v20);
  if ( inserted < 0 )
    goto LABEL_15;
  if ( v20 )
  {
    inserted = STRU::Copy((STRU *)v27, ++v20);
    if ( inserted < 0 )
      goto LABEL_15;
  }
  inserted = STRU::Append((STRU *)v25, 0x2Fu);
  if ( inserted < 0 )
    goto LABEL_15;
  Key = (__int64)STATIC_WSTRING_HASH::FindKey((PROTOCOL_BINDING_TABLE *)((char *)this + 8), v26, v11);
  v13 = Key - 8;
  v14 = -Key;
  v15 = (struct PROTOCOL_BINDING_ENTRY *)(v13 & -(__int64)(v14 != 0));
  v21 = v15;
  if ( v15 )
  {
    inserted = PROTOCOL_BINDING_ENTRY::AddIpScope(
                 (PROTOCOL_BINDING_ENTRY *)(v13 & -(__int64)(v14 != 0)),
                 v18,
                 bstrString,
                 v28);
    if ( inserted >= 0 )
      goto LABEL_13;
LABEL_15:
    v16 = bstrString;
    goto LABEL_16;
  }
  inserted = PROTOCOL_BINDING_TABLE::InsertNoLock(this, v18, bstrString, v26, v28, &v21);
  if ( inserted < 0 )
    goto LABEL_15;
  v15 = v21;
LABEL_13:
  SysFreeString(bstrString);
  v16 = 0;
  bstrString = 0;
  if ( !a5 )
    goto LABEL_18;
  *a5 = v15;
LABEL_16:
  if ( v16 )
  {
    SysFreeString(v16);
    bstrString = 0;
  }
LABEL_18:
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v25);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800588e8  push    rbp
0x1800588ea  push    rbx
0x1800588eb  push    rsi
0x1800588ec  push    rdi
0x1800588ed  push    r12
0x1800588ef  push    r14
0x1800588f1  push    r15
0x1800588f3  lea     rbp, [rsp-410h]
0x1800588fb  sub     rsp, 510h
0x180058902  mov     rax, cs:__security_cookie
0x180058909  xor     rax, rsp
0x18005890c  mov     [rbp+440h+var_40], rax
0x180058913  mov     rsi, [rbp+440h+arg_20]
0x18005891a  mov     r15, r8
0x18005891d  mov     rdi, rdx
0x180058920  mov     r14, rcx
0x180058923  xor     edx, edx; Val
0x180058925  lea     rcx, [rbp+440h+var_440]; void *
0x180058929  mov     r8d, 200h; Size
0x18005892f  mov     r12, r9
0x180058932  call    memset_0
0x180058937  mov     ebx, 100h
0x18005893c  lea     rdx, [rbp+440h+var_440]
0x180058940  mov     r8d, ebx
0x180058943  lea     rcx, [rbp+440h+var_4B8]
0x180058947  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18005894d  xor     edx, edx; Val
0x18005894f  lea     rcx, [rbp+440h+var_240]; void *
0x180058956  mov     r8d, 200h; Size
0x18005895c  call    memset_0
0x180058961  mov     r8d, ebx
0x180058964  lea     rdx, [rbp+440h+var_240]
0x18005896b  lea     rcx, [rbp+440h+var_480]
0x18005896f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180058975  lea     rcx, [rsp+540h+var_4F0]
0x18005897a  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180058980  mov     rax, [rdi]
0x180058983  lea     rdx, [rsp+540h+var_510]
0x180058988  mov     rcx, rdi
0x18005898b  mov     [rsp+540h+var_510], 0
0x180058993  mov     [rsp+540h+bstrString], 0
0x18005899c  mov     [rsp+540h+var_500], 0
0x1800589a5  mov     rax, [rax+40h]
0x1800589a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589ae  mov     ebx, eax
0x1800589b0  test    eax, eax
0x1800589b2  js      loc_180058B01
0x1800589b8  mov     rax, [rdi]
0x1800589bb  lea     rdx, [rsp+540h+bstrString]
0x1800589c0  mov     rcx, rdi
0x1800589c3  mov     rax, [rax+38h]
0x1800589c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589cc  mov     ebx, eax
0x1800589ce  test    eax, eax
0x1800589d0  js      loc_180058B01
0x1800589d6  mov     rdx, r15
0x1800589d9  lea     rcx, [rsp+540h+var_4F0]
0x1800589de  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800589e4  mov     ebx, eax
0x1800589e6  test    eax, eax
0x1800589e8  js      loc_180058B01
0x1800589ee  lea     rdx, asc_18007D400; "://"
0x1800589f5  lea     rcx, [rsp+540h+var_4F0]
0x1800589fa  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058a00  mov     ebx, eax
0x180058a02  test    eax, eax
0x180058a04  js      loc_180058B01
0x180058a0a  mov     r9d, [rsp+540h+var_510]; unsigned int
0x180058a0f  lea     rax, [rsp+540h+var_500]
0x180058a14  mov     r8d, [rbp+440h+var_4C0]; unsigned int
0x180058a18  mov     rcx, r12; String
0x180058a1b  mov     rdx, [rsp+540h+var_4D0]; unsigned __int16 *
0x180058a20  mov     [rsp+540h+var_518], rax; unsigned __int16 **
0x180058a25  lea     rax, [rbp+440h+var_4B8]
0x180058a29  mov     [rsp+540h+var_520], rax; struct STRU *
0x180058a2e  call    ?BindingStringToUrlPrefix@@YAJPEBG0KKPEAVSTRU@@PEAPEBG@Z; BindingStringToUrlPrefix(ushort const *,ushort const *,ulong,ulong,STRU *,ushort const * *)
0x180058a33  mov     ebx, eax
0x180058a35  test    eax, eax
0x180058a37  js      loc_180058B01
0x180058a3d  mov     rdx, [rsp+540h+var_500]
0x180058a42  test    rdx, rdx
0x180058a45  jz      short loc_180058A64
0x180058a47  add     rdx, 2
0x180058a4b  lea     rcx, [rbp+440h+var_480]
0x180058a4f  mov     [rsp+540h+var_500], rdx
0x180058a54  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180058a5a  mov     ebx, eax
0x180058a5c  test    eax, eax
0x180058a5e  js      loc_180058B01
0x180058a64  mov     edx, 2Fh ; '/'
0x180058a69  lea     rcx, [rbp+440h+var_4B8]
0x180058a6d  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180058a73  mov     ebx, eax
0x180058a75  test    eax, eax
0x180058a77  js      loc_180058B01
0x180058a7d  mov     rdx, [rbp+440h+var_498]; unsigned __int16 *
0x180058a81  lea     rcx, [r14+8]; this
0x180058a85  call    ?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z; STATIC_WSTRING_HASH::FindKey(ushort const *,int)
0x180058a8a  mov     r8, [rsp+540h+bstrString]; unsigned __int16 *
0x180058a8f  mov     edx, [rsp+540h+var_510]; unsigned int
0x180058a93  lea     rcx, [rax-8]
0x180058a97  neg     rax
0x180058a9a  sbb     rdi, rdi
0x180058a9d  and     rdi, rcx
0x180058aa0  mov     [rsp+540h+var_4F8], rdi
0x180058aa5  jnz     short loc_180058AD3
0x180058aa7  mov     rax, [rbp+440h+var_460]
0x180058aab  lea     rcx, [rsp+540h+var_4F8]
0x180058ab0  mov     r9, [rbp+440h+var_498]; unsigned __int16 *
0x180058ab4  mov     [rsp+540h+var_518], rcx; struct PROTOCOL_BINDING_ENTRY **
0x180058ab9  mov     rcx, r14; this
0x180058abc  mov     [rsp+540h+var_520], rax; unsigned __int16 *
0x180058ac1  call    ?InsertNoLock@PROTOCOL_BINDING_TABLE@@AEAAJKPEBG00PEAPEAVPROTOCOL_BINDING_ENTRY@@@Z; PROTOCOL_BINDING_TABLE::InsertNoLock(ulong,ushort const *,ushort const *,ushort const *,PROTOCOL_BINDING_ENTRY * *)
0x180058ac6  mov     ebx, eax
0x180058ac8  test    eax, eax
0x180058aca  js      short loc_180058B01
0x180058acc  mov     rdi, [rsp+540h+var_4F8]
0x180058ad1  jmp     short loc_180058AE5
0x180058ad3  mov     r9, [rbp+440h+var_460]; unsigned __int16 *
0x180058ad7  mov     rcx, rdi; this
0x180058ada  call    ?AddIpScope@PROTOCOL_BINDING_ENTRY@@QEAAJKPEBG0@Z; PROTOCOL_BINDING_ENTRY::AddIpScope(ulong,ushort const *,ushort const *)
0x180058adf  mov     ebx, eax
0x180058ae1  test    eax, eax
0x180058ae3  js      short loc_180058B01
0x180058ae5  mov     rcx, [rsp+540h+bstrString]; bstrString
0x180058aea  call    cs:__imp_SysFreeString
0x180058af0  xor     ecx, ecx
0x180058af2  mov     [rsp+540h+bstrString], rcx
0x180058af7  test    rsi, rsi
0x180058afa  jz      short loc_180058B1A
0x180058afc  mov     [rsi], rdi
0x180058aff  jmp     short loc_180058B06
0x180058b01  mov     rcx, [rsp+540h+bstrString]; bstrString
0x180058b06  test    rcx, rcx
0x180058b09  jz      short loc_180058B1A
0x180058b0b  call    cs:__imp_SysFreeString
0x180058b11  mov     [rsp+540h+bstrString], 0
0x180058b1a  lea     rcx, [rsp+540h+var_4F0]
0x180058b1f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180058b25  lea     rcx, [rbp+440h+var_480]
0x180058b29  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180058b2f  lea     rcx, [rbp+440h+var_4B8]
0x180058b33  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180058b39  mov     eax, ebx
0x180058b3b  mov     rcx, [rbp+440h+var_40]
0x180058b42  xor     rcx, rsp; StackCookie
0x180058b45  call    __security_check_cookie
0x180058b4a  add     rsp, 510h
0x180058b51  pop     r15
0x180058b53  pop     r14
0x180058b55  pop     r12
0x180058b57  pop     rdi
0x180058b58  pop     rsi
0x180058b59  pop     rbx
0x180058b5a  pop     rbp
0x180058b5b  retn
```
