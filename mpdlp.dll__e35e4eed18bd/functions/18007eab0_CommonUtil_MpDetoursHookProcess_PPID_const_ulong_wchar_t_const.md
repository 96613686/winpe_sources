# CommonUtil::MpDetoursHookProcess(PPID const &,ulong,wchar_t const *)

- ea: `0x18007eab0`
- end: `0x18007f0bc`
- name: `?MpDetoursHookProcess@CommonUtil@@YAJAEBUPPID@@KPEB_W@Z`
- size: `1548`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const struct PPID *, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800af07c`

## callees

- `0x180046d10`
- `0x18007eab0`
- `0x18007f0bc`
- `0x18007f2f8`
- `0x1800809d0`
- `0x180089510`
- `0x1800b60f0`
- `0x1800cc218`
- `0x1801018c4`
- `0x180105f50`
- `0x18010cb40`
- `0x180144c48`
- `0x18014df1c`
- `0x18022e038`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x18007ebc4`
- `MpClient!MpFreeMemory` at `0x18007ec22`
- `MpClient!MpFreeMemory` at `0x18007ecd9`
- `MpClient!MpFreeMemory` at `0x18007ed67`
- `MpClient!MpFreeMemory` at `0x18007ed75`
- `MpClient!MpFreeMemory` at `0x18007ee72`
- `MpClient!MpFreeMemory` at `0x18007ee80`
- `MpClient!MpFreeMemory` at `0x18007f070`
- `MpClient!MpFreeMemory` at `0x18007f07e`
- `MpClient!MpFreeMemory` at `0x18007ebc4`
- `MpClient!MpFreeMemory` at `0x18007ec22`
- `MpClient!MpFreeMemory` at `0x18007ecd9`
- `MpClient!MpFreeMemory` at `0x18007ed67`
- `MpClient!MpFreeMemory` at `0x18007ed75`
- `MpClient!MpFreeMemory` at `0x18007ee72`
- `MpClient!MpFreeMemory` at `0x18007ee80`
- `MpClient!MpFreeMemory` at `0x18007f070`
- `MpClient!MpFreeMemory` at `0x18007f07e`
- `KERNEL32!WaitForSingleObject` at `0x18007ef5f`
- `KERNEL32!WaitForSingleObject` at `0x18007ef5f`
- `KERNEL32!LoadLibraryW` at `0x18007ebdb`
- `KERNEL32!CloseHandle` at `0x18007eb6b`
- `KERNEL32!CloseHandle` at `0x18007ec31`
- `KERNEL32!CloseHandle` at `0x18007ed84`
- `KERNEL32!CloseHandle` at `0x18007ee8f`
- `KERNEL32!CloseHandle` at `0x18007f041`
- `KERNEL32!CloseHandle` at `0x18007f08d`
- `KERNEL32!CloseHandle` at `0x18007eb6b`
- `KERNEL32!CloseHandle` at `0x18007ec31`
- `KERNEL32!CloseHandle` at `0x18007ed84`
- `KERNEL32!CloseHandle` at `0x18007ee8f`
- `KERNEL32!CloseHandle` at `0x18007f041`
- `KERNEL32!CloseHandle` at `0x18007f08d`
- `KERNEL32!VirtualFreeEx` at `0x18007f062`
- `KERNEL32!VirtualFreeEx` at `0x18007f062`
- `KERNEL32!VirtualAllocEx` at `0x18007ed18`
- `KERNEL32!VirtualAllocEx` at `0x18007ed18`
- `KERNEL32!WriteProcessMemory` at `0x18007edc8`
- `KERNEL32!WriteProcessMemory` at `0x18007edc8`
- `KERNEL32!CreateRemoteThread` at `0x18007eebb`
- `KERNEL32!CreateRemoteThread` at `0x18007eebb`
- `KERNEL32!GetExitCodeThread` at `0x18007ef9f`
- `KERNEL32!GetExitCodeThread` at `0x18007ef9f`

## string_xrefs

- `0x18007eb78`: `MpDetours.dll`
- `0x18007ec87`: `MpDetours.dll`

## pseudocode

```c
__int64 __fastcall CommonUtil::MpDetoursHookProcess(
        CommonUtil *this,
        const struct PPID *a2,
        __int64 a3,
        const wchar_t *a4)
{
  void **v5; // rdx
  int v6; // eax
  const wchar_t *v7; // r8
  bool v8; // r9
  unsigned int v9; // ebx
  int MpFileFullNameFromService; // eax
  LPCVOID v12; // rbx
  _WORD *v13; // r15
  ULONG (__stdcall *v14)(PVOID); // r13
  int TargetProcessArch; // edi
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  _WORD *v18; // rdi
  unsigned __int16 v19; // r9
  int MpArchBasedFullNameFromService; // eax
  __int64 v21; // rax
  SIZE_T v22; // r12
  void *v23; // rax
  int LastFailure; // eax
  unsigned int v25; // esi
  char v26; // r14
  int v27; // eax
  _QWORD *v28; // rcx
  int v29; // r15d
  __int64 v30; // rdx
  HANDLE RemoteThread; // rax
  void *v32; // rsi
  PVOID *v33; // rcx
  DWORD v34; // eax
  unsigned int ExitCodeThread; // eax
  PVOID *v36; // rcx
  unsigned int flProtect; // [rsp+20h] [rbp-49h]
  DWORD dwMilliseconds; // [rsp+40h] [rbp-29h]
  _WORD *v39; // [rsp+48h] [rbp-21h] BYREF
  char v40[8]; // [rsp+50h] [rbp-19h] BYREF
  LPVOID *p_lpParameter; // [rsp+58h] [rbp-11h]
  HANDLE *p_hObject; // [rsp+60h] [rbp-9h]
  LPVOID lpParameter; // [rsp+68h] [rbp-1h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+7h] BYREF
  LPCVOID lpBuffer; // [rsp+78h] [rbp+Fh] BYREF
  SIZE_T NumberOfBytesWritten; // [rsp+80h] [rbp+17h] BYREF

  dwMilliseconds = (unsigned int)a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_df4475de42c930d043888ffd5b211355_Traceguids);
  v5 = (void **)*((unsigned int *)this + 2);
  hObject = 0;
  v6 = CommonUtil::UtilOpenProcessByPpid(
         (CommonUtil *)&hObject,
         v5,
         (unsigned int)this,
         (const struct _FILETIME *)0x2A,
         flProtect);
  v9 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DDD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
        (unsigned int)v6,
        *((_DWORD *)this + 2),
        *((_DWORD *)this + 2));
LABEL_8:
    if ( hObject )
      CloseHandle(hObject);
    return v9;
  }
  lpBuffer = 0;
  MpFileFullNameFromService = MpConfigUtils::GetMpFileFullNameFromService(
                                (MpConfigUtils *)&lpBuffer,
                                (wchar_t **)L"MpDetours.dll",
                                v7,
                                v8);
  v9 = MpFileFullNameFromService;
  if ( MpFileFullNameFromService < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
        (unsigned int)MpFileFullNameFromService);
    if ( lpBuffer )
      MpFreeMemory(lpBuffer);
    goto LABEL_8;
  }
  v12 = lpBuffer;
  v13 = lpBuffer;
  v14 = (ULONG (__stdcall *)(PVOID))LoadLibraryW;
  LOWORD(lpBuffer) = 0;
  TargetProcessArch = CommonUtil::GetTargetProcessArch(hObject);
  if ( TargetProcessArch < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    v17 = 54;
LABEL_21:
    WPP_SF_d(v16[2], v17, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, (unsigned int)TargetProcessArch);
LABEL_22:
    if ( v12 )
      MpFreeMemory(v12);
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)TargetProcessArch;
  }
  v39 = 0;
  v18 = 0;
  if ( (_WORD)lpBuffer == 332 )
  {
    lpBuffer = 0;
    TargetProcessArch = CommonUtil::MpDetoursGetLoadLibraryWAddress32(&lpBuffer);
    if ( TargetProcessArch < 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_22;
      v17 = 55;
      goto LABEL_21;
    }
    v14 = (ULONG (__stdcall *)(PVOID))lpBuffer;
    MpArchBasedFullNameFromService = MpConfigUtils::GetMpArchBasedFullNameFromService(
                                       (MpConfigUtils *)&v39,
                                       (wchar_t **)L"MpDetours.dll",
                                       (const wchar_t *)0x14C,
                                       v19);
    TargetProcessArch = MpArchBasedFullNameFromService;
    if ( MpArchBasedFullNameFromService < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          56,
          &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
          (unsigned int)MpArchBasedFullNameFromService);
      if ( v39 )
        MpFreeMemory(v39);
      goto LABEL_22;
    }
    v18 = v39;
    v13 = v39;
  }
  v21 = -1;
  do
    ++v21;
  while ( v13[v21] );
  v22 = 2 * v21 + 2;
  v23 = VirtualAllocEx(hObject, 0, v22, 0x3000u, 4u);
  lpParameter = v23;
  if ( !v23 )
  {
    LastFailure = HrGetLastFailure();
    v25 = LastFailure;
    if ( LastFailure < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
          (unsigned int)LastFailure);
LABEL_46:
      if ( v18 )
        MpFreeMemory(v18);
      if ( v12 )
        MpFreeMemory(v12);
      if ( hObject )
        CloseHandle(hObject);
      return v25;
    }
    v23 = lpParameter;
  }
  v40[0] = 0;
  p_lpParameter = &lpParameter;
  NumberOfBytesWritten = 0;
  p_hObject = &hObject;
  v26 = 0;
  if ( !WriteProcessMemory(hObject, v23, v13, v22, &NumberOfBytesWritten) )
  {
    v27 = HrGetLastFailure();
    v25 = v27;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
          (unsigned int)v27);
      CommonUtil::ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___::_ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___(v40);
      goto LABEL_46;
    }
  }
  if ( NumberOfBytesWritten != v22 )
  {
    v28 = WPP_GLOBAL_Control;
    v29 = -2147418113;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_65;
    v30 = 61;
LABEL_64:
    WPP_SF_d(v28[2], v30, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, (unsigned int)v29);
LABEL_65:
    CommonUtil::ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___::_ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___(v40);
    if ( v18 )
      MpFreeMemory(v18);
    if ( v12 )
      MpFreeMemory(v12);
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v29;
  }
  RemoteThread = CreateRemoteThread(hObject, 0, 0, v14, lpParameter, 0, 0);
  v32 = RemoteThread;
  v33 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, RemoteThread);
    v33 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v32 )
  {
    v29 = HrGetLastFailure();
    if ( v29 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_65;
      v30 = 63;
      goto LABEL_64;
    }
    v33 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 4) != 0 )
    WPP_SF_(v33[2], 64, &WPP_df4475de42c930d043888ffd5b211355_Traceguids);
  v34 = WaitForSingleObject(v32, dwMilliseconds);
  if ( v34 )
  {
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, v34);
      v36 = (PVOID *)WPP_GLOBAL_Control;
    }
    v26 = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_df4475de42c930d043888ffd5b211355_Traceguids, 0);
    LODWORD(lpBuffer) = 0;
    ExitCodeThread = GetExitCodeThread(v32, (LPDWORD)&lpBuffer);
    v36 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_98;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_df4475de42c930d043888ffd5b211355_Traceguids,
        ExitCodeThread,
        (_DWORD)lpBuffer);
      v36 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v36 != &WPP_GLOBAL_Control && (*((_BYTE *)v36 + 28) & 4) != 0 )
    WPP_SF_(v36[2], 68, &WPP_df4475de42c930d043888ffd5b211355_Traceguids);
LABEL_98:
  if ( v32 )
    CloseHandle(v32);
  if ( !v26 && lpParameter )
    VirtualFreeEx(hObject, lpParameter, 0, 0x8000u);
  if ( v18 )
    MpFreeMemory(v18);
  if ( v12 )
    MpFreeMemory(v12);
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x18007eab0  mov     [rsp-8+arg_10], rbx
0x18007eab5  push    rbp
0x18007eab6  push    rsi
0x18007eab7  push    rdi
0x18007eab8  push    r12
0x18007eaba  push    r13
0x18007eabc  push    r14
0x18007eabe  push    r15
0x18007eac0  lea     rbp, [rsp-27h]
0x18007eac5  sub     rsp, 90h
0x18007eacc  mov     rax, cs:__security_cookie
0x18007ead3  xor     rax, rsp
0x18007ead6  mov     [rbp+57h+var_38], rax
0x18007eada  mov     [rbp+57h+dwMilliseconds], edx
0x18007eadd  mov     rdi, rcx
0x18007eae0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eae7  lea     r14, WPP_GLOBAL_Control
0x18007eaee  lea     r12, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18007eaf5  cmp     rcx, r14
0x18007eaf8  jz      short loc_18007EB11
0x18007eafa  test    byte ptr [rcx+1Ch], 4
0x18007eafe  jz      short loc_18007EB11
0x18007eb00  mov     rcx, [rcx+10h]
0x18007eb04  mov     edx, 33h ; '3'
0x18007eb09  mov     r8, r12
0x18007eb0c  call    WPP_SF_
0x18007eb11  mov     edx, [rdi+8]; void **
0x18007eb14  lea     rcx, [rbp+57h+hObject]; this
0x18007eb18  xor     esi, esi
0x18007eb1a  mov     r8, rdi; unsigned int
0x18007eb1d  mov     [rbp+57h+hObject], rsi
0x18007eb21  lea     r9d, [rsi+2Ah]; struct _FILETIME *
0x18007eb25  call    ?UtilOpenProcessByPpid@CommonUtil@@YAJPEAPEAXKPEBU_FILETIME@@K@Z; CommonUtil::UtilOpenProcessByPpid(void * *,ulong,_FILETIME const *,ulong)
0x18007eb2a  mov     ebx, eax
0x18007eb2c  test    eax, eax
0x18007eb2e  jns     short loc_18007EB78
0x18007eb30  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb37  cmp     rcx, r14
0x18007eb3a  jz      short loc_18007EB62
0x18007eb3c  test    byte ptr [rcx+1Ch], 4
0x18007eb40  jz      short loc_18007EB62
0x18007eb42  mov     r9d, [rdi+8]
0x18007eb46  lea     edx, [rsi+34h]
0x18007eb49  mov     rcx, [rcx+10h]
0x18007eb4d  mov     r8, r12
0x18007eb50  mov     [rsp+0C0h+dwCreationFlags], r9d
0x18007eb55  mov     [rsp+0C0h+flProtect], r9d
0x18007eb5a  mov     r9d, eax
0x18007eb5d  call    WPP_SF_DDD
0x18007eb62  mov     rcx, [rbp+57h+hObject]; hObject
0x18007eb66  test    rcx, rcx
0x18007eb69  jz      short loc_18007EB71
0x18007eb6b  call    cs:__imp_CloseHandle
0x18007eb71  mov     eax, ebx
0x18007eb73  jmp     loc_18007F095
0x18007eb78  lea     rdx, aMpdetoursDll; "MpDetours.dll"
0x18007eb7f  mov     [rbp+57h+lpBuffer], rsi
0x18007eb83  lea     rcx, [rbp+57h+lpBuffer]; this
0x18007eb87  call    ?GetMpFileFullNameFromService@MpConfigUtils@@YAJPEAPEA_WPEB_W_N@Z; MpConfigUtils::GetMpFileFullNameFromService(wchar_t * *,wchar_t const *,bool)
0x18007eb8c  mov     ebx, eax
0x18007eb8e  test    eax, eax
0x18007eb90  jns     short loc_18007EBCC
0x18007eb92  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eb99  cmp     rcx, r14
0x18007eb9c  jz      short loc_18007EBBB
0x18007eb9e  mov     r14b, 1
0x18007eba1  test    [rcx+1Ch], r14b
0x18007eba5  jz      short loc_18007EBBB
0x18007eba7  mov     rcx, [rcx+10h]
0x18007ebab  mov     edx, 35h ; '5'
0x18007ebb0  mov     r9d, eax
0x18007ebb3  mov     r8, r12
0x18007ebb6  call    WPP_SF_d
0x18007ebbb  mov     rcx, [rbp+57h+lpBuffer]
0x18007ebbf  test    rcx, rcx
0x18007ebc2  jz      short loc_18007EB62
0x18007ebc4  call    cs:__imp_MpFreeMemory
0x18007ebca  jmp     short loc_18007EB62
0x18007ebcc  mov     rbx, [rbp+57h+lpBuffer]
0x18007ebd0  lea     rdx, [rbp+57h+lpBuffer]
0x18007ebd4  mov     rcx, [rbp+57h+hObject]; hProcess
0x18007ebd8  mov     r15, rbx
0x18007ebdb  mov     r13, cs:__imp_LoadLibraryW
0x18007ebe2  mov     word ptr [rbp+57h+lpBuffer], si
0x18007ebe6  call    CommonUtil__GetTargetProcessArch
0x18007ebeb  mov     edi, eax
0x18007ebed  test    eax, eax
0x18007ebef  jns     short loc_18007EC3E
0x18007ebf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ebf8  cmp     rcx, r14
0x18007ebfb  jz      short loc_18007EC1A
0x18007ebfd  mov     r14b, 1
0x18007ec00  test    [rcx+1Ch], r14b
0x18007ec04  jz      short loc_18007EC1A
0x18007ec06  mov     edx, 36h ; '6'
0x18007ec0b  mov     rcx, [rcx+10h]
0x18007ec0f  mov     r9d, edi
0x18007ec12  mov     r8, r12
0x18007ec15  call    WPP_SF_d
0x18007ec1a  test    rbx, rbx
0x18007ec1d  jz      short loc_18007EC28
0x18007ec1f  mov     rcx, rbx
0x18007ec22  call    cs:__imp_MpFreeMemory
0x18007ec28  mov     rcx, [rbp+57h+hObject]; hObject
0x18007ec2c  test    rcx, rcx
0x18007ec2f  jz      short loc_18007EC37
0x18007ec31  call    cs:__imp_CloseHandle
0x18007ec37  mov     eax, edi
0x18007ec39  jmp     loc_18007F095
0x18007ec3e  mov     eax, 14Ch
0x18007ec43  mov     [rbp+57h+var_78], rsi
0x18007ec47  mov     rdi, rsi
0x18007ec4a  cmp     word ptr [rbp+57h+lpBuffer], ax
0x18007ec4e  jnz     loc_18007ECEB
0x18007ec54  lea     rcx, [rbp+57h+lpBuffer]
0x18007ec58  mov     [rbp+57h+lpBuffer], rsi
0x18007ec5c  call    CommonUtil__MpDetoursGetLoadLibraryWAddress32
0x18007ec61  mov     edi, eax
0x18007ec63  test    eax, eax
0x18007ec65  jns     short loc_18007EC83
0x18007ec67  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ec6e  cmp     rcx, r14
0x18007ec71  jz      short loc_18007EC1A
0x18007ec73  mov     r14b, 1
0x18007ec76  test    [rcx+1Ch], r14b
0x18007ec7a  jz      short loc_18007EC1A
0x18007ec7c  mov     edx, 37h ; '7'
0x18007ec81  jmp     short loc_18007EC0B
0x18007ec83  mov     r13, [rbp+57h+lpBuffer]
0x18007ec87  lea     rdx, aMpdetoursDll; "MpDetours.dll"
0x18007ec8e  mov     r8d, 14Ch; wchar_t *
0x18007ec94  lea     rcx, [rbp+57h+var_78]; this
0x18007ec98  call    ?GetMpArchBasedFullNameFromService@MpConfigUtils@@YAJPEAPEA_WPEB_WG@Z; MpConfigUtils::GetMpArchBasedFullNameFromService(wchar_t * *,wchar_t const *,ushort)
0x18007ec9d  mov     edi, eax
0x18007ec9f  test    eax, eax
0x18007eca1  jns     short loc_18007ECE4
0x18007eca3  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ecaa  cmp     rcx, r14
0x18007ecad  jz      short loc_18007ECCC
0x18007ecaf  mov     r14b, 1
0x18007ecb2  test    [rcx+1Ch], r14b
0x18007ecb6  jz      short loc_18007ECCC
0x18007ecb8  mov     rcx, [rcx+10h]
0x18007ecbc  mov     edx, 38h ; '8'
0x18007ecc1  mov     r9d, eax
0x18007ecc4  mov     r8, r12
0x18007ecc7  call    WPP_SF_d
0x18007eccc  mov     rcx, [rbp+57h+var_78]
0x18007ecd0  test    rcx, rcx
0x18007ecd3  jz      loc_18007EC1A
0x18007ecd9  call    cs:__imp_MpFreeMemory
0x18007ecdf  jmp     loc_18007EC1A
0x18007ece4  mov     rdi, [rbp+57h+var_78]
0x18007ece8  mov     r15, rdi
0x18007eceb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007ecef  inc     rax
0x18007ecf2  cmp     [r15+rax*2], si
0x18007ecf7  jnz     short loc_18007ECEF
0x18007ecf9  mov     rcx, [rbp+57h+hObject]; hProcess
0x18007ecfd  lea     r12, ds:2[rax*2]
0x18007ed05  mov     r8, r12; dwSize
0x18007ed08  mov     [rsp+0C0h+flProtect], 4; flProtect
0x18007ed10  mov     r9d, 3000h; flAllocationType
0x18007ed16  xor     edx, edx; lpAddress
0x18007ed18  call    cs:__imp_VirtualAllocEx
0x18007ed1e  mov     [rbp+57h+lpParameter], rax
0x18007ed22  test    rax, rax
0x18007ed25  jnz     short loc_18007ED97
0x18007ed27  call    HrGetLastFailure
0x18007ed2c  mov     esi, eax
0x18007ed2e  test    eax, eax
0x18007ed30  jns     short loc_18007ED91
0x18007ed32  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ed39  cmp     rcx, r14
0x18007ed3c  jz      short loc_18007ED5F
0x18007ed3e  mov     r14b, 1
0x18007ed41  test    [rcx+1Ch], r14b
0x18007ed45  jz      short loc_18007ED5F
0x18007ed47  mov     rcx, [rcx+10h]
0x18007ed4b  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18007ed52  mov     edx, 3Bh ; ';'
0x18007ed57  mov     r9d, eax
0x18007ed5a  call    WPP_SF_d
0x18007ed5f  test    rdi, rdi
0x18007ed62  jz      short loc_18007ED6D
0x18007ed64  mov     rcx, rdi
0x18007ed67  call    cs:__imp_MpFreeMemory
0x18007ed6d  test    rbx, rbx
0x18007ed70  jz      short loc_18007ED7B
0x18007ed72  mov     rcx, rbx
0x18007ed75  call    cs:__imp_MpFreeMemory
0x18007ed7b  mov     rcx, [rbp+57h+hObject]; hObject
0x18007ed7f  test    rcx, rcx
0x18007ed82  jz      short loc_18007ED8A
0x18007ed84  call    cs:__imp_CloseHandle
0x18007ed8a  mov     eax, esi
0x18007ed8c  jmp     loc_18007F095
0x18007ed91  mov     rax, [rbp+57h+lpParameter]
0x18007ed95  xor     esi, esi
0x18007ed97  lea     rcx, [rbp+57h+lpParameter]
0x18007ed9b  mov     [rbp+57h+var_70], sil
0x18007ed9f  mov     [rbp+57h+var_68], rcx
0x18007eda3  mov     r9, r12; nSize
0x18007eda6  lea     rcx, [rbp+57h+hObject]
0x18007edaa  mov     [rbp+57h+NumberOfBytesWritten], rsi
0x18007edae  mov     [rbp+57h+var_60], rcx
0x18007edb2  mov     r8, r15; lpBuffer
0x18007edb5  lea     rcx, [rbp+57h+NumberOfBytesWritten]
0x18007edb9  mov     rdx, rax; lpBaseAddress
0x18007edbc  mov     qword ptr [rsp+0C0h+flProtect], rcx; lpNumberOfBytesWritten
0x18007edc1  mov     r14b, sil
0x18007edc4  mov     rcx, [rbp+57h+hObject]; hProcess
0x18007edc8  call    cs:__imp_WriteProcessMemory
0x18007edce  test    eax, eax
0x18007edd0  jnz     short loc_18007EE21
0x18007edd2  call    HrGetLastFailure
0x18007edd7  mov     esi, eax
0x18007edd9  test    eax, eax
0x18007eddb  jns     short loc_18007EE1F
0x18007eddd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ede4  lea     r12, WPP_GLOBAL_Control
0x18007edeb  cmp     rcx, r12
0x18007edee  jz      short loc_18007EE11
0x18007edf0  mov     r14b, 1
0x18007edf3  test    [rcx+1Ch], r14b
0x18007edf7  jz      short loc_18007EE11
0x18007edf9  mov     rcx, [rcx+10h]
0x18007edfd  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18007ee04  mov     edx, 3Ch ; '<'
0x18007ee09  mov     r9d, eax
0x18007ee0c  call    WPP_SF_d
0x18007ee11  lea     rcx, [rbp+57h+var_70]
0x18007ee15  call    CommonUtil__ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048______ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___
0x18007ee1a  jmp     loc_18007ED5F
0x18007ee1f  xor     esi, esi
0x18007ee21  cmp     [rbp+57h+NumberOfBytesWritten], r12
0x18007ee25  jz      short loc_18007EE9D
0x18007ee27  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ee2e  lea     r12, WPP_GLOBAL_Control
0x18007ee35  mov     r15d, 8000FFFFh
0x18007ee3b  cmp     rcx, r12
0x18007ee3e  jz      short loc_18007EE61
0x18007ee40  mov     r14b, 1
0x18007ee43  test    [rcx+1Ch], r14b
0x18007ee47  jz      short loc_18007EE61
0x18007ee49  mov     edx, 3Dh ; '='
0x18007ee4e  mov     rcx, [rcx+10h]
0x18007ee52  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18007ee59  mov     r9d, r15d
0x18007ee5c  call    WPP_SF_d
0x18007ee61  lea     rcx, [rbp+57h+var_70]
0x18007ee65  call    CommonUtil__ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048______ScopeGuardImpl__lambda_b0b92aea7b95d93b91672d424efc3048___
0x18007ee6a  test    rdi, rdi
0x18007ee6d  jz      short loc_18007EE78
0x18007ee6f  mov     rcx, rdi
0x18007ee72  call    cs:__imp_MpFreeMemory
0x18007ee78  test    rbx, rbx
0x18007ee7b  jz      short loc_18007EE86
0x18007ee7d  mov     rcx, rbx
0x18007ee80  call    cs:__imp_MpFreeMemory
0x18007ee86  mov     rcx, [rbp+57h+hObject]; hObject
0x18007ee8a  test    rcx, rcx
0x18007ee8d  jz      short loc_18007EE95
0x18007ee8f  call    cs:__imp_CloseHandle
0x18007ee95  mov     eax, r15d
0x18007ee98  jmp     loc_18007F095
0x18007ee9d  mov     rax, [rbp+57h+lpParameter]
0x18007eea1  mov     r9, r13; lpStartAddress
0x18007eea4  mov     rcx, [rbp+57h+hObject]; hProcess
0x18007eea8  xor     r8d, r8d; dwStackSize
0x18007eeab  mov     [rsp+0C0h+lpThreadId], rsi; lpThreadId
0x18007eeb0  xor     edx, edx; lpThreadAttributes
0x18007eeb2  mov     [rsp+0C0h+dwCreationFlags], esi; dwCreationFlags
0x18007eeb6  mov     qword ptr [rsp+0C0h+flProtect], rax; lpParameter
0x18007eebb  call    cs:__imp_CreateRemoteThread
0x18007eec1  mov     rsi, rax
0x18007eec4  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eecb  lea     r12, WPP_GLOBAL_Control
0x18007eed2  cmp     rcx, r12
0x18007eed5  jz      short loc_18007EEFC
0x18007eed7  test    byte ptr [rcx+1Ch], 4
0x18007eedb  jz      short loc_18007EEFC
0x18007eedd  mov     rcx, [rcx+10h]
0x18007eee1  lea     r8, WPP_df4475de42c930d043888ffd5b211355_Traceguids
0x18007eee8  mov     edx, 3Eh ; '>'
0x18007eeed  mov     r9, rax
0x18007eef0  call    WPP_SF_q
0x18007eef5  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eefc  test    rsi, rsi
0x18007eeff  jnz     short loc_18007EF39
0x18007ef01  call    HrGetLastFailure
0x18007ef06  mov     r15d, eax
0x18007ef09  test    eax, eax
0x18007ef0b  jns     short loc_18007EF32
0x18007ef0d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ef14  cmp     rcx, r12
0x18007ef17  jz      loc_18007EE61
0x18007ef1d  mov     r14b, 1
0x18007ef20  test    [rcx+1Ch], r14b
0x18007ef24  jz      loc_18007EE61
  ... truncated ...
```
