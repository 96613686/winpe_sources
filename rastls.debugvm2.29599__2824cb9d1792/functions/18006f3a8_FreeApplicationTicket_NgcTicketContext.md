# FreeApplicationTicket(_NgcTicketContext * *)

- ea: `0x18006f3a8`
- end: `0x18006f4fb`
- name: `?FreeApplicationTicket@@YAKPEAPEAU_NgcTicketContext@@@Z`
- size: `339`
- prototype: `unsigned int __fastcall(struct _NgcTicketContext **)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022290`
- `0x1800234e0`
- `0x18004ddc8`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x18006f3a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f43a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006f43a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006f3eb`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006f3eb`
- `ncrypt!NCryptSetProperty` at `0x18006f487`
- `ncrypt!NCryptSetProperty` at `0x18006f487`
- `ncrypt!NCryptFreeObject` at `0x18006f44d`
- `ncrypt!NCryptFreeObject` at `0x18006f44d`

## string_xrefs

- `0x18006f480`: `PinCacheFreeApplicationTicket`

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
0x18006f3a8  mov     [rsp+arg_8], rbx
0x18006f3ad  mov     [rsp+arg_10], rbp
0x18006f3b2  push    rsi
0x18006f3b3  push    rdi
0x18006f3b4  push    r14
0x18006f3b6  sub     rsp, 30h
0x18006f3ba  mov     rsi, [rcx]
0x18006f3bd  xor     ebp, ebp
0x18006f3bf  mov     [rsp+48h+phProvider], rbp
0x18006f3c4  mov     r14, rcx
0x18006f3c7  mov     ebx, ebp
0x18006f3c9  cmp     [rsi+60h], rbp
0x18006f3cd  jz      short loc_18006F437
0x18006f3cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006f3d3  inc     rdi
0x18006f3d6  cmp     [rsi+rdi*2], bp
0x18006f3da  jnz     short loc_18006F3D3
0x18006f3dc  xor     r8d, r8d; dwFlags
0x18006f3df  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x18006f3e6  lea     rcx, [rsp+48h+phProvider]; phProvider
0x18006f3eb  call    cs:__imp_NCryptOpenStorageProvider
0x18006f3f1  mov     ebx, eax
0x18006f3f3  test    eax, eax
0x18006f3f5  jns     short loc_18006F468
0x18006f3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f3fe  lea     rax, WPP_GLOBAL_Control
0x18006f405  cmp     rcx, rax
0x18006f408  jz      short loc_18006F422
0x18006f40a  mov     rcx, [rcx+10h]
0x18006f40e  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f415  mov     edx, 16h
0x18006f41a  mov     r9d, ebx
0x18006f41d  call    WPP_SF_d
0x18006f422  mov     eax, ebx
0x18006f424  and     eax, 1FFF0000h
0x18006f429  cmp     eax, 70000h
0x18006f42e  jnz     short loc_18006F433
0x18006f430  movzx   ebx, bx
0x18006f433  test    ebx, ebx
0x18006f435  jnz     short loc_18006F443
0x18006f437  mov     rcx, rsi; hMem
0x18006f43a  call    cs:__imp_LocalFree
0x18006f440  mov     [r14], rbp
0x18006f443  mov     rcx, [rsp+48h+phProvider]; hObject
0x18006f448  test    rcx, rcx
0x18006f44b  jz      short loc_18006F453
0x18006f44d  call    cs:__imp_NCryptFreeObject
0x18006f453  mov     rbp, [rsp+48h+arg_10]
0x18006f458  mov     eax, ebx
0x18006f45a  mov     rbx, [rsp+48h+arg_8]
0x18006f45f  add     rsp, 30h
0x18006f463  pop     r14
0x18006f465  pop     rdi
0x18006f466  pop     rsi
0x18006f467  retn
0x18006f468  mov     rcx, [rsp+48h+phProvider]; hObject
0x18006f46d  lea     r9d, ds:2[rdi*2]; cbInput
0x18006f475  mov     r8, rsi; pbInput
0x18006f478  mov     [rsp+48h+dwFlags], 40h ; '@'; dwFlags
0x18006f480  lea     rdx, aPincachefreeap; "PinCacheFreeApplicationTicket"
0x18006f487  call    cs:__imp_NCryptSetProperty
0x18006f48d  mov     ebx, eax
0x18006f48f  test    eax, eax
0x18006f491  jz      short loc_18006F437
0x18006f493  cmp     eax, 80090011h
0x18006f498  jnz     short loc_18006F4C7
0x18006f49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f4a1  lea     rax, WPP_GLOBAL_Control
0x18006f4a8  cmp     rcx, rax
0x18006f4ab  jz      short loc_18006F443
0x18006f4ad  mov     rcx, [rcx+10h]
0x18006f4b1  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f4b8  mov     edx, 17h
0x18006f4bd  call    WPP_SF_
0x18006f4c2  jmp     loc_18006F443
0x18006f4c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006f4ce  lea     rax, WPP_GLOBAL_Control
0x18006f4d5  cmp     rcx, rax
0x18006f4d8  jz      loc_18006F443
0x18006f4de  mov     rcx, [rcx+10h]
0x18006f4e2  lea     r8, WPP_c4e812f99669349517681909258710e2_Traceguids
0x18006f4e9  mov     edx, 18h
0x18006f4ee  mov     r9d, ebx
0x18006f4f1  call    WPP_SF_d
0x18006f4f6  jmp     loc_18006F443
```
