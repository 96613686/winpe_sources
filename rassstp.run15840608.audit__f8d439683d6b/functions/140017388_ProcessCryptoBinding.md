# ProcessCryptoBinding

- ea: `0x140017388`
- end: `0x1400174db`
- name: `ProcessCryptoBinding`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1400155b0`
- `0x1400174f0`

## callees

- `0x140002bd8`
- `0x140002f88`
- `0x140005df2`
- `0x140005e10`
- `0x140006240`
- `0x1400161b0`
- `0x140016414`
- `0x1400169a4`
- `0x140017388`

## pseudocode

```c
void __fastcall ProcessCryptoBinding(__int64 a1, KIRQL a2)
{
  _BYTE v4[4096]; // [rsp+30h] [rbp-1018h] BYREF

  memset(v4, 0, 0xFFFu);
  if ( IsValidCryptoBinding(a1, (__int64)v4, a2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x74u,
        (__int64)WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
    if ( *(_DWORD *)(a1 + 24) == 11 )
    {
      MoveToCallConnectedState(a1, a2);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF__guid_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x75u,
          (__int64)WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids,
          a1 + 364);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x76u,
        (__int64)WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids);
    }
    MoveToAbortState1(a1, 3, 4, 0, 0);
  }
}

```

## disassembly

```asm
0x140017388  mov     [rsp+arg_10], rbx
0x14001738d  mov     [rsp+arg_18], rsi
0x140017392  push    rdi
0x140017393  mov     eax, 1040h
0x140017398  call    __chkstk_0
0x14001739d  sub     rsp, rax
0x1400173a0  mov     rax, cs:__security_cookie
0x1400173a7  xor     rax, rsp
0x1400173aa  mov     [rsp+1048h+var_18], rax
0x1400173b2  mov     sil, dl
0x1400173b5  mov     rdi, rcx
0x1400173b8  xor     edx, edx; Val
0x1400173ba  lea     rcx, [rsp+1048h+var_1018]; void *
0x1400173bf  mov     r8d, 0FFFh; Size
0x1400173c5  call    memset
0x1400173ca  mov     r8b, sil
0x1400173cd  lea     rdx, [rsp+1048h+var_1018]
0x1400173d2  mov     rcx, rdi
0x1400173d5  call    IsValidCryptoBinding
0x1400173da  test    al, al
0x1400173dc  jz      loc_140017464
0x1400173e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400173e9  lea     rbx, WPP_GLOBAL_Control
0x1400173f0  cmp     rcx, rbx
0x1400173f3  jz      short loc_140017417
0x1400173f5  mov     eax, [rcx+2Ch]
0x1400173f8  test    al, 4
0x1400173fa  jz      short loc_140017417
0x1400173fc  cmp     byte ptr [rcx+29h], 2
0x140017400  jb      short loc_140017417
0x140017402  mov     rcx, [rcx+18h]
0x140017406  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001740d  mov     edx, 74h ; 't'
0x140017412  call    WPP_SF_
0x140017417  cmp     dword ptr [rdi+18h], 0Bh
0x14001741b  jnz     short loc_14001742D
0x14001741d  mov     dl, sil
0x140017420  mov     rcx, rdi
0x140017423  call    MoveToCallConnectedState
0x140017428  jmp     loc_1400174B5
0x14001742d  mov     rcx, cs:WPP_GLOBAL_Control
0x140017434  cmp     rcx, rbx
0x140017437  jz      short loc_1400174B5
0x140017439  mov     eax, [rcx+2Ch]
0x14001743c  test    al, 4
0x14001743e  jz      short loc_1400174B5
0x140017440  cmp     byte ptr [rcx+29h], 1
0x140017444  jb      short loc_1400174B5
0x140017446  mov     rcx, [rcx+18h]
0x14001744a  lea     r9, [rdi+16Ch]
0x140017451  mov     edx, 75h ; 'u'
0x140017456  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001745d  call    WPP_SF__guid_
0x140017462  jmp     short loc_1400174B5
0x140017464  mov     rcx, cs:WPP_GLOBAL_Control
0x14001746b  lea     rbx, WPP_GLOBAL_Control
0x140017472  cmp     rcx, rbx
0x140017475  jz      short loc_140017499
0x140017477  mov     eax, [rcx+2Ch]
0x14001747a  test    al, 4
0x14001747c  jz      short loc_140017499
0x14001747e  cmp     byte ptr [rcx+29h], 1
0x140017482  jb      short loc_140017499
0x140017484  mov     rcx, [rcx+18h]
0x140017488  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x14001748f  mov     edx, 76h ; 'v'
0x140017494  call    WPP_SF_
0x140017499  xor     r9d, r9d
0x14001749c  mov     [rsp+1048h+var_1028], 0
0x1400174a5  mov     rcx, rdi
0x1400174a8  lea     edx, [r9+3]
0x1400174ac  lea     r8d, [r9+4]
0x1400174b0  call    MoveToAbortState1
0x1400174b5  mov     rcx, [rsp+1048h+var_18]
0x1400174bd  xor     rcx, rsp; StackCookie
0x1400174c0  call    __security_check_cookie
0x1400174c5  lea     r11, [rsp+1048h+var_8]
0x1400174cd  mov     rbx, [r11+20h]
0x1400174d1  mov     rsi, [r11+28h]
0x1400174d5  mov     rsp, r11
0x1400174d8  pop     rdi
0x1400174d9  retn
```
