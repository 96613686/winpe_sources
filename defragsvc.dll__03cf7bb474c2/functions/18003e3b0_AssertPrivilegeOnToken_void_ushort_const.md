# AssertPrivilegeOnToken(void *,ushort const *)

- ea: `0x18003e3b0`
- end: `0x18003e55e`
- name: `?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z`
- size: `430`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800146b8`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180038c3c`
- `0x18003e3b0`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e4b7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e4b7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003e4db`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18003e4db`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003e474`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18003e474`

## string_xrefs

- `0x18003e412`: `AssertPrivilegeOnToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AssertPrivilegeOnToken(HANDLE TokenHandle, LPCWSTR lpName)
{
  __int16 v4; // ax
  int LastFailureAsHRESULT; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  signed int LastError; // eax
  _LUID Luid; // [rsp+30h] [rbp-9h] BYREF
  int v17; // [rsp+38h] [rbp-1h] BYREF
  __int16 v18; // [rsp+3Ch] [rbp+3h]
  __int16 v19; // [rsp+3Eh] [rbp+5h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+70h] [rbp+37h] BYREF

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v17, "AssertPrivilegeOnToken", 1255, 1);
  Luid = 0;
  v4 = 1259;
  NewState = 0;
  if ( TokenHandle && (v18 = 1259, v4 = 1260, lpName) )
  {
    v17 = 0;
    v18 = 1260;
    if ( LookupPrivilegeValueW(0, lpName, &Luid) )
    {
      v17 = 0;
      v18 = 1262;
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      SetLastError(0);
      if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
      {
        v17 = 0;
        v18 = 1270;
        LastError = GetLastError();
        LastFailureAsHRESULT = LastError;
        if ( LastError > 0 )
          LastFailureAsHRESULT = (unsigned __int16)LastError | 0x80070000;
        v17 = LastFailureAsHRESULT;
        v4 = 1273;
        if ( LastFailureAsHRESULT >= 0 )
        {
          v18 = 1273;
          goto LABEL_16;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11, v10, v12, v13);
        v17 = LastFailureAsHRESULT;
        v4 = 1270;
      }
    }
    else
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v7, v6, v8, v9);
      v17 = LastFailureAsHRESULT;
      v4 = 1262;
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
    v17 = -2147024809;
  }
  v19 = v4;
LABEL_16:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v17);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18003e3b0  mov     [rsp-8+arg_10], rbx
0x18003e3b5  mov     [rsp-8+arg_18], rdi
0x18003e3ba  push    rbp
0x18003e3bb  lea     rbp, [rsp-57h]
0x18003e3c0  sub     rsp, 90h
0x18003e3c7  mov     rax, cs:__security_cookie
0x18003e3ce  xor     rax, rsp
0x18003e3d1  mov     [rbp+57h+var_10], rax
0x18003e3d5  mov     rbx, rdx
0x18003e3d8  mov     rdi, rcx
0x18003e3db  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e3e2  lea     rax, WPP_GLOBAL_Control
0x18003e3e9  cmp     rcx, rax
0x18003e3ec  jz      short loc_18003E40C
0x18003e3ee  test    dword ptr [rcx+1Ch], 20000000h
0x18003e3f5  jz      short loc_18003E40C
0x18003e3f7  mov     rcx, [rcx+10h]
0x18003e3fb  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x18003e402  mov     edx, 24h ; '$'
0x18003e407  call    WPP_SF_
0x18003e40c  mov     r9d, 1; unsigned __int16
0x18003e412  lea     rdx, aAssertprivileg_0; "AssertPrivilegeOnToken"
0x18003e419  mov     r8d, 4E7h; unsigned __int16
0x18003e41f  lea     rcx, [rbp+57h+var_58]; this
0x18003e423  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18003e428  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x18003e430  xorps   xmm0, xmm0
0x18003e433  mov     eax, 4EBh
0x18003e438  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x18003e43c  test    rdi, rdi
0x18003e43f  jnz     short loc_18003E452
0x18003e441  mov     ebx, 80070057h
0x18003e446  mov     [rbp+57h+var_58], ebx
0x18003e449  mov     [rbp+57h+var_52], ax
0x18003e44d  jmp     loc_18003E532
0x18003e452  mov     [rbp+57h+var_54], ax
0x18003e456  mov     eax, 4ECh
0x18003e45b  test    rbx, rbx
0x18003e45e  jz      short loc_18003E441
0x18003e460  lea     r8, [rbp+57h+Luid]; lpLuid
0x18003e464  mov     [rbp+57h+var_58], 0
0x18003e46b  mov     rdx, rbx; lpName
0x18003e46e  mov     [rbp+57h+var_54], ax
0x18003e472  xor     ecx, ecx; lpSystemName
0x18003e474  call    cs:__imp_LookupPrivilegeValueW
0x18003e47a  test    eax, eax
0x18003e47c  jnz     short loc_18003E48F
0x18003e47e  call    GetLastFailureAsHRESULT
0x18003e483  mov     ebx, eax
0x18003e485  mov     [rbp+57h+var_58], eax
0x18003e488  mov     eax, 4EEh
0x18003e48d  jmp     short loc_18003E449
0x18003e48f  mov     eax, 4EEh
0x18003e494  mov     [rbp+57h+var_58], 0
0x18003e49b  mov     [rbp+57h+var_54], ax
0x18003e49f  xor     ecx, ecx; dwErrCode
0x18003e4a1  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x18003e4a5  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x18003e4a9  mov     [rbp+57h+NewState.PrivilegeCount], 1
0x18003e4b0  mov     [rbp+57h+NewState.Privileges.Attributes], 2
0x18003e4b7  call    cs:__imp_SetLastError
0x18003e4bd  xor     r9d, r9d; BufferLength
0x18003e4c0  mov     [rsp+90h+ReturnLength], 0; ReturnLength
0x18003e4c9  lea     r8, [rbp+57h+NewState]; NewState
0x18003e4cd  mov     [rsp+90h+PreviousState], 0; PreviousState
0x18003e4d6  xor     edx, edx; DisableAllPrivileges
0x18003e4d8  mov     rcx, rdi; TokenHandle
0x18003e4db  call    cs:__imp_AdjustTokenPrivileges
0x18003e4e1  test    eax, eax
0x18003e4e3  jnz     short loc_18003E4F9
0x18003e4e5  call    GetLastFailureAsHRESULT
0x18003e4ea  mov     ebx, eax
0x18003e4ec  mov     [rbp+57h+var_58], eax
0x18003e4ef  mov     eax, 4F6h
0x18003e4f4  jmp     loc_18003E449
0x18003e4f9  mov     eax, 4F6h
0x18003e4fe  mov     [rbp+57h+var_58], 0
0x18003e505  mov     [rbp+57h+var_54], ax
0x18003e509  call    cs:__imp_GetLastError
0x18003e50f  mov     ebx, eax
0x18003e511  test    eax, eax
0x18003e513  jle     short loc_18003E51E
0x18003e515  movzx   ebx, ax
0x18003e518  or      ebx, 80070000h
0x18003e51e  mov     [rbp+57h+var_58], ebx
0x18003e521  mov     eax, 4F9h
0x18003e526  test    ebx, ebx
0x18003e528  js      loc_18003E449
0x18003e52e  mov     [rbp+57h+var_54], ax
0x18003e532  lea     rcx, [rbp+57h+var_58]; this
0x18003e536  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003e53b  mov     eax, ebx
0x18003e53d  mov     rcx, [rbp+57h+var_10]
0x18003e541  xor     rcx, rsp; StackCookie
0x18003e544  call    __security_check_cookie
0x18003e549  lea     r11, [rsp+90h+var_s0]
0x18003e551  mov     rbx, [r11+20h]
0x18003e555  mov     rdi, [r11+28h]
0x18003e559  mov     rsp, r11
0x18003e55c  pop     rbp
0x18003e55d  retn
```
