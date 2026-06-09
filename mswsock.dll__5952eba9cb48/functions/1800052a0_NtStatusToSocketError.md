# NtStatusToSocketError

- ea: `0x1800052a0`
- end: `0x180005807`
- name: `NtStatusToSocketError`
- size: `1383`
- prototype: ``
- caller_count: `66`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e60`
- `0x18000203c`
- `0x180002240`
- `0x180004620`
- `0x180004700`
- `0x180005810`
- `0x1800060e0`
- `0x180007080`
- `0x180008320`
- `0x180008870`
- `0x180008cb0`
- `0x180009a08`
- `0x180009d20`
- `0x18000a6b0`
- `0x18000c2b0`
- `0x18000ca60`
- `0x18000d000`
- `0x18000de00`
- `0x18000ea70`
- `0x18000faa0`
- `0x18000fe60`
- `0x180010030`
- `0x180012600`
- `0x180012c10`
- `0x180013234`
- `0x1800133cc`
- `0x180013520`
- `0x180013670`
- `0x180014030`
- `0x180014420`
- `0x180016b30`
- `0x1800182d0`
- `0x180018750`
- `0x180019368`
- `0x1800198a0`
- `0x18001bc7c`
- `0x18001be40`
- `0x18001c2a0`
- `0x18001c860`
- `0x18001ca90`
- `0x18001d4e8`
- `0x18001d600`
- `0x18001d8ac`
- `0x18001d990`
- `0x18001ed78`
- `0x1800216a8`
- `0x180021800`
- `0x180023030`
- `0x1800248fc`
- `0x180025530`

## callees

- `0x1800052a0`
- `0x18003aec4`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800052a8`
- `ntdll!RtlNtStatusToDosError` at `0x1800052a8`

## pseudocode

```c
__int64 __fastcall NtStatusToSocketError(NTSTATUS a1)
{
  __int64 v2; // rcx
  __int64 result; // rax

  RtlNtStatusToDosError(a1);
  if ( a1 == -1073741616 )
    return 10035;
  if ( a1 <= -1073741536 )
  {
    if ( a1 == -1073741536 )
      return 10004;
    if ( a1 <= -1073741823 )
    {
      if ( a1 == -1073741823 )
        return 10022;
      if ( a1 == -2147483643 )
        return 10040;
LABEL_32:
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_l(v2, 11, WPP_97dcf1eb61bd3c9fe009df6b3349ea30_Traceguids, (unsigned int)a1);
      return 10022;
    }
    switch ( a1 )
    {
      case -1073741822:
      case -1073741637:
        result = 10045;
        break;
      case -1073741819:
      case -1073741789:
LABEL_45:
        result = 10014;
        break;
      case -1073741817:
      case -1073741801:
      case -1073741800:
      case -1073741756:
      case -1073741673:
      case -1073741670:
      case -1073741663:
LABEL_22:
        result = 10055;
        break;
      case -1073741816:
      case -1073741788:
        result = 10038;
        break;
      case -1073741811:
      case -1073741808:
        return 10022;
      case -1073741810:
      case -1073741809:
      case -1073741772:
      case -1073741766:
      case -1073741633:
      case -1073741629:
      case -1073741628:
        result = 10050;
        break;
      case -1073741790:
        result = 10013;
        break;
      case -1073741757:
LABEL_42:
        result = 10048;
        break;
      case -1073741661:
        return 10035;
      case -1073741648:
        result = 10058;
        break;
      case -1073741643:
        return 10060;
      case -1073741636:
        return 10061;
      case -1073741634:
LABEL_19:
        result = 10051;
        break;
      default:
        goto LABEL_32;
    }
  }
  else
  {
    if ( a1 > -1073741258 )
    {
      if ( a1 <= -1073740976 )
      {
        if ( a1 == -1073740976 )
          return 10064;
        switch ( a1 )
        {
          case -1073741257:
            result = 10101;
            break;
          case -1073741256:
          case -1073741255:
          case -1073741254:
            return 10022;
          case -1073741253:
            result = 10056;
            break;
          case -1073741252:
          case -1073741250:
            goto LABEL_19;
          case -1073741251:
            result = 10065;
            break;
          case -1073741249:
            goto LABEL_9;
          case -1073741248:
            return 10004;
          case -1073741247:
            goto LABEL_38;
          case -1073741115:
            goto LABEL_45;
          default:
            goto LABEL_32;
        }
        return result;
      }
      if ( a1 == -1073700845 )
        return 10047;
      if ( a1 == -1073700846 )
        return 10052;
      if ( a1 )
      {
        if ( a1 == 258 )
          return 10060;
        if ( a1 == 259 )
          return 997;
        if ( a1 < 0 )
          goto LABEL_32;
        if ( (xmmword_180063D60 & 2) != 0 )
          WPP_SF_l(v2, 10, WPP_97dcf1eb61bd3c9fe009df6b3349ea30_Traceguids, (unsigned int)a1);
      }
      return 0;
    }
    if ( a1 == -1073741258 )
    {
      return 10061;
    }
    else
    {
      switch ( a1 )
      {
        case -1073741523:
        case -1073741507:
        case -1073741303:
          goto LABEL_22;
        case -1073741509:
        case -1073741297:
LABEL_38:
          result = 10053;
          break;
        case -1073741508:
        case -1073741506:
        case -1073741300:
        case -1073741299:
LABEL_9:
          result = 10054;
          break;
        case -1073741505:
          return 10060;
        case -1073741504:
          result = 10057;
          break;
        case -1073741503:
        case -1073741305:
          result = 10049;
          break;
        case -1073741436:
        case -1073741301:
          return 10022;
        case -1073741306:
          return 10040;
        case -1073741302:
          goto LABEL_42;
        default:
          goto LABEL_32;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800052a0  push    rbx
0x1800052a2  sub     rsp, 20h
0x1800052a6  mov     ebx, ecx
0x1800052a8  call    cs:__imp_RtlNtStatusToDosError
0x1800052af  nop     dword ptr [rax+rax+00h]
0x1800052b4  cmp     ebx, 0C00000D0h
0x1800052ba  jnz     short loc_1800052C8
0x1800052bc  mov     eax, 2733h; jumptable 000000018000536A case -1073741661
0x1800052c1  add     rsp, 20h
0x1800052c5  pop     rbx
0x1800052c6  retn
0x1800052c8  cmp     ebx, 0C0000120h
0x1800052ce  jle     short loc_18000532C
0x1800052d0  cmp     ebx, 0C0000236h
0x1800052d6  jle     loc_1800053BC
0x1800052dc  cmp     ebx, 0C0000350h
0x1800052e2  jg      loc_18000537C
0x1800052e8  jz      loc_1800054F0
0x1800052ee  lea     eax, [rbx+3FFFFDC9h]; switch 143 cases
0x1800052f4  cmp     eax, 8Eh
0x1800052f9  ja      def_18000531A; jumptable 000000018000531A default case, cases -1073741246--1073741116
0x1800052ff  lea     rdx, __ImageBase
0x180005306  cdqe
0x180005308  movzx   eax, ds:(byte_180005570 - 180000000h)[rdx+rax]
0x180005310  mov     ecx, ds:(jpt_18000531A - 180000000h)[rdx+rax*4]
0x180005317  add     rcx, rdx
0x18000531a  jmp     rcx; switch jump
0x180005320  mov     eax, 2746h; jumptable 000000018000531A case -1073741249
0x180005325  add     rsp, 20h
0x180005329  pop     rbx
0x18000532a  retn
0x18000532c  jz      loc_1800054D2; jumptable 000000018000531A case -1073741248
0x180005332  cmp     ebx, 0C0000001h
0x180005338  jle     loc_18000547D
0x18000533e  lea     eax, [rbx+3FFFFFFEh]; switch 195 cases
0x180005344  cmp     eax, 0C2h
0x180005349  ja      def_18000531A; jumptable 000000018000531A default case, cases -1073741246--1073741116
0x18000534f  lea     rdx, __ImageBase
0x180005356  cdqe
0x180005358  movzx   eax, ds:(byte_180005638 - 180000000h)[rdx+rax]
0x180005360  mov     ecx, ds:(jpt_18000536A - 180000000h)[rdx+rax*4]
0x180005367  add     rcx, rdx
0x18000536a  jmp     rcx; switch jump
0x180005370  mov     eax, 2736h; jumptable 000000018000536A cases -1073741816,-1073741788
0x180005375  add     rsp, 20h
0x180005379  pop     rbx
0x18000537a  retn
0x18000537c  cmp     ebx, 0C000A013h
0x180005382  jz      short loc_1800053FC
0x180005384  cmp     ebx, 0C000A012h
0x18000538a  jz      loc_18000553C
0x180005390  test    ebx, ebx
0x180005392  jz      loc_1800054B5
0x180005398  cmp     ebx, 102h
0x18000539e  jnz     loc_180005450
0x1800053a4  mov     eax, 274Ch; jumptable 000000018000536A case -1073741643
0x1800053a9  add     rsp, 20h
0x1800053ad  pop     rbx
0x1800053ae  retn
0x1800053b0  mov     eax, 2743h; jumptable 000000018000531A cases -1073741252,-1073741250
0x1800053b5  add     rsp, 20h
0x1800053b9  pop     rbx
0x1800053ba  retn
0x1800053bc  jz      short loc_180005420; jumptable 000000018000536A case -1073741636
0x1800053be  lea     eax, [rbx+3FFFFED3h]; switch 227 cases
0x1800053c4  cmp     eax, 0E2h
0x1800053c9  ja      def_18000531A; jumptable 000000018000531A default case, cases -1073741246--1073741116
0x1800053cf  lea     rdx, __ImageBase
0x1800053d6  cdqe
0x1800053d8  movzx   eax, ds:(byte_180005724 - 180000000h)[rdx+rax]
0x1800053e0  mov     ecx, ds:(jpt_1800053EA - 180000000h)[rdx+rax*4]
0x1800053e7  add     rcx, rdx
0x1800053ea  jmp     rcx; switch jump
0x1800053f0  mov     eax, 2747h; jumptable 000000018000536A cases -1073741817,-1073741801,-1073741800,-1073741756,-1073741673,-1073741670,-1073741663
0x1800053f5  add     rsp, 20h
0x1800053f9  pop     rbx
0x1800053fa  retn
0x1800053fc  mov     eax, 273Fh
0x180005401  add     rsp, 20h
0x180005405  pop     rbx
0x180005406  retn
0x180005408  mov     eax, 274Ah; jumptable 000000018000536A case -1073741648
0x18000540d  add     rsp, 20h
0x180005411  pop     rbx
0x180005412  retn
0x180005414  mov     eax, 2741h; jumptable 00000001800053EA cases -1073741503,-1073741305
0x180005419  add     rsp, 20h
0x18000541d  pop     rbx
0x18000541e  retn
0x180005420  mov     eax, 274Dh; jumptable 000000018000536A case -1073741636
0x180005425  add     rsp, 20h
0x180005429  pop     rbx
0x18000542a  retn
0x18000542c  mov     eax, 273Dh; jumptable 000000018000536A cases -1073741822,-1073741637
0x180005431  add     rsp, 20h
0x180005435  pop     rbx
0x180005436  retn
0x180005438  mov     eax, 2749h; jumptable 00000001800053EA case -1073741504
0x18000543d  add     rsp, 20h
0x180005441  pop     rbx
0x180005442  retn
0x180005444  mov     eax, 2751h; jumptable 000000018000531A case -1073741251
0x180005449  add     rsp, 20h
0x18000544d  pop     rbx
0x18000544e  retn
0x180005450  cmp     ebx, 103h
0x180005456  jz      loc_180005532
0x18000545c  test    ebx, ebx
0x18000545e  jns     loc_1800054FA
0x180005464  test    byte ptr cs:xmmword_180063D60, 2; jumptable 000000018000531A default case, cases -1073741246--1073741116
0x18000546b  jnz     loc_180005519
0x180005471  mov     eax, 2726h; jumptable 000000018000531A cases -1073741256--1073741254
0x180005476  add     rsp, 20h
0x18000547a  pop     rbx
0x18000547b  retn
0x18000547d  jz      short loc_180005471; jumptable 000000018000531A cases -1073741256--1073741254
0x18000547f  cmp     ebx, 80000005h
0x180005485  jnz     short def_18000531A; jumptable 000000018000531A default case, cases -1073741246--1073741116
0x180005487  mov     eax, 2738h; jumptable 00000001800053EA case -1073741306
0x18000548c  jmp     loc_1800052C1
0x180005491  mov     eax, 2745h; jumptable 000000018000531A case -1073741247
0x180005496  add     rsp, 20h
0x18000549a  pop     rbx
0x18000549b  retn
0x18000549d  mov     eax, 271Dh; jumptable 000000018000536A case -1073741790
0x1800054a2  add     rsp, 20h
0x1800054a6  pop     rbx
0x1800054a7  retn
0x1800054a9  mov     eax, 2742h; jumptable 000000018000536A cases -1073741810,-1073741809,-1073741772,-1073741766,-1073741633,-1073741629,-1073741628
0x1800054ae  add     rsp, 20h
0x1800054b2  pop     rbx
0x1800054b3  retn
0x1800054b5  xor     eax, eax
0x1800054b7  add     rsp, 20h
0x1800054bb  pop     rbx
0x1800054bc  retn
0x1800054be  mov     eax, 2740h; jumptable 000000018000536A case -1073741757
0x1800054c3  jmp     loc_1800052C1
0x1800054c8  mov     eax, 2775h; jumptable 000000018000531A case -1073741257
0x1800054cd  jmp     loc_1800052C1
0x1800054d2  mov     eax, 2714h; jumptable 000000018000531A case -1073741248
0x1800054d7  jmp     loc_1800052C1
0x1800054dc  mov     eax, 271Eh; jumptable 000000018000531A case -1073741115
0x1800054e1  jmp     loc_1800052C1
0x1800054e6  mov     eax, 2748h; jumptable 000000018000531A case -1073741253
0x1800054eb  jmp     loc_1800052C1
0x1800054f0  mov     eax, 2750h
0x1800054f5  jmp     loc_1800052C1
0x1800054fa  test    byte ptr cs:xmmword_180063D60, 2
0x180005501  jz      short loc_1800054B5
0x180005503  mov     edx, 0Ah
0x180005508  lea     r8, WPP_97dcf1eb61bd3c9fe009df6b3349ea30_Traceguids
0x18000550f  mov     r9d, ebx
0x180005512  call    WPP_SF_l
0x180005517  jmp     short loc_1800054B5
0x180005519  mov     edx, 0Bh
0x18000551e  lea     r8, WPP_97dcf1eb61bd3c9fe009df6b3349ea30_Traceguids
0x180005525  mov     r9d, ebx
0x180005528  call    WPP_SF_l
0x18000552d  jmp     loc_180005471; jumptable 000000018000531A cases -1073741256--1073741254
0x180005532  mov     eax, 3E5h
0x180005537  jmp     loc_1800052C1
0x18000553c  mov     eax, 2744h
0x180005541  jmp     loc_1800052C1
```
