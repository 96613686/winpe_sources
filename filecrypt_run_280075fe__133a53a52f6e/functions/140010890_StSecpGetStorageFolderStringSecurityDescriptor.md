# StSecpGetStorageFolderStringSecurityDescriptor

- ea: `0x140010890`
- end: `0x140010caa`
- name: `StSecpGetStorageFolderStringSecurityDescriptor`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140010500`

## callees

- `0x140001190`
- `0x1400012b0`
- `0x140003454`
- `0x14000d7a8`
- `0x140010890`
- `0x140010cb0`
- `0x140010f90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140010a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b00`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010b00`
- `ntoskrnl!ExAllocatePool2` at `0x1400109c0`
- `ntoskrnl!ExAllocatePool2` at `0x1400109c0`
- `ntoskrnl!FsRtlDissectName` at `0x14001096d`
- `ntoskrnl!FsRtlDissectName` at `0x14001098c`
- `ntoskrnl!FsRtlDissectName` at `0x140010ad0`
- `ntoskrnl!FsRtlDissectName` at `0x14001096d`
- `ntoskrnl!FsRtlDissectName` at `0x14001098c`
- `ntoskrnl!FsRtlDissectName` at `0x140010ad0`

## pseudocode

```c
__int64 __fastcall StSecpGetStorageFolderStringSecurityDescriptor(UNICODE_STRING *a1, wchar_t **a2)
{
  __int64 SecurityDescriptorPolicyElement; // rax
  __int64 v5; // r13
  _WORD *v6; // rax
  __int64 v7; // rcx
  int ParameterValue; // ebx
  __int64 v9; // r14
  wchar_t *v10; // rsi
  size_t v11; // r15
  size_t v12; // rdx
  bool v13; // di
  wchar_t *Pool2; // rax
  unsigned __int64 v15; // r8
  wchar_t *v16; // rdx
  __int64 v17; // rcx
  wchar_t *v18; // r9
  wchar_t *v19; // rcx
  __int64 i; // rdi
  PVOID v22; // rcx
  PVOID *v23; // rdi
  _WORD *v24; // rax
  __int64 v25; // rcx
  struct _UNICODE_STRING FirstName; // [rsp+30h] [rbp-39h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-29h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-19h] BYREF
  struct _UNICODE_STRING RemainingName; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING v30; // [rsp+70h] [rbp+7h] BYREF
  UNICODE_STRING Path; // [rsp+80h] [rbp+17h] BYREF
  bool v32; // [rsp+E0h] [rbp+77h] BYREF
  size_t pcbLength; // [rsp+E8h] [rbp+7Fh] BYREF

  pcbLength = 0;
  v32 = 0;
  FirstName = 0;
  RemainingName = 0;
  ValueName = 0;
  v30 = 0;
  *(_OWORD *)P = 0;
  SecurityDescriptorPolicyElement = StSecpFindSecurityDescriptorPolicyElement(a1);
  v5 = SecurityDescriptorPolicyElement;
  if ( !SecurityDescriptorPolicyElement )
    return 3221225524LL;
  v6 = *(_WORD **)(SecurityDescriptorPolicyElement + 32);
  if ( !v6 )
    return 3221225485LL;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  if ( !v7 )
    return 3221225485LL;
  ParameterValue = 0;
  v9 = 0;
  Path = *(UNICODE_STRING *)(v5 + 16);
  v10 = 0;
  v11 = 2 * (0x7FFFFFFF - v7) + 2;
  FsRtlDissectName(&Path, &FirstName, &RemainingName);
  for ( Path = *a1; ; Path = v30 )
  {
    FsRtlDissectName(&Path, &ValueName, &v30);
    if ( !FirstName.Buffer )
      break;
    if ( *FirstName.Buffer == 60 && FirstName.Buffer[((unsigned __int64)FirstName.Length >> 1) - 1] == 62 )
    {
      if ( !ValueName.Buffer || (_DWORD)v9 == 2 )
      {
        ParameterValue = -1073741823;
        goto LABEL_24;
      }
      v23 = &P[v9];
      ParameterValue = StSecpGetParameterValue(&FirstName, &ValueName, v23);
      if ( ParameterValue < 0 )
        goto LABEL_24;
      v24 = *v23;
      if ( !*v23 )
      {
        ParameterValue = -1073741811;
        goto LABEL_24;
      }
      v25 = 0x7FFFFFFF;
      do
      {
        if ( !*v24 )
          break;
        ++v24;
        --v25;
      }
      while ( v25 );
      ParameterValue = -1073741811;
      if ( !v25 )
        goto LABEL_24;
      ParameterValue = 0;
      v11 += 2 * (0x7FFFFFFF - v25);
      pcbLength = 2 * (0x7FFFFFFF - v25);
      v9 = (unsigned int)(v9 + 1);
    }
    if ( *(_QWORD *)(v5 + 40) )
    {
      ParameterValue = StSecpCheckConditionalPolicy(&FirstName, &ValueName, &v32);
      if ( ParameterValue < 0 )
        goto LABEL_24;
    }
    Path = RemainingName;
    FsRtlDissectName(&Path, &FirstName, &RemainingName);
  }
  v13 = v32;
  if ( !v32 )
    goto LABEL_10;
  ParameterValue = RtlStringCbLengthW(*(STRSAFE_PCNZWCH *)(v5 + 40), v12, &pcbLength);
  if ( ParameterValue >= 0 )
  {
    v11 += pcbLength;
LABEL_10:
    Pool2 = (wchar_t *)ExAllocatePool2(256, v11, 1884517459);
    v10 = Pool2;
    if ( Pool2 )
    {
      if ( (_DWORD)v9 )
      {
        if ( (_DWORD)v9 == 1 )
        {
          ParameterValue = RtlStringCbPrintfW(Pool2, v11, *(NTSTRSAFE_PCWSTR *)(v5 + 32), P[0]);
        }
        else if ( (_DWORD)v9 == 2 )
        {
          ParameterValue = RtlStringCbPrintfW(Pool2, v11, *(NTSTRSAFE_PCWSTR *)(v5 + 32), P[0], P[1]);
        }
      }
      else
      {
        v15 = v11 >> 1;
        if ( v11 >> 1 )
        {
          if ( v15 > 0x7FFFFFFF )
          {
            ParameterValue = -1073741811;
            *Pool2 = 0;
          }
          else
          {
            v16 = *(wchar_t **)(v5 + 32);
            v17 = 2147483646;
            v18 = Pool2;
            do
            {
              if ( !v17 )
                break;
              if ( !*v16 )
                break;
              *v18++ = *v16++;
              --v17;
              --v15;
            }
            while ( v15 );
            v19 = v18 - 1;
            ParameterValue = -2147483643;
            if ( v15 )
            {
              v19 = v18;
              ParameterValue = 0;
            }
            *v19 = 0;
          }
        }
        else
        {
          ParameterValue = -1073741811;
        }
      }
      if ( ParameterValue >= 0 )
      {
        if ( !v13 || (ParameterValue = RtlStringCbCatW(v10, v11, *(NTSTRSAFE_PCWSTR *)(v5 + 40)), ParameterValue >= 0) )
        {
          *a2 = v10;
          v10 = 0;
        }
      }
    }
    else
    {
      ParameterValue = -1073741801;
    }
  }
LABEL_24:
  for ( i = 0; (unsigned int)i < (unsigned int)v9; i = (unsigned int)(i + 1) )
  {
    v22 = P[i];
    if ( v22 )
      ExFreePoolWithTag(v22, 0);
  }
  if ( v10 )
    ExFreePoolWithTag(v10, 0x70537453u);
  return (unsigned int)ParameterValue;
}

```

## disassembly

```asm
0x140010890  push    rbp
0x140010892  push    rdi
0x140010893  push    r12
0x140010895  push    r13
0x140010897  lea     rbp, [rsp-3Fh]
0x14001089c  sub     rsp, 0A8h
0x1400108a3  xorps   xmm0, xmm0
0x1400108a6  mov     [rbp+57h+pcbLength], 0
0x1400108ae  xorps   xmm1, xmm1
0x1400108b1  mov     [rbp+57h+arg_10], 0
0x1400108b5  movups  xmmword ptr [rbp+57h+FirstName.Length], xmm0
0x1400108b9  mov     r12, rdx
0x1400108bc  mov     rdi, rcx
0x1400108bf  movups  xmmword ptr [rbp+57h+RemainingName.Length], xmm1
0x1400108c3  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x1400108c7  movups  xmmword ptr [rbp+57h+var_50.Length], xmm1
0x1400108cb  movups  xmmword ptr [rbp+57h+P], xmm0
0x1400108cf  call    StSecpFindSecurityDescriptorPolicyElement
0x1400108d4  mov     r13, rax
0x1400108d7  test    rax, rax
0x1400108da  jz      loc_140010C03
0x1400108e0  mov     rax, [rax+20h]
0x1400108e4  mov     [rsp+0C0h+arg_0], rbx
0x1400108ec  test    rax, rax
0x1400108ef  jz      loc_140010C9E
0x1400108f5  mov     ecx, 7FFFFFFFh
0x1400108fa  nop     word ptr [rax+rax+00h]
0x140010900  cmp     word ptr [rax], 0
0x140010904  jz      short loc_140010910
0x140010906  add     rax, 2
0x14001090a  sub     rcx, 1
0x14001090e  jnz     short loc_140010900
0x140010910  xor     eax, eax
0x140010912  mov     ebx, 0C000000Dh
0x140010917  test    rcx, rcx
0x14001091a  cmovnz  ebx, eax
0x14001091d  jz      loc_140010CA3
0x140010923  mov     eax, 7FFFFFFFh
0x140010928  sub     rax, rcx
0x14001092b  add     rax, rax
0x14001092e  test    rcx, rcx
0x140010931  jz      loc_140010CA3
0x140010937  movups  xmm0, xmmword ptr [r13+10h]
0x14001093c  mov     [rsp+0C0h+var_20], rsi
0x140010944  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x140010948  mov     [rsp+0C0h+var_28], r14
0x140010950  lea     rdx, [rbp+57h+FirstName]; FirstName
0x140010954  mov     [rsp+0C0h+var_30], r15
0x14001095c  lea     rcx, [rbp+57h+Path]; Path
0x140010960  xor     r14d, r14d
0x140010963  movaps  xmmword ptr [rbp+57h+Path.Length], xmm0
0x140010967  xor     esi, esi
0x140010969  lea     r15, [rax+2]
0x14001096d  call    cs:__imp_FsRtlDissectName
0x140010974  nop     dword ptr [rax+rax+00h]
0x140010979  movups  xmm0, xmmword ptr [rdi]
0x14001097c  movaps  xmmword ptr [rbp+57h+Path.Length], xmm0
0x140010980  lea     r8, [rbp+57h+var_50]; RemainingName
0x140010984  lea     rdx, [rbp+57h+ValueName]; FirstName
0x140010988  lea     rcx, [rbp+57h+Path]; Path
0x14001098c  call    cs:__imp_FsRtlDissectName
0x140010993  nop     dword ptr [rax+rax+00h]
0x140010998  mov     rcx, [rbp+57h+FirstName.Buffer]
0x14001099c  test    rcx, rcx
0x14001099f  jnz     loc_140010AAB
0x1400109a5  movzx   edi, [rbp+57h+arg_10]
0x1400109a9  test    dil, dil
0x1400109ac  jnz     loc_140010C41
0x1400109b2  mov     r8d, 70537453h
0x1400109b8  mov     rdx, r15
0x1400109bb  mov     ecx, 100h
0x1400109c0  call    cs:__imp_ExAllocatePool2
0x1400109c7  nop     dword ptr [rax+rax+00h]
0x1400109cc  mov     rsi, rax
0x1400109cf  test    rax, rax
0x1400109d2  jz      loc_140010AEA
0x1400109d8  test    r14d, r14d
0x1400109db  jnz     loc_140010BB5
0x1400109e1  mov     r8, r15
0x1400109e4  shr     r8, 1
0x1400109e7  jz      loc_140010C68
0x1400109ed  cmp     r8, 7FFFFFFFh
0x1400109f4  ja      loc_140010C61
0x1400109fa  mov     rdx, [r13+20h]
0x1400109fe  mov     ecx, 7FFFFFFEh
0x140010a03  mov     r9, rax
0x140010a06  test    rcx, rcx
0x140010a09  jz      short loc_140010A28
0x140010a0b  movzx   eax, word ptr [rdx]
0x140010a0e  test    ax, ax
0x140010a11  jz      short loc_140010A28
0x140010a13  mov     [r9], ax
0x140010a17  add     rdx, 2
0x140010a1b  add     r9, 2
0x140010a1f  dec     rcx
0x140010a22  sub     r8, 1
0x140010a26  jnz     short loc_140010A06
0x140010a28  test    r8, r8
0x140010a2b  lea     rcx, [r9-2]
0x140010a2f  mov     ebx, 80000005h
0x140010a34  cmovnz  rcx, r9
0x140010a38  xor     eax, eax
0x140010a3a  test    r8, r8
0x140010a3d  cmovnz  ebx, eax
0x140010a40  mov     [rcx], ax
0x140010a43  test    ebx, ebx
0x140010a45  js      short loc_140010A56
0x140010a47  test    dil, dil
0x140010a4a  jnz     loc_140010C80
0x140010a50  mov     [r12], rsi
0x140010a54  xor     esi, esi
0x140010a56  mov     r15, [rsp+0C0h+var_30]
0x140010a5e  xor     edi, edi
0x140010a60  test    r14d, r14d
0x140010a63  jnz     loc_140010AF4
0x140010a69  mov     r14, [rsp+0C0h+var_28]
0x140010a71  test    rsi, rsi
0x140010a74  jz      short loc_140010A8A
0x140010a76  mov     edx, 70537453h; Tag
0x140010a7b  mov     rcx, rsi; P
0x140010a7e  call    cs:__imp_ExFreePoolWithTag
0x140010a85  nop     dword ptr [rax+rax+00h]
0x140010a8a  mov     rsi, [rsp+0C0h+var_20]
0x140010a92  mov     eax, ebx
0x140010a94  mov     rbx, [rsp+0C0h+arg_0]
0x140010a9c  add     rsp, 0A8h
0x140010aa3  pop     r13
0x140010aa5  pop     r12
0x140010aa7  pop     rdi
0x140010aa8  pop     rbp
0x140010aa9  retn
0x140010aab  cmp     word ptr [rcx], 3Ch ; '<'
0x140010aaf  jz      short loc_140010B19
0x140010ab1  cmp     [r13+28h], rsi
0x140010ab5  jnz     loc_140010C0D
0x140010abb  movaps  xmm0, xmmword ptr [rbp+57h+RemainingName.Length]
0x140010abf  lea     r8, [rbp+57h+RemainingName]; RemainingName
0x140010ac3  lea     rdx, [rbp+57h+FirstName]; FirstName
0x140010ac7  movdqa  xmmword ptr [rbp+57h+Path.Length], xmm0
0x140010acc  lea     rcx, [rbp+57h+Path]; Path
0x140010ad0  call    cs:__imp_FsRtlDissectName
0x140010ad7  nop     dword ptr [rax+rax+00h]
0x140010adc  movaps  xmm0, xmmword ptr [rbp+57h+var_50.Length]
0x140010ae0  movdqa  xmmword ptr [rbp+57h+Path.Length], xmm0
0x140010ae5  jmp     loc_140010980
0x140010aea  mov     ebx, 0C0000017h
0x140010aef  jmp     loc_140010A56
0x140010af4  mov     rcx, [rbp+rdi*8+57h+P]; P
0x140010af9  test    rcx, rcx
0x140010afc  jz      short loc_140010B0C
0x140010afe  xor     edx, edx; Tag
0x140010b00  call    cs:__imp_ExFreePoolWithTag
0x140010b07  nop     dword ptr [rax+rax+00h]
0x140010b0c  inc     edi
0x140010b0e  cmp     edi, r14d
0x140010b11  jnb     loc_140010A69
0x140010b17  jmp     short loc_140010AF4
0x140010b19  movzx   eax, [rbp+57h+FirstName.Length]
0x140010b1d  shr     rax, 1
0x140010b20  cmp     word ptr [rcx+rax*2-2], 3Eh ; '>'
0x140010b26  jnz     short loc_140010AB1
0x140010b28  cmp     [rbp+57h+ValueName.Buffer], rsi
0x140010b2c  jz      loc_140010C37
0x140010b32  cmp     r14d, 2
0x140010b36  jz      loc_140010C37
0x140010b3c  lea     rdi, [rbp+57h+P]
0x140010b40  lea     rdi, [rdi+r14*8]
0x140010b44  mov     r8, rdi
0x140010b47  lea     rdx, [rbp+57h+ValueName]; SourceString
0x140010b4b  lea     rcx, [rbp+57h+FirstName]; String1
0x140010b4f  call    StSecpGetParameterValue
0x140010b54  mov     ebx, eax
0x140010b56  test    eax, eax
0x140010b58  js      loc_140010A56
0x140010b5e  mov     rax, [rdi]
0x140010b61  test    rax, rax
0x140010b64  jz      loc_140010C2D
0x140010b6a  mov     ecx, 7FFFFFFFh
0x140010b6f  nop
0x140010b70  cmp     [rax], si
0x140010b73  jz      short loc_140010B7F
0x140010b75  add     rax, 2
0x140010b79  sub     rcx, 1
0x140010b7d  jnz     short loc_140010B70
0x140010b7f  xor     eax, eax
0x140010b81  mov     ebx, 0C000000Dh
0x140010b86  test    rcx, rcx
0x140010b89  cmovnz  ebx, eax
0x140010b8c  jz      loc_140010A56
0x140010b92  mov     eax, 7FFFFFFFh
0x140010b97  sub     rax, rcx
0x140010b9a  add     rax, rax
0x140010b9d  test    rcx, rcx
0x140010ba0  jz      loc_140010A56
0x140010ba6  add     r15, rax
0x140010ba9  mov     [rbp+57h+pcbLength], rax
0x140010bad  inc     r14d
0x140010bb0  jmp     loc_140010AB1
0x140010bb5  mov     eax, r14d
0x140010bb8  sub     eax, 1
0x140010bbb  jz      short loc_140010BE9
0x140010bbd  cmp     eax, 1
0x140010bc0  jnz     loc_140010A43
0x140010bc6  mov     rax, [rbp+57h+P+8]
0x140010bca  mov     rdx, r15; cbDest
0x140010bcd  mov     r9, [rbp+57h+P]
0x140010bd1  mov     rcx, rsi; pszDest
0x140010bd4  mov     r8, [r13+20h]; pszFormat
0x140010bd8  mov     [rsp+0C0h+var_A0], rax
0x140010bdd  call    RtlStringCbPrintfW
0x140010be2  mov     ebx, eax
0x140010be4  jmp     loc_140010A43
0x140010be9  mov     r9, [rbp+57h+P]
0x140010bed  mov     rdx, r15; cbDest
0x140010bf0  mov     r8, [r13+20h]; pszFormat
0x140010bf4  mov     rcx, rsi; pszDest
0x140010bf7  call    RtlStringCbPrintfW
0x140010bfc  mov     ebx, eax
0x140010bfe  jmp     loc_140010A43
0x140010c03  mov     eax, 0C0000034h
0x140010c08  jmp     loc_140010A9C
0x140010c0d  lea     r8, [rbp+57h+arg_10]
0x140010c11  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140010c15  lea     rcx, [rbp+57h+FirstName]; String1
0x140010c19  call    StSecpCheckConditionalPolicy
0x140010c1e  mov     ebx, eax
0x140010c20  test    eax, eax
0x140010c22  js      loc_140010A56
0x140010c28  jmp     loc_140010ABB
0x140010c2d  mov     ebx, 0C000000Dh
0x140010c32  jmp     loc_140010A56
0x140010c37  mov     ebx, 0C0000001h
0x140010c3c  jmp     loc_140010A56
0x140010c41  mov     rcx, [r13+28h]; psz
0x140010c45  lea     r8, [rbp+57h+pcbLength]; pcbLength
0x140010c49  call    RtlStringCbLengthW
0x140010c4e  mov     ebx, eax
0x140010c50  test    eax, eax
0x140010c52  js      loc_140010A56
0x140010c58  add     r15, [rbp+57h+pcbLength]
0x140010c5c  jmp     loc_1400109B2
0x140010c61  mov     ebx, 0C000000Dh
0x140010c66  jmp     short loc_140010C76
0x140010c68  mov     ebx, 0C000000Dh
0x140010c6d  test    r8, r8
0x140010c70  jz      loc_140010A43
0x140010c76  xor     eax, eax
0x140010c78  mov     [rsi], ax
0x140010c7b  jmp     loc_140010A43
0x140010c80  mov     r8, [r13+28h]; pszSrc
0x140010c84  mov     rdx, r15; cbDest
0x140010c87  mov     rcx, rsi; pszDest
0x140010c8a  call    RtlStringCbCatW
0x140010c8f  mov     ebx, eax
0x140010c91  test    eax, eax
0x140010c93  js      loc_140010A56
0x140010c99  jmp     loc_140010A50
0x140010c9e  mov     ebx, 0C000000Dh
0x140010ca3  mov     eax, ebx
0x140010ca5  jmp     loc_140010A94
```
