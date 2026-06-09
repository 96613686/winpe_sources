# DocStream::Read(void *,ulong,ulong *)

- ea: `0x100a8cf0`
- end: `0x100a8dc7`
- name: `?Read@DocStream@@UAGJPAXKPAK@Z`
- size: `215`
- prototype: `HRESULT __stdcall(DocStream *this, void *pv, size_t cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100505bc`
- `0x100a8cf0`
- `0x100a8ed3`
- `0x101712a4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a8d57`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a8d57`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a8da8`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a8da8`

## pseudocode

```c
HRESULT __stdcall DocStream::Read(DocStream *this, void *pv, size_t cb, unsigned int *pcbRead)
{
  unsigned __int8 *pBytes; // edx
  size_t v5; // edi
  bool v6; // zf
  HRESULT v7; // ebx
  unsigned int cbRead; // ecx
  EnsureTls _EnsureTls; // [esp+Ch] [ebp-8h] BYREF
  unsigned __int8 *pB; // [esp+10h] [ebp-4h] BYREF

  EnsureTls::EnsureTls(&_EnsureTls);
  if ( _EnsureTls._tlsdata )
  {
    pBytes = this->_pBytes;
    v5 = 0;
    v6 = this->_dwState == NO_VARIABLES;
    v7 = 0;
    pB = pBytes;
    if ( !v6 )
    {
      this->_dwState = NO_CURRENT;
      if ( this->_pDoc._p || this->_psa )
      {
        v5 = cb;
        if ( pv )
        {
          if ( cb )
          {
            if ( this->_psa )
            {
              v7 = SafeArrayAccessData(this->_psa, (void **)&pB);
              if ( v7 < 0 )
                return v7;
              pBytes = pB;
            }
            else if ( !pBytes )
            {
              v7 = DocStream::SaveDocument(this);
              if ( v7 < 0 )
                return v7;
              pBytes = this->_pBytes;
              pB = pBytes;
            }
            cbRead = this->_cbRead;
            if ( cb > this->_cbWritten - cbRead )
              v5 = this->_cbWritten - cbRead;
            memcpy(pv, &pBytes[cbRead], v5);
            this->_cbRead += v5;
            if ( this->_psa )
              SafeArrayUnaccessData(this->_psa);
          }
        }
        else if ( cb )
        {
          return -2147287031;
        }
      }
      if ( pcbRead )
        *pcbRead = v5;
      return v7;
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x100a8cf0  mov     edi, edi
0x100a8cf2  push    ebp
0x100a8cf3  mov     ebp, esp
0x100a8cf5  push    ecx
0x100a8cf6  push    ecx
0x100a8cf7  push    ebx
0x100a8cf8  push    esi
0x100a8cf9  mov     esi, [ebp+this]
0x100a8cfc  lea     ecx, [ebp+_EnsureTls]; this
0x100a8cff  push    edi
0x100a8d00  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100a8d05  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100a8d09  jz      loc_100A8DBB
0x100a8d0f  mov     edx, [esi+1Ch]
0x100a8d12  xor     edi, edi
0x100a8d14  cmp     dword ptr [esi+0Ch], 2
0x100a8d18  mov     ebx, edi
0x100a8d1a  mov     [ebp+pB], edx
0x100a8d1d  jz      loc_100A8DBB
0x100a8d23  mov     dword ptr [esi+0Ch], 1
0x100a8d2a  cmp     [esi+10h], edi
0x100a8d2d  jnz     short loc_100A8D34
0x100a8d2f  cmp     [esi+28h], edi
0x100a8d32  jz      short Done_7
0x100a8d34  mov     edi, [ebp+cb]
0x100a8d37  cmp     [ebp+pv], ebx
0x100a8d3a  jnz     short loc_100A8D47
0x100a8d3c  test    edi, edi
0x100a8d3e  jz      short Done_7
0x100a8d40  mov     ebx, 80030009h
0x100a8d45  jmp     short CleanUp_95
0x100a8d47  test    edi, edi
0x100a8d49  jz      short Done_7
0x100a8d4b  cmp     [esi+28h], ebx
0x100a8d4e  jz      short loc_100A8D68
0x100a8d50  lea     eax, [ebp+pB]
0x100a8d53  push    eax; ppvData
0x100a8d54  push    dword ptr [esi+28h]; psa
0x100a8d57  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x100a8d5d  mov     ebx, eax
0x100a8d5f  test    ebx, ebx
0x100a8d61  js      short CleanUp_95
0x100a8d63  mov     edx, [ebp+pB]
0x100a8d66  jmp     short loc_100A8D7F
0x100a8d68  test    edx, edx
0x100a8d6a  jnz     short loc_100A8D7F
0x100a8d6c  mov     ecx, esi; this
0x100a8d6e  call    ?SaveDocument@DocStream@@AAEJXZ; DocStream::SaveDocument(void)
0x100a8d73  mov     ebx, eax
0x100a8d75  test    ebx, ebx
0x100a8d77  js      short CleanUp_95
0x100a8d79  mov     edx, [esi+1Ch]
0x100a8d7c  mov     [ebp+pB], edx
0x100a8d7f  mov     ecx, [esi+20h]
0x100a8d82  mov     eax, [esi+18h]
0x100a8d85  sub     eax, ecx
0x100a8d87  cmp     edi, eax
0x100a8d89  cmova   edi, eax
0x100a8d8c  lea     eax, [ecx+edx]
0x100a8d8f  push    edi; Size
0x100a8d90  push    eax; Src
0x100a8d91  push    [ebp+pv]; void *
0x100a8d94  call    _memcpy
0x100a8d99  add     [esi+20h], edi
0x100a8d9c  add     esp, 0Ch
0x100a8d9f  cmp     dword ptr [esi+28h], 0
0x100a8da3  jz      short Done_7
0x100a8da5  push    dword ptr [esi+28h]; psa
0x100a8da8  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x100a8dae  mov     eax, [ebp+pcbRead]
0x100a8db1  test    eax, eax
0x100a8db3  jz      short CleanUp_95
0x100a8db5  mov     [eax], edi
0x100a8db7  mov     eax, ebx
0x100a8db9  jmp     short loc_100A8DC0
0x100a8dbb  mov     eax, 80004005h
0x100a8dc0  pop     edi
0x100a8dc1  pop     esi
0x100a8dc2  pop     ebx
0x100a8dc3  leave
0x100a8dc4  retn    10h
```
