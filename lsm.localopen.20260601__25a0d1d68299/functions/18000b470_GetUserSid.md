# GetUserSid

- ea: `0x18000b470`
- end: `0x18000b525`
- name: `GetUserSid`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000b3d0`

## callees

- `0x180009580`
- `0x18000b470`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b4c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b4fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b50b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b50b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b4b4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000b4b4`

## pseudocode

```c
__int64 __fastcall GetUserSid(__int64 *a1, unsigned __int16 *a2, WCHAR *a3)
{
  __int64 v3; // rax
  signed int v5; // ebx
  signed int LastError; // eax
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF

  StringSid = a3;
  v3 = *a1;
  Sid = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, PSID *))(v3 + 72))(a1, &Sid);
  if ( v5 >= 0 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v5 = StringCchCopyW(a2, 0x104u, StringSid);
      LocalFree(StringSid);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
    }
    CoTaskMemFree(Sid);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b470  mov     r11, rsp
0x18000b473  mov     [r11+10h], rbx
0x18000b477  mov     [r11+18h], r8
0x18000b47b  push    rdi
0x18000b47c  sub     rsp, 20h
0x18000b480  mov     rax, [rcx]
0x18000b483  mov     rdi, rdx
0x18000b486  lea     rdx, [r11+8]
0x18000b48a  mov     qword ptr [r11+8], 0
0x18000b492  mov     rax, [rax+48h]
0x18000b496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b49b  mov     ebx, eax
0x18000b49d  test    eax, eax
0x18000b49f  js      short loc_18000B517
0x18000b4a1  mov     rcx, [rsp+28h+Sid]; Sid
0x18000b4a6  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000b4ab  mov     [rsp+28h+StringSid], 0
0x18000b4b4  call    cs:__imp_ConvertSidToStringSidW
0x18000b4bb  nop     dword ptr [rax+rax+00h]
0x18000b4c0  test    eax, eax
0x18000b4c2  jnz     short loc_18000B4E1
0x18000b4c4  call    cs:__imp_GetLastError
0x18000b4cb  nop     dword ptr [rax+rax+00h]
0x18000b4d0  mov     ebx, eax
0x18000b4d2  test    eax, eax
0x18000b4d4  jle     short loc_18000B506
0x18000b4d6  movzx   ebx, ax
0x18000b4d9  or      ebx, 80070000h
0x18000b4df  jmp     short loc_18000B506
0x18000b4e1  mov     r8, [rsp+28h+StringSid]; unsigned __int16 *
0x18000b4e6  mov     edx, 104h; unsigned __int64
0x18000b4eb  mov     rcx, rdi; unsigned __int16 *
0x18000b4ee  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b4f3  mov     rcx, [rsp+28h+StringSid]; hMem
0x18000b4f8  mov     ebx, eax
0x18000b4fa  call    cs:__imp_LocalFree
0x18000b501  nop     dword ptr [rax+rax+00h]
0x18000b506  mov     rcx, [rsp+28h+Sid]; pv
0x18000b50b  call    cs:__imp_CoTaskMemFree
0x18000b512  nop     dword ptr [rax+rax+00h]
0x18000b517  mov     eax, ebx
0x18000b519  mov     rbx, [rsp+28h+arg_8]
0x18000b51e  add     rsp, 20h
0x18000b522  pop     rdi
0x18000b523  retn
```
