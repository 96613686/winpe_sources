# CDumpCollection::_SnapAllThreads(void)

- ea: `0x180040cb4`
- end: `0x180040eda`
- name: `?_SnapAllThreads@CDumpCollection@@AEAAJXZ`
- size: `550`
- prototype: `__int64 __fastcall(CDumpCollection *this, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ea08`
- `0x180040584`

## callees

- `0x180002890`
- `0x180009ed8`
- `0x180009f00`
- `0x18003e5a8`
- `0x18003e650`
- `0x180040cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040d4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040ddd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040e53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040ead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180040ead`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180040d07`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x180040d07`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180040d43`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x180040d43`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x180040dc8`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x180040dc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDumpCollection::_SnapAllThreads(CDumpCollection *this, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v5; // rsi
  HANDLE Toolhelp32Snapshot; // rax
  void *v7; // rbx
  unsigned __int64 v8; // r14
  signed int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  DWORD *v13; // rcx
  signed int v14; // eax
  signed int LastError; // eax
  _DWORD v17[10]; // [rsp+20h] [rbp-50h] BYREF
  THREADENTRY32 te; // [rsp+48h] [rbp-28h] BYREF

  if ( !*((_DWORD *)this + 278) )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  v5 = (_QWORD *)((char *)this + 2400);
  if ( *((_QWORD *)this + 300) != *((_QWORD *)this + 301) )
    return 0;
  Toolhelp32Snapshot = CreateToolhelp32Snapshot(4u, *((_DWORD *)this + 278));
  v7 = Toolhelp32Snapshot;
  v8 = (unsigned __int64)Toolhelp32Snapshot + 1;
  if ( (unsigned __int64)Toolhelp32Snapshot + 1 <= 1 )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v12 = 77;
    goto LABEL_31;
  }
  memset(&v17[2], 0, 28);
  *(_OWORD *)&te.dwSize = *(_OWORD *)&v17[2];
  te.dwSize = 28;
  *(_OWORD *)&te.th32OwnerProcessID = 0;
  if ( Thread32First(Toolhelp32Snapshot, &te) )
  {
    do
    {
      if ( te.th32OwnerProcessID == *((_DWORD *)this + 278) )
      {
        v13 = (DWORD *)*((_QWORD *)this + 301);
        v17[0] = te.th32ThreadID;
        if ( v13 == *((DWORD **)this + 302) )
        {
          if ( !(unsigned __int8)utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(
                                   (char *)this + 2400,
                                   v17) )
          {
            v10 = -2147024882;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids);
            goto LABEL_33;
          }
        }
        else
        {
          *v13 = te.th32ThreadID;
          *((_QWORD *)this + 301) += 4LL;
        }
      }
    }
    while ( Thread32Next(v7, &te) );
    if ( GetLastError() == 18 )
    {
      v10 = 0;
      goto LABEL_35;
    }
    v14 = GetLastError();
    v10 = v14;
    if ( v14 > 0 )
      v10 = (unsigned __int16)v14 | 0x80070000;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = 80;
      goto LABEL_31;
    }
    goto LABEL_32;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 78;
LABEL_31:
    WPP_SF_d(v11[2], v12, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids, v10);
  }
LABEL_32:
  if ( (v10 & 0x80000000) != 0 )
LABEL_33:
    v5[1] = *v5;
  if ( v8 > 1 )
LABEL_35:
    CloseHandle(v7);
  return v10;
}

```

## disassembly

```asm
0x180040cb4  mov     [rsp-18h+arg_8], rbx
0x180040cb9  mov     [rsp-18h+arg_10], rsi
0x180040cbe  push    rbp
0x180040cbf  push    rdi
0x180040cc0  push    r14
0x180040cc2  mov     rbp, rsp
0x180040cc5  sub     rsp, 70h
0x180040cc9  mov     rax, cs:__security_cookie
0x180040cd0  xor     rax, rsp
0x180040cd3  mov     [rbp+var_8], rax
0x180040cd7  cmp     dword ptr [rcx+458h], 0
0x180040cde  mov     rdi, rcx
0x180040ce1  jnz     short loc_180040CE8
0x180040ce3  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180040ce8  lea     rsi, [rdi+960h]
0x180040cef  mov     rax, [rsi+8]
0x180040cf3  cmp     [rsi], rax
0x180040cf6  jnz     loc_180040EB7
0x180040cfc  mov     edx, [rdi+458h]; th32ProcessID
0x180040d02  mov     ecx, 4; dwFlags
0x180040d07  call    cs:__imp_CreateToolhelp32Snapshot
0x180040d0d  mov     rbx, rax
0x180040d10  lea     r14, [rax+1]
0x180040d14  cmp     r14, 1
0x180040d18  jbe     loc_180040E53
0x180040d1e  xorps   xmm1, xmm1
0x180040d21  lea     rdx, [rbp+te]; lpte
0x180040d25  movups  xmmword ptr [rbp+var_48], xmm1
0x180040d29  mov     rcx, rax; hSnapshot
0x180040d2c  movups  xmmword ptr [rbp+var_48+0Ch], xmm1
0x180040d30  movups  xmm0, xmmword ptr [rbp+var_48]
0x180040d34  movups  xmmword ptr [rbp+te.dwSize], xmm0
0x180040d38  mov     [rbp+te.dwSize], 1Ch
0x180040d3f  movups  xmmword ptr [rbp+te.th32OwnerProcessID], xmm1
0x180040d43  call    cs:__imp_Thread32First
0x180040d49  test    eax, eax
0x180040d4b  jnz     short loc_180040D8D
0x180040d4d  call    cs:__imp_GetLastError
0x180040d53  mov     edi, eax
0x180040d55  test    eax, eax
0x180040d57  jle     short loc_180040D62
0x180040d59  movzx   edi, ax
0x180040d5c  or      edi, 80070000h
0x180040d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180040d69  lea     rax, WPP_GLOBAL_Control
0x180040d70  cmp     rcx, rax
0x180040d73  jz      loc_180040E99
0x180040d79  test    byte ptr [rcx+1Ch], 1
0x180040d7d  jz      loc_180040E99
0x180040d83  mov     edx, 4Eh ; 'N'
0x180040d88  jmp     loc_180040E86
0x180040d8d  mov     eax, [rdi+458h]
0x180040d93  cmp     [rbp+te.th32OwnerProcessID], eax
0x180040d96  jnz     short loc_180040DC1
0x180040d98  mov     rcx, [rsi+8]
0x180040d9c  mov     eax, [rbp+te.th32ThreadID]
0x180040d9f  mov     [rbp+var_50], eax
0x180040da2  cmp     rcx, [rsi+10h]
0x180040da6  jz      short loc_180040DB1
0x180040da8  mov     [rcx], eax
0x180040daa  add     qword ptr [rsi+8], 4
0x180040daf  jmp     short loc_180040DC1
0x180040db1  lea     rdx, [rbp+var_50]
0x180040db5  mov     rcx, rsi
0x180040db8  call    ??$_PushBackOne2@UThreadInfoNode@CDumpCollection@@@?$vector@UThreadInfoNode@CDumpCollection@@V?$allocator@UThreadInfoNode@CDumpCollection@@@utl@@@utl@@AEAA_N$$QEAUThreadInfoNode@CDumpCollection@@@Z; utl::vector<CDumpCollection::ThreadInfoNode,utl::allocator<CDumpCollection::ThreadInfoNode>>::_PushBackOne2<CDumpCollection::ThreadInfoNode>(CDumpCollection::ThreadInfoNode &&)
0x180040dbd  test    al, al
0x180040dbf  jz      short loc_180040E1A
0x180040dc1  lea     rdx, [rbp+te]; lpte
0x180040dc5  mov     rcx, rbx; hSnapshot
0x180040dc8  call    cs:__imp_Thread32Next
0x180040dce  test    eax, eax
0x180040dd0  jnz     short loc_180040D8D
0x180040dd2  call    cs:__imp_GetLastError
0x180040dd8  cmp     eax, 12h
0x180040ddb  jz      short loc_180040E4F
0x180040ddd  call    cs:__imp_GetLastError
0x180040de3  mov     edi, eax
0x180040de5  test    eax, eax
0x180040de7  jle     short loc_180040DF2
0x180040de9  movzx   edi, ax
0x180040dec  or      edi, 80070000h
0x180040df2  mov     rcx, cs:WPP_GLOBAL_Control
0x180040df9  lea     rax, WPP_GLOBAL_Control
0x180040e00  cmp     rcx, rax
0x180040e03  jz      loc_180040E99
0x180040e09  test    byte ptr [rcx+1Ch], 1
0x180040e0d  jz      loc_180040E99
0x180040e13  mov     edx, 50h ; 'P'
0x180040e18  jmp     short loc_180040E86
0x180040e1a  mov     edi, 8007000Eh
0x180040e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e26  lea     rax, WPP_GLOBAL_Control
0x180040e2d  cmp     rcx, rax
0x180040e30  jz      short loc_180040E9D
0x180040e32  test    byte ptr [rcx+1Ch], 1
0x180040e36  jz      short loc_180040E9D
0x180040e38  mov     rcx, [rcx+10h]
0x180040e3c  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x180040e43  mov     edx, 4Fh ; 'O'
0x180040e48  call    WPP_SF_
0x180040e4d  jmp     short loc_180040E9D
0x180040e4f  xor     edi, edi
0x180040e51  jmp     short loc_180040EAA
0x180040e53  call    cs:__imp_GetLastError
0x180040e59  mov     edi, eax
0x180040e5b  test    eax, eax
0x180040e5d  jle     short loc_180040E68
0x180040e5f  movzx   edi, ax
0x180040e62  or      edi, 80070000h
0x180040e68  mov     rcx, cs:WPP_GLOBAL_Control
0x180040e6f  lea     rax, WPP_GLOBAL_Control
0x180040e76  cmp     rcx, rax
0x180040e79  jz      short loc_180040E99
0x180040e7b  test    byte ptr [rcx+1Ch], 1
0x180040e7f  jz      short loc_180040E99
0x180040e81  mov     edx, 4Dh ; 'M'
0x180040e86  mov     rcx, [rcx+10h]
0x180040e8a  lea     r8, WPP_f320c46cc3083f8f85fbd82a7e5f48c1_Traceguids
0x180040e91  mov     r9d, edi
0x180040e94  call    WPP_SF_d
0x180040e99  test    edi, edi
0x180040e9b  jns     short loc_180040EA4
0x180040e9d  mov     rcx, [rsi]
0x180040ea0  mov     [rsi+8], rcx
0x180040ea4  cmp     r14, 1
0x180040ea8  jbe     short loc_180040EB3
0x180040eaa  mov     rcx, rbx; hObject
0x180040ead  call    cs:__imp_CloseHandle
0x180040eb3  mov     eax, edi
0x180040eb5  jmp     short loc_180040EB9
0x180040eb7  xor     eax, eax
0x180040eb9  mov     rcx, [rbp+var_8]
0x180040ebd  xor     rcx, rsp; StackCookie
0x180040ec0  call    __security_check_cookie
0x180040ec5  lea     r11, [rsp+70h+var_s0]
0x180040eca  mov     rbx, [r11+28h]
0x180040ece  mov     rsi, [r11+30h]
0x180040ed2  mov     rsp, r11
0x180040ed5  pop     r14
0x180040ed7  pop     rdi
0x180040ed8  pop     rbp
0x180040ed9  retn
```
