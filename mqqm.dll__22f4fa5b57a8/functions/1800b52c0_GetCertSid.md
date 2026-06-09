# GetCertSid

- ea: `0x1800b52c0`
- end: `0x1800b537d`
- name: `GetCertSid`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800b5168`

## callees

- `0x18003e894`
- `0x180045c38`
- `0x1800b52c0`

## import_xrefs

- `msvcrt!free` at `0x1800b531e`
- `msvcrt!free` at `0x1800b5350`
- `msvcrt!free` at `0x1800b536a`
- `msvcrt!free` at `0x1800b531e`
- `msvcrt!free` at `0x1800b5350`
- `msvcrt!free` at `0x1800b536a`
- `ADVAPI32!GetLengthSid` at `0x1800b5341`
- `ADVAPI32!GetLengthSid` at `0x1800b5341`
- `ADVAPI32!IsValidSid` at `0x1800b5334`
- `ADVAPI32!IsValidSid` at `0x1800b5334`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCertSid(__int64 a1, __int64 a2)
{
  wchar_t *v4; // rbx
  void *CertSid; // rbp
  void *v6; // rcx

  v4 = (wchar_t *)basic_xstr_t<wchar_t>::ToStr(a2 + 792);
  CertSid = AppGetCertSid(
              *(const unsigned __int8 **)(a2 + 752),
              *(_DWORD *)(a2 + 744),
              *(_BYTE *)(a2 + 786),
              v4,
              *(_DWORD *)(a2 + 808));
  v6 = *(void **)(a2 + 760);
  *(_QWORD *)(a2 + 760) = 0;
  free(v6);
  *(_QWORD *)(a2 + 760) = CertSid;
  if ( CertSid && IsValidSid(CertSid) )
  {
    *(_DWORD *)a1 = GetLengthSid(CertSid);
    *(_QWORD *)(a1 + 8) = CertSid;
    free(v4);
  }
  else
  {
    *(_DWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    free(v4);
  }
  return a1;
}

```

## disassembly

```asm
0x1800b52c0  push    rbx
0x1800b52c2  push    rbp
0x1800b52c3  push    rsi
0x1800b52c4  push    rdi
0x1800b52c5  sub     rsp, 38h
0x1800b52c9  mov     rdi, rdx
0x1800b52cc  mov     rsi, rcx
0x1800b52cf  lea     rcx, [rdx+318h]
0x1800b52d6  call    ?ToStr@?$basic_xstr_t@_W@@QEBAPEA_WXZ; basic_xstr_t<wchar_t>::ToStr(void)
0x1800b52db  mov     rbx, rax
0x1800b52de  mov     [rsp+58h+arg_8], rax
0x1800b52e3  mov     eax, [rdi+328h]
0x1800b52e9  mov     [rsp+58h+var_38], eax; unsigned int
0x1800b52ed  mov     r9, rbx; wchar_t *
0x1800b52f0  mov     r8b, [rdi+312h]; bool
0x1800b52f7  mov     edx, [rdi+2E8h]; unsigned int
0x1800b52fd  mov     rcx, [rdi+2F0h]; unsigned __int8 *
0x1800b5304  call    ?AppGetCertSid@@YAPEAXPEBEK_NPEB_WK@Z; AppGetCertSid(uchar const *,ulong,bool,wchar_t const *,ulong)
0x1800b5309  mov     rbp, rax
0x1800b530c  mov     rcx, [rdi+2F8h]; Block
0x1800b5313  mov     qword ptr [rdi+2F8h], 0
0x1800b531e  call    cs:__imp_free
0x1800b5324  nop
0x1800b5325  mov     [rdi+2F8h], rbp
0x1800b532c  test    rbp, rbp
0x1800b532f  jz      short loc_1800B5359
0x1800b5331  mov     rcx, rbp; pSid
0x1800b5334  call    cs:__imp_IsValidSid
0x1800b533a  test    eax, eax
0x1800b533c  jz      short loc_1800B5359
0x1800b533e  mov     rcx, rbp; pSid
0x1800b5341  call    cs:__imp_GetLengthSid
0x1800b5347  mov     [rsi], eax
0x1800b5349  mov     [rsi+8], rbp
0x1800b534d  mov     rcx, rbx; Block
0x1800b5350  call    cs:__imp_free
0x1800b5356  nop
0x1800b5357  jmp     short loc_1800B5371
0x1800b5359  mov     dword ptr [rsi], 0
0x1800b535f  mov     qword ptr [rsi+8], 0
0x1800b5367  mov     rcx, rbx; Block
0x1800b536a  call    cs:__imp_free
0x1800b5370  nop
0x1800b5371  mov     rax, rsi
0x1800b5374  add     rsp, 38h
0x1800b5378  pop     rdi
0x1800b5379  pop     rsi
0x1800b537a  pop     rbp
0x1800b537b  pop     rbx
0x1800b537c  retn
```
