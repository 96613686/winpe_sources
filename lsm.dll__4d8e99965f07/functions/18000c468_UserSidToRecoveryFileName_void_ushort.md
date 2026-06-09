# UserSidToRecoveryFileName(void *,ushort * *)

- ea: `0x18000c468`
- end: `0x18000c4fa`
- name: `?UserSidToRecoveryFileName@@YAJPEAXPEAPEAG@Z`
- size: `146`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c314`

## callees

- `0x18000c468`
- `0x18000c500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c4af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4e0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c487`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000c487`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c49f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000c49f`

## pseudocode

```c
__int64 __fastcall UserSidToRecoveryFileName(PSID Sid, unsigned __int16 **a2)
{
  LPWSTR v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx
  LPWSTR StringSid; // [rsp+30h] [rbp+8h] BYREF

  v4 = 0;
  StringSid = 0;
  if ( !Sid )
    goto LABEL_7;
  if ( !IsValidSid(Sid) )
  {
    v4 = StringSid;
LABEL_7:
    v6 = -2147024809;
    goto LABEL_8;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    GetLastError();
  v5 = UserSidToRecoveryFileName(StringSid, a2);
  v4 = StringSid;
  v6 = v5;
LABEL_8:
  if ( v4 )
    LocalFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18000c468  mov     [rsp+arg_8], rbx
0x18000c46d  push    rdi
0x18000c46e  sub     rsp, 20h
0x18000c472  mov     rbx, rcx
0x18000c475  mov     rdi, rdx
0x18000c478  xor     ecx, ecx
0x18000c47a  mov     [rsp+28h+StringSid], rcx
0x18000c47f  test    rbx, rbx
0x18000c482  jz      short loc_18000C4D6
0x18000c484  mov     rcx, rbx; pSid
0x18000c487  call    cs:__imp_IsValidSid
0x18000c48e  nop     dword ptr [rax+rax+00h]
0x18000c493  test    eax, eax
0x18000c495  jz      short loc_18000C4D1
0x18000c497  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18000c49c  mov     rcx, rbx; Sid
0x18000c49f  call    cs:__imp_ConvertSidToStringSidW
0x18000c4a6  nop     dword ptr [rax+rax+00h]
0x18000c4ab  test    eax, eax
0x18000c4ad  jnz     short loc_18000C4BB
0x18000c4af  call    cs:__imp_GetLastError
0x18000c4b6  nop     dword ptr [rax+rax+00h]
0x18000c4bb  mov     rcx, [rsp+28h+StringSid]; pszMore
0x18000c4c0  mov     rdx, rdi; unsigned __int16 **
0x18000c4c3  call    ?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z; UserSidToRecoveryFileName(ushort const *,ushort * *)
0x18000c4c8  mov     rcx, [rsp+28h+StringSid]
0x18000c4cd  mov     ebx, eax
0x18000c4cf  jmp     short loc_18000C4DB
0x18000c4d1  mov     rcx, [rsp+28h+StringSid]; hMem
0x18000c4d6  mov     ebx, 80070057h
0x18000c4db  test    rcx, rcx
0x18000c4de  jz      short loc_18000C4EC
0x18000c4e0  call    cs:__imp_LocalFree
0x18000c4e7  nop     dword ptr [rax+rax+00h]
0x18000c4ec  mov     eax, ebx
0x18000c4ee  mov     rbx, [rsp+28h+arg_8]
0x18000c4f3  add     rsp, 20h
0x18000c4f7  pop     rdi
0x18000c4f8  retn
```
