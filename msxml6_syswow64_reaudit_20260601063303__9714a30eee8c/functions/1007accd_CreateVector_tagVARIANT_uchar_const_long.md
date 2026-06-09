# CreateVector(tagVARIANT *,uchar const *,long)

- ea: `0x1007accd`
- end: `0x1007ad3c`
- name: `?CreateVector@@YGJPAUtagVARIANT@@PBEJ@Z`
- size: `111`
- prototype: `HRESULT __fastcall(tagVARIANT *pVar, unsigned __int8 *pData, ULONG cElems)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1007b819`

## callees

- `0x1007accd`
- `0x101712a4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1007ad08`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1007ad08`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007acfb`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007acfb`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007ad22`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007ad22`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1007ace3`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1007ace3`

## pseudocode

```c
HRESULT __fastcall CreateVector(tagVARIANT *pVar, unsigned __int8 *pData, ULONG cElems)
{
  SAFEARRAY *Vector; // esi
  HRESULT v5; // edi
  unsigned __int8 *pB; // [esp+Ch] [ebp-8h] BYREF
  void *Src; // [esp+10h] [ebp-4h]

  Src = pData;
  Vector = SafeArrayCreateVector(0x11u, 0, cElems);
  if ( !Vector )
    return -2147024882;
  v5 = SafeArrayAccessData(Vector, (void **)&pB);
  if ( v5 >= 0 )
  {
    memcpy(pB, Src, cElems);
    SafeArrayUnaccessData(Vector);
    pVar->decVal.Lo32 = (unsigned int)Vector;
    pVar->vt = 8209;
  }
  else
  {
    SafeArrayDestroy(Vector);
  }
  return v5;
}

```

## disassembly

```asm
0x1007accd  mov     edi, edi
0x1007accf  push    ebp
0x1007acd0  mov     ebp, esp
0x1007acd2  push    pVar
0x1007acd3  push    pVar
0x1007acd4  push    ebx
0x1007acd5  push    esi
0x1007acd6  push    edi
0x1007acd7  push    [ebp+cElems]; cElements
0x1007acda  mov     [ebp+Src], pData
0x1007acdd  mov     ebx, pVar
0x1007acdf  push    0; lLbound
0x1007ace1  push    11h; vt
0x1007ace3  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x1007ace9  mov     esi, eax
0x1007aceb  test    esi, esi
0x1007aced  jnz     short loc_1007ACF6
0x1007acef  mov     edi, 8007000Eh
0x1007acf4  jmp     short Cleanup_3
0x1007acf6  lea     eax, [ebp+pB]
0x1007acf9  push    eax; ppvData
0x1007acfa  push    esi; psa
0x1007acfb  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1007ad01  mov     edi, eax
0x1007ad03  test    edi, edi
0x1007ad05  jns     short loc_1007AD10
0x1007ad07  push    esi; psa
0x1007ad08  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x1007ad0e  jmp     short Cleanup_3
0x1007ad10  push    [ebp+cElems]; Size
0x1007ad13  push    [ebp+Src]; Src
0x1007ad16  push    [ebp+pB]; void *
0x1007ad19  call    _memcpy
0x1007ad1e  add     esp, 0Ch
0x1007ad21  push    esi; psa
0x1007ad22  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1007ad28  mov     eax, 2011h
0x1007ad2d  mov     [ebx+8], esi
0x1007ad30  mov     [ebx], ax
0x1007ad33  mov     eax, edi
0x1007ad35  pop     edi
0x1007ad36  pop     esi
0x1007ad37  pop     ebx
0x1007ad38  leave
0x1007ad39  retn    4
```
