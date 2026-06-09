# DocStream::Stat(tagSTATSTG *,ulong)

- ea: `0x1800f0a50`
- end: `0x1800f0bc3`
- name: `?Stat@DocStream@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `371`
- prototype: `__int64 __fastcall(DocStream *this, tagSTATSTG *pstatstg, char grfStatFlag)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002b064`
- `0x180056bdc`
- `0x18005ac64`
- `0x18009f718`
- `0x1800a3e04`
- `0x1800cba94`
- `0x1800f0938`
- `0x1800f0a50`
- `0x180178528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f0b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f0b51`

## pseudocode

```c
__int64 __fastcall DocStream::Stat(DocStream *this, tagSTATSTG *pstatstg, char grfStatFlag)
{
  unsigned int v7; // edi
  Document *p; // rax
  String *v9; // r14
  unsigned __int64 length; // rbx
  SIZE_T v11; // rcx
  wchar_t *v12; // rax
  unsigned __int64 v13; // rbx
  unsigned __int64 cb; // [rsp+78h] [rbp+20h] BYREF

  EnsureTls::EnsureTls((EnsureTls *)&cb);
  if ( !cb )
    return 2147500037LL;
  if ( pstatstg )
  {
    v7 = 0;
    memset_0(pstatstg, 0, sizeof(tagSTATSTG));
    pstatstg->type = 2;
    if ( this->_pDoc._p )
    {
      if ( !this->_pBytes )
      {
        v7 = DocStream::SaveDocument(this);
        if ( (v7 & 0x80000000) != 0 )
          return v7;
      }
    }
    pstatstg->cbSize.LowPart = this->_cbWritten;
    if ( (grfStatFlag & 1) != 0 )
      return v7;
    p = this->_pDoc._p;
    if ( !p )
      return v7;
    v9 = p->_pResolvedURLdoc._p;
    if ( !v9 )
      return v7;
    cb = 0;
    length = (unsigned int)v9->_length;
    if ( length + 1 < length )
    {
      cb = -1;
    }
    else
    {
      cb = length + 1;
      if ( ULongLongMult(length + 1, 2u, &cb) >= 0 )
      {
        v11 = cb;
        if ( cb <= 0x7FFFFFFF )
        {
          v7 = 0;
          goto LABEL_17;
        }
      }
    }
    v11 = 0;
    cb = 0;
    v7 = -2147024362;
LABEL_17:
    if ( (v7 & 0x80000000) == 0 )
    {
      v12 = (wchar_t *)CoTaskMemAlloc(v11);
      pstatstg->pwcsName = v12;
      if ( v12 )
      {
        v13 = length;
        memcpy_0(v12, v9->_pwsz, v13 * 2);
        pstatstg->pwcsName[v13] = 0;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    return v7;
  }
  return (unsigned int)-2147287031;
}

```

## disassembly

```asm
0x1800f0a50  push    rbx
0x1800f0a52  push    rsi
0x1800f0a53  push    rdi
0x1800f0a54  push    r14
0x1800f0a56  sub     rsp, 38h
0x1800f0a5a  mov     r14d, grfStatFlag
0x1800f0a5d  mov     rsi, pstatstg
0x1800f0a60  mov     rbx, this
0x1800f0a63  lea     this, [rsp+58h+cb]; this
0x1800f0a68  call    ??0EnsureTls@@QEAA@XZ; EnsureTls::EnsureTls(void)
0x1800f0a6d  cmp     [rsp+58h+cb], 0
0x1800f0a73  jnz     short loc_1800F0A7F
0x1800f0a75  mov     eax, 80004005h
0x1800f0a7a  jmp     loc_1800F0BB9
0x1800f0a7f  test    rsi, rsi
0x1800f0a82  jnz     short loc_1800F0A8E
0x1800f0a84  mov     edi, 80030009h
0x1800f0a89  jmp     $CleanUp_214
0x1800f0a8e  xor     edi, edi
0x1800f0a90  xor     edx, edx; Val
0x1800f0a92  lea     grfStatFlag, [rdi+50h]; Size
0x1800f0a96  mov     this, rsi; void *
0x1800f0a99  call    memset_0
0x1800f0a9e  mov     dword ptr [rsi+8], 2
0x1800f0aa5  cmp     [rbx+20h], rdi
0x1800f0aa9  jz      short loc_1800F0AC7
0x1800f0aab  cmp     [rbx+38h], rdi
0x1800f0aaf  jnz     short loc_1800F0AC7
0x1800f0ab1  mov     this, rbx; this
0x1800f0ab4  call    ?SaveDocument@DocStream@@AEAAJXZ; DocStream::SaveDocument(void)
0x1800f0ab9  mov     edi, eax
0x1800f0abb  mov     [rsp+58h+hr], eax
0x1800f0abf  test    eax, eax
0x1800f0ac1  js      $CleanUp_214
0x1800f0ac7  mov     eax, [rbx+30h]
0x1800f0aca  mov     [rsi+10h], eax
0x1800f0acd  test    r14b, 1
0x1800f0ad1  jnz     loc_1800F0B85
0x1800f0ad7  mov     rax, [rbx+20h]
0x1800f0adb  test    rax, rax
0x1800f0ade  jz      loc_1800F0B85
0x1800f0ae4  mov     r14, [rax+100h]
0x1800f0aeb  test    r14, r14
0x1800f0aee  jz      loc_1800F0B85
0x1800f0af4  mov     [rsp+58h+cb], 0
0x1800f0afd  mov     ebx, [r14+10h]
0x1800f0b01  lea     this, [rbx+1]; ullMultiplicand
0x1800f0b05  cmp     this, rbx
0x1800f0b08  jb      short loc_1800F0B34
0x1800f0b0a  mov     [rsp+58h+cb], this
0x1800f0b0f  lea     r8, [rsp+58h+cb]; pullResult
0x1800f0b14  mov     edx, 2; ullMultiplier
0x1800f0b19  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800f0b1e  test    eax, eax
0x1800f0b20  js      short loc_1800F0B3D
0x1800f0b22  mov     this, [rsp+58h+cb]
0x1800f0b27  cmp     this, 7FFFFFFFh
0x1800f0b2e  ja      short loc_1800F0B3D
0x1800f0b30  xor     edi, edi
0x1800f0b32  jmp     short loc_1800F0B49
0x1800f0b34  mov     [rsp+58h+cb], 0FFFFFFFFFFFFFFFFh
0x1800f0b3d  xor     ecx, ecx; cb
0x1800f0b3f  mov     [rsp+58h+cb], this
0x1800f0b44  mov     edi, 80070216h
0x1800f0b49  mov     [rsp+58h+hr], edi
0x1800f0b4d  test    edi, edi
0x1800f0b4f  js      short $CleanUp_214
0x1800f0b51  call    cs:__imp_CoTaskMemAlloc
0x1800f0b57  mov     [rsi], rax
0x1800f0b5a  test    rax, rax
0x1800f0b5d  jnz     short loc_1800F0B6A
0x1800f0b5f  mov     edi, 8007000Eh
0x1800f0b64  mov     [rsp+58h+hr], edi
0x1800f0b68  jmp     short loc_1800F0B85
0x1800f0b6a  add     rbx, rbx
0x1800f0b6d  mov     r8, rbx; Size
0x1800f0b70  mov     pstatstg, [r14+18h]; Src
0x1800f0b74  mov     this, rax; void *
0x1800f0b77  call    memcpy_0
0x1800f0b7c  mov     this, [rsi]
0x1800f0b7f  xor     eax, eax
0x1800f0b81  mov     [rbx+this], ax
0x1800f0b85  jmp     short $CleanUp_214
0x1800f0b87  call    ?exceptionCatch@Exception@@SAXXZ; Exception::exceptionCatch(void)
0x1800f0b8c  mov     ecx, cs:_tls_index
0x1800f0b92  mov     rax, gs:58h
0x1800f0b9b  mov     edx, 8
0x1800f0ba0  mov     rax, [rax+this*8]
0x1800f0ba4  mov     this, [rax+pstatstg]
0x1800f0ba8  mov     this, [this+8]; e
0x1800f0bac  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SAJPEAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x1800f0bb1  mov     edi, eax
0x1800f0bb3  mov     [rsp+58h+hr], eax
0x1800f0bb7  mov     eax, edi
0x1800f0bb9  add     rsp, 38h
0x1800f0bbd  pop     r14
0x1800f0bbf  pop     rdi
0x1800f0bc0  pop     rsi
0x1800f0bc1  pop     rbx
0x1800f0bc2  retn
0x18017de3a  push    rbp
0x18017de3c  sub     rsp, 20h
0x18017de40  mov     rbp, rdx
0x18017de43  call    ?fillException@Exception@@SAHPEAU_EXCEPTION_POINTERS@@@Z
0x18017de48  nop
0x18017de49  add     rsp, 20h
0x18017de4d  pop     rbp
0x18017de4e  retn
```
