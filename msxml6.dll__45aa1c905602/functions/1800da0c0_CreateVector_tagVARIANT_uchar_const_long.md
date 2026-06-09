# CreateVector(tagVARIANT *,uchar const *,long)

- ea: `0x1800da0c0`
- end: `0x1800da172`
- name: `?CreateVector@@YAJPEAUtagVARIANT@@PEBEJ@Z`
- size: `178`
- prototype: `HRESULT __fastcall(tagVARIANT *pVar, const unsigned __int8 *pData, int cElems)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18008cf9c`

## callees

- `0x1800da0c0`
- `0x18017c1d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800da126`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800da126`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800da111`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800da111`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800da147`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800da147`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800da0ee`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800da0ee`

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
0x1800da0c0  mov     [rsp+arg_0], rbx
0x1800da0c5  mov     [rsp+arg_8], rbp
0x1800da0ca  push    rsi
0x1800da0cb  push    rdi
0x1800da0cc  push    r14
0x1800da0ce  sub     rsp, 20h
0x1800da0d2  movsxd  rbp, cElems
0x1800da0d5  mov     r14, pData
0x1800da0d8  mov     rsi, pVar
0x1800da0db  mov     [rsp+38h+pB], 0
0x1800da0e4  mov     cElems, ebp; cElements
0x1800da0e7  mov     ecx, 11h; vt
0x1800da0ec  xor     edx, edx; lLbound
0x1800da0ee  call    cs:__imp_SafeArrayCreateVector
0x1800da0f5  nop     dword ptr [rax+rax+00h]
0x1800da0fa  mov     rdi, rax
0x1800da0fd  test    rax, rax
0x1800da100  jnz     short loc_1800DA109
0x1800da102  mov     ebx, 8007000Eh
0x1800da107  jmp     short $Cleanup_9
0x1800da109  lea     pData, [rsp+38h+pB]; ppvData
0x1800da10e  mov     pVar, rdi; psa
0x1800da111  call    cs:__imp_SafeArrayAccessData
0x1800da118  nop     dword ptr [rax+rax+00h]
0x1800da11d  mov     ebx, eax
0x1800da11f  test    eax, eax
0x1800da121  jns     short loc_1800DA134
0x1800da123  mov     pVar, rdi; psa
0x1800da126  call    cs:__imp_SafeArrayDestroy
0x1800da12d  nop     dword ptr [rax+rax+00h]
0x1800da132  jmp     short $Cleanup_9
0x1800da134  mov     pVar, [rsp+38h+pB]; void *
0x1800da139  mov     r8, rbp; Size
0x1800da13c  mov     pData, r14; Src
0x1800da13f  call    memcpy_0
0x1800da144  mov     pVar, rdi; psa
0x1800da147  call    cs:__imp_SafeArrayUnaccessData
0x1800da14e  nop     dword ptr [rax+rax+00h]
0x1800da153  mov     [rsi+8], rdi
0x1800da157  mov     word ptr [rsi], 2011h
0x1800da15c  mov     rbp, [rsp+38h+arg_8]
0x1800da161  mov     eax, ebx
0x1800da163  mov     rbx, [rsp+38h+arg_0]
0x1800da168  add     rsp, 20h
0x1800da16c  pop     r14
0x1800da16e  pop     rdi
0x1800da16f  pop     rsi
0x1800da170  retn
```
