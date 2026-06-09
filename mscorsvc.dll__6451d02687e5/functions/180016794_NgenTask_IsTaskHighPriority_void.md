# NgenTask::IsTaskHighPriority(void)

- ea: `0x180016794`
- end: `0x180016920`
- name: `?IsTaskHighPriority@NgenTask@@YA_NXZ`
- size: `396`
- prototype: `bool __fastcall(NgenTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180016fd4`

## callees

- `0x180001e8c`
- `0x1800068a8`
- `0x180016794`
- `0x180030d84`
- `0x180037340`
- `0x180037ad4`
- `0x18003dc30`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800168b3`
- `ADVAPI32!RegCloseKey` at `0x1800168b3`
- `KERNEL32!HeapFree` at `0x1800168ef`
- `KERNEL32!HeapFree` at `0x1800168ef`
- `KERNEL32!GetProcessHeap` at `0x1800168da`
- `KERNEL32!GetProcessHeap` at `0x1800168da`

## string_xrefs

- `0x180016800`: `\NgenService`
- `0x180016896`: `TaskHighPriorityMode`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
bool __fastcall NgenTask::IsTaskHighPriority(NgenTask *this)
{
  __int64 v1; // r8
  DWORD v2; // edx
  bool v3; // cl
  const unsigned __int16 *v4; // r8
  int v5; // eax
  bool v6; // di
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  HKEY hKey; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-C0h]
  HKEY *p_hKey; // [rsp+50h] [rbp-B8h]
  int v13; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+5Ch] [rbp-ACh]
  LPVOID lpMem; // [rsp+68h] [rbp-A0h]
  __int16 v16; // [rsp+70h] [rbp-98h] BYREF

  v14 = 512;
  lpMem = &v16;
  v13 = 2;
  v16 = 0;
  Helpers::CLRVersionRegistryRootName((struct SString *)&v13);
  SString::Append((SString *)&v13, L"\\NgenService");
  SString::Append((SString *)&v13, L"\\State");
  LODWORD(v11) = 0;
  p_hKey = &hKey;
  hKey = 0;
  SString::ConvertToUnicode((SString *)&v13);
  v3 = ClrRegOpenKeyEx(HKEY_LOCAL_MACHINE, (const unsigned __int16 *)lpMem, v1, 0x20019u, &hKey) != 0;
  v5 = v11;
  if ( hKey )
    v5 = 1;
  LODWORD(v11) = v5;
  v6 = !v3 && (unsigned int)REGUTIL::GetLong(L"TaskHighPriorityMode", v2, v4, hKey) != 0;
  if ( (_DWORD)v11 )
  {
    RegCloseKey(hKey);
    LODWORD(v11) = 0;
  }
  if ( (v14 & 0x800000000LL) != 0 )
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
  return v6;
}

```

## disassembly

```asm
0x180016794  mov     rax, rsp
0x180016797  mov     [rax+8], rbx
0x18001679b  mov     [rax+10h], rsi
0x18001679f  mov     [rax+18h], rdi
0x1800167a3  push    rbp
0x1800167a4  lea     rbp, [rax-188h]
0x1800167ab  sub     rsp, 280h
0x1800167b2  mov     rax, cs:__security_cookie
0x1800167b9  xor     rax, rsp
0x1800167bc  mov     [rbp+180h+var_10], rax
0x1800167c3  xor     esi, esi
0x1800167c5  mov     dword ptr [rsp+280h+var_250], esi
0x1800167c9  mov     qword ptr [rsp+280h+var_230], rsi
0x1800167ce  mov     qword ptr [rsp+54h], 200h
0x1800167d7  mov     [rsp+280h+lpMem], rsi
0x1800167dc  lea     rax, [rsp+280h+var_218]
0x1800167e1  mov     [rsp+280h+lpMem], rax
0x1800167e6  mov     [rsp+280h+var_230], 2
0x1800167ee  mov     rax, [rsp+280h+lpMem]
0x1800167f3  mov     [rax], si
0x1800167f6  lea     rcx, [rsp+280h+var_230]; this
0x1800167fb  call    ?CLRVersionRegistryRootName@Helpers@@SAXAEAVSString@@@Z; Helpers::CLRVersionRegistryRootName(SString &)
0x180016800  lea     rdx, aNgenservice_0; "\\NgenService"
0x180016807  lea     rcx, [rsp+280h+var_230]; this
0x18001680c  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016811  lea     rdx, aState; "\\State"
0x180016818  lea     rcx, [rsp+280h+var_230]; this
0x18001681d  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180016822  mov     [rsp+280h+hKey], rsi
0x180016827  mov     dword ptr [rsp+280h+var_240], esi
0x18001682b  lea     rax, [rsp+280h+hKey]
0x180016830  mov     [rsp+280h+var_238], rax
0x180016835  mov     [rsp+280h+hKey], rsi
0x18001683a  lea     ebx, [rsi+1]
0x18001683d  mov     dword ptr [rsp+280h+var_250], ebx
0x180016841  lea     rcx, [rsp+280h+var_230]; this
0x180016846  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x18001684b  lea     rax, [rsp+280h+hKey]
0x180016850  mov     [rsp+280h+var_260], rax; HKEY *
0x180016855  mov     r9d, 20019h; unsigned int
0x18001685b  mov     rdx, [rsp+280h+lpMem]; unsigned __int16 *
0x180016860  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180016867  call    ?ClrRegOpenKeyEx@@YAJPEAUHKEY__@@PEBGKKPEAPEAU1@@Z; ClrRegOpenKeyEx(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x18001686c  test    eax, eax
0x18001686e  setnz   cl
0x180016871  mov     eax, ebx
0x180016873  and     eax, 0FFFFFFFEh
0x180016876  mov     dword ptr [rsp+280h+var_250], eax
0x18001687a  mov     eax, dword ptr [rsp+280h+var_240]
0x18001687e  mov     r9, [rsp+280h+hKey]; HKEY
0x180016883  test    r9, r9
0x180016886  cmovnz  eax, ebx
0x180016889  mov     dword ptr [rsp+280h+var_240], eax
0x18001688d  test    cl, cl
0x18001688f  jz      short loc_180016896
0x180016891  mov     dil, sil
0x180016894  jmp     short loc_1800168A8
0x180016896  lea     rcx, aTaskhighpriori; "TaskHighPriorityMode"
0x18001689d  call    ?GetLong@REGUTIL@@SAJPEBGJ0PEAUHKEY__@@@Z; REGUTIL::GetLong(ushort const *,long,ushort const *,HKEY__ *)
0x1800168a2  test    eax, eax
0x1800168a4  setnz   dil
0x1800168a8  cmp     dword ptr [rsp+280h+var_240], esi
0x1800168ac  jz      short loc_1800168BD
0x1800168ae  mov     rcx, [rsp+280h+hKey]; hKey
0x1800168b3  call    cs:__imp_RegCloseKey
0x1800168b9  mov     dword ptr [rsp+280h+var_240], esi
0x1800168bd  test    byte ptr [rsp+280h+var_228], 8
0x1800168c2  jz      short loc_1800168F5
0x1800168c4  mov     rbx, [rsp+280h+lpMem]
0x1800168c9  test    rbx, rbx
0x1800168cc  jz      short loc_1800168F5
0x1800168ce  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800168d5  test    rax, rax
0x1800168d8  jnz     short loc_1800168E7
0x1800168da  call    cs:__imp_GetProcessHeap
0x1800168e0  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1800168e7  mov     r8, rbx; lpMem
0x1800168ea  xor     edx, edx; dwFlags
0x1800168ec  mov     rcx, rax; hHeap
0x1800168ef  call    cs:__imp_HeapFree
0x1800168f5  mov     al, dil
0x1800168f8  mov     rcx, [rbp+180h+var_10]
0x1800168ff  xor     rcx, rsp; StackCookie
0x180016902  call    __security_check_cookie
0x180016907  lea     r11, [rsp+280h+var_s0]
0x18001690f  mov     rbx, [r11+10h]
0x180016913  mov     rsi, [r11+18h]
0x180016917  mov     rdi, [r11+20h]
0x18001691b  mov     rsp, r11
0x18001691e  pop     rbp
0x18001691f  retn
```
