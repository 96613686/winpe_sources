# GetDomainRelevantKeyCharacteristics

- ea: `0x1800174f0`
- end: `0x18001756f`
- name: `GetDomainRelevantKeyCharacteristics`
- size: `127`
- prototype: `__int64 __fastcall(wchar_t *String1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008858`

## callees

- `0x18000d094`
- `0x1800174f0`

## string_xrefs

- `0x18001752d`: `login.live.com`

## pseudocode

```c
__int64 __fastcall GetDomainRelevantKeyCharacteristics(wchar_t *String1, int *a2)
{
  unsigned int v4; // ebp
  int v5; // ebx

  if ( a2 )
  {
    v4 = 0;
    if ( String1 )
    {
      if ( wcsicmp(String1, L"login.windows.net") )
      {
        if ( wcsicmp(String1, L"login.live.com") )
        {
          v5 = 0;
          if ( !wcsicmp(String1, L"FIDO_AUTHENTICATOR") )
            v5 = 0x200000;
        }
        else
        {
          v5 = 0x80000;
        }
      }
      else
      {
        v5 = 0x100000;
      }
      *a2 = v5;
    }
    else
    {
      *a2 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return v4;
}

```

## disassembly

```asm
0x1800174f0  push    rbx
0x1800174f2  push    rbp
0x1800174f3  push    rsi
0x1800174f4  push    rdi
0x1800174f5  sub     rsp, 28h
0x1800174f9  mov     rdi, rdx
0x1800174fc  mov     rsi, rcx
0x1800174ff  test    rdx, rdx
0x180017502  jnz     short loc_18001750B
0x180017504  mov     ebp, 80004003h
0x180017509  jmp     short loc_180017564
0x18001750b  xor     ebp, ebp
0x18001750d  test    rsi, rsi
0x180017510  jnz     short loc_180017516
0x180017512  mov     [rdx], ebp
0x180017514  jmp     short loc_180017564
0x180017516  lea     rdx, aLoginWindowsNe; "login.windows.net"
0x18001751d  call    _wcsicmp
0x180017522  test    eax, eax
0x180017524  jnz     short loc_18001752D
0x180017526  mov     ebx, 100000h
0x18001752b  jmp     short loc_180017562
0x18001752d  lea     rdx, aLoginLiveCom; "login.live.com"
0x180017534  mov     rcx, rsi; String1
0x180017537  call    _wcsicmp
0x18001753c  test    eax, eax
0x18001753e  jnz     short loc_180017547
0x180017540  mov     ebx, 80000h
0x180017545  jmp     short loc_180017562
0x180017547  lea     rdx, aFidoAuthentica; "FIDO_AUTHENTICATOR"
0x18001754e  mov     rcx, rsi; String1
0x180017551  xor     ebx, ebx
0x180017553  call    _wcsicmp
0x180017558  test    eax, eax
0x18001755a  mov     ecx, 200000h
0x18001755f  cmovz   ebx, ecx
0x180017562  mov     [rdi], ebx
0x180017564  mov     eax, ebp
0x180017566  add     rsp, 28h
0x18001756a  pop     rdi
0x18001756b  pop     rsi
0x18001756c  pop     rbp
0x18001756d  pop     rbx
0x18001756e  retn
```
