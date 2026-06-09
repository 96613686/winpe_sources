# CCalcAlbumID::CalcValue(tagPROPVARIANT *)

- ea: `0x180062020`
- end: `0x18006215f`
- name: `?CalcValue@CCalcAlbumID@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `319`
- prototype: `int(CCalcAlbumID *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c890`
- `0x18000ca30`
- `0x180062020`
- `0x180062168`
- `0x18006ba10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006213a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062143`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800620f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006213a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062143`

## pseudocode

```c
__int64 __fastcall CCalcAlbumID::CalcValue(const PROPVARIANT *this, struct tagPROPVARIANT *a2)
{
  HRESULT inited; // edi
  HRESULT v5; // eax
  PWSTR v6; // rbx
  WCHAR v7; // cx
  PWSTR v8; // rsi
  PWSTR *p_ppszOut; // rax
  PWSTR v11; // [rsp+20h] [rbp-40h] BYREF
  PWSTR ppszOut; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pv[3]; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v14[3]; // [rsp+48h] [rbp-18h] BYREF

  ppszOut = 0;
  inited = PropVariantToStringAlloc(this + 9, &ppszOut);
  if ( inited >= 0 )
  {
    v11 = 0;
    v5 = PropVariantToStringAlloc(this + 12, &v11);
    v6 = ppszOut;
    inited = v5;
    if ( v5 < 0 )
    {
LABEL_17:
      CoTaskMemFree(v6);
      return (unsigned int)inited;
    }
    v7 = *ppszOut;
    if ( *ppszOut )
    {
      v8 = v11;
      if ( *v11 )
      {
        memset(v14, 0, sizeof(v14));
        inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
                   v14,
                   g_hModMUIResources,
                   197);
        if ( inited >= 0 )
        {
          memset(pv, 0, sizeof(pv));
          inited = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeMessage(
                     pv,
                     v14[0],
                     v8,
                     v6);
          if ( inited >= 0 )
            inited = InitPropVariantFromString((const unsigned __int16 *)pv[0], a2);
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
        }
        if ( v14[0] )
          CoTaskMemFree(v14[0]);
LABEL_16:
        CoTaskMemFree(v8);
        goto LABEL_17;
      }
    }
    else
    {
      v6 = v11;
    }
    a2->hVal.QuadPart = (LONGLONG)v6;
    p_ppszOut = &v11;
    a2->vt = 31;
    if ( v7 )
      p_ppszOut = &ppszOut;
    *p_ppszOut = 0;
    v6 = ppszOut;
    v8 = v11;
    goto LABEL_16;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180062020  mov     [rsp-28h+arg_10], rbx
0x180062025  push    rbp
0x180062026  push    rsi
0x180062027  push    rdi
0x180062028  push    r12
0x18006202a  push    r13
0x18006202c  mov     rbp, rsp
0x18006202f  sub     rsp, 60h
0x180062033  mov     r12, rdx
0x180062036  mov     rbx, rcx
0x180062039  xor     r13d, r13d
0x18006203c  lea     rdx, [rbp+ppszOut]; ppszOut
0x180062040  add     rcx, 48h ; 'H'; propvar
0x180062044  mov     [rbp+ppszOut], r13
0x180062048  call    PropVariantToStringAlloc
0x18006204d  mov     edi, eax
0x18006204f  test    eax, eax
0x180062051  js      loc_180062149
0x180062057  lea     rcx, [rbx+60h]; propvar
0x18006205b  mov     [rbp+var_40], r13
0x18006205f  lea     rdx, [rbp+var_40]; ppszOut
0x180062063  call    PropVariantToStringAlloc
0x180062068  mov     rbx, [rbp+ppszOut]
0x18006206c  mov     edi, eax
0x18006206e  test    eax, eax
0x180062070  js      loc_180062140
0x180062076  movzx   ecx, word ptr [rbx]
0x180062079  test    cx, cx
0x18006207c  jz      loc_18006210D
0x180062082  mov     rsi, [rbp+var_40]
0x180062086  cmp     [rsi], r13w
0x18006208a  jz      loc_180062111
0x180062090  mov     rdx, cs:?g_hModMUIResources@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModMUIResources
0x180062097  lea     rcx, [rbp+var_18]
0x18006209b  mov     r8d, 0C5h
0x1800620a1  mov     [rbp+var_18], r13
0x1800620a5  mov     [rbp+var_10], r13
0x1800620a9  mov     [rbp+var_8], r13
0x1800620ad  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHINSTANCE__@@IG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(HINSTANCE__ *,uint,ushort)
0x1800620b2  mov     edi, eax
0x1800620b4  test    eax, eax
0x1800620b6  js      short loc_1800620FB
0x1800620b8  mov     rdx, [rbp+var_18]
0x1800620bc  lea     rcx, [rbp+pv]
0x1800620c0  mov     r9, rbx
0x1800620c3  mov     [rbp+pv], r13
0x1800620c7  mov     r8, rsi
0x1800620ca  mov     [rbp+var_28], r13
0x1800620ce  mov     [rbp+var_20], r13
0x1800620d2  call    ?InitializeMessage@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeMessage(ushort const *,...)
0x1800620d7  mov     edi, eax
0x1800620d9  test    eax, eax
0x1800620db  js      short loc_1800620EB
0x1800620dd  mov     rcx, [rbp+pv]; Src
0x1800620e1  mov     rdx, r12; struct tagPROPVARIANT *
0x1800620e4  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x1800620e9  mov     edi, eax
0x1800620eb  cmp     [rbp+pv], r13
0x1800620ef  jz      short loc_1800620FB
0x1800620f1  mov     rcx, [rbp+pv]; pv
0x1800620f5  call    cs:__imp_CoTaskMemFree
0x1800620fb  cmp     [rbp+var_18], r13
0x1800620ff  jz      short loc_180062137
0x180062101  mov     rcx, [rbp+var_18]; pv
0x180062105  call    cs:__imp_CoTaskMemFree
0x18006210b  jmp     short loc_180062137
0x18006210d  mov     rbx, [rbp+var_40]
0x180062111  test    cx, cx
0x180062114  mov     [r12+8], rbx
0x180062119  lea     rax, [rbp+var_40]
0x18006211d  mov     word ptr [r12], 1Fh
0x180062124  lea     rdx, [rbp+ppszOut]
0x180062128  cmovnz  rax, rdx
0x18006212c  mov     [rax], r13
0x18006212f  mov     rbx, [rbp+ppszOut]
0x180062133  mov     rsi, [rbp+var_40]
0x180062137  mov     rcx, rsi; pv
0x18006213a  call    cs:__imp_CoTaskMemFree
0x180062140  mov     rcx, rbx; pv
0x180062143  call    cs:__imp_CoTaskMemFree
0x180062149  mov     rbx, [rsp+60h+arg_10]
0x180062151  mov     eax, edi
0x180062153  add     rsp, 60h
0x180062157  pop     r13
0x180062159  pop     r12
0x18006215b  pop     rdi
0x18006215c  pop     rsi
0x18006215d  pop     rbp
0x18006215e  retn
```
