# CMVEngine::PreHandleStates(void)

- ea: `0x180018438`
- end: `0x18001868f`
- name: `?PreHandleStates@CMVEngine@@AEAAXXZ`
- size: `599`
- prototype: `void __fastcall(CMVEngine *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800141f0`
- `0x180014810`

## callees

- `0x1800010c8`
- `0x1800092dc`
- `0x180018438`
- `0x1800387b4`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180018586`
- `msvcrt!_wcsicmp` at `0x1800185e1`
- `msvcrt!_wcsicmp` at `0x180018586`
- `msvcrt!_wcsicmp` at `0x1800185e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800184d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800184d3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018503`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180018503`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018570`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018524`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018570`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180018643`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180018643`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CMVEngine::PreHandleStates(CMVEngine *this)
{
  CMVEngine *v1; // rdi
  bool IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  signed int v5; // ebx
  bool v6; // cc
  int v7; // eax
  HKEY hKey; // [rsp+30h] [rbp-288h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-280h] BYREF
  CMVEngine *v10; // [rsp+40h] [rbp-278h]
  _BYTE v11[32]; // [rsp+48h] [rbp-270h] BYREF
  __int64 v12; // [rsp+68h] [rbp-250h] BYREF
  BYTE Data[2]; // [rsp+90h] [rbp-228h] BYREF
  _BYTE v14[526]; // [rsp+92h] [rbp-226h] BYREF

  v1 = this;
  v10 = this;
  *((_DWORD *)this + 35) = -1;
  *((_DWORD *)this + 6) = 0;
  *(_WORD *)Data = 0;
  memset_0(v14, 0, 0x206u);
  cbData = 520;
  hKey = 0;
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\Provisioning\\PendingReboot";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 || (v4 = RegQueryValueExW(hKey, 0, 0, 0, Data, &cbData), v5 = v4, v6 = v4 <= 0, v4) )
  {
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v5 < 0 && (unsigned int)dword_18005A000 > 4 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F093, 0, 0, 2, v11);
  }
  else if ( hKey )
  {
    RegCloseKey(hKey);
  }
  v7 = _wcsicmp((const wchar_t *)Data, L"Retry");
  try
  {
    if ( v7 )
    {
      DisableTask((OLECHAR *)L"Retry");
      if ( (unsigned int)dword_18005A000 > 4 )
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004F5C1, 0, 0, 2, v11);
    }
    if ( _wcsicmp((const wchar_t *)Data, L"RunOnReboot") )
    {
      DisableTask((OLECHAR *)L"RunOnReboot");
      if ( (unsigned int)dword_18005A000 > 4 )
        tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, &dword_18004EDCC, 0, 0, 2, v11);
    }
  }
  catch ( ... )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004E8AB, 0, 0, 2, &v12);
    v1 = v10;
  }
  RegDeleteKeyW(HKEY_LOCAL_MACHINE, lpSubKey);
  if ( (char *)v1 + 16 <= (char *)v1 + 24 )
    memset_0((char *)v1 + 16, 0, 4LL * ((char *)v1 + 24 >= (char *)v1 + 16 ? 2 : 0));
}

```

## disassembly

```asm
0x180018438  mov     [rsp+arg_8], rbx
0x18001843d  push    rdi
0x18001843e  sub     rsp, 2B0h
0x180018445  mov     rax, cs:__security_cookie
0x18001844c  xor     rax, rsp
0x18001844f  mov     [rsp+2B8h+var_18], rax
0x180018457  mov     rdi, rcx
0x18001845a  mov     [rsp+2B8h+var_278], rcx
0x18001845f  mov     dword ptr [rcx+8Ch], 0FFFFFFFFh
0x180018469  mov     dword ptr [rcx+18h], 0
0x180018470  xor     eax, eax
0x180018472  mov     word ptr [rsp+2B8h+Data], ax
0x18001847a  xor     edx, edx; Val
0x18001847c  mov     r8d, 206h; Size
0x180018482  lea     rcx, [rsp+2B8h+var_226]; void *
0x18001848a  call    memset_0
0x18001848f  mov     [rsp+2B8h+cbData], 208h
0x180018497  mov     [rsp+2B8h+hKey], 0
0x1800184a0  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800184a5  lea     rcx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Provisioning\\Pend"...
0x1800184ac  lea     rdx, aOsdataSoftware_9; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800184b3  test    al, al
0x1800184b5  cmovz   rdx, rcx; lpSubKey
0x1800184b9  lea     rax, [rsp+2B8h+hKey]
0x1800184be  mov     [rsp+2B8h+phkResult], rax; phkResult
0x1800184c3  mov     r9d, 20019h; samDesired
0x1800184c9  xor     r8d, r8d; ulOptions
0x1800184cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800184d3  call    cs:__imp_RegOpenKeyExW
0x1800184d9  mov     ebx, eax
0x1800184db  test    eax, eax
0x1800184dd  jnz     short loc_18001850F
0x1800184df  lea     rax, [rsp+2B8h+cbData]
0x1800184e4  mov     [rsp+2B8h+lpcbData], rax; lpcbData
0x1800184e9  lea     rax, [rsp+2B8h+Data]
0x1800184f1  mov     [rsp+2B8h+phkResult], rax; lpData
0x1800184f6  xor     r9d, r9d; lpType
0x1800184f9  xor     r8d, r8d; lpReserved
0x1800184fc  xor     edx, edx; lpValueName
0x1800184fe  mov     rcx, [rsp+2B8h+hKey]; hKey
0x180018503  call    cs:__imp_RegQueryValueExW
0x180018509  mov     ebx, eax
0x18001850b  test    eax, eax
0x18001850d  jz      short loc_180018566
0x18001850f  jle     short loc_18001851A
0x180018511  movzx   ebx, ax
0x180018514  or      ebx, 80070000h
0x18001851a  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18001851f  test    rcx, rcx
0x180018522  jz      short loc_18001852A
0x180018524  call    cs:__imp_RegCloseKey
0x18001852a  test    ebx, ebx
0x18001852c  jns     short loc_180018577
0x18001852e  mov     eax, cs:dword_18005A000
0x180018534  cmp     eax, 4
0x180018537  jbe     short loc_180018577
0x180018539  lea     rax, [rsp+2B8h+var_270]
0x18001853e  mov     [rsp+2B8h+lpcbData], rax
0x180018543  mov     dword ptr [rsp+2B8h+phkResult], 2
0x18001854b  xor     r9d, r9d
0x18001854e  xor     r8d, r8d
0x180018551  lea     rdx, byte_18004F093
0x180018558  lea     rcx, dword_18005A000
0x18001855f  call    _tlgWriteTransfer_EventWriteTransfer
0x180018564  jmp     short loc_180018577
0x180018566  mov     rcx, [rsp+2B8h+hKey]; hKey
0x18001856b  test    rcx, rcx
0x18001856e  jz      short loc_180018577
0x180018570  call    cs:__imp_RegCloseKey
0x180018576  nop
0x180018577  lea     rdx, aRetry; "Retry"
0x18001857e  lea     rcx, [rsp+2B8h+Data]; String1
0x180018586  call    cs:__imp__wcsicmp
0x18001858c  test    eax, eax
0x18001858e  jz      short loc_1800185D2
0x180018590  lea     rcx, aRetry; "Retry"
0x180018597  call    ?DisableTask@@YAXPEBG@Z; DisableTask(ushort const *)
0x18001859c  mov     eax, cs:dword_18005A000
0x1800185a2  cmp     eax, 4
0x1800185a5  jbe     short loc_1800185D2
0x1800185a7  lea     rax, [rsp+2B8h+var_270]
0x1800185ac  mov     [rsp+2B8h+lpcbData], rax
0x1800185b1  mov     dword ptr [rsp+2B8h+phkResult], 2
0x1800185b9  xor     r9d, r9d
0x1800185bc  xor     r8d, r8d
0x1800185bf  lea     rdx, byte_18004F5C1
0x1800185c6  lea     rcx, dword_18005A000
0x1800185cd  call    _tlgWriteTransfer_EventWriteTransfer
0x1800185d2  lea     rdx, aRunonreboot; "RunOnReboot"
0x1800185d9  lea     rcx, [rsp+2B8h+Data]; String1
0x1800185e1  call    cs:__imp__wcsicmp
0x1800185e7  test    eax, eax
0x1800185e9  jz      short loc_18001862E
0x1800185eb  lea     rcx, aRunonreboot; "RunOnReboot"
0x1800185f2  call    ?DisableTask@@YAXPEBG@Z; DisableTask(ushort const *)
0x1800185f7  mov     eax, cs:dword_18005A000
0x1800185fd  cmp     eax, 4
0x180018600  jbe     short loc_18001862E
0x180018602  lea     rax, [rsp+2B8h+var_270]
0x180018607  mov     [rsp+2B8h+lpcbData], rax
0x18001860c  mov     dword ptr [rsp+2B8h+phkResult], 2
0x180018614  xor     r9d, r9d
0x180018617  xor     r8d, r8d
0x18001861a  lea     rdx, dword_18004EDCC
0x180018621  lea     rcx, dword_18005A000
0x180018628  call    _tlgWriteTransfer_EventWriteTransfer
0x18001862d  nop
0x18001862e  jmp     short loc_180018635
0x180018630  mov     rdi, [rsp+2B8h+var_278]
0x180018635  mov     rdx, cs:lpSubKey; lpSubKey
0x18001863c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018643  call    cs:__imp_RegDeleteKeyW
0x180018649  lea     rcx, [rdi+10h]; void *
0x18001864d  lea     rax, [rcx+8]
0x180018651  cmp     rax, rcx
0x180018654  sbb     r8, r8
0x180018657  not     r8
0x18001865a  and     r8d, 2
0x18001865e  cmp     rcx, rax
0x180018661  ja      short loc_18001866E
0x180018663  shl     r8, 2; Size
0x180018667  xor     edx, edx; Val
0x180018669  call    memset_0
0x18001866e  mov     rcx, [rsp+2B8h+var_18]
0x180018676  xor     rcx, rsp; StackCookie
0x180018679  call    __security_check_cookie
0x18001867e  mov     rbx, [rsp+2B8h+arg_8]
0x180018686  add     rsp, 2B0h
0x18001868d  pop     rdi
0x18001868e  retn
```
