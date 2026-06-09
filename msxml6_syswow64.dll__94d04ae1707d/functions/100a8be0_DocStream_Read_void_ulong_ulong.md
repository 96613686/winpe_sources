# DocStream::Read(void *,ulong,ulong *)

- ea: `0x100a8be0`
- end: `0x100a8cb7`
- name: `?Read@DocStream@@UAGJPAXKPAK@Z`
- size: `215`
- prototype: `HRESULT __stdcall(DocStream *this, void *pv, size_t cb, unsigned int *pcbRead)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1005064c`
- `0x100a8be0`
- `0x100a8dc3`
- `0x101711b4`

## import_xrefs

- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a8c47`
- `OLEAUT32!__imp__SafeArrayAccessData@8` at `0x100a8c47`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a8c98`
- `OLEAUT32!__imp__SafeArrayUnaccessData@4` at `0x100a8c98`

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
0x100a8be0  mov     edi, edi
0x100a8be2  push    ebp
0x100a8be3  mov     ebp, esp
0x100a8be5  push    ecx
0x100a8be6  push    ecx
0x100a8be7  push    ebx
0x100a8be8  push    esi
0x100a8be9  mov     esi, [ebp+this]
0x100a8bec  lea     ecx, [ebp+_EnsureTls]; this
0x100a8bef  push    edi
0x100a8bf0  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100a8bf5  cmp     [ebp+_EnsureTls._tlsdata], 0
0x100a8bf9  jz      loc_100A8CAB
0x100a8bff  mov     edx, [esi+1Ch]
0x100a8c02  xor     edi, edi
0x100a8c04  cmp     dword ptr [esi+0Ch], 2
0x100a8c08  mov     ebx, edi
0x100a8c0a  mov     [ebp+pB], edx
0x100a8c0d  jz      loc_100A8CAB
0x100a8c13  mov     dword ptr [esi+0Ch], 1
0x100a8c1a  cmp     [esi+10h], edi
0x100a8c1d  jnz     short loc_100A8C24
0x100a8c1f  cmp     [esi+28h], edi
0x100a8c22  jz      short Done_7
0x100a8c24  mov     edi, [ebp+cb]
0x100a8c27  cmp     [ebp+pv], ebx
0x100a8c2a  jnz     short loc_100A8C37
0x100a8c2c  test    edi, edi
0x100a8c2e  jz      short Done_7
0x100a8c30  mov     ebx, 80030009h
0x100a8c35  jmp     short CleanUp_95
0x100a8c37  test    edi, edi
0x100a8c39  jz      short Done_7
0x100a8c3b  cmp     [esi+28h], ebx
0x100a8c3e  jz      short loc_100A8C58
0x100a8c40  lea     eax, [ebp+pB]
0x100a8c43  push    eax; ppvData
0x100a8c44  push    dword ptr [esi+28h]; psa
0x100a8c47  call    ds:__imp__SafeArrayAccessData@8; SafeArrayAccessData(x,x)
0x100a8c4d  mov     ebx, eax
0x100a8c4f  test    ebx, ebx
0x100a8c51  js      short CleanUp_95
0x100a8c53  mov     edx, [ebp+pB]
0x100a8c56  jmp     short loc_100A8C6F
0x100a8c58  test    edx, edx
0x100a8c5a  jnz     short loc_100A8C6F
0x100a8c5c  mov     ecx, esi; this
0x100a8c5e  call    ?SaveDocument@DocStream@@AAEJXZ; DocStream::SaveDocument(void)
0x100a8c63  mov     ebx, eax
0x100a8c65  test    ebx, ebx
0x100a8c67  js      short CleanUp_95
0x100a8c69  mov     edx, [esi+1Ch]
0x100a8c6c  mov     [ebp+pB], edx
0x100a8c6f  mov     ecx, [esi+20h]
0x100a8c72  mov     eax, [esi+18h]
0x100a8c75  sub     eax, ecx
0x100a8c77  cmp     edi, eax
0x100a8c79  cmova   edi, eax
0x100a8c7c  lea     eax, [ecx+edx]
0x100a8c7f  push    edi; Size
0x100a8c80  push    eax; Src
0x100a8c81  push    [ebp+pv]; void *
0x100a8c84  call    _memcpy
0x100a8c89  add     [esi+20h], edi
0x100a8c8c  add     esp, 0Ch
0x100a8c8f  cmp     dword ptr [esi+28h], 0
0x100a8c93  jz      short Done_7
0x100a8c95  push    dword ptr [esi+28h]; psa
0x100a8c98  call    ds:__imp__SafeArrayUnaccessData@4; SafeArrayUnaccessData(x)
0x100a8c9e  mov     eax, [ebp+pcbRead]
0x100a8ca1  test    eax, eax
0x100a8ca3  jz      short CleanUp_95
0x100a8ca5  mov     [eax], edi
0x100a8ca7  mov     eax, ebx
0x100a8ca9  jmp     short loc_100A8CB0
0x100a8cab  mov     eax, 80004005h
0x100a8cb0  pop     edi
0x100a8cb1  pop     esi
0x100a8cb2  pop     ebx
0x100a8cb3  leave
0x100a8cb4  retn    10h
```
