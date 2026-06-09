# IsCapabilityAce_(_ACE_HEADER *)

- ea: `0x180005ef0`
- end: `0x180005fbb`
- name: `?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _ACE_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180005a50`

## callees

- `0x180005ef0`
- `0x18003a730`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005fa9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005fa9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005f1f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005f1f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f56`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005f56`
- `ntdll!RtlEqualSid` at `0x180005f9c`
- `ntdll!RtlEqualSid` at `0x180005f9c`

## string_xrefs

- `0x180005f14`: `ntdll.dll`
- `0x180005f4c`: `RtlIsCapabilitySid`

## pseudocode

```c
__int64 __fastcall IsCapabilityAce_(struct _ACE_HEADER *a1)
{
  unsigned int v2; // edi
  HMODULE Library; // rax
  HMODULE v4; // rbx
  FARPROC ProcAddress; // rax
  _DWORD Sid2[4]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  Library = LoadLibraryExW(L"ntdll.dll", 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "RtlIsCapabilitySid");
    if ( ProcAddress )
    {
      Sid2[0] = 513;
      Sid2[1] = 251658240;
      Sid2[2] = 2;
      Sid2[3] = 1;
      if ( !a1->AceType
        && (((unsigned __int8 (__fastcall *)(struct _ACE_HEADER *))ProcAddress)(&a1[2]) || RtlEqualSid(&a1[2], Sid2)) )
      {
        v2 = 1;
      }
    }
    FreeLibrary(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180005ef0  mov     [rsp+arg_8], rbx
0x180005ef5  mov     [rsp+arg_10], rsi
0x180005efa  push    rdi
0x180005efb  sub     rsp, 40h
0x180005eff  mov     rax, cs:__security_cookie
0x180005f06  xor     rax, rsp
0x180005f09  mov     [rsp+48h+var_18], rax
0x180005f0e  mov     rsi, rcx
0x180005f11  xor     r8d, r8d; dwFlags
0x180005f14  lea     rcx, LibFileName; "ntdll.dll"
0x180005f1b  xor     edx, edx; hFile
0x180005f1d  xor     edi, edi
0x180005f1f  call    cs:__imp_LoadLibraryExW
0x180005f25  mov     rbx, rax
0x180005f28  test    rax, rax
0x180005f2b  jnz     short loc_180005F4C
0x180005f2d  mov     eax, edi
0x180005f2f  mov     rcx, [rsp+48h+var_18]
0x180005f34  xor     rcx, rsp; StackCookie
0x180005f37  call    __security_check_cookie
0x180005f3c  mov     rbx, [rsp+48h+arg_8]
0x180005f41  mov     rsi, [rsp+48h+arg_10]
0x180005f46  add     rsp, 40h
0x180005f4a  pop     rdi
0x180005f4b  retn
0x180005f4c  lea     rdx, ProcName; "RtlIsCapabilitySid"
0x180005f53  mov     rcx, rbx; hModule
0x180005f56  call    cs:__imp_GetProcAddress
0x180005f5c  test    rax, rax
0x180005f5f  jz      short loc_180005FA6
0x180005f61  mov     [rsp+48h+Sid2], 201h
0x180005f69  mov     [rsp+48h+var_24], 0F000000h
0x180005f71  mov     [rsp+48h+var_20], 2
0x180005f79  mov     [rsp+48h+var_1C], 1
0x180005f81  cmp     [rsi], dil
0x180005f84  jnz     short loc_180005FA6
0x180005f86  lea     rcx, [rsi+8]
0x180005f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f8f  test    al, al
0x180005f91  jnz     short loc_180005FB4
0x180005f93  lea     rdx, [rsp+48h+Sid2]; Sid2
0x180005f98  lea     rcx, [rsi+8]; Sid1
0x180005f9c  call    cs:__imp_RtlEqualSid
0x180005fa2  test    al, al
0x180005fa4  jnz     short loc_180005FB4
0x180005fa6  mov     rcx, rbx; hLibModule
0x180005fa9  call    cs:__imp_FreeLibrary
0x180005faf  jmp     loc_180005F2D
0x180005fb4  mov     edi, 1
0x180005fb9  jmp     short loc_180005FA6
```
