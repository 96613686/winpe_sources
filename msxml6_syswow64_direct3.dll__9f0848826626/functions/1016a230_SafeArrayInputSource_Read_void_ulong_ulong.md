# SafeArrayInputSource::Read(void *,ulong,ulong *)

- ea: `0x1016a230`
- end: `0x1016a297`
- name: `?Read@SafeArrayInputSource@@UAEJPAXKPAK@Z`
- size: `103`
- prototype: `HRESULT __thiscall(SafeArrayInputSource *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1016a230`
- `0x101712a4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1016a252`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1016a252`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1016a274`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1016a274`

## pseudocode

```c
HRESULT __thiscall SafeArrayInputSource::Read(SafeArrayInputSource *this, void *pv, size_t cb, unsigned int *pcbRead)
{
  HRESULT v5; // ecx
  size_t ulSize; // edi
  unsigned __int8 *pbData; // [esp+8h] [ebp-4h] BYREF

  v5 = 0;
  if ( !this->_pSafeArray )
  {
    ulSize = 0;
LABEL_8:
    this->_ulCurr += ulSize;
    this->_ulSize -= ulSize;
    *pcbRead = ulSize;
    return v5;
  }
  ulSize = cb;
  if ( cb > this->_ulSize )
    ulSize = this->_ulSize;
  v5 = SafeArrayAccessData(this->_pSafeArray, (void **)&pbData);
  if ( v5 >= 0 )
  {
    memcpy(pv, &pbData[this->_ulCurr], ulSize);
    v5 = SafeArrayUnaccessData(this->_pSafeArray);
    if ( v5 >= 0 )
      goto LABEL_8;
  }
  return v5;
}

```

## disassembly

```asm
0x1016a230  mov     edi, edi
0x1016a232  push    ebp
0x1016a233  mov     ebp, esp
0x1016a235  push    this
0x1016a236  push    esi
0x1016a237  mov     esi, this
0x1016a239  xor     this, this
0x1016a23b  push    edi
0x1016a23c  cmp     [esi+10h], this
0x1016a23f  jz      short loc_1016A282
0x1016a241  mov     edi, [ebp+cb]
0x1016a244  lea     eax, [ebp+pbData]
0x1016a247  cmp     edi, [esi+18h]
0x1016a24a  push    eax; ppvData
0x1016a24b  push    dword ptr [esi+10h]; psa
0x1016a24e  cmova   edi, [esi+18h]
0x1016a252  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1016a258  mov     this, eax
0x1016a25a  test    this, this
0x1016a25c  js      short CleanUp_584
0x1016a25e  mov     eax, [esi+14h]
0x1016a261  add     eax, [ebp+pbData]
0x1016a264  push    edi; Size
0x1016a265  push    eax; Src
0x1016a266  push    [ebp+pv]; void *
0x1016a269  call    _memcpy
0x1016a26e  add     esp, 0Ch
0x1016a271  push    dword ptr [esi+10h]; psa
0x1016a274  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1016a27a  mov     this, eax
0x1016a27c  test    this, this
0x1016a27e  js      short CleanUp_584
0x1016a280  jmp     short loc_1016A284
0x1016a282  xor     edi, edi
0x1016a284  mov     eax, [ebp+pcbRead]
0x1016a287  add     [esi+14h], edi
0x1016a28a  sub     [esi+18h], edi
0x1016a28d  mov     [eax], edi
0x1016a28f  pop     edi
0x1016a290  mov     eax, this
0x1016a292  pop     esi
0x1016a293  leave
0x1016a294  retn    0Ch
```
