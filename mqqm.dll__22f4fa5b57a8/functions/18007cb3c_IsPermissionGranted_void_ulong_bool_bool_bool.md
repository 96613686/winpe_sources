# IsPermissionGranted(void *,ulong,bool *,bool *,bool *)

- ea: `0x18007cb3c`
- end: `0x18007ceb9`
- name: `?IsPermissionGranted@@YAXPEAXKPEA_N11@Z`
- size: `893`
- prototype: `void __fastcall(void *, unsigned int, bool *, bool *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048e24`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18002c574`
- `0x18007cb3c`
- `0x1800d6ea0`

## import_xrefs

- `ADVAPI32!GetAce` at `0x18007ccec`
- `ADVAPI32!GetAce` at `0x18007ccec`
- `ADVAPI32!GetAclInformation` at `0x18007cc22`
- `ADVAPI32!GetAclInformation` at `0x18007cc22`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007cb94`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18007cb94`
- `ADVAPI32!EqualSid` at `0x18007cd27`
- `ADVAPI32!EqualSid` at `0x18007cd74`
- `ADVAPI32!EqualSid` at `0x18007cd27`
- `ADVAPI32!EqualSid` at `0x18007cd74`
- `KERNEL32!GetLastError` at `0x18007cb9e`
- `KERNEL32!GetLastError` at `0x18007cc2c`
- `KERNEL32!GetLastError` at `0x18007cdf1`
- `KERNEL32!GetLastError` at `0x18007cb9e`
- `KERNEL32!GetLastError` at `0x18007cc2c`
- `KERNEL32!GetLastError` at `0x18007cdf1`
- `mqsec!MQSec_GetWorldSid` at `0x18007cd1a`
- `mqsec!MQSec_GetWorldSid` at `0x18007cd1a`
- `mqsec!MQSec_GetAnonymousSid` at `0x18007cd67`
- `mqsec!MQSec_GetAnonymousSid` at `0x18007cd67`

## pseudocode

```c
void __fastcall IsPermissionGranted(void *a1, __int64 a2, bool *a3, bool *a4, bool *a5)
{
  DWORD LastError; // eax
  unsigned __int16 v8; // r8
  DWORD v9; // eax
  DWORD v10; // eax
  char v11; // r12
  char v12; // r14
  DWORD v13; // r15d
  bool v14; // di
  char *v15; // rbx
  void *WorldSid; // rax
  char *v17; // rbx
  void *AnonymousSid; // rax
  DWORD v19; // eax
  WINBOOL bDaclPresent; // [rsp+20h] [rbp-40h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+24h] [rbp-3Ch] BYREF
  PACL pDacl; // [rsp+28h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+30h] [rbp-30h] BYREF
  bool *v24; // [rsp+38h] [rbp-28h]
  bool *v25; // [rsp+40h] [rbp-20h]
  __int64 pAclInformation; // [rsp+48h] [rbp-18h] BYREF
  int v27; // [rsp+50h] [rbp-10h]

  v25 = a5;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v24 = a4;
  bDaclPresent = 0;
  pDacl = 0;
  bDaclDefaulted = 0;
  if ( !GetSecurityDescriptorDacl(a1, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, LastError);
    v8 = 20;
LABEL_6:
    LogMsgBOOL(0, (wchar_t *)L"dumpauthzutl", v8);
    return;
  }
  if ( bDaclPresent && pDacl )
  {
    pAclInformation = 0;
    v27 = 0;
    if ( !GetAclInformation(pDacl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      v9 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 13, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v9);
      v8 = 40;
      goto LABEL_6;
    }
    v10 = pAclInformation;
    if ( !(_DWORD)pAclInformation )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 32),
          (unsigned int)(pAclInformation + 14),
          &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
      v8 = 50;
      goto LABEL_6;
    }
    v11 = 0;
    v12 = 0;
    v13 = 0;
    v14 = 1;
    while ( v13 < v10 )
    {
      pAce = 0;
      if ( !GetAce(pDacl, v13, &pAce) )
      {
        v19 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 15, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids, v19);
        return;
      }
      v15 = (char *)pAce;
      if ( *(_BYTE *)pAce <= 1u && (*((_BYTE *)pAce + 4) & 4) != 0 )
      {
        if ( *(_BYTE *)pAce == 1 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 16, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
          v8 = 60;
          goto LABEL_6;
        }
        WorldSid = MQSec_GetWorldSid();
        if ( EqualSid(WorldSid, v15 + 8) )
        {
          v11 = 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 17, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
        }
        else
        {
          v17 = (char *)pAce;
          AnonymousSid = MQSec_GetAnonymousSid();
          if ( EqualSid(AnonymousSid, v17 + 8) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 18, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
            v12 = 1;
          }
        }
      }
      v10 = pAclInformation;
      ++v13;
    }
    *v24 = v11;
    *v25 = v12;
    if ( !v11 || !v12 )
      v14 = 0;
    *a3 = v14;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, &WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids);
    *a3 = 1;
    *a4 = 1;
    *a5 = 1;
  }
}

```

## disassembly

```asm
0x18007cb3c  mov     [rsp-38h+arg_8], rbx
0x18007cb41  push    rbp
0x18007cb42  push    rsi
0x18007cb43  push    rdi
0x18007cb44  push    r12
0x18007cb46  push    r13
0x18007cb48  push    r14
0x18007cb4a  push    r15
0x18007cb4c  mov     rbp, rsp
0x18007cb4f  sub     rsp, 60h
0x18007cb53  mov     rax, cs:__security_cookie
0x18007cb5a  xor     rax, rsp
0x18007cb5d  mov     [rbp+var_8], rax
0x18007cb61  mov     r14, [rbp+arg_20]
0x18007cb65  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18007cb69  xor     edi, edi
0x18007cb6b  mov     [rbp+var_20], r14
0x18007cb6f  mov     [r8], dil
0x18007cb72  mov     rbx, r9
0x18007cb75  mov     [r9], dil
0x18007cb78  mov     r13, r8
0x18007cb7b  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18007cb7f  mov     [r14], dil
0x18007cb82  lea     r8, [rbp+pDacl]; pDacl
0x18007cb86  mov     [rbp+var_28], rbx
0x18007cb8a  mov     [rbp+bDaclPresent], edi
0x18007cb8d  mov     [rbp+pDacl], rdi
0x18007cb91  mov     [rbp+bDaclDefaulted], edi
0x18007cb94  call    cs:__imp_GetSecurityDescriptorDacl
0x18007cb9a  test    eax, eax
0x18007cb9c  jnz     short loc_18007CBF7
0x18007cb9e  call    cs:__imp_GetLastError
0x18007cba4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cbab  lea     rsi, WPP_GLOBAL_Control
0x18007cbb2  cmp     rcx, rsi
0x18007cbb5  jz      short loc_18007CBDE
0x18007cbb7  mov     edi, 1
0x18007cbbc  test    [rcx+10Ch], dil
0x18007cbc3  jz      short loc_18007CBDE
0x18007cbc5  mov     rcx, [rcx+100h]
0x18007cbcc  lea     edx, [rdi+0Ah]
0x18007cbcf  mov     r9d, eax
0x18007cbd2  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007cbd9  call    WPP_SF_d
0x18007cbde  mov     r8d, 14h; unsigned __int16
0x18007cbe4  lea     rdx, aDumpauthzutl; "dumpauthzutl"
0x18007cbeb  xor     ecx, ecx; int
0x18007cbed  call    ?LogMsgBOOL@@YAXHPEA_WG@Z; LogMsgBOOL(int,wchar_t *,ushort)
0x18007cbf2  jmp     loc_18007CE95
0x18007cbf7  cmp     [rbp+bDaclPresent], edi
0x18007cbfa  jz      loc_18007CE52
0x18007cc00  mov     rcx, [rbp+pDacl]; pAcl
0x18007cc04  test    rcx, rcx
0x18007cc07  jz      loc_18007CE52
0x18007cc0d  xor     eax, eax
0x18007cc0f  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18007cc13  mov     [rbp+pAclInformation], rax
0x18007cc17  mov     [rbp+var_10], eax
0x18007cc1a  lea     r9d, [rax+2]; dwAclInformationClass
0x18007cc1e  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18007cc22  call    cs:__imp_GetAclInformation
0x18007cc28  test    eax, eax
0x18007cc2a  jnz     short loc_18007CC77
0x18007cc2c  call    cs:__imp_GetLastError
0x18007cc32  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc39  lea     rsi, WPP_GLOBAL_Control
0x18007cc40  cmp     rcx, rsi
0x18007cc43  jz      short loc_18007CC6C
0x18007cc45  mov     edi, 1
0x18007cc4a  test    [rcx+10Ch], dil
0x18007cc51  jz      short loc_18007CC6C
0x18007cc53  mov     rcx, [rcx+100h]
0x18007cc5a  lea     edx, [rdi+0Ch]
0x18007cc5d  mov     r9d, eax
0x18007cc60  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007cc67  call    WPP_SF_d
0x18007cc6c  mov     r8d, 28h ; '('
0x18007cc72  jmp     loc_18007CBE4
0x18007cc77  mov     eax, dword ptr [rbp+pAclInformation]
0x18007cc7a  test    eax, eax
0x18007cc7c  jnz     short loc_18007CCBB
0x18007cc7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc85  lea     rsi, WPP_GLOBAL_Control
0x18007cc8c  cmp     rcx, rsi
0x18007cc8f  jz      short loc_18007CCB0
0x18007cc91  test    byte ptr [rcx+10Ch], 4
0x18007cc98  jz      short loc_18007CCB0
0x18007cc9a  mov     rcx, [rcx+100h]
0x18007cca1  lea     edx, [rax+0Eh]
0x18007cca4  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007ccab  call    WPP_SF_
0x18007ccb0  mov     r8d, 32h ; '2'
0x18007ccb6  jmp     loc_18007CBE4
0x18007ccbb  mov     r12b, dil
0x18007ccbe  lea     rsi, WPP_GLOBAL_Control
0x18007ccc5  mov     r14b, dil
0x18007ccc8  mov     r15d, edi
0x18007cccb  mov     edi, 1
0x18007ccd0  cmp     r15d, eax
0x18007ccd3  jnb     loc_18007CE31
0x18007ccd9  mov     rcx, [rbp+pDacl]; pAcl
0x18007ccdd  lea     r8, [rbp+pAce]; pAce
0x18007cce1  mov     edx, r15d; dwAceIndex
0x18007cce4  mov     [rbp+pAce], 0
0x18007ccec  call    cs:__imp_GetAce
0x18007ccf2  test    eax, eax
0x18007ccf4  jz      loc_18007CDF1
0x18007ccfa  mov     rbx, [rbp+pAce]
0x18007ccfe  cmp     [rbx], dil
0x18007cd01  ja      loc_18007CDAE
0x18007cd07  test    byte ptr [rbx+4], 4
0x18007cd0b  jz      loc_18007CDAE
0x18007cd11  cmp     [rbx], dil
0x18007cd14  jz      loc_18007CDB9
0x18007cd1a  call    cs:__imp_?MQSec_GetWorldSid@@YAPEAXXZ; MQSec_GetWorldSid(void)
0x18007cd20  mov     rcx, rax; pSid1
0x18007cd23  lea     rdx, [rbx+8]; pSid2
0x18007cd27  call    cs:__imp_EqualSid
0x18007cd2d  test    eax, eax
0x18007cd2f  jz      short loc_18007CD63
0x18007cd31  mov     r12b, dil
0x18007cd34  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd3b  cmp     rcx, rsi
0x18007cd3e  jz      short loc_18007CDAE
0x18007cd40  test    byte ptr [rcx+10Ch], 4
0x18007cd47  jz      short loc_18007CDAE
0x18007cd49  mov     rcx, [rcx+100h]
0x18007cd50  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007cd57  mov     edx, 11h
0x18007cd5c  call    WPP_SF_
0x18007cd61  jmp     short loc_18007CDAE
0x18007cd63  mov     rbx, [rbp+pAce]
0x18007cd67  call    cs:__imp_?MQSec_GetAnonymousSid@@YAPEAXXZ; MQSec_GetAnonymousSid(void)
0x18007cd6d  mov     rcx, rax; pSid1
0x18007cd70  lea     rdx, [rbx+8]; pSid2
0x18007cd74  call    cs:__imp_EqualSid
0x18007cd7a  test    eax, eax
0x18007cd7c  jz      short loc_18007CDAE
0x18007cd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cd85  cmp     rcx, rsi
0x18007cd88  jz      short loc_18007CDAB
0x18007cd8a  test    byte ptr [rcx+10Ch], 4
0x18007cd91  jz      short loc_18007CDAB
0x18007cd93  mov     rcx, [rcx+100h]
0x18007cd9a  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007cda1  mov     edx, 12h
0x18007cda6  call    WPP_SF_
0x18007cdab  mov     r14b, dil
0x18007cdae  mov     eax, dword ptr [rbp+pAclInformation]
0x18007cdb1  add     r15d, edi
0x18007cdb4  jmp     loc_18007CCD0
0x18007cdb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cdc0  cmp     rcx, rsi
0x18007cdc3  jz      short loc_18007CDE6
0x18007cdc5  test    byte ptr [rcx+10Ch], 4
0x18007cdcc  jz      short loc_18007CDE6
0x18007cdce  mov     rcx, [rcx+100h]
0x18007cdd5  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007cddc  mov     edx, 10h
0x18007cde1  call    WPP_SF_
0x18007cde6  mov     r8d, 3Ch ; '<'
0x18007cdec  jmp     loc_18007CBE4
0x18007cdf1  call    cs:__imp_GetLastError
0x18007cdf7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cdfe  cmp     rcx, rsi
0x18007ce01  jz      loc_18007CE95
0x18007ce07  test    [rcx+10Ch], dil
0x18007ce0e  jz      loc_18007CE95
0x18007ce14  mov     rcx, [rcx+100h]
0x18007ce1b  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007ce22  mov     edx, 0Fh
0x18007ce27  mov     r9d, eax
0x18007ce2a  call    WPP_SF_d
0x18007ce2f  jmp     short loc_18007CE95
0x18007ce31  mov     rax, [rbp+var_28]
0x18007ce35  mov     [rax], r12b
0x18007ce38  mov     rax, [rbp+var_20]
0x18007ce3c  mov     [rax], r14b
0x18007ce3f  test    r12b, r12b
0x18007ce42  jz      short loc_18007CE49
0x18007ce44  test    r14b, r14b
0x18007ce47  jnz     short loc_18007CE4C
0x18007ce49  xor     dil, dil
0x18007ce4c  mov     [r13+0], dil
0x18007ce50  jmp     short loc_18007CE95
0x18007ce52  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ce59  lea     rsi, WPP_GLOBAL_Control
0x18007ce60  cmp     rcx, rsi
0x18007ce63  jz      short loc_18007CE86
0x18007ce65  test    byte ptr [rcx+10Ch], 4
0x18007ce6c  jz      short loc_18007CE86
0x18007ce6e  mov     rcx, [rcx+100h]
0x18007ce75  lea     r8, WPP_43be5b8d365f3686fbce56ada77c046b_Traceguids
0x18007ce7c  mov     edx, 0Ch
0x18007ce81  call    WPP_SF_
0x18007ce86  mov     edi, 1
0x18007ce8b  mov     [r13+0], dil
0x18007ce8f  mov     [rbx], dil
0x18007ce92  mov     [r14], dil
0x18007ce95  mov     rcx, [rbp+var_8]
0x18007ce99  xor     rcx, rsp; StackCookie
0x18007ce9c  call    __security_check_cookie
0x18007cea1  mov     rbx, [rsp+60h+arg_8]
0x18007cea9  add     rsp, 60h
0x18007cead  pop     r15
0x18007ceaf  pop     r14
0x18007ceb1  pop     r13
0x18007ceb3  pop     r12
0x18007ceb5  pop     rdi
0x18007ceb6  pop     rsi
0x18007ceb7  pop     rbp
0x18007ceb8  retn
```
