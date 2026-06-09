# SspNtStatusToSecStatus

- ea: `0x180006830`
- end: `0x180006bec`
- name: `SspNtStatusToSecStatus`
- size: `956`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180006048`
- `0x180006420`
- `0x180006700`
- `0x1800087e8`
- `0x180008a40`
- `0x180008cf0`
- `0x1800092d0`
- `0x18000a070`
- `0x18000a6d0`
- `0x18000ab20`

## callees

- `0x180006830`

## import_xrefs

- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180006b97`
- `ntoskrnl!RtlNtStatusToDosErrorNoTeb` at `0x180006b97`

## pseudocode

```c
__int64 __fastcall SspNtStatusToSecStatus(NTSTATUS a1)
{
  unsigned int v1; // edx
  bool v2; // zf
  signed int v4; // eax

  v1 = a1;
  if ( (a1 & 0x1FFF0000) == 0x90000 )
    return v1;
  if ( a1 > -1073741428 )
  {
    if ( a1 > -1073740928 )
    {
      if ( a1 <= -1073740913 )
      {
        if ( a1 == -1073740913
          || a1 == -1073740927
          || a1 == -1073740925
          || a1 == -1073740924
          || a1 == -1073740923
          || a1 == -1073740922
          || a1 == -1073740921 )
        {
          return (unsigned int)-2146893044;
        }
        if ( a1 == -1073740920 )
          return (unsigned int)-2146892976;
        v2 = a1 == -1073740916;
        goto LABEL_25;
      }
      if ( a1 != -1073740792 )
      {
        if ( a1 == -1073740789 )
          return (unsigned int)-2146892969;
        if ( a1 == -1073740781 )
          return v1;
        if ( a1 != -1073740776 )
        {
          switch ( a1 )
          {
            case -1073740755:
              return (unsigned int)-2146892959;
            case -1073740753:
              return (unsigned int)-2146892958;
            case 0:
              return 0;
          }
          goto LABEL_93;
        }
      }
    }
    else
    {
      if ( a1 == -1073740928 )
        return (unsigned int)-2146893044;
      if ( a1 <= -1073741276 )
      {
        if ( a1 == -1073741276 )
          return (unsigned int)-2146893044;
        if ( a1 != -1073741427 && a1 != -1073741424 && a1 != -1073741422 )
        {
          if ( a1 != -1073741421 )
          {
            if ( a1 == -1073741416 || a1 == -1073741415 || a1 == -1073741414 || a1 == -1073741413 )
              return v1;
            goto LABEL_93;
          }
          return (unsigned int)-2146893044;
        }
        return (unsigned int)-2146893039;
      }
      switch ( a1 )
      {
        case -1073741261:
          return (unsigned int)-2146893039;
        case -1073741260:
          return (unsigned int)-2146893044;
        case -1073741252:
          return (unsigned int)-2146893039;
      }
      if ( a1 != -1073741063 )
      {
        if ( a1 == -1073741058 )
          return (unsigned int)-2146892993;
        if ( a1 != -1073741024 )
        {
          if ( a1 == -1073740965 )
            return (unsigned int)-2146892986;
          goto LABEL_93;
        }
      }
    }
    return (unsigned int)-2146893044;
  }
  if ( a1 == -1073741428 )
    return v1;
  if ( a1 > -1073741717 )
  {
    if ( a1 <= -1073741637 )
    {
      if ( a1 == -1073741637 )
        return (unsigned int)-2146893054;
      if ( a1 == -1073741716
        || a1 == -1073741715
        || a1 == -1073741714
        || a1 == -1073741713
        || a1 == -1073741712
        || a1 == -1073741711
        || a1 == -1073741710 )
      {
        return (unsigned int)-2146893044;
      }
      if ( a1 != -1073741670 )
        goto LABEL_93;
      return (unsigned int)-2146893056;
    }
    if ( a1 == -1073741634 || a1 == -1073741601 )
      return (unsigned int)-2146893039;
    if ( a1 == -1073741595 )
      return (unsigned int)-2146893052;
    if ( a1 != -1073741562 )
    {
      if ( a1 == -1073741517 )
        return (unsigned int)-2146893020;
      if ( a1 == -1073741477 )
        return (unsigned int)-2146893044;
      if ( a1 != -1073741429 )
        goto LABEL_93;
      return (unsigned int)-2146893053;
    }
    return (unsigned int)-2146893048;
  }
  if ( a1 == -1073741717 )
    return (unsigned int)-2146893048;
  if ( a1 > -1073741801 )
  {
    if ( a1 == -1073741789 )
      return (unsigned int)-2146893023;
    if ( a1 != -1073741772 )
    {
      if ( a1 != -1073741730 )
      {
        switch ( a1 )
        {
          case -1073741729:
            return (unsigned int)-2146893043;
          case -1073741727:
            return (unsigned int)-2146893050;
          case -1073741724:
            return (unsigned int)-2146893044;
        }
        v2 = a1 == -1073741718;
LABEL_25:
        if ( !v2 )
          goto LABEL_93;
        return (unsigned int)-2146893044;
      }
      return (unsigned int)-2146893039;
    }
    return (unsigned int)-2146893053;
  }
  switch ( a1 )
  {
    case -1073741801:
      return (unsigned int)-2146893056;
    case -2147483635:
      return (unsigned int)-2146893048;
    case -2146885616:
    case -2146885614:
    case -2146885613:
    case -2146869247:
    case -2146762480:
      return (unsigned int)-2146893044;
    case -1073741816:
      return (unsigned int)-2146893055;
    case -1073741811:
      return (unsigned int)-2146893048;
  }
LABEL_93:
  v4 = RtlNtStatusToDosErrorNoTeb(a1);
  v1 = v4;
  if ( v4 >= 0 || (v4 & 0x1FFF0000) != 0x90000 )
    return (unsigned int)-2146893052;
  return v1;
}

```

## disassembly

```asm
0x180006830  sub     rsp, 28h
0x180006834  mov     eax, ecx
0x180006836  mov     edx, ecx
0x180006838  and     eax, 1FFF0000h
0x18000683d  cmp     eax, 90000h
0x180006842  jz      loc_180006918
0x180006848  mov     eax, 0C000018Ch
0x18000684d  cmp     ecx, eax
0x18000684f  jg      loc_1800069F6
0x180006855  jz      loc_180006918
0x18000685b  mov     eax, 0C000006Bh
0x180006860  cmp     ecx, eax
0x180006862  jg      loc_180006935
0x180006868  jz      short loc_1800068C1
0x18000686a  mov     eax, 0C0000017h
0x18000686f  cmp     ecx, eax
0x180006871  jg      short loc_1800068CF
0x180006873  jz      loc_180006984
0x180006879  cmp     ecx, 8000000Dh
0x18000687f  jz      short loc_1800068C1
0x180006881  cmp     ecx, 80092010h
0x180006887  jz      loc_180006913
0x18000688d  cmp     ecx, 80092012h
0x180006893  jz      short loc_180006913
0x180006895  cmp     ecx, 80092013h
0x18000689b  jz      short loc_180006913
0x18000689d  cmp     ecx, 80096001h
0x1800068a3  jz      short loc_180006913
0x1800068a5  cmp     ecx, 800B0110h
0x1800068ab  jz      short loc_180006913
0x1800068ad  cmp     ecx, 0C0000008h
0x1800068b3  jz      short loc_1800068C8
0x1800068b5  cmp     ecx, 0C000000Dh
0x1800068bb  jnz     loc_180006B97
0x1800068c1  mov     edx, 80090308h
0x1800068c6  jmp     short loc_180006918
0x1800068c8  mov     edx, 80090301h
0x1800068cd  jmp     short loc_180006918
0x1800068cf  cmp     edx, 0C0000023h
0x1800068d5  jz      short loc_18000692E
0x1800068d7  cmp     edx, 0C0000034h
0x1800068dd  jz      loc_1800069E2
0x1800068e3  cmp     edx, 0C000005Eh
0x1800068e9  jz      loc_180006AD9
0x1800068ef  cmp     edx, 0C000005Fh
0x1800068f5  jz      short loc_180006927
0x1800068f7  cmp     edx, 0C0000061h
0x1800068fd  jz      short loc_180006920
0x1800068ff  cmp     edx, 0C0000064h
0x180006905  jz      short loc_180006913
0x180006907  cmp     edx, 0C000006Ah
0x18000690d  jnz     loc_180006B97
0x180006913  mov     edx, 8009030Ch
0x180006918  mov     eax, edx
0x18000691a  add     rsp, 28h
0x18000691e  retn
0x180006920  mov     edx, 80090306h
0x180006925  jmp     short loc_180006918
0x180006927  mov     edx, 8009030Dh
0x18000692c  jmp     short loc_180006918
0x18000692e  mov     edx, 80090321h
0x180006933  jmp     short loc_180006918
0x180006935  mov     eax, 0C00000BBh
0x18000693a  cmp     edx, eax
0x18000693c  jg      short loc_180006992
0x18000693e  jz      short loc_18000698B
0x180006940  cmp     edx, 0C000006Ch
0x180006946  jz      short loc_180006913
0x180006948  cmp     edx, 0C000006Dh
0x18000694e  jz      short loc_180006913
0x180006950  cmp     edx, 0C000006Eh
0x180006956  jz      short loc_180006913
0x180006958  cmp     edx, 0C000006Fh
0x18000695e  jz      short loc_180006913
0x180006960  cmp     edx, 0C0000070h
0x180006966  jz      short loc_180006913
0x180006968  cmp     edx, 0C0000071h
0x18000696e  jz      short loc_180006913
0x180006970  cmp     edx, 0C0000072h
0x180006976  jz      short loc_180006913
0x180006978  cmp     edx, 0C000009Ah
0x18000697e  jnz     loc_180006B97
0x180006984  mov     edx, 80090300h
0x180006989  jmp     short loc_180006918
0x18000698b  mov     edx, 80090302h
0x180006990  jmp     short loc_180006918
0x180006992  cmp     edx, 0C00000BEh
0x180006998  jz      loc_180006AD9
0x18000699e  cmp     edx, 0C00000DFh
0x1800069a4  jz      loc_180006AD9
0x1800069aa  cmp     edx, 0C00000E5h
0x1800069b0  jz      loc_180006BBD
0x1800069b6  cmp     edx, 0C0000106h
0x1800069bc  jz      loc_1800068C1
0x1800069c2  cmp     edx, 0C0000133h
0x1800069c8  jz      short loc_1800069EC
0x1800069ca  cmp     edx, 0C000015Bh
0x1800069d0  jz      loc_180006913
0x1800069d6  cmp     edx, 0C000018Bh
0x1800069dc  jnz     loc_180006B97
0x1800069e2  mov     edx, 80090303h
0x1800069e7  jmp     loc_180006918
0x1800069ec  mov     edx, 80090324h
0x1800069f1  jmp     loc_180006918
0x1800069f6  mov     eax, 0C0000380h
0x1800069fb  cmp     edx, eax
0x1800069fd  jg      loc_180006AE3
0x180006a03  jz      loc_180006913
0x180006a09  mov     eax, 0C0000224h
0x180006a0e  cmp     edx, eax
0x180006a10  jg      short loc_180006A7D
0x180006a12  jz      loc_180006913
0x180006a18  cmp     edx, 0C000018Dh
0x180006a1e  jz      loc_180006AD9
0x180006a24  cmp     edx, 0C0000190h
0x180006a2a  jz      loc_180006AD9
0x180006a30  cmp     edx, 0C0000192h
0x180006a36  jz      loc_180006AD9
0x180006a3c  cmp     edx, 0C0000193h
0x180006a42  jz      loc_180006913
0x180006a48  cmp     edx, 0C0000198h
0x180006a4e  jz      loc_180006918
0x180006a54  cmp     edx, 0C0000199h
0x180006a5a  jz      loc_180006918
0x180006a60  cmp     edx, 0C000019Ah
0x180006a66  jz      loc_180006918
0x180006a6c  cmp     edx, 0C000019Bh
0x180006a72  jnz     loc_180006B97
0x180006a78  jmp     loc_180006918
0x180006a7d  cmp     edx, 0C0000233h
0x180006a83  jz      short loc_180006AD9
0x180006a85  cmp     edx, 0C0000234h
0x180006a8b  jz      loc_180006913
0x180006a91  cmp     edx, 0C000023Ch
0x180006a97  jz      short loc_180006AD9
0x180006a99  cmp     edx, 0C00002F9h
0x180006a9f  jz      loc_180006913
0x180006aa5  cmp     edx, 0C00002FEh
0x180006aab  jz      short loc_180006ACF
0x180006aad  cmp     edx, 0C0000320h
0x180006ab3  jz      loc_180006913
0x180006ab9  cmp     edx, 0C000035Bh
0x180006abf  jnz     loc_180006B97
0x180006ac5  mov     edx, 80090346h
0x180006aca  jmp     loc_180006918
0x180006acf  mov     edx, 8009033Fh
0x180006ad4  jmp     loc_180006918
0x180006ad9  mov     edx, 80090311h
0x180006ade  jmp     loc_180006918
0x180006ae3  mov     eax, 0C000038Fh
0x180006ae8  cmp     edx, eax
0x180006aea  jg      short loc_180006B57
0x180006aec  jz      loc_180006913
0x180006af2  cmp     edx, 0C0000381h
0x180006af8  jz      loc_180006913
0x180006afe  cmp     edx, 0C0000383h
0x180006b04  jz      loc_180006913
0x180006b0a  cmp     edx, 0C0000384h
0x180006b10  jz      loc_180006913
0x180006b16  cmp     edx, 0C0000385h
0x180006b1c  jz      loc_180006913
0x180006b22  cmp     edx, 0C0000386h
0x180006b28  jz      loc_180006913
0x180006b2e  cmp     edx, 0C0000387h
0x180006b34  jz      loc_180006913
0x180006b3a  cmp     edx, 0C0000388h
0x180006b40  jz      short loc_180006B4D
0x180006b42  cmp     edx, 0C000038Ch
0x180006b48  jmp     loc_18000690D
0x180006b4d  mov     edx, 80090350h
0x180006b52  jmp     loc_180006918
0x180006b57  cmp     edx, 0C0000408h
0x180006b5d  jz      loc_180006913
0x180006b63  cmp     edx, 0C000040Bh
0x180006b69  jz      short loc_180006BE2
0x180006b6b  cmp     edx, 0C0000413h
0x180006b71  jz      loc_180006918
0x180006b77  cmp     edx, 0C0000418h
0x180006b7d  jz      loc_180006913
0x180006b83  cmp     edx, 0C000042Dh
0x180006b89  jz      short loc_180006BD8
0x180006b8b  cmp     edx, 0C000042Fh
0x180006b91  jz      short loc_180006BCE
0x180006b93  test    edx, edx
0x180006b95  jz      short loc_180006BC7
0x180006b97  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180006b9e  nop     dword ptr [rax+rax+00h]
0x180006ba3  mov     edx, eax
0x180006ba5  test    eax, eax
0x180006ba7  jns     short loc_180006BBD
0x180006ba9  mov     ecx, eax
0x180006bab  and     ecx, 1FFF0000h
0x180006bb1  cmp     ecx, 90000h
0x180006bb7  jz      loc_180006918
0x180006bbd  mov     edx, 80090304h
0x180006bc2  jmp     loc_180006918
0x180006bc7  xor     edx, edx
0x180006bc9  jmp     loc_180006918
0x180006bce  mov     edx, 80090362h
0x180006bd3  jmp     loc_180006918
0x180006bd8  mov     edx, 80090361h
0x180006bdd  jmp     loc_180006918
0x180006be2  mov     edx, 80090357h
0x180006be7  jmp     loc_180006918
```
