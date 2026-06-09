# DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x1800469e8`
- end: `0x180046a83`
- name: `?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e220`
- `0x180013830`

## callees

- `0x18000bd7c`
- `0x1800469e8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046a28`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046a28`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046a69`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046a5a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180046a5a`

## pseudocode

```c
__int64 __fastcall DmConvertInternalAccountIdToEnrollmentId(unsigned __int16 *a1, struct _GUID *a2)
{
  OLECHAR *v3; // rbx
  __int64 v4; // rax
  __int64 v6; // rcx
  unsigned int v7; // edi
  unsigned __int16 *v8; // rax

  v3 = 0;
  v4 = -1;
  do
    ++v4;
  while ( a1[v4] );
  v6 = (unsigned int)(v4 + 3);
  if ( (unsigned int)v6 >= (unsigned int)v4 )
  {
    v7 = v4 + 3;
    if ( (unsigned __int64)(2 * v6) <= 0xFFFFFFFF )
    {
      v8 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)(2 * v6));
      v3 = v8;
      if ( v8 )
      {
        if ( (int)StringCchPrintfW(v8, v7, L"{%s}", a1) >= 0 )
          CLSIDFromString(v3, a2);
      }
    }
  }
  LocalFree(v3);
  return 0;
}

```

## disassembly

```asm
0x1800469e8  push    rbx
0x1800469ea  push    rbp
0x1800469eb  push    rsi
0x1800469ec  push    rdi
0x1800469ed  push    r14
0x1800469ef  sub     rsp, 20h
0x1800469f3  xor     r14d, r14d
0x1800469f6  mov     rbp, rdx
0x1800469f9  mov     ebx, r14d
0x1800469fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180046a00  mov     rsi, rcx
0x180046a03  inc     rax
0x180046a06  cmp     [rcx+rax*2], r14w
0x180046a0b  jnz     short loc_180046A03
0x180046a0d  lea     ecx, [rax+3]
0x180046a10  cmp     ecx, eax
0x180046a12  jb      short loc_180046A66
0x180046a14  lea     rax, [rcx+rcx]
0x180046a18  mov     edi, ecx
0x180046a1a  mov     ecx, 0FFFFFFFFh
0x180046a1f  cmp     rax, rcx
0x180046a22  ja      short loc_180046A66
0x180046a24  mov     edx, eax; uBytes
0x180046a26  xor     ecx, ecx; uFlags
0x180046a28  call    cs:__imp_LocalAlloc
0x180046a2f  nop     dword ptr [rax+rax+00h]
0x180046a34  mov     rbx, rax
0x180046a37  test    rax, rax
0x180046a3a  jz      short loc_180046A66
0x180046a3c  mov     r9, rsi
0x180046a3f  lea     r8, aS; "{%s}"
0x180046a46  mov     edx, edi; unsigned __int64
0x180046a48  mov     rcx, rax; unsigned __int16 *
0x180046a4b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180046a50  test    eax, eax
0x180046a52  js      short loc_180046A66
0x180046a54  mov     rdx, rbp; pclsid
0x180046a57  mov     rcx, rbx; lpsz
0x180046a5a  call    cs:__imp_CLSIDFromString
0x180046a61  nop     dword ptr [rax+rax+00h]
0x180046a66  mov     rcx, rbx; hMem
0x180046a69  call    cs:__imp_LocalFree
0x180046a70  nop     dword ptr [rax+rax+00h]
0x180046a75  xor     eax, eax
0x180046a77  add     rsp, 20h
0x180046a7b  pop     r14
0x180046a7d  pop     rdi
0x180046a7e  pop     rsi
0x180046a7f  pop     rbp
0x180046a80  pop     rbx
0x180046a81  retn
```
