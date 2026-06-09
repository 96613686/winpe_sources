# InitPerUserLock(void *)

- ea: `0x180005728`
- end: `0x1800057e2`
- name: `?InitPerUserLock@@YAPEAU_PER_USER_LOCK_ENTRY@@PEAX@Z`
- size: `186`
- prototype: `RTL_SRWLOCK *__fastcall(PSID pSourceSid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005658`

## callees

- `0x180005728`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005779`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005779`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800057ab`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800057ab`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180005763`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180005763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800057d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000574b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000578e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000574b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000578e`

## pseudocode

```c
RTL_SRWLOCK *__fastcall InitPerUserLock(PSID pSourceSid)
{
  RTL_SRWLOCK *v2; // rax
  RTL_SRWLOCK *v3; // rbx
  DWORD LengthSid; // esi
  HLOCAL v5; // rax

  if ( !pSourceSid )
    return 0;
  v2 = (RTL_SRWLOCK *)LocalAlloc(0x40u, 0x28u);
  v3 = v2;
  if ( v2 )
  {
    InitializeSRWLock(v2 + 2);
    LODWORD(v3[3].Ptr) = 1;
    LengthSid = GetLengthSid(pSourceSid);
    v5 = LocalAlloc(0x40u, LengthSid);
    v3[4].Ptr = v5;
    if ( v5 )
    {
      CopySid(LengthSid, v5, pSourceSid);
    }
    else
    {
      LocalFree(v3);
      return 0;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180005728  mov     [rsp+arg_0], rbx
0x18000572d  mov     [rsp+arg_8], rsi
0x180005732  push    rdi
0x180005733  sub     rsp, 20h
0x180005737  mov     rdi, rcx
0x18000573a  test    rcx, rcx
0x18000573d  jz      loc_1800057CB
0x180005743  mov     edx, 28h ; '('; uBytes
0x180005748  lea     ecx, [rdx+18h]; uFlags
0x18000574b  call    cs:__imp_LocalAlloc
0x180005752  nop     dword ptr [rax+rax+00h]
0x180005757  mov     rbx, rax
0x18000575a  test    rax, rax
0x18000575d  jz      short loc_1800057B7
0x18000575f  lea     rcx, [rax+10h]; SRWLock
0x180005763  call    cs:__imp_InitializeSRWLock
0x18000576a  nop     dword ptr [rax+rax+00h]
0x18000576f  mov     rcx, rdi; pSid
0x180005772  mov     dword ptr [rbx+18h], 1
0x180005779  call    cs:__imp_GetLengthSid
0x180005780  nop     dword ptr [rax+rax+00h]
0x180005785  mov     edx, eax; uBytes
0x180005787  mov     ecx, 40h ; '@'; uFlags
0x18000578c  mov     esi, eax
0x18000578e  call    cs:__imp_LocalAlloc
0x180005795  nop     dword ptr [rax+rax+00h]
0x18000579a  mov     [rbx+20h], rax
0x18000579e  test    rax, rax
0x1800057a1  jz      short loc_1800057CF
0x1800057a3  mov     r8, rdi; pSourceSid
0x1800057a6  mov     rdx, rax; pDestinationSid
0x1800057a9  mov     ecx, esi; nDestinationSidLength
0x1800057ab  call    cs:__imp_CopySid
0x1800057b2  nop     dword ptr [rax+rax+00h]
0x1800057b7  mov     rax, rbx
0x1800057ba  mov     rbx, [rsp+28h+arg_0]
0x1800057bf  mov     rsi, [rsp+28h+arg_8]
0x1800057c4  add     rsp, 20h
0x1800057c8  pop     rdi
0x1800057c9  retn
0x1800057cb  xor     eax, eax
0x1800057cd  jmp     short loc_1800057BA
0x1800057cf  mov     rcx, rbx; hMem
0x1800057d2  call    cs:__imp_LocalFree
0x1800057d9  nop     dword ptr [rax+rax+00h]
0x1800057de  xor     ebx, ebx
0x1800057e0  jmp     short loc_1800057B7
```
