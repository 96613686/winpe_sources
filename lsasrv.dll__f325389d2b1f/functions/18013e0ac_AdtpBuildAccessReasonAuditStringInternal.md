# AdtpBuildAccessReasonAuditStringInternal

- ea: `0x18013e0ac`
- end: `0x18013ec2b`
- name: `AdtpBuildAccessReasonAuditStringInternal`
- size: `2943`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int, __int64, __int64, int, int, int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18013db10`

## callees

- `0x1800af2ec`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x18013cf40`
- `0x18013e0ac`
- `0x180140608`
- `0x180141514`
- `0x180141ccc`
- `0x180141f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013e6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013e6aa`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18013e639`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18013e639`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18013e65c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18013e65c`
- `ntdll!RtlFreeHeap` at `0x18013e803`
- `ntdll!RtlFreeHeap` at `0x18013e826`
- `ntdll!RtlFreeHeap` at `0x18013e92c`
- `ntdll!RtlFreeHeap` at `0x18013eb62`
- `ntdll!RtlFreeHeap` at `0x18013eb85`
- `ntdll!RtlFreeHeap` at `0x18013ebad`
- `ntdll!RtlFreeHeap` at `0x18013ebd2`
- `ntdll!RtlFreeHeap` at `0x18013ebf9`
- `ntdll!RtlFreeHeap` at `0x18013e803`
- `ntdll!RtlFreeHeap` at `0x18013e826`
- `ntdll!RtlFreeHeap` at `0x18013e92c`
- `ntdll!RtlFreeHeap` at `0x18013eb62`
- `ntdll!RtlFreeHeap` at `0x18013eb85`
- `ntdll!RtlFreeHeap` at `0x18013ebad`
- `ntdll!RtlFreeHeap` at `0x18013ebd2`
- `ntdll!RtlFreeHeap` at `0x18013ebf9`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18013e55a`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18013e55a`
- `ntdll!RtlIntegerToUnicodeString` at `0x18013ea59`
- `ntdll!RtlIntegerToUnicodeString` at `0x18013ea59`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e4fa`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e7c6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e8ee`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e903`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013ea78`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e4fa`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e7c6`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e8ee`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013e903`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18013ea78`
- `ntdll!RtlGetAce` at `0x18013e58b`
- `ntdll!RtlGetAce` at `0x18013e58b`
- `ntdll!RtlAddAce` at `0x18013e618`
- `ntdll!RtlAddAce` at `0x18013e618`
- `ntdll!RtlAllocateHeap` at `0x18013e4af`
- `ntdll!RtlAllocateHeap` at `0x18013e5c2`
- `ntdll!RtlAllocateHeap` at `0x18013e762`
- `ntdll!RtlAllocateHeap` at `0x18013e8a7`
- `ntdll!RtlAllocateHeap` at `0x18013ea0b`
- `ntdll!RtlAllocateHeap` at `0x18013eac6`
- `ntdll!RtlAllocateHeap` at `0x18013e4af`
- `ntdll!RtlAllocateHeap` at `0x18013e5c2`
- `ntdll!RtlAllocateHeap` at `0x18013e762`
- `ntdll!RtlAllocateHeap` at `0x18013e8a7`
- `ntdll!RtlAllocateHeap` at `0x18013ea0b`
- `ntdll!RtlAllocateHeap` at `0x18013eac6`
- `ntdll!RtlAppendUnicodeToString` at `0x18013e7da`
- `ntdll!RtlAppendUnicodeToString` at `0x18013ea42`
- `ntdll!RtlAppendUnicodeToString` at `0x18013ea90`
- `ntdll!RtlAppendUnicodeToString` at `0x18013e7da`
- `ntdll!RtlAppendUnicodeToString` at `0x18013ea42`
- `ntdll!RtlAppendUnicodeToString` at `0x18013ea90`
- `ntdll!RtlCreateAcl` at `0x18013e5e7`
- `ntdll!RtlCreateAcl` at `0x18013e5e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18013e68c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18013e68c`

## pseudocode

```c
__int64 __fastcall AdtpBuildAccessReasonAuditStringInternal(
        int a1,
        size_t a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        _WORD *a8,
        int a9,
        int a10,
        int a11,
        _BYTE *a12)
{
  struct _ACL *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // r15d
  int v17; // ecx
  NTSTATUS appended; // ebx
  int v19; // r13d
  int v20; // r15d
  int v21; // edi
  wchar_t v22; // ax
  __int64 v23; // rax
  __m128i v24; // xmm0
  __int16 v25; // bx
  struct _UNICODE_STRING *p_Source; // rdx
  const UNICODE_STRING *p_String; // rdx
  ULONG v28; // ebx
  const WCHAR *v29; // rbx
  DWORD LastError; // eax
  __int64 v31; // rsi
  __int64 v32; // rcx
  ULONG v33; // ecx
  __int16 v34; // si
  struct _UNICODE_STRING *v35; // rdx
  unsigned int v36; // ebx
  struct _UNICODE_STRING *v37; // rdx
  ULONG v38; // ebx
  unsigned int v39; // r14d
  __int16 v40; // si
  char *Heap; // rdi
  unsigned __int16 v42; // ax
  __int64 v43; // rcx
  __int16 v44; // si
  _WORD *v45; // rcx
  __int64 v47; // [rsp+30h] [rbp-D0h]
  unsigned __int8 DaclPresent; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 DaclDefaulted[7]; // [rsp+51h] [rbp-AFh] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  size_t pcchRemaining; // [rsp+68h] [rbp-98h] BYREF
  ULONG StringSecurityDescriptorLen; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING v54; // [rsp+80h] [rbp-80h] BYREF
  void *Src[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING v56; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v57; // [rsp+B0h] [rbp-50h]
  struct _UNICODE_STRING v58; // [rsp+B8h] [rbp-48h] BYREF
  UNICODE_STRING Source; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v60; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING v61; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING v62; // [rsp+F8h] [rbp-8h] BYREF
  UNICODE_STRING v63; // [rsp+108h] [rbp+8h] BYREF
  struct _UNICODE_STRING String; // [rsp+118h] [rbp+18h] BYREF
  _BYTE *v65; // [rsp+128h] [rbp+28h]
  _WORD *v66; // [rsp+130h] [rbp+30h]
  wchar_t pszFormat[8]; // [rsp+138h] [rbp+38h] BYREF
  wchar_t v68[8]; // [rsp+148h] [rbp+48h] BYREF
  int v69; // [rsp+158h] [rbp+58h]
  wchar_t pszDest[8]; // [rsp+168h] [rbp+68h] BYREF
  __int128 v71; // [rsp+178h] [rbp+78h]
  __int64 v72; // [rsp+188h] [rbp+88h]
  char v73; // [rsp+190h] [rbp+90h] BYREF
  char v74; // [rsp+1A8h] [rbp+A8h] BYREF
  char v75; // [rsp+1C8h] [rbp+C8h] BYREF
  char v76; // [rsp+1E8h] [rbp+E8h] BYREF
  char v77; // [rsp+208h] [rbp+108h] BYREF
  char v78; // [rsp+228h] [rbp+128h] BYREF
  char v79; // [rsp+248h] [rbp+148h] BYREF
  char v80; // [rsp+268h] [rbp+168h] BYREF

  v66 = a8;
  *(_QWORD *)pszFormat = a7;
  pcchRemaining = a2;
  v65 = a12;
  v14 = 0;
  v15 = 0;
  v57 = a4;
  DaclPresent = 0;
  v16 = 0;
  v56 = 0;
  StringSecurityDescriptor = 0;
  v17 = 1;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v58 = 0;
  Source = 0;
  String = 0;
  *(_OWORD *)Src = 0;
  Destination = 0;
  v54 = 0;
  while ( v15 < 0x20 )
  {
    if ( (v17 & a5) != 0 )
    {
      v16 = v15;
      break;
    }
    ++v15;
    v17 *= 2;
  }
  *(_DWORD *)&String.Length = 1310720;
  String.Buffer = (PWSTR)&v73;
  *(_DWORD *)&v56.Length = 1966080;
  v56.Buffer = (PWSTR)&v74;
  appended = AdtpFormatPrefix(&v56, 0x709u);
  if ( appended >= 0 )
  {
    *(_DWORD *)&v60.Length = 1966080;
    v60.Buffer = (PWSTR)&v75;
    appended = AdtpFormatPrefix(&v60, 0x70Au);
    if ( appended >= 0 )
    {
      *(_DWORD *)&v61.Length = 1966080;
      v61.Buffer = (PWSTR)&v76;
      appended = AdtpFormatPrefix(&v61, 0x713u);
      if ( appended >= 0 )
      {
        *(_DWORD *)&v62.Length = 1966080;
        v62.Buffer = (PWSTR)&v77;
        appended = AdtpFormatPrefix(&v62, 0x714u);
        if ( appended >= 0 )
        {
          *(_DWORD *)&v63.Length = 1966080;
          v63.Buffer = (PWSTR)&v78;
          appended = AdtpFormatPrefix(&v63, 0x712u);
          if ( appended >= 0 )
          {
            *(_DWORD *)&v58.Length = 1966080;
            v58.Buffer = (PWSTR)&v79;
            appended = AdtpFormatPrefix(&v58, 0x716u);
            if ( appended >= 0 )
            {
              *(_DWORD *)&Source.Length = 1966080;
              Source.Buffer = (PWSTR)&v80;
              appended = AdtpFormatPrefix(&Source, 0x718u);
              if ( appended >= 0 )
              {
                appended = AdtpBuildAccessesString(
                             a1,
                             pcchRemaining,
                             a5,
                             2,
                             (PUNICODE_STRING)Src,
                             0,
                             0,
                             0,
                             (__int64)&DaclPresent);
                if ( appended >= 0 )
                {
                  v19 = LOWORD(Src[0]) >> 1;
                  v20 = *(_DWORD *)(*(_QWORD *)pszFormat + 4LL * v16);
                  v21 = v20 & 0xFF0000;
                  if ( (v20 & 0xFF0000u) > 0x200000 )
                  {
                    if ( v21 != 3145728
                      && v21 != 0x400000
                      && v21 != 5242880
                      && v21 != 6291456
                      && v21 != 7340032
                      && v21 != 0x800000
                      && v21 != 9437184
                      && v21 != 10485760 )
                    {
LABEL_117:
                      appended = RtlAppendUnicodeToString(&Destination, L"\r\n\t\t\t\t");
                      v39 = v19 + (Destination.Length >> 1);
                      v40 = v39 + 1;
                      Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (v39 + 1));
                      if ( Heap )
                      {
                        *v65 = 1;
                        v42 = (unsigned __int16)Src[0];
                        if ( LOWORD(Src[0]) )
                        {
                          memcpy_0(Heap, Src[1], LOWORD(Src[0]));
                          v42 = (unsigned __int16)Src[0];
                        }
                        if ( Destination.Length )
                          memcpy_0(&Heap[v42], Destination.Buffer, Destination.Length);
                        v43 = v39;
                        v14 = 0;
                        v44 = 2 * v40;
                        *(_WORD *)&Heap[2 * v43] = 0;
                        v45 = v66;
                        *v66 = v44 - 2;
                        v45[1] = v44;
                        *((_QWORD *)v45 + 1) = Heap;
                      }
                      else
                      {
                        appended = -1073741801;
                        v14 = 0;
                      }
                      goto LABEL_124;
                    }
LABEL_92:
                    v38 = 1830;
                    if ( v21 != 458752 )
                      v38 = 0;
                    switch ( v21 )
                    {
                      case 3145728:
                        v38 = 1803;
                        break;
                      case 4194304:
                        v38 = 1804;
                        break;
                      case 5242880:
                        v38 = 1806;
                        break;
                      case 6291456:
                        v38 = 1807;
                        break;
                      case 7340032:
                        v38 = 1808;
                        break;
                      default:
                        if ( v21 )
                        {
                          switch ( v21 )
                          {
                            case 8388608:
                              v38 = 1805;
                              break;
                            case 9437184:
                              v38 = 1841;
                              break;
                            case 10485760:
                              v38 = 1856;
                              break;
                          }
                        }
                        else
                        {
                          v38 = 1809;
                        }
                        break;
                    }
                    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x4Eu);
                    if ( !Destination.Buffer )
                      goto LABEL_113;
                    *(_DWORD *)&Destination.Length = 5111808;
                    RtlAppendUnicodeToString(&Destination, L"%%");
                    appended = RtlIntegerToUnicodeString(v38, 0xAu, &String);
                    if ( appended < 0 )
                      goto LABEL_124;
                    p_String = &String;
LABEL_116:
                    RtlAppendUnicodeStringToString(&Destination, p_String);
                    goto LABEL_117;
                  }
                  if ( v21 == 0x200000 )
                  {
LABEL_77:
                    v69 = 0;
                    wcscpy(v68, L"\x01");
                    *(_DWORD *)&v68[2] = 1;
                    *(_DWORD *)&v68[4] = (unsigned __int16)v20;
                    *(_DWORD *)&v68[6] = 0;
                    appended = AdtpBuildPrivilegeAuditString(v68, &v54, 0, 0);
                    if ( appended < 0 )
                      goto LABEL_124;
                    v36 = (v54.Length >> 1) + 27;
                    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v36);
                    if ( Destination.Buffer )
                    {
                      Destination.Length = 0;
                      Destination.MaximumLength = 2 * v36;
                      if ( v21 == 0x200000 )
                        v37 = &v56;
                      else
                        v37 = &v63;
                      RtlAppendUnicodeStringToString(&Destination, v37);
                      RtlAppendUnicodeStringToString(&Destination, &v54);
                      if ( v54.Buffer )
                      {
                        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v54.Buffer);
                        v54.Buffer = 0;
                      }
                      goto LABEL_117;
                    }
                    goto LABEL_113;
                  }
                  if ( !v21 )
                    goto LABEL_92;
                  if ( v21 != 0x10000 && v21 != 0x20000 && v21 != 196608 && v21 != 0x40000 )
                  {
                    if ( v21 != 327680 && v21 != 393216 )
                    {
                      if ( v21 != 458752 )
                      {
                        if ( v21 != 0x100000 )
                          goto LABEL_117;
                        goto LABEL_77;
                      }
                      goto LABEL_92;
                    }
                    v22 = 2;
                    *(_DWORD *)&v68[2] = 0;
                    v68[0] = 2;
                    *(_QWORD *)&v68[4] = L"-";
                    wcscpy(pszFormat, L"# %d");
                    v68[1] = 2;
                    if ( v21 == 393216 )
                    {
                      if ( *(_DWORD *)(v57 + 8) )
                      {
                        if ( (unsigned int)(unsigned __int16)v20 >= *(_DWORD *)(v57 + 8) )
                          goto LABEL_29;
                        v23 = *(_QWORD *)(v57 + 16);
LABEL_34:
                        v24 = *(__m128i *)(v23 + 16LL * (unsigned __int16)v20);
                        v22 = _mm_cvtsi128_si32(v24);
                        *(__m128i *)v68 = v24;
                      }
                    }
                    else if ( *(_DWORD *)(a3 + 8) )
                    {
                      if ( (unsigned int)(unsigned __int16)v20 >= *(_DWORD *)(a3 + 8) )
                      {
LABEL_29:
                        appended = -1073741811;
                        goto LABEL_124;
                      }
                      v23 = *(_QWORD *)(a3 + 16);
                      goto LABEL_34;
                    }
                    if ( v22 <= 2u )
                    {
                      LODWORD(v47) = (unsigned __int16)v20;
                      pcchRemaining = 0;
                      if ( StringCchPrintfExW(pszDest, 0x14u, 0, &pcchRemaining, 0, pszFormat, v47) < 0 )
                      {
                        v22 = v68[0];
                      }
                      else
                      {
                        *(_QWORD *)&v68[4] = pszDest;
                        v68[1] = 40;
                        v22 = 2 * (20 - pcchRemaining);
                        v68[0] = v22;
                      }
                    }
                    v25 = v22 + 54;
                    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, (unsigned int)v22 + 54);
                    if ( !Destination.Buffer )
                      goto LABEL_113;
                    Destination.Length = 0;
                    Destination.MaximumLength = 2 * v25;
                    if ( v21 == 327680 )
                      p_Source = &v58;
                    else
                      p_Source = &Source;
                    RtlAppendUnicodeStringToString(&Destination, p_Source);
                    p_String = (const UNICODE_STRING *)v68;
                    goto LABEL_116;
                  }
                  *(_QWORD *)pszFormat = 0;
                  v72 = 0;
                  DaclPresent = 0;
                  DaclDefaulted[0] = 0;
                  pcchRemaining = 0;
                  *(_OWORD *)pszDest = 0;
                  if ( ((v21 - 0x10000) & 0xFFFEFFFF) != 0 )
                    a3 = v57;
                  v71 = 0;
                  StringSecurityDescriptorLen = 0;
                  appended = RtlGetDaclSecurityDescriptor(
                               *(PSECURITY_DESCRIPTOR *)a3,
                               &DaclPresent,
                               (PACL *)pszFormat,
                               DaclDefaulted);
                  if ( appended >= 0 )
                  {
                    if ( DaclPresent )
                    {
                      appended = RtlGetAce(*(PACL *)pszFormat, (unsigned __int16)v20, (PVOID *)&pcchRemaining);
                      if ( appended >= 0 )
                      {
                        v28 = *(unsigned __int16 *)(pcchRemaining + 2) + 8;
                        v14 = (struct _ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v28);
                        if ( v14 )
                        {
                          appended = RtlCreateAcl(v14, v28, (unsigned __int8)**(_BYTE **)pszFormat);
                          if ( appended < 0 )
                            goto LABEL_124;
                          appended = RtlAddAce(
                                       v14,
                                       (unsigned __int8)**(_BYTE **)pszFormat,
                                       0,
                                       (PVOID)pcchRemaining,
                                       *(unsigned __int16 *)(pcchRemaining + 2));
                          if ( appended < 0 )
                            goto LABEL_124;
                          appended = RtlCreateSecurityDescriptor(pszDest, 1u);
                          if ( appended < 0 )
                            goto LABEL_124;
                          appended = RtlSetDaclSecurityDescriptor(pszDest, 1u, v14, 0);
                          if ( appended < 0 )
                            goto LABEL_124;
                          if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(
                                 pszDest,
                                 1u,
                                 4u,
                                 &StringSecurityDescriptor,
                                 &StringSecurityDescriptorLen) )
                          {
                            v29 = StringSecurityDescriptor;
                          }
                          else
                          {
                            LastError = GetLastError();
                            if ( LastError == 8 )
                              goto LABEL_113;
                            v29 = v68;
                            if ( StringCchPrintfW(v68, 0x10u, L"<0x%08X>", LastError) < 0 )
                              v29 = L"-";
                          }
                          v31 = -1;
                          v32 = -1;
                          do
                            ++v32;
                          while ( v29[v32] );
                          v33 = v32 + 1;
                          StringSecurityDescriptorLen = v33;
                          if ( 2 * (unsigned __int64)v33 > 0xFFFF )
                          {
                            appended = RtlStringCbPrintfW(v68, 16, L"%%%%%u", 1828);
                            if ( appended < 0 )
                              goto LABEL_124;
                            v29 = v68;
                            do
                              ++v31;
                            while ( v68[v31] );
                            v33 = v31 + 1;
                            StringSecurityDescriptorLen = v31 + 1;
                          }
                          v34 = v33 + 27;
                          Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (v33 + 27));
                          if ( Destination.Buffer )
                          {
                            Destination.Length = 0;
                            Destination.MaximumLength = 2 * v34;
                            switch ( v21 )
                            {
                              case 65536:
                                v35 = &v56;
                                break;
                              case 131072:
                                v35 = &v60;
                                break;
                              case 196608:
                                v35 = &v61;
                                break;
                              default:
                                v35 = &v62;
                                break;
                            }
                            RtlAppendUnicodeStringToString(&Destination, v35);
                            RtlAppendUnicodeToString(&Destination, v29);
                            if ( StringSecurityDescriptor )
                            {
                              RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, StringSecurityDescriptor);
                              StringSecurityDescriptor = 0;
                            }
                            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
                            goto LABEL_117;
                          }
                        }
LABEL_113:
                        appended = -1073741801;
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
LABEL_124:
  if ( StringSecurityDescriptor )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, StringSecurityDescriptor);
  if ( v14 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  if ( v54.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v54.Buffer);
  if ( Src[1] )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Src[1]);
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18013e0ac  push    rbp
0x18013e0ae  push    rbx
0x18013e0af  push    rsi
0x18013e0b0  push    rdi
0x18013e0b1  push    r12
0x18013e0b3  push    r13
0x18013e0b5  push    r14
0x18013e0b7  push    r15
0x18013e0b9  lea     rbp, [rsp-198h]
0x18013e0c1  sub     rsp, 298h
0x18013e0c8  mov     rax, cs:__security_cookie
0x18013e0cf  xor     rax, rsp
0x18013e0d2  mov     [rbp+1D0h+var_48], rax
0x18013e0d9  mov     rax, [rbp+1D0h+arg_38]
0x18013e0e0  xorps   xmm0, xmm0
0x18013e0e3  mov     edi, [rbp+1D0h+arg_20]
0x18013e0e9  xorps   xmm1, xmm1
0x18013e0ec  mov     [rbp+1D0h+var_1A0], rax
0x18013e0f0  mov     r13, rcx
0x18013e0f3  mov     rax, [rbp+1D0h+arg_30]
0x18013e0fa  mov     r12, r8
0x18013e0fd  mov     qword ptr [rbp+1D0h+var_198], rax
0x18013e101  mov     rax, [rbp+1D0h+arg_58]
0x18013e108  mov     [rsp+2D0h+pcchRemaining], rdx
0x18013e10d  xor     edx, edx
0x18013e10f  mov     [rbp+1D0h+var_1A8], rax
0x18013e113  mov     r14d, edx
0x18013e116  mov     eax, edx
0x18013e118  mov     [rbp+1D0h+var_220], r9
0x18013e11c  mov     [rsp+2D0h+DaclPresent], dl
0x18013e120  mov     r15d, edx
0x18013e123  movups  xmmword ptr [rbp+1D0h+var_230.Length], xmm0
0x18013e127  mov     [rsp+2D0h+StringSecurityDescriptor], rdx
0x18013e12c  lea     ecx, [rdx+1]
0x18013e12f  movups  xmmword ptr [rbp+1D0h+var_1F8.Length], xmm1
0x18013e133  movups  xmmword ptr [rbp+1D0h+var_1E8.Length], xmm0
0x18013e137  movups  xmmword ptr [rbp+1D0h+var_1D8.Length], xmm1
0x18013e13b  movups  xmmword ptr [rbp+1D0h+var_1C8.Length], xmm0
0x18013e13f  movups  xmmword ptr [rbp+1D0h+var_218.Length], xmm1
0x18013e143  movups  xmmword ptr [rbp+1D0h+Source.Length], xmm0
0x18013e147  movups  xmmword ptr [rbp+1D0h+String.Length], xmm1
0x18013e14b  movups  xmmword ptr [rbp+1D0h+Src], xmm0
0x18013e14f  movups  xmmword ptr [rsp+2D0h+Destination.Length], xmm1
0x18013e154  movups  xmmword ptr [rbp+1D0h+var_250.Length], xmm0
0x18013e158  cmp     eax, 20h ; ' '
0x18013e15b  jnb     short loc_18013E16A
0x18013e15d  test    edi, ecx
0x18013e15f  jnz     short loc_18013E167
0x18013e161  inc     eax
0x18013e163  add     ecx, ecx
0x18013e165  jmp     short loc_18013E158
0x18013e167  mov     r15d, eax
0x18013e16a  lea     rax, [rbp+1D0h+var_140]
0x18013e171  mov     dword ptr [rbp+1D0h+String.Length], 140000h
0x18013e178  mov     [rbp+1D0h+String.Buffer], rax
0x18013e17c  lea     rcx, [rbp+1D0h+var_230]; Destination
0x18013e180  lea     rax, [rbp+1D0h+var_128]
0x18013e187  mov     dword ptr [rbp+1D0h+var_230.Length], 1E0000h
0x18013e18e  mov     r8b, 1
0x18013e191  mov     [rbp+1D0h+var_230.Buffer], rax
0x18013e195  mov     edx, 709h; Value
0x18013e19a  mov     esi, 14h
0x18013e19f  call    AdtpFormatPrefix
0x18013e1a4  mov     ebx, eax
0x18013e1a6  test    eax, eax
0x18013e1a8  js      loc_18013EB44
0x18013e1ae  lea     rax, [rbp+1D0h+var_108]
0x18013e1b5  mov     dword ptr [rbp+1D0h+var_1F8.Length], 1E0000h
0x18013e1bc  mov     r8b, 1
0x18013e1bf  mov     [rbp+1D0h+var_1F8.Buffer], rax
0x18013e1c3  mov     edx, 70Ah; Value
0x18013e1c8  lea     rcx, [rbp+1D0h+var_1F8]; Destination
0x18013e1cc  call    AdtpFormatPrefix
0x18013e1d1  mov     ebx, eax
0x18013e1d3  test    eax, eax
0x18013e1d5  js      loc_18013EB44
0x18013e1db  lea     rax, [rbp+1D0h+var_E8]
0x18013e1e2  mov     dword ptr [rbp+1D0h+var_1E8.Length], 1E0000h
0x18013e1e9  mov     r8b, 1
0x18013e1ec  mov     [rbp+1D0h+var_1E8.Buffer], rax
0x18013e1f0  mov     edx, 713h; Value
0x18013e1f5  lea     rcx, [rbp+1D0h+var_1E8]; Destination
0x18013e1f9  call    AdtpFormatPrefix
0x18013e1fe  mov     ebx, eax
0x18013e200  test    eax, eax
0x18013e202  js      loc_18013EB44
0x18013e208  lea     rax, [rbp+1D0h+var_C8]
0x18013e20f  mov     dword ptr [rbp+1D0h+var_1D8.Length], 1E0000h
0x18013e216  mov     r8b, 1
0x18013e219  mov     [rbp+1D0h+var_1D8.Buffer], rax
0x18013e21d  mov     edx, 714h; Value
0x18013e222  lea     rcx, [rbp+1D0h+var_1D8]; Destination
0x18013e226  call    AdtpFormatPrefix
0x18013e22b  mov     ebx, eax
0x18013e22d  test    eax, eax
0x18013e22f  js      loc_18013EB44
0x18013e235  lea     rax, [rbp+1D0h+var_A8]
0x18013e23c  mov     dword ptr [rbp+1D0h+var_1C8.Length], 1E0000h
0x18013e243  mov     r8b, 1
0x18013e246  mov     [rbp+1D0h+var_1C8.Buffer], rax
0x18013e24a  mov     edx, 712h; Value
0x18013e24f  lea     rcx, [rbp+1D0h+var_1C8]; Destination
0x18013e253  call    AdtpFormatPrefix
0x18013e258  mov     ebx, eax
0x18013e25a  test    eax, eax
0x18013e25c  js      loc_18013EB44
0x18013e262  lea     rax, [rbp+1D0h+var_88]
0x18013e269  mov     dword ptr [rbp+1D0h+var_218.Length], 1E0000h
0x18013e270  xor     r8d, r8d
0x18013e273  mov     [rbp+1D0h+var_218.Buffer], rax
0x18013e277  mov     edx, 716h; Value
0x18013e27c  lea     rcx, [rbp+1D0h+var_218]; Destination
0x18013e280  call    AdtpFormatPrefix
0x18013e285  mov     ebx, eax
0x18013e287  test    eax, eax
0x18013e289  js      loc_18013EB44
0x18013e28f  lea     rax, [rbp+1D0h+var_68]
0x18013e296  mov     dword ptr [rbp+1D0h+Source.Length], 1E0000h
0x18013e29d  xor     r8d, r8d
0x18013e2a0  mov     [rbp+1D0h+Source.Buffer], rax
0x18013e2a4  mov     edx, 718h; Value
0x18013e2a9  lea     rcx, [rbp+1D0h+Source]; Destination
0x18013e2ad  call    AdtpFormatPrefix
0x18013e2b2  mov     ebx, eax
0x18013e2b4  test    eax, eax
0x18013e2b6  js      loc_18013EB44
0x18013e2bc  mov     rdx, [rsp+2D0h+pcchRemaining]; int
0x18013e2c1  lea     rax, [rsp+2D0h+DaclPresent]
0x18013e2c6  mov     [rsp+2D0h+var_290], rax; __int64
0x18013e2cb  lea     r9d, [rsi-12h]; int
0x18013e2cf  xor     eax, eax
0x18013e2d1  mov     r8d, edi; int
0x18013e2d4  mov     [rsp+2D0h+var_298], rax; __int64
0x18013e2d9  mov     rcx, r13; int
0x18013e2dc  mov     [rsp+2D0h+var_2A0], rax; __int64
0x18013e2e1  mov     [rsp+2D0h+pszFormat], rax; __int64
0x18013e2e6  lea     rax, [rbp+1D0h+Src]
0x18013e2ea  mov     qword ptr [rsp+2D0h+dwFlags], rax; DestinationString
0x18013e2ef  call    AdtpBuildAccessesString
0x18013e2f4  mov     ebx, eax
0x18013e2f6  test    eax, eax
0x18013e2f8  js      loc_18013EB44
0x18013e2fe  movzx   r13d, word ptr [rbp+1D0h+Src]
0x18013e303  mov     edx, 300000h
0x18013e308  mov     eax, r15d
0x18013e30b  mov     ecx, 400000h
0x18013e310  mov     r15, qword ptr [rbp+1D0h+var_198]
0x18013e314  mov     r9d, 500000h
0x18013e31a  shr     r13d, 1
0x18013e31d  mov     r10d, 600000h
0x18013e323  mov     r11d, 700000h
0x18013e329  mov     r15d, [r15+rax*4]
0x18013e32d  mov     eax, 200000h
0x18013e332  mov     edi, r15d
0x18013e335  and     edi, 0FF0000h
0x18013e33b  cmp     edi, eax
0x18013e33d  ja      loc_18013E941
0x18013e343  jz      loc_18013E837
0x18013e349  xor     ebx, ebx
0x18013e34b  test    edi, edi
0x18013e34d  jz      loc_18013E974
0x18013e353  cmp     edi, 10000h
0x18013e359  jz      loc_18013E50F
0x18013e35f  cmp     edi, 20000h
0x18013e365  jz      loc_18013E50F
0x18013e36b  cmp     edi, 30000h
0x18013e371  jz      loc_18013E50F
0x18013e377  cmp     edi, 40000h
0x18013e37d  jz      loc_18013E50F
0x18013e383  mov     r8d, 60000h
0x18013e389  cmp     edi, 50000h
0x18013e38f  jz      short loc_18013E3B3
0x18013e391  cmp     edi, r8d
0x18013e394  jz      short loc_18013E3B3
0x18013e396  cmp     edi, 70000h
0x18013e39c  jz      loc_18013E974
0x18013e3a2  cmp     edi, 100000h
0x18013e3a8  jz      loc_18013E839
0x18013e3ae  jmp     loc_18013EA84
0x18013e3b3  movzx   eax, word ptr cs:aD_5+8; ""
0x18013e3ba  xor     ecx, ecx
0x18013e3bc  movsd   xmm0, qword ptr cs:aD_5; "# %d"
0x18013e3c4  mov     r9d, 2
0x18013e3ca  mov     [rbp+1D0h+var_190], ax
0x18013e3ce  movzx   eax, r9w
0x18013e3d2  mov     dword ptr [rbp+1D0h+var_188+4], ecx
0x18013e3d5  lea     rcx, asc_18016B834; "-"
0x18013e3dc  mov     [rbp+1D0h+var_188], ax
0x18013e3e0  mov     qword ptr [rbp+1D0h+var_188+8], rcx
0x18013e3e4  movsd   qword ptr [rbp+1D0h+var_198], xmm0
0x18013e3e9  mov     [rbp+1D0h+var_188+2], r9w
0x18013e3ee  movzx   edx, r15w
0x18013e3f2  cmp     edi, r8d
0x18013e3f5  jz      short loc_18013E416
0x18013e3f7  cmp     [r12+8], ebx
0x18013e3fc  jz      short loc_18013E43C
0x18013e3fe  cmp     edx, [r12+8]
0x18013e403  jb      short loc_18013E40F
0x18013e405  mov     ebx, 0C000000Dh
0x18013e40a  jmp     loc_18013EB44
0x18013e40f  mov     rax, [r12+10h]
0x18013e414  jmp     short loc_18013E42A
0x18013e416  mov     r8, [rbp+1D0h+var_220]
0x18013e41a  cmp     [r8+8], ebx
0x18013e41e  jz      short loc_18013E43C
0x18013e420  cmp     edx, [r8+8]
0x18013e424  jnb     short loc_18013E405
0x18013e426  mov     rax, [r8+10h]
0x18013e42a  mov     rcx, rdx
0x18013e42d  add     rcx, rcx
0x18013e430  movups  xmm0, xmmword ptr [rax+rcx*8]
0x18013e434  movd    eax, xmm0
0x18013e438  movups  xmmword ptr [rbp+1D0h+var_188], xmm0
0x18013e43c  cmp     ax, r9w
0x18013e440  ja      short loc_18013E494
0x18013e442  mov     dword ptr [rsp+2D0h+var_2A0], edx
0x18013e446  lea     rax, [rbp+1D0h+var_198]
0x18013e44a  mov     [rsp+2D0h+pszFormat], rax; pszFormat
0x18013e44f  lea     r9, [rsp+2D0h+pcchRemaining]; pcchRemaining
0x18013e454  xor     r8d, r8d; ppszDestEnd
0x18013e457  mov     qword ptr [rsp+2D0h+dwFlags], rbx; dwFlags
0x18013e45c  mov     rdx, rsi; cchDest
0x18013e45f  mov     [rsp+2D0h+pcchRemaining], rbx
0x18013e464  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x18013e468  call    StringCchPrintfExW
0x18013e46d  test    eax, eax
0x18013e46f  js      short loc_18013E490
0x18013e471  sub     si, word ptr [rsp+2D0h+pcchRemaining]
0x18013e476  lea     rcx, [rbp+1D0h+pszDest]
0x18013e47a  mov     eax, 28h ; '('
0x18013e47f  mov     qword ptr [rbp+1D0h+var_188+8], rcx
0x18013e483  mov     [rbp+1D0h+var_188+2], ax
0x18013e487  lea     eax, [rsi+rsi]
0x18013e48a  mov     [rbp+1D0h+var_188], ax
0x18013e48e  jmp     short loc_18013E494
0x18013e490  movzx   eax, [rbp+1D0h+var_188]
0x18013e494  mov     rcx, gs:60h
0x18013e49d  mov     edx, 8; Flags
0x18013e4a2  movzx   ebx, ax
0x18013e4a5  add     ebx, 36h ; '6'
0x18013e4a8  mov     r8d, ebx; Size
0x18013e4ab  mov     rcx, [rcx+30h]; HeapHandle
0x18013e4af  call    cs:__imp_RtlAllocateHeap
0x18013e4b6  nop     dword ptr [rax+rax+00h]
0x18013e4bb  xor     r12d, r12d
0x18013e4be  mov     [rsp+2D0h+Destination.Buffer], rax
0x18013e4c3  test    rax, rax
0x18013e4c6  jz      loc_18013EA24
0x18013e4cc  xor     eax, eax
0x18013e4ce  add     bx, bx
0x18013e4d1  mov     [rsp+2D0h+Destination.Length], ax
0x18013e4d6  mov     [rsp+2D0h+Destination.MaximumLength], bx
0x18013e4db  cmp     edi, 50000h
0x18013e4e1  jnz     short loc_18013E4E9
0x18013e4e3  lea     rdx, [rbp+1D0h+var_218]
0x18013e4e7  jmp     short loc_18013E4F5
0x18013e4e9  cmp     edi, 60000h
0x18013e4ef  jnz     short loc_18013E506
0x18013e4f1  lea     rdx, [rbp+1D0h+Source]; Source
0x18013e4f5  lea     rcx, [rsp+2D0h+Destination]; Destination
0x18013e4fa  call    cs:__imp_RtlAppendUnicodeStringToString
0x18013e501  nop     dword ptr [rax+rax+00h]
0x18013e506  lea     rdx, [rbp+1D0h+var_188]
0x18013e50a  jmp     loc_18013EA73
0x18013e50f  xor     eax, eax
0x18013e511  mov     qword ptr [rbp+1D0h+var_198], rbx
0x18013e515  mov     [rbp+1D0h+var_148], rax
0x18013e51c  lea     r9, [rsp+2D0h+DaclDefaulted]; DaclDefaulted
0x18013e521  xorps   xmm0, xmm0
0x18013e524  mov     [rsp+2D0h+DaclPresent], bl
0x18013e528  lea     eax, [rdi-10000h]
0x18013e52e  mov     [rsp+2D0h+DaclDefaulted], bl
0x18013e532  test    eax, 0FFFEFFFFh
0x18013e537  mov     [rsp+2D0h+pcchRemaining], rbx
0x18013e53c  movups  xmmword ptr [rbp+1D0h+pszDest], xmm0
0x18013e540  cmovnz  r12, [rbp+1D0h+var_220]
0x18013e545  lea     r8, [rbp+1D0h+var_198]; Dacl
0x18013e549  movups  [rbp+1D0h+var_158], xmm0
0x18013e54d  mov     [rsp+2D0h+StringSecurityDescriptorLen], ebx
0x18013e551  lea     rdx, [rsp+2D0h+DaclPresent]; DaclPresent
0x18013e556  mov     rcx, [r12]; SecurityDescriptor
0x18013e55a  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18013e561  nop     dword ptr [rax+rax+00h]
0x18013e566  xor     r12d, r12d
0x18013e569  mov     ebx, eax
0x18013e56b  test    eax, eax
0x18013e56d  js      loc_18013EB47
0x18013e573  cmp     [rsp+2D0h+DaclPresent], r12b
0x18013e578  jz      loc_18013EB47
0x18013e57e  mov     rcx, qword ptr [rbp+1D0h+var_198]; Acl
0x18013e582  lea     r8, [rsp+2D0h+pcchRemaining]; Ace
0x18013e587  movzx   edx, r15w; AceIndex
0x18013e58b  call    cs:__imp_RtlGetAce
0x18013e592  nop     dword ptr [rax+rax+00h]
0x18013e597  mov     ebx, eax
0x18013e599  test    eax, eax
0x18013e59b  js      loc_18013EB47
0x18013e5a1  mov     rax, [rsp+2D0h+pcchRemaining]
0x18013e5a6  lea     edx, [r12+8]; Flags
0x18013e5ab  mov     rcx, gs:60h
  ... truncated ...
```
