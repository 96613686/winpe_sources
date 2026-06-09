# FTCache::RecordFromDomainInfoEntry(FTCache::DOMAIN_INFO_ENTRY *)

- ea: `0x18002a43c`
- end: `0x18002a5a3`
- name: `?RecordFromDomainInfoEntry@FTCache@@AEAAPEAU_LSA_FOREST_TRUST_RECORD2@@PEAUDOMAIN_INFO_ENTRY@1@@Z`
- size: `359`
- prototype: `struct _LSA_FOREST_TRUST_RECORD2 *__fastcall(FTCache *__hidden this, struct FTCache::DOMAIN_INFO_ENTRY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002aa14`

## callees

- `0x18000fd18`
- `0x180022278`
- `0x18002a43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a456`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a4b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a456`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a4b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a570`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a579`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a570`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a579`
- `ntdll!RtlCopySid` at `0x18002a4e9`
- `ntdll!RtlCopySid` at `0x18002a4e9`
- `ntdll!RtlLengthSid` at `0x18002a493`
- `ntdll!RtlLengthSid` at `0x18002a493`

## pseudocode

```c
struct _LSA_FOREST_TRUST_RECORD2 *__fastcall FTCache::RecordFromDomainInfoEntry(
        FTCache *this,
        struct FTCache::DOMAIN_INFO_ENTRY *a2)
{
  _DWORD *v3; // rbx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  ULONG v6; // eax
  ULONG v7; // esi
  HLOCAL v8; // rax
  const UNICODE_STRING *v9; // rdx

  v3 = LocalAlloc(0x40u, 0x38u);
  if ( !v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    {
LABEL_17:
      LocalFree(v3);
      return 0;
    }
    v5 = 210;
LABEL_4:
    WPP_SF_(v4[2], v5, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    goto LABEL_17;
  }
  v6 = RtlLengthSid(*((PSID *)a2 + 10));
  *((_QWORD *)v3 + 1) = *((_QWORD *)a2 + 8);
  *v3 = *((_DWORD *)a2 + 32);
  v7 = v6;
  v3[1] = 2;
  v8 = LocalAlloc(0x40u, v6);
  *((_QWORD *)v3 + 2) = v8;
  if ( !v8 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_17;
    v5 = 211;
    goto LABEL_4;
  }
  RtlCopySid(v7, v8, *((PSID *)a2 + 10));
  if ( !FtcCopyUnicodeString((PUNICODE_STRING)(v3 + 6), *((PCUNICODE_STRING *)a2 + 14), 0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
LABEL_16:
    LocalFree(*((HLOCAL *)v3 + 2));
    goto LABEL_17;
  }
  v9 = (const UNICODE_STRING *)*((_QWORD *)a2 + 15);
  if ( !v9 )
  {
    *((_QWORD *)v3 + 6) = 0;
    v3[10] = 0;
    return (struct _LSA_FOREST_TRUST_RECORD2 *)v3;
  }
  if ( !FtcCopyUnicodeString((PUNICODE_STRING)(v3 + 10), v9, 0) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    LocalFree(*((HLOCAL *)v3 + 4));
    goto LABEL_16;
  }
  return (struct _LSA_FOREST_TRUST_RECORD2 *)v3;
}

```

## disassembly

```asm
0x18002a43c  mov     [rsp+arg_0], rbx
0x18002a441  mov     [rsp+arg_8], rsi
0x18002a446  push    rdi
0x18002a447  sub     rsp, 20h
0x18002a44b  mov     rdi, rdx
0x18002a44e  mov     edx, 38h ; '8'; uBytes
0x18002a453  lea     ecx, [rdx+8]; uFlags
0x18002a456  call    cs:__imp_LocalAlloc
0x18002a45c  mov     rbx, rax
0x18002a45f  test    rax, rax
0x18002a462  jnz     short loc_18002A48F
0x18002a464  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a46b  test    byte ptr [rcx+1Ch], 8
0x18002a46f  jz      loc_18002A576
0x18002a475  mov     edx, 0D2h
0x18002a47a  mov     rcx, [rcx+10h]
0x18002a47e  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a485  call    WPP_SF_
0x18002a48a  jmp     loc_18002A576
0x18002a48f  mov     rcx, [rdi+50h]; Sid
0x18002a493  call    cs:__imp_RtlLengthSid
0x18002a499  mov     rdx, [rdi+40h]
0x18002a49d  mov     ecx, 40h ; '@'; uFlags
0x18002a4a2  mov     [rbx+8], rdx
0x18002a4a6  mov     edx, [rdi+80h]
0x18002a4ac  mov     [rbx], edx
0x18002a4ae  mov     edx, eax; uBytes
0x18002a4b0  mov     esi, eax
0x18002a4b2  mov     dword ptr [rbx+4], 2
0x18002a4b9  call    cs:__imp_LocalAlloc
0x18002a4bf  mov     [rbx+10h], rax
0x18002a4c3  test    rax, rax
0x18002a4c6  jnz     short loc_18002A4E0
0x18002a4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a4cf  test    byte ptr [rcx+1Ch], 8
0x18002a4d3  jz      loc_18002A576
0x18002a4d9  mov     edx, 0D3h
0x18002a4de  jmp     short loc_18002A47A
0x18002a4e0  mov     r8, [rdi+50h]; SourceSid
0x18002a4e4  mov     rdx, rax; DestinationSid
0x18002a4e7  mov     ecx, esi; DestinationSidLength
0x18002a4e9  call    cs:__imp_RtlCopySid
0x18002a4ef  mov     rdx, [rdi+70h]; SourceString
0x18002a4f3  lea     rcx, [rbx+18h]; DestinationString
0x18002a4f7  xor     r8d, r8d; unsigned __int16 *
0x18002a4fa  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002a4ff  test    al, al
0x18002a501  jnz     short loc_18002A527
0x18002a503  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a50a  test    byte ptr [rcx+1Ch], 8
0x18002a50e  jz      short loc_18002A56C
0x18002a510  mov     rcx, [rcx+10h]
0x18002a514  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a51b  mov     edx, 0D4h
0x18002a520  call    WPP_SF_
0x18002a525  jmp     short loc_18002A56C
0x18002a527  mov     rdx, [rdi+78h]; SourceString
0x18002a52b  test    rdx, rdx
0x18002a52e  jz      short loc_18002A583
0x18002a530  xor     r8d, r8d; unsigned __int16 *
0x18002a533  lea     rcx, [rbx+28h]; DestinationString
0x18002a537  call    ?FtcCopyUnicodeString@@YAEPEAU_UNICODE_STRING@@PEBU1@PEAG@Z; FtcCopyUnicodeString(_UNICODE_STRING *,_UNICODE_STRING const *,ushort *)
0x18002a53c  test    al, al
0x18002a53e  jnz     short loc_18002A590
0x18002a540  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a547  test    byte ptr [rcx+1Ch], 8
0x18002a54b  jz      short loc_18002A562
0x18002a54d  mov     rcx, [rcx+10h]
0x18002a551  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x18002a558  mov     edx, 0D5h
0x18002a55d  call    WPP_SF_
0x18002a562  mov     rcx, [rbx+20h]; hMem
0x18002a566  call    cs:__imp_LocalFree
0x18002a56c  mov     rcx, [rbx+10h]; hMem
0x18002a570  call    cs:__imp_LocalFree
0x18002a576  mov     rcx, rbx; hMem
0x18002a579  call    cs:__imp_LocalFree
0x18002a57f  xor     ebx, ebx
0x18002a581  jmp     short loc_18002A590
0x18002a583  xor     ecx, ecx
0x18002a585  mov     qword ptr [rbx+30h], 0
0x18002a58d  mov     [rbx+28h], ecx
0x18002a590  mov     rsi, [rsp+28h+arg_8]
0x18002a595  mov     rax, rbx
0x18002a598  mov     rbx, [rsp+28h+arg_0]
0x18002a59d  add     rsp, 20h
0x18002a5a1  pop     rdi
0x18002a5a2  retn
```
