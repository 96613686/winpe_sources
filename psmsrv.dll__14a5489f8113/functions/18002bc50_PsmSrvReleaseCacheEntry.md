# PsmSrvReleaseCacheEntry

- ea: `0x18002bc50`
- end: `0x18002bced`
- name: `PsmSrvReleaseCacheEntry`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000191c`
- `0x18001622c`
- `0x18002bc50`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002bc74`
- `ntdll!RtlLengthSid` at `0x18002bc74`
- `ntdll!RtlValidSid` at `0x18002bc81`
- `ntdll!RtlValidSid` at `0x18002bc81`

## pseudocode

```c
__int64 __fastcall PsmSrvReleaseCacheEntry(__int64 a1, unsigned int a2, void *a3, int a4, WCHAR *a5)
{
  int v8; // [rsp+58h] [rbp+20h] BYREF

  v8 = a4;
  if ( a2 >= 2 && RtlLengthSid(a3) == a2 && RtlValidSid(a3) )
    return PsmpSetApplicationCache(&v8, a3, a5, 0, a1, 0);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids);
  return 3221225713LL;
}

```

## disassembly

```asm
0x18002bc50  mov     [rsp+arg_0], rbx
0x18002bc55  mov     [rsp+arg_8], rsi
0x18002bc5a  mov     [rsp+arg_18], r9d
0x18002bc5f  push    rdi
0x18002bc60  sub     rsp, 30h
0x18002bc64  mov     rbx, r8
0x18002bc67  mov     edi, edx
0x18002bc69  mov     rsi, rcx
0x18002bc6c  cmp     edx, 2
0x18002bc6f  jb      short loc_18002BCB0
0x18002bc71  mov     rcx, rbx; Sid
0x18002bc74  call    cs:__imp_RtlLengthSid
0x18002bc7a  cmp     eax, edi
0x18002bc7c  jnz     short loc_18002BCB0
0x18002bc7e  mov     rcx, rbx; Sid
0x18002bc81  call    cs:__imp_RtlValidSid
0x18002bc87  test    al, al
0x18002bc89  jz      short loc_18002BCB0
0x18002bc8b  mov     r8, [rsp+38h+arg_20]
0x18002bc90  lea     rcx, [rsp+38h+arg_18]
0x18002bc95  mov     [rsp+38h+var_10], 0
0x18002bc9e  xor     r9d, r9d
0x18002bca1  mov     rdx, rbx
0x18002bca4  mov     [rsp+38h+var_18], rsi
0x18002bca9  call    PsmpSetApplicationCache
0x18002bcae  jmp     short loc_18002BCDD
0x18002bcb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bcb7  test    byte ptr [rcx+1Ch], 2
0x18002bcbb  jz      short loc_18002BCD8
0x18002bcbd  cmp     byte ptr [rcx+19h], 2
0x18002bcc1  jb      short loc_18002BCD8
0x18002bcc3  mov     rcx, [rcx+10h]
0x18002bcc7  lea     r8, WPP_8b54d6d5430f33977cd8c28693ba15fd_Traceguids
0x18002bcce  mov     edx, 21h ; '!'
0x18002bcd3  call    WPP_SF_
0x18002bcd8  mov     eax, 0C00000F1h
0x18002bcdd  mov     rbx, [rsp+38h+arg_0]
0x18002bce2  mov     rsi, [rsp+38h+arg_8]
0x18002bce7  add     rsp, 30h
0x18002bceb  pop     rdi
0x18002bcec  retn
```
