# MRxSmbRead

- ea: `0x14003bbd0`
- end: `0x14003bd32`
- name: `MRxSmbRead`
- size: `354`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14003bbd0`
- `0x14003f9cc`
- `0x140046120`
- `0x14004d7f0`
- `0x14004dd50`

## import_xrefs

- `rdbss!RxLowIoGetBufferAddress` at `0x14003bc29`
- `rdbss!RxLowIoGetBufferAddress` at `0x14003bc29`

## pseudocode

```c
__int64 __fastcall MRxSmbRead(PRX_CONTEXT RxContext)
{
  PMRX_FOBX pFobx; // rax
  __int64 v3; // r14
  unsigned int OrdinaryExchange; // ebx
  int v5; // ebp
  unsigned __int8 *v6; // rsi
  unsigned __int8 *v7; // rcx
  __int64 v9; // [rsp+20h] [rbp-48h]
  PVOID pContext; // [rsp+70h] [rbp+8h] BYREF

  pFobx = RxContext->pFobx;
  pContext = 0;
  v3 = *((_QWORD *)pFobx->Context2 + 5);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
  if ( !RxLowIoGetBufferAddress(RxContext) && *((_DWORD *)&RxContext->9 + 42) )
  {
    OrdinaryExchange = -1073741670;
LABEL_16:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_f246e64eea833cb58dbbe2117b998014_Traceguids,
        OrdinaryExchange);
    return OrdinaryExchange;
  }
  v5 = 0;
  while ( 1 )
  {
    OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                         (__int64)RxContext,
                         v3,
                         14,
                         (__int64)SmbPseExchangeStart_Read,
                         v9,
                         (__int64 *)&pContext);
    if ( OrdinaryExchange )
      break;
    v6 = (unsigned __int8 *)pContext;
    v7 = (unsigned __int8 *)pContext;
    *((_DWORD *)pContext + 104) = v5;
    *((_QWORD *)v7 + 15) = &RxContext->PrefixClaim.NetRootType;
    OrdinaryExchange = SmbCeInitiateExchange(v7);
    if ( OrdinaryExchange == 259 )
      goto LABEL_16;
    v5 = *((_DWORD *)v6 + 104);
    SmbPseFinalizeOrdinaryExchange(v6);
    if ( OrdinaryExchange != -1069481983 )
      goto LABEL_16;
    if ( ((__int64)RxContext->RdbssDbgExtension & 0x1000) != 0 )
    {
      MRxSmbResumeAsyncReadWriteRequests(RxContext);
      OrdinaryExchange = 259;
      goto LABEL_16;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
    goto LABEL_16;
  }
  return OrdinaryExchange;
}

```

## disassembly

```asm
0x14003bbd0  push    rbx
0x14003bbd2  push    rbp
0x14003bbd3  push    rsi
0x14003bbd4  push    rdi
0x14003bbd5  push    r12
0x14003bbd7  push    r14
0x14003bbd9  sub     rsp, 38h
0x14003bbdd  mov     rax, [rcx+40h]
0x14003bbe1  mov     rdi, rcx
0x14003bbe4  mov     [rsp+68h+pContext], 0
0x14003bbed  mov     rdx, [rax+20h]
0x14003bbf1  mov     r14, [rdx+28h]
0x14003bbf5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bbfc  lea     r12, WPP_GLOBAL_Control
0x14003bc03  cmp     rcx, r12
0x14003bc06  jz      short loc_14003BC26
0x14003bc08  test    dword ptr [rcx+2Ch], 400h
0x14003bc0f  jz      short loc_14003BC26
0x14003bc11  mov     rcx, [rcx+18h]
0x14003bc15  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003bc1c  mov     edx, 0Ah
0x14003bc21  call    WPP_SF_
0x14003bc26  mov     rcx, rdi; RxContext
0x14003bc29  call    cs:__imp_RxLowIoGetBufferAddress
0x14003bc30  nop     dword ptr [rax+rax+00h]
0x14003bc35  test    rax, rax
0x14003bc38  jnz     short loc_14003BC4C
0x14003bc3a  cmp     [rdi+238h], eax
0x14003bc40  jz      short loc_14003BC4C
0x14003bc42  mov     ebx, 0C000009Ah
0x14003bc47  jmp     loc_14003BCF5
0x14003bc4c  xor     ebp, ebp
0x14003bc4e  lea     rax, [rsp+68h+pContext]
0x14003bc53  mov     r8d, 0Eh
0x14003bc59  lea     r9, SmbPseExchangeStart_Read
0x14003bc60  mov     [rsp+68h+var_40], rax
0x14003bc65  mov     rdx, r14
0x14003bc68  mov     rcx, rdi
0x14003bc6b  call    __SmbPseCreateOrdinaryExchange
0x14003bc70  mov     ebx, eax
0x14003bc72  test    eax, eax
0x14003bc74  jnz     short loc_14003BCCB
0x14003bc76  mov     rsi, [rsp+68h+pContext]
0x14003bc7b  lea     rax, [rdi+180h]
0x14003bc82  mov     rcx, rsi
0x14003bc85  mov     [rsi+1A0h], ebp
0x14003bc8b  mov     [rsi+78h], rax
0x14003bc8f  call    SmbCeInitiateExchange
0x14003bc94  mov     ebx, eax
0x14003bc96  cmp     eax, 103h
0x14003bc9b  jz      short loc_14003BCF5
0x14003bc9d  mov     ebp, [rsi+1A0h]
0x14003bca3  mov     rcx, rsi; pContext
0x14003bca6  call    SmbPseFinalizeOrdinaryExchange
0x14003bcab  cmp     ebx, 0C0410001h
0x14003bcb1  jnz     short loc_14003BCF5
0x14003bcb3  test    dword ptr [rdi+78h], 1000h
0x14003bcba  jz      short loc_14003BC4E
0x14003bcbc  mov     rcx, rdi; RxContext
0x14003bcbf  call    MRxSmbResumeAsyncReadWriteRequests
0x14003bcc4  mov     ebx, 103h
0x14003bcc9  jmp     short loc_14003BCF5
0x14003bccb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bcd2  cmp     rcx, r12
0x14003bcd5  jz      short loc_14003BD22
0x14003bcd7  test    dword ptr [rcx+2Ch], 400h
0x14003bcde  jz      short loc_14003BCF5
0x14003bce0  mov     rcx, [rcx+18h]
0x14003bce4  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003bceb  mov     edx, 0Bh
0x14003bcf0  call    WPP_SF_
0x14003bcf5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bcfc  cmp     rcx, r12
0x14003bcff  jz      short loc_14003BD22
0x14003bd01  test    dword ptr [rcx+2Ch], 400h
0x14003bd08  jz      short loc_14003BD22
0x14003bd0a  mov     rcx, [rcx+18h]
0x14003bd0e  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003bd15  mov     edx, 0Ch
0x14003bd1a  mov     r9d, ebx
0x14003bd1d  call    WPP_SF_d
0x14003bd22  mov     eax, ebx
0x14003bd24  add     rsp, 38h
0x14003bd28  pop     r14
0x14003bd2a  pop     r12
0x14003bd2c  pop     rdi
0x14003bd2d  pop     rsi
0x14003bd2e  pop     rbp
0x14003bd2f  pop     rbx
0x14003bd30  retn
```
