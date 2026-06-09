# NetpCompareSid2

- ea: `0x180038280`
- end: `0x1800382fb`
- name: `NetpCompareSid2`
- size: `123`
- prototype: `__int64 __fastcall(void *Buf1, void *Buf2)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037a90`
- `0x1800399dc`

## callees

- `0x180038280`
- `0x18003ad24`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382a9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382b4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382a9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800382b4`

## pseudocode

```c
__int64 __fastcall NetpCompareSid2(void *Buf1, void *Buf2)
{
  __int64 result; // rax
  DWORD LengthSid; // esi
  DWORD v6; // eax
  int v7; // edx

  if ( !Buf1 )
  {
    if ( !Buf2 )
      return 2;
    return 0;
  }
  if ( !Buf2 )
    return 1;
  LengthSid = GetLengthSid(Buf1);
  v6 = GetLengthSid(Buf2);
  if ( LengthSid > v6 )
    return 1;
  if ( LengthSid < v6 )
    return 0;
  v7 = memcmp_0(Buf1, Buf2, LengthSid);
  if ( v7 > 0 )
    return 1;
  result = 2;
  if ( v7 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180038280  mov     [rsp+arg_0], rbx
0x180038285  mov     [rsp+arg_8], rsi
0x18003828a  push    rdi
0x18003828b  sub     rsp, 20h
0x18003828f  mov     rbx, rdx
0x180038292  mov     rdi, rcx
0x180038295  test    rcx, rcx
0x180038298  jnz     short loc_1800382A4
0x18003829a  test    rdx, rdx
0x18003829d  jnz     short loc_1800382E2
0x18003829f  lea     eax, [rdx+2]
0x1800382a2  jmp     short loc_1800382EB
0x1800382a4  test    rbx, rbx
0x1800382a7  jz      short loc_1800382E6
0x1800382a9  call    cs:__imp_GetLengthSid
0x1800382af  mov     rcx, rbx; pSid
0x1800382b2  mov     esi, eax
0x1800382b4  call    cs:__imp_GetLengthSid
0x1800382ba  cmp     esi, eax
0x1800382bc  ja      short loc_1800382E6
0x1800382be  jb      short loc_1800382E2
0x1800382c0  mov     r8d, esi; Size
0x1800382c3  mov     rdx, rbx; Buf2
0x1800382c6  mov     rcx, rdi; Buf1
0x1800382c9  call    memcmp_0
0x1800382ce  mov     edx, eax
0x1800382d0  test    eax, eax
0x1800382d2  jg      short loc_1800382E6
0x1800382d4  xor     ecx, ecx
0x1800382d6  mov     eax, 2
0x1800382db  test    edx, edx
0x1800382dd  cmovs   eax, ecx
0x1800382e0  jmp     short loc_1800382EB
0x1800382e2  xor     eax, eax
0x1800382e4  jmp     short loc_1800382EB
0x1800382e6  mov     eax, 1
0x1800382eb  mov     rbx, [rsp+28h+arg_0]
0x1800382f0  mov     rsi, [rsp+28h+arg_8]
0x1800382f5  add     rsp, 20h
0x1800382f9  pop     rdi
0x1800382fa  retn
```
