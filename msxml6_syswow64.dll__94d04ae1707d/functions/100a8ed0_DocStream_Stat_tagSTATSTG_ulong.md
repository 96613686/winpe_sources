# DocStream::Stat(tagSTATSTG *,ulong)

- ea: `0x100a8ed0`
- end: `0x100a9036`
- name: `?Stat@DocStream@@UAGJPAUtagSTATSTG@@K@Z`
- size: `358`
- prototype: `HRESULT __stdcall(DocStream *this, tagSTATSTG *pstatstg, unsigned int grfStatFlag)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1004118e`
- `0x1005064c`
- `0x1006c080`
- `0x1006c354`
- `0x10076046`
- `0x100779c5`
- `0x10077a1b`
- `0x100a8dc3`
- `0x100a8ed0`
- `0x101711b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a8fb9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a8fb9`

## pseudocode

```c
HRESULT __stdcall DocStream::Stat(DocStream *this, tagSTATSTG *pstatstg, char grfStatFlag)
{
  int v4; // edi
  Document *p; // eax
  String *v6; // eax
  unsigned int length; // esi
  unsigned int v8; // eax
  int v9; // ecx
  SIZE_T v10; // eax
  wchar_t *v11; // eax
  unsigned int v12; // esi
  String *v13; // [esp+10h] [ebp-24h]
  unsigned int cb; // [esp+18h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+1Ch] [ebp-18h]

  EnsureTls::EnsureTls((EnsureTls *)&cb);
  if ( !cb )
    return -2147467259;
  v4 = 0;
  if ( !pstatstg )
    return -2147287031;
  memset(pstatstg, 0, sizeof(tagSTATSTG));
  pstatstg->type = 2;
  ms_exc.registration.TryLevel = 0;
  if ( !this->_pDoc._p || this->_pBytes || (v4 = DocStream::SaveDocument(this), v4 >= 0) )
  {
    pstatstg->cbSize.LowPart = this->_cbWritten;
    if ( (grfStatFlag & 1) == 0 )
    {
      p = this->_pDoc._p;
      if ( p )
      {
        v6 = p->_pResolvedURLdoc._p;
        v13 = v6;
        if ( v6 )
        {
          length = v6->_length;
          v8 = length + 1;
          v4 = -2147024362;
          if ( length + 1 < length )
          {
            v8 = -1;
            v9 = -2147024362;
          }
          else
          {
            v9 = 0;
          }
          cb = v8;
          if ( v9 < 0 || ULongLongToUInt(2LL * v8, &cb) < 0 || (v10 = cb, cb > 0x7FFFFFFF) )
          {
            v10 = 0;
            cb = 0;
          }
          else
          {
            v4 = 0;
          }
          if ( v4 >= 0 )
          {
            v11 = (wchar_t *)CoTaskMemAlloc(v10);
            pstatstg->pwcsName = v11;
            if ( v11 )
            {
              v12 = length;
              memcpy(v11, v13->_pwsz, v12 * 2);
              pstatstg->pwcsName[v12] = 0;
            }
            else
            {
              v4 = -2147024882;
            }
          }
        }
      }
    }
  }
  ms_exc.registration.TryLevel = -2;
  return v4;
}

```

## disassembly

```asm
0x100a8ed0  push    14h
0x100a8ed2  push    offset stru_10176650
0x100a8ed7  call    __SEH_prolog4
0x100a8edc  lea     ecx, [ebp+cb]; this
0x100a8edf  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100a8ee4  cmp     [ebp+cb], 0
0x100a8ee8  jnz     short loc_100A8EF4
0x100a8eea  mov     eax, 80004005h
0x100a8eef  jmp     loc_100A9024
0x100a8ef4  xor     edi, edi
0x100a8ef6  mov     ebx, [ebp+pstatstg]
0x100a8ef9  test    ebx, ebx
0x100a8efb  jnz     short loc_100A8F07
0x100a8efd  mov     edi, 80030009h
0x100a8f02  jmp     CleanUp_97
0x100a8f07  push    48h ; 'H'; Size
0x100a8f09  push    0; Val
0x100a8f0b  push    ebx; void *
0x100a8f0c  call    _memset
0x100a8f11  add     esp, 0Ch
0x100a8f14  push    2
0x100a8f16  pop     edx
0x100a8f17  mov     [ebx+4], edx
0x100a8f1a  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100a8f1d  mov     esi, [ebp+this]
0x100a8f20  cmp     dword ptr [esi+10h], 0
0x100a8f24  jz      short loc_100A8F43
0x100a8f26  cmp     dword ptr [esi+1Ch], 0
0x100a8f2a  jnz     short loc_100A8F43
0x100a8f2c  mov     ecx, esi; this
0x100a8f2e  call    ?SaveDocument@DocStream@@AAEJXZ; DocStream::SaveDocument(void)
0x100a8f33  mov     edi, eax
0x100a8f35  mov     [ebp+hr], edi
0x100a8f38  test    edi, edi
0x100a8f3a  js      loc_100A901B
0x100a8f40  push    2
0x100a8f42  pop     edx
0x100a8f43  mov     eax, [esi+18h]
0x100a8f46  mov     [ebx+8], eax
0x100a8f49  test    byte ptr [ebp+grfStatFlag], 1
0x100a8f4d  jnz     loc_100A901B
0x100a8f53  mov     eax, [esi+10h]
0x100a8f56  test    eax, eax
0x100a8f58  jz      loc_100A901B
0x100a8f5e  mov     eax, [eax+8Ch]
0x100a8f64  mov     [ebp+var_24], eax
0x100a8f67  test    eax, eax
0x100a8f69  jz      loc_100A901B
0x100a8f6f  mov     esi, [eax+8]
0x100a8f72  lea     eax, [esi+1]
0x100a8f75  mov     edi, 80070216h
0x100a8f7a  cmp     eax, esi
0x100a8f7c  jb      short loc_100A8F82
0x100a8f7e  xor     ecx, ecx
0x100a8f80  jmp     short loc_100A8F87
0x100a8f82  or      eax, 0FFFFFFFFh
0x100a8f85  mov     ecx, edi
0x100a8f87  mov     [ebp+cb], eax
0x100a8f8a  test    ecx, ecx
0x100a8f8c  js      short loc_100A8FAC
0x100a8f8e  mul     edx
0x100a8f90  push    edx
0x100a8f91  push    eax; ullOperand
0x100a8f92  lea     ecx, [ebp+cb]; puResult
0x100a8f95  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x100a8f9a  test    eax, eax
0x100a8f9c  js      short loc_100A8FAC
0x100a8f9e  mov     eax, [ebp+cb]
0x100a8fa1  cmp     eax, 7FFFFFFFh
0x100a8fa6  ja      short loc_100A8FAC
0x100a8fa8  xor     edi, edi
0x100a8faa  jmp     short loc_100A8FB1
0x100a8fac  xor     eax, eax
0x100a8fae  mov     [ebp+cb], eax
0x100a8fb1  mov     [ebp+hr], edi
0x100a8fb4  test    edi, edi
0x100a8fb6  js      short loc_100A901B
0x100a8fb8  push    eax; cb
0x100a8fb9  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a8fbf  mov     [ebx], eax
0x100a8fc1  test    eax, eax
0x100a8fc3  jnz     short loc_100A8FCC
0x100a8fc5  mov     edi, 8007000Eh
0x100a8fca  jmp     short loc_100A9018
0x100a8fcc  add     esi, esi
0x100a8fce  push    esi; Size
0x100a8fcf  mov     ecx, [ebp+var_24]
0x100a8fd2  push    dword ptr [ecx+0Ch]; Src
0x100a8fd5  push    eax; void *
0x100a8fd6  call    _memcpy
0x100a8fdb  add     esp, 0Ch
0x100a8fde  mov     eax, [ebx]
0x100a8fe0  xor     ecx, ecx
0x100a8fe2  mov     [esi+eax], cx
0x100a8fe6  jmp     short loc_100A901B
0x100a8fe8  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100a8feb  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100a8ff0  retn
0x100a8ff1  mov     esp, [ebp+ms_exc.old_esp]
0x100a8ff4  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100a8ff9  mov     ecx, __tls_index
0x100a8fff  mov     eax, large fs:2Ch
0x100a9005  mov     eax, [eax+ecx*4]
0x100a9008  mov     eax, [eax+4]
0x100a900e  mov     ecx, [eax+8]; e
0x100a9011  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x100a9016  mov     edi, eax
0x100a9018  mov     [ebp+hr], edi
0x100a901b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100a9022  mov     eax, edi
0x100a9024  mov     ecx, [ebp+ms_exc.registration.Next]
0x100a9027  mov     large fs:0, ecx
0x100a902e  pop     ecx
0x100a902f  pop     edi
0x100a9030  pop     esi
0x100a9031  pop     ebx
0x100a9032  leave
0x100a9033  retn    0Ch
```
