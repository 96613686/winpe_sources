# Win32LiveSystemProvider::StartProcessEnum(void *,ulong)

- ea: `0x180015cf0`
- end: `0x180015ea0`
- name: `?StartProcessEnum@Win32LiveSystemProvider@@UEAAJPEAXK@Z`
- size: `432`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180026700`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180014780`
- `0x180015cf0`
- `0x18002c010`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180015d5b`
- `ntdll!NtQuerySystemInformation` at `0x180015d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015e1f`

## string_xrefs

- `0x180015db5`: `LoadNtDeviceMapCache failed, 0x%08x`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::StartProcessEnum(
        Win32LiveSystemProvider *this,
        void *a2,
        unsigned int a3)
{
  signed int result; // eax
  int v7; // edi
  NTSTATUS v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned int NtDeviceMapCache; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  _BYTE SystemInformation[40]; // [rsp+30h] [rbp-68h] BYREF
  __int64 v15; // [rsp+58h] [rbp-40h]

  if ( !*((_QWORD *)this + 39) )
    return -2147467263;
  v7 = 1;
  *((_DWORD *)this + 204) = 1;
  memset_0(SystemInformation, 0, 0x40u);
  v8 = NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  v10 = (unsigned int)v8;
  if ( v8 >= 0 )
  {
    *((_QWORD *)this + 103) = v15;
  }
  else
  {
    (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 7) + 8LL))(
      *((_QWORD *)this + 7),
      1,
      "NtQuerySystemInformation failed, 0x%08x",
      (unsigned int)v8);
    *((_DWORD *)this + 204) = 0;
  }
  if ( *((_DWORD *)this + 204) )
  {
    NtDeviceMapCache = Win32LiveSystemProvider::LoadNtDeviceMapCache(this);
    v10 = NtDeviceMapCache;
    if ( NtDeviceMapCache )
    {
      (*(void (**)(_QWORD, __int64, const char *, ...))(**((_QWORD **)this + 7) + 8LL))(
        *((_QWORD *)this + 7),
        1,
        "LoadNtDeviceMapCache failed, 0x%08x",
        NtDeviceMapCache);
      *((_DWORD *)this + 204) = 0;
    }
  }
  if ( *((_DWORD *)this + 16) == 2 )
  {
    v12 = 4;
    if ( *((_DWORD *)this + 17) >= 0x9A5u )
    {
      *((_DWORD *)this + 170) = 0;
      v12 = 28;
    }
  }
  else
  {
    *((_DWORD *)this + 170) = 1;
    v12 = 12;
  }
  v13 = (*((__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64))this + 39))(v12, a3, v9, v10);
  *((_QWORD *)this + 84) = v13;
  if ( v13 != -1 )
    goto LABEL_17;
  result = GetLastError();
  if ( result == 234 )
  {
    if ( *((_DWORD *)this + 204) )
    {
      v7 = 0;
LABEL_17:
      *((_DWORD *)this + 205) = v7;
      result = 0;
      *((_QWORD *)this + 82) = a2;
      *((_DWORD *)this + 166) = a3;
      *(_QWORD *)((char *)this + 684) = 0;
      *((_QWORD *)this + 87) = 0;
      *((_QWORD *)this + 88) = 0;
      return result;
    }
    return (unsigned __int16)result | 0x80070000;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180015cf0  mov     [rsp+arg_8], rbx
0x180015cf5  mov     [rsp+arg_18], rbp
0x180015cfa  push    rsi
0x180015cfb  push    rdi
0x180015cfc  push    r14
0x180015cfe  sub     rsp, 80h
0x180015d05  mov     rax, cs:__security_cookie
0x180015d0c  xor     rax, rsp
0x180015d0f  mov     [rsp+98h+var_28], rax
0x180015d14  cmp     qword ptr [rcx+138h], 0
0x180015d1c  mov     ebp, r8d
0x180015d1f  mov     r14, rdx
0x180015d22  mov     rbx, rcx
0x180015d25  jnz     short loc_180015D31
0x180015d27  mov     eax, 80004001h
0x180015d2c  jmp     loc_180015E6D
0x180015d31  mov     edi, 1
0x180015d36  xor     edx, edx; Val
0x180015d38  mov     [rcx+330h], edi
0x180015d3e  lea     rcx, [rsp+98h+SystemInformation]; void *
0x180015d43  lea     esi, [rdi+3Fh]
0x180015d46  mov     r8d, esi; Size
0x180015d49  call    memset_0
0x180015d4e  xor     r9d, r9d; ReturnLength
0x180015d51  lea     rdx, [rsp+98h+SystemInformation]; SystemInformation
0x180015d56  mov     r8d, esi; SystemInformationLength
0x180015d59  xor     ecx, ecx; SystemInformationClass
0x180015d5b  call    cs:__imp_NtQuerySystemInformation
0x180015d61  mov     r9d, eax
0x180015d64  test    eax, eax
0x180015d66  jns     short loc_180015D8D
0x180015d68  mov     rcx, [rbx+38h]
0x180015d6c  lea     r8, aNtquerysystemi; "NtQuerySystemInformation failed, 0x%08x"
0x180015d73  mov     rdx, [rcx]
0x180015d76  mov     rax, [rdx+8]
0x180015d7a  mov     edx, edi
0x180015d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d81  mov     dword ptr [rbx+330h], 0
0x180015d8b  jmp     short loc_180015D99
0x180015d8d  mov     rax, [rsp+98h+var_40]
0x180015d92  mov     [rbx+338h], rax
0x180015d99  cmp     dword ptr [rbx+330h], 0
0x180015da0  jz      short loc_180015DD4
0x180015da2  mov     rcx, rbx; this
0x180015da5  call    ?LoadNtDeviceMapCache@Win32LiveSystemProvider@@AEAAJXZ; Win32LiveSystemProvider::LoadNtDeviceMapCache(void)
0x180015daa  mov     r9d, eax
0x180015dad  test    eax, eax
0x180015daf  jz      short loc_180015DD4
0x180015db1  mov     rcx, [rbx+38h]
0x180015db5  lea     r8, aLoadntdevicema; "LoadNtDeviceMapCache failed, 0x%08x"
0x180015dbc  mov     rdx, [rcx]
0x180015dbf  mov     rax, [rdx+8]
0x180015dc3  mov     edx, edi
0x180015dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dca  mov     dword ptr [rbx+330h], 0
0x180015dd4  cmp     dword ptr [rbx+40h], 2
0x180015dd8  jnz     short loc_180015DF9
0x180015dda  cmp     dword ptr [rbx+44h], 9A5h
0x180015de1  mov     ecx, 4
0x180015de6  jb      short loc_180015E04
0x180015de8  mov     dword ptr [rbx+2A8h], 0
0x180015df2  mov     ecx, 1Ch
0x180015df7  jmp     short loc_180015E04
0x180015df9  mov     [rbx+2A8h], edi
0x180015dff  mov     ecx, 0Ch
0x180015e04  mov     rax, [rbx+138h]
0x180015e0b  mov     edx, ebp
0x180015e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e12  mov     [rbx+2A0h], rax
0x180015e19  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015e1d  jnz     short loc_180015E37
0x180015e1f  call    cs:__imp_GetLastError
0x180015e25  cmp     eax, 0EAh
0x180015e2a  jnz     short loc_180015E92
0x180015e2c  cmp     dword ptr [rbx+330h], 0
0x180015e33  jz      short loc_180015E96
0x180015e35  xor     edi, edi
0x180015e37  mov     [rbx+334h], edi
0x180015e3d  xor     eax, eax
0x180015e3f  mov     [rbx+290h], r14
0x180015e46  mov     [rbx+298h], ebp
0x180015e4c  mov     qword ptr [rbx+2ACh], 0
0x180015e57  mov     qword ptr [rbx+2B8h], 0
0x180015e62  mov     qword ptr [rbx+2C0h], 0
0x180015e6d  mov     rcx, [rsp+98h+var_28]
0x180015e72  xor     rcx, rsp; StackCookie
0x180015e75  call    __security_check_cookie
0x180015e7a  lea     r11, [rsp+98h+var_18]
0x180015e82  mov     rbx, [r11+28h]
0x180015e86  mov     rbp, [r11+38h]
0x180015e8a  mov     rsp, r11
0x180015e8d  pop     r14
0x180015e8f  pop     rdi
0x180015e90  pop     rsi
0x180015e91  retn
0x180015e92  test    eax, eax
0x180015e94  jle     short loc_180015E6D
0x180015e96  movzx   eax, ax
0x180015e99  or      eax, 80070000h
0x180015e9e  jmp     short loc_180015E6D
```
