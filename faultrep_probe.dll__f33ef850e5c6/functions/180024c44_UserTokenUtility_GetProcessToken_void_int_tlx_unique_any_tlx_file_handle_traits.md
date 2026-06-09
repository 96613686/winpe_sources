# UserTokenUtility::GetProcessToken(void *,int,tlx::unique_any<tlx::file_handle_traits> *)

- ea: `0x180024c44`
- end: `0x180024df2`
- name: `?GetProcessToken@UserTokenUtility@@SAJPEAXHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18000e7c0`

## callees

- `0x180002890`
- `0x180007704`
- `0x180009ed8`
- `0x180009f00`
- `0x180024c44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024cc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180024cc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024cd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024da4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024cad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024d47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024da4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024dce`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall UserTokenUtility::GetProcessToken(HANDLE ProcessHandle, __int64 a2, void **a3)
{
  void *v5; // rcx
  void **v6; // rax
  signed int LastError; // eax
  unsigned int v8; // ebx
  void *v9; // rcx
  unsigned __int64 v10; // rdx
  HANDLE v11; // r8
  HANDLE v12; // rax
  HANDLE v14; // [rsp+20h] [rbp-30h] BYREF
  HANDLE v15; // [rsp+28h] [rbp-28h]
  HANDLE hObject; // [rsp+30h] [rbp-20h]
  __int64 v17; // [rsp+38h] [rbp-18h]
  int v18; // [rsp+40h] [rbp-10h]

  v14 = 0;
  v15 = 0;
  hObject = 0;
  v17 = 0;
  v18 = 0;
  if ( ProcessHandle && a3 )
  {
    v5 = *a3;
    *a3 = 0;
    if ( (unsigned __int64)v5 + 1 > 1 )
      CloseHandle(v5);
    v6 = (void **)tlx::replace<tlx::file_handle_traits>(&v14);
    if ( OpenProcessToken(ProcessHandle, 0x4Fu, v6) )
    {
      v9 = *a3;
      v10 = (unsigned __int64)*a3 + 1;
      v11 = v15;
      if ( (unsigned __int64)v15 + 1 <= 1 )
      {
        v12 = v14;
        v14 = 0;
        *a3 = v12;
      }
      else
      {
        v15 = 0;
        *a3 = v11;
      }
      if ( v10 > 1 )
        CloseHandle(v9);
      v8 = 0;
    }
    else
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids, v8);
    }
  }
  else
  {
    v8 = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( (unsigned __int64)v15 + 1 > 1 )
    CloseHandle(v15);
  if ( (unsigned __int64)v14 + 1 > 1 )
    CloseHandle(v14);
  return v8;
}

```

## disassembly

```asm
0x180024c44  mov     [rsp-8+arg_8], rbx
0x180024c49  mov     [rsp-8+arg_18], rdi
0x180024c4e  push    rbp
0x180024c4f  mov     rbp, rsp
0x180024c52  sub     rsp, 50h
0x180024c56  mov     rax, cs:__security_cookie
0x180024c5d  xor     rax, rsp
0x180024c60  mov     [rbp+var_8], rax
0x180024c64  mov     rbx, r8
0x180024c67  mov     rdi, rcx
0x180024c6a  mov     [rbp+var_30], 0
0x180024c72  mov     [rbp+var_28], 0
0x180024c7a  mov     [rbp+hObject], 0
0x180024c82  xor     eax, eax
0x180024c84  mov     [rbp+var_18], rax
0x180024c88  mov     [rbp+var_10], eax
0x180024c8b  test    rcx, rcx
0x180024c8e  jz      loc_180024D62
0x180024c94  test    rbx, rbx
0x180024c97  jz      loc_180024D62
0x180024c9d  mov     rcx, [r8]; hObject
0x180024ca0  mov     [r8], rax
0x180024ca3  lea     rax, [rcx+1]
0x180024ca7  cmp     rax, 1
0x180024cab  jbe     short loc_180024CB3
0x180024cad  call    cs:__imp_CloseHandle
0x180024cb3  lea     rcx, [rbp+var_30]
0x180024cb7  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x180024cbc  mov     r8, rax; TokenHandle
0x180024cbf  mov     edx, 4Fh ; 'O'; DesiredAccess
0x180024cc4  mov     rcx, rdi; ProcessHandle
0x180024cc7  call    cs:__imp_OpenProcessToken
0x180024ccd  test    eax, eax
0x180024ccf  jnz     short loc_180024D21
0x180024cd1  call    cs:__imp_GetLastError
0x180024cd7  mov     ebx, eax
0x180024cd9  test    eax, eax
0x180024cdb  jle     short loc_180024CE6
0x180024cdd  movzx   ebx, ax
0x180024ce0  or      ebx, 80070000h
0x180024ce6  lea     rax, WPP_GLOBAL_Control
0x180024ced  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cf4  cmp     rcx, rax
0x180024cf7  jz      loc_180024D96
0x180024cfd  test    byte ptr [rcx+1Ch], 1
0x180024d01  jz      loc_180024D96
0x180024d07  mov     edx, 11h
0x180024d0c  mov     r9d, ebx
0x180024d0f  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180024d16  mov     rcx, [rcx+10h]
0x180024d1a  call    WPP_SF_d
0x180024d1f  jmp     short loc_180024D96
0x180024d21  mov     rcx, [rbx]; hObject
0x180024d24  lea     rdx, [rcx+1]
0x180024d28  mov     r8, [rbp+var_28]
0x180024d2c  lea     rax, [r8+1]
0x180024d30  cmp     rax, 1
0x180024d34  jbe     short loc_180024D51
0x180024d36  mov     [rbp+var_28], 0
0x180024d3e  mov     [rbx], r8
0x180024d41  cmp     rdx, 1
0x180024d45  jbe     short loc_180024D4D
0x180024d47  call    cs:__imp_CloseHandle
0x180024d4d  xor     ebx, ebx
0x180024d4f  jmp     short loc_180024D96
0x180024d51  mov     rax, [rbp+var_30]
0x180024d55  mov     [rbp+var_30], 0
0x180024d5d  mov     [rbx], rax
0x180024d60  jmp     short loc_180024D41
0x180024d62  mov     ebx, 80070057h
0x180024d67  lea     rax, WPP_GLOBAL_Control
0x180024d6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d75  cmp     rcx, rax
0x180024d78  jz      short loc_180024D96
0x180024d7a  test    byte ptr [rcx+1Ch], 1
0x180024d7e  jz      short loc_180024D96
0x180024d80  mov     edx, 10h
0x180024d85  lea     r8, WPP_a23aa53e43603591c4e5d6b4fc0b4a04_Traceguids
0x180024d8c  mov     rcx, [rcx+10h]
0x180024d90  call    WPP_SF_
0x180024d95  nop
0x180024d96  mov     rcx, [rbp+hObject]; hObject
0x180024d9a  lea     rax, [rcx+1]
0x180024d9e  cmp     rax, 1
0x180024da2  jbe     short loc_180024DAB
0x180024da4  call    cs:__imp_CloseHandle
0x180024daa  nop
0x180024dab  mov     rcx, [rbp+var_28]; hObject
0x180024daf  lea     rax, [rcx+1]
0x180024db3  cmp     rax, 1
0x180024db7  jbe     short loc_180024DC0
0x180024db9  call    cs:__imp_CloseHandle
0x180024dbf  nop
0x180024dc0  mov     rcx, [rbp+var_30]; hObject
0x180024dc4  lea     rdx, [rcx+1]
0x180024dc8  cmp     rdx, 1
0x180024dcc  jbe     short loc_180024DD4
0x180024dce  call    cs:__imp_CloseHandle
0x180024dd4  mov     eax, ebx
0x180024dd6  mov     rcx, [rbp+var_8]
0x180024dda  xor     rcx, rsp; StackCookie
0x180024ddd  call    __security_check_cookie
0x180024de2  mov     rbx, [rsp+50h+arg_8]
0x180024de7  mov     rdi, [rsp+50h+arg_18]
0x180024dec  add     rsp, 50h
0x180024df0  pop     rbp
0x180024df1  retn
```
