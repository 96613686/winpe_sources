# MQSec_AccessCheckForSelf(_SECURITY_DESCRIPTOR *,ulong,void *,ulong,int)

- ea: `0x18001fa40`
- end: `0x18001fd68`
- name: `?MQSec_AccessCheckForSelf@@YAJPEAU_SECURITY_DESCRIPTOR@@KPEAXKH@Z`
- size: `808`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR pSecurityDescriptor@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, int)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800041cc`
- `0x1800049ac`
- `0x18000c39c`
- `0x18001722c`
- `0x18001adf4`
- `0x18001f3e0`
- `0x18001fa40`
- `0x1800254f4`
- `0x180028214`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `ADVAPI32!AccessCheckByTypeResultList` at `0x18001fc0d`
- `ADVAPI32!AccessCheckByTypeResultList` at `0x18001fc0d`
- `ADVAPI32!AreAllAccessesGranted` at `0x18001fc58`
- `ADVAPI32!AreAllAccessesGranted` at `0x18001fc58`
- `KERNEL32!GetLastError` at `0x18001fc17`
- `KERNEL32!GetLastError` at `0x18001fcaa`
- `KERNEL32!GetLastError` at `0x18001fc17`
- `KERNEL32!GetLastError` at `0x18001fcaa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MQSec_AccessCheckForSelf(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        unsigned int a2,
        void *a3,
        DWORD a4,
        int a5)
{
  CImpersonate *v9; // rax
  CImpersonate *v10; // rcx
  unsigned int v11; // ebx
  unsigned int AccessToken; // eax
  __int64 LastError; // r9
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  DWORD AccessStatusList; // [rsp+60h] [rbp-41h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-3Dh] BYREF
  HANDLE ClientToken; // [rsp+68h] [rbp-39h] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp-31h] BYREF
  CImpersonate *v21; // [rsp+78h] [rbp-29h] BYREF
  struct _OBJECT_TYPE_LIST ObjectTypeList; // [rsp+80h] [rbp-21h] BYREF
  CImpersonate *v23; // [rsp+90h] [rbp-11h]
  _DWORD v24[4]; // [rsp+98h] [rbp-9h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+A8h] [rbp+7h] BYREF

  if ( a2 == 52 )
  {
    v21 = 0;
    if ( a5 )
    {
      v9 = (CImpersonate *)MmAllocate(0x20u);
      v23 = v9;
      v10 = v9 ? CImpersonate::CImpersonate(v9, 1, 1) : 0LL;
      v21 = v10;
      if ( (*(unsigned int (__fastcall **)(CImpersonate *))(*(_QWORD *)v10 + 8LL))(v10) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 43, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids);
        v11 = -1072824284;
        goto LABEL_39;
      }
    }
    ClientToken = 0;
    AccessToken = GetAccessToken(&ClientToken, 0, (__int64)a3, 1);
    LastError = AccessToken;
    if ( AccessToken )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
        goto LABEL_38;
      v15 = 44;
    }
    else
    {
      PrivilegeSetLength = 32;
      GrantedAccess = 0;
      AccessStatusList = 1;
      v24[0] = -1710374076;
      v24[1] = 298959104;
      v24[2] = -2147433029;
      v24[3] = -1066375481;
      *(_QWORD *)&ObjectTypeList.Level = 0;
      ObjectTypeList.ObjectType = (GUID *)v24;
      GenericMapping = GetObjectGenericMapping(0x34u);
      if ( AccessCheckByTypeResultList(
             pSecurityDescriptor,
             a3,
             ClientToken,
             a4,
             &ObjectTypeList,
             1u,
             GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatusList) )
      {
        if ( !AccessStatusList && AreAllAccessesGranted(GrantedAccess, a4) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 46, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, a4);
          CHandle::~CHandle((CHandle *)&ClientToken);
          v11 = 0;
          goto LABEL_39;
        }
        if ( GetLastError() == 1314 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 47, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, a4);
          CHandle::~CHandle((CHandle *)&ClientToken);
          v11 = -1072824282;
          goto LABEL_39;
        }
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
          goto LABEL_38;
        v15 = 48;
        LastError = a4;
      }
      else
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) == 0 )
          goto LABEL_38;
        v15 = 45;
      }
    }
    WPP_SF_d(v14[32], v15, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, LastError);
LABEL_38:
    CHandle::~CHandle((CHandle *)&ClientToken);
    v11 = -1072824283;
LABEL_39:
    P<CImpersonate>::~P<CImpersonate>(&v21);
    return v11;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 42, &WPP_106f3f6591d133db7d775beace9e6f93_Traceguids, a2);
  return 3222143013LL;
}

```

## disassembly

```asm
0x18001fa40  push    rbp
0x18001fa42  push    rbx
0x18001fa43  push    rsi
0x18001fa44  push    rdi
0x18001fa45  push    r14
0x18001fa47  lea     rbp, [rsp-2Fh]
0x18001fa4c  sub     rsp, 0D0h
0x18001fa53  mov     rax, cs:__security_cookie
0x18001fa5a  xor     rax, rsp
0x18001fa5d  mov     [rbp+4Fh+var_28], rax
0x18001fa61  mov     edi, r9d
0x18001fa64  mov     r14, r8
0x18001fa67  mov     r9d, edx
0x18001fa6a  mov     rsi, rcx
0x18001fa6d  cmp     edx, 34h ; '4'
0x18001fa70  jz      short loc_18001FAB2
0x18001fa72  lea     rax, WPP_GLOBAL_Control
0x18001fa79  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fa80  cmp     rcx, rax
0x18001fa83  jz      short loc_18001FAA8
0x18001fa85  mov     ebx, 1
0x18001fa8a  test    [rcx+10Ch], bl
0x18001fa90  jz      short loc_18001FAA8
0x18001fa92  lea     edx, [rbx+29h]
0x18001fa95  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fa9c  mov     rcx, [rcx+100h]
0x18001faa3  call    WPP_SF_d
0x18001faa8  mov     eax, 0C00E0025h
0x18001faad  jmp     loc_18001FD4E
0x18001fab2  mov     [rbp+4Fh+var_78], 0
0x18001faba  mov     ebx, 1
0x18001fabf  cmp     [rbp+4Fh+arg_20], 0
0x18001fac3  jz      short loc_18001FB3B
0x18001fac5  lea     ecx, [rbx+1Fh]; unsigned __int64
0x18001fac8  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001facd  mov     [rbp+4Fh+var_60], rax
0x18001fad1  test    rax, rax
0x18001fad4  jz      short loc_18001FAE8
0x18001fad6  mov     r8d, ebx; int
0x18001fad9  mov     edx, ebx; int
0x18001fadb  mov     rcx, rax; this
0x18001fade  call    ??0CImpersonate@@QEAA@HH@Z; CImpersonate::CImpersonate(int,int)
0x18001fae3  mov     rcx, rax
0x18001fae6  jmp     short loc_18001FAEA
0x18001fae8  xor     ecx, ecx
0x18001faea  mov     [rbp+4Fh+var_78], rcx
0x18001faee  mov     rax, [rcx]
0x18001faf1  mov     rax, [rax+8]
0x18001faf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fafa  test    eax, eax
0x18001fafc  jz      short loc_18001FB3B
0x18001fafe  lea     rax, WPP_GLOBAL_Control
0x18001fb05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb0c  cmp     rcx, rax
0x18001fb0f  jz      short loc_18001FB31
0x18001fb11  test    [rcx+10Ch], bl
0x18001fb17  jz      short loc_18001FB31
0x18001fb19  mov     edx, 2Bh ; '+'
0x18001fb1e  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fb25  mov     rcx, [rcx+100h]
0x18001fb2c  call    WPP_SF_
0x18001fb31  mov     ebx, 0C00E0024h
0x18001fb36  jmp     loc_18001FD43
0x18001fb3b  mov     [rbp+4Fh+ClientToken], 0
0x18001fb43  mov     r9d, ebx; int
0x18001fb46  xor     edx, edx; int
0x18001fb48  lea     rcx, [rbp+4Fh+ClientToken]; TokenHandle
0x18001fb4c  call    ?GetAccessToken@@YAKPEAPEAXHKH@Z; GetAccessToken(void * *,int,ulong,int)
0x18001fb51  mov     r9d, eax
0x18001fb54  test    eax, eax
0x18001fb56  jz      short loc_18001FB85
0x18001fb58  lea     rax, WPP_GLOBAL_Control
0x18001fb5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb66  cmp     rcx, rax
0x18001fb69  jz      loc_18001FD35
0x18001fb6f  test    [rcx+10Ch], bl
0x18001fb75  jz      loc_18001FD35
0x18001fb7b  mov     edx, 2Ch ; ','
0x18001fb80  jmp     loc_18001FD21
0x18001fb85  mov     [rbp+4Fh+var_80], 20h ; ' '
0x18001fb8c  mov     [rbp+4Fh+GrantedAccess], 0
0x18001fb93  mov     [rbp+4Fh+var_90], ebx
0x18001fb96  mov     [rbp+4Fh+var_58], 9A0DC344h
0x18001fb9d  mov     [rbp+4Fh+var_54], 11D1C100h
0x18001fba4  mov     [rbp+4Fh+var_50], 8000C5BBh
0x18001fbab  mov     [rbp+4Fh+var_4C], 0C07066C7h
0x18001fbb2  xor     eax, eax
0x18001fbb4  mov     qword ptr [rbp+4Fh+var_70.Level], rax
0x18001fbb8  lea     rax, [rbp+4Fh+var_58]
0x18001fbbc  mov     [rbp+4Fh+var_70.ObjectType], rax
0x18001fbc0  mov     ecx, 34h ; '4'; unsigned int
0x18001fbc5  call    ?GetObjectGenericMapping@@YAPEAU_GENERIC_MAPPING@@K@Z; GetObjectGenericMapping(ulong)
0x18001fbca  lea     rdx, [rbp+4Fh+var_90]
0x18001fbce  mov     [rsp+0F0h+AccessStatusList], rdx; AccessStatusList
0x18001fbd3  lea     rdx, [rbp+4Fh+GrantedAccess]
0x18001fbd7  mov     [rsp+0F0h+GrantedAccessList], rdx; GrantedAccessList
0x18001fbdc  lea     rdx, [rbp+4Fh+var_80]
0x18001fbe0  mov     [rsp+0F0h+PrivilegeSetLength], rdx; PrivilegeSetLength
0x18001fbe5  lea     rdx, [rbp+4Fh+var_48]
0x18001fbe9  mov     [rsp+0F0h+PrivilegeSet], rdx; PrivilegeSet
0x18001fbee  mov     [rsp+0F0h+GenericMapping], rax; GenericMapping
0x18001fbf3  mov     [rsp+0F0h+ObjectTypeListLength], ebx; ObjectTypeListLength
0x18001fbf7  lea     rax, [rbp+4Fh+var_70]
0x18001fbfb  mov     [rsp+0F0h+ObjectTypeList], rax; ObjectTypeList
0x18001fc00  mov     r9d, edi; DesiredAccess
0x18001fc03  mov     r8, [rbp+4Fh+ClientToken]; ClientToken
0x18001fc07  mov     rdx, r14; PrincipalSelfSid
0x18001fc0a  mov     rcx, rsi; pSecurityDescriptor
0x18001fc0d  call    cs:__imp_AccessCheckByTypeResultList
0x18001fc13  test    eax, eax
0x18001fc15  jnz     short loc_18001FC4D
0x18001fc17  call    cs:__imp_GetLastError
0x18001fc1d  mov     r9d, eax
0x18001fc20  lea     rax, WPP_GLOBAL_Control
0x18001fc27  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc2e  cmp     rcx, rax
0x18001fc31  jz      loc_18001FD35
0x18001fc37  test    [rcx+10Ch], bl
0x18001fc3d  jz      loc_18001FD35
0x18001fc43  mov     edx, 2Dh ; '-'
0x18001fc48  jmp     loc_18001FD21
0x18001fc4d  cmp     [rbp+4Fh+var_90], 0
0x18001fc51  jnz     short loc_18001FCAA
0x18001fc53  mov     edx, edi; DesiredAccess
0x18001fc55  mov     ecx, [rbp+4Fh+GrantedAccess]; GrantedAccess
0x18001fc58  call    cs:__imp_AreAllAccessesGranted
0x18001fc5e  test    eax, eax
0x18001fc60  jz      short loc_18001FCAA
0x18001fc62  lea     rax, WPP_GLOBAL_Control
0x18001fc69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc70  cmp     rcx, rax
0x18001fc73  jz      short loc_18001FC9A
0x18001fc75  test    byte ptr [rcx+10Ch], 4
0x18001fc7c  jz      short loc_18001FC9A
0x18001fc7e  mov     edx, 2Eh ; '.'
0x18001fc83  mov     r9d, edi
0x18001fc86  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fc8d  mov     rcx, [rcx+100h]
0x18001fc94  call    WPP_SF_d
0x18001fc99  nop
0x18001fc9a  lea     rcx, [rbp+4Fh+ClientToken]; this
0x18001fc9e  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001fca3  xor     ebx, ebx
0x18001fca5  jmp     loc_18001FD43
0x18001fcaa  call    cs:__imp_GetLastError
0x18001fcb0  cmp     eax, 522h
0x18001fcb5  jnz     short loc_18001FCFE
0x18001fcb7  lea     rax, WPP_GLOBAL_Control
0x18001fcbe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcc5  cmp     rcx, rax
0x18001fcc8  jz      short loc_18001FCEE
0x18001fcca  test    [rcx+10Ch], bl
0x18001fcd0  jz      short loc_18001FCEE
0x18001fcd2  mov     edx, 2Fh ; '/'
0x18001fcd7  mov     r9d, edi
0x18001fcda  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fce1  mov     rcx, [rcx+100h]
0x18001fce8  call    WPP_SF_d
0x18001fced  nop
0x18001fcee  lea     rcx, [rbp+4Fh+ClientToken]; this
0x18001fcf2  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001fcf7  mov     ebx, 0C00E0026h
0x18001fcfc  jmp     short loc_18001FD43
0x18001fcfe  lea     rax, WPP_GLOBAL_Control
0x18001fd05  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd0c  cmp     rcx, rax
0x18001fd0f  jz      short loc_18001FD35
0x18001fd11  test    [rcx+10Ch], bl
0x18001fd17  jz      short loc_18001FD35
0x18001fd19  mov     edx, 30h ; '0'
0x18001fd1e  mov     r9d, edi
0x18001fd21  lea     r8, WPP_106f3f6591d133db7d775beace9e6f93_Traceguids
0x18001fd28  mov     rcx, [rcx+100h]
0x18001fd2f  call    WPP_SF_d
0x18001fd34  nop
0x18001fd35  lea     rcx, [rbp+4Fh+ClientToken]; this
0x18001fd39  call    ??1CHandle@@QEAA@XZ; CHandle::~CHandle(void)
0x18001fd3e  mov     ebx, 0C00E0025h
0x18001fd43  lea     rcx, [rbp+4Fh+var_78]
0x18001fd47  call    ??1?$P@VCImpersonate@@@@QEAA@XZ; P<CImpersonate>::~P<CImpersonate>(void)
0x18001fd4c  mov     eax, ebx
0x18001fd4e  mov     rcx, [rbp+4Fh+var_28]
0x18001fd52  xor     rcx, rsp; StackCookie
0x18001fd55  call    __security_check_cookie
0x18001fd5a  add     rsp, 0D0h
0x18001fd61  pop     r14
0x18001fd63  pop     rdi
0x18001fd64  pop     rsi
0x18001fd65  pop     rbx
0x18001fd66  pop     rbp
0x18001fd67  retn
```
