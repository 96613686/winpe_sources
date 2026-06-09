# CDirFltr::GetValue(tagPROPVARIANT * *)

- ea: `0x180009310`
- end: `0x18000963c`
- name: `?GetValue@CDirFltr@@UEAAJPEAPEAUtagPROPVARIANT@@@Z`
- size: `812`
- prototype: `__int64 __fastcall(CDirFltr *this, LPVOID *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009310`
- `0x18000a210`
- `0x18001e194`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000940b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800093f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009402`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000940b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800094ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009522`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009522`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800093b5`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800093b5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800094cb`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800094cb`

## string_xrefs

- `0x180009609`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
__int64 __fastcall CDirFltr::GetValue(CDirFltr *this, LPVOID *a2)
{
  struct tagPROPVARIANT *v4; // rax
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  HRESULT v8; // esi
  void *v10; // rcx
  bool v11; // zf
  __int64 v12; // rcx
  __int64 v13; // rax
  int v14; // eax
  const WCHAR *v15; // rcx
  void *v16; // rcx
  struct tagPROPVARIANT *v17; // rax
  BYTE *v18; // rax
  _QWORD *v19; // rax
  LPVOID v20; // rdx
  unsigned int v21; // [rsp+20h] [rbp-30h]
  PROPVARIANT pvarSrc[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPVOID pv; // [rsp+70h] [rbp+20h] BYREF

  if ( !*((_DWORD *)this + 170) )
  {
    pv = 0;
    if ( *((_DWORD *)this + 123) )
    {
      v12 = *((unsigned int *)this + 66);
      if ( (unsigned int)v12 > *((_DWORD *)this + 30) - 1 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x13B,
          (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
          (const char *)0xCE,
          v21);
      v13 = *((_QWORD *)this + 14);
      *((_DWORD *)this + 31) = v12;
      *(_WORD *)(v13 + 2 * v12) = 0;
      v14 = *((_DWORD *)this + 31);
      if ( !v14 || *(_WORD *)(*((_QWORD *)this + 14) + 2LL * (unsigned int)(v14 - 1)) != 92 )
        CLMString::Append((CDirFltr *)((char *)this + 104), L"\\", 0xFFFFFFFF);
      (*(void (__fastcall **)(char *, _QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 13) + 32LL))(
        (char *)this + 104,
        *((_QWORD *)this + 64),
        *((unsigned int *)this + 31),
        *((unsigned int *)this + 131));
      v15 = (const WCHAR *)*((_QWORD *)this + 14);
      pvarSrc[0] = &pv;
      *((_DWORD *)this + 123) = 0;
      pvarSrc[1] = 0;
      LOBYTE(v23) = 1;
      v8 = SHStrDupW(v15, (LPWSTR *)&pvarSrc[1]);
      if ( (_BYTE)v23 )
      {
        v16 = *(void **)pvarSrc[0];
        *(_QWORD *)pvarSrc[0] = pvarSrc[1];
        if ( v16 )
          CoTaskMemFree(v16);
      }
      if ( v8 >= 0 )
      {
        v17 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
        *a2 = v17;
        if ( v17 )
        {
          *(_OWORD *)&v17->vt = 0;
          v17->bstrblobVal.pData = 0;
          v18 = (BYTE *)CoTaskMemAlloc(0x30u);
          if ( v18 )
          {
            *(_WORD *)*a2 = 4108;
            *((_DWORD *)*a2 + 2) = 2;
            *((_QWORD *)*a2 + 2) = v18;
            **((_WORD **)*a2 + 2) = 31;
            v19 = *a2;
            v20 = pv;
            pv = 0;
            *(_QWORD *)(v19[2] + 8LL) = v20;
            *(_WORD *)(*((_QWORD *)*a2 + 2) + 24LL) = 64;
            *(_QWORD *)(*((_QWORD *)*a2 + 2) + 32LL) = *((_QWORD *)this + 83);
LABEL_15:
            v10 = pv;
            pv = 0;
            if ( v10 )
              CoTaskMemFree(v10);
            return (unsigned int)v8;
          }
        }
        v8 = -2147024882;
      }
    }
    else
    {
      v8 = -2147215611;
    }
    CoTaskMemFree(*(LPVOID *)(*((_QWORD *)*a2 + 2) + 8LL));
    CoTaskMemFree(*((LPVOID *)*a2 + 2));
    CoTaskMemFree(*a2);
    *a2 = 0;
    goto LABEL_15;
  }
  if ( a2 )
  {
    v4 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
    *a2 = v4;
    if ( v4 )
    {
      *(_OWORD *)&v4->vt = 0;
      v4->bstrblobVal.pData = 0;
      v5 = *((_DWORD *)this + 19);
      v23 = 0;
      *(_OWORD *)pvarSrc = 0;
      if ( v5 == 4 )
      {
        v11 = (*((_DWORD *)this + 16) & 0x4000) == 0;
        LOWORD(pvarSrc[0]) = 11;
        if ( v11 )
          LOWORD(pvarSrc[1]) = 0;
        else
          LOWORD(pvarSrc[1]) = -1;
      }
      else if ( v5 )
      {
        v6 = v5 - 1;
        if ( v6 )
        {
          v7 = v6 - 1;
          if ( v7 )
          {
            if ( v7 != 1 )
              return (unsigned int)-2147418113;
            LOWORD(pvarSrc[0]) = 64;
            pvarSrc[1] = *((PROPVARIANT *)this + 12);
          }
          else
          {
            LOWORD(pvarSrc[0]) = 64;
            pvarSrc[1] = *((PROPVARIANT *)this + 11);
          }
        }
        else
        {
          LOWORD(pvarSrc[0]) = 64;
          pvarSrc[1] = *((PROPVARIANT *)this + 10);
        }
      }
      else
      {
        LOWORD(pvarSrc[0]) = 19;
        LODWORD(pvarSrc[1]) = *((_DWORD *)this + 16);
      }
      return (unsigned int)PropVariantCopy((PROPVARIANT *)*a2, pvarSrc);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
}

```

## disassembly

```asm
0x180009310  mov     [rsp-18h+arg_8], rbx
0x180009315  mov     [rsp-18h+arg_10], rsi
0x18000931a  push    rbp
0x18000931b  push    rdi
0x18000931c  push    r14
0x18000931e  mov     rbp, rsp
0x180009321  sub     rsp, 50h
0x180009325  cmp     dword ptr [rcx+2A8h], 0
0x18000932c  mov     rdi, rdx
0x18000932f  mov     rbx, rcx
0x180009332  jz      loc_1800093D5
0x180009338  test    rdx, rdx
0x18000933b  jz      loc_1800095D3
0x180009341  mov     ecx, 18h; cb
0x180009346  call    cs:__imp_CoTaskMemAlloc
0x18000934c  mov     [rdi], rax
0x18000934f  test    rax, rax
0x180009352  jz      loc_1800095DD
0x180009358  xor     ecx, ecx
0x18000935a  xorps   xmm0, xmm0
0x18000935d  movups  xmmword ptr [rax], xmm0
0x180009360  mov     [rax+10h], rcx
0x180009364  xor     eax, eax
0x180009366  mov     ecx, [rbx+4Ch]
0x180009369  mov     [rbp+var_10], rax
0x18000936d  movups  xmmword ptr [rbp+pvarSrc], xmm0
0x180009371  cmp     ecx, 4
0x180009374  jz      loc_180009429
0x18000937a  test    ecx, ecx
0x18000937c  jz      loc_1800095F1
0x180009382  sub     ecx, 1
0x180009385  jz      loc_1800095B3
0x18000938b  sub     ecx, 1
0x18000938e  jz      loc_18000959D
0x180009394  cmp     ecx, 1
0x180009397  jnz     loc_1800095E7
0x18000939d  mov     eax, 40h ; '@'
0x1800093a2  mov     word ptr [rbp+pvarSrc], ax
0x1800093a6  mov     rax, [rbx+60h]
0x1800093aa  mov     [rbp+pvarSrc+8], rax
0x1800093ae  mov     rcx, [rdi]; pvarDest
0x1800093b1  lea     rdx, [rbp+pvarSrc]; pvarSrc
0x1800093b5  call    cs:__imp_PropVariantCopy
0x1800093bb  mov     esi, eax
0x1800093bd  mov     rbx, [rsp+50h+arg_8]
0x1800093c2  mov     eax, esi
0x1800093c4  mov     rsi, [rsp+50h+arg_10]
0x1800093cc  add     rsp, 50h
0x1800093d0  pop     r14
0x1800093d2  pop     rdi
0x1800093d3  pop     rbp
0x1800093d4  retn
0x1800093d5  xor     r14d, r14d
0x1800093d8  mov     [rbp+pv], r14
0x1800093dc  cmp     [rcx+1ECh], r14d
0x1800093e3  jnz     short loc_18000944D
0x1800093e5  mov     esi, 80041705h
0x1800093ea  mov     rax, [rdi]
0x1800093ed  mov     rcx, [rax+10h]
0x1800093f1  mov     rcx, [rcx+8]; pv
0x1800093f5  call    cs:__imp_CoTaskMemFree
0x1800093fb  mov     rcx, [rdi]
0x1800093fe  mov     rcx, [rcx+10h]; pv
0x180009402  call    cs:__imp_CoTaskMemFree
0x180009408  mov     rcx, [rdi]; pv
0x18000940b  call    cs:__imp_CoTaskMemFree
0x180009411  mov     [rdi], r14
0x180009414  mov     rcx, [rbp+pv]; pv
0x180009418  mov     [rbp+pv], r14
0x18000941c  test    rcx, rcx
0x18000941f  jz      short loc_1800093BD
0x180009421  call    cs:__imp_CoTaskMemFree
0x180009427  jmp     short loc_1800093BD
0x180009429  test    dword ptr [rbx+40h], 4000h
0x180009430  mov     eax, 0Bh
0x180009435  mov     word ptr [rbp+pvarSrc], ax
0x180009439  jz      loc_180009590
0x18000943f  mov     eax, 0FFFFFFFFh
0x180009444  mov     word ptr [rbp+pvarSrc+8], ax
0x180009448  jmp     loc_1800093AE
0x18000944d  mov     eax, [rbx+78h]
0x180009450  mov     ecx, [rcx+108h]
0x180009456  dec     eax
0x180009458  cmp     ecx, eax
0x18000945a  ja      loc_180009605
0x180009460  mov     rax, [rbx+70h]
0x180009464  mov     [rbx+7Ch], ecx
0x180009467  mov     [rax+rcx*2], r14w
0x18000946c  mov     eax, [rbx+7Ch]
0x18000946f  test    eax, eax
0x180009471  jz      loc_180009621
0x180009477  lea     ecx, [rax-1]
0x18000947a  mov     rax, [rbx+70h]
0x18000947e  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180009483  jnz     loc_180009621
0x180009489  mov     rax, [rbx+68h]
0x18000948d  lea     rcx, [rbx+68h]
0x180009491  mov     r9d, [rbx+20Ch]
0x180009498  mov     r8d, [rbx+7Ch]
0x18000949c  mov     rdx, [rbx+200h]
0x1800094a3  mov     rax, [rax+20h]
0x1800094a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ac  mov     rcx, [rbx+70h]; psz
0x1800094b0  lea     rax, [rbp+pv]
0x1800094b4  lea     rdx, [rbp+pvarSrc+8]; ppwsz
0x1800094b8  mov     [rbp+pvarSrc], rax
0x1800094bc  mov     [rbx+1ECh], r14d
0x1800094c3  mov     [rbp+pvarSrc+8], r14
0x1800094c7  mov     byte ptr [rbp+var_10], 1
0x1800094cb  call    cs:__imp_SHStrDupW
0x1800094d1  mov     esi, eax
0x1800094d3  cmp     byte ptr [rbp+var_10], r14b
0x1800094d7  jz      short loc_1800094F2
0x1800094d9  mov     r8, [rbp+pvarSrc]
0x1800094dd  mov     rdx, [rbp+pvarSrc+8]
0x1800094e1  mov     rcx, [r8]; pv
0x1800094e4  mov     [r8], rdx
0x1800094e7  test    rcx, rcx
0x1800094ea  jz      short loc_1800094F2
0x1800094ec  call    cs:__imp_CoTaskMemFree
0x1800094f2  test    esi, esi
0x1800094f4  js      loc_1800093EA
0x1800094fa  mov     ecx, 18h; cb
0x1800094ff  call    cs:__imp_CoTaskMemAlloc
0x180009505  mov     [rdi], rax
0x180009508  test    rax, rax
0x18000950b  jz      loc_1800095C9
0x180009511  xor     ecx, ecx
0x180009513  xorps   xmm0, xmm0
0x180009516  movups  xmmword ptr [rax], xmm0
0x180009519  mov     [rax+10h], rcx
0x18000951d  mov     ecx, 30h ; '0'; cb
0x180009522  call    cs:__imp_CoTaskMemAlloc
0x180009528  mov     rcx, rax
0x18000952b  test    rax, rax
0x18000952e  jz      loc_1800095C9
0x180009534  mov     rax, [rdi]
0x180009537  mov     word ptr [rax], 100Ch
0x18000953c  mov     rax, [rdi]
0x18000953f  mov     dword ptr [rax+8], 2
0x180009546  mov     rax, [rdi]
0x180009549  mov     [rax+10h], rcx
0x18000954d  mov     rax, [rdi]
0x180009550  mov     rcx, [rax+10h]
0x180009554  mov     word ptr [rcx], 1Fh
0x180009559  mov     rax, [rdi]
0x18000955c  mov     rdx, [rbp+pv]
0x180009560  mov     [rbp+pv], r14
0x180009564  mov     rcx, [rax+10h]
0x180009568  mov     [rcx+8], rdx
0x18000956c  mov     rax, [rdi]
0x18000956f  mov     rcx, [rax+10h]
0x180009573  mov     word ptr [rcx+18h], 40h ; '@'
0x180009579  mov     rax, [rdi]
0x18000957c  mov     rcx, [rax+10h]
0x180009580  mov     rax, [rbx+298h]
0x180009587  mov     [rcx+20h], rax
0x18000958b  jmp     loc_180009414
0x180009590  xor     r14d, r14d
0x180009593  mov     word ptr [rbp+pvarSrc+8], r14w
0x180009598  jmp     loc_1800093AE
0x18000959d  mov     eax, 40h ; '@'
0x1800095a2  mov     word ptr [rbp+pvarSrc], ax
0x1800095a6  mov     rax, [rbx+58h]
0x1800095aa  mov     [rbp+pvarSrc+8], rax
0x1800095ae  jmp     loc_1800093AE
0x1800095b3  mov     eax, 40h ; '@'
0x1800095b8  mov     word ptr [rbp+pvarSrc], ax
0x1800095bc  mov     rax, [rbx+50h]
0x1800095c0  mov     [rbp+pvarSrc+8], rax
0x1800095c4  jmp     loc_1800093AE
0x1800095c9  mov     esi, 8007000Eh
0x1800095ce  jmp     loc_1800093EA
0x1800095d3  mov     esi, 80004003h
0x1800095d8  jmp     loc_1800093BD
0x1800095dd  mov     esi, 8007000Eh
0x1800095e2  jmp     loc_1800093BD
0x1800095e7  mov     esi, 8000FFFFh
0x1800095ec  jmp     loc_1800093BD
0x1800095f1  mov     eax, 13h
0x1800095f6  mov     word ptr [rbp+pvarSrc], ax
0x1800095fa  mov     eax, [rbx+40h]
0x1800095fd  mov     dword ptr [rbp+pvarSrc+8], eax
0x180009600  jmp     loc_1800093AE
0x180009605  mov     rcx, [rbp+18h]; this
0x180009609  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180009610  mov     r9d, 0CEh; char *
0x180009616  mov     edx, 13Bh; void *
0x18000961b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180009621  mov     r8d, 0FFFFFFFFh; unsigned int
0x180009627  lea     rdx, asc_18002B500; "\\"
0x18000962e  lea     rcx, [rbx+68h]; this
0x180009632  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x180009637  jmp     loc_180009489
```
