# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x180002a60`
- end: `0x180002af4`
- name: `?AllocateAndCreateWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `148`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800028f8`
- `0x180002afc`

## callees

- `0x180002a60`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x180002aac`
- `ADVAPI32!CreateWellKnownSid` at `0x180002aac`
- `KERNEL32!GetLastError` at `0x180002ab6`
- `KERNEL32!GetLastError` at `0x180002ab6`
- `KERNEL32!LocalFree` at `0x180002ace`
- `KERNEL32!LocalFree` at `0x180002ace`
- `KERNEL32!LocalAlloc` at `0x180002a8b`
- `KERNEL32!LocalAlloc` at `0x180002a8b`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE WellKnownSidType, void **a2)
{
  HLOCAL v4; // rax
  void *v5; // rdi
  unsigned int v6; // ebx
  signed int LastError; // eax
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  cbSid = 68;
  if ( !a2 || *a2 )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v4 = LocalAlloc(0x40u, 0x44u);
    v5 = v4;
    if ( v4 )
    {
      if ( CreateWellKnownSid(WellKnownSidType, 0, v4, &cbSid) )
      {
        v6 = 0;
        *a2 = v5;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(v5);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002a60  mov     [rsp+arg_0], rbx
0x180002a65  mov     [rsp+arg_10], rsi
0x180002a6a  push    rdi
0x180002a6b  sub     rsp, 20h
0x180002a6f  mov     rsi, rdx
0x180002a72  mov     ebx, ecx
0x180002a74  mov     edx, 44h ; 'D'; uBytes
0x180002a79  mov     [rsp+28h+cbSid], edx
0x180002a7d  test    rsi, rsi
0x180002a80  jz      short loc_180002ADD
0x180002a82  cmp     qword ptr [rsi], 0
0x180002a86  jnz     short loc_180002ADD
0x180002a88  lea     ecx, [rdx-4]; uFlags
0x180002a8b  call    cs:__imp_LocalAlloc
0x180002a91  mov     rdi, rax
0x180002a94  test    rax, rax
0x180002a97  jnz     short loc_180002AA0
0x180002a99  mov     ebx, 8007000Eh
0x180002a9e  jmp     short loc_180002AE2
0x180002aa0  lea     r9, [rsp+28h+cbSid]; cbSid
0x180002aa5  mov     r8, rdi; pSid
0x180002aa8  xor     edx, edx; DomainSid
0x180002aaa  mov     ecx, ebx; WellKnownSidType
0x180002aac  call    cs:__imp_CreateWellKnownSid
0x180002ab2  test    eax, eax
0x180002ab4  jnz     short loc_180002AD6
0x180002ab6  call    cs:__imp_GetLastError
0x180002abc  mov     ebx, eax
0x180002abe  test    eax, eax
0x180002ac0  jle     short loc_180002ACB
0x180002ac2  movzx   ebx, ax
0x180002ac5  or      ebx, 80070000h
0x180002acb  mov     rcx, rdi; hMem
0x180002ace  call    cs:__imp_LocalFree
0x180002ad4  jmp     short loc_180002AE2
0x180002ad6  xor     ebx, ebx
0x180002ad8  mov     [rsi], rdi
0x180002adb  jmp     short loc_180002AE2
0x180002add  mov     ebx, 80070057h
0x180002ae2  mov     rsi, [rsp+28h+arg_10]
0x180002ae7  mov     eax, ebx
0x180002ae9  mov     rbx, [rsp+28h+arg_0]
0x180002aee  add     rsp, 20h
0x180002af2  pop     rdi
0x180002af3  retn
```
