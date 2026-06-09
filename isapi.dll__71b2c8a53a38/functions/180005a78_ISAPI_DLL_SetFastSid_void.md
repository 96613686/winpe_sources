# ISAPI_DLL::SetFastSid(void *)

- ea: `0x180005a78`
- end: `0x180005ad2`
- name: `?SetFastSid@ISAPI_DLL@@QEAAJPEAX@Z`
- size: `90`
- prototype: `int(ISAPI_DLL *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005640`

## callees

- `0x180005a78`
- `0x180012476`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005a90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005aa5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005a90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005aa5`

## pseudocode

```c
__int64 __fastcall ISAPI_DLL::SetFastSid(ISAPI_DLL *this, void *a2)
{
  DWORD LengthSid; // eax

  if ( GetLengthSid(a2) <= 0x40 )
  {
    LengthSid = GetLengthSid(a2);
    memcpy_0((char *)this + 256, a2, LengthSid);
    *((_QWORD *)this + 31) = (char *)this + 256;
  }
  return 0;
}

```

## disassembly

```asm
0x180005a78  mov     [rsp+arg_0], rbx
0x180005a7d  mov     [rsp+arg_8], rsi
0x180005a82  push    rdi
0x180005a83  sub     rsp, 20h
0x180005a87  mov     rsi, rcx
0x180005a8a  mov     rdi, rdx
0x180005a8d  mov     rcx, rdx; pSid
0x180005a90  call    cs:__imp_GetLengthSid
0x180005a96  cmp     eax, 40h ; '@'
0x180005a99  ja      short loc_180005AC0
0x180005a9b  mov     rcx, rdi; pSid
0x180005a9e  lea     rbx, [rsi+100h]
0x180005aa5  call    cs:__imp_GetLengthSid
0x180005aab  mov     r8d, eax; Size
0x180005aae  mov     rdx, rdi; Src
0x180005ab1  mov     rcx, rbx; void *
0x180005ab4  call    memcpy_0
0x180005ab9  mov     [rsi+0F8h], rbx
0x180005ac0  mov     rbx, [rsp+28h+arg_0]
0x180005ac5  xor     eax, eax
0x180005ac7  mov     rsi, [rsp+28h+arg_8]
0x180005acc  add     rsp, 20h
0x180005ad0  pop     rdi
0x180005ad1  retn
```
