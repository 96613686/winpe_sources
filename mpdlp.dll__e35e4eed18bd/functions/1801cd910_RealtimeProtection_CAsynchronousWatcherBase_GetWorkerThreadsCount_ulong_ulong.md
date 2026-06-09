# RealtimeProtection::CAsynchronousWatcherBase::GetWorkerThreadsCount(ulong &,ulong &)

- ea: `0x1801cd910`
- end: `0x1801cdaf2`
- name: `?GetWorkerThreadsCount@CAsynchronousWatcherBase@RealtimeProtection@@EEAAXAEAK0@Z`
- size: `482`
- prototype: `void __fastcall(RealtimeProtection::CAsynchronousWatcherBase *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180046d10`
- `0x180087900`
- `0x18010cb40`
- `0x1801cd910`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x1801cd9cb`
- `MpClient!MpConfigGetValue` at `0x1801cd9cb`
- `MpClient!MpConfigClose` at `0x1801cd9f6`
- `MpClient!MpConfigClose` at `0x1801cd9f6`
- `MpClient!MpConfigOpen` at `0x1801cd992`
- `MpClient!MpConfigOpen` at `0x1801cd992`
- `KERNEL32!GetSystemInfo` at `0x1801cd957`
- `KERNEL32!GetSystemInfo` at `0x1801cd957`

## string_xrefs

- `0x1801cd9ba`: `DlpAsyncThreadNumberFactorInPercent`
- `0x1801cda14`: `MpRTP_AsyncWatcherNormalPriorityThreadCount`
- `0x1801cda5e`: `MpRTP_AsyncWatcherVeryLowPriorityThreadCount`

## pseudocode

```c
void __fastcall RealtimeProtection::CAsynchronousWatcherBase::GetWorkerThreadsCount(
        RealtimeProtection::CAsynchronousWatcherBase *this,
        unsigned int *a2,
        unsigned int *a3)
{
  DWORD dwNumberOfProcessors; // edi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  DWORD v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // eax
  PVOID *v15; // rcx
  int v16; // [rsp+30h] [rbp-50h] BYREF
  int v17; // [rsp+34h] [rbp-4Ch] BYREF
  int v18; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-40h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-38h] BYREF

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  dwNumberOfProcessors = 4;
  GetSystemInfo(&SystemInfo);
  v7 = *((_DWORD *)this + 126);
  if ( v7 == 1 )
  {
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  }
  else
  {
    if ( v7 != 2 )
      goto LABEL_14;
    v8 = 100;
    v19 = 0;
    v16 = 100;
    if ( (int)MpConfigOpen(L"Features", &v19) < 0
      || (v18 = 1,
          v17 = 4,
          (int)((__int64 (__fastcall *)(__int64, const wchar_t *, int *, int *, int *, _QWORD))MpConfigGetValue)(
                 v19,
                 L"DlpAsyncThreadNumberFactorInPercent",
                 &v18,
                 &v17,
                 &v16,
                 0) >= 0) )
    {
      v8 = v16;
    }
    else
    {
      v16 = 100;
    }
    v12 = SystemInfo.dwNumberOfProcessors * v8;
    dwNumberOfProcessors = v12 / 0x64;
    if ( v19 )
    {
      LODWORD(v9) = (1374389535 * (unsigned __int64)v12) >> 32;
      MpConfigClose(v19, v9, v10, v11);
    }
  }
  if ( dwNumberOfProcessors >= 4 )
  {
    if ( dwNumberOfProcessors > 0x20 )
      dwNumberOfProcessors = 32;
  }
  else
  {
    dwNumberOfProcessors = 4;
  }
LABEL_14:
  v13 = MpLookupMiscConfig(L"MpRTP_AsyncWatcherNormalPriorityThreadCount", dwNumberOfProcessors);
  *a2 = v13;
  if ( v13 != dwNumberOfProcessors
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids,
      dwNumberOfProcessors,
      v13);
  }
  v14 = MpLookupMiscConfig(L"MpRTP_AsyncWatcherVeryLowPriorityThreadCount", 0);
  *a3 = v14;
  if ( !v14 )
    goto LABEL_22;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids, 0, v14);
LABEL_22:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
    WPP_SF_Dd(v15[2], 13, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids, *a2, *a3);
}

```

## disassembly

```asm
0x1801cd910  mov     [rsp-18h+arg_0], rbx
0x1801cd915  mov     [rsp-18h+arg_18], rsi
0x1801cd91a  push    rbp
0x1801cd91b  push    rdi
0x1801cd91c  push    r14
0x1801cd91e  mov     rbp, rsp
0x1801cd921  sub     rsp, 80h
0x1801cd928  mov     rax, cs:__security_cookie
0x1801cd92f  xor     rax, rsp
0x1801cd932  mov     [rbp+var_8], rax
0x1801cd936  xorps   xmm0, xmm0
0x1801cd939  mov     rbx, rcx
0x1801cd93c  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1801cd940  mov     rsi, r8
0x1801cd943  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1801cd947  mov     r14, rdx
0x1801cd94a  mov     edi, 4
0x1801cd94f  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1801cd953  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1801cd957  call    cs:__imp_GetSystemInfo
0x1801cd95d  mov     eax, [rbx+1F8h]
0x1801cd963  cmp     eax, 1
0x1801cd966  jnz     short loc_1801CD970
0x1801cd968  mov     edi, [rbp+SystemInfo.dwNumberOfProcessors]
0x1801cd96b  jmp     loc_1801CD9FC
0x1801cd970  cmp     eax, 2
0x1801cd973  jnz     loc_1801CDA12
0x1801cd979  lea     ebx, [rax+62h]
0x1801cd97c  mov     [rbp+var_40], 0
0x1801cd984  lea     rdx, [rbp+var_40]
0x1801cd988  mov     [rbp+var_50], ebx
0x1801cd98b  lea     rcx, aFeatures_0; "Features"
0x1801cd992  call    cs:__imp_MpConfigOpen
0x1801cd998  test    eax, eax
0x1801cd99a  js      short loc_1801CD9DA
0x1801cd99c  mov     rcx, [rbp+var_40]
0x1801cd9a0  lea     rax, [rbp+var_50]
0x1801cd9a4  mov     [rsp+80h+var_58], 0
0x1801cd9ad  lea     r9, [rbp+var_4C]
0x1801cd9b1  lea     r8, [rbp+var_48]
0x1801cd9b5  mov     [rsp+80h+var_60], rax
0x1801cd9ba  lea     rdx, aDlpasyncthread; "DlpAsyncThreadNumberFactorInPercent"
0x1801cd9c1  mov     [rbp+var_48], 1
0x1801cd9c8  mov     [rbp+var_4C], edi
0x1801cd9cb  call    cs:__imp_MpConfigGetValue
0x1801cd9d1  test    eax, eax
0x1801cd9d3  jns     short loc_1801CD9DA
0x1801cd9d5  mov     [rbp+var_50], ebx
0x1801cd9d8  jmp     short loc_1801CD9DD
0x1801cd9da  mov     ebx, [rbp+var_50]
0x1801cd9dd  imul    ebx, [rbp+SystemInfo.dwNumberOfProcessors]
0x1801cd9e1  mov     eax, 51EB851Fh
0x1801cd9e6  mov     rcx, [rbp+var_40]
0x1801cd9ea  mul     ebx
0x1801cd9ec  mov     edi, edx
0x1801cd9ee  shr     edi, 5
0x1801cd9f1  test    rcx, rcx
0x1801cd9f4  jz      short loc_1801CD9FC
0x1801cd9f6  call    cs:__imp_MpConfigClose
0x1801cd9fc  cmp     edi, 4
0x1801cd9ff  jnb     short loc_1801CDA08
0x1801cda01  mov     edi, 4
0x1801cda06  jmp     short loc_1801CDA12
0x1801cda08  mov     eax, 20h ; ' '
0x1801cda0d  cmp     edi, eax
0x1801cda0f  cmova   edi, eax
0x1801cda12  mov     edx, edi
0x1801cda14  lea     rcx, aMprtpAsyncwatc; "MpRTP_AsyncWatcherNormalPriorityThreadC"...
0x1801cda1b  call    MpLookupMiscConfig
0x1801cda20  mov     [r14], eax
0x1801cda23  lea     rbx, WPP_GLOBAL_Control
0x1801cda2a  cmp     eax, edi
0x1801cda2c  jz      short loc_1801CDA5C
0x1801cda2e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cda35  cmp     rcx, rbx
0x1801cda38  jz      short loc_1801CDA5C
0x1801cda3a  test    byte ptr [rcx+1Ch], 2
0x1801cda3e  jz      short loc_1801CDA5C
0x1801cda40  mov     rcx, [rcx+10h]
0x1801cda44  lea     r8, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids
0x1801cda4b  mov     edx, 0Bh
0x1801cda50  mov     dword ptr [rsp+80h+var_60], eax
0x1801cda54  mov     r9d, edi
0x1801cda57  call    WPP_SF_Dd
0x1801cda5c  xor     edx, edx
0x1801cda5e  lea     rcx, aMprtpAsyncwatc_0; "MpRTP_AsyncWatcherVeryLowPriorityThread"...
0x1801cda65  call    MpLookupMiscConfig
0x1801cda6a  mov     [rsi], eax
0x1801cda6c  test    eax, eax
0x1801cda6e  jz      short loc_1801CDA9E
0x1801cda70  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cda77  cmp     rcx, rbx
0x1801cda7a  jz      short loc_1801CDACE
0x1801cda7c  test    byte ptr [rcx+1Ch], 2
0x1801cda80  jz      short loc_1801CDAA5
0x1801cda82  mov     rcx, [rcx+10h]
0x1801cda86  lea     r8, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids
0x1801cda8d  mov     edx, 0Ch
0x1801cda92  mov     dword ptr [rsp+80h+var_60], eax
0x1801cda96  xor     r9d, r9d
0x1801cda99  call    WPP_SF_Dd
0x1801cda9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1801cdaa5  cmp     rcx, rbx
0x1801cdaa8  jz      short loc_1801CDACE
0x1801cdaaa  test    byte ptr [rcx+1Ch], 4
0x1801cdaae  jz      short loc_1801CDACE
0x1801cdab0  mov     eax, [rsi]
0x1801cdab2  lea     r8, WPP_d35c89b3c91e3489af9e88b19891e994_Traceguids
0x1801cdab9  mov     r9d, [r14]
0x1801cdabc  mov     edx, 0Dh
0x1801cdac1  mov     rcx, [rcx+10h]
0x1801cdac5  mov     dword ptr [rsp+80h+var_60], eax
0x1801cdac9  call    WPP_SF_Dd
0x1801cdace  mov     rcx, [rbp+var_8]
0x1801cdad2  xor     rcx, rsp; StackCookie
0x1801cdad5  call    __security_check_cookie
0x1801cdada  lea     r11, [rsp+80h+var_s0]
0x1801cdae2  mov     rbx, [r11+20h]
0x1801cdae6  mov     rsi, [r11+38h]
0x1801cdaea  mov     rsp, r11
0x1801cdaed  pop     r14
0x1801cdaef  pop     rdi
0x1801cdaf0  pop     rbp
0x1801cdaf1  retn
```
