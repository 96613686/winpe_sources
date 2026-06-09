# InterfaceProfileKnobCollection::Open(ulong,KnobTransaction &)

- ea: `0x1401677d0`
- end: `0x14016805f`
- name: `?Open@InterfaceProfileKnobCollection@@UEBAJKAEAUKnobTransaction@@@Z`
- size: `2191`
- prototype: `int(InterfaceProfileKnobCollection *__hidden this, unsigned int, struct KnobTransaction *)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x14001cf60`
- `0x14002ab60`
- `0x14005a250`
- `0x140070990`
- `0x140073020`
- `0x1400cfe0c`
- `0x1400eb380`
- `0x140164fe0`
- `0x140165230`
- `0x1401677d0`
- `0x1401684e0`
- `0x140168c60`
- `0x1401690b0`
- `0x1401690f0`
- `0x140169770`
- `0x140169a00`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1401678ff`
- `ntoskrnl!ZwOpenKey` at `0x1401678ff`
- `ntoskrnl!ZwClose` at `0x14016791c`
- `ntoskrnl!ZwClose` at `0x140167a87`
- `ntoskrnl!ZwClose` at `0x140167bca`
- `ntoskrnl!ZwClose` at `0x140167c1d`
- `ntoskrnl!ZwClose` at `0x140167c96`
- `ntoskrnl!ZwClose` at `0x140167cc7`
- `ntoskrnl!ZwClose` at `0x140167e97`
- `ntoskrnl!ZwClose` at `0x140167f24`
- `ntoskrnl!ZwClose` at `0x140167faf`
- `ntoskrnl!ZwClose` at `0x140168014`
- `ntoskrnl!ZwClose` at `0x14016791c`
- `ntoskrnl!ZwClose` at `0x140167a87`
- `ntoskrnl!ZwClose` at `0x140167bca`
- `ntoskrnl!ZwClose` at `0x140167c1d`
- `ntoskrnl!ZwClose` at `0x140167c96`
- `ntoskrnl!ZwClose` at `0x140167cc7`
- `ntoskrnl!ZwClose` at `0x140167e97`
- `ntoskrnl!ZwClose` at `0x140167f24`
- `ntoskrnl!ZwClose` at `0x140167faf`
- `ntoskrnl!ZwClose` at `0x140168014`
- `ntoskrnl!ExFreePoolWithTag` at `0x140167c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140167f0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140167c07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140167f0e`

## pseudocode

```c
__int64 __fastcall InterfaceProfileKnobCollection::Open(
        InterfaceProfileKnobCollection *this,
        unsigned int a2,
        struct KnobTransaction *a3)
{
  struct KnobTransaction *v3; // rdi
  __int64 result; // rax
  __int64 v7; // r12
  _BYTE *v8; // r15
  wchar_t *v9; // rax
  __int64 v10; // r14
  __int64 v11; // rcx
  int v12; // r13d
  NTSTATUS v13; // esi
  int v14; // edx
  int v15; // r9d
  HANDLE v16; // rcx
  const wchar_t *v17; // rax
  void *v18; // r9
  __int16 v19; // r14
  int v20; // edx
  int v21; // ebx
  PVOID v22; // rcx
  const wchar_t *v23; // rax
  __int64 v24; // rdx
  int v25; // r12d
  void *v26; // r9
  struct _UNICODE_STRING *v27; // r8
  const wchar_t *v28; // rax
  __int64 v29; // rcx
  int v30; // edx
  int v31; // eax
  const wchar_t *v32; // rax
  struct Rtl::KString *v33; // rax
  __int16 v34; // r14
  int v35; // edx
  int v36; // edx
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  wchar_t v44[256]; // [rsp+B0h] [rbp-50h] BYREF

  v3 = a3;
  result = RegistryKnobCollection::Open(this, a2, a3);
  if ( (int)result < 0 )
    return result;
  *((_BYTE *)v3 + 16) = 0;
  v7 = *((_QWORD *)this + 3) + 12LL;
  v8 = (char *)v3 + 16;
  Handle = 0;
  v42 = v7;
  netsetupBuildObjectPath(2, v7, 0, 1, v44);
  v9 = v44;
  v10 = 0x7FFF;
  v39 = 0;
  v11 = 0x7FFF;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v11;
  }
  while ( v11 );
  v12 = -1073741811;
  v13 = -1073741811;
  if ( v11 )
  {
    KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    v39.Length = -2 - 2 * v11;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    v39.MaximumLength = -2 * v11;
    *(_QWORD *)&ObjectAttributes.Attributes = 576;
    v39.Buffer = v44;
    ObjectAttributes.ObjectName = &v39;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v13 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
    Handle = KeyHandle;
    v7 = v42;
  }
  if ( v13 == -1073741772 )
  {
    netsetupBuildObjectPath(2, v7, 1, 1, v44);
    v13 = KRegKey::Open((KRegKey *)&Handle, 1u, v44, 0);
  }
  if ( v13 < 0 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF__guid_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        0,
        1,
        10,
        (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
        v7,
        1,
        v13);
    goto LABEL_20;
  }
  v40 = 0;
  P = 0;
  KeyHandle = &Handle;
  v13 = NetSetupPropertyBag::ReadString(&KeyHandle, &NETSETUPPKEY_Operational_ExecutionContextProfile, &P);
  if ( v13 < 0 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v15 = 11;
LABEL_18:
      LOBYTE(v14) = 3;
      WPP_RECORDER_SF__guid_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v14,
        1,
        v15,
        (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
        v7,
        v13);
      goto LABEL_19;
    }
    goto LABEL_19;
  }
  v13 = NetSetupPropertyBag::ReadUint32(
          (NetSetupPropertyBag *)&KeyHandle,
          (const struct _NETSETUPPROPKEY *)&NETSETUPPKEY_Operational_ExecutionContextProfileSource,
          &v40);
  if ( v13 < 0 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v15 = 12;
      goto LABEL_18;
    }
LABEL_19:
    wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
LABEL_20:
    if ( Handle )
      ZwClose(Handle);
    return (unsigned int)v13;
  }
  if ( v40 && v40 != 3 )
  {
    if ( v40 != 2 )
    {
      wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
      v16 = Handle;
      if ( !Handle )
        return 3221225524LL;
LABEL_49:
      ZwClose(v16);
      return 3221225524LL;
    }
    if ( !*(_WORD *)P )
    {
      wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
      v16 = Handle;
      if ( !Handle )
        return 3221225524LL;
      goto LABEL_49;
    }
    v39 = 0;
    v17 = L"Reserved\\ExecutionContextProfiles";
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v10;
    }
    while ( v10 );
    if ( v10 )
    {
      v18 = *(void **)v3;
      v39.Buffer = (wchar_t *)L"Reserved\\ExecutionContextProfiles";
      v19 = 2 * v10;
      v39.Length = -2 - v19;
      v39.MaximumLength = -v19;
      v12 = KRegKey::Open((KRegKey *)v3, a2, &v39, v18);
      if ( v12 >= 0 )
      {
        v21 = KRegKey::Open((KRegKey *)v3, a2, (const struct _UNICODE_STRING *)P, *(void **)v3);
        if ( v21 < 0 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 3;
            WPP_RECORDER_SF__guid_d(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v20,
              1,
              18,
              (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
              v7,
              v21);
          }
          wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
          if ( Handle )
          {
            ZwClose(Handle);
            return (unsigned int)v21;
          }
          return (unsigned int)v21;
        }
        v3 = (struct KnobTransaction *)((char *)v3 + 8);
LABEL_40:
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          v3,
          0);
        v22 = P;
        *v8 = 1;
        P = 0;
        if ( v22 )
          ExFreePoolWithTag(v22, 0x7274534Bu);
        if ( Handle )
          ZwClose(Handle);
        return 0;
      }
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 3;
      WPP_RECORDER_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v14,
        1,
        17,
        (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
        v12);
    }
    wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
    goto LABEL_83;
  }
  if ( (a2 & 2) != 0 )
  {
    wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
    if ( Handle )
      ZwClose(Handle);
    return 3221225506LL;
  }
  v39 = 0;
  v23 = L"Reserved\\ExecutionContextProfiles";
  v24 = 0x7FFF;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v24;
  }
  while ( v24 );
  v25 = -1073741811;
  if ( v24 )
  {
    v26 = (void *)*((_QWORD *)v3 + 1);
    v39.Buffer = (wchar_t *)L"Reserved\\ExecutionContextProfiles";
    v39.Length = -2 - 2 * v24;
    v39.MaximumLength = -2 * v24;
    v25 = KRegKey::Open((KRegKey *)v3 + 1, a2, &v39, v26);
    if ( v25 >= 0 )
    {
      v27 = (struct _UNICODE_STRING *)P;
      if ( !*(_WORD *)P )
      {
        v39 = 0;
        v28 = L"DefaultProfile";
        v29 = 0x7FFF;
        do
        {
          if ( !*v28 )
            break;
          ++v28;
          --v29;
        }
        while ( v29 );
        v30 = 0;
        if ( v29 )
        {
          v39.Buffer = L"DefaultProfile";
          v39.Length = -2 - 2 * v29;
          v39.MaximumLength = -2 * v29;
          v31 = KRegKey::QueryValueString((char *)v3 + 8, &v39, &P);
          v27 = (struct _UNICODE_STRING *)P;
          v12 = v31;
          v30 = 0;
        }
        if ( v12 == -1073741772 )
        {
          v39 = 0;
          v32 = L"Balanced";
          while ( *v32 )
          {
            ++v32;
            if ( !--v10 )
            {
              v33 = 0;
              goto LABEL_72;
            }
          }
          v34 = 2 * v10;
          v39.Buffer = (wchar_t *)L"Balanced";
          v39.Length = -2 - v34;
          v39.MaximumLength = -v34;
          v33 = Rtl::KString::Initialize(&v39);
LABEL_72:
          wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, v33);
          v27 = (struct _UNICODE_STRING *)P;
          if ( !P )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v35) = 3;
              WPP_RECORDER_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v35,
                1,
                14,
                (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids);
            }
            wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
            if ( Handle )
              ZwClose(Handle);
            return 3221225626LL;
          }
        }
        else if ( v12 < 0 )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v30) = 3;
            WPP_RECORDER_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v30,
              1,
              15,
              (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
              v12);
            v27 = (struct _UNICODE_STRING *)P;
          }
          P = 0;
          if ( v27 )
            ExFreePoolWithTag(v27, 0x7274534Bu);
LABEL_83:
          if ( Handle )
            ZwClose(Handle);
          return (unsigned int)v12;
        }
      }
      v21 = KRegKey::Open((KRegKey *)v3 + 1, a2, v27, *((void **)v3 + 1));
      if ( v21 < 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v36) = 3;
          WPP_RECORDER_SF__guid_d(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v36,
            1,
            16,
            (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
            v42,
            v21);
        }
        wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
        if ( Handle )
          ZwClose(Handle);
        return (unsigned int)v21;
      }
      goto LABEL_40;
    }
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v24) = 3;
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v24,
      1,
      13,
      (struct _GUID *)&WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids,
      v25);
  }
  wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(&P, 0);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1401677d0  push    rbp
0x1401677d2  push    rbx
0x1401677d3  push    rsi
0x1401677d4  push    rdi
0x1401677d5  lea     rbp, [rsp-1D8h]
0x1401677dd  sub     rsp, 2D8h
0x1401677e4  mov     rax, cs:__security_cookie
0x1401677eb  xor     rax, rsp
0x1401677ee  mov     [rbp+1F0h+var_40], rax
0x1401677f5  mov     rdi, r8
0x1401677f8  mov     ebx, edx
0x1401677fa  mov     rsi, rcx
0x1401677fd  call    ?Open@RegistryKnobCollection@@UEBAJKAEAUKnobTransaction@@@Z; RegistryKnobCollection::Open(ulong,KnobTransaction &)
0x140167802  test    eax, eax
0x140167804  js      loc_140168043
0x14016780a  mov     [rsp+2F0h+arg_18], r12
0x140167812  lea     rax, [rbp+1F0h+var_240]
0x140167816  mov     [rsp+2F0h+var_20], r13
0x14016781e  mov     r9d, 1
0x140167824  mov     byte ptr [rdi+10h], 0
0x140167828  xor     r8d, r8d
0x14016782b  mov     r12, [rsi+18h]
0x14016782f  mov     ecx, 2
0x140167834  add     r12, 0Ch
0x140167838  mov     [rsp+2F0h+var_28], r14
0x140167840  mov     [rsp+2F0h+var_30], r15
0x140167848  mov     rdx, r12
0x14016784b  lea     r15, [rdi+10h]
0x14016784f  mov     [rsp+2F0h+Handle], 0
0x140167858  mov     [rsp+2F0h+var_280], r12
0x14016785d  mov     [rsp+2F0h+var_2D0], rax
0x140167862  call    ?netsetupBuildObjectPath@@YAXW4_NETSETUP_OBJECT_TYPE@@AEBU_GUID@@W4NetSetupStoreType@@W4NetSetupSubkeyType@@PEA_W@Z; netsetupBuildObjectPath(_NETSETUP_OBJECT_TYPE,_GUID const &,NetSetupStoreType,NetSetupSubkeyType,wchar_t *)
0x140167867  xorps   xmm0, xmm0
0x14016786a  lea     rax, [rbp+1F0h+var_240]
0x14016786e  mov     r14d, 7FFFh
0x140167874  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x140167879  mov     ecx, r14d
0x14016787c  cmp     word ptr [rax], 0
0x140167880  jz      short loc_14016788C
0x140167882  add     rax, 2
0x140167886  sub     rcx, 1
0x14016788a  jnz     short loc_14016787C
0x14016788c  xor     edx, edx
0x14016788e  mov     r13d, 0C000000Dh
0x140167894  test    rcx, rcx
0x140167897  mov     esi, r13d
0x14016789a  mov     eax, 0FFFEh
0x14016789f  cmovnz  esi, edx
0x1401678a2  jz      loc_140167934
0x1401678a8  add     cx, cx
0x1401678ab  mov     [rsp+2F0h+KeyHandle], rdx
0x1401678b0  sub     ax, cx
0x1401678b3  mov     [rbp+1F0h+ObjectAttributes.RootDirectory], rdx
0x1401678b7  mov     [rsp+2F0h+var_2A0.Length], ax
0x1401678bc  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1401678c1  add     ax, 2
0x1401678c5  mov     qword ptr [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1401678ce  mov     [rsp+2F0h+var_2A0.MaximumLength], ax
0x1401678d3  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x1401678d8  lea     rax, [rbp+1F0h+var_240]
0x1401678dc  mov     qword ptr [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x1401678e4  mov     [rsp+2F0h+var_2A0.Buffer], rax
0x1401678e9  xorps   xmm0, xmm0
0x1401678ec  lea     rax, [rsp+2F0h+var_2A0]
0x1401678f1  mov     edx, 1; DesiredAccess
0x1401678f6  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x1401678fa  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1401678ff  call    cs:__imp_ZwOpenKey
0x140167906  nop     dword ptr [rax+rax+00h]
0x14016790b  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167910  mov     esi, eax
0x140167912  mov     r12, [rsp+2F0h+KeyHandle]
0x140167917  test    rcx, rcx
0x14016791a  jz      short loc_140167928
0x14016791c  call    cs:__imp_ZwClose
0x140167923  nop     dword ptr [rax+rax+00h]
0x140167928  mov     [rsp+2F0h+Handle], r12
0x14016792d  xor     edx, edx
0x14016792f  mov     r12, [rsp+2F0h+var_280]
0x140167934  cmp     esi, 0C0000034h
0x14016793a  jnz     short loc_140167975
0x14016793c  mov     r9d, 1
0x140167942  lea     rax, [rbp+1F0h+var_240]
0x140167946  mov     r8d, r9d
0x140167949  mov     [rsp+2F0h+var_2D0], rax
0x14016794e  mov     rdx, r12
0x140167951  mov     ecx, 2
0x140167956  call    ?netsetupBuildObjectPath@@YAXW4_NETSETUP_OBJECT_TYPE@@AEBU_GUID@@W4NetSetupStoreType@@W4NetSetupSubkeyType@@PEA_W@Z; netsetupBuildObjectPath(_NETSETUP_OBJECT_TYPE,_GUID const &,NetSetupStoreType,NetSetupSubkeyType,wchar_t *)
0x14016795b  xor     r9d, r9d; void *
0x14016795e  lea     r8, [rbp+1F0h+var_240]; wchar_t *
0x140167962  mov     edx, 1; unsigned int
0x140167967  lea     rcx, [rsp+2F0h+Handle]; this
0x14016796c  call    ?Open@KRegKey@@QEAAJKPEB_WPEAX@Z; KRegKey::Open(ulong,wchar_t const *,void *)
0x140167971  mov     esi, eax
0x140167973  xor     edx, edx; int
0x140167975  test    esi, esi
0x140167977  jns     short loc_1401679CB
0x140167979  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140167980  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140167987  jz      loc_140167A7D
0x14016798d  mov     rcx, cs:WPP_GLOBAL_Control
0x140167994  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x14016799b  mov     dword ptr [rsp+2F0h+var_2B8], esi; char
0x14016799f  mov     r9d, 0Ah; int
0x1401679a5  mov     dword ptr [rsp+2F0h+var_2C0], 1; char
0x1401679ad  mov     r8d, 1; int
0x1401679b3  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x1401679b8  mov     rcx, [rcx+40h]; int
0x1401679bc  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x1401679c1  call    WPP_RECORDER_SF__guid_Dd
0x1401679c6  jmp     loc_140167A7D
0x1401679cb  lea     rax, [rsp+2F0h+Handle]
0x1401679d0  mov     [rsp+2F0h+var_290], edx
0x1401679d4  mov     [rsp+2F0h+P], rdx
0x1401679d9  lea     r8, [rsp+2F0h+P]
0x1401679de  lea     rdx, NETSETUPPKEY_Operational_ExecutionContextProfile
0x1401679e5  mov     [rsp+2F0h+KeyHandle], rax
0x1401679ea  lea     rcx, [rsp+2F0h+KeyHandle]
0x1401679ef  call    ?ReadString@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@@Z; NetSetupPropertyBag::ReadString(_NETSETUPPROPKEY const &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &)
0x1401679f4  mov     esi, eax
0x1401679f6  test    eax, eax
0x1401679f8  jns     short loc_140167A12
0x1401679fa  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140167a01  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140167a08  jz      short loc_140167A71
0x140167a0a  mov     r9d, 0Bh
0x140167a10  jmp     short loc_140167A44
0x140167a12  lea     r8, [rsp+2F0h+var_290]; unsigned int *
0x140167a17  lea     rdx, NETSETUPPKEY_Operational_ExecutionContextProfileSource; struct _NETSETUPPROPKEY *
0x140167a1e  lea     rcx, [rsp+2F0h+KeyHandle]; this
0x140167a23  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x140167a28  mov     esi, eax
0x140167a2a  test    eax, eax
0x140167a2c  jns     short loc_140167A9A
0x140167a2e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140167a35  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140167a3c  jz      short loc_140167A71
0x140167a3e  mov     r9d, 0Ch; int
0x140167a44  mov     rcx, cs:WPP_GLOBAL_Control
0x140167a4b  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140167a52  mov     dword ptr [rsp+2F0h+var_2C0], esi; char
0x140167a56  mov     r8d, 1; int
0x140167a5c  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x140167a61  mov     dl, 3; int
0x140167a63  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140167a68  mov     rcx, [rcx+40h]; int
0x140167a6c  call    WPP_RECORDER_SF__guid_d
0x140167a71  xor     edx, edx
0x140167a73  lea     rcx, [rsp+2F0h+P]
0x140167a78  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167a7d  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167a82  test    rcx, rcx
0x140167a85  jz      short loc_140167A93
0x140167a87  call    cs:__imp_ZwClose
0x140167a8e  nop     dword ptr [rax+rax+00h]
0x140167a93  mov     eax, esi
0x140167a95  jmp     loc_140168023
0x140167a9a  mov     eax, [rsp+2F0h+var_290]
0x140167a9e  test    eax, eax
0x140167aa0  jz      loc_140167CAC
0x140167aa6  cmp     eax, 3
0x140167aa9  jz      loc_140167CAC
0x140167aaf  cmp     eax, 2
0x140167ab2  jnz     loc_140167C80
0x140167ab8  mov     rax, [rsp+2F0h+P]
0x140167abd  cmp     word ptr [rax], 0
0x140167ac1  jnz     short loc_140167AE7
0x140167ac3  xor     edx, edx
0x140167ac5  lea     rcx, [rsp+2F0h+P]
0x140167aca  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167acf  mov     rcx, [rsp+2F0h+Handle]
0x140167ad4  test    rcx, rcx
0x140167ad7  jnz     loc_140167C96
0x140167add  mov     eax, 0C0000034h
0x140167ae2  jmp     loc_140168023
0x140167ae7  xorps   xmm0, xmm0
0x140167aea  lea     rcx, aReservedExecut; "Reserved\\ExecutionContextProfiles"
0x140167af1  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x140167af6  mov     rax, rcx
0x140167af9  cmp     word ptr [rax], 0
0x140167afd  jz      short loc_140167B09
0x140167aff  add     rax, 2
0x140167b03  sub     r14, 1
0x140167b07  jnz     short loc_140167AF9
0x140167b09  xor     eax, eax
0x140167b0b  test    r14, r14
0x140167b0e  cmovnz  r13d, eax
0x140167b12  jz      loc_140167C30
0x140167b18  mov     r9, [rdi]; void *
0x140167b1b  lea     r8, [rsp+2F0h+var_2A0]; struct _UNICODE_STRING *
0x140167b20  mov     eax, 0FFFEh
0x140167b25  mov     [rsp+2F0h+var_2A0.Buffer], rcx
0x140167b2a  add     r14w, r14w
0x140167b2e  mov     edx, ebx; unsigned int
0x140167b30  sub     ax, r14w
0x140167b34  mov     rcx, rdi; this
0x140167b37  mov     [rsp+2F0h+var_2A0.Length], ax
0x140167b3c  add     ax, 2
0x140167b40  mov     [rsp+2F0h+var_2A0.MaximumLength], ax
0x140167b45  call    ?Open@KRegKey@@QEAAJKPEBU_UNICODE_STRING@@PEAX@Z; KRegKey::Open(ulong,_UNICODE_STRING const *,void *)
0x140167b4a  mov     r13d, eax
0x140167b4d  test    eax, eax
0x140167b4f  js      loc_140167C30
0x140167b55  mov     r9, [rdi]; void *
0x140167b58  mov     edx, ebx; unsigned int
0x140167b5a  mov     r8, [rsp+2F0h+P]; struct _UNICODE_STRING *
0x140167b5f  mov     rcx, rdi; this
0x140167b62  call    ?Open@KRegKey@@QEAAJKPEBU_UNICODE_STRING@@PEAX@Z; KRegKey::Open(ulong,_UNICODE_STRING const *,void *)
0x140167b67  mov     ebx, eax
0x140167b69  test    eax, eax
0x140167b6b  jns     short loc_140167BDD
0x140167b6d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140167b74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140167b7b  jz      short loc_140167BB0
0x140167b7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140167b84  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140167b8b  mov     dword ptr [rsp+2F0h+var_2C0], ebx; char
0x140167b8f  mov     r9d, 12h; int
0x140167b95  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x140167b9a  mov     r8d, 1; int
0x140167ba0  mov     dl, 3; int
0x140167ba2  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140167ba7  mov     rcx, [rcx+40h]; int
0x140167bab  call    WPP_RECORDER_SF__guid_d
0x140167bb0  xor     edx, edx
0x140167bb2  lea     rcx, [rsp+2F0h+P]
0x140167bb7  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167bbc  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167bc1  test    rcx, rcx
0x140167bc4  jz      loc_140167FBB
0x140167bca  call    cs:__imp_ZwClose
0x140167bd1  nop     dword ptr [rax+rax+00h]
0x140167bd6  mov     eax, ebx
0x140167bd8  jmp     loc_140168023
0x140167bdd  add     rdi, 8
0x140167be1  xor     edx, edx
0x140167be3  mov     rcx, rdi
0x140167be6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140167beb  mov     rcx, [rsp+2F0h+P]; P
0x140167bf0  mov     byte ptr [r15], 1
0x140167bf4  mov     [rsp+2F0h+P], 0
0x140167bfd  test    rcx, rcx
0x140167c00  jz      short loc_140167C13
0x140167c02  mov     edx, 7274534Bh; Tag
0x140167c07  call    cs:__imp_ExFreePoolWithTag
0x140167c0e  nop     dword ptr [rax+rax+00h]
0x140167c13  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167c18  test    rcx, rcx
0x140167c1b  jz      short loc_140167C29
0x140167c1d  call    cs:__imp_ZwClose
0x140167c24  nop     dword ptr [rax+rax+00h]
0x140167c29  xor     eax, eax
0x140167c2b  jmp     loc_140168023
0x140167c30  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140167c37  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140167c3e  jz      short loc_140167C6F
0x140167c40  mov     rcx, cs:WPP_GLOBAL_Control
0x140167c47  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140167c4e  mov     r9d, 11h; int
0x140167c54  mov     dword ptr [rsp+2F0h+var_2C8], r13d; char
0x140167c59  mov     r8d, 1; int
0x140167c5f  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140167c64  mov     dl, 3; int
0x140167c66  mov     rcx, [rcx+40h]; int
0x140167c6a  call    WPP_RECORDER_SF_d
0x140167c6f  xor     edx, edx
0x140167c71  lea     rcx, [rsp+2F0h+P]
0x140167c76  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167c7b  jmp     loc_140167F1A
0x140167c80  xor     edx, edx
0x140167c82  lea     rcx, [rsp+2F0h+P]
0x140167c87  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167c8c  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167c91  test    rcx, rcx
0x140167c94  jz      short loc_140167CA2
0x140167c96  call    cs:__imp_ZwClose
0x140167c9d  nop     dword ptr [rax+rax+00h]
0x140167ca2  mov     eax, 0C0000034h
0x140167ca7  jmp     loc_140168023
0x140167cac  test    bl, 2
0x140167caf  jz      short loc_140167CDD
0x140167cb1  xor     edx, edx
0x140167cb3  lea     rcx, [rsp+2F0h+P]
0x140167cb8  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140167cbd  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140167cc2  test    rcx, rcx
0x140167cc5  jz      short loc_140167CD3
0x140167cc7  call    cs:__imp_ZwClose
0x140167cce  nop     dword ptr [rax+rax+00h]
0x140167cd3  mov     eax, 0C0000022h
0x140167cd8  jmp     loc_140168023
0x140167cdd  xorps   xmm0, xmm0
0x140167ce0  lea     rcx, aReservedExecut; "Reserved\\ExecutionContextProfiles"
0x140167ce7  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x140167cec  mov     rax, rcx
0x140167cef  mov     rdx, r14
0x140167cf2  cmp     word ptr [rax], 0
0x140167cf6  jz      short loc_140167D02
0x140167cf8  add     rax, 2
0x140167cfc  sub     rdx, 1
  ... truncated ...
```
