# AllocAndCopySid(void *,void * *)

- ea: `0x180009830`
- end: `0x1800098d6`
- name: `?AllocAndCopySid@@YAJPEAXPEAPEAX@Z`
- size: `166`
- prototype: `__int64 __fastcall(PSID pSourceSid, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005a4c8`
- `0x18006f368`
- `0x180070344`

## callees

- `0x180009830`
- `0x1800098dc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009847`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009847`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009883`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180009883`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000985e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000985e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000986d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000986d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800098ce`

## pseudocode

```c
__int64 __fastcall AllocAndCopySid(PSID pSourceSid, void **a2)
{
  DWORD LengthSid; // ebp
  HLOCAL v5; // rax
  void *v6; // rsi
  int Error; // ebx

  *a2 = 0;
  if ( !IsValidSid(pSourceSid) )
    return 2147942487LL;
  LengthSid = GetLengthSid(pSourceSid);
  v5 = LocalAlloc(0x40u, LengthSid);
  v6 = v5;
  if ( !v5 )
    return 2147942414LL;
  if ( CopySid(LengthSid, v5, pSourceSid) )
  {
    Error = 0;
  }
  else
  {
    Error = ResultFromKnownLastError();
    if ( Error < 0 )
    {
      LocalFree(v6);
      return (unsigned int)Error;
    }
  }
  *a2 = v6;
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180009830  mov     [rsp+arg_10], rbx
0x180009835  push    rdi
0x180009836  sub     rsp, 20h
0x18000983a  mov     rdi, rdx
0x18000983d  mov     qword ptr [rdx], 0
0x180009844  mov     rbx, rcx
0x180009847  call    cs:__imp_IsValidSid
0x18000984d  test    eax, eax
0x18000984f  jz      short loc_1800098A9
0x180009851  mov     [rsp+28h+arg_0], rbp
0x180009856  mov     rcx, rbx; pSid
0x180009859  mov     [rsp+28h+arg_8], rsi
0x18000985e  call    cs:__imp_GetLengthSid
0x180009864  mov     edx, eax; uBytes
0x180009866  mov     ecx, 40h ; '@'; uFlags
0x18000986b  mov     ebp, eax
0x18000986d  call    cs:__imp_LocalAlloc
0x180009873  mov     rsi, rax
0x180009876  test    rax, rax
0x180009879  jz      short loc_1800098B9
0x18000987b  mov     r8, rbx; pSourceSid
0x18000987e  mov     rdx, rax; pDestinationSid
0x180009881  mov     ecx, ebp; nDestinationSidLength
0x180009883  call    cs:__imp_CopySid
0x180009889  test    eax, eax
0x18000988b  jz      short loc_1800098C0
0x18000988d  xor     ebx, ebx
0x18000988f  mov     [rdi], rsi
0x180009892  mov     eax, ebx
0x180009894  mov     rbp, [rsp+28h+arg_0]
0x180009899  mov     rsi, [rsp+28h+arg_8]
0x18000989e  mov     rbx, [rsp+28h+arg_10]
0x1800098a3  add     rsp, 20h
0x1800098a7  pop     rdi
0x1800098a8  retn
0x1800098a9  mov     rbx, [rsp+28h+arg_10]
0x1800098ae  mov     eax, 80070057h
0x1800098b3  add     rsp, 20h
0x1800098b7  pop     rdi
0x1800098b8  retn
0x1800098b9  mov     eax, 8007000Eh
0x1800098be  jmp     short loc_180009894
0x1800098c0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800098c5  mov     ebx, eax
0x1800098c7  test    eax, eax
0x1800098c9  jns     short loc_18000988F
0x1800098cb  mov     rcx, rsi; hMem
0x1800098ce  call    cs:__imp_LocalFree
0x1800098d4  jmp     short loc_180009892
```
