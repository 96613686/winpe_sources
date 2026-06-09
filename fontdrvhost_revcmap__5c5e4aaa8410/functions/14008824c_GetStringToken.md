# GetStringToken

- ea: `0x14008824c`
- end: `0x140088271`
- name: `GetStringToken`
- size: `37`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400867e0`
- `0x140087494`
- `0x14008a470`
- `0x14008a4b0`

## callees

- `0x140062794`
- `0x140074984`
- `0x14008824c`

## pseudocode

```c
STRSAFE_LPCSTR __fastcall GetStringToken(
        DWORD a1,
        struct _POLICY_ELEMENT *a2,
        PGENERIC_XML_TOKEN *a3,
        PINFORMATIONCARD_CRYPTO_HANDLE *a4)
{
  if ( (unsigned int)GetToken(a1, a2, a3, a4) > 1 )
  {
    ParseError(4294967292LL);
    __debugbreak();
  }
  return token;
}

```

## disassembly

```asm
0x14008824c  sub     rsp, 28h
0x140088250  call    GetToken
0x140088255  cmp     eax, 1
0x140088258  jbe     short loc_140088265
0x14008825a  mov     ecx, 0FFFFFFFCh
0x14008825f  call    ParseError
0x140088264  int     3; Trap to Debugger
0x140088265  mov     rax, cs:token
0x14008826c  add     rsp, 28h
0x140088270  retn
```
