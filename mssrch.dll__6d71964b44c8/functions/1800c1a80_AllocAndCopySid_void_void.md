# AllocAndCopySid(void *,void * *)

- ea: `0x1800c1a80`
- end: `0x1800c1b08`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `136`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f8bc4`

## callees

- `0x1800c1a80`
- `0x18010ff58`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1af5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c1af5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1abe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800c1abe`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c1a9d`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800c1a9d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c1aaa`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800c1aaa`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c1ad4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800c1ad4`

## pseudocode

```c
__int64 __fastcall AllocAndCopySid(PSID pSourceSid, void **a2)
{
  int Error; // ebx
  DWORD LengthSid; // ebp
  HLOCAL v6; // rax
  void *v7; // rdi

  *a2 = 0;
  Error = -2147024809;
  if ( IsValidSid(pSourceSid) )
  {
    LengthSid = GetLengthSid(pSourceSid);
    Error = -2147024882;
    v6 = LocalAlloc(0x40u, LengthSid);
    v7 = v6;
    if ( v6 )
    {
      if ( CopySid(LengthSid, v6, pSourceSid) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          LocalFree(v7);
          return (unsigned int)Error;
        }
      }
      *a2 = v7;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c1a80  push    rbx
0x1800c1a82  push    rbp
0x1800c1a83  push    rsi
0x1800c1a84  push    rdi
0x1800c1a85  push    r14
0x1800c1a87  sub     rsp, 20h
0x1800c1a8b  mov     r14, rdx
0x1800c1a8e  mov     qword ptr [rdx], 0
0x1800c1a95  mov     rsi, rcx
0x1800c1a98  mov     ebx, 80070057h
0x1800c1a9d  call    cs:__imp_IsValidSid
0x1800c1aa3  test    eax, eax
0x1800c1aa5  jz      short loc_1800C1AFB
0x1800c1aa7  mov     rcx, rsi; pSid
0x1800c1aaa  call    cs:__imp_GetLengthSid
0x1800c1ab0  mov     edx, eax; uBytes
0x1800c1ab2  mov     ecx, 40h ; '@'; uFlags
0x1800c1ab7  mov     ebp, eax
0x1800c1ab9  mov     ebx, 8007000Eh
0x1800c1abe  call    cs:__imp_LocalAlloc
0x1800c1ac4  mov     rdi, rax
0x1800c1ac7  test    rax, rax
0x1800c1aca  jz      short loc_1800C1AFB
0x1800c1acc  mov     r8, rsi; pSourceSid
0x1800c1acf  mov     rdx, rax; pDestinationSid
0x1800c1ad2  mov     ecx, ebp; nDestinationSidLength
0x1800c1ad4  call    cs:__imp_CopySid
0x1800c1ada  test    eax, eax
0x1800c1adc  jz      short loc_1800C1AE2
0x1800c1ade  xor     ebx, ebx
0x1800c1ae0  jmp     short loc_1800C1AED
0x1800c1ae2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c1ae7  mov     ebx, eax
0x1800c1ae9  test    eax, eax
0x1800c1aeb  js      short loc_1800C1AF2
0x1800c1aed  mov     [r14], rdi
0x1800c1af0  jmp     short loc_1800C1AFB
0x1800c1af2  mov     rcx, rdi; hMem
0x1800c1af5  call    cs:__imp_LocalFree
0x1800c1afb  mov     eax, ebx
0x1800c1afd  add     rsp, 20h
0x1800c1b01  pop     r14
0x1800c1b03  pop     rdi
0x1800c1b04  pop     rsi
0x1800c1b05  pop     rbp
0x1800c1b06  pop     rbx
0x1800c1b07  retn
```
