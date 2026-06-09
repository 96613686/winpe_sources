# DXGVAILOBJECT::AllocateResourceSecurityDescriptor(uchar,ulong,void * *)

- ea: `0x14026b4d0`
- end: `0x14026bb2a`
- name: `?AllocateResourceSecurityDescriptor@DXGVAILOBJECT@@QEAAJEKPEAPEAX@Z`
- size: `1626`
- prototype: `int(DXGVAILOBJECT *__hidden this, unsigned __int8, unsigned int, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14026c088`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x1400144ec`
- `0x1400150d0`
- `0x1400161c8`
- `0x1400a0100`
- `0x14026b4d0`
- `0x14026c9e0`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14026b838`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14026b838`
- `ntoskrnl!RtlLengthSid` at `0x14026b6de`
- `ntoskrnl!RtlLengthSid` at `0x14026b73b`
- `ntoskrnl!RtlLengthSid` at `0x14026b783`
- `ntoskrnl!RtlLengthSid` at `0x14026b7cd`
- `ntoskrnl!RtlLengthSid` at `0x14026b6de`
- `ntoskrnl!RtlLengthSid` at `0x14026b73b`
- `ntoskrnl!RtlLengthSid` at `0x14026b783`
- `ntoskrnl!RtlLengthSid` at `0x14026b7cd`
- `ntoskrnl!RtlCreateAcl` at `0x14026b94e`
- `ntoskrnl!RtlCreateAcl` at `0x14026b94e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14026ba39`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14026ba39`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14026ba78`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14026ba78`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14026b5fd`
- `ntoskrnl!PsGetProcessSessionIdEx` at `0x14026b5fd`
- `ntoskrnl!ObGetObjectSecurity` at `0x14026b533`
- `ntoskrnl!ObGetObjectSecurity` at `0x14026b533`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14026b58f`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14026b58f`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14026b69e`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x14026b69e`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14026b6fc`
- `ntoskrnl!RtlGetGroupSecurityDescriptor` at `0x14026b6fc`
- `ntoskrnl!RtlGetAce` at `0x14026b768`
- `ntoskrnl!RtlGetAce` at `0x14026b9a7`
- `ntoskrnl!RtlGetAce` at `0x14026b768`
- `ntoskrnl!RtlGetAce` at `0x14026b9a7`
- `ntoskrnl!RtlCopySid` at `0x14026b87c`
- `ntoskrnl!RtlCopySid` at `0x14026b8dd`
- `ntoskrnl!RtlCopySid` at `0x14026b87c`
- `ntoskrnl!RtlCopySid` at `0x14026b8dd`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14026b892`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14026b892`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14026b8f6`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14026b8f6`
- `ntoskrnl!RtlAddAce` at `0x14026b9d0`
- `ntoskrnl!RtlAddAce` at `0x14026b9d0`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14026baf4`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14026baf4`
- `watchdog!WdLogSingleEntry2` at `0x14026b811`
- `watchdog!WdLogSingleEntry2` at `0x14026b811`
- `watchdog!WdLogSingleEntry3` at `0x14026b667`
- `watchdog!WdLogSingleEntry3` at `0x14026b667`
- `watchdog!WdLogSingleEntry1` at `0x14026b554`
- `watchdog!WdLogSingleEntry1` at `0x14026b5aa`
- `watchdog!WdLogSingleEntry1` at `0x14026b62c`
- `watchdog!WdLogSingleEntry1` at `0x14026b6b8`
- `watchdog!WdLogSingleEntry1` at `0x14026b717`
- `watchdog!WdLogSingleEntry1` at `0x14026b7a2`
- `watchdog!WdLogSingleEntry1` at `0x14026b852`
- `watchdog!WdLogSingleEntry1` at `0x14026b8ad`
- `watchdog!WdLogSingleEntry1` at `0x14026b911`
- `watchdog!WdLogSingleEntry1` at `0x14026b969`
- `watchdog!WdLogSingleEntry1` at `0x14026b9f1`
- `watchdog!WdLogSingleEntry1` at `0x14026ba14`
- `watchdog!WdLogSingleEntry1` at `0x14026ba54`
- `watchdog!WdLogSingleEntry1` at `0x14026ba93`
- `watchdog!WdLogSingleEntry1` at `0x14026bace`
- `watchdog!WdLogSingleEntry1` at `0x14026b554`
- `watchdog!WdLogSingleEntry1` at `0x14026b5aa`
- `watchdog!WdLogSingleEntry1` at `0x14026b62c`
- `watchdog!WdLogSingleEntry1` at `0x14026b6b8`
- `watchdog!WdLogSingleEntry1` at `0x14026b717`
- `watchdog!WdLogSingleEntry1` at `0x14026b7a2`
- `watchdog!WdLogSingleEntry1` at `0x14026b852`
- `watchdog!WdLogSingleEntry1` at `0x14026b8ad`
- `watchdog!WdLogSingleEntry1` at `0x14026b911`
- `watchdog!WdLogSingleEntry1` at `0x14026b969`
- `watchdog!WdLogSingleEntry1` at `0x14026b9f1`
- `watchdog!WdLogSingleEntry1` at `0x14026ba14`
- `watchdog!WdLogSingleEntry1` at `0x14026ba54`
- `watchdog!WdLogSingleEntry1` at `0x14026ba93`
- `watchdog!WdLogSingleEntry1` at `0x14026bace`

## pseudocode

```c
__int64 __fastcall DXGVAILOBJECT::AllocateResourceSecurityDescriptor(
        DXGVAILOBJECT *this,
        char a2,
        ACCESS_MASK a3,
        void **a4)
{
  NTSTATUS ObjectSecurity; // eax
  NTSTATUS DaclSecurityDescriptor; // ebx
  unsigned int ProcessSessionId; // r15d
  unsigned int v10; // eax
  __int64 v11; // r14
  ULONG v12; // esi
  int v13; // r12d
  WORD i; // di
  ULONG v15; // r12d
  char *v16; // rax
  char *v17; // rdi
  struct _ACL *v18; // r14
  WORD v19; // si
  unsigned __int8 DaclPresent; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+31h] [rbp-38h] BYREF
  unsigned __int8 MemoryAllocated[6]; // [rsp+32h] [rbp-37h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+38h] [rbp-31h] BYREF
  PVOID Ace[2]; // [rsp+40h] [rbp-29h] BYREF
  PSID Owner; // [rsp+50h] [rbp-19h] BYREF
  PSID Group; // [rsp+58h] [rbp-11h] BYREF
  PACL Dacl; // [rsp+60h] [rbp-9h] BYREF
  void **v29; // [rsp+68h] [rbp-1h]
  _BYTE Sid[24]; // [rsp+70h] [rbp+7h] BYREF

  v29 = a4;
  SecurityDescriptor = 0;
  Dacl = 0;
  MemoryAllocated[0] = 0;
  Owner = 0;
  Group = 0;
  ObjectSecurity = ObGetObjectSecurity(this, &SecurityDescriptor, MemoryAllocated);
  if ( !SecurityDescriptor )
  {
    DaclSecurityDescriptor = -1073741786;
    WdLogSingleEntry1(3);
    WdLogGlobalForLineNumber = 374;
    goto LABEL_58;
  }
  if ( ObjectSecurity < 0 )
  {
    DaclSecurityDescriptor = ObjectSecurity;
  }
  else
  {
    DaclPresent = 0;
    DaclDefaulted = 0;
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(SecurityDescriptor, &DaclPresent, &Dacl, &DaclDefaulted);
    if ( DaclSecurityDescriptor < 0 )
    {
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 391;
      goto LABEL_58;
    }
    if ( !DaclPresent || DaclDefaulted )
    {
      DaclSecurityDescriptor = -1073741786;
      WdLogSingleEntry1(3);
      WdLogGlobalForLineNumber = 400;
    }
    else
    {
      DXGAUTOMUTEX::DXGAUTOMUTEX((DXGAUTOMUTEX *)Ace, (DXGVAILOBJECT *)((char *)this + 40), 1u);
      DXGAUTOMUTEX::Acquire((DXGAUTOMUTEX *)Ace);
      if ( *((_QWORD *)this + 12) )
      {
        DaclSecurityDescriptor = 0;
        ProcessSessionId = PsGetProcessSessionIdEx();
      }
      else
      {
        ProcessSessionId = -1;
        DaclSecurityDescriptor = -1073741275;
      }
      DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX((DXGPROCESSCOPYPROTECTIONMUTEX *)Ace);
      if ( DaclSecurityDescriptor < 0 )
      {
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 412;
        goto LABEL_58;
      }
      v10 = *((_DWORD *)this + 34);
      if ( v10 != ProcessSessionId )
      {
        DaclSecurityDescriptor = -1073741790;
        WdLogSingleEntry3(3, -1073741790, v10, ProcessSessionId);
        WdLogGlobalForLineNumber = 421;
        goto LABEL_58;
      }
      v11 = 0;
      if ( a2 )
      {
        DaclDefaulted = 0;
        DaclSecurityDescriptor = RtlGetOwnerSecurityDescriptor(SecurityDescriptor, &Owner, &DaclDefaulted);
        if ( DaclSecurityDescriptor < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 437;
          goto LABEL_58;
        }
        v12 = 0;
        if ( Owner )
          v12 = RtlLengthSid(Owner);
        DaclPresent = 0;
        DaclSecurityDescriptor = RtlGetGroupSecurityDescriptor(SecurityDescriptor, &Group, &DaclPresent);
        if ( DaclSecurityDescriptor < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 458;
          goto LABEL_58;
        }
        if ( Group )
          v11 = RtlLengthSid(Group);
      }
      else
      {
        v12 = 0;
      }
      v13 = 0;
      Ace[0] = 0;
      for ( i = 0; i < Dacl->AceCount; ++i )
      {
        DaclSecurityDescriptor = RtlGetAce(Dacl, i, Ace);
        if ( DaclSecurityDescriptor < 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 480;
          goto LABEL_58;
        }
        v13 += RtlLengthSid((char *)Ace[0] + 8) + 12;
      }
      DXGVAILOBJECT::InitializeDWMSid((DXGVAILOBJECT *)Dacl, ProcessSessionId, Sid);
      v15 = RtlLengthSid(Sid) + v13;
      v16 = (char *)operator new[](v12 + (_DWORD)v11 + v15 + 60, 1265072196, 256);
      v17 = v16;
      if ( v16 )
      {
        DaclSecurityDescriptor = RtlCreateSecurityDescriptor(v16, 1u);
        if ( DaclSecurityDescriptor >= 0 )
        {
          if ( Owner
            && (RtlCopySid(v12, v17 + 40, Owner),
                DaclSecurityDescriptor = RtlSetOwnerSecurityDescriptor(v17, v17 + 40, 0),
                DaclSecurityDescriptor < 0) )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 548;
          }
          else if ( Group
                 && (RtlCopySid(v11, &v17[v12 + 40], Group),
                     DaclSecurityDescriptor = RtlSetGroupSecurityDescriptor(v17, &v17[v12 + 40], 0),
                     DaclSecurityDescriptor < 0) )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 566;
          }
          else
          {
            v18 = (struct _ACL *)&v17[v11 + 40 + v12];
            DaclSecurityDescriptor = RtlCreateAcl(v18, v15 + 12, 4u);
            if ( DaclSecurityDescriptor >= 0 )
            {
              v19 = 0;
              Ace[0] = 0;
              while ( v19 < Dacl->AceCount )
              {
                DaclSecurityDescriptor = RtlGetAce(Dacl, v19, Ace);
                if ( DaclSecurityDescriptor < 0 )
                {
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 599;
                  goto LABEL_53;
                }
                DaclSecurityDescriptor = RtlAddAce(v18, 4u, 0, Ace[0], *((unsigned __int16 *)Ace[0] + 1));
                if ( DaclSecurityDescriptor < 0 )
                {
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 607;
                  goto LABEL_53;
                }
                ++v19;
              }
              DaclSecurityDescriptor = RtlAddAccessAllowedAce(v18, 4u, a3, Sid);
              if ( DaclSecurityDescriptor >= 0 )
              {
                DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(v17, 1u, v18, 0);
                if ( DaclSecurityDescriptor < 0 )
                {
                  WdLogSingleEntry1(3);
                  WdLogGlobalForLineNumber = 638;
                }
              }
              else
              {
                WdLogSingleEntry1(3);
                WdLogGlobalForLineNumber = 625;
              }
            }
            else
            {
              WdLogSingleEntry1(3);
              WdLogGlobalForLineNumber = 582;
            }
          }
        }
        else
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 530;
        }
LABEL_53:
        if ( DaclSecurityDescriptor < 0 )
          DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v17);
        else
          *v29 = v17;
      }
      else
      {
        DaclSecurityDescriptor = -1073741801;
        WdLogSingleEntry2(3, v12 + (_DWORD)v11 + v15 + 60);
        WdLogGlobalForLineNumber = 518;
      }
    }
  }
LABEL_58:
  if ( SecurityDescriptor )
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated[0]);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x14026b4d0  mov     [rsp-8+arg_8], rbx
0x14026b4d5  push    rbp
0x14026b4d6  push    rsi
0x14026b4d7  push    rdi
0x14026b4d8  push    r12
0x14026b4da  push    r13
0x14026b4dc  push    r14
0x14026b4de  push    r15
0x14026b4e0  lea     rbp, [rsp-27h]
0x14026b4e5  sub     rsp, 90h
0x14026b4ec  mov     rax, cs:__security_cookie
0x14026b4f3  xor     rax, rsp
0x14026b4f6  mov     [rbp+57h+var_38], rax
0x14026b4fa  mov     r13d, r8d
0x14026b4fd  mov     [rbp+57h+var_58], r9
0x14026b501  mov     sil, dl
0x14026b504  mov     [rbp+57h+SecurityDescriptor], 0
0x14026b50c  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14026b510  mov     [rbp+57h+Dacl], 0
0x14026b518  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14026b51c  mov     [rbp+57h+MemoryAllocated], 0
0x14026b520  mov     rdi, rcx
0x14026b523  mov     [rbp+57h+Owner], 0
0x14026b52b  mov     [rbp+57h+Group], 0
0x14026b533  call    cs:__imp_ObGetObjectSecurity
0x14026b53a  nop     dword ptr [rax+rax+00h]
0x14026b53f  cmp     [rbp+57h+SecurityDescriptor], 0
0x14026b544  jnz     short loc_14026B56F
0x14026b546  mov     rdx, 0FFFFFFFFC0000026h
0x14026b54d  mov     ebx, edx
0x14026b54f  mov     ecx, 3
0x14026b554  call    cs:__imp_WdLogSingleEntry1
0x14026b55b  nop     dword ptr [rax+rax+00h]
0x14026b560  mov     cs:WdLogGlobalForLineNumber, 176h
0x14026b56a  jmp     loc_14026BAE8
0x14026b56f  test    eax, eax
0x14026b571  js      loc_14026BAE6
0x14026b577  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14026b57b  lea     r9, [rbp+57h+DaclDefaulted]; DaclDefaulted
0x14026b57f  lea     r8, [rbp+57h+Dacl]; Dacl
0x14026b583  mov     [rbp+57h+DaclPresent], 0
0x14026b587  lea     rdx, [rbp+57h+DaclPresent]; DaclPresent
0x14026b58b  mov     [rbp+57h+DaclDefaulted], 0
0x14026b58f  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x14026b596  nop     dword ptr [rax+rax+00h]
0x14026b59b  movsxd  rbx, eax
0x14026b59e  test    eax, eax
0x14026b5a0  jns     short loc_14026B5C5
0x14026b5a2  mov     rdx, rbx
0x14026b5a5  mov     ecx, 3
0x14026b5aa  call    cs:__imp_WdLogSingleEntry1
0x14026b5b1  nop     dword ptr [rax+rax+00h]
0x14026b5b6  mov     cs:WdLogGlobalForLineNumber, 187h
0x14026b5c0  jmp     loc_14026BAE8
0x14026b5c5  cmp     [rbp+57h+DaclPresent], 0
0x14026b5c9  jz      loc_14026BAC0
0x14026b5cf  cmp     [rbp+57h+DaclDefaulted], 0
0x14026b5d3  jnz     loc_14026BAC0
0x14026b5d9  lea     rdx, [rdi+28h]; struct DXGFASTMUTEX *
0x14026b5dd  mov     r8b, 1; unsigned __int8
0x14026b5e0  lea     rcx, [rbp+57h+Ace]; this
0x14026b5e4  call    ??0DXGAUTOMUTEX@@QEAA@QEAVDXGFASTMUTEX@@E@Z; DXGAUTOMUTEX::DXGAUTOMUTEX(DXGFASTMUTEX * const,uchar)
0x14026b5e9  lea     rcx, [rbp+57h+Ace]; this
0x14026b5ed  call    ?Acquire@DXGAUTOMUTEX@@QEAAXXZ; DXGAUTOMUTEX::Acquire(void)
0x14026b5f2  mov     rcx, [rdi+60h]
0x14026b5f6  test    rcx, rcx
0x14026b5f9  jz      short loc_14026B60E
0x14026b5fb  xor     ebx, ebx
0x14026b5fd  call    cs:__imp_PsGetProcessSessionIdEx
0x14026b604  nop     dword ptr [rax+rax+00h]
0x14026b609  mov     r15d, eax
0x14026b60c  jmp     short loc_14026B617
0x14026b60e  or      r15d, 0FFFFFFFFh
0x14026b612  mov     ebx, 0C0000225h
0x14026b617  lea     rcx, [rbp+57h+Ace]; this
0x14026b61b  call    ??1DXGPROCESSCOPYPROTECTIONMUTEX@@QEAA@XZ; DXGPROCESSCOPYPROTECTIONMUTEX::~DXGPROCESSCOPYPROTECTIONMUTEX(void)
0x14026b620  test    ebx, ebx
0x14026b622  jns     short loc_14026B647
0x14026b624  movsxd  rdx, ebx
0x14026b627  mov     ecx, 3
0x14026b62c  call    cs:__imp_WdLogSingleEntry1
0x14026b633  nop     dword ptr [rax+rax+00h]
0x14026b638  mov     cs:WdLogGlobalForLineNumber, 19Ch
0x14026b642  jmp     loc_14026BAE8
0x14026b647  mov     eax, [rdi+88h]
0x14026b64d  cmp     eax, r15d
0x14026b650  jz      short loc_14026B682
0x14026b652  mov     rbx, 0FFFFFFFFC0000022h
0x14026b659  mov     r9d, r15d
0x14026b65c  mov     r8d, eax
0x14026b65f  mov     rdx, rbx
0x14026b662  mov     ecx, 3
0x14026b667  call    cs:__imp_WdLogSingleEntry3
0x14026b66e  nop     dword ptr [rax+rax+00h]
0x14026b673  mov     cs:WdLogGlobalForLineNumber, 1A5h
0x14026b67d  jmp     loc_14026BAE8
0x14026b682  xor     r14d, r14d
0x14026b685  test    sil, sil
0x14026b688  jz      loc_14026B74C
0x14026b68e  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14026b692  lea     r8, [rbp+57h+DaclDefaulted]; OwnerDefaulted
0x14026b696  lea     rdx, [rbp+57h+Owner]; Owner
0x14026b69a  mov     [rbp+57h+DaclDefaulted], r14b
0x14026b69e  call    cs:__imp_RtlGetOwnerSecurityDescriptor
0x14026b6a5  nop     dword ptr [rax+rax+00h]
0x14026b6aa  movsxd  rbx, eax
0x14026b6ad  test    eax, eax
0x14026b6af  jns     short loc_14026B6D3
0x14026b6b1  mov     rdx, rbx
0x14026b6b4  lea     ecx, [r14+3]
0x14026b6b8  call    cs:__imp_WdLogSingleEntry1
0x14026b6bf  nop     dword ptr [rax+rax+00h]
0x14026b6c4  mov     cs:WdLogGlobalForLineNumber, 1B5h
0x14026b6ce  jmp     loc_14026BAE8
0x14026b6d3  mov     rcx, [rbp+57h+Owner]; Sid
0x14026b6d7  xor     esi, esi
0x14026b6d9  test    rcx, rcx
0x14026b6dc  jz      short loc_14026B6EC
0x14026b6de  call    cs:__imp_RtlLengthSid
0x14026b6e5  nop     dword ptr [rax+rax+00h]
0x14026b6ea  mov     esi, eax
0x14026b6ec  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14026b6f0  lea     r8, [rbp+57h+DaclPresent]; GroupDefaulted
0x14026b6f4  lea     rdx, [rbp+57h+Group]; Group
0x14026b6f8  mov     [rbp+57h+DaclPresent], r14b
0x14026b6fc  call    cs:__imp_RtlGetGroupSecurityDescriptor
0x14026b703  nop     dword ptr [rax+rax+00h]
0x14026b708  movsxd  rbx, eax
0x14026b70b  test    eax, eax
0x14026b70d  jns     short loc_14026B732
0x14026b70f  mov     rdx, rbx
0x14026b712  mov     ecx, 3
0x14026b717  call    cs:__imp_WdLogSingleEntry1
0x14026b71e  nop     dword ptr [rax+rax+00h]
0x14026b723  mov     cs:WdLogGlobalForLineNumber, 1CAh
0x14026b72d  jmp     loc_14026BAE8
0x14026b732  mov     rcx, [rbp+57h+Group]; Sid
0x14026b736  test    rcx, rcx
0x14026b739  jz      short loc_14026B74E
0x14026b73b  call    cs:__imp_RtlLengthSid
0x14026b742  nop     dword ptr [rax+rax+00h]
0x14026b747  mov     r14d, eax
0x14026b74a  jmp     short loc_14026B74E
0x14026b74c  xor     esi, esi
0x14026b74e  xor     r12d, r12d
0x14026b751  mov     [rbp+57h+Ace], r12
0x14026b755  xor     edi, edi
0x14026b757  mov     rcx, [rbp+57h+Dacl]; this
0x14026b75b  cmp     di, [rcx+4]
0x14026b75f  jnb     short loc_14026B7BD
0x14026b761  movzx   edx, di; AceIndex
0x14026b764  lea     r8, [rbp+57h+Ace]; Ace
0x14026b768  call    cs:__imp_RtlGetAce
0x14026b76f  nop     dword ptr [rax+rax+00h]
0x14026b774  movsxd  rbx, eax
0x14026b777  test    eax, eax
0x14026b779  js      short loc_14026B79A
0x14026b77b  mov     rcx, [rbp+57h+Ace]
0x14026b77f  add     rcx, 8; Sid
0x14026b783  call    cs:__imp_RtlLengthSid
0x14026b78a  nop     dword ptr [rax+rax+00h]
0x14026b78f  add     eax, 0Ch
0x14026b792  add     r12d, eax
0x14026b795  inc     di
0x14026b798  jmp     short loc_14026B757
0x14026b79a  mov     rdx, rbx
0x14026b79d  mov     ecx, 3
0x14026b7a2  call    cs:__imp_WdLogSingleEntry1
0x14026b7a9  nop     dword ptr [rax+rax+00h]
0x14026b7ae  mov     cs:WdLogGlobalForLineNumber, 1E0h
0x14026b7b8  jmp     loc_14026BAE8
0x14026b7bd  lea     r8, [rbp+57h+Sid]; void *
0x14026b7c1  mov     edx, r15d; unsigned int
0x14026b7c4  call    ?InitializeDWMSid@DXGVAILOBJECT@@QEAAXKPEAX@Z; DXGVAILOBJECT::InitializeDWMSid(ulong,void *)
0x14026b7c9  lea     rcx, [rbp+57h+Sid]; Sid
0x14026b7cd  call    cs:__imp_RtlLengthSid
0x14026b7d4  nop     dword ptr [rax+rax+00h]
0x14026b7d9  mov     edx, 4B677844h
0x14026b7de  mov     r8d, 100h
0x14026b7e4  add     r12d, eax
0x14026b7e7  lea     ecx, [r12+3Ch]
0x14026b7ec  add     ecx, r14d
0x14026b7ef  add     ecx, esi
0x14026b7f1  mov     r15d, ecx
0x14026b7f4  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x14026b7f9  mov     rdi, rax
0x14026b7fc  test    rax, rax
0x14026b7ff  jnz     short loc_14026B82C
0x14026b801  mov     r8, 0FFFFFFFFC0000017h
0x14026b808  mov     ebx, r8d
0x14026b80b  mov     edx, r15d
0x14026b80e  lea     ecx, [rax+3]
0x14026b811  call    cs:__imp_WdLogSingleEntry2
0x14026b818  nop     dword ptr [rax+rax+00h]
0x14026b81d  mov     cs:WdLogGlobalForLineNumber, 206h
0x14026b827  jmp     loc_14026BAE8
0x14026b82c  mov     r15d, 1
0x14026b832  mov     rcx, rdi; SecurityDescriptor
0x14026b835  mov     edx, r15d; Revision
0x14026b838  call    cs:__imp_RtlCreateSecurityDescriptor
0x14026b83f  nop     dword ptr [rax+rax+00h]
0x14026b844  movsxd  rbx, eax
0x14026b847  test    eax, eax
0x14026b849  jns     short loc_14026B86D
0x14026b84b  mov     rdx, rbx
0x14026b84e  lea     ecx, [r15+2]
0x14026b852  call    cs:__imp_WdLogSingleEntry1
0x14026b859  nop     dword ptr [rax+rax+00h]
0x14026b85e  mov     cs:WdLogGlobalForLineNumber, 212h
0x14026b868  jmp     loc_14026BAA9
0x14026b86d  mov     r8, [rbp+57h+Owner]; SourceSid
0x14026b871  test    r8, r8
0x14026b874  jz      short loc_14026B8C8
0x14026b876  lea     rdx, [rdi+28h]; DestinationSid
0x14026b87a  mov     ecx, esi; DestinationSidLength
0x14026b87c  call    cs:__imp_RtlCopySid
0x14026b883  nop     dword ptr [rax+rax+00h]
0x14026b888  xor     r8d, r8d; OwnerDefaulted
0x14026b88b  lea     rdx, [rdi+28h]; Owner
0x14026b88f  mov     rcx, rdi; SecurityDescriptor
0x14026b892  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14026b899  nop     dword ptr [rax+rax+00h]
0x14026b89e  movsxd  rbx, eax
0x14026b8a1  test    eax, eax
0x14026b8a3  jns     short loc_14026B8C8
0x14026b8a5  mov     rdx, rbx
0x14026b8a8  mov     ecx, 3
0x14026b8ad  call    cs:__imp_WdLogSingleEntry1
0x14026b8b4  nop     dword ptr [rax+rax+00h]
0x14026b8b9  mov     cs:WdLogGlobalForLineNumber, 224h
0x14026b8c3  jmp     loc_14026BAA9
0x14026b8c8  mov     r8, [rbp+57h+Group]; SourceSid
0x14026b8cc  test    r8, r8
0x14026b8cf  jz      short loc_14026B92C
0x14026b8d1  mov     ebx, esi
0x14026b8d3  lea     rdx, [rdi+28h]
0x14026b8d7  add     rdx, rbx; DestinationSid
0x14026b8da  mov     ecx, r14d; DestinationSidLength
0x14026b8dd  call    cs:__imp_RtlCopySid
0x14026b8e4  nop     dword ptr [rax+rax+00h]
0x14026b8e9  lea     rdx, [rbx+28h]
0x14026b8ed  xor     r8d, r8d; GroupDefaulted
0x14026b8f0  add     rdx, rdi; Group
0x14026b8f3  mov     rcx, rdi; SecurityDescriptor
0x14026b8f6  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14026b8fd  nop     dword ptr [rax+rax+00h]
0x14026b902  movsxd  rbx, eax
0x14026b905  test    eax, eax
0x14026b907  jns     short loc_14026B934
0x14026b909  mov     rdx, rbx
0x14026b90c  mov     ecx, 3
0x14026b911  call    cs:__imp_WdLogSingleEntry1
0x14026b918  nop     dword ptr [rax+rax+00h]
0x14026b91d  mov     cs:WdLogGlobalForLineNumber, 236h
0x14026b927  jmp     loc_14026BAA9
0x14026b92c  test    ebx, ebx
0x14026b92e  js      loc_14026BAB6
0x14026b934  mov     ecx, esi
0x14026b936  lea     edx, [r12+0Ch]; AclLength
0x14026b93b  add     rcx, 28h ; '('
0x14026b93f  add     r14, rdi
0x14026b942  add     r14, rcx
0x14026b945  mov     r8d, 4; AclRevision
0x14026b94b  mov     rcx, r14; Acl
0x14026b94e  call    cs:__imp_RtlCreateAcl
0x14026b955  nop     dword ptr [rax+rax+00h]
0x14026b95a  movsxd  rbx, eax
0x14026b95d  test    eax, eax
0x14026b95f  jns     short loc_14026B984
0x14026b961  mov     rdx, rbx
0x14026b964  mov     ecx, 3
0x14026b969  call    cs:__imp_WdLogSingleEntry1
0x14026b970  nop     dword ptr [rax+rax+00h]
0x14026b975  mov     cs:WdLogGlobalForLineNumber, 246h
0x14026b97f  jmp     loc_14026BAA9
0x14026b984  xor     esi, esi
0x14026b986  mov     [rbp+57h+Ace], 0
0x14026b98e  lea     r12d, [rsi+4]
0x14026b992  mov     rcx, [rbp+57h+Dacl]; Acl
0x14026b996  cmp     si, [rcx+4]
0x14026b99a  jnb     loc_14026BA2C
0x14026b9a0  movzx   edx, si; AceIndex
0x14026b9a3  lea     r8, [rbp+57h+Ace]; Ace
0x14026b9a7  call    cs:__imp_RtlGetAce
0x14026b9ae  nop     dword ptr [rax+rax+00h]
0x14026b9b3  movsxd  rbx, eax
0x14026b9b6  test    eax, eax
0x14026b9b8  js      short loc_14026BA0C
0x14026b9ba  mov     r9, [rbp+57h+Ace]; AceList
0x14026b9be  xor     r8d, r8d; StartingAceIndex
0x14026b9c1  mov     edx, r12d; AceRevision
0x14026b9c4  mov     rcx, r14; Acl
0x14026b9c7  movzx   eax, word ptr [r9+2]
0x14026b9cc  mov     [rsp+0C0h+AceListLength], eax; AceListLength
0x14026b9d0  call    cs:__imp_RtlAddAce
0x14026b9d7  nop     dword ptr [rax+rax+00h]
0x14026b9dc  movsxd  rbx, eax
0x14026b9df  test    eax, eax
0x14026b9e1  js      short loc_14026B9E9
0x14026b9e3  add     si, r15w
  ... truncated ...
```
