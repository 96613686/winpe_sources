# _GetAppContainerPath(void *,ushort const *,ushort * *)

- ea: `0x18000cf24`
- end: `0x18000d003`
- name: `?_GetAppContainerPath@@YAJPEAXPEBGPEAPEAG@Z`
- size: `223`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a914`
- `0x180016400`

## callees

- `0x180001ab8`
- `0x180002484`
- `0x180005b60`
- `0x1800064b0`
- `0x18000cf24`
- `0x180016250`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf79`

## string_xrefs

- `0x18000cfbb`: `_GetAppContainerPath %ws %ws`

## pseudocode

```c
__int64 __fastcall _GetAppContainerPath(void *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int SidString; // eax
  unsigned int v6; // ebx
  const char *v8; // rbx
  int AppContainerPath; // eax
  unsigned int v10; // esi
  unsigned int v11; // edi
  int v12; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HLOCAL hMem; // [rsp+80h] [rbp+18h] BYREF

  *a3 = 0;
  hMem = 0;
  SidString = GetSidString(a1, (unsigned __int16 **)&hMem);
  v6 = SidString;
  if ( SidString >= 0 )
  {
    v8 = (const char *)hMem;
    AppContainerPath = _GetAppContainerPath((char *)hMem, a2, a3);
    v10 = -2147024877;
    v11 = AppContainerPath;
    if ( AppContainerPath != -2147024877 )
    {
      if ( AppContainerPath != -2147024891 && AppContainerPath != -2147024894 )
      {
        if ( AppContainerPath >= 0 )
        {
          v10 = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xD4,
          (unsigned int)"minio\\profapi\\appcontainer.cpp",
          (const char *)(unsigned int)AppContainerPath,
          (int)"_GetAppContainerPath %ws %ws",
          v8,
          a2);
      }
      v10 = v11;
    }
LABEL_11:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
    return v10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCD,
    (unsigned int)"minio\\profapi\\appcontainer.cpp",
    (const char *)(unsigned int)SidString,
    v12);
  if ( hMem )
    LocalFree(hMem);
  return v6;
}

```

## disassembly

```asm
0x18000cf24  mov     rax, rsp
0x18000cf27  push    rbx
0x18000cf28  push    rbp
0x18000cf29  push    rsi
0x18000cf2a  push    rdi
0x18000cf2b  sub     rsp, 48h
0x18000cf2f  mov     rbp, rdx
0x18000cf32  mov     qword ptr [r8], 0
0x18000cf39  lea     rdx, [rax+18h]; unsigned __int16 **
0x18000cf3d  mov     qword ptr [rax+18h], 0
0x18000cf45  mov     rdi, r8
0x18000cf48  call    ?GetSidString@@YAJPEAXPEAPEAG@Z; GetSidString(void *,ushort * *)
0x18000cf4d  mov     ebx, eax
0x18000cf4f  test    eax, eax
0x18000cf51  jns     short loc_18000CF83
0x18000cf53  mov     rcx, [rsp+68h]; this
0x18000cf58  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000cf5f  mov     r9d, eax; char *
0x18000cf62  mov     edx, 0CDh; void *
0x18000cf67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf6c  mov     rcx, [rsp+68h+hMem]; hMem
0x18000cf74  test    rcx, rcx
0x18000cf77  jz      short loc_18000CF7F
0x18000cf79  call    cs:__imp_LocalFree
0x18000cf7f  mov     eax, ebx
0x18000cf81  jmp     short loc_18000CFF6
0x18000cf83  mov     rbx, [rsp+68h+hMem]
0x18000cf8b  mov     r8, rdi; unsigned __int16 **
0x18000cf8e  mov     rcx, rbx; char *
0x18000cf91  mov     rdx, rbp; unsigned __int16 *
0x18000cf94  call    ?_GetAppContainerPath@@YAJPEBG0PEAPEAG@Z; _GetAppContainerPath(ushort const *,ushort const *,ushort * *)
0x18000cf99  mov     esi, 80070013h
0x18000cf9e  mov     edi, eax
0x18000cfa0  cmp     eax, esi
0x18000cfa2  jz      short loc_18000CFE7
0x18000cfa4  cmp     eax, 80070005h
0x18000cfa9  jz      short loc_18000CFE5
0x18000cfab  cmp     eax, 80070002h
0x18000cfb0  jz      short loc_18000CFE5
0x18000cfb2  test    eax, eax
0x18000cfb4  jns     short loc_18000CFFF
0x18000cfb6  mov     rcx, [rsp+68h]; this
0x18000cfbb  lea     rax, aGetappcontaine_1; "_GetAppContainerPath %ws %ws"
0x18000cfc2  mov     [rsp+68h+var_38], rbp
0x18000cfc7  lea     r8, aMinioProfapiAp; "minio\\profapi\\appcontainer.cpp"
0x18000cfce  mov     [rsp+68h+var_40], rbx; char *
0x18000cfd3  mov     r9d, edi; char *
0x18000cfd6  mov     edx, 0D4h; void *
0x18000cfdb  mov     qword ptr [rsp+68h+var_48], rax; int
0x18000cfe0  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000cfe5  mov     esi, edi
0x18000cfe7  lea     rcx, [rsp+68h+hMem]
0x18000cfef  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18000cff4  mov     eax, esi
0x18000cff6  add     rsp, 48h
0x18000cffa  pop     rdi
0x18000cffb  pop     rsi
0x18000cffc  pop     rbp
0x18000cffd  pop     rbx
0x18000cffe  retn
0x18000cfff  xor     esi, esi
0x18000d001  jmp     short loc_18000CFE7
```
