# GetPidFromHandleWorker(void *)

- ea: `0x18002f908`
- end: `0x18002fa02`
- name: `?GetPidFromHandleWorker@@YAKPEAX@Z`
- size: `250`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002fa08`

## callees

- `0x180028c04`
- `0x18002f908`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002f94f`
- `KERNEL32!GetProcAddress` at `0x18002f98e`
- `KERNEL32!GetProcAddress` at `0x18002f94f`
- `KERNEL32!GetProcAddress` at `0x18002f98e`
- `KERNEL32!LoadLibraryW` at `0x18002f927`
- `KERNEL32!LoadLibraryW` at `0x18002f96d`
- `KERNEL32!LoadLibraryW` at `0x18002f927`
- `KERNEL32!LoadLibraryW` at `0x18002f96d`

## string_xrefs

- `0x18002f920`: `kernel32.dll`
- `0x18002f948`: `GetProcessId`
- `0x18002f966`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetPidFromHandleWorker(void *a1)
{
  HMODULE LibraryW; // rcx
  FARPROC ProcAddress; // rax
  unsigned int v4; // ebx
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v8; // [rsp+30h] [rbp-50h] BYREF
  BOOL v9; // [rsp+38h] [rbp-48h]
  HMODULE v10; // [rsp+40h] [rbp-40h] BYREF
  BOOL v11; // [rsp+48h] [rbp-38h]
  _OWORD v12[2]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v13; // [rsp+70h] [rbp-10h]

  LibraryW = LoadLibraryW(L"kernel32.dll");
  v10 = LibraryW;
  v11 = LibraryW != 0;
  if ( !LibraryW )
    goto LABEL_9;
  ProcAddress = GetProcAddress(LibraryW, "GetProcessId");
  if ( !ProcAddress )
  {
    v5 = LoadLibraryW(L"ntdll.dll");
    v8 = v5;
    v9 = v5 != 0;
    if ( v5 )
    {
      v6 = GetProcAddress(v5, "NtQueryInformationProcess");
      if ( v6 )
      {
        memset(v12, 0, sizeof(v12));
        v13 = 0;
        if ( !((unsigned int (__fastcall *)(void *, _QWORD, _OWORD *, __int64, _QWORD))v6)(a1, 0, v12, 48, 0) )
        {
          v4 = v13;
          Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v8);
          goto LABEL_10;
        }
      }
    }
    Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v8);
LABEL_9:
    v4 = 0;
    goto LABEL_10;
  }
  v4 = ((__int64 (__fastcall *)(void *))ProcAddress)(a1);
LABEL_10:
  Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v10);
  return v4;
}

```

## disassembly

```asm
0x18002f908  mov     [rsp-8+arg_0], rbx
0x18002f90d  mov     [rsp-8+arg_8], rdi
0x18002f912  push    rbp
0x18002f913  mov     rbp, rsp
0x18002f916  sub     rsp, 80h
0x18002f91d  mov     rbx, rcx
0x18002f920  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x18002f927  call    cs:__imp_LoadLibraryW
0x18002f92d  mov     rcx, rax; hModule
0x18002f930  mov     [rbp+var_40], rax
0x18002f934  xor     eax, eax
0x18002f936  lea     edi, [rax+1]
0x18002f939  test    rcx, rcx
0x18002f93c  cmovnz  eax, edi
0x18002f93f  mov     [rbp+var_38], eax
0x18002f942  jz      loc_18002F9E0
0x18002f948  lea     rdx, aGetprocessid; "GetProcessId"
0x18002f94f  call    cs:__imp_GetProcAddress
0x18002f955  test    rax, rax
0x18002f958  jz      short loc_18002F966
0x18002f95a  mov     rcx, rbx
0x18002f95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f962  mov     ebx, eax
0x18002f964  jmp     short loc_18002F9E2
0x18002f966  lea     rcx, aNtdllDll; "ntdll.dll"
0x18002f96d  call    cs:__imp_LoadLibraryW
0x18002f973  mov     rcx, rax; hModule
0x18002f976  mov     [rbp+var_50], rax
0x18002f97a  xor     eax, eax
0x18002f97c  test    rcx, rcx
0x18002f97f  cmovnz  eax, edi
0x18002f982  mov     [rbp+var_48], eax
0x18002f985  jz      short loc_18002F9D7
0x18002f987  lea     rdx, aNtqueryinforma; "NtQueryInformationProcess"
0x18002f98e  call    cs:__imp_GetProcAddress
0x18002f994  test    rax, rax
0x18002f997  jz      short loc_18002F9D7
0x18002f999  xorps   xmm0, xmm0
0x18002f99c  movups  [rbp+var_30], xmm0
0x18002f9a0  movups  [rbp+var_20], xmm0
0x18002f9a4  movups  [rbp+var_10], xmm0
0x18002f9a8  mov     [rsp+80h+var_60], 0
0x18002f9b1  mov     r9d, 30h ; '0'
0x18002f9b7  lea     r8, [rbp+var_30]
0x18002f9bb  xor     edx, edx
0x18002f9bd  mov     rcx, rbx
0x18002f9c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f9c5  test    eax, eax
0x18002f9c7  jnz     short loc_18002F9D7
0x18002f9c9  mov     ebx, dword ptr [rbp+var_10]
0x18002f9cc  lea     rcx, [rbp+var_50]
0x18002f9d0  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002f9d5  jmp     short loc_18002F9E2
0x18002f9d7  lea     rcx, [rbp+var_50]
0x18002f9db  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002f9e0  xor     ebx, ebx
0x18002f9e2  lea     rcx, [rbp+var_40]
0x18002f9e6  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002f9eb  mov     eax, ebx
0x18002f9ed  lea     r11, [rsp+80h+var_s0]
0x18002f9f5  mov     rbx, [r11+10h]
0x18002f9f9  mov     rdi, [r11+18h]
0x18002f9fd  mov     rsp, r11
0x18002fa00  pop     rbp
0x18002fa01  retn
```
