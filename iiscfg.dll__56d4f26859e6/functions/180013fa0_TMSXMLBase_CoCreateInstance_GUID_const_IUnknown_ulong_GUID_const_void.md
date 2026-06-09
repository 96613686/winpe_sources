# TMSXMLBase::CoCreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)

- ea: `0x180013fa0`
- end: `0x18001407f`
- name: `?CoCreateInstance@TMSXMLBase@@MEBAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z`
- size: `223`
- prototype: `int(TMSXMLBase *__hidden this, const struct _GUID *, struct IUnknown *, unsigned int, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800066f0`
- `0x18001bd40`

## callees

- `0x180001f70`
- `0x180013fa0`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180014021`
- `KERNEL32!GetProcAddress` at `0x180014021`
- `KERNEL32!LoadLibraryW` at `0x180013ff5`
- `KERNEL32!LoadLibraryW` at `0x180013ff5`
- `KERNEL32!GetLastError` at `0x180014000`
- `KERNEL32!GetLastError` at `0x180014000`
- `ole32!CoCreateInstance` at `0x180013fdf`
- `ole32!CoCreateInstance` at `0x180013fdf`

## string_xrefs

- `0x180013fee`: `msxml3.dll`
- `0x180014017`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall TMSXMLBase::CoCreateInstance(
        TMSXMLBase *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        DWORD a4,
        const struct _GUID *riid,
        void **a6)
{
  int Instance; // ebx
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  _QWORD v12[3]; // [rsp+30h] [rbp-18h] BYREF

  v12[0] = 0;
  *a6 = 0;
  Instance = CoCreateInstance(a2, a3, a4, riid, a6);
  if ( Instance == -2147221164 )
  {
    LibraryW = LoadLibraryW(L"msxml3.dll");
    if ( LibraryW && (ProcAddress = GetProcAddress(LibraryW, "DllGetClassObject")) != 0 )
    {
      Instance = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, _QWORD *))ProcAddress)(
                   a2,
                   &IID_IClassFactory,
                   v12);
      if ( Instance >= 0 )
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _GUID *, void **))(*(_QWORD *)v12[0] + 24LL))(
                     v12[0],
                     0,
                     riid,
                     a6);
    }
    else
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
    }
  }
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(v12);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180013fa0  mov     r11, rsp
0x180013fa3  mov     [r11+8], rbx
0x180013fa7  mov     [r11+10h], rsi
0x180013fab  push    rdi
0x180013fac  sub     rsp, 40h
0x180013fb0  mov     rdi, [rsp+48h+arg_28]
0x180013fb5  mov     eax, r9d
0x180013fb8  mov     r9, [rsp+48h+riid]; riid
0x180013fbd  mov     r10, r8
0x180013fc0  mov     rsi, rdx
0x180013fc3  mov     qword ptr [r11-18h], 0
0x180013fcb  mov     r8d, eax; dwClsContext
0x180013fce  mov     [r11-28h], rdi
0x180013fd2  mov     rdx, r10; pUnkOuter
0x180013fd5  mov     qword ptr [rdi], 0
0x180013fdc  mov     rcx, rsi; rclsid
0x180013fdf  call    cs:__imp_CoCreateInstance
0x180013fe5  mov     ebx, eax
0x180013fe7  cmp     eax, 80040154h
0x180013fec  jnz     short loc_180014063
0x180013fee  lea     rcx, LibFileName; "msxml3.dll"
0x180013ff5  call    cs:__imp_LoadLibraryW
0x180013ffb  test    rax, rax
0x180013ffe  jnz     short loc_180014017
0x180014000  call    cs:__imp_GetLastError
0x180014006  mov     ebx, eax
0x180014008  test    eax, eax
0x18001400a  jle     short loc_180014063
0x18001400c  movzx   ebx, ax
0x18001400f  or      ebx, 80070000h
0x180014015  jmp     short loc_180014063
0x180014017  lea     rdx, ProcName; "DllGetClassObject"
0x18001401e  mov     rcx, rax; hModule
0x180014021  call    cs:__imp_GetProcAddress
0x180014027  test    rax, rax
0x18001402a  jz      short loc_180014000
0x18001402c  lea     r8, [rsp+48h+var_18]
0x180014031  mov     rcx, rsi
0x180014034  lea     rdx, IID_IClassFactory
0x18001403b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014040  mov     ebx, eax
0x180014042  test    eax, eax
0x180014044  js      short loc_180014063
0x180014046  mov     rcx, [rsp+48h+var_18]
0x18001404b  mov     r9, rdi
0x18001404e  mov     r8, [rsp+48h+riid]
0x180014053  xor     edx, edx
0x180014055  mov     rax, [rcx]
0x180014058  mov     rax, [rax+18h]
0x18001405c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014061  mov     ebx, eax
0x180014063  lea     rcx, [rsp+48h+var_18]
0x180014068  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18001406d  mov     rsi, [rsp+48h+arg_8]
0x180014072  mov     eax, ebx
0x180014074  mov     rbx, [rsp+48h+arg_0]
0x180014079  add     rsp, 40h
0x18001407d  pop     rdi
0x18001407e  retn
```
