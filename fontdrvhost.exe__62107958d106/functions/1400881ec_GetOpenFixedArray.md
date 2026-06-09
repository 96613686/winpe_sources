# GetOpenFixedArray

- ea: `0x1400881ec`
- end: `0x140088246`
- name: `GetOpenFixedArray`
- size: `90`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140088124`
- `0x140088770`
- `0x1400889e0`
- `0x140088bc0`
- `0x140088d10`
- `0x140089540`

## callees

- `0x140062794`
- `0x140074984`
- `0x1400881ec`
- `0x1400886f0`

## pseudocode

```c
__int64 __fastcall GetOpenFixedArray(
        _DWORD *a1,
        struct _POLICY_ELEMENT *a2,
        PGENERIC_XML_TOKEN *a3,
        PINFORMATIONCARD_CRYPTO_HANDLE *a4)
{
  unsigned int v4; // esi
  _DWORD *v5; // rdi
  unsigned int v6; // ebx
  HRESULT Token; // eax

  v4 = (unsigned int)a2;
  v5 = a1;
  v6 = 0;
  while ( 1 )
  {
    Token = GetToken((DWORD)a1, a2, a3, a4);
    if ( Token != 3 )
      break;
    ++v6;
    *v5 = MakeFixed();
    if ( v6 >= v4 )
    {
      Token = GetToken((DWORD)a1, a2, a3, a4);
      break;
    }
    ++v5;
  }
  if ( Token != 5 )
  {
    ParseError(4294967292LL);
    JUMPOUT(0x140088245LL);
  }
  return v6;
}

```

## disassembly

```asm
0x1400881ec  mov     [rsp+arg_0], rbx
0x1400881f1  mov     [rsp+arg_8], rsi
0x1400881f6  push    rdi
0x1400881f7  sub     rsp, 20h
0x1400881fb  mov     esi, edx
0x1400881fd  mov     rdi, rcx
0x140088200  xor     ebx, ebx
0x140088202  call    GetToken
0x140088207  cmp     eax, 3
0x14008820a  jnz     short loc_140088224
0x14008820c  call    MakeFixed
0x140088211  inc     ebx
0x140088213  mov     [rdi], eax
0x140088215  cmp     ebx, esi
0x140088217  jnb     short loc_14008821F
0x140088219  add     rdi, 4
0x14008821d  jmp     short loc_140088202
0x14008821f  call    GetToken
0x140088224  cmp     eax, 5
0x140088227  jnz     short loc_14008823B
0x140088229  mov     rsi, [rsp+28h+arg_8]
0x14008822e  mov     eax, ebx
0x140088230  mov     rbx, [rsp+28h+arg_0]
0x140088235  add     rsp, 20h
0x140088239  pop     rdi
0x14008823a  retn
0x14008823b  mov     ecx, 0FFFFFFFCh
0x140088240  call    ParseError
```
