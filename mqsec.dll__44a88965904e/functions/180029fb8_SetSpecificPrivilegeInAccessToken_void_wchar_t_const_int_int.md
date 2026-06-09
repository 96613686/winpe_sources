# SetSpecificPrivilegeInAccessToken(void *,wchar_t const *,int,int *)

- ea: `0x180029fb8`
- end: `0x18002a1a2`
- name: `?SetSpecificPrivilegeInAccessToken@@YAJPEAXPEB_WHPEAH@Z`
- size: `490`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, const wchar_t *, int, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001fd70`
- `0x180029990`

## callees

- `0x1800049ac`
- `0x180013940`
- `0x18001722c`
- `0x180029fb8`
- `0x18002f0e0`

## import_xrefs

- `msvcrt!free` at `0x18002a15c`
- `msvcrt!free` at `0x18002a179`
- `msvcrt!free` at `0x18002a15c`
- `msvcrt!free` at `0x18002a179`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18002a0d9`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18002a0d9`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180029ff7`
- `ADVAPI32!LookupPrivilegeValueW` at `0x180029ff7`
- `KERNEL32!GetLastError` at `0x18002a01d`
- `KERNEL32!GetLastError` at `0x18002a045`
- `KERNEL32!GetLastError` at `0x18002a103`
- `KERNEL32!GetLastError` at `0x18002a12b`
- `KERNEL32!GetLastError` at `0x18002a01d`
- `KERNEL32!GetLastError` at `0x18002a045`
- `KERNEL32!GetLastError` at `0x18002a103`
- `KERNEL32!GetLastError` at `0x18002a12b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SetSpecificPrivilegeInAccessToken(HANDLE TokenHandle, const wchar_t *a2, int a3, int *a4)
{
  DWORD v7; // eax
  signed int v8; // eax
  signed int v9; // ebx
  struct _TOKEN_PRIVILEGES *v11; // rbx
  DWORD v12; // r14d
  struct _TOKEN_PRIVILEGES *PreviousState; // rdi
  DWORD *ReturnLength; // rax
  DWORD LastError; // eax
  signed int v16; // eax
  signed int v17; // edi
  DWORD v18; // [rsp+30h] [rbp-30h] BYREF
  struct _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES *v20; // [rsp+40h] [rbp-20h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  Luid = 0;
  NewState = 0;
  if ( LookupPrivilegeValueW(0, a2, &Luid) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = Luid;
    NewState.Privileges[0].Attributes = a3 != 0 ? 2 : 0;
    v11 = 0;
    v20 = 0;
    v18 = 0;
    if ( a4 )
    {
      v12 = 28;
      v11 = (struct _TOKEN_PRIVILEGES *)MmAllocate(0x1Cu);
      v20 = v11;
      PreviousState = v11;
      ReturnLength = &v18;
    }
    else
    {
      v12 = 0;
      ReturnLength = 0;
      PreviousState = 0;
    }
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, v12, PreviousState, ReturnLength) )
    {
      if ( a4 )
        *a4 = PreviousState->Privileges[0].Attributes != 0;
      free(v11);
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids, LastError);
      }
      v16 = GetLastError();
      v17 = v16;
      if ( v16 > 0 )
        v17 = (unsigned __int16)v16 | 0x80070000;
      if ( v17 < 0 )
        LogMsgHR(v17, (wchar_t *)L"acssctrl/privilge", 0x1Bu);
      free(v11);
      return (unsigned int)v17;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
    {
      v7 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids, v7);
    }
    v8 = GetLastError();
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v9 < 0 )
      LogMsgHR(v9, (wchar_t *)L"acssctrl/privilge", 0x14u);
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x180029fb8  mov     [rsp-28h+arg_10], rbx
0x180029fbd  push    rbp
0x180029fbe  push    rsi
0x180029fbf  push    rdi
0x180029fc0  push    r14
0x180029fc2  push    r15
0x180029fc4  mov     rbp, rsp
0x180029fc7  sub     rsp, 60h
0x180029fcb  mov     rax, cs:__security_cookie
0x180029fd2  xor     rax, rsp
0x180029fd5  mov     [rbp+var_8], rax
0x180029fd9  mov     rsi, r9
0x180029fdc  mov     ebx, r8d
0x180029fdf  mov     r15, rcx
0x180029fe2  mov     qword ptr [rbp+Luid.LowPart], 0
0x180029fea  xorps   xmm0, xmm0
0x180029fed  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180029ff1  lea     r8, [rbp+Luid]; lpLuid
0x180029ff5  xor     ecx, ecx; lpSystemName
0x180029ff7  call    cs:__imp_LookupPrivilegeValueW
0x180029ffd  test    eax, eax
0x180029fff  jnz     short loc_18002A079
0x18002a001  lea     rax, WPP_GLOBAL_Control
0x18002a008  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a00f  cmp     rcx, rax
0x18002a012  jz      short loc_18002A045
0x18002a014  test    byte ptr [rcx+10Ch], 1
0x18002a01b  jz      short loc_18002A045
0x18002a01d  call    cs:__imp_GetLastError
0x18002a023  mov     edx, 0Ah
0x18002a028  mov     r9d, eax
0x18002a02b  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x18002a032  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a039  mov     rcx, [rcx+100h]
0x18002a040  call    WPP_SF_d
0x18002a045  call    cs:__imp_GetLastError
0x18002a04b  mov     ebx, eax
0x18002a04d  test    eax, eax
0x18002a04f  jle     short loc_18002A05A
0x18002a051  movzx   ebx, ax
0x18002a054  or      ebx, 80070000h
0x18002a05a  test    ebx, ebx
0x18002a05c  jns     short loc_18002A072
0x18002a05e  mov     r8d, 14h; unsigned __int16
0x18002a064  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x18002a06b  mov     ecx, ebx; int
0x18002a06d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002a072  mov     eax, ebx
0x18002a074  jmp     loc_18002A182
0x18002a079  mov     [rbp+NewState.PrivilegeCount], 1
0x18002a080  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18002a084  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18002a088  neg     ebx
0x18002a08a  sbb     eax, eax
0x18002a08c  and     eax, 2
0x18002a08f  mov     [rbp+NewState.Privileges.Attributes], eax
0x18002a092  xor     ebx, ebx
0x18002a094  mov     [rbp+var_20], rbx
0x18002a098  mov     [rbp+var_30], ebx
0x18002a09b  test    rsi, rsi
0x18002a09e  jz      short loc_18002A0BC
0x18002a0a0  lea     r14d, [rbx+1Ch]
0x18002a0a4  mov     ecx, r14d; unsigned __int64
0x18002a0a7  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002a0ac  mov     rbx, rax
0x18002a0af  mov     [rbp+var_20], rax
0x18002a0b3  mov     rdi, rax
0x18002a0b6  lea     rax, [rbp+var_30]
0x18002a0ba  jmp     short loc_18002A0C3
0x18002a0bc  xor     r14d, r14d
0x18002a0bf  xor     eax, eax
0x18002a0c1  xor     edi, edi
0x18002a0c3  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18002a0c8  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x18002a0cd  mov     r9d, r14d; BufferLength
0x18002a0d0  lea     r8, [rbp+NewState]; NewState
0x18002a0d4  xor     edx, edx; DisableAllPrivileges
0x18002a0d6  mov     rcx, r15; TokenHandle
0x18002a0d9  call    cs:__imp_AdjustTokenPrivileges
0x18002a0df  test    eax, eax
0x18002a0e1  jnz     loc_18002A167
0x18002a0e7  lea     rax, WPP_GLOBAL_Control
0x18002a0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0f5  cmp     rcx, rax
0x18002a0f8  jz      short loc_18002A12B
0x18002a0fa  test    byte ptr [rcx+10Ch], 1
0x18002a101  jz      short loc_18002A12B
0x18002a103  call    cs:__imp_GetLastError
0x18002a109  mov     edx, 0Bh
0x18002a10e  mov     r9d, eax
0x18002a111  lea     r8, WPP_6595c8b0bcaf330ab6208b6e35db9f13_Traceguids
0x18002a118  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a11f  mov     rcx, [rcx+100h]
0x18002a126  call    WPP_SF_d
0x18002a12b  call    cs:__imp_GetLastError
0x18002a131  mov     edi, eax
0x18002a133  test    eax, eax
0x18002a135  jle     short loc_18002A140
0x18002a137  movzx   edi, ax
0x18002a13a  or      edi, 80070000h
0x18002a140  test    edi, edi
0x18002a142  jns     short loc_18002A159
0x18002a144  mov     r8d, 1Bh; unsigned __int16
0x18002a14a  lea     rdx, aAcssctrlPrivil; "acssctrl/privilge"
0x18002a151  mov     ecx, edi; int
0x18002a153  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002a158  nop
0x18002a159  mov     rcx, rbx; Block
0x18002a15c  call    cs:__imp_free
0x18002a162  nop
0x18002a163  mov     eax, edi
0x18002a165  jmp     short loc_18002A182
0x18002a167  test    rsi, rsi
0x18002a16a  jz      short loc_18002A176
0x18002a16c  xor     eax, eax
0x18002a16e  cmp     [rdi+0Ch], eax
0x18002a171  setnz   al
0x18002a174  mov     [rsi], eax
0x18002a176  mov     rcx, rbx; Block
0x18002a179  call    cs:__imp_free
0x18002a17f  nop
0x18002a180  xor     eax, eax
0x18002a182  mov     rcx, [rbp+var_8]
0x18002a186  xor     rcx, rsp; StackCookie
0x18002a189  call    __security_check_cookie
0x18002a18e  mov     rbx, [rsp+60h+arg_10]
0x18002a196  add     rsp, 60h
0x18002a19a  pop     r15
0x18002a19c  pop     r14
0x18002a19e  pop     rdi
0x18002a19f  pop     rsi
0x18002a1a0  pop     rbp
0x18002a1a1  retn
```
