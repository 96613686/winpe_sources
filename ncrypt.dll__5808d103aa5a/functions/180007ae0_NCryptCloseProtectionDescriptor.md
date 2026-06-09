# NCryptCloseProtectionDescriptor

- ea: `0x180007ae0`
- end: `0x180007b76`
- name: `NCryptCloseProtectionDescriptor`
- size: `150`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000260c`
- `0x1800053ac`
- `0x180007274`
- `0x180007420`
- `0x18000962c`
- `0x180013d38`
- `0x180016128`

## callees

- `0x180007958`
- `0x180007ae0`
- `0x180008cfc`
- `0x18000a770`
- `0x18000d02c`

## string_xrefs

- `0x180007b4c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\ncryptprotect.c`

## pseudocode

```c
__int64 __fastcall NCryptCloseProtectionDescriptor(__int64 a1, int a2, int a3)
{
  __int64 v4; // rcx
  unsigned int v5; // edi
  __int64 v6; // rcx

  if ( a1 && *(_DWORD *)a1 == 40 )
  {
    v4 = *(_QWORD *)(a1 + 8);
    v5 = 0;
    if ( v4 )
      CNG_FreeProtectionDescriptor(v4);
    v6 = *(_QWORD *)(a1 + 24);
    if ( v6 )
      NCryptMsgClose(v6);
    MSCryptFree(a1);
  }
  else
  {
    v5 = -2146893786;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\ncryptprotect.c",
        153);
  }
  return v5;
}

```

## disassembly

```asm
0x180007ae0  mov     [rsp+arg_0], rbx
0x180007ae5  push    rdi
0x180007ae6  sub     rsp, 40h
0x180007aea  mov     rbx, rcx
0x180007aed  test    rcx, rcx
0x180007af0  jz      short loc_180007B2A
0x180007af2  cmp     dword ptr [rcx], 28h ; '('
0x180007af5  jnz     short loc_180007B2A
0x180007af7  mov     rcx, [rcx+8]
0x180007afb  xor     edi, edi
0x180007afd  test    rcx, rcx
0x180007b00  jz      short loc_180007B07
0x180007b02  call    CNG_FreeProtectionDescriptor
0x180007b07  mov     rcx, [rbx+18h]
0x180007b0b  test    rcx, rcx
0x180007b0e  jz      short loc_180007B15
0x180007b10  call    NCryptMsgClose
0x180007b15  mov     rcx, rbx
0x180007b18  call    MSCryptFree
0x180007b1d  mov     rbx, [rsp+48h+arg_0]
0x180007b22  mov     eax, edi
0x180007b24  add     rsp, 40h
0x180007b28  pop     rdi
0x180007b29  retn
0x180007b2a  mov     edi, 80090026h
0x180007b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b36  lea     rax, WPP_GLOBAL_Control
0x180007b3d  cmp     rcx, rax
0x180007b40  jz      short loc_180007B1D
0x180007b42  test    byte ptr [rcx+1Ch], 1
0x180007b46  jz      short loc_180007B1D
0x180007b48  mov     rcx, [rcx+10h]
0x180007b4c  lea     rax, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007b53  mov     [rsp+48h+var_18], 199h
0x180007b5b  lea     r9, aStatus; "Status"
0x180007b62  mov     [rsp+48h+var_20], rax
0x180007b67  mov     [rsp+48h+var_28], 80090026h
0x180007b6f  call    WPP_SF_sDsd
0x180007b74  jmp     short loc_180007B1D
```
