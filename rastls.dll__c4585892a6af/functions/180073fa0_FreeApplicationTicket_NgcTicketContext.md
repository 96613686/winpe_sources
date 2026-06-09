# FreeApplicationTicket(_NgcTicketContext * *)

- ea: `0x180073fa0`
- end: `0x18007410c`
- name: `?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z`
- size: `364`
- prototype: `unsigned int __fastcall(struct _NgcTicketContext **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180024a9c`
- `0x180025ff0`
- `0x1800508d4`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180073fa0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074038`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074038`
- `ncrypt!NCryptOpenStorageProvider` at `0x180073fe3`
- `ncrypt!NCryptOpenStorageProvider` at `0x180073fe3`
- `ncrypt!NCryptSetProperty` at `0x180074092`
- `ncrypt!NCryptSetProperty` at `0x180074092`
- `ncrypt!NCryptFreeObject` at `0x180074051`
- `ncrypt!NCryptFreeObject` at `0x180074051`

## string_xrefs

- `0x18007408b`: `PinCacheFreeApplicationTicket`

## pseudocode

```c
__int64 __fastcall FreeApplicationTicket(struct _NgcTicketContext **a1)
{
  __int64 v1; // rsi
  SECURITY_STATUS v3; // ebx
  __int64 v4; // rdi
  unsigned int v6; // eax
  NCRYPT_PROV_HANDLE phProvider; // [rsp+50h] [rbp+8h] BYREF

  v1 = (__int64)*a1;
  phProvider = 0;
  v3 = 0;
  if ( !*(_QWORD *)(v1 + 96) )
    goto LABEL_10;
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
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_c4e812f99669349517681909258710e2_Traceguids);
      }
      else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_c4e812f99669349517681909258710e2_Traceguids, v6);
      }
      goto LABEL_11;
    }
LABEL_10:
    LocalFree((HLOCAL)v1);
    *a1 = 0;
    goto LABEL_11;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      &WPP_c4e812f99669349517681909258710e2_Traceguids,
      (unsigned int)v3);
  if ( (v3 & 0x1FFF0000) == 0x70000 )
    v3 = (unsigned __int16)v3;
  if ( !v3 )
    goto LABEL_10;
LABEL_11:
  if ( phProvider )
    NCryptFreeObject(phProvider);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180073fa0  mov     [rsp+arg_8], rbx
0x180073fa5  mov     [rsp+arg_10], rbp
0x180073faa  push    rsi
0x180073fab  push    rdi
0x180073fac  push    r14
0x180073fae  sub     rsp, 30h
0x180073fb2  mov     rsi, [rcx]
0x180073fb5  xor     ebp, ebp
0x180073fb7  mov     [rsp+48h+phProvider], rbp
0x180073fbc  mov     r14, rcx
0x180073fbf  mov     ebx, ebp
0x180073fc1  cmp     [rsi+60h], rbp
0x180073fc5  jz      short loc_180074035
0x180073fc7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180073fcb  inc     rdi
0x180073fce  cmp     [rsi+rdi*2], bp
0x180073fd2  jnz     short loc_180073FCB
0x180073fd4  xor     r8d, r8d; dwFlags
0x180073fd7  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180073fde  lea     rcx, [rsp+48h+phProvider]; phProvider
0x180073fe3  call    cs:__imp_NCryptOpenStorageProvider
0x180073fea  nop     dword ptr [rax+rax+00h]
0x180073fef  mov     ebx, eax
0x180073ff1  test    eax, eax
0x180073ff3  jns     short loc_180074073
0x180073ff5  mov     rcx, cs:WPP_GLOBAL_Control
0x180073ffc  lea     rax, WPP_GLOBAL_Control
0x180074003  cmp     rcx, rax
0x180074006  jz      short loc_180074020
0x180074008  mov     rcx, [rcx+10h]
0x18007400c  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x180074013  mov     edx, 16h
0x180074018  mov     r9d, ebx
0x18007401b  call    WPP_SF_d
0x180074020  mov     eax, ebx
0x180074022  and     eax, 1FFF0000h
0x180074027  cmp     eax, 70000h
0x18007402c  jnz     short loc_180074031
0x18007402e  movzx   ebx, bx
0x180074031  test    ebx, ebx
0x180074033  jnz     short loc_180074047
0x180074035  mov     rcx, rsi; hMem
0x180074038  call    cs:__imp_LocalFree
0x18007403f  nop     dword ptr [rax+rax+00h]
0x180074044  mov     [r14], rbp
0x180074047  mov     rcx, [rsp+48h+phProvider]; hObject
0x18007404c  test    rcx, rcx
0x18007404f  jz      short loc_18007405D
0x180074051  call    cs:__imp_NCryptFreeObject
0x180074058  nop     dword ptr [rax+rax+00h]
0x18007405d  mov     rbp, [rsp+48h+arg_10]
0x180074062  mov     eax, ebx
0x180074064  mov     rbx, [rsp+48h+arg_8]
0x180074069  add     rsp, 30h
0x18007406d  pop     r14
0x18007406f  pop     rdi
0x180074070  pop     rsi
0x180074071  retn
0x180074073  mov     rcx, [rsp+48h+phProvider]; hObject
0x180074078  lea     r9d, ds:2[rdi*2]; cbInput
0x180074080  mov     r8, rsi; pbInput
0x180074083  mov     [rsp+48h+dwFlags], 40h ; '@'; dwFlags
0x18007408b  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x180074092  call    cs:__imp_NCryptSetProperty
0x180074099  nop     dword ptr [rax+rax+00h]
0x18007409e  mov     ebx, eax
0x1800740a0  test    eax, eax
0x1800740a2  jz      short loc_180074035
0x1800740a4  cmp     eax, 80090011h
0x1800740a9  jnz     short loc_1800740D8
0x1800740ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800740b2  lea     rax, WPP_GLOBAL_Control
0x1800740b9  cmp     rcx, rax
0x1800740bc  jz      short loc_180074047
0x1800740be  mov     rcx, [rcx+10h]
0x1800740c2  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800740c9  mov     edx, 17h
0x1800740ce  call    WPP_SF_
0x1800740d3  jmp     loc_180074047
0x1800740d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800740df  lea     rax, WPP_GLOBAL_Control
0x1800740e6  cmp     rcx, rax
0x1800740e9  jz      loc_180074047
0x1800740ef  mov     rcx, [rcx+10h]
0x1800740f3  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x1800740fa  mov     edx, 18h
0x1800740ff  mov     r9d, ebx
0x180074102  call    WPP_SF_d
0x180074107  jmp     loc_180074047
```
