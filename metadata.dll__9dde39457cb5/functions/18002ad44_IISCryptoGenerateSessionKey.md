# IISCryptoGenerateSessionKey

- ea: `0x18002ad44`
- end: `0x18002adf7`
- name: `IISCryptoGenerateSessionKey`
- size: `179`
- prototype: `__int64 __fastcall(HCRYPTKEY *phKey, HCRYPTPROV hProv)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002914c`
- `0x180029220`

## callees

- `0x18002937c`
- `0x18002ad44`

## import_xrefs

- `ADVAPI32!CryptGenKey` at `0x18002ad94`
- `ADVAPI32!CryptGenKey` at `0x18002ad94`
- `IisRTL!PuDbgPrint` at `0x18002addd`
- `IisRTL!PuDbgPrint` at `0x18002addd`

## string_xrefs

- `0x18002adcb`: `IISCryptoGenerateSessionKey.CryptGenKey (advapi32.dll) failed err=0x%x.\n`

## pseudocode

```c
__int64 __fastcall IISCryptoGenerateSessionKey(HCRYPTKEY *phKey, HCRYPTPROV hProv, int a3)
{
  unsigned int v5; // ebx
  int LastError; // eax

  if ( dword_180048964 )
  {
    v5 = 0;
    if ( !CryptGenKey(hProv, a3 != 0 ? 26115 : 26625, 1u, phKey) )
    {
      LastError = IcpGetLastError();
      v5 = LastError;
      if ( LastError < 0 )
      {
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "inetsrv\\iis\\mb\\crypto\\key.cxx",
            329,
            "IISCryptoGenerateSessionKey",
            "IISCryptoGenerateSessionKey.CryptGenKey (advapi32.dll) failed err=0x%x.\n",
            LastError);
        *phKey = 0;
      }
    }
    return v5;
  }
  else if ( hProv == 1984918096 )
  {
    *phKey = 1800627539;
    return 0;
  }
  else
  {
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18002ad44  mov     [rsp+arg_0], rbx
0x18002ad49  push    rdi
0x18002ad4a  sub     rsp, 30h
0x18002ad4e  cmp     cs:dword_180048964, 0
0x18002ad55  mov     rax, rdx
0x18002ad58  mov     rdi, rcx
0x18002ad5b  jnz     short loc_18002AD77
0x18002ad5d  cmp     rax, 764F7250h
0x18002ad63  jnz     short loc_18002AD70
0x18002ad65  mov     qword ptr [rcx], 6B536553h
0x18002ad6c  xor     eax, eax
0x18002ad6e  jmp     short loc_18002ADEC
0x18002ad70  mov     eax, 80070057h
0x18002ad75  jmp     short loc_18002ADEC
0x18002ad77  xor     ebx, ebx
0x18002ad79  mov     r9, rdi; phKey
0x18002ad7c  neg     r8d
0x18002ad7f  mov     rcx, rax; hProv
0x18002ad82  sbb     edx, edx
0x18002ad84  and     edx, 0FFFFFE02h
0x18002ad8a  lea     r8d, [rbx+1]; dwFlags
0x18002ad8e  add     edx, 6801h; Algid
0x18002ad94  call    cs:__imp_CryptGenKey
0x18002ad9a  test    eax, eax
0x18002ad9c  jnz     short loc_18002ADEA
0x18002ad9e  call    ?IcpGetLastError@@YAJXZ; IcpGetLastError(void)
0x18002ada3  mov     ebx, eax
0x18002ada5  test    eax, eax
0x18002ada7  jns     short loc_18002ADEA
0x18002ada9  test    byte ptr cs:g_dwDebugFlags, 3
0x18002adb0  jz      short loc_18002ADE3
0x18002adb2  mov     rcx, cs:g_pDebug
0x18002adb9  lea     r9, aIiscryptogener_0; "IISCryptoGenerateSessionKey"
0x18002adc0  mov     [rsp+38h+var_10], eax
0x18002adc4  lea     rdx, aInetsrvIisMbCr_1; "inetsrv\\iis\\mb\\crypto\\key.cxx"
0x18002adcb  lea     rax, aIiscryptogener; "IISCryptoGenerateSessionKey.CryptGenKey"...
0x18002add2  mov     r8d, 149h
0x18002add8  mov     [rsp+38h+var_18], rax
0x18002addd  call    cs:__imp_PuDbgPrint
0x18002ade3  mov     qword ptr [rdi], 0
0x18002adea  mov     eax, ebx
0x18002adec  mov     rbx, [rsp+38h+arg_0]
0x18002adf1  add     rsp, 30h
0x18002adf5  pop     rdi
0x18002adf6  retn
```
