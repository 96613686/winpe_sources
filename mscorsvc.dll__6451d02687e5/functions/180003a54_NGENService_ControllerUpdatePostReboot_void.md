# NGENService::ControllerUpdatePostReboot(void)

- ea: `0x180003a54`
- end: `0x180003c90`
- name: `?ControllerUpdatePostReboot@NGENService@@YAJXZ`
- size: `572`
- prototype: `__int64 __fastcall(NGENService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800283d0`

## callees

- `0x180001e8c`
- `0x180003a54`
- `0x180006328`
- `0x1800068a8`
- `0x180030d84`
- `0x1800373e0`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180003b04`
- `ADVAPI32!RegCloseKey` at `0x180003b94`
- `ADVAPI32!RegCloseKey` at `0x180003c43`
- `ADVAPI32!RegCloseKey` at `0x180003c58`
- `ADVAPI32!RegCloseKey` at `0x180003b04`
- `ADVAPI32!RegCloseKey` at `0x180003b94`
- `ADVAPI32!RegCloseKey` at `0x180003c43`
- `ADVAPI32!RegCloseKey` at `0x180003c58`
- `KERNEL32!HeapFree` at `0x180003c31`
- `KERNEL32!HeapFree` at `0x180003c31`
- `KERNEL32!GetProcessHeap` at `0x180003c1c`
- `KERNEL32!GetProcessHeap` at `0x180003c1c`

## string_xrefs

- `0x180003bdd`: `PendingUpdate`
- `0x180003ace`: `\NgenService`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall NGENService::ControllerUpdatePostReboot(NGENService *this)
{
  __int64 v1; // r8
  unsigned __int16 *v2; // r9
  BOOL v3; // ebx
  int v4; // eax
  signed int v5; // ebx
  const unsigned __int16 *v6; // r8
  int v7; // eax
  int Long; // eax
  void *v9; // rdi
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+38h] [rbp-D0h]
  HKEY v13; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v14; // [rsp+68h] [rbp-A0h]
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  __int64 v16; // [rsp+78h] [rbp-90h]
  HKEY *p_hKey; // [rsp+80h] [rbp-88h]
  int v18; // [rsp+88h] [rbp-80h] BYREF
  __int64 v19; // [rsp+8Ch] [rbp-7Ch]
  LPVOID lpMem; // [rsp+98h] [rbp-70h]
  __int16 v21; // [rsp+A0h] [rbp-68h] BYREF

  hKey = 0;
  LODWORD(v16) = 0;
  v13 = 0;
  LODWORD(v14) = 0;
  v19 = 512;
  lpMem = &v21;
  v18 = 2;
  v21 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v18);
  SString::Append((SString *)&v18, L"\\NgenService");
  SString::Append((SString *)&v18, L"\\State\\PendingReboot");
  p_hKey = &hKey;
  hKey = 0;
  SString::ConvertToUnicode((SString *)&v18);
  v3 = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v1, v2, 1u, 0x2001Fu, v12, &hKey) != 0;
  v4 = v16;
  if ( hKey )
    v4 = 1;
  LODWORD(v16) = v4;
  if ( v3 )
  {
    v5 = v3 | 0x80070000;
  }
  else
  {
    p_hKey = &v13;
    v13 = 0;
    v5 = NGENServicePersistentStateKey(&v13);
    v7 = v14;
    if ( v13 )
      v7 = 1;
    LODWORD(v14) = v7;
    if ( v5 >= 0 )
    {
      Long = REGUTIL::SetOrCreateLong(L"PendingUpdate", 1, v6, v13);
      if ( Long )
      {
        v5 = (unsigned __int16)Long | 0x80070000;
        if ( Long <= 0 )
          v5 = Long;
      }
      else
      {
        v5 = 0;
      }
    }
  }
  if ( (v19 & 0x800000000LL) != 0 )
  {
    v9 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v9);
    }
  }
  if ( (_DWORD)v14 )
  {
    RegCloseKey(v13);
    LODWORD(v14) = 0;
  }
  if ( (_DWORD)v16 )
  {
    RegCloseKey(hKey);
    LODWORD(v16) = 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180003a54  mov     rax, rsp
0x180003a57  mov     [rax+8], rbx
0x180003a5b  mov     [rax+10h], rsi
0x180003a5f  mov     [rax+18h], rdi
0x180003a63  mov     [rax+20h], r14
0x180003a67  push    rbp
0x180003a68  lea     rbp, [rax-1B8h]
0x180003a6f  sub     rsp, 2B0h
0x180003a76  mov     rax, cs:__security_cookie
0x180003a7d  xor     rax, rsp
0x180003a80  mov     [rbp+1B0h+var_10], rax
0x180003a87  xor     esi, esi
0x180003a89  mov     dword ptr [rsp+2B0h+var_260], esi
0x180003a8d  mov     [rsp+2B0h+hKey], rsi
0x180003a92  mov     dword ptr [rsp+2B0h+var_240], esi
0x180003a96  mov     [rsp+2B0h+var_258], rsi
0x180003a9b  mov     dword ptr [rsp+2B0h+var_250], esi
0x180003a9f  mov     [rbp+1B0h+var_230], rsi
0x180003aa3  mov     [rbp+1B0h+var_230+4], 200h
0x180003aab  mov     [rbp+1B0h+lpMem], rsi
0x180003aaf  lea     rax, [rbp+1B0h+var_218]
0x180003ab3  mov     [rbp+1B0h+lpMem], rax
0x180003ab7  mov     dword ptr [rbp+1B0h+var_230], 2
0x180003abe  mov     rax, [rbp+1B0h+lpMem]
0x180003ac2  mov     [rax], si
0x180003ac5  lea     rcx, [rbp+1B0h+var_230]; this
0x180003ac9  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x180003ace  lea     rdx, aNgenservice_0; "\\NgenService"
0x180003ad5  lea     rcx, [rbp+1B0h+var_230]; this
0x180003ad9  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180003ade  lea     rdx, aStatePendingre; "\\State\\PendingReboot"
0x180003ae5  lea     rcx, [rbp+1B0h+var_230]; this
0x180003ae9  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180003aee  nop
0x180003aef  lea     rax, [rsp+2B0h+hKey]
0x180003af4  mov     [rsp+2B0h+var_238], rax
0x180003af9  cmp     dword ptr [rsp+2B0h+var_240], esi
0x180003afd  jz      short loc_180003B0E
0x180003aff  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180003b04  call    cs:__imp_RegCloseKey
0x180003b0a  mov     dword ptr [rsp+2B0h+var_240], esi
0x180003b0e  mov     [rsp+2B0h+hKey], rsi
0x180003b13  mov     r14d, 1
0x180003b19  mov     dword ptr [rsp+2B0h+var_260], r14d
0x180003b1e  lea     rcx, [rbp+1B0h+var_230]; this
0x180003b22  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180003b27  lea     rax, [rsp+2B0h+hKey]
0x180003b2c  mov     [rsp+2B0h+var_278], rax; HKEY *
0x180003b31  mov     [rsp+2B0h+var_288], 2001Fh; REGSAM
0x180003b39  mov     [rsp+2B0h+var_290], r14d; DWORD
0x180003b3e  mov     rdx, [rbp+1B0h+lpMem]; unsigned __int16 *
0x180003b42  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180003b49  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180003b4e  mov     ebx, esi
0x180003b50  test    eax, eax
0x180003b52  setnz   bl
0x180003b55  mov     edi, r14d
0x180003b58  and     edi, 0FFFFFFFEh
0x180003b5b  mov     dword ptr [rsp+2B0h+var_260], edi
0x180003b5f  mov     eax, dword ptr [rsp+2B0h+var_240]
0x180003b63  cmp     [rsp+2B0h+hKey], rsi
0x180003b68  cmovnz  eax, r14d
0x180003b6c  mov     dword ptr [rsp+2B0h+var_240], eax
0x180003b70  test    ebx, ebx
0x180003b72  jz      short loc_180003B7F
0x180003b74  or      ebx, 80070000h
0x180003b7a  jmp     loc_180003C01
0x180003b7f  lea     rax, [rsp+2B0h+var_258]
0x180003b84  mov     [rsp+2B0h+var_238], rax
0x180003b89  cmp     dword ptr [rsp+2B0h+var_250], esi
0x180003b8d  jz      short loc_180003B9E
0x180003b8f  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180003b94  call    cs:__imp_RegCloseKey
0x180003b9a  mov     dword ptr [rsp+2B0h+var_250], esi
0x180003b9e  mov     [rsp+2B0h+var_258], rsi
0x180003ba3  or      edi, 2
0x180003ba6  mov     dword ptr [rsp+2B0h+var_260], edi
0x180003baa  lea     rcx, [rsp+2B0h+var_258]; HKEY *
0x180003baf  call    NGENServicePersistentStateKey
0x180003bb4  mov     ebx, eax
0x180003bb6  test    eax, eax
0x180003bb8  sets    cl
0x180003bbb  and     edi, 0FFFFFFFDh
0x180003bbe  mov     dword ptr [rsp+2B0h+var_260], edi
0x180003bc2  mov     eax, dword ptr [rsp+2B0h+var_250]
0x180003bc6  mov     r9, [rsp+2B0h+var_258]; HKEY
0x180003bcb  test    r9, r9
0x180003bce  cmovnz  eax, r14d
0x180003bd2  mov     dword ptr [rsp+2B0h+var_250], eax
0x180003bd6  test    cl, cl
0x180003bd8  jnz     short loc_180003C01
0x180003bda  mov     edx, r14d; int
0x180003bdd  lea     rcx, aPendingupdate; "PendingUpdate"
0x180003be4  call    ?SetOrCreateLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::SetOrCreateLong(ushort const *,long,ushort const *,HKEY__ *)
0x180003be9  test    eax, eax
0x180003beb  jz      short loc_180003BFF
0x180003bed  movzx   ebx, ax
0x180003bf0  or      ebx, 80070000h
0x180003bf6  test    eax, eax
0x180003bf8  cmovle  ebx, eax
0x180003bfb  test    ebx, ebx
0x180003bfd  js      short loc_180003C01
0x180003bff  mov     ebx, esi
0x180003c01  test    [rbp+1B0h+var_228], 8
0x180003c05  jz      short loc_180003C38
0x180003c07  mov     rdi, [rbp+1B0h+lpMem]
0x180003c0b  test    rdi, rdi
0x180003c0e  jz      short loc_180003C38
0x180003c10  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180003c17  test    rax, rax
0x180003c1a  jnz     short loc_180003C29
0x180003c1c  call    cs:__imp_GetProcessHeap
0x180003c22  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180003c29  mov     r8, rdi; lpMem
0x180003c2c  xor     edx, edx; dwFlags
0x180003c2e  mov     rcx, rax; hHeap
0x180003c31  call    cs:__imp_HeapFree
0x180003c37  nop
0x180003c38  cmp     dword ptr [rsp+2B0h+var_250], esi
0x180003c3c  jz      short loc_180003C4D
0x180003c3e  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180003c43  call    cs:__imp_RegCloseKey
0x180003c49  mov     dword ptr [rsp+2B0h+var_250], esi
0x180003c4d  cmp     dword ptr [rsp+2B0h+var_240], esi
0x180003c51  jz      short loc_180003C62
0x180003c53  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180003c58  call    cs:__imp_RegCloseKey
0x180003c5e  mov     dword ptr [rsp+2B0h+var_240], esi
0x180003c62  mov     eax, ebx
0x180003c64  mov     rcx, [rbp+1B0h+var_10]
0x180003c6b  xor     rcx, rsp; StackCookie
0x180003c6e  call    __security_check_cookie
0x180003c73  lea     r11, [rsp+2B0h+var_s0]
0x180003c7b  mov     rbx, [r11+10h]
0x180003c7f  mov     rsi, [r11+18h]
0x180003c83  mov     rdi, [r11+20h]
0x180003c87  mov     r14, [r11+28h]
0x180003c8b  mov     rsp, r11
0x180003c8e  pop     rbp
0x180003c8f  retn
```
