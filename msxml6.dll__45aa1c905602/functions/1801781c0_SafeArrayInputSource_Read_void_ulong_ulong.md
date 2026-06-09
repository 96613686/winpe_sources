# SafeArrayInputSource::Read(void *,ulong,ulong *)

- ea: `0x1801781c0`
- end: `0x180178243`
- name: `?Read@SafeArrayInputSource@@UEAAJPEAXKPEAK@Z`
- size: `131`
- prototype: `HRESULT __fastcall(SafeArrayInputSource *this, void *pv, unsigned int cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1801781c0`
- `0x18017c1d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801781f4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1801781f4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18017821b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18017821b`

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
0x1801781c0  push    rbx
0x1801781c2  push    rbp
0x1801781c3  push    rsi
0x1801781c4  push    rdi
0x1801781c5  sub     rsp, 28h
0x1801781c9  mov     rbx, this
0x1801781cc  mov     [rsp+48h+pbData], 0
0x1801781d5  mov     this, [this+20h]; psa
0x1801781d9  mov     rsi, pcbRead
0x1801781dc  mov     edi, cb
0x1801781df  mov     rbp, pv
0x1801781e2  test    this, this
0x1801781e5  jz      short loc_18017822D
0x1801781e7  cmp     cb, [rbx+2Ch]
0x1801781eb  lea     pv, [rsp+48h+pbData]; ppvData
0x1801781f0  cmova   edi, [rbx+2Ch]
0x1801781f4  call    cs:__imp_SafeArrayAccessData
0x1801781fb  nop     dword ptr [rax+rax+00h]
0x180178200  test    eax, eax
0x180178202  js      short $CleanUp_589
0x180178204  mov     edx, [rbx+28h]
0x180178207  mov     this, rbp; void *
0x18017820a  add     pv, [rsp+48h+pbData]; Src
0x18017820f  mov     cb, edi; Size
0x180178212  call    memcpy_0
0x180178217  mov     this, [rbx+20h]; psa
0x18017821b  call    cs:__imp_SafeArrayUnaccessData
0x180178222  nop     dword ptr [rax+rax+00h]
0x180178227  test    eax, eax
0x180178229  js      short $CleanUp_589
0x18017822b  jmp     short loc_180178231
0x18017822d  xor     eax, eax
0x18017822f  xor     edi, edi
0x180178231  add     [rbx+28h], edi
0x180178234  sub     [rbx+2Ch], edi
0x180178237  mov     [rsi], edi
0x180178239  add     rsp, 28h
0x18017823d  pop     rdi
0x18017823e  pop     rsi
0x18017823f  pop     rbp
0x180178240  pop     rbx
0x180178241  retn
```
