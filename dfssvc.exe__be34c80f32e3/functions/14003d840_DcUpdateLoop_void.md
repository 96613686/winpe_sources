# DcUpdateLoop(void *)

- ea: `0x14003d840`
- end: `0x14003db0c`
- name: `?DcUpdateLoop@@YAKPEAX@Z`
- size: `716`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x140006bf0`
- `0x14000971c`
- `0x14000abc4`
- `0x140018108`
- `0x140019d98`
- `0x14003cb94`
- `0x14003d840`
- `0x14003dfb8`
- `0x14003e164`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d91d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d953`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003dad7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d91d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003d953`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003dad7`

## pseudocode

```c
__int64 __fastcall DcUpdateLoop(unsigned int *Parameter)
{
  int v1; // esi
  unsigned int v2; // r14d
  unsigned int v3; // ebp
  unsigned int DomainInformation; // edi
  struct DfsDomainInformation *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // esi
  __int64 v9; // r8
  _UNKNOWN **v10; // rcx
  struct DfsDomainInformation *v11; // rdi
  unsigned int *v12; // r10
  __int64 v13; // rsi
  unsigned __int8 *v14; // r8
  struct DfsDomainInformation *v16; // [rsp+58h] [rbp+10h] BYREF

  v1 = 10;
  v2 = 1000 * *((_DWORD *)CConfigurationSettings::_GetInstance(Parameter) + 5) / 0x927C0u;
  v3 = v2 / 0xC;
  if ( !v2 )
    v2 = 1;
  if ( !v3 )
    v3 = 1;
  do
  {
    v16 = 0;
    DomainInformation = GetDomainInformation(&v16, 0);
    v5 = v16;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && pWppControl
      && (pWppControl[7] & 0x20) != 0
      && *((_BYTE *)pWppControl + 25) >= 3u )
    {
      WPP_SF_qd(
        *((_QWORD *)pWppControl + 2),
        10,
        WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids,
        v16,
        DomainInformation);
    }
    if ( v5 )
    {
      DfsSetGlobalDomainInfo(v5);
      DfsGeneric::ReleaseReference(v5);
      v16 = 0;
      if ( !DomainInformation )
        break;
    }
    WaitForSingleObject(hEvent, 0x3A98u);
    if ( HIBYTE(word_140071515) == 1 )
      return 0;
    if ( !DomainInformation )
      break;
    v6 = v1--;
  }
  while ( v6 > 0 );
  WaitForSingleObject(hEvent, 0x927C0u);
  if ( HIBYTE(word_140071515) != 1 )
  {
    v7 = v3;
    if ( !DomainInformation )
      v7 = v2;
    do
    {
      if ( --v7 )
      {
        v13 = DfsAcquireDomainInfo(&v16);
        v11 = v16;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)pWppControl + 2), 13, WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids, v16, v13);
        }
        if ( (_DWORD)v13 )
          goto LABEL_42;
        if ( *((_DWORD *)v11 + 6) )
        {
          do
          {
            DfsTrustedDomain::RemoveDcReferralData((DfsTrustedDomain *)(*((_QWORD *)v11 + 2) + 72 * v13), 0, v14);
            v13 = (unsigned int)(v13 + 1);
          }
          while ( (unsigned int)v13 < *((_DWORD *)v11 + 6) );
        }
      }
      else
      {
        v8 = GetDomainInformation(&v16, 1u);
        v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
        v11 = v16;
        v12 = pWppControl;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (pWppControl[7] & 0x20) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)pWppControl + 2), 11, WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids, v16, v8);
          v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
          v12 = pWppControl;
        }
        if ( v8 )
        {
          v7 = v3;
          if ( v10 != &WPP_GLOBAL_Control && v12 && (v12[7] & 0x20) != 0 && *((_BYTE *)v12 + 25) )
            WPP_SF_Dqd(*((_QWORD *)v12 + 2), 600000 * v3 / 0xEA60, v9, v8, v11, 600000 * v3 / 0xEA60);
        }
        else
        {
          v7 = v2;
        }
        if ( !v11 )
          goto LABEL_42;
        DfsSetGlobalDomainInfo(v11);
      }
      DfsGeneric::ReleaseReference(v11);
      v16 = 0;
LABEL_42:
      WaitForSingleObject(hEvent, 0x927C0u);
    }
    while ( HIBYTE(word_140071515) != 1 );
  }
  return 0;
}

```

## disassembly

```asm
0x14003d840  mov     [rsp+arg_0], rbx
0x14003d845  mov     [rsp+arg_10], rbp
0x14003d84a  mov     [rsp+arg_18], rsi
0x14003d84f  push    rdi
0x14003d850  push    r12
0x14003d852  push    r14
0x14003d854  sub     rsp, 30h
0x14003d858  mov     esi, 0Ah
0x14003d85d  call    ?_GetInstance@CConfigurationSettings@@SAPEAV1@PEAK@Z; CConfigurationSettings::_GetInstance(ulong *)
0x14003d862  lea     r12d, [rsi-9]
0x14003d866  imul    ecx, [rax+14h], 3E8h
0x14003d86d  mov     eax, 6FD91D85h
0x14003d872  mul     ecx
0x14003d874  mov     eax, 0AAAAAAABh
0x14003d879  mov     r14d, edx
0x14003d87c  shr     r14d, 12h
0x14003d880  mul     r14d
0x14003d883  mov     ebp, edx
0x14003d885  shr     ebp, 3
0x14003d888  test    r14d, r14d
0x14003d88b  cmovz   r14d, r12d
0x14003d88f  test    ebp, ebp
0x14003d891  cmovz   ebp, r12d
0x14003d895  and     [rsp+48h+arg_8], 0
0x14003d89b  lea     rcx, [rsp+48h+arg_8]; struct DfsDomainInformation **
0x14003d8a0  xor     edx, edx; unsigned __int8
0x14003d8a2  call    ?GetDomainInformation@@YAKPEAPEAVDfsDomainInformation@@E@Z; GetDomainInformation(DfsDomainInformation * *,uchar)
0x14003d8a7  mov     edi, eax
0x14003d8a9  mov     rbx, [rsp+48h+arg_8]
0x14003d8ae  lea     rax, WPP_GLOBAL_Control
0x14003d8b5  cmp     cs:WPP_GLOBAL_Control, rax
0x14003d8bc  jz      short loc_14003D8F2
0x14003d8be  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d8c5  test    rcx, rcx
0x14003d8c8  jz      short loc_14003D8F2
0x14003d8ca  test    byte ptr [rcx+1Ch], 20h
0x14003d8ce  jz      short loc_14003D8F2
0x14003d8d0  cmp     byte ptr [rcx+19h], 3
0x14003d8d4  jb      short loc_14003D8F2
0x14003d8d6  mov     rcx, [rcx+10h]
0x14003d8da  lea     r8, WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids
0x14003d8e1  mov     edx, 0Ah
0x14003d8e6  mov     dword ptr [rsp+48h+var_28], edi
0x14003d8ea  mov     r9, rbx
0x14003d8ed  call    WPP_SF_qd
0x14003d8f2  test    rbx, rbx
0x14003d8f5  jz      short loc_14003D911
0x14003d8f7  mov     rcx, rbx; struct DfsDomainInformation *
0x14003d8fa  call    ?DfsSetGlobalDomainInfo@@YAXPEAVDfsDomainInformation@@@Z; DfsSetGlobalDomainInfo(DfsDomainInformation *)
0x14003d8ff  mov     rcx, rbx; this
0x14003d902  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14003d907  and     [rsp+48h+arg_8], 0
0x14003d90d  test    edi, edi
0x14003d90f  jz      short loc_14003D947
0x14003d911  mov     rcx, cs:hEvent; hHandle
0x14003d918  mov     edx, 3A98h; dwMilliseconds
0x14003d91d  call    cs:__imp_WaitForSingleObject
0x14003d924  nop     dword ptr [rax+rax+00h]
0x14003d929  cmp     byte ptr cs:word_140071515+1, r12b
0x14003d930  jz      loc_14003DAF0
0x14003d936  test    edi, edi
0x14003d938  jz      short loc_14003D947
0x14003d93a  mov     eax, esi
0x14003d93c  sub     esi, r12d
0x14003d93f  test    eax, eax
0x14003d941  jg      loc_14003D895
0x14003d947  mov     rcx, cs:hEvent; hHandle
0x14003d94e  mov     edx, 927C0h; dwMilliseconds
0x14003d953  call    cs:__imp_WaitForSingleObject
0x14003d95a  nop     dword ptr [rax+rax+00h]
0x14003d95f  cmp     byte ptr cs:word_140071515+1, r12b
0x14003d966  jz      loc_14003DAF0
0x14003d96c  test    edi, edi
0x14003d96e  mov     ebx, ebp
0x14003d970  cmovz   ebx, r14d
0x14003d974  lea     rcx, [rsp+48h+arg_8]; struct DfsDomainInformation **
0x14003d979  add     ebx, 0FFFFFFFFh
0x14003d97c  jnz     loc_14003DA49
0x14003d982  mov     dl, r12b; unsigned __int8
0x14003d985  call    ?GetDomainInformation@@YAKPEAPEAVDfsDomainInformation@@E@Z; GetDomainInformation(DfsDomainInformation * *,uchar)
0x14003d98a  mov     esi, eax
0x14003d98c  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d993  lea     rax, WPP_GLOBAL_Control
0x14003d99a  mov     rdi, [rsp+48h+arg_8]
0x14003d99f  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d9a6  cmp     rcx, rax
0x14003d9a9  jz      short loc_14003D9EF
0x14003d9ab  test    r10, r10
0x14003d9ae  jz      short loc_14003D9EF
0x14003d9b0  test    byte ptr [r10+1Ch], 20h
0x14003d9b5  jz      short loc_14003D9EF
0x14003d9b7  cmp     byte ptr [r10+19h], 3
0x14003d9bc  jb      short loc_14003D9EF
0x14003d9be  mov     rcx, [r10+10h]
0x14003d9c2  lea     r8, WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids
0x14003d9c9  mov     edx, 0Bh
0x14003d9ce  mov     dword ptr [rsp+48h+var_28], esi
0x14003d9d2  mov     r9, rdi
0x14003d9d5  call    WPP_SF_qd
0x14003d9da  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d9e1  lea     rax, WPP_GLOBAL_Control
0x14003d9e8  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003d9ef  test    esi, esi
0x14003d9f1  jnz     short loc_14003D9F8
0x14003d9f3  mov     ebx, r14d
0x14003d9f6  jmp     short loc_14003DA36
0x14003d9f8  mov     ebx, ebp
0x14003d9fa  cmp     rcx, rax
0x14003d9fd  jz      short loc_14003DA36
0x14003d9ff  test    r10, r10
0x14003da02  jz      short loc_14003DA36
0x14003da04  test    byte ptr [r10+1Ch], 20h
0x14003da09  jz      short loc_14003DA36
0x14003da0b  cmp     [r10+19h], r12b
0x14003da0f  jb      short loc_14003DA36
0x14003da11  imul    ecx, ebp, 927C0h
0x14003da17  mov     eax, 45E7B273h
0x14003da1c  mov     r9d, esi
0x14003da1f  mul     ecx
0x14003da21  mov     rcx, [r10+10h]
0x14003da25  shr     edx, 0Eh
0x14003da28  mov     [rsp+48h+var_20], edx
0x14003da2c  mov     [rsp+48h+var_28], rdi
0x14003da31  call    WPP_SF_Dqd
0x14003da36  test    rdi, rdi
0x14003da39  jz      loc_14003DACB
0x14003da3f  mov     rcx, rdi; struct DfsDomainInformation *
0x14003da42  call    ?DfsSetGlobalDomainInfo@@YAXPEAVDfsDomainInformation@@@Z; DfsSetGlobalDomainInfo(DfsDomainInformation *)
0x14003da47  jmp     short loc_14003DABD
0x14003da49  call    ?DfsAcquireDomainInfo@@YAKPEAPEAVDfsDomainInformation@@@Z; DfsAcquireDomainInfo(DfsDomainInformation * *)
0x14003da4e  mov     esi, eax
0x14003da50  mov     rdi, [rsp+48h+arg_8]
0x14003da55  lea     rax, WPP_GLOBAL_Control
0x14003da5c  cmp     cs:WPP_GLOBAL_Control, rax
0x14003da63  jz      short loc_14003DA99
0x14003da65  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14003da6c  test    rcx, rcx
0x14003da6f  jz      short loc_14003DA99
0x14003da71  test    byte ptr [rcx+1Ch], 20h
0x14003da75  jz      short loc_14003DA99
0x14003da77  cmp     byte ptr [rcx+19h], 3
0x14003da7b  jb      short loc_14003DA99
0x14003da7d  mov     rcx, [rcx+10h]
0x14003da81  lea     r8, WPP_348730c78fa13fb2f81551b1b352efdc_Traceguids
0x14003da88  mov     edx, 0Dh
0x14003da8d  mov     dword ptr [rsp+48h+var_28], esi
0x14003da91  mov     r9, rdi
0x14003da94  call    WPP_SF_qd
0x14003da99  test    esi, esi
0x14003da9b  jnz     short loc_14003DACB
0x14003da9d  cmp     [rdi+18h], esi
0x14003daa0  jbe     short loc_14003DABD
0x14003daa2  mov     rax, [rdi+10h]
0x14003daa6  lea     rdx, [rsi+rsi*8]
0x14003daaa  lea     rcx, [rax+rdx*8]; this
0x14003daae  xor     edx, edx; struct DfsReferralData *
0x14003dab0  call    ?RemoveDcReferralData@DfsTrustedDomain@@QEAAKPEAVDfsReferralData@@PEAE@Z; DfsTrustedDomain::RemoveDcReferralData(DfsReferralData *,uchar *)
0x14003dab5  add     esi, r12d
0x14003dab8  cmp     esi, [rdi+18h]
0x14003dabb  jb      short loc_14003DAA2
0x14003dabd  mov     rcx, rdi; this
0x14003dac0  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x14003dac5  and     [rsp+48h+arg_8], 0
0x14003dacb  mov     rcx, cs:hEvent; hHandle
0x14003dad2  mov     edx, 927C0h; dwMilliseconds
0x14003dad7  call    cs:__imp_WaitForSingleObject
0x14003dade  nop     dword ptr [rax+rax+00h]
0x14003dae3  cmp     byte ptr cs:word_140071515+1, r12b
0x14003daea  jnz     loc_14003D974
0x14003daf0  mov     rbx, [rsp+48h+arg_0]
0x14003daf5  xor     eax, eax
0x14003daf7  mov     rbp, [rsp+48h+arg_10]
0x14003dafc  mov     rsi, [rsp+48h+arg_18]
0x14003db01  add     rsp, 30h
0x14003db05  pop     r14
0x14003db07  pop     r12
0x14003db09  pop     rdi
0x14003db0a  retn
```
