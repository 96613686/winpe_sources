# LpcLookupWellKnownSid(_SPM_LPC_MESSAGE *)

- ea: `0x1800c9e50`
- end: `0x1800ca000`
- name: `?LpcLookupWellKnownSid@@YAJPEAU_SPM_LPC_MESSAGE@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(struct _SPM_LPC_MESSAGE *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180011278`
- `0x1800b86d0`
- `0x1800bd6e0`
- `0x1800c9e50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c9e97`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800c9e97`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c9f93`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800c9f93`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f20`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f51`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f66`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f20`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f51`
- `ntdll!RtlSubAuthorityCountSid` at `0x1800c9f66`
- `ntdll!RtlSubAuthoritySid` at `0x1800c9f3c`
- `ntdll!RtlSubAuthoritySid` at `0x1800c9f3c`
- `ntdll!RtlLengthSid` at `0x1800c9edb`
- `ntdll!RtlLengthSid` at `0x1800c9efd`
- `ntdll!RtlLengthSid` at `0x1800c9edb`
- `ntdll!RtlLengthSid` at `0x1800c9efd`

## pseudocode

```c
__int64 __fastcall LpcLookupWellKnownSid(struct _SPM_LPC_MESSAGE *a1)
{
  unsigned int *Value; // rax
  PSID v3; // rcx
  ULONG v5; // eax
  PUCHAR v6; // rax
  UCHAR v7; // bl
  BOOL v8; // r8d
  __int16 v9; // cx
  DWORD cbSid; // [rsp+20h] [rbp-58h] BYREF
  _BYTE Sid[68]; // [rsp+24h] [rbp-54h] BYREF

  cbSid = 0;
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    Value = (unsigned int *)TlsGetValue(dwSession);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids, Value[4]);
  }
  v3 = LsapAccountDomainMemberSid;
  *((_QWORD *)a1 + 9) = 216;
  cbSid = 288;
  if ( RtlLengthSid(v3) > 0x44 )
    return 2148074244LL;
  v5 = RtlLengthSid(LsapAccountDomainMemberSid);
  memcpy_0(Sid, LsapAccountDomainMemberSid, v5);
  v6 = RtlSubAuthorityCountSid(Sid);
  if ( !*RtlSubAuthoritySid(Sid, (unsigned int)*v6 - 1) )
  {
    v7 = *RtlSubAuthorityCountSid(Sid) - 1;
    *RtlSubAuthorityCountSid(Sid) = v7;
  }
  if ( cbSid > 0x44 )
    cbSid = 68;
  v8 = CreateWellKnownSid(*((WELL_KNOWN_SID_TYPE *)a1 + 16), Sid, (char *)a1 + 216, &cbSid);
  if ( v8 )
    v9 = cbSid;
  else
    v9 = 0;
  *((_WORD *)a1 + 24) &= 0xFEF8u;
  *((_WORD *)a1 + 1) = v9 + 216;
  *(_WORD *)a1 = v9 + 176;
  *((_DWORD *)a1 + 11) = !v8 ? 0xC000000D : 0;
  if ( !v8 )
    *((_WORD *)a1 + 24) |= 1u;
  return 0;
}

```

## disassembly

```asm
0x1800c9e50  push    rbp
0x1800c9e52  push    rbx
0x1800c9e53  push    rsi
0x1800c9e54  push    rdi
0x1800c9e55  push    r14
0x1800c9e57  push    r15
0x1800c9e59  mov     rbp, rsp
0x1800c9e5c  sub     rsp, 78h
0x1800c9e60  mov     rax, cs:__security_cookie
0x1800c9e67  xor     rax, rsp
0x1800c9e6a  mov     [rbp+var_10], rax
0x1800c9e6e  mov     rdi, rcx
0x1800c9e71  mov     [rbp+cbSid], 0
0x1800c9e78  mov     rax, cs:WPP_GLOBAL_Control
0x1800c9e7f  lea     rcx, WPP_GLOBAL_Control
0x1800c9e86  cmp     rax, rcx
0x1800c9e89  jz      short loc_1800C9EC3
0x1800c9e8b  test    byte ptr [rax+1Ch], 4
0x1800c9e8f  jz      short loc_1800C9EC3
0x1800c9e91  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x1800c9e97  call    cs:__imp_TlsGetValue
0x1800c9e9e  nop     dword ptr [rax+rax+00h]
0x1800c9ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9eaa  lea     r8, WPP_3d7179d4473f3929e4c7f3204c0b1992_Traceguids
0x1800c9eb1  mov     edx, 29h ; ')'
0x1800c9eb6  mov     r9d, [rax+10h]
0x1800c9eba  mov     rcx, [rcx+10h]
0x1800c9ebe  call    WPP_SF_d
0x1800c9ec3  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Sid
0x1800c9eca  mov     r14d, 0D8h
0x1800c9ed0  mov     [rdi+48h], r14
0x1800c9ed4  mov     [rbp+cbSid], 120h
0x1800c9edb  call    cs:__imp_RtlLengthSid
0x1800c9ee2  nop     dword ptr [rax+rax+00h]
0x1800c9ee7  cmp     eax, 44h ; 'D'
0x1800c9eea  jbe     short loc_1800C9EF6
0x1800c9eec  mov     eax, 80090304h
0x1800c9ef1  jmp     loc_1800C9FE6
0x1800c9ef6  mov     rcx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Sid
0x1800c9efd  call    cs:__imp_RtlLengthSid
0x1800c9f04  nop     dword ptr [rax+rax+00h]
0x1800c9f09  mov     rdx, cs:?LsapAccountDomainMemberSid@@3PEAXEA; Src
0x1800c9f10  lea     rcx, [rbp+Sid]; void *
0x1800c9f14  mov     r8d, eax; Size
0x1800c9f17  call    memcpy_0
0x1800c9f1c  lea     rcx, [rbp+Sid]; Sid
0x1800c9f20  call    cs:__imp_RtlSubAuthorityCountSid
0x1800c9f27  nop     dword ptr [rax+rax+00h]
0x1800c9f2c  mov     r15d, 1
0x1800c9f32  lea     rcx, [rbp+Sid]; Sid
0x1800c9f36  movzx   edx, byte ptr [rax]
0x1800c9f39  sub     edx, r15d; SubAuthority
0x1800c9f3c  call    cs:__imp_RtlSubAuthoritySid
0x1800c9f43  nop     dword ptr [rax+rax+00h]
0x1800c9f48  cmp     dword ptr [rax], 0
0x1800c9f4b  jnz     short loc_1800C9F74
0x1800c9f4d  lea     rcx, [rbp+Sid]; Sid
0x1800c9f51  call    cs:__imp_RtlSubAuthorityCountSid
0x1800c9f58  nop     dword ptr [rax+rax+00h]
0x1800c9f5d  lea     rcx, [rbp+Sid]; Sid
0x1800c9f61  mov     bl, [rax]
0x1800c9f63  sub     bl, r15b
0x1800c9f66  call    cs:__imp_RtlSubAuthorityCountSid
0x1800c9f6d  nop     dword ptr [rax+rax+00h]
0x1800c9f72  mov     [rax], bl
0x1800c9f74  cmp     [rbp+cbSid], 44h ; 'D'
0x1800c9f78  jbe     short loc_1800C9F81
0x1800c9f7a  mov     [rbp+cbSid], 44h ; 'D'
0x1800c9f81  mov     ecx, [rdi+40h]; WellKnownSidType
0x1800c9f84  lea     r9, [rbp+cbSid]; cbSid
0x1800c9f88  lea     r8, [rdi+0D8h]; pSid
0x1800c9f8f  lea     rdx, [rbp+Sid]; DomainSid
0x1800c9f93  call    cs:__imp_CreateWellKnownSid
0x1800c9f9a  nop     dword ptr [rax+rax+00h]
0x1800c9f9f  mov     r8d, eax
0x1800c9fa2  test    eax, eax
0x1800c9fa4  jnz     short loc_1800C9FAA
0x1800c9fa6  xor     ecx, ecx
0x1800c9fa8  jmp     short loc_1800C9FAD
0x1800c9faa  mov     ecx, [rbp+cbSid]
0x1800c9fad  mov     eax, 0FEF8h
0x1800c9fb2  and     [rdi+30h], ax
0x1800c9fb6  mov     eax, 0B0h
0x1800c9fbb  add     eax, ecx
0x1800c9fbd  add     cx, r14w
0x1800c9fc1  mov     [rdi+2], cx
0x1800c9fc5  mov     [rdi], ax
0x1800c9fc8  mov     eax, r8d
0x1800c9fcb  neg     eax
0x1800c9fcd  sbb     ecx, ecx
0x1800c9fcf  not     ecx
0x1800c9fd1  and     ecx, 0C000000Dh
0x1800c9fd7  mov     [rdi+2Ch], ecx
0x1800c9fda  test    r8d, r8d
0x1800c9fdd  jnz     short loc_1800C9FE4
0x1800c9fdf  or      [rdi+30h], r15w
0x1800c9fe4  xor     eax, eax
0x1800c9fe6  mov     rcx, [rbp+var_10]
0x1800c9fea  xor     rcx, rsp; StackCookie
0x1800c9fed  call    __security_check_cookie
0x1800c9ff2  add     rsp, 78h
0x1800c9ff6  pop     r15
0x1800c9ff8  pop     r14
0x1800c9ffa  pop     rdi
0x1800c9ffb  pop     rsi
0x1800c9ffc  pop     rbx
0x1800c9ffd  pop     rbp
0x1800c9ffe  retn
```
