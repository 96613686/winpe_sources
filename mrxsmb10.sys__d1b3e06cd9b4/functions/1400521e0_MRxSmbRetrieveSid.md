# MRxSmbRetrieveSid

- ea: `0x1400521e0`
- end: `0x140052298`
- name: `MRxSmbRetrieveSid`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140036d40`

## callees

- `0x1400521e0`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x140052255`
- `ntoskrnl!RtlCopySid` at `0x140052255`
- `ntoskrnl!SeQueryInformationToken` at `0x140052227`
- `ntoskrnl!SeQueryInformationToken` at `0x140052227`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052272`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052272`

## pseudocode

```c
NTSTATUS __fastcall MRxSmbRetrieveSid(__int64 a1, void *a2)
{
  __int64 v2; // rax
  __int64 v4; // r8
  void *v5; // rcx
  NTSTATUS result; // eax
  int v7; // ebx
  PVOID v8; // r9
  ULONG v9; // ecx
  PVOID TokenInformation; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)(a1 + 544);
  TokenInformation = 0;
  if ( !v2 )
    return -1073741823;
  v4 = *(_QWORD *)(v2 + 8);
  v5 = *(void **)(v4 + 32);
  if ( !v5 )
  {
    v5 = *(void **)(v4 + 48);
    if ( !v5 )
      return -1073741823;
  }
  result = SeQueryInformationToken(v5, TokenUser, &TokenInformation);
  v7 = result;
  if ( !result )
  {
    v8 = TokenInformation;
    v9 = 4 * *(unsigned __int8 *)(*(_QWORD *)TokenInformation + 1LL) + 8;
    if ( v9 > 0x44 )
    {
      v7 = -2147483643;
    }
    else
    {
      RtlCopySid(v9, a2, *(PSID *)TokenInformation);
      v8 = TokenInformation;
    }
    ExFreePoolWithTag(v8, 0);
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x1400521e0  push    rdi
0x1400521e2  sub     rsp, 20h
0x1400521e6  mov     rax, [rcx+220h]
0x1400521ed  mov     rdi, rdx
0x1400521f0  mov     [rsp+28h+TokenInformation], 0
0x1400521f9  test    rax, rax
0x1400521fc  jz      loc_14005228C
0x140052202  mov     r8, [rax+8]
0x140052206  mov     rcx, [r8+20h]
0x14005220a  test    rcx, rcx
0x14005220d  jnz     short loc_140052218
0x14005220f  mov     rcx, [r8+30h]; Token
0x140052213  test    rcx, rcx
0x140052216  jz      short loc_14005228C
0x140052218  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x14005221d  mov     [rsp+28h+arg_8], rbx
0x140052222  mov     edx, 1; TokenInformationClass
0x140052227  call    cs:__imp_SeQueryInformationToken
0x14005222e  nop     dword ptr [rax+rax+00h]
0x140052233  mov     ebx, eax
0x140052235  test    eax, eax
0x140052237  jnz     short loc_140052280
0x140052239  mov     r9, [rsp+28h+TokenInformation]
0x14005223e  mov     r8, [r9]; SourceSid
0x140052241  movzx   ecx, byte ptr [r8+1]
0x140052246  lea     ecx, ds:8[rcx*4]; DestinationSidLength
0x14005224d  cmp     ecx, 44h ; 'D'
0x140052250  ja      short loc_140052268
0x140052252  mov     rdx, rdi; DestinationSid
0x140052255  call    cs:__imp_RtlCopySid
0x14005225c  nop     dword ptr [rax+rax+00h]
0x140052261  mov     r9, [rsp+28h+TokenInformation]
0x140052266  jmp     short loc_14005226D
0x140052268  mov     ebx, 80000005h
0x14005226d  xor     edx, edx; Tag
0x14005226f  mov     rcx, r9; P
0x140052272  call    cs:__imp_ExFreePoolWithTag
0x140052279  nop     dword ptr [rax+rax+00h]
0x14005227e  mov     eax, ebx
0x140052280  mov     rbx, [rsp+28h+arg_8]
0x140052285  add     rsp, 20h
0x140052289  pop     rdi
0x14005228a  retn
0x14005228c  mov     eax, 0C0000001h
0x140052291  add     rsp, 20h
0x140052295  pop     rdi
0x140052296  retn
```
