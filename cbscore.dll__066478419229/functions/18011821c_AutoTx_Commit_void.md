# AutoTx::Commit(void)

- ea: `0x18011821c`
- end: `0x180118412`
- name: `?Commit@AutoTx@@QEAAJXZ`
- size: `502`
- prototype: `__int64 __fastcall(AutoTx *__hidden this)`
- caller_count: `5`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18014aaac`
- `0x18015e4b8`
- `0x18015e9c0`
- `0x1801e80f4`
- `0x1801f5628`

## callees

- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800f70dc`
- `0x180118190`
- `0x18011821c`
- `0x180119730`
- `0x1802d5010`

## import_xrefs

- `ntdll!NtCommitTransaction` at `0x18011833e`
- `ntdll!NtCommitTransaction` at `0x18011833e`
- `ntdll!NtFlushKey` at `0x180118391`
- `ntdll!NtFlushKey` at `0x180118391`
- `ntdll!NtOpenKey` at `0x1801182f2`
- `ntdll!NtOpenKey` at `0x1801182f2`

## string_xrefs

- `0x180118278`: `TransactionCommit`
- `0x180118328`: `::NtOpenKey( &Key, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &ObjectAttributes)`
- `0x180118377`: `::NtCommitTransaction(m_Tx, 1 )`
- `0x18011831d`: `AutoTx::Commit`
- `0x180118369`: `AutoTx::Commit`
- `0x1801183b8`: `AutoTx::Commit`
- `0x1801182a2`: `\Registry`

## pseudocode

```c
__int64 __fastcall AutoTx::Commit(AutoTx *this)
{
  __int64 v1; // rax
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 result; // rax
  NTSTATUS v6; // eax
  _QWORD *v7; // rdx
  int v8; // eax
  unsigned int v9; // ebx
  _QWORD v10[4]; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v11[4]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v12; // [rsp+60h] [rbp-19h] BYREF
  const char *v13; // [rsp+68h] [rbp-11h]
  __int64 v14; // [rsp+70h] [rbp-9h]
  const char *v15; // [rsp+78h] [rbp-1h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  int v17; // [rsp+B0h] [rbp+37h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+3Fh] BYREF

  v1 = *(_QWORD *)this;
  v17 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(AutoTx *))(v1 + 8))(this) && *((_QWORD *)this + 1) )
  {
    v3 = (*(__int64 (__fastcall **)(AutoTx *))(*(_QWORD *)this + 24LL))(this);
    LogTransactionDetails(*((_QWORD *)this + 1), "TransactionCommit", v3);
    if ( *((_DWORD *)this + 6) == 1 )
    {
      result = AutoFsTx::Commit((AutoTx *)((char *)this + 16));
      if ( (int)result < 0 )
        return result;
    }
    else
    {
      LOBYTE(v4) = 1;
      v8 = NtCommitTransaction(*((_QWORD *)this + 1), v4);
      if ( v8 < 0 )
      {
        v14 = 800;
        v12 = (__int64)"onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
        v13 = "AutoTx::Commit";
        v15 = "::NtCommitTransaction(m_Tx, 1 )";
        return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                 &v17,
                 &v12,
                 (unsigned int)v8);
      }
    }
    v12 = 1310738;
    v13 = (const char *)L"\\Registry";
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v12;
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    KeyHandle = 0;
    v6 = NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
    if ( v6 < 0 )
    {
      v10[2] = 812;
      v10[0] = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v7 = v10;
      v10[1] = "AutoTx::Commit";
      v10[3] = "::NtOpenKey( &Key, ((((0x00020000L)) | (0x0001) | (0x0008) | (0x0010)) & (~(0x00100000L))), &ObjectAttributes)";
LABEL_11:
      v9 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v17,
             v7,
             (unsigned int)v6);
      Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(&KeyHandle);
      return v9;
    }
    v6 = NtFlushKey(KeyHandle);
    if ( v6 < 0 )
    {
      v11[2] = 814;
      v11[0] = "onecore\\base\\wcp\\rtllib\\nativelib-transactions\\transactions.cpp";
      v7 = v11;
      v11[1] = "AutoTx::Commit";
      v11[3] = "::NtFlushKey(Key)";
      goto LABEL_11;
    }
    Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(&KeyHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x18011821c  mov     [rsp-8+arg_8], rbx
0x180118221  push    rbp
0x180118222  lea     rbp, [rsp-57h]
0x180118227  sub     rsp, 0D0h
0x18011822e  mov     rax, cs:__security_cookie
0x180118235  xor     rax, rsp
0x180118238  mov     [rbp+57h+var_10], rax
0x18011823c  mov     rax, [rcx]
0x18011823f  mov     rbx, rcx
0x180118242  mov     [rbp+57h+var_20], 0
0x180118249  mov     rax, [rax+8]
0x18011824d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118252  test    al, al
0x180118254  jnz     loc_1801183F2
0x18011825a  cmp     qword ptr [rbx+8], 0
0x18011825f  jz      loc_1801183F2
0x180118265  mov     rax, [rbx]
0x180118268  mov     rcx, rbx
0x18011826b  mov     rax, [rax+18h]
0x18011826f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180118274  mov     rcx, [rbx+8]
0x180118278  lea     rdx, aTransactioncom; "TransactionCommit"
0x18011827f  mov     r8, rax
0x180118282  call    LogTransactionDetails
0x180118287  lea     rcx, [rbx+10h]; this
0x18011828b  cmp     dword ptr [rcx+8], 1
0x18011828f  jnz     loc_180118338
0x180118295  call    ?Commit@AutoFsTx@@QEAAJXZ; AutoFsTx::Commit(void)
0x18011829a  test    eax, eax
0x18011829c  js      loc_1801183F4
0x1801182a2  lea     rax, ??$LiteralBuffer@$2U?$BaseLiteralBuffer@$09U_UNICODE_STRING@@_W@Details@RtlStringLiterals@@3_W0FM@@0FC@@0GF@@0GH@@0GJ@@0HD@@0HE@@0HC@@0HJ@@0A@@@@$0A@$00$01$02$03$04$05$06$07$08@Details@RtlStringLiterals@@3QB_WB; "\\Registry"
0x1801182a9  mov     [rbp+57h+var_70], 140012h
0x1801182b1  mov     [rbp+57h+var_68], rax
0x1801182b5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801182b9  lea     rax, [rbp+57h+var_70]
0x1801182bd  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1801182c5  xorps   xmm0, xmm0
0x1801182c8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1801182cc  mov     edx, 20019h; DesiredAccess
0x1801182d1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1801182d9  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1801182dd  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1801182e5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801182ea  mov     [rbp+57h+KeyHandle], 0
0x1801182f2  call    cs:__imp_NtOpenKey
0x1801182f9  nop     dword ptr [rax+rax+00h]
0x1801182fe  test    eax, eax
0x180118300  jns     loc_18011838D
0x180118306  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x18011830d  mov     [rbp+57h+var_A0], 32Ch
0x180118315  mov     [rbp+57h+var_B0], rcx
0x180118319  lea     rdx, [rbp+57h+var_B0]
0x18011831d  lea     rcx, aAutotxCommit; "AutoTx::Commit"
0x180118324  mov     [rbp+57h+var_A8], rcx
0x180118328  lea     rcx, aNtopenkeyKey0x; "::NtOpenKey( &Key, ((((0x00020000L)) | "...
0x18011832f  mov     [rbp+57h+var_98], rcx
0x180118333  jmp     loc_1801183CE
0x180118338  mov     rcx, [rbx+8]
0x18011833c  mov     dl, 1
0x18011833e  call    cs:__imp_NtCommitTransaction
0x180118345  nop     dword ptr [rax+rax+00h]
0x18011834a  test    eax, eax
0x18011834c  jns     loc_1801182A2
0x180118352  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x180118359  mov     [rbp+57h+var_60], 320h
0x180118361  mov     [rbp+57h+var_70], rcx
0x180118365  lea     rdx, [rbp+57h+var_70]
0x180118369  lea     rcx, aAutotxCommit; "AutoTx::Commit"
0x180118370  mov     r8d, eax
0x180118373  mov     [rbp+57h+var_68], rcx
0x180118377  lea     rcx, aNtcommittransa; "::NtCommitTransaction(m_Tx, 1 )"
0x18011837e  mov     [rbp+57h+var_58], rcx
0x180118382  lea     rcx, [rbp+57h+var_20]
0x180118386  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18011838b  jmp     short loc_1801183F4
0x18011838d  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180118391  call    cs:__imp_NtFlushKey
0x180118398  nop     dword ptr [rax+rax+00h]
0x18011839d  test    eax, eax
0x18011839f  jns     short loc_1801183E9
0x1801183a1  lea     rcx, aOnecoreBaseWcp_48; "onecore\\base\\wcp\\rtllib\\nativelib-t"...
0x1801183a8  mov     [rbp+57h+var_80], 32Eh
0x1801183b0  mov     [rbp+57h+var_90], rcx
0x1801183b4  lea     rdx, [rbp+57h+var_90]
0x1801183b8  lea     rcx, aAutotxCommit; "AutoTx::Commit"
0x1801183bf  mov     [rbp+57h+var_88], rcx
0x1801183c3  lea     rcx, aNtflushkeyKey; "::NtFlushKey(Key)"
0x1801183ca  mov     [rbp+57h+var_78], rcx
0x1801183ce  mov     r8d, eax
0x1801183d1  lea     rcx, [rbp+57h+var_20]
0x1801183d5  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1801183da  lea     rcx, [rbp+57h+KeyHandle]
0x1801183de  mov     ebx, eax
0x1801183e0  call    ?Close@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoTxnHandle@23@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(void)
0x1801183e5  mov     eax, ebx
0x1801183e7  jmp     short loc_1801183F4
0x1801183e9  lea     rcx, [rbp+57h+KeyHandle]
0x1801183ed  call    ?Close@?$AutoHandleBase@V?$AutoHandleDefaultTraits@PEAX@Rtl@Windows@@VAutoTxnHandle@23@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoHandleBase<Windows::Rtl::AutoHandleDefaultTraits<void *>,Windows::Rtl::AutoTxnHandle>::Close(void)
0x1801183f2  xor     eax, eax
0x1801183f4  mov     rcx, [rbp+57h+var_10]
0x1801183f8  xor     rcx, rsp; StackCookie
0x1801183fb  call    __security_check_cookie
0x180118400  mov     rbx, [rsp+0D0h+arg_8]
0x180118408  add     rsp, 0D0h
0x18011840f  pop     rbp
0x180118410  retn
```
