# SidToStringSid(void *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800aaa00`
- end: `0x1800aaaab`
- name: `?SidToStringSid@@YAJPEAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aaab4`
- `0x1800ac58c`

## callees

- `0x180008618`
- `0x18001d5fc`
- `0x1800aaa00`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800aaa82`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x1800aaa26`
- `api-ms-win-security-sddl-ansi-l1-1-0!ConvertSidToStringSidA` at `0x1800aaa26`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall SidToStringSid(void *a1, void *a2)
{
  const char *v3; // r9
  unsigned int LastError; // ebx
  size_t v6; // r8
  LPSTR StringSid; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  StringSid = 0;
  if ( ConvertSidToStringSidA(a1, &StringSid) )
  {
    v6 = -1;
    do
      ++v6;
    while ( StringSid[v6] );
    std::string::assign(a2, StringSid, v6);
    if ( StringSid )
      LocalFree(StringSid);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\GeneralUtils.cpp",
                  v3);
    if ( StringSid )
      LocalFree(StringSid);
    return LastError;
  }
}

```

## disassembly

```asm
0x1800aaa00  push    rbx
0x1800aaa02  sub     rsp, 30h
0x1800aaa06  mov     rax, cs:__security_cookie
0x1800aaa0d  xor     rax, rsp
0x1800aaa10  mov     [rsp+38h+var_10], rax
0x1800aaa15  mov     rbx, rdx
0x1800aaa18  mov     [rsp+38h+StringSid], 0
0x1800aaa21  lea     rdx, [rsp+38h+StringSid]; StringSid
0x1800aaa26  call    cs:__imp_ConvertSidToStringSidA
0x1800aaa2c  test    eax, eax
0x1800aaa2e  jnz     short loc_1800AAA5C
0x1800aaa30  mov     rcx, [rsp+38h]; this
0x1800aaa35  lea     r8, aCW1SSrcDeliver_8; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800aaa3c  mov     edx, 0A9h; void *
0x1800aaa41  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aaa46  mov     ebx, eax
0x1800aaa48  mov     rcx, [rsp+38h+StringSid]; hMem
0x1800aaa4d  test    rcx, rcx
0x1800aaa50  jz      short loc_1800AAA58
0x1800aaa52  call    cs:__imp_LocalFree
0x1800aaa58  mov     eax, ebx
0x1800aaa5a  jmp     short loc_1800AAA97
0x1800aaa5c  mov     rdx, [rsp+38h+StringSid]; Src
0x1800aaa61  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800aaa65  inc     r8; Size
0x1800aaa68  cmp     byte ptr [rdx+r8], 0
0x1800aaa6d  jnz     short loc_1800AAA65
0x1800aaa6f  mov     rcx, rbx; void *
0x1800aaa72  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1800aaa77  nop
0x1800aaa78  mov     rcx, [rsp+38h+StringSid]; hMem
0x1800aaa7d  test    rcx, rcx
0x1800aaa80  jz      short loc_1800AAA88
0x1800aaa82  call    cs:__imp_LocalFree
0x1800aaa88  xor     eax, eax
0x1800aaa8a  jmp     short loc_1800AAA97
0x1800aaa8c  mov     eax, 8007000Eh
0x1800aaa91  jmp     short loc_1800AAA97
0x1800aaa93  mov     eax, dword ptr [rsp+38h+StringSid]
0x1800aaa97  mov     rcx, [rsp+38h+var_10]
0x1800aaa9c  xor     rcx, rsp; StackCookie
0x1800aaa9f  call    __security_check_cookie
0x1800aaaa4  add     rsp, 30h
0x1800aaaa8  pop     rbx
0x1800aaaa9  retn
```
