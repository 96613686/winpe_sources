# CUserProfileRoamingProvider::_SaveUnloadTime(ushort const *,ushort const *)

- ea: `0x180016ef8`
- end: `0x180016fef`
- name: `?_SaveUnloadTime@CUserProfileRoamingProvider@@AEAAJPEBG0@Z`
- size: `247`
- prototype: `__int64 __fastcall(CUserProfileRoamingProvider *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800159b0`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x180009d08`
- `0x18001375c`
- `0x180016ef8`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016f19`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180016f19`

## string_xrefs

- `0x180016fae`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileRoamingProvider::_SaveUnloadTime(
        CUserProfileRoamingProvider *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v6; // rax
  int *v7; // r8
  int ProfileListKeyNameFromSid; // eax
  HKEY v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rdx
  HKEY v12; // rcx
  unsigned __int16 *v14; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+28h] [rbp-20h]
  __int64 v16; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+28h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  (*(void (__fastcall **)(_QWORD, struct _FILETIME *))(**((_QWORD **)this + 1) + 160LL))(
    *((_QWORD *)this + 1),
    &SystemTimeAsFileTime);
  v14 = 0;
  v15 = 0;
  v16 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v14);
  v15 = -1;
  v16 = -1;
  v6 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 32LL))(*((_QWORD *)this + 1));
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(v6, &v14, v7);
  v10 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    ProfileListKeyNameFromSid = SHRegSetDWORD(v9, v14, a2, SystemTimeAsFileTime.dwLowDateTime);
    v10 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid >= 0 )
    {
      ProfileListKeyNameFromSid = SHRegSetDWORD(v12, v14, a3, SystemTimeAsFileTime.dwHighDateTime);
      v10 = ProfileListKeyNameFromSid;
      if ( ProfileListKeyNameFromSid >= 0 )
      {
        v10 = 0;
        goto LABEL_9;
      }
      v11 = 2861;
    }
    else
    {
      v11 = 2860;
    }
  }
  else
  {
    v11 = 2858;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    (int)v14);
LABEL_9:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v14);
  return v10;
}

```

## disassembly

```asm
0x180016ef8  push    rbp
0x180016efa  push    rbx
0x180016efb  push    rsi
0x180016efc  push    rdi
0x180016efd  mov     rbp, rsp
0x180016f00  sub     rsp, 48h
0x180016f04  mov     rsi, r8
0x180016f07  mov     rdi, rdx
0x180016f0a  mov     rbx, rcx
0x180016f0d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180016f15  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016f19  call    cs:__imp_GetSystemTimeAsFileTime
0x180016f1f  mov     rcx, [rbx+8]
0x180016f23  mov     rax, [rcx]
0x180016f26  lea     rdx, [rbp+SystemTimeAsFileTime]
0x180016f2a  mov     rax, [rax+0A0h]
0x180016f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f36  mov     [rbp+var_28], 0
0x180016f3e  mov     [rbp+var_20], 0
0x180016f46  mov     [rbp+var_18], 0
0x180016f4e  lea     rcx, [rbp+var_28]
0x180016f52  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016f57  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016f5b  mov     [rbp+var_20], rax
0x180016f5f  mov     [rbp+var_18], rax
0x180016f63  mov     rcx, [rbx+8]
0x180016f67  mov     rax, [rcx]
0x180016f6a  mov     rax, [rax+20h]
0x180016f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f73  lea     rdx, [rbp+var_28]; unsigned __int16 **
0x180016f77  mov     rcx, rax; unsigned __int16 *
0x180016f7a  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180016f7f  mov     ebx, eax
0x180016f81  test    eax, eax
0x180016f83  jns     short loc_180016F8C
0x180016f85  mov     edx, 0B2Ah
0x180016f8a  jmp     short loc_180016FA7
0x180016f8c  mov     r9d, [rbp+SystemTimeAsFileTime.dwLowDateTime]; unsigned int
0x180016f90  mov     r8, rdi; unsigned __int16 *
0x180016f93  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180016f97  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180016f9c  mov     ebx, eax
0x180016f9e  test    eax, eax
0x180016fa0  jns     short loc_180016FBC
0x180016fa2  mov     edx, 0B2Ch; void *
0x180016fa7  mov     rcx, [rbp+20h]; this
0x180016fab  mov     r9d, eax; char *
0x180016fae  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016fba  jmp     short loc_180016FDB
0x180016fbc  mov     r9d, [rbp+SystemTimeAsFileTime.dwHighDateTime]; unsigned int
0x180016fc0  mov     r8, rsi; unsigned __int16 *
0x180016fc3  mov     rdx, [rbp+var_28]; unsigned __int16 *
0x180016fc7  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180016fcc  mov     ebx, eax
0x180016fce  test    eax, eax
0x180016fd0  jns     short loc_180016FD9
0x180016fd2  mov     edx, 0B2Dh
0x180016fd7  jmp     short loc_180016FA7
0x180016fd9  xor     ebx, ebx
0x180016fdb  lea     rcx, [rbp+var_28]
0x180016fdf  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180016fe4  mov     eax, ebx
0x180016fe6  add     rsp, 48h
0x180016fea  pop     rdi
0x180016feb  pop     rsi
0x180016fec  pop     rbx
0x180016fed  pop     rbp
0x180016fee  retn
```
