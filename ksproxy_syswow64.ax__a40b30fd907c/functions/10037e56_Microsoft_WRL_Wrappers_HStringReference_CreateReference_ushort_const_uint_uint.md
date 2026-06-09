# Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)

- ea: `0x10037e56`
- end: `0x10037e86`
- name: `?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AAEXPBGII@Z`
- size: `48`
- prototype: `void __thiscall(Microsoft::WRL::Wrappers::HStringReference *__hidden this, PCWSTR sourceString, unsigned int, UINT32 length)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10037be0`

## callees

- `0x10037e42`
- `0x10037e56`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10037e71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x10037e71`

## pseudocode

```c
void __thiscall Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        Microsoft::WRL::Wrappers::HStringReference *this,
        PCWSTR sourceString,
        unsigned int a3,
        UINT32 length)
{
  UINT32 v4; // edx
  void *StringReference; // eax

  v4 = length;
  if ( length >= a3 )
    v4 = a3 - 1;
  StringReference = (void *)WindowsCreateStringReference(sourceString, v4, &this->header_, &this->hstr_);
  if ( (int)StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException(StringReference);
    JUMPOUT(0x10037E86);
  }
}

```

## disassembly

```asm
0x10037e56  mov     edi, edi
0x10037e58  push    ebp; this
0x10037e59  mov     ebp, esp
0x10037e5b  mov     edx, [ebp+length]
0x10037e5e  mov     eax, [ebp+arg_4]
0x10037e61  cmp     edx, eax
0x10037e63  jb      short loc_10037E68
0x10037e65  lea     edx, [eax-1]
0x10037e68  lea     eax, [ecx+14h]
0x10037e6b  push    eax; string
0x10037e6c  push    ecx; hstringHeader
0x10037e6d  push    edx; length
0x10037e6e  push    [ebp+sourceString]; sourceString
0x10037e71  call    ds:__imp__WindowsCreateStringReference@16; WindowsCreateStringReference(x,x,x,x)
0x10037e77  test    eax, eax
0x10037e79  js      short loc_10037E7F
0x10037e7b  pop     ebp
0x10037e7c  retn    0Ch
0x10037e7f  mov     ecx, eax
0x10037e81  call    ?RaiseException@Details@WRL@Microsoft@@YGXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
