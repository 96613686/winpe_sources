# Bcrypt::Init(void)

- ea: `0x100c426d`
- end: `0x100c42b6`
- name: `?Init@Bcrypt@@AAEJXZ`
- size: `73`
- prototype: `HRESULT __thiscall(Bcrypt *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100c4a09`

## callees

- `0x100c426d`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c4280`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c4280`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c42a1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c42a1`

## pseudocode

```c
HRESULT __thiscall Bcrypt::Init(Bcrypt *this)
{
  HRESULT result; // eax
  NTSTATUS v2; // eax
  int v3; // ecx
  void *handle; // [esp+0h] [ebp-4h] BYREF

  handle = this;
  result = BCryptOpenAlgorithmProvider(&handle, L"SHA256", 0, 0);
  if ( result >= 0 )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&sha2, (signed __int32)handle, 0) )
    {
      v2 = BCryptCloseAlgorithmProvider(handle, 0);
      v3 = 0;
      if ( v2 < 0 )
        return v2;
      return v3;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100c426d  mov     edi, edi
0x100c426f  push    ebp
0x100c4270  mov     ebp, esp
0x100c4272  push    ecx
0x100c4273  push    0; dwFlags
0x100c4275  push    0; pszImplementation
0x100c4277  push    offset aSha256; "SHA256"
0x100c427c  lea     eax, [ebp+handle]
0x100c427f  push    eax; phAlgorithm
0x100c4280  call    ds:__imp__BCryptOpenAlgorithmProvider@16; BCryptOpenAlgorithmProvider(x,x,x,x)
0x100c4286  test    eax, eax
0x100c4288  js      short locret_100C42B4
0x100c428a  mov     ecx, [ebp+handle]
0x100c428d  mov     edx, offset sha2
0x100c4292  xor     eax, eax
0x100c4294  lock cmpxchg [edx], ecx
0x100c4298  test    eax, eax
0x100c429a  jz      short loc_100C42B2
0x100c429c  push    0; dwFlags
0x100c429e  push    [ebp+handle]; hAlgorithm
0x100c42a1  call    ds:__imp__BCryptCloseAlgorithmProvider@8; BCryptCloseAlgorithmProvider(x,x)
0x100c42a7  xor     ecx, ecx
0x100c42a9  test    eax, eax
0x100c42ab  cmovs   ecx, eax
0x100c42ae  mov     eax, ecx
0x100c42b0  leave
0x100c42b1  retn
0x100c42b2  xor     eax, eax
0x100c42b4  leave
0x100c42b5  retn
```
