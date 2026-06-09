# CreateVector(tagVARIANT *,uchar const *,long)

- ea: `0x1800d82f8`
- end: `0x1800d8391`
- name: `?CreateVector@@YAJPEAUtagVARIANT@@PEBEJ@Z`
- size: `153`
- prototype: `__int64 __fastcall(tagVARIANT *pVar, const unsigned __int8 *pData, ULONG cElems)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008ccb4`

## callees

- `0x1800d82f8`
- `0x180178528`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d8352`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800d8352`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d8343`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800d8343`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d836d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800d836d`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d8326`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800d8326`

## pseudocode

```c
__int64 __fastcall CreateVector(tagVARIANT *pVar, const unsigned __int8 *pData, ULONG cElems)
{
  size_t v3; // rbp
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v7; // rdi
  HRESULT v8; // ebx
  unsigned __int8 *pB; // [rsp+58h] [rbp+20h] BYREF

  v3 = (int)cElems;
  pB = 0;
  Vector = SafeArrayCreateVector(0x11u, 0, cElems);
  v7 = Vector;
  if ( Vector )
  {
    v8 = SafeArrayAccessData(Vector, (void **)&pB);
    if ( v8 >= 0 )
    {
      memcpy_0(pB, pData, v3);
      SafeArrayUnaccessData(v7);
      pVar->llVal = (__int64)v7;
      pVar->vt = 8209;
    }
    else
    {
      SafeArrayDestroy(v7);
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800d82f8  mov     [rsp+arg_0], rbx
0x1800d82fd  mov     [rsp+arg_8], rbp
0x1800d8302  push    rsi
0x1800d8303  push    rdi
0x1800d8304  push    r14
0x1800d8306  sub     rsp, 20h
0x1800d830a  movsxd  rbp, cElems
0x1800d830d  mov     r14, pData
0x1800d8310  mov     rsi, pVar
0x1800d8313  mov     [rsp+38h+pB], 0
0x1800d831c  mov     cElems, ebp; cElements
0x1800d831f  mov     ecx, 11h; vt
0x1800d8324  xor     edx, edx; lLbound
0x1800d8326  call    cs:__imp_SafeArrayCreateVector
0x1800d832c  mov     rdi, rax
0x1800d832f  test    rax, rax
0x1800d8332  jnz     short loc_1800D833B
0x1800d8334  mov     ebx, 8007000Eh
0x1800d8339  jmp     short $Cleanup_9
0x1800d833b  lea     pData, [rsp+38h+pB]; ppvData
0x1800d8340  mov     pVar, rdi; psa
0x1800d8343  call    cs:__imp_SafeArrayAccessData
0x1800d8349  mov     ebx, eax
0x1800d834b  test    eax, eax
0x1800d834d  jns     short loc_1800D835A
0x1800d834f  mov     pVar, rdi; psa
0x1800d8352  call    cs:__imp_SafeArrayDestroy
0x1800d8358  jmp     short $Cleanup_9
0x1800d835a  mov     pVar, [rsp+38h+pB]; void *
0x1800d835f  mov     r8, rbp; Size
0x1800d8362  mov     pData, r14; Src
0x1800d8365  call    memcpy_0
0x1800d836a  mov     pVar, rdi; psa
0x1800d836d  call    cs:__imp_SafeArrayUnaccessData
0x1800d8373  mov     [rsi+8], rdi
0x1800d8377  mov     word ptr [rsi], 2011h
0x1800d837c  mov     rbp, [rsp+38h+arg_8]
0x1800d8381  mov     eax, ebx
0x1800d8383  mov     rbx, [rsp+38h+arg_0]
0x1800d8388  add     rsp, 20h
0x1800d838c  pop     r14
0x1800d838e  pop     rdi
0x1800d838f  pop     rsi
0x1800d8390  retn
```
