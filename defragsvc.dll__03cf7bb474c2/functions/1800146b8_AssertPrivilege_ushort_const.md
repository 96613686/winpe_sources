# AssertPrivilege(ushort const *)

- ea: `0x1800146b8`
- end: `0x1800147bb`
- name: `?AssertPrivilege@@YAJPEBG@Z`
- size: `259`
- prototype: `__int64 __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001457c`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x1800146b8`
- `0x18001a630`
- `0x180038c3c`
- `0x18003e3b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001471d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001471d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001472f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001472f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014797`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014797`

## string_xrefs

- `0x1800146ff`: `AssertPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall AssertPrivilege(LPCWSTR lpName)
{
  HANDLE CurrentProcess; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  int LastFailureAsHRESULT; // ebx
  int v9; // [rsp+20h] [rbp-40h] BYREF
  __int16 v10; // [rsp+24h] [rbp-3Ch]
  __int16 v11; // [rsp+26h] [rbp-3Ah]
  int v12; // [rsp+28h] [rbp-38h]
  void *TokenHandle; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids);
  }
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "AssertPrivilege", 1239, 1);
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
  {
    v10 = 1242;
    v9 = 0;
    LastFailureAsHRESULT = AssertPrivilegeOnToken(TokenHandle, lpName);
    v9 = LastFailureAsHRESULT;
    if ( LastFailureAsHRESULT >= 0 )
    {
      v10 = 1243;
    }
    else
    {
      v11 = 1243;
      v12 = 1;
    }
  }
  else
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4, v3, v5, v6);
    v9 = LastFailureAsHRESULT;
    v11 = 1242;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x1800146b8  mov     [rsp-8+arg_0], rbx
0x1800146bd  push    rbp
0x1800146be  mov     rbp, rsp
0x1800146c1  sub     rsp, 60h
0x1800146c5  mov     rbx, rcx
0x1800146c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800146cf  lea     rax, WPP_GLOBAL_Control
0x1800146d6  cmp     rcx, rax
0x1800146d9  jz      short loc_1800146F9
0x1800146db  test    dword ptr [rcx+1Ch], 20000000h
0x1800146e2  jz      short loc_1800146F9
0x1800146e4  mov     rcx, [rcx+10h]
0x1800146e8  lea     r8, WPP_7721446ba4e13eeec3b2d73f96dbe50c_Traceguids
0x1800146ef  mov     edx, 23h ; '#'
0x1800146f4  call    WPP_SF_
0x1800146f9  mov     r9d, 1; unsigned __int16
0x1800146ff  lea     rdx, aAssertprivileg; "AssertPrivilege"
0x180014706  mov     r8d, 4D7h; unsigned __int16
0x18001470c  lea     rcx, [rbp+var_40]; this
0x180014710  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180014715  mov     [rbp+TokenHandle], 0
0x18001471d  call    cs:__imp_GetCurrentProcess
0x180014723  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180014727  mov     edx, 2000000h; DesiredAccess
0x18001472c  mov     rcx, rax; ProcessHandle
0x18001472f  call    cs:__imp_OpenProcessToken
0x180014735  test    eax, eax
0x180014737  jnz     short loc_18001474E
0x180014739  call    GetLastFailureAsHRESULT
0x18001473e  mov     ebx, eax
0x180014740  mov     [rbp+var_40], eax
0x180014743  mov     eax, 4DAh
0x180014748  mov     [rbp+var_3A], ax
0x18001474c  jmp     short loc_180014789
0x18001474e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180014752  mov     eax, 4DAh
0x180014757  mov     rdx, rbx; lpName
0x18001475a  mov     [rbp+var_3C], ax
0x18001475e  mov     [rbp+var_40], 0
0x180014765  call    ?AssertPrivilegeOnToken@@YAJPEAXPEBG@Z; AssertPrivilegeOnToken(void *,ushort const *)
0x18001476a  mov     ebx, eax
0x18001476c  mov     [rbp+var_40], eax
0x18001476f  test    eax, eax
0x180014771  mov     eax, 4DBh
0x180014776  jns     short loc_180014785
0x180014778  mov     [rbp+var_3A], ax
0x18001477c  mov     [rbp+var_38], 1
0x180014783  jmp     short loc_180014789
0x180014785  mov     [rbp+var_3C], ax
0x180014789  mov     rcx, [rbp+TokenHandle]; hObject
0x18001478d  lea     rdx, [rcx-1]
0x180014791  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180014795  ja      short loc_1800147A5
0x180014797  call    cs:__imp_CloseHandle
0x18001479d  mov     [rbp+TokenHandle], 0
0x1800147a5  lea     rcx, [rbp+var_40]; this
0x1800147a9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800147ae  mov     eax, ebx
0x1800147b0  mov     rbx, [rsp+60h+arg_0]
0x1800147b5  add     rsp, 60h
0x1800147b9  pop     rbp
0x1800147ba  retn
```
