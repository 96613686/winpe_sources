# COleSafeArray::GetByteArray(CByteArray &)

- ea: `0x1802791f0`
- end: `0x1802792d0`
- name: `?GetByteArray@COleSafeArray@@QEAAXAEAVCByteArray@@@Z`
- size: `224`
- prototype: `void __fastcall(COleVariant *this, CByteArray *bytes)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1801dc1e0`
- `0x180231d70`
- `0x180278960`
- `0x1802791f0`

## import_xrefs

- `VCRUNTIME140!memset` at `0x1802792b2`
- `VCRUNTIME140!memset` at `0x1802792b2`
- `VCRUNTIME140!memcpy` at `0x18027928a`
- `VCRUNTIME140!memcpy` at `0x18027928a`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802792c4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1802792c4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802792b8`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1802792b8`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180279218`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x180279218`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180279256`
- `OLEAUT32!__imp_SafeArrayGetElemsize` at `0x180279256`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180279242`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180279242`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18027922e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18027922e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180279207`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180279207`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1802792a4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1802792a4`

## pseudocode

```c
void __fastcall COleSafeArray::GetByteArray(COleVariant *this, CByteArray *bytes)
{
  HRESULT v4; // eax
  int v5; // ebx
  __int64 v6; // rbx
  unsigned __int8 *m_pData; // rcx
  int iUpperBound; // [rsp+40h] [rbp+8h] BYREF
  int iLowerBound; // [rsp+50h] [rbp+18h] BYREF
  void *pSrc; // [rsp+58h] [rbp+20h] BYREF

  v4 = SafeArrayAccessData(this->parray, &pSrc);
  AfxCheckError(v4);
  if ( SafeArrayGetDim(this->parray) != 1 )
  {
    CByteArray::SetSize(bytes, 0, -1);
    goto LABEL_7;
  }
  SafeArrayGetLBound(this->parray, 1u, &iLowerBound);
  SafeArrayGetUBound(this->parray, 1u, &iUpperBound);
  v5 = iUpperBound - iLowerBound + 1;
  v6 = v5 * SafeArrayGetElemsize(this->parray);
  CByteArray::SetSize(bytes, v6, -1);
  m_pData = bytes->m_pData;
  if ( v6 )
  {
    if ( m_pData )
    {
      if ( pSrc )
      {
        memcpy(m_pData, pSrc, (unsigned int)v6);
        goto LABEL_7;
      }
      memset(m_pData, 0, (unsigned int)v6);
    }
    *_errno() = 22;
    _invalid_parameter_noinfo();
    AfxThrowInvalidArgException();
  }
LABEL_7:
  SafeArrayUnaccessData(this->parray);
}

```

## disassembly

```asm
0x1802791f0  push    rbx
0x1802791f2  push    rsi
0x1802791f3  push    rdi
0x1802791f4  sub     rsp, 20h
0x1802791f8  mov     rsi, bytes
0x1802791fb  mov     rdi, this
0x1802791fe  mov     this, [this+8]; psa
0x180279202  lea     bytes, [rsp+38h+pSrc]; ppvData
0x180279207  call    cs:__imp_SafeArrayAccessData
0x18027920d  mov     ecx, eax; sc
0x18027920f  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180279214  mov     this, [rdi+8]; psa
0x180279218  call    cs:__imp_SafeArrayGetDim
0x18027921e  cmp     eax, 1
0x180279221  jnz     short loc_180279292
0x180279223  mov     this, [rdi+8]; psa
0x180279227  lea     r8, [rsp+38h+iLowerBound]; plLbound
0x18027922c  mov     edx, eax; nDim
0x18027922e  call    cs:__imp_SafeArrayGetLBound
0x180279234  mov     this, [rdi+8]; psa
0x180279238  lea     r8, [rsp+38h+iUpperBound]; plUbound
0x18027923d  mov     edx, 1; nDim
0x180279242  call    cs:__imp_SafeArrayGetUBound
0x180279248  mov     ebx, [rsp+38h+iUpperBound]
0x18027924c  sub     ebx, [rsp+38h+iLowerBound]
0x180279250  mov     this, [rdi+8]; psa
0x180279254  inc     ebx
0x180279256  call    cs:__imp_SafeArrayGetElemsize
0x18027925c  imul    eax, ebx
0x18027925f  or      r8, 0FFFFFFFFFFFFFFFFh; nGrowBy
0x180279263  mov     this, rsi; this
0x180279266  mov     edx, eax; nNewSize
0x180279268  mov     ebx, eax
0x18027926a  call    ?SetSize@CByteArray@@QEAAX_J0@Z; CByteArray::SetSize(__int64,__int64)
0x18027926f  mov     this, [rsi+8]; void *
0x180279273  mov     bytes, [rsp+38h+pSrc]; Val
0x180279278  test    rbx, rbx
0x18027927b  jz      short loc_1802792A0
0x18027927d  test    this, this
0x180279280  jz      short loc_1802792B8
0x180279282  mov     r8d, ebx; Size
0x180279285  test    bytes, bytes
0x180279288  jz      short loc_1802792B2
0x18027928a  call    cs:__imp_memcpy
0x180279290  jmp     short loc_1802792A0
0x180279292  or      r8, 0FFFFFFFFFFFFFFFFh; nGrowBy
0x180279296  xor     edx, edx; nNewSize
0x180279298  mov     this, rsi; this
0x18027929b  call    ?SetSize@CByteArray@@QEAAX_J0@Z; CByteArray::SetSize(__int64,__int64)
0x1802792a0  mov     this, [rdi+8]; psa
0x1802792a4  call    cs:__imp_SafeArrayUnaccessData
0x1802792aa  add     rsp, 20h
0x1802792ae  pop     rdi
0x1802792af  pop     rsi
0x1802792b0  pop     rbx
0x1802792b1  retn
0x1802792b2  call    cs:__imp_memset
0x1802792b8  call    cs:__imp__errno
0x1802792be  mov     dword ptr [rax], 16h
0x1802792c4  call    cs:__imp__invalid_parameter_noinfo
0x1802792ca  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
```
