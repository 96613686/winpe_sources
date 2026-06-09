# GetWindowsAccountCloudDomainSid(void *,void *,ulong *)

- ea: `0x180105f04`
- end: `0x1801060d9`
- name: `?GetWindowsAccountCloudDomainSid@@YA_NPEAX0PEAK@Z`
- size: `469`
- prototype: `bool __fastcall(PSID Sid, PSID, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18001b760`

## callees

- `0x180011278`
- `0x1800284d4`
- `0x180105f04`
- `0x180106170`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801060bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801060bd`
- `ntdll!RtlSubAuthorityCountSid` at `0x180105f76`
- `ntdll!RtlSubAuthorityCountSid` at `0x180105f76`
- `ntdll!RtlSubAuthoritySid` at `0x180105f98`
- `ntdll!RtlSubAuthoritySid` at `0x18010608d`
- `ntdll!RtlSubAuthoritySid` at `0x1801060a0`
- `ntdll!RtlSubAuthoritySid` at `0x180105f98`
- `ntdll!RtlSubAuthoritySid` at `0x18010608d`
- `ntdll!RtlSubAuthoritySid` at `0x1801060a0`
- `ntdll!RtlValidSid` at `0x180105f1a`
- `ntdll!RtlValidSid` at `0x180105f1a`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180105f45`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180106036`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180105f45`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180106036`
- `ntdll!RtlInitializeSid` at `0x18010604b`
- `ntdll!RtlInitializeSid` at `0x18010604b`
- `ntdll!RtlLengthRequiredSid` at `0x18010600a`
- `ntdll!RtlLengthRequiredSid` at `0x18010600a`

## pseudocode

```c
char __fastcall GetWindowsAccountCloudDomainSid(PSID Sid, PSID a2, unsigned int *a3)
{
  DWORD v6; // ecx
  UCHAR v7; // di
  unsigned __int8 v8; // bl
  PSID_IDENTIFIER_AUTHORITY v9; // rax
  int v10; // ecx
  unsigned __int8 IsEnabled; // al
  ULONG v12; // ebp
  ULONG v13; // eax
  ULONG v14; // ecx
  struct _SID_IDENTIFIER_AUTHORITY *v15; // rax
  NTSTATUS v16; // eax
  ULONG i; // edi
  ULONG v18; // ebx
  PULONG v19; // rax

  if ( !RtlValidSid(Sid) )
  {
    v6 = 1337;
LABEL_26:
    SetLastError(v6);
    return 0;
  }
  if ( !a3 )
    goto LABEL_25;
  v7 = 0;
  v8 = 0;
  v9 = RtlIdentifierAuthoritySid(Sid);
  v10 = *(_DWORD *)v9->Value;
  if ( !*(_DWORD *)v9->Value )
    v10 = *(unsigned __int16 *)&v9->Value[4] - 3072;
  if ( !v10
    && *RtlSubAuthorityCountSid(Sid) == 4
    && (wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Bugfix_CloudSid>::GetImpl'::`2'::impl)
     || !*RtlSubAuthoritySid(Sid, 0)) )
  {
    v8 = 1;
    v7 = 4;
  }
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Bugfix_CloudSid>::GetImpl'::`2'::impl)
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Bugfix_CloudSid>::GetImpl'::`2'::impl);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids, v8, IsEnabled);
  }
  if ( !v8 )
  {
    v6 = 1257;
    goto LABEL_26;
  }
  v12 = v7;
  v13 = RtlLengthRequiredSid(v7);
  v14 = *a3;
  *a3 = v13;
  if ( v14 < v13 )
  {
    v6 = 122;
    goto LABEL_26;
  }
  if ( !a2 )
  {
LABEL_25:
    v6 = 87;
    goto LABEL_26;
  }
  v15 = RtlIdentifierAuthoritySid(Sid);
  v16 = RtlInitializeSid(a2, v15, v7);
  if ( v16 < 0 )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids,
        (unsigned int)v16);
    return 0;
  }
  for ( i = 0; i < v12; *v19 = v18 )
  {
    v18 = *RtlSubAuthoritySid(Sid, i);
    v19 = RtlSubAuthoritySid(a2, i++);
  }
  return 1;
}

```

## disassembly

```asm
0x180105f04  push    rbx
0x180105f06  push    rbp
0x180105f07  push    rsi
0x180105f08  push    rdi
0x180105f09  push    r14
0x180105f0b  push    r15
0x180105f0d  sub     rsp, 38h
0x180105f11  mov     r14, r8
0x180105f14  mov     r15, rdx
0x180105f17  mov     rsi, rcx
0x180105f1a  call    cs:__imp_RtlValidSid
0x180105f21  nop     dword ptr [rax+rax+00h]
0x180105f26  test    al, al
0x180105f28  jnz     short loc_180105F34
0x180105f2a  mov     ecx, 539h
0x180105f2f  jmp     loc_1801060BD
0x180105f34  test    r14, r14
0x180105f37  jz      loc_1801060B8
0x180105f3d  mov     rcx, rsi; Sid
0x180105f40  xor     dil, dil
0x180105f43  xor     bl, bl
0x180105f45  call    cs:__imp_RtlIdentifierAuthoritySid
0x180105f4c  nop     dword ptr [rax+rax+00h]
0x180105f51  mov     ecx, [rax]
0x180105f53  sub     ecx, cs:dword_18016CF38
0x180105f59  jnz     short loc_180105F68
0x180105f5b  movzx   ecx, word ptr [rax+4]
0x180105f5f  movzx   eax, cs:word_18016CF3C
0x180105f66  sub     ecx, eax
0x180105f68  lea     rbp, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_CloudSid@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_CloudSid@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_CloudSid>::GetImpl(void)'::`2'::impl
0x180105f6f  test    ecx, ecx
0x180105f71  jnz     short loc_180105FAE
0x180105f73  mov     rcx, rsi; Sid
0x180105f76  call    cs:__imp_RtlSubAuthorityCountSid
0x180105f7d  nop     dword ptr [rax+rax+00h]
0x180105f82  cmp     byte ptr [rax], 4
0x180105f85  jnz     short loc_180105FAE
0x180105f87  mov     rcx, rbp
0x180105f8a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_CloudSid@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled(void)
0x180105f8f  test    al, al
0x180105f91  jnz     short loc_180105FA9
0x180105f93  xor     edx, edx; SubAuthority
0x180105f95  mov     rcx, rsi; Sid
0x180105f98  call    cs:__imp_RtlSubAuthoritySid
0x180105f9f  nop     dword ptr [rax+rax+00h]
0x180105fa4  cmp     dword ptr [rax], 0
0x180105fa7  jnz     short loc_180105FAE
0x180105fa9  mov     bl, 1
0x180105fab  mov     dil, 4
0x180105fae  mov     rcx, rbp
0x180105fb1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_CloudSid@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled(void)
0x180105fb6  test    al, al
0x180105fb8  jz      short loc_180105FF6
0x180105fba  mov     rax, cs:WPP_GLOBAL_Control
0x180105fc1  test    byte ptr [rax+1Ch], 4
0x180105fc5  jz      short loc_180105FF6
0x180105fc7  mov     rcx, rbp
0x180105fca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_CloudSid@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_CloudSid>::__private_IsEnabled(void)
0x180105fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180105fd6  lea     r8, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids
0x180105fdd  movzx   eax, al
0x180105fe0  mov     edx, 0Bh
0x180105fe5  movzx   r9d, bl
0x180105fe9  mov     [rsp+68h+var_48], eax
0x180105fed  mov     rcx, [rcx+10h]
0x180105ff1  call    WPP_SF_Dd
0x180105ff6  test    bl, bl
0x180105ff8  jnz     short loc_180106004
0x180105ffa  mov     ecx, 4E9h
0x180105fff  jmp     loc_1801060BD
0x180106004  movzx   ebp, dil
0x180106008  mov     ecx, ebp; SubAuthorityCount
0x18010600a  call    cs:__imp_RtlLengthRequiredSid
0x180106011  nop     dword ptr [rax+rax+00h]
0x180106016  mov     ecx, [r14]
0x180106019  mov     [r14], eax
0x18010601c  cmp     ecx, eax
0x18010601e  jnb     short loc_18010602A
0x180106020  mov     ecx, 7Ah ; 'z'
0x180106025  jmp     loc_1801060BD
0x18010602a  test    r15, r15
0x18010602d  jz      loc_1801060B8
0x180106033  mov     rcx, rsi; Sid
0x180106036  call    cs:__imp_RtlIdentifierAuthoritySid
0x18010603d  nop     dword ptr [rax+rax+00h]
0x180106042  mov     r8b, dil; SubAuthorityCount
0x180106045  mov     rcx, r15; Sid
0x180106048  mov     rdx, rax; IdentifierAuthority
0x18010604b  call    cs:__imp_RtlInitializeSid
0x180106052  nop     dword ptr [rax+rax+00h]
0x180106057  test    eax, eax
0x180106059  jns     short loc_180106082
0x18010605b  mov     rcx, cs:WPP_GLOBAL_Control
0x180106062  test    byte ptr [rcx+1Ch], 1
0x180106066  jz      short loc_1801060C9
0x180106068  mov     rcx, [rcx+10h]
0x18010606c  lea     r8, WPP_87b3b7cc10c835e5694d3c1700f89fb3_Traceguids
0x180106073  mov     edx, 0Ch
0x180106078  mov     r9d, eax
0x18010607b  call    WPP_SF_d
0x180106080  jmp     short loc_1801060C9
0x180106082  xor     edi, edi
0x180106084  test    ebp, ebp
0x180106086  jz      short loc_1801060B4
0x180106088  mov     edx, edi; SubAuthority
0x18010608a  mov     rcx, rsi; Sid
0x18010608d  call    cs:__imp_RtlSubAuthoritySid
0x180106094  nop     dword ptr [rax+rax+00h]
0x180106099  mov     edx, edi; SubAuthority
0x18010609b  mov     rcx, r15; Sid
0x18010609e  mov     ebx, [rax]
0x1801060a0  call    cs:__imp_RtlSubAuthoritySid
0x1801060a7  nop     dword ptr [rax+rax+00h]
0x1801060ac  inc     edi
0x1801060ae  mov     [rax], ebx
0x1801060b0  cmp     edi, ebp
0x1801060b2  jb      short loc_180106088
0x1801060b4  mov     al, 1
0x1801060b6  jmp     short loc_1801060CB
0x1801060b8  mov     ecx, 57h ; 'W'; dwErrCode
0x1801060bd  call    cs:__imp_SetLastError
0x1801060c4  nop     dword ptr [rax+rax+00h]
0x1801060c9  xor     al, al
0x1801060cb  add     rsp, 38h
0x1801060cf  pop     r15
0x1801060d1  pop     r14
0x1801060d3  pop     rdi
0x1801060d4  pop     rsi
0x1801060d5  pop     rbp
0x1801060d6  pop     rbx
0x1801060d7  retn
```
