# PEH_Buffer_ListenerState_SetListener

- ea: `0x18003f858`
- end: `0x18003f9bb`
- name: `PEH_Buffer_ListenerState_SetListener`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18003f5d0`

## callees

- `0x180006ef8`
- `0x18003f858`
- `0x180042c5c`
- `0x180042ecc`
- `0x180043120`
- `0x1800431f0`
- `0x18004370c`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003f891`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x18003f891`

## string_xrefs

- `0x18003f885`: `mpunits.dll`

## pseudocode

```c
const MI_InstanceFT *__fastcall PEH_Buffer_ListenerState_SetListener(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax
  int String_LoadString; // eax
  const MI_InstanceFT *result; // rax
  int v7; // edi
  int v8; // edi
  MI_Instance *extendedError; // [rsp+50h] [rbp+8h] BYREF

  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), 1, 0) )
  {
    ((void (__fastcall *)(__int64))ObserverProtocol_AddRef)(a2);
    if ( !(unsigned int)TryAcquireWrite(a1 + 40) )
      QueueAcquireWrite(a1 + 40);
    v7 = *(_DWORD *)(a1 + 20);
    if ( !v7 )
      *(_QWORD *)a1 = a2;
    ReadWriteLock_ReleaseWrite((volatile signed __int64 *)(a1 + 40));
    if ( !v7 )
      return (const MI_InstanceFT *)CondLock_Broadcast(a1);
    v8 = v7 - 2;
    if ( v8 )
    {
      if ( v8 == 1 )
        ((void (__fastcall *)(__int64))ObserverProtocol_PostCompleted)(a2);
    }
    else
    {
      ((void (__fastcall *)(__int64, _QWORD, _QWORD))ObserverProtocol_PostError)(
        a2,
        *(unsigned int *)(a1 + 24),
        *(_QWORD *)(a1 + 32));
    }
    _InterlockedExchange64((volatile __int64 *)(a1 + 8), 0);
    result = (const MI_InstanceFT *)&s_observerProtocolFT;
    return (const MI_InstanceFT *)((__int64 (*)(void))result->Delete)();
  }
  extendedError = 0;
  ModuleHandleA = GetModuleHandleA("mpunits.dll");
  String_LoadString = Intlstr_GetString_LoadString(ModuleHandleA, 2137);
  CreateOMIError_shared(String_LoadString, 11, (int)L"MI", 19, (__int64)&OMI_Error_rtti, &extendedError);
  result = (const MI_InstanceFT *)((__int64 (__fastcall *)(__int64, __int64, MI_Instance *))ObserverProtocol_PostError)(
                                    a2,
                                    11,
                                    extendedError);
  if ( extendedError )
  {
    result = extendedError->ft;
    if ( extendedError->ft )
      return (const MI_InstanceFT *)((__int64 (*)(void))result->Delete)();
  }
  return result;
}

```

## disassembly

```asm
0x18003f858  mov     [rsp+arg_8], rbx
0x18003f85d  mov     [rsp+arg_10], rbp
0x18003f862  push    rsi
0x18003f863  push    rdi
0x18003f864  push    r14
0x18003f866  sub     rsp, 30h
0x18003f86a  mov     rbx, rcx
0x18003f86d  mov     rbp, rdx
0x18003f870  mov     ecx, 1
0x18003f875  xor     eax, eax
0x18003f877  lock cmpxchg [rbx+8], rcx
0x18003f87d  jz      loc_18003F90B
0x18003f883  xor     esi, esi
0x18003f885  lea     rcx, ModuleName; "mpunits.dll"
0x18003f88c  mov     [rsp+48h+arg_0], rsi
0x18003f891  call    cs:__imp_GetModuleHandleA
0x18003f897  mov     rcx, rax
0x18003f89a  mov     edx, 859h
0x18003f89f  call    _Intlstr_GetString_LoadString
0x18003f8a4  lea     rcx, [rsp+48h+arg_0]
0x18003f8a9  mov     [rsp+48h+extendedError], rcx; extendedError
0x18003f8ae  lea     ebx, [rsi+0Bh]
0x18003f8b1  lea     rcx, OMI_Error_rtti
0x18003f8b8  mov     edx, ebx; int
0x18003f8ba  mov     [rsp+48h+var_28], rcx; __int64
0x18003f8bf  lea     r9d, [rsi+13h]; int
0x18003f8c3  mov     rcx, rax; int
0x18003f8c6  lea     r8, aMi; "MI"
0x18003f8cd  call    CreateOMIError_shared
0x18003f8d2  mov     rax, cs:off_180047BB0
0x18003f8d9  mov     edx, ebx
0x18003f8db  mov     r8, [rsp+48h+arg_0]
0x18003f8e0  mov     rcx, rbp
0x18003f8e3  mov     rax, [rax+50h]
0x18003f8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8ec  mov     rcx, [rsp+48h+arg_0]
0x18003f8f1  test    rcx, rcx
0x18003f8f4  jz      loc_18003F9A8
0x18003f8fa  mov     rax, [rcx]
0x18003f8fd  test    rax, rax
0x18003f900  jz      loc_18003F9A8
0x18003f906  jmp     loc_18003F99F
0x18003f90b  mov     rax, cs:off_180047BB0
0x18003f912  mov     rcx, rbp
0x18003f915  mov     rax, [rax+8]
0x18003f919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f91e  lea     r14, [rbx+28h]
0x18003f922  mov     rcx, r14
0x18003f925  call    TryAcquireWrite
0x18003f92a  xor     esi, esi
0x18003f92c  test    eax, eax
0x18003f92e  jnz     short loc_18003F938
0x18003f930  mov     rcx, r14
0x18003f933  call    QueueAcquireWrite
0x18003f938  mov     edi, [rbx+14h]
0x18003f93b  test    edi, edi
0x18003f93d  jnz     short loc_18003F942
0x18003f93f  mov     [rbx], rbp
0x18003f942  mov     rcx, r14
0x18003f945  call    ReadWriteLock_ReleaseWrite
0x18003f94a  test    edi, edi
0x18003f94c  jnz     short loc_18003F958
0x18003f94e  mov     rcx, rbx
0x18003f951  call    CondLock_Broadcast
0x18003f956  jmp     short loc_18003F9A8
0x18003f958  sub     edi, 2
0x18003f95b  jz      short loc_18003F977
0x18003f95d  cmp     edi, 1
0x18003f960  jnz     short loc_18003F991
0x18003f962  mov     rax, cs:off_180047BB0
0x18003f969  mov     rcx, rbp
0x18003f96c  mov     rax, [rax+30h]
0x18003f970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f975  jmp     short loc_18003F991
0x18003f977  mov     rax, cs:off_180047BB0
0x18003f97e  mov     rcx, rbp
0x18003f981  mov     r8, [rbx+20h]
0x18003f985  mov     edx, [rbx+18h]
0x18003f988  mov     rax, [rax+50h]
0x18003f98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f991  xchg    rsi, [rbx+8]
0x18003f995  mov     rax, cs:off_180047BB0
0x18003f99c  mov     rcx, rbp
0x18003f99f  mov     rax, [rax+10h]
0x18003f9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9a8  mov     rbx, [rsp+48h+arg_8]
0x18003f9ad  mov     rbp, [rsp+48h+arg_10]
0x18003f9b2  add     rsp, 30h
0x18003f9b6  pop     r14
0x18003f9b8  pop     rdi
0x18003f9b9  pop     rsi
0x18003f9ba  retn
```
