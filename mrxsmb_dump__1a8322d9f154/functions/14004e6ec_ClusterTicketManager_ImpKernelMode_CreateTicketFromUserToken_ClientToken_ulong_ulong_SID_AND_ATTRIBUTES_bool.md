# ClusterTicketManager<ImpKernelMode>::CreateTicketFromUserToken(ClientToken *,ulong,ulong,_SID_AND_ATTRIBUTES *,bool)

- ea: `0x14004e6ec`
- end: `0x14004ed80`
- name: `?CreateTicketFromUserToken@?$ClusterTicketManager@VImpKernelMode@@@@QEAAJPEAVClientToken@@KKPEAU_SID_AND_ATTRIBUTES@@_N@Z`
- size: `1684`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x1400876e0`

## callees

- `0x14004e1b0`
- `0x14004e27c`
- `0x14004e4d8`
- `0x14004e544`
- `0x14004e6ec`
- `0x14004ed88`
- `0x14004eecc`
- `0x14004ef58`
- `0x14004f088`
- `0x14004f114`
- `0x14004f294`
- `0x14004f38c`
- `0x14004f454`
- `0x140059dc0`
- `0x140059f00`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004e7aa`
- `ntoskrnl!ExAllocatePool2` at `0x14004e879`
- `ntoskrnl!ExAllocatePool2` at `0x14004e7aa`
- `ntoskrnl!ExAllocatePool2` at `0x14004e879`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed56`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ed56`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e7c6`
- `ntoskrnl!ObfReferenceObjectWithTag` at `0x14004e7c6`

## string_xrefs

- `0x14004e924`: `CreateTicketFromUserToken - User name is %s, domain is %s`
- `0x14004e8d7`: `TokenUser`
- `0x14004eadd`: `TokenPrimaryGroup`
- `0x14004e9f5`: `TokenGroupsAndPrivileges`
- `0x14004eb78`: `TokenDefaultDacl`
- `0x14004eb23`: `TokenOwner`
- `0x14004ed30`: `Error on CreateFromUserToken: %d`
- `0x14004ebf8`: `TokenDeviceGroups`

## pseudocode

```c
__int64 __fastcall ClusterTicketManager<ImpKernelMode>::CreateTicketFromUserToken(
        PVOID *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        char a6)
{
  struct ClientToken *Pool2; // r14
  ImpKernelMode *v11; // rcx
  int v12; // ebx
  _WORD *v13; // rax
  __int64 v14; // rbx
  int UserClaimsBlob; // edi
  _DWORD *v16; // r15
  _WORD *v17; // r12
  _WORD *v18; // r13
  int v19; // ecx
  __int64 v20; // r15
  _DWORD *v21; // rax
  __int64 v22; // rdi
  size_t v23; // rdi
  char *v24; // rbx
  char *v25; // rbx
  size_t v26; // rdi
  char *v27; // rbx
  char *v28; // rbx
  _QWORD *v29; // rdi
  unsigned int v30; // r9d
  _WORD *v31; // rbx
  unsigned __int64 v32; // rcx
  unsigned int v33; // eax
  __int64 v34; // rdx
  unsigned __int64 v35; // r8
  _DWORD *v36; // rbx
  int v37; // eax
  _WORD *v38; // rcx
  const void *v39; // rdx
  _WORD *v40; // rax
  _WORD *v41; // rbx
  size_t v42; // rdi
  size_t v43; // r8
  char *v44; // rbx
  _DWORD *v45; // rdx
  int v46; // r8d
  size_t v47; // rdi
  void *v48; // rdx
  size_t v49; // r8
  char *v50; // rbx
  __int16 v51; // di
  void *v52; // rdx
  size_t v53; // r8
  ImpKernelMode *v54; // rcx
  ImpKernelMode *v55; // rcx
  _DWORD *v56; // [rsp+30h] [rbp-D0h] BYREF
  void *v57; // [rsp+38h] [rbp-C8h] BYREF
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v59; // [rsp+48h] [rbp-B8h]
  void *Src[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v61; // [rsp+60h] [rbp-A0h]
  int v62[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v63[880]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v64; // [rsp+3E8h] [rbp+2E8h]
  int v65; // [rsp+3F0h] [rbp+2F0h]
  __int64 v66; // [rsp+3F8h] [rbp+2F8h]
  int v67; // [rsp+400h] [rbp+300h]
  int v68; // [rsp+404h] [rbp+304h]

  v59 = a4;
  v61 = a5;
  Size = 0;
  *(_OWORD *)Src = 0;
  if ( a2 )
  {
    Pool2 = (struct ClientToken *)ExAllocatePool2(256, 16, 1094929747);
    if ( !Pool2 )
      goto LABEL_3;
    ObfReferenceObjectWithTag(*(PVOID *)a2, 0x4F424D53u);
    *(_QWORD *)Pool2 = *(_QWORD *)a2;
    *((_BYTE *)Pool2 + 8) = *(_BYTE *)(a2 + 8);
    *((_BYTE *)Pool2 + 9) = *(_BYTE *)(a2 + 9);
    *((_BYTE *)Pool2 + 10) = *(_BYTE *)(a2 + 10);
    *((_DWORD *)Pool2 + 3) = *(_DWORD *)(a2 + 12);
  }
  else
  {
    Pool2 = ClientToken::CreateFromCurrentToken();
    if ( !Pool2 )
    {
LABEL_3:
      AccountInfo<ImpKernelMode>::Release(Src);
      return 3221225473LL;
    }
  }
  *(_QWORD *)v62 = Pool2;
  v68 = 0;
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  *a1 = 0;
  v56 = 0;
  v12 = ClusterTicketManager<ImpKernelMode>::CalculateBufferSize((__int64)a1, (__int64)v62, a4, a5, &v56);
  if ( v12 < 0 )
    goto LABEL_9;
  v13 = (_WORD *)ExAllocatePool2(256, v56, 1094929747);
  *a1 = v13;
  if ( !v13 )
  {
    ImpKernelMode::Log(a1, 1, "Error allocating buffer");
    v12 = -1073741670;
LABEL_9:
    ImpKernelMode::CloseClientToken(v11, Pool2);
    TokenInfo<ImpKernelMode>::~TokenInfo<ImpKernelMode>(v62);
    AccountInfo<ImpKernelMode>::Release(Src);
    return (unsigned int)v12;
  }
  v57 = 0;
  *v13 = 0;
  v14 = (__int64)*a1 + 28;
  v56 = (_DWORD *)v14;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get((int)v62, 1, (int)"TokenUser", (int)&v57, 0);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  v16 = v57;
  UserClaimsBlob = AccountInfo<ImpKernelMode>::GetFrom(Src, *(_QWORD *)v57);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  v17 = Src[0];
  v18 = Src[1];
  ImpKernelMode::Log(
    a1,
    4,
    "CreateTicketFromUserToken - User name is %s, domain is %s",
    (const char *)Src[0],
    (const char *)Src[1]);
  *((_WORD *)*a1 + 2) = v14 - *(_WORD *)a1;
  ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(&v56, *(_QWORD *)v16);
  v19 = v16[2];
  v20 = -1;
  v21 = v56;
  v22 = -1;
  *v56 = v19;
  *((_WORD *)*a1 + 3) = (_WORD)v21 + 4 - *(_WORD *)a1;
  do
    ++v22;
  while ( v17[v22] );
  v23 = 2 * v22 + 2;
  *((_WORD *)v21 + 2) = v23;
  v24 = (char *)v21 + 6;
  memmove((char *)v21 + 6, v17, v23);
  v25 = &v24[v23];
  *((_WORD *)*a1 + 4) = (_WORD)v25 - *(_WORD *)a1;
  do
    ++v20;
  while ( v18[v20] );
  v26 = 2 * v20 + 2;
  *(_WORD *)v25 = v26;
  v27 = v25 + 2;
  memmove(v27, v18, v26);
  v28 = &v27[v26];
  v56 = v28;
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get((int)v62, 13, (int)"TokenGroupsAndPrivileges", (int)&v57, 0);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  v29 = v57;
  v30 = v59;
  *((_WORD *)*a1 + 5) = (_WORD)v28 - *(_WORD *)a1;
  ClusterTicketManager<ImpKernelMode>::Serializer::SerializeGroups((unsigned int)&v56, *(_DWORD *)v29, v29[1], v30, v61);
  *((_WORD *)*a1 + 6) = (_WORD)v56 - *(_WORD *)a1;
  ClusterTicketManager<ImpKernelMode>::Serializer::SerializeGroups(
    (unsigned int)&v56,
    *((_DWORD *)v29 + 4),
    v29[3],
    0,
    0);
  v31 = v56;
  *((_WORD *)*a1 + 7) = (_WORD)v56 - *(_WORD *)a1;
  v32 = 0;
  v33 = *((_DWORD *)v29 + 8);
  v34 = v29[5];
  v35 = v33;
  *v31 = v33;
  v36 = v31 + 1;
  v56 = v36;
  if ( v33 )
  {
    do
    {
      *(_QWORD *)v36 = *(_QWORD *)(v34 + 12 * v32);
      v37 = *(_DWORD *)(v34 + 12 * v32 + 8);
      v36[2] = v37;
      if ( a6 && (v37 & 4) == 0 )
        v36[2] = 3;
      v36 += 3;
      ++v32;
    }
    while ( v32 < v35 );
    v56 = v36;
  }
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get((int)v62, 5, (int)"TokenPrimaryGroup", (int)&v57, 0);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  *((_WORD *)*a1 + 8) = (_WORD)v36 - *(_WORD *)a1;
  ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(&v56, *(_QWORD *)v57);
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get((int)v62, 4, (int)"TokenOwner", (int)&v57, 0);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  *((_WORD *)*a1 + 9) = (_WORD)v56 - *(_WORD *)a1;
  ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(&v56, *(_QWORD *)v57);
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(
                     (int)v62,
                     6,
                     (int)"TokenDefaultDacl",
                     (int)&v57,
                     (ImpKernelMode *)&Size);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  v38 = *a1;
  v39 = *(const void **)v57;
  if ( *(_QWORD *)v57 )
  {
    v40 = v56;
    v38[10] = (_WORD)v56 - (_WORD)v38;
    v41 = v40 + 1;
    v42 = Size - 8;
    v43 = Size - 8;
    *v40 = Size - 8;
    memmove(v40 + 1, v39, v43);
    v44 = (char *)v41 + v42;
    v56 = v44;
  }
  else
  {
    v44 = (char *)v56;
    v38[10] = 0;
  }
  UserClaimsBlob = TokenInfo<ImpKernelMode>::Get(
                     (int)v62,
                     37,
                     (int)"TokenDeviceGroups",
                     (int)&v57,
                     (ImpKernelMode *)&Size);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  v45 = v57;
  if ( *(_DWORD *)v57 )
  {
    v46 = (_DWORD)v57 + 8;
    *((_WORD *)*a1 + 11) = (_WORD)v44 - *(_WORD *)a1;
    ClusterTicketManager<ImpKernelMode>::Serializer::SerializeGroups((unsigned int)&v56, *v45, v46, 0, 0);
    v44 = (char *)v56;
  }
  else
  {
    *((_WORD *)*a1 + 11) = 0;
  }
  UserClaimsBlob = TokenInfo<ImpKernelMode>::GetUserClaimsBlob(v62, &v57, &Size);
  if ( UserClaimsBlob < 0 )
    goto LABEL_42;
  if ( v57 )
  {
    *((_WORD *)*a1 + 12) = (_WORD)v44 - *(_WORD *)a1;
    v47 = Size;
    v48 = v57;
    v49 = Size;
    *(_WORD *)v44 = Size;
    v50 = v44 + 2;
    memmove(v50, v48, v49);
    v44 = &v50[v47];
  }
  else
  {
    *((_WORD *)*a1 + 12) = 0;
  }
  UserClaimsBlob = TokenInfo<ImpKernelMode>::GetDeviceClaimsBlob(v62, &v57, &Size);
  if ( UserClaimsBlob < 0 )
  {
LABEL_42:
    ImpKernelMode::Log(a1, 1, "Error on CreateFromUserToken: %d", UserClaimsBlob);
    ImpKernelMode::CloseClientToken(v55, Pool2);
    if ( *a1 )
    {
      ExFreePoolWithTag(*a1, 0);
      *a1 = 0;
    }
    TokenInfo<ImpKernelMode>::~TokenInfo<ImpKernelMode>(v62);
    AccountInfo<ImpKernelMode>::Release(Src);
    return (unsigned int)UserClaimsBlob;
  }
  else
  {
    if ( v57 )
    {
      *((_WORD *)*a1 + 13) = (_WORD)v44 - *(_WORD *)a1;
      v51 = Size;
      v52 = v57;
      v53 = Size;
      *(_WORD *)v44 = Size;
      v44 += 2;
      memmove(v44, v52, v53);
      LOWORD(v44) = v51 + (_WORD)v44;
    }
    else
    {
      v54 = (ImpKernelMode *)*a1;
      *((_WORD *)*a1 + 13) = 0;
    }
    *((_WORD *)*a1 + 1) = (_WORD)v44 - *(_WORD *)a1;
    ImpKernelMode::CloseClientToken(v54, Pool2);
    TokenInfo<ImpKernelMode>::~TokenInfo<ImpKernelMode>(v62);
    AccountInfo<ImpKernelMode>::Release(Src);
    return 0;
  }
}

```

## disassembly

```asm
0x14004e6ec  mov     [rsp-8+arg_10], rbx
0x14004e6f1  push    rbp
0x14004e6f2  push    rsi
0x14004e6f3  push    rdi
0x14004e6f4  push    r12
0x14004e6f6  push    r13
0x14004e6f8  push    r14
0x14004e6fa  push    r15
0x14004e6fc  lea     rbp, [rsp-320h]
0x14004e704  sub     rsp, 420h
0x14004e70b  mov     rax, cs:__security_cookie
0x14004e712  xor     rax, rsp
0x14004e715  mov     [rbp+350h+var_40], rax
0x14004e71c  mov     r15, [rbp+350h+arg_20]
0x14004e723  xor     r12d, r12d
0x14004e726  mov     [rsp+450h+var_408], r9d
0x14004e72b  xorps   xmm0, xmm0
0x14004e72e  mov     [rsp+450h+var_3F0], r15
0x14004e733  mov     edi, r9d
0x14004e736  mov     [rsp+450h+Size], r12
0x14004e73b  mov     rbx, rdx
0x14004e73e  mov     rsi, rcx
0x14004e741  mov     r13d, 41434D53h
0x14004e747  movdqu  xmmword ptr [rsp+450h+Src], xmm0
0x14004e74d  test    rdx, rdx
0x14004e750  jnz     short loc_14004E79D
0x14004e752  call    ?CreateFromCurrentToken@ClientToken@@SAPEAV1@XZ; ClientToken::CreateFromCurrentToken(void)
0x14004e757  mov     r14, rax
0x14004e75a  test    rax, rax
0x14004e75d  jnz     loc_14004E7F4
0x14004e763  lea     rcx, [rsp+450h+Src]
0x14004e768  call    ?Release@?$AccountInfo@VImpKernelMode@@@@AEAAXXZ; AccountInfo<ImpKernelMode>::Release(void)
0x14004e76d  mov     eax, 0C0000001h
0x14004e772  mov     rcx, [rbp+350h+var_40]
0x14004e779  xor     rcx, rsp; StackCookie
0x14004e77c  call    __security_check_cookie
0x14004e781  mov     rbx, [rsp+450h+arg_10]
0x14004e789  add     rsp, 420h
0x14004e790  pop     r15
0x14004e792  pop     r14
0x14004e794  pop     r13
0x14004e796  pop     r12
0x14004e798  pop     rdi
0x14004e799  pop     rsi
0x14004e79a  pop     rbp
0x14004e79b  retn
0x14004e79d  mov     r8d, r13d
0x14004e7a0  mov     edx, 10h
0x14004e7a5  mov     ecx, 100h
0x14004e7aa  call    cs:__imp_ExAllocatePool2
0x14004e7b1  nop     dword ptr [rax+rax+00h]
0x14004e7b6  mov     r14, rax
0x14004e7b9  test    rax, rax
0x14004e7bc  jz      short loc_14004E763
0x14004e7be  mov     rcx, [rbx]; Object
0x14004e7c1  mov     edx, 4F424D53h; Tag
0x14004e7c6  call    cs:__imp_ObfReferenceObjectWithTag
0x14004e7cd  nop     dword ptr [rax+rax+00h]
0x14004e7d2  mov     rax, [rbx]
0x14004e7d5  mov     [r14], rax
0x14004e7d8  mov     al, [rbx+8]
0x14004e7db  mov     [r14+8], al
0x14004e7df  mov     al, [rbx+9]
0x14004e7e2  mov     [r14+9], al
0x14004e7e6  mov     al, [rbx+0Ah]
0x14004e7e9  mov     [r14+0Ah], al
0x14004e7ed  mov     eax, [rbx+0Ch]
0x14004e7f0  mov     [r14+0Ch], eax
0x14004e7f4  mov     ebx, 1B8h
0x14004e7f9  mov     qword ptr [rsp+450h+var_3E0], r14
0x14004e7fe  mov     r8d, ebx; Size
0x14004e801  mov     [rbp+350h+var_4C], r12d
0x14004e808  xor     edx, edx; Val
0x14004e80a  lea     rcx, [rsp+450h+var_3D8]; void *
0x14004e80f  call    memset
0x14004e814  mov     r8d, ebx; Size
0x14004e817  lea     rcx, [rbp+350h+var_220]; void *
0x14004e81e  xor     edx, edx; Val
0x14004e820  call    memset
0x14004e825  lea     rax, [rsp+450h+var_420]
0x14004e82a  mov     [rbp+350h+var_68], r12
0x14004e831  mov     r9, r15
0x14004e834  mov     [rsp+450h+var_430], rax
0x14004e839  mov     r8d, edi
0x14004e83c  mov     [rbp+350h+var_60], r12d
0x14004e843  lea     rdx, [rsp+450h+var_3E0]
0x14004e848  mov     [rbp+350h+var_58], r12
0x14004e84f  mov     rcx, rsi
0x14004e852  mov     [rbp+350h+var_50], r12d
0x14004e859  mov     [rsi], r12
0x14004e85c  mov     [rsp+450h+var_420], r12
0x14004e861  call    ?CalculateBufferSize@?$ClusterTicketManager@VImpKernelMode@@@@AEAAJAEAV?$TokenInfo@VImpKernelMode@@@@KPEAU_SID_AND_ATTRIBUTES@@PEA_K@Z; ClusterTicketManager<ImpKernelMode>::CalculateBufferSize(TokenInfo<ImpKernelMode> &,ulong,_SID_AND_ATTRIBUTES *,unsigned __int64 *)
0x14004e866  mov     ebx, eax
0x14004e868  test    eax, eax
0x14004e86a  js      short loc_14004E8A6
0x14004e86c  mov     rdx, [rsp+450h+var_420]
0x14004e871  mov     r8d, r13d
0x14004e874  mov     ecx, 100h
0x14004e879  call    cs:__imp_ExAllocatePool2
0x14004e880  nop     dword ptr [rax+rax+00h]
0x14004e885  mov     [rsi], rax
0x14004e888  mov     edx, 1; int
0x14004e88d  test    rax, rax
0x14004e890  jnz     short loc_14004E8C9
0x14004e892  lea     r8, aErrorAllocatin_0; "Error allocating buffer"
0x14004e899  mov     rcx, rsi
0x14004e89c  call    ?Log@ImpKernelMode@@IEAAXW4LOG_LEVEL@@PEBDZZ; ImpKernelMode::Log(LOG_LEVEL,char const *,...)
0x14004e8a1  mov     ebx, 0C000009Ah
0x14004e8a6  mov     rdx, r14; struct ClientToken *
0x14004e8a9  call    ?CloseClientToken@ImpKernelMode@@IEAAXPEAVClientToken@@@Z; ImpKernelMode::CloseClientToken(ClientToken *)
0x14004e8ae  lea     rcx, [rsp+450h+var_3E0]
0x14004e8b3  call    ??1?$TokenInfo@VImpKernelMode@@@@QEAA@XZ; TokenInfo<ImpKernelMode>::~TokenInfo<ImpKernelMode>(void)
0x14004e8b8  lea     rcx, [rsp+450h+Src]
0x14004e8bd  call    ?Release@?$AccountInfo@VImpKernelMode@@@@AEAAXXZ; AccountInfo<ImpKernelMode>::Release(void)
0x14004e8c2  mov     eax, ebx
0x14004e8c4  jmp     loc_14004E772
0x14004e8c9  mov     [rsp+450h+var_418], r12
0x14004e8ce  lea     r9, [rsp+450h+var_418]; int
0x14004e8d3  mov     [rax], r12w
0x14004e8d7  lea     r8, aTokenuser; "TokenUser"
0x14004e8de  mov     rbx, [rsi]
0x14004e8e1  lea     rcx, [rsp+450h+var_3E0]; int
0x14004e8e6  add     rbx, 1Ch
0x14004e8ea  mov     [rsp+450h+var_430], r12; ImpKernelMode *
0x14004e8ef  mov     [rsp+450h+var_420], rbx
0x14004e8f4  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004e8f9  mov     edi, eax
0x14004e8fb  test    eax, eax
0x14004e8fd  js      loc_14004ED2D
0x14004e903  mov     r15, [rsp+450h+var_418]
0x14004e908  lea     rcx, [rsp+450h+Src]
0x14004e90d  mov     rdx, [r15]
0x14004e910  call    ?GetFrom@?$AccountInfo@VImpKernelMode@@@@QEAAJPEAX@Z; AccountInfo<ImpKernelMode>::GetFrom(void *)
0x14004e915  mov     edi, eax
0x14004e917  test    eax, eax
0x14004e919  js      loc_14004ED2D
0x14004e91f  mov     r12, [rsp+450h+Src]
0x14004e924  lea     r8, aCreateticketfr; "CreateTicketFromUserToken - User name i"...
0x14004e92b  mov     r13, [rsp+450h+Src+8]
0x14004e930  mov     r9, r12
0x14004e933  mov     edx, 4
0x14004e938  mov     [rsp+450h+var_430], r13
0x14004e93d  mov     rcx, rsi
0x14004e940  call    ?Log@ImpKernelMode@@IEAAXW4LOG_LEVEL@@PEBDZZ; ImpKernelMode::Log(LOG_LEVEL,char const *,...)
0x14004e945  mov     rax, [rsi]
0x14004e948  lea     rcx, [rsp+450h+var_420]
0x14004e94d  sub     bx, [rsi]
0x14004e950  mov     [rax+4], bx
0x14004e954  mov     rdx, [r15]
0x14004e957  call    ?SerializeSid@Serializer@?$ClusterTicketManager@VImpKernelMode@@@@QEAAXPEAX@Z; ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(void *)
0x14004e95c  mov     ecx, [r15+8]
0x14004e960  or      r15, 0FFFFFFFFFFFFFFFFh
0x14004e964  mov     rax, [rsp+450h+var_420]
0x14004e969  mov     rdi, r15
0x14004e96c  mov     [rax], ecx
0x14004e96e  lea     rbx, [rax+4]
0x14004e972  mov     rax, [rsi]
0x14004e975  movzx   ecx, bx
0x14004e978  sub     cx, [rsi]
0x14004e97b  mov     [rax+6], cx
0x14004e97f  xor     eax, eax
0x14004e981  inc     rdi
0x14004e984  cmp     [r12+rdi*2], ax
0x14004e989  jnz     short loc_14004E981
0x14004e98b  lea     rdi, ds:2[rdi*2]
0x14004e993  mov     rdx, r12; Src
0x14004e996  mov     [rbx], di
0x14004e999  mov     r8, rdi; Size
0x14004e99c  add     rbx, 2
0x14004e9a0  mov     rcx, rbx; void *
0x14004e9a3  call    memmove
0x14004e9a8  mov     rax, [rsi]
0x14004e9ab  add     rbx, rdi
0x14004e9ae  movzx   ecx, bx
0x14004e9b1  sub     cx, [rsi]
0x14004e9b4  xor     r12d, r12d
0x14004e9b7  mov     [rax+8], cx
0x14004e9bb  inc     r15
0x14004e9be  cmp     [r13+r15*2+0], r12w
0x14004e9c4  jnz     short loc_14004E9BB
0x14004e9c6  lea     rdi, ds:2[r15*2]
0x14004e9ce  mov     rdx, r13; Src
0x14004e9d1  mov     [rbx], di
0x14004e9d4  mov     r8, rdi; Size
0x14004e9d7  add     rbx, 2
0x14004e9db  mov     rcx, rbx; void *
0x14004e9de  call    memmove
0x14004e9e3  add     rbx, rdi
0x14004e9e6  mov     [rsp+450h+var_430], r12; ImpKernelMode *
0x14004e9eb  lea     r9, [rsp+450h+var_418]; int
0x14004e9f0  mov     [rsp+450h+var_420], rbx
0x14004e9f5  lea     r8, aTokengroupsand; "TokenGroupsAndPrivileges"
0x14004e9fc  mov     edx, 0Dh; int
0x14004ea01  lea     rcx, [rsp+450h+var_3E0]; int
0x14004ea06  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004ea0b  mov     edi, eax
0x14004ea0d  test    eax, eax
0x14004ea0f  js      loc_14004ED2D
0x14004ea15  mov     rdi, [rsp+450h+var_418]
0x14004ea1a  lea     rcx, [rsp+450h+var_420]
0x14004ea1f  mov     rax, [rsi]
0x14004ea22  sub     bx, [rsi]
0x14004ea25  mov     r9d, [rsp+450h+var_408]
0x14004ea2a  mov     [rax+0Ah], bx
0x14004ea2e  mov     rax, [rsp+450h+var_3F0]
0x14004ea33  mov     r8, [rdi+8]
0x14004ea37  mov     edx, [rdi]
0x14004ea39  mov     [rsp+450h+var_430], rax
0x14004ea3e  call    ?SerializeGroups@Serializer@?$ClusterTicketManager@VImpKernelMode@@@@QEAAXKPEAU_SID_AND_ATTRIBUTES@@K0@Z; ClusterTicketManager<ImpKernelMode>::Serializer::SerializeGroups(ulong,_SID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *)
0x14004ea43  movzx   ecx, word ptr [rsp+450h+var_420]
0x14004ea48  xor     r9d, r9d
0x14004ea4b  sub     cx, [rsi]
0x14004ea4e  mov     rax, [rsi]
0x14004ea51  mov     [rsp+450h+var_430], r12
0x14004ea56  mov     [rax+0Ch], cx
0x14004ea5a  lea     rcx, [rsp+450h+var_420]
0x14004ea5f  mov     r8, [rdi+18h]
0x14004ea63  mov     edx, [rdi+10h]
0x14004ea66  call    ?SerializeGroups@Serializer@?$ClusterTicketManager@VImpKernelMode@@@@QEAAXKPEAU_SID_AND_ATTRIBUTES@@K0@Z; ClusterTicketManager<ImpKernelMode>::Serializer::SerializeGroups(ulong,_SID_AND_ATTRIBUTES *,ulong,_SID_AND_ATTRIBUTES *)
0x14004ea6b  mov     rbx, [rsp+450h+var_420]
0x14004ea70  mov     rax, [rsi]
0x14004ea73  movzx   ecx, bx
0x14004ea76  sub     cx, [rsi]
0x14004ea79  mov     [rax+0Eh], cx
0x14004ea7d  mov     rcx, r12
0x14004ea80  mov     eax, [rdi+20h]
0x14004ea83  mov     rdx, [rdi+28h]
0x14004ea87  mov     r8d, eax
0x14004ea8a  mov     [rbx], ax
0x14004ea8d  add     rbx, 2
0x14004ea91  mov     [rsp+450h+var_420], rbx
0x14004ea96  test    eax, eax
0x14004ea98  jz      short loc_14004EAD3
0x14004ea9a  lea     rax, [rcx+rcx*2]
0x14004ea9e  movsd   xmm0, qword ptr [rdx+rax*4]
0x14004eaa3  movsd   qword ptr [rbx], xmm0
0x14004eaa7  mov     eax, [rdx+rax*4+8]
0x14004eaab  mov     [rbx+8], eax
0x14004eaae  cmp     [rbp+350h+arg_28], r12b
0x14004eab5  jz      short loc_14004EAC2
0x14004eab7  test    al, 4
0x14004eab9  jnz     short loc_14004EAC2
0x14004eabb  mov     dword ptr [rbx+8], 3
0x14004eac2  add     rbx, 0Ch
0x14004eac6  inc     rcx
0x14004eac9  cmp     rcx, r8
0x14004eacc  jb      short loc_14004EA9A
0x14004eace  mov     [rsp+450h+var_420], rbx
0x14004ead3  lea     r9, [rsp+450h+var_418]; int
0x14004ead8  mov     [rsp+450h+var_430], r12; ImpKernelMode *
0x14004eadd  lea     r8, aTokenprimarygr; "TokenPrimaryGroup"
0x14004eae4  mov     edx, 5; int
0x14004eae9  lea     rcx, [rsp+450h+var_3E0]; int
0x14004eaee  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004eaf3  mov     edi, eax
0x14004eaf5  test    eax, eax
0x14004eaf7  js      loc_14004ED2D
0x14004eafd  mov     rax, [rsi]
0x14004eb00  lea     rcx, [rsp+450h+var_420]
0x14004eb05  sub     bx, [rsi]
0x14004eb08  mov     [rax+10h], bx
0x14004eb0c  mov     rdx, [rsp+450h+var_418]
0x14004eb11  mov     rdx, [rdx]
0x14004eb14  call    ?SerializeSid@Serializer@?$ClusterTicketManager@VImpKernelMode@@@@QEAAXPEAX@Z; ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(void *)
0x14004eb19  lea     r9, [rsp+450h+var_418]; int
0x14004eb1e  mov     [rsp+450h+var_430], r12; ImpKernelMode *
0x14004eb23  lea     r8, aTokenowner; "TokenOwner"
0x14004eb2a  mov     edx, 4; int
0x14004eb2f  lea     rcx, [rsp+450h+var_3E0]; int
0x14004eb34  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004eb39  mov     edi, eax
0x14004eb3b  test    eax, eax
0x14004eb3d  js      loc_14004ED2D
0x14004eb43  movzx   ecx, word ptr [rsp+450h+var_420]
0x14004eb48  sub     cx, [rsi]
0x14004eb4b  mov     rax, [rsi]
0x14004eb4e  mov     [rax+12h], cx
0x14004eb52  lea     rcx, [rsp+450h+var_420]
0x14004eb57  mov     rdx, [rsp+450h+var_418]
0x14004eb5c  mov     rdx, [rdx]
0x14004eb5f  call    ?SerializeSid@Serializer@?$ClusterTicketManager@VImpKernelMode@@@@QEAAXPEAX@Z; ClusterTicketManager<ImpKernelMode>::Serializer::SerializeSid(void *)
0x14004eb64  lea     rax, [rsp+450h+Size]
0x14004eb69  mov     edx, 6; int
0x14004eb6e  lea     r9, [rsp+450h+var_418]; int
0x14004eb73  mov     [rsp+450h+var_430], rax; ImpKernelMode *
0x14004eb78  lea     r8, aTokendefaultda; "TokenDefaultDacl"
0x14004eb7f  lea     rcx, [rsp+450h+var_3E0]; int
0x14004eb84  call    ?Get@?$TokenInfo@VImpKernelMode@@@@QEAAJW4_TOKEN_INFORMATION_CLASS@@PEBDPEAPEAXPEA_K@Z; TokenInfo<ImpKernelMode>::Get(_TOKEN_INFORMATION_CLASS,char const *,void * *,unsigned __int64 *)
0x14004eb89  mov     edi, eax
0x14004eb8b  test    eax, eax
0x14004eb8d  js      loc_14004ED2D
0x14004eb93  mov     rax, [rsp+450h+var_418]
0x14004eb98  mov     rcx, [rsi]
0x14004eb9b  mov     rdx, [rax]; Src
0x14004eb9e  test    rdx, rdx
0x14004eba1  jz      short loc_14004EBDA
0x14004eba3  mov     rax, [rsp+450h+var_420]
0x14004eba8  movzx   r8d, ax
0x14004ebac  sub     r8w, cx
0x14004ebb0  mov     [rcx+14h], r8w
  ... truncated ...
```
