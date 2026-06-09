# DefaultHostInit

- ea: `0x18000a260`
- end: `0x18000a2ee`
- name: `DefaultHostInit`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x18000175c`
- `0x18000a260`
- `0x18000a380`
- `0x180043244`
- `0x180044880`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a27e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a27e`

## pseudocode

```c
__int64 __fastcall DefaultHostInit(__int64 a1, _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  __int64 result; // rax
  _BYTE v5[208]; // [rsp+20h] [rbp-E8h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  Swprintf(v5, 100, L"_MPUnits_%d", CurrentProcessId);
  result = MonitoringHost_New(&Block, v5);
  if ( !(_DWORD)result )
  {
    if ( atexit(DefaultHostCleanUp) )
    {
      return 27;
    }
    else
    {
      *a2 = Block;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a260  push    rbx
0x18000a262  sub     rsp, 100h
0x18000a269  mov     rax, cs:__security_cookie
0x18000a270  xor     rax, rsp
0x18000a273  mov     [rsp+108h+var_18], rax
0x18000a27b  mov     rbx, rdx
0x18000a27e  call    cs:__imp_GetCurrentProcessId
0x18000a284  lea     r8, aMpunitsD; "_MPUnits_%d"
0x18000a28b  mov     edx, 64h ; 'd'
0x18000a290  mov     r9d, eax
0x18000a293  lea     rcx, [rsp+108h+var_E8]
0x18000a298  call    Swprintf
0x18000a29d  lea     rdx, [rsp+108h+var_E8]
0x18000a2a2  lea     rcx, Block
0x18000a2a9  call    MonitoringHost_New
0x18000a2ae  test    eax, eax
0x18000a2b0  jnz     short loc_18000A2D5
0x18000a2b2  lea     rcx, DefaultHostCleanUp; void (__cdecl *)()
0x18000a2b9  call    atexit
0x18000a2be  test    eax, eax
0x18000a2c0  jz      short loc_18000A2C9
0x18000a2c2  mov     eax, 1Bh
0x18000a2c7  jmp     short loc_18000A2D5
0x18000a2c9  mov     rax, cs:Block
0x18000a2d0  mov     [rbx], rax
0x18000a2d3  xor     eax, eax
0x18000a2d5  mov     rcx, [rsp+108h+var_18]
0x18000a2dd  xor     rcx, rsp; StackCookie
0x18000a2e0  call    __security_check_cookie
0x18000a2e5  add     rsp, 100h
0x18000a2ec  pop     rbx
0x18000a2ed  retn
```
