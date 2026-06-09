# SHA2::Hash(void const *,ulong)

- ea: `0x100c41ab`
- end: `0x100c4267`
- name: `?Hash@SHA2@@QBE?AUDigest@1@PBXK@Z`
- size: `188`
- prototype: `SHA2::Digest *__thiscall(SHA2 *this, SHA2::Digest *result, const void *input, unsigned int input)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x100c4a09`

## callees

- `0x1003f548`
- `0x10040dee`
- `0x10064cf1`
- `0x1006c080`
- `0x100c41ab`
- `0x100c68c8`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x100c4255`
- `bcrypt!BCryptDestroyHash` at `0x100c4255`
- `bcrypt!BCryptHashData` at `0x100c4210`
- `bcrypt!BCryptHashData` at `0x100c4210`
- `bcrypt!BCryptFinishHash` at `0x100c4222`
- `bcrypt!BCryptFinishHash` at `0x100c4222`
- `bcrypt!BCryptCreateHash` at `0x100c41f5`
- `bcrypt!BCryptCreateHash` at `0x100c41f5`

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
0x100c41ab  push    10h
0x100c41ad  push    offset stru_10177F60
0x100c41b2  call    __SEH_prolog4
0x100c41b7  mov     [ebp+cryptHash], 0
0x100c41be  push    8
0x100c41c0  pop     ecx; this
0x100c41c1  xor     eax, eax
0x100c41c3  mov     esi, [ebp+digest]
0x100c41c6  mov     edi, esi
0x100c41c8  rep stosd
0x100c41ca  push    ecx; propertyName
0x100c41cb  call    ?getPropertyLength@Bcrypt@@QBEKPBG@Z; Bcrypt::getPropertyLength(ushort const *)
0x100c41d0  mov     ebx, eax
0x100c41d2  push    4
0x100c41d4  pop     edx; dwFlags
0x100c41d5  mov     ecx, ebx; cb
0x100c41d7  call    ?_MemAlloc@@YGPAXIK@Z; _MemAlloc(uint,ulong)
0x100c41dc  mov     edi, eax
0x100c41de  mov     [ebp+buffer], edi
0x100c41e1  xor     eax, eax
0x100c41e3  mov     [ebp+ms_exc.registration.TryLevel], eax
0x100c41e6  push    eax; dwFlags
0x100c41e7  push    eax; cbSecret
0x100c41e8  push    eax; pbSecret
0x100c41e9  push    ebx; cbHashObject
0x100c41ea  push    edi; pbHashObject
0x100c41eb  lea     eax, [ebp+cryptHash]
0x100c41ee  push    eax; phHash
0x100c41ef  push    sha2.m_bcrypt.m_handle; hAlgorithm
0x100c41f5  call    ds:__imp__BCryptCreateHash@28; BCryptCreateHash(x,x,x,x,x,x,x)
0x100c41fb  test    eax, eax
0x100c41fd  jns     short loc_100C4206
0x100c41ff  mov     ecx, eax; hr
0x100c4201  call    ?throwHR@Exception@@SGXJ@Z; Exception::throwHR(long)
0x100c4206  push    0; dwFlags
0x100c4208  push    10h; cbInput
0x100c420a  push    [ebp+input]; pbInput
0x100c420d  push    [ebp+cryptHash]; hHash
0x100c4210  call    ds:__imp__BCryptHashData@16; BCryptHashData(x,x,x,x)
0x100c4216  test    eax, eax
0x100c4218  js      short loc_100C41FF
0x100c421a  push    0; dwFlags
0x100c421c  push    20h ; ' '; cbOutput
0x100c421e  push    esi; pbOutput
0x100c421f  push    [ebp+cryptHash]; hHash
0x100c4222  call    ds:__imp__BCryptFinishHash@16; BCryptFinishHash(x,x,x,x)
0x100c4228  test    eax, eax
0x100c422a  js      short loc_100C41FF
0x100c422c  mov     [ebp+ms_exc.registration.TryLevel], 0FFFFFFFEh
0x100c4233  call    $LN7_45
0x100c4238  mov     eax, esi
0x100c423a  mov     ecx, [ebp+ms_exc.registration.Next]
0x100c423d  mov     large fs:0, ecx
0x100c4244  pop     ecx
0x100c4245  pop     edi
0x100c4246  pop     esi
0x100c4247  pop     ebx
0x100c4248  leave
0x100c4249  retn    0Ch
0x100c424c  mov     esi, [ebp+digest]
0x100c424f  mov     edi, [ebp+buffer]
0x100c4252  push    [ebp+cryptHash]; hHash
0x100c4255  call    ds:__imp__BCryptDestroyHash@4; BCryptDestroyHash(x)
0x100c425b  test    eax, eax
0x100c425d  js      short loc_100C41FF
0x100c425f  mov     ecx, edi; pv
0x100c4261  call    ?MemFree@@YGXPAX@Z; MemFree(void *)
0x100c4266  retn
```
