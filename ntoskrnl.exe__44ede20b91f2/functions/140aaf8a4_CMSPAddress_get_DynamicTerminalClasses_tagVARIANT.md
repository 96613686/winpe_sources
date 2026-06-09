# CMSPAddress::get_DynamicTerminalClasses(tagVARIANT *)

- ea: `0x140aaf8a4`
- end: `0x140ab0918`
- name: `?get_DynamicTerminalClasses@CMSPAddress@@UEAAJPEAUtagVARIANT@@@Z_3`
- size: `4212`
- prototype: `__int64 __fastcall(CMSPAddress *__hidden this, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `56`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140aaf834`
- `0x140ad9fbc`
- `0x140c83918`

## callees

- `0x140223fb0`
- `0x140272040`
- `0x1402bb4b0`
- `0x1402f92c0`
- `0x140307470`
- `0x1403075d0`
- `0x14030aec0`
- `0x1403f2d50`
- `0x14041368c`
- `0x1404a3150`
- `0x1404afb50`
- `0x1404bcea4`
- `0x1404e7c00`
- `0x14053cf40`
- `0x14067ed58`
- `0x1406d9d70`
- `0x1406daa70`
- `0x1406f4750`
- `0x1407d6040`
- `0x1407d60d0`
- `0x1407d6168`
- `0x1407d6234`
- `0x140861930`
- `0x1408619e0`
- `0x140861f80`
- `0x140869d40`
- `0x1408ad040`
- `0x1408eeff0`
- `0x14094eb7c`
- `0x14094ec90`
- `0x14094ee30`
- `0x14094ef64`
- `0x14094f030`
- `0x14094f5f4`
- `0x14094f870`
- `0x140951024`
- `0x140951364`
- `0x1409590c0`
- `0x140964ff0`
- `0x1409650e4`
- `0x140965a98`
- `0x1409b3930`
- `0x1409f24f4`
- `0x140a19da8`
- `0x140a30ad4`
- `0x140a8f198`
- `0x140a9059c`
- `0x140aaf8a4`
- `0x140abb0a8`
- `0x140abf1b0`

## string_xrefs

- `0x140aafe44`: `Eventlog-Security`
- `0x140aaff06`: `Eventlog-Security`

## pseudocode

```c
__int64 __fastcall CMSPAddress::get_DynamicTerminalClasses(CMSPAddress *this, struct tagVARIANT *a2)
{
  unsigned int v3; // r15d
  NTSTATUS ClientSecurity; // edi
  int v5; // r13d
  int v6; // ecx
  int v7; // ecx
  int v8; // r8d
  int v10; // edx
  int v11; // ecx
  int v12; // eax
  UUID *v13; // rbx
  unsigned int v14; // edi
  ACCESS_MASK v15; // edx
  __int64 v16; // rbx
  __int64 v17; // rsi
  unsigned int v18; // r13d
  bool v19; // zf
  char v20; // bl
  int v21; // edx
  int v22; // ecx
  unsigned int *v23; // rbx
  unsigned int v24; // edi
  __int64 v25; // rax
  __int64 v26; // rsi
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // r8d
  __int64 v30; // rcx
  const WCHAR *v31; // rdx
  __int64 v32; // rcx
  unsigned int *v33; // rsi
  __int64 v34; // rax
  __int16 v35; // dx
  __int64 v36; // rbx
  __int64 v37; // rdx
  __int64 v38; // rcx
  void *v39; // rcx
  unsigned int v40; // eax
  int v41; // eax
  int v42; // ebx
  __int64 v43; // rdx
  char v44; // al
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  int v49; // edx
  unsigned __int64 v50; // rax
  __int64 Pool2; // rax
  unsigned int v52; // ecx
  unsigned __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // r15
  __int64 CurrentServerSilo; // rax
  __int64 v57; // rcx
  __int64 v58; // r8
  __int64 v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rdx
  unsigned __int8 v62; // [rsp+40h] [rbp-C0h]
  unsigned int v63; // [rsp+44h] [rbp-BCh]
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v66; // [rsp+60h] [rbp-A0h] BYREF
  int v67; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp-90h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+80h] [rbp-80h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+90h] [rbp-70h]
  UUID Uuid; // [rsp+98h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+A8h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  __int64 *v77; // [rsp+F0h] [rbp-10h]
  __int64 v78; // [rsp+F8h] [rbp-8h]
  __int64 *v79; // [rsp+100h] [rbp+0h]
  __int64 v80; // [rsp+108h] [rbp+8h]

  v64 = (__int64)this;
  LODWORD(v66) = 0;
  v69 = 0;
  SecurityDescriptor = 0;
  HIWORD(UserData.Size) = 0;
  v67 = 0;
  Uuid = 0;
  UnicodeString = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&UnicodeString, 0);
  v3 = *((_DWORD *)a2 + 16) & 0x9DECE5FF;
  v63 = 3;
  if ( (*((_BYTE *)a2 + 64) & 3) == 0 && ((*((_BYTE *)a2 + 64) & 8) != 0 || (*((_BYTE *)a2 + 64) & 4) != 0) )
    v3 = *((_DWORD *)a2 + 16) & 0x9DECE5FE | 1;
  if ( (v3 & 0x40000) != 0 )
    v3 |= 0x80u;
  if ( (v3 & 0x80000) != 0 && (v3 & 0x1000000) != 0 )
    v3 &= ~0x1000000u;
  if ( !*((_WORD *)a2 + 72) || !*((_QWORD *)a2 + 19) )
    goto LABEL_58;
  ClientSecurity = sub_1409650E4((char *)a2 + 144, &DestinationString);
  if ( ClientSecurity )
    goto LABEL_59;
  if ( (v3 & 0x400) != 0 )
  {
    if ( *((_QWORD *)a2 + 17) || (v3 & 0xF) != 0 )
      goto LABEL_58;
    if ( (v3 & 0x100) != 0 )
      v3 &= ~0x100u;
    if ( *((_DWORD *)a2 + 17) )
      *((_DWORD *)a2 + 17) = 0;
    if ( *((_DWORD *)a2 + 19) )
      *((_DWORD *)a2 + 19) = 0;
  }
  if ( (v3 & 3) == 3 )
    goto LABEL_58;
  if ( (v3 & 0xC000) == 0xC000 )
    goto LABEL_58;
  v5 = v3 & 0x100;
  if ( (v3 & 0x100) == 0 && (v3 & 0x400) == 0 && !*((_QWORD *)a2 + 17) )
    goto LABEL_58;
  if ( (v3 & 2) != 0 && ((v3 & 4) != 0 || !*((_DWORD *)a2 + 15)) )
    goto LABEL_58;
  if ( (v3 & 0x20) != 0 && (!*((_DWORD *)a2 + 15) || (*((_DWORD *)a2 + 16) & 0xC) != 0) )
    goto LABEL_58;
  if ( (v3 & 0x40) != 0
    && ((*((_DWORD *)a2 + 28) & 2) == 0
     || (v3 & 2) == 0 && (v3 & 0x400) == 0 && ((v3 & 0x100) == 0 || *((_QWORD *)a2 + 17))) )
  {
    goto LABEL_58;
  }
  if ( (v3 & 0xC00000) == 0xC00000
    || (v3 & 8) != 0
    && (!*((_QWORD *)a2 + 17)
     || (v3 & 2) != 0
     || !*((_DWORD *)a2 + 15)
     || (*((_DWORD *)a2 + 28) & 2) != 0
     || (*((_DWORD *)a2 + 16) & 0x2000000) != 0
     || !memcmp((char *)a2 + 24, &qword_140015BD8, 0x10u)
     || !memcmp((char *)a2 + 24, qword_1400313C8, 0x10u)
     || (v3 & 4) != 0) )
  {
    goto LABEL_58;
  }
  v6 = *((_DWORD *)a2 + 16);
  if ( (v6 & 0x2000000) != 0 && (v6 & 0x1000000) != 0 )
    goto LABEL_58;
  if ( (v6 & 0x4000000) != 0 && (v6 & 0x106) != 0 || (v6 & 0x10000) != 0 )
    goto LABEL_58;
  if ( (*((_BYTE *)a2 + 80) & 4) != 0 )
  {
    if ( !qword_140FDBCD8 )
    {
      ClientSecurity = -1073741637;
      if ( EtwEventEnabled(qword_140EED2B0, &stru_140028B30) )
        sub_1407D6168(
          v11,
          v10,
          (_DWORD)a2 + 24,
          *((_DWORD *)a2 + 16),
          (__int64)&DestinationString,
          (__int64)&UnicodeString);
LABEL_59:
      if ( EtwEventEnabled(qword_140EED2B0, &stru_1400281D0) )
        sub_140ACAF20(
          v7,
          (unsigned int)&stru_1400281D0,
          v8,
          (unsigned int)&DestinationString,
          (__int64)&UnicodeString,
          ClientSecurity,
          v3);
      RtlFreeUnicodeString(&DestinationString);
      RtlFreeUnicodeString(&UnicodeString);
      sub_140A30AD4(&SecurityDescriptor);
      return (unsigned int)ClientSecurity;
    }
    if ( (v6 & 0x400) == 0 || (v6 & 0x1000000) != 0 )
    {
LABEL_58:
      ClientSecurity = -1073741811;
      goto LABEL_59;
    }
  }
  v12 = *((_DWORD *)a2 + 28);
  if ( v12 >= 0 )
  {
    v13 = (UUID *)((char *)a2 + 24);
  }
  else
  {
    if ( byte_140EED4E0 )
      goto LABEL_58;
    if ( (v12 & 2) == 0 )
      goto LABEL_58;
    if ( (*((_DWORD *)a2 + 16) & 0x2000000) == 0 )
      goto LABEL_58;
    if ( ((*((_DWORD *)a2 + 10) - 2) & 0xFFFFFFFD) == 0 )
      goto LABEL_58;
    v13 = (UUID *)((char *)a2 + 24);
    if ( !memcmp((char *)a2 + 24, &xmmword_140012B30, 0x10u) )
      goto LABEL_58;
  }
  ClientSecurity = sub_14094F5F4(a2);
  if ( ClientSecurity < 0 )
    goto LABEL_59;
  v14 = 0;
  v15 = (v5 != 0 ? 160 : 128) | 0x40;
  if ( !*((_WORD *)a2 + 64) )
    v15 = v5 != 0 ? 160 : 128;
  DesiredAccess = v15;
  if ( !(unsigned int)sub_140965A98(v64, &DestinationString, &v66) )
  {
LABEL_77:
    ClientSecurity = -1073741771;
    goto LABEL_59;
  }
  if ( !memcmp(v13, &xmmword_140012B30, 0x10u) )
  {
    ClientSecurity = ExUuidCreate(&Uuid);
    if ( ClientSecurity < 0 )
      goto LABEL_59;
    v14 = 0;
  }
  else
  {
    Uuid = *v13;
  }
  if ( (v3 & 0xC00000) == 0 )
  {
    if ( *((_BYTE *)KeGetCurrentThread() + 562)
      && (unsigned int)PsGetProcessSessionId(*((_QWORD *)KeGetCurrentThread() + 23)) )
    {
      v3 |= 0x400000u;
    }
    else
    {
      v3 |= 0x800000u;
    }
  }
  v16 = v64;
  v17 = *(_QWORD *)(v64 + 712);
  v66 = v17;
  if ( !memcmp(&Uuid, &qword_140015BD8, 0x10u) || !memcmp(&Uuid, qword_1400313C8, 0x10u) )
  {
    RtlFreeUnicodeString(&DestinationString);
    if ( !memcmp(&Uuid, &qword_140015BD8, 0x10u) )
    {
      v18 = 0;
      v31 = L"NT Kernel Logger";
    }
    else
    {
      v14 = 2;
      v31 = L"Circular Kernel Context Logger";
      v18 = 1;
    }
    v63 = v14;
    if ( RtlCreateUnicodeString(&DestinationString, v31) )
    {
      v3 |= 0x80u;
      if ( (v3 & 0x1000000) != 0 )
        goto LABEL_58;
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8LL * v14), v17 | 1, 1) == 1;
      goto LABEL_133;
    }
    goto LABEL_130;
  }
  v18 = 8;
  if ( !memcmp(&Uuid, &xmmword_140B87D28, 0x10u) )
  {
    v63 = 1;
    v14 = 1;
    if ( !sub_14094F030(a2, 1) )
    {
LABEL_94:
      v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8), v17 | 1, 1) == 1;
LABEL_133:
      if ( v19 )
        goto LABEL_100;
      goto LABEL_77;
    }
    if ( (v3 & 0x1000000) != 0 )
      goto LABEL_58;
    RtlFreeUnicodeString(&DestinationString);
    if ( RtlCreateUnicodeString(&DestinationString, L"NT Kernel Logger") )
    {
      v18 = 0;
      goto LABEL_94;
    }
LABEL_130:
    ClientSecurity = -1073741801;
    goto LABEL_59;
  }
  if ( !memcmp(&Uuid, qword_140031548, 0x10u) )
  {
    if ( (v3 & 0x1000000) != 0 )
      goto LABEL_58;
    RtlFreeUnicodeString(&DestinationString);
    if ( RtlCreateUnicodeString(&DestinationString, L"Eventlog-Security") )
    {
      v3 |= 0x80u;
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 24), v17 | 1, 1) == 1 )
      {
        v14 = 3;
        goto LABEL_100;
      }
      goto LABEL_77;
    }
    goto LABEL_130;
  }
  if ( !wcsicmp(DestinationString.Buffer, L"Eventlog-Security") && memcmp(&Uuid, qword_140031548, 0x10u) )
    goto LABEL_77;
  v23 = (unsigned int *)(v64 + 16);
  v24 = 4;
  if ( *(_DWORD *)(v64 + 16) <= 4u )
    goto LABEL_114;
  while ( 1 )
  {
    v25 = sub_140964FF0(v64, v24, 0);
    v26 = v25;
    if ( v25 )
      break;
LABEL_110:
    if ( ++v24 >= *v23 )
      goto LABEL_113;
  }
  if ( memcmp((const void *)(v25 + 276), &Uuid, 0x10u) )
  {
    sub_140A19DA8(v26, 0);
    goto LABEL_110;
  }
  sub_140A19DA8(v26, 0);
LABEL_113:
  v17 = v66;
LABEL_114:
  if ( v24 < *v23 )
    goto LABEL_77;
  v14 = 4;
  v63 = 4;
  if ( *v23 > 4 )
  {
    do
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)(v17 + 8LL * v14), v17 | 1, 1) == 1 )
        break;
      ++v14;
    }
    while ( v14 < *v23 );
    v63 = v14;
  }
  if ( v14 >= *v23 )
  {
    if ( !byte_140E44DE9 )
    {
      byte_140E44DE9 = 1;
      UserData.Ptr = v64 + 16;
      *(_QWORD *)&UserData.Size = 4;
      EtwWrite(qword_140EED2B0, &stru_140028FE0, 0, 1u, &UserData);
      if ( (unsigned int)dword_140E0C6D0 > 5 )
      {
        if ( (unsigned __int8)sub_1404E7C00(&dword_140E0C6D0, 0x200000000000LL, v27, v28) )
        {
          v69 = 1;
          v75 = &v69;
          v76 = 8;
          v77 = &v64;
          LODWORD(v66) = *v23;
          v79 = &v66;
          v64 = 0x1000000;
          v78 = 8;
          v80 = 4;
          sub_14041368C((int)&dword_140E0C6D0, (int)&byte_140054AF8, v29, 5, &v74);
        }
      }
    }
    ClientSecurity = -1073741670;
    if ( EtwEventEnabled(qword_140EED2B0, &stru_140029460) )
      sub_1407D6234(v30, &stru_140029460, &DestinationString, *v23);
    goto LABEL_59;
  }
  v16 = v64;
LABEL_100:
  ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v16 + 704) + 8LL * v14), 1u);
  if ( *((int *)a2 + 28) >= 0 )
  {
    sub_140861F80(&Uuid, &SecurityDescriptor);
    v20 = DesiredAccess;
    v69 = (__int64)SecurityDescriptor;
    ClientSecurity = sub_140861930(SecurityDescriptor, DesiredAccess);
    if ( ClientSecurity < 0 )
    {
      if ( EtwEventEnabled(qword_140EED2B0, &stru_1400282C0) )
        sub_1407D60D0(v22, v21, (unsigned int)&DestinationString, (unsigned int)&Uuid, v20);
      goto LABEL_166;
    }
    v16 = v64;
  }
  if ( !memcmp(&qword_1400159D0, &Uuid, 0x10u) )
    v62 = 0;
  else
    v62 = memcmp(&qword_1400159E0, &Uuid, 0x10u) != 0 ? 9 : 1;
  if ( (*((_DWORD *)a2 + 16) & 0x2000000) != 0 && v18 == 8 )
  {
    if ( *((int *)a2 + 28) < 0 || (ClientSecurity = sub_1408619E0(&qword_140015BD8, 128, 0), ClientSecurity >= 0) )
    {
      v18 = 2;
      while ( _bittest((const signed __int32 *)(v16 + 4520), v18) )
      {
        if ( ++v18 >= 8 )
        {
          if ( v18 != 8 )
            goto LABEL_150;
          ClientSecurity = -1073741670;
          if ( EtwEventEnabled(qword_140EED2B0, &stru_1400277A0) )
            sub_1407D6234(v32, &stru_1400277A0, &DestinationString, 8);
          goto LABEL_166;
        }
      }
      goto LABEL_150;
    }
LABEL_166:
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v64 + 704) + 8LL * v63), 1u);
    _InterlockedExchange64((volatile __int64 *)(v66 + 8LL * v63), 1);
    goto LABEL_59;
  }
LABEL_150:
  v33 = (unsigned int *)sub_140A8F198(&DestinationString, v3, *((unsigned int *)a2 + 28));
  if ( !v33 )
  {
    ClientSecurity = -1073741801;
    goto LABEL_166;
  }
  v34 = sub_14094F030(a2, 6);
  v36 = v34;
  if ( v34 )
  {
    if ( 4 * *(_WORD *)v34 == v35 + 6 )
    {
      ClientSecurity = sub_14067ED58(v33 + 396, *(_QWORD *)(v34 + 4));
      if ( ClientSecurity < 0 )
      {
        if ( EtwEventEnabled(qword_140EED2B0, &stru_140027320) )
          sub_1407D6040(v38, v37, &DestinationString, *(_QWORD *)(v36 + 4));
        goto LABEL_157;
      }
    }
  }
  RtlFreeUnicodeString(&DestinationString);
  *(UUID *)(v33 + 69) = Uuid;
  v33[73] = *((_DWORD *)a2 + 15);
  if ( (*((_BYTE *)a2 + 80) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x10u);
  v33[50] = *((_DWORD *)a2 + 10);
  if ( (*((_BYTE *)a2 + 80) & 2) != 0 )
  {
    ClientSecurity = sub_1404BCEA4(v33);
    if ( ClientSecurity < 0 )
      goto LABEL_157;
  }
  if ( (*((_BYTE *)a2 + 80) & 8) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x40000000u);
  v40 = *((_DWORD *)a2 + 17);
  if ( v40 )
  {
    v33[52] = v40;
  }
  else if ( (v3 & 0x100) != 0 )
  {
    v33[52] = (v3 & 0x10) != 0 ? 1000 : 1;
  }
  v41 = *((_DWORD *)a2 + 19);
  if ( v41 )
  {
    if ( v33[52] || v41 < 0 )
    {
      *((_DWORD *)a2 + 19) = 0;
      goto LABEL_181;
    }
  }
  else
  {
LABEL_181:
    v41 = 0;
  }
  v33[53] = v41;
  ClientSecurity = 0;
  *v33 = v63;
  *((_QWORD *)v33 + 170) = v64;
  if ( *((_WORD *)a2 + 64) )
  {
    if ( *((_QWORD *)a2 + 17) )
    {
      ClientSecurity = sub_1409650E4((char *)a2 + 128, &UnicodeString);
      if ( ClientSecurity < 0 )
        goto LABEL_157;
    }
  }
  if ( (*((_DWORD *)a2 + 28) & 2) != 0 )
  {
    v33[74] = *((_DWORD *)a2 + 24);
    *((_DWORD *)a2 + 24) = 0;
  }
  if ( (v33[3] & 8) == 0 )
  {
    *(UNICODE_STRING *)(v33 + 38) = UnicodeString;
    RtlInitUnicodeString(&UnicodeString, 0);
    goto LABEL_191;
  }
  *(UNICODE_STRING *)(v33 + 42) = UnicodeString;
  RtlInitUnicodeString(&UnicodeString, 0);
  ClientSecurity = sub_140ABB0A8(v33 + 42, v33 + 74, v33 + 38);
  if ( ClientSecurity < 0 )
  {
LABEL_157:
    if ( (v33[3] & 0x2000000) != 0 )
      _interlockedbittestandreset((volatile signed __int32 *)(v64 + 4520), v18);
    sub_1404A3150(v33 + 208);
    if ( (v33[204] & 0x80u) != 0 )
      ExFreePoolWithTag(*((PVOID *)v33 + 131), 0);
    if ( (v33[204] & 0x2000) != 0 )
      _InterlockedDecrement((volatile signed __int32 *)&qword_140E2D040);
    RtlFreeUnicodeString((PUNICODE_STRING)(v33 + 38));
    RtlFreeUnicodeString((PUNICODE_STRING)(v33 + 42));
    v39 = (void *)*((_QWORD *)v33 + 100);
    if ( v39 )
      ZwClose(v39);
    ExFreePoolWithTag(v33, 0);
    goto LABEL_166;
  }
LABEL_191:
  if ( *((int *)a2 + 28) >= 0 )
  {
    UserData.Ptr = 0x20000000CLL;
    LOWORD(UserData.Size) = 257;
    ClientSecurity = SeCreateClientSecurity(
                       KeGetCurrentThread(),
                       (PSECURITY_QUALITY_OF_SERVICE)&UserData,
                       0,
                       (PSECURITY_CLIENT_CONTEXT)(v33 + 176));
  }
  if ( ClientSecurity < 0 )
    goto LABEL_157;
  if ( (v33[3] & 0x100) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 8u);
  else
    _InterlockedAnd((volatile signed __int32 *)v33 + 204, 0xFFFFFFF7);
  if ( (*((_DWORD *)a2 + 28) & 2) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 2u);
  if ( *((int *)a2 + 28) < 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x80000000);
  if ( (*((_DWORD *)a2 + 28) & 1) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 1u);
  v42 = 0x4000;
  if ( (*((_DWORD *)a2 + 28) & 0x4000) != 0 )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x4000u);
  sub_140B1CFB4(v33);
  if ( v18 < 8 )
  {
    _InterlockedAnd((volatile signed __int32 *)v33 + 204, 0xFF00FFFF);
    _InterlockedOr((volatile signed __int32 *)v33 + 204, v18 << 16);
    v33[3] |= 0x2000000u;
    if ( v18 <= 1 )
      _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x20u);
    v43 = v64;
    *(_BYTE *)(v64 + 2LL * v18 + 4504) = v63;
    if ( v33[50] - 1 >= 4 )
      v44 = 1;
    else
      v44 = *((_BYTE *)v33 + 200);
    *(_BYTE *)(v43 + 2LL * v18 + 4505) = v44;
    _interlockedbittestandset((volatile signed __int32 *)(v43 + 4520), v18);
  }
  ClientSecurity = sub_14094EF64(a2, v33);
  if ( ClientSecurity < 0 )
    goto LABEL_157;
  v45 = *((_DWORD *)a2 + 13);
  if ( v45 )
    v33[56] = v45;
  v46 = *((_DWORD *)a2 + 14);
  if ( v46 )
    v33[59] = v46;
  v47 = *((_DWORD *)a2 + 12);
  if ( v47 )
  {
    if ( v47 <= 0x4000 )
      v42 = *((_DWORD *)a2 + 12);
    else
      *((_DWORD *)a2 + 12) = 0x4000;
    v33[1] = v42 << 10;
  }
  if ( (*((_BYTE *)a2 + 80) & 4) != 0 )
  {
    v33[1] = (v33[1] + 0x1FFFFF) & 0xFFE00000;
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x20000000u);
  }
  if ( *((_WORD *)v33 + 76) )
  {
    *((_QWORD *)v33 + 4) = KeGetCurrentThread();
    while ( 1 )
    {
      _InterlockedOr((volatile signed __int32 *)v33 + 206, 1u);
      ClientSecurity = sub_1409F24F4(v33, 0, &v67);
      if ( ClientSecurity >= 0 )
        break;
      if ( ClientSecurity != -1073741306 )
        goto LABEL_157;
      v48 = v33[1];
      v49 = ~(v67 - 1) & (v67 - 1 + v48);
      if ( v48 == v49 )
        goto LABEL_157;
      v33[1] = v49;
    }
  }
  if ( v33[1] < 0x1000 && (*((_WORD *)v33 + 76) || (v33[3] & 0x400) != 0) )
    _InterlockedOr((volatile signed __int32 *)v33 + 204, 0x1000u);
  v50 = v33[1] - 72LL;
  if ( v50 >= 0xFFFF )
    LODWORD(v50) = 0xFFFF;
  v33[2] = v50 & 0xFFFFFFF8;
  ClientSecurity = sub_140B1CA40(v33);
  if ( ClientSecurity < 0 )
  {
LABEL_237:
    sub_140A9059C(v33);
    goto LABEL_157;
  }
  if ( (v3 & 0x4000000) != 0 && (v3 & 0x400) == 0 )
  {
    Pool2 = ExAllocatePool2(64, v33[1], 1517777989);
    *((_QWORD *)v33 + 177) = Pool2;
    if ( !Pool2 )
    {
      ClientSecurity = -1073741801;
      goto LABEL_157;
    }
  }
  v52 = v33[73];
  if ( !v52 || (v33[3] & 0x2000) != 0 )
    v53 = 10485760;
  else
    v53 = (unsigned __int64)v52 << 20;
  v54 = v33[1] * v33[59];
  if ( v53 <= (unsigned int)(2 * v54) )
    v53 = (unsigned int)(2 * v54);
  *((_QWORD *)v33 + 52) = v53;
  if ( *((int *)a2 + 28) >= 0 )
  {
    ClientSecurity = sub_140ABF1B0(v33, v69);
    sub_140A30AD4(&SecurityDescriptor);
    if ( ClientSecurity < 0 )
      goto LABEL_237;
  }
  v55 = v64;
  _InterlockedAdd((volatile signed __int32 *)(v64 + 4404), 1u);
  ExAcquireRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v64 + 704) + 8LL * v63), 1u);
  if ( (v33[3] & 0x400) == 0 && *((int *)a2 + 28) >= 0 )
  {
    CurrentServerSilo = PsGetCurrentServerSilo();
    ClientSecurity = sub_1404AFB50(CurrentServerSilo, v33);
    if ( ClientSecurity < 0 )
    {
      ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v64 + 704) + 8LL * v63), 1u);
      goto LABEL_254;
    }
  }
  if ( EtwEventEnabled(qword_140EED2B0, &stru_140015A00) )
    sub_140951364(v57, &stru_140015A00, v33);
  KeWaitForSingleObject(v33 + 158, Executive, 0, 0, 0);
  _InterlockedExchange64((volatile __int64 *)(v66 + 8LL * v63), (__int64)v33);
  sub_1409590C0(v33, 5);
  if ( (v33[3] & 0x2000000) == 0 )
    goto LABEL_264;
  if ( (CMSPAddress *)v64 != qword_140FBEBE8 )
    goto LABEL_261;
  LOBYTE(v58) = 1;
  ClientSecurity = sub_14094EC90(v33, a2, v58);
  if ( ClientSecurity >= 0 )
  {
    v59 = 5LL * v18;
    *((_WORD *)qword_140EED380 + 2 * v59) = 1;
    *((_DWORD *)qword_140EED380 + v59 + 1) = 42;
LABEL_261:
    ClientSecurity = sub_14094EE30(v33, a2);
    if ( ClientSecurity >= 0 )
      goto LABEL_264;
  }
  v33[10] = ClientSecurity;
  sub_14094F870(v33);
  if ( (v33[3] & 0x400) != 0 )
  {
    sub_140951024(a2, v33);
    LOBYTE(v60) = 1;
    sub_140A19DA8(v33, v60);
LABEL_254:
    sub_140B1CB54(v33);
  }
  else
  {
LABEL_264:
    if ( v62 != 9 )
      sub_14094EB7C(a2, v55, *v33, v62);
    sub_140951024(a2, v33);
    LOBYTE(v61) = 1;
    sub_140A19DA8(v33, v61);
  }
  return (unsigned int)ClientSecurity;
}

```

## disassembly

```asm
0x140aaf8a4  mov     [rsp-8+arg_10], rbx
0x140aaf8a9  push    rbp
0x140aaf8aa  push    rsi
0x140aaf8ab  push    rdi
0x140aaf8ac  push    r12
0x140aaf8ae  push    r13
0x140aaf8b0  push    r14
0x140aaf8b2  push    r15
0x140aaf8b4  lea     rbp, [rsp-20h]
0x140aaf8b9  sub     rsp, 120h
0x140aaf8c0  mov     rax, cs:__security_cookie
0x140aaf8c7  xor     rax, rsp
0x140aaf8ca  mov     [rbp+50h+var_40], rax
0x140aaf8ce  xor     edi, edi
0x140aaf8d0  mov     [rsp+150h+var_108], rcx
0x140aaf8d5  mov     eax, edi
0x140aaf8d7  mov     dword ptr [rsp+150h+var_F0], edi
0x140aaf8db  xorps   xmm0, xmm0
0x140aaf8de  mov     [rsp+150h+var_D8], rax
0x140aaf8e3  mov     r14, rdx
0x140aaf8e6  mov     [rsp+150h+SecurityDescriptor], rax
0x140aaf8eb  xorps   xmm1, xmm1
0x140aaf8ee  mov     word ptr [rbp+50h+var_A8.Size+2], di
0x140aaf8f2  xor     edx, edx; SourceString
0x140aaf8f4  mov     [rsp+150h+var_E8], edi
0x140aaf8f8  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x140aaf8fd  movups  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140aaf901  movups  xmmword ptr [rbp+50h+UnicodeString.Length], xmm0
0x140aaf905  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm1
0x140aaf90a  call    RtlInitUnicodeString
0x140aaf90f  xor     edx, edx; SourceString
0x140aaf911  lea     rcx, [rbp+50h+UnicodeString]; DestinationString
0x140aaf915  call    RtlInitUnicodeString
0x140aaf91a  mov     r15d, [r14+40h]
0x140aaf91e  lea     ebx, [rdi+3]
0x140aaf921  and     r15d, 9DECE5FFh
0x140aaf928  mov     [rsp+150h+var_10C], ebx
0x140aaf92c  lea     r12d, [rdi+1]
0x140aaf930  test    bl, r15b
0x140aaf933  jnz     short loc_140AAF944
0x140aaf935  test    r15b, 8
0x140aaf939  jnz     short loc_140AAF941
0x140aaf93b  test    r15b, 4
0x140aaf93f  jz      short loc_140AAF944
0x140aaf941  or      r15d, r12d
0x140aaf944  bt      r15d, 12h
0x140aaf949  jnb     short loc_140AAF950
0x140aaf94b  bts     r15d, 7
0x140aaf950  bt      r15d, 13h
0x140aaf955  jnb     short loc_140AAF963
0x140aaf957  bt      r15d, 18h
0x140aaf95c  jnb     short loc_140AAF963
0x140aaf95e  btr     r15d, 18h
0x140aaf963  lea     rcx, [r14+90h]
0x140aaf96a  cmp     [rcx], di
0x140aaf96d  jbe     loc_140AAFB5B
0x140aaf973  cmp     [r14+98h], rdi
0x140aaf97a  jz      loc_140AAFB5B
0x140aaf980  lea     rdx, [rsp+150h+DestinationString]
0x140aaf985  call    sub_1409650E4
0x140aaf98a  mov     edi, eax
0x140aaf98c  test    eax, eax
0x140aaf98e  jnz     loc_140AAFB60
0x140aaf994  mov     r8d, 400h
0x140aaf99a  xor     edi, edi
0x140aaf99c  mov     edx, 100h
0x140aaf9a1  test    r8d, r15d
0x140aaf9a4  jz      short loc_140AAF9DB
0x140aaf9a6  cmp     [r14+88h], rdi
0x140aaf9ad  jnz     loc_140AAFB5B
0x140aaf9b3  test    r15b, 0Fh
0x140aaf9b7  jnz     loc_140AAFB5B
0x140aaf9bd  test    edx, r15d
0x140aaf9c0  jz      short loc_140AAF9C7
0x140aaf9c2  btr     r15d, 8
0x140aaf9c7  cmp     [r14+44h], edi
0x140aaf9cb  jz      short loc_140AAF9D1
0x140aaf9cd  mov     [r14+44h], edi
0x140aaf9d1  cmp     [r14+4Ch], edi
0x140aaf9d5  jz      short loc_140AAF9DB
0x140aaf9d7  mov     [r14+4Ch], edi
0x140aaf9db  mov     eax, r15d
0x140aaf9de  and     eax, ebx
0x140aaf9e0  cmp     al, bl
0x140aaf9e2  jz      loc_140AAFB5B
0x140aaf9e8  mov     ecx, 0C000h
0x140aaf9ed  mov     eax, r15d
0x140aaf9f0  and     eax, ecx
0x140aaf9f2  cmp     eax, ecx
0x140aaf9f4  jz      loc_140AAFB5B
0x140aaf9fa  mov     r13d, r15d
0x140aaf9fd  and     r13d, edx
0x140aafa00  jnz     short loc_140AAFA14
0x140aafa02  test    r8d, r15d
0x140aafa05  jnz     short loc_140AAFA14
0x140aafa07  cmp     [r14+88h], rdi
0x140aafa0e  jz      loc_140AAFB5B
0x140aafa14  mov     ecx, r15d
0x140aafa17  and     ecx, 2
0x140aafa1a  jz      short loc_140AAFA30
0x140aafa1c  test    r15b, 4
0x140aafa20  jnz     loc_140AAFB5B
0x140aafa26  cmp     [r14+3Ch], edi
0x140aafa2a  jz      loc_140AAFB5B
0x140aafa30  test    r15b, 20h
0x140aafa34  jz      short loc_140AAFA4C
0x140aafa36  cmp     [r14+3Ch], edi
0x140aafa3a  jz      loc_140AAFB5B
0x140aafa40  mov     eax, [r14+40h]
0x140aafa44  test    al, 0Ch
0x140aafa46  jnz     loc_140AAFB5B
0x140aafa4c  test    r15b, 40h
0x140aafa50  jz      short loc_140AAFA7D
0x140aafa52  mov     eax, [r14+70h]
0x140aafa56  test    al, 2
0x140aafa58  jz      loc_140AAFB5B
0x140aafa5e  test    ecx, ecx
0x140aafa60  jnz     short loc_140AAFA7D
0x140aafa62  test    r8d, r15d
0x140aafa65  jnz     short loc_140AAFA7D
0x140aafa67  test    r13d, r13d
0x140aafa6a  jz      loc_140AAFB5B
0x140aafa70  cmp     [r14+88h], rdi
0x140aafa77  jnz     loc_140AAFB5B
0x140aafa7d  mov     eax, 0C00000h
0x140aafa82  mov     esi, r15d
0x140aafa85  and     esi, eax
0x140aafa87  cmp     esi, eax
0x140aafa89  jz      loc_140AAFB5B
0x140aafa8f  test    r15b, 8
0x140aafa93  jz      short loc_140AAFB0C
0x140aafa95  cmp     [r14+88h], rdi
0x140aafa9c  jz      loc_140AAFB5B
0x140aafaa2  test    ecx, ecx
0x140aafaa4  jnz     loc_140AAFB5B
0x140aafaaa  cmp     [r14+3Ch], edi
0x140aafaae  jz      loc_140AAFB5B
0x140aafab4  mov     eax, [r14+70h]
0x140aafab8  test    al, 2
0x140aafaba  jnz     loc_140AAFB5B
0x140aafac0  test    dword ptr [r14+40h], 2000000h
0x140aafac8  jnz     loc_140AAFB5B
0x140aaface  lea     r8d, [rcx+10h]; Size
0x140aafad2  lea     rcx, [r14+18h]; Buf1
0x140aafad6  lea     rdx, qword_140015BD8; Buf2
0x140aafadd  call    memcmp
0x140aafae2  test    eax, eax
0x140aafae4  jz      short loc_140AAFB5B
0x140aafae6  mov     r8d, 10h; Size
0x140aafaec  lea     rdx, qword_1400313C8; Buf2
0x140aafaf3  lea     rcx, [r14+18h]; Buf1
0x140aafaf7  call    memcmp
0x140aafafc  test    eax, eax
0x140aafafe  jz      short loc_140AAFB5B
0x140aafb00  test    r15b, 4
0x140aafb04  jnz     short loc_140AAFB5B
0x140aafb06  mov     r8d, 400h
0x140aafb0c  mov     ecx, [r14+40h]
0x140aafb10  mov     edx, ecx
0x140aafb12  and     edx, 2000000h
0x140aafb18  jz      short loc_140AAFB20
0x140aafb1a  bt      ecx, 18h
0x140aafb1e  jb      short loc_140AAFB5B
0x140aafb20  bt      ecx, 1Ah
0x140aafb24  jnb     short loc_140AAFB2E
0x140aafb26  test    ecx, 106h
0x140aafb2c  jnz     short loc_140AAFB5B
0x140aafb2e  bt      ecx, 10h
0x140aafb32  jb      short loc_140AAFB5B
0x140aafb34  test    byte ptr [r14+50h], 4
0x140aafb39  jz      loc_140AAFC26
0x140aafb3f  cmp     cs:qword_140FDBCD8, rdi
0x140aafb46  jz      loc_140AAFBE1
0x140aafb4c  test    r8d, ecx
0x140aafb4f  jz      short loc_140AAFB5B
0x140aafb51  bt      ecx, 18h
0x140aafb55  jnb     loc_140AAFC26
0x140aafb5b  mov     edi, 0C000000Dh
0x140aafb60  mov     rcx, cs:qword_140EED2B0; RegHandle
0x140aafb67  lea     rdx, stru_1400281D0; EventDescriptor
0x140aafb6e  call    EtwEventEnabled
0x140aafb73  test    al, al
0x140aafb75  jz      short loc_140AAFB9A
0x140aafb77  mov     [rsp+150h+var_120], r15d
0x140aafb7c  lea     rax, [rbp+50h+UnicodeString]
0x140aafb80  mov     dword ptr [rsp+150h+var_128], edi
0x140aafb84  lea     r9, [rsp+150h+DestinationString]
0x140aafb89  lea     rdx, stru_1400281D0
0x140aafb90  mov     [rsp+150h+UserData], rax
0x140aafb95  call    sub_140ACAF20
0x140aafb9a  lea     rcx, [rsp+150h+DestinationString]; UnicodeString
0x140aafb9f  call    RtlFreeUnicodeString
0x140aafba4  lea     rcx, [rbp+50h+UnicodeString]; UnicodeString
0x140aafba8  call    RtlFreeUnicodeString
0x140aafbad  lea     rcx, [rsp+150h+SecurityDescriptor]
0x140aafbb2  call    sub_140A30AD4
0x140aafbb7  mov     eax, edi
0x140aafbb9  mov     rcx, [rbp+50h+var_40]
0x140aafbbd  xor     rcx, rsp; StackCookie
0x140aafbc0  call    __security_check_cookie
0x140aafbc5  mov     rbx, [rsp+150h+arg_10]
0x140aafbcd  add     rsp, 120h
0x140aafbd4  pop     r15
0x140aafbd6  pop     r14
0x140aafbd8  pop     r13
0x140aafbda  pop     r12
0x140aafbdc  pop     rdi
0x140aafbdd  pop     rsi
0x140aafbde  pop     rbp
0x140aafbdf  retn
0x140aafbe1  mov     rcx, cs:qword_140EED2B0; RegHandle
0x140aafbe8  lea     rdx, stru_140028B30; EventDescriptor
0x140aafbef  mov     edi, 0C00000BBh
0x140aafbf4  call    EtwEventEnabled
0x140aafbf9  test    al, al
0x140aafbfb  jz      loc_140AAFB60
0x140aafc01  mov     r9d, [r14+40h]
0x140aafc05  lea     rax, [rbp+50h+UnicodeString]
0x140aafc09  mov     [rsp+150h+var_128], rax
0x140aafc0e  lea     r8, [r14+18h]
0x140aafc12  lea     rax, [rsp+150h+DestinationString]
0x140aafc17  mov     [rsp+150h+UserData], rax
0x140aafc1c  call    sub_1407D6168
0x140aafc21  jmp     loc_140AAFB60
0x140aafc26  mov     eax, [r14+70h]
0x140aafc2a  test    eax, eax
0x140aafc2c  jns     short loc_140AAFC7F
0x140aafc2e  cmp     cs:byte_140EED4E0, dil
0x140aafc35  jnz     loc_140AAFB5B
0x140aafc3b  test    al, 2
0x140aafc3d  jz      loc_140AAFB5B
0x140aafc43  test    edx, edx
0x140aafc45  jz      loc_140AAFB5B
0x140aafc4b  mov     eax, [r14+28h]
0x140aafc4f  sub     eax, 2
0x140aafc52  test    eax, 0FFFFFFFDh
0x140aafc57  jz      loc_140AAFB5B
0x140aafc5d  lea     rbx, [r14+18h]
0x140aafc61  mov     r8d, 10h; Size
0x140aafc67  mov     rcx, rbx; Buf1
0x140aafc6a  lea     rdx, xmmword_140012B30; Buf2
0x140aafc71  call    memcmp
0x140aafc76  test    eax, eax
0x140aafc78  jnz     short loc_140AAFC83
0x140aafc7a  jmp     loc_140AAFB5B
0x140aafc7f  lea     rbx, [r14+18h]
0x140aafc83  mov     rcx, r14
0x140aafc86  call    sub_14094F5F4
0x140aafc8b  mov     edi, eax
0x140aafc8d  test    eax, eax
0x140aafc8f  js      loc_140AAFB60
0x140aafc95  neg     r13d
0x140aafc98  lea     r8, [rsp+150h+var_F0]
0x140aafc9d  sbb     ecx, ecx
0x140aafc9f  xor     edi, edi
0x140aafca1  and     ecx, 20h
0x140aafca4  sub     ecx, 0FFFFFF80h
0x140aafca7  mov     edx, ecx
0x140aafca9  or      edx, 40h
0x140aafcac  cmp     [r14+80h], di
0x140aafcb4  cmovz   edx, ecx
0x140aafcb7  mov     rcx, [rsp+150h+var_108]
0x140aafcbc  mov     [rbp+50h+DesiredAccess], edx
0x140aafcbf  lea     rdx, [rsp+150h+DestinationString]
0x140aafcc4  call    sub_140965A98
0x140aafcc9  test    eax, eax
0x140aafccb  jnz     short loc_140AAFCD7
0x140aafccd  mov     edi, 0C0000035h
0x140aafcd2  jmp     loc_140AAFB60
0x140aafcd7  mov     r13d, 10h
0x140aafcdd  lea     rdx, xmmword_140012B30; Buf2
0x140aafce4  mov     r8d, r13d; Size
0x140aafce7  mov     rcx, rbx; Buf1
0x140aafcea  call    memcmp
0x140aafcef  test    eax, eax
0x140aafcf1  jnz     short loc_140AAFD0A
0x140aafcf3  lea     rcx, [rbp+50h+Uuid]; Uuid
0x140aafcf7  call    ExUuidCreate
0x140aafcfc  mov     edi, eax
0x140aafcfe  test    eax, eax
0x140aafd00  js      loc_140AAFB60
0x140aafd06  xor     edi, edi
0x140aafd08  jmp     short loc_140AAFD12
0x140aafd0a  movups  xmm0, xmmword ptr [rbx]
0x140aafd0d  movdqu  xmmword ptr [rbp+50h+Uuid.Data1], xmm0
0x140aafd12  test    esi, esi
0x140aafd14  jnz     short loc_140AAFD4D
0x140aafd16  mov     rax, gs:188h
0x140aafd1f  cmp     [rax+232h], dil
0x140aafd26  jz      short loc_140AAFD48
0x140aafd28  mov     rcx, gs:188h
0x140aafd31  mov     rcx, [rcx+0B8h]
0x140aafd38  call    PsGetProcessSessionId
0x140aafd3d  test    eax, eax
0x140aafd3f  jz      short loc_140AAFD48
0x140aafd41  bts     r15d, 16h
0x140aafd46  jmp     short loc_140AAFD4D
0x140aafd48  bts     r15d, 17h
0x140aafd4d  mov     rbx, [rsp+150h+var_108]
0x140aafd52  lea     rdx, qword_140015BD8; Buf2
  ... truncated ...
```
