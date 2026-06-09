# CHiveUploadTaskConfigurator::_DisableTask(void)

- ea: `0x180019de4`
- end: `0x180019e6f`
- name: `?_DisableTask@CHiveUploadTaskConfigurator@@CAJXZ`
- size: `139`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180019cdc`

## callees

- `0x180004b00`
- `0x180006a9c`
- `0x18000f220`
- `0x18000f4b0`
- `0x180019de4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019e3f`

## string_xrefs

- `0x180019e4a`: `clientcore\ds\security\gina\profile\roaming\uploadtask.cpp`

## pseudocode

```c
__int64 CHiveUploadTaskConfigurator::_DisableTask(void)
{
  char v0; // di
  signed int v1; // eax
  unsigned int v2; // ebx
  const wchar_t **v3; // rax
  __int64 v4; // rcx
  const wchar_t *v5; // r8
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HLOCAL hMem; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  LODWORD(hMem) = 0;
  v1 = lambda_62445a73be0091c1964fa69319b6c69b_::operator()();
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  if ( (Microsoft_Windows_User_Profiles_ServiceEnableBits & 0x10) != 0 )
  {
    v3 = (const wchar_t **)CErrorText::CErrorText((LPWSTR)&hMem, v1);
    v5 = L"???";
    v0 = 1;
    if ( *v3 )
      v5 = *v3;
    McTemplateU0z_EtwEventWriteTransfer(v4, EVENT_DISABLE_UPLOAD_TASK_FAILED, v5);
  }
  if ( (v0 & 1) != 0 )
    LocalFree(hMem);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C1,
    (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\uploadtask.cpp",
    (const char *)v2,
    v7);
  return v2;
}

```

## disassembly

```asm
0x180019de4  mov     [rsp+arg_8], rbx
0x180019de9  push    rdi; int
0x180019dea  sub     rsp, 20h
0x180019dee  xor     edi, edi
0x180019df0  mov     dword ptr [rsp+28h+hMem], edi
0x180019df4  call    _lambda_62445a73be0091c1964fa69319b6c69b___operator__
0x180019df9  mov     ebx, eax
0x180019dfb  test    eax, eax
0x180019dfd  jns     short loc_180019E62
0x180019dff  test    cs:Microsoft_Windows_User_Profiles_ServiceEnableBits, 10h
0x180019e06  jz      short loc_180019E34
0x180019e08  mov     edx, eax; dwMessageId
0x180019e0a  lea     rcx, [rsp+28h+hMem]; lpBuffer
0x180019e0f  call    ??0CErrorText@@QEAA@J@Z; CErrorText::CErrorText(long)
0x180019e14  lea     r8, asc_180022B10; "???"
0x180019e1b  mov     edi, 1
0x180019e20  lea     rdx, EVENT_DISABLE_UPLOAD_TASK_FAILED
0x180019e27  cmp     qword ptr [rax], 0
0x180019e2b  cmovnz  r8, [rax]
0x180019e2f  call    McTemplateU0z_EtwEventWriteTransfer
0x180019e34  test    dil, 1
0x180019e38  jz      short loc_180019E45
0x180019e3a  mov     rcx, [rsp+28h+hMem]; hMem
0x180019e3f  call    cs:__imp_LocalFree
0x180019e45  mov     rcx, [rsp+28h]; this
0x180019e4a  lea     r8, aClientcoreDsSe_0; "clientcore\\ds\\security\\gina\\profile"...
0x180019e51  mov     r9d, ebx; char *
0x180019e54  mov     edx, 1C1h; void *
0x180019e59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e5e  mov     eax, ebx
0x180019e60  jmp     short loc_180019E64
0x180019e62  xor     eax, eax
0x180019e64  mov     rbx, [rsp+28h+arg_8]
0x180019e69  add     rsp, 20h
0x180019e6d  pop     rdi
0x180019e6e  retn
```
