# CSystemWriter::AddLegacyDriverFiles(IVssCreateWriterMetadata *,void *)

- ea: `0x1800076b0`
- end: `0x180007890`
- name: `?AddLegacyDriverFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `480`
- prototype: `bool(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18001e1d4`

## callees

- `0x180005640`
- `0x180006e54`
- `0x1800076b0`
- `0x180007898`
- `0x18000be40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007758`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007773`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007773`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000785b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000785b`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000774e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800077c2`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18000774e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x1800077c2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007864`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180007864`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800076ff`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800076ff`

## pseudocode

```c
char __fastcall CSystemWriter::AddLegacyDriverFiles(CSystemWriter *this, struct IVssCreateWriterMetadata *a2, void *a3)
{
  void *v3; // rbx
  SC_HANDLE v4; // rsi
  char v5; // di
  DWORD cbBufSize; // r13d
  BYTE *lpServices; // r14
  int v8; // r12d
  CSystemWriter *v9; // rcx
  struct IVssCreateWriterMetadata *v10; // r8
  BYTE *v11; // r15
  DWORD LastError; // ebx
  DWORD ServicesReturned; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbBytesNeeded; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD ResumeHandle[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v18[336]; // [rsp+70h] [rbp-90h] BYREF

  v3 = a3;
  pcbBytesNeeded = 0;
  ServicesReturned = 0;
  ResumeHandle[0] = 0;
  v4 = OpenSCManagerW(0, 0, 5u);
  v5 = 0;
  if ( v4 )
  {
    if ( EnumServicesStatusExW(
           v4,
           SC_ENUM_PROCESS_INFO,
           0xBu,
           3u,
           0,
           0,
           &pcbBytesNeeded,
           &ServicesReturned,
           ResumeHandle,
           0)
      || GetLastError() == 234 )
    {
      cbBufSize = pcbBytesNeeded;
      lpServices = (BYTE *)LocalAlloc(0, pcbBytesNeeded);
      if ( lpServices )
      {
        do
        {
          v8 = 0;
          if ( !EnumServicesStatusExW(
                  v4,
                  SC_ENUM_PROCESS_INFO,
                  0xBu,
                  1u,
                  lpServices,
                  cbBufSize,
                  &pcbBytesNeeded,
                  &ServicesReturned,
                  ResumeHandle,
                  0) )
          {
            if ( GetLastError() != 234 )
              goto LABEL_15;
            v8 = 1;
          }
          v11 = lpServices;
          while ( ServicesReturned )
          {
            --ServicesReturned;
            if ( !CSystemWriter::AddLegacyDriver(v9, *(unsigned __int16 **)v11, v10, v3, v4) )
            {
              LastError = GetLastError();
              StringCchPrintfW(
                v18,
                0x14Bu,
                L"AddLegacyDriverFiles: Unable to back up image of binary %ws.",
                *((_QWORD *)v11 + 1));
              CSystemWriter::LogSystemErrorEvent(0x201u, v18, LastError);
              v3 = a3;
            }
            v11 += 56;
          }
          ServicesReturned = -1;
        }
        while ( v8 );
        v5 = 1;
LABEL_15:
        LocalFree(lpServices);
      }
    }
    CloseServiceHandle(v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1800076b0  push    rbp
0x1800076b2  push    rbx
0x1800076b3  push    rsi
0x1800076b4  push    rdi
0x1800076b5  push    r12
0x1800076b7  push    r13
0x1800076b9  push    r14
0x1800076bb  push    r15
0x1800076bd  lea     rbp, [rsp-228h]
0x1800076c5  sub     rsp, 328h
0x1800076cc  mov     rax, cs:__security_cookie
0x1800076d3  xor     rax, rsp
0x1800076d6  mov     [rbp+260h+var_50], rax
0x1800076dd  xor     r15d, r15d
0x1800076e0  mov     rbx, r8
0x1800076e3  xor     edx, edx; lpDatabaseName
0x1800076e5  mov     [rsp+360h+var_310], rbx
0x1800076ea  xor     ecx, ecx; lpMachineName
0x1800076ec  mov     [rsp+360h+var_304], r15d
0x1800076f1  mov     [rsp+360h+ServicesReturned], r15d
0x1800076f6  lea     r8d, [r15+5]; dwDesiredAccess
0x1800076fa  mov     [rsp+360h+ResumeHandle], r15d
0x1800076ff  call    cs:__imp_OpenSCManagerW
0x180007705  mov     rsi, rax
0x180007708  mov     dil, r15b
0x18000770b  test    rax, rax
0x18000770e  jz      loc_18000786A
0x180007714  mov     [rsp+360h+pszGroupName], r15; pszGroupName
0x180007719  lea     rax, [rsp+360h+ResumeHandle]
0x18000771e  mov     [rsp+360h+lpResumeHandle], rax; lpResumeHandle
0x180007723  lea     r9d, [r15+3]; dwServiceState
0x180007727  lea     rax, [rsp+360h+ServicesReturned]
0x18000772c  xor     edx, edx; InfoLevel
0x18000772e  mov     [rsp+360h+lpServicesReturned], rax; lpServicesReturned
0x180007733  lea     r8d, [r15+0Bh]; dwServiceType
0x180007737  lea     rax, [rsp+360h+var_304]
0x18000773c  mov     rcx, rsi; hSCManager
0x18000773f  mov     [rsp+360h+pcbBytesNeeded], rax; pcbBytesNeeded
0x180007744  mov     [rsp+360h+cbBufSize], r15d; cbBufSize
0x180007749  mov     [rsp+360h+lpServices], r15; lpServices
0x18000774e  call    cs:__imp_EnumServicesStatusExW
0x180007754  test    eax, eax
0x180007756  jnz     short loc_180007769
0x180007758  call    cs:__imp_GetLastError
0x18000775e  cmp     eax, 0EAh
0x180007763  jnz     loc_180007861
0x180007769  mov     r13d, [rsp+360h+var_304]
0x18000776e  xor     ecx, ecx; uFlags
0x180007770  mov     edx, r13d; uBytes
0x180007773  call    cs:__imp_LocalAlloc
0x180007779  mov     r14, rax
0x18000777c  test    rax, rax
0x18000777f  jz      loc_180007861
0x180007785  mov     [rsp+360h+pszGroupName], r15; pszGroupName
0x18000778a  lea     rax, [rsp+360h+ResumeHandle]
0x18000778f  mov     [rsp+360h+lpResumeHandle], rax; lpResumeHandle
0x180007794  xor     edx, edx; InfoLevel
0x180007796  lea     rax, [rsp+360h+ServicesReturned]
0x18000779b  mov     rcx, rsi; hSCManager
0x18000779e  mov     [rsp+360h+lpServicesReturned], rax; lpServicesReturned
0x1800077a3  mov     r12d, r15d
0x1800077a6  lea     rax, [rsp+360h+var_304]
0x1800077ab  mov     [rsp+360h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800077b0  lea     r9d, [rdx+1]; dwServiceState
0x1800077b4  mov     [rsp+360h+cbBufSize], r13d; cbBufSize
0x1800077b9  lea     r8d, [rdx+0Bh]; dwServiceType
0x1800077bd  mov     [rsp+360h+lpServices], r14; lpServices
0x1800077c2  call    cs:__imp_EnumServicesStatusExW
0x1800077c8  test    eax, eax
0x1800077ca  jnz     short loc_1800077DF
0x1800077cc  call    cs:__imp_GetLastError
0x1800077d2  cmp     eax, 0EAh
0x1800077d7  jnz     short loc_180007858
0x1800077d9  mov     r12d, 1
0x1800077df  mov     r15, r14
0x1800077e2  jmp     short loc_18000783B
0x1800077e4  dec     eax
0x1800077e6  mov     [rsp+360h+lpServices], rsi; struct SC_HANDLE__ *
0x1800077eb  mov     [rsp+360h+ServicesReturned], eax
0x1800077ef  mov     r9, rbx; void *
0x1800077f2  mov     rdx, [r15]; unsigned __int16 *
0x1800077f5  call    ?AddLegacyDriver@CSystemWriter@@AEAA_NPEAGPEAVIVssCreateWriterMetadata@@PEAXPEAUSC_HANDLE__@@@Z; CSystemWriter::AddLegacyDriver(ushort *,IVssCreateWriterMetadata *,void *,SC_HANDLE__ *)
0x1800077fa  test    al, al
0x1800077fc  jnz     short loc_180007837
0x1800077fe  call    cs:__imp_GetLastError
0x180007804  mov     r9, [r15+8]
0x180007808  lea     r8, aAddlegacydrive; "AddLegacyDriverFiles: Unable to back up"...
0x18000780f  mov     edx, 14Bh; unsigned __int64
0x180007814  lea     rcx, [rsp+360h+var_2F0]; unsigned __int16 *
0x180007819  mov     ebx, eax
0x18000781b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007820  mov     r8d, ebx; unsigned int
0x180007823  lea     rdx, [rsp+360h+var_2F0]; unsigned __int16 *
0x180007828  mov     ecx, 201h; unsigned int
0x18000782d  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180007832  mov     rbx, [rsp+360h+var_310]
0x180007837  add     r15, 38h ; '8'
0x18000783b  mov     eax, [rsp+360h+ServicesReturned]
0x18000783f  test    eax, eax
0x180007841  jnz     short loc_1800077E4
0x180007843  dec     eax
0x180007845  xor     r15d, r15d
0x180007848  mov     [rsp+360h+ServicesReturned], eax
0x18000784c  test    r12d, r12d
0x18000784f  jnz     loc_180007785
0x180007855  mov     dil, 1
0x180007858  mov     rcx, r14; hMem
0x18000785b  call    cs:__imp_LocalFree
0x180007861  mov     rcx, rsi; hSCObject
0x180007864  call    cs:__imp_CloseServiceHandle
0x18000786a  mov     al, dil
0x18000786d  mov     rcx, [rbp+260h+var_50]
0x180007874  xor     rcx, rsp; StackCookie
0x180007877  call    __security_check_cookie
0x18000787c  add     rsp, 328h
0x180007883  pop     r15
0x180007885  pop     r14
0x180007887  pop     r13
0x180007889  pop     r12
0x18000788b  pop     rdi
0x18000788c  pop     rsi
0x18000788d  pop     rbx
0x18000788e  pop     rbp
0x18000788f  retn
```
