# GetCipherSuiteDetailsFromRegistry

- ea: `0x18001d72c`
- end: `0x18001d8e0`
- name: `GetCipherSuiteDetailsFromRegistry`
- size: `436`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d8e8`

## callees

- `0x180012a7c`
- `0x18001d72c`
- `0x1800244f0`

## string_xrefs

- `0x18001d75a`: `Protocols`

## pseudocode

```c
__int64 __fastcall GetCipherSuiteDetailsFromRegistry(HANDLE KeyHandle, unsigned __int16 *a2)
{
  __int64 result; // rax

  result = GetSslDWordFromRegistry(KeyHandle);
  if ( (int)result >= 0 )
  {
    result = GetSslDWordFromRegistry(KeyHandle);
    if ( (int)result >= 0 )
    {
      result = GetSslDWordFromRegistry(KeyHandle);
      if ( (int)result >= 0 )
      {
        result = GetSslStringFromRegistry(KeyHandle, L"Hash", a2 + 70);
        if ( (int)result >= 0 )
        {
          result = GetSslStringFromRegistry(KeyHandle, L"Signature", a2 + 334);
          if ( (int)result >= 0 )
          {
            result = GetSslStringFromRegistry(KeyHandle, L"KeyExchange", a2 + 266);
            if ( (int)result >= 0 )
            {
              result = GetSslStringFromRegistry(KeyHandle, L"Cipher", a2 + 134);
              if ( (int)result >= 0 )
              {
                result = GetSslDWordFromRegistry(KeyHandle);
                if ( (int)result >= 0 )
                {
                  result = GetSslDWordFromRegistry(KeyHandle);
                  if ( (int)result >= 0 )
                  {
                    result = GetSslStringFromRegistry(KeyHandle, L"CipherMode", a2 + 202);
                    if ( (int)result >= 0 )
                    {
                      result = GetSslStringFromRegistry(KeyHandle, L"KDF", a2 + 398);
                      if ( (int)result >= 0 )
                      {
                        result = GetSslDWordFromRegistry(KeyHandle);
                        if ( (int)result >= 0 )
                        {
                          result = GetSslDWordFromRegistry(KeyHandle);
                          if ( (int)result >= 0 )
                          {
                            result = GetSslStringFromRegistry(KeyHandle, L"PRFHash", a2 + 462);
                            if ( (int)result >= 0 )
                              return GetSslDWordFromRegistry(KeyHandle);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001d72c  mov     [rsp+arg_0], rbx
0x18001d731  push    rdi
0x18001d732  sub     rsp, 20h
0x18001d736  mov     rbx, rdx
0x18001d739  mov     r8, rdx
0x18001d73c  lea     rdx, aVersion; "Version"
0x18001d743  mov     rdi, rcx
0x18001d746  call    GetSslDWordFromRegistry
0x18001d74b  test    eax, eax
0x18001d74d  js      loc_18001D8D5
0x18001d753  lea     r8, [rbx+4]
0x18001d757  mov     rcx, rdi; KeyHandle
0x18001d75a  lea     rdx, aProtocols; "Protocols"
0x18001d761  call    GetSslDWordFromRegistry
0x18001d766  test    eax, eax
0x18001d768  js      loc_18001D8D5
0x18001d76e  lea     r8, [rbx+8]
0x18001d772  mov     rcx, rdi; KeyHandle
0x18001d775  lea     rdx, aCiphersuite; "CipherSuite"
0x18001d77c  call    GetSslDWordFromRegistry
0x18001d781  test    eax, eax
0x18001d783  js      loc_18001D8D5
0x18001d789  lea     r8, [rbx+8Ch]; unsigned __int16 *
0x18001d790  mov     rcx, rdi; KeyHandle
0x18001d793  lea     rdx, SourceString; "Hash"
0x18001d79a  call    GetSslStringFromRegistry
0x18001d79f  test    eax, eax
0x18001d7a1  js      loc_18001D8D5
0x18001d7a7  lea     r8, [rbx+29Ch]; unsigned __int16 *
0x18001d7ae  mov     rcx, rdi; KeyHandle
0x18001d7b1  lea     rdx, aSignature; "Signature"
0x18001d7b8  call    GetSslStringFromRegistry
0x18001d7bd  test    eax, eax
0x18001d7bf  js      loc_18001D8D5
0x18001d7c5  lea     r8, [rbx+214h]; unsigned __int16 *
0x18001d7cc  mov     rcx, rdi; KeyHandle
0x18001d7cf  lea     rdx, aKeyexchange; "KeyExchange"
0x18001d7d6  call    GetSslStringFromRegistry
0x18001d7db  test    eax, eax
0x18001d7dd  js      loc_18001D8D5
0x18001d7e3  lea     r8, [rbx+10Ch]; unsigned __int16 *
0x18001d7ea  mov     rcx, rdi; KeyHandle
0x18001d7ed  lea     rdx, aCipher; "Cipher"
0x18001d7f4  call    GetSslStringFromRegistry
0x18001d7f9  test    eax, eax
0x18001d7fb  js      loc_18001D8D5
0x18001d801  lea     r8, [rbx+18Ch]
0x18001d808  mov     rcx, rdi; KeyHandle
0x18001d80b  lea     rdx, aCipherbits; "CipherBits"
0x18001d812  call    GetSslDWordFromRegistry
0x18001d817  test    eax, eax
0x18001d819  js      loc_18001D8D5
0x18001d81f  lea     r8, [rbx+190h]
0x18001d826  mov     rcx, rdi; KeyHandle
0x18001d829  lea     rdx, aCipherbytes; "CipherBytes"
0x18001d830  call    GetSslDWordFromRegistry
0x18001d835  test    eax, eax
0x18001d837  js      loc_18001D8D5
0x18001d83d  lea     r8, [rbx+194h]; unsigned __int16 *
0x18001d844  mov     rcx, rdi; KeyHandle
0x18001d847  lea     rdx, aCiphermode; "CipherMode"
0x18001d84e  call    GetSslStringFromRegistry
0x18001d853  test    eax, eax
0x18001d855  js      short loc_18001D8D5
0x18001d857  lea     r8, [rbx+31Ch]; unsigned __int16 *
0x18001d85e  mov     rcx, rdi; KeyHandle
0x18001d861  lea     rdx, aKdf; "KDF"
0x18001d868  call    GetSslStringFromRegistry
0x18001d86d  test    eax, eax
0x18001d86f  js      short loc_18001D8D5
0x18001d871  lea     r8, [rbx+294h]
0x18001d878  mov     rcx, rdi; KeyHandle
0x18001d87b  lea     rdx, aKeyexchangemin; "KeyExchangeMinLength"
0x18001d882  call    GetSslDWordFromRegistry
0x18001d887  test    eax, eax
0x18001d889  js      short loc_18001D8D5
0x18001d88b  lea     r8, [rbx+298h]
0x18001d892  mov     rcx, rdi; KeyHandle
0x18001d895  lea     rdx, aKeyexchangemax; "KeyExchangeMaxLength"
0x18001d89c  call    GetSslDWordFromRegistry
0x18001d8a1  test    eax, eax
0x18001d8a3  js      short loc_18001D8D5
0x18001d8a5  lea     r8, [rbx+39Ch]; unsigned __int16 *
0x18001d8ac  mov     rcx, rdi; KeyHandle
0x18001d8af  lea     rdx, aPrfhash; "PRFHash"
0x18001d8b6  call    GetSslStringFromRegistry
0x18001d8bb  test    eax, eax
0x18001d8bd  js      short loc_18001D8D5
0x18001d8bf  lea     r8, [rbx+41Ch]
0x18001d8c6  mov     rcx, rdi; KeyHandle
0x18001d8c9  lea     rdx, aPaddingflags; "PaddingFlags"
0x18001d8d0  call    GetSslDWordFromRegistry
0x18001d8d5  mov     rbx, [rsp+28h+arg_0]
0x18001d8da  add     rsp, 20h
0x18001d8de  pop     rdi
0x18001d8df  retn
```
