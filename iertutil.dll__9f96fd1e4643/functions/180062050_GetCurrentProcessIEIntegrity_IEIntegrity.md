# GetCurrentProcessIEIntegrity(_IEIntegrity *)

- ea: `0x180062050`
- end: `0x18006215e`
- name: `?GetCurrentProcessIEIntegrity@@YAJPEAW4_IEIntegrity@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(enum _IEIntegrity *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180018410`
- `0x180031f00`
- `0x180062050`
- `0x180062164`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062136`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180062136`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006206d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18006206d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062083`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180062083`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006212e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006212e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800620e8`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800620e8`

## pseudocode

```c
__int64 __fastcall GetCurrentProcessIEIntegrity(enum _IEIntegrity *a1)
{
  HANDLE CurrentProcess; // rax
  __int64 String; // r14
  __int64 v4; // rbp
  char Bool; // si
  char v6; // al
  void *v7; // rdi
  char v8; // bl
  __int64 v9; // r8
  __int64 v10; // rdx
  int v11; // ebx
  signed int LastError; // eax
  unsigned int v14; // [rsp+78h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v14 = 0;
    String = IEConfiguration_GetString(268435507);
    v4 = IEConfiguration_GetString(268435506);
    Bool = IEConfiguration_GetBool(268435520);
    v6 = IEConfiguration_GetBool(268435519);
    v7 = TokenHandle;
    v8 = v6;
    InitOnceExecuteOnce(&g_InitOnce, LoadIsoDll, 0, 0);
    LOBYTE(v9) = Bool;
    LOBYTE(v10) = v8;
    v11 = ((__int64 (__fastcall *)(void *, __int64, __int64, __int64, __int64, unsigned int *))qword_1802A3070)(
            v7,
            v10,
            v9,
            v4,
            String,
            &v14);
    if ( v11 >= 0 )
      *(_DWORD *)a1 = GetIEIntegrityFromIsoIntegrity(v14);
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180062050  mov     rax, rsp
0x180062053  mov     [rax+8], rbx
0x180062057  push    rbp
0x180062058  push    rsi
0x180062059  push    rdi
0x18006205a  push    r14
0x18006205c  push    r15
0x18006205e  sub     rsp, 40h
0x180062062  mov     r15, rcx
0x180062065  mov     qword ptr [rax+18h], 0
0x18006206d  call    cs:__imp_GetCurrentProcess
0x180062073  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x18006207b  mov     edx, 8; DesiredAccess
0x180062080  mov     rcx, rax; ProcessHandle
0x180062083  call    cs:__imp_OpenProcessToken
0x180062089  test    eax, eax
0x18006208b  jz      loc_180062136
0x180062091  mov     ecx, 10000033h
0x180062096  mov     [rsp+68h+arg_8], 0
0x18006209e  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800620a3  mov     ecx, 10000032h
0x1800620a8  mov     r14, rax
0x1800620ab  call    ?IEConfiguration_GetString@@YAPEBGW4IEConfigurationID@@@Z; IEConfiguration_GetString(IEConfigurationID)
0x1800620b0  mov     ecx, 10000040h
0x1800620b5  mov     rbp, rax
0x1800620b8  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800620bd  mov     ecx, 1000003Fh
0x1800620c2  mov     sil, al
0x1800620c5  call    ?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1800620ca  mov     rdi, [rsp+68h+TokenHandle]
0x1800620d2  lea     rdx, ?LoadIsoDll@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800620d9  xor     r9d, r9d; Context
0x1800620dc  lea     rcx, ?g_InitOnce@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800620e3  xor     r8d, r8d; Parameter
0x1800620e6  mov     bl, al
0x1800620e8  call    cs:__imp_InitOnceExecuteOnce
0x1800620ee  lea     rax, [rsp+68h+arg_8]
0x1800620f3  mov     r9, rbp
0x1800620f6  mov     [rsp+68h+var_40], rax
0x1800620fb  mov     r8b, sil
0x1800620fe  mov     rax, cs:qword_1802A3070
0x180062105  mov     dl, bl
0x180062107  mov     rcx, rdi
0x18006210a  mov     [rsp+68h+var_48], r14
0x18006210f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062114  mov     ebx, eax
0x180062116  test    eax, eax
0x180062118  js      short loc_180062126
0x18006211a  mov     ecx, [rsp+68h+arg_8]
0x18006211e  call    GetIEIntegrityFromIsoIntegrity
0x180062123  mov     [r15], eax
0x180062126  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18006212e  call    cs:__imp_CloseHandle
0x180062134  jmp     short loc_18006214B
0x180062136  call    cs:__imp_GetLastError
0x18006213c  mov     ebx, eax
0x18006213e  test    eax, eax
0x180062140  jle     short loc_18006214B
0x180062142  movzx   ebx, ax
0x180062145  or      ebx, 80070000h
0x18006214b  mov     eax, ebx
0x18006214d  mov     rbx, [rsp+68h+arg_0]
0x180062152  add     rsp, 40h
0x180062156  pop     r15
0x180062158  pop     r14
0x18006215a  pop     rdi
0x18006215b  pop     rsi
0x18006215c  pop     rbp
0x18006215d  retn
```
