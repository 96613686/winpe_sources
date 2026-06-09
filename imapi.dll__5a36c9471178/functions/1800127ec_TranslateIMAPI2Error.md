# TranslateIMAPI2Error

- ea: `0x1800127ec`
- end: `0x180012a25`
- name: `TranslateIMAPI2Error`
- size: `569`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a40`
- `0x180004d50`
- `0x1800056e8`
- `0x180006c20`
- `0x180006d30`
- `0x180006e50`
- `0x180007420`
- `0x18000d830`
- `0x18000ef90`
- `0x18000f2c0`
- `0x18000f520`
- `0x18000f670`
- `0x180012e0c`
- `0x180013108`
- `0x1800134e8`
- `0x1800140ac`
- `0x1800165b4`

## callees

- `0x1800127ec`

## pseudocode

```c
__int64 __fastcall TranslateIMAPI2Error(int a1)
{
  __int64 result; // rax
  bool v2; // zf
  unsigned int v3; // edx

  result = 3232411921LL;
  if ( a1 > -1062555375 )
  {
    if ( a1 <= -1062555333 )
    {
      if ( a1 == -1062555333 )
        return 2147746318LL;
      if ( a1 > -1062555351 )
      {
        if ( a1 == -1062555350 || (unsigned int)(a1 + 1062555344) <= 1 )
          return 2147746318LL;
        if ( a1 != -1062555342 )
        {
          result = 2147746328LL;
          if ( (unsigned int)(a1 + 1062555336) <= 1 )
            return result;
          v2 = a1 == -1062555334;
          goto LABEL_47;
        }
      }
      else
      {
        if ( a1 == -1062555351 )
          return 2147746318LL;
        if ( a1 == -1062555374 )
          return 2147746340LL;
        if ( a1 == -1062555373 || (unsigned int)(a1 + 1062555368) <= 2 || (unsigned int)(a1 + 1062555360) > 1 )
          return 2147746318LL;
      }
      return 2147746332LL;
    }
    if ( a1 > -1062555309 )
    {
      if ( (unsigned int)(a1 + 1062555308) > 3 )
      {
        if ( a1 == -1062555304 )
          return 2147746339LL;
        if ( a1 != -1062555298 )
          return a1 != 11141632 ? 0x8004020E : 0;
      }
    }
    else if ( a1 != -1062555309 )
    {
      switch ( a1 )
      {
        case -1062555328:
          return 2147746318LL;
        case -1062555327:
          return 2147746346LL;
        case -1062555326:
          return 2147746318LL;
      }
      if ( (unsigned int)(a1 + 1062555320) <= 1 )
        return 2147746350LL;
      if ( a1 == -1062555312 )
        return 2147746319LL;
      if ( (unsigned int)(a1 + 1062555311) > 1 )
        return 2147746318LL;
    }
    return 2147746327LL;
  }
  if ( a1 == -1062555375 )
    return result;
  if ( a1 > -1062599680 )
  {
    if ( a1 > -1062555388 )
    {
      if ( a1 != -1062555387 )
      {
        result = 3232411910LL;
        if ( a1 == -1062555386 )
          return result;
      }
    }
    else
    {
      if ( a1 == -1062555388 )
        return 2147746333LL;
      if ( (unsigned int)(a1 + 1062599679) > 3 && (unsigned int)(a1 + 1062555392) > 2 )
      {
        LODWORD(result) = -1062555389;
        v2 = a1 == -1062555389;
        goto LABEL_47;
      }
    }
    return 2147746318LL;
  }
  if ( a1 == -1062599680 )
    return 2147746342LL;
  if ( a1 > -1062600184 )
  {
    if ( a1 == -1062600183 )
      return 2147746348LL;
    if ( (unsigned int)(a1 + 1062600182) <= 2 || (unsigned int)(a1 + 1062600179) > 1 && a1 == -1062599937 )
      return 2147746324LL;
    return 2147746318LL;
  }
  switch ( a1 )
  {
    case -1062600184:
      return 2147746324LL;
    case -1062600702:
      return 2147746317LL;
    case -1062600191:
      return 2147746324LL;
    case -1062600190:
      return 2147746319LL;
    case -1062600189:
      return 2147746320LL;
    case -1062600188:
      return 2147746319LL;
  }
  if ( (unsigned int)(a1 + 1062600187) <= 1 )
    return 2147746342LL;
  LODWORD(result) = -2147220970;
  v2 = a1 == -1062600185;
LABEL_47:
  v3 = -2147220978;
  if ( v2 )
    return (unsigned int)result;
  return v3;
}

```

## disassembly

```asm
0x1800127ec  mov     eax, 0C0AAB111h
0x1800127f1  cmp     ecx, eax
0x1800127f3  jg      loc_18001290B
0x1800127f9  jz      locret_1800129E1
0x1800127ff  mov     eax, 0C0AA0400h
0x180012804  cmp     ecx, eax
0x180012806  jg      loc_1800128AC
0x18001280c  jz      loc_1800128A6
0x180012812  mov     eax, 0C0AA0208h
0x180012817  cmp     ecx, eax
0x180012819  jg      short loc_180012874
0x18001281b  jz      short loc_18001289A
0x18001281d  cmp     ecx, 0C0AA0002h
0x180012823  jz      short loc_18001286E
0x180012825  cmp     ecx, 0C0AA0201h
0x18001282b  jz      short loc_18001289A
0x18001282d  cmp     ecx, 0C0AA0202h
0x180012833  jz      loc_1800129E2
0x180012839  cmp     ecx, 0C0AA0203h
0x18001283f  jz      short loc_180012868
0x180012841  cmp     ecx, 0C0AA0204h
0x180012847  jz      loc_1800129E2
0x18001284d  lea     eax, [rcx+3F55FDFBh]
0x180012853  cmp     eax, 1
0x180012856  jbe     short loc_1800128A6
0x180012858  mov     eax, 80040216h
0x18001285d  cmp     ecx, 0C0AA0207h
0x180012863  jmp     loc_180012984
0x180012868  mov     eax, 80040210h
0x18001286d  retn
0x18001286e  mov     eax, 8004020Dh
0x180012873  retn
0x180012874  cmp     ecx, 0C0AA0209h
0x18001287a  jz      short loc_1800128A0
0x18001287c  lea     eax, [rcx+3F55FDF6h]
0x180012882  cmp     eax, 2
0x180012885  jbe     short loc_18001289A
0x180012887  lea     eax, [rcx+3F55FDF3h]
0x18001288d  cmp     eax, 1
0x180012890  jbe     short loc_180012905
0x180012892  cmp     ecx, 0C0AA02FFh
0x180012898  jnz     short loc_180012905
0x18001289a  mov     eax, 80040214h
0x18001289f  retn
0x1800128a0  mov     eax, 8004022Ch
0x1800128a5  retn
0x1800128a6  mov     eax, 80040226h
0x1800128ab  retn
0x1800128ac  mov     eax, 0C0AAB104h
0x1800128b1  cmp     ecx, eax
0x1800128b3  jg      short loc_1800128DF
0x1800128b5  jz      short loc_1800128D9
0x1800128b7  lea     eax, [rcx+3F55FBFFh]
0x1800128bd  cmp     eax, 3
0x1800128c0  jbe     short loc_180012905
0x1800128c2  lea     eax, [rcx+3F554F00h]
0x1800128c8  cmp     eax, 2
0x1800128cb  jbe     short loc_180012905
0x1800128cd  mov     eax, 0C0AAB103h
0x1800128d2  cmp     ecx, eax
0x1800128d4  jmp     loc_180012984
0x1800128d9  mov     eax, 8004021Dh
0x1800128de  retn
0x1800128df  cmp     ecx, 0C0AAB105h
0x1800128e5  jz      short loc_180012905
0x1800128e7  mov     eax, 0C0AAB106h
0x1800128ec  cmp     ecx, eax
0x1800128ee  jz      locret_1800129E1
0x1800128f4  lea     eax, [rcx+3F554EF8h]
0x1800128fa  cmp     eax, 3
0x1800128fd  jbe     short loc_180012905
0x1800128ff  cmp     ecx, 0C0AAB110h
0x180012905  mov     eax, 8004020Eh
0x18001290a  retn
0x18001290b  mov     eax, 0C0AAB13Bh
0x180012910  cmp     ecx, eax
0x180012912  jg      short loc_18001298F
0x180012914  jz      short loc_180012905
0x180012916  mov     eax, 0C0AAB129h
0x18001291b  cmp     ecx, eax
0x18001291d  jg      short loc_180012953
0x18001291f  jz      short loc_180012905
0x180012921  cmp     ecx, 0C0AAB112h
0x180012927  jz      short loc_18001294D
0x180012929  cmp     ecx, 0C0AAB113h
0x18001292f  jz      short loc_180012905
0x180012931  lea     eax, [rcx+3F554EE8h]
0x180012937  cmp     eax, 2
0x18001293a  jbe     short loc_180012905
0x18001293c  lea     eax, [rcx+3F554EE0h]
0x180012942  cmp     eax, 1
0x180012945  ja      short loc_180012905
0x180012947  mov     eax, 8004021Ch
0x18001294c  retn
0x18001294d  mov     eax, 80040224h
0x180012952  retn
0x180012953  cmp     ecx, 0C0AAB12Ah
0x180012959  jz      short loc_180012905
0x18001295b  lea     eax, [rcx+3F554ED0h]
0x180012961  cmp     eax, 1
0x180012964  jbe     short loc_180012905
0x180012966  cmp     ecx, 0C0AAB132h
0x18001296c  jz      short loc_180012947
0x18001296e  lea     eax, [rcx+3F554EC8h]
0x180012974  cmp     eax, 1
0x180012977  mov     eax, 80040218h
0x18001297c  jbe     short locret_1800129E1
0x18001297e  cmp     ecx, 0C0AAB13Ah
0x180012984  mov     edx, 8004020Eh
0x180012989  cmovz   edx, eax
0x18001298c  mov     eax, edx
0x18001298e  retn
0x18001298f  mov     eax, 0C0AAB153h
0x180012994  cmp     ecx, eax
0x180012996  jg      short loc_1800129F4
0x180012998  jz      short loc_1800129DC
0x18001299a  cmp     ecx, 0C0AAB140h
0x1800129a0  jz      loc_180012905
0x1800129a6  cmp     ecx, 0C0AAB141h
0x1800129ac  jz      short loc_1800129EE
0x1800129ae  cmp     ecx, 0C0AAB142h
0x1800129b4  jz      loc_180012905
0x1800129ba  lea     eax, [rcx+3F554EB8h]
0x1800129c0  cmp     eax, 1
0x1800129c3  jbe     short loc_1800129E8
0x1800129c5  cmp     ecx, 0C0AAB150h
0x1800129cb  jz      short loc_1800129E2
0x1800129cd  lea     eax, [rcx+3F554EAFh]
0x1800129d3  cmp     eax, 1
0x1800129d6  ja      loc_180012905
0x1800129dc  mov     eax, 80040217h
0x1800129e1  retn
0x1800129e2  mov     eax, 8004020Fh
0x1800129e7  retn
0x1800129e8  mov     eax, 8004022Eh
0x1800129ed  retn
0x1800129ee  mov     eax, 8004022Ah
0x1800129f3  retn
0x1800129f4  lea     eax, [rcx+3F554EACh]
0x1800129fa  cmp     eax, 3
0x1800129fd  jbe     short loc_1800129DC
0x1800129ff  cmp     ecx, 0C0AAB158h
0x180012a05  jz      short loc_180012A1F
0x180012a07  cmp     ecx, 0C0AAB15Eh
0x180012a0d  jz      short loc_1800129DC
0x180012a0f  sub     ecx, 0AA0200h
0x180012a15  neg     ecx
0x180012a17  sbb     eax, eax
0x180012a19  and     eax, 8004020Eh
0x180012a1e  retn
0x180012a1f  mov     eax, 80040223h
0x180012a24  retn
```
