# SafeArrayInputSource::Read(void *,ulong,ulong *)

- ea: `0x1016a140`
- end: `0x1016a1a7`
- name: `?Read@SafeArrayInputSource@@UAEJPAXKPAK@Z`
- size: `103`
- prototype: `HRESULT __thiscall(SafeArrayInputSource *this, void *pv, size_t cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1016a140`
- `0x101711b4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1016a162`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x1016a162`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1016a184`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x1016a184`

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
0x1016a140  mov     edi, edi
0x1016a142  push    ebp
0x1016a143  mov     ebp, esp
0x1016a145  push    this
0x1016a146  push    esi
0x1016a147  mov     esi, this
0x1016a149  xor     this, this
0x1016a14b  push    edi
0x1016a14c  cmp     [esi+10h], this
0x1016a14f  jz      short loc_1016A192
0x1016a151  mov     edi, [ebp+cb]
0x1016a154  lea     eax, [ebp+pbData]
0x1016a157  cmp     edi, [esi+18h]
0x1016a15a  push    eax; ppvData
0x1016a15b  push    dword ptr [esi+10h]; psa
0x1016a15e  cmova   edi, [esi+18h]
0x1016a162  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x1016a168  mov     this, eax
0x1016a16a  test    this, this
0x1016a16c  js      short CleanUp_584
0x1016a16e  mov     eax, [esi+14h]
0x1016a171  add     eax, [ebp+pbData]
0x1016a174  push    edi; Size
0x1016a175  push    eax; Src
0x1016a176  push    [ebp+pv]; void *
0x1016a179  call    _memcpy
0x1016a17e  add     esp, 0Ch
0x1016a181  push    dword ptr [esi+10h]; psa
0x1016a184  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x1016a18a  mov     this, eax
0x1016a18c  test    this, this
0x1016a18e  js      short CleanUp_584
0x1016a190  jmp     short loc_1016A194
0x1016a192  xor     edi, edi
0x1016a194  mov     eax, [ebp+pcbRead]
0x1016a197  add     [esi+14h], edi
0x1016a19a  sub     [esi+18h], edi
0x1016a19d  mov     [eax], edi
0x1016a19f  pop     edi
0x1016a1a0  mov     eax, this
0x1016a1a2  pop     esi
0x1016a1a3  leave
0x1016a1a4  retn    0Ch
```
