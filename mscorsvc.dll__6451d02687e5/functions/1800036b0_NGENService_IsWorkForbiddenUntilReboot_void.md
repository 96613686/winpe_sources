# NGENService::IsWorkForbiddenUntilReboot(void)

- ea: `0x1800036b0`
- end: `0x180003822`
- name: `?IsWorkForbiddenUntilReboot@NGENService@@YA_NXZ`
- size: `370`
- prototype: `bool __fastcall(NGENService *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180004cac`
- `0x1800053a0`

## callees

- `0x180001e8c`
- `0x1800036b0`
- `0x1800068a8`
- `0x180030d84`
- `0x180037ad4`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800037b5`
- `ADVAPI32!RegCloseKey` at `0x1800037b5`
- `KERNEL32!HeapFree` at `0x1800037f1`
- `KERNEL32!HeapFree` at `0x1800037f1`
- `KERNEL32!GetProcessHeap` at `0x1800037dc`
- `KERNEL32!GetProcessHeap` at `0x1800037dc`

## string_xrefs

- `0x18000371c`: `\NgenService`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
bool __fastcall NGENService::IsWorkForbiddenUntilReboot(NGENService *this)
{
  __int64 v1; // r8
  bool v2; // di
  int v3; // eax
  bool v4; // di
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-C0h]
  HKEY *p_hKey; // [rsp+50h] [rbp-B8h]
  int v11; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+5Ch] [rbp-ACh]
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  __int16 v14; // [rsp+70h] [rbp-98h] BYREF

  v12 = 512;
  lpMem = &v14;
  v11 = 2;
  v14 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v11);
  SString::Append((SString *)&v11, L"\\NgenService");
  SString::Append((SString *)&v11, L"\\State\\PendingReboot");
  LODWORD(v9) = 0;
  p_hKey = &hKey;
  hKey = 0;
  SString::ConvertToUnicode((SString *)&v11);
  v2 = ClrRegOpenKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v1, 0x20019u, &hKey) != 0;
  v3 = v9;
  if ( hKey )
    v3 = 1;
  LODWORD(v9) = v3;
  v4 = !v2;
  if ( v3 )
  {
    RegCloseKey(hKey);
    LODWORD(v9) = 0;
  }
  if ( (v12 & 0x800000000LL) != 0 )
  {
    v5 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
      }
      HeapFree(ProcessHeap, 0, v5);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800036b0  mov     rax, rsp
0x1800036b3  mov     [rax+8], rbx
0x1800036b7  mov     [rax+10h], rsi
0x1800036bb  mov     [rax+18h], rdi
0x1800036bf  push    rbp
0x1800036c0  lea     rbp, [rax-188h]
0x1800036c7  sub     rsp, 280h
0x1800036ce  mov     rax, cs:__security_cookie
0x1800036d5  xor     rax, rsp
0x1800036d8  mov     [rbp+180h+var_10], rax
0x1800036df  xor     esi, esi
0x1800036e1  mov     dword ptr [rsp+280h+var_250], esi
0x1800036e5  mov     qword ptr [rsp+280h+var_230], rsi
0x1800036ea  mov     qword ptr [rsp+54h], 200h
0x1800036f3  mov     [rsp+280h+lpMem], rsi
0x1800036f8  lea     rax, [rsp+280h+var_218]
0x1800036fd  mov     [rsp+280h+lpMem], rax
0x180003702  mov     [rsp+280h+var_230], 2
0x18000370a  mov     rax, [rsp+280h+lpMem]
0x18000370f  mov     [rax], si
0x180003712  lea     rcx, [rsp+280h+var_230]; this
0x180003717  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x18000371c  lea     rdx, aNgenservice_0; "\\NgenService"
0x180003723  lea     rcx, [rsp+280h+var_230]; this
0x180003728  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18000372d  lea     rdx, aStatePendingre; "\\State\\PendingReboot"
0x180003734  lea     rcx, [rsp+280h+var_230]; this
0x180003739  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x18000373e  mov     [rsp+280h+hKey], rsi
0x180003743  mov     dword ptr [rsp+280h+var_240], esi
0x180003747  lea     rax, [rsp+280h+hKey]
0x18000374c  mov     [rsp+280h+var_238], rax
0x180003751  mov     [rsp+280h+hKey], rsi
0x180003756  lea     ebx, [rsi+1]
0x180003759  mov     dword ptr [rsp+280h+var_250], ebx
0x18000375d  lea     rcx, [rsp+280h+var_230]; this
0x180003762  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180003767  lea     rax, [rsp+280h+hKey]
0x18000376c  mov     [rsp+280h+var_260], rax; HKEY *
0x180003771  mov     r9d, 20019h; unsigned int
0x180003777  mov     rdx, [rsp+280h+lpMem]; unsigned __int16 *
0x18000377c  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180003783  call    ?ClrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ClrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x180003788  test    eax, eax
0x18000378a  setnz   dil
0x18000378e  mov     eax, ebx
0x180003790  and     eax, 0FFFFFFFEh
0x180003793  mov     dword ptr [rsp+280h+var_250], eax
0x180003797  mov     eax, dword ptr [rsp+280h+var_240]
0x18000379b  cmp     [rsp+280h+hKey], rsi
0x1800037a0  cmovnz  eax, ebx
0x1800037a3  mov     dword ptr [rsp+280h+var_240], eax
0x1800037a7  xor     dil, bl
0x1800037aa  cmp     dword ptr [rsp+280h+var_240], esi
0x1800037ae  jz      short loc_1800037BF
0x1800037b0  mov     rcx, [rsp+280h+hKey]; hKey
0x1800037b5  call    cs:__imp_RegCloseKey
0x1800037bb  mov     dword ptr [rsp+280h+var_240], esi
0x1800037bf  test    byte ptr [rsp+280h+var_228], 8
0x1800037c4  jz      short loc_1800037F7
0x1800037c6  mov     rbx, [rsp+280h+lpMem]
0x1800037cb  test    rbx, rbx
0x1800037ce  jz      short loc_1800037F7
0x1800037d0  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800037d7  test    rax, rax
0x1800037da  jnz     short loc_1800037E9
0x1800037dc  call    cs:__imp_GetProcessHeap
0x1800037e2  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800037e9  mov     r8, rbx; lpMem
0x1800037ec  xor     edx, edx; dwFlags
0x1800037ee  mov     rcx, rax; hHeap
0x1800037f1  call    cs:__imp_HeapFree
0x1800037f7  mov     al, dil
0x1800037fa  mov     rcx, [rbp+180h+var_10]
0x180003801  xor     rcx, rsp; StackCookie
0x180003804  call    __security_check_cookie
0x180003809  lea     r11, [rsp+280h+var_s0]
0x180003811  mov     rbx, [r11+10h]
0x180003815  mov     rsi, [r11+18h]
0x180003819  mov     rdi, [r11+20h]
0x18000381d  mov     rsp, r11
0x180003820  pop     rbp
0x180003821  retn
```
