# CFileCollection::DuplicateHandleFromClient(ulong,void *,ulong,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x18000a7c4`
- end: `0x18000a99b`
- name: `?DuplicateHandleFromClient@CFileCollection@@QEAAJKPEAXKPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(__int64, DWORD, void *, __int64, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008030`
- `0x180008490`

## callees

- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x18000a7c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000a8f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a92b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a895`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a92b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a7f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a988`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a921`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000a921`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a975`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000a975`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a830`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000a830`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a882`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000a882`

## pseudocode

```c
__int64 __fastcall CFileCollection::DuplicateHandleFromClient(__int64 a1, DWORD a2, void *a3, __int64 a4, void **a5)
{
  void *v7; // rcx
  unsigned int v9; // ebx
  HANDLE v10; // rdi
  signed int v11; // eax
  HANDLE *v12; // rbx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax

  v7 = *a5;
  *a5 = 0;
  if ( (unsigned __int64)v7 + 1 > 1 )
    CloseHandle(v7);
  if ( a2 )
  {
    v9 = CoImpersonateClient();
    if ( (v9 & 0x80000000) == 0 )
    {
      v10 = OpenProcess(0x40u, 0, a2);
      if ( (unsigned __int64)v10 + 1 > 1 )
      {
        v12 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(a5);
        CurrentProcess = GetCurrentProcess();
        if ( DuplicateHandle(v10, a3, CurrentProcess, v12, 0x100000u, 0, 0) )
        {
          v9 = 0;
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids, v9);
        }
      }
      else
      {
        v11 = GetLastError();
        v9 = v11;
        if ( v11 > 0 )
          v9 = (unsigned __int16)v11 | 0x80070000;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids, a2, v9);
      }
      CoRevertToSelf();
      if ( (unsigned __int64)v10 + 1 > 1 )
        CloseHandle(v10);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids, v9);
    }
    return v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000a7c4  push    rbx
0x18000a7c6  push    rbp
0x18000a7c7  push    rsi
0x18000a7c8  push    rdi
0x18000a7c9  push    r14
0x18000a7cb  sub     rsp, 40h
0x18000a7cf  mov     r14, [rsp+68h+arg_20]
0x18000a7d7  mov     rbp, r8
0x18000a7da  mov     esi, edx
0x18000a7dc  mov     rcx, [r14]; hObject
0x18000a7df  mov     qword ptr [r14], 0
0x18000a7e6  lea     rax, [rcx+1]
0x18000a7ea  cmp     rax, 1
0x18000a7ee  jbe     short loc_18000A7F6
0x18000a7f0  call    cs:__imp_CloseHandle
0x18000a7f6  test    esi, esi
0x18000a7f8  jnz     short loc_18000A830
0x18000a7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a801  lea     rax, WPP_GLOBAL_Control
0x18000a808  cmp     rcx, rax
0x18000a80b  jz      short loc_18000A826
0x18000a80d  test    byte ptr [rcx+1Ch], 1
0x18000a811  jz      short loc_18000A826
0x18000a813  mov     rcx, [rcx+10h]
0x18000a817  lea     edx, [rsi+0Eh]
0x18000a81a  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a821  call    WPP_SF_
0x18000a826  mov     eax, 80070057h
0x18000a82b  jmp     loc_18000A990
0x18000a830  call    cs:__imp_CoImpersonateClient
0x18000a836  mov     ebx, eax
0x18000a838  test    eax, eax
0x18000a83a  jns     short loc_18000A87A
0x18000a83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a843  lea     rax, WPP_GLOBAL_Control
0x18000a84a  cmp     rcx, rax
0x18000a84d  jz      loc_18000A98E
0x18000a853  test    byte ptr [rcx+1Ch], 8
0x18000a857  jz      loc_18000A98E
0x18000a85d  mov     rcx, [rcx+10h]
0x18000a861  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a868  mov     edx, 0Fh
0x18000a86d  mov     r9d, ebx
0x18000a870  call    WPP_SF_d
0x18000a875  jmp     loc_18000A98E
0x18000a87a  xor     edx, edx; bInheritHandle
0x18000a87c  mov     r8d, esi; dwProcessId
0x18000a87f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18000a882  call    cs:__imp_OpenProcess
0x18000a888  mov     rdi, rax
0x18000a88b  lea     rcx, [rax+1]
0x18000a88f  cmp     rcx, 1
0x18000a893  ja      short loc_18000A8EC
0x18000a895  call    cs:__imp_GetLastError
0x18000a89b  mov     ebx, eax
0x18000a89d  test    eax, eax
0x18000a89f  jle     short loc_18000A8AA
0x18000a8a1  movzx   ebx, ax
0x18000a8a4  or      ebx, 80070000h
0x18000a8aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8b1  lea     rax, WPP_GLOBAL_Control
0x18000a8b8  cmp     rcx, rax
0x18000a8bb  jz      loc_18000A975
0x18000a8c1  test    byte ptr [rcx+1Ch], 1
0x18000a8c5  jz      loc_18000A975
0x18000a8cb  mov     rcx, [rcx+10h]
0x18000a8cf  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a8d6  mov     edx, 10h
0x18000a8db  mov     [rsp+68h+dwDesiredAccess], ebx
0x18000a8df  mov     r9d, esi
0x18000a8e2  call    WPP_SF_Dd
0x18000a8e7  jmp     loc_18000A975
0x18000a8ec  mov     rcx, r14
0x18000a8ef  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x18000a8f4  mov     rbx, rax
0x18000a8f7  call    cs:__imp_GetCurrentProcess
0x18000a8fd  mov     [rsp+68h+dwOptions], 0; dwOptions
0x18000a905  mov     r9, rbx; lpTargetHandle
0x18000a908  mov     r8, rax; hTargetProcessHandle
0x18000a90b  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18000a913  mov     rdx, rbp; hSourceHandle
0x18000a916  mov     [rsp+68h+dwDesiredAccess], 100000h; dwDesiredAccess
0x18000a91e  mov     rcx, rdi; hSourceProcessHandle
0x18000a921  call    cs:__imp_DuplicateHandle
0x18000a927  test    eax, eax
0x18000a929  jnz     short loc_18000A973
0x18000a92b  call    cs:__imp_GetLastError
0x18000a931  mov     ebx, eax
0x18000a933  test    eax, eax
0x18000a935  jle     short loc_18000A940
0x18000a937  movzx   ebx, ax
0x18000a93a  or      ebx, 80070000h
0x18000a940  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a947  lea     rax, WPP_GLOBAL_Control
0x18000a94e  cmp     rcx, rax
0x18000a951  jz      short loc_18000A975
0x18000a953  test    byte ptr [rcx+1Ch], 1
0x18000a957  jz      short loc_18000A975
0x18000a959  mov     rcx, [rcx+10h]
0x18000a95d  lea     r8, WPP_5830178aa191323d89eeb6488c1e9d69_Traceguids
0x18000a964  mov     edx, 11h
0x18000a969  mov     r9d, ebx
0x18000a96c  call    WPP_SF_d
0x18000a971  jmp     short loc_18000A975
0x18000a973  xor     ebx, ebx
0x18000a975  call    cs:__imp_CoRevertToSelf
0x18000a97b  lea     rax, [rdi+1]
0x18000a97f  cmp     rax, 1
0x18000a983  jbe     short loc_18000A98E
0x18000a985  mov     rcx, rdi; hObject
0x18000a988  call    cs:__imp_CloseHandle
0x18000a98e  mov     eax, ebx
0x18000a990  add     rsp, 40h
0x18000a994  pop     r14
0x18000a996  pop     rdi
0x18000a997  pop     rsi
0x18000a998  pop     rbp
0x18000a999  pop     rbx
0x18000a99a  retn
```
