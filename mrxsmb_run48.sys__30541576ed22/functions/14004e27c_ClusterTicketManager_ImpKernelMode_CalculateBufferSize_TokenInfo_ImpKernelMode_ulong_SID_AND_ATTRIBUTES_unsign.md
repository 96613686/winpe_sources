# ClusterTicketManager<ImpKernelMode>::CalculateBufferSize(TokenInfo<ImpKernelMode> &,ulong,_SID_AND_ATTRIBUTES *,unsigned __int64 *)

- ea: `0x14004e27c`
- end: `0x14004e4cf`
- name: `?CalculateBufferSize@?$ClusterTicketManager@VImpKernelMode@@@@AEAAJAEAV?$TokenInfo@VImpKernelMode@@@@KPEAU_SID_AND_ATTRIBUTES@@PEA_K@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14004e6ec`

## callees

- `0x14004e27c`
- `0x14004ed88`
- `0x14004eecc`
- `0x14004ef58`
- `0x14004f088`
- `0x14004f114`
- `0x14004f294`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14004e42f`
- `ntoskrnl!RtlLengthSid` at `0x14004e42f`

## string_xrefs

- `0x14004e2bd`: `TokenUser`
- `0x14004e34d`: `TokenPrimaryGroup`
- `0x14004e321`: `TokenGroupsAndPrivileges`
- `0x14004e3b8`: `TokenDefaultDacl`
- `0x14004e38b`: `TokenOwner`
- `0x14004e3e6`: `TokenDeviceGroups`

## pseudocode

```c
__int64 __fastcall ClusterTicketManager<ImpKernelMode>::CalculateBufferSize(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _QWORD *a5)
{
  unsigned __int64 v5; // r12
  int UserClaimsBlob; // ebx
  __int64 v9; // r15
  __int64 v10; // rdi
  __int64 v11; // r14
  __int64 v12; // rdi
  __int64 v13; // rdi
  __int64 v14; // rdi
  __int64 v15; // r14
  unsigned __int64 v16; // rbx
  __int64 v17; // rdi
  ULONG v18; // eax
  __int64 v19; // rdi
  __int64 v21; // [rsp+30h] [rbp-28h] BYREF
  int v22[2]; // [rsp+38h] [rbp-20h] BYREF
  __int128 v23; // [rsp+40h] [rbp-18h] BYREF

  v5 = a3;
  v21 = 0;
  *(_QWORD *)v22 = 0;
  v23 = 0;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 1, (int)"TokenUser", (int)v22, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v9 = v21;
  UserClaimsBlob = AccountInfo<ImpKernelMode>::GetFrom(&v23, **(_QWORD **)v22);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(v23 + 2 * v11) );
  do
    ++v10;
  while ( *(_WORD *)(*((_QWORD *)&v23 + 1) + 2 * v10) );
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 13, (int)"TokenGroupsAndPrivileges", 0, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v12 = v21 + v9 + 2 * (v10 + v11 + 16);
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 5, (int)"TokenPrimaryGroup", 0, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v13 = v21 + v12;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 4, (int)"TokenOwner", 0, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v14 = v21 + v13;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 6, (int)"TokenDefaultDacl", 0, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  v15 = v14 + v21;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(a2, 37, (int)"TokenDeviceGroups", (int)v22, (ImpKernelMode *)&v21);
  if ( UserClaimsBlob < 0 )
    goto LABEL_18;
  if ( **(_DWORD **)v22 )
    v15 += v21;
  v21 = 0;
  v16 = 0;
  v17 = 0;
  if ( (_DWORD)v5 )
  {
    do
    {
      v18 = RtlLengthSid(*(PSID *)(a4 + 16 * v16++));
      v17 = v18 + v21;
      v21 = v17;
    }
    while ( v16 < v5 );
  }
  UserClaimsBlob = TokenInfo<ImpKernelMode>::GetUserClaimsBlob(a2, 0, &v21);
  if ( UserClaimsBlob < 0
    || (v19 = v21 + v15 + v17,
        UserClaimsBlob = TokenInfo<ImpKernelMode>::GetDeviceClaimsBlob(a2, 0, &v21),
        UserClaimsBlob < 0) )
  {
LABEL_18:
    ImpKernelMode::Log(a1, 1, "Error on CalculateBufferSize: %d", UserClaimsBlob);
    AccountInfo<ImpKernelMode>::Release(&v23);
    return (unsigned int)UserClaimsBlob;
  }
  else
  {
    *a5 = v19 + v21;
    AccountInfo<ImpKernelMode>::Release(&v23);
    return 0;
  }
}

```

## disassembly

```asm
0x14004e27c  mov     [rsp-40h+arg_0], rcx
0x14004e281  push    rbp
0x14004e282  push    rbx
0x14004e283  push    rsi
0x14004e284  push    rdi
0x14004e285  push    r12
0x14004e287  push    r13
0x14004e289  push    r14
0x14004e28b  push    r15
0x14004e28d  mov     rbp, rsp
0x14004e290  sub     rsp, 58h
0x14004e294  xor     edi, edi
0x14004e296  mov     r12d, r8d
0x14004e299  mov     rsi, rdx
0x14004e29c  mov     [rbp+var_28], rdi
0x14004e2a0  mov     r13, r9
0x14004e2a3  mov     qword ptr [rbp+var_20], rdi
0x14004e2a7  xorps   xmm0, xmm0
0x14004e2aa  lea     rax, [rbp+var_28]
0x14004e2ae  lea     edx, [rdi+1]; int
0x14004e2b1  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e2b6  lea     r9, [rbp+var_20]; int
0x14004e2ba  mov     rcx, rsi; int
0x14004e2bd  lea     r8, aTokenuser; "TokenUser"
0x14004e2c4  movdqu  [rbp+var_18], xmm0
0x14004e2c9  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e2ce  mov     ebx, eax
0x14004e2d0  test    eax, eax
0x14004e2d2  js      loc_14004E49A
0x14004e2d8  mov     rdx, qword ptr [rbp+var_20]
0x14004e2dc  lea     rcx, [rbp+var_18]
0x14004e2e0  mov     r15, [rbp+var_28]
0x14004e2e4  mov     rdx, [rdx]
0x14004e2e7  call    ?GetFrom@?$AccountInfo@VImpKernelMode@@@@QEAAJPEAX@Z; AccountInfo<ImpKernelMode>::GetFrom(void *)
0x14004e2ec  mov     ebx, eax
0x14004e2ee  test    eax, eax
0x14004e2f0  js      loc_14004E49A
0x14004e2f6  mov     rax, qword ptr [rbp+var_18]
0x14004e2fa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14004e2fe  mov     r14, rdi
0x14004e301  xor     ecx, ecx
0x14004e303  inc     r14
0x14004e306  cmp     [rax+r14*2], cx
0x14004e30b  jnz     short loc_14004E303
0x14004e30d  mov     rax, qword ptr [rbp+var_18+8]
0x14004e311  inc     rdi
0x14004e314  cmp     [rax+rdi*2], cx
0x14004e318  jnz     short loc_14004E311
0x14004e31a  xor     r9d, r9d; int
0x14004e31d  lea     rax, [rbp+var_28]
0x14004e321  lea     r8, aTokengroupsand; "TokenGroupsAndPrivileges"
0x14004e328  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e32d  mov     rcx, rsi; int
0x14004e330  lea     edx, [r9+0Dh]; int
0x14004e334  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e339  mov     ebx, eax
0x14004e33b  test    eax, eax
0x14004e33d  js      loc_14004E49A
0x14004e343  xor     r9d, r9d; int
0x14004e346  lea     rax, [r14+10h]
0x14004e34a  add     rax, rdi
0x14004e34d  lea     r8, aTokenprimarygr; "TokenPrimaryGroup"
0x14004e354  mov     rcx, rsi; int
0x14004e357  lea     edx, [r9+5]; int
0x14004e35b  lea     rdi, [r15+rax*2]
0x14004e35f  add     rdi, [rbp+var_28]
0x14004e363  lea     rax, [rbp+var_28]
0x14004e367  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e36c  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e371  mov     ebx, eax
0x14004e373  test    eax, eax
0x14004e375  js      loc_14004E49A
0x14004e37b  add     rdi, [rbp+var_28]
0x14004e37f  lea     rax, [rbp+var_28]
0x14004e383  xor     r9d, r9d; int
0x14004e386  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e38b  lea     r8, aTokenowner; "TokenOwner"
0x14004e392  mov     rcx, rsi; int
0x14004e395  lea     edx, [r9+4]; int
0x14004e399  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e39e  mov     ebx, eax
0x14004e3a0  test    eax, eax
0x14004e3a2  js      loc_14004E49A
0x14004e3a8  add     rdi, [rbp+var_28]
0x14004e3ac  lea     rax, [rbp+var_28]
0x14004e3b0  xor     r9d, r9d; int
0x14004e3b3  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e3b8  lea     r8, aTokendefaultda; "TokenDefaultDacl"
0x14004e3bf  mov     rcx, rsi; int
0x14004e3c2  lea     edx, [r9+6]; int
0x14004e3c6  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e3cb  mov     ebx, eax
0x14004e3cd  test    eax, eax
0x14004e3cf  js      loc_14004E49A
0x14004e3d5  mov     r14, [rbp+var_28]
0x14004e3d9  lea     rax, [rbp+var_28]
0x14004e3dd  lea     r9, [rbp+var_20]; int
0x14004e3e1  mov     [rsp+58h+var_38], rax; ImpKernelMode *
0x14004e3e6  lea     r8, aTokendevicegro; "TokenDeviceGroups"
0x14004e3ed  mov     edx, 25h ; '%'; int
0x14004e3f2  mov     rcx, rsi; int
0x14004e3f5  add     r14, rdi
0x14004e3f8  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e3fd  xor     ecx, ecx
0x14004e3ff  mov     ebx, eax
0x14004e401  test    eax, eax
0x14004e403  js      loc_14004E49A
0x14004e409  mov     rax, qword ptr [rbp+var_20]
0x14004e40d  cmp     [rax], ecx
0x14004e40f  jz      short loc_14004E415
0x14004e411  add     r14, [rbp+var_28]
0x14004e415  mov     [rbp+var_28], rcx
0x14004e419  mov     rbx, rcx
0x14004e41c  mov     rdi, rcx
0x14004e41f  test    r12d, r12d
0x14004e422  jz      short loc_14004E450
0x14004e424  mov     rcx, rbx
0x14004e427  add     rcx, rcx
0x14004e42a  mov     rcx, [r13+rcx*8+0]; Sid
0x14004e42f  call    cs:__imp_RtlLengthSid
0x14004e436  nop     dword ptr [rax+rax+00h]
0x14004e43b  mov     rdi, [rbp+var_28]
0x14004e43f  inc     rbx
0x14004e442  mov     eax, eax
0x14004e444  add     rdi, rax
0x14004e447  mov     [rbp+var_28], rdi
0x14004e44b  cmp     rbx, r12
0x14004e44e  jb      short loc_14004E424
0x14004e450  lea     r8, [rbp+var_28]
0x14004e454  xor     edx, edx
0x14004e456  mov     rcx, rsi
0x14004e459  call    ?GetUserClaimsBlob@?$TokenInfo@VImpKernelMode@@@@QEAAJPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::GetUserClaimsBlob(void * *,unsigned __int64 *)
0x14004e45e  mov     ebx, eax
0x14004e460  test    eax, eax
0x14004e462  js      short loc_14004E49A
0x14004e464  add     rdi, r14
0x14004e467  lea     r8, [rbp+var_28]
0x14004e46b  add     rdi, [rbp+var_28]
0x14004e46f  xor     edx, edx
0x14004e471  mov     rcx, rsi
0x14004e474  call    ?GetDeviceClaimsBlob@?$TokenInfo@VImpKernelMode@@@@QEAAJPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::GetDeviceClaimsBlob(void * *,unsigned __int64 *)
0x14004e479  mov     ebx, eax
0x14004e47b  test    eax, eax
0x14004e47d  js      short loc_14004E49A
0x14004e47f  mov     rax, [rbp+arg_20]
0x14004e483  mov     rcx, [rbp+var_28]
0x14004e487  add     rcx, rdi
0x14004e48a  mov     [rax], rcx
0x14004e48d  lea     rcx, [rbp+var_18]
0x14004e491  call    ?Release@?$AccountInfo@VImpKernelMode@@@@AEAAXXZ; AccountInfo<ImpKernelMode>::Release(void)
0x14004e496  xor     eax, eax
0x14004e498  jmp     short loc_14004E4BD
0x14004e49a  mov     rcx, [rbp+arg_0]
0x14004e49e  lea     r8, aErrorOnCalcula; "Error on CalculateBufferSize: %d"
0x14004e4a5  mov     r9d, ebx
0x14004e4a8  mov     edx, 1
0x14004e4ad  call    ?Log@ImpKernelMode@@IEAAXW4LOG_LEVEL@@PEBDZZ; ImpKernelMode::Log(LOG_LEVEL,char const *,...)
0x14004e4b2  lea     rcx, [rbp+var_18]
0x14004e4b6  call    ?Release@?$AccountInfo@VImpKernelMode@@@@AEAAXXZ; AccountInfo<ImpKernelMode>::Release(void)
0x14004e4bb  mov     eax, ebx
0x14004e4bd  add     rsp, 58h
0x14004e4c1  pop     r15
0x14004e4c3  pop     r14
0x14004e4c5  pop     r13
0x14004e4c7  pop     r12
0x14004e4c9  pop     rdi
0x14004e4ca  pop     rsi
0x14004e4cb  pop     rbx
0x14004e4cc  pop     rbp
0x14004e4cd  retn
```
