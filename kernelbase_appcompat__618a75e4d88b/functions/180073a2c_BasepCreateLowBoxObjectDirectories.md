# BasepCreateLowBoxObjectDirectories

- ea: `0x180073a2c`
- end: `0x180074618`
- name: `BasepCreateLowBoxObjectDirectories`
- size: `3052`
- prototype: `__int64 __usercall@<rax>(PSID Sid@<rcx>, HANDLE TokenHandle@<rdx>, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ec14`

## callees

- `0x180073a2c`
- `0x180074620`
- `0x180074ac8`
- `0x180074b5c`
- `0x1800751e0`
- `0x1800753a0`
- `0x180075568`
- `0x180075754`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x1800744ff`
- `ntdll!RtlSubAuthoritySid` at `0x180074515`
- `ntdll!RtlSubAuthoritySid` at `0x18007452b`
- `ntdll!RtlSubAuthoritySid` at `0x180074541`
- `ntdll!RtlSubAuthoritySid` at `0x1800744ff`
- `ntdll!RtlSubAuthoritySid` at `0x180074515`
- `ntdll!RtlSubAuthoritySid` at `0x18007452b`
- `ntdll!RtlSubAuthoritySid` at `0x180074541`
- `ntdll!RtlFreeUnicodeString` at `0x18007439c`
- `ntdll!RtlFreeUnicodeString` at `0x1800743ac`
- `ntdll!RtlFreeUnicodeString` at `0x1800743bc`
- `ntdll!RtlFreeUnicodeString` at `0x1800745ac`
- `ntdll!RtlFreeUnicodeString` at `0x18007439c`
- `ntdll!RtlFreeUnicodeString` at `0x1800743ac`
- `ntdll!RtlFreeUnicodeString` at `0x1800743bc`
- `ntdll!RtlFreeUnicodeString` at `0x1800745ac`
- `ntdll!RtlInitUnicodeString` at `0x180073e13`
- `ntdll!RtlInitUnicodeString` at `0x180073f57`
- `ntdll!RtlInitUnicodeString` at `0x180074044`
- `ntdll!RtlInitUnicodeString` at `0x18007410a`
- `ntdll!RtlInitUnicodeString` at `0x180074174`
- `ntdll!RtlInitUnicodeString` at `0x180074585`
- `ntdll!RtlInitUnicodeString` at `0x180073e13`
- `ntdll!RtlInitUnicodeString` at `0x180073f57`
- `ntdll!RtlInitUnicodeString` at `0x180074044`
- `ntdll!RtlInitUnicodeString` at `0x18007410a`
- `ntdll!RtlInitUnicodeString` at `0x180074174`
- `ntdll!RtlInitUnicodeString` at `0x180074585`
- `ntdll!NtQuerySecurityObject` at `0x180073cf4`
- `ntdll!NtQuerySecurityObject` at `0x180073d59`
- `ntdll!NtQuerySecurityObject` at `0x180073cf4`
- `ntdll!NtQuerySecurityObject` at `0x180073d59`
- `ntdll!NtCreateFile` at `0x18007425c`
- `ntdll!NtCreateFile` at `0x18007425c`
- `ntdll!RtlGetAce` at `0x180074204`
- `ntdll!RtlGetAce` at `0x180074204`
- `ntdll!NtQueryInformationToken` at `0x180073ba8`
- `ntdll!NtQueryInformationToken` at `0x180073bd6`
- `ntdll!NtQueryInformationToken` at `0x180073c2d`
- `ntdll!NtQueryInformationToken` at `0x180073ba8`
- `ntdll!NtQueryInformationToken` at `0x180073bd6`
- `ntdll!NtQueryInformationToken` at `0x180073c2d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180073c4d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180073c94`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800744c2`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180073c4d`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180073c94`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800744c2`
- `ntdll!NtClose` at `0x180074340`
- `ntdll!NtClose` at `0x180074355`
- `ntdll!NtClose` at `0x18007436a`
- `ntdll!NtClose` at `0x18007437f`
- `ntdll!NtClose` at `0x180074606`
- `ntdll!NtClose` at `0x18019be51`
- `ntdll!NtClose` at `0x180074340`
- `ntdll!NtClose` at `0x180074355`
- `ntdll!NtClose` at `0x18007436a`
- `ntdll!NtClose` at `0x18007437f`
- `ntdll!NtClose` at `0x180074606`
- `ntdll!NtClose` at `0x18019be51`
- `ntdll!RtlGetAppContainerSidType` at `0x180073c6b`
- `ntdll!RtlGetAppContainerSidType` at `0x180073c6b`
- `ntdll!RtlGetAppContainerParent` at `0x1800744a3`
- `ntdll!RtlGetAppContainerParent` at `0x1800744a3`
- `ntdll!RtlFreeHeap` at `0x180074289`
- `ntdll!RtlFreeHeap` at `0x1800742b1`
- `ntdll!RtlFreeHeap` at `0x1800742dc`
- `ntdll!RtlFreeHeap` at `0x180074307`
- `ntdll!RtlFreeHeap` at `0x18007432a`
- `ntdll!RtlFreeHeap` at `0x1800744e3`
- `ntdll!RtlFreeHeap` at `0x180074289`
- `ntdll!RtlFreeHeap` at `0x1800742b1`
- `ntdll!RtlFreeHeap` at `0x1800742dc`
- `ntdll!RtlFreeHeap` at `0x180074307`
- `ntdll!RtlFreeHeap` at `0x18007432a`
- `ntdll!RtlFreeHeap` at `0x1800744e3`
- `ntdll!NtOpenDirectoryObject` at `0x180073e64`
- `ntdll!NtOpenDirectoryObject` at `0x180073e64`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180073ec3`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180073fb1`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800740a1`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180073ec3`
- `ntdll!NtCreateDirectoryObjectEx` at `0x180073fb1`
- `ntdll!NtCreateDirectoryObjectEx` at `0x1800740a1`
- `ntdll!RtlAllocateHeap` at `0x180073bfd`
- `ntdll!RtlAllocateHeap` at `0x180073d25`
- `ntdll!RtlAllocateHeap` at `0x180073bfd`
- `ntdll!RtlAllocateHeap` at `0x180073d25`

## pseudocode

```c
NTSTATUS __fastcall BasepCreateLowBoxObjectDirectories(
        PSID Sid,
        HANDLE TokenHandle,
        HANDLE *a3,
        HANDLE *a4,
        HANDLE *a5,
        __int64 a6,
        void *a7,
        HANDLE *a8,
        _QWORD *a9)
{
  PVOID v9; // r15
  PVOID v10; // rdi
  HANDLE *v11; // rsi
  NTSTATUS result; // eax
  PSID *Heap; // r14
  NTSTATUS v17; // ebx
  int v18; // eax
  ACL *v19; // rdi
  int v20; // ebx
  ULONG v21; // edx
  int *v22; // rdx
  int v23; // r8d
  int v24; // ecx
  HANDLE *v25; // rcx
  ULONG v26; // esi
  ULONG v27; // edi
  ULONG v28; // ebx
  PULONG v29; // rax
  HANDLE v30; // rax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PWSTR FileAttributes; // [rsp+28h] [rbp-D8h]
  ULONG LengthNeeded; // [rsp+60h] [rbp-A0h] BYREF
  int v35; // [rsp+64h] [rbp-9Ch] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+6Ch] [rbp-94h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE SourceHandle; // [rsp+78h] [rbp-88h] BYREF
  PVOID Ace; // [rsp+80h] [rbp-80h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES v42; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v43; // [rsp+C0h] [rbp-40h] BYREF
  PSID Sida; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE v45; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v46; // [rsp+D8h] [rbp-28h] BYREF
  HANDLE v47; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v49; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING v50; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v52[3]; // [rsp+128h] [rbp+28h] BYREF
  __int64 v53; // [rsp+134h] [rbp+34h]
  PHANDLE v54; // [rsp+140h] [rbp+40h]
  _QWORD *v55; // [rsp+148h] [rbp+48h]
  HANDLE *v56; // [rsp+150h] [rbp+50h]
  _OWORD v57[2]; // [rsp+158h] [rbp+58h] BYREF
  PACL Acl; // [rsp+178h] [rbp+78h]
  HANDLE *v59; // [rsp+180h] [rbp+80h]
  struct _UNICODE_STRING v60; // [rsp+188h] [rbp+88h] BYREF
  struct _UNICODE_STRING v61; // [rsp+198h] [rbp+98h] BYREF
  struct _UNICODE_STRING v62; // [rsp+1A8h] [rbp+A8h] BYREF
  struct _UNICODE_STRING v63; // [rsp+1B8h] [rbp+B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+1C8h] [rbp+C8h] BYREF
  _OWORD v65[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  PVOID P; // [rsp+218h] [rbp+118h]
  _OWORD v67[2]; // [rsp+220h] [rbp+120h] BYREF
  PVOID v68; // [rsp+240h] [rbp+140h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+248h] [rbp+148h] BYREF
  WCHAR SourceString[256]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR v71[256]; // [rsp+460h] [rbp+360h] BYREF
  WCHAR v72[256]; // [rsp+660h] [rbp+560h] BYREF
  WCHAR v73[256]; // [rsp+860h] [rbp+760h] BYREF

  v9 = 0;
  v10 = a7;
  v11 = a3;
  v59 = a5;
  v54 = a8;
  v55 = a9;
  *(_QWORD *)&DestinationString.Length = a3;
  Acl = 0;
  v56 = a4;
  Ace = a7;
  LengthNeeded = 0;
  TokenInformation = 0;
  v35 = 0;
  Sida = 0;
  Handle = 0;
  memset(v57, 0, sizeof(v57));
  memset_0(SourceString, 0, sizeof(SourceString));
  *v11 = 0;
  FileHandle = 0;
  P = 0;
  v68 = 0;
  memset(&v42, 0, sizeof(v42));
  SourceHandle = 0;
  v52[0] = 4;
  v46 = 0;
  v43 = 0;
  v47 = 0;
  v45 = 0;
  v52[1] = 1048578;
  memset(v65, 0, sizeof(v65));
  v52[2] = 8;
  v53 = 1048580;
  v60 = 0;
  v36 = 0;
  v62 = 0;
  *a4 = 0;
  memset(v67, 0, sizeof(v67));
  v61 = 0;
  v63 = 0;
  IoStatusBlock = 0;
  v49 = 0;
  v50 = 0;
  UnicodeString = 0;
  result = NtQueryInformationToken(TokenHandle, TokenSessionId, &TokenInformation, 4u, &LengthNeeded);
  if ( result >= 0 )
  {
    result = NtQueryInformationToken(TokenHandle, TokenIsRestricted|TokenGroups, &v36, 4u, &LengthNeeded);
    if ( result >= 0 )
    {
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x54u);
      if ( !Heap )
      {
        v17 = -1073741801;
        goto LABEL_43;
      }
      v17 = NtQueryInformationToken(TokenHandle, TokenUser, Heap, 0x54u, &LengthNeeded);
      if ( v17 < 0 )
        goto LABEL_41;
      v17 = RtlConvertSidToUnicodeString(&UnicodeString, *Heap, 1u);
      if ( v17 < 0 )
        goto LABEL_41;
      result = RtlGetAppContainerSidType(Sid, &v35);
      if ( result < 0 )
        return result;
      if ( v35 == 2 )
      {
        result = RtlConvertSidToUnicodeString(&v49, Sid, 1u);
        if ( result < 0 )
          return result;
        goto LABEL_9;
      }
      result = RtlGetAppContainerParent(Sid, &Sida);
      if ( result >= 0 )
      {
        v17 = RtlConvertSidToUnicodeString(&v50, Sida, 1u);
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Sida);
        if ( v17 >= 0 )
        {
          v26 = *RtlSubAuthoritySid(Sid, 0xBu);
          v27 = *RtlSubAuthoritySid(Sid, 0xAu);
          v28 = *RtlSubAuthoritySid(Sid, 9u);
          v29 = RtlSubAuthoritySid(Sid, 8u);
          LODWORD(ReturnLength) = v28;
          v17 = RtlStringCchPrintfW(v72, 256, L"%u-%u-%u-%u", *v29, ReturnLength, v27, v26);
          if ( v17 >= 0 )
          {
            RtlInitUnicodeString(&v49, v72);
            v10 = Ace;
            v11 = *(HANDLE **)&DestinationString.Length;
LABEL_9:
            v17 = BasepOpenBaseObjectDirectory(v35, TokenInformation, (int)&v50, v36, (__int64)&UnicodeString, &Handle);
            if ( v17 >= 0 )
            {
              v17 = NtQuerySecurityObject(Handle, 4u, 0, 0, &LengthNeeded);
              if ( (int)(v17 + 0x80000000) < 0 || v17 == -1073741789 )
              {
                v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, LengthNeeded);
                if ( !v9 )
                {
                  v17 = -1073741801;
                  goto LABEL_43;
                }
                v17 = NtQuerySecurityObject(Handle, 4u, v9, LengthNeeded, &LengthNeeded);
                if ( v17 >= 0 )
                {
                  v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 0, v57);
                  if ( v17 >= 0 )
                  {
                    DestinationString = 0;
                    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
                    if ( v35 != 2 && (v35 != 1 || !v50.Buffer) )
                    {
                      v17 = -1073741811;
                      goto LABEL_42;
                    }
                    if ( v36 )
                    {
                      if ( v35 != 2 )
                      {
                        LODWORD(ReturnLengtha) = TokenInformation;
                        v18 = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects\\%ws\\%ws",
                                L"\\Sessions",
                                ReturnLengtha,
                                UnicodeString.Buffer,
                                v50.Buffer);
LABEL_18:
                        v17 = v18;
                        if ( v18 < 0 )
                          goto LABEL_42;
                        RtlInitUnicodeString(&DestinationString, SourceString);
                        ObjectAttributes.Length = 48;
                        ObjectAttributes.ObjectName = &DestinationString;
                        ObjectAttributes.RootDirectory = 0;
                        ObjectAttributes.Attributes = 0;
                        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                        v17 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
                        if ( v17 < 0 )
                          goto LABEL_42;
                        v42.RootDirectory = FileHandle;
                        v42.Length = 48;
                        v42.ObjectName = &v49;
                        v42.SecurityDescriptor = v57;
                        v42.Attributes = 130;
                        v42.SecurityQualityOfService = 0;
                        v17 = NtCreateDirectoryObjectEx(&SourceHandle, 15, &v42, Handle, 1);
                        if ( v17 >= 0 )
                        {
                          v17 = BasepSetKernelIntegrityLabel(SourceHandle);
                          if ( v17 >= 0 )
                          {
                            v17 = BasepOpenShadowRpcControlDirectory(
                                    v35,
                                    TokenInformation,
                                    v36,
                                    (int)&UnicodeString,
                                    (__int64)FileHandle,
                                    &v46);
                            if ( v17 >= 0 )
                            {
                              v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 7, v65);
                              if ( v17 >= 0 )
                              {
                                RtlInitUnicodeString(&v60, L"RPC Control");
                                v42.RootDirectory = SourceHandle;
                                v42.Length = 48;
                                v42.ObjectName = &v60;
                                v42.SecurityDescriptor = v65;
                                v42.Attributes = 130;
                                v42.SecurityQualityOfService = 0;
                                v17 = NtCreateDirectoryObjectEx(&v43, 15, &v42, v46, 1);
                                if ( v17 >= 0 )
                                {
                                  v17 = BasepSetKernelIntegrityLabel(v43);
                                  if ( v17 >= 0 )
                                  {
                                    v17 = BasepOpenShadowGlobalDirectory(
                                            v35,
                                            TokenInformation,
                                            v36,
                                            (int)&UnicodeString,
                                            (__int64)FileHandle,
                                            &v47);
                                    if ( v17 >= 0 )
                                    {
                                      v17 = BasepBuildPackageSecurityDescriptor(v9, Sid, *Heap, 7, v67);
                                      if ( v17 >= 0 )
                                      {
                                        RtlInitUnicodeString(&v61, L"Global");
                                        v42.RootDirectory = SourceHandle;
                                        v42.Length = 48;
                                        v42.ObjectName = &v61;
                                        v42.SecurityDescriptor = v67;
                                        v42.Attributes = 130;
                                        v42.SecurityQualityOfService = 0;
                                        v17 = NtCreateDirectoryObjectEx(&v45, 15, &v42, v47, 1);
                                        if ( v17 >= 0 )
                                        {
                                          v17 = BasepSetKernelIntegrityLabel(v45);
                                          if ( v17 >= 0 )
                                          {
                                            v17 = RtlStringCchPrintfW(v71, 256, L"%ws\\%ws", SourceString, v49.Buffer);
                                            if ( v17 >= 0 )
                                            {
                                              RtlInitUnicodeString(&v62, v71);
                                              v17 = BasepCreateLowBoxSymbolicLinks(SourceHandle, &v62, v57, a6, v10);
                                              if ( v17 >= 0 )
                                              {
                                                v17 = RtlStringCchPrintfW(v73, 256, L"\\Device\\NamedPipe%ws", v71);
                                                if ( v17 >= 0 )
                                                {
                                                  RtlInitUnicodeString(&v63, v73);
                                                  v19 = Acl;
                                                  v42.ObjectName = &v63;
                                                  v20 = 0;
                                                  v42.Length = 48;
                                                  v42.SecurityDescriptor = v57;
                                                  v21 = 0;
                                                  v42.RootDirectory = 0;
                                                  v42.Attributes = 66;
                                                  v42.SecurityQualityOfService = 0;
                                                  Ace = 0;
                                                  while ( RtlGetAce(v19, v21, &Ace) >= 0 )
                                                  {
                                                    v22 = v52;
                                                    v23 = *((_DWORD *)Ace + 1);
                                                    *((_WORD *)Ace + 2) = 0;
                                                    v24 = 4;
                                                    do
                                                    {
                                                      if ( v24 == (unsigned __int16)(v24 & v23) )
                                                        *((_DWORD *)Ace + 1) |= v22[1];
                                                      v22 += 2;
                                                      v24 = *v22;
                                                    }
                                                    while ( *v22 );
                                                    v21 = ++v20;
                                                  }
                                                  v17 = NtCreateFile(
                                                          v54,
                                                          0x1F0006u,
                                                          &v42,
                                                          &IoStatusBlock,
                                                          0,
                                                          0x80u,
                                                          3u,
                                                          3u,
                                                          1u,
                                                          0,
                                                          0);
                                                  if ( v17 >= 0 )
                                                  {
                                                    if ( v35 == 1 )
                                                    {
                                                      v30 = Handle;
                                                      Handle = 0;
                                                      *v55 = v30;
                                                    }
                                                    v25 = v56;
                                                    *v11 = SourceHandle;
                                                    *v25 = v43;
                                                    *v59 = v45;
                                                    goto LABEL_42;
                                                  }
                                                }
                                              }
                                            }
                                          }
                                        }
                                      }
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                        goto LABEL_41;
                      }
                      FileAttributes = UnicodeString.Buffer;
                    }
                    else
                    {
                      if ( v35 == 2 )
                      {
                        LODWORD(ReturnLengtha) = TokenInformation;
                        v18 = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects",
                                L"\\Sessions",
                                ReturnLengtha);
                        goto LABEL_18;
                      }
                      FileAttributes = v50.Buffer;
                    }
                    LODWORD(ReturnLengtha) = TokenInformation;
                    v18 = RtlStringCchPrintfW(
                            SourceString,
                            256,
                            L"%ws\\%ld\\AppContainerNamedObjects\\%ws",
                            L"\\Sessions",
                            ReturnLengtha,
                            FileAttributes);
                    goto LABEL_18;
                  }
                }
              }
            }
LABEL_41:
            if ( !v9 )
            {
LABEL_43:
              if ( Acl )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Acl);
              if ( P )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( v68 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v68);
              if ( Heap )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
              if ( Handle )
                NtClose(Handle);
              if ( FileHandle )
                NtClose(FileHandle);
              if ( v46 )
                NtClose(v46);
              if ( v47 )
                NtClose(v47);
              if ( v49.Buffer != v72 )
                RtlFreeUnicodeString(&v49);
              RtlFreeUnicodeString(&v50);
              RtlFreeUnicodeString(&UnicodeString);
              if ( v17 < 0 )
              {
                if ( SourceHandle )
                  NtClose(SourceHandle);
                if ( v43 )
                  NtClose(v43);
              }
              return v17;
            }
LABEL_42:
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v9);
            goto LABEL_43;
          }
          RtlFreeUnicodeString(&v50);
        }
        return v17;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180073a2c  push    rbp
0x180073a2e  push    rbx
0x180073a2f  push    rsi
0x180073a30  push    rdi
0x180073a31  push    r12
0x180073a33  push    r13
0x180073a35  push    r14
0x180073a37  push    r15
0x180073a39  lea     rbp, [rsp-978h]
0x180073a41  sub     rsp, 0A78h
0x180073a48  mov     rax, cs:__security_cookie
0x180073a4f  xor     rax, rsp
0x180073a52  mov     [rbp+9B0h+var_50], rax
0x180073a59  mov     rax, [rbp+9B0h+arg_20]
0x180073a60  xor     r15d, r15d
0x180073a63  mov     rdi, [rbp+9B0h+arg_30]
0x180073a6a  xorps   xmm0, xmm0
0x180073a6d  mov     r13, [rbp+9B0h+arg_28]
0x180073a74  mov     rsi, r8
0x180073a77  mov     [rbp+9B0h+var_930], rax
0x180073a7e  mov     rbx, rdx
0x180073a81  mov     rax, [rbp+9B0h+arg_38]
0x180073a88  mov     r12, rcx
0x180073a8b  mov     [rbp+9B0h+var_970], rax
0x180073a8f  lea     rcx, [rbp+9B0h+SourceString]; void *
0x180073a96  mov     rax, [rbp+9B0h+arg_40]
0x180073a9d  xor     edx, edx; Val
0x180073a9f  mov     [rbp+9B0h+var_968], rax
0x180073aa3  mov     r14, r9
0x180073aa6  xor     eax, eax
0x180073aa8  mov     qword ptr [rbp+9B0h+DestinationString.Length], r8
0x180073aac  mov     r8d, 200h; Size
0x180073ab2  mov     [rbp+9B0h+Acl], rax
0x180073ab6  mov     [rbp+9B0h+var_960], r9
0x180073aba  mov     [rbp+9B0h+Ace], rdi
0x180073abe  mov     [rsp+0AB0h+LengthNeeded], r15d
0x180073ac3  mov     [rsp+0AB0h+TokenInformation], r15d
0x180073ac8  mov     [rsp+0AB0h+var_A4C], r15d
0x180073acd  mov     [rbp+9B0h+Sid], r15
0x180073ad1  mov     [rsp+0AB0h+Handle], r15
0x180073ad6  movups  [rbp+9B0h+var_958], xmm0
0x180073ada  movups  [rbp+9B0h+var_948], xmm0
0x180073ade  call    memset_0
0x180073ae3  xorps   xmm0, xmm0
0x180073ae6  mov     [rsi], r15
0x180073ae9  xor     eax, eax
0x180073aeb  mov     [rbp+9B0h+FileHandle], r15
0x180073aef  xorps   xmm1, xmm1
0x180073af2  mov     [rbp+9B0h+P], rax
0x180073af9  mov     [rbp+9B0h+var_870], rax
0x180073b00  lea     r8, [rsp+0AB0h+TokenInformation]; TokenInformation
0x180073b05  movups  xmmword ptr [rbp+9B0h+var_A20.Length], xmm0
0x180073b09  lea     ecx, [rax+4]
0x180073b0c  mov     [rsp+0AB0h+SourceHandle], r15
0x180073b11  mov     [rbp+9B0h+var_988], ecx
0x180073b14  lea     edx, [rcx+8]; TokenInformationClass
0x180073b17  mov     r9d, ecx; TokenInformationLength
0x180073b1a  mov     [rbp+9B0h+var_9D8], r15
0x180073b1e  lea     rax, [rsp+0AB0h+LengthNeeded]
0x180073b23  mov     [rbp+9B0h+var_9F0], r15
0x180073b27  mov     rcx, rbx; TokenHandle
0x180073b2a  mov     [rbp+9B0h+var_9D0], r15
0x180073b2e  movups  xmmword ptr [rbp+9B0h+var_A20.ObjectName], xmm0
0x180073b32  mov     [rbp+9B0h+var_9E0], r15
0x180073b36  movups  xmmword ptr [rbp+9B0h+var_A20.SecurityDescriptor], xmm0
0x180073b3a  mov     [rbp+9B0h+var_984], 100002h
0x180073b41  movups  [rbp+9B0h+var_8B8], xmm0
0x180073b48  mov     [rbp+9B0h+var_980], 8
0x180073b4f  movups  [rbp+9B0h+var_8A8], xmm0
0x180073b56  mov     [rbp+9B0h+var_97C], 100004h
0x180073b5e  movups  xmmword ptr [rbp+9B0h+var_928.Length], xmm0
0x180073b65  mov     [rsp+0AB0h+var_A48], r15d
0x180073b6a  movups  xmmword ptr [rbp+9B0h+var_908.Length], xmm1
0x180073b71  mov     [r14], r15
0x180073b74  movups  [rbp+9B0h+var_890], xmm0
0x180073b7b  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x180073b80  movups  [rbp+9B0h+var_880], xmm0
0x180073b87  movups  xmmword ptr [rbp+9B0h+var_918.Length], xmm0
0x180073b8e  movups  xmmword ptr [rbp+9B0h+var_8F8.Length], xmm1
0x180073b95  movups  xmmword ptr [rbp+9B0h+IoStatusBlock], xmm0
0x180073b9c  movups  xmmword ptr [rbp+9B0h+var_9B8.Length], xmm1
0x180073ba0  movups  xmmword ptr [rbp+9B0h+var_9A8.Length], xmm0
0x180073ba4  movups  xmmword ptr [rbp+9B0h+UnicodeString.Length], xmm1
0x180073ba8  call    cs:__imp_NtQueryInformationToken
0x180073baf  nop     dword ptr [rax+rax+00h]
0x180073bb4  test    eax, eax
0x180073bb6  js      loc_1800743D2
0x180073bbc  lea     rax, [rsp+0AB0h+LengthNeeded]
0x180073bc1  mov     rcx, rbx; TokenHandle
0x180073bc4  lea     r9d, [r15+4]; TokenInformationLength
0x180073bc8  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x180073bcd  lea     r8, [rsp+0AB0h+var_A48]; TokenInformation
0x180073bd2  lea     edx, [r15+2Ah]; TokenInformationClass
0x180073bd6  call    cs:__imp_NtQueryInformationToken
0x180073bdd  nop     dword ptr [rax+rax+00h]
0x180073be2  test    eax, eax
0x180073be4  js      loc_1800743D2
0x180073bea  mov     rcx, gs:60h
0x180073bf3  lea     r8d, [r15+54h]; Size
0x180073bf7  xor     edx, edx; Flags
0x180073bf9  mov     rcx, [rcx+30h]; HeapHandle
0x180073bfd  call    cs:__imp_RtlAllocateHeap
0x180073c04  nop     dword ptr [rax+rax+00h]
0x180073c09  mov     r14, rax
0x180073c0c  test    rax, rax
0x180073c0f  jz      loc_18007459E
0x180073c15  lea     rax, [rsp+0AB0h+LengthNeeded]
0x180073c1a  mov     r8, r14; TokenInformation
0x180073c1d  lea     r9d, [r15+54h]; TokenInformationLength
0x180073c21  mov     [rsp+0AB0h+ReturnLength], rax; ReturnLength
0x180073c26  lea     edx, [r15+1]; TokenInformationClass
0x180073c2a  mov     rcx, rbx; TokenHandle
0x180073c2d  call    cs:__imp_NtQueryInformationToken
0x180073c34  nop     dword ptr [rax+rax+00h]
0x180073c39  mov     ebx, eax
0x180073c3b  test    eax, eax
0x180073c3d  js      loc_180074272
0x180073c43  mov     rdx, [r14]; Sid
0x180073c46  lea     rcx, [rbp+9B0h+UnicodeString]; UnicodeString
0x180073c4a  mov     r8b, 1; AllocateDestinationString
0x180073c4d  call    cs:__imp_RtlConvertSidToUnicodeString
0x180073c54  nop     dword ptr [rax+rax+00h]
0x180073c59  mov     ebx, eax
0x180073c5b  test    eax, eax
0x180073c5d  js      loc_180074272
0x180073c63  lea     rdx, [rsp+0AB0h+var_A4C]
0x180073c68  mov     rcx, r12
0x180073c6b  call    cs:__imp_RtlGetAppContainerSidType
0x180073c72  nop     dword ptr [rax+rax+00h]
0x180073c77  test    eax, eax
0x180073c79  js      loc_1800743D2
0x180073c7f  cmp     [rsp+0AB0h+var_A4C], 2
0x180073c84  jnz     loc_18007449C
0x180073c8a  mov     r8b, 1; AllocateDestinationString
0x180073c8d  lea     rcx, [rbp+9B0h+var_9B8]; UnicodeString
0x180073c91  mov     rdx, r12; Sid
0x180073c94  call    cs:__imp_RtlConvertSidToUnicodeString
0x180073c9b  nop     dword ptr [rax+rax+00h]
0x180073ca0  test    eax, eax
0x180073ca2  js      loc_1800743D2
0x180073ca8  mov     r9d, [rsp+0AB0h+var_A48]; int
0x180073cad  lea     rax, [rsp+0AB0h+Handle]
0x180073cb2  mov     edx, [rsp+0AB0h+TokenInformation]; int
0x180073cb6  lea     r8, [rbp+9B0h+var_9A8]; int
0x180073cba  mov     ecx, [rsp+0AB0h+var_A4C]; int
0x180073cbe  mov     qword ptr [rsp+0AB0h+FileAttributes], rax; FileHandle
0x180073cc3  lea     rax, [rbp+9B0h+UnicodeString]
0x180073cc7  mov     [rsp+0AB0h+ReturnLength], rax; __int64
0x180073ccc  call    BasepOpenBaseObjectDirectory
0x180073cd1  mov     ebx, eax
0x180073cd3  test    eax, eax
0x180073cd5  js      loc_180074272
0x180073cdb  mov     rcx, [rsp+0AB0h+Handle]; Handle
0x180073ce0  lea     rax, [rsp+0AB0h+LengthNeeded]
0x180073ce5  xor     r9d, r9d; Length
0x180073ce8  mov     [rsp+0AB0h+ReturnLength], rax; LengthNeeded
0x180073ced  xor     r8d, r8d; SecurityDescriptor
0x180073cf0  lea     edx, [r9+4]; SecurityInformation
0x180073cf4  call    cs:__imp_NtQuerySecurityObject
0x180073cfb  nop     dword ptr [rax+rax+00h]
0x180073d00  mov     ecx, 80000000h
0x180073d05  mov     ebx, eax
0x180073d07  add     eax, ecx
0x180073d09  test    ecx, eax
0x180073d0b  jz      loc_1800743F6
0x180073d11  mov     rcx, gs:60h
0x180073d1a  xor     edx, edx; Flags
0x180073d1c  mov     r8d, [rsp+0AB0h+LengthNeeded]; Size
0x180073d21  mov     rcx, [rcx+30h]; HeapHandle
0x180073d25  call    cs:__imp_RtlAllocateHeap
0x180073d2c  nop     dword ptr [rax+rax+00h]
0x180073d31  mov     r15, rax
0x180073d34  test    rax, rax
0x180073d37  jz      loc_1800745BD
0x180073d3d  mov     r9d, [rsp+0AB0h+LengthNeeded]; Length
0x180073d42  lea     rax, [rsp+0AB0h+LengthNeeded]
0x180073d47  mov     rcx, [rsp+0AB0h+Handle]; Handle
0x180073d4c  mov     r8, r15; SecurityDescriptor
0x180073d4f  mov     edx, 4; SecurityInformation
0x180073d54  mov     [rsp+0AB0h+ReturnLength], rax; LengthNeeded
0x180073d59  call    cs:__imp_NtQuerySecurityObject
0x180073d60  nop     dword ptr [rax+rax+00h]
0x180073d65  mov     ebx, eax
0x180073d67  test    eax, eax
0x180073d69  js      loc_180074272
0x180073d6f  mov     r8, [r14]; Sid1
0x180073d72  lea     rax, [rbp+9B0h+var_958]
0x180073d76  xor     r9d, r9d
0x180073d79  mov     [rsp+0AB0h+ReturnLength], rax; PSECURITY_DESCRIPTOR
0x180073d7e  mov     rdx, r12; Sid
0x180073d81  mov     rcx, r15; SecurityDescriptor
0x180073d84  call    BasepBuildPackageSecurityDescriptor
0x180073d89  mov     ebx, eax
0x180073d8b  test    eax, eax
0x180073d8d  js      loc_180074272
0x180073d93  mov     eax, [rsp+0AB0h+var_A4C]
0x180073d97  xorps   xmm1, xmm1
0x180073d9a  mov     rdx, [rbp+9B0h+var_9A8.Buffer]
0x180073d9e  xorps   xmm0, xmm0
0x180073da1  movups  xmmword ptr [rbp+9B0h+DestinationString.Length], xmm0
0x180073da5  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.Length], xmm1
0x180073dac  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.ObjectName], xmm1
0x180073db3  movups  xmmword ptr [rbp+9B0h+ObjectAttributes.SecurityDescriptor], xmm1
0x180073dba  cmp     eax, 2
0x180073dbd  jnz     loc_1800745C7
0x180073dc3  cmp     [rsp+0AB0h+var_A48], 0
0x180073dc8  lea     r9, aSessions; "\\Sessions"
0x180073dcf  mov     ecx, [rsp+0AB0h+TokenInformation]
0x180073dd3  jnz     loc_180074407
0x180073dd9  cmp     eax, 2
0x180073ddc  jnz     loc_180074492
0x180073de2  mov     dword ptr [rsp+0AB0h+ReturnLength], ecx
0x180073de6  lea     r8, aWsLdAppcontain_1; "%ws\\%ld\\AppContainerNamedObjects"
0x180073ded  lea     rcx, [rbp+9B0h+SourceString]
0x180073df4  mov     edx, 100h
0x180073df9  call    RtlStringCchPrintfW
0x180073dfe  mov     ebx, eax
0x180073e00  test    eax, eax
0x180073e02  js      loc_180074277
0x180073e08  lea     rdx, [rbp+9B0h+SourceString]; SourceString
0x180073e0f  lea     rcx, [rbp+9B0h+DestinationString]; DestinationString
0x180073e13  call    cs:__imp_RtlInitUnicodeString
0x180073e1a  nop     dword ptr [rax+rax+00h]
0x180073e1f  lea     rax, [rbp+9B0h+DestinationString]
0x180073e23  mov     [rbp+9B0h+ObjectAttributes.Length], 30h ; '0'
0x180073e2d  xorps   xmm0, xmm0
0x180073e30  mov     [rbp+9B0h+ObjectAttributes.ObjectName], rax
0x180073e37  lea     r8, [rbp+9B0h+ObjectAttributes]; ObjectAttributes
0x180073e3e  mov     [rbp+9B0h+ObjectAttributes.RootDirectory], 0
0x180073e49  mov     edx, 0Fh; DesiredAccess
0x180073e4e  mov     [rbp+9B0h+ObjectAttributes.Attributes], 0
0x180073e58  lea     rcx, [rbp+9B0h+FileHandle]; FileHandle
0x180073e5c  movdqu  xmmword ptr [rbp+9B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180073e64  call    cs:__imp_NtOpenDirectoryObject
0x180073e6b  nop     dword ptr [rax+rax+00h]
0x180073e70  mov     ebx, eax
0x180073e72  test    eax, eax
0x180073e74  js      loc_180074277
0x180073e7a  mov     rax, [rbp+9B0h+FileHandle]
0x180073e7e  lea     r8, [rbp+9B0h+var_A20]
0x180073e82  mov     r9, [rsp+0AB0h+Handle]
0x180073e87  lea     rcx, [rsp+0AB0h+SourceHandle]
0x180073e8c  mov     [rbp+9B0h+var_A20.RootDirectory], rax
0x180073e90  mov     edx, 0Fh
0x180073e95  lea     rax, [rbp+9B0h+var_9B8]
0x180073e99  mov     [rbp+9B0h+var_A20.Length], 30h ; '0'
0x180073ea0  mov     [rbp+9B0h+var_A20.ObjectName], rax
0x180073ea4  lea     rax, [rbp+9B0h+var_958]
0x180073ea8  mov     [rbp+9B0h+var_A20.SecurityDescriptor], rax
0x180073eac  mov     [rbp+9B0h+var_A20.Attributes], 82h
0x180073eb3  mov     [rbp+9B0h+var_A20.SecurityQualityOfService], 0
0x180073ebb  mov     dword ptr [rsp+0AB0h+ReturnLength], 1
0x180073ec3  call    cs:__imp_NtCreateDirectoryObjectEx
0x180073eca  nop     dword ptr [rax+rax+00h]
0x180073ecf  mov     ebx, eax
0x180073ed1  test    eax, eax
0x180073ed3  js      loc_180074272
0x180073ed9  mov     rcx, [rsp+0AB0h+SourceHandle]; SourceHandle
0x180073ede  call    BasepSetKernelIntegrityLabel
0x180073ee3  mov     ebx, eax
0x180073ee5  test    eax, eax
0x180073ee7  js      loc_180074272
0x180073eed  mov     r8d, [rsp+0AB0h+var_A48]; int
0x180073ef2  lea     rax, [rbp+9B0h+var_9D8]
0x180073ef6  mov     edx, [rsp+0AB0h+TokenInformation]; int
0x180073efa  lea     r9, [rbp+9B0h+UnicodeString]; int
0x180073efe  mov     ecx, [rsp+0AB0h+var_A4C]; int
0x180073f02  mov     qword ptr [rsp+0AB0h+FileAttributes], rax; FileHandle
0x180073f07  mov     rax, [rbp+9B0h+FileHandle]
0x180073f0b  mov     [rsp+0AB0h+ReturnLength], rax; __int64
0x180073f10  call    BasepOpenShadowRpcControlDirectory
0x180073f15  mov     ebx, eax
0x180073f17  test    eax, eax
0x180073f19  js      loc_180074272
0x180073f1f  mov     r8, [r14]; Sid1
0x180073f22  lea     rax, [rbp+9B0h+var_8B8]
0x180073f29  mov     r9d, 7
0x180073f2f  mov     [rsp+0AB0h+ReturnLength], rax; PSECURITY_DESCRIPTOR
0x180073f34  mov     rdx, r12; Sid
0x180073f37  mov     rcx, r15; SecurityDescriptor
0x180073f3a  call    BasepBuildPackageSecurityDescriptor
0x180073f3f  mov     ebx, eax
0x180073f41  test    eax, eax
0x180073f43  js      loc_180074272
0x180073f49  lea     rdx, aRpcControl; "RPC Control"
0x180073f50  lea     rcx, [rbp+9B0h+var_928]; DestinationString
0x180073f57  call    cs:__imp_RtlInitUnicodeString
0x180073f5e  nop     dword ptr [rax+rax+00h]
0x180073f63  mov     rax, [rsp+0AB0h+SourceHandle]
0x180073f68  lea     r8, [rbp+9B0h+var_A20]
0x180073f6c  mov     r9, [rbp+9B0h+var_9D8]
0x180073f70  lea     rcx, [rbp+9B0h+var_9F0]
0x180073f74  mov     [rbp+9B0h+var_A20.RootDirectory], rax
0x180073f78  mov     edx, 0Fh
0x180073f7d  lea     rax, [rbp+9B0h+var_928]
0x180073f84  mov     [rbp+9B0h+var_A20.Length], 30h ; '0'
0x180073f8b  mov     [rbp+9B0h+var_A20.ObjectName], rax
0x180073f8f  lea     rax, [rbp+9B0h+var_8B8]
0x180073f96  mov     [rbp+9B0h+var_A20.SecurityDescriptor], rax
0x180073f9a  mov     [rbp+9B0h+var_A20.Attributes], 82h
  ... truncated ...
```
