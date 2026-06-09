# RealtimeProtection::CDlpSyncWatcher::GetWorkerThreadsCount(ulong &,ulong &)

- ea: `0x18015e6e0`
- end: `0x18015e8c1`
- name: `?GetWorkerThreadsCount@CDlpSyncWatcher@RealtimeProtection@@EEAAXAEAK0@Z`
- size: `481`
- prototype: `void __fastcall(RealtimeProtection::CDlpSyncWatcher *__hidden this, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180046d10`
- `0x180087900`
- `0x180105db0`
- `0x18010cb40`
- `0x18015e6e0`

## import_xrefs

- `MpClient!MpConfigGetValue` at `0x18015e77d`
- `MpClient!MpConfigGetValue` at `0x18015e77d`
- `MpClient!MpConfigClose` at `0x18015e897`
- `MpClient!MpConfigClose` at `0x18015e897`
- `MpClient!MpConfigOpen` at `0x18015e740`
- `MpClient!MpConfigOpen` at `0x18015e740`
- `KERNEL32!GetSystemInfo` at `0x18015e71f`
- `KERNEL32!GetSystemInfo` at `0x18015e71f`

## string_xrefs

- `0x18015e768`: `DlpSyncThreadNumberFactorInPercent`
- `0x18015e7cf`: `MpRTP_FileWatcherNormalPriorityThreadCount`
- `0x18015e81c`: `MpRTP_FileWatcherVeryLowPriorityThreadCount`

## pseudocode

```c
void __fastcall RealtimeProtection::CDlpSyncWatcher::GetWorkerThreadsCount(
        RealtimeProtection::CDlpSyncWatcher *this,
        unsigned int *a2,
        unsigned int *a3)
{
  int v5; // ebx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  unsigned int IsVistaOrGreater; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  PVOID *v16; // rcx
  int v17; // [rsp+30h] [rbp-50h] BYREF
  int v18; // [rsp+34h] [rbp-4Ch] BYREF
  int v19; // [rsp+38h] [rbp-48h] BYREF
  __int64 v20; // [rsp+40h] [rbp-40h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-38h] BYREF

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  v5 = 200;
  v20 = 0;
  v17 = 200;
  if ( (int)MpConfigOpen(L"Features", &v20) < 0
    || (v19 = 1,
        v18 = 4,
        (int)((__int64 (__fastcall *)(__int64, const wchar_t *, int *, int *, int *, _QWORD))MpConfigGetValue)(
               v20,
               L"DlpSyncThreadNumberFactorInPercent",
               &v19,
               &v18,
               &v17,
               0) >= 0) )
  {
    v5 = v17;
  }
  else
  {
    v17 = 200;
  }
  v6 = v5 * (SystemInfo.dwNumberOfProcessors + 1);
  v7 = 8;
  if ( (unsigned int)v6 / 0x64 >= 8 )
  {
    v7 = (unsigned int)v6 / 0x64;
    if ( (unsigned int)v6 / 0x64 > 0x40 )
      v7 = 64;
  }
  IsVistaOrGreater = MpIsVistaOrGreater(v6);
  if ( IsVistaOrGreater )
  {
    *a2 = v7 - 2;
    IsVistaOrGreater = 2;
  }
  else
  {
    *a2 = v7;
  }
  *a3 = IsVistaOrGreater;
  v9 = *a2;
  v10 = MpLookupMiscConfig(L"MpRTP_FileWatcherNormalPriorityThreadCount", *a2);
  *a2 = v10;
  if ( v10 != v9 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids, v9, v10);
  v11 = *a3;
  v12 = MpLookupMiscConfig(L"MpRTP_FileWatcherVeryLowPriorityThreadCount", *a3);
  *a3 = v12;
  if ( v12 == v11 )
    goto LABEL_19;
  v16 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_23;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids, v11, v12);
LABEL_19:
    v16 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
    WPP_SF_Dd(v16[2], 21, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids, *a2, *a3);
LABEL_23:
  if ( v20 )
    MpConfigClose(v20, v13, v14, v15);
}

```

## disassembly

```asm
0x18015e6e0  mov     [rsp-18h+arg_0], rbx
0x18015e6e5  mov     [rsp-18h+arg_18], rsi
0x18015e6ea  push    rbp
0x18015e6eb  push    rdi
0x18015e6ec  push    r14
0x18015e6ee  mov     rbp, rsp
0x18015e6f1  sub     rsp, 80h
0x18015e6f8  mov     rax, cs:__security_cookie
0x18015e6ff  xor     rax, rsp
0x18015e702  mov     [rbp+var_8], rax
0x18015e706  xorps   xmm0, xmm0
0x18015e709  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18015e70d  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18015e711  mov     rsi, r8
0x18015e714  mov     rdi, rdx
0x18015e717  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18015e71b  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18015e71f  call    cs:__imp_GetSystemInfo
0x18015e725  mov     ebx, 0C8h
0x18015e72a  mov     [rbp+var_40], 0
0x18015e732  lea     rdx, [rbp+var_40]
0x18015e736  mov     [rbp+var_50], ebx
0x18015e739  lea     rcx, aFeatures_0; "Features"
0x18015e740  call    cs:__imp_MpConfigOpen
0x18015e746  test    eax, eax
0x18015e748  js      short loc_18015E78C
0x18015e74a  mov     rcx, [rbp+var_40]
0x18015e74e  lea     rax, [rbp+var_50]
0x18015e752  mov     [rsp+80h+var_58], 0
0x18015e75b  lea     r9, [rbp+var_4C]
0x18015e75f  lea     r8, [rbp+var_48]
0x18015e763  mov     [rsp+80h+var_60], rax
0x18015e768  lea     rdx, aDlpsyncthreadn; "DlpSyncThreadNumberFactorInPercent"
0x18015e76f  mov     [rbp+var_48], 1
0x18015e776  mov     [rbp+var_4C], 4
0x18015e77d  call    cs:__imp_MpConfigGetValue
0x18015e783  test    eax, eax
0x18015e785  jns     short loc_18015E78C
0x18015e787  mov     [rbp+var_50], ebx
0x18015e78a  jmp     short loc_18015E78F
0x18015e78c  mov     ebx, [rbp+var_50]
0x18015e78f  mov     ecx, [rbp+SystemInfo.dwNumberOfProcessors]
0x18015e792  mov     eax, 51EB851Fh
0x18015e797  inc     ecx
0x18015e799  imul    ecx, ebx
0x18015e79c  mov     ebx, 8
0x18015e7a1  mul     ecx
0x18015e7a3  shr     edx, 5
0x18015e7a6  cmp     edx, ebx
0x18015e7a8  jb      short loc_18015E7B6
0x18015e7aa  mov     eax, 40h ; '@'
0x18015e7af  mov     ebx, edx
0x18015e7b1  cmp     edx, eax
0x18015e7b3  cmova   ebx, eax
0x18015e7b6  call    MpIsVistaOrGreater
0x18015e7bb  test    eax, eax
0x18015e7bd  jnz     short loc_18015E7C3
0x18015e7bf  mov     [rdi], ebx
0x18015e7c1  jmp     short loc_18015E7CD
0x18015e7c3  lea     eax, [rbx-2]
0x18015e7c6  mov     [rdi], eax
0x18015e7c8  mov     eax, 2
0x18015e7cd  mov     [rsi], eax
0x18015e7cf  lea     rcx, aMprtpFilewatch_0; "MpRTP_FileWatcherNormalPriorityThreadCo"...
0x18015e7d6  mov     ebx, [rdi]
0x18015e7d8  mov     edx, ebx
0x18015e7da  call    MpLookupMiscConfig
0x18015e7df  mov     [rdi], eax
0x18015e7e1  lea     r14, WPP_GLOBAL_Control
0x18015e7e8  cmp     eax, ebx
0x18015e7ea  jz      short loc_18015E81A
0x18015e7ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18015e7f3  cmp     rcx, r14
0x18015e7f6  jz      short loc_18015E81A
0x18015e7f8  test    byte ptr [rcx+1Ch], 2
0x18015e7fc  jz      short loc_18015E81A
0x18015e7fe  mov     rcx, [rcx+10h]
0x18015e802  lea     r8, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids
0x18015e809  mov     edx, 13h
0x18015e80e  mov     dword ptr [rsp+80h+var_60], eax
0x18015e812  mov     r9d, ebx
0x18015e815  call    WPP_SF_Dd
0x18015e81a  mov     ebx, [rsi]
0x18015e81c  lea     rcx, aMprtpFilewatch; "MpRTP_FileWatcherVeryLowPriorityThreadC"...
0x18015e823  mov     edx, ebx
0x18015e825  call    MpLookupMiscConfig
0x18015e82a  mov     [rsi], eax
0x18015e82c  cmp     eax, ebx
0x18015e82e  jz      short loc_18015E85E
0x18015e830  mov     rcx, cs:WPP_GLOBAL_Control
0x18015e837  cmp     rcx, r14
0x18015e83a  jz      short loc_18015E88E
0x18015e83c  test    byte ptr [rcx+1Ch], 2
0x18015e840  jz      short loc_18015E865
0x18015e842  mov     rcx, [rcx+10h]
0x18015e846  lea     r8, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids
0x18015e84d  mov     edx, 14h
0x18015e852  mov     dword ptr [rsp+80h+var_60], eax
0x18015e856  mov     r9d, ebx
0x18015e859  call    WPP_SF_Dd
0x18015e85e  mov     rcx, cs:WPP_GLOBAL_Control
0x18015e865  cmp     rcx, r14
0x18015e868  jz      short loc_18015E88E
0x18015e86a  test    byte ptr [rcx+1Ch], 4
0x18015e86e  jz      short loc_18015E88E
0x18015e870  mov     eax, [rsi]
0x18015e872  lea     r8, WPP_742f2f96c3793b6ec1a2630691659419_Traceguids
0x18015e879  mov     r9d, [rdi]
0x18015e87c  mov     edx, 15h
0x18015e881  mov     rcx, [rcx+10h]
0x18015e885  mov     dword ptr [rsp+80h+var_60], eax
0x18015e889  call    WPP_SF_Dd
0x18015e88e  mov     rcx, [rbp+var_40]
0x18015e892  test    rcx, rcx
0x18015e895  jz      short loc_18015E89D
0x18015e897  call    cs:__imp_MpConfigClose
0x18015e89d  mov     rcx, [rbp+var_8]
0x18015e8a1  xor     rcx, rsp; StackCookie
0x18015e8a4  call    __security_check_cookie
0x18015e8a9  lea     r11, [rsp+80h+var_s0]
0x18015e8b1  mov     rbx, [r11+20h]
0x18015e8b5  mov     rsi, [r11+38h]
0x18015e8b9  mov     rsp, r11
0x18015e8bc  pop     r14
0x18015e8be  pop     rdi
0x18015e8bf  pop     rbp
0x18015e8c0  retn
```
