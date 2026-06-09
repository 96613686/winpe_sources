# CRpcUtils::GetRpcCallerInfo(ulong *,ulong *,ulong,ushort *)

- ea: `0x18001b090`
- end: `0x18001b199`
- name: `?GetRpcCallerInfo@CRpcUtils@@SAJPEAK0KPEAG@Z`
- size: `265`
- prototype: `__int64 __fastcall(DWORD *pSessionId, unsigned int *, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180031400`

## callees

- `0x18001aa50`
- `0x18001b090`
- `0x18004b460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b167`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001b167`
- `ntdll!NtQueryInformationProcess` at `0x18001b14d`
- `ntdll!NtQueryInformationProcess` at `0x18001b14d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b0df`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001b0df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b18e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b18e`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b0ca`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001b0ca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b123`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001b123`

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
0x18001b090  push    rbx
0x18001b092  push    rbp
0x18001b093  push    rsi
0x18001b094  push    rdi
0x18001b095  push    r14
0x18001b097  sub     rsp, 150h
0x18001b09e  mov     rax, cs:__security_cookie
0x18001b0a5  xor     rax, rsp
0x18001b0a8  mov     [rsp+178h+var_38], rax
0x18001b0b0  mov     dword ptr [rcx], 0FFFFFFFFh
0x18001b0b6  mov     rsi, rcx
0x18001b0b9  xor     ecx, ecx; Binding
0x18001b0bb  mov     ebp, r8d
0x18001b0be  mov     r14, r9
0x18001b0c1  mov     dword ptr [rdx], 0FFFFFFFFh
0x18001b0c7  mov     rdi, rdx
0x18001b0ca  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001b0d0  mov     ebx, eax
0x18001b0d2  test    eax, eax
0x18001b0d4  jg      short loc_18001B109
0x18001b0d6  test    ebx, ebx
0x18001b0d8  js      short loc_18001B0E9
0x18001b0da  mov     ecx, [rdi]; dwProcessId
0x18001b0dc  mov     rdx, rsi; pSessionId
0x18001b0df  call    cs:__imp_ProcessIdToSessionId
0x18001b0e5  test    ebp, ebp
0x18001b0e7  jnz     short loc_18001B114
0x18001b0e9  mov     eax, ebx
0x18001b0eb  mov     rcx, [rsp+178h+var_38]
0x18001b0f3  xor     rcx, rsp; StackCookie
0x18001b0f6  call    __security_check_cookie
0x18001b0fb  add     rsp, 150h
0x18001b102  pop     r14
0x18001b104  pop     rdi
0x18001b105  pop     rsi
0x18001b106  pop     rbp
0x18001b107  pop     rbx
0x18001b108  retn
0x18001b109  movzx   ebx, ax
0x18001b10c  or      ebx, 80070000h
0x18001b112  jmp     short loc_18001B0D6
0x18001b114  test    r14, r14
0x18001b117  jz      short loc_18001B0E9
0x18001b119  mov     r8d, [rdi]; dwProcessId
0x18001b11c  xor     edx, edx; bInheritHandle
0x18001b11e  mov     ecx, 400h; dwDesiredAccess
0x18001b123  call    cs:__imp_OpenProcess
0x18001b129  mov     rdi, rax
0x18001b12c  test    rax, rax
0x18001b12f  jz      short loc_18001B0E9
0x18001b131  mov     r9d, 110h; ProcessInformationLength
0x18001b137  mov     [rsp+178h+ReturnLength], 0; ReturnLength
0x18001b140  lea     r8, [rsp+178h+ProcessInformation]; ProcessInformation
0x18001b145  mov     edx, 1Bh; ProcessInformationClass
0x18001b14a  mov     rcx, rax; ProcessHandle
0x18001b14d  call    cs:__imp_NtQueryInformationProcess
0x18001b153  mov     ebx, eax
0x18001b155  or      ebx, 10000000h
0x18001b15b  jl      short loc_18001B18B
0x18001b15d  mov     rcx, [rsp+178h+Str]; Str
0x18001b162  mov     edx, 5Ch ; '\'; Ch
0x18001b167  call    cs:__imp_wcsrchr
0x18001b16d  test    rax, rax
0x18001b170  jnz     short loc_18001B179
0x18001b172  mov     rax, [rsp+178h+Str]
0x18001b177  jmp     short loc_18001B17D
0x18001b179  add     rax, 2
0x18001b17d  mov     rdx, rbp; unsigned __int64
0x18001b180  mov     r8, rax; unsigned __int16 *
0x18001b183  mov     rcx, r14; unsigned __int16 *
0x18001b186  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001b18b  mov     rcx, rdi; hObject
0x18001b18e  call    cs:__imp_CloseHandle
0x18001b194  jmp     loc_18001B0E9
```
