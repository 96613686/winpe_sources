# FTCache::RecordFromScannerInfoEntry(FTCache::SCANNER_INFO_ENTRY *)

- ea: `0x18002a5ac`
- end: `0x18002a735`
- name: `?RecordFromScannerInfoEntry@FTCache@@AEAAPEAU_LSA_FOREST_TRUST_RECORD2@@PEAUSCANNER_INFO_ENTRY@1@@Z`
- size: `393`
- prototype: `struct _LSA_FOREST_TRUST_RECORD2 *__fastcall(FTCache *__hidden this, struct FTCache::SCANNER_INFO_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002aa14`

## callees

- `0x18000fd18`
- `0x180022278`
- `0x18002a5ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a5c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a648`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a5c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a648`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a70b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a6f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a702`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a70b`
- `ntdll!RtlCopySid` at `0x18002a67b`
- `ntdll!RtlCopySid` at `0x18002a67b`
- `ntdll!RtlLengthSid` at `0x18002a61e`
- `ntdll!RtlLengthSid` at `0x18002a61e`

## pseudocode

```c
struct _LSA_FOREST_TRUST_RECORD2 *__fastcall FTCache::RecordFromScannerInfoEntry(
        FTCache *this,
        struct FTCache::SCANNER_INFO_ENTRY *a2)
{
  _OWORD *v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ULONG v6; // esi
  void *v7; // rcx
  HLOCAL v8; // rax
  const UNICODE_STRING *v9; // rdx

  v3 = LocalAlloc(0x40u, 0x38u);
  if ( !v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_21:
      LocalFree(v3);
      return 0;
    }
    v5 = 214;
LABEL_4:
    WPP_SF_(v4[2], v5, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_21;
  }
  *v3 = 0;
  v6 = 0;
  v3[1] = 0;
  v3[2] = 0;
  *((_QWORD *)v3 + 6) = 0;
  v7 = (void *)*((_QWORD *)a2 + 8);
  if ( v7 )
    v6 = RtlLengthSid(v7);
  *((_QWORD *)v3 + 1) = *((_QWORD *)a2 + 6);
  *(_DWORD *)v3 = *((_DWORD *)a2 + 24);
  *((_DWORD *)v3 + 1) = 4;
  if ( *((_QWORD *)a2 + 8) )
  {
    v8 = LocalAlloc(0x40u, v6);
    *((_QWORD *)v3 + 2) = v8;
    if ( !v8 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_21;
      v5 = 215;
      goto LABEL_4;
    }
    RtlCopySid(v6, v8, *((PSID *)a2 + 8));
  }
  if ( !FtcCopyUnicodeString((PUNICODE_STRING)((char *)v3 + 24), *((PCUNICODE_STRING *)a2 + 10), 0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 216, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
LABEL_20:
    LocalFree(*((HLOCAL *)v3 + 2));
    goto LABEL_21;
  }
  v9 = (const UNICODE_STRING *)*((_QWORD *)a2 + 11);
  if ( !v9 )
  {
    *((_QWORD *)v3 + 6) = 0;
    *((_DWORD *)v3 + 10) = 0;
    return (struct _LSA_FOREST_TRUST_RECORD2 *)v3;
  }
  if ( !FtcCopyUnicodeString((PUNICODE_STRING)((char *)v3 + 40), v9, 0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    LocalFree(*((HLOCAL *)v3 + 4));
    goto LABEL_20;
  }
  return (struct _LSA_FOREST_TRUST_RECORD2 *)v3;
}

```

## disassembly

```asm
0x18002a5ac  mov     [rsp+arg_0], rbx
0x18002a5b1  mov     [rsp+arg_8], rsi
0x18002a5b6  push    rdi
0x18002a5b7  sub     rsp, 20h
0x18002a5bb  mov     rdi, rdx
0x18002a5be  mov     edx, 38h ; '8'; uBytes
0x18002a5c3  lea     ecx, [rdx+8]; uFlags
0x18002a5c6  call    cs:__imp_LocalAlloc
0x18002a5cc  mov     rbx, rax
0x18002a5cf  test    rax, rax
0x18002a5d2  jnz     short loc_18002A5FF
0x18002a5d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a5db  test    byte ptr [rcx+1Ch], 8
0x18002a5df  jz      loc_18002A708
0x18002a5e5  mov     edx, 0D6h
0x18002a5ea  mov     rcx, [rcx+10h]
0x18002a5ee  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a5f5  call    WPP_SF_
0x18002a5fa  jmp     loc_18002A708
0x18002a5ff  xorps   xmm0, xmm0
0x18002a602  xor     eax, eax
0x18002a604  movups  xmmword ptr [rbx], xmm0
0x18002a607  xor     esi, esi
0x18002a609  movups  xmmword ptr [rbx+10h], xmm0
0x18002a60d  movups  xmmword ptr [rbx+20h], xmm0
0x18002a611  mov     [rbx+30h], rax
0x18002a615  mov     rcx, [rdi+40h]; Sid
0x18002a619  test    rcx, rcx
0x18002a61c  jz      short loc_18002A626
0x18002a61e  call    cs:__imp_RtlLengthSid
0x18002a624  mov     esi, eax
0x18002a626  mov     rdx, [rdi+30h]
0x18002a62a  mov     [rbx+8], rdx
0x18002a62e  mov     edx, [rdi+60h]
0x18002a631  mov     [rbx], edx
0x18002a633  mov     dword ptr [rbx+4], 4
0x18002a63a  cmp     qword ptr [rdi+40h], 0
0x18002a63f  jz      short loc_18002A681
0x18002a641  mov     edx, esi; uBytes
0x18002a643  mov     ecx, 40h ; '@'; uFlags
0x18002a648  call    cs:__imp_LocalAlloc
0x18002a64e  mov     [rbx+10h], rax
0x18002a652  test    rax, rax
0x18002a655  jnz     short loc_18002A672
0x18002a657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a65e  test    byte ptr [rcx+1Ch], 8
0x18002a662  jz      loc_18002A708
0x18002a668  mov     edx, 0D7h
0x18002a66d  jmp     loc_18002A5EA
0x18002a672  mov     r8, [rdi+40h]; SourceSid
0x18002a676  mov     rdx, rax; DestinationSid
0x18002a679  mov     ecx, esi; DestinationSidLength
0x18002a67b  call    cs:__imp_RtlCopySid
0x18002a681  mov     rdx, [rdi+50h]; SourceString
0x18002a685  lea     rcx, [rbx+18h]; DestinationString
0x18002a689  xor     r8d, r8d; unsigned __int16 *
0x18002a68c  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002a691  test    al, al
0x18002a693  jnz     short loc_18002A6B9
0x18002a695  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a69c  test    byte ptr [rcx+1Ch], 8
0x18002a6a0  jz      short loc_18002A6FE
0x18002a6a2  mov     rcx, [rcx+10h]
0x18002a6a6  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a6ad  mov     edx, 0D8h
0x18002a6b2  call    WPP_SF_
0x18002a6b7  jmp     short loc_18002A6FE
0x18002a6b9  mov     rdx, [rdi+58h]; SourceString
0x18002a6bd  test    rdx, rdx
0x18002a6c0  jz      short loc_18002A715
0x18002a6c2  xor     r8d, r8d; unsigned __int16 *
0x18002a6c5  lea     rcx, [rbx+28h]; DestinationString
0x18002a6c9  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002a6ce  test    al, al
0x18002a6d0  jnz     short loc_18002A722
0x18002a6d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a6d9  test    byte ptr [rcx+1Ch], 8
0x18002a6dd  jz      short loc_18002A6F4
0x18002a6df  mov     rcx, [rcx+10h]
0x18002a6e3  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a6ea  mov     edx, 0D9h
0x18002a6ef  call    WPP_SF_
0x18002a6f4  mov     rcx, [rbx+20h]; hMem
0x18002a6f8  call    cs:__imp_LocalFree
0x18002a6fe  mov     rcx, [rbx+10h]; hMem
0x18002a702  call    cs:__imp_LocalFree
0x18002a708  mov     rcx, rbx; hMem
0x18002a70b  call    cs:__imp_LocalFree
0x18002a711  xor     ebx, ebx
0x18002a713  jmp     short loc_18002A722
0x18002a715  xor     ecx, ecx
0x18002a717  mov     qword ptr [rbx+30h], 0
0x18002a71f  mov     [rbx+28h], ecx
0x18002a722  mov     rsi, [rsp+28h+arg_8]
0x18002a727  mov     rax, rbx
0x18002a72a  mov     rbx, [rsp+28h+arg_0]
0x18002a72f  add     rsp, 20h
0x18002a733  pop     rdi
0x18002a734  retn
```
