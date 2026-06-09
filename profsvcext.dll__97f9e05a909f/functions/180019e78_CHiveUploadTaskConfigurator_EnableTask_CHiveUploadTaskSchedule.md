# CHiveUploadTaskConfigurator::_EnableTask(CHiveUploadTaskSchedule &)

- ea: `0x180019e78`
- end: `0x180019f0d`
- name: `?_EnableTask@CHiveUploadTaskConfigurator@@CAJAEAVCHiveUploadTaskSchedule@@@Z`
- size: `149`
- prototype: `__int64 __fastcall(struct CHiveUploadTaskSchedule *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019cdc`

## callees

- `0x180006a9c`
- `0x18000f220`
- `0x18000f4b0`
- `0x180018c78`
- `0x180019e78`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019edd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019edd`

## string_xrefs

- `0x180019ee8`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 __fastcall CHiveUploadTaskConfigurator::_EnableTask(struct CHiveUploadTaskSchedule *a1)
{
  char v1; // di
  signed int v2; // eax
  unsigned int v3; // ebx
  const wchar_t **v4; // rax
  __int64 v5; // rcx
  const wchar_t *v6; // r8
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  hMem = a1;
  v2 = lambda_59ffb547234e235f2e8c89cec80f48f9_::operator()(&hMem);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
  {
    v4 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v2);
    v6 = L"???";
    v1 = 1;
    if ( *v4 )
      v6 = *v4;
    McTemplateU0z_EtwEventWriteTransfer(v5, EVENT_ENABLE_UPLOAD_TASK_FAILED, v6);
  }
  if ( (v1 & 1) != 0 )
    LocalFree(hMem);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x19D,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)v3,
    v8);
  return v3;
}

```

## disassembly

```asm
0x180019e78  mov     [rsp+arg_8], rbx
0x180019e7d  push    rdi; int
0x180019e7e  sub     rsp, 20h
0x180019e82  xor     edi, edi
0x180019e84  mov     dword ptr [rsp+28h+hMem], edi
0x180019e88  mov     [rsp+28h+hMem], rcx
0x180019e8d  lea     rcx, [rsp+28h+hMem]
0x180019e92  call    _lambda_59ffb547234e235f2e8c89cec80f48f9___operator__
0x180019e97  mov     ebx, eax
0x180019e99  test    eax, eax
0x180019e9b  jns     short loc_180019F00
0x180019e9d  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x180019ea4  jz      short loc_180019ED2
0x180019ea6  mov     edx, eax; dwMessageId
0x180019ea8  lea     rcx, [rsp+28h+hMem]; lpBuffer
0x180019ead  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180019eb2  lea     r8, asc_180022B10; "???"
0x180019eb9  mov     edi, 1
0x180019ebe  lea     rdx, EVENT_ENABLE_UPLOAD_TASK_FAILED
0x180019ec5  cmp     qword ptr [rax], 0
0x180019ec9  cmovnz  r8, [rax]
0x180019ecd  call    McTemplateU0z_EtwEventWriteTransfer
0x180019ed2  test    dil, 1
0x180019ed6  jz      short loc_180019EE3
0x180019ed8  mov     rcx, [rsp+28h+hMem]; hMem
0x180019edd  call    cs:__imp_LocalFree
0x180019ee3  mov     rcx, [rsp+28h]; this
0x180019ee8  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019eef  mov     r9d, ebx; char *
0x180019ef2  mov     edx, 19Dh; void *
0x180019ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019efc  mov     eax, ebx
0x180019efe  jmp     short loc_180019F02
0x180019f00  xor     eax, eax
0x180019f02  mov     rbx, [rsp+28h+arg_8]
0x180019f07  add     rsp, 20h
0x180019f0b  pop     rdi
0x180019f0c  retn
```
