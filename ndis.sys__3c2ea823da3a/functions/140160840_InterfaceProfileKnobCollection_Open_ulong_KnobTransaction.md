# InterfaceProfileKnobCollection::Open(ulong,KnobTransaction &)

- ea: `0x140160840`
- end: `0x1401610cf`
- name: `?Open@InterfaceProfileKnobCollection@@UEBAJKAEAUKnobTransaction@@@Z`
- size: `2191`
- prototype: `int(InterfaceProfileKnobCollection *__hidden this, unsigned int, struct KnobTransaction *)`
- caller_count: `0`
- callee_count: `16`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x140028e00`
- `0x140029620`
- `0x140055150`
- `0x14006b010`
- `0x14006d6a0`
- `0x1400cac5c`
- `0x1400e6160`
- `0x14015e050`
- `0x14015e2a0`
- `0x140160840`
- `0x140161550`
- `0x140161cd0`
- `0x140162120`
- `0x140162160`
- `0x1401627e0`
- `0x140162a70`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x14016096f`
- `ntoskrnl!ZwOpenKey` at `0x14016096f`
- `ntoskrnl!ZwClose` at `0x14016098c`
- `ntoskrnl!ZwClose` at `0x140160af7`
- `ntoskrnl!ZwClose` at `0x140160c3a`
- `ntoskrnl!ZwClose` at `0x140160c8d`
- `ntoskrnl!ZwClose` at `0x140160d06`
- `ntoskrnl!ZwClose` at `0x140160d37`
- `ntoskrnl!ZwClose` at `0x140160f07`
- `ntoskrnl!ZwClose` at `0x140160f94`
- `ntoskrnl!ZwClose` at `0x14016101f`
- `ntoskrnl!ZwClose` at `0x140161084`
- `ntoskrnl!ZwClose` at `0x14016098c`
- `ntoskrnl!ZwClose` at `0x140160af7`
- `ntoskrnl!ZwClose` at `0x140160c3a`
- `ntoskrnl!ZwClose` at `0x140160c8d`
- `ntoskrnl!ZwClose` at `0x140160d06`
- `ntoskrnl!ZwClose` at `0x140160d37`
- `ntoskrnl!ZwClose` at `0x140160f07`
- `ntoskrnl!ZwClose` at `0x140160f94`
- `ntoskrnl!ZwClose` at `0x14016101f`
- `ntoskrnl!ZwClose` at `0x140161084`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160c77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160f7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160c77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140160f7e`

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
0x140160840  push    rbp
0x140160842  push    rbx
0x140160843  push    rsi
0x140160844  push    rdi
0x140160845  lea     rbp, [rsp-1D8h]
0x14016084d  sub     rsp, 2D8h
0x140160854  mov     rax, cs:__security_cookie
0x14016085b  xor     rax, rsp
0x14016085e  mov     [rbp+1F0h+var_40], rax
0x140160865  mov     rdi, r8
0x140160868  mov     ebx, edx
0x14016086a  mov     rsi, rcx
0x14016086d  call    ?Open@RegistryKnobCollection@@UEBAJKAEAUKnobTransaction@@@Z; RegistryKnobCollection::Open(ulong,KnobTransaction &)
0x140160872  test    eax, eax
0x140160874  js      loc_1401610B3
0x14016087a  mov     [rsp+2F0h+arg_18], r12
0x140160882  lea     rax, [rbp+1F0h+var_240]
0x140160886  mov     [rsp+2F0h+var_20], r13
0x14016088e  mov     r9d, 1
0x140160894  mov     byte ptr [rdi+10h], 0
0x140160898  xor     r8d, r8d
0x14016089b  mov     r12, [rsi+18h]
0x14016089f  mov     ecx, 2
0x1401608a4  add     r12, 0Ch
0x1401608a8  mov     [rsp+2F0h+var_28], r14
0x1401608b0  mov     [rsp+2F0h+var_30], r15
0x1401608b8  mov     rdx, r12
0x1401608bb  lea     r15, [rdi+10h]
0x1401608bf  mov     [rsp+2F0h+Handle], 0
0x1401608c8  mov     [rsp+2F0h+var_280], r12
0x1401608cd  mov     [rsp+2F0h+var_2D0], rax
0x1401608d2  call    ?netsetupBuildObjectPath@@YAXW4_NETSETUP_OBJECT_TYPE@@AEBU_GUID@@W4NetSetupStoreType@@W4NetSetupSubkeyType@@PEA_W@Z; netsetupBuildObjectPath(_NETSETUP_OBJECT_TYPE,_GUID const &,NetSetupStoreType,NetSetupSubkeyType,wchar_t *)
0x1401608d7  xorps   xmm0, xmm0
0x1401608da  lea     rax, [rbp+1F0h+var_240]
0x1401608de  mov     r14d, 7FFFh
0x1401608e4  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x1401608e9  mov     ecx, r14d
0x1401608ec  cmp     word ptr [rax], 0
0x1401608f0  jz      short loc_1401608FC
0x1401608f2  add     rax, 2
0x1401608f6  sub     rcx, 1
0x1401608fa  jnz     short loc_1401608EC
0x1401608fc  xor     edx, edx
0x1401608fe  mov     r13d, 0C000000Dh
0x140160904  test    rcx, rcx
0x140160907  mov     esi, r13d
0x14016090a  mov     eax, 0FFFEh
0x14016090f  cmovnz  esi, edx
0x140160912  jz      loc_1401609A4
0x140160918  add     cx, cx
0x14016091b  mov     [rsp+2F0h+KeyHandle], rdx
0x140160920  sub     ax, cx
0x140160923  mov     [rbp+1F0h+ObjectAttributes.RootDirectory], rdx
0x140160927  mov     [rsp+2F0h+var_2A0.Length], ax
0x14016092c  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x140160931  add     ax, 2
0x140160935  mov     qword ptr [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x14016093e  mov     [rsp+2F0h+var_2A0.MaximumLength], ax
0x140160943  lea     rcx, [rsp+2F0h+KeyHandle]; KeyHandle
0x140160948  lea     rax, [rbp+1F0h+var_240]
0x14016094c  mov     qword ptr [rbp+1F0h+ObjectAttributes.Attributes], 240h
0x140160954  mov     [rsp+2F0h+var_2A0.Buffer], rax
0x140160959  xorps   xmm0, xmm0
0x14016095c  lea     rax, [rsp+2F0h+var_2A0]
0x140160961  mov     edx, 1; DesiredAccess
0x140160966  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x14016096a  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x14016096f  call    cs:__imp_ZwOpenKey
0x140160976  nop     dword ptr [rax+rax+00h]
0x14016097b  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160980  mov     esi, eax
0x140160982  mov     r12, [rsp+2F0h+KeyHandle]
0x140160987  test    rcx, rcx
0x14016098a  jz      short loc_140160998
0x14016098c  call    cs:__imp_ZwClose
0x140160993  nop     dword ptr [rax+rax+00h]
0x140160998  mov     [rsp+2F0h+Handle], r12
0x14016099d  xor     edx, edx
0x14016099f  mov     r12, [rsp+2F0h+var_280]
0x1401609a4  cmp     esi, 0C0000034h
0x1401609aa  jnz     short loc_1401609E5
0x1401609ac  mov     r9d, 1
0x1401609b2  lea     rax, [rbp+1F0h+var_240]
0x1401609b6  mov     r8d, r9d
0x1401609b9  mov     [rsp+2F0h+var_2D0], rax
0x1401609be  mov     rdx, r12
0x1401609c1  mov     ecx, 2
0x1401609c6  call    ?netsetupBuildObjectPath@@YAXW4_NETSETUP_OBJECT_TYPE@@AEBU_GUID@@W4NetSetupStoreType@@W4NetSetupSubkeyType@@PEA_W@Z; netsetupBuildObjectPath(_NETSETUP_OBJECT_TYPE,_GUID const &,NetSetupStoreType,NetSetupSubkeyType,wchar_t *)
0x1401609cb  xor     r9d, r9d; void *
0x1401609ce  lea     r8, [rbp+1F0h+var_240]; wchar_t *
0x1401609d2  mov     edx, 1; unsigned int
0x1401609d7  lea     rcx, [rsp+2F0h+Handle]; this
0x1401609dc  call    ?Open@KRegKey@@QEAAJKPEB_WPEAX@Z; KRegKey::Open(ulong,wchar_t const *,void *)
0x1401609e1  mov     esi, eax
0x1401609e3  xor     edx, edx; int
0x1401609e5  test    esi, esi
0x1401609e7  jns     short loc_140160A3B
0x1401609e9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1401609f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1401609f7  jz      loc_140160AED
0x1401609fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140160a04  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140160a0b  mov     dword ptr [rsp+2F0h+var_2B8], esi; char
0x140160a0f  mov     r9d, 0Ah; int
0x140160a15  mov     dword ptr [rsp+2F0h+var_2C0], 1; char
0x140160a1d  mov     r8d, 1; int
0x140160a23  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x140160a28  mov     rcx, [rcx+40h]; int
0x140160a2c  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140160a31  call    WPP_RECORDER_SF__guid_Dd
0x140160a36  jmp     loc_140160AED
0x140160a3b  lea     rax, [rsp+2F0h+Handle]
0x140160a40  mov     [rsp+2F0h+var_290], edx
0x140160a44  mov     [rsp+2F0h+P], rdx
0x140160a49  lea     r8, [rsp+2F0h+P]
0x140160a4e  lea     rdx, NETSETUPPKEY_Operational_ExecutionContextProfile
0x140160a55  mov     [rsp+2F0h+KeyHandle], rax
0x140160a5a  lea     rcx, [rsp+2F0h+KeyHandle]
0x140160a5f  call    ?ReadString@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAV?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@@Z; NetSetupPropertyBag::ReadString(_NETSETUPPROPKEY const &,wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>> &)
0x140160a64  mov     esi, eax
0x140160a66  test    eax, eax
0x140160a68  jns     short loc_140160A82
0x140160a6a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140160a71  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140160a78  jz      short loc_140160AE1
0x140160a7a  mov     r9d, 0Bh
0x140160a80  jmp     short loc_140160AB4
0x140160a82  lea     r8, [rsp+2F0h+var_290]; unsigned int *
0x140160a87  lea     rdx, NETSETUPPKEY_Operational_ExecutionContextProfileSource; struct _NETSETUPPROPKEY *
0x140160a8e  lea     rcx, [rsp+2F0h+KeyHandle]; this
0x140160a93  call    ?ReadUint32@NetSetupPropertyBag@@QEAAJAEBU_NETSETUPPROPKEY@@AEAI@Z; NetSetupPropertyBag::ReadUint32(_NETSETUPPROPKEY const &,uint &)
0x140160a98  mov     esi, eax
0x140160a9a  test    eax, eax
0x140160a9c  jns     short loc_140160B0A
0x140160a9e  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140160aa5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140160aac  jz      short loc_140160AE1
0x140160aae  mov     r9d, 0Ch; int
0x140160ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x140160abb  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140160ac2  mov     dword ptr [rsp+2F0h+var_2C0], esi; char
0x140160ac6  mov     r8d, 1; int
0x140160acc  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x140160ad1  mov     dl, 3; int
0x140160ad3  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140160ad8  mov     rcx, [rcx+40h]; int
0x140160adc  call    WPP_RECORDER_SF__guid_d
0x140160ae1  xor     edx, edx
0x140160ae3  lea     rcx, [rsp+2F0h+P]
0x140160ae8  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160aed  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160af2  test    rcx, rcx
0x140160af5  jz      short loc_140160B03
0x140160af7  call    cs:__imp_ZwClose
0x140160afe  nop     dword ptr [rax+rax+00h]
0x140160b03  mov     eax, esi
0x140160b05  jmp     loc_140161093
0x140160b0a  mov     eax, [rsp+2F0h+var_290]
0x140160b0e  test    eax, eax
0x140160b10  jz      loc_140160D1C
0x140160b16  cmp     eax, 3
0x140160b19  jz      loc_140160D1C
0x140160b1f  cmp     eax, 2
0x140160b22  jnz     loc_140160CF0
0x140160b28  mov     rax, [rsp+2F0h+P]
0x140160b2d  cmp     word ptr [rax], 0
0x140160b31  jnz     short loc_140160B57
0x140160b33  xor     edx, edx
0x140160b35  lea     rcx, [rsp+2F0h+P]
0x140160b3a  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160b3f  mov     rcx, [rsp+2F0h+Handle]
0x140160b44  test    rcx, rcx
0x140160b47  jnz     loc_140160D06
0x140160b4d  mov     eax, 0C0000034h
0x140160b52  jmp     loc_140161093
0x140160b57  xorps   xmm0, xmm0
0x140160b5a  lea     rcx, aReservedExecut; "Reserved\\ExecutionContextProfiles"
0x140160b61  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x140160b66  mov     rax, rcx
0x140160b69  cmp     word ptr [rax], 0
0x140160b6d  jz      short loc_140160B79
0x140160b6f  add     rax, 2
0x140160b73  sub     r14, 1
0x140160b77  jnz     short loc_140160B69
0x140160b79  xor     eax, eax
0x140160b7b  test    r14, r14
0x140160b7e  cmovnz  r13d, eax
0x140160b82  jz      loc_140160CA0
0x140160b88  mov     r9, [rdi]; void *
0x140160b8b  lea     r8, [rsp+2F0h+var_2A0]; struct _UNICODE_STRING *
0x140160b90  mov     eax, 0FFFEh
0x140160b95  mov     [rsp+2F0h+var_2A0.Buffer], rcx
0x140160b9a  add     r14w, r14w
0x140160b9e  mov     edx, ebx; unsigned int
0x140160ba0  sub     ax, r14w
0x140160ba4  mov     rcx, rdi; this
0x140160ba7  mov     [rsp+2F0h+var_2A0.Length], ax
0x140160bac  add     ax, 2
0x140160bb0  mov     [rsp+2F0h+var_2A0.MaximumLength], ax
0x140160bb5  call    ?Open@KRegKey@@QEAAJKPEBU_UNICODE_STRING@@PEAX@Z; KRegKey::Open(ulong,_UNICODE_STRING const *,void *)
0x140160bba  mov     r13d, eax
0x140160bbd  test    eax, eax
0x140160bbf  js      loc_140160CA0
0x140160bc5  mov     r9, [rdi]; void *
0x140160bc8  mov     edx, ebx; unsigned int
0x140160bca  mov     r8, [rsp+2F0h+P]; struct _UNICODE_STRING *
0x140160bcf  mov     rcx, rdi; this
0x140160bd2  call    ?Open@KRegKey@@QEAAJKPEBU_UNICODE_STRING@@PEAX@Z; KRegKey::Open(ulong,_UNICODE_STRING const *,void *)
0x140160bd7  mov     ebx, eax
0x140160bd9  test    eax, eax
0x140160bdb  jns     short loc_140160C4D
0x140160bdd  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140160be4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140160beb  jz      short loc_140160C20
0x140160bed  mov     rcx, cs:WPP_GLOBAL_Control
0x140160bf4  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140160bfb  mov     dword ptr [rsp+2F0h+var_2C0], ebx; char
0x140160bff  mov     r9d, 12h; int
0x140160c05  mov     qword ptr [rsp+2F0h+var_2C8], r12; __int64
0x140160c0a  mov     r8d, 1; int
0x140160c10  mov     dl, 3; int
0x140160c12  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140160c17  mov     rcx, [rcx+40h]; int
0x140160c1b  call    WPP_RECORDER_SF__guid_d
0x140160c20  xor     edx, edx
0x140160c22  lea     rcx, [rsp+2F0h+P]
0x140160c27  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160c2c  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160c31  test    rcx, rcx
0x140160c34  jz      loc_14016102B
0x140160c3a  call    cs:__imp_ZwClose
0x140160c41  nop     dword ptr [rax+rax+00h]
0x140160c46  mov     eax, ebx
0x140160c48  jmp     loc_140161093
0x140160c4d  add     rdi, 8
0x140160c51  xor     edx, edx
0x140160c53  mov     rcx, rdi
0x140160c56  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?ZwClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&ZwClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x140160c5b  mov     rcx, [rsp+2F0h+P]; P
0x140160c60  mov     byte ptr [r15], 1
0x140160c64  mov     [rsp+2F0h+P], 0
0x140160c6d  test    rcx, rcx
0x140160c70  jz      short loc_140160C83
0x140160c72  mov     edx, 7274534Bh; Tag
0x140160c77  call    cs:__imp_ExFreePoolWithTag
0x140160c7e  nop     dword ptr [rax+rax+00h]
0x140160c83  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160c88  test    rcx, rcx
0x140160c8b  jz      short loc_140160C99
0x140160c8d  call    cs:__imp_ZwClose
0x140160c94  nop     dword ptr [rax+rax+00h]
0x140160c99  xor     eax, eax
0x140160c9b  jmp     loc_140161093
0x140160ca0  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140160ca7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140160cae  jz      short loc_140160CDF
0x140160cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x140160cb7  lea     rax, WPP_7350990bba9a33d8934e66c0f1152c3c_Traceguids
0x140160cbe  mov     r9d, 11h; int
0x140160cc4  mov     dword ptr [rsp+2F0h+var_2C8], r13d; char
0x140160cc9  mov     r8d, 1; int
0x140160ccf  mov     [rsp+2F0h+var_2D0], rax; struct _GUID *
0x140160cd4  mov     dl, 3; int
0x140160cd6  mov     rcx, [rcx+40h]; int
0x140160cda  call    WPP_RECORDER_SF_d
0x140160cdf  xor     edx, edx
0x140160ce1  lea     rcx, [rsp+2F0h+P]
0x140160ce6  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160ceb  jmp     loc_140160F8A
0x140160cf0  xor     edx, edx
0x140160cf2  lea     rcx, [rsp+2F0h+P]
0x140160cf7  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160cfc  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160d01  test    rcx, rcx
0x140160d04  jz      short loc_140160D12
0x140160d06  call    cs:__imp_ZwClose
0x140160d0d  nop     dword ptr [rax+rax+00h]
0x140160d12  mov     eax, 0C0000034h
0x140160d17  jmp     loc_140161093
0x140160d1c  test    bl, 2
0x140160d1f  jz      short loc_140160D4D
0x140160d21  xor     edx, edx
0x140160d23  lea     rcx, [rsp+2F0h+P]
0x140160d28  call    ?reset@?$unique_ptr@UKString@Rtl@@U?$default_delete@UKString@Rtl@@@wistd@@@wistd@@QEAAXPEAUKString@Rtl@@@Z; wistd::unique_ptr<Rtl::KString,wistd::default_delete<Rtl::KString>>::reset(Rtl::KString *)
0x140160d2d  mov     rcx, [rsp+2F0h+Handle]; Handle
0x140160d32  test    rcx, rcx
0x140160d35  jz      short loc_140160D43
0x140160d37  call    cs:__imp_ZwClose
0x140160d3e  nop     dword ptr [rax+rax+00h]
0x140160d43  mov     eax, 0C0000022h
0x140160d48  jmp     loc_140161093
0x140160d4d  xorps   xmm0, xmm0
0x140160d50  lea     rcx, aReservedExecut; "Reserved\\ExecutionContextProfiles"
0x140160d57  movups  xmmword ptr [rsp+2F0h+var_2A0.Length], xmm0
0x140160d5c  mov     rax, rcx
0x140160d5f  mov     rdx, r14
0x140160d62  cmp     word ptr [rax], 0
0x140160d66  jz      short loc_140160D72
0x140160d68  add     rax, 2
0x140160d6c  sub     rdx, 1
  ... truncated ...
```
