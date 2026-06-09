# CCreateDeviceCache::CAdapterCache::CreateLevel9(D3D_FEATURE_LEVEL,IDXGIAdapter *)

- ea: `0x1800a69dc`
- end: `0x1800a6ae4`
- name: `?CreateLevel9@CAdapterCache@CCreateDeviceCache@@QEAAPEAV12@W4D3D_FEATURE_LEVEL@@PEAUIDXGIAdapter@@@Z`
- size: `264`
- prototype: `struct CCreateDeviceCache::CAdapterCache *__fastcall(CCreateDeviceCache::CAdapterCache *__hidden this, enum D3D_FEATURE_LEVEL, struct IDXGIAdapter *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180048670`

## callees

- `0x1800229a0`
- `0x18004948c`
- `0x18005e4a0`
- `0x1800a69dc`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a6a18`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800a6a18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a30`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a6a30`

## string_xrefs

- `0x1800a6a11`: `D3D10Level9.dll`
- `0x1800a6ab1`: `Failed to create 10level9 adapter.`
- `0x1800a6a26`: `D3D11CreateDeviceExternalImplementation`

## pseudocode

```c
struct CCreateDeviceCache::CAdapterCache *__fastcall CCreateDeviceCache::CAdapterCache::CreateLevel9(
        CCreateDeviceCache::CAdapterCache *this,
        enum D3D_FEATURE_LEVEL a2,
        struct IDXGIAdapter *a3)
{
  CCreateDeviceCache::CAdapterCache *v4; // rsi
  int v5; // edi
  _QWORD *v6; // r14
  HMODULE Library; // rbx
  FARPROC ProcAddress; // rax
  int v9; // eax
  __int64 v10; // r9
  __int64 v11; // r9
  HMODULE v13; // [rsp+50h] [rbp+8h] BYREF
  enum D3D_FEATURE_LEVEL v14; // [rsp+58h] [rbp+10h] BYREF

  v14 = a2;
  v4 = this;
  v5 = 0;
  v6 = (_QWORD *)((char *)this + 24);
  if ( !*((_QWORD *)this + 3) )
  {
    v5 = -2005270524;
    Library = LoadLibraryExA("D3D10Level9.dll", 0, 0);
    v13 = Library;
    ProcAddress = GetProcAddress(Library, "D3D11CreateDeviceExternalImplementation");
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(struct IDXGIAdapter *, _QWORD *))ProcAddress)(a3, v6);
      v5 = v9;
      if ( v9 >= 0 )
      {
        (*(void (__fastcall **)(_QWORD, GUID *, __int64, enum D3D_FEATURE_LEVEL *))(*(_QWORD *)*v6 + 24LL))(
          *v6,
          &GUID_DDILevel,
          4,
          &v14);
        v13 = 0;
        UniqueHMODULE::attach((CCreateDeviceCache::CAdapterCache *)((char *)v4 + 8), Library);
      }
      else
      {
        CModule::RecordJournal((CModule *)&g_Module, v9, "D3D10Level9 initialization", v10, 1);
      }
    }
    SafeHMODULE::~SafeHMODULE((SafeHMODULE *)&v13);
    if ( v5 < 0 )
      CModule::RecordJournal((CModule *)&g_Module, v5, "Failed to create 10level9 adapter.", v11, 1);
  }
  if ( v5 < 0 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x1800a69dc  mov     [rsp+arg_10], rbx
0x1800a69e1  mov     [rsp+arg_18], rbp
0x1800a69e6  mov     [rsp+arg_8], edx
0x1800a69ea  push    rsi
0x1800a69eb  push    rdi
0x1800a69ec  push    r14
0x1800a69ee  sub     rsp, 30h
0x1800a69f2  mov     rbp, r8
0x1800a69f5  mov     rsi, rcx
0x1800a69f8  xor     edi, edi
0x1800a69fa  lea     r14, [rcx+18h]
0x1800a69fe  cmp     [r14], rdi
0x1800a6a01  jnz     loc_1800A6AC6
0x1800a6a07  mov     edi, 887A0004h
0x1800a6a0c  xor     r8d, r8d; dwFlags
0x1800a6a0f  xor     edx, edx; hFile
0x1800a6a11  lea     rcx, aD3d10level9Dll; "D3D10Level9.dll"
0x1800a6a18  call    cs:__imp_LoadLibraryExA
0x1800a6a1e  mov     rbx, rax
0x1800a6a21  mov     [rsp+48h+arg_0], rax
0x1800a6a26  lea     rdx, aD3d11createdev_4; "D3D11CreateDeviceExternalImplementation"
0x1800a6a2d  mov     rcx, rax; hModule
0x1800a6a30  call    cs:__imp_GetProcAddress
0x1800a6a36  test    rax, rax
0x1800a6a39  jz      short loc_1800A6A9E
0x1800a6a3b  mov     rdx, r14
0x1800a6a3e  mov     rcx, rbp
0x1800a6a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6a46  mov     edi, eax
0x1800a6a48  test    eax, eax
0x1800a6a4a  jns     short loc_1800A6A68
0x1800a6a4c  mov     [rsp+48h+var_28], 1; bool
0x1800a6a51  lea     r8, aD3d10level9Ini; "D3D10Level9 initialization"
0x1800a6a58  mov     edx, eax; unsigned int
0x1800a6a5a  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800a6a61  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800a6a66  jmp     short loc_1800A6A9E
0x1800a6a68  mov     rcx, [r14]
0x1800a6a6b  mov     rax, [rcx]
0x1800a6a6e  lea     r9, [rsp+48h+arg_8]
0x1800a6a73  mov     r8d, 4
0x1800a6a79  lea     rdx, GUID_DDILevel
0x1800a6a80  mov     rax, [rax+18h]
0x1800a6a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6a89  mov     [rsp+48h+arg_0], 0
0x1800a6a92  lea     rcx, [rsi+8]; this
0x1800a6a96  mov     rdx, rbx; HINSTANCE
0x1800a6a99  call    ?attach@UniqueHMODULE@@QEAAXPEAUHINSTANCE__@@@Z; UniqueHMODULE::attach(HINSTANCE__ *)
0x1800a6a9e  lea     rcx, [rsp+48h+arg_0]; this
0x1800a6aa3  call    ??1SafeHMODULE@@QEAA@XZ; SafeHMODULE::~SafeHMODULE(void)
0x1800a6aa8  test    edi, edi
0x1800a6aaa  jns     short loc_1800A6AC6
0x1800a6aac  mov     [rsp+48h+var_28], 1; bool
0x1800a6ab1  lea     r8, aFailedToCreate; "Failed to create 10level9 adapter."
0x1800a6ab8  mov     edx, edi; unsigned int
0x1800a6aba  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800a6ac1  call    ?RecordJournal@CModule@@QEAAXIPEBD_N1@Z; CModule::RecordJournal(uint,char const *,bool,bool)
0x1800a6ac6  xor     eax, eax
0x1800a6ac8  test    edi, edi
0x1800a6aca  cmovs   rsi, rax
0x1800a6ace  mov     rax, rsi
0x1800a6ad1  mov     rbx, [rsp+48h+arg_10]
0x1800a6ad6  mov     rbp, [rsp+48h+arg_18]
0x1800a6adb  add     rsp, 30h
0x1800a6adf  pop     r14
0x1800a6ae1  pop     rdi
0x1800a6ae2  pop     rsi
0x1800a6ae3  retn
```
