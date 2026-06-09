# DocStream::Stat(tagSTATSTG *,ulong)

- ea: `0x100a8fe0`
- end: `0x100a9146`
- name: `?Stat@DocStream@@UAGJPAUtagSTATSTG@@K@Z`
- size: `358`
- prototype: `HRESULT __stdcall(DocStream *this, tagSTATSTG *pstatstg, unsigned int grfStatFlag)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x100410fe`
- `0x100505bc`
- `0x1006bff0`
- `0x1006c2c4`
- `0x10076076`
- `0x100779f5`
- `0x10077a4b`
- `0x100a8ed3`
- `0x100a8fe0`
- `0x101712a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a90c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x100a90c9`

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
0x100a8fe0  push    14h
0x100a8fe2  push    offset stru_10176740
0x100a8fe7  call    __SEH_prolog4
0x100a8fec  lea     ecx, [ebp+cb]; this
0x100a8fef  call    ??0EnsureTls@@QAE@XZ; EnsureTls::EnsureTls(void)
0x100a8ff4  cmp     [ebp+cb], 0
0x100a8ff8  jnz     short loc_100A9004
0x100a8ffa  mov     eax, 80004005h
0x100a8fff  jmp     loc_100A9134
0x100a9004  xor     edi, edi
0x100a9006  mov     ebx, [ebp+pstatstg]
0x100a9009  test    ebx, ebx
0x100a900b  jnz     short loc_100A9017
0x100a900d  mov     edi, 80030009h
0x100a9012  jmp     CleanUp_97
0x100a9017  push    48h ; 'H'; Size
0x100a9019  push    0; Val
0x100a901b  push    ebx; void *
0x100a901c  call    _memset
0x100a9021  add     esp, 0Ch
0x100a9024  push    2
0x100a9026  pop     edx
0x100a9027  mov     [ebx+4], edx
0x100a902a  mov     [ebp+ms_exc.registration.TryLevel], edi
0x100a902d  mov     esi, [ebp+this]
0x100a9030  cmp     dword ptr [esi+10h], 0
0x100a9034  jz      short loc_100A9053
0x100a9036  cmp     dword ptr [esi+1Ch], 0
0x100a903a  jnz     short loc_100A9053
0x100a903c  mov     ecx, esi; this
0x100a903e  call    ?SaveDocument@DocStream@@AAEJXZ; DocStream::SaveDocument(void)
0x100a9043  mov     edi, eax
0x100a9045  mov     [ebp+hr], edi
0x100a9048  test    edi, edi
0x100a904a  js      loc_100A912B
0x100a9050  push    2
0x100a9052  pop     edx
0x100a9053  mov     eax, [esi+18h]
0x100a9056  mov     [ebx+8], eax
0x100a9059  test    byte ptr [ebp+grfStatFlag], 1
0x100a905d  jnz     loc_100A912B
0x100a9063  mov     eax, [esi+10h]
0x100a9066  test    eax, eax
0x100a9068  jz      loc_100A912B
0x100a906e  mov     eax, [eax+8Ch]
0x100a9074  mov     [ebp+var_24], eax
0x100a9077  test    eax, eax
0x100a9079  jz      loc_100A912B
0x100a907f  mov     esi, [eax+8]
0x100a9082  lea     eax, [esi+1]
0x100a9085  mov     edi, 80070216h
0x100a908a  cmp     eax, esi
0x100a908c  jb      short loc_100A9092
0x100a908e  xor     ecx, ecx
0x100a9090  jmp     short loc_100A9097
0x100a9092  or      eax, 0FFFFFFFFh
0x100a9095  mov     ecx, edi
0x100a9097  mov     [ebp+cb], eax
0x100a909a  test    ecx, ecx
0x100a909c  js      short loc_100A90BC
0x100a909e  mul     edx
0x100a90a0  push    edx
0x100a90a1  push    eax; ullOperand
0x100a90a2  lea     ecx, [ebp+cb]; puResult
0x100a90a5  call    ?ULongLongToUInt@@YGJ_KPAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x100a90aa  test    eax, eax
0x100a90ac  js      short loc_100A90BC
0x100a90ae  mov     eax, [ebp+cb]
0x100a90b1  cmp     eax, 7FFFFFFFh
0x100a90b6  ja      short loc_100A90BC
0x100a90b8  xor     edi, edi
0x100a90ba  jmp     short loc_100A90C1
0x100a90bc  xor     eax, eax
0x100a90be  mov     [ebp+cb], eax
0x100a90c1  mov     [ebp+hr], edi
0x100a90c4  test    edi, edi
0x100a90c6  js      short loc_100A912B
0x100a90c8  push    eax; cb
0x100a90c9  call    ds:__imp__CoTaskMemAlloc@4; CoTaskMemAlloc(x)
0x100a90cf  mov     [ebx], eax
0x100a90d1  test    eax, eax
0x100a90d3  jnz     short loc_100A90DC
0x100a90d5  mov     edi, 8007000Eh
0x100a90da  jmp     short loc_100A9128
0x100a90dc  add     esi, esi
0x100a90de  push    esi; Size
0x100a90df  mov     ecx, [ebp+var_24]
0x100a90e2  push    dword ptr [ecx+0Ch]; Src
0x100a90e5  push    eax; void *
0x100a90e6  call    _memcpy
0x100a90eb  add     esp, 0Ch
0x100a90ee  mov     eax, [ebx]
0x100a90f0  xor     ecx, ecx
0x100a90f2  mov     [esi+eax], cx
0x100a90f6  jmp     short loc_100A912B
0x100a90f8  mov     ecx, [ebp+ms_exc.exc_ptr]; ep
0x100a90fb  call    ?fillException@Exception@@SGHPAU_EXCEPTION_POINTERS@@@Z; Exception::fillException(_EXCEPTION_POINTERS *)
0x100a9100  retn
0x100a9101  mov     esp, [ebp+ms_exc.old_esp]
0x100a9104  call    ?exceptionCatch@Exception@@SGXXZ; Exception::exceptionCatch(void)
0x100a9109  mov     ecx, __tls_index
0x100a910f  mov     eax, large fs:2Ch
0x100a9115  mov     eax, [eax+ecx*4]
0x100a9118  mov     eax, [eax+4]
0x100a911e  mov     ecx, [eax+8]; e
0x100a9121  call    ?setErrorInfoAndGetHR@_dispatchImpl@@SGJPAVException@@@Z; _dispatchImpl::setErrorInfoAndGetHR(Exception *)
0x100a9126  mov     edi, eax
0x100a9128  mov     [ebp+hr], edi
0x100a912b  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100a9132  mov     eax, edi
0x100a9134  mov     ecx, [ebp+ms_exc.registration.Next]
0x100a9137  mov     large fs:0, ecx
0x100a913e  pop     ecx
0x100a913f  pop     edi
0x100a9140  pop     esi
0x100a9141  pop     ebx
0x100a9142  leave
0x100a9143  retn    0Ch
```
