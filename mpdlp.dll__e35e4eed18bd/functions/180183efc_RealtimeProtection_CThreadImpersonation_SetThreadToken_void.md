# RealtimeProtection::CThreadImpersonation::_SetThreadToken(void *)

- ea: `0x180183efc`
- end: `0x180183fed`
- name: `?_SetThreadToken@CThreadImpersonation@RealtimeProtection@@AEAAJPEAX@Z`
- size: `241`
- prototype: `int(RealtimeProtection::CThreadImpersonation *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180183540`

## callees

- `0x1800809d0`
- `0x180105f50`
- `0x18010cb40`
- `0x180183efc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180183f86`
- `KERNEL32!CloseHandle` at `0x180183fd2`
- `KERNEL32!CloseHandle` at `0x180183f86`
- `KERNEL32!CloseHandle` at `0x180183fd2`
- `ADVAPI32!SetThreadToken` at `0x180183f97`
- `ADVAPI32!SetThreadToken` at `0x180183f97`
- `ADVAPI32!DuplicateTokenEx` at `0x180183f3a`
- `ADVAPI32!DuplicateTokenEx` at `0x180183f3a`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CThreadImpersonation::_SetThreadToken(
        RealtimeProtection::CThreadImpersonation *this,
        void *a2)
{
  unsigned int LastFailure; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  HANDLE hObject; // [rsp+30h] [rbp-18h] BYREF

  hObject = 0;
  if ( !DuplicateTokenEx(a2, 4u, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
  {
    LastFailure = HrGetLastFailure();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 43;
LABEL_5:
      WPP_SF_d(v3[2], v4, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, LastFailure);
      goto LABEL_6;
    }
    goto LABEL_6;
  }
  if ( !SetThreadToken(0, hObject) )
  {
    LastFailure = HrGetLastFailure();
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = 44;
      goto LABEL_5;
    }
LABEL_6:
    if ( hObject )
      CloseHandle(hObject);
    return LastFailure;
  }
  if ( hObject )
    CloseHandle(hObject);
  return 0;
}

```

## disassembly

```asm
0x180183efc  mov     r11, rsp
0x180183eff  push    rbx
0x180183f00  sub     rsp, 40h
0x180183f04  mov     rax, cs:__security_cookie
0x180183f0b  xor     rax, rsp
0x180183f0e  mov     [rsp+48h+var_10], rax
0x180183f13  mov     r9d, 2; ImpersonationLevel
0x180183f19  mov     qword ptr [r11-18h], 0
0x180183f21  lea     rcx, [r11-18h]
0x180183f25  mov     rax, rdx
0x180183f28  mov     [r11-20h], rcx
0x180183f2c  xor     r8d, r8d; lpTokenAttributes
0x180183f2f  mov     rcx, rax; hExistingToken
0x180183f32  mov     [r11-28h], r9d
0x180183f36  lea     edx, [r9+2]; dwDesiredAccess
0x180183f3a  call    cs:__imp_DuplicateTokenEx
0x180183f40  test    eax, eax
0x180183f42  jnz     short loc_180183F90
0x180183f44  call    HrGetLastFailure
0x180183f49  mov     ebx, eax
0x180183f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180183f52  lea     rdx, WPP_GLOBAL_Control
0x180183f59  cmp     rcx, rdx
0x180183f5c  jz      short loc_180183F7C
0x180183f5e  test    byte ptr [rcx+1Ch], 1
0x180183f62  jz      short loc_180183F7C
0x180183f64  mov     edx, 2Bh ; '+'
0x180183f69  mov     rcx, [rcx+10h]
0x180183f6d  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180183f74  mov     r9d, ebx
0x180183f77  call    WPP_SF_d
0x180183f7c  mov     rcx, [rsp+48h+hObject]; hObject
0x180183f81  test    rcx, rcx
0x180183f84  jz      short loc_180183F8C
0x180183f86  call    cs:__imp_CloseHandle
0x180183f8c  mov     eax, ebx
0x180183f8e  jmp     short loc_180183FDA
0x180183f90  mov     rdx, [rsp+48h+hObject]; Token
0x180183f95  xor     ecx, ecx; Thread
0x180183f97  call    cs:__imp_SetThreadToken
0x180183f9d  test    eax, eax
0x180183f9f  jnz     short loc_180183FC8
0x180183fa1  call    HrGetLastFailure
0x180183fa6  mov     ebx, eax
0x180183fa8  mov     rcx, cs:WPP_GLOBAL_Control
0x180183faf  lea     rdx, WPP_GLOBAL_Control
0x180183fb6  cmp     rcx, rdx
0x180183fb9  jz      short loc_180183F7C
0x180183fbb  test    byte ptr [rcx+1Ch], 1
0x180183fbf  jz      short loc_180183F7C
0x180183fc1  mov     edx, 2Ch ; ','
0x180183fc6  jmp     short loc_180183F69
0x180183fc8  mov     rcx, [rsp+48h+hObject]; hObject
0x180183fcd  test    rcx, rcx
0x180183fd0  jz      short loc_180183FD8
0x180183fd2  call    cs:__imp_CloseHandle
0x180183fd8  xor     eax, eax
0x180183fda  mov     rcx, [rsp+48h+var_10]
0x180183fdf  xor     rcx, rsp; StackCookie
0x180183fe2  call    __security_check_cookie
0x180183fe7  add     rsp, 40h
0x180183feb  pop     rbx
0x180183fec  retn
```
