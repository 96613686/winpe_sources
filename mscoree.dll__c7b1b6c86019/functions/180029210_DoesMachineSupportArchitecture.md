# DoesMachineSupportArchitecture

- ea: `0x180029210`
- end: `0x1800292cb`
- name: `DoesMachineSupportArchitecture`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002dfb4`

## callees

- `0x180028c04`
- `0x180029210`
- `0x18002a7c8`
- `0x180045020`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18002926d`
- `KERNEL32!GetProcAddress` at `0x18002926d`
- `KERNEL32!LoadLibraryW` at `0x180029241`
- `KERNEL32!LoadLibraryW` at `0x180029241`

## string_xrefs

- `0x18002923a`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DoesMachineSupportArchitecture(unsigned int a1)
{
  HMODULE LibraryW; // rcx
  unsigned int LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v6; // [rsp+20h] [rbp-48h] BYREF
  BOOL v7; // [rsp+28h] [rbp-40h]
  _WORD v8[28]; // [rsp+30h] [rbp-38h] BYREF

  if ( a1 > 1 )
  {
    memset(v8, 0, 48);
    LibraryW = LoadLibraryW(L"kernel32.dll");
    v6 = LibraryW;
    v7 = LibraryW != 0;
    if ( !LibraryW )
    {
      LastError = HRESULT_FROM_GetLastError();
LABEL_12:
      Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v6);
      return LastError;
    }
    ProcAddress = GetProcAddress(LibraryW, "GetNativeSystemInfo");
    if ( !ProcAddress )
    {
      LastError = 1;
      goto LABEL_12;
    }
    ((void (__fastcall *)(_WORD *))ProcAddress)(v8);
    if ( v8[0] == 6 )
    {
      if ( a1 != 3 )
      {
LABEL_8:
        Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(&v6);
        return 1;
      }
    }
    else if ( v8[0] != 9 || a1 != 2 )
    {
      goto LABEL_8;
    }
    LastError = 0;
    goto LABEL_12;
  }
  return 0;
}

```

## disassembly

```asm
0x180029210  mov     rax, rsp
0x180029213  mov     [rax+8], rbx
0x180029217  push    rdi
0x180029218  sub     rsp, 60h
0x18002921c  mov     ebx, ecx
0x18002921e  mov     edi, 1
0x180029223  cmp     ecx, edi
0x180029225  jbe     loc_1800292BE
0x18002922b  xorps   xmm0, xmm0
0x18002922e  movups  xmmword ptr [rax-38h], xmm0
0x180029232  movups  xmmword ptr [rax-28h], xmm0
0x180029236  movups  xmmword ptr [rax-18h], xmm0
0x18002923a  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180029241  call    cs:__imp_LoadLibraryW
0x180029247  mov     rcx, rax; hModule
0x18002924a  mov     [rsp+68h+var_48], rax
0x18002924f  xor     eax, eax
0x180029251  test    rcx, rcx
0x180029254  cmovnz  eax, edi
0x180029257  mov     [rsp+68h+var_40], eax
0x18002925b  jnz     short loc_180029266
0x18002925d  call    ?HRESULT_FROM_GetLastError@@YAJXZ; HRESULT_FROM_GetLastError(void)
0x180029262  mov     ebx, eax
0x180029264  jmp     short loc_1800292B0
0x180029266  lea     rdx, aGetnativesyste; "GetNativeSystemInfo"
0x18002926d  call    cs:__imp_GetProcAddress
0x180029273  test    rax, rax
0x180029276  jnz     short loc_18002927C
0x180029278  mov     ebx, edi
0x18002927a  jmp     short loc_1800292B0
0x18002927c  lea     rcx, [rsp+68h+var_38]
0x180029281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029286  cmp     [rsp+68h+var_38], 6
0x18002928c  jnz     short loc_1800292A1
0x18002928e  cmp     ebx, 3
0x180029291  jz      short loc_1800292AE
0x180029293  lea     rcx, [rsp+68h+var_48]
0x180029298  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x18002929d  mov     eax, edi
0x18002929f  jmp     short loc_1800292C0
0x1800292a1  cmp     [rsp+68h+var_38], 9
0x1800292a7  jnz     short loc_180029293
0x1800292a9  cmp     ebx, 2
0x1800292ac  jnz     short loc_180029293
0x1800292ae  xor     ebx, ebx
0x1800292b0  lea     rcx, [rsp+68h+var_48]
0x1800292b5  call    ??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ; Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)
0x1800292ba  mov     eax, ebx
0x1800292bc  jmp     short loc_1800292C0
0x1800292be  xor     eax, eax
0x1800292c0  mov     rbx, [rsp+68h+arg_0]
0x1800292c5  add     rsp, 60h
0x1800292c9  pop     rdi
0x1800292ca  retn
```
