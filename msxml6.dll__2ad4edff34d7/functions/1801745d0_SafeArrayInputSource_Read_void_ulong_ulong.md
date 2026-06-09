# SafeArrayInputSource::Read(void *,ulong,ulong *)

- ea: `0x1801745d0`
- end: `0x180174646`
- name: `?Read@SafeArrayInputSource@@UEAAJPEAXKPEAK@Z`
- size: `118`
- prototype: `HRESULT __fastcall(SafeArrayInputSource *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1801745d0`
- `0x180178528`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180174604`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180174604`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180174625`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180174625`

## pseudocode

```c
HRESULT __fastcall SafeArrayInputSource::Read(
        SafeArrayInputSource *this,
        void *pv,
        unsigned int cb,
        unsigned int *pcbRead)
{
  tagSAFEARRAY *pSafeArray; // rcx
  unsigned int ulSize; // edi
  HRESULT result; // eax
  unsigned __int8 *pbData; // [rsp+50h] [rbp+8h] BYREF

  pbData = 0;
  pSafeArray = this->_pSafeArray;
  ulSize = cb;
  if ( !pSafeArray )
  {
    result = 0;
    ulSize = 0;
LABEL_8:
    this->_ulCurr += ulSize;
    this->_ulSize -= ulSize;
    *pcbRead = ulSize;
    return result;
  }
  if ( cb > this->_ulSize )
    ulSize = this->_ulSize;
  result = SafeArrayAccessData(pSafeArray, (void **)&pbData);
  if ( result >= 0 )
  {
    memcpy_0(pv, &pbData[this->_ulCurr], ulSize);
    result = SafeArrayUnaccessData(this->_pSafeArray);
    if ( result >= 0 )
      goto LABEL_8;
  }
  return result;
}

```

## disassembly

```asm
0x1801745d0  push    rbx
0x1801745d2  push    rbp
0x1801745d3  push    rsi
0x1801745d4  push    rdi
0x1801745d5  sub     rsp, 28h
0x1801745d9  mov     rbx, this
0x1801745dc  mov     [rsp+48h+pbData], 0
0x1801745e5  mov     this, [this+20h]; psa
0x1801745e9  mov     rsi, pcbRead
0x1801745ec  mov     edi, cb
0x1801745ef  mov     rbp, pv
0x1801745f2  test    this, this
0x1801745f5  jz      short loc_180174631
0x1801745f7  cmp     cb, [rbx+2Ch]
0x1801745fb  lea     pv, [rsp+48h+pbData]; ppvData
0x180174600  cmova   edi, [rbx+2Ch]
0x180174604  call    cs:__imp_SafeArrayAccessData
0x18017460a  test    eax, eax
0x18017460c  js      short $CleanUp_589
0x18017460e  mov     edx, [rbx+28h]
0x180174611  mov     this, rbp; void *
0x180174614  add     pv, [rsp+48h+pbData]; Src
0x180174619  mov     cb, edi; Size
0x18017461c  call    memcpy_0
0x180174621  mov     this, [rbx+20h]; psa
0x180174625  call    cs:__imp_SafeArrayUnaccessData
0x18017462b  test    eax, eax
0x18017462d  js      short $CleanUp_589
0x18017462f  jmp     short loc_180174635
0x180174631  xor     eax, eax
0x180174633  xor     edi, edi
0x180174635  add     [rbx+28h], edi
0x180174638  sub     [rbx+2Ch], edi
0x18017463b  mov     [rsi], edi
0x18017463d  add     rsp, 28h
0x180174641  pop     rdi
0x180174642  pop     rsi
0x180174643  pop     rbp
0x180174644  pop     rbx
0x180174645  retn
```
