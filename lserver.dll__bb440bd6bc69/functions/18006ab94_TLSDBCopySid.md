# TLSDBCopySid

- ea: `0x18006ab94`
- end: `0x18006ac48`
- name: `TLSDBCopySid`
- size: `180`
- prototype: `int __fastcall(PSID pSourceSid, DWORD nDestinationSidLength, HLOCAL *, _DWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180066350`
- `0x18006640c`
- `0x180066484`
- `0x18006661c`

## callees

- `0x18006ab94`

## import_xrefs

- `ADVAPI32!CopySid` at `0x18006ac1e`
- `ADVAPI32!CopySid` at `0x18006ac1e`
- `KERNEL32!LocalSize` at `0x18006abc1`
- `KERNEL32!LocalSize` at `0x18006abc1`
- `KERNEL32!LocalAlloc` at `0x18006abfb`
- `KERNEL32!LocalAlloc` at `0x18006abfb`
- `KERNEL32!LocalFree` at `0x18006abda`
- `KERNEL32!LocalFree` at `0x18006abda`

## pseudocode

```c
int __fastcall TLSDBCopySid(PSID pSourceSid, DWORD nDestinationSidLength, HLOCAL *a3, _DWORD *a4)
{
  SIZE_T v5; // rbx
  HLOCAL v8; // rax

  v5 = nDestinationSidLength;
  if ( *a3 && pSourceSid && LocalSize(*a3) >= nDestinationSidLength )
    goto LABEL_9;
  if ( *a3 )
  {
    LocalFree(*a3);
    *a3 = 0;
  }
  if ( !(_DWORD)v5 || !pSourceSid || (v8 = LocalAlloc(0x40u, v5), (*a3 = v8) != 0) )
  {
LABEL_9:
    *a4 = v5;
    if ( (_DWORD)v5 )
      LODWORD(v8) = CopySid(v5, *a3, pSourceSid);
    else
      LODWORD(v8) = 1;
  }
  return (int)v8;
}

```

## disassembly

```asm
0x18006ab94  mov     [rsp+arg_0], rbx
0x18006ab99  mov     [rsp+arg_8], rsi
0x18006ab9e  mov     [rsp+arg_10], rdi
0x18006aba3  push    r14
0x18006aba5  sub     rsp, 20h
0x18006aba9  mov     rsi, rcx
0x18006abac  mov     ebx, edx
0x18006abae  mov     rcx, [r8]; hMem
0x18006abb1  mov     r14, r9
0x18006abb4  mov     rdi, r8
0x18006abb7  test    rcx, rcx
0x18006abba  jz      short loc_18006ABD2
0x18006abbc  test    rsi, rsi
0x18006abbf  jz      short loc_18006ABD2
0x18006abc1  call    cs:__imp_LocalSize
0x18006abc8  nop     dword ptr [rax+rax+00h]
0x18006abcd  cmp     rax, rbx
0x18006abd0  jnb     short loc_18006AC0F
0x18006abd2  mov     rcx, [rdi]; hMem
0x18006abd5  test    rcx, rcx
0x18006abd8  jz      short loc_18006ABEA
0x18006abda  call    cs:__imp_LocalFree
0x18006abe1  nop     dword ptr [rax+rax+00h]
0x18006abe6  and     qword ptr [rdi], 0
0x18006abea  test    ebx, ebx
0x18006abec  jz      short loc_18006AC0F
0x18006abee  test    rsi, rsi
0x18006abf1  jz      short loc_18006AC0F
0x18006abf3  mov     rdx, rbx; uBytes
0x18006abf6  mov     ecx, 40h ; '@'; uFlags
0x18006abfb  call    cs:__imp_LocalAlloc
0x18006ac02  nop     dword ptr [rax+rax+00h]
0x18006ac07  mov     [rdi], rax
0x18006ac0a  test    rax, rax
0x18006ac0d  jz      short loc_18006AC31
0x18006ac0f  mov     [r14], ebx
0x18006ac12  test    ebx, ebx
0x18006ac14  jz      short loc_18006AC2C
0x18006ac16  mov     rdx, [rdi]; pDestinationSid
0x18006ac19  mov     r8, rsi; pSourceSid
0x18006ac1c  mov     ecx, ebx; nDestinationSidLength
0x18006ac1e  call    cs:__imp_CopySid
0x18006ac25  nop     dword ptr [rax+rax+00h]
0x18006ac2a  jmp     short loc_18006AC31
0x18006ac2c  mov     eax, 1
0x18006ac31  mov     rbx, [rsp+28h+arg_0]
0x18006ac36  mov     rsi, [rsp+28h+arg_8]
0x18006ac3b  mov     rdi, [rsp+28h+arg_10]
0x18006ac40  add     rsp, 20h
0x18006ac44  pop     r14
0x18006ac46  retn
```
