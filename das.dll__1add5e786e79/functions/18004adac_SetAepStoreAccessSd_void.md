# SetAepStoreAccessSd(void * *)

- ea: `0x18004adac`
- end: `0x18004af63`
- name: `?SetAepStoreAccessSd@@YAJPEAPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *SecurityDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18004a5cc`

## callees

- `0x180007500`
- `0x180019f78`
- `0x18002a948`
- `0x18003bc80`
- `0x18004adac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ae08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004af35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004ae08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004af35`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004af43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004af43`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ae19`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004ae19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004aee1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004aed7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004aed7`

## string_xrefs

- `0x18004aeaf`: `onecore\base\devices\association\service\lib\rpcif.cpp`

## pseudocode

```c
__int64 __fastcall SetAepStoreAccessSd(PSECURITY_DESCRIPTOR *SecurityDescriptor)
{
  HANDLE ProcessHeap; // rax
  WCHAR *v3; // rax
  int v4; // edx
  int v5; // r8d
  unsigned int v6; // ebx
  int v7; // eax
  signed int LastError; // eax
  int v9; // edx
  int v10; // r8d
  WCHAR *v11; // rdi
  HANDLE v12; // rax
  int MessageGuid; // [rsp+20h] [rbp-59h]
  LPCWSTR StringSecurityDescriptor; // [rsp+30h] [rbp-49h] BYREF
  int v16; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v18[8]; // [rsp+48h] [rbp-31h] BYREF
  _OWORD v19[2]; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v19[0] = *(_OWORD *)L"(A;;GR;;;%s)";
  v16 = 1024;
  *(_OWORD *)((char *)v19 + 10) = *(_OWORD *)L"R;;;%s)";
  v17 = 0;
  ProcessHeap = GetProcessHeap();
  v3 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
  StringSecurityDescriptor = v3;
  if ( v3 )
  {
    v17 = 2;
    *(_DWORD *)v3 = *(_DWORD *)L"D:";
    v3[2] = aD[2];
    v18[0] = off_180083958;
    v18[1] = v19;
    v18[2] = &v17;
    v18[3] = &v16;
    v18[4] = &StringSecurityDescriptor;
    v18[7] = v18;
    v7 = DAS::ProviderManagement::ProviderManager::ForEach(g_providerManager, v18);
    v6 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\rpcif.cpp",
        (const char *)(unsigned int)v7,
        MessageGuid);
      return v6;
    }
    v6 = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, SecurityDescriptor, 0) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v9,
          v10,
          11,
          &WPP_1ac4981e7da6391f895fbd18b31c02c5_Traceguids,
          v6);
    }
  }
  else
  {
    v6 = -2147024882;
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v4,
        v5,
        10,
        &WPP_1ac4981e7da6391f895fbd18b31c02c5_Traceguids,
        14);
  }
  v11 = (WCHAR *)StringSecurityDescriptor;
  if ( StringSecurityDescriptor )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  return v6;
}

```

## disassembly

```asm
0x18004adac  push    rbp
0x18004adae  push    rbx
0x18004adaf  push    rsi
0x18004adb0  push    rdi
0x18004adb1  lea     rbp, [rsp-3Fh]
0x18004adb6  sub     rsp, 0B8h
0x18004adbd  mov     rax, cs:__security_cookie
0x18004adc4  xor     rax, rsp
0x18004adc7  mov     [rbp+57h+var_28], rax
0x18004adcb  movups  xmm0, xmmword ptr cs:aAGrS; "(A;;GR;;;%s)"
0x18004add2  mov     ebx, dword ptr cs:aD; "D:"
0x18004add8  mov     rdi, rcx
0x18004addb  movups  xmm1, xmmword ptr cs:aAGrS+0Ah; "R;;;%s)"
0x18004ade2  movzx   esi, word ptr cs:aD+4; ""
0x18004ade9  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18004aded  mov     [rbp+57h+var_98], 400h
0x18004adf4  movups  xmmword ptr [rbp+57h+var_48+0Ah], xmm1
0x18004adf8  mov     [rbp+57h+StringSecurityDescriptor], 0
0x18004ae00  mov     [rbp+57h+var_90], 0
0x18004ae08  call    cs:__imp_GetProcessHeap
0x18004ae0e  xor     edx, edx; dwFlags
0x18004ae10  mov     r8d, 800h; dwBytes
0x18004ae16  mov     rcx, rax; hHeap
0x18004ae19  call    cs:__imp_HeapAlloc
0x18004ae1f  mov     [rbp+57h+StringSecurityDescriptor], rax
0x18004ae23  test    rax, rax
0x18004ae26  jnz     short loc_18004AE54
0x18004ae28  mov     ebx, 8007000Eh
0x18004ae2d  lea     rax, WPP_RECORDER_INITIALIZED
0x18004ae34  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004ae3b  jz      loc_18004AF2C
0x18004ae41  mov     r9d, 0Ah
0x18004ae47  mov     dword ptr [rsp+0D0h+var_A8], 8007000Eh
0x18004ae4f  jmp     loc_18004AF10
0x18004ae54  mov     [rbp+57h+var_90], 2
0x18004ae5c  lea     rdx, [rbp+57h+var_88]
0x18004ae60  mov     [rax], ebx
0x18004ae62  mov     [rax+4], si
0x18004ae66  lea     rax, off_180083958
0x18004ae6d  mov     rcx, cs:?g_providerManager@@3V?$unique_ptr@VProviderManager@ProviderManagement@DAS@@U?$default_delete@VProviderManager@ProviderManagement@DAS@@@std@@@std@@A; std::unique_ptr<DAS::ProviderManagement::ProviderManager> g_providerManager
0x18004ae74  mov     [rbp+57h+var_88], rax
0x18004ae78  lea     rax, [rbp+57h+var_48]
0x18004ae7c  mov     [rbp+57h+var_80], rax
0x18004ae80  lea     rax, [rbp+57h+var_90]
0x18004ae84  mov     [rbp+57h+var_78], rax
0x18004ae88  lea     rax, [rbp+57h+var_98]
0x18004ae8c  mov     [rbp+57h+var_70], rax
0x18004ae90  lea     rax, [rbp+57h+StringSecurityDescriptor]
0x18004ae94  mov     [rbp+57h+var_68], rax
0x18004ae98  lea     rax, [rbp+57h+var_88]
0x18004ae9c  mov     [rbp+57h+var_50], rax
0x18004aea0  call    ?ForEach@ProviderManager@ProviderManagement@DAS@@QEAAJV?$function@$$A6AJV?$shared_ptr@VProviderContext@@@std@@AEA_N@Z@std@@@Z; DAS::ProviderManagement::ProviderManager::ForEach(std::function<long (std::shared_ptr<ProviderContext>,bool &)>)
0x18004aea5  mov     ebx, eax
0x18004aea7  test    eax, eax
0x18004aea9  jns     short loc_18004AEC8
0x18004aeab  mov     rcx, [rbp+5Fh]; this
0x18004aeaf  lea     r8, aOnecoreBaseDev_5; "onecore\\base\\devices\\association\\se"...
0x18004aeb6  mov     r9d, eax; char *
0x18004aeb9  mov     edx, 0C5h; void *
0x18004aebe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004aec3  jmp     loc_18004AF49
0x18004aec8  mov     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18004aecc  xor     ebx, ebx
0x18004aece  xor     r9d, r9d; SecurityDescriptorSize
0x18004aed1  mov     r8, rdi; SecurityDescriptor
0x18004aed4  lea     edx, [rbx+1]; StringSDRevision
0x18004aed7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004aedd  test    eax, eax
0x18004aedf  jnz     short loc_18004AF2C
0x18004aee1  call    cs:__imp_GetLastError
0x18004aee7  mov     ebx, eax
0x18004aee9  test    eax, eax
0x18004aeeb  jle     short loc_18004AEF6
0x18004aeed  movzx   ebx, ax
0x18004aef0  or      ebx, 80070000h
0x18004aef6  lea     rax, WPP_RECORDER_INITIALIZED
0x18004aefd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004af04  jz      short loc_18004AF2C
0x18004af06  mov     r9d, 0Bh; int
0x18004af0c  mov     dword ptr [rsp+0D0h+var_A8], ebx; char
0x18004af10  mov     rcx, cs:WPP_GLOBAL_Control
0x18004af17  lea     rax, WPP_1ac4981e7da6391f895fbd18b31c02c5_Traceguids
0x18004af1e  mov     [rsp+0D0h+MessageGuid], rax; MessageGuid
0x18004af23  mov     rcx, [rcx+28h]; int
0x18004af27  call    WPP_RECORDER_SF_D
0x18004af2c  mov     rdi, [rbp+57h+StringSecurityDescriptor]
0x18004af30  test    rdi, rdi
0x18004af33  jz      short loc_18004AF49
0x18004af35  call    cs:__imp_GetProcessHeap
0x18004af3b  mov     r8, rdi; lpMem
0x18004af3e  xor     edx, edx; dwFlags
0x18004af40  mov     rcx, rax; hHeap
0x18004af43  call    cs:__imp_HeapFree
0x18004af49  mov     eax, ebx
0x18004af4b  mov     rcx, [rbp+57h+var_28]
0x18004af4f  xor     rcx, rsp; StackCookie
0x18004af52  call    __security_check_cookie
0x18004af57  add     rsp, 0B8h
0x18004af5e  pop     rdi
0x18004af5f  pop     rsi
0x18004af60  pop     rbx
0x18004af61  pop     rbp
0x18004af62  retn
```
