# MQUInitGlobalScurityVars(void)

- ea: `0x180004780`
- end: `0x180004801`
- name: `?MQUInitGlobalScurityVars@@YAXXZ`
- size: `129`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004780`
- `0x1800049ac`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x1800047b5`
- `ADVAPI32!CryptAcquireContextW` at `0x1800047b5`
- `KERNEL32!GetLastError` at `0x1800047bf`
- `KERNEL32!GetLastError` at `0x1800047bf`

## pseudocode

```c
void MQUInitGlobalScurityVars(void)
{
  DWORD LastError; // eax

  if ( !dword_1800421B8 )
  {
    dword_1800421B8 = 1;
    if ( !CryptAcquireContextW(
            &g_hProvVer,
            0,
            L"Microsoft Enhanced RSA and AES Cryptographic Provider",
            0x18u,
            0xF0000000) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, &WPP_2d00db894b443409422f6842f1d0ba08_Traceguids, LastError);
    }
  }
}

```

## disassembly

```asm
0x180004780  sub     rsp, 38h
0x180004784  cmp     cs:dword_1800421B8, 0
0x18000478b  jnz     short loc_1800047FC
0x18000478d  mov     r9d, 18h; dwProvType
0x180004793  mov     cs:dword_1800421B8, 1
0x18000479d  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x1800047a4  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x1800047ac  xor     edx, edx; szContainer
0x1800047ae  lea     rcx, ?g_hProvVer@@3VCHCryptProv@@A; phProv
0x1800047b5  call    cs:__imp_CryptAcquireContextW
0x1800047bb  test    eax, eax
0x1800047bd  jnz     short loc_1800047FC
0x1800047bf  call    cs:__imp_GetLastError
0x1800047c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800047cc  lea     rdx, WPP_GLOBAL_Control
0x1800047d3  cmp     rcx, rdx
0x1800047d6  jz      short loc_1800047FC
0x1800047d8  test    byte ptr [rcx+10Ch], 1
0x1800047df  jz      short loc_1800047FC
0x1800047e1  mov     rcx, [rcx+100h]
0x1800047e8  lea     r8, WPP_2d00db894b443409422f6842f1d0ba08_Traceguids
0x1800047ef  mov     edx, 0Ah
0x1800047f4  mov     r9d, eax
0x1800047f7  call    WPP_SF_d
0x1800047fc  add     rsp, 38h
0x180004800  retn
```
