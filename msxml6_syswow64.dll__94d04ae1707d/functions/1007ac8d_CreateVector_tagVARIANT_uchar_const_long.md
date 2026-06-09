# CreateVector(tagVARIANT *,uchar const *,long)

- ea: `0x1007ac8d`
- end: `0x1007acfc`
- name: `?CreateVector@@YGJPAUtagVARIANT@@PBEJ@Z`
- size: `111`
- prototype: `HRESULT __fastcall(tagVARIANT *pVar, unsigned __int8 *pData, ULONG cElems)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1007b7d9`

## callees

- `0x1007ac8d`
- `0x101711b4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1007acc8`
- `OLEAUT32!__imp__SafeArrayDestroy@4` at `0x1007acc8`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007acbb`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1007acbb`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007ace2`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1007ace2`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1007aca3`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x1007aca3`

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
0x1007ac8d  mov     edi, edi
0x1007ac8f  push    ebp
0x1007ac90  mov     ebp, esp
0x1007ac92  push    pVar
0x1007ac93  push    pVar
0x1007ac94  push    ebx
0x1007ac95  push    esi
0x1007ac96  push    edi
0x1007ac97  push    [ebp+cElems]; cElements
0x1007ac9a  mov     [ebp+Src], pData
0x1007ac9d  mov     ebx, pVar
0x1007ac9f  push    0; lLbound
0x1007aca1  push    11h; vt
0x1007aca3  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x1007aca9  mov     esi, eax
0x1007acab  test    esi, esi
0x1007acad  jnz     short loc_1007ACB6
0x1007acaf  mov     edi, 8007000Eh
0x1007acb4  jmp     short Cleanup_3
0x1007acb6  lea     eax, [ebp+pB]
0x1007acb9  push    eax; ppvData
0x1007acba  push    esi; psa
0x1007acbb  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1007acc1  mov     edi, eax
0x1007acc3  test    edi, edi
0x1007acc5  jns     short loc_1007ACD0
0x1007acc7  push    esi; psa
0x1007acc8  call    ds:__imp__SafeArrayDestroy@4; SafeArrayDestroy(x)
0x1007acce  jmp     short Cleanup_3
0x1007acd0  push    [ebp+cElems]; Size
0x1007acd3  push    [ebp+Src]; Src
0x1007acd6  push    [ebp+pB]; void *
0x1007acd9  call    _memcpy
0x1007acde  add     esp, 0Ch
0x1007ace1  push    esi; psa
0x1007ace2  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1007ace8  mov     eax, 2011h
0x1007aced  mov     [ebx+8], esi
0x1007acf0  mov     [ebx], ax
0x1007acf3  mov     eax, edi
0x1007acf5  pop     edi
0x1007acf6  pop     esi
0x1007acf7  pop     ebx
0x1007acf8  leave
0x1007acf9  retn    4
```
