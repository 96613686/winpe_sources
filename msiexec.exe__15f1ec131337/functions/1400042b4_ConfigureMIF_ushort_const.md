# ConfigureMIF(ushort const *)

- ea: `0x1400042b4`
- end: `0x14000443c`
- name: `?ConfigureMIF@@YAXPEBG@Z`
- size: `392`
- prototype: `void __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x140004444`
- `0x140004ca8`

## callees

- `0x140003c20`
- `0x1400042b4`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x140004425`
- `KERNEL32!WideCharToMultiByte` at `0x140004425`
- `msi!__imp_MsiGetSummaryInformationW` at `0x1400042e5`
- `msi!__imp_MsiGetSummaryInformationW` at `0x1400042e5`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x14000434d`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x140004386`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x1400043bb`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x1400043f4`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x14000434d`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x140004386`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x1400043bb`
- `msi!__imp_MsiSummaryInfoGetPropertyA` at `0x1400043f4`

## pseudocode

```c
void __fastcall ConfigureMIF(LPCWCH lpWideCharStr)
{
  FILETIME pftValue; // [rsp+40h] [rbp-10h] BYREF
  DWORD pcchValueBuf; // [rsp+70h] [rbp+20h] BYREF
  MSIHANDLE phSummaryInfo; // [rsp+78h] [rbp+28h] BYREF
  int piValue; // [rsp+80h] [rbp+30h] BYREF
  unsigned int puiDataType; // [rsp+88h] [rbp+38h] BYREF

  phSummaryInfo = 0;
  if ( lpWideCharStr )
  {
    if ( !*lpWideCharStr || MsiGetSummaryInformationW(0, lpWideCharStr, 0, &phSummaryInfo) )
    {
      WideCharToMultiByte(0, 0, lpWideCharStr, -1, &MultiByteStr, 64, 0, 0);
    }
    else
    {
      puiDataType = 0;
      piValue = 0;
      pftValue = 0;
      byte_140010F10 = 0;
      byte_140010DE0 = 0;
      MultiByteStr = 0;
      szValueBuf = 0;
      pcchValueBuf = 128;
      MsiSummaryInfoGetPropertyA(phSummaryInfo, 4u, &puiDataType, &piValue, &pftValue, &szValueBuf, &pcchValueBuf);
      pcchValueBuf = 64;
      MsiSummaryInfoGetPropertyA(phSummaryInfo, 9u, &puiDataType, &piValue, &pftValue, &MultiByteStr, &pcchValueBuf);
      pcchValueBuf = 128;
      MsiSummaryInfoGetPropertyA(phSummaryInfo, 3u, &puiDataType, &piValue, &pftValue, &byte_140010DE0, &pcchValueBuf);
      pcchValueBuf = 64;
      MsiSummaryInfoGetPropertyA(phSummaryInfo, 7u, &puiDataType, &piValue, &pftValue, &byte_140010F10, &pcchValueBuf);
    }
  }
  PMSIHANDLE::~PMSIHANDLE(&phSummaryInfo);
}

```

## disassembly

```asm
0x1400042b4  push    rbp
0x1400042b6  push    rbx
0x1400042b7  push    rdi
0x1400042b8  mov     rbp, rsp
0x1400042bb  sub     rsp, 50h
0x1400042bf  xor     edi, edi
0x1400042c1  mov     rbx, rcx
0x1400042c4  mov     [rbp+phSummaryInfo], edi
0x1400042c7  test    rcx, rcx
0x1400042ca  jz      loc_14000442B
0x1400042d0  cmp     [rcx], di
0x1400042d3  jz      loc_1400043FC
0x1400042d9  mov     rdx, rcx; szDatabasePath
0x1400042dc  lea     r9, [rbp+phSummaryInfo]; phSummaryInfo
0x1400042e0  xor     ecx, ecx; hDatabase
0x1400042e2  xor     r8d, r8d; uiUpdateCount
0x1400042e5  call    cs:__imp_MsiGetSummaryInformationW
0x1400042eb  test    eax, eax
0x1400042ed  jnz     loc_1400043FC
0x1400042f3  mov     ecx, [rbp+phSummaryInfo]; hSummaryInfo
0x1400042f6  lea     rax, [rbp+arg_0]
0x1400042fa  mov     [rsp+50h+pcchValueBuf], rax; pcchValueBuf
0x1400042ff  lea     r9, [rbp+piValue]; piValue
0x140004303  lea     rax, szValueBuf
0x14000430a  mov     [rbp+puiDataType], edi
0x14000430d  mov     [rsp+50h+szValueBuf], rax; szValueBuf
0x140004312  lea     r8, [rbp+puiDataType]; puiDataType
0x140004316  lea     rax, [rbp+var_10]
0x14000431a  mov     [rbp+piValue], edi
0x14000431d  mov     ebx, 80h
0x140004322  mov     [rsp+50h+pftValue], rax; pftValue
0x140004327  lea     edx, [rdi+4]; uiProperty
0x14000432a  mov     qword ptr [rbp+var_10.dwLowDateTime], rdi
0x14000432e  mov     cs:byte_140010F10, dil
0x140004335  mov     cs:byte_140010DE0, dil
0x14000433c  mov     cs:MultiByteStr, dil
0x140004343  mov     cs:szValueBuf, dil
0x14000434a  mov     [rbp+arg_0], ebx
0x14000434d  call    cs:__imp_MsiSummaryInfoGetPropertyA
0x140004353  mov     ecx, [rbp+phSummaryInfo]; hSummaryInfo
0x140004356  lea     rax, [rbp+arg_0]
0x14000435a  mov     [rsp+50h+pcchValueBuf], rax; pcchValueBuf
0x14000435f  lea     r9, [rbp+piValue]; piValue
0x140004363  lea     rax, MultiByteStr
0x14000436a  mov     [rbp+arg_0], 40h ; '@'
0x140004371  mov     [rsp+50h+szValueBuf], rax; szValueBuf
0x140004376  lea     r8, [rbp+puiDataType]; puiDataType
0x14000437a  lea     rax, [rbp+var_10]
0x14000437e  lea     edx, [rdi+9]; uiProperty
0x140004381  mov     [rsp+50h+pftValue], rax; pftValue
0x140004386  call    cs:__imp_MsiSummaryInfoGetPropertyA
0x14000438c  mov     ecx, [rbp+phSummaryInfo]; hSummaryInfo
0x14000438f  lea     rax, [rbp+arg_0]
0x140004393  mov     [rsp+50h+pcchValueBuf], rax; pcchValueBuf
0x140004398  lea     r9, [rbp+piValue]; piValue
0x14000439c  lea     rax, byte_140010DE0
0x1400043a3  mov     [rbp+arg_0], ebx
0x1400043a6  mov     [rsp+50h+szValueBuf], rax; szValueBuf
0x1400043ab  lea     r8, [rbp+puiDataType]; puiDataType
0x1400043af  lea     rax, [rbp+var_10]
0x1400043b3  lea     edx, [rdi+3]; uiProperty
0x1400043b6  mov     [rsp+50h+pftValue], rax; pftValue
0x1400043bb  call    cs:__imp_MsiSummaryInfoGetPropertyA
0x1400043c1  mov     ecx, [rbp+phSummaryInfo]; hSummaryInfo
0x1400043c4  lea     rax, [rbp+arg_0]
0x1400043c8  mov     [rsp+50h+pcchValueBuf], rax; pcchValueBuf
0x1400043cd  lea     r9, [rbp+piValue]; piValue
0x1400043d1  lea     rax, byte_140010F10
0x1400043d8  mov     [rbp+arg_0], 40h ; '@'
0x1400043df  mov     [rsp+50h+szValueBuf], rax; szValueBuf
0x1400043e4  lea     r8, [rbp+puiDataType]; puiDataType
0x1400043e8  lea     rax, [rbp+var_10]
0x1400043ec  lea     edx, [rdi+7]; uiProperty
0x1400043ef  mov     [rsp+50h+pftValue], rax; pftValue
0x1400043f4  call    cs:__imp_MsiSummaryInfoGetPropertyA
0x1400043fa  jmp     short loc_14000442B
0x1400043fc  mov     [rsp+50h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x140004401  lea     rax, MultiByteStr
0x140004408  mov     [rsp+50h+pcchValueBuf], rdi; lpDefaultChar
0x14000440d  or      r9d, 0FFFFFFFFh; cchWideChar
0x140004411  mov     dword ptr [rsp+50h+szValueBuf], 40h ; '@'; cbMultiByte
0x140004419  mov     r8, rbx; lpWideCharStr
0x14000441c  xor     edx, edx; dwFlags
0x14000441e  mov     [rsp+50h+pftValue], rax; lpMultiByteStr
0x140004423  xor     ecx, ecx; CodePage
0x140004425  call    cs:__imp_WideCharToMultiByte
0x14000442b  lea     rcx, [rbp+phSummaryInfo]; this
0x14000442f  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x140004434  add     rsp, 50h
0x140004438  pop     rdi
0x140004439  pop     rbx
0x14000443a  pop     rbp
0x14000443b  retn
```
