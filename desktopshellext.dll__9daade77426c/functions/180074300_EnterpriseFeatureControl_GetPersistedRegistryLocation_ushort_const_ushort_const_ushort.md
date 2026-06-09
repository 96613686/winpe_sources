# EnterpriseFeatureControl::GetPersistedRegistryLocation(ushort const *,ushort const *,ushort * *)

- ea: `0x180074300`
- end: `0x180074443`
- name: `?GetPersistedRegistryLocation@EnterpriseFeatureControl@@CAJPEBG0PEAPEAG@Z`
- size: `323`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007652c`

## callees

- `0x180017988`
- `0x180017c80`
- `0x18003eb5c`
- `0x180040b60`
- `0x180074300`

## import_xrefs

- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074364`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800743f7`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180074364`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800743f7`

## string_xrefs

- `0x18007435d`: `WindowsUpdate`
- `0x1800743f0`: `WindowsUpdate`
- `0x180074356`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x1800743dd`: `SOFTWARE\Microsoft\WindowsUpdate`

## pseudocode

```c
__int64 __fastcall EnterpriseFeatureControl::GetPersistedRegistryLocation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  int PersistedRegistryLocationW; // eax
  unsigned __int16 *v7; // rbx
  unsigned int v8; // eax
  const unsigned __int16 **v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  const unsigned __int16 *v12; // [rsp+40h] [rbp+8h] BYREF
  const unsigned __int16 *v13; // [rsp+48h] [rbp+10h] BYREF

  v13 = a2;
  v12 = a1;
  if ( !a3 )
  {
    v4 = -2147467261;
    v5 = 87;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v4,
      (int)v10);
    return v4;
  }
  LODWORD(v13) = 0;
  v10 = &v13;
  PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                 L"WindowsUpdate",
                                 L"SOFTWARE\\Microsoft\\WindowsUpdate",
                                 0,
                                 0);
  v4 = PersistedRegistryLocationW;
  if ( !PersistedRegistryLocationW )
  {
    v4 = -2147418113;
    v5 = 93;
    goto LABEL_3;
  }
  if ( PersistedRegistryLocationW == 234 )
  {
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v12,
      0,
      (unsigned int)v13);
    v7 = (unsigned __int16 *)v12;
    if ( v12 )
    {
      v8 = GetPersistedRegistryLocationW(
             L"WindowsUpdate",
             L"SOFTWARE\\Microsoft\\WindowsUpdate",
             v12,
             (unsigned int)v13);
      if ( v8 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x63,
               (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
               (const char *)v8,
               0);
      }
      else
      {
        *a3 = v7;
        v4 = 0;
        v12 = 0;
      }
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
        (const char *)0x8007000ELL,
        (int)&v13);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v12);
  }
  else
  {
    if ( PersistedRegistryLocationW > 0 )
      v4 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    if ( (v4 & 0x80000000) != 0 )
    {
      v5 = 94;
      goto LABEL_3;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180074300  mov     [rsp+arg_10], rbx
0x180074305  mov     [rsp+arg_8], rdx
0x18007430a  mov     [rsp+arg_0], rcx
0x18007430f  push    rdi
0x180074310  sub     rsp, 30h
0x180074314  mov     rdi, r8
0x180074317  test    r8, r8
0x18007431a  jnz     short loc_18007433E
0x18007431c  mov     ebx, 80004003h
0x180074321  lea     edx, [r8+57h]; void *
0x180074325  mov     rcx, [rsp+38h]; this
0x18007432a  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180074331  mov     r9d, ebx; char *
0x180074334  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074339  jmp     loc_180074436
0x18007433e  lea     rax, [rsp+38h+arg_8]
0x180074343  mov     dword ptr [rsp+38h+arg_8], 0
0x18007434b  xor     r9d, r9d
0x18007434e  mov     qword ptr [rsp+38h+var_18], rax; int
0x180074353  xor     r8d, r8d
0x180074356  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x18007435d  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x180074364  call    cs:__imp_GetPersistedRegistryLocationW
0x18007436a  mov     ebx, eax
0x18007436c  test    eax, eax
0x18007436e  jnz     short loc_18007437A
0x180074370  mov     ebx, 8000FFFFh
0x180074375  lea     edx, [rax+5Dh]
0x180074378  jmp     short loc_180074325
0x18007437a  cmp     eax, 0EAh
0x18007437f  jz      short loc_18007439D
0x180074381  test    eax, eax
0x180074383  jle     short loc_18007438E
0x180074385  movzx   ebx, ax
0x180074388  or      ebx, 80070000h
0x18007438e  test    ebx, ebx
0x180074390  jns     loc_180074436
0x180074396  mov     edx, 5Eh ; '^'
0x18007439b  jmp     short loc_180074325
0x18007439d  mov     r8d, dword ptr [rsp+38h+arg_8]
0x1800743a2  lea     rcx, [rsp+38h+arg_0]
0x1800743a7  xor     edx, edx
0x1800743a9  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800743ae  mov     rbx, [rsp+38h+arg_0]
0x1800743b3  test    rbx, rbx
0x1800743b6  jnz     short loc_1800743D8
0x1800743b8  mov     rcx, [rsp+38h]; this
0x1800743bd  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800743c4  mov     ebx, 8007000Eh
0x1800743c9  mov     edx, 61h ; 'a'; void *
0x1800743ce  mov     r9d, ebx; char *
0x1800743d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800743d6  jmp     short loc_18007442C
0x1800743d8  mov     r9d, dword ptr [rsp+38h+arg_8]
0x1800743dd  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x1800743e4  mov     r8, rbx
0x1800743e7  mov     qword ptr [rsp+38h+var_18], 0; unsigned int
0x1800743f0  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x1800743f7  call    cs:__imp_GetPersistedRegistryLocationW
0x1800743fd  test    eax, eax
0x1800743ff  jz      short loc_18007441E
0x180074401  mov     rcx, [rsp+38h]; this
0x180074406  lea     r8, aOnecoreInterna_12; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18007440d  mov     r9d, eax; char *
0x180074410  mov     edx, 63h ; 'c'; void *
0x180074415  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007441a  mov     ebx, eax
0x18007441c  jmp     short loc_18007442C
0x18007441e  mov     [rdi], rbx
0x180074421  xor     ebx, ebx
0x180074423  mov     [rsp+38h+arg_0], 0
0x18007442c  lea     rcx, [rsp+38h+arg_0]
0x180074431  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180074436  mov     eax, ebx
0x180074438  mov     rbx, [rsp+38h+arg_10]
0x18007443d  add     rsp, 30h
0x180074441  pop     rdi
0x180074442  retn
```
