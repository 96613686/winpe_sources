# UserSidToRecoveryFileName(void *,ushort * *)

- ea: `0x1800184a8`
- end: `0x180018521`
- name: `?UserSidToRecoveryFileName@@YAJPEAXPEAPEAG@Z`
- size: `121`
- prototype: `__int64 __fastcall(PSID Sid, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018384`

## callees

- `0x1800184a8`
- `0x180018528`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001850e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001850e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800184c7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800184c7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800184d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800184d9`

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
0x1800184a8  mov     [rsp+arg_8], rbx
0x1800184ad  push    rdi
0x1800184ae  sub     rsp, 20h
0x1800184b2  mov     rbx, rcx
0x1800184b5  mov     rdi, rdx
0x1800184b8  xor     ecx, ecx
0x1800184ba  mov     [rsp+28h+StringSid], rcx
0x1800184bf  test    rbx, rbx
0x1800184c2  jz      short loc_180018504
0x1800184c4  mov     rcx, rbx; pSid
0x1800184c7  call    cs:__imp_IsValidSid
0x1800184cd  test    eax, eax
0x1800184cf  jz      short loc_1800184FF
0x1800184d1  lea     rdx, [rsp+28h+StringSid]; StringSid
0x1800184d6  mov     rcx, rbx; Sid
0x1800184d9  call    cs:__imp_ConvertSidToStringSidW
0x1800184df  test    eax, eax
0x1800184e1  jnz     short loc_1800184E9
0x1800184e3  call    cs:__imp_GetLastError
0x1800184e9  mov     rcx, [rsp+28h+StringSid]; pszMore
0x1800184ee  mov     rdx, rdi; unsigned __int16 **
0x1800184f1  call    ?UserSidToRecoveryFileName@@YAJPEBGPEAPEAG@Z; UserSidToRecoveryFileName(ushort const *,ushort * *)
0x1800184f6  mov     rcx, [rsp+28h+StringSid]
0x1800184fb  mov     ebx, eax
0x1800184fd  jmp     short loc_180018509
0x1800184ff  mov     rcx, [rsp+28h+StringSid]; hMem
0x180018504  mov     ebx, 80070057h
0x180018509  test    rcx, rcx
0x18001850c  jz      short loc_180018514
0x18001850e  call    cs:__imp_LocalFree
0x180018514  mov     eax, ebx
0x180018516  mov     rbx, [rsp+28h+arg_8]
0x18001851b  add     rsp, 20h
0x18001851f  pop     rdi
0x180018520  retn
```
