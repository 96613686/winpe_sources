# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140035488`
- end: `0x140035584`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `252`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x140035330`
- `0x1400515c0`

## callees

- `0x140035488`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x1400354fd`
- `ADVAPI32!RegDeleteKeyW` at `0x1400354fd`
- `KERNEL32!GetModuleHandleW` at `0x1400354b6`
- `KERNEL32!GetModuleHandleW` at `0x14003552a`
- `KERNEL32!GetModuleHandleW` at `0x1400354b6`
- `KERNEL32!GetModuleHandleW` at `0x14003552a`
- `KERNEL32!GetProcAddress` at `0x1400354cb`
- `KERNEL32!GetProcAddress` at `0x14003553f`
- `KERNEL32!GetProcAddress` at `0x1400354cb`
- `KERNEL32!GetProcAddress` at `0x14003553f`

## string_xrefs

- `0x140035535`: `RegDeleteKeyExW`
- `0x1400354c1`: `RegDeleteKeyTransactedW`
- `0x1400354af`: `Advapi32.dll`
- `0x140035523`: `Advapi32.dll`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  const unsigned __int16 *v3; // rsi
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HKEY v9; // rcx
  HMODULE v10; // rax
  FARPROC v11; // r10

  v2 = *((_QWORD *)this + 2);
  v3 = a2;
  if ( v2 )
  {
    v5 = *(_QWORD *)this;
    if ( *(_QWORD *)v2 )
    {
      ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyTransactedW");
        if ( ProcAddress )
          return ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
                   v5,
                   v3,
                   0,
                   0,
                   *(_QWORD *)v2,
                   0);
      }
      return 1;
    }
    if ( !*(_DWORD *)(v2 + 8) )
      return 1;
    v9 = *(HKEY *)this;
    return RegDeleteKeyW(v9, a2);
  }
  if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
  {
    v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
  }
  else
  {
    v10 = GetModuleHandleW(L"Advapi32.dll");
    if ( v10 )
    {
      v11 = GetProcAddress(v10, "RegDeleteKeyExW");
      `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v11;
    }
    else
    {
      v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
    }
    `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
  }
  v9 = *(HKEY *)this;
  a2 = v3;
  if ( !v11 )
    return RegDeleteKeyW(v9, a2);
  return ((__int64 (__fastcall *)(HKEY, const unsigned __int16 *, _QWORD, _QWORD))v11)(
           v9,
           v3,
           *((unsigned int *)this + 2),
           0);
}

```

## disassembly

```asm
0x140035488  mov     [rsp+arg_0], rbx
0x14003548d  mov     [rsp+arg_8], rsi
0x140035492  push    rdi
0x140035493  sub     rsp, 30h
0x140035497  mov     rdi, [rcx+10h]
0x14003549b  mov     rsi, rdx
0x14003549e  mov     rbx, rcx
0x1400354a1  test    rdi, rdi
0x1400354a4  jz      short loc_14003551A
0x1400354a6  cmp     qword ptr [rdi], 0
0x1400354aa  mov     rbx, [rcx]
0x1400354ad  jz      short loc_1400354F4
0x1400354af  lea     rcx, aAdvapi32Dll_1; "Advapi32.dll"
0x1400354b6  call    cs:__imp_GetModuleHandleW
0x1400354bc  test    rax, rax
0x1400354bf  jz      short loc_140035513
0x1400354c1  lea     rdx, aRegdeletekeytr; "RegDeleteKeyTransactedW"
0x1400354c8  mov     rcx, rax; hModule
0x1400354cb  call    cs:__imp_GetProcAddress
0x1400354d1  test    rax, rax
0x1400354d4  jz      short loc_140035513
0x1400354d6  mov     rdx, [rdi]
0x1400354d9  xor     r9d, r9d
0x1400354dc  and     [rsp+38h+var_10], 0
0x1400354e2  xor     r8d, r8d
0x1400354e5  mov     [rsp+38h+var_18], rdx
0x1400354ea  mov     rcx, rbx
0x1400354ed  mov     rdx, rsi
0x1400354f0  call    rax
0x1400354f2  jmp     short loc_140035503
0x1400354f4  cmp     dword ptr [rdi+8], 0
0x1400354f8  jz      short loc_140035513
0x1400354fa  mov     rcx, rbx; hKey
0x1400354fd  call    cs:__imp_RegDeleteKeyW
0x140035503  mov     rbx, [rsp+38h+arg_0]
0x140035508  mov     rsi, [rsp+38h+arg_8]
0x14003550d  add     rsp, 30h
0x140035511  pop     rdi
0x140035512  retn
0x140035513  mov     eax, 1
0x140035518  jmp     short loc_140035503
0x14003551a  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, 0; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x140035521  jnz     short loc_140035565
0x140035523  lea     rcx, aAdvapi32Dll_1; "Advapi32.dll"
0x14003552a  call    cs:__imp_GetModuleHandleW
0x140035530  test    rax, rax
0x140035533  jz      short loc_140035551
0x140035535  lea     rdx, aRegdeletekeyex_0; "RegDeleteKeyExW"
0x14003553c  mov     rcx, rax; hModule
0x14003553f  call    cs:__imp_GetProcAddress
0x140035545  mov     r10, rax
0x140035548  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x14003554f  jmp     short loc_140035558
0x140035551  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x140035558  mov     eax, 1
0x14003555d  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4_NA, al; bool `ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::bInitialized
0x140035563  jmp     short loc_14003556C
0x140035565  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(ushort const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,ushort const *,ulong,ulong)
0x14003556c  mov     rcx, [rbx]
0x14003556f  mov     rdx, rsi
0x140035572  test    r10, r10
0x140035575  jz      short loc_1400354FD
0x140035577  mov     r8d, [rbx+8]
0x14003557b  xor     r9d, r9d
0x14003557e  call    r10
0x140035581  jmp     short loc_140035503
```
