# RasEapInvokeConfigUI

- ea: `0x1800172d0`
- end: `0x18001735b`
- name: `RasEapInvokeConfigUI`
- size: `139`
- prototype: `DWORD __stdcall(DWORD dwEapTypeId, HWND hwndParent, DWORD dwFlags, BYTE *pConnectionDataIn, DWORD dwSizeOfConnectionDataIn, BYTE **ppConnectionDataOut, DWORD *pdwSizeOfConnectionDataOut)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180006a20`
- `0x1800147cc`
- `0x1800172d0`

## import_xrefs

- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_InvokeConfigUI` at `0x18001731d`
- `ext-ms-win-raschapext-eap-l1-1-0!RasChapExt_InvokeConfigUI` at `0x18001731d`

## pseudocode

```c
DWORD __stdcall RasEapInvokeConfigUI(
        DWORD dwEapTypeId,
        HWND hwndParent,
        DWORD dwFlags,
        BYTE *pConnectionDataIn,
        DWORD dwSizeOfConnectionDataIn,
        BYTE **ppConnectionDataOut,
        DWORD *pdwSizeOfConnectionDataOut)
{
  if ( (unsigned __int8)IsRasChapExt_GetConfigIgnoreIASLogonPresent() )
    return RasChapExt_InvokeConfigUI(
             dwEapTypeId,
             hwndParent,
             dwFlags,
             pConnectionDataIn,
             dwSizeOfConnectionDataIn,
             ppConnectionDataOut,
             pdwSizeOfConnectionDataOut);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, &WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids);
  return 120;
}

```

## disassembly

```asm
0x1800172d0  push    rbx
0x1800172d2  push    rbp
0x1800172d3  push    rsi
0x1800172d4  push    rdi
0x1800172d5  sub     rsp, 48h
0x1800172d9  mov     rbx, r9
0x1800172dc  mov     edi, r8d
0x1800172df  mov     rsi, rdx
0x1800172e2  mov     ebp, ecx
0x1800172e4  call    IsRasChapExt_GetConfigIgnoreIASLogonPresent
0x1800172e9  test    al, al
0x1800172eb  jz      short loc_180017325
0x1800172ed  mov     rax, [rsp+68h+pdwSizeOfConnectionDataOut]
0x1800172f5  mov     r9, rbx
0x1800172f8  mov     [rsp+68h+var_38], rax
0x1800172fd  mov     r8d, edi
0x180017300  mov     rax, [rsp+68h+ppConnectionDataOut]
0x180017308  mov     rdx, rsi
0x18001730b  mov     [rsp+68h+var_40], rax
0x180017310  mov     ecx, ebp
0x180017312  mov     eax, [rsp+68h+dwSizeOfConnectionDataIn]
0x180017319  mov     [rsp+68h+var_48], eax
0x18001731d  call    cs:__imp_RasChapExt_InvokeConfigUI
0x180017323  jmp     short loc_180017352
0x180017325  mov     rcx, cs:WPP_GLOBAL_Control
0x18001732c  lea     rax, WPP_GLOBAL_Control
0x180017333  cmp     rcx, rax
0x180017336  jz      short loc_18001734D
0x180017338  mov     rcx, [rcx+10h]
0x18001733c  lea     r8, WPP_9b8b2f5616a63040265c7a7536bda72e_Traceguids
0x180017343  mov     edx, 0BBh
0x180017348  call    WPP_SF_
0x18001734d  mov     eax, 78h ; 'x'
0x180017352  add     rsp, 48h
0x180017356  pop     rdi
0x180017357  pop     rsi
0x180017358  pop     rbp
0x180017359  pop     rbx
0x18001735a  retn
```
