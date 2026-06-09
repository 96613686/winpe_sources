# MRxSmbNetworkOpenInformationByName

- ea: `0x140039420`
- end: `0x1400394e8`
- name: `MRxSmbNetworkOpenInformationByName`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x14000dfa8`
- `0x140039420`
- `0x140046120`
- `0x14004d7f0`
- `0x14004dd50`

## pseudocode

```c
__int64 __fastcall MRxSmbNetworkOpenInformationByName(__int64 a1, __int64 a2)
{
  unsigned int OrdinaryExchange; // ebx
  __int64 v4; // [rsp+20h] [rbp-18h]
  PVOID pContext; // [rsp+40h] [rbp+8h] BYREF

  pContext = 0;
  if ( !a2 )
    a2 = *(_QWORD *)(a1 + 56) + 360LL;
  if ( !*(_WORD *)a2 || *(_WORD *)a2 == 2 && **(_WORD **)(a2 + 8) == 92 )
  {
    return (unsigned int)-1073741811;
  }
  else
  {
    OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                         a1,
                         *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL) + 40LL),
                         9,
                         (__int64)MRxSmbUpdateFileInformationAfterClose_Start,
                         v4,
                         (__int64 *)&pContext);
    if ( OrdinaryExchange )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
      }
    }
    else
    {
      OrdinaryExchange = SmbCeInitiateExchange((unsigned __int8 *)pContext);
      SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)pContext);
    }
  }
  return OrdinaryExchange;
}

```

## disassembly

```asm
0x140039420  mov     [rsp+arg_8], rbx
0x140039425  push    rdi
0x140039426  sub     rsp, 30h
0x14003942a  xor     edi, edi
0x14003942c  mov     [rsp+38h+pContext], rdi
0x140039431  test    rdx, rdx
0x140039434  jnz     short loc_140039441
0x140039436  mov     rdx, [rcx+38h]
0x14003943a  add     rdx, 168h
0x140039441  movzx   eax, word ptr [rdx]
0x140039444  test    ax, ax
0x140039447  jnz     short loc_140039453
0x140039449  mov     ebx, 0C000000Dh
0x14003944e  jmp     loc_1400394DA
0x140039453  cmp     ax, 2
0x140039457  jnz     short loc_140039463
0x140039459  mov     rax, [rdx+8]
0x14003945d  cmp     word ptr [rax], 5Ch ; '\'
0x140039461  jz      short loc_140039449
0x140039463  mov     rax, [rcx+40h]
0x140039467  lea     r9, MRxSmbUpdateFileInformationAfterClose_Start
0x14003946e  mov     r8d, 9
0x140039474  mov     rdx, [rax+20h]
0x140039478  lea     rax, [rsp+38h+pContext]
0x14003947d  mov     [rsp+38h+var_10], rax
0x140039482  mov     rdx, [rdx+28h]
0x140039486  call    __SmbPseCreateOrdinaryExchange
0x14003948b  mov     ebx, eax
0x14003948d  test    eax, eax
0x14003948f  jz      short loc_1400394C4
0x140039491  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140039498  lea     rax, WPP_GLOBAL_Control
0x14003949f  cmp     rcx, rax
0x1400394a2  jz      short loc_1400394DA
0x1400394a4  test    dword ptr [rcx+2Ch], 400h
0x1400394ab  jz      short loc_1400394DA
0x1400394ad  mov     rcx, [rcx+18h]
0x1400394b1  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400394b8  mov     edx, 5Fh ; '_'
0x1400394bd  call    WPP_SF_
0x1400394c2  jmp     short loc_1400394DA
0x1400394c4  mov     rcx, [rsp+38h+pContext]
0x1400394c9  call    SmbCeInitiateExchange
0x1400394ce  mov     rcx, [rsp+38h+pContext]; pContext
0x1400394d3  mov     ebx, eax
0x1400394d5  call    SmbPseFinalizeOrdinaryExchange
0x1400394da  mov     eax, ebx
0x1400394dc  mov     rbx, [rsp+38h+arg_8]
0x1400394e1  add     rsp, 30h
0x1400394e5  pop     rdi
0x1400394e6  retn
```
