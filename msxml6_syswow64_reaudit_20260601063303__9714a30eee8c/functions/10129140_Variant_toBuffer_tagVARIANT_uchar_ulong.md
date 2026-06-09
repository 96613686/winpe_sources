# Variant::toBuffer(tagVARIANT,uchar * *,ulong *)

- ea: `0x10129140`
- end: `0x10129269`
- name: `?toBuffer@Variant@@SGJUtagVARIANT@@PAPAEPAK@Z`
- size: `297`
- prototype: `HRESULT __fastcall(unsigned __int8 **pData, unsigned int *pcb, tagVARIANT varVariant)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x101292bc`

## callees

- `0x1004dfcf`
- `0x10128e74`
- `0x1012909d`
- `0x10129140`
- `0x101712a4`

## import_xrefs

- `OLEAUT32!__imp__SysFreeString@4` at `0x1012923d`
- `OLEAUT32!__imp__SysFreeString@4` at `0x1012923d`
- `OLEAUT32!__imp__SafeArrayGetDim@4` at `0x1012918d`
- `OLEAUT32!__imp__SafeArrayGetDim@4` at `0x1012918d`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x101291d4`
- `OLEAUT32!__imp__SafeArrayGetUBound@12` at `0x101291d4`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x101291bd`
- `OLEAUT32!__imp__SafeArrayGetLBound@12` at `0x101291bd`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x101291a6`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x101291a6`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10129255`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x10129255`

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
0x10129140  mov     edi, edi
0x10129142  push    ebp
0x10129143  mov     ebp, esp
0x10129145  sub     esp, 20h
0x10129148  mov     eax, pData
0x1012914a  mov     [ebp+var_20], pcb
0x1012914d  xor     pData, pData
0x1012914f  mov     [ebp+psz], eax
0x10129152  push    ebx
0x10129153  push    esi
0x10129154  xor     ebx, ebx
0x10129156  mov     [eax], pData
0x10129158  mov     ax, word ptr [ebp+varVariant.___u0]
0x1012915c  inc     ebx
0x1012915d  push    edi
0x1012915e  test    al, 11h
0x10129160  mov     [ebp+pb], pData
0x10129163  mov     esi, pData
0x10129165  mov     [ebp+lUBound], pData
0x10129168  push    0Dh
0x1012916a  mov     [ebp+lLBound], pData
0x1012916d  mov     [ebp+var_18], pData
0x10129170  setnz   cl
0x10129173  pop     pcb
0x10129174  bt      ax, dx
0x10129178  mov     [ebp+var_1C], esi
0x1012917b  mov     [ebp+cb], esi
0x1012917e  setb    al
0x10129181  test    al, cl
0x10129183  jz      loc_10129215
0x10129189  mov     edi, dword ptr [ebp+varVariant.___u0+8]
0x1012918c  push    edi; psa
0x1012918d  call    ds:__imp__SafeArrayGetDim@4; SafeArrayGetDim(x)
0x10129193  cmp     eax, ebx
0x10129195  jz      short loc_101291A1
0x10129197  mov     ebx, 80004005h
0x1012919c  jmp     CleanUp_419
0x101291a1  lea     eax, [ebp+pb]
0x101291a4  push    eax; ppvData
0x101291a5  push    edi; psa
0x101291a6  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x101291ac  mov     ebx, eax
0x101291ae  test    ebx, ebx
0x101291b0  js      CleanUp_419
0x101291b6  lea     eax, [ebp+lLBound]
0x101291b9  push    eax; plLbound
0x101291ba  push    1; nDim
0x101291bc  push    edi; psa
0x101291bd  call    ds:__imp__SafeArrayGetLBound@12; SafeArrayGetLBound(x,x,x)
0x101291c3  mov     ebx, eax
0x101291c5  test    ebx, ebx
0x101291c7  js      CleanUp_419
0x101291cd  lea     eax, [ebp+lUBound]
0x101291d0  push    eax; plUbound
0x101291d1  push    1; nDim
0x101291d3  push    edi; psa
0x101291d4  call    ds:__imp__SafeArrayGetUBound@12; SafeArrayGetUBound(x,x,x)
0x101291da  mov     ebx, eax
0x101291dc  test    ebx, ebx
0x101291de  js      short CleanUp_419
0x101291e0  mov     esi, [ebp+lUBound]
0x101291e3  sub     esi, [ebp+lLBound]
0x101291e6  add     esi, 1
0x101291e9  jz      short loc_10129211
0x101291eb  mov     pData, esi; cch
0x101291ed  call    ??$new_array_ne@E@@YGPAEJ@Z; new_array_ne<uchar>(long)
0x101291f2  mov     pcb, [ebp+psz]
0x101291f5  mov     [pcb], eax
0x101291f7  test    eax, eax
0x101291f9  jnz     short loc_10129204
0x101291fb  xor     esi, esi
0x101291fd  mov     ebx, 8007000Eh
0x10129202  jmp     short CleanUp_419
0x10129204  push    esi; Size
0x10129205  push    [ebp+pb]; Src
0x10129208  push    eax; void *
0x10129209  call    _memcpy
0x1012920e  add     esp, 0Ch
0x10129211  xor     ebx, ebx
0x10129213  jmp     short CleanUp_419
0x10129215  sub     esp, 10h
0x10129218  lea     esi, [ebp+varVariant]
0x1012921b  mov     edi, esp
0x1012921d  movsd
0x1012921e  movsd
0x1012921f  movsd
0x10129220  movsd
0x10129221  call    ?toBSTR@Variant@@SGPAGUtagVARIANT@@@Z; Variant::toBSTR(tagVARIANT)
0x10129226  mov     esi, eax
0x10129228  test    esi, esi
0x1012922a  jz      short loc_10129248
0x1012922c  mov     pcb, [ebp+psz]; psz
0x1012922f  lea     eax, [ebp+cb]
0x10129232  push    eax; pcbUTF8
0x10129233  mov     pData, esi; bstr
0x10129235  call    ?BSTRToUTF8@@YGJPAGPAPAEPAK@Z; BSTRToUTF8(ushort *,uchar * *,ulong *)
0x1012923a  push    esi; bstrString
0x1012923b  mov     ebx, eax
0x1012923d  call    ds:__imp__SysFreeString@4; SysFreeString(x)
0x10129243  mov     esi, [ebp+cb]
0x10129246  jmp     short loc_1012924B
0x10129248  mov     esi, [ebp+var_1C]
0x1012924b  mov     edi, [ebp+var_18]
0x1012924e  cmp     [ebp+pb], 0
0x10129252  jz      short loc_1012925B
0x10129254  push    edi; psa
0x10129255  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1012925b  mov     eax, [ebp+var_20]
0x1012925e  pop     edi
0x1012925f  mov     [eax], esi
0x10129261  mov     eax, ebx
0x10129263  pop     esi
0x10129264  pop     ebx
0x10129265  leave
0x10129266  retn    10h
```
