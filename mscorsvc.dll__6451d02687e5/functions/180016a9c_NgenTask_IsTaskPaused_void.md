# NgenTask::IsTaskPaused(void)

- ea: `0x180016a9c`
- end: `0x180016ca6`
- name: `?IsTaskPaused@NgenTask@@YA_NXZ`
- size: `522`
- prototype: `bool __fastcall(NgenTask *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180015208`
- `0x180015de4`
- `0x1800171a8`
- `0x180017698`

## callees

- `0x180001e8c`
- `0x1800068a8`
- `0x180016a9c`
- `0x180030d84`
- `0x180037ad4`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180016bc3`
- `ADVAPI32!RegCloseKey` at `0x180016c20`
- `ADVAPI32!RegCloseKey` at `0x180016c35`
- `ADVAPI32!RegCloseKey` at `0x180016bc3`
- `ADVAPI32!RegCloseKey` at `0x180016c20`
- `ADVAPI32!RegCloseKey` at `0x180016c35`
- `KERNEL32!HeapFree` at `0x180016c71`
- `KERNEL32!HeapFree` at `0x180016c71`
- `KERNEL32!GetProcessHeap` at `0x180016c5c`
- `KERNEL32!GetProcessHeap` at `0x180016c5c`

## string_xrefs

- `0x180016b0c`: `\NgenService`
- `0x180016be6`: `TaskPaused`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
bool __fastcall NgenTask::IsTaskPaused(NgenTask *this)
{
  __int64 v1; // r8
  bool v2; // cl
  __int64 v3; // r8
  int v4; // eax
  bool v5; // di
  int v6; // eax
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-C0h]
  HKEY v12; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v13; // [rsp+58h] [rbp-B0h]
  HKEY *p_hKey; // [rsp+60h] [rbp-A8h]
  int v15; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v16; // [rsp+6Ch] [rbp-9Ch]
  LPVOID lpMem; // [rsp+78h] [rbp-90h]
  __int16 v18; // [rsp+80h] [rbp-88h] BYREF

  v16 = 512;
  lpMem = &v18;
  v15 = 2;
  v18 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v15);
  SString::Append((SString *)&v15, L"\\NgenService");
  SString::Append((SString *)&v15, L"\\State");
  LODWORD(v13) = 0;
  hKey = 0;
  LODWORD(v11) = 0;
  p_hKey = &v12;
  v12 = 0;
  SString::ConvertToUnicode((SString *)&v15);
  v2 = ClrRegOpenKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v1, 0x20019u, &v12) != 0;
  v4 = v13;
  if ( v12 )
    v4 = 1;
  LODWORD(v13) = v4;
  if ( v2 )
  {
    v5 = 0;
  }
  else
  {
    p_hKey = &hKey;
    hKey = 0;
    v5 = ClrRegOpenKeyEx(v12, L"TaskPaused", v3, 0x20019u, &hKey) == 0;
    v6 = v11;
    if ( hKey )
      v6 = 1;
    LODWORD(v11) = v6;
  }
  if ( (_DWORD)v11 )
  {
    RegCloseKey(hKey);
    LODWORD(v11) = 0;
  }
  if ( (_DWORD)v13 )
  {
    RegCloseKey(v12);
    LODWORD(v13) = 0;
  }
  if ( (v16 & 0x800000000LL) != 0 )
  {
    v7 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v7);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180016a9c  mov     rax, rsp
0x180016a9f  mov     [rax+8], rbx
0x180016aa3  mov     [rax+10h], rsi
0x180016aa7  mov     [rax+18h], rdi
0x180016aab  mov     [rax+20h], r14
0x180016aaf  push    rbp
0x180016ab0  lea     rbp, [rax-198h]
0x180016ab7  sub     rsp, 290h
0x180016abe  mov     rax, cs:__security_cookie
0x180016ac5  xor     rax, rsp
0x180016ac8  mov     [rbp+190h+var_10], rax
0x180016acf  xor     esi, esi
0x180016ad1  mov     dword ptr [rsp+290h+var_260], esi
0x180016ad5  mov     qword ptr [rsp+290h+var_230], rsi
0x180016ada  mov     qword ptr [rsp+64h], 200h
0x180016ae3  mov     [rsp+290h+lpMem], rsi
0x180016ae8  lea     rax, [rsp+290h+var_218]
0x180016aed  mov     [rsp+290h+lpMem], rax
0x180016af2  mov     [rsp+290h+var_230], 2
0x180016afa  mov     rax, [rsp+290h+lpMem]
0x180016aff  mov     [rax], si
0x180016b02  lea     rcx, [rsp+290h+var_230]; this
0x180016b07  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x180016b0c  lea     rdx, aNgenservice_0; "\\NgenService"
0x180016b13  lea     rcx, [rsp+290h+var_230]; this
0x180016b18  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016b1d  lea     rdx, aState; "\\State"
0x180016b24  lea     rcx, [rsp+290h+var_230]; this
0x180016b29  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016b2e  mov     [rsp+290h+var_248], rsi
0x180016b33  mov     dword ptr [rsp+290h+var_240], esi
0x180016b37  mov     [rsp+290h+hKey], rsi
0x180016b3c  mov     dword ptr [rsp+290h+var_250], esi
0x180016b40  lea     rax, [rsp+290h+var_248]
0x180016b45  mov     [rsp+290h+var_238], rax
0x180016b4a  mov     [rsp+290h+var_248], rsi
0x180016b4f  lea     r14d, [rsi+1]
0x180016b53  mov     dword ptr [rsp+290h+var_260], r14d
0x180016b58  lea     rcx, [rsp+290h+var_230]; this
0x180016b5d  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180016b62  lea     rax, [rsp+290h+var_248]
0x180016b67  mov     [rsp+290h+var_270], rax; HKEY *
0x180016b6c  mov     edi, 20019h
0x180016b71  mov     r9d, edi; unsigned int
0x180016b74  mov     rdx, [rsp+290h+lpMem]; unsigned __int16 *
0x180016b79  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180016b80  call    ?ClrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ClrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180016b85  test    eax, eax
0x180016b87  setnz   cl
0x180016b8a  mov     ebx, r14d
0x180016b8d  and     ebx, 0FFFFFFFEh
0x180016b90  mov     dword ptr [rsp+290h+var_260], ebx
0x180016b94  mov     eax, dword ptr [rsp+290h+var_240]
0x180016b98  cmp     [rsp+290h+var_248], rsi
0x180016b9d  cmovnz  eax, r14d
0x180016ba1  mov     dword ptr [rsp+290h+var_240], eax
0x180016ba5  test    cl, cl
0x180016ba7  jz      short loc_180016BAE
0x180016ba9  mov     dil, sil
0x180016bac  jmp     short loc_180016C15
0x180016bae  lea     rax, [rsp+290h+hKey]
0x180016bb3  mov     [rsp+290h+var_238], rax
0x180016bb8  cmp     dword ptr [rsp+290h+var_250], esi
0x180016bbc  jz      short loc_180016BCD
0x180016bbe  mov     rcx, [rsp+290h+hKey]; hKey
0x180016bc3  call    cs:__imp_RegCloseKey
0x180016bc9  mov     dword ptr [rsp+290h+var_250], esi
0x180016bcd  mov     [rsp+290h+hKey], rsi
0x180016bd2  or      ebx, 2
0x180016bd5  mov     dword ptr [rsp+290h+var_260], ebx
0x180016bd9  lea     rax, [rsp+290h+hKey]
0x180016bde  mov     [rsp+290h+var_270], rax; HKEY *
0x180016be3  mov     r9d, edi; unsigned int
0x180016be6  lea     rdx, SubKey; "TaskPaused"
0x180016bed  mov     rcx, [rsp+290h+var_248]; HKEY
0x180016bf2  call    ?ClrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ClrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180016bf7  test    eax, eax
0x180016bf9  setz    dil
0x180016bfd  and     ebx, 0FFFFFFFDh
0x180016c00  mov     dword ptr [rsp+290h+var_260], ebx
0x180016c04  mov     eax, dword ptr [rsp+290h+var_250]
0x180016c08  cmp     [rsp+290h+hKey], rsi
0x180016c0d  cmovnz  eax, r14d
0x180016c11  mov     dword ptr [rsp+290h+var_250], eax
0x180016c15  cmp     dword ptr [rsp+290h+var_250], esi
0x180016c19  jz      short loc_180016C2A
0x180016c1b  mov     rcx, [rsp+290h+hKey]; hKey
0x180016c20  call    cs:__imp_RegCloseKey
0x180016c26  mov     dword ptr [rsp+290h+var_250], esi
0x180016c2a  cmp     dword ptr [rsp+290h+var_240], esi
0x180016c2e  jz      short loc_180016C3F
0x180016c30  mov     rcx, [rsp+290h+var_248]; hKey
0x180016c35  call    cs:__imp_RegCloseKey
0x180016c3b  mov     dword ptr [rsp+290h+var_240], esi
0x180016c3f  test    byte ptr [rsp+290h+var_228], 8
0x180016c44  jz      short loc_180016C77
0x180016c46  mov     rbx, [rsp+290h+lpMem]
0x180016c4b  test    rbx, rbx
0x180016c4e  jz      short loc_180016C77
0x180016c50  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016c57  test    rax, rax
0x180016c5a  jnz     short loc_180016C69
0x180016c5c  call    cs:__imp_GetProcessHeap
0x180016c62  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180016c69  mov     r8, rbx; lpMem
0x180016c6c  xor     edx, edx; dwFlags
0x180016c6e  mov     rcx, rax; hHeap
0x180016c71  call    cs:__imp_HeapFree
0x180016c77  mov     al, dil
0x180016c7a  mov     rcx, [rbp+190h+var_10]
0x180016c81  xor     rcx, rsp; StackCookie
0x180016c84  call    __security_check_cookie
0x180016c89  lea     r11, [rsp+290h+var_s0]
0x180016c91  mov     rbx, [r11+10h]
0x180016c95  mov     rsi, [r11+18h]
0x180016c99  mov     rdi, [r11+20h]
0x180016c9d  mov     r14, [r11+28h]
0x180016ca1  mov     rsp, r11
0x180016ca4  pop     rbp
0x180016ca5  retn
```
