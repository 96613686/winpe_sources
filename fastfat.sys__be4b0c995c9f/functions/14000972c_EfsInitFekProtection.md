# EfsInitFekProtection

- ea: `0x14000972c`
- end: `0x140009a28`
- name: `EfsInitFekProtection`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004da14`

## callees

- `0x1400083b0`
- `0x14000972c`
- `0x14000c230`
- `0x14000c680`
- `0x14005693c`

## import_xrefs

- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000980f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009885`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14000980f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140009885`
- `ksecdd!BCryptGetProperty` at `0x140009856`
- `ksecdd!BCryptGetProperty` at `0x1400098cc`
- `ksecdd!BCryptGetProperty` at `0x140009856`
- `ksecdd!BCryptGetProperty` at `0x1400098cc`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400099db`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400099f8`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d93c`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d95b`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400099db`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400099f8`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d93c`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14000d95b`

## pseudocode

```c
__int64 EfsInitFekProtection()
{
  __int64 v0; // rcx
  NTSTATUS Property; // ebx
  __int64 v2; // r8
  ULONG pcbResult; // [rsp+44h] [rbp-A4h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-A0h] BYREF
  int v6; // [rsp+50h] [rbp-98h]
  BCRYPT_ALG_HANDLE hObject; // [rsp+58h] [rbp-90h] BYREF
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-88h] BYREF
  UCHAR v9[4]; // [rsp+64h] [rbp-84h] BYREF
  __int64 v10; // [rsp+68h] [rbp-80h]
  _OWORD v11[2]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v12[64]; // [rsp+90h] [rbp-58h] BYREF

  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  hObject = 0;
  *(_DWORD *)v9 = 0;
  pcbResult = 0;
  v6 = 0;
  memset(v11, 0, sizeof(v11));
  memset(v12, 0, sizeof(v12));
  v10 = 0;
  if ( (_DWORD)Size || (_DWORD)dword_140017920 || hAlgorithm || cbKeyObject || ::hObject || cbHashObject )
  {
    Property = -1073741811;
    v2 = 148;
    goto LABEL_17;
  }
  if ( dword_1400178C8 != 16 )
  {
    Property = -1073741823;
    v2 = 169;
LABEL_17:
    EfspTraceLogAssert(v0, 9, v2, (unsigned int)Property);
    goto LABEL_18;
  }
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SP800_108_CTR_HMAC", 0, 0);
  if ( Property >= 0 )
  {
    pcbResult = 4;
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 8u);
      if ( Property >= 0 )
      {
        pcbResult = 4;
        Property = BCryptGetProperty(hObject, L"ObjectLength", v9, 4u, &pcbResult, 0);
        if ( Property >= 0 )
        {
          hAlgorithm = phAlgorithm;
          phAlgorithm = 0;
          cbKeyObject = *(_DWORD *)pbOutput;
          ::hObject = hObject;
          hObject = 0;
          cbHashObject = *(_DWORD *)v9;
          Property = DplWrapProtect(v11, 32, v12);
          if ( Property >= 0 )
          {
            LODWORD(Size) = 64;
            LODWORD(dword_140017920) = v6;
          }
          else
          {
            phAlgorithm = hAlgorithm;
            hAlgorithm = 0;
            cbKeyObject = 0;
            hObject = ::hObject;
            ::hObject = 0;
            cbHashObject = 0;
          }
        }
      }
    }
  }
LABEL_18:
  if ( phAlgorithm )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    phAlgorithm = 0;
  }
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14000972c  mov     r11, rsp
0x14000972f  mov     [r11+8], rbx
0x140009733  push    rdi
0x140009734  sub     rsp, 0E0h
0x14000973b  mov     rax, cs:__security_cookie
0x140009742  xor     rax, rsp
0x140009745  mov     [rsp+0E8h+var_18], rax
0x14000974d  xor     edi, edi
0x14000974f  mov     [rsp+0E8h+phAlgorithm], rdi
0x140009754  mov     dword ptr [rsp+0E8h+pbOutput], edi
0x140009758  mov     [rsp+0E8h+hObject], rdi
0x14000975d  mov     dword ptr [rsp+0E8h+var_84], edi
0x140009761  mov     [rsp+0E8h+var_A4], edi
0x140009765  mov     [rsp+0E8h+var_98], edi
0x140009769  xorps   xmm0, xmm0
0x14000976c  movups  [rsp+0E8h+var_78], xmm0
0x140009771  movups  xmmword ptr [r11-68h], xmm0
0x140009776  xor     edx, edx; Val
0x140009778  lea     r8d, [rdi+40h]; Size
0x14000977c  lea     rcx, [r11-58h]; void *
0x140009780  call    memset
0x140009785  mov     [rsp+0E8h+var_80], rdi
0x14000978a  mov     eax, cs:Size
0x140009790  test    eax, eax
0x140009792  jnz     loc_1400099B2
0x140009798  mov     eax, cs:dword_140017920
0x14000979e  test    eax, eax
0x1400097a0  jnz     loc_1400099B2
0x1400097a6  mov     rax, cs:hAlgorithm
0x1400097ad  test    rax, rax
0x1400097b0  jnz     loc_1400099B2
0x1400097b6  mov     eax, cs:cbKeyObject
0x1400097bc  test    eax, eax
0x1400097be  jnz     loc_1400099B2
0x1400097c4  mov     rax, cs:hObject
0x1400097cb  test    rax, rax
0x1400097ce  jnz     loc_1400099B2
0x1400097d4  mov     eax, cs:cbHashObject
0x1400097da  test    eax, eax
0x1400097dc  jnz     loc_1400099B2
0x1400097e2  mov     eax, cs:dword_1400178C8
0x1400097e8  cmp     eax, 10h
0x1400097eb  jz      short loc_1400097FD
0x1400097ed  mov     ebx, 0C0000001h
0x1400097f2  mov     r8d, 0A9h
0x1400097f8  jmp     loc_1400099BD
0x1400097fd  xor     r9d, r9d; dwFlags
0x140009800  xor     r8d, r8d; pszImplementation
0x140009803  lea     rdx, pszAlgId; "SP800_108_CTR_HMAC"
0x14000980a  lea     rcx, [rsp+0E8h+phAlgorithm]; phAlgorithm
0x14000980f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140009816  nop     dword ptr [rax+rax+00h]
0x14000981b  mov     ebx, eax
0x14000981d  mov     [rsp+0E8h+var_A8], eax
0x140009821  test    eax, eax
0x140009823  js      loc_1400099CF
0x140009829  mov     [rsp+0E8h+var_A4], 4
0x140009831  mov     [rsp+0E8h+dwFlags], edi; dwFlags
0x140009835  lea     rax, [rsp+0E8h+var_A4]
0x14000983a  mov     [rsp+0E8h+pcbResult], rax; pcbResult
0x14000983f  mov     r9d, 4; cbOutput
0x140009845  lea     r8, [rsp+0E8h+pbOutput]; pbOutput
0x14000984a  lea     rdx, aObjectlength; "ObjectLength"
0x140009851  mov     rcx, [rsp+0E8h+phAlgorithm]; hObject
0x140009856  call    cs:__imp_BCryptGetProperty
0x14000985d  nop     dword ptr [rax+rax+00h]
0x140009862  mov     ebx, eax
0x140009864  mov     [rsp+0E8h+var_A8], eax
0x140009868  test    eax, eax
0x14000986a  js      loc_1400099CF
0x140009870  mov     r9d, 8; dwFlags
0x140009876  xor     r8d, r8d; pszImplementation
0x140009879  lea     rdx, aSha256; "SHA256"
0x140009880  lea     rcx, [rsp+0E8h+hObject]; phAlgorithm
0x140009885  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14000988c  nop     dword ptr [rax+rax+00h]
0x140009891  mov     ebx, eax
0x140009893  mov     [rsp+0E8h+var_A8], eax
0x140009897  test    eax, eax
0x140009899  js      loc_1400099CF
0x14000989f  mov     [rsp+0E8h+var_A4], 4
0x1400098a7  mov     [rsp+0E8h+dwFlags], edi; dwFlags
0x1400098ab  lea     rax, [rsp+0E8h+var_A4]
0x1400098b0  mov     [rsp+0E8h+pcbResult], rax; pcbResult
0x1400098b5  mov     r9d, 4; cbOutput
0x1400098bb  lea     r8, [rsp+0E8h+var_84]; pbOutput
0x1400098c0  lea     rdx, aObjectlength; "ObjectLength"
0x1400098c7  mov     rcx, [rsp+0E8h+hObject]; hObject
0x1400098cc  call    cs:__imp_BCryptGetProperty
0x1400098d3  nop     dword ptr [rax+rax+00h]
0x1400098d8  mov     ebx, eax
0x1400098da  mov     [rsp+0E8h+var_A8], eax
0x1400098de  test    eax, eax
0x1400098e0  js      loc_1400099CF
0x1400098e6  mov     rax, [rsp+0E8h+phAlgorithm]
0x1400098eb  mov     cs:hAlgorithm, rax
0x1400098f2  mov     [rsp+0E8h+phAlgorithm], rdi
0x1400098f7  mov     eax, dword ptr [rsp+0E8h+pbOutput]
0x1400098fb  mov     cs:cbKeyObject, eax
0x140009901  mov     rax, [rsp+0E8h+hObject]
0x140009906  mov     cs:hObject, rax
0x14000990d  mov     [rsp+0E8h+hObject], rdi
0x140009912  mov     eax, dword ptr [rsp+0E8h+var_84]
0x140009916  mov     cs:cbHashObject, eax
0x14000991c  lea     rax, [rsp+0E8h+var_98]
0x140009921  mov     [rsp+0E8h+var_B0], rax
0x140009926  lea     rax, [rsp+0E8h+var_98]
0x14000992b  mov     [rsp+0E8h+var_B8], rax
0x140009930  mov     [rsp+0E8h+dwFlags], 8
0x140009938  lea     rax, [rsp+0E8h+var_80]
0x14000993d  mov     [rsp+0E8h+pcbResult], rax
0x140009942  mov     r9d, 40h ; '@'
0x140009948  lea     r8, [rsp+0E8h+var_58]
0x140009950  lea     edx, [r9-20h]
0x140009954  lea     rcx, [rsp+0E8h+var_78]
0x140009959  call    DplWrapProtect
0x14000995e  mov     ebx, eax
0x140009960  mov     [rsp+0E8h+var_A8], eax
0x140009964  test    eax, eax
0x140009966  jns     short loc_14000999C
0x140009968  mov     rax, cs:hAlgorithm
0x14000996f  mov     [rsp+0E8h+phAlgorithm], rax
0x140009974  mov     cs:hAlgorithm, rdi
0x14000997b  mov     cs:cbKeyObject, edi
0x140009981  mov     rax, cs:hObject
0x140009988  mov     [rsp+0E8h+hObject], rax
0x14000998d  mov     cs:hObject, rdi
0x140009994  mov     cs:cbHashObject, edi
0x14000999a  jmp     short loc_1400099CF
0x14000999c  mov     cs:Size, 40h ; '@'
0x1400099a6  mov     eax, [rsp+0E8h+var_98]
0x1400099aa  mov     cs:dword_140017920, eax
0x1400099b0  jmp     short loc_1400099CF
0x1400099b2  mov     ebx, 0C000000Dh
0x1400099b7  mov     r8d, 94h
0x1400099bd  mov     [rsp+0E8h+var_A8], ebx
0x1400099c1  mov     r9d, ebx
0x1400099c4  mov     edx, 9
0x1400099c9  call    EfspTraceLogAssert
0x1400099ce  nop
0x1400099cf  mov     rcx, [rsp+0E8h+phAlgorithm]; hAlgorithm
0x1400099d4  test    rcx, rcx
0x1400099d7  jz      short loc_1400099EC
0x1400099d9  xor     edx, edx; dwFlags
0x1400099db  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400099e2  nop     dword ptr [rax+rax+00h]
0x1400099e7  mov     [rsp+0E8h+phAlgorithm], rdi
0x1400099ec  mov     rcx, [rsp+0E8h+hObject]; hAlgorithm
0x1400099f1  test    rcx, rcx
0x1400099f4  jz      short loc_140009A04
0x1400099f6  xor     edx, edx; dwFlags
0x1400099f8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400099ff  nop     dword ptr [rax+rax+00h]
0x140009a04  mov     eax, ebx
0x140009a06  mov     rcx, [rsp+0E8h+var_18]
0x140009a0e  xor     rcx, rsp; StackCookie
0x140009a11  call    __security_check_cookie
0x140009a16  mov     rbx, [rsp+0E8h+arg_0]
0x140009a1e  add     rsp, 0E0h
0x140009a25  pop     rdi
0x140009a26  retn
0x14000d928  push    rbp
0x14000d92a  sub     rsp, 40h
0x14000d92e  mov     rbp, rdx
0x14000d931  mov     rcx, [rbp+48h]; hAlgorithm
0x14000d935  test    rcx, rcx
0x14000d938  jz      short loc_14000D950
0x14000d93a  xor     edx, edx; dwFlags
0x14000d93c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d943  nop     dword ptr [rax+rax+00h]
0x14000d948  mov     qword ptr [rbp+48h], 0
0x14000d950  mov     rcx, [rbp+58h]; hAlgorithm
0x14000d954  test    rcx, rcx
0x14000d957  jz      short loc_14000D968
0x14000d959  xor     edx, edx; dwFlags
0x14000d95b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14000d962  nop     dword ptr [rax+rax+00h]
0x14000d967  nop
0x14000d968  add     rsp, 40h
0x14000d96c  pop     rbp
0x14000d96d  retn
```
