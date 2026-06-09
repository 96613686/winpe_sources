# OService::StartService(void)

- ea: `0x180136b54`
- end: `0x180136c0b`
- name: `?StartService@OService@@QEAA_NXZ`
- size: `183`
- prototype: `bool __fastcall(OService *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018870`
- `0x180136b54`

## callees

- `0x18012c164`
- `0x18013695c`
- `0x180136b20`
- `0x180136b54`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180136b78`
- `KERNEL32!GetLastError` at `0x180136b78`
- `ADVAPI32!StartServiceW` at `0x180136b6a`
- `ADVAPI32!StartServiceW` at `0x180136b6a`

## string_xrefs

- `0x180136b89`: `OService::StartService - Service instance already running`

## pseudocode

```c
char __fastcall OService::StartService(SC_HANDLE *this)
{
  int v2; // edx
  int v3; // ecx
  int v4; // r8d
  int v5; // r9d
  OService *i; // rbx
  OService *v7; // rcx
  OService *v9; // rdx

  if ( !StartServiceW(this[1], 0, 0) )
  {
    if ( GetLastError() != 1056 )
    {
      Mso::Logging::MsoSendTraceTag<int,unsigned long>(v3, v2, v4, v5);
      return 0;
    }
    Mso::Logging::MsoSendTraceTag(39063619, 1985, 100);
  }
  if ( *((_BYTE *)this + 40) )
  {
    for ( i = (OService *)this[3]; ; OService::StartService(i) )
    {
      v7 = (OService *)this[2];
      if ( i == v7 )
        break;
      i = (OService *)((char *)i - 48);
    }
    v9 = (OService *)this[3];
    if ( v7 != v9 )
    {
      std::_Destroy_range<std::allocator<OService>>(v7, v9);
      this[3] = this[2];
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180136b54  mov     [rsp+arg_10], rbx
0x180136b59  push    rdi
0x180136b5a  sub     rsp, 40h
0x180136b5e  mov     rdi, rcx
0x180136b61  xor     r8d, r8d; lpServiceArgVectors
0x180136b64  mov     rcx, [rcx+8]; hService
0x180136b68  xor     edx, edx; dwNumServiceArgs
0x180136b6a  call    cs:__imp_StartServiceW
0x180136b70  mov     [rsp+48h+arg_8], eax
0x180136b74  test    eax, eax
0x180136b76  jnz     short loc_180136BAA
0x180136b78  call    cs:__imp_GetLastError
0x180136b7e  mov     [rsp+48h+arg_0], eax
0x180136b82  cmp     eax, 420h
0x180136b87  jnz     short loc_180136BCB
0x180136b89  lea     rax, aOserviceStarts_0; "OService::StartService - Service instan"...
0x180136b90  mov     edx, 7C1h
0x180136b95  mov     ecx, 2541043h
0x180136b9a  mov     [rsp+48h+var_28], rax
0x180136b9f  mov     r8d, 64h ; 'd'
0x180136ba5  call    ?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@W4DataCategories@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *)
0x180136baa  cmp     byte ptr [rdi+28h], 0
0x180136bae  jz      short loc_180136BFE
0x180136bb0  mov     rbx, [rdi+18h]
0x180136bb4  mov     rcx, [rdi+10h]; this
0x180136bb8  cmp     rbx, rcx
0x180136bbb  jz      short loc_180136BE8
0x180136bbd  add     rbx, 0FFFFFFFFFFFFFFD0h
0x180136bc1  mov     rcx, rbx; this
0x180136bc4  call    ?StartService@OService@@QEAA_NXZ; OService::StartService(void)
0x180136bc9  jmp     short loc_180136BB4
0x180136bcb  lea     rax, [rsp+48h+arg_0]
0x180136bd0  mov     [rsp+48h+var_18], rax
0x180136bd5  lea     rax, [rsp+48h+arg_8]
0x180136bda  mov     [rsp+48h+var_20], rax
0x180136bdf  call    ??$MsoSendTraceTag@HK@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBHAEBK@Z; Mso::Logging::MsoSendTraceTag<int,ulong>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,int const &,ulong const &)
0x180136be4  xor     al, al
0x180136be6  jmp     short loc_180136C00
0x180136be8  mov     rdx, [rdi+18h]
0x180136bec  cmp     rcx, rdx
0x180136bef  jz      short loc_180136BFE
0x180136bf1  call    ??$_Destroy_range@V?$allocator@VOService@@@std@@@std@@YAXPEAVOService@@QEAV1@AEAV?$allocator@VOService@@@0@@Z; std::_Destroy_range<std::allocator<OService>>(OService *,OService * const,std::allocator<OService> &)
0x180136bf6  mov     rax, [rdi+10h]
0x180136bfa  mov     [rdi+18h], rax
0x180136bfe  mov     al, 1
0x180136c00  mov     rbx, [rsp+48h+arg_10]
0x180136c05  add     rsp, 40h
0x180136c09  pop     rdi
0x180136c0a  retn
```
