# GetAikEnrollRetryType(DelayRetryAction *)

- ea: `0x18001bbdc`
- end: `0x18001bc87`
- name: `?GetAikEnrollRetryType@@YAJPEAW4DelayRetryAction@@@Z`
- size: `171`
- prototype: `int(enum DelayRetryAction *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b950`

## callees

- `0x18000b0fc`
- `0x18000db5c`
- `0x180010730`
- `0x18001bbdc`
- `0x180022ef4`
- `0x18002308c`

## string_xrefs

- `0x18001bc52`: `onecore\ds\security\ngc\ngcpopkey\pregenkey\pregenkey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetAikEnrollRetryType(enum DelayRetryAction *a1)
{
  const unsigned __int16 *v2; // rdx
  NgcUtils *v3; // rcx
  int NgcStateSeparatedRegistryLocation; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  enum DelayRetryAction v10; // [rsp+30h] [rbp+8h] BYREF
  HKEY v11; // [rsp+38h] [rbp+10h] BYREF

  *a1 = DelayRetryUnknown;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v11,
    0);
  NgcStateSeparatedRegistryLocation = NgcUtils::GetNgcStateSeparatedRegistryLocation(
                                        v3,
                                        v2,
                                        L"AIKCertEnroll",
                                        (unsigned __int16 *)&v11);
  v5 = NgcStateSeparatedRegistryLocation;
  if ( NgcStateSeparatedRegistryLocation >= 0 )
  {
    v10 = DelayRetryUnknown;
    NgcStateSeparatedRegistryLocation = NgcUtils::GetRegistryDwordValue(
                                          (NgcUtils *)0xFFFFFFFF80000002LL,
                                          (const WCHAR *)v11,
                                          L"RetryAction",
                                          (unsigned __int16 *)&v10);
    v5 = NgcStateSeparatedRegistryLocation;
    if ( NgcStateSeparatedRegistryLocation >= 0 )
    {
      *a1 = v10;
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 242;
  }
  else
  {
    v6 = 235;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngcpopkey\\pregenkey\\pregenkey.cpp",
    (const char *)(unsigned int)NgcStateSeparatedRegistryLocation,
    v8);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  return v5;
}

```

## disassembly

```asm
0x18001bbdc  mov     [rsp+arg_10], rbx
0x18001bbe1  push    rdi; int
0x18001bbe2  sub     rsp, 20h
0x18001bbe6  mov     rdi, rcx
0x18001bbe9  mov     dword ptr [rcx], 0
0x18001bbef  mov     [rsp+28h+arg_8], 0
0x18001bbf8  xor     edx, edx
0x18001bbfa  lea     rcx, [rsp+28h+arg_8]
0x18001bbff  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001bc04  lea     r9, [rsp+28h+arg_8]; unsigned __int16 *
0x18001bc09  lea     r8, aAikcertenroll; "AIKCertEnroll"
0x18001bc10  call    ?GetNgcStateSeparatedRegistryLocation@NgcUtils@@YAJPEBG00PEAPEAG@Z; NgcUtils::GetNgcStateSeparatedRegistryLocation(ushort const *,ushort const *,ushort const *,ushort * *)
0x18001bc15  mov     ebx, eax
0x18001bc17  test    eax, eax
0x18001bc19  jns     short loc_18001BC22
0x18001bc1b  mov     edx, 0EBh
0x18001bc20  jmp     short loc_18001BC52
0x18001bc22  mov     [rsp+28h+arg_0], 0
0x18001bc2a  lea     r9, [rsp+28h+arg_0]; unsigned __int16 *
0x18001bc2f  lea     r8, aRetryaction; "RetryAction"
0x18001bc36  mov     rdx, [rsp+28h+arg_8]; HKEY
0x18001bc3b  mov     rcx, 0FFFFFFFF80000002h; this
0x18001bc42  call    ?GetRegistryDwordValue@NgcUtils@@YAJPEAUHKEY__@@PEBG1PEAK@Z; NgcUtils::GetRegistryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001bc47  mov     ebx, eax
0x18001bc49  test    eax, eax
0x18001bc4b  jns     short loc_18001BC68
0x18001bc4d  mov     edx, 0F2h; void *
0x18001bc52  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\ngcpopkey\\"...
0x18001bc59  mov     r9d, eax; char *
0x18001bc5c  mov     rcx, [rsp+28h]; this
0x18001bc61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bc66  jmp     short loc_18001BC70
0x18001bc68  mov     eax, [rsp+28h+arg_0]
0x18001bc6c  mov     [rdi], eax
0x18001bc6e  xor     ebx, ebx
0x18001bc70  lea     rcx, [rsp+28h+arg_8]
0x18001bc75  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001bc7a  mov     eax, ebx
0x18001bc7c  mov     rbx, [rsp+28h+arg_10]
0x18001bc81  add     rsp, 20h
0x18001bc85  pop     rdi
0x18001bc86  retn
```
