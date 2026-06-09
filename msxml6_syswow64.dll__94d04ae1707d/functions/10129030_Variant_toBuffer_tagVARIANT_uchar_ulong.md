# Variant::toBuffer(tagVARIANT,uchar * *,ulong *)

- ea: `0x10129030`
- end: `0x10129159`
- name: `?toBuffer@Variant@@SGJUtagVARIANT@@PAPAEPAK@Z`
- size: `297`
- prototype: `HRESULT __fastcall(unsigned __int8 **pData, unsigned int *pcb, tagVARIANT varVariant)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x101291ac`

## callees

- `0x1004e05f`
- `0x10128d64`
- `0x10128f8d`
- `0x10129030`
- `0x101711b4`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x1012912d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012912d`
- `OLEAUT32!__imp__SafeArrayGetDim@4` at `0x1012907d`
- `OLEAUT32!__imp__SafeArrayGetDim@4` at `0x1012907d`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x101290c4`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x101290c4`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x101290ad`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x101290ad`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10129096`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x10129096`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10129145`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10129145`

## pseudocode

```c
HRESULT __fastcall Variant::toBuffer(unsigned __int8 **pData, unsigned int *pcb, tagVARIANT varVariant)
{
  HRESULT LBound; // ebx
  size_t v4; // esi
  SAFEARRAY *parray; // edi
  unsigned __int8 *v6; // eax
  wchar_t *v7; // esi
  unsigned int cb; // [esp+18h] [ebp-14h] BYREF
  unsigned __int8 **psz; // [esp+1Ch] [ebp-10h]
  int lLBound; // [esp+20h] [ebp-Ch] BYREF
  int lUBound; // [esp+24h] [ebp-8h] BYREF
  unsigned __int8 *pb; // [esp+28h] [ebp-4h] BYREF

  psz = pData;
  *pData = 0;
  LBound = 1;
  pb = 0;
  v4 = 0;
  lUBound = 0;
  lLBound = 0;
  cb = 0;
  if ( (varVariant.gap0[0] & 0x11) == 0 || (varVariant.vt & 0x2000) == 0 )
  {
    v7 = Variant::toBSTR(varVariant);
    if ( v7 )
    {
      LBound = BSTRToUTF8(v7, psz, &cb);
      SysFreeString(v7);
      v4 = cb;
    }
    else
    {
      v4 = 0;
    }
    parray = 0;
    goto CleanUp_419;
  }
  parray = varVariant.parray;
  if ( SafeArrayGetDim(varVariant.parray) != 1 )
  {
    LBound = -2147467259;
    goto CleanUp_419;
  }
  LBound = SafeArrayAccessData(varVariant.parray, (void **)&pb);
  if ( LBound >= 0 )
  {
    LBound = SafeArrayGetLBound(varVariant.parray, 1u, &lLBound);
    if ( LBound >= 0 )
    {
      LBound = SafeArrayGetUBound(varVariant.parray, 1u, &lUBound);
      if ( LBound >= 0 )
      {
        v4 = lUBound - lLBound + 1;
        if ( lUBound - lLBound != -1 )
        {
          v6 = (unsigned __int8 *)new_array_ne<unsigned char>(lUBound - lLBound + 1);
          *psz = v6;
          if ( !v6 )
          {
            v4 = 0;
            LBound = -2147024882;
            goto CleanUp_419;
          }
          memcpy(v6, pb, v4);
        }
        LBound = 0;
      }
    }
  }
CleanUp_419:
  if ( pb )
    SafeArrayUnaccessData(parray);
  *pcb = v4;
  return LBound;
}

```

## disassembly

```asm
0x10129030  mov     edi, edi
0x10129032  push    ebp
0x10129033  mov     ebp, esp
0x10129035  sub     esp, 20h
0x10129038  mov     eax, pData
0x1012903a  mov     [ebp+var_20], pcb
0x1012903d  xor     pData, pData
0x1012903f  mov     [ebp+psz], eax
0x10129042  push    ebx
0x10129043  push    esi
0x10129044  xor     ebx, ebx
0x10129046  mov     [eax], pData
0x10129048  mov     ax, word ptr [ebp+varVariant.___u0]
0x1012904c  inc     ebx
0x1012904d  push    edi
0x1012904e  test    al, 11h
0x10129050  mov     [ebp+pb], pData
0x10129053  mov     esi, pData
0x10129055  mov     [ebp+lUBound], pData
0x10129058  push    0Dh
0x1012905a  mov     [ebp+lLBound], pData
0x1012905d  mov     [ebp+var_18], pData
0x10129060  setnz   cl
0x10129063  pop     pcb
0x10129064  bt      ax, dx
0x10129068  mov     [ebp+var_1C], esi
0x1012906b  mov     [ebp+cb], esi
0x1012906e  setb    al
0x10129071  test    al, cl
0x10129073  jz      loc_10129105
0x10129079  mov     edi, dword ptr [ebp+varVariant.___u0+8]
0x1012907c  push    edi; psa
0x1012907d  call    ds:__imp__SafeArrayGetDim@4; SafeArrayGetDim(x)
0x10129083  cmp     eax, ebx
0x10129085  jz      short loc_10129091
0x10129087  mov     ebx, 80004005h
0x1012908c  jmp     CleanUp_419
0x10129091  lea     eax, [ebp+pb]
0x10129094  push    eax; ppvData
0x10129095  push    edi; psa
0x10129096  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1012909c  mov     ebx, eax
0x1012909e  test    ebx, ebx
0x101290a0  js      CleanUp_419
0x101290a6  lea     eax, [ebp+lLBound]
0x101290a9  push    eax; plLbound
0x101290aa  push    1; nDim
0x101290ac  push    edi; psa
0x101290ad  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x101290b3  mov     ebx, eax
0x101290b5  test    ebx, ebx
0x101290b7  js      CleanUp_419
0x101290bd  lea     eax, [ebp+lUBound]
0x101290c0  push    eax; plUbound
0x101290c1  push    1; nDim
0x101290c3  push    edi; psa
0x101290c4  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x101290ca  mov     ebx, eax
0x101290cc  test    ebx, ebx
0x101290ce  js      short CleanUp_419
0x101290d0  mov     esi, [ebp+lUBound]
0x101290d3  sub     esi, [ebp+lLBound]
0x101290d6  add     esi, 1
0x101290d9  jz      short loc_10129101
0x101290db  mov     pData, esi; cch
0x101290dd  call    ??$new_array_ne@E@@YGPAEJ@Z; new_array_ne<uchar>(long)
0x101290e2  mov     pcb, [ebp+psz]
0x101290e5  mov     [pcb], eax
0x101290e7  test    eax, eax
0x101290e9  jnz     short loc_101290F4
0x101290eb  xor     esi, esi
0x101290ed  mov     ebx, 8007000Eh
0x101290f2  jmp     short CleanUp_419
0x101290f4  push    esi; Size
0x101290f5  push    [ebp+pb]; Src
0x101290f8  push    eax; void *
0x101290f9  call    _memcpy
0x101290fe  add     esp, 0Ch
0x10129101  xor     ebx, ebx
0x10129103  jmp     short CleanUp_419
0x10129105  sub     esp, 10h
0x10129108  lea     esi, [ebp+varVariant]
0x1012910b  mov     edi, esp
0x1012910d  movsd
0x1012910e  movsd
0x1012910f  movsd
0x10129110  movsd
0x10129111  call    ?toBSTR@Variant@@SGPAGUtagVARIANT@@@Z; Variant::toBSTR(tagVARIANT)
0x10129116  mov     esi, eax
0x10129118  test    esi, esi
0x1012911a  jz      short loc_10129138
0x1012911c  mov     pcb, [ebp+psz]; psz
0x1012911f  lea     eax, [ebp+cb]
0x10129122  push    eax; pcbUTF8
0x10129123  mov     pData, esi; bstr
0x10129125  call    ?BSTRToUTF8@@YGJPAGPAPAEPAK@Z; BSTRToUTF8(ushort *,uchar * *,ulong *)
0x1012912a  push    esi; bstrString
0x1012912b  mov     ebx, eax
0x1012912d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10129133  mov     esi, [ebp+cb]
0x10129136  jmp     short loc_1012913B
0x10129138  mov     esi, [ebp+var_1C]
0x1012913b  mov     edi, [ebp+var_18]
0x1012913e  cmp     [ebp+pb], 0
0x10129142  jz      short loc_1012914B
0x10129144  push    edi; psa
0x10129145  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1012914b  mov     eax, [ebp+var_20]
0x1012914e  pop     edi
0x1012914f  mov     [eax], esi
0x10129151  mov     eax, ebx
0x10129153  pop     esi
0x10129154  pop     ebx
0x10129155  leave
0x10129156  retn    10h
```
