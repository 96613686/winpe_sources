# CMachineEnroller::ReadInProvisioningXML(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x180050884`
- end: `0x180050af7`
- name: `?ReadInProvisioningXML@CMachineEnroller@@SAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `627`
- prototype: `static int(const unsigned __int16 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180050558`

## callees

- `0x18001367c`
- `0x1800140d0`
- `0x180014148`
- `0x18001aec8`
- `0x1800206a8`
- `0x180020cb4`
- `0x18003aabc`
- `0x18003dba8`
- `0x180050884`
- `0x180050b00`
- `0x180051824`
- `0x18005d01c`
- `0x180072464`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800508f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050a99`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800508e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800508e6`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180050972`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180050972`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180050914`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180050914`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800509b2`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800509b2`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ad6`
- `OLEAUT32!__imp_SysFreeString` at `0x180050a8a`
- `OLEAUT32!__imp_SysFreeString` at `0x180050ad6`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18005099e`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x1800509d6`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x18005099e`
- `DMCmnUtils!SafeMultiByteToWideChar` at `0x1800509d6`

## string_xrefs

- `0x1800508b7`: `CMachineEnroller::ReadInProvisioningXML`
- `0x180050a4b`: `UpdatedProvXML.txt`
- `0x180050a6b`: `UpdatedProvXML.txt`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CMachineEnroller::ReadInProvisioningXML(const unsigned __int16 *a1, LPVOID *a2)
{
  OLECHAR *v3; // r15
  char *v4; // rsi
  HANDLE FileW; // rax
  void *v6; // r14
  signed int LastError; // eax
  DWORD FileSize; // eax
  DWORD v9; // ebx
  char *v10; // rax
  UINT v11; // eax
  UINT v12; // edi
  unsigned __int16 *v13; // rax
  LPVOID v14; // rdi
  HRESULT (__stdcall *v15)(IXMLDOMDocument2 *, BSTR *); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rcx
  CEnrollmentLogger *Logger; // rax
  unsigned int v20; // ebx
  __int64 v21; // rdx
  unsigned __int16 *v23[2]; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-10h] BYREF
  int inited; // [rsp+A0h] [rbp+40h] BYREF
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF

  inited = 0;
  v3 = 0;
  v4 = 0;
  NumberOfBytesRead = 0;
  v23[1] = 0;
  v23[0] = 0;
  v24[0] = "CMachineEnroller::ReadInProvisioningXML";
  v24[1] = &inited;
  FileW = CreateFileW(a1, 0x80000000, 0, 0, 3u, 0, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
    goto LABEL_2;
  FileSize = GetFileSize(FileW, 0);
  if ( FileSize == -1 )
    goto LABEL_2;
  if ( !FileSize )
  {
    inited = 1006;
    goto LABEL_22;
  }
  v9 = FileSize + 1;
  if ( FileSize + 1 < FileSize )
  {
    inited = -2147024362;
    goto LABEL_22;
  }
  inited = 0;
  v10 = (char *)SafeHeapAlloc(v9);
  v4 = v10;
  if ( !v10 )
  {
LABEL_10:
    inited = -2147024882;
    goto LABEL_22;
  }
  if ( !ReadFile(v6, v10, v9, &NumberOfBytesRead, 0) )
    goto LABEL_2;
  v11 = SafeMultiByteToWideChar(0xFDE9u, 0, v4, v9, 0, 0);
  v12 = v11;
  if ( !v11 )
    goto LABEL_2;
  v13 = SysAllocStringLen(0, v11);
  v3 = v13;
  if ( !v13 )
    goto LABEL_10;
  if ( SafeMultiByteToWideChar(0xFDE9u, 0, v4, v9, v13, v12) == v12 )
  {
    inited = InitXMLDOMDoc(v3, 0, a2);
    if ( inited >= 0 )
    {
      inited = CMachineEnroller::VerifyValidNodePaths((struct IXMLDOMDocument2 *)*a2);
      if ( inited >= 0 )
      {
        CMachineEnroller::RemoveProvXMLNode(
          (struct IXMLDOMDocument2 *)*a2,
          L"//characteristic[@type='PrivateKeyContainer']",
          0);
        v14 = *a2;
        v15 = *(HRESULT (__stdcall **)(IXMLDOMDocument2 *, BSTR *))(*(_QWORD *)*a2 + 272LL);
        v16 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v23);
        inited = ((__int64 (__fastcall *)(LPVOID, __int64))v15)(v14, v16);
        if ( inited >= 0 )
        {
          v17 = WriteToTempFile(v23[0], L"UpdatedProvXML.txt");
          if ( v17 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
            McTemplateU0zq_EventWriteTransfer(v18, SavingTempFileFailedEvent, L"UpdatedProvXML.txt", (unsigned int)v17);
        }
      }
    }
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    inited = LastError;
  }
LABEL_22:
  SysFreeString(v3);
  if ( v6 != (void *)-1LL )
    CloseHandle(v6);
  if ( inited < 0 )
  {
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogEnrollProvisioningFail(Logger, inited);
  }
  SafeHeapFree(v4);
  v20 = inited;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v24, v21);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v23);
  SysFreeString(0);
  return v20;
}

```

## disassembly

```asm
0x180050884  mov     [rsp-28h+arg_0], rbx
0x180050889  mov     [rsp-28h+arg_8], rsi
0x18005088e  push    rbp
0x18005088f  push    rdi
0x180050890  push    r12
0x180050892  push    r14
0x180050894  push    r15
0x180050896  mov     rbp, rsp
0x180050899  sub     rsp, 60h
0x18005089d  mov     r12, rdx
0x1800508a0  mov     [rbp+arg_10], 0
0x1800508a7  xor     r15d, r15d
0x1800508aa  xor     esi, esi
0x1800508ac  mov     [rbp+NumberOfBytesRead], esi
0x1800508af  mov     [rbp+var_18], rsi
0x1800508b3  mov     [rbp+var_20], rsi
0x1800508b7  lea     rax, aCmachineenroll_3; "CMachineEnroller::ReadInProvisioningXML"
0x1800508be  mov     [rbp+var_10], rax
0x1800508c2  lea     rax, [rbp+arg_10]
0x1800508c6  mov     [rbp+var_8], rax
0x1800508ca  mov     [rsp+60h+hTemplateFile], rsi; hTemplateFile
0x1800508cf  mov     [rsp+60h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x1800508d3  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x1800508db  xor     r9d, r9d; lpSecurityAttributes
0x1800508de  xor     r8d, r8d; dwShareMode
0x1800508e1  mov     edx, 80000000h; dwDesiredAccess
0x1800508e6  call    cs:__imp_CreateFileW
0x1800508ec  mov     r14, rax
0x1800508ef  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800508f3  jnz     short loc_18005090F
0x1800508f5  call    cs:__imp_GetLastError
0x1800508fb  test    eax, eax
0x1800508fd  jle     short loc_180050907
0x1800508ff  movzx   eax, ax
0x180050902  or      eax, 80070000h
0x180050907  mov     [rbp+arg_10], eax
0x18005090a  jmp     loc_180050A87
0x18005090f  xor     edx, edx; lpFileSizeHigh
0x180050911  mov     rcx, r14; hFile
0x180050914  call    cs:__imp_GetFileSize
0x18005091a  cmp     eax, 0FFFFFFFFh
0x18005091d  jz      short loc_1800508F5
0x18005091f  test    eax, eax
0x180050921  jnz     short loc_18005092F
0x180050923  mov     [rbp+arg_10], 3EEh
0x18005092a  jmp     loc_180050A87
0x18005092f  lea     ebx, [rax+1]
0x180050932  cmp     ebx, eax
0x180050934  jb      loc_180050A80
0x18005093a  mov     [rbp+arg_10], 0
0x180050941  mov     ecx, ebx; unsigned __int64
0x180050943  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x180050948  mov     rsi, rax
0x18005094b  test    rax, rax
0x18005094e  jnz     short loc_18005095C
0x180050950  mov     [rbp+arg_10], 8007000Eh
0x180050957  jmp     loc_180050A87
0x18005095c  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x180050965  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180050969  mov     r8d, ebx; nNumberOfBytesToRead
0x18005096c  mov     rdx, rsi; lpBuffer
0x18005096f  mov     rcx, r14; hFile
0x180050972  call    cs:__imp_ReadFile
0x180050978  test    eax, eax
0x18005097a  jz      loc_1800508F5
0x180050980  mov     [rsp+60h+dwFlagsAndAttributes], 0
0x180050988  mov     qword ptr [rsp+60h+dwCreationDisposition], 0
0x180050991  mov     r9d, ebx
0x180050994  mov     r8, rsi
0x180050997  xor     edx, edx
0x180050999  mov     ecx, 0FDE9h
0x18005099e  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x1800509a4  mov     edi, eax
0x1800509a6  test    eax, eax
0x1800509a8  jz      loc_1800508F5
0x1800509ae  mov     edx, eax; ui
0x1800509b0  xor     ecx, ecx; strIn
0x1800509b2  call    cs:__imp_SysAllocStringLen
0x1800509b8  mov     r15, rax
0x1800509bb  test    rax, rax
0x1800509be  jz      short loc_180050950
0x1800509c0  mov     [rsp+60h+dwFlagsAndAttributes], edi
0x1800509c4  mov     qword ptr [rsp+60h+dwCreationDisposition], rax
0x1800509c9  mov     r9d, ebx
0x1800509cc  mov     r8, rsi
0x1800509cf  xor     edx, edx
0x1800509d1  mov     ecx, 0FDE9h
0x1800509d6  call    cs:__imp_?SafeMultiByteToWideChar@@YAHIKPEBDHPEAGH@Z; SafeMultiByteToWideChar(uint,ulong,char const *,int,ushort *,int)
0x1800509dc  cmp     eax, edi
0x1800509de  jnz     loc_1800508F5
0x1800509e4  mov     r8, r12; ppv
0x1800509e7  xor     edx, edx; OLECHAR *
0x1800509e9  mov     rcx, r15; psz
0x1800509ec  call    ?InitXMLDOMDoc@@YAJPEBG0PEAPEAUIXMLDOMDocument2@@@Z; InitXMLDOMDoc(ushort const *,ushort const *,IXMLDOMDocument2 * *)
0x1800509f1  mov     [rbp+arg_10], eax
0x1800509f4  test    eax, eax
0x1800509f6  js      loc_180050A87
0x1800509fc  mov     rcx, [r12]; struct IXMLDOMDocument2 *
0x180050a00  call    ?VerifyValidNodePaths@CMachineEnroller@@CAJPEAUIXMLDOMDocument2@@@Z; CMachineEnroller::VerifyValidNodePaths(IXMLDOMDocument2 *)
0x180050a05  mov     [rbp+arg_10], eax
0x180050a08  test    eax, eax
0x180050a0a  js      short loc_180050A87
0x180050a0c  xor     r8d, r8d; unsigned __int16 *
0x180050a0f  lea     rdx, aCharacteristic; "//characteristic[@type='PrivateKeyConta"...
0x180050a16  mov     rcx, [r12]; struct IXMLDOMDocument2 *
0x180050a1a  call    ?RemoveProvXMLNode@CMachineEnroller@@SAJPEAUIXMLDOMDocument2@@PEBG1@Z; CMachineEnroller::RemoveProvXMLNode(IXMLDOMDocument2 *,ushort const *,ushort const *)
0x180050a1f  mov     rdi, [r12]
0x180050a23  mov     rax, [rdi]
0x180050a26  mov     rbx, [rax+110h]
0x180050a2d  lea     rcx, [rbp+var_20]
0x180050a31  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x180050a36  mov     rdx, rax
0x180050a39  mov     rcx, rdi
0x180050a3c  mov     rax, rbx
0x180050a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050a44  mov     [rbp+arg_10], eax
0x180050a47  test    eax, eax
0x180050a49  js      short loc_180050A87
0x180050a4b  lea     rdx, aUpdatedprovxml; "UpdatedProvXML.txt"
0x180050a52  mov     rcx, [rbp+var_20]; unsigned __int16 *
0x180050a56  call    ?WriteToTempFile@@YAJPEBG0@Z; WriteToTempFile(ushort const *,ushort const *)
0x180050a5b  test    eax, eax
0x180050a5d  jns     short loc_180050A87
0x180050a5f  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x180050a66  jz      short loc_180050A87
0x180050a68  mov     r9d, eax
0x180050a6b  lea     r8, aUpdatedprovxml; "UpdatedProvXML.txt"
0x180050a72  lea     rdx, SavingTempFileFailedEvent
0x180050a79  call    McTemplateU0zq_EventWriteTransfer
0x180050a7e  jmp     short loc_180050A87
0x180050a80  mov     [rbp+arg_10], 80070216h
0x180050a87  mov     rcx, r15; bstrString
0x180050a8a  call    cs:__imp_SysFreeString
0x180050a90  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180050a94  jz      short loc_180050A9F
0x180050a96  mov     rcx, r14; hObject
0x180050a99  call    cs:__imp_CloseHandle
0x180050a9f  cmp     [rbp+arg_10], 0
0x180050aa3  jge     short loc_180050AB5
0x180050aa5  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180050aaa  mov     edx, [rbp+arg_10]; int
0x180050aad  mov     rcx, rax; this
0x180050ab0  call    ?LogEnrollProvisioningFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollProvisioningFail(long)
0x180050ab5  mov     rcx, rsi; void *
0x180050ab8  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180050abd  mov     ebx, [rbp+arg_10]
0x180050ac0  lea     rcx, [rbp+var_10]; this
0x180050ac4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180050ac9  nop
0x180050aca  lea     rcx, [rbp+var_20]
0x180050ace  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180050ad3  nop
0x180050ad4  xor     ecx, ecx; bstrString
0x180050ad6  call    cs:__imp_SysFreeString
0x180050adc  mov     eax, ebx
0x180050ade  lea     r11, [rsp+60h+var_s0]
0x180050ae3  mov     rbx, [r11+30h]
0x180050ae7  mov     rsi, [r11+38h]
0x180050aeb  mov     rsp, r11
0x180050aee  pop     r15
0x180050af0  pop     r14
0x180050af2  pop     r12
0x180050af4  pop     rdi
0x180050af5  pop     rbp
0x180050af6  retn
```
