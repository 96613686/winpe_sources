# PnpDeviceWatcher::ProcessDeviceNotifications(ulong *)

- ea: `0x18005ca58`
- end: `0x18005d0d1`
- name: `?ProcessDeviceNotifications@PnpDeviceWatcher@@QEAAJPEAK@Z`
- size: `1657`
- prototype: `__int64 __fastcall(PnpDeviceWatcher *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config`

## callers

- `0x18005c634`

## callees

- `0x18002e24c`
- `0x18002fbec`
- `0x180055b40`
- `0x18005c058`
- `0x18005ca58`
- `0x180064a30`
- `0x180065464`
- `0x180065538`
- `0x18008789c`
- `0x18008e2b4`
- `0x18008ead4`
- `0x1800ad318`
- `0x1800b8a98`
- `0x1800b8acc`
- `0x180123c2c`
- `0x1801243d4`
- `0x1801246c0`
- `0x180124b00`
- `0x180125188`
- `0x180125288`
- `0x180125430`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cb26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cbbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cc57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ccee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cdaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ce3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cead`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cb26`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cbbe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cc57`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ccee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cdaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005ce3c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005cead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d05e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005d09a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cffb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cf71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005cffb`

## string_xrefs

- `0x18005cf7b`: `Successfully exclusively opened LampArray`
- `0x18005d005`: `Failed to exclusively open LampArray`

## pseudocode

```c
__int64 __fastcall PnpDeviceWatcher::ProcessDeviceNotifications(RTL_SRWLOCK *this, unsigned int *a2)
{
  PnpDeviceWatcher::NotificationListEntry *v4; // rbx
  char *v5; // r12
  char *v6; // r14
  PnpDeviceWatcher::NotificationListEntry *v7; // rcx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int DeviceListEntryByInterfacePath; // edi
  struct PnpDeviceWatcher::DeviceListEntry *v16; // rsi
  int started; // eax
  int DeviceListEntryByInstanceId; // eax
  struct PnpDeviceWatcher::DeviceListEntry *v19; // rdi
  __int64 v20; // rax
  PnpDeviceWatcher *Ptr; // rbx
  PnpDeviceWatcher *v22; // r12
  PnpDeviceWatcher *v23; // rsi
  unsigned int CurrentMilliSecTime; // eax
  unsigned int v25; // ecx
  PnpDevice *v26; // rdi
  int InterfacePath; // eax
  unsigned int v28; // edi
  int v29; // eax
  unsigned int v30; // edx
  int v31; // r8d
  int v32; // r9d
  PnpDeviceWatcher *v33; // rcx
  PnpDeviceWatcher **v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  __int16 v38; // ax
  unsigned int v39; // ecx
  int v41; // [rsp+20h] [rbp-38h]
  const char *v42; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  struct PnpDeviceWatcher::DeviceListEntry *v44; // [rsp+A0h] [rbp+48h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+50h] BYREF
  char *v46; // [rsp+B0h] [rbp+58h] BYREF
  PCWSTR StringRawBuffer; // [rsp+B8h] [rbp+60h] BYREF

  *a2 = -1;
  v4 = 0;
  v5 = (char *)&this[4];
  while ( 1 )
  {
    v6 = *(char **)v5;
    v20 = **(_QWORD **)v5;
    if ( *(char **)(*(_QWORD *)v5 + 8LL) != v5 || *(char **)(v20 + 8) != v6 )
LABEL_48:
      __fastfail(3u);
    *(_QWORD *)v5 = v20;
    *(_QWORD *)(v20 + 8) = v5;
    if ( v6 == v5 )
      v6 = 0;
    else
      --*((_DWORD *)v5 + 4);
    v7 = v4;
    v4 = (PnpDeviceWatcher::NotificationListEntry *)v6;
    v46 = v6;
    if ( v7 )
      PnpDeviceWatcher::NotificationListEntry::`scalar deleting destructor'(v7, (unsigned int)a2);
    if ( !v6 )
      break;
    v44 = 0;
    v8 = *((_DWORD *)v6 + 6);
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            v12 = v11 - 1;
            if ( v12 )
            {
              v13 = v12 - 1;
              if ( !v13 || (v14 = v13 - 1) == 0 || (unsigned int)(v14 - 1) <= 1 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
                {
                  AcquireSRWLockExclusive(this + 7);
                  string = (HSTRING)&this[7];
                  DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                                                     (PnpDeviceWatcher *)this,
                                                     *((HSTRING *)v6 + 4),
                                                     0,
                                                     &v44);
                  v16 = v44;
                  if ( DeviceListEntryByInterfacePath >= 0 && v44 )
                    PnpDevice::OnPnpNotification(*((_QWORD *)v44 + 2), *((unsigned int *)v6 + 6));
                  goto LABEL_21;
                }
                if ( (int)PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                            (PnpDeviceWatcher *)this,
                            *((HSTRING *)v6 + 4),
                            0,
                            &v44) < 0 )
                  goto LABEL_56;
                if ( v44 )
                  PnpDevice::OnPnpNotification(*((_QWORD *)v44 + 2), *((unsigned int *)v6 + 6));
              }
            }
            else
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
              {
                AcquireSRWLockExclusive(this + 7);
                string = (HSTRING)&this[7];
                DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                                                   (PnpDeviceWatcher *)this,
                                                   *((HSTRING *)v6 + 4),
                                                   0,
                                                   &v44);
                v16 = v44;
                if ( DeviceListEntryByInterfacePath >= 0 && v44 )
                {
                  started = PnpDevice::RemoveInterface(*((PnpDevice **)v44 + 2), *((HSTRING *)v6 + 4));
                  goto LABEL_29;
                }
                goto LABEL_21;
              }
              if ( (int)PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                          (PnpDeviceWatcher *)this,
                          *((HSTRING *)v6 + 4),
                          0,
                          &v44) < 0 )
                goto LABEL_56;
              v16 = v44;
              if ( v44 )
              {
                DeviceListEntryByInstanceId = PnpDevice::RemoveInterface(*((PnpDevice **)v44 + 2), *((HSTRING *)v6 + 4));
LABEL_60:
                DeviceListEntryByInterfacePath = DeviceListEntryByInstanceId;
                goto LABEL_61;
              }
            }
          }
          else
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
            {
              AcquireSRWLockExclusive(this + 7);
              string = (HSTRING)&this[7];
              DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                                                 (PnpDeviceWatcher *)this,
                                                 *((HSTRING *)v6 + 4),
                                                 1,
                                                 &v44);
              v16 = v44;
              if ( DeviceListEntryByInterfacePath >= 0 && v44 )
              {
                started = PnpDevice::AddInterface(*((PnpDevice **)v44 + 2), *((HSTRING *)v6 + 4));
                goto LABEL_29;
              }
              goto LABEL_21;
            }
            if ( (int)PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(
                        (PnpDeviceWatcher *)this,
                        *((HSTRING *)v6 + 4),
                        1,
                        &v44) < 0 )
              goto LABEL_56;
            v16 = v44;
            if ( v44 )
            {
              DeviceListEntryByInstanceId = PnpDevice::AddInterface(*((PnpDevice **)v44 + 2), *((HSTRING *)v6 + 4));
              goto LABEL_60;
            }
          }
        }
        else
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
          {
            AcquireSRWLockExclusive(this + 7);
            string = (HSTRING)&this[7];
            DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                                               (PnpDeviceWatcher *)this,
                                               *((HSTRING *)v6 + 4),
                                               0,
                                               &v44);
            v16 = v44;
            if ( DeviceListEntryByInterfacePath >= 0 && v44 )
            {
              PnpDeviceWatcher::StopDeviceObject((PnpDeviceWatcher *)this, v44);
              NtList<PnpDeviceWatcher::DeviceListEntry>::Erase(&this[8], v16);
            }
            goto LABEL_21;
          }
          if ( (int)PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                      (PnpDeviceWatcher *)this,
                      *((HSTRING *)v6 + 4),
                      0,
                      &v44) < 0 )
            goto LABEL_56;
          v19 = v44;
          if ( v44 )
          {
            PnpDeviceWatcher::StopDeviceObject((PnpDeviceWatcher *)this, v44);
            NtList<PnpDeviceWatcher::DeviceListEntry>::Erase(&this[8], v19);
          }
        }
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
        {
          AcquireSRWLockExclusive(this + 7);
          string = (HSTRING)&this[7];
          DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                                             (PnpDeviceWatcher *)this,
                                             *((HSTRING *)v6 + 4),
                                             1,
                                             &v44);
          v16 = v44;
          if ( DeviceListEntryByInterfacePath >= 0 && v44 )
          {
            started = PnpDeviceWatcher::StartDeviceObject((PnpDeviceWatcher *)this, v44);
LABEL_29:
            DeviceListEntryByInterfacePath = started;
          }
LABEL_21:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&string);
          goto LABEL_61;
        }
        if ( (int)PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                    (PnpDeviceWatcher *)this,
                    *((HSTRING *)v6 + 4),
                    1,
                    &v44) < 0 )
        {
LABEL_56:
          v16 = v44;
LABEL_62:
          if ( v16 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
            {
              AcquireSRWLockExclusive(this + 7);
              v44 = (struct PnpDeviceWatcher::DeviceListEntry *)&this[7];
              PnpDeviceWatcher::StopDeviceObject((PnpDeviceWatcher *)this, v16);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v44);
            }
            else
            {
              PnpDeviceWatcher::StopDeviceObject((PnpDeviceWatcher *)this, v16);
            }
          }
        }
        else
        {
          v16 = v44;
          if ( v44 )
          {
            DeviceListEntryByInstanceId = PnpDeviceWatcher::StartDeviceObject((PnpDeviceWatcher *)this, v44);
            goto LABEL_60;
          }
        }
      }
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl'::`2'::impl) )
      {
        DeviceListEntryByInstanceId = PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                                        (PnpDeviceWatcher *)this,
                                        *((HSTRING *)v6 + 4),
                                        1,
                                        &v44);
        v16 = v44;
        goto LABEL_60;
      }
      AcquireSRWLockExclusive(this + 7);
      string = (HSTRING)&this[7];
      DeviceListEntryByInterfacePath = PnpDeviceWatcher::FindDeviceListEntryByInstanceId(
                                         (PnpDeviceWatcher *)this,
                                         *((HSTRING *)v6 + 4),
                                         1,
                                         &v44);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&string);
      v16 = v44;
LABEL_61:
      if ( DeviceListEntryByInterfacePath < 0 )
        goto LABEL_62;
    }
  }
  Ptr = (PnpDeviceWatcher *)this[11].Ptr;
  while ( Ptr != (PnpDeviceWatcher *)&this[11] )
  {
    v22 = Ptr;
    v23 = Ptr;
    Ptr = *(PnpDeviceWatcher **)Ptr;
    CurrentMilliSecTime = QpcTimeConverter::GetCurrentMilliSecTime((QpcTimeConverter *)&this[14]);
    v25 = *((_DWORD *)v23 + 6);
    if ( CurrentMilliSecTime < v25 )
    {
      v39 = v25 - CurrentMilliSecTime;
      if ( *a2 > v39 )
        *a2 = v39;
    }
    else
    {
      *((_DWORD *)v23 + 6) = CurrentMilliSecTime + 100;
      string = 0;
      v26 = (PnpDevice *)*((_QWORD *)v23 + 2);
      WindowsDeleteString(0);
      string = 0;
      InterfacePath = PnpDevice::GetInterfacePath(v26, &string);
      v28 = InterfacePath;
      if ( InterfacePath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\rawinputproviders\\lamparray\\lib\\pnpdevicewatcher.cpp",
          (const char *)(unsigned int)InterfacePath,
          v41);
        WindowsDeleteString(string);
        string = 0;
        std::unique_ptr<PnpDeviceWatcher::NotificationListEntry>::~unique_ptr<PnpDeviceWatcher::NotificationListEntry>(&v46);
        return v28;
      }
      v29 = PnpDevice::OpenInterface(*((PnpDevice **)v23 + 2));
      if ( v29 < 0 )
      {
        if ( v29 == -2147024864 )
        {
          if ( (unsigned int)dword_180241248 > 5 )
          {
            LOWORD(v44) = *((_WORD *)v23 + 14);
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            v42 = "Failed to exclusively open LampArray";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<2>>(
              v35,
              (unsigned int)&unk_180207360,
              v36,
              v37,
              (__int64)&v42,
              (__int64)&StringRawBuffer,
              (__int64)&v44);
          }
          v38 = *((_WORD *)v23 + 14);
          if ( v38 > 0 )
          {
            *((_WORD *)v23 + 14) = v38 - 1;
            if ( *a2 > 0x64 )
              *a2 = 100;
            goto LABEL_82;
          }
        }
      }
      else
      {
        LampArrayRawInputProvider::OnLampArrayAdded(
          (LampArrayRawInputProvider *)this->Ptr,
          *((struct PnpDevice **)v23 + 2));
        if ( (unsigned int)dword_180241248 > 5 )
        {
          v44 = (struct PnpDeviceWatcher::DeviceListEntry *)WindowsGetStringRawBuffer(string, 0);
          StringRawBuffer = (PCWSTR)"Successfully exclusively opened LampArray";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_180241248,
            (unsigned int)byte_1802073C5,
            v31,
            v32,
            (__int64)&StringRawBuffer,
            (__int64)&v44);
        }
      }
      v33 = *(PnpDeviceWatcher **)v22;
      if ( *(PnpDeviceWatcher **)(*(_QWORD *)v22 + 8LL) != v23 )
        goto LABEL_48;
      v34 = (PnpDeviceWatcher **)*((_QWORD *)v23 + 1);
      if ( *v34 != v23 )
        goto LABEL_48;
      *v34 = v33;
      *((_QWORD *)v33 + 1) = v34;
      --LODWORD(this[13].Ptr);
      PnpDeviceWatcher::RetryDeviceListEntry::`scalar deleting destructor'(v23, v30);
LABEL_82:
      WindowsDeleteString(string);
    }
  }
  std::unique_ptr<PnpDeviceWatcher::NotificationListEntry>::~unique_ptr<PnpDeviceWatcher::NotificationListEntry>(&v46);
  return 0;
}

```

## disassembly

```asm
0x18005ca58  push    rbp
0x18005ca5a  push    rbx
0x18005ca5b  push    rsi
0x18005ca5c  push    rdi
0x18005ca5d  push    r12
0x18005ca5f  push    r13
0x18005ca61  push    r14
0x18005ca63  push    r15
0x18005ca65  mov     rbp, rsp
0x18005ca68  sub     rsp, 58h
0x18005ca6c  mov     r13, rdx
0x18005ca6f  mov     r15, rcx
0x18005ca72  mov     dword ptr [rdx], 0FFFFFFFFh
0x18005ca78  xor     edi, edi
0x18005ca7a  mov     ebx, edi
0x18005ca7c  lea     r12, [rcx+20h]
0x18005ca80  jmp     loc_18005CD7B
0x18005ca85  cmp     [rax+8], r14
0x18005ca89  jnz     loc_18005CD8C
0x18005ca8f  mov     [r12], rax
0x18005ca93  mov     [rax+8], r12
0x18005ca97  cmp     r14, r12
0x18005ca9a  jz      short loc_18005CAA3
0x18005ca9c  dec     dword ptr [r12+10h]
0x18005caa1  jmp     short loc_18005CAA6
0x18005caa3  mov     r14, rdi
0x18005caa6  mov     rcx, rbx; this
0x18005caa9  mov     rbx, r14
0x18005caac  mov     [rbp+arg_10], rbx
0x18005cab0  test    rcx, rcx
0x18005cab3  jz      short loc_18005CABA
0x18005cab5  call    ??_GNotificationListEntry@PnpDeviceWatcher@@QEAAPEAXI@Z; PnpDeviceWatcher::NotificationListEntry::`scalar deleting destructor'(uint)
0x18005caba  test    r14, r14
0x18005cabd  jz      loc_18005CEE0
0x18005cac3  mov     [rbp+arg_0], rdi
0x18005cac7  mov     ecx, [r14+18h]
0x18005cacb  test    ecx, ecx
0x18005cacd  jz      loc_18005CE25
0x18005cad3  sub     ecx, 1
0x18005cad6  jz      loc_18005CD93
0x18005cadc  sub     ecx, 1
0x18005cadf  jz      loc_18005CCD7
0x18005cae5  sub     ecx, 1
0x18005cae8  jz      loc_18005CC40
0x18005caee  sub     ecx, 1
0x18005caf1  jz      loc_18005CBA7
0x18005caf7  sub     ecx, 1
0x18005cafa  jz      short loc_18005CB0F
0x18005cafc  sub     ecx, 1
0x18005caff  jz      short loc_18005CB0F
0x18005cb01  sub     ecx, 1
0x18005cb04  jz      short loc_18005CB0F
0x18005cb06  cmp     ecx, 1
0x18005cb09  jnz     loc_18005CD7B
0x18005cb0f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005cb16  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cb1b  test    al, al
0x18005cb1d  jz      short loc_18005CB6D
0x18005cb1f  lea     rdi, [r15+38h]
0x18005cb23  mov     rcx, rdi; SRWLock
0x18005cb26  call    cs:__imp_AcquireSRWLockExclusive
0x18005cb2c  mov     [rbp+string], rdi
0x18005cb30  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cb34  xor     r8d, r8d; bool
0x18005cb37  mov     rdx, [r14+20h]; HSTRING
0x18005cb3b  mov     rcx, r15; this
0x18005cb3e  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cb43  mov     edi, eax
0x18005cb45  mov     rsi, [rbp+arg_0]
0x18005cb49  test    eax, eax
0x18005cb4b  js      short loc_18005CB5F
0x18005cb4d  test    rsi, rsi
0x18005cb50  jz      short loc_18005CB5F
0x18005cb52  mov     edx, [r14+18h]
0x18005cb56  mov     rcx, [rsi+10h]
0x18005cb5a  call    ?OnPnpNotification@PnpDevice@@QEAAXW4DeviceEventId@PnpApiWrapper@@@Z; PnpDevice::OnPnpNotification(PnpApiWrapper::DeviceEventId)
0x18005cb5f  lea     rcx, [rbp+string]
0x18005cb63  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005cb68  jmp     loc_18005CE83
0x18005cb6d  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cb71  xor     r8d, r8d; bool
0x18005cb74  mov     rdx, [r14+20h]; HSTRING
0x18005cb78  mov     rcx, r15; this
0x18005cb7b  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cb80  test    eax, eax
0x18005cb82  js      loc_18005CE1F
0x18005cb88  mov     rcx, [rbp+arg_0]
0x18005cb8c  test    rcx, rcx
0x18005cb8f  jz      loc_18005CD7B
0x18005cb95  mov     edx, [r14+18h]
0x18005cb99  mov     rcx, [rcx+10h]
0x18005cb9d  call    ?OnPnpNotification@PnpDevice@@QEAAXW4DeviceEventId@PnpApiWrapper@@@Z; PnpDevice::OnPnpNotification(PnpApiWrapper::DeviceEventId)
0x18005cba2  jmp     loc_18005CD7B
0x18005cba7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005cbae  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cbb3  test    al, al
0x18005cbb5  jz      short loc_18005CC06
0x18005cbb7  lea     rdi, [r15+38h]
0x18005cbbb  mov     rcx, rdi; SRWLock
0x18005cbbe  call    cs:__imp_AcquireSRWLockExclusive
0x18005cbc4  mov     [rbp+string], rdi
0x18005cbc8  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cbcc  xor     r8d, r8d; bool
0x18005cbcf  mov     rdx, [r14+20h]; HSTRING
0x18005cbd3  mov     rcx, r15; this
0x18005cbd6  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cbdb  mov     edi, eax
0x18005cbdd  mov     rsi, [rbp+arg_0]
0x18005cbe1  test    eax, eax
0x18005cbe3  js      loc_18005CB5F
0x18005cbe9  test    rsi, rsi
0x18005cbec  jz      loc_18005CB5F
0x18005cbf2  mov     rdx, [r14+20h]; string1
0x18005cbf6  mov     rcx, [rsi+10h]; this
0x18005cbfa  call    ?RemoveInterface@PnpDevice@@AEAAJPEAUHSTRING__@@@Z; PnpDevice::RemoveInterface(HSTRING__ *)
0x18005cbff  mov     edi, eax
0x18005cc01  jmp     loc_18005CB5F
0x18005cc06  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cc0a  xor     r8d, r8d; bool
0x18005cc0d  mov     rdx, [r14+20h]; HSTRING
0x18005cc11  mov     rcx, r15; this
0x18005cc14  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cc19  test    eax, eax
0x18005cc1b  js      loc_18005CE1F
0x18005cc21  mov     rsi, [rbp+arg_0]
0x18005cc25  test    rsi, rsi
0x18005cc28  jz      loc_18005CD7B
0x18005cc2e  mov     rdx, [r14+20h]; string1
0x18005cc32  mov     rcx, [rsi+10h]; this
0x18005cc36  call    ?RemoveInterface@PnpDevice@@AEAAJPEAUHSTRING__@@@Z; PnpDevice::RemoveInterface(HSTRING__ *)
0x18005cc3b  jmp     loc_18005CE81
0x18005cc40  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005cc47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cc4c  test    al, al
0x18005cc4e  jz      short loc_18005CC9D
0x18005cc50  lea     rdi, [r15+38h]
0x18005cc54  mov     rcx, rdi; SRWLock
0x18005cc57  call    cs:__imp_AcquireSRWLockExclusive
0x18005cc5d  mov     [rbp+string], rdi
0x18005cc61  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cc65  mov     r8b, 1; bool
0x18005cc68  mov     rdx, [r14+20h]; HSTRING
0x18005cc6c  mov     rcx, r15; this
0x18005cc6f  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cc74  mov     edi, eax
0x18005cc76  mov     rsi, [rbp+arg_0]
0x18005cc7a  test    eax, eax
0x18005cc7c  js      loc_18005CB5F
0x18005cc82  test    rsi, rsi
0x18005cc85  jz      loc_18005CB5F
0x18005cc8b  mov     rdx, [r14+20h]; HSTRING
0x18005cc8f  mov     rcx, [rsi+10h]; this
0x18005cc93  call    ?AddInterface@PnpDevice@@AEAAJPEAUHSTRING__@@@Z; PnpDevice::AddInterface(HSTRING__ *)
0x18005cc98  jmp     loc_18005CBFF
0x18005cc9d  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cca1  mov     r8b, 1; bool
0x18005cca4  mov     rdx, [r14+20h]; HSTRING
0x18005cca8  mov     rcx, r15; this
0x18005ccab  call    ?FindDeviceListEntryByInterfacePath@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInterfacePath(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005ccb0  test    eax, eax
0x18005ccb2  js      loc_18005CE1F
0x18005ccb8  mov     rsi, [rbp+arg_0]
0x18005ccbc  test    rsi, rsi
0x18005ccbf  jz      loc_18005CD7B
0x18005ccc5  mov     rdx, [r14+20h]; HSTRING
0x18005ccc9  mov     rcx, [rsi+10h]; this
0x18005cccd  call    ?AddInterface@PnpDevice@@AEAAJPEAUHSTRING__@@@Z; PnpDevice::AddInterface(HSTRING__ *)
0x18005ccd2  jmp     loc_18005CE81
0x18005ccd7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005ccde  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cce3  test    al, al
0x18005cce5  jz      short loc_18005CD3E
0x18005cce7  lea     rdi, [r15+38h]
0x18005cceb  mov     rcx, rdi; SRWLock
0x18005ccee  call    cs:__imp_AcquireSRWLockExclusive
0x18005ccf4  mov     [rbp+string], rdi
0x18005ccf8  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005ccfc  xor     r8d, r8d; bool
0x18005ccff  mov     rdx, [r14+20h]; HSTRING
0x18005cd03  mov     rcx, r15; this
0x18005cd06  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cd0b  mov     edi, eax
0x18005cd0d  mov     rsi, [rbp+arg_0]
0x18005cd11  test    eax, eax
0x18005cd13  js      loc_18005CB5F
0x18005cd19  test    rsi, rsi
0x18005cd1c  jz      loc_18005CB5F
0x18005cd22  mov     rdx, rsi; struct PnpDeviceWatcher::DeviceListEntry *
0x18005cd25  mov     rcx, r15; this
0x18005cd28  call    ?StopDeviceObject@PnpDeviceWatcher@@AEAAXAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StopDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18005cd2d  lea     rcx, [r15+40h]
0x18005cd31  mov     rdx, rsi
0x18005cd34  call    ?Erase@?$NtList@UDeviceListEntry@PnpDeviceWatcher@@@@QEAAXPEAUDeviceListEntry@PnpDeviceWatcher@@@Z; NtList<PnpDeviceWatcher::DeviceListEntry>::Erase(PnpDeviceWatcher::DeviceListEntry *)
0x18005cd39  jmp     loc_18005CB5F
0x18005cd3e  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cd42  xor     r8d, r8d; bool
0x18005cd45  mov     rdx, [r14+20h]; HSTRING
0x18005cd49  mov     rcx, r15; this
0x18005cd4c  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cd51  test    eax, eax
0x18005cd53  js      loc_18005CE1F
0x18005cd59  mov     rdi, [rbp+arg_0]
0x18005cd5d  test    rdi, rdi
0x18005cd60  jz      short loc_18005CD79
0x18005cd62  mov     rdx, rdi; struct PnpDeviceWatcher::DeviceListEntry *
0x18005cd65  mov     rcx, r15; this
0x18005cd68  call    ?StopDeviceObject@PnpDeviceWatcher@@AEAAXAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StopDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18005cd6d  lea     rcx, [r15+40h]
0x18005cd71  mov     rdx, rdi
0x18005cd74  call    ?Erase@?$NtList@UDeviceListEntry@PnpDeviceWatcher@@@@QEAAXPEAUDeviceListEntry@PnpDeviceWatcher@@@Z; NtList<PnpDeviceWatcher::DeviceListEntry>::Erase(PnpDeviceWatcher::DeviceListEntry *)
0x18005cd79  xor     edi, edi
0x18005cd7b  mov     r14, [r12]
0x18005cd7f  cmp     [r14+8], r12
0x18005cd83  mov     rax, [r14]
0x18005cd86  jz      loc_18005CA85
0x18005cd8c  mov     ecx, 3
0x18005cd91  int     29h; Win8: RtlFailFast(ecx)
0x18005cd93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005cd9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cd9f  test    al, al
0x18005cda1  jz      short loc_18005CDEE
0x18005cda3  lea     rdi, [r15+38h]
0x18005cda7  mov     rcx, rdi; SRWLock
0x18005cdaa  call    cs:__imp_AcquireSRWLockExclusive
0x18005cdb0  mov     [rbp+string], rdi
0x18005cdb4  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cdb8  mov     r8b, 1; bool
0x18005cdbb  mov     rdx, [r14+20h]; HSTRING
0x18005cdbf  mov     rcx, r15; this
0x18005cdc2  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005cdc7  mov     edi, eax
0x18005cdc9  mov     rsi, [rbp+arg_0]
0x18005cdcd  test    eax, eax
0x18005cdcf  js      loc_18005CB5F
0x18005cdd5  test    rsi, rsi
0x18005cdd8  jz      loc_18005CB5F
0x18005cdde  mov     rdx, rsi; struct PnpDeviceWatcher::DeviceListEntry *
0x18005cde1  mov     rcx, r15; this
0x18005cde4  call    ?StartDeviceObject@PnpDeviceWatcher@@AEAAJAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StartDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18005cde9  jmp     loc_18005CBFF
0x18005cdee  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005cdf2  mov     r8b, 1; bool
0x18005cdf5  mov     rdx, [r14+20h]; HSTRING
0x18005cdf9  mov     rcx, r15; this
0x18005cdfc  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005ce01  test    eax, eax
0x18005ce03  js      short loc_18005CE1F
0x18005ce05  mov     rsi, [rbp+arg_0]
0x18005ce09  test    rsi, rsi
0x18005ce0c  jz      loc_18005CD7B
0x18005ce12  mov     rdx, rsi; struct PnpDeviceWatcher::DeviceListEntry *
0x18005ce15  mov     rcx, r15; this
0x18005ce18  call    ?StartDeviceObject@PnpDeviceWatcher@@AEAAJAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StartDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18005ce1d  jmp     short loc_18005CE81
0x18005ce1f  mov     rsi, [rbp+arg_0]
0x18005ce23  jmp     short loc_18005CE8D
0x18005ce25  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005ce2c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005ce31  test    al, al
0x18005ce33  jz      short loc_18005CE6A
0x18005ce35  lea     rdi, [r15+38h]
0x18005ce39  mov     rcx, rdi; SRWLock
0x18005ce3c  call    cs:__imp_AcquireSRWLockExclusive
0x18005ce42  mov     [rbp+string], rdi
0x18005ce46  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005ce4a  mov     r8b, 1; bool
0x18005ce4d  mov     rdx, [r14+20h]; HSTRING
0x18005ce51  mov     rcx, r15; this
0x18005ce54  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005ce59  mov     edi, eax
0x18005ce5b  lea     rcx, [rbp+string]
0x18005ce5f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005ce64  mov     rsi, [rbp+arg_0]
0x18005ce68  jmp     short loc_18005CE83
0x18005ce6a  lea     r9, [rbp+arg_0]; struct PnpDeviceWatcher::DeviceListEntry **
0x18005ce6e  mov     r8b, 1; bool
0x18005ce71  mov     rdx, [r14+20h]; HSTRING
0x18005ce75  mov     rcx, r15; this
0x18005ce78  call    ?FindDeviceListEntryByInstanceId@PnpDeviceWatcher@@AEAAJPEAUHSTRING__@@_NAEAPEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::FindDeviceListEntryByInstanceId(HSTRING__ *,bool,PnpDeviceWatcher::DeviceListEntry * &)
0x18005ce7d  mov     rsi, [rbp+arg_0]
0x18005ce81  mov     edi, eax
0x18005ce83  test    edi, edi
0x18005ce85  jns     loc_18005CD79
0x18005ce8b  xor     edi, edi
0x18005ce8d  test    rsi, rsi
0x18005ce90  jz      loc_18005CD7B
0x18005ce96  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DLSDOCF@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF> `wil::Feature<__WilFeatureTraits_Feature_DLSDOCF>::GetImpl(void)'::`2'::impl
0x18005ce9d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DLSDOCF@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DLSDOCF>::__private_IsEnabled(void)
0x18005cea2  test    al, al
0x18005cea4  jz      short loc_18005CED0
0x18005cea6  lea     rdi, [r15+38h]
0x18005ceaa  mov     rcx, rdi; SRWLock
0x18005cead  call    cs:__imp_AcquireSRWLockExclusive
0x18005ceb3  mov     [rbp+arg_0], rdi
0x18005ceb7  mov     rdx, rsi; struct PnpDeviceWatcher::DeviceListEntry *
0x18005ceba  mov     rcx, r15; this
0x18005cebd  call    ?StopDeviceObject@PnpDeviceWatcher@@AEAAXAEAUDeviceListEntry@1@@Z; PnpDeviceWatcher::StopDeviceObject(PnpDeviceWatcher::DeviceListEntry &)
0x18005cec2  lea     rcx, [rbp+arg_0]
0x18005cec6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18005cecb  jmp     loc_18005CD79
  ... truncated ...
```
