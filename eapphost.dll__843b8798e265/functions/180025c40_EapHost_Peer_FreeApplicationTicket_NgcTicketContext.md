# EapHost::Peer::FreeApplicationTicket(_NgcTicketContext * *)

- ea: `0x180025c40`
- end: `0x180025dc6`
- name: `?FreeApplicationTicket@Peer@EapHost@@YAKPEAPEAU_NgcTicketContext@@@Z`
- size: `390`
- prototype: `unsigned int __fastcall(EapHost::Peer *__hidden this, struct _NgcTicketContext **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002960c`

## callees

- `0x18000a21c`
- `0x18000a24c`
- `0x180025c40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ce2`
- `ncrypt!NCryptSetProperty` at `0x180025d3c`
- `ncrypt!NCryptSetProperty` at `0x180025d3c`
- `ncrypt!NCryptOpenStorageProvider` at `0x180025c83`
- `ncrypt!NCryptOpenStorageProvider` at `0x180025c83`
- `ncrypt!NCryptFreeObject` at `0x180025cfb`
- `ncrypt!NCryptFreeObject` at `0x180025cfb`

## string_xrefs

- `0x180025d35`: `PinCacheFreeApplicationTicket`

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
0x180025c40  mov     [rsp+arg_8], rbx
0x180025c45  mov     [rsp+arg_10], rbp
0x180025c4a  push    rsi
0x180025c4b  push    rdi
0x180025c4c  push    r14
0x180025c4e  sub     rsp, 30h
0x180025c52  mov     rsi, [rcx]
0x180025c55  xor     ebp, ebp
0x180025c57  mov     [rsp+48h+phProvider], rbp
0x180025c5c  mov     r14, rcx
0x180025c5f  mov     ebx, ebp
0x180025c61  cmp     [rsi+60h], rbp
0x180025c65  jz      short loc_180025CDF
0x180025c67  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025c6b  inc     rdi
0x180025c6e  cmp     [rsi+rdi*2], bp
0x180025c72  jnz     short loc_180025C6B
0x180025c74  xor     r8d, r8d; dwFlags
0x180025c77  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180025c7e  lea     rcx, [rsp+48h+phProvider]; phProvider
0x180025c83  call    cs:__imp_NCryptOpenStorageProvider
0x180025c8a  nop     dword ptr [rax+rax+00h]
0x180025c8f  mov     ebx, eax
0x180025c91  test    eax, eax
0x180025c93  jns     loc_180025D1D
0x180025c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ca0  lea     rax, WPP_GLOBAL_Control
0x180025ca7  cmp     rcx, rax
0x180025caa  jz      short loc_180025CCA
0x180025cac  test    byte ptr [rcx+1Ch], 4
0x180025cb0  jz      short loc_180025CCA
0x180025cb2  mov     rcx, [rcx+10h]
0x180025cb6  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180025cbd  mov     edx, 4Fh ; 'O'
0x180025cc2  mov     r9d, ebx
0x180025cc5  call    WPP_SF_d
0x180025cca  mov     eax, ebx
0x180025ccc  and     eax, 1FFF0000h
0x180025cd1  cmp     eax, 70000h
0x180025cd6  jnz     short loc_180025CDB
0x180025cd8  movzx   ebx, bx
0x180025cdb  test    ebx, ebx
0x180025cdd  jnz     short loc_180025CF1
0x180025cdf  mov     rcx, rsi; hMem
0x180025ce2  call    cs:__imp_LocalFree
0x180025ce9  nop     dword ptr [rax+rax+00h]
0x180025cee  mov     [r14], rbp
0x180025cf1  mov     rcx, [rsp+48h+phProvider]; hObject
0x180025cf6  test    rcx, rcx
0x180025cf9  jz      short loc_180025D07
0x180025cfb  call    cs:__imp_NCryptFreeObject
0x180025d02  nop     dword ptr [rax+rax+00h]
0x180025d07  mov     rbp, [rsp+48h+arg_10]
0x180025d0c  mov     eax, ebx
0x180025d0e  mov     rbx, [rsp+48h+arg_8]
0x180025d13  add     rsp, 30h
0x180025d17  pop     r14
0x180025d19  pop     rdi
0x180025d1a  pop     rsi
0x180025d1b  retn
0x180025d1d  mov     rcx, [rsp+48h+phProvider]; hObject
0x180025d22  lea     r9d, ds:2[rdi*2]; cbInput
0x180025d2a  mov     r8, rsi; pbInput
0x180025d2d  mov     [rsp+48h+dwFlags], 40h ; '@'; dwFlags
0x180025d35  lea     rdx, pszProperty; "PinCacheFreeApplicationTicket"
0x180025d3c  call    cs:__imp_NCryptSetProperty
0x180025d43  nop     dword ptr [rax+rax+00h]
0x180025d48  mov     ebx, eax
0x180025d4a  test    eax, eax
0x180025d4c  jz      short loc_180025CDF
0x180025d4e  cmp     eax, 80090011h
0x180025d53  jnz     short loc_180025D88
0x180025d55  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d5c  lea     rax, WPP_GLOBAL_Control
0x180025d63  cmp     rcx, rax
0x180025d66  jz      short loc_180025CF1
0x180025d68  test    byte ptr [rcx+1Ch], 4
0x180025d6c  jz      short loc_180025CF1
0x180025d6e  mov     rcx, [rcx+10h]
0x180025d72  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180025d79  mov     edx, 50h ; 'P'
0x180025d7e  call    WPP_SF_
0x180025d83  jmp     loc_180025CF1
0x180025d88  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d8f  lea     rax, WPP_GLOBAL_Control
0x180025d96  cmp     rcx, rax
0x180025d99  jz      loc_180025CF1
0x180025d9f  test    byte ptr [rcx+1Ch], 4
0x180025da3  jz      loc_180025CF1
0x180025da9  mov     rcx, [rcx+10h]
0x180025dad  lea     r8, WPP_17bb9c8b7e153c2f561ce6723573d579_Traceguids
0x180025db4  mov     edx, 51h ; 'Q'
0x180025db9  mov     r9d, ebx
0x180025dbc  call    WPP_SF_d
0x180025dc1  jmp     loc_180025CF1
```
