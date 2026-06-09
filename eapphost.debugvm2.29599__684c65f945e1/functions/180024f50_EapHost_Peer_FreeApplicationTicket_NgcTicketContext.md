# EapHost::Peer::FreeApplicationTicket(_NgcTicketContext * *)

- ea: `0x180024f50`
- end: `0x1800250b9`
- name: `?FreeApplicationTicket@Peer@EapHost@@YAKPEAPEAU_NgcTicketContext@@@Z`
- size: `361`
- prototype: `unsigned int __fastcall(EapHost::Peer *__hidden this, struct _NgcTicketContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180028820`

## callees

- `0x180009dc4`
- `0x180009dec`
- `0x180024f50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fe8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024fe8`
- `ncrypt!NCryptSetProperty` at `0x180025035`
- `ncrypt!NCryptSetProperty` at `0x180025035`
- `ncrypt!NCryptOpenStorageProvider` at `0x180024f93`
- `ncrypt!NCryptOpenStorageProvider` at `0x180024f93`
- `ncrypt!NCryptFreeObject` at `0x180024ffb`
- `ncrypt!NCryptFreeObject` at `0x180024ffb`

## string_xrefs

- `0x18002502e`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall EapHost::Peer::FreeApplicationTicket(EapHost::Peer *this, struct _NgcTicketContext **a2)
{
  __int64 v2; // rsi
  SECURITY_STATUS v4; // ebx
  __int64 v5; // rdi
  unsigned int v7; // eax
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  phProvider = 0;
  v4 = 0;
  if ( !*(_QWORD *)(v2 + 96) )
    goto LABEL_11;
  v5 = -1;
  do
    ++v5;
  while ( *(_WORD *)(v2 + 2 * v5) );
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  if ( v4 >= 0 )
  {
    v7 = NCryptSetProperty(phProvider, L"PinCacheFreeApplicationTicket", (PBYTE)v2, 2 * v5 + 2, 0x40u);
    v4 = v7;
    if ( v7 )
    {
      if ( v7 == -2146893807 )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids);
        }
      }
      else if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, v7);
      }
      goto LABEL_12;
    }
LABEL_11:
    LocalFree((HLOCAL)v2);
    *(_QWORD *)this = 0;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids, (unsigned int)v4);
  }
  if ( (v4 & 0x1FFF0000) == 0x70000 )
    v4 = (unsigned __int16)v4;
  if ( !v4 )
    goto LABEL_11;
LABEL_12:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180024f50  mov     [rsp+arg_8], rbx
0x180024f55  mov     [rsp+arg_10], rbp
0x180024f5a  push    rsi
0x180024f5b  push    rdi
0x180024f5c  push    r14
0x180024f5e  sub     rsp, 30h
0x180024f62  mov     rsi, [rcx]
0x180024f65  xor     ebp, ebp
0x180024f67  mov     [rsp+48h+phProvider], rbp
0x180024f6c  mov     r14, rcx
0x180024f6f  mov     ebx, ebp
0x180024f71  cmp     [rsi+60h], rbp
0x180024f75  jz      short loc_180024FE5
0x180024f77  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180024f7b  inc     rdi
0x180024f7e  cmp     [rsi+rdi*2], bp
0x180024f82  jnz     short loc_180024F7B
0x180024f84  xor     r8d, r8d; dwFlags
0x180024f87  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180024f8e  lea     rcx, [rsp+48h+phProvider]; phProvider
0x180024f93  call    cs:__imp_NCryptOpenStorageProvider
0x180024f99  mov     ebx, eax
0x180024f9b  test    eax, eax
0x180024f9d  jns     short loc_180025016
0x180024f9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024fa6  lea     rax, WPP_GLOBAL_Control
0x180024fad  cmp     rcx, rax
0x180024fb0  jz      short loc_180024FD0
0x180024fb2  test    byte ptr [rcx+1Ch], 4
0x180024fb6  jz      short loc_180024FD0
0x180024fb8  mov     rcx, [rcx+10h]
0x180024fbc  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180024fc3  mov     edx, 4Fh ; 'O'
0x180024fc8  mov     r9d, ebx
0x180024fcb  call    WPP_SF_d
0x180024fd0  mov     eax, ebx
0x180024fd2  and     eax, 1FFF0000h
0x180024fd7  cmp     eax, 70000h
0x180024fdc  jnz     short loc_180024FE1
0x180024fde  movzx   ebx, bx
0x180024fe1  test    ebx, ebx
0x180024fe3  jnz     short loc_180024FF1
0x180024fe5  mov     rcx, rsi; hMem
0x180024fe8  call    cs:__imp_LocalFree
0x180024fee  mov     [r14], rbp
0x180024ff1  mov     rcx, [rsp+48h+phProvider]; hObject
0x180024ff6  test    rcx, rcx
0x180024ff9  jz      short loc_180025001
0x180024ffb  call    cs:__imp_NCryptFreeObject
0x180025001  mov     rbp, [rsp+48h+arg_10]
0x180025006  mov     eax, ebx
0x180025008  mov     rbx, [rsp+48h+arg_8]
0x18002500d  add     rsp, 30h
0x180025011  pop     r14
0x180025013  pop     rdi
0x180025014  pop     rsi
0x180025015  retn
0x180025016  mov     rcx, [rsp+48h+phProvider]; hObject
0x18002501b  lea     r9d, ds:2[rdi*2]; cbInput
0x180025023  mov     r8, rsi; pbInput
0x180025026  mov     [rsp+48h+dwFlags], 40h ; '@'; dwFlags
0x18002502e  lea     rdx, pszProperty; "PinCacheFreeApplicationTicket"
0x180025035  call    cs:__imp_NCryptSetProperty
0x18002503b  mov     ebx, eax
0x18002503d  test    eax, eax
0x18002503f  jz      short loc_180024FE5
0x180025041  cmp     eax, 80090011h
0x180025046  jnz     short loc_18002507B
0x180025048  mov     rcx, cs:WPP_GLOBAL_Control
0x18002504f  lea     rax, WPP_GLOBAL_Control
0x180025056  cmp     rcx, rax
0x180025059  jz      short loc_180024FF1
0x18002505b  test    byte ptr [rcx+1Ch], 4
0x18002505f  jz      short loc_180024FF1
0x180025061  mov     rcx, [rcx+10h]
0x180025065  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x18002506c  mov     edx, 50h ; 'P'
0x180025071  call    WPP_SF_
0x180025076  jmp     loc_180024FF1
0x18002507b  mov     rcx, cs:WPP_GLOBAL_Control
0x180025082  lea     rax, WPP_GLOBAL_Control
0x180025089  cmp     rcx, rax
0x18002508c  jz      loc_180024FF1
0x180025092  test    byte ptr [rcx+1Ch], 4
0x180025096  jz      loc_180024FF1
0x18002509c  mov     rcx, [rcx+10h]
0x1800250a0  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x1800250a7  mov     edx, 51h ; 'Q'
0x1800250ac  mov     r9d, ebx
0x1800250af  call    WPP_SF_d
0x1800250b4  jmp     loc_180024FF1
```
