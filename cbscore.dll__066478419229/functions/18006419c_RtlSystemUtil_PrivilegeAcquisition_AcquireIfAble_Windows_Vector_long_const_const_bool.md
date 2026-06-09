# RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(Windows::Vector<long const> const &,bool *)

- ea: `0x18006419c`
- end: `0x1800645cf`
- name: `?AcquireIfAble@PrivilegeAcquisition@RtlSystemUtil@@QEAAJAEBU?$Vector@$$CBJ@Windows@@PEA_N@Z`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800be18c`

## callees

- `0x18002e280`
- `0x18002ec34`
- `0x18003ff34`
- `0x18004cc90`
- `0x18006419c`
- `0x1800aa134`
- `0x1800aa1a4`
- `0x1800eb4c0`
- `0x1800eb500`
- `0x1800eb518`
- `0x1800eb920`
- `0x1800ef360`

## import_xrefs

- `ntdll!NtAdjustPrivilegesToken` at `0x18006445b`
- `ntdll!NtAdjustPrivilegesToken` at `0x18006445b`
- `ntdll!NtSetInformationThread` at `0x1800644c3`
- `ntdll!NtSetInformationThread` at `0x1800644c3`
- `ntdll!NtDuplicateToken` at `0x180064400`
- `ntdll!NtDuplicateToken` at `0x180064400`
- `ntdll!NtOpenThreadToken` at `0x1800642c8`
- `ntdll!NtOpenThreadToken` at `0x1800642c8`
- `ntdll!NtOpenProcessToken` at `0x1800642f5`
- `ntdll!NtOpenProcessToken` at `0x1800642f5`

## string_xrefs

- `0x180064305`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006436f`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180064410`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x18006446d`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x1800644d3`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180064576`: `onecore\base\wcp\rtllib\nativelib\security_library.cpp`
- `0x180064589`: `TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)`
- `0x18006431f`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x18006438b`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180064429`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180064487`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1800644ea`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x180064590`: `RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble`
- `0x1800644f5`: `NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))`
- `0x180064435`: `NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())`
- `0x18006432b`: `NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.GetInitPointer())`

## pseudocode

```c
__int64 __fastcall RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble(__int64 a1, _QWORD *a2, _BYTE *a3)
{
  int v6; // ebx
  struct _TOKEN_PRIVILEGES *v7; // rax
  struct _TOKEN_PRIVILEGES *v8; // rbx
  struct _TOKEN_PRIVILEGES *v9; // rdi
  int v10; // r15d
  unsigned __int64 i; // rdx
  __int64 v12; // rcx
  LUID v13; // rax
  void **InitPointer; // rax
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  void **v18; // rax
  NTSTATUS v19; // eax
  _QWORD *v20; // rdx
  int v21; // esi
  char v22; // r14
  void **NewTokenHandle; // rax
  NTSTATUS v24; // edx
  HANDLE v25; // rcx
  _QWORD v27[4]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v28[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v30[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v31[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v32[4]; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE ThreadInformation; // [rsp+F0h] [rbp-10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  int v35; // [rsp+128h] [rbp+28h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+130h] [rbp+30h] BYREF
  HANDLE TokenHandle; // [rsp+138h] [rbp+38h] BYREF
  _DWORD v38[4]; // [rsp+140h] [rbp+40h] BYREF

  *a3 = 0;
  v35 = 0;
  TokenHandle = 0;
  ExistingTokenHandle = 0;
  ThreadInformation = 0;
  if ( *(_BYTE *)(a1 + 8) || *(_QWORD *)a1 )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x1800645CELL);
  }
  v6 = BUCL::Rtl::Multiply<unsigned __int64>(a2[1], 12, &ThreadInformation);
  if ( v6 < 0 )
    goto LABEL_39;
  if ( (unsigned __int64)ThreadInformation >= 0xFFFFFFFFFFFFFFEFuLL
    || (v7 = (struct _TOKEN_PRIVILEGES *)operator new((size_t)ThreadInformation + 16), (v8 = v7) == 0) )
  {
    v32[2] = 632;
    v32[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v32[3] = "TokenPrivileges.AllocateWithExtraBytes(cbToAllocate)";
    v32[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(
           &v35,
           v32);
LABEL_39:
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
    Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
    return (unsigned int)v6;
  }
  v9 = v7 + 1;
  v10 = BUCL::Rtl::ConvertInteger<unsigned __int64,unsigned long>(a2[1], v7);
  if ( v10 < 0 )
  {
    if ( v9 )
      operator delete(v8);
    else
      operator delete(v8, (const struct std::nothrow_t *)0x10);
    v6 = v10;
    goto LABEL_39;
  }
  for ( i = 0; i < a2[1]; v8->Privileges[v12].Attributes = 2 )
  {
    v12 = i;
    v13 = (LUID)*(int *)(*a2 + 4 * i++);
    ThreadInformation = (HANDLE)v13;
    v8->Privileges[v12].Luid = v13;
  }
  InitPointer = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                           &ExistingTokenHandle,
                           i);
  v15 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2Eu, 1u, InitPointer);
  v17 = (unsigned int)v15;
  if ( v15 == -1073741700 )
  {
    v18 = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                     &ExistingTokenHandle,
                     v16);
    v19 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x2Eu, v18);
    if ( v19 < 0 )
    {
      v27[2] = 660;
      v27[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v20 = v27;
      v27[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v27[3] = "NtOpenProcessToken( ( (HANDLE)(LONG_PTR) -1 ), (0x0002) | (0x0020) | (0x0004) | (0x0008), PreviousToken.G"
               "etInitPointer())";
LABEL_16:
      v17 = (unsigned int)v19;
LABEL_17:
      v21 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
              &v35,
              v20,
              v17);
      if ( v9 )
        operator delete(v8);
      else
        operator delete(v8, (const struct std::nothrow_t *)0x10);
      v6 = v21;
      goto LABEL_39;
    }
    v22 = 0;
  }
  else
  {
    if ( v15 < 0 )
    {
      v28[2] = 666;
      v28[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v28[3] = "Status";
      v28[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v20 = v28;
      goto LABEL_17;
    }
    v22 = 1;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.SecurityQualityOfService = v38;
  v38[2] = 1;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v38[0] = 12;
  v38[1] = 2;
  NewTokenHandle = (void **)Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(
                              &TokenHandle,
                              v16);
  v19 = NtDuplicateToken(ExistingTokenHandle, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, NewTokenHandle);
  if ( v19 < 0 )
  {
    v29[2] = 686;
    v29[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v20 = v29;
    v29[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v29[3] = "NtDuplicateToken( PreviousToken, (0x0020) | (0x0008) | (0x0004), &ObjA, 0, TokenImpersonation, NewToken.GetInitPointer())";
    goto LABEL_16;
  }
  v24 = NtAdjustPrivilegesToken(TokenHandle, 0, v8, 0, 0, 0);
  if ( v24 < 0 )
  {
    v30[2] = 697;
    v30[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
    v30[3] = "Status";
    v17 = (unsigned int)v24;
    v30[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
    v20 = v30;
    goto LABEL_17;
  }
  if ( v24 != 262 )
  {
    ThreadInformation = TokenHandle;
    v19 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    if ( v19 < 0 )
    {
      v31[2] = 718;
      v31[0] = "onecore\\base\\wcp\\rtllib\\nativelib\\security_library.cpp";
      v20 = v31;
      v31[1] = "RtlSystemUtil::PrivilegeAcquisition::AcquireIfAble";
      v31[3] = "NtSetInformationThread( ( (HANDLE)(LONG_PTR) -2 ), ThreadImpersonationToken, (PVOID)&hNewToken, sizeof(hNewToken))";
      goto LABEL_16;
    }
    *(_BYTE *)(a1 + 8) = 1;
    *a3 = 1;
    if ( v22 )
    {
      v25 = ExistingTokenHandle;
      ExistingTokenHandle = *(HANDLE *)a1;
      *(_QWORD *)a1 = v25;
    }
  }
  if ( v9 )
    operator delete(v8);
  else
    operator delete(v8, (const struct std::nothrow_t *)0x10);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&ExistingTokenHandle);
  Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&void Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(&TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18006419c  mov     [rsp-8+arg_18], rbx
0x1800641a1  push    rbp
0x1800641a2  push    rsi
0x1800641a3  push    rdi
0x1800641a4  push    r12
0x1800641a6  push    r13
0x1800641a8  push    r14
0x1800641aa  push    r15
0x1800641ac  lea     rbp, [rsp-60h]
0x1800641b1  sub     rsp, 160h
0x1800641b8  mov     rax, cs:__security_cookie
0x1800641bf  xor     rax, rsp
0x1800641c2  mov     [rbp+90h+var_40], rax
0x1800641c6  xor     r13d, r13d
0x1800641c9  mov     r12, r8
0x1800641cc  mov     [r8], r13b
0x1800641cf  mov     r14, rdx
0x1800641d2  mov     rsi, rcx
0x1800641d5  mov     [rbp+90h+var_68], r13d
0x1800641d9  mov     [rbp+90h+TokenHandle], r13
0x1800641dd  mov     [rbp+90h+ExistingTokenHandle], r13
0x1800641e1  mov     [rbp+90h+ThreadInformation], r13
0x1800641e5  cmp     [rcx+8], r13b
0x1800641e9  jnz     loc_1800645C4
0x1800641ef  cmp     [rcx], r13
0x1800641f2  jnz     loc_1800645C4
0x1800641f8  mov     rcx, [r14+8]
0x1800641fc  lea     r8, [rbp+90h+ThreadInformation]
0x180064200  lea     edx, [r13+0Ch]
0x180064204  call    ??$Multiply@_K@Rtl@BUCL@@YAJ_K0AEA_K@Z; BUCL::Rtl::Multiply<unsigned __int64>(unsigned __int64,unsigned __int64,unsigned __int64 &)
0x180064209  mov     ebx, eax
0x18006420b  test    eax, eax
0x18006420d  js      loc_1800645AE
0x180064213  mov     rcx, [rbp+90h+ThreadInformation]
0x180064217  cmp     rcx, 0FFFFFFFFFFFFFFEFh
0x18006421b  jnb     loc_180064576
0x180064221  add     rcx, 10h; Size
0x180064225  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006422a  mov     rbx, rax
0x18006422d  test    rax, rax
0x180064230  jz      loc_180064576
0x180064236  mov     rcx, [r14+8]
0x18006423a  lea     rdi, [rax+10h]
0x18006423e  mov     rdx, rax
0x180064241  call    ??$ConvertInteger@_KK@Rtl@BUCL@@YAJ_KAEAK@Z; BUCL::Rtl::ConvertInteger<unsigned __int64,ulong>(unsigned __int64,ulong &)
0x180064246  mov     r15d, eax
0x180064249  test    eax, eax
0x18006424b  jns     short loc_18006426E
0x18006424d  mov     rcx, rbx; void *
0x180064250  test    rdi, rdi
0x180064253  jz      short loc_18006425C
0x180064255  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006425a  jmp     short loc_180064266
0x18006425c  mov     edx, 10h; struct std::nothrow_t *
0x180064261  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064266  mov     ebx, r15d
0x180064269  jmp     loc_1800645AE
0x18006426e  mov     rdx, r13
0x180064271  cmp     [r14+8], r13
0x180064275  jbe     short loc_1800642A6
0x180064277  mov     rax, [r14]
0x18006427a  lea     rcx, [rdx+rdx*2]
0x18006427e  movsxd  rax, dword ptr [rax+rdx*4]
0x180064282  inc     rdx
0x180064285  mov     dword ptr [rbp+90h+ThreadInformation], eax
0x180064288  shr     rax, 20h
0x18006428c  mov     dword ptr [rbp+90h+ThreadInformation+4], eax
0x18006428f  mov     rax, [rbp+90h+ThreadInformation]
0x180064293  mov     [rbx+rcx*4+4], rax
0x180064298  mov     dword ptr [rbx+rcx*4+0Ch], 2
0x1800642a0  cmp     rdx, [r14+8]
0x1800642a4  jb      short loc_180064277
0x1800642a6  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x1800642aa  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1800642af  mov     r14d, 2Eh ; '.'
0x1800642b5  mov     r15, 0FFFFFFFFFFFFFFFEh
0x1800642bc  mov     edx, r14d; DesiredAccess
0x1800642bf  mov     rcx, r15; ThreadHandle
0x1800642c2  mov     r9, rax; TokenHandle
0x1800642c5  mov     r8b, 1; OpenAsSelf
0x1800642c8  call    cs:__imp_NtOpenThreadToken
0x1800642cf  nop     dword ptr [rax+rax+00h]
0x1800642d4  mov     r8d, eax
0x1800642d7  cmp     eax, 0C000007Ch
0x1800642dc  jnz     loc_18006436A
0x1800642e2  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x1800642e6  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1800642eb  mov     r8, rax; TokenHandle
0x1800642ee  mov     edx, r14d; DesiredAccess
0x1800642f1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800642f5  call    cs:__imp_NtOpenProcessToken
0x1800642fc  nop     dword ptr [rax+rax+00h]
0x180064301  test    eax, eax
0x180064303  jns     short loc_180064365
0x180064305  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006430c  mov     [rsp+190h+var_150], 294h
0x180064315  mov     [rsp+190h+var_160], rcx
0x18006431a  lea     rdx, [rsp+190h+var_160]
0x18006431f  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180064326  mov     [rsp+190h+var_158], rcx
0x18006432b  lea     rcx, aNtopenprocesst; "NtOpenProcessToken( ( (HANDLE)(LONG_PTR"...
0x180064332  mov     [rsp+190h+var_148], rcx
0x180064337  mov     r8d, eax
0x18006433a  lea     rcx, [rbp+90h+var_68]
0x18006433e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180064343  mov     esi, eax
0x180064345  mov     rcx, rbx; void *
0x180064348  test    rdi, rdi
0x18006434b  jz      short loc_180064354
0x18006434d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180064352  jmp     short loc_18006435E
0x180064354  mov     edx, 10h; struct std::nothrow_t *
0x180064359  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006435e  mov     ebx, esi
0x180064360  jmp     loc_1800645AE
0x180064365  mov     r14b, r13b
0x180064368  jmp     short loc_1800643A6
0x18006436a  test    r8d, r8d
0x18006436d  jns     short loc_1800643A3
0x18006436f  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180064376  mov     [rsp+190h+var_130], 29Ah
0x18006437f  mov     [rsp+190h+var_140], rcx
0x180064384  lea     rax, aStatus_0; "Status"
0x18006438b  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180064392  mov     [rsp+190h+var_128], rax
0x180064397  mov     [rsp+190h+var_138], rcx
0x18006439c  lea     rdx, [rsp+190h+var_140]
0x1800643a1  jmp     short loc_18006433A
0x1800643a3  mov     r14b, 1
0x1800643a6  lea     rax, [rbp+90h+var_50]
0x1800643aa  mov     qword ptr [rbp+90h+ObjectAttributes.Length], 30h ; '0'
0x1800643b2  lea     rcx, [rbp+90h+TokenHandle]
0x1800643b6  mov     [rbp+90h+ObjectAttributes.SecurityQualityOfService], rax
0x1800643ba  mov     qword ptr [rbp+90h+ObjectAttributes.Attributes], r13
0x1800643be  mov     [rbp+90h+var_48], 1
0x1800643c5  mov     [rbp+90h+ObjectAttributes.RootDirectory], r13
0x1800643c9  mov     [rbp+90h+ObjectAttributes.ObjectName], r13
0x1800643cd  mov     [rbp+90h+ObjectAttributes.SecurityDescriptor], r13
0x1800643d1  mov     [rbp+90h+var_50], 0Ch
0x1800643d8  mov     [rbp+90h+var_4C], 2
0x1800643df  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::GetInitPointer(void)
0x1800643e4  mov     rcx, [rbp+90h+ExistingTokenHandle]; ExistingTokenHandle
0x1800643e8  lea     r8, [rbp+90h+ObjectAttributes]; ObjectAttributes
0x1800643ec  xor     r9d, r9d; EffectiveOnly
0x1800643ef  mov     [rsp+190h+NewTokenHandle], rax; NewTokenHandle
0x1800643f4  mov     [rsp+190h+TokenType], 2; TokenType
0x1800643fc  lea     edx, [r9+2Ch]; DesiredAccess
0x180064400  call    cs:__imp_NtDuplicateToken
0x180064407  nop     dword ptr [rax+rax+00h]
0x18006440c  test    eax, eax
0x18006440e  jns     short loc_180064445
0x180064410  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180064417  mov     [rbp+90h+var_110], 2AEh
0x18006441f  mov     [rsp+190h+var_120], rcx
0x180064424  lea     rdx, [rsp+190h+var_120]
0x180064429  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180064430  mov     [rsp+190h+var_118], rcx
0x180064435  lea     rcx, aNtduplicatetok; "NtDuplicateToken( PreviousToken, (0x002"...
0x18006443c  mov     [rbp+90h+var_108], rcx
0x180064440  jmp     loc_180064337
0x180064445  mov     rcx, [rbp+90h+TokenHandle]; TokenHandle
0x180064449  xor     r9d, r9d; BufferLength
0x18006444c  mov     [rsp+190h+NewTokenHandle], r13; ReturnLength
0x180064451  mov     r8, rbx; NewState
0x180064454  xor     edx, edx; DisableAllPrivileges
0x180064456  mov     qword ptr [rsp+190h+TokenType], r13; PreviousState
0x18006445b  call    cs:__imp_NtAdjustPrivilegesToken
0x180064462  nop     dword ptr [rax+rax+00h]
0x180064467  mov     edx, eax
0x180064469  test    eax, eax
0x18006446b  jns     short loc_1800644A2
0x18006446d  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x180064474  mov     [rbp+90h+var_F0], 2B9h
0x18006447c  mov     [rbp+90h+var_100], rcx
0x180064480  lea     rax, aStatus_0; "Status"
0x180064487  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x18006448e  mov     [rbp+90h+var_E8], rax
0x180064492  mov     r8d, edx
0x180064495  mov     [rbp+90h+var_F8], rcx
0x180064499  lea     rdx, [rbp+90h+var_100]
0x18006449d  jmp     loc_18006433A
0x1800644a2  cmp     edx, 106h
0x1800644a8  jz      short loc_180064521
0x1800644aa  mov     rax, [rbp+90h+TokenHandle]
0x1800644ae  lea     r8, [rbp+90h+ThreadInformation]; ThreadInformation
0x1800644b2  mov     r9d, 8; ThreadInformationLength
0x1800644b8  mov     [rbp+90h+ThreadInformation], rax
0x1800644bc  mov     rcx, r15; ThreadHandle
0x1800644bf  lea     edx, [r9-3]; ThreadInformationClass
0x1800644c3  call    cs:__imp_NtSetInformationThread
0x1800644ca  nop     dword ptr [rax+rax+00h]
0x1800644cf  test    eax, eax
0x1800644d1  jns     short loc_180064505
0x1800644d3  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x1800644da  mov     [rbp+90h+var_D0], 2CEh
0x1800644e2  mov     [rbp+90h+var_E0], rcx
0x1800644e6  lea     rdx, [rbp+90h+var_E0]
0x1800644ea  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x1800644f1  mov     [rbp+90h+var_D8], rcx
0x1800644f5  lea     rcx, aNtsetinformati_3; "NtSetInformationThread( ( (HANDLE)(LONG"...
0x1800644fc  mov     [rbp+90h+var_C8], rcx
0x180064500  jmp     loc_180064337
0x180064505  mov     byte ptr [rsi+8], 1
0x180064509  mov     byte ptr [r12], 1
0x18006450e  test    r14b, r14b
0x180064511  jz      short loc_180064521
0x180064513  mov     rcx, [rbp+90h+ExistingTokenHandle]
0x180064517  mov     rax, [rsi]
0x18006451a  mov     [rbp+90h+ExistingTokenHandle], rax
0x18006451e  mov     [rsi], rcx
0x180064521  mov     rcx, rbx; void *
0x180064524  test    rdi, rdi
0x180064527  jz      short loc_180064530
0x180064529  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18006452e  jmp     short loc_18006453A
0x180064530  mov     edx, 10h; struct std::nothrow_t *
0x180064535  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006453a  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x18006453e  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x180064543  lea     rcx, [rbp+90h+TokenHandle]
0x180064547  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x18006454c  xor     eax, eax
0x18006454e  mov     rcx, [rbp+90h+var_40]
0x180064552  xor     rcx, rsp; StackCookie
0x180064555  call    __security_check_cookie
0x18006455a  mov     rbx, [rsp+190h+arg_18]
0x180064562  add     rsp, 160h
0x180064569  pop     r15
0x18006456b  pop     r14
0x18006456d  pop     r13
0x18006456f  pop     r12
0x180064571  pop     rdi
0x180064572  pop     rsi
0x180064573  pop     rbp
0x180064574  retn
0x180064576  lea     rcx, aOnecoreBaseWcp_56; "onecore\\base\\wcp\\rtllib\\nativelib\\"...
0x18006457d  mov     [rbp+90h+var_B0], 278h
0x180064585  mov     [rbp+90h+var_C0], rcx
0x180064589  lea     rax, aTokenprivilege; "TokenPrivileges.AllocateWithExtraBytes("...
0x180064590  lea     rcx, aRtlsystemutilP; "RtlSystemUtil::PrivilegeAcquisition::Ac"...
0x180064597  mov     [rbp+90h+var_A8], rax
0x18006459b  mov     [rbp+90h+var_B8], rcx
0x18006459f  lea     rdx, [rbp+90h+var_C0]
0x1800645a3  lea     rcx, [rbp+90h+var_68]
0x1800645a7  call    ?OriginateFailedMemoryAllocation@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateFailedMemoryAllocation(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800645ac  mov     ebx, eax
0x1800645ae  lea     rcx, [rbp+90h+ExistingTokenHandle]
0x1800645b2  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800645b7  lea     rcx, [rbp+90h+TokenHandle]
0x1800645bb  call    ?Close@?$AutoGenericHandleBase@PEAX$00V?$AutoGenericHandle@PEAX$00$1?CloseWithNtCloseHandle@Detail@Windows@@YAXPEAX@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<void *,1,Windows::AutoGenericHandle<void *,1,&Windows::Detail::CloseWithNtCloseHandle(void *)>>::Close(void)
0x1800645c0  mov     eax, ebx
0x1800645c2  jmp     short loc_18006454E
0x1800645c4  mov     ecx, 0C00000E5h; int
0x1800645c9  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
