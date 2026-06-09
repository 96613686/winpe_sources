# DmConvertInternalAccountIdToEnrollmentId(ushort *,_GUID *)

- ea: `0x1800205c8`
- end: `0x180020663`
- name: `?DmConvertInternalAccountIdToEnrollmentId@@YAJPEAGPEAU_GUID@@@Z`
- size: `155`
- prototype: `int(unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002066c`

## callees

- `0x180006140`
- `0x1800205c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020649`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020649`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020608`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020608`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002063a`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18002063a`

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
0x1800205c8  push    rbx
0x1800205ca  push    rbp
0x1800205cb  push    rsi
0x1800205cc  push    rdi
0x1800205cd  push    r14
0x1800205cf  sub     rsp, 20h
0x1800205d3  xor     r14d, r14d
0x1800205d6  mov     rbp, rdx
0x1800205d9  mov     ebx, r14d
0x1800205dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800205e0  mov     rsi, rcx
0x1800205e3  inc     rax
0x1800205e6  cmp     [rcx+rax*2], r14w
0x1800205eb  jnz     short loc_1800205E3
0x1800205ed  lea     ecx, [rax+3]
0x1800205f0  cmp     ecx, eax
0x1800205f2  jb      short loc_180020646
0x1800205f4  lea     rax, [rcx+rcx]
0x1800205f8  mov     edi, ecx
0x1800205fa  mov     ecx, 0FFFFFFFFh
0x1800205ff  cmp     rax, rcx
0x180020602  ja      short loc_180020646
0x180020604  mov     edx, eax; uBytes
0x180020606  xor     ecx, ecx; uFlags
0x180020608  call    cs:__imp_LocalAlloc
0x18002060f  nop     dword ptr [rax+rax+00h]
0x180020614  mov     rbx, rax
0x180020617  test    rax, rax
0x18002061a  jz      short loc_180020646
0x18002061c  mov     r9, rsi
0x18002061f  lea     r8, aS; "{%s}"
0x180020626  mov     edx, edi; unsigned __int64
0x180020628  mov     rcx, rax; unsigned __int16 *
0x18002062b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180020630  test    eax, eax
0x180020632  js      short loc_180020646
0x180020634  mov     rdx, rbp; pclsid
0x180020637  mov     rcx, rbx; lpsz
0x18002063a  call    cs:__imp_CLSIDFromString
0x180020641  nop     dword ptr [rax+rax+00h]
0x180020646  mov     rcx, rbx; hMem
0x180020649  call    cs:__imp_LocalFree
0x180020650  nop     dword ptr [rax+rax+00h]
0x180020655  xor     eax, eax
0x180020657  add     rsp, 20h
0x18002065b  pop     r14
0x18002065d  pop     rdi
0x18002065e  pop     rsi
0x18002065f  pop     rbp
0x180020660  pop     rbx
0x180020661  retn
```
