# DXGVAILOBJECT::AllocateResourceSecurityDescriptor(uchar,ulong,void * *)

- ea: `0x140270a90`
- end: `0x1402710ea`
- name: `?AllocateResourceSecurityDescriptor@DXGVAILOBJECT@@QEAAJEKPEAPEAX@Z`
- size: `1626`
- prototype: `int(DXGVAILOBJECT *__hidden this, unsigned __int8, unsigned int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140271648`

## callees

- `0x1400091f0`
- `0x14000d990`
- `0x1400146ac`
- `0x140015290`
- `0x140016388`
- `0x1400a0bd0`
- `0x140270a90`
- `0x140271fa0`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140270df8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140270df8`
- `ntoskrnl!RtlLengthSid` at `0x140270c9e`
- `ntoskrnl!RtlLengthSid` at `0x140270cfb`
- `ntoskrnl!RtlLengthSid` at `0x140270d43`
- `ntoskrnl!RtlLengthSid` at `0x140270d8d`
- `ntoskrnl!RtlLengthSid` at `0x140270c9e`
- `ntoskrnl!RtlLengthSid` at `0x140270cfb`
- `ntoskrnl!RtlLengthSid` at `0x140270d43`
- `ntoskrnl!RtlLengthSid` at `0x140270d8d`
- `ntoskrnl!RtlCreateAcl` at `0x140270f0e`
- `ntoskrnl!RtlCreateAcl` at `0x140270f0e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140270ff9`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140270ff9`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140271038`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140271038`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140270bbd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x140270bbd`
- `ntoskrnl!ObGetObjectSecurity` at `0x140270af3`
- `ntoskrnl!ObGetObjectSecurity` at `0x140270af3`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140270b4f`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x140270b4f`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140270c5e`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140270c5e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140270cbc`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x140270cbc`
- `ntoskrnl!RtlGetAce` at `0x140270d28`
- `ntoskrnl!RtlGetAce` at `0x140270f67`
- `ntoskrnl!RtlGetAce` at `0x140270d28`
- `ntoskrnl!RtlGetAce` at `0x140270f67`
- `ntoskrnl!RtlCopySid` at `0x140270e3c`
- `ntoskrnl!RtlCopySid` at `0x140270e9d`
- `ntoskrnl!RtlCopySid` at `0x140270e3c`
- `ntoskrnl!RtlCopySid` at `0x140270e9d`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140270e52`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140270e52`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140270eb6`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140270eb6`
- `ntoskrnl!RtlAddAce` at `0x140270f90`
- `ntoskrnl!RtlAddAce` at `0x140270f90`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1402710b4`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1402710b4`
- `watchdog!WdLogSingleEntry2` at `0x140270dd1`
- `watchdog!WdLogSingleEntry2` at `0x140270dd1`
- `watchdog!WdLogSingleEntry3` at `0x140270c27`
- `watchdog!WdLogSingleEntry3` at `0x140270c27`
- `watchdog!WdLogSingleEntry1` at `0x140270b14`
- `watchdog!WdLogSingleEntry1` at `0x140270b6a`
- `watchdog!WdLogSingleEntry1` at `0x140270bec`
- `watchdog!WdLogSingleEntry1` at `0x140270c78`
- `watchdog!WdLogSingleEntry1` at `0x140270cd7`
- `watchdog!WdLogSingleEntry1` at `0x140270d62`
- `watchdog!WdLogSingleEntry1` at `0x140270e12`
- `watchdog!WdLogSingleEntry1` at `0x140270e6d`
- `watchdog!WdLogSingleEntry1` at `0x140270ed1`
- `watchdog!WdLogSingleEntry1` at `0x140270f29`
- `watchdog!WdLogSingleEntry1` at `0x140270fb1`
- `watchdog!WdLogSingleEntry1` at `0x140270fd4`
- `watchdog!WdLogSingleEntry1` at `0x140271014`
- `watchdog!WdLogSingleEntry1` at `0x140271053`
- `watchdog!WdLogSingleEntry1` at `0x14027108e`
- `watchdog!WdLogSingleEntry1` at `0x140270b14`
- `watchdog!WdLogSingleEntry1` at `0x140270b6a`
- `watchdog!WdLogSingleEntry1` at `0x140270bec`
- `watchdog!WdLogSingleEntry1` at `0x140270c78`
- `watchdog!WdLogSingleEntry1` at `0x140270cd7`
- `watchdog!WdLogSingleEntry1` at `0x140270d62`
- `watchdog!WdLogSingleEntry1` at `0x140270e12`
- `watchdog!WdLogSingleEntry1` at `0x140270e6d`
- `watchdog!WdLogSingleEntry1` at `0x140270ed1`
- `watchdog!WdLogSingleEntry1` at `0x140270f29`
- `watchdog!WdLogSingleEntry1` at `0x140270fb1`
- `watchdog!WdLogSingleEntry1` at `0x140270fd4`
- `watchdog!WdLogSingleEntry1` at `0x140271014`
- `watchdog!WdLogSingleEntry1` at `0x140271053`
- `watchdog!WdLogSingleEntry1` at `0x14027108e`

## pseudocode

```c
__int64 __fastcall DXGVAILOBJECT::AllocateResourceSecurityDescriptor(
        DXGVAILOBJECT *this,
        char a2,
        ACCESS_MASK a3,
        void **a4)
{
  NTSTATUS ObjectSecurity; // eax
  int v8; // ebx
  NTSTATUS DaclSecurityDescriptor; // eax
  __int64 v10; // rcx
  unsigned int ProcessSessionId; // r15d
  unsigned int v12; // eax
  __int64 v13; // r14
  NTSTATUS OwnerSecurityDescriptor; // eax
  ULONG v15; // esi
  NTSTATUS GroupSecurityDescriptor; // eax
  int v17; // r12d
  WORD i; // di
  NTSTATUS v19; // eax
  ULONG v20; // r12d
  char *v21; // rax
  char *v22; // rdi
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  NTSTATUS v25; // eax
  struct _ACL *v26; // r14
  NTSTATUS Acl; // eax
  WORD v28; // si
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+31h] [rbp-38h] BYREF
  unsigned __int8 MemoryAllocated[6]; // [rsp+32h] [rbp-37h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-31h] BYREF
  PVOID Ace[2]; // [rsp+40h] [rbp-29h] BYREF
  PSID Owner; // [rsp+50h] [rbp-19h] BYREF
  PSID Group; // [rsp+58h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+60h] [rbp-9h] BYREF
  void **v42; // [rsp+68h] [rbp-1h]
  _BYTE Sid[24]; // [rsp+70h] [rbp+7h] BYREF

  v42 = a4;
  SecurityDescriptor = 0;
  Dacl = 0;
  MemoryAllocated[0] = 0;
  Owner = 0;
  Group = 0;
  ObjectSecurity = ObGetObjectSecurity(this, &SecurityDescriptor, MemoryAllocated);
  if ( !SecurityDescriptor )
  {
    v8 = -1073741786;
    WdLogSingleEntry1(3, -1073741786);
    WdLogGlobalForLineNumber = 374;
    goto LABEL_59;
  }
  if ( ObjectSecurity < 0 )
  {
    v8 = ObjectSecurity;
  }
  else
  {
    DaclPresent = 0;
    DaclDefaulted = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
    v8 = DaclSecurityDescriptor;
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(3, DaclSecurityDescriptor);
      WdLogGlobalForLineNumber = 391;
      goto LABEL_59;
    }
    if ( DaclPresent && !DaclDefaulted )
    {
      DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)Ace, (DXGVAILOBJECT *)((char *)this + 40), 1u);
      DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)Ace);
      v10 = *((_QWORD *)this + 12);
      if ( v10 )
      {
        v8 = 0;
        ProcessSessionId = PsGetProcessSessionIdEx(v10);
      }
      else
      {
        ProcessSessionId = -1;
        v8 = -1073741275;
      }
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)Ace);
      if ( v8 < 0 )
      {
        WdLogSingleEntry1(3, v8);
        WdLogGlobalForLineNumber = 412;
        goto LABEL_59;
      }
      v12 = *((_DWORD *)this + 34);
      if ( v12 != ProcessSessionId )
      {
        v8 = -1073741790;
        WdLogSingleEntry3(3, -1073741790, v12, ProcessSessionId);
        WdLogGlobalForLineNumber = 421;
        goto LABEL_59;
      }
      v13 = 0;
      if ( a2 )
      {
        DaclDefaulted = 0;
        OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &DaclDefaulted);
        v8 = OwnerSecurityDescriptor;
        if ( OwnerSecurityDescriptor < 0 )
        {
          WdLogSingleEntry1(3, OwnerSecurityDescriptor);
          WdLogGlobalForLineNumber = 437;
          goto LABEL_59;
        }
        v15 = 0;
        if ( Owner )
          v15 = RtlLengthSid(Owner);
        DaclPresent = 0;
        GroupSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Group, &DaclPresent);
        v8 = GroupSecurityDescriptor;
        if ( GroupSecurityDescriptor < 0 )
        {
          WdLogSingleEntry1(3, GroupSecurityDescriptor);
          WdLogGlobalForLineNumber = 458;
          goto LABEL_59;
        }
        if ( Group )
          v13 = RtlLengthSid(Group);
      }
      else
      {
        v15 = 0;
      }
      v17 = 0;
      Ace[0] = 0;
      for ( i = 0; i < Dacl->AceCount; ++i )
      {
        v19 = RtlGetAce(Dacl, i, Ace);
        v8 = v19;
        if ( v19 < 0 )
        {
          WdLogSingleEntry1(3, v19);
          WdLogGlobalForLineNumber = 480;
          goto LABEL_59;
        }
        v17 += RtlLengthSid((char *)Ace[0] + 8) + 12;
      }
      DXGVAILOBJECT::InitializeDWMSid((DXGVAILOBJECT *)Dacl, ProcessSessionId, Sid);
      v20 = RtlLengthSid(Sid) + v17;
      v21 = (char *)operator new[](v15 + (_DWORD)v13 + v20 + 60, 1265072196, 256);
      v22 = v21;
      if ( !v21 )
      {
        v8 = -1073741801;
        WdLogSingleEntry2(3, v15 + (_DWORD)v13 + v20 + 60, -1073741801);
        WdLogGlobalForLineNumber = 518;
        goto LABEL_59;
      }
      v23 = RtlCreateSecurityDescriptor(v21, 1u);
      v8 = v23;
      if ( v23 < 0 )
      {
        WdLogSingleEntry1(3, v23);
        WdLogGlobalForLineNumber = 530;
        goto LABEL_54;
      }
      if ( Owner )
      {
        RtlCopySid(v15, v22 + 40, Owner);
        v24 = RtlSetOwnerSecurityDescriptor(v22, v22 + 40, 0);
        v8 = v24;
        if ( v24 < 0 )
        {
          WdLogSingleEntry1(3, v24);
          WdLogGlobalForLineNumber = 548;
          goto LABEL_54;
        }
      }
      if ( Group )
      {
        RtlCopySid(v13, &v22[v15 + 40], Group);
        v25 = RtlSetGroupSecurityDescriptor(v22, &v22[v15 + 40], 0);
        v8 = v25;
        if ( v25 < 0 )
        {
          WdLogSingleEntry1(3, v25);
          WdLogGlobalForLineNumber = 566;
          goto LABEL_54;
        }
      }
      else if ( v8 < 0 )
      {
LABEL_56:
        DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v22);
        goto LABEL_59;
      }
      v26 = (struct _ACL *)&v22[v13 + 40 + v15];
      Acl = RtlCreateAcl(v26, v20 + 12, 4u);
      v8 = Acl;
      if ( Acl >= 0 )
      {
        v28 = 0;
        Ace[0] = 0;
        while ( v28 < Dacl->AceCount )
        {
          v29 = RtlGetAce(Dacl, v28, Ace);
          v8 = v29;
          if ( v29 < 0 )
          {
            WdLogSingleEntry1(3, v29);
            WdLogGlobalForLineNumber = 599;
            goto LABEL_54;
          }
          v30 = RtlAddAce(v26, 4u, 0, Ace[0], *((unsigned __int16 *)Ace[0] + 1));
          v8 = v30;
          if ( v30 < 0 )
          {
            WdLogSingleEntry1(3, v30);
            WdLogGlobalForLineNumber = 607;
            goto LABEL_54;
          }
          ++v28;
        }
        v31 = RtlAddAccessAllowedAce(v26, 4u, a3, Sid);
        v8 = v31;
        if ( v31 >= 0 )
        {
          v32 = RtlSetDaclSecurityDescriptor(v22, 1u, v26, 0);
          v8 = v32;
          if ( v32 < 0 )
          {
            WdLogSingleEntry1(3, v32);
            WdLogGlobalForLineNumber = 638;
          }
        }
        else
        {
          WdLogSingleEntry1(3, v31);
          WdLogGlobalForLineNumber = 625;
        }
      }
      else
      {
        WdLogSingleEntry1(3, Acl);
        WdLogGlobalForLineNumber = 582;
      }
LABEL_54:
      if ( v8 >= 0 )
      {
        *v42 = v22;
        goto LABEL_59;
      }
      goto LABEL_56;
    }
    v8 = -1073741786;
    WdLogSingleEntry1(3, -1073741786);
    WdLogGlobalForLineNumber = 400;
  }
LABEL_59:
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140270a90  mov     [rsp-8+arg_8], rbx
0x140270a95  push    rbp
0x140270a96  push    rsi
0x140270a97  push    rdi
0x140270a98  push    r12
0x140270a9a  push    r13
0x140270a9c  push    r14
0x140270a9e  push    r15
0x140270aa0  lea     rbp, [rsp-27h]
0x140270aa5  sub     rsp, 90h
0x140270aac  mov     rax, cs:__security_cookie
0x140270ab3  xor     rax, rsp
0x140270ab6  mov     [rbp+57h+var_38], rax
0x140270aba  mov     r13d, r8d
0x140270abd  mov     [rbp+57h+var_58], r9
0x140270ac1  mov     sil, dl
0x140270ac4  mov     [rbp+57h+SecurityDescriptor], 0
0x140270acc  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140270ad0  mov     [rbp+57h+Dacl], 0
0x140270ad8  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140270adc  mov     [rbp+57h+MemoryAllocated], 0
0x140270ae0  mov     rdi, rcx
0x140270ae3  mov     [rbp+57h+Owner], 0
0x140270aeb  mov     [rbp+57h+Group], 0
0x140270af3  call    cs:__imp_ObGetObjectSecurity
0x140270afa  nop     dword ptr [rax+rax+00h]
0x140270aff  cmp     [rbp+57h+SecurityDescriptor], 0
0x140270b04  jnz     short loc_140270B2F
0x140270b06  mov     rdx, 0FFFFFFFFC0000026h
0x140270b0d  mov     ebx, edx
0x140270b0f  mov     ecx, 3
0x140270b14  call    cs:__imp_WdLogSingleEntry1
0x140270b1b  nop     dword ptr [rax+rax+00h]
0x140270b20  mov     cs:WdLogGlobalForLineNumber, 176h
0x140270b2a  jmp     loc_1402710A8
0x140270b2f  test    eax, eax
0x140270b31  js      loc_1402710A6
0x140270b37  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140270b3b  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x140270b3f  lea     r8, [rbp+57h+Dacl]; Dacl
0x140270b43  mov     [rbp+57h+DaclPresent], 0
0x140270b47  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x140270b4b  mov     [rbp+57h+DaclDefaulted], 0
0x140270b4f  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x140270b56  nop     dword ptr [rax+rax+00h]
0x140270b5b  movsxd  rbx, eax
0x140270b5e  test    eax, eax
0x140270b60  jns     short loc_140270B85
0x140270b62  mov     rdx, rbx
0x140270b65  mov     ecx, 3
0x140270b6a  call    cs:__imp_WdLogSingleEntry1
0x140270b71  nop     dword ptr [rax+rax+00h]
0x140270b76  mov     cs:WdLogGlobalForLineNumber, 187h
0x140270b80  jmp     loc_1402710A8
0x140270b85  cmp     [rbp+57h+DaclPresent], 0
0x140270b89  jz      loc_140271080
0x140270b8f  cmp     [rbp+57h+DaclDefaulted], 0
0x140270b93  jnz     loc_140271080
0x140270b99  lea     rdx, [rdi+28h]; struct DXGFASTMUTEX *
0x140270b9d  mov     r8b, 1; unsigned __int8
0x140270ba0  lea     rcx, [rbp+57h+Ace]; this
0x140270ba4  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x140270ba9  lea     rcx, [rbp+57h+Ace]; this
0x140270bad  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x140270bb2  mov     rcx, [rdi+60h]
0x140270bb6  test    rcx, rcx
0x140270bb9  jz      short loc_140270BCE
0x140270bbb  xor     ebx, ebx
0x140270bbd  call    cs:__imp_PsGetProcessSessionIdEx
0x140270bc4  nop     dword ptr [rax+rax+00h]
0x140270bc9  mov     r15d, eax
0x140270bcc  jmp     short loc_140270BD7
0x140270bce  or      r15d, 0FFFFFFFFh
0x140270bd2  mov     ebx, 0C0000225h
0x140270bd7  lea     rcx, [rbp+57h+Ace]; this
0x140270bdb  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x140270be0  test    ebx, ebx
0x140270be2  jns     short loc_140270C07
0x140270be4  movsxd  rdx, ebx
0x140270be7  mov     ecx, 3
0x140270bec  call    cs:__imp_WdLogSingleEntry1
0x140270bf3  nop     dword ptr [rax+rax+00h]
0x140270bf8  mov     cs:WdLogGlobalForLineNumber, 19Ch
0x140270c02  jmp     loc_1402710A8
0x140270c07  mov     eax, [rdi+88h]
0x140270c0d  cmp     eax, r15d
0x140270c10  jz      short loc_140270C42
0x140270c12  mov     rbx, 0FFFFFFFFC0000022h
0x140270c19  mov     r9d, r15d
0x140270c1c  mov     r8d, eax
0x140270c1f  mov     rdx, rbx
0x140270c22  mov     ecx, 3
0x140270c27  call    cs:__imp_WdLogSingleEntry3
0x140270c2e  nop     dword ptr [rax+rax+00h]
0x140270c33  mov     cs:WdLogGlobalForLineNumber, 1A5h
0x140270c3d  jmp     loc_1402710A8
0x140270c42  xor     r14d, r14d
0x140270c45  test    sil, sil
0x140270c48  jz      loc_140270D0C
0x140270c4e  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140270c52  lea     r8, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x140270c56  lea     rdx, [rbp+57h+Owner]; Owner
0x140270c5a  mov     [rbp+57h+DaclDefaulted], r14b
0x140270c5e  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x140270c65  nop     dword ptr [rax+rax+00h]
0x140270c6a  movsxd  rbx, eax
0x140270c6d  test    eax, eax
0x140270c6f  jns     short loc_140270C93
0x140270c71  mov     rdx, rbx
0x140270c74  lea     ecx, [r14+3]
0x140270c78  call    cs:__imp_WdLogSingleEntry1
0x140270c7f  nop     dword ptr [rax+rax+00h]
0x140270c84  mov     cs:WdLogGlobalForLineNumber, 1B5h
0x140270c8e  jmp     loc_1402710A8
0x140270c93  mov     rcx, [rbp+57h+Owner]; Sid
0x140270c97  xor     esi, esi
0x140270c99  test    rcx, rcx
0x140270c9c  jz      short loc_140270CAC
0x140270c9e  call    cs:__imp_RtlLengthSid
0x140270ca5  nop     dword ptr [rax+rax+00h]
0x140270caa  mov     esi, eax
0x140270cac  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140270cb0  lea     r8, [rbp+57h+DaclPresent]; GroupDefaulted
0x140270cb4  lea     rdx, [rbp+57h+Group]; Group
0x140270cb8  mov     [rbp+57h+DaclPresent], r14b
0x140270cbc  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x140270cc3  nop     dword ptr [rax+rax+00h]
0x140270cc8  movsxd  rbx, eax
0x140270ccb  test    eax, eax
0x140270ccd  jns     short loc_140270CF2
0x140270ccf  mov     rdx, rbx
0x140270cd2  mov     ecx, 3
0x140270cd7  call    cs:__imp_WdLogSingleEntry1
0x140270cde  nop     dword ptr [rax+rax+00h]
0x140270ce3  mov     cs:WdLogGlobalForLineNumber, 1CAh
0x140270ced  jmp     loc_1402710A8
0x140270cf2  mov     rcx, [rbp+57h+Group]; Sid
0x140270cf6  test    rcx, rcx
0x140270cf9  jz      short loc_140270D0E
0x140270cfb  call    cs:__imp_RtlLengthSid
0x140270d02  nop     dword ptr [rax+rax+00h]
0x140270d07  mov     r14d, eax
0x140270d0a  jmp     short loc_140270D0E
0x140270d0c  xor     esi, esi
0x140270d0e  xor     r12d, r12d
0x140270d11  mov     [rbp+57h+Ace], r12
0x140270d15  xor     edi, edi
0x140270d17  mov     rcx, [rbp+57h+Dacl]; this
0x140270d1b  cmp     di, [rcx+4]
0x140270d1f  jnb     short loc_140270D7D
0x140270d21  movzx   edx, di; AceIndex
0x140270d24  lea     r8, [rbp+57h+Ace]; Ace
0x140270d28  call    cs:__imp_RtlGetAce
0x140270d2f  nop     dword ptr [rax+rax+00h]
0x140270d34  movsxd  rbx, eax
0x140270d37  test    eax, eax
0x140270d39  js      short loc_140270D5A
0x140270d3b  mov     rcx, [rbp+57h+Ace]
0x140270d3f  add     rcx, 8; Sid
0x140270d43  call    cs:__imp_RtlLengthSid
0x140270d4a  nop     dword ptr [rax+rax+00h]
0x140270d4f  add     eax, 0Ch
0x140270d52  add     r12d, eax
0x140270d55  inc     di
0x140270d58  jmp     short loc_140270D17
0x140270d5a  mov     rdx, rbx
0x140270d5d  mov     ecx, 3
0x140270d62  call    cs:__imp_WdLogSingleEntry1
0x140270d69  nop     dword ptr [rax+rax+00h]
0x140270d6e  mov     cs:WdLogGlobalForLineNumber, 1E0h
0x140270d78  jmp     loc_1402710A8
0x140270d7d  lea     r8, [rbp+57h+Sid]; void *
0x140270d81  mov     edx, r15d; unsigned int
0x140270d84  call    ?InitializeDWMSid@DXGVAILOBJECT@@QEAAXKPEAX@Z; DXGVAILOBJECT::InitializeDWMSid(ulong,void *)
0x140270d89  lea     rcx, [rbp+57h+Sid]; Sid
0x140270d8d  call    cs:__imp_RtlLengthSid
0x140270d94  nop     dword ptr [rax+rax+00h]
0x140270d99  mov     edx, 4B677844h
0x140270d9e  mov     r8d, 100h
0x140270da4  add     r12d, eax
0x140270da7  lea     ecx, [r12+3Ch]
0x140270dac  add     ecx, r14d
0x140270daf  add     ecx, esi
0x140270db1  mov     r15d, ecx
0x140270db4  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140270db9  mov     rdi, rax
0x140270dbc  test    rax, rax
0x140270dbf  jnz     short loc_140270DEC
0x140270dc1  mov     r8, 0FFFFFFFFC0000017h
0x140270dc8  mov     ebx, r8d
0x140270dcb  mov     edx, r15d
0x140270dce  lea     ecx, [rax+3]
0x140270dd1  call    cs:__imp_WdLogSingleEntry2
0x140270dd8  nop     dword ptr [rax+rax+00h]
0x140270ddd  mov     cs:WdLogGlobalForLineNumber, 206h
0x140270de7  jmp     loc_1402710A8
0x140270dec  mov     r15d, 1
0x140270df2  mov     rcx, rdi; SecurityDescriptor
0x140270df5  mov     edx, r15d; Revision
0x140270df8  call    cs:__imp_RtlCreateSecurityDescriptor
0x140270dff  nop     dword ptr [rax+rax+00h]
0x140270e04  movsxd  rbx, eax
0x140270e07  test    eax, eax
0x140270e09  jns     short loc_140270E2D
0x140270e0b  mov     rdx, rbx
0x140270e0e  lea     ecx, [r15+2]
0x140270e12  call    cs:__imp_WdLogSingleEntry1
0x140270e19  nop     dword ptr [rax+rax+00h]
0x140270e1e  mov     cs:WdLogGlobalForLineNumber, 212h
0x140270e28  jmp     loc_140271069
0x140270e2d  mov     r8, [rbp+57h+Owner]; SourceSid
0x140270e31  test    r8, r8
0x140270e34  jz      short loc_140270E88
0x140270e36  lea     rdx, [rdi+28h]; DestinationSid
0x140270e3a  mov     ecx, esi; DestinationSidLength
0x140270e3c  call    cs:__imp_RtlCopySid
0x140270e43  nop     dword ptr [rax+rax+00h]
0x140270e48  xor     r8d, r8d; OwnerDefaulted
0x140270e4b  lea     rdx, [rdi+28h]; Owner
0x140270e4f  mov     rcx, rdi; SecurityDescriptor
0x140270e52  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140270e59  nop     dword ptr [rax+rax+00h]
0x140270e5e  movsxd  rbx, eax
0x140270e61  test    eax, eax
0x140270e63  jns     short loc_140270E88
0x140270e65  mov     rdx, rbx
0x140270e68  mov     ecx, 3
0x140270e6d  call    cs:__imp_WdLogSingleEntry1
0x140270e74  nop     dword ptr [rax+rax+00h]
0x140270e79  mov     cs:WdLogGlobalForLineNumber, 224h
0x140270e83  jmp     loc_140271069
0x140270e88  mov     r8, [rbp+57h+Group]; SourceSid
0x140270e8c  test    r8, r8
0x140270e8f  jz      short loc_140270EEC
0x140270e91  mov     ebx, esi
0x140270e93  lea     rdx, [rdi+28h]
0x140270e97  add     rdx, rbx; DestinationSid
0x140270e9a  mov     ecx, r14d; DestinationSidLength
0x140270e9d  call    cs:__imp_RtlCopySid
0x140270ea4  nop     dword ptr [rax+rax+00h]
0x140270ea9  lea     rdx, [rbx+28h]
0x140270ead  xor     r8d, r8d; GroupDefaulted
0x140270eb0  add     rdx, rdi; Group
0x140270eb3  mov     rcx, rdi; SecurityDescriptor
0x140270eb6  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140270ebd  nop     dword ptr [rax+rax+00h]
0x140270ec2  movsxd  rbx, eax
0x140270ec5  test    eax, eax
0x140270ec7  jns     short loc_140270EF4
0x140270ec9  mov     rdx, rbx
0x140270ecc  mov     ecx, 3
0x140270ed1  call    cs:__imp_WdLogSingleEntry1
0x140270ed8  nop     dword ptr [rax+rax+00h]
0x140270edd  mov     cs:WdLogGlobalForLineNumber, 236h
0x140270ee7  jmp     loc_140271069
0x140270eec  test    ebx, ebx
0x140270eee  js      loc_140271076
0x140270ef4  mov     ecx, esi
0x140270ef6  lea     edx, [r12+0Ch]; AclLength
0x140270efb  add     rcx, 28h ; '('
0x140270eff  add     r14, rdi
0x140270f02  add     r14, rcx
0x140270f05  mov     r8d, 4; AclRevision
0x140270f0b  mov     rcx, r14; Acl
0x140270f0e  call    cs:__imp_RtlCreateAcl
0x140270f15  nop     dword ptr [rax+rax+00h]
0x140270f1a  movsxd  rbx, eax
0x140270f1d  test    eax, eax
0x140270f1f  jns     short loc_140270F44
0x140270f21  mov     rdx, rbx
0x140270f24  mov     ecx, 3
0x140270f29  call    cs:__imp_WdLogSingleEntry1
0x140270f30  nop     dword ptr [rax+rax+00h]
0x140270f35  mov     cs:WdLogGlobalForLineNumber, 246h
0x140270f3f  jmp     loc_140271069
0x140270f44  xor     esi, esi
0x140270f46  mov     [rbp+57h+Ace], 0
0x140270f4e  lea     r12d, [rsi+4]
0x140270f52  mov     rcx, [rbp+57h+Dacl]; Acl
0x140270f56  cmp     si, [rcx+4]
0x140270f5a  jnb     loc_140270FEC
0x140270f60  movzx   edx, si; AceIndex
0x140270f63  lea     r8, [rbp+57h+Ace]; Ace
0x140270f67  call    cs:__imp_RtlGetAce
0x140270f6e  nop     dword ptr [rax+rax+00h]
0x140270f73  movsxd  rbx, eax
0x140270f76  test    eax, eax
0x140270f78  js      short loc_140270FCC
0x140270f7a  mov     r9, [rbp+57h+Ace]; AceList
0x140270f7e  xor     r8d, r8d; StartingAceIndex
0x140270f81  mov     edx, r12d; AceRevision
0x140270f84  mov     rcx, r14; Acl
0x140270f87  movzx   eax, word ptr [r9+2]
0x140270f8c  mov     [rsp+0C0h+AceListLength], eax; AceListLength
0x140270f90  call    cs:__imp_RtlAddAce
0x140270f97  nop     dword ptr [rax+rax+00h]
0x140270f9c  movsxd  rbx, eax
0x140270f9f  test    eax, eax
0x140270fa1  js      short loc_140270FA9
0x140270fa3  add     si, r15w
  ... truncated ...
```
