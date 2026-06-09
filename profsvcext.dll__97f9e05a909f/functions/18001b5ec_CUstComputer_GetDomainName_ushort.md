# CUstComputer::GetDomainName(ushort * *)

- ea: `0x18001b5ec`
- end: `0x18001b7b6`
- name: `?GetDomainName@CUstComputer@@SAJPEAPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001b214`

## callees

- `0x18001afc8`
- `0x18001b008`
- `0x18001b5ec`
- `0x18001d264`

## import_xrefs

- `logoncli!DsGetDcNameW` at `0x18001b61d`
- `logoncli!DsGetDcNameW` at `0x18001b61d`
- `netutils!NetApiBufferFree` at `0x18001b7a5`
- `netutils!NetApiBufferFree` at `0x18001b7a5`

## pseudocode

```c
__int64 __fastcall CUstComputer::GetDomainName(unsigned __int16 **a1)
{
  signed int DcNameW; // eax
  unsigned int StringCopy; // ebx
  UstCommon::CImpersonator *v4; // rcx
  PDOMAIN_CONTROLLER_INFOW DomainControllerInfo; // [rsp+68h] [rbp+10h] BYREF

  DomainControllerInfo = 0;
  DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x40008000u, &DomainControllerInfo);
  StringCopy = DcNameW;
  if ( !DcNameW )
  {
    v4 = WPP_GLOBAL_Control;
LABEL_10:
    if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
      {
        WPP_SF_S(
          *((_QWORD *)v4 + 2),
          37,
          WPP_ab0185983553356c12180ac14bccd298_Traceguids,
          DomainControllerInfo->DomainControllerName);
        v4 = WPP_GLOBAL_Control;
      }
      if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
        {
          WPP_SF_S(
            *((_QWORD *)v4 + 2),
            38,
            WPP_ab0185983553356c12180ac14bccd298_Traceguids,
            DomainControllerInfo->DomainControllerAddress);
          v4 = WPP_GLOBAL_Control;
        }
        if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
          {
            WPP_SF_S(
              *((_QWORD *)v4 + 2),
              39,
              WPP_ab0185983553356c12180ac14bccd298_Traceguids,
              DomainControllerInfo->DomainName);
            v4 = WPP_GLOBAL_Control;
          }
          if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
            {
              WPP_SF_S(
                *((_QWORD *)v4 + 2),
                40,
                WPP_ab0185983553356c12180ac14bccd298_Traceguids,
                DomainControllerInfo->DnsForestName);
              v4 = WPP_GLOBAL_Control;
            }
            if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v4 + 28) & 2) != 0 )
              {
                WPP_SF_S(
                  *((_QWORD *)v4 + 2),
                  41,
                  WPP_ab0185983553356c12180ac14bccd298_Traceguids,
                  DomainControllerInfo->DcSiteName);
                v4 = WPP_GLOBAL_Control;
              }
              if ( v4 != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 )
                WPP_SF_S(
                  *((_QWORD *)v4 + 2),
                  42,
                  WPP_ab0185983553356c12180ac14bccd298_Traceguids,
                  DomainControllerInfo->ClientSiteName);
            }
          }
        }
      }
    }
    StringCopy = CUstUtil::CreateStringCopy(DomainControllerInfo->DomainName, a1);
    goto LABEL_29;
  }
  if ( DcNameW > 0 )
    StringCopy = (unsigned __int16)DcNameW | 0x80070000;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_ab0185983553356c12180ac14bccd298_Traceguids, StringCopy);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (StringCopy & 0x80000000) == 0 )
    goto LABEL_10;
LABEL_29:
  if ( DomainControllerInfo )
    NetApiBufferFree(DomainControllerInfo);
  return StringCopy;
}

```

## disassembly

```asm
0x18001b5ec  push    rbx
0x18001b5ee  push    rbp
0x18001b5ef  push    rsi
0x18001b5f0  push    rdi
0x18001b5f1  sub     rsp, 38h
0x18001b5f5  lea     rax, [rsp+58h+arg_8]
0x18001b5fa  mov     [rsp+58h+arg_8], 0
0x18001b603  mov     rdi, rcx
0x18001b606  mov     [rsp+58h+DomainControllerInfo], rax; DomainControllerInfo
0x18001b60b  xor     r9d, r9d; SiteName
0x18001b60e  mov     [rsp+58h+Flags], 40008000h; Flags
0x18001b616  xor     r8d, r8d; DomainGuid
0x18001b619  xor     edx, edx; DomainName
0x18001b61b  xor     ecx, ecx; ComputerName
0x18001b61d  call    cs:__imp_DsGetDcNameW
0x18001b623  lea     rsi, WPP_GLOBAL_Control
0x18001b62a  mov     ebx, eax
0x18001b62c  lea     rbp, WPP_ab0185983553356c12180ac14bccd298_Traceguids
0x18001b633  test    eax, eax
0x18001b635  jz      short loc_18001B679
0x18001b637  jle     short loc_18001B642
0x18001b639  movzx   ebx, ax
0x18001b63c  or      ebx, 80070000h
0x18001b642  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b649  cmp     rcx, rsi
0x18001b64c  jz      short loc_18001B66F
0x18001b64e  test    byte ptr [rcx+1Ch], 1
0x18001b652  jz      short loc_18001B66F
0x18001b654  mov     rcx, [rcx+10h]
0x18001b658  mov     edx, 24h ; '$'
0x18001b65d  mov     r9d, ebx
0x18001b660  mov     r8, rbp
0x18001b663  call    WPP_SF_d
0x18001b668  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b66f  test    ebx, ebx
0x18001b671  js      loc_18001B79B
0x18001b677  jmp     short loc_18001B680
0x18001b679  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b680  cmp     rcx, rsi
0x18001b683  jz      loc_18001B788
0x18001b689  mov     bl, 2
0x18001b68b  test    [rcx+1Ch], bl
0x18001b68e  jz      short loc_18001B6B0
0x18001b690  mov     r9, [rsp+58h+arg_8]
0x18001b695  mov     edx, 25h ; '%'
0x18001b69a  mov     rcx, [rcx+10h]
0x18001b69e  mov     r8, rbp
0x18001b6a1  mov     r9, [r9]
0x18001b6a4  call    WPP_SF_S
0x18001b6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6b0  cmp     rcx, rsi
0x18001b6b3  jz      loc_18001B788
0x18001b6b9  test    [rcx+1Ch], bl
0x18001b6bc  jz      short loc_18001B6DF
0x18001b6be  mov     r9, [rsp+58h+arg_8]
0x18001b6c3  mov     edx, 26h ; '&'
0x18001b6c8  mov     rcx, [rcx+10h]
0x18001b6cc  mov     r8, rbp
0x18001b6cf  mov     r9, [r9+8]
0x18001b6d3  call    WPP_SF_S
0x18001b6d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6df  cmp     rcx, rsi
0x18001b6e2  jz      loc_18001B788
0x18001b6e8  test    [rcx+1Ch], bl
0x18001b6eb  jz      short loc_18001B70E
0x18001b6ed  mov     r9, [rsp+58h+arg_8]
0x18001b6f2  mov     edx, 27h ; '''
0x18001b6f7  mov     rcx, [rcx+10h]
0x18001b6fb  mov     r8, rbp
0x18001b6fe  mov     r9, [r9+28h]
0x18001b702  call    WPP_SF_S
0x18001b707  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b70e  cmp     rcx, rsi
0x18001b711  jz      short loc_18001B788
0x18001b713  test    [rcx+1Ch], bl
0x18001b716  jz      short loc_18001B739
0x18001b718  mov     r9, [rsp+58h+arg_8]
0x18001b71d  mov     edx, 28h ; '('
0x18001b722  mov     rcx, [rcx+10h]
0x18001b726  mov     r8, rbp
0x18001b729  mov     r9, [r9+30h]
0x18001b72d  call    WPP_SF_S
0x18001b732  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b739  cmp     rcx, rsi
0x18001b73c  jz      short loc_18001B788
0x18001b73e  test    [rcx+1Ch], bl
0x18001b741  jz      short loc_18001B764
0x18001b743  mov     r9, [rsp+58h+arg_8]
0x18001b748  mov     edx, 29h ; ')'
0x18001b74d  mov     rcx, [rcx+10h]
0x18001b751  mov     r8, rbp
0x18001b754  mov     r9, [r9+40h]
0x18001b758  call    WPP_SF_S
0x18001b75d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b764  cmp     rcx, rsi
0x18001b767  jz      short loc_18001B788
0x18001b769  test    [rcx+1Ch], bl
0x18001b76c  jz      short loc_18001B788
0x18001b76e  mov     r9, [rsp+58h+arg_8]
0x18001b773  mov     edx, 2Ah ; '*'
0x18001b778  mov     rcx, [rcx+10h]
0x18001b77c  mov     r8, rbp
0x18001b77f  mov     r9, [r9+48h]
0x18001b783  call    WPP_SF_S
0x18001b788  mov     rcx, [rsp+58h+arg_8]
0x18001b78d  mov     rdx, rdi; unsigned __int16 **
0x18001b790  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18001b794  call    ?CreateStringCopy@CUstUtil@@SAJPEAGPEAPEAG@Z; CUstUtil::CreateStringCopy(ushort *,ushort * *)
0x18001b799  mov     ebx, eax
0x18001b79b  mov     rcx, [rsp+58h+arg_8]; Buffer
0x18001b7a0  test    rcx, rcx
0x18001b7a3  jz      short loc_18001B7AB
0x18001b7a5  call    cs:__imp_NetApiBufferFree
0x18001b7ab  mov     eax, ebx
0x18001b7ad  add     rsp, 38h
0x18001b7b1  pop     rdi
0x18001b7b2  pop     rsi
0x18001b7b3  pop     rbp
0x18001b7b4  pop     rbx
0x18001b7b5  retn
```
