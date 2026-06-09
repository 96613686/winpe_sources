# DocStream::WriteSafeArray(void const *,ulong)

- ea: `0x100a932d`
- end: `0x100a93e8`
- name: `?WriteSafeArray@DocStream@@AAEJPBXK@Z`
- size: `187`
- prototype: `HRESULT __thiscall(DocStream *this, char *pv, unsigned int cb)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x100a9150`

## callees

- `0x100a8a8c`
- `0x100a932d`
- `0x101712a4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a9381`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a9381`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a93b5`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a93b5`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x100a9355`
- `OLEAUT32!__imp__SafeArrayCreateVector@12` at `0x100a9355`

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
0x100a932d  mov     edi, edi
0x100a932f  push    ebp
0x100a9330  mov     ebp, esp
0x100a9332  sub     esp, 0Ch
0x100a9335  push    ebx
0x100a9336  push    esi
0x100a9337  push    edi
0x100a9338  mov     edi, this
0x100a933a  xor     eax, eax
0x100a933c  mov     [ebp+var_8], eax
0x100a933f  mov     ebx, eax
0x100a9341  lea     esi, [edi+2Ch]
0x100a9344  cmp     [edi+28h], eax
0x100a9347  jnz     loc_100A93D8
0x100a934d  push    1000h; cElements
0x100a9352  push    eax; lLbound
0x100a9353  push    11h; vt
0x100a9355  call    ds:__imp__SafeArrayCreateVector@12; SafeArrayCreateVector(x,x,x)
0x100a935b  mov     [edi+28h], eax
0x100a935e  mov     [esi], ebx
0x100a9360  test    eax, eax
0x100a9362  jnz     short loc_100A93D8
0x100a9364  mov     ebx, 8007000Eh
0x100a9369  jmp     short CleanUp_99
0x100a936b  mov     eax, 1000h
0x100a9370  sub     eax, [esi]
0x100a9372  cmp     this, eax
0x100a9374  cmovbe  eax, this
0x100a9377  mov     [ebp+Size], eax
0x100a937a  lea     eax, [ebp+pB]
0x100a937d  push    eax; ppvData
0x100a937e  push    dword ptr [edi+28h]; psa
0x100a9381  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x100a9387  mov     ebx, eax
0x100a9389  test    ebx, ebx
0x100a938b  js      short CleanUp_99
0x100a938d  push    [ebp+Size]; Size
0x100a9390  mov     this, [ebp+pv]
0x100a9393  add     this, [ebp+var_8]
0x100a9396  push    this; Src
0x100a9397  mov     this, [esi]
0x100a9399  add     this, [ebp+pB]
0x100a939c  push    this; void *
0x100a939d  call    _memcpy
0x100a93a2  mov     eax, [ebp+Size]
0x100a93a5  add     esp, 0Ch
0x100a93a8  add     [esi], eax
0x100a93aa  mov     eax, [edi+28h]
0x100a93ad  mov     this, [esi]
0x100a93af  mov     [eax+10h], this
0x100a93b2  push    dword ptr [edi+28h]; psa
0x100a93b5  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x100a93bb  mov     this, [ebp+cb]
0x100a93be  mov     eax, [ebp+Size]
0x100a93c1  sub     this, eax
0x100a93c3  add     [ebp+var_8], eax
0x100a93c6  cmp     dword ptr [esi], 1000h
0x100a93cc  mov     [ebp+cb], this
0x100a93cf  jb      short loc_100A93DB
0x100a93d1  mov     this, edi; this
0x100a93d3  call    ?FlushSafeArray@DocStream@@AAEJXZ; DocStream::FlushSafeArray(void)
0x100a93d8  mov     this, [ebp+cb]
0x100a93db  test    this, this
0x100a93dd  jnz     short loc_100A936B
0x100a93df  pop     edi
0x100a93e0  pop     esi
0x100a93e1  mov     eax, ebx
0x100a93e3  pop     ebx
0x100a93e4  leave
0x100a93e5  retn    8
```
