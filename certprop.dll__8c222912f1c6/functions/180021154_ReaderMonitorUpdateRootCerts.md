# ReaderMonitorUpdateRootCerts

- ea: `0x180021154`
- end: `0x180021217`
- name: `ReaderMonitorUpdateRootCerts`
- size: `195`
- prototype: `__int64 __fastcall(int *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800185d8`

## callees

- `0x180004600`
- `0x180012690`
- `0x180018b58`
- `0x180018bb4`
- `0x180021154`

## pseudocode

```c
__int64 __fastcall ReaderMonitorUpdateRootCerts(int *a1, __int64 a2)
{
  STRSAFE_LPSTR v4; // rcx
  unsigned int RootCertsFromCard; // ebx

  WppTraceIndent(a1, 0);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( a1 && a2 )
  {
    RootCertsFromCard = 0;
    if ( a1[1] )
      RootCertsFromCard = I_ReaderListReadRootCertsFromCard(a1, a2);
  }
  else
  {
    RootCertsFromCard = 87;
  }
  WppTraceIndent(v4, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      240,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      RootCertsFromCard);
  }
  return RootCertsFromCard;
}

```

## disassembly

```asm
0x180021154  push    rbx
0x180021156  push    rbp
0x180021157  push    rsi
0x180021158  push    rdi
0x180021159  sub     rsp, 38h
0x18002115d  mov     rsi, rdx
0x180021160  mov     rdi, rcx
0x180021163  xor     edx, edx
0x180021165  call    WppTraceIndent
0x18002116a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021171  lea     rbp, WPP_GLOBAL_Control
0x180021178  cmp     rcx, rbp
0x18002117b  jz      short loc_1800211A5
0x18002117d  test    byte ptr [rcx+1Ch], 2
0x180021181  jz      short loc_1800211A5
0x180021183  cmp     byte ptr [rcx+19h], 5
0x180021187  jb      short loc_1800211A5
0x180021189  mov     r9, cs:WPP_pszIndent
0x180021190  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180021197  mov     rcx, [rcx+10h]
0x18002119b  mov     edx, 0EFh
0x1800211a0  call    WPP_SF_s
0x1800211a5  test    rdi, rdi
0x1800211a8  jz      short loc_1800211C5
0x1800211aa  test    rsi, rsi
0x1800211ad  jz      short loc_1800211C5
0x1800211af  xor     ebx, ebx
0x1800211b1  cmp     [rdi+4], ebx
0x1800211b4  jz      short loc_1800211CA
0x1800211b6  mov     rdx, rsi
0x1800211b9  mov     rcx, rdi
0x1800211bc  call    I_ReaderListReadRootCertsFromCard
0x1800211c1  mov     ebx, eax
0x1800211c3  jmp     short loc_1800211CA
0x1800211c5  mov     ebx, 57h ; 'W'
0x1800211ca  mov     edx, 1
0x1800211cf  call    WppTraceIndent
0x1800211d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800211db  cmp     rcx, rbp
0x1800211de  jz      short loc_18002120C
0x1800211e0  test    byte ptr [rcx+1Ch], 2
0x1800211e4  jz      short loc_18002120C
0x1800211e6  cmp     byte ptr [rcx+19h], 5
0x1800211ea  jb      short loc_18002120C
0x1800211ec  mov     r9, cs:WPP_pszIndent
0x1800211f3  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x1800211fa  mov     rcx, [rcx+10h]
0x1800211fe  mov     edx, 0F0h
0x180021203  mov     [rsp+58h+var_38], ebx
0x180021207  call    WPP_SF_sD
0x18002120c  mov     eax, ebx
0x18002120e  add     rsp, 38h
0x180021212  pop     rdi
0x180021213  pop     rsi
0x180021214  pop     rbp
0x180021215  pop     rbx
0x180021216  retn
```
