# CHiveUploadTaskHandler::_SaveLastUploadTime(ushort const *)

- ea: `0x18001a1e4`
- end: `0x18001a2be`
- name: `?_SaveLastUploadTime@CHiveUploadTaskHandler@@AEAAJPEBG@Z`
- size: `218`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009770`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x180009d08`
- `0x18001375c`
- `0x18001a1e4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a205`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a205`

## string_xrefs

- `0x18001a277`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x18001a255`: `ProfileBackgroundRegistryUploadTimeLow`
- `0x18001a289`: `ProfileBackgroundRegistryUploadTimeHigh`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler::_SaveLastUploadTime(
        CHiveUploadTaskHandler *this,
        const unsigned __int16 *a2)
{
  int *v3; // r8
  int ProfileListKeyNameFromSid; // eax
  HKEY v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  HKEY v8; // rcx
  unsigned __int16 *v10; // [rsp+20h] [rbp-20h] BYREF
  __int64 v11; // [rsp+28h] [rbp-18h]
  __int64 v12; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+50h] [rbp+10h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v10 = 0;
  v11 = 0;
  v12 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v10);
  v11 = -1;
  v12 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a2, &v10, v3);
  v6 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    ProfileListKeyNameFromSid = SHRegSetDWORD(
                                  v5,
                                  v10,
                                  L"ProfileBackgroundRegistryUploadTimeLow",
                                  SystemTimeAsFileTime.dwLowDateTime);
    v6 = ProfileListKeyNameFromSid;
    if ( ProfileListKeyNameFromSid >= 0 )
    {
      ProfileListKeyNameFromSid = SHRegSetDWORD(
                                    v8,
                                    v10,
                                    L"ProfileBackgroundRegistryUploadTimeHigh",
                                    SystemTimeAsFileTime.dwHighDateTime);
      v6 = ProfileListKeyNameFromSid;
      if ( ProfileListKeyNameFromSid >= 0 )
      {
        v6 = 0;
        goto LABEL_9;
      }
      v7 = 545;
    }
    else
    {
      v7 = 539;
    }
  }
  else
  {
    v7 = 533;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)(unsigned int)ProfileListKeyNameFromSid,
    (int)v10);
LABEL_9:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v10);
  return v6;
}

```

## disassembly

```asm
0x18001a1e4  mov     [rsp-8+arg_8], rbx
0x18001a1e9  mov     qword ptr [rsp-8+SystemTimeAsFileTime.dwLowDateTime], rcx
0x18001a1ee  push    rbp
0x18001a1ef  mov     rbp, rsp
0x18001a1f2  sub     rsp, 40h
0x18001a1f6  mov     rbx, rdx
0x18001a1f9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001a201  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a205  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a20b  mov     [rbp+var_20], 0
0x18001a213  mov     [rbp+var_18], 0
0x18001a21b  mov     [rbp+var_10], 0
0x18001a223  lea     rcx, [rbp+var_20]
0x18001a227  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a22c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a230  mov     [rbp+var_18], rax
0x18001a234  mov     [rbp+var_10], rax
0x18001a238  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18001a23c  mov     rcx, rbx; unsigned __int16 *
0x18001a23f  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x18001a244  mov     ebx, eax
0x18001a246  test    eax, eax
0x18001a248  jns     short loc_18001A251
0x18001a24a  mov     edx, 215h
0x18001a24f  jmp     short loc_18001A270
0x18001a251  mov     r9d, [rbp+SystemTimeAsFileTime.dwLowDateTime]; unsigned int
0x18001a255  lea     r8, aProfilebackgro; "ProfileBackgroundRegistryUploadTimeLow"
0x18001a25c  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18001a260  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001a265  mov     ebx, eax
0x18001a267  test    eax, eax
0x18001a269  jns     short loc_18001A285
0x18001a26b  mov     edx, 21Bh; void *
0x18001a270  mov     rcx, [rbp+8]; this
0x18001a274  mov     r9d, eax; char *
0x18001a277  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x18001a27e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a283  jmp     short loc_18001A2A8
0x18001a285  mov     r9d, [rbp+SystemTimeAsFileTime.dwHighDateTime]; unsigned int
0x18001a289  lea     r8, aProfilebackgro_0; "ProfileBackgroundRegistryUploadTimeHigh"
0x18001a290  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18001a294  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18001a299  mov     ebx, eax
0x18001a29b  test    eax, eax
0x18001a29d  jns     short loc_18001A2A6
0x18001a29f  mov     edx, 221h
0x18001a2a4  jmp     short loc_18001A270
0x18001a2a6  xor     ebx, ebx
0x18001a2a8  lea     rcx, [rbp+var_20]
0x18001a2ac  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a2b1  mov     eax, ebx
0x18001a2b3  mov     rbx, [rsp+40h+arg_8]
0x18001a2b8  add     rsp, 40h
0x18001a2bc  pop     rbp
0x18001a2bd  retn
```
