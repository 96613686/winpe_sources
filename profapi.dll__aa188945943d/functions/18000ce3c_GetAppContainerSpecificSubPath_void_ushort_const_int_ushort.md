# _GetAppContainerSpecificSubPath(void *,ushort const *,int,ushort * *)

- ea: `0x18000ce3c`
- end: `0x18000cf1c`
- name: `?_GetAppContainerSpecificSubPath@@YAJPEAXPEBGHPEAPEAG@Z`
- size: `224`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003914`
- `0x18000c0f0`

## callees

- `0x1800017e4`
- `0x180001ab8`
- `0x180002484`
- `0x180005b60`
- `0x1800064b0`
- `0x18000ce3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ce94`

## string_xrefs

- `0x18000ced4`: `_GetAppContainerSpecificSubPath %ws %ws`

## pseudocode

```c
__int64 __fastcall _GetAppContainerSpecificSubPath(void *a1, const unsigned __int16 *a2, int a3, unsigned __int16 **a4)
{
  int SidString; // eax
  unsigned int v8; // ebx
  const char *v10; // rbx
  int AppContainerSpecificSubPath; // eax
  unsigned int v12; // edi
  unsigned int v13; // esi
  int v14; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HLOCAL hMem; // [rsp+88h] [rbp+20h] BYREF

  *a4 = 0;
  hMem = 0;
  SidString = GetSidString(a1, (unsigned __int16 **)&hMem);
  v8 = SidString;
  if ( SidString >= 0 )
  {
    v10 = (const char *)hMem;
    AppContainerSpecificSubPath = _GetAppContainerSpecificSubPath((const unsigned __int16 *)hMem, a2, a3, a4);
    v12 = -2147024877;
    v13 = AppContainerSpecificSubPath;
    if ( AppContainerSpecificSubPath != -2147024877 )
    {
      v12 = -2147024894;
      if ( AppContainerSpecificSubPath != -2147024894 )
      {
        if ( AppContainerSpecificSubPath >= 0 )
        {
          v12 = 0;
        }
        else
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0xAB,
            (unsigned int)"minio\\profapi\\appcontainer.cpp",
            (const char *)(unsigned int)AppContainerSpecificSubPath,
            (int)"_GetAppContainerSpecificSubPath %ws %ws",
            v10,
            a2);
          v12 = v13;
        }
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
    return v12;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"minio\\profapi\\appcontainer.cpp",
      (const char *)(unsigned int)SidString,
      v14);
    if ( hMem )
      LocalFree(hMem);
    return v8;
  }
}

```

## disassembly

```asm
0x18000ce3c  mov     rax, rsp
0x18000ce3f  push    rbx
0x18000ce40  push    rbp
0x18000ce41  push    rsi
0x18000ce42  push    rdi
0x18000ce43  sub     rsp, 48h
0x18000ce47  mov     rbp, rdx
0x18000ce4a  mov     qword ptr [r9], 0
0x18000ce51  lea     rdx, [rax+20h]; unsigned __int16 **
0x18000ce55  mov     qword ptr [rax+20h], 0
0x18000ce5d  mov     rdi, r9
0x18000ce60  mov     esi, r8d
0x18000ce63  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x18000ce68  mov     ebx, eax
0x18000ce6a  test    eax, eax
0x18000ce6c  jns     short loc_18000CE9E
0x18000ce6e  mov     rcx, [rsp+68h]; this
0x18000ce73  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000ce7a  mov     r9d, eax; char *
0x18000ce7d  mov     edx, 0A7h; void *
0x18000ce82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce87  mov     rcx, [rsp+68h+hMem]; hMem
0x18000ce8f  test    rcx, rcx
0x18000ce92  jz      short loc_18000CE9A
0x18000ce94  call    cs:__imp_LocalFree
0x18000ce9a  mov     eax, ebx
0x18000ce9c  jmp     short loc_18000CF13
0x18000ce9e  mov     rbx, [rsp+68h+hMem]
0x18000cea6  mov     r9, rdi; unsigned __int16 **
0x18000cea9  mov     rcx, rbx; unsigned __int16 *
0x18000ceac  mov     r8d, esi; int
0x18000ceaf  mov     rdx, rbp; unsigned __int16 *
0x18000ceb2  call    ?_GetAppContainerSpecificSubPath@@YAJPEBG0HPEAPEAG@Z; _GetAppContainerSpecificSubPath(ushort const *,ushort const *,int,ushort * *)
0x18000ceb7  mov     edi, 80070013h
0x18000cebc  mov     esi, eax
0x18000cebe  cmp     eax, edi
0x18000cec0  jz      short loc_18000CF04
0x18000cec2  mov     edi, 80070002h
0x18000cec7  cmp     eax, edi
0x18000cec9  jz      short loc_18000CF04
0x18000cecb  test    eax, eax
0x18000cecd  jns     short loc_18000CF02
0x18000cecf  mov     rcx, [rsp+68h]; this
0x18000ced4  lea     rax, aGetappcontaine_3; "_GetAppContainerSpecificSubPath %ws %ws"
0x18000cedb  mov     [rsp+68h+var_38], rbp
0x18000cee0  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000cee7  mov     [rsp+68h+var_40], rbx; char *
0x18000ceec  mov     r9d, esi; char *
0x18000ceef  mov     edx, 0ABh; void *
0x18000cef4  mov     qword ptr [rsp+68h+var_48], rax; int
0x18000cef9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cefe  mov     edi, esi
0x18000cf00  jmp     short loc_18000CF04
0x18000cf02  xor     edi, edi
0x18000cf04  lea     rcx, [rsp+68h+hMem]
0x18000cf0c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18000cf11  mov     eax, edi
0x18000cf13  add     rsp, 48h
0x18000cf17  pop     rdi
0x18000cf18  pop     rsi
0x18000cf19  pop     rbp
0x18000cf1a  pop     rbx
0x18000cf1b  retn
```
