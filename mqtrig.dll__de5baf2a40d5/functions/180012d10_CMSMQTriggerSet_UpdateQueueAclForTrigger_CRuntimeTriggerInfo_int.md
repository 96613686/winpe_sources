# CMSMQTriggerSet::UpdateQueueAclForTrigger(CRuntimeTriggerInfo *,int)

- ea: `0x180012d10`
- end: `0x180012f3a`
- name: `?UpdateQueueAclForTrigger@CMSMQTriggerSet@@AEAAJPEAVCRuntimeTriggerInfo@@H@Z`
- size: `554`
- prototype: `__int64 __fastcall(CMSMQTriggerSet *__hidden this, struct CRuntimeTriggerInfo *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180010590`
- `0x180010ea0`
- `0x180012f40`

## callees

- `0x18001108c`
- `0x1800119a8`
- `0x180011a94`
- `0x1800124f0`
- `0x180012d10`

## import_xrefs

- `msvcrt!free` at `0x180012eee`
- `msvcrt!free` at `0x180012efd`
- `msvcrt!free` at `0x180012eee`
- `msvcrt!free` at `0x180012efd`
- `KERNEL32!LocalFree` at `0x180012f0c`
- `KERNEL32!LocalFree` at `0x180012f20`
- `KERNEL32!LocalFree` at `0x180012f0c`
- `KERNEL32!LocalFree` at `0x180012f20`
- `KERNEL32!GetLastError` at `0x180012dd2`
- `KERNEL32!GetLastError` at `0x180012ea3`
- `KERNEL32!GetLastError` at `0x180012dd2`
- `KERNEL32!GetLastError` at `0x180012ea3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012ec4`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180012ec4`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012e99`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180012e99`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180012dc8`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180012dc8`
- `ADVAPI32!SetEntriesInAclW` at `0x180012e78`
- `ADVAPI32!SetEntriesInAclW` at `0x180012e78`
- `mqrt!MQSetQueueSecurity` at `0x180012edb`
- `mqrt!MQSetQueueSecurity` at `0x180012edb`

## pseudocode

```c
__int64 __fastcall CMSMQTriggerSet::UpdateQueueAclForTrigger(
        CMSMQTriggerSet *this,
        struct CRuntimeTriggerInfo *a2,
        int a3)
{
  PSECURITY_DESCRIPTOR v6; // rsi
  WCHAR *v7; // rdi
  const wchar_t **v8; // rax
  const wchar_t *v9; // rdx
  CMSMQTriggerSet *v10; // rcx
  int QueueFormatName; // ebx
  __int64 v12; // r8
  CMSMQTriggerSet *v13; // rcx
  signed int v14; // eax
  CMSMQTriggerSet *v15; // rcx
  signed int v16; // eax
  signed int LastError; // eax
  PACL NewAcl; // [rsp+20h] [rbp-59h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-51h] BYREF
  void *v20; // [rsp+30h] [rbp-49h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+38h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+40h] [rbp-39h] BYREF
  _OWORD v23[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v24; // [rsp+90h] [rbp+17h]
  CMSMQTriggerSet *bDaclPresent; // [rsp+E0h] [rbp+67h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+E8h] [rbp+6Fh] BYREF
  LPCWSTR lpwcsFormatName; // [rsp+F8h] [rbp+7Fh] BYREF

  bDaclPresent = this;
  if ( *((_DWORD *)a2 + 526) )
    return 0;
  lpwcsFormatName = 0;
  v6 = 0;
  pSecurityDescriptor = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  NewAcl = 0;
  v7 = 0;
  v20 = 0;
  pDacl = 0;
  LODWORD(bDaclPresent) = 0;
  bDaclDefaulted = 0;
  v8 = (const wchar_t **)*((_QWORD *)a2 + 262);
  if ( v8 )
    v9 = *v8;
  else
    v9 = 0;
  QueueFormatName = CMSMQTriggerSet::GetQueueFormatName(this, v9, (wchar_t **)&lpwcsFormatName);
  if ( QueueFormatName >= 0 )
  {
    QueueFormatName = CMSMQTriggerSet::GetQueueSecurityDescriptor(v10, lpwcsFormatName, v12, &pSecurityDescriptor);
    v6 = pSecurityDescriptor;
    if ( QueueFormatName >= 0 )
    {
      if ( GetSecurityDescriptorDacl(pSecurityDescriptor, (LPBOOL)&bDaclPresent, &pDacl, &bDaclDefaulted) )
      {
        if ( (_DWORD)bDaclPresent )
        {
          QueueFormatName = CMSMQTriggerSet::GetTriggerServiceSid(v13, &v20);
          v7 = (WCHAR *)v20;
          if ( QueueFormatName >= 0 )
          {
            CMSMQTriggerSet::DeleteTriggerServiceFromDacl(v15, pDacl, v20);
            NewAcl = pDacl;
            if ( a3 )
              goto LABEL_35;
            memset(&pListOfExplicitEntries.grfInheritance, 0, 24);
            *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 1;
            pListOfExplicitEntries.grfAccessPermissions = (*((_DWORD *)a2 + 5) != 0) + 2;
            pListOfExplicitEntries.grfAccessMode = GRANT_ACCESS;
            pListOfExplicitEntries.Trustee.ptstrName = v7;
            v16 = SetEntriesInAclW(1u, &pListOfExplicitEntries, pDacl, &NewAcl);
            QueueFormatName = v16;
            if ( v16 > 0 )
              QueueFormatName = (unsigned __int16)v16 | 0x80070000;
            if ( QueueFormatName >= 0 )
            {
LABEL_35:
              if ( InitializeSecurityDescriptor(v23, 1u) && SetSecurityDescriptorDacl(v23, 1, NewAcl, 0) )
              {
                QueueFormatName = MQSetQueueSecurity(lpwcsFormatName, 4u, v23);
              }
              else
              {
                LastError = GetLastError();
                QueueFormatName = LastError;
                if ( LastError > 0 )
                  QueueFormatName = (unsigned __int16)LastError | 0x80070000;
              }
            }
          }
        }
        else
        {
          QueueFormatName = -1072824283;
        }
      }
      else
      {
        v14 = GetLastError();
        QueueFormatName = v14;
        if ( v14 > 0 )
          QueueFormatName = (unsigned __int16)v14 | 0x80070000;
      }
    }
  }
  if ( lpwcsFormatName )
    free((void *)lpwcsFormatName);
  if ( v7 )
    free(v7);
  if ( v6 )
    LocalFree(v6);
  if ( !a3 )
  {
    if ( NewAcl )
      LocalFree(NewAcl);
  }
  return (unsigned int)QueueFormatName;
}

```

## disassembly

```asm
0x180012d10  mov     [rsp-8+bDaclPresent], rcx
0x180012d15  push    rbp
0x180012d16  push    rbx
0x180012d17  push    rsi
0x180012d18  push    rdi
0x180012d19  push    r13
0x180012d1b  push    r14
0x180012d1d  push    r15
0x180012d1f  lea     rbp, [rsp-27h]
0x180012d24  sub     rsp, 0A0h
0x180012d2b  mov     r13d, r8d
0x180012d2e  mov     r15, rdx
0x180012d31  xor     r14d, r14d
0x180012d34  cmp     [rdx+838h], r14d
0x180012d3b  jz      short loc_180012D44
0x180012d3d  xor     eax, eax
0x180012d3f  jmp     loc_180012F28
0x180012d44  mov     [rbp+57h+lpwcsFormatName], r14
0x180012d48  mov     rsi, r14
0x180012d4b  mov     [rbp+57h+pSecurityDescriptor], r14
0x180012d4f  xorps   xmm0, xmm0
0x180012d52  xor     eax, eax
0x180012d54  movups  [rbp+57h+var_60], xmm0
0x180012d58  movups  [rbp+57h+var_50], xmm0
0x180012d5c  mov     [rbp+57h+var_40], rax
0x180012d60  mov     [rbp+57h+NewAcl], r14
0x180012d64  mov     rdi, r14
0x180012d67  mov     [rbp+57h+var_A0], r14
0x180012d6b  mov     [rbp+57h+pDacl], r14
0x180012d6f  mov     dword ptr [rbp+57h+bDaclPresent], r14d
0x180012d73  mov     [rbp+57h+bDaclDefaulted], r14d
0x180012d77  mov     rax, [rdx+830h]
0x180012d7e  test    rax, rax
0x180012d81  jz      short loc_180012D88
0x180012d83  mov     rdx, [rax]
0x180012d86  jmp     short loc_180012D8B
0x180012d88  mov     rdx, r14; wchar_t *
0x180012d8b  lea     r8, [rbp+57h+lpwcsFormatName]; wchar_t **
0x180012d8f  call    ?GetQueueFormatName@CMSMQTriggerSet@@AEAAJPEB_WPEAPEA_W@Z; CMSMQTriggerSet::GetQueueFormatName(wchar_t const *,wchar_t * *)
0x180012d94  mov     ebx, eax
0x180012d96  test    eax, eax
0x180012d98  js      loc_180012EE3
0x180012d9e  lea     r9, [rbp+57h+pSecurityDescriptor]; void **
0x180012da2  mov     rdx, [rbp+57h+lpwcsFormatName]; wchar_t *
0x180012da6  call    ?GetQueueSecurityDescriptor@CMSMQTriggerSet@@AEAAJPEB_WKPEAPEAX@Z; CMSMQTriggerSet::GetQueueSecurityDescriptor(wchar_t const *,ulong,void * *)
0x180012dab  mov     ebx, eax
0x180012dad  mov     rsi, [rbp+57h+pSecurityDescriptor]
0x180012db1  test    eax, eax
0x180012db3  js      loc_180012EE3
0x180012db9  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180012dbd  lea     r8, [rbp+57h+pDacl]; pDacl
0x180012dc1  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180012dc5  mov     rcx, rsi; pSecurityDescriptor
0x180012dc8  call    cs:__imp_GetSecurityDescriptorDacl
0x180012dce  test    eax, eax
0x180012dd0  jnz     short loc_180012DF0
0x180012dd2  call    cs:__imp_GetLastError
0x180012dd8  mov     ebx, eax
0x180012dda  test    eax, eax
0x180012ddc  jle     loc_180012EE3
0x180012de2  movzx   ebx, ax
0x180012de5  or      ebx, 80070000h
0x180012deb  jmp     loc_180012EE3
0x180012df0  cmp     dword ptr [rbp+57h+bDaclPresent], r14d
0x180012df4  jnz     short loc_180012E00
0x180012df6  mov     ebx, 0C00E0025h
0x180012dfb  jmp     loc_180012EE3
0x180012e00  lea     rdx, [rbp+57h+var_A0]; void **
0x180012e04  call    ?GetTriggerServiceSid@CMSMQTriggerSet@@AEAAJPEAPEAX@Z; CMSMQTriggerSet::GetTriggerServiceSid(void * *)
0x180012e09  mov     ebx, eax
0x180012e0b  mov     rdi, [rbp+57h+var_A0]
0x180012e0f  test    eax, eax
0x180012e11  js      loc_180012EE3
0x180012e17  mov     r8, rdi; void *
0x180012e1a  mov     rdx, [rbp+57h+pDacl]; struct _ACL *
0x180012e1e  call    ?DeleteTriggerServiceFromDacl@CMSMQTriggerSet@@AEAAJPEAU_ACL@@PEAX@Z; CMSMQTriggerSet::DeleteTriggerServiceFromDacl(_ACL *,void *)
0x180012e23  mov     r8, [rbp+57h+pDacl]; OldAcl
0x180012e27  mov     [rbp+57h+NewAcl], r8
0x180012e2b  mov     ebx, 1
0x180012e30  mov     r14d, 80070000h
0x180012e36  test    r13d, r13d
0x180012e39  jnz     short loc_180012E93
0x180012e3b  mov     qword ptr [rbp+57h+pListOfExplicitEntries.grfInheritance], 0
0x180012e43  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], rbx
0x180012e47  mov     eax, [r15+14h]
0x180012e4b  neg     eax
0x180012e4d  sbb     ecx, ecx
0x180012e4f  neg     ecx
0x180012e51  add     ecx, 2
0x180012e54  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], ecx
0x180012e57  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], ebx
0x180012e5a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.pMultipleTrustee], 0
0x180012e62  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], 0
0x180012e6a  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rdi
0x180012e6e  lea     r9, [rbp+57h+NewAcl]; NewAcl
0x180012e72  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180012e76  mov     ecx, ebx; cCountOfExplicitEntries
0x180012e78  call    cs:__imp_SetEntriesInAclW
0x180012e7e  mov     ebx, eax
0x180012e80  test    eax, eax
0x180012e82  jle     short loc_180012E8A
0x180012e84  movzx   ebx, ax
0x180012e87  or      ebx, r14d
0x180012e8a  test    ebx, ebx
0x180012e8c  js      short loc_180012EE3
0x180012e8e  mov     ebx, 1
0x180012e93  mov     edx, ebx; dwRevision
0x180012e95  lea     rcx, [rbp+57h+var_60]; pSecurityDescriptor
0x180012e99  call    cs:__imp_InitializeSecurityDescriptor
0x180012e9f  test    eax, eax
0x180012ea1  jnz     short loc_180012EB7
0x180012ea3  call    cs:__imp_GetLastError
0x180012ea9  mov     ebx, eax
0x180012eab  test    eax, eax
0x180012ead  jle     short loc_180012EE3
0x180012eaf  movzx   ebx, ax
0x180012eb2  or      ebx, r14d
0x180012eb5  jmp     short loc_180012EE3
0x180012eb7  xor     r9d, r9d; bDaclDefaulted
0x180012eba  mov     r8, [rbp+57h+NewAcl]; pDacl
0x180012ebe  mov     edx, ebx; bDaclPresent
0x180012ec0  lea     rcx, [rbp+57h+var_60]; pSecurityDescriptor
0x180012ec4  call    cs:__imp_SetSecurityDescriptorDacl
0x180012eca  test    eax, eax
0x180012ecc  jz      short loc_180012EA3
0x180012ece  lea     r8, [rbp+57h+var_60]; pSecurityDescriptor
0x180012ed2  mov     edx, 4; SecurityInformation
0x180012ed7  mov     rcx, [rbp+57h+lpwcsFormatName]; lpwcsFormatName
0x180012edb  call    cs:__imp_MQSetQueueSecurity
0x180012ee1  mov     ebx, eax
0x180012ee3  cmp     [rbp+57h+lpwcsFormatName], 0
0x180012ee8  jz      short loc_180012EF5
0x180012eea  mov     rcx, [rbp+57h+lpwcsFormatName]; Block
0x180012eee  call    cs:__imp_free
0x180012ef4  nop
0x180012ef5  test    rdi, rdi
0x180012ef8  jz      short loc_180012F04
0x180012efa  mov     rcx, rdi; Block
0x180012efd  call    cs:__imp_free
0x180012f03  nop
0x180012f04  test    rsi, rsi
0x180012f07  jz      short loc_180012F12
0x180012f09  mov     rcx, rsi; hMem
0x180012f0c  call    cs:__imp_LocalFree
0x180012f12  test    r13d, r13d
0x180012f15  jnz     short loc_180012F26
0x180012f17  mov     rcx, [rbp+57h+NewAcl]; hMem
0x180012f1b  test    rcx, rcx
0x180012f1e  jz      short loc_180012F26
0x180012f20  call    cs:__imp_LocalFree
0x180012f26  mov     eax, ebx
0x180012f28  add     rsp, 0A0h
0x180012f2f  pop     r15
0x180012f31  pop     r14
0x180012f33  pop     r13
0x180012f35  pop     rdi
0x180012f36  pop     rsi
0x180012f37  pop     rbx
0x180012f38  pop     rbp
0x180012f39  retn
```
