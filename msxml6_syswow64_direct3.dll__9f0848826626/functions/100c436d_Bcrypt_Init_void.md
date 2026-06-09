# Bcrypt::Init(void)

- ea: `0x100c436d`
- end: `0x100c43b6`
- name: `?Init@Bcrypt@@AAEJXZ`
- size: `73`
- prototype: `HRESULT __thiscall(Bcrypt *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x100c4b09`

## callees

- `0x100c436d`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c4380`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x100c4380`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c43a1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x100c43a1`

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
0x100c436d  mov     edi, edi
0x100c436f  push    ebp
0x100c4370  mov     ebp, esp
0x100c4372  push    ecx
0x100c4373  push    0; dwFlags
0x100c4375  push    0; pszImplementation
0x100c4377  push    offset aSha256; "SHA256"
0x100c437c  lea     eax, [ebp+handle]
0x100c437f  push    eax; phAlgorithm
0x100c4380  call    ds:__imp__BCryptOpenAlgorithmProvider@16; BCryptOpenAlgorithmProvider(x,x,x,x)
0x100c4386  test    eax, eax
0x100c4388  js      short locret_100C43B4
0x100c438a  mov     ecx, [ebp+handle]
0x100c438d  mov     edx, offset sha2
0x100c4392  xor     eax, eax
0x100c4394  lock cmpxchg [edx], ecx
0x100c4398  test    eax, eax
0x100c439a  jz      short loc_100C43B2
0x100c439c  push    0; dwFlags
0x100c439e  push    [ebp+handle]; hAlgorithm
0x100c43a1  call    ds:__imp__BCryptCloseAlgorithmProvider@8; BCryptCloseAlgorithmProvider(x,x)
0x100c43a7  xor     ecx, ecx
0x100c43a9  test    eax, eax
0x100c43ab  cmovs   ecx, eax
0x100c43ae  mov     eax, ecx
0x100c43b0  leave
0x100c43b1  retn
0x100c43b2  xor     eax, eax
0x100c43b4  leave
0x100c43b5  retn
```
