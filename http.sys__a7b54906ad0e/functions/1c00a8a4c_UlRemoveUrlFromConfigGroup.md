# UlRemoveUrlFromConfigGroup

- ea: `0x1c00a8a4c`
- end: `0x1c00a8c95`
- name: `UlRemoveUrlFromConfigGroup`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1c00a8880`

## callees

- `0x1c00035ac`
- `0x1c00036b8`
- `0x1c001a4b0`
- `0x1c001b900`
- `0x1c003332c`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f680`
- `0x1c0093a10`
- `0x1c0093a80`
- `0x1c0093af0`
- `0x1c0094094`
- `0x1c00a17c0`
- `0x1c00a6318`
- `0x1c00a8a4c`
- `0x1c00a8c9c`
- `0x1c00a8d30`
- `0x1c00a8f10`
- `0x1c0140e5c`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a8c2f`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c00a8c2f`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a8b00`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c00a8b00`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a8c53`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00a8c53`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a8c3b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c00a8c3b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a8aed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c00a8aed`

## pseudocode

```c
__int64 __fastcall UlRemoveUrlFromConfigGroup(__int64 a1, __int64 a2, __int64 a3, int a4, int a5, char a6)
{
  _DWORD *v9; // rdi
  __int64 v11; // rdx
  int v12; // r8d
  __int64 v13; // rsi
  int RegistrationNode; // ebx
  __int64 v15; // rbx
  _DWORD *ObjectFromOpaqueId; // rax
  int v17; // edx
  int v18; // ecx
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  PVOID v21[3]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22[18]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v23; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v24; // [rsp+100h] [rbp+0h]
  char v25; // [rsp+108h] [rbp+8h]
  int v26; // [rsp+109h] [rbp+9h]
  __int16 v27; // [rsp+10Dh] [rbp+Dh]
  char v28; // [rsp+10Fh] [rbp+Fh]

  v21[0] = 0;
  P = 0;
  v9 = 0;
  memset(v22, 0, 0x88u);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_qqSqLl(122, v11, a1, a2, *(_QWORD *)(a3 + 8), a4, a5, a6);
  v13 = *(_QWORD *)(a2 + 8);
  if ( (BYTE4(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 8) != 0 )
    WPP_SF_Si(123, v11, *(_QWORD *)(a3 + 8), *(_QWORD *)(a2 + 8));
  LOBYTE(v12) = 1;
  RegistrationNode = UlSanitizeUrl(*(_QWORD *)(a1 + 56), *(_QWORD *)(a3 + 8), v12, (unsigned int)&P, (__int64)v22);
  if ( RegistrationNode >= 0 )
  {
    v15 = *(_QWORD *)(a1 + 56);
    KeEnterCriticalRegion();
    ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v15 + 1360));
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        RegistrationNode = UlpTreeFindRegistrationNode(*(_QWORD *)(a1 + 56), P, v21);
        if ( RegistrationNode < 0 )
        {
          if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
            WPP_SF_D(125, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
          goto LABEL_23;
        }
        ObjectFromOpaqueId = (_DWORD *)UxGetObjectFromOpaqueId(
                                         v13,
                                         2,
                                         (unsigned int)UlReferenceServerSession,
                                         (unsigned int)UlValidateConfigGroup,
                                         a1);
        v9 = ObjectFromOpaqueId;
        if ( ObjectFromOpaqueId && *ObjectFromOpaqueId == 1245932629 )
        {
          if ( *((_DWORD **)v21[0] + 11) == ObjectFromOpaqueId )
          {
            RegistrationNode = UlpTreeDeleteRegistration(v21[0]);
            if ( *(_BYTE *)(*(_QWORD *)(a1 + 56) + 1568LL) )
            {
              v24 = *(_QWORD *)(a1 + 56);
              v26 = 0;
              v27 = 0;
              v28 = 0;
              v23 = 0;
              v25 = 0;
              McTemplateK0xz_UlEtwWriteEventWrapper(v18, v17, (unsigned int)&v23, v13, v22[1]);
            }
            if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
              WPP_SF_diS(128, v17, RegistrationNode, v13, v22[1]);
            if ( RegistrationNode < 0 )
            {
              if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
                WPP_SF_D(129, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
            }
            else
            {
              UlFlushCacheForRemoveUrl(v22, v9);
              if ( *((_DWORD **)v9 + 4) == v9 + 8 && v9 != (_DWORD *)-120LL && (v9[32] & 1) != 0 && *((_QWORD *)v9 + 30) )
                UlDisableLoggingConfig();
            }
          }
          else
          {
            if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
              WPP_SF_(127, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
            RegistrationNode = -1073741734;
          }
        }
        else
        {
          if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
            WPP_SF_q(126, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, v13);
          RegistrationNode = -1073741811;
        }
        goto LABEL_20;
      }
      RegistrationNode = -1073741811;
    }
    else
    {
      RegistrationNode = UlpDeleteReservationEntry(*(_QWORD *)(a1 + 56), (unsigned int)v22, a4, a5, a6, 0);
      if ( RegistrationNode < 0 && (WPP_MAIN_CB.DeviceType & 8) != 0 )
      {
        WPP_SF_Sd(130, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, v22[1], (unsigned int)RegistrationNode);
LABEL_20:
        if ( v9 && _InterlockedExchangeAdd(v9 + 1, 0xFFFFFFFF) == 1 )
          UlFreeConfigGroup(v9);
      }
    }
LABEL_23:
    ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(*(_QWORD *)(a1 + 56) + 1360LL));
    KeLeaveCriticalRegion();
    goto LABEL_24;
  }
  if ( (WPP_MAIN_CB.DeviceType & 8) != 0 )
    WPP_SF_Sd(124, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids, *(_QWORD *)(a3 + 8), (unsigned int)RegistrationNode);
LABEL_24:
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 8) != 0 )
    WPP_SF_D(131, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids);
  return (unsigned int)RegistrationNode;
}

```

## disassembly

```asm
0x1c00a8a4c  push    rbp
0x1c00a8a4e  push    rbx
0x1c00a8a4f  push    rsi
0x1c00a8a50  push    rdi
0x1c00a8a51  push    r12
0x1c00a8a53  push    r13
0x1c00a8a55  push    r14
0x1c00a8a57  push    r15
0x1c00a8a59  lea     rbp, [rsp-28h]
0x1c00a8a5e  sub     rsp, 128h
0x1c00a8a65  mov     rax, cs:__security_cookie
0x1c00a8a6c  xor     rax, rsp
0x1c00a8a6f  mov     [rbp+60h+var_50], rax
0x1c00a8a73  and     [rsp+160h+var_118], 0
0x1c00a8a79  mov     r15, r8
0x1c00a8a7c  and     [rsp+160h+P], 0
0x1c00a8a82  mov     r12, rdx
0x1c00a8a85  mov     r14, rcx
0x1c00a8a88  xor     edx, edx; Val
0x1c00a8a8a  mov     r8d, 88h; Size
0x1c00a8a90  lea     rcx, [rsp+160h+var_100]; void *
0x1c00a8a95  xor     edi, edi
0x1c00a8a97  mov     r13, r9
0x1c00a8a9a  call    memset
0x1c00a8a9f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a8aa5  test    al, 8
0x1c00a8aa7  jnz     loc_1C00E7794
0x1c00a8aad  mov     rsi, [r12+8]
0x1c00a8ab2  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue+4
0x1c00a8ab8  test    al, 8
0x1c00a8aba  jnz     loc_1C00E77CD
0x1c00a8ac0  mov     rdx, [r15+8]
0x1c00a8ac4  lea     rax, [rsp+160h+var_100]
0x1c00a8ac9  mov     rcx, [r14+38h]
0x1c00a8acd  lea     r9, [rsp+160h+P]
0x1c00a8ad2  mov     r8b, 1
0x1c00a8ad5  mov     [rsp+160h+var_140], rax
0x1c00a8ada  call    UlSanitizeUrl
0x1c00a8adf  mov     ebx, eax
0x1c00a8ae1  test    eax, eax
0x1c00a8ae3  js      loc_1C00E77E4
0x1c00a8ae9  mov     rbx, [r14+38h]
0x1c00a8aed  call    cs:__imp_KeEnterCriticalRegion
0x1c00a8af4  nop     dword ptr [rax+rax+00h]
0x1c00a8af9  mov     rcx, [rbx+550h]
0x1c00a8b00  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c00a8b07  nop     dword ptr [rax+rax+00h]
0x1c00a8b0c  mov     ecx, [r12]
0x1c00a8b10  xor     r15d, r15d
0x1c00a8b13  test    ecx, ecx
0x1c00a8b15  jz      loc_1C00E78EB
0x1c00a8b1b  cmp     ecx, 1
0x1c00a8b1e  jnz     loc_1C00E780E
0x1c00a8b24  mov     rdx, [rsp+160h+P]
0x1c00a8b29  lea     r8, [rsp+160h+var_118]
0x1c00a8b2e  mov     rcx, [r14+38h]
0x1c00a8b32  call    UlpTreeFindRegistrationNode
0x1c00a8b37  mov     ebx, eax
0x1c00a8b39  test    eax, eax
0x1c00a8b3b  js      loc_1C00E7818
0x1c00a8b41  lea     r9, UlValidateConfigGroup
0x1c00a8b48  mov     [rsp+160h+var_140], r14
0x1c00a8b4d  lea     r8, UlReferenceServerSession
0x1c00a8b54  mov     rcx, rsi
0x1c00a8b57  lea     edx, [r15+2]
0x1c00a8b5b  call    UxGetObjectFromOpaqueId
0x1c00a8b60  mov     rdi, rax
0x1c00a8b63  test    rax, rax
0x1c00a8b66  jz      loc_1C00E78C3
0x1c00a8b6c  cmp     dword ptr [rax], 4A436C55h
0x1c00a8b72  jnz     loc_1C00E78C3
0x1c00a8b78  mov     rcx, [rsp+160h+var_118]; P
0x1c00a8b7d  cmp     [rcx+58h], rax
0x1c00a8b81  jnz     loc_1C00E7840
0x1c00a8b87  call    UlpTreeDeleteRegistration
0x1c00a8b8c  mov     ebx, eax
0x1c00a8b8e  mov     rax, [r14+38h]
0x1c00a8b92  cmp     [rax+620h], r15b
0x1c00a8b99  jz      short loc_1C00A8BCE
0x1c00a8b9b  mov     [rbp+60h+var_60], rax
0x1c00a8b9f  lea     r8, [rbp+60h+var_70]
0x1c00a8ba3  mov     rax, [rsp+160h+var_F8]
0x1c00a8ba8  xorps   xmm0, xmm0
0x1c00a8bab  mov     r9, rsi
0x1c00a8bae  mov     [rsp+160h+var_140], rax
0x1c00a8bb3  mov     [rbp+60h+var_57], r15d
0x1c00a8bb7  mov     [rbp+60h+var_53], r15w
0x1c00a8bbc  mov     [rbp+60h+var_51], r15b
0x1c00a8bc0  movdqu  [rbp+60h+var_70], xmm0
0x1c00a8bc5  mov     [rbp+60h+var_58], r15b
0x1c00a8bc9  call    McTemplateK0xz_UlEtwWriteEventWrapper
0x1c00a8bce  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a8bd4  test    al, 8
0x1c00a8bd6  jnz     loc_1C00E7866
0x1c00a8bdc  test    ebx, ebx
0x1c00a8bde  js      loc_1C00E7886
0x1c00a8be4  mov     rdx, rdi
0x1c00a8be7  lea     rcx, [rsp+160h+var_100]
0x1c00a8bec  call    UlFlushCacheForRemoveUrl
0x1c00a8bf1  lea     rax, [rdi+20h]
0x1c00a8bf5  cmp     [rax], rax
0x1c00a8bf8  jnz     short loc_1C00A8C0E
0x1c00a8bfa  lea     rcx, [rdi+78h]
0x1c00a8bfe  test    rcx, rcx
0x1c00a8c01  jz      short loc_1C00A8C0E
0x1c00a8c03  mov     eax, [rcx+8]
0x1c00a8c06  test    al, 1
0x1c00a8c08  jnz     loc_1C00E78AE
0x1c00a8c0e  test    rdi, rdi
0x1c00a8c11  jz      short loc_1C00A8C24
0x1c00a8c13  or      eax, 0FFFFFFFFh
0x1c00a8c16  lock xadd [rdi+4], eax
0x1c00a8c1b  cmp     eax, 1
0x1c00a8c1e  jz      loc_1C00E7949
0x1c00a8c24  mov     rcx, [r14+38h]
0x1c00a8c28  mov     rcx, [rcx+550h]
0x1c00a8c2f  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c00a8c36  nop     dword ptr [rax+rax+00h]
0x1c00a8c3b  call    cs:__imp_KeLeaveCriticalRegion
0x1c00a8c42  nop     dword ptr [rax+rax+00h]
0x1c00a8c47  mov     rcx, [rsp+160h+P]; P
0x1c00a8c4c  test    rcx, rcx
0x1c00a8c4f  jz      short loc_1C00A8C64
0x1c00a8c51  xor     edx, edx; Tag
0x1c00a8c53  call    cs:__imp_ExFreePoolWithTag
0x1c00a8c5a  nop     dword ptr [rax+rax+00h]
0x1c00a8c5f  mov     [rsp+160h+P], r15
0x1c00a8c64  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c00a8c6a  test    al, 8
0x1c00a8c6c  jnz     loc_1C00E7957
0x1c00a8c72  mov     eax, ebx
0x1c00a8c74  mov     rcx, [rbp+60h+var_50]
0x1c00a8c78  xor     rcx, rsp; StackCookie
0x1c00a8c7b  call    __security_check_cookie
0x1c00a8c80  add     rsp, 128h
0x1c00a8c87  pop     r15
0x1c00a8c89  pop     r14
0x1c00a8c8b  pop     r13
0x1c00a8c8d  pop     r12
0x1c00a8c8f  pop     rdi
0x1c00a8c90  pop     rsi
0x1c00a8c91  pop     rbx
0x1c00a8c92  pop     rbp
0x1c00a8c93  retn
0x1c00e7794  movsx   eax, [rbp+60h+arg_28]
0x1c00e779b  mov     ecx, 7Ah ; 'z'
0x1c00e77a0  mov     [rsp+160h+var_128], eax
0x1c00e77a4  mov     r9, r12
0x1c00e77a7  mov     eax, [rbp+60h+arg_20]
0x1c00e77ad  mov     r8, r14
0x1c00e77b0  mov     [rsp+160h+var_130], eax
0x1c00e77b4  mov     rax, [r15+8]
0x1c00e77b8  mov     [rsp+160h+var_138], r13
0x1c00e77bd  mov     [rsp+160h+var_140], rax
0x1c00e77c2  call    WPP_SF_qqSqLl
0x1c00e77c7  nop
0x1c00e77c8  jmp     loc_1C00A8AAD
0x1c00e77cd  mov     r8, [r15+8]
0x1c00e77d1  mov     ecx, 7Bh ; '{'
0x1c00e77d6  mov     r9, rsi
0x1c00e77d9  call    WPP_SF_Si
0x1c00e77de  nop
0x1c00e77df  jmp     loc_1C00A8AC0
0x1c00e77e4  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00e77ea  test    al, 8
0x1c00e77ec  jz      short loc_1C00E7806
0x1c00e77ee  mov     r8, [r15+8]
0x1c00e77f2  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e77f9  mov     ecx, 7Ch ; '|'
0x1c00e77fe  mov     r9d, ebx
0x1c00e7801  call    WPP_SF_Sd
0x1c00e7806  xor     r15d, r15d
0x1c00e7809  jmp     loc_1C00A8C47
0x1c00e780e  mov     ebx, 0C000000Dh
0x1c00e7813  jmp     loc_1C00A8C24
0x1c00e7818  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00e781e  test    al, 8
0x1c00e7820  jz      loc_1C00A8C24
0x1c00e7826  mov     ecx, 7Dh ; '}'
0x1c00e782b  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e7832  mov     r8d, ebx
0x1c00e7835  call    WPP_SF_D
0x1c00e783a  nop
0x1c00e783b  jmp     loc_1C00A8C24
0x1c00e7840  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x1c00e7846  test    cl, 8
0x1c00e7849  jz      short loc_1C00E785C
0x1c00e784b  mov     ecx, 7Fh
0x1c00e7850  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e7857  call    WPP_SF_
0x1c00e785c  mov     ebx, 0C000005Ah
0x1c00e7861  jmp     loc_1C00A8C0E
0x1c00e7866  mov     rax, [rsp+160h+var_F8]
0x1c00e786b  mov     ecx, 80h
0x1c00e7870  mov     r9, rsi
0x1c00e7873  mov     [rsp+160h+var_140], rax
0x1c00e7878  mov     r8d, ebx
0x1c00e787b  call    WPP_SF_diS
0x1c00e7880  nop
0x1c00e7881  jmp     loc_1C00A8BDC
0x1c00e7886  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00e788c  test    al, 8
0x1c00e788e  jz      loc_1C00A8C0E
0x1c00e7894  mov     ecx, 81h
0x1c00e7899  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e78a0  mov     r8d, ebx
0x1c00e78a3  call    WPP_SF_D
0x1c00e78a8  nop
0x1c00e78a9  jmp     loc_1C00A8C0E
0x1c00e78ae  cmp     [rcx+78h], r15
0x1c00e78b2  jz      loc_1C00A8C0E
0x1c00e78b8  call    UlDisableLoggingConfig
0x1c00e78bd  nop
0x1c00e78be  jmp     loc_1C00A8C0E
0x1c00e78c3  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00e78c9  test    al, 8
0x1c00e78cb  jz      short loc_1C00E78E1
0x1c00e78cd  mov     ecx, 7Eh ; '~'
0x1c00e78d2  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e78d9  mov     r8, rsi
0x1c00e78dc  call    WPP_SF_q
0x1c00e78e1  mov     ebx, 0C000000Dh
0x1c00e78e6  jmp     loc_1C00A8C0E
0x1c00e78eb  mov     al, [rbp+60h+arg_28]
0x1c00e78f1  lea     rdx, [rsp+160h+var_100]
0x1c00e78f6  mov     r9d, [rbp+60h+arg_20]
0x1c00e78fd  mov     r8, r13
0x1c00e7900  mov     rcx, [r14+38h]
0x1c00e7904  mov     byte ptr [rsp+160h+var_138], r15b
0x1c00e7909  mov     byte ptr [rsp+160h+var_140], al
0x1c00e790d  call    UlpDeleteReservationEntry
0x1c00e7912  mov     ebx, eax
0x1c00e7914  test    eax, eax
0x1c00e7916  jns     loc_1C00A8C24
0x1c00e791c  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c00e7922  test    al, 8
0x1c00e7924  jz      loc_1C00A8C24
0x1c00e792a  mov     r8, [rsp+160h+var_F8]
0x1c00e792f  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e7936  mov     ecx, 82h
0x1c00e793b  mov     r9d, ebx
0x1c00e793e  call    WPP_SF_Sd
0x1c00e7943  nop
0x1c00e7944  jmp     loc_1C00A8C0E
0x1c00e7949  mov     rcx, rdi; P
0x1c00e794c  call    UlFreeConfigGroup
0x1c00e7951  nop
0x1c00e7952  jmp     loc_1C00A8C24
0x1c00e7957  mov     ecx, 83h
0x1c00e795c  lea     rdx, WPP_04fa14b6be9632dc06b6ccf0245e6307_Traceguids
0x1c00e7963  mov     r8d, ebx
0x1c00e7966  call    WPP_SF_D
0x1c00e796b  nop
0x1c00e796c  jmp     loc_1C00A8C72
```
