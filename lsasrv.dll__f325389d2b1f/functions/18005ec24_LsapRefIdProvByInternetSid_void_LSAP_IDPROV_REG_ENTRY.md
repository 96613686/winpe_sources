# LsapRefIdProvByInternetSid(void *,_LSAP_IDPROV_REG_ENTRY * *)

- ea: `0x18005ec24`
- end: `0x18005ed94`
- name: `?LsapRefIdProvByInternetSid@@YAJPEAXPEAPEAU_LSAP_IDPROV_REG_ENTRY@@@Z`
- size: `368`
- prototype: `__int64 __fastcall(PSID Sid, struct _LSAP_IDPROV_REG_ENTRY **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005eda0`
- `0x180060e6c`
- `0x180061e88`
- `0x180128560`

## callees

- `0x18005ec24`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18005ed07`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ed19`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ed07`
- `ntdll!RtlSubAuthorityCountSid` at `0x18005ed19`
- `ntdll!RtlSubAuthoritySid` at `0x18005ed43`
- `ntdll!RtlSubAuthoritySid` at `0x18005ed57`
- `ntdll!RtlSubAuthoritySid` at `0x18005ed43`
- `ntdll!RtlSubAuthoritySid` at `0x18005ed57`
- `ntdll!RtlReleaseResource` at `0x18005eca4`
- `ntdll!RtlReleaseResource` at `0x18005eca4`
- `ntdll!RtlAcquireResourceShared` at `0x18005ec6a`
- `ntdll!RtlAcquireResourceShared` at `0x18005ec6a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005ecd2`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005ece4`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005ecd2`
- `ntdll!RtlIdentifierAuthoritySid` at `0x18005ece4`

## pseudocode

```c
__int64 __fastcall LsapRefIdProvByInternetSid(PSID Sid, struct _LIST_ENTRY **a2)
{
  bool v4; // zf
  struct _LIST_ENTRY *i; // rsi
  unsigned int v6; // ebx
  struct _LIST_ENTRY *Flink; // r13
  PSID_IDENTIFIER_AUTHORITY v9; // rbx
  PSID_IDENTIFIER_AUTHORITY v10; // rax
  int v11; // ecx
  PUCHAR v12; // r12
  UCHAR j; // bp
  PULONG v14; // rdi

  if ( !Sid || !a2 )
    return 3221225485LL;
  v4 = g_fHasInitIdProvExtension == 0;
  *a2 = 0;
  if ( v4 )
    return 3221226021LL;
  if ( !RtlAcquireResourceShared(&g_IdProvRegLock, 1u) )
    return 3221225473LL;
  for ( i = g_IdProvList.Flink; ; i = i->Flink )
  {
    if ( i == &g_IdProvList )
    {
      v6 = -1073741275;
      goto LABEL_10;
    }
    if ( HIDWORD(i[3].Blink) )
    {
      Flink = i[4].Flink;
      v9 = RtlIdentifierAuthoritySid(Flink);
      v10 = RtlIdentifierAuthoritySid(Sid);
      v11 = *(_DWORD *)v9->Value - *(_DWORD *)v10->Value;
      if ( *(_DWORD *)v9->Value == *(_DWORD *)v10->Value )
        v11 = *(unsigned __int16 *)&v9->Value[4] - *(unsigned __int16 *)&v10->Value[4];
      if ( !v11 )
      {
        v12 = RtlSubAuthorityCountSid(Flink);
        if ( *v12 <= *RtlSubAuthorityCountSid(Sid) )
          break;
      }
    }
LABEL_8:
    ;
  }
  for ( j = 0; j < *v12; ++j )
  {
    v14 = RtlSubAuthoritySid(Flink, j);
    if ( *RtlSubAuthoritySid(Sid, j) != *v14 )
      goto LABEL_8;
  }
  _InterlockedIncrement((volatile signed __int32 *)&i[1].Flink + 1);
  *a2 = i;
  v6 = 0;
LABEL_10:
  RtlReleaseResource(&g_IdProvRegLock);
  return v6;
}

```

## disassembly

```asm
0x18005ec24  push    rbx
0x18005ec26  push    rbp
0x18005ec27  push    rsi
0x18005ec28  push    rdi
0x18005ec29  push    r12
0x18005ec2b  push    r13
0x18005ec2d  push    r14
0x18005ec2f  push    r15
0x18005ec31  sub     rsp, 28h
0x18005ec35  mov     r14, rdx
0x18005ec38  mov     r15, rcx
0x18005ec3b  test    rcx, rcx
0x18005ec3e  jz      loc_18005ED8A
0x18005ec44  test    rdx, rdx
0x18005ec47  jz      loc_18005ED8A
0x18005ec4d  cmp     cs:?g_fHasInitIdProvExtension@@3HA, 0; int g_fHasInitIdProvExtension
0x18005ec54  mov     qword ptr [rdx], 0
0x18005ec5b  jz      loc_18005ED80
0x18005ec61  mov     dl, 1; Wait
0x18005ec63  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005ec6a  call    cs:__imp_RtlAcquireResourceShared
0x18005ec71  nop     dword ptr [rax+rax+00h]
0x18005ec76  test    al, al
0x18005ec78  jz      short loc_18005ECC4
0x18005ec7a  mov     rsi, cs:?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005ec81  lea     rax, ?g_IdProvList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_IdProvList
0x18005ec88  cmp     rsi, rax
0x18005ec8b  jz      short loc_18005EC98
0x18005ec8d  cmp     dword ptr [rsi+3Ch], 0
0x18005ec91  jnz     short loc_18005ECCB
0x18005ec93  mov     rsi, [rsi]
0x18005ec96  jmp     short loc_18005EC81
0x18005ec98  mov     ebx, 0C0000225h
0x18005ec9d  lea     rcx, ?g_IdProvRegLock@@3U_RTL_RESOURCE@@A; Resource
0x18005eca4  call    cs:__imp_RtlReleaseResource
0x18005ecab  nop     dword ptr [rax+rax+00h]
0x18005ecb0  mov     eax, ebx
0x18005ecb2  add     rsp, 28h
0x18005ecb6  pop     r15
0x18005ecb8  pop     r14
0x18005ecba  pop     r13
0x18005ecbc  pop     r12
0x18005ecbe  pop     rdi
0x18005ecbf  pop     rsi
0x18005ecc0  pop     rbp
0x18005ecc1  pop     rbx
0x18005ecc2  retn
0x18005ecc4  mov     eax, 0C0000001h
0x18005ecc9  jmp     short loc_18005ECB2
0x18005eccb  mov     r13, [rsi+40h]
0x18005eccf  mov     rcx, r13; Sid
0x18005ecd2  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005ecd9  nop     dword ptr [rax+rax+00h]
0x18005ecde  mov     rcx, r15; Sid
0x18005ece1  mov     rbx, rax
0x18005ece4  call    cs:__imp_RtlIdentifierAuthoritySid
0x18005eceb  nop     dword ptr [rax+rax+00h]
0x18005ecf0  mov     ecx, [rbx]
0x18005ecf2  sub     ecx, [rax]
0x18005ecf4  jnz     short loc_18005ED00
0x18005ecf6  movzx   ecx, word ptr [rbx+4]
0x18005ecfa  movzx   eax, word ptr [rax+4]
0x18005ecfe  sub     ecx, eax
0x18005ed00  test    ecx, ecx
0x18005ed02  jnz     short loc_18005EC93
0x18005ed04  mov     rcx, r13; Sid
0x18005ed07  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ed0e  nop     dword ptr [rax+rax+00h]
0x18005ed13  mov     rcx, r15; Sid
0x18005ed16  mov     r12, rax
0x18005ed19  call    cs:__imp_RtlSubAuthorityCountSid
0x18005ed20  nop     dword ptr [rax+rax+00h]
0x18005ed25  mov     cl, [rax]
0x18005ed27  cmp     [r12], cl
0x18005ed2b  ja      loc_18005EC93
0x18005ed31  xor     bpl, bpl
0x18005ed34  cmp     bpl, [r12]
0x18005ed38  jnb     short loc_18005ED72
0x18005ed3a  movzx   ebx, bpl
0x18005ed3e  mov     rcx, r13; Sid
0x18005ed41  mov     edx, ebx; SubAuthority
0x18005ed43  call    cs:__imp_RtlSubAuthoritySid
0x18005ed4a  nop     dword ptr [rax+rax+00h]
0x18005ed4f  mov     edx, ebx; SubAuthority
0x18005ed51  mov     rcx, r15; Sid
0x18005ed54  mov     rdi, rax
0x18005ed57  call    cs:__imp_RtlSubAuthoritySid
0x18005ed5e  nop     dword ptr [rax+rax+00h]
0x18005ed63  mov     ecx, [rdi]
0x18005ed65  cmp     [rax], ecx
0x18005ed67  jnz     loc_18005EC93
0x18005ed6d  inc     bpl
0x18005ed70  jmp     short loc_18005ED34
0x18005ed72  lock inc dword ptr [rsi+14h]
0x18005ed76  mov     [r14], rsi
0x18005ed79  xor     ebx, ebx
0x18005ed7b  jmp     loc_18005EC9D
0x18005ed80  mov     eax, 0C0000225h
0x18005ed85  jmp     loc_18005ECB2
0x18005ed8a  mov     eax, 0C000000Dh
0x18005ed8f  jmp     loc_18005ECB2
```
