# CSyncMLCmdReplace::ReplaceNodeProperty(CSyncMLItem *,IConfigNode *,IConfigManager2URI *)

- ea: `0x1800212c8`
- end: `0x18002161c`
- name: `?ReplaceNodeProperty@CSyncMLCmdReplace@@AEBAJPEAVCSyncMLItem@@PEAUIConfigNode@@PEAUIConfigManager2URI@@@Z`
- size: `852`
- prototype: `int(CSyncMLCmdReplace *__hidden this, struct CSyncMLItem *, struct IConfigNode *, struct IConfigManager2URI *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bc70`

## callees

- `0x1800032d0`
- `0x1800034d0`
- `0x180010654`
- `0x180014330`
- `0x180016208`
- `0x1800212c8`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800213db`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800213db`
- `OLEAUT32!__imp_SysAllocString` at `0x180021522`
- `OLEAUT32!__imp_SysAllocString` at `0x180021522`
- `OLEAUT32!__imp_VariantInit` at `0x18002131e`
- `OLEAUT32!__imp_VariantInit` at `0x18002131e`
- `OLEAUT32!__imp_VariantClear` at `0x1800215c9`
- `OLEAUT32!__imp_VariantClear` at `0x1800215c9`
- `DMCmnUtils!InvStrCmpIW` at `0x180021353`
- `DMCmnUtils!InvStrCmpIW` at `0x180021353`

## pseudocode

```c
__int64 __fastcall CSyncMLCmdReplace::ReplaceNodeProperty(
        CSyncMLCmdReplace *this,
        const unsigned __int16 **a2,
        struct IConfigNode *a3,
        struct IConfigManager2URI *a4)
{
  __int64 v4; // rbx
  int v8; // ebx
  const unsigned __int16 *Type; // rax
  const OLECHAR *v10; // rcx
  __int128 v11; // xmm0
  const wchar_t *v12; // rsi
  int v13; // eax
  int v14; // eax
  const unsigned __int16 *v15; // rcx
  __int64 v16; // rax
  __int128 v17; // xmm0
  __int64 v18; // rax
  __int64 (__fastcall *v19)(struct IConfigNode *, __int128 *, VARIANTARG *); // rax
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v23; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h] BYREF
  int v25; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG v28; // [rsp+70h] [rbp-9h] BYREF
  __int128 v29; // [rsp+90h] [rbp+17h] BYREF

  v4 = *((int *)a2 + 25);
  v23 = 0;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v26 = 0;
  VariantInit(&pvarg);
  if ( (unsigned int)CSyncMLItem::GetFormat(a2) != 1 )
    goto LABEL_2;
  Type = CSyncMLItem::GetType((CSyncMLItem *)a2);
  if ( InvStrCmpIW(Type, L"text/plain") )
    goto LABEL_2;
  if ( (int)v4 > 9 )
  {
    if ( (_DWORD)v4 != 10 )
    {
      if ( (_DWORD)v4 == 11 )
      {
        v15 = a2[10];
        if ( !v15 )
        {
          v11 = xmmword_18003E8B0;
          goto LABEL_34;
        }
        v8 = MultipleToVariant(v15, &pvarg);
        if ( v8 < 0 )
          goto LABEL_42;
        v17 = xmmword_18003E8B0;
LABEL_40:
        v18 = *(_QWORD *)a3;
        v29 = v17;
        v19 = *(__int64 (__fastcall **)(struct IConfigNode *, __int128 *, VARIANTARG *))(v18 + 168);
        v28 = pvarg;
        v14 = v19(a3, &v29, &v28);
        goto LABEL_41;
      }
      if ( (_DWORD)v4 != 12 && (_DWORD)v4 != 13 )
      {
        if ( (_DWORD)v4 != 14 )
          goto LABEL_31;
        goto LABEL_19;
      }
    }
LABEL_12:
    v10 = a2[10];
    if ( !v10 )
    {
      v11 = *((_OWORD *)&gc_pgmPropsToGuid + v4);
LABEL_34:
      v16 = *(_QWORD *)a3;
      v29 = v11;
      v14 = (*(__int64 (__fastcall **)(struct IConfigNode *, __int128 *))(v16 + 176))(a3, &v29);
      goto LABEL_41;
    }
    pvarg.llVal = (LONGLONG)SysAllocString(v10);
    if ( !pvarg.llVal )
    {
      v8 = -2147024882;
      goto LABEL_42;
    }
    pvarg.vt = 8;
    v17 = *((_OWORD *)&gc_pgmPropsToGuid + v4);
    goto LABEL_40;
  }
  if ( (_DWORD)v4 == 9 || (_DWORD)v4 == 1 )
    goto LABEL_12;
  if ( (_DWORD)v4 != 2 )
  {
    if ( (_DWORD)v4 == 3 )
      goto LABEL_19;
    if ( (_DWORD)v4 != 4 )
    {
      if ( (_DWORD)v4 != 5 )
      {
        if ( (_DWORD)v4 == 8 )
          goto LABEL_12;
LABEL_31:
        v8 = -2147418113;
        goto LABEL_42;
      }
LABEL_19:
      v8 = -2046820335;
      goto LABEL_42;
    }
    goto LABEL_12;
  }
  v12 = a2[10];
  if ( !v12 || !*v12 || wcschr(v12, 0x2Fu) )
  {
LABEL_2:
    v8 = -2147024809;
    goto LABEL_42;
  }
  v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, unsigned int *))(*(_QWORD *)a4 + 136LL))(a4, &v23);
  if ( v8 < 0 )
    goto LABEL_42;
  if ( v23 <= 1 )
    goto LABEL_19;
  v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a4 + 144LL))(a4, 0, &v24);
  if ( v8 < 0 )
    goto LABEL_42;
  v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)v24 + 192LL))(
          v24,
          v23 - 1,
          v12,
          1);
  v8 = v13;
  if ( v13 >= 0 )
  {
    v14 = (*(__int64 (__fastcall **)(struct IConfigNode *, __int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 64LL))(
            a3,
            v24,
            0,
            &v26);
LABEL_41:
    v8 = v14;
    goto LABEL_42;
  }
  if ( v13 != -2147418113 && v13 != -2147024882 )
    v8 = -2102788095;
LABEL_42:
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v24 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  VariantClear(&pvarg);
  if ( (unsigned int)dword_18003E048 > 5 )
  {
    v25 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_18003E048,
      (unsigned __int8 *)byte_1800369E1,
      v20,
      v21,
      (__int64)&v25);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800212c8  push    rbp
0x1800212ca  push    rbx
0x1800212cb  push    rsi
0x1800212cc  push    rdi
0x1800212cd  push    r14
0x1800212cf  lea     rbp, [rsp-37h]
0x1800212d4  sub     rsp, 0B0h
0x1800212db  mov     rax, cs:__security_cookie
0x1800212e2  xor     rax, rsp
0x1800212e5  mov     [rbp+57h+var_30], rax
0x1800212e9  movsxd  rbx, dword ptr [rdx+64h]
0x1800212ed  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800212f1  xorps   xmm0, xmm0
0x1800212f4  mov     [rbp+57h+var_A0], 0
0x1800212fb  xor     eax, eax
0x1800212fd  mov     [rbp+57h+var_98], 0
0x180021305  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180021309  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18002130d  mov     r14, r9
0x180021310  mov     rdi, r8
0x180021313  mov     [rbp+57h+var_88], 0
0x18002131b  mov     rsi, rdx
0x18002131e  call    cs:__imp_VariantInit
0x180021325  nop     dword ptr [rax+rax+00h]
0x18002132a  mov     rcx, rsi
0x18002132d  call    ?GetFormat@CSyncMLItem@@QEBA?AW4ConfigDataType@@XZ; CSyncMLItem::GetFormat(void)
0x180021332  cmp     eax, 1
0x180021335  jz      short loc_180021341
0x180021337  mov     ebx, 80070057h
0x18002133c  jmp     loc_18002158B
0x180021341  mov     rcx, rsi; this
0x180021344  call    ?GetType@CSyncMLItem@@QEBAPEBGXZ; CSyncMLItem::GetType(void)
0x180021349  mov     rcx, rax
0x18002134c  lea     rdx, ?gc_szDefaultType@@3QBGB; "text/plain"
0x180021353  call    cs:__imp_?InvStrCmpIW@@YAHPEBG0@Z; InvStrCmpIW(ushort const *,ushort const *)
0x18002135a  nop     dword ptr [rax+rax+00h]
0x18002135f  test    eax, eax
0x180021361  jnz     short loc_180021337
0x180021363  cmp     ebx, 9
0x180021366  jg      loc_1800214A8
0x18002136c  jz      short loc_18002139A
0x18002136e  mov     ecx, ebx
0x180021370  sub     ecx, 1
0x180021373  jz      short loc_18002139A
0x180021375  sub     ecx, 1
0x180021378  jz      short loc_1800213BD
0x18002137a  sub     ecx, 1
0x18002137d  jz      loc_180021416
0x180021383  sub     ecx, 1
0x180021386  jz      short loc_18002139A
0x180021388  sub     ecx, 1
0x18002138b  jz      loc_180021416
0x180021391  cmp     ecx, 3
0x180021394  jnz     loc_1800214D3
0x18002139a  mov     rcx, [rsi+50h]; psz
0x18002139e  test    rcx, rcx
0x1800213a1  jnz     loc_180021522
0x1800213a7  mov     rax, rbx
0x1800213aa  lea     rcx, ?gc_pgmPropsToGuid@@3QBU_GUID@@B; _GUID const near * const gc_pgmPropsToGuid
0x1800213b1  add     rax, rax
0x1800213b4  movups  xmm0, xmmword ptr [rcx+rax*8]
0x1800213b8  jmp     loc_1800214ED
0x1800213bd  mov     rsi, [rsi+50h]
0x1800213c1  test    rsi, rsi
0x1800213c4  jz      loc_180021337
0x1800213ca  xor     eax, eax
0x1800213cc  cmp     ax, [rsi]
0x1800213cf  jz      loc_180021337
0x1800213d5  lea     edx, [rax+2Fh]; Ch
0x1800213d8  mov     rcx, rsi; Str
0x1800213db  call    cs:__imp_wcschr
0x1800213e2  nop     dword ptr [rax+rax+00h]
0x1800213e7  test    rax, rax
0x1800213ea  jnz     loc_180021337
0x1800213f0  mov     rax, [r14]
0x1800213f3  lea     rdx, [rbp+57h+var_A0]
0x1800213f7  mov     rcx, r14
0x1800213fa  mov     rax, [rax+88h]
0x180021401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021406  mov     ebx, eax
0x180021408  test    eax, eax
0x18002140a  js      loc_18002158B
0x180021410  cmp     [rbp+57h+var_A0], 1
0x180021414  ja      short loc_180021420
0x180021416  mov     ebx, 86000011h
0x18002141b  jmp     loc_18002158B
0x180021420  mov     rax, [r14]
0x180021423  lea     r8, [rbp+57h+var_98]
0x180021427  xor     edx, edx
0x180021429  mov     rcx, r14
0x18002142c  mov     rax, [rax+90h]
0x180021433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021438  mov     ebx, eax
0x18002143a  test    eax, eax
0x18002143c  js      loc_18002158B
0x180021442  mov     rcx, [rbp+57h+var_98]
0x180021446  mov     r9d, 1
0x18002144c  mov     edx, [rbp+57h+var_A0]
0x18002144f  mov     r8, rsi
0x180021452  dec     edx
0x180021454  mov     rax, [rcx]
0x180021457  mov     rax, [rax+0C0h]
0x18002145e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021463  mov     ebx, eax
0x180021465  test    eax, eax
0x180021467  jns     short loc_180021489
0x180021469  cmp     eax, 8000FFFFh
0x18002146e  jz      loc_18002158B
0x180021474  cmp     eax, 8007000Eh
0x180021479  jz      loc_18002158B
0x18002147f  mov     ebx, 82AA0001h
0x180021484  jmp     loc_18002158B
0x180021489  mov     rax, [rdi]
0x18002148c  lea     r9, [rbp+57h+var_88]
0x180021490  mov     rdx, [rbp+57h+var_98]
0x180021494  xor     r8d, r8d
0x180021497  mov     rcx, rdi
0x18002149a  mov     rax, [rax+40h]
0x18002149e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214a3  jmp     loc_180021589
0x1800214a8  mov     ecx, ebx
0x1800214aa  sub     ecx, 0Ah
0x1800214ad  jz      loc_18002139A
0x1800214b3  sub     ecx, 1
0x1800214b6  jz      short loc_1800214DD
0x1800214b8  sub     ecx, 1
0x1800214bb  jz      loc_18002139A
0x1800214c1  sub     ecx, 1
0x1800214c4  jz      loc_18002139A
0x1800214ca  cmp     ecx, 1
0x1800214cd  jz      loc_180021416
0x1800214d3  mov     ebx, 8000FFFFh
0x1800214d8  jmp     loc_18002158B
0x1800214dd  mov     rcx, [rsi+50h]; unsigned __int16 *
0x1800214e1  test    rcx, rcx
0x1800214e4  jnz     short loc_18002150A
0x1800214e6  movaps  xmm0, cs:xmmword_18003E8B0
0x1800214ed  mov     rax, [rdi]
0x1800214f0  lea     rdx, [rbp+57h+var_40]
0x1800214f4  mov     rcx, rdi
0x1800214f7  movdqu  [rbp+57h+var_40], xmm0
0x1800214fc  mov     rax, [rax+0B0h]
0x180021503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021508  jmp     short loc_180021589
0x18002150a  lea     rdx, [rbp+57h+pvarg]; struct tagVARIANT *
0x18002150e  call    ?MultipleToVariant@@YAJPEBGPEAUtagVARIANT@@@Z; MultipleToVariant(ushort const *,tagVARIANT *)
0x180021513  mov     ebx, eax
0x180021515  test    eax, eax
0x180021517  js      short loc_18002158B
0x180021519  movaps  xmm0, cs:xmmword_18003E8B0
0x180021520  jmp     short loc_180021558
0x180021522  call    cs:__imp_SysAllocString
0x180021529  nop     dword ptr [rax+rax+00h]
0x18002152e  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180021532  test    rax, rax
0x180021535  jnz     short loc_18002153E
0x180021537  mov     ebx, 8007000Eh
0x18002153c  jmp     short loc_18002158B
0x18002153e  mov     eax, 8
0x180021543  lea     rcx, ?gc_pgmPropsToGuid@@3QBU_GUID@@B; _GUID const near * const gc_pgmPropsToGuid
0x18002154a  mov     word ptr [rbp+57h+pvarg], ax
0x18002154e  mov     rax, rbx
0x180021551  add     rax, rax
0x180021554  movups  xmm0, xmmword ptr [rcx+rax*8]
0x180021558  mov     rax, [rdi]
0x18002155b  lea     r8, [rbp+57h+var_60]
0x18002155f  movups  xmm1, xmmword ptr [rbp+57h+pvarg]
0x180021563  lea     rdx, [rbp+57h+var_40]
0x180021567  mov     rcx, rdi
0x18002156a  movdqu  [rbp+57h+var_40], xmm0
0x18002156f  mov     rax, [rax+0A8h]
0x180021576  movsd   xmm0, qword ptr [rbp+57h+pvarg+10h]
0x18002157b  movaps  [rbp+57h+var_60], xmm1
0x18002157f  movsd   [rbp+57h+var_50], xmm0
0x180021584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021589  mov     ebx, eax
0x18002158b  mov     rcx, [rbp+57h+var_98]
0x18002158f  test    rcx, rcx
0x180021592  jz      short loc_1800215A8
0x180021594  mov     rax, [rcx]
0x180021597  mov     rax, [rax+10h]
0x18002159b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215a0  mov     [rbp+57h+var_98], 0
0x1800215a8  mov     rcx, [rbp+57h+var_88]
0x1800215ac  test    rcx, rcx
0x1800215af  jz      short loc_1800215C5
0x1800215b1  mov     rax, [rcx]
0x1800215b4  mov     rax, [rax+10h]
0x1800215b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800215bd  mov     [rbp+57h+var_88], 0
0x1800215c5  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800215c9  call    cs:__imp_VariantClear
0x1800215d0  nop     dword ptr [rax+rax+00h]
0x1800215d5  mov     eax, cs:dword_18003E048
0x1800215db  cmp     eax, 5
0x1800215de  jbe     short loc_1800215FF
0x1800215e0  lea     rax, [rbp+57h+var_90]
0x1800215e4  mov     [rbp+57h+var_90], ebx
0x1800215e7  lea     rdx, byte_1800369E1
0x1800215ee  mov     [rsp+0D0h+var_B0], rax
0x1800215f3  lea     rcx, dword_18003E048
0x1800215fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800215ff  mov     eax, ebx
0x180021601  mov     rcx, [rbp+57h+var_30]
0x180021605  xor     rcx, rsp; StackCookie
0x180021608  call    __security_check_cookie
0x18002160d  add     rsp, 0B0h
0x180021614  pop     r14
0x180021616  pop     rdi
0x180021617  pop     rsi
0x180021618  pop     rbx
0x180021619  pop     rbp
0x18002161a  retn
```
