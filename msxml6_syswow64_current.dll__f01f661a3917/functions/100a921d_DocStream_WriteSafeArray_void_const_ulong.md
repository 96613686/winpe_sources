# DocStream::WriteSafeArray(void const *,ulong)

- ea: `0x100a921d`
- end: `0x100a92d8`
- name: `?WriteSafeArray@DocStream@@AAEJPBXK@Z`
- size: `187`
- prototype: `HRESULT __thiscall(DocStream *this, const void *pv, unsigned int cb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100a9040`

## callees

- `0x100a897c`
- `0x100a921d`
- `0x101711b4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a9271`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a9271`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a92a5`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a92a5`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x100a9245`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x100a9245`

## pseudocode

```c
HRESULT __thiscall DocStream::WriteSafeArray(DocStream *this, char *pv, unsigned int cb)
{
  HRESULT v4; // ebx
  unsigned int *p_dwBuffered; // esi
  tagSAFEARRAY *Vector; // eax
  size_t v7; // eax
  unsigned int v8; // ecx
  unsigned __int8 *pB; // [esp+Ch] [ebp-Ch] BYREF
  int v11; // [esp+10h] [ebp-8h]
  size_t Size; // [esp+14h] [ebp-4h]

  v11 = 0;
  v4 = 0;
  p_dwBuffered = &this->_dwBuffered;
  if ( !this->_psa )
  {
    Vector = SafeArrayCreateVector(0x11u, 0, 0x1000u);
    this->_psa = Vector;
    *p_dwBuffered = 0;
    if ( !Vector )
      return -2147024882;
  }
LABEL_9:
  v8 = cb;
  while ( v8 )
  {
    v7 = 4096 - *p_dwBuffered;
    if ( v8 <= v7 )
      v7 = v8;
    Size = v7;
    v4 = SafeArrayAccessData(this->_psa, (void **)&pB);
    if ( v4 < 0 )
      break;
    memcpy(&pB[*p_dwBuffered], &pv[v11], Size);
    *p_dwBuffered += Size;
    this->_psa->rgsabound[0].cElements = *p_dwBuffered;
    SafeArrayUnaccessData(this->_psa);
    v8 = cb - Size;
    v11 += Size;
    cb -= Size;
    if ( *p_dwBuffered >= 0x1000 )
    {
      DocStream::FlushSafeArray(this);
      goto LABEL_9;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x100a921d  mov     edi, edi
0x100a921f  push    ebp
0x100a9220  mov     ebp, esp
0x100a9222  sub     esp, 0Ch
0x100a9225  push    ebx
0x100a9226  push    esi
0x100a9227  push    edi
0x100a9228  mov     edi, this
0x100a922a  xor     eax, eax
0x100a922c  mov     [ebp+var_8], eax
0x100a922f  mov     ebx, eax
0x100a9231  lea     esi, [edi+2Ch]
0x100a9234  cmp     [edi+28h], eax
0x100a9237  jnz     loc_100A92C8
0x100a923d  push    1000h; cElements
0x100a9242  push    eax; lLbound
0x100a9243  push    11h; vt
0x100a9245  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x100a924b  mov     [edi+28h], eax
0x100a924e  mov     [esi], ebx
0x100a9250  test    eax, eax
0x100a9252  jnz     short loc_100A92C8
0x100a9254  mov     ebx, 8007000Eh
0x100a9259  jmp     short CleanUp_99
0x100a925b  mov     eax, 1000h
0x100a9260  sub     eax, [esi]
0x100a9262  cmp     this, eax
0x100a9264  cmovbe  eax, this
0x100a9267  mov     [ebp+Size], eax
0x100a926a  lea     eax, [ebp+pB]
0x100a926d  push    eax; ppvData
0x100a926e  push    dword ptr [edi+28h]; psa
0x100a9271  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x100a9277  mov     ebx, eax
0x100a9279  test    ebx, ebx
0x100a927b  js      short CleanUp_99
0x100a927d  push    [ebp+Size]; Size
0x100a9280  mov     this, [ebp+pv]
0x100a9283  add     this, [ebp+var_8]
0x100a9286  push    this; Src
0x100a9287  mov     this, [esi]
0x100a9289  add     this, [ebp+pB]
0x100a928c  push    this; void *
0x100a928d  call    _memcpy
0x100a9292  mov     eax, [ebp+Size]
0x100a9295  add     esp, 0Ch
0x100a9298  add     [esi], eax
0x100a929a  mov     eax, [edi+28h]
0x100a929d  mov     this, [esi]
0x100a929f  mov     [eax+10h], this
0x100a92a2  push    dword ptr [edi+28h]; psa
0x100a92a5  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x100a92ab  mov     this, [ebp+cb]
0x100a92ae  mov     eax, [ebp+Size]
0x100a92b1  sub     this, eax
0x100a92b3  add     [ebp+var_8], eax
0x100a92b6  cmp     dword ptr [esi], 1000h
0x100a92bc  mov     [ebp+cb], this
0x100a92bf  jb      short loc_100A92CB
0x100a92c1  mov     this, edi; this
0x100a92c3  call    ?FlushSafeArray@DocStream@@AAEJXZ; DocStream::FlushSafeArray(void)
0x100a92c8  mov     this, [ebp+cb]
0x100a92cb  test    this, this
0x100a92cd  jnz     short loc_100A925B
0x100a92cf  pop     edi
0x100a92d0  pop     esi
0x100a92d1  mov     eax, ebx
0x100a92d3  pop     ebx
0x100a92d4  leave
0x100a92d5  retn    8
```
