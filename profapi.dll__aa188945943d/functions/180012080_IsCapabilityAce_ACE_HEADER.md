# IsCapabilityAce_(_ACE_HEADER *)

- ea: `0x180012080`
- end: `0x180012143`
- name: `?IsCapabilityAce_@@YAHPEAU_ACE_HEADER@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(struct _ACE_HEADER *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000e874`

## callees

- `0x18000fa10`
- `0x180012080`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800120af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800120af`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001211e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001211e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120c7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800120c7`
- `ntdll!RtlEqualSid` at `0x18001210c`
- `ntdll!RtlEqualSid` at `0x18001210c`

## string_xrefs

- `0x1800120a4`: `ntdll.dll`
- `0x1800120bd`: `RtlIsCapabilitySid`

## pseudocode

```c
__int64 __fastcall IsCapabilityAce_(struct _ACE_HEADER *a1)
{
  unsigned int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
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
0x180012080  mov     [rsp+arg_8], rbx
0x180012085  mov     [rsp+arg_10], rsi
0x18001208a  push    rdi
0x18001208b  sub     rsp, 40h
0x18001208f  mov     rax, cs:__security_cookie
0x180012096  xor     rax, rsp
0x180012099  mov     [rsp+48h+var_18], rax
0x18001209e  mov     rsi, rcx
0x1800120a1  xor     r8d, r8d; dwFlags
0x1800120a4  lea     rcx, LibFileName; "ntdll.dll"
0x1800120ab  xor     edx, edx; hFile
0x1800120ad  xor     ebx, ebx
0x1800120af  call    cs:__imp_LoadLibraryExW
0x1800120b5  mov     rdi, rax
0x1800120b8  test    rax, rax
0x1800120bb  jz      short loc_180012124
0x1800120bd  lea     rdx, aRtliscapabilit; "RtlIsCapabilitySid"
0x1800120c4  mov     rcx, rax; hModule
0x1800120c7  call    cs:__imp_GetProcAddress
0x1800120cd  test    rax, rax
0x1800120d0  jz      short loc_18001211B
0x1800120d2  mov     [rsp+48h+Sid2], 201h
0x1800120da  mov     [rsp+48h+var_24], 0F000000h
0x1800120e2  mov     [rsp+48h+var_20], 2
0x1800120ea  mov     [rsp+48h+var_1C], 1
0x1800120f2  cmp     [rsi], bl
0x1800120f4  jnz     short loc_18001211B
0x1800120f6  lea     rcx, [rsi+8]
0x1800120fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120ff  test    al, al
0x180012101  jnz     short loc_180012116
0x180012103  lea     rdx, [rsp+48h+Sid2]; Sid2
0x180012108  lea     rcx, [rsi+8]; Sid1
0x18001210c  call    cs:__imp_RtlEqualSid
0x180012112  test    al, al
0x180012114  jz      short loc_18001211B
0x180012116  mov     ebx, 1
0x18001211b  mov     rcx, rdi; hLibModule
0x18001211e  call    cs:__imp_FreeLibrary
0x180012124  mov     eax, ebx
0x180012126  mov     rcx, [rsp+48h+var_18]
0x18001212b  xor     rcx, rsp; StackCookie
0x18001212e  call    __security_check_cookie
0x180012133  mov     rbx, [rsp+48h+arg_8]
0x180012138  mov     rsi, [rsp+48h+arg_10]
0x18001213d  add     rsp, 40h
0x180012141  pop     rdi
0x180012142  retn
```
