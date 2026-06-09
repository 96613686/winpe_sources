# GetFileIntegrityRid(ushort const *,ulong *)

- ea: `0x180044724`
- end: `0x18004483e`
- name: `?GetFileIntegrityRid@@YAJPEBGPEAK@Z`
- size: `282`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800446f0`
- `0x1800648f0`

## callees

- `0x180044724`
- `0x180044850`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004481a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004481a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044831`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800447b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800447ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800447ae`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004478c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18004478c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800447a0`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800447a0`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004477e`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18004477e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18004474d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180044807`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18004474d`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180044807`

## pseudocode

```c
__int64 __fastcall GetFileIntegrityRid(const unsigned __int16 *a1, unsigned int *a2)
{
  void *File2; // rdi
  int HandleIntegrityLevel; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  PSID pSid; // [rsp+90h] [rbp+38h] BYREF

  File2 = (void *)CreateFile2(a1, 0x20000, 3);
  if ( File2 == (void *)-1LL
    && (GetLastError() != 5 || (File2 = (void *)CreateFile2(a1, 0x20000, 3), File2 == (void *)-1LL)) )
  {
    LastError = GetLastError();
    HandleIntegrityLevel = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    pSid = 0;
    HandleIntegrityLevel = GetHandleIntegrityLevel(File2, &pSid);
    if ( HandleIntegrityLevel >= 0 )
    {
      if ( IsValidSid(pSid) && (SidSubAuthorityCount = GetSidSubAuthorityCount(pSid), *SidSubAuthorityCount) )
        *a2 = *GetSidSubAuthority(pSid, (unsigned int)*SidSubAuthorityCount - 1);
      else
        HandleIntegrityLevel = -2147467259;
      LocalFree(pSid);
    }
    CloseHandle(File2);
  }
  return (unsigned int)HandleIntegrityLevel;
}

```

## disassembly

```asm
0x180044724  push    rbp
0x180044726  push    rbx
0x180044727  push    rsi
0x180044728  push    rdi
0x180044729  mov     rbp, rsp
0x18004472c  sub     rsp, 58h
0x180044730  mov     r9d, 3
0x180044736  mov     [rsp+58h+var_38], 0
0x18004473f  mov     rsi, rdx
0x180044742  mov     r8d, r9d
0x180044745  mov     edx, 20000h
0x18004474a  mov     rbx, rcx
0x18004474d  call    cs:__imp_CreateFile2
0x180044753  mov     rdi, rax
0x180044756  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004475a  jz      loc_180044831
0x180044760  lea     rdx, [rbp+pSid]; Sid
0x180044764  mov     [rbp+pSid], 0
0x18004476c  mov     rcx, rdi; Handle
0x18004476f  call    ?GetHandleIntegrityLevel@@YAJPEAXPEAPEAX@Z; GetHandleIntegrityLevel(void *,void * *)
0x180044774  mov     ebx, eax
0x180044776  test    eax, eax
0x180044778  js      short loc_1800447B4
0x18004477a  mov     rcx, [rbp+pSid]; pSid
0x18004477e  call    cs:__imp_IsValidSid
0x180044784  test    eax, eax
0x180044786  jz      short loc_1800447C8
0x180044788  mov     rcx, [rbp+pSid]; pSid
0x18004478c  call    cs:__imp_GetSidSubAuthorityCount
0x180044792  cmp     byte ptr [rax], 0
0x180044795  jbe     short loc_1800447C8
0x180044797  movzx   edx, byte ptr [rax]
0x18004479a  mov     rcx, [rbp+pSid]; pSid
0x18004479e  dec     edx; nSubAuthority
0x1800447a0  call    cs:__imp_GetSidSubAuthority
0x1800447a6  mov     ecx, [rax]
0x1800447a8  mov     [rsi], ecx
0x1800447aa  mov     rcx, [rbp+pSid]; hMem
0x1800447ae  call    cs:__imp_LocalFree
0x1800447b4  mov     rcx, rdi; hObject
0x1800447b7  call    cs:__imp_CloseHandle
0x1800447bd  mov     eax, ebx
0x1800447bf  add     rsp, 58h
0x1800447c3  pop     rdi
0x1800447c4  pop     rsi
0x1800447c5  pop     rbx
0x1800447c6  pop     rbp
0x1800447c7  retn
0x1800447c8  mov     ebx, 80004005h
0x1800447cd  jmp     short loc_1800447AA
0x1800447cf  mov     r9d, 3
0x1800447d5  mov     [rbp+var_28], 20h ; ' '
0x1800447dc  xorps   xmm0, xmm0
0x1800447df  mov     [rbp+var_24], 80h
0x1800447e6  lea     rax, [rbp+var_28]
0x1800447ea  mov     [rbp+var_20], 2000000h
0x1800447f2  mov     r8d, r9d
0x1800447f5  mov     [rsp+58h+var_38], rax
0x1800447fa  mov     edx, 20000h
0x1800447ff  mov     rcx, rbx
0x180044802  movdqu  [rbp+var_18], xmm0
0x180044807  call    cs:__imp_CreateFile2
0x18004480d  mov     rdi, rax
0x180044810  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044814  jnz     loc_180044760
0x18004481a  call    cs:__imp_GetLastError
0x180044820  mov     ebx, eax
0x180044822  test    eax, eax
0x180044824  jle     short loc_1800447BD
0x180044826  movzx   ebx, ax
0x180044829  or      ebx, 80070000h
0x18004482f  jmp     short loc_1800447BD
0x180044831  call    cs:__imp_GetLastError
0x180044837  cmp     eax, 5
0x18004483a  jnz     short loc_18004481A
0x18004483c  jmp     short loc_1800447CF
```
