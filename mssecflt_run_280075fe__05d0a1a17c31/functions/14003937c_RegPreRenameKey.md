# RegPreRenameKey

- ea: `0x14003937c`
- end: `0x14003958c`
- name: `RegPreRenameKey`
- size: `528`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140033020`

## callees

- `0x140011650`
- `0x140033858`
- `0x14003410c`
- `0x140034adc`
- `0x140034b30`
- `0x14003571c`
- `0x14003588c`
- `0x1400358c0`
- `0x14003937c`

## import_xrefs

- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039529`
- `ntoskrnl!CmCallbackReleaseKeyObjectIDEx` at `0x140039529`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400393f2`
- `ntoskrnl!CmCallbackGetKeyObjectIDEx` at `0x1400393f2`

## pseudocode

```c
__int64 __fastcall RegPreRenameKey(_QWORD *a1)
{
  int KeyObjectIDEx; // edi
  unsigned int v4; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  char v7; // r9
  __int64 v8; // rcx
  PSLIST_ENTRY v9; // rax
  PVOID P; // [rsp+30h] [rbp-30h] BYREF
  PVOID v11; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-20h] BYREF
  struct _SLIST_ENTRY *v13; // [rsp+48h] [rbp-18h] BYREF

  v12 = 0;
  v13 = 0;
  P = 0;
  v11 = 0;
  if ( !a1 )
    return 3221225485LL;
  if ( (xmmword_14001B740 & 0x1000) == 0 )
    return 0;
  KeyObjectIDEx = CmCallbackGetKeyObjectIDEx((char *)RegData + 8, *a1, 0, &v12, 0);
  if ( KeyObjectIDEx >= 0 )
  {
    KeyObjectIDEx = RegpGetKeyDestinationName(v12, a1[1], &v13);
    if ( KeyObjectIDEx >= 0 && (xmmword_14001B740 & 0x1000) != 0 )
    {
      RegMatchData(v12, 0, 4, &P);
      RegMatchData(v13, 0, 4, &v11);
      if ( P )
      {
        if ( v11 )
        {
          v4 = 0;
          if ( *(_DWORD *)v11 )
          {
            do
            {
              v5 = 20LL * v4;
              v6 = *((_QWORD *)v11 + 1);
              v7 = (BYTE8(xmmword_14001B740) & 0x40) != 0 ? *(_BYTE *)(v6 + v5 + 16) : 0;
              v8 = v6 + v5;
              LOBYTE(v6) = v7;
              KeyObjectIDEx = RegAddMatches(v8, v6, &P);
              if ( KeyObjectIDEx < 0 )
                goto LABEL_24;
            }
            while ( ++v4 < *(_DWORD *)v11 );
          }
          *((_DWORD *)P + 5) |= *((_DWORD *)v11 + 5);
        }
        if ( P )
          goto LABEL_21;
      }
      else if ( !v11 )
      {
        KeyObjectIDEx = 0;
        goto LABEL_24;
      }
      P = v11;
      v11 = 0;
LABEL_21:
      v9 = MpRegpAllocRenameKeyContext();
      if ( v9 )
      {
        *((_QWORD *)&v9[3].Next + 1) = P;
        P = 0;
        *((_QWORD *)&v9[2].Next + 1) = v12;
        v12 = 0;
        v9[3].Next = v13;
        v13 = 0;
        MpRegpInsertCallContext(v9);
      }
      else
      {
        KeyObjectIDEx = -1073741670;
      }
    }
  }
LABEL_24:
  if ( v12 )
    CmCallbackReleaseKeyObjectIDEx();
  if ( v13 )
  {
    RegpFreeDestinationKeyName();
    v13 = 0;
  }
  if ( P )
  {
    RegFreeMatchingInfo(P);
    P = 0;
  }
  if ( v11 )
    RegFreeMatchingInfo(v11);
  return (unsigned int)KeyObjectIDEx;
}

```

## disassembly

```asm
0x14003937c  mov     [rsp-8+arg_8], rbx
0x140039381  mov     [rsp-8+arg_10], rsi
0x140039386  mov     [rsp-8+arg_18], rdi
0x14003938b  push    rbp
0x14003938c  mov     rbp, rsp
0x14003938f  sub     rsp, 60h
0x140039393  mov     rax, cs:__security_cookie
0x14003939a  xor     rax, rsp
0x14003939d  mov     [rbp+var_10], rax
0x1400393a1  xor     esi, esi
0x1400393a3  mov     rbx, rcx
0x1400393a6  mov     [rbp+var_20], rsi
0x1400393aa  mov     [rbp+var_18], rsi
0x1400393ae  mov     [rbp+P], rsi
0x1400393b2  mov     [rbp+var_28], rsi
0x1400393b6  test    rcx, rcx
0x1400393b9  jnz     short loc_1400393C5
0x1400393bb  mov     eax, 0C000000Dh
0x1400393c0  jmp     loc_140039569
0x1400393c5  test    qword ptr cs:xmmword_14001B740, 1000h
0x1400393d0  jnz     short loc_1400393D9
0x1400393d2  xor     eax, eax
0x1400393d4  jmp     loc_140039569
0x1400393d9  mov     rcx, cs:RegData
0x1400393e0  lea     r9, [rbp+var_20]
0x1400393e4  mov     rdx, [rbx]
0x1400393e7  add     rcx, 8
0x1400393eb  xor     r8d, r8d
0x1400393ee  mov     [rsp+60h+var_40], esi
0x1400393f2  call    cs:__imp_CmCallbackGetKeyObjectIDEx
0x1400393f9  nop     dword ptr [rax+rax+00h]
0x1400393fe  mov     edi, eax
0x140039400  test    eax, eax
0x140039402  js      loc_140039520
0x140039408  mov     rdx, [rbx+8]
0x14003940c  lea     r8, [rbp+var_18]
0x140039410  mov     rcx, [rbp+var_20]
0x140039414  call    RegpGetKeyDestinationName
0x140039419  mov     edi, eax
0x14003941b  test    eax, eax
0x14003941d  js      loc_140039520
0x140039423  test    qword ptr cs:xmmword_14001B740, 1000h
0x14003942e  mov     ebx, 4
0x140039433  jz      loc_140039520
0x140039439  mov     rcx, [rbp+var_20]
0x14003943d  lea     r9, [rbp+P]
0x140039441  mov     r8d, ebx
0x140039444  xor     edx, edx
0x140039446  call    RegMatchData
0x14003944b  mov     rcx, [rbp+var_18]
0x14003944f  lea     r9, [rbp+var_28]
0x140039453  mov     r8d, ebx
0x140039456  xor     edx, edx
0x140039458  call    RegMatchData
0x14003945d  cmp     [rbp+P], rsi
0x140039461  jnz     short loc_140039470
0x140039463  cmp     [rbp+var_28], rsi
0x140039467  jnz     short loc_1400394D7
0x140039469  mov     edi, esi
0x14003946b  jmp     loc_140039520
0x140039470  mov     rcx, [rbp+var_28]
0x140039474  test    rcx, rcx
0x140039477  jz      short loc_1400394D1
0x140039479  mov     ebx, esi
0x14003947b  cmp     [rcx], esi
0x14003947d  jbe     short loc_1400394C3
0x14003947f  mov     eax, ebx
0x140039481  lea     rcx, [rax+rax*4]
0x140039485  mov     rax, [rbp+var_28]
0x140039489  shl     rcx, 2
0x14003948d  test    byte ptr cs:xmmword_14001B740+8, 40h
0x140039494  mov     rdx, [rax+8]
0x140039498  jz      short loc_1400394A1
0x14003949a  mov     r9b, [rdx+rcx+10h]
0x14003949f  jmp     short loc_1400394A4
0x1400394a1  mov     r9b, sil
0x1400394a4  add     rcx, rdx
0x1400394a7  lea     r8, [rbp+P]
0x1400394ab  mov     dl, r9b
0x1400394ae  call    RegAddMatches
0x1400394b3  mov     edi, eax
0x1400394b5  test    eax, eax
0x1400394b7  js      short loc_140039520
0x1400394b9  mov     rax, [rbp+var_28]
0x1400394bd  inc     ebx
0x1400394bf  cmp     ebx, [rax]
0x1400394c1  jb      short loc_14003947F
0x1400394c3  mov     rax, [rbp+var_28]
0x1400394c7  mov     rdx, [rbp+P]
0x1400394cb  mov     ecx, [rax+14h]
0x1400394ce  or      [rdx+14h], ecx
0x1400394d1  cmp     [rbp+P], rsi
0x1400394d5  jnz     short loc_1400394E3
0x1400394d7  mov     rax, [rbp+var_28]
0x1400394db  mov     [rbp+P], rax
0x1400394df  mov     [rbp+var_28], rsi
0x1400394e3  call    MpRegpAllocRenameKeyContext
0x1400394e8  mov     rcx, rax
0x1400394eb  test    rax, rax
0x1400394ee  jnz     short loc_1400394F7
0x1400394f0  mov     edi, 0C000009Ah
0x1400394f5  jmp     short loc_140039520
0x1400394f7  mov     rax, [rbp+P]
0x1400394fb  mov     [rcx+38h], rax
0x1400394ff  mov     rax, [rbp+var_20]
0x140039503  mov     [rbp+P], rsi
0x140039507  mov     [rcx+28h], rax
0x14003950b  mov     rax, [rbp+var_18]
0x14003950f  mov     [rbp+var_20], rsi
0x140039513  mov     [rcx+30h], rax
0x140039517  mov     [rbp+var_18], rsi
0x14003951b  call    MpRegpInsertCallContext
0x140039520  mov     rcx, [rbp+var_20]
0x140039524  test    rcx, rcx
0x140039527  jz      short loc_140039535
0x140039529  call    cs:__imp_CmCallbackReleaseKeyObjectIDEx
0x140039530  nop     dword ptr [rax+rax+00h]
0x140039535  mov     rcx, [rbp+var_18]
0x140039539  test    rcx, rcx
0x14003953c  jz      short loc_140039547
0x14003953e  call    RegpFreeDestinationKeyName
0x140039543  mov     [rbp+var_18], rsi
0x140039547  mov     rcx, [rbp+P]; P
0x14003954b  test    rcx, rcx
0x14003954e  jz      short loc_140039559
0x140039550  call    RegFreeMatchingInfo
0x140039555  mov     [rbp+P], rsi
0x140039559  mov     rcx, [rbp+var_28]; P
0x14003955d  test    rcx, rcx
0x140039560  jz      short loc_140039567
0x140039562  call    RegFreeMatchingInfo
0x140039567  mov     eax, edi
0x140039569  mov     rcx, [rbp+var_10]
0x14003956d  xor     rcx, rsp; StackCookie
0x140039570  call    __security_check_cookie
0x140039575  lea     r11, [rsp+60h+var_s0]
0x14003957a  mov     rbx, [r11+18h]
0x14003957e  mov     rsi, [r11+20h]
0x140039582  mov     rdi, [r11+28h]
0x140039586  mov     rsp, r11
0x140039589  pop     rbp
0x14003958a  retn
```
