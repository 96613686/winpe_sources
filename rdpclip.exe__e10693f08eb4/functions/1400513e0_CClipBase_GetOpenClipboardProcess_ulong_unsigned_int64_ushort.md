# CClipBase::GetOpenClipboardProcess(ulong *,unsigned __int64,ushort *)

- ea: `0x1400513e0`
- end: `0x140051657`
- name: `?GetOpenClipboardProcess@CClipBase@@AEAAJPEAK_KPEAG@Z`
- size: `631`
- prototype: `int(CClipBase *__hidden this, unsigned int *, unsigned __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x1400579e4`

## callees

- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x1400513e0`
- `0x14006b010`

## import_xrefs

- `USER32!GetWindowThreadProcessId` at `0x140051518`
- `USER32!GetWindowThreadProcessId` at `0x140051518`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005163f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14005163f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1400515d8`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1400515d8`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14005157b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14005157b`

## string_xrefs

- `0x14005142f`: `pdwProcessId`

## pseudocode

```c
__int64 __fastcall CClipBase::GetOpenClipboardProcess(
        __int64 (**this)(void),
        unsigned int *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  unsigned int v9; // ebx
  HWND v10; // rax
  unsigned int v11; // eax
  int v12; // edx
  const char *v13; // rcx
  unsigned int v14; // eax
  HANDLE v15; // rax
  void *v16; // rdi
  unsigned int v17; // eax
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF
  int v20; // [rsp+54h] [rbp+1Ch]

  v20 = HIDWORD(a3);
  dwProcessId = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 264;
    v8 = "pdwProcessId";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      -2147024809);
    return (unsigned int)-2147024809;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147024809;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 265;
    v8 = "pszFileName";
    goto LABEL_6;
  }
  v10 = (HWND)this[100]();
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 266;
    v13 = "hwnd";
LABEL_18:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      (unsigned int)&WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
      v11,
      (__int64)v13,
      -2147467259);
    return (unsigned int)-2147467259;
  }
  if ( !GetWindowThreadProcessId(v10, &dwProcessId) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        267,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v14,
        -2147467259);
    }
    return (unsigned int)-2147467259;
  }
  v15 = OpenProcess(0x410u, 0, dwProcessId);
  v16 = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)-2147467259;
    }
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    v12 = 268;
    v13 = "hProcess";
    goto LABEL_18;
  }
  if ( K32GetModuleFileNameExW(v15, 0, a4, 0x104u) )
  {
    v9 = 0;
    *a2 = dwProcessId;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        269,
        &WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids,
        v17,
        -2147467259);
    }
    v9 = -2147467259;
  }
  CloseHandle(v16);
  return v9;
}

```

## disassembly

```asm
0x1400513e0  mov     rax, rsp
0x1400513e3  mov     [rax+8], rbx
0x1400513e7  mov     [rax+10h], rsi
0x1400513eb  mov     [rax+18h], r8
0x1400513ef  push    rdi
0x1400513f0  sub     rsp, 30h
0x1400513f4  mov     dword ptr [rax+18h], 0
0x1400513fb  mov     rbx, r9
0x1400513fe  mov     rsi, rdx
0x140051401  test    rdx, rdx
0x140051404  jnz     short loc_140051467
0x140051406  mov     rcx, cs:WPP_GLOBAL_Control
0x14005140d  lea     rax, WPP_GLOBAL_Control
0x140051414  cmp     rcx, rax
0x140051417  jz      short loc_14005145D
0x140051419  test    byte ptr [rcx+1Ch], 8
0x14005141d  jz      short loc_14005145D
0x14005141f  cmp     byte ptr [rcx+19h], 2
0x140051423  jb      short loc_14005145D
0x140051425  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14005142a  mov     edx, 108h
0x14005142f  lea     rcx, aPdwprocessid; "pdwProcessId"
0x140051436  mov     [rsp+38h+var_10], 80070057h
0x14005143e  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051445  mov     [rsp+38h+var_18], rcx
0x14005144a  mov     r9d, eax
0x14005144d  mov     rcx, cs:WPP_GLOBAL_Control
0x140051454  mov     rcx, [rcx+10h]
0x140051458  call    WPP_SF_DsD
0x14005145d  mov     ebx, 80070057h
0x140051462  jmp     loc_140051645
0x140051467  test    rbx, rbx
0x14005146a  jnz     short loc_14005149E
0x14005146c  mov     rcx, cs:WPP_GLOBAL_Control
0x140051473  lea     rax, WPP_GLOBAL_Control
0x14005147a  cmp     rcx, rax
0x14005147d  jz      short loc_14005145D
0x14005147f  test    byte ptr [rcx+1Ch], 8
0x140051483  jz      short loc_14005145D
0x140051485  cmp     byte ptr [rcx+19h], 2
0x140051489  jb      short loc_14005145D
0x14005148b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051490  mov     edx, 109h
0x140051495  lea     rcx, aPszfilename; "pszFileName"
0x14005149c  jmp     short loc_140051436
0x14005149e  mov     rax, [rcx+320h]
0x1400514a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400514aa  test    rax, rax
0x1400514ad  jnz     short loc_140051510
0x1400514af  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514b6  lea     rax, WPP_GLOBAL_Control
0x1400514bd  cmp     rcx, rax
0x1400514c0  jz      short loc_140051506
0x1400514c2  test    byte ptr [rcx+1Ch], 8
0x1400514c6  jz      short loc_140051506
0x1400514c8  cmp     byte ptr [rcx+19h], 2
0x1400514cc  jb      short loc_140051506
0x1400514ce  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400514d3  mov     edx, 10Ah
0x1400514d8  lea     rcx, aHwnd; "hwnd"
0x1400514df  mov     [rsp+38h+var_10], 80004005h
0x1400514e7  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x1400514ee  mov     [rsp+38h+var_18], rcx
0x1400514f3  mov     r9d, eax
0x1400514f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400514fd  mov     rcx, [rcx+10h]
0x140051501  call    WPP_SF_DsD
0x140051506  mov     ebx, 80004005h
0x14005150b  jmp     loc_140051645
0x140051510  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x140051515  mov     rcx, rax; hWnd
0x140051518  call    cs:__imp_GetWindowThreadProcessId
0x14005151e  test    eax, eax
0x140051520  jnz     short loc_14005156F
0x140051522  mov     rcx, cs:WPP_GLOBAL_Control
0x140051529  lea     rax, WPP_GLOBAL_Control
0x140051530  cmp     rcx, rax
0x140051533  jz      short loc_140051506
0x140051535  test    byte ptr [rcx+1Ch], 8
0x140051539  jz      short loc_140051506
0x14005153b  cmp     byte ptr [rcx+19h], 2
0x14005153f  jb      short loc_140051506
0x140051541  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051546  mov     rcx, cs:WPP_GLOBAL_Control
0x14005154d  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051554  mov     edx, 10Bh
0x140051559  mov     dword ptr [rsp+38h+var_18], 80004005h
0x140051561  mov     r9d, eax
0x140051564  mov     rcx, [rcx+10h]
0x140051568  call    WPP_SF_Dd
0x14005156d  jmp     short loc_140051506
0x14005156f  mov     r8d, [rsp+38h+dwProcessId]; dwProcessId
0x140051574  xor     edx, edx; bInheritHandle
0x140051576  mov     ecx, 410h; dwDesiredAccess
0x14005157b  call    cs:__imp_OpenProcess
0x140051581  mov     rdi, rax
0x140051584  test    rax, rax
0x140051587  jnz     short loc_1400515CA
0x140051589  mov     rcx, cs:WPP_GLOBAL_Control
0x140051590  lea     rax, WPP_GLOBAL_Control
0x140051597  cmp     rcx, rax
0x14005159a  jz      loc_140051506
0x1400515a0  test    byte ptr [rcx+1Ch], 8
0x1400515a4  jz      loc_140051506
0x1400515aa  cmp     byte ptr [rcx+19h], 2
0x1400515ae  jb      loc_140051506
0x1400515b4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400515b9  mov     edx, 10Ch
0x1400515be  lea     rcx, aHprocess; "hProcess"
0x1400515c5  jmp     loc_1400514DF
0x1400515ca  mov     r9d, 104h; nSize
0x1400515d0  mov     r8, rbx; lpFilename
0x1400515d3  xor     edx, edx; hModule
0x1400515d5  mov     rcx, rdi; hProcess
0x1400515d8  call    cs:__imp_K32GetModuleFileNameExW
0x1400515de  test    eax, eax
0x1400515e0  jnz     short loc_140051634
0x1400515e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400515e9  lea     rax, WPP_GLOBAL_Control
0x1400515f0  cmp     rcx, rax
0x1400515f3  jz      short loc_14005162D
0x1400515f5  test    byte ptr [rcx+1Ch], 8
0x1400515f9  jz      short loc_14005162D
0x1400515fb  cmp     byte ptr [rcx+19h], 2
0x1400515ff  jb      short loc_14005162D
0x140051601  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140051606  mov     rcx, cs:WPP_GLOBAL_Control
0x14005160d  lea     r8, WPP_a1edf116bee93c7d211c7ed564dae13f_Traceguids
0x140051614  mov     edx, 10Dh
0x140051619  mov     dword ptr [rsp+38h+var_18], 80004005h
0x140051621  mov     r9d, eax
0x140051624  mov     rcx, [rcx+10h]
0x140051628  call    WPP_SF_Dd
0x14005162d  mov     ebx, 80004005h
0x140051632  jmp     short loc_14005163C
0x140051634  mov     eax, [rsp+38h+dwProcessId]
0x140051638  xor     ebx, ebx
0x14005163a  mov     [rsi], eax
0x14005163c  mov     rcx, rdi; hObject
0x14005163f  call    cs:__imp_CloseHandle
0x140051645  mov     rsi, [rsp+38h+arg_8]
0x14005164a  mov     eax, ebx
0x14005164c  mov     rbx, [rsp+38h+arg_0]
0x140051651  add     rsp, 30h
0x140051655  pop     rdi
0x140051656  retn
```
