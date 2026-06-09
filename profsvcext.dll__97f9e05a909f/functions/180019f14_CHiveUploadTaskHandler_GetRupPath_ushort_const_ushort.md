# CHiveUploadTaskHandler::_GetRupPath(ushort const *,ushort * *)

- ea: `0x180019f14`
- end: `0x18001a02a`
- name: `?_GetRupPath@CHiveUploadTaskHandler@@AEAAJPEBGPEAPEAG@Z`
- size: `278`
- prototype: `__int64 __fastcall(CHiveUploadTaskHandler *this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180018a3c`

## callees

- `0x180005424`
- `0x180006a9c`
- `0x18001375c`
- `0x180013af4`
- `0x180019f14`

## string_xrefs

- `0x180019f79`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`
- `0x180019fc8`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskHandler::_GetRupPath(
        CHiveUploadTaskHandler *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int *v5; // r8
  int ProfileListKeyNameFromSid; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  int v9; // eax
  unsigned __int16 *v10; // rax
  unsigned __int16 *v12; // [rsp+20h] [rbp-30h] BYREF
  __int64 v13; // [rsp+28h] [rbp-28h]
  __int64 v14; // [rsp+30h] [rbp-20h]
  unsigned __int16 *v15; // [rsp+38h] [rbp-18h] BYREF
  __int64 v16; // [rsp+40h] [rbp-10h]
  __int64 v17; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  *a3 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v15);
  v16 = -1;
  v17 = -1;
  ProfileListKeyNameFromSid = GetProfileListKeyNameFromSid(a2, &v15, v5);
  v8 = ProfileListKeyNameFromSid;
  if ( ProfileListKeyNameFromSid >= 0 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    v9 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
           &v12,
           v7,
           v15,
           L"CentralProfile");
    v8 = v9;
    if ( v9 >= 0 )
    {
      v10 = v12;
      v12 = 0;
      v14 = 0;
      v13 = 0;
      *a3 = v10;
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
      v8 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
        (const char *)(unsigned int)v9,
        (int)v12);
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x253,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
      (const char *)(unsigned int)ProfileListKeyNameFromSid,
      (int)v12);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(&v15);
  return v8;
}

```

## disassembly

```asm
0x180019f14  mov     [rsp-8+arg_0], rbx
0x180019f19  mov     [rsp-8+arg_8], rdi
0x180019f1e  push    rbp
0x180019f1f  mov     rbp, rsp
0x180019f22  sub     rsp, 50h
0x180019f26  mov     rdi, r8
0x180019f29  mov     rbx, rdx
0x180019f2c  mov     qword ptr [r8], 0
0x180019f33  mov     [rbp+var_18], 0
0x180019f3b  mov     [rbp+var_10], 0
0x180019f43  mov     [rbp+var_8], 0
0x180019f4b  lea     rcx, [rbp+var_18]
0x180019f4f  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019f54  or      rax, 0FFFFFFFFFFFFFFFFh
0x180019f58  mov     [rbp+var_10], rax
0x180019f5c  mov     [rbp+var_8], rax
0x180019f60  lea     rdx, [rbp+var_18]; unsigned __int16 **
0x180019f64  mov     rcx, rbx; unsigned __int16 *
0x180019f67  call    ?GetProfileListKeyNameFromSid@@YAJPEBGPEAPEAGPEAH@Z; GetProfileListKeyNameFromSid(ushort const *,ushort * *,int *)
0x180019f6c  mov     ebx, eax
0x180019f6e  test    eax, eax
0x180019f70  jns     short loc_180019F8F
0x180019f72  mov     rcx, [rbp+8]; this
0x180019f76  mov     r9d, eax; char *
0x180019f79  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019f80  mov     edx, 253h; void *
0x180019f85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f8a  jmp     loc_18001A00F
0x180019f8f  mov     [rbp+var_30], 0
0x180019f97  mov     [rbp+var_28], 0
0x180019f9f  mov     [rbp+var_20], 0
0x180019fa7  lea     r9, aCentralprofile; "CentralProfile"
0x180019fae  mov     r8, [rbp+var_18]
0x180019fb2  lea     rcx, [rbp+var_30]
0x180019fb6  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x180019fbb  mov     ebx, eax
0x180019fbd  test    eax, eax
0x180019fbf  jns     short loc_180019FE5
0x180019fc1  mov     rcx, [rbp+8]; this
0x180019fc5  mov     r9d, eax; char *
0x180019fc8  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019fcf  mov     edx, 256h; void *
0x180019fd4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fd9  nop
0x180019fda  lea     rcx, [rbp+var_30]
0x180019fde  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180019fe3  jmp     short loc_18001A00F
0x180019fe5  mov     rax, [rbp+var_30]
0x180019fe9  mov     [rbp+var_30], 0
0x180019ff1  mov     [rbp+var_20], 0
0x180019ff9  mov     [rbp+var_28], 0
0x18001a001  mov     [rdi], rax
0x18001a004  lea     rcx, [rbp+var_30]
0x18001a008  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a00d  xor     ebx, ebx
0x18001a00f  lea     rcx, [rbp+var_18]
0x18001a013  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18001a018  mov     eax, ebx
0x18001a01a  mov     rbx, [rsp+50h+arg_0]
0x18001a01f  mov     rdi, [rsp+50h+arg_8]
0x18001a024  add     rsp, 50h
0x18001a028  pop     rbp
0x18001a029  retn
```
