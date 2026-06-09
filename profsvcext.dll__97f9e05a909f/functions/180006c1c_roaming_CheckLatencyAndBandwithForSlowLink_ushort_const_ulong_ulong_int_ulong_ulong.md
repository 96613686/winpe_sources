# roaming::_CheckLatencyAndBandwithForSlowLink(ushort const *,ulong,ulong,int &,ulong *,ulong *)

- ea: `0x180006c1c`
- end: `0x180007293`
- name: `?_CheckLatencyAndBandwithForSlowLink@roaming@@YAJPEBGKKAEAHPEAK2@Z`
- size: `1655`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, unsigned int, _DWORD *, int *, unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fed8`

## callees

- `0x180005960`
- `0x180006a80`
- `0x180006a9c`
- `0x180006c1c`
- `0x18000729c`
- `0x180008b1c`
- `0x18000a520`
- `0x18000a8f0`
- `0x18000aef8`
- `0x18000fca8`
- `0x18000fe30`
- `0x18000feb8`
- `0x180010470`
- `0x18001059c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180006ea2`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180006f90`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180006ea2`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x180006f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ce5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006ce5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cf3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180006cf3`
- `ntdll!RtlInitUnicodeString` at `0x180006c98`
- `ntdll!RtlInitUnicodeString` at `0x180006cad`
- `ntdll!RtlInitUnicodeString` at `0x180006cc5`
- `ntdll!RtlInitUnicodeString` at `0x180006c98`
- `ntdll!RtlInitUnicodeString` at `0x180006cad`
- `ntdll!RtlInitUnicodeString` at `0x180006cc5`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d33`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d4c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d79`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d33`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d4c`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180006d79`
- `ntdll!NtCreateFile` at `0x180006dfb`
- `ntdll!NtCreateFile` at `0x180006dfb`
- `ntdll!NtFsControlFile` at `0x180006f74`
- `ntdll!NtFsControlFile` at `0x180006f74`
- `ntdll!NtReadFile` at `0x180007084`
- `ntdll!NtReadFile` at `0x180007084`
- `ntdll!NtWriteFile` at `0x180006efe`
- `ntdll!NtWriteFile` at `0x180006fec`
- `ntdll!NtWriteFile` at `0x180006efe`
- `ntdll!NtWriteFile` at `0x180006fec`

## string_xrefs

- `0x180006d09`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x1800070a4`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x1800070ef`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x18000715b`: `clientcore\ds\security\gina\profile\roaming\network.cpp`
- `0x18000723e`: `clientcore\ds\security\gina\profile\roaming\network.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall roaming::_CheckLatencyAndBandwithForSlowLink(
        const WCHAR *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        _DWORD *a4,
        int *a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v10; // rax
  NTSTATUS appended; // eax
  unsigned int v12; // r8d
  __int64 v13; // rdx
  unsigned int v14; // ebx
  NTSTATUS v15; // eax
  unsigned int v16; // r8d
  ULONG v17; // edi
  _BYTE *v18; // rbx
  ULONG v19; // eax
  ULONG i; // esi
  int v21; // eax
  char v22; // r8
  int v23; // edx
  __int64 v24; // rax
  NTSTATUS v25; // eax
  unsigned int v26; // r8d
  __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  int v29; // edi
  ULONG j; // esi
  int v31; // eax
  char v32; // r8
  int v33; // edx
  __int64 v34; // rax
  unsigned int *v35; // r9
  unsigned int v36; // r14d
  ULONG v37; // r12d
  PVOID v38; // rsi
  unsigned int v39; // eax
  unsigned __int64 v40; // rdx
  int NetworkPerformance; // eax
  unsigned __int64 v43; // rdx
  int v44; // r8d
  int v45; // esi
  unsigned int v46; // edi
  unsigned int v47; // ecx
  _DWORD *v48; // r12
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  int AllocationSizea; // [rsp+20h] [rbp-E0h]
  int AllocationSizeb; // [rsp+20h] [rbp-E0h]
  ULONG Length; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  PVOID Buffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v55; // [rsp+78h] [rbp-88h]
  unsigned int v56; // [rsp+80h] [rbp-80h] BYREF
  PVOID v57; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v58; // [rsp+90h] [rbp-70h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+98h] [rbp-68h] BYREF
  _DWORD *v60; // [rsp+A8h] [rbp-58h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  int *v62; // [rsp+C0h] [rbp-40h]
  _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  UNICODE_STRING Source; // [rsp+D8h] [rbp-28h] BYREF
  UNICODE_STRING v65; // [rsp+E8h] [rbp-18h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD InputBuffer[2]; // [rsp+128h] [rbp+28h] BYREF
  char v68[16]; // [rsp+148h] [rbp+48h] BYREF
  unsigned int *v69; // [rsp+158h] [rbp+58h]
  __int64 v70; // [rsp+160h] [rbp+60h]
  PVOID *p_Buffer; // [rsp+168h] [rbp+68h]
  __int64 v72; // [rsp+170h] [rbp+70h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v60 = a4;
  v55 = a3;
  v56 = (unsigned int)a2;
  v62 = a5;
  *a4 = 0;
  if ( a5 )
    *a5 = 0;
  v7 = 0;
  if ( a6 )
    *a6 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Mup");
  Source = 0;
  RtlInitUnicodeString(&Source, this + 1);
  v65 = 0;
  RtlInitUnicodeString(&v65, L"\\6A6DCA49-668C-4DD1-8A7F-9D5B61E8EE92.tmp");
  v8 = (unsigned __int16)(DestinationString.Length + Source.Length + v65.Length);
  *(_QWORD *)&Destination.Length = 0;
  *(_DWORD *)&Destination.MaximumLength = v8;
  ProcessHeap = GetProcessHeap();
  v10 = (WCHAR *)HeapAlloc(ProcessHeap, 0, v8);
  Destination.Buffer = v10;
  if ( !v10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4A3,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)0x8007000ELL,
      AllocationSize);
    return 2147942414LL;
  }
  v58 = v10;
  appended = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
  if ( appended < 0 )
  {
    v13 = 1191;
LABEL_11:
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v13,
            v12,
            (const char *)(unsigned int)appended,
            AllocationSize);
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
    return v14;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &Source);
  if ( appended < 0 )
  {
    v13 = 1192;
    goto LABEL_11;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, &v65);
  if ( appended < 0 )
  {
    v13 = 1193;
    goto LABEL_11;
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  v15 = NtCreateFile(&FileHandle, 0xC0110000, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 2u, 0x106Au, 0, 0);
  if ( v15 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x4BF,
            v16,
            (const char *)(unsigned int)v15,
            AllocationSizea);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&FileHandle);
    goto LABEL_49;
  }
  Length = 0x10000;
  if ( (int)SHRegGetDWORD(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
              L"PingBufferSize",
              &Length) < 0
    || (v17 = Length, Length < 0x800) )
  {
    v17 = 0x10000;
    Length = 0x10000;
  }
  if ( v17 > 0x400000 )
  {
    v17 = 0x400000;
    Length = 0x400000;
  }
  wil::make_unique_nothrow<char [0]>(&Buffer, v17);
  v18 = Buffer;
  if ( !Buffer )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4D2,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)0x8007000ELL,
      AllocationSizea);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&FileHandle);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
    return 2147942414LL;
  }
  v19 = Length;
  for ( i = 0; i < Length; v19 = Length )
  {
    v21 = rand();
    v22 = v21;
    v23 = (unsigned __int64)(1321528399LL * v21) >> 32;
    v24 = i++;
    v18[v24] = v22 - 26 * ((v23 < 0) + (v23 >> 3)) + 97;
  }
  v25 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v18, v19, 0, 0);
  if ( v25 < 0 )
  {
    v27 = 1250;
LABEL_26:
    v29 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v27,
            v26,
            (const char *)(unsigned int)v25,
            AllocationSizeb);
LABEL_46:
    if ( v18 )
      operator delete(v18, v28);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&FileHandle);
    v14 = v29;
    goto LABEL_49;
  }
  memset(InputBuffer, 0, sizeof(InputBuffer));
  LOWORD(InputBuffer[0]) = 32;
  DWORD1(InputBuffer[0]) = 2;
  BYTE8(InputBuffer[0]) = 1;
  v25 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x1401F0u, InputBuffer, 0x20u, 0, 0);
  if ( v25 < 0 )
  {
    v27 = 1269;
    goto LABEL_26;
  }
  Length = 0x2000;
  for ( j = 0; j < Length; ++j )
  {
    v31 = rand();
    v32 = v31;
    v33 = (unsigned __int64)(1321528399LL * v31) >> 32;
    v34 = j;
    v18[v34] = v32 - 26 * ((v33 < 0) + (v33 >> 3)) + 97;
  }
  v25 = NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, v18, Length, 0, 0);
  if ( v25 < 0 )
  {
    v27 = 1289;
    goto LABEL_26;
  }
  v36 = 0;
LABEL_34:
  if ( v36 < 4 )
  {
    v17 += Length;
    Buffer = 0;
    v37 = v17 >> 2;
    while ( 1 )
    {
      if ( v7 >= 4 )
      {
        ++v36;
        v7 = 0;
        goto LABEL_34;
      }
      wil::make_unique_nothrow<char [0]>(&v57, v37);
      v38 = v57;
      if ( !v57 )
        break;
      memset_0(v57, 0, v37);
      v39 = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, v38, v17 >> 2, (PLARGE_INTEGER)&Buffer, 0);
      v40 = 0x80000000LL;
      if ( (int)(v39 + 0x80000000) >= 0 && v39 != -1073741807 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x52F,
          (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
          (const char *)v39,
          AllocationSizeb);
      Buffer = (char *)Buffer + v37;
      v57 = 0;
      if ( v38 )
        operator delete(v38, v40);
      ++v7;
    }
    v29 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x518,
      (unsigned int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)0x8007000ELL,
      AllocationSizeb);
    goto LABEL_46;
  }
  LODWORD(Buffer) = 0;
  LODWORD(v57) = -1;
  NetworkPerformance = roaming::_GetNetworkPerformance(FileHandle, &Buffer, (unsigned int *)&v57, v35);
  if ( NetworkPerformance < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x53B,
      (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\network.cpp",
      (const char *)(unsigned int)NetworkPerformance);
  v45 = (int)Buffer;
  v46 = (unsigned int)v57;
  if ( (unsigned int)Buffer < v56 )
  {
    v48 = v60;
    *v60 = 0;
    if ( v46 )
    {
      v47 = v55;
      *v48 = v46 < v55;
      goto LABEL_55;
    }
  }
  else
  {
    *v60 = 1;
  }
  v47 = v55;
LABEL_55:
  if ( Microsoft_Windows_User_Profiles_ServiceEnableBits < 0 )
  {
    LODWORD(Buffer) = v47;
    v69 = &v56;
    v56 = v46;
    p_Buffer = &Buffer;
    v70 = 4;
    v72 = 4;
    McGenEventWrite_EtwEventWriteTransfer(v47, (unsigned int)EVENT_RUP_SLOWLINK_BANDWIDTH, v44, 3, (__int64)v68);
  }
  if ( a6 )
    *a6 = v46;
  if ( v62 )
    *v62 = v45;
  if ( v18 )
    operator delete(v18, v43);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&FileHandle);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v58);
  return 0;
}

```

## disassembly

```asm
0x180006c1c  mov     [rsp-8+arg_8], rbx
0x180006c21  push    rbp
0x180006c22  push    rsi
0x180006c23  push    rdi
0x180006c24  push    r12
0x180006c26  push    r13
0x180006c28  push    r14
0x180006c2a  push    r15
0x180006c2c  lea     rbp, [rsp-80h]
0x180006c31  sub     rsp, 180h
0x180006c38  mov     rax, cs:__security_cookie
0x180006c3f  xor     rax, rsp
0x180006c42  mov     [rbp+0B0h+var_38], rax
0x180006c46  mov     r15, [rbp+0B0h+arg_20]
0x180006c4d  mov     rbx, rcx
0x180006c50  mov     r13, [rbp+0B0h+arg_28]
0x180006c57  mov     [rbp+0B0h+var_108], r9
0x180006c5b  mov     [rsp+1B0h+var_138], r8d
0x180006c60  mov     [rbp+0B0h+var_130], edx
0x180006c63  mov     [rbp+0B0h+var_F0], r15
0x180006c67  mov     dword ptr [r9], 0
0x180006c6e  test    r15, r15
0x180006c71  jz      short loc_180006C7A
0x180006c73  mov     dword ptr [r15], 0
0x180006c7a  xor     r15d, r15d
0x180006c7d  test    r13, r13
0x180006c80  jz      short loc_180006C86
0x180006c82  mov     [r13+0], r15d
0x180006c86  xorps   xmm0, xmm0
0x180006c89  lea     rdx, SourceString; "\\Device\\Mup"
0x180006c90  lea     rcx, [rbp+0B0h+DestinationString]; DestinationString
0x180006c94  movups  xmmword ptr [rbp+0B0h+DestinationString.Length], xmm0
0x180006c98  call    cs:__imp_RtlInitUnicodeString
0x180006c9e  xorps   xmm0, xmm0
0x180006ca1  lea     rdx, [rbx+2]; SourceString
0x180006ca5  lea     rcx, [rbp+0B0h+Source]; DestinationString
0x180006ca9  movups  xmmword ptr [rbp+0B0h+Source.Length], xmm0
0x180006cad  call    cs:__imp_RtlInitUnicodeString
0x180006cb3  xorps   xmm0, xmm0
0x180006cb6  lea     rdx, a6a6dca49668c4d; "\\6A6DCA49-668C-4DD1-8A7F-9D5B61E8EE92."...
0x180006cbd  lea     rcx, [rbp+0B0h+var_C8]; DestinationString
0x180006cc1  movups  xmmword ptr [rbp+0B0h+var_C8.Length], xmm0
0x180006cc5  call    cs:__imp_RtlInitUnicodeString
0x180006ccb  movzx   eax, [rbp+0B0h+var_C8.Length]
0x180006ccf  xorps   xmm0, xmm0
0x180006cd2  add     ax, [rbp+0B0h+Source.Length]
0x180006cd6  add     ax, [rbp+0B0h+DestinationString.Length]
0x180006cda  movzx   ebx, ax
0x180006cdd  movups  xmmword ptr [rbp+0B0h+Destination.Length], xmm0
0x180006ce1  mov     [rbp+0B0h+Destination.MaximumLength], bx
0x180006ce5  call    cs:__imp_GetProcessHeap
0x180006ceb  mov     r8d, ebx; dwBytes
0x180006cee  xor     edx, edx; dwFlags
0x180006cf0  mov     rcx, rax; hHeap
0x180006cf3  call    cs:__imp_HeapAlloc
0x180006cf9  mov     [rbp+0B0h+Destination.Buffer], rax
0x180006cfd  test    rax, rax
0x180006d00  jnz     short loc_180006D27
0x180006d02  mov     rcx, [rbp+0B8h]; this
0x180006d09  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x180006d10  mov     edi, 8007000Eh
0x180006d15  mov     edx, 4A3h; void *
0x180006d1a  mov     r9d, edi; char *
0x180006d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d22  jmp     loc_18000726A
0x180006d27  lea     rdx, [rbp+0B0h+DestinationString]; Source
0x180006d2b  mov     [rbp+0B0h+var_120], rax
0x180006d2f  lea     rcx, [rbp+0B0h+Destination]; Destination
0x180006d33  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006d39  test    eax, eax
0x180006d3b  jns     short loc_180006D44
0x180006d3d  mov     edx, 4A7h
0x180006d42  jmp     short loc_180006D5B
0x180006d44  lea     rdx, [rbp+0B0h+Source]; Source
0x180006d48  lea     rcx, [rbp+0B0h+Destination]; Destination
0x180006d4c  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006d52  test    eax, eax
0x180006d54  jns     short loc_180006D71
0x180006d56  mov     edx, 4A8h; void *
0x180006d5b  mov     rcx, [rbp+0B8h]; this
0x180006d62  mov     r9d, eax; char *
0x180006d65  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006d6a  mov     ebx, eax
0x180006d6c  jmp     loc_180007121
0x180006d71  lea     rdx, [rbp+0B0h+var_C8]; Source
0x180006d75  lea     rcx, [rbp+0B0h+Destination]; Destination
0x180006d79  call    cs:__imp_RtlAppendUnicodeStringToString
0x180006d7f  test    eax, eax
0x180006d81  jns     short loc_180006D8A
0x180006d83  mov     edx, 4A9h
0x180006d88  jmp     short loc_180006D5B
0x180006d8a  mov     [rsp+1B0h+EaLength], r15d; EaLength
0x180006d8f  lea     rax, [rbp+0B0h+Destination]
0x180006d93  mov     [rsp+1B0h+EaBuffer], r15; EaBuffer
0x180006d98  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x180006d9c  mov     [rsp+1B0h+CreateOptions], 106Ah; CreateOptions
0x180006da4  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x180006da8  xorps   xmm0, xmm0
0x180006dab  mov     qword ptr [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x180006db3  mov     r14d, 2
0x180006db9  mov     qword ptr [rbp+0B0h+ObjectAttributes.Attributes], 40h ; '@'
0x180006dc1  mov     [rsp+1B0h+CreateDisposition], r14d; CreateDisposition
0x180006dc6  lea     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x180006dcb  mov     [rsp+1B0h+ShareAccess], 7; ShareAccess
0x180006dd3  mov     edx, 0C0110000h; DesiredAccess
0x180006dd8  mov     [rsp+1B0h+FileAttributes], 80h; FileAttributes
0x180006de0  mov     [rsp+1B0h+AllocationSize], r15; int
0x180006de5  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], r15
0x180006de9  mov     [rbp+0B0h+ObjectAttributes.ObjectName], rax
0x180006ded  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006df2  mov     [rsp+1B0h+FileHandle], r15
0x180006df7  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x180006dfb  call    cs:__imp_NtCreateFile
0x180006e01  test    eax, eax
0x180006e03  jns     short loc_180006E2A
0x180006e05  mov     rcx, [rbp+0B8h]; this
0x180006e0c  mov     r9d, eax; char *
0x180006e0f  mov     edx, 4BFh; void *
0x180006e14  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006e19  lea     rcx, [rsp+1B0h+FileHandle]
0x180006e1e  mov     ebx, eax
0x180006e20  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?NtClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&NtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180006e25  jmp     loc_180007121
0x180006e2a  mov     ebx, 10000h
0x180006e2f  lea     r9, [rsp+1B0h+Length]; unsigned int *
0x180006e34  lea     r8, aPingbuffersize; "PingBufferSize"
0x180006e3b  mov     [rsp+1B0h+Length], ebx
0x180006e3f  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows NT\\Curren"...
0x180006e46  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180006e4d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180006e52  test    eax, eax
0x180006e54  js      short loc_180006E62
0x180006e56  mov     edi, [rsp+1B0h+Length]
0x180006e5a  cmp     edi, 800h
0x180006e60  jnb     short loc_180006E68
0x180006e62  mov     edi, ebx
0x180006e64  mov     [rsp+1B0h+Length], ebx
0x180006e68  mov     eax, 400000h
0x180006e6d  cmp     edi, eax
0x180006e6f  jbe     short loc_180006E77
0x180006e71  mov     edi, eax
0x180006e73  mov     [rsp+1B0h+Length], eax
0x180006e77  mov     edx, edi
0x180006e79  lea     rcx, [rsp+1B0h+Buffer]
0x180006e7e  call    ??$make_unique_nothrow@$$BY0A@D@wil@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<char [0]>(unsigned __int64)
0x180006e83  mov     rbx, [rsp+1B0h+Buffer]
0x180006e88  test    rbx, rbx
0x180006e8b  jz      loc_180007237
0x180006e91  mov     eax, [rsp+1B0h+Length]
0x180006e95  mov     esi, r15d
0x180006e98  mov     r12d, 4EC4EC4Fh
0x180006e9e  test    eax, eax
0x180006ea0  jz      short loc_180006ED5
0x180006ea2  call    cs:__imp_rand
0x180006ea8  mov     r8d, eax
0x180006eab  mov     eax, r12d
0x180006eae  imul    r8d
0x180006eb1  mov     eax, esi
0x180006eb3  inc     esi
0x180006eb5  sar     edx, 3
0x180006eb8  mov     ecx, edx
0x180006eba  shr     ecx, 1Fh
0x180006ebd  add     edx, ecx
0x180006ebf  imul    ecx, edx, 1Ah
0x180006ec2  sub     r8d, ecx
0x180006ec5  add     r8b, 61h ; 'a'
0x180006ec9  mov     [rax+rbx], r8b
0x180006ecd  mov     eax, [rsp+1B0h+Length]
0x180006ed1  cmp     esi, eax
0x180006ed3  jb      short loc_180006EA2
0x180006ed5  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x180006eda  xor     r9d, r9d; ApcContext
0x180006edd  mov     qword ptr [rsp+1B0h+CreateOptions], r15; Key
0x180006ee2  xor     r8d, r8d; ApcRoutine
0x180006ee5  mov     qword ptr [rsp+1B0h+CreateDisposition], r15; ByteOffset
0x180006eea  xor     edx, edx; Event
0x180006eec  mov     [rsp+1B0h+ShareAccess], eax; Length
0x180006ef0  lea     rax, [rbp+0B0h+IoStatusBlock]
0x180006ef4  mov     qword ptr [rsp+1B0h+FileAttributes], rbx; Buffer
0x180006ef9  mov     [rsp+1B0h+AllocationSize], rax; int
0x180006efe  call    cs:__imp_NtWriteFile
0x180006f04  test    eax, eax
0x180006f06  jns     short loc_180006F23
0x180006f08  mov     edx, 4E2h; void *
0x180006f0d  mov     rcx, [rbp+0B8h]; this
0x180006f14  mov     r9d, eax; char *
0x180006f17  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180006f1c  mov     edi, eax
0x180006f1e  jmp     loc_180007108
0x180006f23  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x180006f28  xorps   xmm0, xmm0
0x180006f2b  mov     dword ptr [rsp+1B0h+EaBuffer], r15d; OutputBufferLength
0x180006f30  mov     eax, 20h ; ' '
0x180006f35  movups  [rbp+0B0h+InputBuffer], xmm0
0x180006f39  mov     qword ptr [rsp+1B0h+CreateOptions], r15; OutputBuffer
0x180006f3e  xor     r9d, r9d; ApcContext
0x180006f41  mov     [rsp+1B0h+CreateDisposition], eax; InputBufferLength
0x180006f45  xor     r8d, r8d; ApcRoutine
0x180006f48  mov     word ptr [rbp+0B0h+InputBuffer], ax
0x180006f4c  xor     edx, edx; Event
0x180006f4e  lea     rax, [rbp+0B0h+InputBuffer]
0x180006f52  mov     dword ptr [rbp+0B0h+InputBuffer+4], r14d
0x180006f56  mov     qword ptr [rsp+1B0h+ShareAccess], rax; InputBuffer
0x180006f5b  lea     rax, [rbp+0B0h+IoStatusBlock]
0x180006f5f  mov     [rsp+1B0h+FileAttributes], 1401F0h; FsControlCode
0x180006f67  mov     [rsp+1B0h+AllocationSize], rax; IoStatusBlock
0x180006f6c  movups  [rbp+0B0h+var_78], xmm0
0x180006f70  mov     byte ptr [rbp+0B0h+InputBuffer+8], 1
0x180006f74  call    cs:__imp_NtFsControlFile
0x180006f7a  test    eax, eax
0x180006f7c  jns     short loc_180006F85
0x180006f7e  mov     edx, 4F5h
0x180006f83  jmp     short loc_180006F0D
0x180006f85  mov     [rsp+1B0h+Length], 2000h
0x180006f8d  mov     esi, r15d
0x180006f90  call    cs:__imp_rand
0x180006f96  mov     r8d, eax
0x180006f99  mov     eax, r12d
0x180006f9c  imul    r8d
0x180006f9f  mov     eax, esi
0x180006fa1  inc     esi
0x180006fa3  sar     edx, 3
0x180006fa6  mov     ecx, edx
0x180006fa8  shr     ecx, 1Fh
0x180006fab  add     edx, ecx
0x180006fad  imul    ecx, edx, 1Ah
0x180006fb0  sub     r8d, ecx
0x180006fb3  add     r8b, 61h ; 'a'
0x180006fb7  mov     [rax+rbx], r8b
0x180006fbb  mov     eax, [rsp+1B0h+Length]
0x180006fbf  cmp     esi, eax
0x180006fc1  jb      short loc_180006F90
0x180006fc3  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x180006fc8  xor     r9d, r9d; ApcContext
0x180006fcb  mov     qword ptr [rsp+1B0h+CreateOptions], r15; Key
0x180006fd0  xor     r8d, r8d; ApcRoutine
0x180006fd3  mov     qword ptr [rsp+1B0h+CreateDisposition], r15; ByteOffset
0x180006fd8  xor     edx, edx; Event
0x180006fda  mov     [rsp+1B0h+ShareAccess], eax; Length
0x180006fde  lea     rax, [rbp+0B0h+IoStatusBlock]
0x180006fe2  mov     qword ptr [rsp+1B0h+FileAttributes], rbx; Buffer
0x180006fe7  mov     [rsp+1B0h+AllocationSize], rax; int
0x180006fec  call    cs:__imp_NtWriteFile
0x180006ff2  test    eax, eax
0x180006ff4  jns     short loc_180007000
0x180006ff6  mov     edx, 509h
0x180006ffb  jmp     loc_180006F0D
0x180007000  mov     r14d, r15d
0x180007003  cmp     r14d, 4
0x180007007  jnb     loc_180007131
0x18000700d  add     edi, [rsp+1B0h+Length]
0x180007011  mov     r12d, edi
0x180007014  mov     [rsp+1B0h+Buffer], 0
0x18000701d  shr     r12d, 2
0x180007021  cmp     r15d, 4
0x180007025  jnb     loc_1800070DD
0x18000702b  mov     edx, r12d
0x18000702e  lea     rcx, [rbp+0B0h+var_128]
0x180007032  call    ??$make_unique_nothrow@$$BY0A@D@wil@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<char [0]>(unsigned __int64)
0x180007037  mov     rsi, [rbp+0B0h+var_128]
0x18000703b  test    rsi, rsi
0x18000703e  jz      loc_1800070E8
0x180007044  mov     r8d, r12d; Size
0x180007047  xor     edx, edx; Val
0x180007049  mov     rcx, rsi; void *
0x18000704c  call    memset_0
0x180007051  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x180007056  lea     rax, [rsp+1B0h+Buffer]
0x18000705b  mov     qword ptr [rsp+1B0h+CreateOptions], 0; Key
0x180007064  xor     r9d, r9d; ApcContext
0x180007067  mov     qword ptr [rsp+1B0h+CreateDisposition], rax; ByteOffset
0x18000706c  xor     r8d, r8d; ApcRoutine
0x18000706f  mov     [rsp+1B0h+ShareAccess], r12d; Length
0x180007074  lea     rax, [rbp+0B0h+IoStatusBlock]
0x180007078  mov     qword ptr [rsp+1B0h+FileAttributes], rsi; Buffer
0x18000707d  xor     edx, edx; Event
0x18000707f  mov     [rsp+1B0h+AllocationSize], rax; int
0x180007084  call    cs:__imp_NtReadFile
0x18000708a  mov     edx, 80000000h
0x18000708f  lea     ecx, [rax+rdx]
0x180007092  test    edx, ecx
0x180007094  jnz     short loc_1800070B8
0x180007096  cmp     eax, 0C0000011h
0x18000709b  jz      short loc_1800070B8
0x18000709d  mov     rcx, [rbp+0B8h]; this
0x1800070a4  lea     r8, aClientcoreDsSe_4; "clientcore\\ds\\security\\gina\\profile"...
0x1800070ab  mov     r9d, eax; char *
0x1800070ae  mov     edx, 52Fh; void *
0x1800070b3  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800070b8  mov     eax, r12d
0x1800070bb  add     [rsp+1B0h+Buffer], rax
0x1800070c0  mov     [rbp+0B0h+var_128], 0
0x1800070c8  test    rsi, rsi
0x1800070cb  jz      short loc_1800070D5
0x1800070cd  mov     rcx, rsi; void *
0x1800070d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800070d5  inc     r15d
0x1800070d8  jmp     loc_180007021
0x1800070dd  inc     r14d
0x1800070e0  xor     r15d, r15d
  ... truncated ...
```
