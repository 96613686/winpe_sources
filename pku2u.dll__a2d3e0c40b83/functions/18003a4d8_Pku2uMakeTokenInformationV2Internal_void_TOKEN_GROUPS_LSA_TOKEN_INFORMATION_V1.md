# Pku2uMakeTokenInformationV2Internal(void *,_TOKEN_GROUPS *,_LSA_TOKEN_INFORMATION_V1 * *)

- ea: `0x18003a4d8`
- end: `0x18003a67f`
- name: `?Pku2uMakeTokenInformationV2Internal@@YAJPEAXPEAU_TOKEN_GROUPS@@PEAPEAU_LSA_TOKEN_INFORMATION_V1@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(PSID SourceSid, struct _TOKEN_GROUPS *, struct _LSA_TOKEN_INFORMATION_V1 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180039908`

## callees

- `0x1800057f0`
- `0x180018870`
- `0x18003a4d8`
- `0x18003b0e4`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18003a5b2`
- `ntdll!RtlCopySid` at `0x18003a5eb`
- `ntdll!RtlCopySid` at `0x18003a600`
- `ntdll!RtlCopySid` at `0x18003a5b2`
- `ntdll!RtlCopySid` at `0x18003a5eb`
- `ntdll!RtlCopySid` at `0x18003a600`
- `ntdll!RtlLengthSid` at `0x18003a512`
- `ntdll!RtlLengthSid` at `0x18003a524`
- `ntdll!RtlLengthSid` at `0x18003a5a0`
- `ntdll!RtlLengthSid` at `0x18003a5db`
- `ntdll!RtlLengthSid` at `0x18003a512`
- `ntdll!RtlLengthSid` at `0x18003a524`
- `ntdll!RtlLengthSid` at `0x18003a5a0`
- `ntdll!RtlLengthSid` at `0x18003a5db`

## string_xrefs

- `0x18003a630`: `Pku2uMakeTokenInformationV2Internal`

## pseudocode

```c
__int64 __fastcall Pku2uMakeTokenInformationV2Internal(
        PSID SourceSid,
        struct _TOKEN_GROUPS *a2,
        struct _LSA_TOKEN_INFORMATION_V1 **a3)
{
  DWORD v3; // edi
  struct _LSA_TOKEN_INFORMATION_V1 **v4; // r13
  DWORD i; // ebx
  unsigned __int64 v8; // r12
  union _LARGE_INTEGER *v9; // rax
  struct _LSA_TOKEN_INFORMATION_V1 *v10; // rsi
  __int64 result; // rax
  union _LARGE_INTEGER *v12; // rbp
  DWORD v13; // r13d
  __int64 v14; // rdi
  ULONG v15; // eax
  __int64 v16; // rbx
  ULONG v17; // eax
  __int64 v18; // rdi
  char *v19; // rbp
  int v20; // r8d

  v3 = 0;
  v4 = a3;
  for ( i = 16 * a2->GroupCount + 72; v3 < a2->GroupCount; ++v3 )
    i += RtlLengthSid(a2->Groups[v3].Sid);
  v8 = i + 2 * RtlLengthSid(SourceSid);
  v9 = (union _LARGE_INTEGER *)basessp::BaseSSP::WSTAllocate(Pku2uGlobalBaseSSP, v8);
  v10 = (struct _LSA_TOKEN_INFORMATION_V1 *)v9;
  if ( !v9 )
    return 3221225495LL;
  *v9 = Pku2uGlobalWillNeverTime;
  v9[3].QuadPart = (LONGLONG)&v9[8];
  v9[8].LowPart = a2->GroupCount;
  v12 = &v9[2 * a2->GroupCount + 9];
  if ( a2->GroupCount )
  {
    v13 = 0;
    do
    {
      v14 = v13;
      v10->Groups->Groups[v13].Attributes = a2->Groups[v13].Attributes;
      v15 = RtlLengthSid(a2->Groups[v13].Sid);
      v16 = v15;
      RtlCopySid(v15, v12, a2->Groups[v13++].Sid);
      v10->Groups->Groups[v14].Sid = v12;
      v12 = (union _LARGE_INTEGER *)((char *)v12 + v16);
    }
    while ( v13 < a2->GroupCount );
    v4 = a3;
  }
  v10->User.User.Sid = v12;
  v17 = RtlLengthSid(SourceSid);
  v18 = v17;
  RtlCopySid(v17, v12, SourceSid);
  v19 = (char *)v12 + v18;
  v10->PrimaryGroup.PrimaryGroup = v19;
  RtlCopySid(v18, v19, SourceSid);
  if ( (char *)v10 + v8 >= &v19[v18] )
  {
    result = 0;
    *v4 = v10;
    v10->Privileges = 0;
    v10->Owner.Owner = 0;
    v10->DefaultDacl.DefaultDacl = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v20, (unsigned int)"Pku2uMakeTokenInformationV2Internal", 229);
    Pku2uFree(v10);
    return 3221225701LL;
  }
  return result;
}

```

## disassembly

```asm
0x18003a4d8  mov     [rsp+arg_0], rbx
0x18003a4dd  mov     [rsp+arg_10], r8
0x18003a4e2  push    rbp
0x18003a4e3  push    rsi
0x18003a4e4  push    rdi
0x18003a4e5  push    r12
0x18003a4e7  push    r13
0x18003a4e9  push    r14
0x18003a4eb  push    r15
0x18003a4ed  sub     rsp, 30h
0x18003a4f1  mov     ebx, [rdx]
0x18003a4f3  xor     edi, edi
0x18003a4f5  shl     ebx, 4
0x18003a4f8  mov     r13, r8
0x18003a4fb  add     ebx, 48h ; 'H'
0x18003a4fe  mov     r14, rdx
0x18003a501  mov     r15, rcx
0x18003a504  cmp     [rdx], edi
0x18003a506  jbe     short loc_18003A521
0x18003a508  mov     ecx, edi
0x18003a50a  add     rcx, rcx
0x18003a50d  mov     rcx, [r14+rcx*8+8]; Sid
0x18003a512  call    cs:__imp_RtlLengthSid
0x18003a518  add     ebx, eax
0x18003a51a  inc     edi
0x18003a51c  cmp     edi, [r14]
0x18003a51f  jb      short loc_18003A508
0x18003a521  mov     rcx, r15; Sid
0x18003a524  call    cs:__imp_RtlLengthSid
0x18003a52a  lea     ecx, [rbx+rax*2]
0x18003a52d  mov     r12d, ecx
0x18003a530  mov     edx, ecx; unsigned __int64
0x18003a532  mov     rcx, cs:?Pku2uGlobalBaseSSP@@3PEAVBaseSSP@basessp@@EA; this
0x18003a539  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18003a53e  mov     rsi, rax
0x18003a541  test    rax, rax
0x18003a544  jnz     short loc_18003A550
0x18003a546  mov     eax, 0C0000017h
0x18003a54b  jmp     loc_18003A66A
0x18003a550  mov     rax, qword ptr cs:?Pku2uGlobalWillNeverTime@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER Pku2uGlobalWillNeverTime ...
0x18003a557  lea     rdx, [rsi+40h]
0x18003a55b  mov     [rsi], rax
0x18003a55e  mov     [rsi+18h], rdx
0x18003a562  mov     eax, [r14]
0x18003a565  mov     [rdx], eax
0x18003a567  mov     ecx, [r14]
0x18003a56a  mov     ebp, ecx
0x18003a56c  mov     [rsp+68h+arg_8], 0
0x18003a574  shl     rbp, 4
0x18003a578  add     rbp, 8
0x18003a57c  add     rbp, rdx
0x18003a57f  test    ecx, ecx
0x18003a581  jz      short loc_18003A5D4
0x18003a583  mov     r13d, [rsp+68h+arg_8]
0x18003a588  mov     rcx, [rsi+18h]
0x18003a58c  mov     edi, r13d
0x18003a58f  add     rdi, rdi
0x18003a592  mov     eax, [r14+rdi*8+10h]
0x18003a597  mov     [rcx+rdi*8+10h], eax
0x18003a59b  mov     rcx, [r14+rdi*8+8]; Sid
0x18003a5a0  call    cs:__imp_RtlLengthSid
0x18003a5a6  mov     r8, [r14+rdi*8+8]; SourceSid
0x18003a5ab  mov     rdx, rbp; DestinationSid
0x18003a5ae  mov     ecx, eax; DestinationSidLength
0x18003a5b0  mov     ebx, eax
0x18003a5b2  call    cs:__imp_RtlCopySid
0x18003a5b8  mov     rcx, [rsi+18h]
0x18003a5bc  inc     r13d
0x18003a5bf  mov     [rcx+rdi*8+8], rbp
0x18003a5c4  add     rbp, rbx
0x18003a5c7  cmp     r13d, [r14]
0x18003a5ca  jb      short loc_18003A588
0x18003a5cc  mov     r13, [rsp+68h+arg_10]
0x18003a5d4  mov     rcx, r15; Sid
0x18003a5d7  mov     [rsi+8], rbp
0x18003a5db  call    cs:__imp_RtlLengthSid
0x18003a5e1  mov     r8, r15; SourceSid
0x18003a5e4  mov     rdx, rbp; DestinationSid
0x18003a5e7  mov     ecx, eax; DestinationSidLength
0x18003a5e9  mov     edi, eax
0x18003a5eb  call    cs:__imp_RtlCopySid
0x18003a5f1  add     rbp, rdi
0x18003a5f4  mov     r8, r15; SourceSid
0x18003a5f7  mov     rdx, rbp; DestinationSid
0x18003a5fa  mov     [rsi+20h], rbp
0x18003a5fe  mov     ecx, edi; DestinationSidLength
0x18003a600  call    cs:__imp_RtlCopySid
0x18003a606  lea     rcx, [rdi+rbp]
0x18003a60a  lea     rax, [r12+rsi]
0x18003a60e  cmp     rax, rcx
0x18003a611  jnb     short loc_18003A658
0x18003a613  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a61a  lea     rax, WPP_GLOBAL_Control
0x18003a621  cmp     rcx, rax
0x18003a624  jz      short loc_18003A649
0x18003a626  test    byte ptr [rcx+1Ch], 1
0x18003a62a  jz      short loc_18003A649
0x18003a62c  mov     rcx, [rcx+10h]
0x18003a630  lea     r9, aPku2umaketoken; "Pku2uMakeTokenInformationV2Internal"
0x18003a637  mov     edx, 15h
0x18003a63c  mov     [rsp+68h+var_48], 0C00000E5h
0x18003a644  call    WPP_SF_sD
0x18003a649  mov     rcx, rsi; void *
0x18003a64c  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x18003a651  mov     eax, 0C00000E5h
0x18003a656  jmp     short loc_18003A66A
0x18003a658  xor     eax, eax
0x18003a65a  mov     [r13+0], rsi
0x18003a65e  mov     [rsi+28h], rax
0x18003a662  mov     [rsi+30h], rax
0x18003a666  mov     [rsi+38h], rax
0x18003a66a  mov     rbx, [rsp+68h+arg_0]
0x18003a66f  add     rsp, 30h
0x18003a673  pop     r15
0x18003a675  pop     r14
0x18003a677  pop     r13
0x18003a679  pop     r12
0x18003a67b  pop     rdi
0x18003a67c  pop     rsi
0x18003a67d  pop     rbp
0x18003a67e  retn
```
