# BaseRegOpenKeyInternal

- ea: `0x18005ebc0`
- end: `0x18005f89a`
- name: `BaseRegOpenKeyInternal`
- size: `3290`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, int, PHANDLE, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002d4b0`
- `0x18005e320`

## callees

- `0x18005ebc0`
- `0x18005f8a0`
- `0x18005fa00`
- `0x180060700`
- `0x180060db0`
- `0x180061910`
- `0x1800b33d8`
- `0x1800d1550`
- `0x1801369c9`
- `0x180139854`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18005f2e8`
- `ntdll!RtlFreeUnicodeString` at `0x18005f2e8`
- `ntdll!_wcsnicmp` at `0x18005f6f6`
- `ntdll!_wcsnicmp` at `0x18019b2ef`
- `ntdll!_wcsnicmp` at `0x18019b386`
- `ntdll!_wcsnicmp` at `0x18005f6f6`
- `ntdll!_wcsnicmp` at `0x18019b2ef`
- `ntdll!_wcsnicmp` at `0x18019b386`
- `ntdll!NtOpenKey` at `0x18005ee53`
- `ntdll!NtOpenKey` at `0x18005eec1`
- `ntdll!NtOpenKey` at `0x18005f2b2`
- `ntdll!NtOpenKey` at `0x18005f4bb`
- `ntdll!NtOpenKey` at `0x18005ee53`
- `ntdll!NtOpenKey` at `0x18005eec1`
- `ntdll!NtOpenKey` at `0x18005f2b2`
- `ntdll!NtOpenKey` at `0x18005f4bb`
- `ntdll!RtlNtStatusToDosError` at `0x18005ef18`
- `ntdll!RtlNtStatusToDosError` at `0x18005ef18`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f190`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f1b0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f206`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f228`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f246`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f394`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f3b6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f40f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f431`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f44f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f190`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f1b0`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f206`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f228`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f246`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f394`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f3b6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f40f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f431`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005f44f`
- `ntdll!NtClose` at `0x18005f523`
- `ntdll!NtClose` at `0x18005f53b`
- `ntdll!NtClose` at `0x18005f6ab`
- `ntdll!NtClose` at `0x18005f83a`
- `ntdll!NtClose` at `0x18005f523`
- `ntdll!NtClose` at `0x18005f53b`
- `ntdll!NtClose` at `0x18005f6ab`
- `ntdll!NtClose` at `0x18005f83a`
- `ntdll!NtQueryKey` at `0x18005efac`
- `ntdll!NtQueryKey` at `0x18005f829`
- `ntdll!NtQueryKey` at `0x18019b33f`
- `ntdll!NtQueryKey` at `0x18005efac`
- `ntdll!NtQueryKey` at `0x18005f829`
- `ntdll!NtQueryKey` at `0x18019b33f`
- `ntdll!RtlFreeHeap` at `0x18005edb2`
- `ntdll!RtlFreeHeap` at `0x18005f2d4`
- `ntdll!RtlFreeHeap` at `0x18005f4dd`
- `ntdll!RtlFreeHeap` at `0x18005f4fb`
- `ntdll!RtlFreeHeap` at `0x18005f560`
- `ntdll!RtlFreeHeap` at `0x18005f626`
- `ntdll!RtlFreeHeap` at `0x18005f649`
- `ntdll!RtlFreeHeap` at `0x18005f78d`
- `ntdll!RtlFreeHeap` at `0x18005edb2`
- `ntdll!RtlFreeHeap` at `0x18005f2d4`
- `ntdll!RtlFreeHeap` at `0x18005f4dd`
- `ntdll!RtlFreeHeap` at `0x18005f4fb`
- `ntdll!RtlFreeHeap` at `0x18005f560`
- `ntdll!RtlFreeHeap` at `0x18005f626`
- `ntdll!RtlFreeHeap` at `0x18005f649`
- `ntdll!RtlFreeHeap` at `0x18005f78d`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005efed`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f02b`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f066`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f0e6`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005efed`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f02b`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f066`
- `ntdll!RtlCompareUnicodeStrings` at `0x18005f0e6`
- `ntdll!RtlAllocateHeap` at `0x18005ef7a`
- `ntdll!RtlAllocateHeap` at `0x18005f15e`
- `ntdll!RtlAllocateHeap` at `0x18005f362`
- `ntdll!RtlAllocateHeap` at `0x18005ef7a`
- `ntdll!RtlAllocateHeap` at `0x18005f15e`
- `ntdll!RtlAllocateHeap` at `0x18005f362`
- `ntdll!NtOpenKeyEx` at `0x18005ed8a`
- `ntdll!NtOpenKeyEx` at `0x18005ed8a`
- `ntdll!NtSetInformationKey` at `0x18005f690`
- `ntdll!NtSetInformationKey` at `0x18005f690`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005f765`
- `ntdll!NtOpenKeyTransactedEx` at `0x18005f765`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvOpenRegEntry` at `0x18005f314`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvOpenRegEntry` at `0x18005f314`

## string_xrefs

- `0x18005efe6`: `\Registry\Machine\`
- `0x18005f024`: `\Registry\Machine\`
- `0x18005f05f`: `\Registry\User\`

## pseudocode

```c
ULONG __fastcall BaseRegOpenKeyInternal(
        HANDLE KeyHandle,
        UNICODE_STRING *Source,
        int a3,
        unsigned int a4,
        int a5,
        _QWORD *KeyHandlea,
        __int64 a7)
{
  HANDLE v10; // rsi
  UNICODE_STRING v11; // xmm6
  __int64 v12; // rbx
  USHORT v13; // ax
  int v14; // eax
  int KeySemantics; // ebx
  int v16; // r15d
  char v17; // al
  char v18; // al
  ULONG v20; // eax
  unsigned __int16 *Heap; // r15
  NTSTATUS CurrentUserSid; // ebx
  unsigned __int16 *v23; // rax
  void *v24; // rbx
  unsigned __int16 v25; // bx
  bool v26; // dl
  __int16 v27; // cx
  __int64 *v28; // r8
  USHORT v29; // bx
  WCHAR *v30; // rax
  __int16 v31; // ax
  USHORT v32; // bx
  WCHAR *v33; // rax
  int v34; // edx
  int v35; // eax
  __int64 v36; // rcx
  unsigned __int64 v37; // rax
  unsigned __int16 v38[2]; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG Length; // [rsp+44h] [rbp-2B4h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-2A0h] BYREF
  PVOID P[2]; // [rsp+60h] [rbp-298h] BYREF
  struct _OBJECT_ATTRIBUTES v43; // [rsp+70h] [rbp-288h] BYREF
  ULONG v44; // [rsp+A0h] [rbp-258h] BYREF
  ULONG ResultLength; // [rsp+A4h] [rbp-254h] BYREF
  struct _OBJECT_ATTRIBUTES v46; // [rsp+A8h] [rbp-250h] BYREF
  __int64 v47; // [rsp+D8h] [rbp-220h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-218h] BYREF
  _BYTE v49[400]; // [rsp+110h] [rbp-1E8h] BYREF

  v10 = KeyHandle;
  v47 = a7;
  memset(&v46, 0, 44);
  if ( !Source || Source->Length < 2u || (Source->Length & 1) != 0 || !Source->Buffer || (v11 = *Source, !KeyHandlea) )
  {
    KeySemantics = -1073741811;
    return RtlNtStatusToDosError(KeySemantics);
  }
  v12 = 0;
  *KeyHandlea = 0;
  v13 = Source->Length - 2;
  Source->Length = v13;
  v46.Length = 48;
  v46.RootDirectory = KeyHandle;
  if ( (a3 & 8) != 0 )
    v46.Attributes = 320;
  else
    v46.Attributes = 64;
  v46.ObjectName = Source;
  *(_OWORD *)&v46.SecurityDescriptor = 0;
  if ( ((unsigned __int8)KeyHandle & 2) != 0 )
    goto LABEL_84;
  if ( (g_RegKrnGlobalState & 2) != 0 )
  {
    v44 = 0;
    if ( v13 >= 0xEu )
    {
      if ( !_wcsnicmp(Source->Buffer, L"Classes\\", 7u) && (Source->Length <= 0xEu || Source->Buffer[7] == 92)
        || Source->Length >= 0x20u
        && !_wcsnicmp(Source->Buffer, L"Software\\Classes\\", 0x10u)
        && ((v12 = 1, Source->Length <= 0x20u) || Source->Buffer[16] == 92) )
      {
        if ( NtQueryKey(v10, KeyNameInformation, &dword_1803A6988, 0x3Eu, &v44) >= 0
          && dword_1803A6988 == (unsigned __int16)word_1802E58F0[v12]
          && !_wcsnicmp(&word_1803A698C, off_180282310[v12], (unsigned __int16)word_1802E58F8[v12])
          && (::Handle || !(unsigned int)OpenClassesRootInternal(v36, 0x2000000, &::Handle, a7)) )
        {
          v37 = (unsigned __int16)word_1802E58F4[v12];
          if ( Source->Length > (unsigned __int16)v37 )
          {
            Source->Length -= v37;
            Source->MaximumLength -= v37;
            Source->Buffer += v37 >> 1;
          }
          else
          {
            Source->Length = 0;
          }
          v10 = ::Handle;
LABEL_84:
          memset_0(v49, 0, 0x182u);
          *(_QWORD *)(&ObjectAttributes.Length + 1) = 0;
          ObjectAttributes.ObjectName = (PUNICODE_STRING)v49;
          HIDWORD(ObjectAttributes.RootDirectory) = 386;
          ObjectAttributes.Length = 0;
          KeySemantics = BaseRegGetKeySemantics(v10, Source);
          if ( KeySemantics >= 0 )
          {
            KeySemantics = BaseRegOpenClassKeyFromLocation(&ObjectAttributes, v10, Source, a4, 3, a3, KeyHandlea, a7);
            if ( (ObjectAttributes.Length & 0x20) != 0 )
              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, ObjectAttributes.ObjectName);
          }
          goto LABEL_19;
        }
      }
    }
  }
  memset(&ObjectAttributes, 0, 40);
  ResultLength = 0;
  P[0] = 0;
  Length = 0;
  *(_QWORD *)&Destination.Length = 0;
  LOWORD(Destination.Buffer) = 0;
  BYTE2(Destination.Buffer) = 0;
  Handle = 0;
  LOBYTE(v38[0]) = 0;
  v43 = v46;
  v14 = ConstructKernelKeyPath(
          a4,
          (unsigned int)&v43,
          (unsigned int)&Length,
          (unsigned int)&Destination,
          (__int64)v38,
          (__int64)P);
  KeySemantics = v14;
  if ( a7 )
  {
    if ( v14 < 0 )
      goto LABEL_18;
    v16 = NtOpenKeyTransactedEx(&Handle, a4, &v43, a3 & 0x1C, a7);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( v16 < 0 )
      goto LABEL_17;
    if ( !LOBYTE(v38[0]) )
      goto LABEL_16;
    goto LABEL_89;
  }
  if ( v14 >= 0 )
  {
    v16 = NtOpenKeyEx(&Handle, a4, &v43, a3 & 0x1C);
    if ( P[0] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( v16 < 0 )
      goto LABEL_17;
    if ( !LOBYTE(v38[0]) )
    {
LABEL_16:
      *KeyHandlea = Handle;
LABEL_17:
      KeySemantics = v16;
      goto LABEL_18;
    }
LABEL_89:
    if ( Length )
    {
      Length &= 0xF01u;
      KeySemantics = NtSetInformationKey(Handle, KeySetHandleTagsInformation, &Length, 4u);
      if ( KeySemantics < 0 )
      {
        NtClose(Handle);
        goto LABEL_18;
      }
    }
    goto LABEL_16;
  }
LABEL_18:
  if ( KeySemantics == 1073741846 )
  {
    KeySemantics = NtQueryKey((HANDLE)*KeyHandlea, KeyCachedInformation, &ObjectAttributes, 0x28u, &ResultLength);
    NtClose((HANDLE)*KeyHandlea);
    if ( KeySemantics >= 0 )
      *KeyHandlea = SHIDWORD(ObjectAttributes.ObjectName);
  }
LABEL_19:
  if ( KeySemantics == -1073741772 )
  {
    if ( byte_1803A990A )
    {
      v18 = byte_1803A9909;
    }
    else
    {
      P[0] = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&stru_1801A5BA8;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(P, 0x80000100, &ObjectAttributes) >= 0 )
      {
        NtClose(P[0]);
        v17 = 1;
      }
      else
      {
        v17 = 0;
      }
      byte_1803A9908 = v17;
      P[0] = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&stru_1801A5BB8;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(P, 0x80000100, &ObjectAttributes) >= 0 )
      {
        NtClose(P[0]);
        v18 = 1;
      }
      else
      {
        v18 = 0;
      }
      byte_1803A9909 = v18;
      byte_1803A990A = 1;
    }
    if ( byte_1803A9908 || v18 )
    {
      Destination = 0;
      v20 = 256;
      for ( Length = 256; ; v20 = Length )
      {
        Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
        if ( !Heap )
        {
          CurrentUserSid = -1073741670;
          goto LABEL_77;
        }
        CurrentUserSid = NtQueryKey(v10, KeyNameInformation, Heap, Length, &Length);
        if ( CurrentUserSid >= 0 )
          break;
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
        if ( CurrentUserSid != -1073741789 && CurrentUserSid != -2147483643 )
          goto LABEL_77;
      }
      v23 = Heap + 2;
      v24 = (void *)*Heap;
      Handle = v24;
      if ( v24 != (void *)34 )
        goto LABEL_41;
      if ( !(unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\Machine\\", 17, Heap + 2) )
        goto LABEL_65;
      v23 = Heap + 2;
LABEL_41:
      if ( (unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\Machine\\", 18, v23) )
      {
        if ( !(unsigned int)RtlCompareUnicodeStrings(L"\\Registry\\User\\", 15, Heap + 2) && byte_1803A9909 )
        {
          *(_OWORD *)&ObjectAttributes.Length = 0;
          CurrentUserSid = DaxLookasideGetCurrentUserSid((PUNICODE_STRING)&ObjectAttributes);
          if ( CurrentUserSid >= 0 )
          {
            v25 = (unsigned __int16)Handle;
            if ( (unsigned __int64)Handle < (unsigned __int64)((unsigned int)LOWORD(ObjectAttributes.Length) + 30) + 16 )
            {
              v26 = 0;
            }
            else
            {
              v26 = (unsigned int)RtlCompareUnicodeStrings(
                                    L"_Classes",
                                    8,
                                    &Heap[((unsigned __int64)((unsigned int)LOWORD(ObjectAttributes.Length) + 30) >> 1)
                                        + 2]) == 0;
              if ( v26 )
              {
                v27 = 140;
                goto LABEL_48;
              }
            }
            v27 = 122;
LABEL_48:
            v28 = &qword_1801A5D00;
            if ( !v26 )
              v28 = (__int64 *)&stru_1801A5BD8;
            P[0] = v28;
            v38[0] = LOWORD(ObjectAttributes.Length) + 32;
            if ( v25 > (unsigned __int16)(LOWORD(ObjectAttributes.Length) + 32) )
              v27 = v25 + v27 - (LOWORD(ObjectAttributes.Length) + 32) + 2;
            v29 = Source->Length + v27 + 2;
            v30 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
            if ( v30 )
            {
              Destination.Buffer = v30;
              Destination.Length = 0;
              Destination.MaximumLength = v29;
              CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_1801A5BB8);
              if ( CurrentUserSid >= 0 )
              {
                CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)P[0]);
                if ( CurrentUserSid >= 0 )
                {
                  if ( (unsigned __int16)Handle <= v38[0]
                    || (HIWORD(P[0]) = 0,
                        LOWORD(P[0]) = (_WORD)Handle - v38[0],
                        *(_DWORD *)((char *)P + 2) = (unsigned __int16)((_WORD)Handle - v38[0]),
                        P[1] = &Heap[((unsigned __int64)v38[0] >> 1) + 2],
                        CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)P),
                        CurrentUserSid >= 0)
                    && (CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_1801A5BD8),
                        CurrentUserSid >= 0) )
                  {
                    CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, Source);
                    if ( CurrentUserSid >= 0 )
                    {
                      Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
                      *(_QWORD *)&v43.Length = 48;
                      *(_QWORD *)&v43.Attributes = 64;
                      v43.RootDirectory = 0;
                      v43.ObjectName = &Destination;
                      *(_OWORD *)&v43.SecurityDescriptor = 0;
                      CurrentUserSid = NtOpenKey((PHANDLE)KeyHandlea, 0x80000100, &v43);
                      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
                    }
                  }
                }
              }
            }
            else
            {
              CurrentUserSid = -1073741670;
            }
            RtlFreeUnicodeString((PUNICODE_STRING)&ObjectAttributes);
          }
LABEL_76:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
LABEL_77:
          if ( CurrentUserSid >= 0 )
          {
            KeySemantics = 0;
            goto LABEL_29;
          }
LABEL_83:
          KeySemantics = -1073741772;
          goto LABEL_29;
        }
      }
      else
      {
LABEL_65:
        if ( byte_1803A9908 )
        {
          v31 = 128;
          if ( (unsigned int)v24 > 0x24 )
            v31 = (_WORD)v24 + 94;
          v32 = Source->Length + v31 + 2;
          v33 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v32);
          if ( v33 )
          {
            Destination.Buffer = v33;
            Destination.Length = 0;
            Destination.MaximumLength = v32;
            CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_1801A5BA8);
            if ( CurrentUserSid >= 0 )
            {
              CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_1801A5BD8);
              if ( CurrentUserSid >= 0 )
              {
                if ( (unsigned __int16)Handle <= 0x24u
                  || (*((_WORD *)&ObjectAttributes.Length + 3) = 0,
                      LOWORD(ObjectAttributes.Length) = (_WORD)Handle - 36,
                      *(ULONG *)((char *)&ObjectAttributes.Length + 2) = (unsigned __int16)((_WORD)Handle - 36),
                      ObjectAttributes.RootDirectory = Heap + 20,
                      CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)&ObjectAttributes),
                      CurrentUserSid >= 0)
                  && (CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, &stru_1801A5BD8), CurrentUserSid >= 0) )
                {
                  CurrentUserSid = RtlAppendUnicodeStringToString(&Destination, Source);
                  if ( CurrentUserSid >= 0 )
                  {
                    Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
                    *(_QWORD *)&v43.Length = 48;
                    *(_QWORD *)&v43.Attributes = 64;
                    v43.RootDirectory = 0;
                    v43.ObjectName = &Destination;
                    *(_OWORD *)&v43.SecurityDescriptor = 0;
                    CurrentUserSid = NtOpenKey((PHANDLE)KeyHandlea, 0x80000100, &v43);
                    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
                  }
                }
              }
            }
          }
          else
          {
            CurrentUserSid = -1073741670;
          }
          goto LABEL_76;
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      goto LABEL_83;
    }
    KeySemantics = -1073741772;
  }
LABEL_29:
  if ( KeySemantics == -1073741790 && (g_RegKrnGlobalState & 1) != 0 )
  {
    v34 = a4 & 0x1000300 | 0x2000000;
    if ( ((unsigned __int8)v10 & 2) != 0 )
      v35 = BaseRegOpenClassKey(v10, Source, (__int64)KeyHandlea, v47);
    else
      v35 = v47
          ? Wow64NtOpenKey((_DWORD)KeyHandlea, v34, (unsigned int)&v46, 0, v47)
          : Wow64NtOpenKey((_DWORD)KeyHandlea, v34, (unsigned int)&v46, 0, 0);
    KeySemantics = v35;
    if ( v35 < 0 )
      KeySemantics = -1073741790;
  }
  if ( ((unsigned __int8)v10 & 2) == 0
    && KeySemantics < 0
    && (unsigned __int8)IsTermsrvDeleteKeyPresent()
    && (unsigned int)TermsrvOpenRegEntry(KeyHandlea, a4, &v46) )
  {
    KeySemantics = 0;
  }
  *Source = v11;
  return RtlNtStatusToDosError(KeySemantics);
}

```

## disassembly

```asm
0x18005ebc0  push    rbx
0x18005ebc2  push    rsi
0x18005ebc3  push    rdi
0x18005ebc4  push    r12
0x18005ebc6  push    r13
0x18005ebc8  push    r14
0x18005ebca  push    r15
0x18005ebcc  sub     rsp, 2C0h
0x18005ebd3  movaps  [rsp+2F8h+var_48], xmm6
0x18005ebdb  mov     rax, cs:__security_cookie
0x18005ebe2  xor     rax, rsp
0x18005ebe5  mov     [rsp+2F8h+var_58], rax
0x18005ebed  mov     r13d, r9d
0x18005ebf0  mov     r12d, r8d
0x18005ebf3  mov     rdi, rdx
0x18005ebf6  mov     rsi, rcx
0x18005ebf9  mov     r14, [rsp+2F8h+KeyHandle]
0x18005ec01  mov     r15, [rsp+2F8h+arg_30]
0x18005ec09  mov     [rsp+2F8h+var_220], r15
0x18005ec11  xor     eax, eax
0x18005ec13  xorps   xmm0, xmm0
0x18005ec16  movups  [rsp+2F8h+var_250], xmm0
0x18005ec1e  movups  [rsp+2F8h+var_240], xmm0
0x18005ec26  movups  [rsp+2F8h+var_240+0Ch], xmm0
0x18005ec2e  test    rdx, rdx
0x18005ec31  jz      loc_18005EF50
0x18005ec37  movzx   eax, word ptr [rdx]
0x18005ec3a  cmp     ax, 2
0x18005ec3e  jb      loc_18005EF50
0x18005ec44  test    al, 1
0x18005ec46  jnz     loc_18005EF50
0x18005ec4c  cmp     qword ptr [rdx+8], 0
0x18005ec51  jz      loc_18005EF50
0x18005ec57  movups  xmm6, xmmword ptr [rdx]
0x18005ec5a  test    r14, r14
0x18005ec5d  jz      loc_18005EF50
0x18005ec63  xor     ebx, ebx
0x18005ec65  mov     [r14], rbx
0x18005ec68  jmp     short loc_18005EC71
0x18005ec6a  mov     ebx, eax
0x18005ec6c  jmp     loc_18005EF16
0x18005ec71  movzx   eax, word ptr [rdx]
0x18005ec74  sub     ax, 2
0x18005ec78  mov     [rdx], ax
0x18005ec7b  mov     dword ptr [rsp+2F8h+var_250], 30h ; '0'
0x18005ec86  mov     qword ptr [rsp+2F8h+var_250+8], rsi
0x18005ec8e  test    r12b, 8
0x18005ec92  jnz     loc_18005F734
0x18005ec98  mov     dword ptr [rsp+2F8h+var_240+8], 40h ; '@'
0x18005eca3  mov     qword ptr [rsp+2F8h+var_240], rdi
0x18005ecab  movdqu  [rsp+2F8h+var_230], xmm0
0x18005ecb4  test    sil, 2
0x18005ecb8  jnz     loc_18005F576
0x18005ecbe  test    byte ptr cs:g_RegKrnGlobalState, 2
0x18005ecc5  jnz     loc_18005F6D4
0x18005eccb  xorps   xmm0, xmm0
0x18005ecce  xor     eax, eax
0x18005ecd0  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.Length], xmm0
0x18005ecd8  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.ObjectName], xmm0
0x18005ece0  mov     [rsp+2F8h+ObjectAttributes.SecurityDescriptor], rax
0x18005ece8  mov     [rsp+2F8h+var_254], ebx
0x18005ecef  mov     [rsp+2F8h+P], rbx
0x18005ecf4  movups  xmm0, [rsp+2F8h+var_250]
0x18005ecfc  movups  xmm1, [rsp+2F8h+var_240]
0x18005ed04  mov     [rsp+2F8h+Length], ebx
0x18005ed08  mov     qword ptr [rsp+2F8h+Destination.Length], rax
0x18005ed0d  mov     word ptr [rsp+2F8h+Destination.Buffer], ax
0x18005ed12  mov     byte ptr [rsp+2F8h+Destination.Buffer+2], al
0x18005ed16  mov     [rsp+2F8h+Handle], rbx
0x18005ed1b  mov     byte ptr [rsp+2F8h+var_2B8], al
0x18005ed1f  lea     r9, [rsp+2F8h+Destination]
0x18005ed24  lea     r8, [rsp+2F8h+Length]
0x18005ed29  lea     rdx, [rsp+2F8h+var_288]
0x18005ed2e  mov     ecx, r13d
0x18005ed31  movups  xmmword ptr [rsp+2F8h+var_288.Length], xmm0
0x18005ed36  movups  xmmword ptr [rsp+2F8h+var_288.ObjectName], xmm1
0x18005ed3e  lea     rax, [rsp+2F8h+P]
0x18005ed43  movups  xmm0, [rsp+2F8h+var_230]
0x18005ed4b  mov     [rsp+2F8h+var_2D0], rax
0x18005ed50  movups  xmmword ptr [rsp+2F8h+var_288.SecurityDescriptor], xmm0
0x18005ed58  lea     rax, [rsp+2F8h+var_2B8]
0x18005ed5d  mov     [rsp+2F8h+ResultLength], rax
0x18005ed62  call    ConstructKernelKeyPath
0x18005ed67  mov     ebx, eax
0x18005ed69  test    r15, r15
0x18005ed6c  jnz     loc_18005F744
0x18005ed72  test    eax, eax
0x18005ed74  js      short loc_18005EDD9
0x18005ed76  mov     r9d, r12d
0x18005ed79  and     r9d, 1Ch
0x18005ed7d  lea     r8, [rsp+2F8h+var_288]
0x18005ed82  mov     edx, r13d
0x18005ed85  lea     rcx, [rsp+2F8h+Handle]
0x18005ed8a  call    cs:__imp_NtOpenKeyEx
0x18005ed91  nop     dword ptr [rax+rax+00h]
0x18005ed96  mov     r15d, eax
0x18005ed99  mov     r8, [rsp+2F8h+P]; P
0x18005ed9e  test    r8, r8
0x18005eda1  jz      short loc_18005EDBE
0x18005eda3  mov     rcx, gs:60h
0x18005edac  xor     edx, edx; Flags
0x18005edae  mov     rcx, [rcx+30h]; HeapHandle
0x18005edb2  call    cs:__imp_RtlFreeHeap
0x18005edb9  nop     dword ptr [rax+rax+00h]
0x18005edbe  test    r15d, r15d
0x18005edc1  js      short loc_18005EDD6
0x18005edc3  cmp     byte ptr [rsp+2F8h+var_2B8], 0
0x18005edc8  jnz     loc_18005F666
0x18005edce  mov     rax, [rsp+2F8h+Handle]
0x18005edd3  mov     [r14], rax
0x18005edd6  mov     ebx, r15d
0x18005edd9  cmp     ebx, 40000016h
0x18005eddf  jz      loc_18005F806
0x18005ede5  cmp     ebx, 0C0000034h
0x18005edeb  jnz     loc_18005EEF6
0x18005edf1  cmp     cs:byte_1803A990A, 0
0x18005edf8  jnz     loc_18005F512
0x18005edfe  xor     r15d, r15d
0x18005ee01  mov     [rsp+2F8h+P], r15
0x18005ee06  mov     qword ptr [rsp+2F8h+ObjectAttributes.Length], 30h ; '0'
0x18005ee12  mov     qword ptr [rsp+2F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18005ee1e  mov     [rsp+2F8h+ObjectAttributes.RootDirectory], r15
0x18005ee26  lea     rbx, stru_1801A5BA8
0x18005ee2d  mov     [rsp+2F8h+ObjectAttributes.ObjectName], rbx
0x18005ee35  xorps   xmm0, xmm0
0x18005ee38  movdqu  xmmword ptr [rsp+2F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005ee41  lea     r8, [rsp+2F8h+ObjectAttributes]; ObjectAttributes
0x18005ee49  mov     edx, 80000100h; DesiredAccess
0x18005ee4e  lea     rcx, [rsp+2F8h+P]; KeyHandle
0x18005ee53  call    cs:__imp_NtOpenKey
0x18005ee5a  nop     dword ptr [rax+rax+00h]
0x18005ee5f  test    eax, eax
0x18005ee61  jns     loc_18005F51E
0x18005ee67  xor     al, al
0x18005ee69  mov     cs:byte_1803A9908, al
0x18005ee6f  mov     [rsp+2F8h+P], r15
0x18005ee74  mov     qword ptr [rsp+2F8h+ObjectAttributes.Length], 30h ; '0'
0x18005ee80  mov     qword ptr [rsp+2F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18005ee8c  mov     [rsp+2F8h+ObjectAttributes.RootDirectory], r15
0x18005ee94  lea     rbx, stru_1801A5BB8
0x18005ee9b  mov     [rsp+2F8h+ObjectAttributes.ObjectName], rbx
0x18005eea3  xorps   xmm0, xmm0
0x18005eea6  movdqu  xmmword ptr [rsp+2F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005eeaf  lea     r8, [rsp+2F8h+ObjectAttributes]; ObjectAttributes
0x18005eeb7  mov     edx, 80000100h; DesiredAccess
0x18005eebc  lea     rcx, [rsp+2F8h+P]; KeyHandle
0x18005eec1  call    cs:__imp_NtOpenKey
0x18005eec8  nop     dword ptr [rax+rax+00h]
0x18005eecd  test    eax, eax
0x18005eecf  jns     loc_18005F536
0x18005eed5  xor     al, al
0x18005eed7  mov     cs:byte_1803A9909, al
0x18005eedd  mov     cs:byte_1803A990A, 1
0x18005eee4  cmp     cs:byte_1803A9908, 0
0x18005eeeb  jnz     short loc_18005EF57
0x18005eeed  test    al, al
0x18005eeef  jnz     short loc_18005EF57
0x18005eef1  mov     ebx, 0C0000034h
0x18005eef6  mov     r15d, 0C0000022h
0x18005eefc  cmp     ebx, r15d
0x18005eeff  jz      loc_18005F7B2
0x18005ef05  test    sil, 2
0x18005ef09  jnz     short loc_18005EF13
0x18005ef0b  test    ebx, ebx
0x18005ef0d  js      loc_18005F2F9
0x18005ef13  movups  xmmword ptr [rdi], xmm6
0x18005ef16  mov     ecx, ebx; Status
0x18005ef18  call    cs:__imp_RtlNtStatusToDosError
0x18005ef1f  nop     dword ptr [rax+rax+00h]
0x18005ef24  mov     rcx, [rsp+2F8h+var_58]
0x18005ef2c  xor     rcx, rsp; StackCookie
0x18005ef2f  call    __security_check_cookie
0x18005ef34  movaps  xmm6, [rsp+2F8h+var_48]
0x18005ef3c  add     rsp, 2C0h
0x18005ef43  pop     r15
0x18005ef45  pop     r14
0x18005ef47  pop     r13
0x18005ef49  pop     r12
0x18005ef4b  pop     rdi
0x18005ef4c  pop     rsi
0x18005ef4d  pop     rbx
0x18005ef4e  retn
0x18005ef50  mov     ebx, 0C000000Dh
0x18005ef55  jmp     short loc_18005EF16
0x18005ef57  xorps   xmm0, xmm0
0x18005ef5a  movups  xmmword ptr [rsp+2F8h+Destination.Length], xmm0
0x18005ef5f  mov     eax, 100h
0x18005ef64  mov     [rsp+2F8h+Length], eax
0x18005ef68  mov     r8d, eax; Size
0x18005ef6b  mov     rcx, gs:60h
0x18005ef74  xor     edx, edx; Flags
0x18005ef76  mov     rcx, [rcx+30h]; HeapHandle
0x18005ef7a  call    cs:__imp_RtlAllocateHeap
0x18005ef81  nop     dword ptr [rax+rax+00h]
0x18005ef86  mov     r15, rax
0x18005ef89  test    rax, rax
0x18005ef8c  jz      loc_18005F6BC
0x18005ef92  lea     rax, [rsp+2F8h+Length]
0x18005ef97  mov     [rsp+2F8h+ResultLength], rax; ResultLength
0x18005ef9c  mov     r9d, [rsp+2F8h+Length]; Length
0x18005efa1  mov     r8, r15; KeyInformation
0x18005efa4  mov     edx, 3; KeyInformationClass
0x18005efa9  mov     rcx, rsi; KeyHandle
0x18005efac  call    cs:__imp_NtQueryKey
0x18005efb3  nop     dword ptr [rax+rax+00h]
0x18005efb8  mov     ebx, eax
0x18005efba  test    eax, eax
0x18005efbc  js      loc_18005F637
0x18005efc2  lea     rax, [r15+4]
0x18005efc6  movzx   ebx, word ptr [r15]
0x18005efca  mov     [rsp+2F8h+Handle], rbx
0x18005efcf  cmp     rbx, 22h ; '"'
0x18005efd3  jnz     short loc_18005F005
0x18005efd5  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005efda  mov     r9d, 11h
0x18005efe0  mov     r8, rax
0x18005efe3  mov     edx, r9d
0x18005efe6  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\"
0x18005efed  call    cs:__imp_RtlCompareUnicodeStrings
0x18005eff4  nop     dword ptr [rax+rax+00h]
0x18005eff9  test    eax, eax
0x18005effb  jz      loc_18005F32C
0x18005f001  lea     rax, [r15+4]
0x18005f005  mov     r9, rbx
0x18005f008  mov     ecx, 24h ; '$'
0x18005f00d  cmp     rbx, rcx
0x18005f010  cmova   r9, rcx
0x18005f014  shr     r9, 1
0x18005f017  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005f01c  mov     r8, rax
0x18005f01f  mov     edx, 12h
0x18005f024  lea     rcx, aRegistryMachin_3; "\\Registry\\Machine\\"
0x18005f02b  call    cs:__imp_RtlCompareUnicodeStrings
0x18005f032  nop     dword ptr [rax+rax+00h]
0x18005f037  test    eax, eax
0x18005f039  jz      loc_18005F32C
0x18005f03f  mov     r9, rbx
0x18005f042  mov     eax, 1Eh
0x18005f047  cmp     rbx, rax
0x18005f04a  cmova   r9, rax
0x18005f04e  shr     r9, 1
0x18005f051  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005f056  lea     r8, [r15+4]
0x18005f05a  mov     edx, 0Fh
0x18005f05f  lea     rcx, aRegistryUser_0; "\\Registry\\User\\"
0x18005f066  call    cs:__imp_RtlCompareUnicodeStrings
0x18005f06d  nop     dword ptr [rax+rax+00h]
0x18005f072  test    eax, eax
0x18005f074  jnz     loc_18005F54E
0x18005f07a  cmp     cs:byte_1803A9909, al
0x18005f080  jz      loc_18005F54E
0x18005f086  xorps   xmm0, xmm0
0x18005f089  movups  xmmword ptr [rsp+2F8h+ObjectAttributes.Length], xmm0
0x18005f091  lea     rcx, [rsp+2F8h+ObjectAttributes]; UnicodeString
0x18005f099  call    DaxLookasideGetCurrentUserSid
0x18005f09e  mov     ebx, eax
0x18005f0a0  test    eax, eax
0x18005f0a2  js      loc_18005F4E9
0x18005f0a8  movzx   eax, word ptr [rsp+2F8h+ObjectAttributes.Length]
0x18005f0b0  add     eax, 1Eh
0x18005f0b3  mov     ecx, eax
0x18005f0b5  add     rax, 10h
0x18005f0b9  mov     rbx, [rsp+2F8h+Handle]
0x18005f0be  cmp     rbx, rax
0x18005f0c1  jb      loc_18005F728
0x18005f0c7  shr     rcx, 1
0x18005f0ca  add     rcx, 2
0x18005f0ce  lea     r8, [r15+rcx*2]
0x18005f0d2  mov     byte ptr [rsp+2F8h+ResultLength], 1
0x18005f0d7  mov     edx, 8
0x18005f0dc  mov     r9d, edx
0x18005f0df  lea     rcx, aClasses_0; "_Classes"
0x18005f0e6  call    cs:__imp_RtlCompareUnicodeStrings
0x18005f0ed  nop     dword ptr [rax+rax+00h]
0x18005f0f2  test    eax, eax
0x18005f0f4  jnz     loc_18005F868
0x18005f0fa  mov     dl, 1
0x18005f0fc  test    dl, dl
0x18005f0fe  jz      loc_18005F72A
0x18005f104  mov     ecx, 8Ch
0x18005f109  lea     rax, stru_1801A5BD8
0x18005f110  lea     r8, qword_1801A5D00
0x18005f117  test    dl, dl
0x18005f119  cmovz   r8, rax
0x18005f11d  mov     [rsp+2F8h+P], r8
0x18005f122  movzx   eax, word ptr [rsp+2F8h+ObjectAttributes.Length]
0x18005f12a  add     ax, 20h ; ' '
0x18005f12e  mov     [rsp+2F8h+var_2B8], ax
0x18005f133  cmp     bx, ax
0x18005f136  jbe     short loc_18005F142
0x18005f138  sub     cx, ax
0x18005f13b  add     cx, 2
0x18005f13f  add     cx, bx
0x18005f142  add     cx, 2
0x18005f146  add     cx, [rdi]
0x18005f149  movzx   ebx, cx
0x18005f14c  mov     r8d, ebx; Size
0x18005f14f  mov     rcx, gs:60h
0x18005f158  xor     edx, edx; Flags
0x18005f15a  mov     rcx, [rcx+30h]; HeapHandle
  ... truncated ...
```
