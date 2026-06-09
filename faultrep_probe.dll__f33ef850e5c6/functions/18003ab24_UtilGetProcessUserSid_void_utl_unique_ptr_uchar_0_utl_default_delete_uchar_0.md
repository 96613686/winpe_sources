# UtilGetProcessUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)

- ea: `0x18003ab24`
- end: `0x18003ac9d`
- name: `?UtilGetProcessUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18004704c`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x180009f00`
- `0x1800390e0`
- `0x18003ab24`
- `0x18003b078`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003abb0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003abb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003abe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003abe1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003abd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ac8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003abd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003ac8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtilGetProcessUserSid(HANDLE ProcessHandle, const struct std::nothrow_t *a2)
{
  int TokenUserSid; // ebx
  void *v5; // rcx
  void **v6; // rax
  BOOL v7; // edi
  void *v8; // rcx
  signed int LastError; // eax
  void *v11; // [rsp+20h] [rbp-28h] BYREF
  void **v12; // [rsp+28h] [rbp-20h]
  HANDLE hObject; // [rsp+58h] [rbp+10h] BYREF

  hObject = 0;
  if ( a2 )
  {
    v5 = *(void **)a2;
    *(_QWORD *)a2 = 0;
    if ( v5 )
      operator delete(v5, a2);
    v6 = (void **)utl::out_ptr<void,tlx::unique_any<tlx::file_handle_traits>,>(&v11, &hObject);
    v7 = OpenProcessToken(ProcessHandle, 8u, v6);
    if ( v11 )
    {
      v8 = *v12;
      *v12 = v11;
      if ( (unsigned __int64)v8 + 1 > 1 )
        CloseHandle(v8);
    }
    if ( v7 )
    {
      TokenUserSid = UtilGetTokenUserSid(hObject, a2);
      if ( TokenUserSid >= 0 )
      {
        TokenUserSid = 0;
      }
      else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)TokenUserSid);
      }
    }
    else
    {
      LastError = GetLastError();
      TokenUserSid = LastError;
      if ( LastError > 0 )
        TokenUserSid = (unsigned __int16)LastError | 0x80070000;
      if ( TokenUserSid >= 0 )
        TokenUserSid = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_988ce82756cb3ec502560a762615dae0_Traceguids,
          (unsigned int)TokenUserSid);
    }
  }
  else
  {
    TokenUserSid = -2147024809;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)TokenUserSid;
}

```

## disassembly

```asm
0x18003ab24  mov     [rsp+arg_0], rbx
0x18003ab29  push    rdi
0x18003ab2a  sub     rsp, 40h
0x18003ab2e  mov     rbx, rdx
0x18003ab31  mov     rdi, rcx
0x18003ab34  mov     [rsp+48h+hObject], 0
0x18003ab3d  test    rdx, rdx
0x18003ab40  jnz     short loc_18003AB82
0x18003ab42  mov     ebx, 80070057h
0x18003ab47  lea     rax, WPP_GLOBAL_Control
0x18003ab4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ab55  cmp     rcx, rax
0x18003ab58  jz      loc_18003AC7B
0x18003ab5e  test    byte ptr [rcx+1Ch], 1
0x18003ab62  jz      loc_18003AC7B
0x18003ab68  mov     edx, 0Fh
0x18003ab6d  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003ab74  mov     rcx, [rcx+10h]
0x18003ab78  call    WPP_SF_
0x18003ab7d  jmp     loc_18003AC7B
0x18003ab82  mov     rcx, [rdx]; void *
0x18003ab85  mov     qword ptr [rdx], 0
0x18003ab8c  test    rcx, rcx
0x18003ab8f  jz      short loc_18003AB96
0x18003ab91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ab96  lea     rdx, [rsp+48h+hObject]
0x18003ab9b  lea     rcx, [rsp+48h+var_28]
0x18003aba0  call    ??$out_ptr@XV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z
0x18003aba5  mov     r8, rax; TokenHandle
0x18003aba8  mov     edx, 8; DesiredAccess
0x18003abad  mov     rcx, rdi; ProcessHandle
0x18003abb0  call    cs:__imp_OpenProcessToken
0x18003abb6  mov     edi, eax
0x18003abb8  mov     r8, [rsp+48h+var_28]
0x18003abbd  test    r8, r8
0x18003abc0  jz      short loc_18003ABDD
0x18003abc2  mov     rdx, [rsp+48h+var_20]
0x18003abc7  mov     rcx, [rdx]; hObject
0x18003abca  mov     [rdx], r8
0x18003abcd  lea     rdx, [rcx+1]
0x18003abd1  cmp     rdx, 1
0x18003abd5  jbe     short loc_18003ABDD
0x18003abd7  call    cs:__imp_CloseHandle
0x18003abdd  test    edi, edi
0x18003abdf  jnz     short loc_18003AC33
0x18003abe1  call    cs:__imp_GetLastError
0x18003abe7  mov     ebx, eax
0x18003abe9  test    eax, eax
0x18003abeb  jle     short loc_18003ABF6
0x18003abed  movzx   ebx, ax
0x18003abf0  or      ebx, 80070000h
0x18003abf6  mov     eax, 80004005h
0x18003abfb  test    ebx, ebx
0x18003abfd  cmovns  ebx, eax
0x18003ac00  lea     rax, WPP_GLOBAL_Control
0x18003ac07  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac0e  cmp     rcx, rax
0x18003ac11  jz      short loc_18003AC7B
0x18003ac13  test    byte ptr [rcx+1Ch], 1
0x18003ac17  jz      short loc_18003AC7B
0x18003ac19  mov     edx, 10h
0x18003ac1e  mov     r9d, ebx
0x18003ac21  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003ac28  mov     rcx, [rcx+10h]
0x18003ac2c  call    WPP_SF_d
0x18003ac31  jmp     short loc_18003AC7B
0x18003ac33  mov     rdx, rbx
0x18003ac36  mov     rcx, [rsp+48h+hObject]; TokenHandle
0x18003ac3b  call    ?UtilGetTokenUserSid@@YAJPEAXPEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@utl@@@Z; UtilGetTokenUserSid(void *,utl::unique_ptr<uchar [0],utl::default_delete<uchar [0]>> *)
0x18003ac40  mov     ebx, eax
0x18003ac42  test    eax, eax
0x18003ac44  jns     short loc_18003AC79
0x18003ac46  lea     rax, WPP_GLOBAL_Control
0x18003ac4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac54  cmp     rcx, rax
0x18003ac57  jz      short loc_18003AC7B
0x18003ac59  test    byte ptr [rcx+1Ch], 1
0x18003ac5d  jz      short loc_18003AC7B
0x18003ac5f  mov     edx, 11h
0x18003ac64  mov     r9d, ebx
0x18003ac67  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x18003ac6e  mov     rcx, [rcx+10h]
0x18003ac72  call    WPP_SF_d
0x18003ac77  jmp     short loc_18003AC7B
0x18003ac79  xor     ebx, ebx
0x18003ac7b  mov     rcx, [rsp+48h+hObject]; hObject
0x18003ac80  lea     rax, [rcx+1]
0x18003ac84  cmp     rax, 1
0x18003ac88  jbe     short loc_18003AC90
0x18003ac8a  call    cs:__imp_CloseHandle
0x18003ac90  mov     eax, ebx
0x18003ac92  mov     rbx, [rsp+48h+arg_0]
0x18003ac97  add     rsp, 40h
0x18003ac9b  pop     rdi
0x18003ac9c  retn
```
