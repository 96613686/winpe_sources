# NgenTask::SetTaskPaused(bool)

- ea: `0x180016ca8`
- end: `0x180016ead`
- name: `?SetTaskPaused@NgenTask@@YAX_N@Z`
- size: `517`
- prototype: `void __fastcall(NgenTask *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008500`

## callees

- `0x180001e8c`
- `0x1800068a8`
- `0x180016ca8`
- `0x180030d84`
- `0x180037964`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016e19`
- `ADVAPI32!RegCloseKey` at `0x180016e41`
- `ADVAPI32!RegCloseKey` at `0x180016e19`
- `ADVAPI32!RegCloseKey` at `0x180016e41`
- `ADVAPI32!RegDeleteKeyW` at `0x180016e2f`
- `ADVAPI32!RegDeleteKeyW` at `0x180016e2f`
- `KERNEL32!HeapFree` at `0x180016e7b`
- `KERNEL32!HeapFree` at `0x180016e7b`
- `KERNEL32!GetProcessHeap` at `0x180016e66`
- `KERNEL32!GetProcessHeap` at `0x180016e66`

## string_xrefs

- `0x180016d13`: `\NgenService`
- `0x180016de5`: `TaskPaused`
- `0x180016e25`: `TaskPaused`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall NgenTask::SetTaskPaused(NgenTask *this)
{
  char v1; // di
  __int64 v2; // r8
  unsigned __int16 *v3; // r9
  bool v4; // cl
  unsigned __int16 *v5; // r9
  int v6; // eax
  int v7; // eax
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  struct _SECURITY_ATTRIBUTES *v10; // [rsp+38h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+38h] [rbp-D0h]
  HKEY v12; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v13; // [rsp+68h] [rbp-A0h]
  HKEY hKey; // [rsp+70h] [rbp-98h] BYREF
  __int64 v15; // [rsp+78h] [rbp-90h]
  HKEY *p_hKey; // [rsp+80h] [rbp-88h]
  int v17; // [rsp+88h] [rbp-80h] BYREF
  __int64 v18; // [rsp+8Ch] [rbp-7Ch]
  LPVOID lpMem; // [rsp+98h] [rbp-70h]
  __int16 v20; // [rsp+A0h] [rbp-68h] BYREF

  v1 = (char)this;
  v18 = 512;
  lpMem = &v20;
  v17 = 2;
  v20 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v17);
  SString::Append((SString *)&v17, L"\\NgenService");
  SString::Append((SString *)&v17, L"\\State");
  LODWORD(v13) = 0;
  p_hKey = &v12;
  v12 = 0;
  SString::ConvertToUnicode((SString *)&v17);
  v4 = ClrRegCreateKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v2, v3, 0, 0x2001Bu, v10, &v12) != 0;
  v6 = v13;
  if ( v12 )
    v6 = 1;
  LODWORD(v13) = v6;
  if ( !v4 )
  {
    if ( v1 )
    {
      LODWORD(v15) = 0;
      p_hKey = &hKey;
      hKey = 0;
      ClrRegCreateKeyEx(v12, L"TaskPaused", (__int64)v12, v5, 1u, 0, v11, &hKey);
      v7 = v15;
      if ( hKey )
        v7 = 1;
      LODWORD(v15) = v7;
      if ( v7 )
      {
        RegCloseKey(hKey);
        LODWORD(v15) = 0;
      }
    }
    else
    {
      RegDeleteKeyW(v12, L"TaskPaused");
    }
  }
  if ( (_DWORD)v13 )
  {
    RegCloseKey(v12);
    LODWORD(v13) = 0;
  }
  if ( (v18 & 0x800000000LL) != 0 )
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
}

```

## disassembly

```asm
0x180016ca8  mov     rax, rsp
0x180016cab  mov     [rax+8], rbx
0x180016caf  mov     [rax+10h], rsi
0x180016cb3  mov     [rax+18h], rdi
0x180016cb7  mov     [rax+20h], r14
0x180016cbb  push    rbp
0x180016cbc  lea     rbp, [rax-1B8h]
0x180016cc3  sub     rsp, 2B0h
0x180016cca  mov     rax, cs:__security_cookie
0x180016cd1  xor     rax, rsp
0x180016cd4  mov     [rbp+1B0h+var_10], rax
0x180016cdb  mov     dil, cl
0x180016cde  xor     esi, esi
0x180016ce0  mov     dword ptr [rsp+2B0h+var_260], esi
0x180016ce4  mov     [rbp+1B0h+var_230], rsi
0x180016ce8  mov     [rbp+1B0h+var_230+4], 200h
0x180016cf0  mov     [rbp+1B0h+lpMem], rsi
0x180016cf4  lea     rax, [rbp+1B0h+var_218]
0x180016cf8  mov     [rbp+1B0h+lpMem], rax
0x180016cfc  mov     dword ptr [rbp+1B0h+var_230], 2
0x180016d03  mov     rax, [rbp+1B0h+lpMem]
0x180016d07  mov     [rax], si
0x180016d0a  lea     rcx, [rbp+1B0h+var_230]; this
0x180016d0e  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x180016d13  lea     rdx, aNgenservice_0; "\\NgenService"
0x180016d1a  lea     rcx, [rbp+1B0h+var_230]; this
0x180016d1e  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016d23  lea     rdx, aState; "\\State"
0x180016d2a  lea     rcx, [rbp+1B0h+var_230]; this
0x180016d2e  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016d33  mov     [rsp+2B0h+var_258], rsi
0x180016d38  mov     dword ptr [rsp+2B0h+var_250], esi
0x180016d3c  lea     rax, [rsp+2B0h+var_258]
0x180016d41  mov     [rsp+2B0h+var_238], rax
0x180016d46  mov     [rsp+2B0h+var_258], rsi
0x180016d4b  lea     r14d, [rsi+1]
0x180016d4f  mov     dword ptr [rsp+2B0h+var_260], r14d
0x180016d54  lea     rcx, [rbp+1B0h+var_230]; this
0x180016d58  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180016d5d  lea     rax, [rsp+2B0h+var_258]
0x180016d62  mov     [rsp+2B0h+var_278], rax; HKEY *
0x180016d67  mov     [rsp+2B0h+var_288], 2001Bh; REGSAM
0x180016d6f  mov     [rsp+2B0h+var_290], esi; DWORD
0x180016d73  mov     rdx, [rbp+1B0h+lpMem]; unsigned __int16 *
0x180016d77  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180016d7e  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180016d83  test    eax, eax
0x180016d85  setnz   cl
0x180016d88  mov     ebx, r14d
0x180016d8b  and     ebx, 0FFFFFFFEh
0x180016d8e  mov     dword ptr [rsp+2B0h+var_260], ebx
0x180016d92  mov     eax, dword ptr [rsp+2B0h+var_250]
0x180016d96  mov     r8, [rsp+2B0h+var_258]; unsigned int
0x180016d9b  test    r8, r8
0x180016d9e  cmovnz  eax, r14d
0x180016da2  mov     dword ptr [rsp+2B0h+var_250], eax
0x180016da6  test    cl, cl
0x180016da8  jnz     loc_180016E36
0x180016dae  test    dil, dil
0x180016db1  jz      short loc_180016E25
0x180016db3  mov     [rsp+2B0h+hKey], rsi
0x180016db8  mov     dword ptr [rsp+2B0h+var_240], esi
0x180016dbc  lea     rax, [rsp+2B0h+hKey]
0x180016dc1  mov     [rsp+2B0h+var_238], rax
0x180016dc6  mov     [rsp+2B0h+hKey], rsi
0x180016dcb  or      ebx, 2
0x180016dce  mov     dword ptr [rsp+2B0h+var_260], ebx
0x180016dd2  lea     rax, [rsp+2B0h+hKey]
0x180016dd7  mov     [rsp+2B0h+var_278], rax; HKEY *
0x180016ddc  mov     [rsp+2B0h+var_288], esi; REGSAM
0x180016de0  mov     [rsp+2B0h+var_290], r14d; DWORD
0x180016de5  lea     rdx, SubKey; "TaskPaused"
0x180016dec  mov     rcx, [rsp+2B0h+var_258]; HKEY
0x180016df1  call    ?ClrRegCreateKeyEx@@YAJPEAUHKEY__@@PEBGKPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAK@Z; ClrRegCreateKeyEx(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,HKEY__ * *,ulong *)
0x180016df6  and     ebx, 0FFFFFFFDh
0x180016df9  mov     dword ptr [rsp+2B0h+var_260], ebx
0x180016dfd  mov     eax, dword ptr [rsp+2B0h+var_240]
0x180016e01  cmp     [rsp+2B0h+hKey], rsi
0x180016e06  cmovnz  eax, r14d
0x180016e0a  mov     dword ptr [rsp+2B0h+var_240], eax
0x180016e0e  cmp     dword ptr [rsp+2B0h+var_240], esi
0x180016e12  jz      short loc_180016E36
0x180016e14  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180016e19  call    cs:__imp_RegCloseKey
0x180016e1f  mov     dword ptr [rsp+2B0h+var_240], esi
0x180016e23  jmp     short loc_180016E36
0x180016e25  lea     rdx, SubKey; "TaskPaused"
0x180016e2c  mov     rcx, r8; hKey
0x180016e2f  call    cs:__imp_RegDeleteKeyW
0x180016e35  nop
0x180016e36  cmp     dword ptr [rsp+2B0h+var_250], esi
0x180016e3a  jz      short loc_180016E4B
0x180016e3c  mov     rcx, [rsp+2B0h+var_258]; hKey
0x180016e41  call    cs:__imp_RegCloseKey
0x180016e47  mov     dword ptr [rsp+2B0h+var_250], esi
0x180016e4b  test    [rbp+1B0h+var_228], 8
0x180016e4f  jz      short loc_180016E81
0x180016e51  mov     rbx, [rbp+1B0h+lpMem]
0x180016e55  test    rbx, rbx
0x180016e58  jz      short loc_180016E81
0x180016e5a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016e61  test    rax, rax
0x180016e64  jnz     short loc_180016E73
0x180016e66  call    cs:__imp_GetProcessHeap
0x180016e6c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016e73  mov     r8, rbx; lpMem
0x180016e76  xor     edx, edx; dwFlags
0x180016e78  mov     rcx, rax; hHeap
0x180016e7b  call    cs:__imp_HeapFree
0x180016e81  mov     rcx, [rbp+1B0h+var_10]
0x180016e88  xor     rcx, rsp; StackCookie
0x180016e8b  call    __security_check_cookie
0x180016e90  lea     r11, [rsp+2B0h+var_s0]
0x180016e98  mov     rbx, [r11+10h]
0x180016e9c  mov     rsi, [r11+18h]
0x180016ea0  mov     rdi, [r11+20h]
0x180016ea4  mov     r14, [r11+28h]
0x180016ea8  mov     rsp, r11
0x180016eab  pop     rbp
0x180016eac  retn
```
