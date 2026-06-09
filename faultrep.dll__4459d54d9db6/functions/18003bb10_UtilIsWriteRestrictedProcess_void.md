# UtilIsWriteRestrictedProcess(void *)

- ea: `0x18003bb10`
- end: `0x18003bbd6`
- name: `?UtilIsWriteRestrictedProcess@@YA_NPEAX@Z`
- size: `198`
- prototype: `bool __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18000d8b4`

## callees

- `0x180009f00`
- `0x1800390e0`
- `0x18003bb10`
- `0x18003bbdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003bb3c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003bb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003bb86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bbc8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bb63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003bbc8`

## pseudocode

```c
bool __fastcall UtilIsWriteRestrictedProcess(HANDLE ProcessHandle)
{
  void **v2; // rax
  BOOL v3; // ebx
  void *v4; // rcx
  DWORD LastError; // eax
  bool v6; // bl
  void *v8; // [rsp+20h] [rbp-28h] BYREF
  void **v9; // [rsp+28h] [rbp-20h]
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF

  hObject = 0;
  v2 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v8, &hObject);
  v3 = OpenProcessToken(ProcessHandle, 2u, v2);
  if ( v8 )
  {
    v4 = *v9;
    *v9 = v8;
    if ( (unsigned __int64)v4 + 1 > 1 )
      CloseHandle(v4);
  }
  if ( v3 )
  {
    v6 = UtilIsWriteRestrictedToken(hObject);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_988ce82756cb3ec502560a762615dae0_Traceguids, LastError);
    }
    v6 = 0;
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return v6;
}

```

## disassembly

```asm
0x18003bb10  push    rbx
0x18003bb12  sub     rsp, 40h
0x18003bb16  mov     rbx, rcx
0x18003bb19  mov     [rsp+48h+hObject], 0
0x18003bb22  lea     rcx, [rsp+48h+var_28]
0x18003bb27  lea     rdx, [rsp+48h+hObject]
0x18003bb2c  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003bb31  mov     r8, rax; TokenHandle
0x18003bb34  mov     edx, 2; DesiredAccess
0x18003bb39  mov     rcx, rbx; ProcessHandle
0x18003bb3c  call    cs:__imp_OpenProcessToken
0x18003bb42  mov     r8, [rsp+48h+var_28]
0x18003bb47  mov     ebx, eax
0x18003bb49  test    r8, r8
0x18003bb4c  jz      short loc_18003BB69
0x18003bb4e  mov     rdx, [rsp+48h+var_20]
0x18003bb53  mov     rcx, [rdx]; hObject
0x18003bb56  mov     [rdx], r8
0x18003bb59  lea     rdx, [rcx+1]
0x18003bb5d  cmp     rdx, 1
0x18003bb61  jbe     short loc_18003BB69
0x18003bb63  call    cs:__imp_CloseHandle
0x18003bb69  test    ebx, ebx
0x18003bb6b  jnz     short loc_18003BBAD
0x18003bb6d  mov     rax, cs:WPP_GLOBAL_Control
0x18003bb74  lea     rcx, WPP_GLOBAL_Control
0x18003bb7b  cmp     rax, rcx
0x18003bb7e  jz      short loc_18003BBA9
0x18003bb80  test    byte ptr [rax+1Ch], 1
0x18003bb84  jz      short loc_18003BBA9
0x18003bb86  call    cs:__imp_GetLastError
0x18003bb8c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003bb93  lea     edx, [rbx+2Eh]
0x18003bb96  mov     r9d, eax
0x18003bb99  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003bba0  mov     rcx, [rcx+10h]
0x18003bba4  call    WPP_SF_d
0x18003bba9  xor     bl, bl
0x18003bbab  jmp     short loc_18003BBB9
0x18003bbad  mov     rcx, [rsp+48h+hObject]; ExistingTokenHandle
0x18003bbb2  call    ?UtilIsWriteRestrictedToken@@YA_NPEAX@Z; UtilIsWriteRestrictedToken(void *)
0x18003bbb7  mov     bl, al
0x18003bbb9  mov     rcx, [rsp+48h+hObject]; hObject
0x18003bbbe  lea     rdx, [rcx+1]
0x18003bbc2  cmp     rdx, 1
0x18003bbc6  jbe     short loc_18003BBCE
0x18003bbc8  call    cs:__imp_CloseHandle
0x18003bbce  mov     al, bl
0x18003bbd0  add     rsp, 40h
0x18003bbd4  pop     rbx
0x18003bbd5  retn
```
