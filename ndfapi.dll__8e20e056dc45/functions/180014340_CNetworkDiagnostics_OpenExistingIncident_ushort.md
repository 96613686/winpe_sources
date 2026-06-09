# CNetworkDiagnostics::OpenExistingIncident(ushort *)

- ea: `0x180014340`
- end: `0x180014461`
- name: `?OpenExistingIncident@CNetworkDiagnostics@@UEAAJPEAG@Z`
- size: `289`
- prototype: `__int64 __fastcall(CNetworkDiagnostics *this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000264c`
- `0x180007f1c`
- `0x180008304`
- `0x18000d390`
- `0x18000d6f4`
- `0x180014340`
- `0x180019af8`
- `0x18001f690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001442f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001442f`
- `KERNEL32!EnterCriticalSection` at `0x18001436b`
- `KERNEL32!EnterCriticalSection` at `0x18001436b`
- `KERNEL32!LeaveCriticalSection` at `0x18001443f`
- `KERNEL32!LeaveCriticalSection` at `0x18001443f`
- `ole32!CLSIDFromString` at `0x180014391`
- `ole32!CLSIDFromString` at `0x180014391`
- `ole32!CoTaskMemFree` at `0x18001441c`
- `ole32!CoTaskMemFree` at `0x18001441c`

## pseudocode

```c
__int64 __fastcall CNetworkDiagnostics::OpenExistingIncident(CNetworkDiagnostics *this, unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  int RootCauses; // edi
  CNetDiagClient *v6; // rax
  CNetDiagClient *v7; // rax
  HINSTANCE v8; // rdx
  CNetDiagClient *v9; // rbx
  CLSID pclsid; // [rsp+20h] [rbp-38h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 128);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  if ( *((_DWORD *)this + 30) )
  {
    RootCauses = -2147024120;
  }
  else
  {
    pclsid = 0;
    CLSIDFromString(a2, &pclsid);
    v6 = (CNetDiagClient *)operator new(0xCD8u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v6 && (v7 = CNetDiagClient::CNetDiagClient(v6), (v9 = v7) != 0) )
    {
      RootCauses = CNetDiagClient::Initialize(v7, v8, 0);
      if ( RootCauses < 0
        || (*((_DWORD *)v9 + 4) = 0,
            *((_DWORD *)v9 + 820) = 1,
            RootCauses = CNetDiagClient::InitDiagnosis(v9, &pclsid),
            RootCauses < 0) )
      {
        CNetDiagClient::~CNetDiagClient((void **)v9);
        operator delete(v9);
      }
      else
      {
        RootCauses = CNetDiagClient::GetRootCauses(v9, (unsigned int *)this + 8, (struct tagRootCauseInfo **)this + 3);
        if ( RootCauses < 0 )
        {
          CoTaskMemFree(v9);
        }
        else
        {
          *((_QWORD *)this + 2) = v9;
          *((_DWORD *)this + 30) = 3;
        }
      }
    }
    else
    {
      RootCauses = -2147024882;
    }
  }
  LeaveCriticalSection(v2);
  return (unsigned int)RootCauses;
}

```

## disassembly

```asm
0x180014340  mov     [rsp+arg_10], rbx
0x180014345  push    rbp
0x180014346  push    rsi
0x180014347  push    rdi
0x180014348  sub     rsp, 40h
0x18001434c  mov     rax, cs:__security_cookie
0x180014353  xor     rax, rsp
0x180014356  mov     [rsp+58h+var_28], rax
0x18001435b  lea     rbp, [rcx+80h]
0x180014362  mov     rsi, rcx
0x180014365  mov     rcx, rbp; lpCriticalSection
0x180014368  mov     rbx, rdx
0x18001436b  call    cs:__imp_EnterCriticalSection
0x180014371  cmp     dword ptr [rsi+78h], 0
0x180014375  jz      short loc_180014381
0x180014377  mov     edi, 80070308h
0x18001437c  jmp     loc_18001443C
0x180014381  xorps   xmm0, xmm0
0x180014384  lea     rdx, [rsp+58h+pclsid]; pclsid
0x180014389  mov     rcx, rbx; lpsz
0x18001438c  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180014391  call    cs:__imp_CLSIDFromString
0x180014397  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001439e  mov     ecx, 0CD8h; unsigned __int64
0x1800143a3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800143a8  test    rax, rax
0x1800143ab  jz      loc_180014437
0x1800143b1  mov     rcx, rax; this
0x1800143b4  call    ??0CNetDiagClient@@QEAA@XZ; CNetDiagClient::CNetDiagClient(void)
0x1800143b9  mov     rbx, rax
0x1800143bc  test    rax, rax
0x1800143bf  jz      short loc_180014437
0x1800143c1  xor     r8d, r8d; HWND
0x1800143c4  mov     rcx, rax; this
0x1800143c7  call    ?Initialize@CNetDiagClient@@QEAAJPEAUHINSTANCE__@@PEAUHWND__@@@Z; CNetDiagClient::Initialize(HINSTANCE__ *,HWND__ *)
0x1800143cc  mov     edi, eax
0x1800143ce  test    eax, eax
0x1800143d0  js      short loc_180014424
0x1800143d2  lea     rdx, [rsp+58h+pclsid]; struct _GUID *
0x1800143d7  mov     dword ptr [rbx+10h], 0
0x1800143de  mov     rcx, rbx; this
0x1800143e1  mov     dword ptr [rbx+0CD0h], 1
0x1800143eb  call    ?InitDiagnosis@CNetDiagClient@@IEAAJPEAU_GUID@@@Z; CNetDiagClient::InitDiagnosis(_GUID *)
0x1800143f0  mov     edi, eax
0x1800143f2  test    eax, eax
0x1800143f4  js      short loc_180014424
0x1800143f6  lea     r8, [rsi+18h]; struct tagRootCauseInfo **
0x1800143fa  mov     rcx, rbx; this
0x1800143fd  lea     rdx, [rsi+20h]; unsigned int *
0x180014401  call    ?GetRootCauses@CNetDiagClient@@QEAAJPEAKPEAPEAUtagRootCauseInfo@@@Z; CNetDiagClient::GetRootCauses(ulong *,tagRootCauseInfo * *)
0x180014406  mov     edi, eax
0x180014408  test    eax, eax
0x18001440a  js      short loc_180014419
0x18001440c  mov     [rsi+10h], rbx
0x180014410  mov     dword ptr [rsi+78h], 3
0x180014417  jmp     short loc_18001443C
0x180014419  mov     rcx, rbx; pv
0x18001441c  call    cs:__imp_CoTaskMemFree
0x180014422  jmp     short loc_18001443C
0x180014424  mov     rcx, rbx; this
0x180014427  call    ??1CNetDiagClient@@QEAA@XZ; CNetDiagClient::~CNetDiagClient(void)
0x18001442c  mov     rcx, rbx
0x18001442f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014435  jmp     short loc_18001443C
0x180014437  mov     edi, 8007000Eh
0x18001443c  mov     rcx, rbp; lpCriticalSection
0x18001443f  call    cs:__imp_LeaveCriticalSection
0x180014445  mov     eax, edi
0x180014447  mov     rcx, [rsp+58h+var_28]
0x18001444c  xor     rcx, rsp; StackCookie
0x18001444f  call    __security_check_cookie
0x180014454  mov     rbx, [rsp+58h+arg_10]
0x180014459  add     rsp, 40h
0x18001445d  pop     rdi
0x18001445e  pop     rsi
0x18001445f  pop     rbp
0x180014460  retn
```
