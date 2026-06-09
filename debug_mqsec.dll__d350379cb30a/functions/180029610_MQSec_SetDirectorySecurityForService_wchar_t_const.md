# MQSec_SetDirectorySecurityForService(wchar_t const *)

- ea: `0x180029610`
- end: `0x180029989`
- name: `?MQSec_SetDirectorySecurityForService@@YAJPEB_W@Z`
- size: `889`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004074`
- `0x180013940`
- `0x18001722c`
- `0x180017430`
- `0x1800216f0`
- `0x180029610`

## import_xrefs

- `msvcrt!free` at `0x1800296ce`
- `msvcrt!free` at `0x180029768`
- `msvcrt!free` at `0x180029772`
- `msvcrt!free` at `0x1800297c7`
- `msvcrt!free` at `0x1800297d1`
- `msvcrt!free` at `0x18002982d`
- `msvcrt!free` at `0x180029837`
- `msvcrt!free` at `0x180029891`
- `msvcrt!free` at `0x18002989b`
- `msvcrt!free` at `0x1800298ee`
- `msvcrt!free` at `0x1800298f8`
- `msvcrt!free` at `0x18002994b`
- `msvcrt!free` at `0x180029955`
- `msvcrt!free` at `0x180029964`
- `msvcrt!free` at `0x18002996e`
- `msvcrt!free` at `0x1800296ce`
- `msvcrt!free` at `0x180029768`
- `msvcrt!free` at `0x180029772`
- `msvcrt!free` at `0x1800297c7`
- `msvcrt!free` at `0x1800297d1`
- `msvcrt!free` at `0x18002982d`
- `msvcrt!free` at `0x180029837`
- `msvcrt!free` at `0x180029891`
- `msvcrt!free` at `0x18002989b`
- `msvcrt!free` at `0x1800298ee`
- `msvcrt!free` at `0x1800298f8`
- `msvcrt!free` at `0x18002994b`
- `msvcrt!free` at `0x180029955`
- `msvcrt!free` at `0x180029964`
- `msvcrt!free` at `0x18002996e`
- `ADVAPI32!SetFileSecurityW` at `0x180029910`
- `ADVAPI32!SetFileSecurityW` at `0x180029910`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x1800297f2`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180029856`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x1800297f2`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x180029856`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002972d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18002972d`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800298b3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800298b3`
- `ADVAPI32!InitializeAcl` at `0x18002978c`
- `ADVAPI32!InitializeAcl` at `0x18002978c`
- `ADVAPI32!GetLengthSid` at `0x1800296df`
- `ADVAPI32!GetLengthSid` at `0x1800296ee`
- `ADVAPI32!GetLengthSid` at `0x1800296df`
- `ADVAPI32!GetLengthSid` at `0x1800296ee`
- `KERNEL32!GetLastError` at `0x180029737`
- `KERNEL32!GetLastError` at `0x180029796`
- `KERNEL32!GetLastError` at `0x1800297fc`
- `KERNEL32!GetLastError` at `0x180029860`
- `KERNEL32!GetLastError` at `0x1800298bd`
- `KERNEL32!GetLastError` at `0x18002991a`
- `KERNEL32!GetLastError` at `0x180029737`
- `KERNEL32!GetLastError` at `0x180029796`
- `KERNEL32!GetLastError` at `0x1800297fc`
- `KERNEL32!GetLastError` at `0x180029860`
- `KERNEL32!GetLastError` at `0x1800298bd`
- `KERNEL32!GetLastError` at `0x18002991a`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MQSec_SetDirectorySecurityForService(LPCWSTR lpFileName)
{
  PSID pSid; // rdi
  int v3; // ebx
  unsigned int v4; // eax
  __int16 LengthSid; // bx
  void *v7; // r14
  DWORD v8; // r12d
  struct _ACL *v9; // rbx
  signed int v10; // eax
  signed int v11; // esi
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int LastError; // eax
  _OWORD pSecurityDescriptor[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v18; // [rsp+80h] [rbp+17h]
  struct _ACL *v19; // [rsp+D8h] [rbp+6Fh] BYREF
  int v20; // [rsp+E0h] [rbp+77h] BYREF
  void *Block; // [rsp+E8h] [rbp+7Fh] BYREF

  pSid = g_pAdminSid;
  Block = 0;
  v3 = MQSec_CalculateServiceSid(&Block);
  if ( v3 >= 0 )
  {
    LengthSid = GetLengthSid(pSid);
    v7 = Block;
    v8 = 2 * (unsigned __int16)(GetLengthSid(Block) + LengthSid + 8) + 8;
    v9 = (struct _ACL *)MmAllocate(v8);
    v19 = v9;
    memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
    v18 = 0;
    if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    {
      if ( InitializeAcl(v9, v8, 2u) )
      {
        if ( AddAccessAllowedAceEx(v9, 2u, 1u, 0x1F01FFu, pSid) )
        {
          if ( AddAccessAllowedAceEx(v9, 2u, 1u, 0x1F01FFu, v7) )
          {
            if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v9, 0) )
            {
              if ( SetFileSecurityW(lpFileName, 4u, pSecurityDescriptor) )
              {
                free(v9);
                free(v7);
                return 0;
              }
              LastError = GetLastError();
              v11 = LastError;
              if ( LastError > 0 )
                v11 = (unsigned __int16)LastError | 0x80070000;
              if ( v11 < 0 )
                LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x50u);
            }
            else
            {
              v15 = GetLastError();
              v11 = v15;
              if ( v15 > 0 )
                v11 = (unsigned __int16)v15 | 0x80070000;
              if ( v11 < 0 )
                LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x4Fu);
            }
          }
          else
          {
            v14 = GetLastError();
            v11 = v14;
            if ( v14 > 0 )
              v11 = (unsigned __int16)v14 | 0x80070000;
            if ( v11 < 0 )
              LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x4Eu);
          }
        }
        else
        {
          v13 = GetLastError();
          v11 = v13;
          if ( v13 > 0 )
            v11 = (unsigned __int16)v13 | 0x80070000;
          if ( v11 < 0 )
            LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x4Du);
        }
      }
      else
      {
        v12 = GetLastError();
        v11 = v12;
        if ( v12 > 0 )
          v11 = (unsigned __int16)v12 | 0x80070000;
        if ( v11 < 0 )
          LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x4Cu);
      }
    }
    else
    {
      v10 = GetLastError();
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( v11 < 0 )
        LogMsgHR(v11, (wchar_t *)L"acssctrl/privilge", 0x4Bu);
    }
    free(v9);
    free(v7);
    return (unsigned int)v11;
  }
  LOWORD(v19) = 70;
  v20 = v3;
  if ( g_pMSMQErrorLoggingTrace )
  {
    v4 = mqwcslen(L"acssctrl/privilge");
    CMSMQTrace::MSMQTraceEvent(
      g_pMSMQErrorLoggingTrace,
      1,
      1,
      2LL * (v4 + 1),
      L"acssctrl/privilge",
      2,
      &v19,
      4,
      &v20,
      0,
      0);
  }
  free(Block);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180029610  push    rbp
0x180029612  push    rbx
0x180029613  push    rsi
0x180029614  push    rdi
0x180029615  push    r12
0x180029617  push    r14
0x180029619  push    r15
0x18002961b  lea     rbp, [rsp-27h]
0x180029620  sub     rsp, 90h
0x180029627  mov     r15, rcx
0x18002962a  mov     rdi, cs:?g_pAdminSid@@3PEAXEA; void * g_pAdminSid
0x180029631  mov     [rbp+57h+Block], 0
0x180029639  lea     rcx, [rbp+57h+Block]; void **
0x18002963d  call    ?MQSec_CalculateServiceSid@@YAJPEAPEAX@Z; MQSec_CalculateServiceSid(void * *)
0x180029642  mov     ebx, eax
0x180029644  test    eax, eax
0x180029646  jns     loc_1800296DC
0x18002964c  mov     eax, 46h ; 'F'
0x180029651  mov     word ptr [rbp+57h+arg_8], ax
0x180029655  mov     [rbp+57h+arg_10], ebx
0x180029658  cmp     cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA, 0; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x180029660  jz      short loc_1800296CA
0x180029662  lea     rdi, aAcssctrlPrivil; "acssctrl/privilge"
0x180029669  mov     rcx, rdi; wchar_t *
0x18002966c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180029671  mov     esi, 1
0x180029676  lea     r9d, [rsi+rax]
0x18002967a  add     r9, r9
0x18002967d  mov     [rsp+0C0h+var_70], 0
0x180029686  mov     [rsp+0C0h+var_78], 0
0x18002968f  lea     rax, [rbp+57h+arg_10]
0x180029693  mov     [rsp+0C0h+var_80], rax
0x180029698  mov     [rsp+0C0h+var_88], 4
0x1800296a1  lea     rax, [rbp+57h+arg_8]
0x1800296a5  mov     [rsp+0C0h+var_90], rax
0x1800296aa  mov     [rsp+0C0h+var_98], 2
0x1800296b3  mov     [rsp+0C0h+pSid], rdi
0x1800296b8  mov     r8d, esi
0x1800296bb  mov     edx, esi
0x1800296bd  mov     rcx, cs:?g_pMSMQErrorLoggingTrace@@3PEAVCMSMQTrace@@EA; CMSMQTrace * g_pMSMQErrorLoggingTrace
0x1800296c4  call    ?MSMQTraceEvent@CMSMQTrace@@QEAAJW4TRACE_FLAGS@@KZZ; CMSMQTrace::MSMQTraceEvent(TRACE_FLAGS,ulong,...)
0x1800296c9  nop
0x1800296ca  mov     rcx, [rbp+57h+Block]; Block
0x1800296ce  call    cs:__imp_free
0x1800296d4  nop
0x1800296d5  mov     eax, ebx
0x1800296d7  jmp     loc_180029977
0x1800296dc  mov     rcx, rdi; pSid
0x1800296df  call    cs:__imp_GetLengthSid
0x1800296e5  mov     ebx, eax
0x1800296e7  mov     r14, [rbp+57h+Block]
0x1800296eb  mov     rcx, r14; pSid
0x1800296ee  call    cs:__imp_GetLengthSid
0x1800296f4  lea     ecx, [rbx+8]
0x1800296f7  add     ecx, eax
0x1800296f9  movzx   eax, cx
0x1800296fc  lea     r12d, ds:8[rax*2]
0x180029704  mov     ecx, r12d; unsigned __int64
0x180029707  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002970c  mov     rbx, rax
0x18002970f  mov     [rbp+57h+arg_8], rax
0x180029713  xorps   xmm0, xmm0
0x180029716  xor     eax, eax
0x180029718  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18002971c  movups  [rbp+57h+var_50], xmm0
0x180029720  mov     [rbp+57h+var_40], rax
0x180029724  lea     esi, [rax+1]
0x180029727  mov     edx, esi; dwRevision
0x180029729  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002972d  call    cs:__imp_InitializeSecurityDescriptor
0x180029733  test    eax, eax
0x180029735  jnz     short loc_180029780
0x180029737  call    cs:__imp_GetLastError
0x18002973d  mov     esi, eax
0x18002973f  test    eax, eax
0x180029741  jle     short loc_18002974C
0x180029743  movzx   esi, ax
0x180029746  or      esi, 80070000h
0x18002974c  test    esi, esi
0x18002974e  jns     short loc_180029765
0x180029750  mov     r8d, 4Bh ; 'K'; unsigned __int16
0x180029756  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x18002975d  mov     ecx, esi; int
0x18002975f  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029764  nop
0x180029765  mov     rcx, rbx; Block
0x180029768  call    cs:__imp_free
0x18002976e  nop
0x18002976f  mov     rcx, r14; Block
0x180029772  call    cs:__imp_free
0x180029778  nop
0x180029779  mov     eax, esi
0x18002977b  jmp     loc_180029977
0x180029780  mov     r8d, 2; dwAclRevision
0x180029786  mov     edx, r12d; nAclLength
0x180029789  mov     rcx, rbx; pAcl
0x18002978c  call    cs:__imp_InitializeAcl
0x180029792  test    eax, eax
0x180029794  jnz     short loc_1800297DA
0x180029796  call    cs:__imp_GetLastError
0x18002979c  mov     esi, eax
0x18002979e  test    eax, eax
0x1800297a0  jle     short loc_1800297AB
0x1800297a2  movzx   esi, ax
0x1800297a5  or      esi, 80070000h
0x1800297ab  test    esi, esi
0x1800297ad  jns     short loc_1800297C4
0x1800297af  mov     r8d, 4Ch ; 'L'; unsigned __int16
0x1800297b5  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x1800297bc  mov     ecx, esi; int
0x1800297be  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800297c3  nop
0x1800297c4  mov     rcx, rbx; Block
0x1800297c7  call    cs:__imp_free
0x1800297cd  nop
0x1800297ce  mov     rcx, r14; Block
0x1800297d1  call    cs:__imp_free
0x1800297d7  nop
0x1800297d8  jmp     short loc_180029779
0x1800297da  mov     [rsp+0C0h+pSid], rdi; pSid
0x1800297df  mov     edi, 1F01FFh
0x1800297e4  mov     r9d, edi; AccessMask
0x1800297e7  mov     r8d, esi; AceFlags
0x1800297ea  mov     edx, 2; dwAceRevision
0x1800297ef  mov     rcx, rbx; pAcl
0x1800297f2  call    cs:__imp_AddAccessAllowedAceEx
0x1800297f8  test    eax, eax
0x1800297fa  jnz     short loc_180029843
0x1800297fc  call    cs:__imp_GetLastError
0x180029802  mov     esi, eax
0x180029804  test    eax, eax
0x180029806  jle     short loc_180029811
0x180029808  movzx   esi, ax
0x18002980b  or      esi, 80070000h
0x180029811  test    esi, esi
0x180029813  jns     short loc_18002982A
0x180029815  mov     r8d, 4Dh ; 'M'; unsigned __int16
0x18002981b  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029822  mov     ecx, esi; int
0x180029824  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029829  nop
0x18002982a  mov     rcx, rbx; Block
0x18002982d  call    cs:__imp_free
0x180029833  nop
0x180029834  mov     rcx, r14; Block
0x180029837  call    cs:__imp_free
0x18002983d  nop
0x18002983e  jmp     loc_180029779
0x180029843  mov     [rsp+0C0h+pSid], r14; pSid
0x180029848  mov     r9d, edi; AccessMask
0x18002984b  mov     r8d, esi; AceFlags
0x18002984e  mov     edx, 2; dwAceRevision
0x180029853  mov     rcx, rbx; pAcl
0x180029856  call    cs:__imp_AddAccessAllowedAceEx
0x18002985c  test    eax, eax
0x18002985e  jnz     short loc_1800298A7
0x180029860  call    cs:__imp_GetLastError
0x180029866  mov     esi, eax
0x180029868  test    eax, eax
0x18002986a  jle     short loc_180029875
0x18002986c  movzx   esi, ax
0x18002986f  or      esi, 80070000h
0x180029875  test    esi, esi
0x180029877  jns     short loc_18002988E
0x180029879  mov     r8d, 4Eh ; 'N'; unsigned __int16
0x18002987f  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029886  mov     ecx, esi; int
0x180029888  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002988d  nop
0x18002988e  mov     rcx, rbx; Block
0x180029891  call    cs:__imp_free
0x180029897  nop
0x180029898  mov     rcx, r14; Block
0x18002989b  call    cs:__imp_free
0x1800298a1  nop
0x1800298a2  jmp     loc_180029779
0x1800298a7  xor     r9d, r9d; bDaclDefaulted
0x1800298aa  mov     r8, rbx; pDacl
0x1800298ad  mov     edx, esi; bDaclPresent
0x1800298af  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800298b3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800298b9  test    eax, eax
0x1800298bb  jnz     short loc_180029904
0x1800298bd  call    cs:__imp_GetLastError
0x1800298c3  mov     esi, eax
0x1800298c5  test    eax, eax
0x1800298c7  jle     short loc_1800298D2
0x1800298c9  movzx   esi, ax
0x1800298cc  or      esi, 80070000h
0x1800298d2  test    esi, esi
0x1800298d4  jns     short loc_1800298EB
0x1800298d6  mov     r8d, 4Fh ; 'O'; unsigned __int16
0x1800298dc  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x1800298e3  mov     ecx, esi; int
0x1800298e5  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x1800298ea  nop
0x1800298eb  mov     rcx, rbx; Block
0x1800298ee  call    cs:__imp_free
0x1800298f4  nop
0x1800298f5  mov     rcx, r14; Block
0x1800298f8  call    cs:__imp_free
0x1800298fe  nop
0x1800298ff  jmp     loc_180029779
0x180029904  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x180029908  mov     edx, 4; SecurityInformation
0x18002990d  mov     rcx, r15; lpFileName
0x180029910  call    cs:__imp_SetFileSecurityW
0x180029916  test    eax, eax
0x180029918  jnz     short loc_180029961
0x18002991a  call    cs:__imp_GetLastError
0x180029920  mov     esi, eax
0x180029922  test    eax, eax
0x180029924  jle     short loc_18002992F
0x180029926  movzx   esi, ax
0x180029929  or      esi, 80070000h
0x18002992f  test    esi, esi
0x180029931  jns     short loc_180029948
0x180029933  mov     r8d, 50h ; 'P'; unsigned __int16
0x180029939  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x180029940  mov     ecx, esi; int
0x180029942  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180029947  nop
0x180029948  mov     rcx, rbx; Block
0x18002994b  call    cs:__imp_free
0x180029951  nop
0x180029952  mov     rcx, r14; Block
0x180029955  call    cs:__imp_free
0x18002995b  nop
0x18002995c  jmp     loc_180029779
0x180029961  mov     rcx, rbx; Block
0x180029964  call    cs:__imp_free
0x18002996a  nop
0x18002996b  mov     rcx, r14; Block
0x18002996e  call    cs:__imp_free
0x180029974  nop
0x180029975  xor     eax, eax
0x180029977  add     rsp, 90h
0x18002997e  pop     r15
0x180029980  pop     r14
0x180029982  pop     r12
0x180029984  pop     rdi
0x180029985  pop     rsi
0x180029986  pop     rbx
0x180029987  pop     rbp
0x180029988  retn
```
