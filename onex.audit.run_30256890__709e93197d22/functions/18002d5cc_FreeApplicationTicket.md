# FreeApplicationTicket

- ea: `0x18002d5cc`
- end: `0x18002d735`
- name: `FreeApplicationTicket`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f04c`

## callees

- `0x180005440`
- `0x180010ae0`
- `0x1800214f0`
- `0x18002d5cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d664`
- `ncrypt!NCryptSetProperty` at `0x18002d6b1`
- `ncrypt!NCryptSetProperty` at `0x18002d6b1`
- `ncrypt!NCryptFreeObject` at `0x18002d677`
- `ncrypt!NCryptFreeObject` at `0x18002d677`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002d60f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002d60f`

## string_xrefs

- `0x18002d6aa`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall FreeApplicationTicket(__int64 *a1)
{
  __int64 v1; // rsi
  SECURITY_STATUS v3; // ebx
  __int64 v4; // rdi
  unsigned int v6; // eax
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+8h] BYREF

  v1 = *a1;
  phProvider = 0;
  v3 = 0;
  if ( !*(_QWORD *)(v1 + 96) )
    goto LABEL_11;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(v1 + 2 * v4) );
  v3 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Passport Key Storage Provider", 0);
  if ( v3 >= 0 )
  {
    v6 = NCryptSetProperty(phProvider, L"PinCacheFreeApplicationTicket", (PBYTE)v1, 2 * v4 + 2, 0x40u);
    v3 = v6;
    if ( v6 )
    {
      if ( v6 == -2146893807 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 51, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids);
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 7), 52, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, v6);
      }
      goto LABEL_12;
    }
LABEL_11:
    LocalFree((HLOCAL)v1);
    *a1 = 0;
    goto LABEL_12;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids, (unsigned int)v3);
  if ( (v3 & 0x1FFF0000) == 0x70000 )
    v3 = (unsigned __int16)v3;
  if ( !v3 )
    goto LABEL_11;
LABEL_12:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002d5cc  mov     [rsp+arg_8], rbx
0x18002d5d1  mov     [rsp+arg_10], rbp
0x18002d5d6  push    rsi
0x18002d5d7  push    rdi
0x18002d5d8  push    r14
0x18002d5da  sub     rsp, 30h
0x18002d5de  mov     rsi, [rcx]
0x18002d5e1  xor     ebp, ebp
0x18002d5e3  mov     [rsp+48h+phProvider], rbp
0x18002d5e8  mov     r14, rcx
0x18002d5eb  mov     ebx, ebp
0x18002d5ed  cmp     [rsi+60h], rbp
0x18002d5f1  jz      short loc_18002D661
0x18002d5f3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d5f7  inc     rdi
0x18002d5fa  cmp     [rsi+rdi*2], bp
0x18002d5fe  jnz     short loc_18002D5F7
0x18002d600  xor     r8d, r8d; dwFlags
0x18002d603  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18002d60a  lea     rcx, [rsp+48h+phProvider]; phProvider
0x18002d60f  call    cs:__imp_NCryptOpenStorageProvider
0x18002d615  mov     ebx, eax
0x18002d617  test    eax, eax
0x18002d619  jns     short loc_18002D692
0x18002d61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d622  lea     rax, WPP_GLOBAL_Control
0x18002d629  cmp     rcx, rax
0x18002d62c  jz      short loc_18002D64C
0x18002d62e  test    byte ptr [rcx+44h], 10h
0x18002d632  jz      short loc_18002D64C
0x18002d634  mov     rcx, [rcx+38h]
0x18002d638  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18002d63f  mov     edx, 32h ; '2'
0x18002d644  mov     r9d, ebx
0x18002d647  call    WPP_SF_d
0x18002d64c  mov     eax, ebx
0x18002d64e  and     eax, 1FFF0000h
0x18002d653  cmp     eax, 70000h
0x18002d658  jnz     short loc_18002D65D
0x18002d65a  movzx   ebx, bx
0x18002d65d  test    ebx, ebx
0x18002d65f  jnz     short loc_18002D66D
0x18002d661  mov     rcx, rsi; hMem
0x18002d664  call    cs:__imp_LocalFree
0x18002d66a  mov     [r14], rbp
0x18002d66d  mov     rcx, [rsp+48h+phProvider]; hObject
0x18002d672  test    rcx, rcx
0x18002d675  jz      short loc_18002D67D
0x18002d677  call    cs:__imp_NCryptFreeObject
0x18002d67d  mov     rbp, [rsp+48h+arg_10]
0x18002d682  mov     eax, ebx
0x18002d684  mov     rbx, [rsp+48h+arg_8]
0x18002d689  add     rsp, 30h
0x18002d68d  pop     r14
0x18002d68f  pop     rdi
0x18002d690  pop     rsi
0x18002d691  retn
0x18002d692  mov     rcx, [rsp+48h+phProvider]; hObject
0x18002d697  lea     r9d, ds:2[rdi*2]; cbInput
0x18002d69f  mov     r8, rsi; pbInput
0x18002d6a2  mov     [rsp+48h+dwFlags], 40h ; '@'; dwFlags
0x18002d6aa  lea     rdx, pszProperty; "PinCacheFreeApplicationTicket"
0x18002d6b1  call    cs:__imp_NCryptSetProperty
0x18002d6b7  mov     ebx, eax
0x18002d6b9  test    eax, eax
0x18002d6bb  jz      short loc_18002D661
0x18002d6bd  cmp     eax, 80090011h
0x18002d6c2  jnz     short loc_18002D6F7
0x18002d6c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6cb  lea     rax, WPP_GLOBAL_Control
0x18002d6d2  cmp     rcx, rax
0x18002d6d5  jz      short loc_18002D66D
0x18002d6d7  test    byte ptr [rcx+44h], 10h
0x18002d6db  jz      short loc_18002D66D
0x18002d6dd  mov     rcx, [rcx+38h]
0x18002d6e1  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18002d6e8  mov     edx, 33h ; '3'
0x18002d6ed  call    WPP_SF_
0x18002d6f2  jmp     loc_18002D66D
0x18002d6f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d6fe  lea     rax, WPP_GLOBAL_Control
0x18002d705  cmp     rcx, rax
0x18002d708  jz      loc_18002D66D
0x18002d70e  test    byte ptr [rcx+44h], 10h
0x18002d712  jz      loc_18002D66D
0x18002d718  mov     rcx, [rcx+38h]
0x18002d71c  lea     r8, WPP_28f4580cfa8b3b33a978321bcc095e5a_Traceguids
0x18002d723  mov     edx, 34h ; '4'
0x18002d728  mov     r9d, ebx
0x18002d72b  call    WPP_SF_D
0x18002d730  jmp     loc_18002D66D
```
