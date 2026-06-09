# CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)

- ea: `0x1800192f0`
- end: `0x18001941e`
- name: `?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z`
- size: `302`
- prototype: `__int64 __fastcall(DWORD *pSessionId, unsigned int *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800334a0`

## callees

- `0x180009580`
- `0x1800192f0`
- `0x18004e850`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800193e0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800193e0`
- `ntdll!NtQueryInformationProcess` at `0x1800193c0`
- `ntdll!NtQueryInformationProcess` at `0x1800193c0`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019345`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180019345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001940d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001940d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001932a`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001932a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019390`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180019390`

## pseudocode

```c
__int64 __fastcall CRpcUtils::GetRpcCallerInfo(
        DWORD *pSessionId,
        unsigned int *a2,
        unsigned int a3,
        unsigned __int16 *a4)
{
  unsigned __int64 v5; // rbp
  RPC_STATUS v8; // eax
  int v9; // ebx
  HANDLE v11; // rax
  void *v12; // rdi
  NTSTATUS InformationProcess; // eax
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  _BYTE ProcessInformation[8]; // [rsp+30h] [rbp-148h] BYREF
  wchar_t *Str; // [rsp+38h] [rbp-140h]

  *pSessionId = -1;
  v5 = a3;
  *a2 = -1;
  v8 = I_RpcBindingInqLocalClientPID(0, a2);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v9 >= 0 )
  {
    ProcessIdToSessionId(*a2, pSessionId);
    if ( (_DWORD)v5 )
    {
      if ( a4 )
      {
        v11 = OpenProcess(0x400u, 0, *a2);
        v12 = v11;
        if ( v11 )
        {
          InformationProcess = NtQueryInformationProcess(v11, ProcessImageFileName, ProcessInformation, 0x110u, 0);
          v9 = InformationProcess | 0x10000000;
          if ( InformationProcess >= 0 )
          {
            v14 = wcsrchr(Str, 0x5Cu);
            if ( v14 )
              v15 = v14 + 1;
            else
              v15 = Str;
            StringCchCopyW(a4, v5, v15);
          }
          CloseHandle(v12);
        }
      }
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800192f0  push    rbx
0x1800192f2  push    rbp
0x1800192f3  push    rsi
0x1800192f4  push    rdi
0x1800192f5  push    r14
0x1800192f7  sub     rsp, 150h
0x1800192fe  mov     rax, cs:__security_cookie
0x180019305  xor     rax, rsp
0x180019308  mov     [rsp+178h+var_38], rax
0x180019310  mov     dword ptr [rcx], 0FFFFFFFFh
0x180019316  mov     rsi, rcx
0x180019319  xor     ecx, ecx; Binding
0x18001931b  mov     ebp, r8d
0x18001931e  mov     r14, r9
0x180019321  mov     dword ptr [rdx], 0FFFFFFFFh
0x180019327  mov     rdi, rdx
0x18001932a  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180019331  nop     dword ptr [rax+rax+00h]
0x180019336  mov     ebx, eax
0x180019338  test    eax, eax
0x18001933a  jg      short loc_180019376
0x18001933c  test    ebx, ebx
0x18001933e  js      short loc_180019355
0x180019340  mov     ecx, [rdi]; dwProcessId
0x180019342  mov     rdx, rsi; pSessionId
0x180019345  call    cs:__imp_ProcessIdToSessionId
0x18001934c  nop     dword ptr [rax+rax+00h]
0x180019351  test    ebp, ebp
0x180019353  jnz     short loc_180019381
0x180019355  mov     eax, ebx
0x180019357  mov     rcx, [rsp+178h+var_38]
0x18001935f  xor     rcx, rsp; StackCookie
0x180019362  call    __security_check_cookie
0x180019367  add     rsp, 150h
0x18001936e  pop     r14
0x180019370  pop     rdi
0x180019371  pop     rsi
0x180019372  pop     rbp
0x180019373  pop     rbx
0x180019374  retn
0x180019376  movzx   ebx, ax
0x180019379  or      ebx, 80070000h
0x18001937f  jmp     short loc_18001933C
0x180019381  test    r14, r14
0x180019384  jz      short loc_180019355
0x180019386  mov     r8d, [rdi]; dwProcessId
0x180019389  xor     edx, edx; bInheritHandle
0x18001938b  mov     ecx, 400h; dwDesiredAccess
0x180019390  call    cs:__imp_OpenProcess
0x180019397  nop     dword ptr [rax+rax+00h]
0x18001939c  mov     rdi, rax
0x18001939f  test    rax, rax
0x1800193a2  jz      short loc_180019355
0x1800193a4  mov     r9d, 110h; ProcessInformationLength
0x1800193aa  mov     [rsp+178h+ReturnLength], 0; ReturnLength
0x1800193b3  lea     r8, [rsp+178h+ProcessInformation]; ProcessInformation
0x1800193b8  mov     edx, 1Bh; ProcessInformationClass
0x1800193bd  mov     rcx, rax; ProcessHandle
0x1800193c0  call    cs:__imp_NtQueryInformationProcess
0x1800193c7  nop     dword ptr [rax+rax+00h]
0x1800193cc  mov     ebx, eax
0x1800193ce  or      ebx, 10000000h
0x1800193d4  jl      short loc_18001940A
0x1800193d6  mov     rcx, [rsp+178h+Str]; Str
0x1800193db  mov     edx, 5Ch ; '\'; Ch
0x1800193e0  call    cs:__imp_wcsrchr
0x1800193e7  nop     dword ptr [rax+rax+00h]
0x1800193ec  test    rax, rax
0x1800193ef  jnz     short loc_1800193F8
0x1800193f1  mov     rax, [rsp+178h+Str]
0x1800193f6  jmp     short loc_1800193FC
0x1800193f8  add     rax, 2
0x1800193fc  mov     rdx, rbp; unsigned __int64
0x1800193ff  mov     r8, rax; unsigned __int16 *
0x180019402  mov     rcx, r14; unsigned __int16 *
0x180019405  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001940a  mov     rcx, rdi; hObject
0x18001940d  call    cs:__imp_CloseHandle
0x180019414  nop     dword ptr [rax+rax+00h]
0x180019419  jmp     loc_180019355
```
