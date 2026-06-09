# NtLmInitKernelContext

- ea: `0x140023580`
- end: `0x140023d6f`
- name: `NtLmInitKernelContext`
- size: `2031`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140010160`
- `0x140010240`
- `0x1400102c0`
- `0x1400105c0`
- `0x140023580`
- `0x14002fe40`
- `0x14002ff40`
- `0x140030020`

## import_xrefs

- `ntoskrnl!ZwQueryObject` at `0x1400236fb`
- `ntoskrnl!ZwQueryObject` at `0x1400236fb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002372e`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002372e`
- `ntoskrnl!ZwSetInformationObject` at `0x140023790`
- `ntoskrnl!ZwSetInformationObject` at `0x140023790`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023748`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002376c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023748`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002376c`
- `ntoskrnl!ExAllocatePool2` at `0x14002363f`
- `ntoskrnl!ExAllocatePool2` at `0x1400236cc`
- `ntoskrnl!ExAllocatePool2` at `0x140023bc3`
- `ntoskrnl!ExAllocatePool2` at `0x14002363f`
- `ntoskrnl!ExAllocatePool2` at `0x1400236cc`
- `ntoskrnl!ExAllocatePool2` at `0x140023bc3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023718`
- `ntoskrnl!RtlInitUnicodeString` at `0x140023718`
- `cng!BCryptCreateHash` at `0x1400237fb`
- `cng!BCryptCreateHash` at `0x1400238d5`
- `cng!BCryptCreateHash` at `0x1400239af`
- `cng!BCryptCreateHash` at `0x140023a8c`
- `cng!BCryptCreateHash` at `0x1400237fb`
- `cng!BCryptCreateHash` at `0x1400238d5`
- `cng!BCryptCreateHash` at `0x1400239af`
- `cng!BCryptCreateHash` at `0x140023a8c`
- `cng!BCryptHashData` at `0x140023822`
- `cng!BCryptHashData` at `0x14002384c`
- `cng!BCryptHashData` at `0x1400238fc`
- `cng!BCryptHashData` at `0x140023926`
- `cng!BCryptHashData` at `0x1400239d9`
- `cng!BCryptHashData` at `0x140023a03`
- `cng!BCryptHashData` at `0x140023ab6`
- `cng!BCryptHashData` at `0x140023ae0`
- `cng!BCryptHashData` at `0x140023822`
- `cng!BCryptHashData` at `0x14002384c`
- `cng!BCryptHashData` at `0x1400238fc`
- `cng!BCryptHashData` at `0x140023926`
- `cng!BCryptHashData` at `0x1400239d9`
- `cng!BCryptHashData` at `0x140023a03`
- `cng!BCryptHashData` at `0x140023ab6`
- `cng!BCryptHashData` at `0x140023ae0`
- `cng!BCryptDestroyHash` at `0x14002388d`
- `cng!BCryptDestroyHash` at `0x140023967`
- `cng!BCryptDestroyHash` at `0x140023a44`
- `cng!BCryptDestroyHash` at `0x140023b21`
- `cng!BCryptDestroyHash` at `0x140023d00`
- `cng!BCryptDestroyHash` at `0x14002388d`
- `cng!BCryptDestroyHash` at `0x140023967`
- `cng!BCryptDestroyHash` at `0x140023a44`
- `cng!BCryptDestroyHash` at `0x140023b21`
- `cng!BCryptDestroyHash` at `0x140023d00`
- `cng!BCryptFinishHash` at `0x140023873`
- `cng!BCryptFinishHash` at `0x14002394d`
- `cng!BCryptFinishHash` at `0x140023a2a`
- `cng!BCryptFinishHash` at `0x140023b07`
- `cng!BCryptFinishHash` at `0x140023873`
- `cng!BCryptFinishHash` at `0x14002394d`
- `cng!BCryptFinishHash` at `0x140023a2a`
- `cng!BCryptFinishHash` at `0x140023b07`

## string_xrefs

- `0x14002370d`: `Token`

## pseudocode

```c
__int64 __fastcall NtLmInitKernelContext(__int64 a1, __int64 a2, char **a3)
{
  __int64 v3; // rsi
  __int64 v4; // r14
  bool v5; // cf
  NTSTATUS v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 Pool2; // rax
  char *v12; // rdi
  void *v13; // r15
  __int64 v14; // r12
  UNICODE_STRING *v15; // rax
  UNICODE_STRING *v16; // r14
  NTSTATUS Object; // eax
  int v18; // eax
  __int128 v19; // xmm0
  ULONG v20; // r14d
  char *v21; // r14
  __int64 v22; // rax
  void *v23; // rax
  __int64 v24; // rcx
  char *v25; // rax
  size_t v26; // r8
  char *v27; // rbx
  __int64 v28; // rax
  size_t v29; // r8
  __int64 v30; // rcx
  void *v31; // rcx
  bool v32; // zf
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-29h] BYREF
  __int64 v35; // [rsp+50h] [rbp-21h]
  __int16 ObjectInformation[2]; // [rsp+58h] [rbp-19h] BYREF
  enum _POOL_TYPE v37; // [rsp+5Ch] [rbp-15h]
  __int64 v38; // [rsp+60h] [rbp-11h]
  char **v39; // [rsp+68h] [rbp-9h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-1h] BYREF
  UCHAR pbOutput[16]; // [rsp+80h] [rbp+Fh] BYREF

  v3 = *(_QWORD *)(a2 + 8);
  v4 = a2;
  *a3 = 0;
  v5 = *(_DWORD *)a2 < 0xA8u;
  v39 = a3;
  v35 = a2;
  phHash = 0;
  if ( v5 )
  {
    v7 = -1073741811;
    goto LABEL_77;
  }
  v8 = *(unsigned int *)(v3 + 72);
  if ( (unsigned int)v8 >= 0xFFFF )
  {
    v7 = -1073741811;
    goto LABEL_77;
  }
  v9 = *(unsigned int *)(v3 + 144);
  if ( (unsigned int)v9 >= 0xFFFF )
  {
    v7 = -1073741811;
    goto LABEL_77;
  }
  v37 = NtlmPoolType;
  v10 = 256;
  if ( NtlmPoolType != PagedPool )
    v10 = 64;
  v38 = v10;
  Pool2 = ExAllocatePool2((unsigned int)v10, v8 + v9 + 280, 1131836237);
  v12 = (char *)Pool2;
  if ( Pool2 )
  {
    *(_OWORD *)(Pool2 + 40) = 0;
    memset((void *)(Pool2 + 64), 0, 0xD8u);
    v13 = (void *)*(int *)(v3 + 8);
    *((_QWORD *)v12 + 1) = 0;
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 3) = 0;
    *((_QWORD *)v12 + 4) = 0;
    v14 = 120;
    *((_DWORD *)v12 + 4) = 1;
    *((_DWORD *)v12 + 5) = 1296847950;
    *((_QWORD *)v12 + 7) = v13;
    if ( !v13 )
      goto LABEL_21;
    ObjectInformation[0] = 0;
    DestinationString = 0;
    v15 = (UNICODE_STRING *)ExAllocatePool2(256, 120, 1131836237);
    v16 = v15;
    if ( v15 )
    {
      Object = ZwQueryObject(v13, ObjectTypeInformation, v15, 0x78u, 0);
      v7 = Object;
      if ( Object >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"Token");
        if ( !RtlEqualUnicodeString(v16, &DestinationString, 0) )
          v7 = -1073741816;
LABEL_16:
        ExFreePoolWithTag(v16, 0);
        if ( v7 < 0 )
          goto LABEL_71;
        goto LABEL_20;
      }
      if ( Object == -1073741816 )
        goto LABEL_16;
      ExFreePoolWithTag(v16, 0);
    }
LABEL_20:
    ObjectInformation[0] = 256;
    ZwSetInformationObject(v13, ObjectHandleFlagInformation, ObjectInformation, 2u);
LABEL_21:
    v18 = *(_DWORD *)(v3 + 4);
    *((_QWORD *)v12 + 5) = a1;
    *((_DWORD *)v12 + 12) = v18;
    v19 = *(_OWORD *)(v3 + 20);
    *(_OWORD *)(v12 + 148) = v19;
    if ( (v18 & 0x80000) != 0 )
    {
      if ( (v18 & 0x20000000) != 0 )
      {
        v20 = 16;
      }
      else
      {
        v20 = 5;
        if ( v18 < 0 )
          v20 = 7;
      }
      v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)v12 + 148, v20, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)"session key to client-to-server sealing key magic constant", 0x3Bu, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      BCryptDestroyHash(phHash);
      phHash = 0;
      if ( *((_QWORD *)v12 + 7) )
        *(_OWORD *)(v12 + 244) = *(_OWORD *)pbOutput;
      else
        *(_OWORD *)(v12 + 228) = *(_OWORD *)pbOutput;
      v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)v12 + 148, v20, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)"session key to server-to-client sealing key magic constant", 0x3Bu, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      BCryptDestroyHash(phHash);
      phHash = 0;
      if ( *((_QWORD *)v12 + 7) )
        *(_OWORD *)(v12 + 228) = *(_OWORD *)pbOutput;
      else
        *(_OWORD *)(v12 + 244) = *(_OWORD *)pbOutput;
      v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)v12 + 148, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)"session key to client-to-server signing key magic constant", 0x3Bu, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      BCryptDestroyHash(phHash);
      phHash = 0;
      if ( *((_QWORD *)v12 + 7) )
        *(_OWORD *)(v12 + 212) = *(_OWORD *)pbOutput;
      else
        *(_OWORD *)(v12 + 196) = *(_OWORD *)pbOutput;
      v7 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &phHash, 0, 0, 0, 0, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)v12 + 148, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptHashData(phHash, (PUCHAR)"session key to server-to-client signing key magic constant", 0x3Bu, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      v7 = BCryptFinishHash(phHash, pbOutput, 0x10u, 0);
      if ( v7 < 0 )
        goto LABEL_71;
      BCryptDestroyHash(phHash);
      phHash = 0;
      if ( *((_QWORD *)v12 + 7) )
        *(_OWORD *)(v12 + 196) = *(_OWORD *)pbOutput;
      else
        *(_OWORD *)(v12 + 212) = *(_OWORD *)pbOutput;
      v21 = v12 + 228;
      v22 = 112;
      v14 = 124;
    }
    else
    {
      v21 = v12 + 228;
      v22 = 104;
      *(_OWORD *)(v12 + 228) = v19;
      *(_OWORD *)(v12 + 244) = v19;
      *(_OWORD *)(v12 + 196) = v19;
      *(_OWORD *)(v12 + 212) = v19;
    }
    *((_QWORD *)v12 + 11) = v12 + 104;
    *((_QWORD *)v12 + 12) = &v12[v22];
    *((_QWORD *)v12 + 9) = v12 + 120;
    *((_QWORD *)v12 + 10) = &v12[v14];
    if ( *(_DWORD *)(v3 + 64) )
    {
      v23 = (void *)ExAllocatePool2(v38, *(unsigned int *)(v3 + 64), 1131836237);
      *((_QWORD *)v12 + 16) = v23;
      if ( !v23 )
      {
        v7 = -1073741670;
LABEL_71:
        v4 = v35;
        goto LABEL_72;
      }
      memmove(v23, (const void *)(v3 + *(unsigned int *)(v3 + 60)), *(unsigned int *)(v3 + 64));
    }
    else
    {
      *((_QWORD *)v12 + 16) = 0;
    }
    v24 = *(unsigned int *)(v3 + 68);
    v25 = v12 + 280;
    if ( (_DWORD)v24 )
    {
      v26 = *(unsigned int *)(v3 + 72);
      *((_QWORD *)v12 + 17) = v25;
      *((_DWORD *)v12 + 36) = v26;
      v27 = &v25[v26];
      memmove(v12 + 280, (const void *)(v3 + v24), v26);
    }
    else
    {
      v27 = v12 + 280;
    }
    v28 = *(unsigned int *)(v3 + 140);
    if ( (_DWORD)v28 )
    {
      v29 = *(unsigned int *)(v3 + 144);
      *((_DWORD *)v12 + 68) = v29;
      *((_QWORD *)v12 + 33) = v27;
      memmove(v27, (const void *)(v3 + v28), v29);
    }
    v30 = *((unsigned int *)v12 + 12);
    *((_DWORD *)v12 + 30) = *(_DWORD *)(v3 + 12);
    *((_DWORD *)v12 + 31) = *(_DWORD *)(v3 + 16);
    v7 = SspRc4Key(v30, v12 + 104, v21);
    if ( v7 >= 0 )
    {
      v7 = SspRc4Key(*((unsigned int *)v12 + 12), v12 + 112, v12 + 244);
      if ( v7 >= 0 )
      {
        v31 = NtlmNonPagedList;
        v32 = v37 == PagedPool;
        *((_QWORD *)v12 + 22) = *(_QWORD *)(v3 + 40);
        if ( v32 )
          v31 = NtlmPagedList;
        *((_QWORD *)v12 + 23) = *(_QWORD *)(v3 + 48);
        *((_DWORD *)v12 + 48) = *(_DWORD *)(v3 + 56);
        (*((void (__fastcall **)(void *, char *))LsaKernelFunctions + 3))(v31, v12);
        NtlmDerefContext(v12);
        *v39 = v12;
      }
    }
    goto LABEL_71;
  }
  v7 = -1073741670;
LABEL_72:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v7 < 0 && v12 )
    NtlmFreeKernelContext(v12);
LABEL_77:
  if ( *(_QWORD *)(v4 + 8) )
  {
    (*((void (**)(void))LsaKernelFunctions + 1))();
    *(_QWORD *)(v4 + 8) = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140023580  mov     r11, rsp
0x140023583  push    rbp
0x140023584  push    rbx
0x140023585  push    r12
0x140023587  push    r14
0x140023589  lea     rbp, [r11-5Fh]
0x14002358d  sub     rsp, 0A8h
0x140023594  mov     rax, cs:__security_cookie
0x14002359b  xor     rax, rsp
0x14002359e  mov     [rbp+57h+var_38], rax
0x1400235a2  xor     r12d, r12d
0x1400235a5  mov     [r11+8], rsi
0x1400235a9  mov     rsi, [rdx+8]
0x1400235ad  mov     r14, rdx
0x1400235b0  mov     [r8], r12
0x1400235b3  cmp     dword ptr [rdx], 0A8h
0x1400235b9  mov     [r11-30h], r13
0x1400235bd  mov     r13, rcx
0x1400235c0  mov     [rbp+57h+var_60], r8
0x1400235c4  mov     [rbp+57h+var_78], rdx
0x1400235c8  mov     [rbp+57h+phHash], r12
0x1400235cc  jnb     short loc_1400235D8
0x1400235ce  mov     ebx, 0C000000Dh
0x1400235d3  jmp     loc_140023D25
0x1400235d8  mov     eax, [rsi+48h]
0x1400235db  cmp     eax, 0FFFFh
0x1400235e0  jb      short loc_1400235EC
0x1400235e2  mov     ebx, 0C000000Dh
0x1400235e7  jmp     loc_140023D25
0x1400235ec  mov     ecx, [rsi+90h]
0x1400235f2  cmp     ecx, 0FFFFh
0x1400235f8  jb      short loc_140023604
0x1400235fa  mov     ebx, 0C000000Dh
0x1400235ff  jmp     loc_140023D25
0x140023604  mov     edx, cs:?NtlmPoolType@@3W4_POOL_TYPE@@A; _POOL_TYPE NtlmPoolType
0x14002360a  mov     r8d, 40h ; '@'
0x140023610  cmp     edx, 1
0x140023613  mov     [rbp+57h+var_6C], edx
0x140023616  lea     rdx, [rcx+118h]
0x14002361d  mov     [rsp+0A0h], rdi
0x140023625  mov     r9d, 100h
0x14002362b  cmovnz  r9d, r8d
0x14002362f  add     rdx, rax
0x140023632  mov     ecx, r9d
0x140023635  mov     [rbp+57h+var_68], r9
0x140023639  mov     r8d, 4376734Dh
0x14002363f  call    cs:__imp_ExAllocatePool2
0x140023646  nop     dword ptr [rax+rax+00h]
0x14002364b  mov     rdi, rax
0x14002364e  test    rax, rax
0x140023651  jnz     short loc_14002365D
0x140023653  mov     ebx, 0C000009Ah
0x140023658  jmp     loc_140023CF7
0x14002365d  xorps   xmm0, xmm0
0x140023660  mov     [rsp+0C0h+var_30], r15
0x140023668  lea     rcx, [rax+40h]; void *
0x14002366c  xor     edx, edx; Val
0x14002366e  mov     r8d, 0D8h; Size
0x140023674  movups  xmmword ptr [rax+28h], xmm0
0x140023678  call    memset
0x14002367d  movsxd  r15, dword ptr [rsi+8]
0x140023681  mov     [rdi+8], r12
0x140023685  mov     [rdi], r12
0x140023688  mov     [rdi+18h], r12
0x14002368c  mov     [rdi+20h], r12
0x140023690  mov     r12d, 78h ; 'x'
0x140023696  mov     dword ptr [rdi+10h], 1
0x14002369d  mov     dword ptr [rdi+14h], 4D4C544Eh
0x1400236a4  mov     [rdi+38h], r15
0x1400236a8  test    r15, r15
0x1400236ab  jz      loc_14002379C
0x1400236b1  xor     eax, eax
0x1400236b3  xorps   xmm0, xmm0
0x1400236b6  mov     r8d, 4376734Dh
0x1400236bc  mov     [rbp+57h+ObjectInformation], ax
0x1400236c0  mov     edx, r12d
0x1400236c3  mov     ecx, 100h
0x1400236c8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400236cc  call    cs:__imp_ExAllocatePool2
0x1400236d3  nop     dword ptr [rax+rax+00h]
0x1400236d8  mov     r14, rax
0x1400236db  test    rax, rax
0x1400236de  jz      loc_140023778
0x1400236e4  mov     r9d, r12d; ObjectInformationLength
0x1400236e7  mov     [rsp+0C0h+ReturnLength], 0; ReturnLength
0x1400236f0  mov     r8, rax; ObjectInformation
0x1400236f3  mov     edx, 2; ObjectInformationClass
0x1400236f8  mov     rcx, r15; Handle
0x1400236fb  call    cs:__imp_ZwQueryObject
0x140023702  nop     dword ptr [rax+rax+00h]
0x140023707  mov     ebx, eax
0x140023709  test    eax, eax
0x14002370b  js      short loc_140023760
0x14002370d  lea     rdx, aToken; "Token"
0x140023714  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140023718  call    cs:__imp_RtlInitUnicodeString
0x14002371f  nop     dword ptr [rax+rax+00h]
0x140023724  xor     r8d, r8d; CaseInSensitive
0x140023727  lea     rdx, [rbp+57h+DestinationString]; String2
0x14002372b  mov     rcx, r14; String1
0x14002372e  call    cs:__imp_RtlEqualUnicodeString
0x140023735  nop     dword ptr [rax+rax+00h]
0x14002373a  test    al, al
0x14002373c  jnz     short loc_140023743
0x14002373e  mov     ebx, 0C0000008h
0x140023743  xor     edx, edx; Tag
0x140023745  mov     rcx, r14; P
0x140023748  call    cs:__imp_ExFreePoolWithTag
0x14002374f  nop     dword ptr [rax+rax+00h]
0x140023754  test    ebx, ebx
0x140023756  jns     short loc_140023778
0x140023758  xor     r12d, r12d
0x14002375b  jmp     loc_140023CEB
0x140023760  cmp     eax, 0C0000008h
0x140023765  jz      short loc_140023743
0x140023767  xor     edx, edx; Tag
0x140023769  mov     rcx, r14; P
0x14002376c  call    cs:__imp_ExFreePoolWithTag
0x140023773  nop     dword ptr [rax+rax+00h]
0x140023778  mov     r9d, 2; Length
0x14002377e  mov     [rbp+57h+ObjectInformation], 100h
0x140023784  lea     r8, [rbp+57h+ObjectInformation]; ObjectInformation
0x140023788  mov     edx, 4; ObjectInformationClass
0x14002378d  mov     rcx, r15; ObjectHandle
0x140023790  call    cs:__imp_ZwSetInformationObject
0x140023797  nop     dword ptr [rax+rax+00h]
0x14002379c  mov     eax, [rsi+4]
0x14002379f  mov     [rdi+28h], r13
0x1400237a3  mov     [rdi+30h], eax
0x1400237a6  movups  xmm0, xmmword ptr [rsi+14h]
0x1400237aa  movups  xmmword ptr [rdi+94h], xmm0
0x1400237b1  bt      eax, 13h
0x1400237b5  jnb     loc_140023B5F
0x1400237bb  bt      eax, 1Dh
0x1400237bf  jnb     short loc_1400237C9
0x1400237c1  mov     r14d, 10h
0x1400237c7  jmp     short loc_1400237DA
0x1400237c9  test    eax, eax
0x1400237cb  mov     ecx, 7
0x1400237d0  mov     r14d, 5
0x1400237d6  cmovs   r14d, ecx
0x1400237da  xor     r12d, r12d
0x1400237dd  lea     rdx, [rbp+57h+phHash]; phHash
0x1400237e1  mov     [rsp+30h], r12d; dwFlags
0x1400237e6  xor     r9d, r9d; cbHashObject
0x1400237e9  mov     [rsp+0C0h+cbSecret], r12d; cbSecret
0x1400237ee  xor     r8d, r8d; pbHashObject
0x1400237f1  mov     ecx, 21h ; '!'; hAlgorithm
0x1400237f6  mov     [rsp+0C0h+ReturnLength], r12; pbSecret
0x1400237fb  call    cs:__imp_BCryptCreateHash
0x140023802  nop     dword ptr [rax+rax+00h]
0x140023807  mov     ebx, eax
0x140023809  test    eax, eax
0x14002380b  js      loc_140023CEB
0x140023811  mov     rcx, [rbp+57h+phHash]; hHash
0x140023815  lea     rdx, [rdi+94h]; pbInput
0x14002381c  xor     r9d, r9d; dwFlags
0x14002381f  mov     r8d, r14d; cbInput
0x140023822  call    cs:__imp_BCryptHashData
0x140023829  nop     dword ptr [rax+rax+00h]
0x14002382e  mov     ebx, eax
0x140023830  test    eax, eax
0x140023832  js      loc_140023CEB
0x140023838  mov     rcx, [rbp+57h+phHash]; hHash
0x14002383c  lea     rdx, pbInput; "session key to client-to-server sealing"...
0x140023843  xor     r9d, r9d; dwFlags
0x140023846  mov     r8d, 3Bh ; ';'; cbInput
0x14002384c  call    cs:__imp_BCryptHashData
0x140023853  nop     dword ptr [rax+rax+00h]
0x140023858  mov     ebx, eax
0x14002385a  test    eax, eax
0x14002385c  js      loc_140023CEB
0x140023862  mov     rcx, [rbp+57h+phHash]; hHash
0x140023866  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x14002386a  xor     r9d, r9d; dwFlags
0x14002386d  mov     r8d, 10h; cbOutput
0x140023873  call    cs:__imp_BCryptFinishHash
0x14002387a  nop     dword ptr [rax+rax+00h]
0x14002387f  mov     ebx, eax
0x140023881  test    eax, eax
0x140023883  js      loc_140023CEB
0x140023889  mov     rcx, [rbp+57h+phHash]; hHash
0x14002388d  call    cs:__imp_BCryptDestroyHash
0x140023894  nop     dword ptr [rax+rax+00h]
0x140023899  movups  xmm0, xmmword ptr [rbp+57h+pbOutput]
0x14002389d  mov     [rbp+57h+phHash], r12
0x1400238a1  cmp     [rdi+38h], r12
0x1400238a5  jnz     short loc_1400238B0
0x1400238a7  movups  xmmword ptr [rdi+0E4h], xmm0
0x1400238ae  jmp     short loc_1400238B7
0x1400238b0  movups  xmmword ptr [rdi+0F4h], xmm0
0x1400238b7  mov     [rsp+30h], r12d; dwFlags
0x1400238bc  lea     rdx, [rbp+57h+phHash]; phHash
0x1400238c0  mov     [rsp+0C0h+cbSecret], r12d; cbSecret
0x1400238c5  xor     r9d, r9d; cbHashObject
0x1400238c8  xor     r8d, r8d; pbHashObject
0x1400238cb  mov     [rsp+0C0h+ReturnLength], r12; pbSecret
0x1400238d0  mov     ecx, 21h ; '!'; hAlgorithm
0x1400238d5  call    cs:__imp_BCryptCreateHash
0x1400238dc  nop     dword ptr [rax+rax+00h]
0x1400238e1  mov     ebx, eax
0x1400238e3  test    eax, eax
0x1400238e5  js      loc_140023CEB
0x1400238eb  mov     rcx, [rbp+57h+phHash]; hHash
0x1400238ef  lea     rdx, [rdi+94h]; pbInput
0x1400238f6  xor     r9d, r9d; dwFlags
0x1400238f9  mov     r8d, r14d; cbInput
0x1400238fc  call    cs:__imp_BCryptHashData
0x140023903  nop     dword ptr [rax+rax+00h]
0x140023908  mov     ebx, eax
0x14002390a  test    eax, eax
0x14002390c  js      loc_140023CEB
0x140023912  mov     rcx, [rbp+57h+phHash]; hHash
0x140023916  lea     rdx, aSessionKeyToSe_0; "session key to server-to-client sealing"...
0x14002391d  xor     r9d, r9d; dwFlags
0x140023920  mov     r8d, 3Bh ; ';'; cbInput
0x140023926  call    cs:__imp_BCryptHashData
0x14002392d  nop     dword ptr [rax+rax+00h]
0x140023932  mov     ebx, eax
0x140023934  test    eax, eax
0x140023936  js      loc_140023CEB
0x14002393c  mov     rcx, [rbp+57h+phHash]; hHash
0x140023940  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x140023944  xor     r9d, r9d; dwFlags
0x140023947  mov     r8d, 10h; cbOutput
0x14002394d  call    cs:__imp_BCryptFinishHash
0x140023954  nop     dword ptr [rax+rax+00h]
0x140023959  mov     ebx, eax
0x14002395b  test    eax, eax
0x14002395d  js      loc_140023CEB
0x140023963  mov     rcx, [rbp+57h+phHash]; hHash
0x140023967  call    cs:__imp_BCryptDestroyHash
0x14002396e  nop     dword ptr [rax+rax+00h]
0x140023973  movups  xmm0, xmmword ptr [rbp+57h+pbOutput]
0x140023977  mov     [rbp+57h+phHash], r12
0x14002397b  cmp     [rdi+38h], r12
0x14002397f  jnz     short loc_14002398A
0x140023981  movups  xmmword ptr [rdi+0F4h], xmm0
0x140023988  jmp     short loc_140023991
0x14002398a  movups  xmmword ptr [rdi+0E4h], xmm0
0x140023991  mov     [rsp+30h], r12d; dwFlags
0x140023996  lea     rdx, [rbp+57h+phHash]; phHash
0x14002399a  mov     [rsp+0C0h+cbSecret], r12d; cbSecret
0x14002399f  xor     r9d, r9d; cbHashObject
0x1400239a2  xor     r8d, r8d; pbHashObject
0x1400239a5  mov     [rsp+0C0h+ReturnLength], r12; pbSecret
0x1400239aa  mov     ecx, 21h ; '!'; hAlgorithm
0x1400239af  call    cs:__imp_BCryptCreateHash
0x1400239b6  nop     dword ptr [rax+rax+00h]
0x1400239bb  mov     ebx, eax
0x1400239bd  test    eax, eax
0x1400239bf  js      loc_140023CEB
0x1400239c5  mov     rcx, [rbp+57h+phHash]; hHash
0x1400239c9  lea     rdx, [rdi+94h]; pbInput
0x1400239d0  xor     r9d, r9d; dwFlags
0x1400239d3  mov     r8d, 10h; cbInput
0x1400239d9  call    cs:__imp_BCryptHashData
0x1400239e0  nop     dword ptr [rax+rax+00h]
0x1400239e5  mov     ebx, eax
0x1400239e7  test    eax, eax
0x1400239e9  js      loc_140023CEB
0x1400239ef  mov     rcx, [rbp+57h+phHash]; hHash
0x1400239f3  lea     rdx, aSessionKeyToCl; "session key to client-to-server signing"...
0x1400239fa  xor     r9d, r9d; dwFlags
0x1400239fd  mov     r8d, 3Bh ; ';'; cbInput
0x140023a03  call    cs:__imp_BCryptHashData
0x140023a0a  nop     dword ptr [rax+rax+00h]
0x140023a0f  mov     ebx, eax
0x140023a11  test    eax, eax
0x140023a13  js      loc_140023CEB
0x140023a19  mov     rcx, [rbp+57h+phHash]; hHash
0x140023a1d  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x140023a21  xor     r9d, r9d; dwFlags
0x140023a24  mov     r8d, 10h; cbOutput
0x140023a2a  call    cs:__imp_BCryptFinishHash
0x140023a31  nop     dword ptr [rax+rax+00h]
0x140023a36  mov     ebx, eax
0x140023a38  test    eax, eax
0x140023a3a  js      loc_140023CEB
0x140023a40  mov     rcx, [rbp+57h+phHash]; hHash
0x140023a44  call    cs:__imp_BCryptDestroyHash
0x140023a4b  nop     dword ptr [rax+rax+00h]
0x140023a50  movups  xmm0, xmmword ptr [rbp+57h+pbOutput]
0x140023a54  mov     [rbp+57h+phHash], r12
0x140023a58  cmp     [rdi+38h], r12
0x140023a5c  jnz     short loc_140023A67
0x140023a5e  movups  xmmword ptr [rdi+0C4h], xmm0
0x140023a65  jmp     short loc_140023A6E
0x140023a67  movups  xmmword ptr [rdi+0D4h], xmm0
0x140023a6e  mov     [rsp+30h], r12d; dwFlags
0x140023a73  lea     rdx, [rbp+57h+phHash]; phHash
0x140023a77  mov     [rsp+0C0h+cbSecret], r12d; cbSecret
0x140023a7c  xor     r9d, r9d; cbHashObject
0x140023a7f  xor     r8d, r8d; pbHashObject
0x140023a82  mov     [rsp+0C0h+ReturnLength], r12; pbSecret
0x140023a87  mov     ecx, 21h ; '!'; hAlgorithm
0x140023a8c  call    cs:__imp_BCryptCreateHash
0x140023a93  nop     dword ptr [rax+rax+00h]
0x140023a98  mov     ebx, eax
0x140023a9a  test    eax, eax
  ... truncated ...
```
