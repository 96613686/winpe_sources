# SHA2::Hash(void const *,ulong)

- ea: `0x100c42ab`
- end: `0x100c4367`
- name: `?Hash@SHA2@@QBE?AUDigest@1@PBXK@Z`
- size: `188`
- prototype: `SHA2::Digest *__thiscall(SHA2 *this, SHA2::Digest *result, const void *input, unsigned int input)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x100c4b09`

## callees

- `0x1003f4b8`
- `0x10040d5e`
- `0x10064c51`
- `0x1006bff0`
- `0x100c42ab`
- `0x100c69d8`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x100c4355`
- `bcrypt!BCryptDestroyHash` at `0x100c4355`
- `bcrypt!BCryptHashData` at `0x100c4310`
- `bcrypt!BCryptHashData` at `0x100c4310`
- `bcrypt!BCryptFinishHash` at `0x100c4322`
- `bcrypt!BCryptFinishHash` at `0x100c4322`
- `bcrypt!BCryptCreateHash` at `0x100c42f5`
- `bcrypt!BCryptCreateHash` at `0x100c42f5`

## pseudocode

```c
void __thiscall SHA2::Hash(SHA2 *this, SHA2::Digest *result, unsigned __int8 *input, unsigned int a4)
{
  SIZE_T PropertyLength; // ebx
  unsigned __int8 *v5; // edi
  NTSTATUS v6; // eax
  void *cryptHash; // [esp+14h] [ebp-1Ch] BYREF
  CPPEH_RECORD ms_exc; // [esp+18h] [ebp-18h]

  cryptHash = 0;
  memset(result, 0, sizeof(SHA2::Digest));
  PropertyLength = Bcrypt::getPropertyLength(0, 0);
  v5 = (unsigned __int8 *)_MemAlloc(PropertyLength, 4);
  ms_exc.registration.TryLevel = 0;
  v6 = BCryptCreateHash(sha2.m_bcrypt.m_handle, &cryptHash, v5, PropertyLength, 0, 0, 0);
  if ( v6 >= 0 )
    goto LABEL_3;
  while ( 1 )
  {
    Exception::throwHR(v6);
LABEL_3:
    v6 = BCryptHashData(cryptHash, input, 0x10u, 0);
    if ( v6 >= 0 )
    {
      v6 = BCryptFinishHash(cryptHash, (PUCHAR)result, 0x20u, 0);
      if ( v6 >= 0 )
      {
        ms_exc.registration.TryLevel = -2;
        v6 = BCryptDestroyHash(cryptHash);
        if ( v6 >= 0 )
          break;
      }
    }
  }
  MemFree(v5);
}

```

## disassembly

```asm
0x100c42ab  push    10h
0x100c42ad  push    offset stru_10178050
0x100c42b2  call    __SEH_prolog4
0x100c42b7  mov     [ebp+cryptHash], 0
0x100c42be  push    8
0x100c42c0  pop     ecx; this
0x100c42c1  xor     eax, eax
0x100c42c3  mov     esi, [ebp+digest]
0x100c42c6  mov     edi, esi
0x100c42c8  rep stosd
0x100c42ca  push    ecx; propertyName
0x100c42cb  call    ?getPropertyLength@Bcrypt@@QBEKPBG@Z; Bcrypt::getPropertyLength(ushort const *)
0x100c42d0  mov     ebx, eax
0x100c42d2  push    4
0x100c42d4  pop     edx; dwFlags
0x100c42d5  mov     ecx, ebx; cb
0x100c42d7  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x100c42dc  mov     edi, eax
0x100c42de  mov     [ebp+buffer], edi
0x100c42e1  xor     eax, eax
0x100c42e3  mov     [ebp+ms_exc.registration.TryLevel], eax
0x100c42e6  push    eax; dwFlags
0x100c42e7  push    eax; cbSecret
0x100c42e8  push    eax; pbSecret
0x100c42e9  push    ebx; cbHashObject
0x100c42ea  push    edi; pbHashObject
0x100c42eb  lea     eax, [ebp+cryptHash]
0x100c42ee  push    eax; phHash
0x100c42ef  push    sha2.m_bcrypt.m_handle; hAlgorithm
0x100c42f5  call    ds:__imp__BCryptCreateHash@28; BCryptCreateHash(x,x,x,x,x,x,x)
0x100c42fb  test    eax, eax
0x100c42fd  jns     short loc_100C4306
0x100c42ff  mov     ecx, eax; hr
0x100c4301  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100c4306  push    0; dwFlags
0x100c4308  push    10h; cbInput
0x100c430a  push    [ebp+input]; pbInput
0x100c430d  push    [ebp+cryptHash]; hHash
0x100c4310  call    ds:__imp__BCryptHashData@16; BCryptHashData(x,x,x,x)
0x100c4316  test    eax, eax
0x100c4318  js      short loc_100C42FF
0x100c431a  push    0; dwFlags
0x100c431c  push    20h ; ' '; cbOutput
0x100c431e  push    esi; pbOutput
0x100c431f  push    [ebp+cryptHash]; hHash
0x100c4322  call    ds:__imp__BCryptFinishHash@16; BCryptFinishHash(x,x,x,x)
0x100c4328  test    eax, eax
0x100c432a  js      short loc_100C42FF
0x100c432c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100c4333  call    $LN7_45
0x100c4338  mov     eax, esi
0x100c433a  mov     ecx, [ebp+ms_exc.registration.Next]
0x100c433d  mov     large fs:0, ecx
0x100c4344  pop     ecx
0x100c4345  pop     edi
0x100c4346  pop     esi
0x100c4347  pop     ebx
0x100c4348  leave
0x100c4349  retn    0Ch
0x100c434c  mov     esi, [ebp+digest]
0x100c434f  mov     edi, [ebp+buffer]
0x100c4352  push    [ebp+cryptHash]; hHash
0x100c4355  call    ds:__imp__BCryptDestroyHash@4; BCryptDestroyHash(x)
0x100c435b  test    eax, eax
0x100c435d  js      short loc_100C42FF
0x100c435f  mov     ecx, edi; pv
0x100c4361  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x100c4366  retn
```
