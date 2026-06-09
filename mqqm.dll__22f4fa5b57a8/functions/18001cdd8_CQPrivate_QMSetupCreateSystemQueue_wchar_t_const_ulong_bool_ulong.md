# CQPrivate::QMSetupCreateSystemQueue(wchar_t const *,ulong,bool,ulong)

- ea: `0x18001cdd8`
- end: `0x18001d2b0`
- name: `?QMSetupCreateSystemQueue@CQPrivate@@QEAAJPEB_WK_NK@Z`
- size: `1240`
- prototype: `int(CQPrivate *__hidden this, const wchar_t *, unsigned int, bool, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180039cc8`
- `0x18005e564`

## callees

- `0x18000f35c`
- `0x180011578`
- `0x18001b388`
- `0x18001b3c4`
- `0x18001cdd8`
- `0x18001d438`
- `0x18001d5e0`
- `0x180029394`
- `0x18002c61c`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x18001ce8a`
- `msvcrt!free` at `0x18001ce93`
- `msvcrt!free` at `0x18001ce9d`
- `msvcrt!free` at `0x18001cea8`
- `msvcrt!free` at `0x18001ceb1`
- `msvcrt!free` at `0x18001d04b`
- `msvcrt!free` at `0x18001d055`
- `msvcrt!free` at `0x18001d05f`
- `msvcrt!free` at `0x18001d06a`
- `msvcrt!free` at `0x18001d073`
- `msvcrt!free` at `0x18001d0d2`
- `msvcrt!free` at `0x18001d0dc`
- `msvcrt!free` at `0x18001d0e6`
- `msvcrt!free` at `0x18001d0f1`
- `msvcrt!free` at `0x18001d0fc`
- `msvcrt!free` at `0x18001d13a`
- `msvcrt!free` at `0x18001d144`
- `msvcrt!free` at `0x18001d14e`
- `msvcrt!free` at `0x18001d159`
- `msvcrt!free` at `0x18001d164`
- `msvcrt!free` at `0x18001d263`
- `msvcrt!free` at `0x18001d26d`
- `msvcrt!free` at `0x18001d277`
- `msvcrt!free` at `0x18001d282`
- `msvcrt!free` at `0x18001d28c`
- `msvcrt!free` at `0x18001ce8a`
- `msvcrt!free` at `0x18001ce93`
- `msvcrt!free` at `0x18001ce9d`
- `msvcrt!free` at `0x18001cea8`
- `msvcrt!free` at `0x18001ceb1`
- `msvcrt!free` at `0x18001d04b`
- `msvcrt!free` at `0x18001d055`
- `msvcrt!free` at `0x18001d05f`
- `msvcrt!free` at `0x18001d06a`
- `msvcrt!free` at `0x18001d073`
- `msvcrt!free` at `0x18001d0d2`
- `msvcrt!free` at `0x18001d0dc`
- `msvcrt!free` at `0x18001d0e6`
- `msvcrt!free` at `0x18001d0f1`
- `msvcrt!free` at `0x18001d0fc`
- `msvcrt!free` at `0x18001d13a`
- `msvcrt!free` at `0x18001d144`
- `msvcrt!free` at `0x18001d14e`
- `msvcrt!free` at `0x18001d159`
- `msvcrt!free` at `0x18001d164`
- `msvcrt!free` at `0x18001d263`
- `msvcrt!free` at `0x18001d26d`
- `msvcrt!free` at `0x18001d277`
- `msvcrt!free` at `0x18001d282`
- `msvcrt!free` at `0x18001d28c`
- `msvcrt!wcschr` at `0x18001d110`
- `msvcrt!wcschr` at `0x18001d110`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf5f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf7b`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf92`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cfa6`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf5f`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf7b`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cf92`
- `ADVAPI32!AddAccessAllowedAce` at `0x18001cfa6`
- `ADVAPI32!GetLengthSid` at `0x18001cec3`
- `ADVAPI32!GetLengthSid` at `0x18001cee0`
- `ADVAPI32!GetLengthSid` at `0x18001cf07`
- `ADVAPI32!GetLengthSid` at `0x18001cf1b`
- `ADVAPI32!GetLengthSid` at `0x18001cec3`
- `ADVAPI32!GetLengthSid` at `0x18001cee0`
- `ADVAPI32!GetLengthSid` at `0x18001cf07`
- `ADVAPI32!GetLengthSid` at `0x18001cf1b`
- `ADVAPI32!InitializeAcl` at `0x18001cf45`
- `ADVAPI32!InitializeAcl` at `0x18001cf45`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001ce6c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18001ce6c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001cfb9`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18001cfb9`
- `mqsec!MQSec_GetWorldSid` at `0x18001cee8`
- `mqsec!MQSec_GetWorldSid` at `0x18001cee8`
- `mqsec!MQSec_CalculateServiceSid` at `0x18001ce7a`
- `mqsec!MQSec_CalculateServiceSid` at `0x18001ce7a`
- `mqsec!MQSec_GetAnonymousSid` at `0x18001ced4`
- `mqsec!MQSec_GetAnonymousSid` at `0x18001ced4`
- `mqsec!MQSec_GetAdminSid` at `0x18001cefb`
- `mqsec!MQSec_GetAdminSid` at `0x18001cefb`
- `mqsec!MQSec_GetNetworkServiceSid` at `0x18001cf0f`
- `mqsec!MQSec_GetNetworkServiceSid` at `0x18001cf0f`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x18001cfd8`
- `mqsec!MQSec_GetDefaultPrivateQueueSecurityDescriptor` at `0x18001cfd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CQPrivate::QMSetupCreateSystemQueue(
        CQPrivate *this,
        const wchar_t *a2,
        unsigned int a3,
        char a4,
        LONG a5)
{
  void *AdminSid; // r12
  void *v8; // rdi
  int v9; // ebx
  void *v11; // r15
  void *AnonymousSid; // r13
  DWORD v13; // ebx
  void *NetworkServiceSid; // rax
  DWORD v15; // esi
  struct _ACL *v16; // rbx
  void *v17; // r9
  DWORD v18; // r8d
  CQPrivate *v19; // rcx
  int DefaultPrivateQueueSecurityDescriptor; // esi
  int v21; // esi
  int v22; // eax
  __int64 v23; // rcx
  wchar_t *v24; // r8
  int v25; // eax
  struct tagPROPVARIANT *v26; // r15
  __int64 v27; // r8
  int v28; // eax
  LARGE_INTEGER v29; // r8
  int v30; // eax
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  __int64 v35; // r8
  int v36; // eax
  unsigned __int8 v37; // r9
  wchar_t *v38; // r8
  DWORD LengthSid; // [rsp+58h] [rbp-21h]
  void *Block; // [rsp+60h] [rbp-19h] BYREF
  void *v41; // [rsp+68h] [rbp-11h] BYREF
  struct tagPROPVARIANT *v42; // [rsp+70h] [rbp-9h] BYREF
  PSID pSid; // [rsp+78h] [rbp-1h]
  unsigned int *v44; // [rsp+80h] [rbp+7h] BYREF
  void *v45; // [rsp+88h] [rbp+Fh]
  struct _ACL *v46; // [rsp+90h] [rbp+17h]
  void *v47; // [rsp+D8h] [rbp+5Fh] BYREF
  unsigned int v48; // [rsp+E8h] [rbp+6Fh]
  char v49; // [rsp+F0h] [rbp+77h]

  v49 = a4;
  v48 = a3;
  v47 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
  AdminSid = 0;
  LODWORD(v47) = 0;
  v44 = 0;
  v42 = 0;
  v41 = 0;
  v45 = 0;
  v46 = 0;
  v8 = MmAllocate(0x28u);
  v45 = v8;
  InitializeSecurityDescriptor(v8, 1u);
  Block = 0;
  v9 = MQSec_CalculateServiceSid(&Block);
  if ( v9 >= 0 )
  {
    LengthSid = GetLengthSid(Block);
    if ( a4 )
    {
      AnonymousSid = 0;
      pSid = 0;
      AdminSid = MQSec_GetAdminSid();
      v13 = GetLengthSid(AdminSid);
      NetworkServiceSid = MQSec_GetNetworkServiceSid();
      v11 = NetworkServiceSid;
    }
    else
    {
      v11 = 0;
      AnonymousSid = MQSec_GetAnonymousSid();
      v13 = GetLengthSid(AnonymousSid);
      NetworkServiceSid = MQSec_GetWorldSid();
      pSid = NetworkServiceSid;
    }
    v15 = GetLengthSid(NetworkServiceSid) + v13 + LengthSid + 32;
    v16 = (struct _ACL *)MmAllocate(v15);
    v46 = v16;
    InitializeAcl(v16, v15, 2u);
    AddAccessAllowedAce(v16, 2u, 0xE003Fu, Block);
    if ( v49 )
    {
      AddAccessAllowedAce(v16, 2u, 0x6003Fu, AdminSid);
      v17 = v11;
      v18 = 917567;
    }
    else
    {
      AddAccessAllowedAce(v16, 2u, 4u, pSid);
      v17 = AnonymousSid;
      v18 = 4;
    }
    AddAccessAllowedAce(v16, 2u, v18, v17);
    SetSecurityDescriptorDacl(v8, 1, v16, 0);
    DefaultPrivateQueueSecurityDescriptor = MQSec_GetDefaultPrivateQueueSecurityDescriptor(&v41, 0, v8, 0, 0, 0);
    if ( DefaultPrivateQueueSecurityDescriptor >= 0 )
    {
      v22 = CQPrivate::SetQueueProperties(v19, a2, v41, 0, 0, 0, (unsigned int *)&v47, &v44, &v42);
      v21 = v22;
      if ( v22 >= 0 )
      {
        v24 = wcschr(a2, 0x5Cu);
        if ( v24 )
        {
          v25 = PROPERTY_MAP::operator[](v23, 103, v24);
          v26 = v42;
          v42[v25].hVal.QuadPart = (LONGLONG)a2;
          v28 = PROPERTY_MAP::operator[](v25, 108, v27 + 2);
          v26[v28].hVal = v29;
          v30 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))PROPERTY_MAP::operator[])(
                  v28,
                  5001,
                  (LARGE_INTEGER)v29.QuadPart);
          v26[v30].cVal = 1;
          v32 = PROPERTY_MAP::operator[](v30, 111, v31);
          v26[v32].cVal = 0;
          v34 = PROPERTY_MAP::operator[](v32, 106, v33);
          v26[v34].lVal = 0x7FFF;
          v36 = PROPERTY_MAP::operator[](v34, 105, v35);
          v26[v36].lVal = a5;
          v21 = CQPrivate::RegisterPrivateQueueProperties((CQPrivate *)v36, a2, v48, v37, (unsigned int)v47, v44, v26);
          if ( v21 < 0 || (v47 = 0, v21 = LQSOpen(a2, &v47, v38), CHLQS::~CHLQS((CHLQS *)&v47), v21 < 0) )
            LogMsgHR(v21, (wchar_t *)L"cqpriv", 0x2Du);
          free(Block);
          free(v16);
          free(v8);
          free(v41);
          free(v26);
        }
        else
        {
          v21 = -1072824319;
          LogMsgHR(-1072824319, (wchar_t *)L"cqpriv", 0x28u);
          free(Block);
          free(v16);
          free(v8);
          free(v41);
          free(v42);
        }
      }
      else
      {
        LogMsgHR(v22, (wchar_t *)L"cqpriv", 0x1Eu);
        free(Block);
        free(v16);
        free(v8);
        free(v41);
        free(v42);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids,
          (unsigned int)DefaultPrivateQueueSecurityDescriptor);
      LogMsgHR(DefaultPrivateQueueSecurityDescriptor, (wchar_t *)L"cqpriv", 0x452u);
      v21 = -1072824281;
      LogMsgHR(-1072824281, (wchar_t *)L"cqpriv", 0x451u);
      free(Block);
      free(v16);
      free(v8);
      free(v41);
      free(0);
    }
    return (unsigned int)v21;
  }
  else
  {
    free(Block);
    free(0);
    free(v8);
    free(v41);
    free(0);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x18001cdd8  mov     rax, rsp
0x18001cddb  mov     [rax+10h], rbx
0x18001cddf  mov     [rax+20h], r9b
0x18001cde3  mov     [rax+18h], r8d
0x18001cde7  mov     [rax+8], rcx
0x18001cdeb  push    rbp
0x18001cdec  push    rsi
0x18001cded  push    rdi
0x18001cdee  push    r12
0x18001cdf0  push    r13
0x18001cdf2  push    r14
0x18001cdf4  push    r15
0x18001cdf6  lea     rbp, [rax-57h]
0x18001cdfa  sub     rsp, 90h
0x18001ce01  mov     sil, r9b
0x18001ce04  mov     r14, rdx
0x18001ce07  lea     rax, WPP_GLOBAL_Control
0x18001ce0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce15  cmp     rcx, rax
0x18001ce18  jz      short loc_18001CE38
0x18001ce1a  test    byte ptr [rcx+1Ch], 4
0x18001ce1e  jz      short loc_18001CE38
0x18001ce20  mov     edx, 0Bh
0x18001ce25  mov     r9, r14
0x18001ce28  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001ce2f  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ce33  call    WPP_SF_S
0x18001ce38  xor     r12d, r12d
0x18001ce3b  mov     dword ptr [rbp+4Fh+arg_0], r12d
0x18001ce3f  mov     [rbp+4Fh+var_48], r12
0x18001ce43  mov     [rbp+4Fh+var_58], r12
0x18001ce47  mov     [rbp+4Fh+var_60], r12
0x18001ce4b  mov     [rbp+4Fh+var_40], r12
0x18001ce4f  mov     [rbp+4Fh+var_38], r12
0x18001ce53  lea     ecx, [r12+28h]; unsigned __int64
0x18001ce58  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001ce5d  mov     rdi, rax
0x18001ce60  mov     [rbp+4Fh+var_40], rax
0x18001ce64  lea     edx, [r12+1]; dwRevision
0x18001ce69  mov     rcx, rax; pSecurityDescriptor
0x18001ce6c  call    cs:__imp_InitializeSecurityDescriptor
0x18001ce72  mov     [rbp+4Fh+Block], r12
0x18001ce76  lea     rcx, [rbp+4Fh+Block]
0x18001ce7a  call    cs:__imp_?MQSec_CalculateServiceSid@@YAJPEAPEAX@Z; MQSec_CalculateServiceSid(void * *)
0x18001ce80  mov     ebx, eax
0x18001ce82  test    eax, eax
0x18001ce84  jns     short loc_18001CEBF
0x18001ce86  mov     rcx, [rbp+4Fh+Block]; Block
0x18001ce8a  call    cs:__imp_free
0x18001ce90  nop
0x18001ce91  xor     ecx, ecx; Block
0x18001ce93  call    cs:__imp_free
0x18001ce99  nop
0x18001ce9a  mov     rcx, rdi; Block
0x18001ce9d  call    cs:__imp_free
0x18001cea3  nop
0x18001cea4  mov     rcx, [rbp+4Fh+var_60]; Block
0x18001cea8  call    cs:__imp_free
0x18001ceae  nop
0x18001ceaf  xor     ecx, ecx; Block
0x18001ceb1  call    cs:__imp_free
0x18001ceb7  nop
0x18001ceb8  mov     eax, ebx
0x18001ceba  jmp     loc_18001D295
0x18001cebf  mov     rcx, [rbp+4Fh+Block]; pSid
0x18001cec3  call    cs:__imp_GetLengthSid
0x18001cec9  mov     [rbp+4Fh+var_70], eax
0x18001cecc  test    sil, sil
0x18001cecf  jnz     short loc_18001CEF4
0x18001ced1  mov     r15, r12
0x18001ced4  call    cs:__imp_?MQSec_GetAnonymousSid@@YAPEAXXZ; MQSec_GetAnonymousSid(void)
0x18001ceda  mov     r13, rax
0x18001cedd  mov     rcx, rax; pSid
0x18001cee0  call    cs:__imp_GetLengthSid
0x18001cee6  mov     ebx, eax
0x18001cee8  call    cs:__imp_?MQSec_GetWorldSid@@YAPEAXXZ; MQSec_GetWorldSid(void)
0x18001ceee  mov     [rbp+4Fh+pSid], rax
0x18001cef2  jmp     short loc_18001CF18
0x18001cef4  mov     r13, r12
0x18001cef7  mov     [rbp+4Fh+pSid], r12
0x18001cefb  call    cs:__imp_?MQSec_GetAdminSid@@YAPEAXXZ; MQSec_GetAdminSid(void)
0x18001cf01  mov     r12, rax
0x18001cf04  mov     rcx, rax; pSid
0x18001cf07  call    cs:__imp_GetLengthSid
0x18001cf0d  mov     ebx, eax
0x18001cf0f  call    cs:__imp_?MQSec_GetNetworkServiceSid@@YAPEAXXZ; MQSec_GetNetworkServiceSid(void)
0x18001cf15  mov     r15, rax
0x18001cf18  mov     rcx, rax; pSid
0x18001cf1b  call    cs:__imp_GetLengthSid
0x18001cf21  lea     ecx, [rax+rbx]
0x18001cf24  mov     esi, [rbp+4Fh+var_70]
0x18001cf27  add     esi, 20h ; ' '
0x18001cf2a  add     esi, ecx
0x18001cf2c  mov     ecx, esi; unsigned __int64
0x18001cf2e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001cf33  mov     rbx, rax
0x18001cf36  mov     [rbp+4Fh+var_38], rax
0x18001cf3a  mov     r8d, 2; dwAclRevision
0x18001cf40  mov     edx, esi; nAclLength
0x18001cf42  mov     rcx, rax; pAcl
0x18001cf45  call    cs:__imp_InitializeAcl
0x18001cf4b  mov     r9, [rbp+4Fh+Block]; pSid
0x18001cf4f  mov     esi, 2
0x18001cf54  mov     r8d, 0E003Fh; AccessMask
0x18001cf5a  mov     edx, esi; dwAceRevision
0x18001cf5c  mov     rcx, rbx; pAcl
0x18001cf5f  call    cs:__imp_AddAccessAllowedAce
0x18001cf65  mov     edx, esi; dwAceRevision
0x18001cf67  mov     rcx, rbx; pAcl
0x18001cf6a  cmp     [rbp+4Fh+arg_18], 0
0x18001cf6e  jnz     short loc_18001CF89
0x18001cf70  mov     r9, [rbp+4Fh+pSid]; pSid
0x18001cf74  lea     r15d, [rsi+2]
0x18001cf78  mov     r8d, r15d; AccessMask
0x18001cf7b  call    cs:__imp_AddAccessAllowedAce
0x18001cf81  mov     r9, r13
0x18001cf84  mov     r8d, r15d
0x18001cf87  jmp     short loc_18001CFA1
0x18001cf89  mov     r9, r12; pSid
0x18001cf8c  mov     r8d, 6003Fh; AccessMask
0x18001cf92  call    cs:__imp_AddAccessAllowedAce
0x18001cf98  mov     r9, r15; pSid
0x18001cf9b  mov     r8d, 0E003Fh; AccessMask
0x18001cfa1  mov     edx, esi; dwAceRevision
0x18001cfa3  mov     rcx, rbx; pAcl
0x18001cfa6  call    cs:__imp_AddAccessAllowedAce
0x18001cfac  xor     r9d, r9d; bDaclDefaulted
0x18001cfaf  mov     r8, rbx; pDacl
0x18001cfb2  lea     edx, [r9+1]; bDaclPresent
0x18001cfb6  mov     rcx, rdi; pSecurityDescriptor
0x18001cfb9  call    cs:__imp_SetSecurityDescriptorDacl
0x18001cfbf  xor     r12d, r12d
0x18001cfc2  mov     [rsp+0C0h+var_98], r12
0x18001cfc7  mov     dword ptr [rsp+0C0h+var_A0], r12d
0x18001cfcc  xor     r9d, r9d
0x18001cfcf  mov     r8, rdi
0x18001cfd2  xor     edx, edx
0x18001cfd4  lea     rcx, [rbp+4Fh+var_60]
0x18001cfd8  call    cs:__imp_?MQSec_GetDefaultPrivateQueueSecurityDescriptor@@YAJPEAPEAXHPEAXKW4enumDaclType@@1@Z; MQSec_GetDefaultPrivateQueueSecurityDescriptor(void * *,int,void *,ulong,enumDaclType,void *)
0x18001cfde  mov     esi, eax
0x18001cfe0  test    eax, eax
0x18001cfe2  jns     loc_18001D07F
0x18001cfe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfef  lea     rax, WPP_GLOBAL_Control
0x18001cff6  cmp     rcx, rax
0x18001cff9  jz      short loc_18001D019
0x18001cffb  test    byte ptr [rcx+1Ch], 1
0x18001cfff  jz      short loc_18001D019
0x18001d001  lea     edx, [r12+0Ch]
0x18001d006  mov     r9d, esi
0x18001d009  lea     r8, WPP_9e5e5d50122933ccaaa31007e157135b_Traceguids
0x18001d010  mov     rcx, [rcx+10h]
0x18001d014  call    WPP_SF_d
0x18001d019  mov     r8d, 452h; unsigned __int16
0x18001d01f  lea     rdx, aCqpriv; "cqpriv"
0x18001d026  mov     ecx, esi; int
0x18001d028  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d02d  mov     r8d, 451h; unsigned __int16
0x18001d033  lea     rdx, aCqpriv; "cqpriv"
0x18001d03a  mov     esi, 0C00E0027h
0x18001d03f  mov     ecx, esi; int
0x18001d041  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d046  nop
0x18001d047  mov     rcx, [rbp+4Fh+Block]; Block
0x18001d04b  call    cs:__imp_free
0x18001d051  nop
0x18001d052  mov     rcx, rbx; Block
0x18001d055  call    cs:__imp_free
0x18001d05b  nop
0x18001d05c  mov     rcx, rdi; Block
0x18001d05f  call    cs:__imp_free
0x18001d065  nop
0x18001d066  mov     rcx, [rbp+4Fh+var_60]; Block
0x18001d06a  call    cs:__imp_free
0x18001d070  nop
0x18001d071  xor     ecx, ecx; Block
0x18001d073  call    cs:__imp_free
0x18001d079  nop
0x18001d07a  jmp     loc_18001D293
0x18001d07f  lea     rax, [rbp+4Fh+var_58]
0x18001d083  mov     [rsp+40h], rax; struct tagPROPVARIANT **
0x18001d088  lea     rax, [rbp+4Fh+var_48]
0x18001d08c  mov     [rsp+0C0h+var_88], rax; unsigned int **
0x18001d091  lea     rax, [rbp+4Fh+arg_0]
0x18001d095  mov     [rsp+0C0h+var_90], rax; unsigned int *
0x18001d09a  mov     [rsp+0C0h+var_98], r12; struct tagPROPVARIANT *
0x18001d09f  mov     [rsp+0C0h+var_A0], r12; unsigned int *
0x18001d0a4  xor     r9d, r9d; unsigned int
0x18001d0a7  mov     r8, [rbp+4Fh+var_60]; void *
0x18001d0ab  mov     rdx, r14; wchar_t *
0x18001d0ae  call    ?SetQueueProperties@CQPrivate@@AEAAJPEB_WPEAXKQEAKQEAUtagPROPVARIANT@@PEAKPEAPEAKPEAPEAU2@@Z; CQPrivate::SetQueueProperties(wchar_t const *,void *,ulong,ulong * const,tagPROPVARIANT * const,ulong *,ulong * *,tagPROPVARIANT * *)
0x18001d0b3  mov     esi, eax
0x18001d0b5  test    eax, eax
0x18001d0b7  jns     short loc_18001D108
0x18001d0b9  mov     r8d, 1Eh; unsigned __int16
0x18001d0bf  lea     rdx, aCqpriv; "cqpriv"
0x18001d0c6  mov     ecx, eax; int
0x18001d0c8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d0cd  nop
0x18001d0ce  mov     rcx, [rbp+4Fh+Block]; Block
0x18001d0d2  call    cs:__imp_free
0x18001d0d8  nop
0x18001d0d9  mov     rcx, rbx; Block
0x18001d0dc  call    cs:__imp_free
0x18001d0e2  nop
0x18001d0e3  mov     rcx, rdi; Block
0x18001d0e6  call    cs:__imp_free
0x18001d0ec  nop
0x18001d0ed  mov     rcx, [rbp+4Fh+var_60]; Block
0x18001d0f1  call    cs:__imp_free
0x18001d0f7  nop
0x18001d0f8  mov     rcx, [rbp+4Fh+var_58]; Block
0x18001d0fc  call    cs:__imp_free
0x18001d102  nop
0x18001d103  jmp     loc_18001D293
0x18001d108  mov     edx, 5Ch ; '\'; Ch
0x18001d10d  mov     rcx, r14; Str
0x18001d110  call    cs:__imp_wcschr
0x18001d116  mov     r8, rax
0x18001d119  test    rax, rax
0x18001d11c  jnz     short loc_18001D170
0x18001d11e  lea     r8d, [rax+28h]; unsigned __int16
0x18001d122  lea     rdx, aCqpriv; "cqpriv"
0x18001d129  mov     esi, 0C00E0001h
0x18001d12e  mov     ecx, esi; int
0x18001d130  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18001d135  nop
0x18001d136  mov     rcx, [rbp+4Fh+Block]; Block
0x18001d13a  call    cs:__imp_free
0x18001d140  nop
0x18001d141  mov     rcx, rbx; Block
0x18001d144  call    cs:__imp_free
0x18001d14a  nop
0x18001d14b  mov     rcx, rdi; Block
0x18001d14e  call    cs:__imp_free
0x18001d154  nop
0x18001d155  mov     rcx, [rbp+4Fh+var_60]; Block
0x18001d159  call    cs:__imp_free
0x18001d15f  nop
0x18001d160  mov     rcx, [rbp+4Fh+var_58]; Block
0x18001d164  call    cs:__imp_free
0x18001d16a  nop
0x18001d16b  jmp     loc_18001D293
0x18001d170  mov     edx, 67h ; 'g'
0x18001d175  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d17a  movsxd  rcx, eax
0x18001d17d  lea     rax, [rcx+rcx*2]
0x18001d181  mov     r15, [rbp+4Fh+var_58]
0x18001d185  mov     [r15+rax*8+8], r14
0x18001d18a  add     r8, 2
0x18001d18e  mov     edx, 6Ch ; 'l'
0x18001d193  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d198  movsxd  rcx, eax
0x18001d19b  lea     rax, [rcx+rcx*2]
0x18001d19f  mov     [r15+rax*8+8], r8
0x18001d1a4  mov     edx, 1389h
0x18001d1a9  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d1ae  movsxd  rcx, eax
0x18001d1b1  lea     rax, [rcx+rcx*2]
0x18001d1b5  mov     byte ptr [r15+rax*8+8], 1
0x18001d1bb  mov     edx, 6Fh ; 'o'
0x18001d1c0  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d1c5  movsxd  rcx, eax
0x18001d1c8  lea     rax, [rcx+rcx*2]
0x18001d1cc  mov     [r15+rax*8+8], r12b
0x18001d1d1  mov     edx, 6Ah ; 'j'
0x18001d1d6  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d1db  movsxd  rcx, eax
0x18001d1de  lea     rax, [rcx+rcx*2]
0x18001d1e2  mov     dword ptr [r15+rax*8+8], 7FFFh
0x18001d1eb  mov     edx, 69h ; 'i'
0x18001d1f0  call    ??APROPERTY_MAP@@QEAAHK@Z; PROPERTY_MAP::operator[](ulong)
0x18001d1f5  movsxd  rcx, eax; this
0x18001d1f8  lea     rdx, [rcx+rcx*2]
0x18001d1fc  mov     eax, [rbp+4Fh+arg_20]
0x18001d1ff  mov     [r15+rdx*8+8], eax
0x18001d204  mov     [rsp+0C0h+var_90], r15; struct tagPROPVARIANT *
0x18001d209  mov     rax, [rbp+4Fh+var_48]
0x18001d20d  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x18001d212  mov     eax, dword ptr [rbp+4Fh+arg_0]
0x18001d215  mov     dword ptr [rsp+0C0h+var_A0], eax; unsigned int
0x18001d219  mov     r8d, [rbp+4Fh+arg_10]; unsigned int
0x18001d21d  mov     rdx, r14; wchar_t *
0x18001d220  call    ?RegisterPrivateQueueProperties@CQPrivate@@AEAAJPEB_WKEKQEAKQEAUtagPROPVARIANT@@@Z; CQPrivate::RegisterPrivateQueueProperties(wchar_t const *,ulong,uchar,ulong,ulong * const,tagPROPVARIANT * const)
0x18001d225  mov     esi, eax
0x18001d227  test    eax, eax
0x18001d229  js      short loc_18001D24A
0x18001d22b  mov     [rbp+4Fh+arg_0], r12
0x18001d22f  lea     rdx, [rbp+4Fh+arg_0]; void **
0x18001d233  mov     rcx, r14; wchar_t *
0x18001d236  call    ?LQSOpen@@YAJPEB_WPEAPEAXPEA_W@Z; LQSOpen(wchar_t const *,void * *,wchar_t *)
0x18001d23b  mov     esi, eax
0x18001d23d  lea     rcx, [rbp+4Fh+arg_0]; this
0x18001d241  call    ??1CHLQS@@QEAA@XZ; CHLQS::~CHLQS(void)
0x18001d246  test    esi, esi
0x18001d248  jns     short loc_18001D25F
0x18001d24a  mov     r8d, 2Dh ; '-'; unsigned __int16
0x18001d250  lea     rdx, aCqpriv; "cqpriv"
0x18001d257  mov     ecx, esi; int
0x18001d259  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
  ... truncated ...
```
