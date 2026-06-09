# IsCapabilityAce_(_ACE_HEADER *)

- ea: `0x1800114d0`
- end: `0x1800115b4`
- name: `?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(struct _ACE_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180010fb0`

## callees

- `0x1800114d0`
- `0x18003bc70`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001159c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001159c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800114ff`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800114ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001153d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001153d`
- `ntdll!RtlEqualSid` at `0x180011589`
- `ntdll!RtlEqualSid` at `0x180011589`

## string_xrefs

- `0x1800114f4`: `ntdll.dll`
- `0x180011533`: `RtlIsCapabilitySid`

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
0x1800114d0  mov     [rsp+arg_8], rbx
0x1800114d5  mov     [rsp+arg_10], rsi
0x1800114da  push    rdi
0x1800114db  sub     rsp, 40h
0x1800114df  mov     rax, cs:__security_cookie
0x1800114e6  xor     rax, rsp
0x1800114e9  mov     [rsp+48h+var_18], rax
0x1800114ee  mov     rsi, rcx
0x1800114f1  xor     r8d, r8d; dwFlags
0x1800114f4  lea     rcx, LibFileName; "ntdll.dll"
0x1800114fb  xor     edx, edx; hFile
0x1800114fd  xor     edi, edi
0x1800114ff  call    cs:__imp_LoadLibraryExW
0x180011506  nop     dword ptr [rax+rax+00h]
0x18001150b  mov     rbx, rax
0x18001150e  test    rax, rax
0x180011511  jnz     short loc_180011533
0x180011513  mov     eax, edi
0x180011515  mov     rcx, [rsp+48h+var_18]
0x18001151a  xor     rcx, rsp; StackCookie
0x18001151d  call    __security_check_cookie
0x180011522  mov     rbx, [rsp+48h+arg_8]
0x180011527  mov     rsi, [rsp+48h+arg_10]
0x18001152c  add     rsp, 40h
0x180011530  pop     rdi
0x180011531  retn
0x180011533  lea     rdx, ProcName; "RtlIsCapabilitySid"
0x18001153a  mov     rcx, rbx; hModule
0x18001153d  call    cs:__imp_GetProcAddress
0x180011544  nop     dword ptr [rax+rax+00h]
0x180011549  test    rax, rax
0x18001154c  jz      short loc_180011599
0x18001154e  mov     [rsp+48h+Sid2], 201h
0x180011556  mov     [rsp+48h+var_24], 0F000000h
0x18001155e  mov     [rsp+48h+var_20], 2
0x180011566  mov     [rsp+48h+var_1C], 1
0x18001156e  cmp     [rsi], dil
0x180011571  jnz     short loc_180011599
0x180011573  lea     rcx, [rsi+8]
0x180011577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001157c  test    al, al
0x18001157e  jnz     short loc_1800115AD
0x180011580  lea     rdx, [rsp+48h+Sid2]; Sid2
0x180011585  lea     rcx, [rsi+8]; Sid1
0x180011589  call    cs:__imp_RtlEqualSid
0x180011590  nop     dword ptr [rax+rax+00h]
0x180011595  test    al, al
0x180011597  jnz     short loc_1800115AD
0x180011599  mov     rcx, rbx; hLibModule
0x18001159c  call    cs:__imp_FreeLibrary
0x1800115a3  nop     dword ptr [rax+rax+00h]
0x1800115a8  jmp     loc_180011513
0x1800115ad  mov     edi, 1
0x1800115b2  jmp     short loc_180011599
```
