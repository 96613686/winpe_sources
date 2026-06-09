# NGENService::ServiceExtraInstallSteps(void)

- ea: `0x18001b57c`
- end: `0x18001b7fd`
- name: `?ServiceExtraInstallSteps@NGENService@@YAJXZ`
- size: `641`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001bcfc`

## callees

- `0x180001e8c`
- `0x1800068a8`
- `0x180007884`
- `0x180007914`
- `0x18001a690`
- `0x18001b57c`
- `0x180030d84`
- `0x180037340`
- `0x1800373e0`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001b7b7`
- `ADVAPI32!RegCloseKey` at `0x18001b7b7`
- `KERNEL32!GetLastError` at `0x18001b781`
- `KERNEL32!GetLastError` at `0x18001b781`
- `KERNEL32!HeapFree` at `0x18001b688`
- `KERNEL32!HeapFree` at `0x18001b6c7`
- `KERNEL32!HeapFree` at `0x18001b688`
- `KERNEL32!HeapFree` at `0x18001b6c7`
- `KERNEL32!GetProcessHeap` at `0x18001b673`
- `KERNEL32!GetProcessHeap` at `0x18001b6b2`
- `KERNEL32!GetProcessHeap` at `0x18001b673`
- `KERNEL32!GetProcessHeap` at `0x18001b6b2`

## string_xrefs

- `0x18001b5ef`: `\NgenService`
- `0x18001b6d2`: `ExtraInstallSteps`
- `0x18001b79e`: `ExtraInstallSteps`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NGENService::ServiceExtraInstallSteps(NGENService *this)
{
  struct SC_HANDLE__ *v1; // rdi
  __int64 v2; // r8
  unsigned __int16 *v3; // r9
  LSTATUS v4; // eax
  DWORD v5; // edx
  const unsigned __int16 *v6; // r8
  signed int v7; // ebx
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  struct SC_HANDLE__ **v12; // rdx
  unsigned __int16 *v13; // r8
  signed int LastError; // eax
  struct _SECURITY_ATTRIBUTES *v16; // [rsp+38h] [rbp-D0h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  struct SC_HANDLE__ *v18; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v19[3]; // [rsp+68h] [rbp-A0h] BYREF
  int v20; // [rsp+80h] [rbp-88h]
  _DWORD *v21; // [rsp+88h] [rbp-80h]
  int v22; // [rsp+98h] [rbp-70h] BYREF
  __int64 v23; // [rsp+9Ch] [rbp-6Ch]
  LPVOID lpMem; // [rsp+A8h] [rbp-60h]
  __int16 v25; // [rsp+B0h] [rbp-58h] BYREF
  _DWORD v26[5]; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int64 v27; // [rsp+2CCh] [rbp+1C4h]
  int v28; // [rsp+2D4h] [rbp+1CCh]

  hKey = 0;
  v1 = 0;
  v18 = 0;
  v23 = 512;
  lpMem = &v25;
  v22 = 2;
  v25 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v22);
  SString::Append((SString *)&v22, L"\\NgenService");
  SString::Append((SString *)&v22, L"\\State");
  SString::ConvertToUnicode((SString *)&v22);
  v4 = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v2, v3, 0, 0x2001Fu, v16, &hKey);
  if ( v4 )
  {
    v7 = (v4 != 0) | 0x80070000;
    if ( (v23 & 0x800000000LL) != 0 )
    {
      v8 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v8);
      }
    }
    goto LABEL_22;
  }
  if ( (v23 & 0x800000000LL) != 0 )
  {
    v10 = lpMem;
    if ( lpMem )
    {
      v11 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v11 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v11;
      }
      HeapFree(v11, 0, v10);
    }
  }
  if ( (unsigned int)REGUTIL::GetLong(L"ExtraInstallSteps", v5, v6, hKey) == 1 )
  {
LABEL_21:
    v7 = 0;
    goto LABEL_22;
  }
  v7 = NGENService::OpenNGENService((NGENService *)&v18, v12);
  v1 = v18;
  if ( v7 < 0 )
    goto LABEL_22;
  if ( *(&NGENService::g_Options + 1) )
    goto LABEL_20;
  v26[0] = 1;
  v26[1] = 60000;
  v26[2] = 1;
  v26[3] = 960000;
  v26[4] = 1;
  v27 = 15360000;
  v28 = 0;
  LODWORD(v19[0]) = 86400;
  *(_OWORD *)&v19[1] = 0;
  v20 = 4;
  v21 = v26;
  if ( (unsigned int)CLRChangeServiceConfig2(v18, 2u, v19) )
  {
LABEL_20:
    REGUTIL::SetOrCreateLong(L"ExtraInstallSteps", 1, v13, hKey);
    goto LABEL_21;
  }
  LastError = GetLastError();
  v7 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v7 = LastError;
LABEL_22:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 )
    CLRCloseServiceHandle(v1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001b57c  mov     rax, rsp
0x18001b57f  mov     [rax+8], rbx
0x18001b583  mov     [rax+10h], rsi
0x18001b587  mov     [rax+18h], rdi
0x18001b58b  mov     [rax+20h], r14
0x18001b58f  push    rbp
0x18001b590  lea     rbp, [rax-1E8h]
0x18001b597  sub     rsp, 2E0h
0x18001b59e  mov     rax, cs:__security_cookie
0x18001b5a5  xor     rax, rsp
0x18001b5a8  mov     [rbp+1E0h+var_10], rax
0x18001b5af  xor     r14d, r14d
0x18001b5b2  mov     [rsp+2E0h+hKey], r14
0x18001b5b7  mov     edi, r14d
0x18001b5ba  mov     [rsp+2E0h+var_288], r14
0x18001b5bf  mov     [rbp+1E0h+var_250], r14
0x18001b5c3  mov     [rbp+1E0h+var_250+4], 200h
0x18001b5cb  mov     [rbp+1E0h+lpMem], r14
0x18001b5cf  lea     rax, [rbp+1E0h+var_238]
0x18001b5d3  mov     [rbp+1E0h+lpMem], rax
0x18001b5d7  mov     dword ptr [rbp+1E0h+var_250], 2
0x18001b5de  mov     rax, [rbp+1E0h+lpMem]
0x18001b5e2  mov     [rax], r14w
0x18001b5e6  lea     rcx, [rbp+1E0h+var_250]; this
0x18001b5ea  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x18001b5ef  lea     rdx, aNgenservice_0; "\\NgenService"
0x18001b5f6  lea     rcx, [rbp+1E0h+var_250]; this
0x18001b5fa  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001b5ff  lea     rdx, aState; "\\State"
0x18001b606  lea     rcx, [rbp+1E0h+var_250]; this
0x18001b60a  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18001b60f  lea     rcx, [rbp+1E0h+var_250]; this
0x18001b613  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001b618  lea     rax, [rsp+2E0h+hKey]
0x18001b61d  mov     [rsp+2E0h+var_2A8], rax; HKEY *
0x18001b622  mov     [rsp+2E0h+var_2B8], 2001Fh; REGSAM
0x18001b62a  mov     [rsp+2E0h+var_2C0], r14d; DWORD
0x18001b62f  mov     rdx, [rbp+1E0h+lpMem]; unsigned __int16 *
0x18001b633  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18001b63a  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x18001b63f  mov     ecx, r14d
0x18001b642  test    eax, eax
0x18001b644  setnz   cl
0x18001b647  test    eax, eax
0x18001b649  jz      short loc_18001B697
0x18001b64b  mov     ebx, ecx
0x18001b64d  or      ebx, 80070000h
0x18001b653  test    ecx, ecx
0x18001b655  cmovz   ebx, ecx
0x18001b658  test    [rbp+1E0h+var_248], 8
0x18001b65c  jz      short loc_18001B68E
0x18001b65e  mov     rsi, [rbp+1E0h+lpMem]
0x18001b662  test    rsi, rsi
0x18001b665  jz      short loc_18001B68E
0x18001b667  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001b66e  test    rax, rax
0x18001b671  jnz     short loc_18001B680
0x18001b673  call    cs:__imp_GetProcessHeap
0x18001b679  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001b680  mov     r8, rsi; lpMem
0x18001b683  xor     edx, edx; dwFlags
0x18001b685  mov     rcx, rax; hHeap
0x18001b688  call    cs:__imp_HeapFree
0x18001b68e  test    ebx, ebx
0x18001b690  jns     short loc_18001B6CD
0x18001b692  jmp     loc_18001B7AD
0x18001b697  test    [rbp+1E0h+var_248], 8
0x18001b69b  jz      short loc_18001B6CD
0x18001b69d  mov     rbx, [rbp+1E0h+lpMem]
0x18001b6a1  test    rbx, rbx
0x18001b6a4  jz      short loc_18001B6CD
0x18001b6a6  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001b6ad  test    rax, rax
0x18001b6b0  jnz     short loc_18001B6BF
0x18001b6b2  call    cs:__imp_GetProcessHeap
0x18001b6b8  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x18001b6bf  mov     r8, rbx; lpMem
0x18001b6c2  xor     edx, edx; dwFlags
0x18001b6c4  mov     rcx, rax; hHeap
0x18001b6c7  call    cs:__imp_HeapFree
0x18001b6cd  mov     r9, [rsp+2E0h+hKey]; HKEY
0x18001b6d2  lea     rcx, aExtrainstallst; "ExtraInstallSteps"
0x18001b6d9  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x18001b6de  mov     esi, 1
0x18001b6e3  cmp     eax, esi
0x18001b6e5  jz      loc_18001B7AA
0x18001b6eb  lea     rcx, [rsp+2E0h+var_288]; this
0x18001b6f0  call    ?OpenNGENService@NGENService@@YAJPEAPEAUSC_HANDLE__@@@Z; NGENService::OpenNGENService(SC_HANDLE__ * *)
0x18001b6f5  mov     ebx, eax
0x18001b6f7  mov     rdi, [rsp+2E0h+var_288]
0x18001b6fc  test    eax, eax
0x18001b6fe  js      loc_18001B7AD
0x18001b704  cmp     dword ptr cs:?g_Options@NGENService@@3U_ServiceOptions@@A+4, r14d; _ServiceOptions NGENService::g_Options
0x18001b70b  jnz     loc_18001B797
0x18001b711  mov     [rbp+1E0h+var_30], esi
0x18001b717  mov     [rbp+1E0h+var_2C], 0EA60h
0x18001b721  mov     [rbp+1E0h+var_28], esi
0x18001b727  mov     [rbp+1E0h+var_24], 0EA600h
0x18001b731  mov     [rbp+1E0h+var_20], esi
0x18001b737  mov     [rbp+1E0h+var_1C], 0EA6000h
0x18001b742  mov     [rbp+1E0h+var_14], r14d
0x18001b749  mov     dword ptr [rsp+2E0h+var_280], 15180h
0x18001b751  xorps   xmm0, xmm0
0x18001b754  movdqu  xmmword ptr [rsp+2E0h+var_280+8], xmm0
0x18001b75a  mov     [rsp+2E0h+var_268], 4
0x18001b762  lea     rax, [rbp+1E0h+var_30]
0x18001b769  mov     [rbp+1E0h+var_260], rax
0x18001b76d  lea     r8, [rsp+2E0h+var_280]; void *
0x18001b772  lea     edx, [rsi+1]; unsigned int
0x18001b775  mov     rcx, rdi; struct SC_HANDLE__ *
0x18001b778  call    ?CLRChangeServiceConfig2@@YAHPEAUSC_HANDLE__@@KPEAX@Z; CLRChangeServiceConfig2(SC_HANDLE__ *,ulong,void *)
0x18001b77d  test    eax, eax
0x18001b77f  jnz     short loc_18001B797
0x18001b781  call    cs:__imp_GetLastError
0x18001b787  movzx   ebx, ax
0x18001b78a  or      ebx, 80070000h
0x18001b790  test    eax, eax
0x18001b792  cmovle  ebx, eax
0x18001b795  jmp     short loc_18001B7AD
0x18001b797  mov     r9, [rsp+2E0h+hKey]; HKEY
0x18001b79c  mov     edx, esi; int
0x18001b79e  lea     rcx, aExtrainstallst; "ExtraInstallSteps"
0x18001b7a5  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x18001b7aa  mov     ebx, r14d
0x18001b7ad  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18001b7b2  test    rcx, rcx
0x18001b7b5  jz      short loc_18001B7C2
0x18001b7b7  call    cs:__imp_RegCloseKey
0x18001b7bd  mov     [rsp+2E0h+hKey], r14
0x18001b7c2  test    rdi, rdi
0x18001b7c5  jz      short loc_18001B7CF
0x18001b7c7  mov     rcx, rdi; struct SC_HANDLE__ *
0x18001b7ca  call    ?CLRCloseServiceHandle@@YAHPEAUSC_HANDLE__@@@Z; CLRCloseServiceHandle(SC_HANDLE__ *)
0x18001b7cf  mov     eax, ebx
0x18001b7d1  mov     rcx, [rbp+1E0h+var_10]
0x18001b7d8  xor     rcx, rsp; StackCookie
0x18001b7db  call    __security_check_cookie
0x18001b7e0  lea     r11, [rsp+2E0h+var_s0]
0x18001b7e8  mov     rbx, [r11+10h]
0x18001b7ec  mov     rsi, [r11+18h]
0x18001b7f0  mov     rdi, [r11+20h]
0x18001b7f4  mov     r14, [r11+28h]
0x18001b7f8  mov     rsp, r11
0x18001b7fb  pop     rbp
0x18001b7fc  retn
```
