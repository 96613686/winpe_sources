# GetHardwareAddressForIpAddress

- ea: `0x18003bf98`
- end: `0x18003c05b`
- name: `GetHardwareAddressForIpAddress`
- size: `195`
- prototype: `__int64 __fastcall(u_long, void *, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x18003bebc`
- `0x18003c554`
- `0x18003c9d8`

## callees

- `0x1800057f0`
- `0x1800135dc`
- `0x18003bf98`
- `0x180042300`
- `0x180047e3c`
- `0x18004d1a0`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x18003bfbf`
- `WS2_32!__imp_htonl` at `0x18003bfbf`

## pseudocode

```c
__int64 __fastcall GetHardwareAddressForIpAddress(u_long a1, void *a2, unsigned int *a3)
{
  const void **v3; // rdi
  u_long v6; // eax
  unsigned int InterfaceFromIPv4Address; // ebx
  unsigned int LinkCharacteristics; // eax
  unsigned int v9; // esi
  _QWORD v11[5]; // [rsp+20h] [rbp-28h] BYREF
  const void **v12; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v11[0] = 0;
  v12 = 0;
  v6 = htonl(a1);
  InterfaceFromIPv4Address = DhcpGetInterfaceFromIPv4Address(v6, v11);
  if ( !InterfaceFromIPv4Address )
  {
    LinkCharacteristics = DhcpGetLinkCharacteristics(v11, &v12);
    v3 = v12;
    InterfaceFromIPv4Address = LinkCharacteristics;
    if ( !LinkCharacteristics )
    {
      v9 = *((unsigned __int16 *)v12 + 30);
      if ( v9 <= *a3 )
      {
        memcpy_0(a2, v12[8], *((unsigned __int16 *)v12 + 30));
        goto LABEL_8;
      }
      InterfaceFromIPv4Address = 234;
    }
  }
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 10, WPP_c84194e7b785338e3b207dae288fd792_Traceguids, InterfaceFromIPv4Address);
  v9 = 0;
LABEL_8:
  *a3 = v9;
  if ( v3 )
    DhcpPunycodeFree((LPVOID *)&v12);
  return InterfaceFromIPv4Address;
}

```

## disassembly

```asm
0x18003bf98  mov     rax, rsp
0x18003bf9b  mov     [rax+8], rbx
0x18003bf9f  mov     [rax+10h], rbp
0x18003bfa3  push    rsi
0x18003bfa4  push    rdi
0x18003bfa5  push    r14
0x18003bfa7  sub     rsp, 30h
0x18003bfab  xor     edi, edi
0x18003bfad  mov     qword ptr [rax-28h], 0
0x18003bfb5  mov     [rax+20h], rdi
0x18003bfb9  mov     r14, r8
0x18003bfbc  mov     rbp, rdx
0x18003bfbf  call    cs:__imp_htonl
0x18003bfc5  mov     ecx, eax
0x18003bfc7  lea     rdx, [rsp+48h+var_28]
0x18003bfcc  call    DhcpGetInterfaceFromIPv4Address
0x18003bfd1  mov     ebx, eax
0x18003bfd3  test    eax, eax
0x18003bfd5  jnz     short loc_18003BFFF
0x18003bfd7  lea     rdx, [rsp+48h+arg_18]
0x18003bfdc  lea     rcx, [rsp+48h+var_28]
0x18003bfe1  call    DhcpGetLinkCharacteristics
0x18003bfe6  mov     rdi, [rsp+48h+arg_18]
0x18003bfeb  mov     ebx, eax
0x18003bfed  test    eax, eax
0x18003bfef  jnz     short loc_18003BFFF
0x18003bff1  movzx   esi, word ptr [rdi+3Ch]
0x18003bff5  cmp     esi, [r14]
0x18003bff8  jbe     short loc_18003C04A
0x18003bffa  mov     ebx, 0EAh
0x18003bfff  test    byte ptr cs:xmmword_1800616A0, 2
0x18003c006  jz      short loc_18003C021
0x18003c008  mov     edx, 0Ah
0x18003c00d  lea     r8, WPP_c84194e7b785338e3b207dae288fd792_Traceguids
0x18003c014  mov     ecx, 401h
0x18003c019  mov     r9d, ebx
0x18003c01c  call    WPP_SF_D
0x18003c021  xor     esi, esi
0x18003c023  mov     [r14], esi
0x18003c026  test    rdi, rdi
0x18003c029  jz      short loc_18003C035
0x18003c02b  lea     rcx, [rsp+48h+arg_18]
0x18003c030  call    DhcpPunycodeFree
0x18003c035  mov     rbp, [rsp+48h+arg_8]
0x18003c03a  mov     eax, ebx
0x18003c03c  mov     rbx, [rsp+48h+arg_0]
0x18003c041  add     rsp, 30h
0x18003c045  pop     r14
0x18003c047  pop     rdi
0x18003c048  pop     rsi
0x18003c049  retn
0x18003c04a  mov     rdx, [rdi+40h]; Src
0x18003c04e  mov     r8, rsi; Size
0x18003c051  mov     rcx, rbp; void *
0x18003c054  call    memcpy_0
0x18003c059  jmp     short loc_18003C023
```
