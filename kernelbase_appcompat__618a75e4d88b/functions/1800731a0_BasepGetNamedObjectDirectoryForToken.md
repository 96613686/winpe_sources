# BasepGetNamedObjectDirectoryForToken

- ea: `0x1800731a0`
- end: `0x180073a26`
- name: `BasepGetNamedObjectDirectoryForToken`
- size: `2182`
- prototype: `__int64 __usercall@<rax>(HANDLE TokenHandle@<rcx>, __int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800715e0`
- `0x180072e90`
- `0x1800ba520`
- `0x1800c1230`
- `0x180188c40`

## callees

- `0x1800731a0`
- `0x180074ac8`
- `0x1801369c9`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x18019bd55`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd6c`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd83`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd9a`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd55`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd6c`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd83`
- `ntdll!RtlSubAuthoritySid` at `0x18019bd9a`
- `ntdll!RtlFreeUnicodeString` at `0x1800733b6`
- `ntdll!RtlFreeUnicodeString` at `0x180073a15`
- `ntdll!RtlFreeUnicodeString` at `0x1800733b6`
- `ntdll!RtlFreeUnicodeString` at `0x180073a15`
- `ntdll!RtlInitUnicodeString` at `0x1800735cb`
- `ntdll!RtlInitUnicodeString` at `0x180073812`
- `ntdll!RtlInitUnicodeString` at `0x180073891`
- `ntdll!RtlInitUnicodeString` at `0x180073907`
- `ntdll!RtlInitUnicodeString` at `0x18019bde9`
- `ntdll!RtlInitUnicodeString` at `0x1800735cb`
- `ntdll!RtlInitUnicodeString` at `0x180073812`
- `ntdll!RtlInitUnicodeString` at `0x180073891`
- `ntdll!RtlInitUnicodeString` at `0x180073907`
- `ntdll!RtlInitUnicodeString` at `0x18019bde9`
- `ntdll!RtlLengthRequiredSid` at `0x1800735e1`
- `ntdll!RtlLengthRequiredSid` at `0x1800735e1`
- `ntdll!NtQueryInformationToken` at `0x180073282`
- `ntdll!NtQueryInformationToken` at `0x1800732b4`
- `ntdll!NtQueryInformationToken` at `0x1800732e3`
- `ntdll!NtQueryInformationToken` at `0x18007355d`
- `ntdll!NtQueryInformationToken` at `0x180073636`
- `ntdll!NtQueryInformationToken` at `0x18019bb79`
- `ntdll!NtQueryInformationToken` at `0x18019bca0`
- `ntdll!NtQueryInformationToken` at `0x180073282`
- `ntdll!NtQueryInformationToken` at `0x1800732b4`
- `ntdll!NtQueryInformationToken` at `0x1800732e3`
- `ntdll!NtQueryInformationToken` at `0x18007355d`
- `ntdll!NtQueryInformationToken` at `0x180073636`
- `ntdll!NtQueryInformationToken` at `0x18019bb79`
- `ntdll!NtQueryInformationToken` at `0x18019bca0`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800737a7`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18019bb9a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18019bd36`
- `ntdll!RtlConvertSidToUnicodeString` at `0x1800737a7`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18019bb9a`
- `ntdll!RtlConvertSidToUnicodeString` at `0x18019bd36`
- `ntdll!NtClose` at `0x1800733da`
- `ntdll!NtClose` at `0x18007386a`
- `ntdll!NtClose` at `0x180073963`
- `ntdll!NtClose` at `0x1800739ef`
- `ntdll!NtClose` at `0x18019bd07`
- `ntdll!NtClose` at `0x1800733da`
- `ntdll!NtClose` at `0x18007386a`
- `ntdll!NtClose` at `0x180073963`
- `ntdll!NtClose` at `0x1800739ef`
- `ntdll!NtClose` at `0x18019bd07`
- `ntdll!RtlFreeSid` at `0x180073a00`
- `ntdll!RtlFreeSid` at `0x180073a00`
- `ntdll!RtlGetAppContainerSidType` at `0x18007377c`
- `ntdll!RtlGetAppContainerSidType` at `0x18007377c`
- `ntdll!RtlGetAppContainerParent` at `0x18007399a`
- `ntdll!RtlGetAppContainerParent` at `0x18007399a`
- `ntdll!RtlFreeHeap` at `0x18007340a`
- `ntdll!RtlFreeHeap` at `0x18019bc50`
- `ntdll!RtlFreeHeap` at `0x18007340a`
- `ntdll!RtlFreeHeap` at `0x18019bc50`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180073313`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180073313`
- `ntdll!NtOpenDirectoryObject` at `0x180073528`
- `ntdll!NtOpenDirectoryObject` at `0x1800735a4`
- `ntdll!NtOpenDirectoryObject` at `0x180073753`
- `ntdll!NtOpenDirectoryObject` at `0x1800737ee`
- `ntdll!NtOpenDirectoryObject` at `0x180073857`
- `ntdll!NtOpenDirectoryObject` at `0x1800738d3`
- `ntdll!NtOpenDirectoryObject` at `0x180073945`
- `ntdll!NtOpenDirectoryObject` at `0x18019bcec`
- `ntdll!NtOpenDirectoryObject` at `0x18019be26`
- `ntdll!NtOpenDirectoryObject` at `0x180073528`
- `ntdll!NtOpenDirectoryObject` at `0x1800735a4`
- `ntdll!NtOpenDirectoryObject` at `0x180073753`
- `ntdll!NtOpenDirectoryObject` at `0x1800737ee`
- `ntdll!NtOpenDirectoryObject` at `0x180073857`
- `ntdll!NtOpenDirectoryObject` at `0x1800738d3`
- `ntdll!NtOpenDirectoryObject` at `0x180073945`
- `ntdll!NtOpenDirectoryObject` at `0x18019bcec`
- `ntdll!NtOpenDirectoryObject` at `0x18019be26`
- `ntdll!RtlAllocateHeap` at `0x180073602`
- `ntdll!RtlAllocateHeap` at `0x18019bc70`
- `ntdll!RtlAllocateHeap` at `0x180073602`
- `ntdll!RtlAllocateHeap` at `0x18019bc70`

## pseudocode

```c
__int64 __fastcall BasepGetNamedObjectDirectoryForToken(HANDLE TokenHandle, int a2, int a3, __int64 a4, _QWORD *a5)
{
  int v5; // esi
  _QWORD *Heap; // r12
  NTSTATUS AppContainerSidType; // ebx
  int v10; // eax
  int CurrentServiceSessionId; // eax
  int v12; // ecx
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  WCHAR *v16; // rax
  WCHAR *v17; // rcx
  struct _UNICODE_STRING *p_DestinationString; // rax
  HANDLE v20; // rax
  ULONG v21; // ebx
  NTSTATUS v22; // eax
  NTSTATUS v23; // eax
  NTSTATUS v24; // eax
  PULONG ReturnLength; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengtha; // [rsp+20h] [rbp-E0h]
  PULONG ReturnLengthb; // [rsp+20h] [rbp-E0h]
  ULONG v28; // [rsp+28h] [rbp-D8h]
  ULONG v29; // [rsp+30h] [rbp-D0h]
  ULONG v30; // [rsp+38h] [rbp-C8h]
  ULONG TokenInformationLength; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE v33; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  int TokenInformation; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-98h] BYREF
  HANDLE Handle; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+A8h] [rbp-58h] BYREF
  int v40; // [rsp+ACh] [rbp-54h] BYREF
  int v41; // [rsp+B0h] [rbp-50h]
  PSID Sid; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+C0h] [rbp-40h] BYREF
  struct _UNICODE_STRING v44; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v45; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING v46; // [rsp+E8h] [rbp-18h] BYREF
  PSID v47[12]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SourceString[256]; // [rsp+160h] [rbp+60h] BYREF
  PCWSTR v49; // [rsp+360h] [rbp+260h] BYREF
  char v50; // [rsp+368h] [rbp+268h]
  WCHAR v51[264]; // [rsp+480h] [rbp+380h] BYREF

  v45 = a5;
  v5 = a3;
  v41 = a3;
  v39 = 0;
  TokenInformationLength = 0;
  v40 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  UnicodeString = 0;
  memset_0(v51, 0, 0x208u);
  v46 = 0;
  v44 = 0;
  memset_0(SourceString, 0, sizeof(SourceString));
  TokenInformation = 0;
  v32 = 0;
  Handle = 0;
  v33 = 0;
  FileHandle = 0;
  Heap = 0;
  Sid = 0;
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenSessionId,
                          &TokenInformation,
                          4u,
                          &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  v39 = 0;
  AppContainerSidType = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v39, 4u, &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenIsRestricted|TokenGroups,
                          &v32,
                          4u,
                          &TokenInformationLength);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  v10 = v32;
  if ( v32 )
  {
    AppContainerSidType = NtQueryInformationToken(TokenHandle, TokenUser, v47, 0x54u, &TokenInformationLength);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    AppContainerSidType = RtlConvertSidToUnicodeString(&v44, v47[0], 1u);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    v10 = v32;
  }
  if ( v39 )
  {
    v21 = RtlLengthRequiredSid(0xCu) + 8;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
    if ( Heap )
    {
      v22 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, Heap, v21, &TokenInformationLength);
      AppContainerSidType = v22;
      if ( v22 >= 0 )
      {
LABEL_47:
        LODWORD(ReturnLengtha) = TokenInformation;
        AppContainerSidType = RtlStringCchPrintfW(
                                SourceString,
                                256,
                                L"%ws\\%ld\\AppContainerNamedObjects",
                                L"\\Sessions",
                                ReturnLengtha);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( a2 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
        }
        else
        {
          DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 2520);
          if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
            DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                             + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                             + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                             - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                         + 2536)
                                             - (unsigned __int64)NtCurrentPeb()[1].Ldr);
          else
            DestinationString.Buffer = 0;
        }
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        AppContainerSidType = NtOpenDirectoryObject(&Handle, 2u, &ObjectAttributes);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( v32 )
        {
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v44;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          AppContainerSidType = NtOpenDirectoryObject(&v33, 2u, &ObjectAttributes);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          NtClose(Handle);
          Handle = v33;
          v33 = 0;
        }
        AppContainerSidType = RtlGetAppContainerSidType(*Heap, &v40);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        if ( v40 == 2 )
        {
          AppContainerSidType = RtlConvertSidToUnicodeString(&UnicodeString, (PSID)*Heap, 1u);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &UnicodeString;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v23 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
        }
        else
        {
          AppContainerSidType = RtlGetAppContainerParent(*Heap, &Sid);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          v24 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
          AppContainerSidType = v24;
          if ( v24 < 0 )
            goto LABEL_18;
          v30 = *RtlSubAuthoritySid((PSID)*Heap, 0xBu);
          v29 = *RtlSubAuthoritySid((PSID)*Heap, 0xAu);
          v28 = *RtlSubAuthoritySid((PSID)*Heap, 9u);
          LODWORD(ReturnLengthb) = *RtlSubAuthoritySid((PSID)*Heap, 8u);
          AppContainerSidType = RtlStringCchPrintfW(
                                  v51,
                                  260,
                                  L"%s\\%u-%u-%u-%u",
                                  UnicodeString.Buffer,
                                  ReturnLengthb,
                                  v28,
                                  v29,
                                  v30);
          if ( AppContainerSidType < 0 )
            goto LABEL_18;
          RtlInitUnicodeString(&v46, v51);
          ObjectAttributes.RootDirectory = Handle;
          ObjectAttributes.Length = 48;
          ObjectAttributes.ObjectName = &v46;
          ObjectAttributes.Attributes = 64;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v23 = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
          v5 = v41;
        }
        AppContainerSidType = v23;
        goto LABEL_58;
      }
      if ( v22 != -1073741789 )
        goto LABEL_18;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, TokenInformationLength);
      if ( Heap )
      {
        AppContainerSidType = NtQueryInformationToken(
                                TokenHandle,
                                TokenAppContainerSid,
                                Heap,
                                TokenInformationLength,
                                &TokenInformationLength);
        if ( AppContainerSidType < 0 )
          goto LABEL_18;
        goto LABEL_47;
      }
    }
    AppContainerSidType = -1073741670;
    goto LABEL_18;
  }
  if ( v10 )
  {
    v12 = TokenInformation;
  }
  else
  {
    CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
    v12 = TokenInformation;
    if ( TokenInformation == CurrentServiceSessionId )
    {
      v13 = 2147483646;
      v14 = L"\\BaseNamedObjects";
      v15 = 256;
      v16 = SourceString;
      do
      {
        if ( !v13 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v13;
        --v15;
      }
      while ( v15 );
      v17 = v16 - 1;
      if ( v15 )
        v17 = v16;
      AppContainerSidType = v15 == 0 ? 0x80000005 : 0;
      *v17 = 0;
      goto LABEL_17;
    }
  }
  LODWORD(ReturnLength) = v12;
  AppContainerSidType = RtlStringCchPrintfW(
                          SourceString,
                          256,
                          L"%ws\\%ld\\BaseNamedObjects",
                          L"\\Sessions",
                          ReturnLength);
LABEL_17:
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  if ( v32 )
  {
    if ( a2 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
    }
    else
    {
      DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 2544);
      if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
        DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                         + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                         - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                     - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                     + 2536)
                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr);
      else
        DestinationString.Buffer = 0;
    }
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AppContainerSidType = NtOpenDirectoryObject(&Handle, 2u, &ObjectAttributes);
    if ( AppContainerSidType < 0 )
      goto LABEL_18;
    ObjectAttributes.RootDirectory = Handle;
    p_DestinationString = &v44;
  }
  else
  {
    if ( a2 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
    }
    else
    {
      DestinationString = *(struct _UNICODE_STRING *)(BaseStaticServerData + 32);
      if ( _mm_srli_si128((__m128i)DestinationString, 8).m128i_u64[0] )
        DestinationString.Buffer = (PWSTR)((char *)DestinationString.Buffer
                                         + (unsigned __int64)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                         + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                         - *(_QWORD *)((char *)NtCurrentPeb()->ReadOnlySharedMemoryBase
                                                     + *((_QWORD *)NtCurrentPeb()->ReadOnlyStaticServerData + 1)
                                                     - (unsigned __int64)NtCurrentPeb()[1].Ldr
                                                     + 2536)
                                         - (unsigned __int64)NtCurrentPeb()[1].Ldr);
      else
        DestinationString.Buffer = 0;
    }
    ObjectAttributes.RootDirectory = 0;
    p_DestinationString = &DestinationString;
  }
  ObjectAttributes.ObjectName = p_DestinationString;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  AppContainerSidType = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
  if ( AppContainerSidType >= 0 )
    goto LABEL_37;
  AppContainerSidType = NtOpenDirectoryObject(&v33, 2u, &ObjectAttributes);
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
  ObjectAttributes.RootDirectory = v33;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1801A5E28;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  AppContainerSidType = NtOpenDirectoryObject(&FileHandle, 0xFu, &ObjectAttributes);
  NtClose(v33);
  v33 = 0;
LABEL_58:
  if ( AppContainerSidType < 0 )
    goto LABEL_18;
LABEL_37:
  if ( !v5 )
  {
LABEL_40:
    v20 = FileHandle;
LABEL_41:
    FileHandle = 0;
    *v45 = v20;
    goto LABEL_18;
  }
  AppContainerSidType = NtQueryInformationToken(
                          TokenHandle,
                          TokenIsRestricted|TokenOwner,
                          &v49,
                          0x120u,
                          &TokenInformationLength);
  if ( AppContainerSidType >= 0 )
  {
    if ( !v50 )
      goto LABEL_40;
    RtlInitUnicodeString(&DestinationString, v49);
    ObjectAttributes.RootDirectory = FileHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    AppContainerSidType = NtOpenDirectoryObject(&v33, 0xFu, &ObjectAttributes);
    if ( AppContainerSidType >= 0 )
    {
      NtClose(FileHandle);
      v20 = v33;
      v33 = 0;
      goto LABEL_41;
    }
  }
LABEL_18:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( FileHandle )
    NtClose(FileHandle);
  if ( Handle )
    NtClose(Handle);
  if ( Sid )
    RtlFreeSid(Sid);
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( v44.Buffer )
    RtlFreeUnicodeString(&v44);
  return (unsigned int)AppContainerSidType;
}

```

## disassembly

```asm
0x1800731a0  push    rbp
0x1800731a2  push    rbx
0x1800731a3  push    rsi
0x1800731a4  push    rdi
0x1800731a5  push    r12
0x1800731a7  push    r13
0x1800731a9  push    r14
0x1800731ab  push    r15
0x1800731ad  lea     rbp, [rsp-5A8h]
0x1800731b5  sub     rsp, 6A8h
0x1800731bc  mov     rax, cs:__security_cookie
0x1800731c3  xor     rax, rsp
0x1800731c6  mov     [rbp+5E0h+var_50], rax
0x1800731cd  mov     rax, [rbp+5E0h+arg_20]
0x1800731d4  xorps   xmm0, xmm0
0x1800731d7  xor     r15d, r15d
0x1800731da  mov     [rbp+5E0h+var_600], rax
0x1800731de  mov     esi, r8d
0x1800731e1  mov     [rbp+5E0h+var_630], r8d
0x1800731e5  mov     edi, edx
0x1800731e7  mov     [rbp+5E0h+var_638], r15d
0x1800731eb  mov     r13, rcx
0x1800731ee  mov     [rsp+6E0h+TokenInformationLength], r15d
0x1800731f3  xorps   xmm1, xmm1
0x1800731f6  mov     [rbp+5E0h+var_634], r15d
0x1800731fa  movups  xmmword ptr [rbp+5E0h+ObjectAttributes.ObjectName], xmm0
0x1800731fe  xor     eax, eax
0x180073200  lea     rcx, [rbp+5E0h+var_260]; void *
0x180073207  xor     edx, edx; Val
0x180073209  mov     r8d, 208h; Size
0x18007320f  movups  xmmword ptr [rsp+6E0h+ObjectAttributes.Length], xmm0
0x180073214  movups  xmmword ptr [rbp+5E0h+ObjectAttributes+1Ch], xmm0
0x180073218  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x18007321d  movups  xmmword ptr [rbp+5E0h+UnicodeString.Length], xmm1
0x180073221  call    memset_0
0x180073226  xorps   xmm0, xmm0
0x180073229  lea     rcx, [rbp+5E0h+SourceString]; void *
0x18007322d  xorps   xmm1, xmm1
0x180073230  xor     edx, edx; Val
0x180073232  mov     r8d, 200h; Size
0x180073238  movups  xmmword ptr [rbp+5E0h+var_5F8.Length], xmm0
0x18007323c  movups  xmmword ptr [rbp+5E0h+var_610.Length], xmm1
0x180073240  call    memset_0
0x180073245  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18007324a  mov     [rsp+6E0h+TokenInformation], r15d
0x18007324f  lea     r14d, [r15+4]
0x180073253  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x180073258  mov     r9d, r14d; TokenInformationLength
0x18007325b  mov     [rsp+6E0h+var_69C], r15d
0x180073260  lea     r8, [rsp+6E0h+TokenInformation]; TokenInformation
0x180073265  mov     [rsp+6E0h+Handle], r15
0x18007326a  lea     edx, [r15+0Ch]; TokenInformationClass
0x18007326e  mov     [rsp+6E0h+var_698], r15
0x180073273  mov     rcx, r13; TokenHandle
0x180073276  mov     [rsp+6E0h+FileHandle], r15
0x18007327b  mov     r12d, r15d
0x18007327e  mov     [rbp+5E0h+Sid], r15
0x180073282  call    cs:__imp_NtQueryInformationToken
0x180073289  nop     dword ptr [rax+rax+00h]
0x18007328e  mov     ebx, eax
0x180073290  test    eax, eax
0x180073292  js      loc_1800733AC
0x180073298  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18007329d  mov     [rbp+5E0h+var_638], r15d
0x1800732a1  mov     r9d, r14d; TokenInformationLength
0x1800732a4  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x1800732a9  lea     r8, [rbp+5E0h+var_638]; TokenInformation
0x1800732ad  mov     rcx, r13; TokenHandle
0x1800732b0  lea     edx, [r15+1Dh]; TokenInformationClass
0x1800732b4  call    cs:__imp_NtQueryInformationToken
0x1800732bb  nop     dword ptr [rax+rax+00h]
0x1800732c0  mov     ebx, eax
0x1800732c2  test    eax, eax
0x1800732c4  js      loc_1800733AC
0x1800732ca  lea     rax, [rsp+6E0h+TokenInformationLength]
0x1800732cf  mov     r9d, r14d; TokenInformationLength
0x1800732d2  lea     r8, [rsp+6E0h+var_69C]; TokenInformation
0x1800732d7  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x1800732dc  lea     edx, [r15+2Ah]; TokenInformationClass
0x1800732e0  mov     rcx, r13; TokenHandle
0x1800732e3  call    cs:__imp_NtQueryInformationToken
0x1800732ea  nop     dword ptr [rax+rax+00h]
0x1800732ef  mov     ebx, eax
0x1800732f1  test    eax, eax
0x1800732f3  js      loc_1800733AC
0x1800732f9  mov     eax, [rsp+6E0h+var_69C]
0x1800732fd  test    eax, eax
0x1800732ff  jnz     loc_18019BB5E
0x180073305  cmp     [rbp+5E0h+var_638], r15d
0x180073309  jnz     loc_1800735DC
0x18007330f  test    eax, eax
0x180073311  jnz     short loc_18007337E
0x180073313  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18007331a  nop     dword ptr [rax+rax+00h]
0x18007331f  mov     ecx, [rsp+6E0h+TokenInformation]
0x180073323  cmp     ecx, eax
0x180073325  jnz     short loc_180073382
0x180073327  mov     ecx, 7FFFFFFEh
0x18007332c  lea     r8, aBasenamedobjec; "\\BaseNamedObjects"
0x180073333  mov     edx, 100h
0x180073338  lea     rax, [rbp+5E0h+SourceString]
0x18007333c  test    rcx, rcx
0x18007333f  jz      short loc_180073360
0x180073341  movzx   r9d, word ptr [r8]
0x180073345  test    r9w, r9w
0x180073349  jz      short loc_180073360
0x18007334b  mov     [rax], r9w
0x18007334f  add     r8, 2
0x180073353  add     rax, 2
0x180073357  dec     rcx
0x18007335a  sub     rdx, 1
0x18007335e  jnz     short loc_18007333C
0x180073360  test    rdx, rdx
0x180073363  lea     rcx, [rax-2]
0x180073367  cmovnz  rcx, rax
0x18007336b  neg     rdx
0x18007336e  sbb     ebx, ebx
0x180073370  not     ebx
0x180073372  and     ebx, 80000005h
0x180073378  mov     [rcx], r15w
0x18007337c  jmp     short loc_1800733A4
0x18007337e  mov     ecx, [rsp+6E0h+TokenInformation]
0x180073382  mov     dword ptr [rsp+6E0h+ReturnLength], ecx
0x180073386  lea     r9, aSessions; "\\Sessions"
0x18007338d  lea     rcx, [rbp+5E0h+SourceString]
0x180073391  mov     edx, 100h
0x180073396  lea     r8, aWsLdBasenamedo_0; "%ws\\%ld\\BaseNamedObjects"
0x18007339d  call    RtlStringCchPrintfW
0x1800733a2  mov     ebx, eax
0x1800733a4  test    ebx, ebx
0x1800733a6  jns     loc_180073446
0x1800733ac  cmp     [rbp+5E0h+UnicodeString.Buffer], r15
0x1800733b0  jz      short loc_1800733C2
0x1800733b2  lea     rcx, [rbp+5E0h+UnicodeString]; UnicodeString
0x1800733b6  call    cs:__imp_RtlFreeUnicodeString
0x1800733bd  nop     dword ptr [rax+rax+00h]
0x1800733c2  mov     rcx, [rsp+6E0h+FileHandle]; Handle
0x1800733c7  test    rcx, rcx
0x1800733ca  jnz     loc_1800739EF
0x1800733d0  mov     rcx, [rsp+6E0h+Handle]; Handle
0x1800733d5  test    rcx, rcx
0x1800733d8  jz      short loc_1800733E6
0x1800733da  call    cs:__imp_NtClose
0x1800733e1  nop     dword ptr [rax+rax+00h]
0x1800733e6  mov     rcx, [rbp+5E0h+Sid]; Sid
0x1800733ea  test    rcx, rcx
0x1800733ed  jnz     loc_180073A00
0x1800733f3  test    r12, r12
0x1800733f6  jz      short loc_180073416
0x1800733f8  mov     rcx, gs:60h
0x180073401  mov     r8, r12; P
0x180073404  xor     edx, edx; Flags
0x180073406  mov     rcx, [rcx+30h]; HeapHandle
0x18007340a  call    cs:__imp_RtlFreeHeap
0x180073411  nop     dword ptr [rax+rax+00h]
0x180073416  cmp     [rbp+5E0h+var_610.Buffer], r15
0x18007341a  jnz     loc_180073A11
0x180073420  mov     eax, ebx
0x180073422  mov     rcx, [rbp+5E0h+var_50]
0x180073429  xor     rcx, rsp; StackCookie
0x18007342c  call    __security_check_cookie
0x180073431  add     rsp, 6A8h
0x180073438  pop     r15
0x18007343a  pop     r14
0x18007343c  pop     r13
0x18007343e  pop     r12
0x180073440  pop     rdi
0x180073441  pop     rsi
0x180073442  pop     rbx
0x180073443  pop     rbp
0x180073444  retn
0x180073446  cmp     [rsp+6E0h+var_69C], r15d
0x18007344b  jnz     loc_180073880
0x180073451  test    edi, edi
0x180073453  jnz     loc_1800735C2
0x180073459  mov     rax, cs:BaseStaticServerData
0x180073460  movups  xmm0, xmmword ptr [rax+20h]
0x180073464  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x180073469  psrldq  xmm0, 8
0x18007346e  movq    rax, xmm0
0x180073473  test    rax, rax
0x180073476  jz      loc_180073988
0x18007347c  mov     rax, gs:60h
0x180073485  mov     rcx, [rax+98h]
0x18007348c  mov     rax, gs:60h
0x180073495  mov     r8, [rcx+8]
0x180073499  sub     r8, [rax+380h]
0x1800734a0  mov     rax, gs:60h
0x1800734a9  mov     rdx, [rax+88h]
0x1800734b0  mov     rax, gs:60h
0x1800734b9  mov     rcx, [rax+98h]
0x1800734c0  mov     rax, gs:60h
0x1800734c9  mov     r9, [rcx+8]
0x1800734cd  sub     r9, [r8+rdx+9E8h]
0x1800734d5  sub     r9, [rax+380h]
0x1800734dc  mov     rax, gs:60h
0x1800734e5  add     r9, [rax+88h]
0x1800734ec  add     [rsp+6E0h+DestinationString.Buffer], r9
0x1800734f1  mov     r14d, 30h ; '0'
0x1800734f7  mov     [rbp+5E0h+ObjectAttributes.RootDirectory], r15
0x1800734fb  lea     rax, [rsp+6E0h+DestinationString]
0x180073500  lea     r15d, [r14+10h]
0x180073504  xorps   xmm0, xmm0
0x180073507  mov     [rbp+5E0h+ObjectAttributes.ObjectName], rax
0x18007350b  lea     r8, [rsp+6E0h+ObjectAttributes]; ObjectAttributes
0x180073510  mov     [rbp+5E0h+ObjectAttributes.Attributes], r15d
0x180073514  mov     edx, 0Fh; DesiredAccess
0x180073519  mov     [rsp+6E0h+ObjectAttributes.Length], r14d
0x18007351e  lea     rcx, [rsp+6E0h+FileHandle]; FileHandle
0x180073523  movdqu  xmmword ptr [rbp+5E0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180073528  call    cs:__imp_NtOpenDirectoryObject
0x18007352f  nop     dword ptr [rax+rax+00h]
0x180073534  mov     ebx, eax
0x180073536  test    eax, eax
0x180073538  js      short loc_180073595
0x18007353a  test    esi, esi
0x18007353c  jz      short loc_18007357C
0x18007353e  lea     rax, [rsp+6E0h+TokenInformationLength]
0x180073543  mov     r9d, 120h; TokenInformationLength
0x180073549  lea     r8, [rbp+5E0h+var_380]; TokenInformation
0x180073550  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x180073555  mov     edx, 2Ch ; ','; TokenInformationClass
0x18007355a  mov     rcx, r13; TokenHandle
0x18007355d  call    cs:__imp_NtQueryInformationToken
0x180073564  nop     dword ptr [rax+rax+00h]
0x180073569  mov     ebx, eax
0x18007356b  test    eax, eax
0x18007356d  js      short loc_1800735BA
0x18007356f  cmp     [rbp+5E0h+var_378], 0
0x180073576  jnz     loc_1800738FB
0x18007357c  mov     rax, [rsp+6E0h+FileHandle]
0x180073581  xor     r15d, r15d
0x180073584  mov     rcx, [rbp+5E0h+var_600]
0x180073588  mov     [rsp+6E0h+FileHandle], r15
0x18007358d  mov     [rcx], rax
0x180073590  jmp     loc_1800733AC
0x180073595  lea     r8, [rsp+6E0h+ObjectAttributes]; ObjectAttributes
0x18007359a  mov     edx, 2; DesiredAccess
0x18007359f  lea     rcx, [rsp+6E0h+var_698]; FileHandle
0x1800735a4  call    cs:__imp_NtOpenDirectoryObject
0x1800735ab  nop     dword ptr [rax+rax+00h]
0x1800735b0  mov     ebx, eax
0x1800735b2  test    eax, eax
0x1800735b4  jns     loc_180073823
0x1800735ba  xor     r15d, r15d
0x1800735bd  jmp     loc_1800733AC
0x1800735c2  lea     rdx, [rbp+5E0h+SourceString]; SourceString
0x1800735c6  lea     rcx, [rsp+6E0h+DestinationString]; DestinationString
0x1800735cb  call    cs:__imp_RtlInitUnicodeString
0x1800735d2  nop     dword ptr [rax+rax+00h]
0x1800735d7  jmp     loc_1800734F1
0x1800735dc  mov     ecx, 0Ch; SubAuthorityCount
0x1800735e1  call    cs:__imp_RtlLengthRequiredSid
0x1800735e8  nop     dword ptr [rax+rax+00h]
0x1800735ed  mov     rcx, gs:60h
0x1800735f6  xor     edx, edx; Flags
0x1800735f8  lea     ebx, [rax+8]
0x1800735fb  mov     rcx, [rcx+30h]; HeapHandle
0x1800735ff  mov     r8d, ebx; Size
0x180073602  call    cs:__imp_RtlAllocateHeap
0x180073609  nop     dword ptr [rax+rax+00h]
0x18007360e  mov     r12, rax
0x180073611  test    rax, rax
0x180073614  jz      loc_1800739E5
0x18007361a  lea     rax, [rsp+6E0h+TokenInformationLength]
0x18007361f  mov     r14d, 1Fh
0x180073625  mov     edx, r14d; TokenInformationClass
0x180073628  mov     [rsp+6E0h+ReturnLength], rax; ReturnLength
0x18007362d  mov     r9d, ebx; TokenInformationLength
0x180073630  mov     r8, r12; TokenInformation
0x180073633  mov     rcx, r13; TokenHandle
0x180073636  call    cs:__imp_NtQueryInformationToken
0x18007363d  nop     dword ptr [rax+rax+00h]
0x180073642  mov     ebx, eax
0x180073644  test    eax, eax
0x180073646  js      loc_18019BC33
0x18007364c  mov     eax, [rsp+6E0h+TokenInformation]
0x180073650  lea     r9, aSessions; "\\Sessions"
0x180073657  lea     r8, aWsLdAppcontain_1; "%ws\\%ld\\AppContainerNamedObjects"
0x18007365e  mov     dword ptr [rsp+6E0h+ReturnLength], eax
0x180073662  mov     edx, 100h
0x180073667  lea     rcx, [rbp+5E0h+SourceString]
0x18007366b  call    RtlStringCchPrintfW
0x180073670  mov     ebx, eax
0x180073672  test    eax, eax
0x180073674  js      loc_1800733AC
0x18007367a  test    edi, edi
0x18007367c  jnz     loc_180073809
0x180073682  mov     rax, cs:BaseStaticServerData
0x180073689  movups  xmm0, xmmword ptr [rax+9D8h]
0x180073690  movups  xmmword ptr [rsp+6E0h+DestinationString.Length], xmm0
0x180073695  psrldq  xmm0, 8
0x18007369a  movq    rax, xmm0
0x18007369f  test    rax, rax
0x1800736a2  jz      loc_18007397E
0x1800736a8  mov     rax, gs:60h
0x1800736b1  mov     rcx, [rax+98h]
0x1800736b8  mov     rax, gs:60h
0x1800736c1  mov     r8, [rcx+8]
0x1800736c5  sub     r8, [rax+380h]
  ... truncated ...
```
