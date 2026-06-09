# DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x140054a6c`
- end: `0x140054b07`
- name: `?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `16`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140052b40`
- `0x140052c10`
- `0x140052ce0`
- `0x140052da0`
- `0x140052e80`
- `0x140052f40`
- `0x140053000`
- `0x1400530c0`
- `0x140053180`
- `0x140053250`
- `0x140053330`
- `0x140053400`
- `0x1400534d0`
- `0x140053fc0`
- `0x140054090`
- `0x140055248`

## callees

- `0x14000bf50`
- `0x140054a6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140054ade`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140054ade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054aed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054aed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140054aac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140054aac`

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
0x140054a6c  push    rbx
0x140054a6e  push    rbp
0x140054a6f  push    rsi
0x140054a70  push    rdi
0x140054a71  push    r14
0x140054a73  sub     rsp, 20h
0x140054a77  xor     r14d, r14d
0x140054a7a  mov     rbp, rdx
0x140054a7d  mov     ebx, r14d
0x140054a80  or      rax, 0FFFFFFFFFFFFFFFFh
0x140054a84  mov     rsi, rcx
0x140054a87  inc     rax
0x140054a8a  cmp     [rcx+rax*2], r14w
0x140054a8f  jnz     short loc_140054A87
0x140054a91  lea     ecx, [rax+3]
0x140054a94  cmp     ecx, eax
0x140054a96  jb      short loc_140054AEA
0x140054a98  lea     rax, [rcx+rcx]
0x140054a9c  mov     edi, ecx
0x140054a9e  mov     ecx, 0FFFFFFFFh
0x140054aa3  cmp     rax, rcx
0x140054aa6  ja      short loc_140054AEA
0x140054aa8  mov     edx, eax; uBytes
0x140054aaa  xor     ecx, ecx; uFlags
0x140054aac  call    cs:__imp_LocalAlloc
0x140054ab3  nop     dword ptr [rax+rax+00h]
0x140054ab8  mov     rbx, rax
0x140054abb  test    rax, rax
0x140054abe  jz      short loc_140054AEA
0x140054ac0  mov     r9, rsi
0x140054ac3  lea     r8, aS; "{%s}"
0x140054aca  mov     edx, edi; unsigned __int64
0x140054acc  mov     rcx, rax; unsigned __int16 *
0x140054acf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140054ad4  test    eax, eax
0x140054ad6  js      short loc_140054AEA
0x140054ad8  mov     rdx, rbp; pclsid
0x140054adb  mov     rcx, rbx; lpsz
0x140054ade  call    cs:__imp_CLSIDFromString
0x140054ae5  nop     dword ptr [rax+rax+00h]
0x140054aea  mov     rcx, rbx; hMem
0x140054aed  call    cs:__imp_LocalFree
0x140054af4  nop     dword ptr [rax+rax+00h]
0x140054af9  xor     eax, eax
0x140054afb  add     rsp, 20h
0x140054aff  pop     r14
0x140054b01  pop     rdi
0x140054b02  pop     rsi
0x140054b03  pop     rbp
0x140054b04  pop     rbx
0x140054b05  retn
```
