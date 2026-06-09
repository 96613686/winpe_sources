# IECheckIntegrityFile(ushort const *,ushort const *)

- ea: `0x1800648f0`
- end: `0x1800649a0`
- name: `?IECheckIntegrityFile@@YAJPEBG0@Z`
- size: `176`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180044724`
- `0x1800648f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006497e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006497e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064976`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180064976`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180064929`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180064929`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006493e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006493e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006491a`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18006491a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006490b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18006490b`

## pseudocode

```c
__int64 __fastcall IECheckIntegrityFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  PUCHAR SidSubAuthorityCount; // rax
  PDWORD SidSubAuthority; // rax
  DWORD v5; // edi
  int FileIntegrityRid; // ebx
  signed int LastError; // eax
  unsigned int v9; // [rsp+40h] [rbp+18h] BYREF
  PSID Sid; // [rsp+48h] [rbp+20h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(a1, &Sid) && IsValidSid(Sid) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(Sid);
    if ( *SidSubAuthorityCount )
    {
      SidSubAuthority = GetSidSubAuthority(Sid, (unsigned int)*SidSubAuthorityCount - 1);
      v9 = 0;
      v5 = *SidSubAuthority;
      FileIntegrityRid = GetFileIntegrityRid(a2, &v9);
      if ( FileIntegrityRid >= 0 )
        FileIntegrityRid = v5 != v9;
    }
    else
    {
      FileIntegrityRid = -2147467259;
    }
    LocalFree(Sid);
  }
  else
  {
    LastError = GetLastError();
    FileIntegrityRid = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)FileIntegrityRid;
}

```

## disassembly

```asm
0x1800648f0  mov     [rsp+arg_0], rbx
0x1800648f5  push    rdi
0x1800648f6  sub     rsp, 20h
0x1800648fa  mov     rbx, rdx
0x1800648fd  mov     [rsp+28h+Sid], 0
0x180064906  lea     rdx, [rsp+28h+Sid]; Sid
0x18006490b  call    cs:__imp_ConvertStringSidToSidW
0x180064911  test    eax, eax
0x180064913  jz      short loc_18006497E
0x180064915  mov     rcx, [rsp+28h+Sid]; pSid
0x18006491a  call    cs:__imp_IsValidSid
0x180064920  test    eax, eax
0x180064922  jz      short loc_18006497E
0x180064924  mov     rcx, [rsp+28h+Sid]; pSid
0x180064929  call    cs:__imp_GetSidSubAuthorityCount
0x18006492f  cmp     byte ptr [rax], 0
0x180064932  jbe     short loc_18006496C
0x180064934  movzx   edx, byte ptr [rax]
0x180064937  mov     rcx, [rsp+28h+Sid]; pSid
0x18006493c  dec     edx; nSubAuthority
0x18006493e  call    cs:__imp_GetSidSubAuthority
0x180064944  lea     rdx, [rsp+28h+arg_10]; unsigned int *
0x180064949  mov     [rsp+28h+arg_10], 0
0x180064951  mov     rcx, rbx; unsigned __int16 *
0x180064954  mov     edi, [rax]
0x180064956  call    ?GetFileIntegrityRid@@YAJPEBGPEAK@Z; GetFileIntegrityRid(ushort const *,ulong *)
0x18006495b  mov     ebx, eax
0x18006495d  test    eax, eax
0x18006495f  js      short loc_180064971
0x180064961  xor     ebx, ebx
0x180064963  cmp     edi, [rsp+28h+arg_10]
0x180064967  setnz   bl
0x18006496a  jmp     short loc_180064971
0x18006496c  mov     ebx, 80004005h
0x180064971  mov     rcx, [rsp+28h+Sid]; hMem
0x180064976  call    cs:__imp_LocalFree
0x18006497c  jmp     short loc_180064993
0x18006497e  call    cs:__imp_GetLastError
0x180064984  mov     ebx, eax
0x180064986  test    eax, eax
0x180064988  jle     short loc_180064993
0x18006498a  movzx   ebx, ax
0x18006498d  or      ebx, 80070000h
0x180064993  mov     eax, ebx
0x180064995  mov     rbx, [rsp+28h+arg_0]
0x18006499a  add     rsp, 20h
0x18006499e  pop     rdi
0x18006499f  retn
```
