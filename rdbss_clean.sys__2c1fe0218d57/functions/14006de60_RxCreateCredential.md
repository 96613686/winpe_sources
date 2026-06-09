# RxCreateCredential

- ea: `0x14006de60`
- end: `0x14006e0bc`
- name: `RxCreateCredential`
- size: `604`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14007a510`

## callees

- `0x14000e180`
- `0x140017310`
- `0x140025d80`
- `0x14006de60`
- `0x14006e180`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006df02`
- `ntoskrnl!ExAllocatePool2` at `0x14006df02`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006e055`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14006e055`
- `ksecdd!MapSecurityError` at `0x14007f078`
- `ksecdd!MapSecurityError` at `0x14007f100`
- `ksecdd!MapSecurityError` at `0x14007f078`
- `ksecdd!MapSecurityError` at `0x14007f100`
- `ksecdd!SspiUnmarshalAuthIdentity` at `0x14007f068`
- `ksecdd!SspiUnmarshalAuthIdentity` at `0x14007f068`
- `ksecdd!SspiEncodeAuthIdentityAsStrings` at `0x14007f0f0`
- `ksecdd!SspiEncodeAuthIdentityAsStrings` at `0x14007f0f0`
- `ksecdd!SspiLocalFree` at `0x14006e089`
- `ksecdd!SspiLocalFree` at `0x14006e09a`
- `ksecdd!SspiLocalFree` at `0x14006e0ab`
- `ksecdd!SspiLocalFree` at `0x14006e089`
- `ksecdd!SspiLocalFree` at `0x14006e09a`
- `ksecdd!SspiLocalFree` at `0x14006e0ab`

## pseudocode

```c
__int64 __fastcall RxCreateCredential(
        _QWORD *a1,
        char *a2,
        unsigned int a3,
        __int128 *a4,
        __int128 *a5,
        __int128 *a6,
        __int64 a7,
        __int64 a8,
        PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  PSECURITY_DESCRIPTOR v9; // r12
  __int128 *v10; // r13
  __int128 *v11; // r15
  __int128 *v12; // r14
  int v14; // edi
  ULONG v15; // eax
  char *Pool2; // rbx
  size_t v18; // r8
  SECURITY_STATUS v19; // esi
  NTSTATUS v20; // eax
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  PVOID v26; // [rsp+30h] [rbp-50h] BYREF
  PVOID v27; // [rsp+38h] [rbp-48h] BYREF
  size_t Size; // [rsp+40h] [rbp-40h]
  __int128 v29; // [rsp+48h] [rbp-38h] BYREF
  __int128 v30; // [rsp+58h] [rbp-28h] BYREF
  __int128 v31; // [rsp+68h] [rbp-18h] BYREF
  PVOID DataBuffer; // [rsp+C8h] [rbp+48h] BYREF
  unsigned int AuthIdentityLength; // [rsp+D0h] [rbp+50h]

  AuthIdentityLength = a3;
  v9 = SecurityDescriptor;
  v10 = a6;
  v11 = a5;
  DataBuffer = 0;
  *a1 = 0;
  v12 = a4;
  v26 = 0;
  v27 = 0;
  v14 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( !a2 && !a4 && !v11 && !v10 && !a7 && !a8 && !v9 )
    return 0;
  v15 = 0;
  if ( v9 )
    v15 = RtlLengthSecurityDescriptor(v9);
  Size = v15;
  Pool2 = (char *)ExAllocatePool2(66, v15 + 72LL, 1917024338);
  if ( Pool2 )
  {
    *((_QWORD *)Pool2 + 1) = 0;
    *((_QWORD *)Pool2 + 2) = 0;
    *((_QWORD *)Pool2 + 3) = 0;
    *((_QWORD *)Pool2 + 4) = 0;
    *((_QWORD *)Pool2 + 5) = 0;
    *((_QWORD *)Pool2 + 6) = 0;
    *((_QWORD *)Pool2 + 7) = 0;
    *((_QWORD *)Pool2 + 8) = 0;
    *(_DWORD *)Pool2 = 4778848;
    *((_DWORD *)Pool2 + 1) = 1;
    if ( !a2 )
    {
LABEL_10:
      if ( (unsigned __int8)RxCloneUnicodeStringNonPagedPool(v12, Pool2 + 16) )
      {
        if ( (unsigned __int8)RxCloneUnicodeStringNonPagedPool(v11, Pool2 + 24) )
        {
          if ( (unsigned __int8)RxCloneUnicodeStringNonPagedPool(v10, Pool2 + 32) )
          {
            if ( (unsigned __int8)RxCloneUnicodeStringNonPagedPool(a7, Pool2 + 40) )
            {
              if ( (unsigned __int8)RxCloneUnicodeStringNonPagedPool(a8, Pool2 + 48) )
              {
                if ( v9 )
                {
                  v18 = Size;
                  *((_QWORD *)Pool2 + 7) = Pool2 + 72;
                  memmove(Pool2 + 72, v9, v18);
                }
                *a1 = Pool2;
              }
              else
              {
                v14 = -1073741670;
              }
            }
            else
            {
              v14 = -1073741670;
            }
          }
          else
          {
            v14 = -1073741670;
          }
        }
        else
        {
          v14 = -1073741670;
        }
      }
      else
      {
        v14 = -1073741670;
      }
      goto LABEL_18;
    }
    v19 = SspiUnmarshalAuthIdentity(AuthIdentityLength, a2, (PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)Pool2 + 1);
    v20 = MapSecurityError(v19);
    v14 = v20;
    if ( v20 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_18;
      }
      v22 = 14;
      goto LABEL_42;
    }
    v19 = SspiEncodeAuthIdentityAsStrings(
            *((PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)Pool2 + 1),
            (PCWSTR *)&DataBuffer,
            (PCWSTR *)&v26,
            (PCWSTR *)&v27);
    v20 = MapSecurityError(v19);
    v14 = v20;
    if ( v20 >= 0 )
    {
      v23 = -1;
      if ( DataBuffer )
      {
        v24 = -1;
        do
          ++v24;
        while ( *((_WORD *)DataBuffer + v24) );
        *((_QWORD *)&v29 + 1) = DataBuffer;
        WORD1(v29) = 2 * v24;
        v12 = &v29;
        LOWORD(v29) = 2 * v24;
      }
      if ( v26 )
      {
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)v26 + v25) );
        *((_QWORD *)&v30 + 1) = v26;
        WORD1(v30) = 2 * v25;
        v10 = &v30;
        LOWORD(v30) = 2 * v25;
      }
      if ( v27 )
      {
        do
          ++v23;
        while ( *((_WORD *)v27 + v23) );
        *((_QWORD *)&v31 + 1) = v27;
        WORD1(v31) = 2 * v23;
        v11 = &v31;
        LOWORD(v31) = 2 * v23;
      }
      goto LABEL_10;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v22 = 15;
LABEL_42:
      WPP_SF_Dd(v21->AttachedDevice, v22, &WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, (unsigned int)v20, v19);
    }
  }
  else
  {
    v14 = -1073741670;
  }
LABEL_18:
  if ( DataBuffer )
    SspiLocalFree(DataBuffer);
  if ( v26 )
    SspiLocalFree(v26);
  if ( v27 )
    SspiLocalFree(v27);
  if ( v14 < 0 )
  {
    if ( Pool2 )
      RxpFreeCredential(Pool2);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14006de60  mov     [rsp-38h+AuthIdentityLength], r8d
0x14006de65  mov     [rsp-38h+arg_0], rcx
0x14006de6a  push    rbp
0x14006de6b  push    rsi
0x14006de6c  push    rdi
0x14006de6d  push    r12
0x14006de6f  push    r13
0x14006de71  push    r14
0x14006de73  push    r15
0x14006de75  mov     rbp, rsp
0x14006de78  sub     rsp, 80h
0x14006de7f  mov     r12, [rbp+SecurityDescriptor]
0x14006de86  mov     rax, rcx
0x14006de89  mov     r13, [rbp+arg_28]
0x14006de8d  xor     ecx, ecx
0x14006de8f  mov     r15, [rbp+arg_20]
0x14006de93  xorps   xmm0, xmm0
0x14006de96  mov     [rbp+DataBuffer], rcx
0x14006de9a  xorps   xmm1, xmm1
0x14006de9d  mov     [rax], rcx
0x14006dea0  mov     r14, r9
0x14006dea3  mov     [rbp+var_50], rcx
0x14006dea7  mov     rsi, rdx
0x14006deaa  mov     [rbp+var_48], rcx
0x14006deae  mov     edi, ecx
0x14006deb0  movups  [rbp+var_38], xmm0
0x14006deb4  movups  [rbp+var_28], xmm1
0x14006deb8  movups  [rbp+var_18], xmm0
0x14006debc  test    rdx, rdx
0x14006debf  jnz     short loc_14006DEDA
0x14006dec1  test    r9, r9
0x14006dec4  jnz     short loc_14006DEDA
0x14006dec6  test    r15, r15
0x14006dec9  jnz     short loc_14006DEDA
0x14006decb  test    r13, r13
0x14006dece  jnz     short loc_14006DEDA
0x14006ded0  cmp     [rbp+arg_30], rcx
0x14006ded4  jz      loc_14006E03B
0x14006deda  mov     [rsp+80h+arg_18], rbx
0x14006dee2  mov     eax, ecx
0x14006dee4  test    r12, r12
0x14006dee7  jnz     loc_14006E052
0x14006deed  mov     eax, eax
0x14006deef  mov     ecx, 42h ; 'B'
0x14006def4  mov     r8d, 72437852h
0x14006defa  mov     [rbp+Size], rax
0x14006defe  lea     rdx, [rax+48h]
0x14006df02  call    cs:__imp_ExAllocatePool2
0x14006df09  nop     dword ptr [rax+rax+00h]
0x14006df0e  mov     rbx, rax
0x14006df11  test    rax, rax
0x14006df14  jz      loc_14006E02D
0x14006df1a  xor     eax, eax
0x14006df1c  mov     [rbx+8], rax
0x14006df20  mov     [rbx+10h], rax
0x14006df24  mov     [rbx+18h], rax
0x14006df28  mov     [rbx+20h], rax
0x14006df2c  mov     [rbx+28h], rax
0x14006df30  mov     [rbx+30h], rax
0x14006df34  mov     [rbx+38h], rax
0x14006df38  mov     [rbx+40h], rax
0x14006df3c  mov     dword ptr [rbx], 48EB60h
0x14006df42  mov     dword ptr [rbx+4], 1
0x14006df49  test    rsi, rsi
0x14006df4c  jnz     loc_14007F05E
0x14006df52  lea     rdx, [rbx+10h]
0x14006df56  mov     rcx, r14
0x14006df59  call    RxCloneUnicodeStringNonPagedPool
0x14006df5e  test    al, al
0x14006df60  jz      loc_14006E034
0x14006df66  lea     rdx, [rbx+18h]
0x14006df6a  mov     rcx, r15
0x14006df6d  call    RxCloneUnicodeStringNonPagedPool
0x14006df72  test    al, al
0x14006df74  jz      loc_14006E066
0x14006df7a  lea     rdx, [rbx+20h]
0x14006df7e  mov     rcx, r13
0x14006df81  call    RxCloneUnicodeStringNonPagedPool
0x14006df86  test    al, al
0x14006df88  jz      loc_14006E010
0x14006df8e  mov     rcx, [rbp+arg_30]
0x14006df92  lea     rdx, [rbx+28h]
0x14006df96  call    RxCloneUnicodeStringNonPagedPool
0x14006df9b  test    al, al
0x14006df9d  jz      short loc_14006E009
0x14006df9f  mov     rcx, [rbp+arg_38]
0x14006dfa3  lea     rdx, [rbx+30h]
0x14006dfa7  call    RxCloneUnicodeStringNonPagedPool
0x14006dfac  test    al, al
0x14006dfae  jz      short loc_14006E017
0x14006dfb0  test    r12, r12
0x14006dfb3  jnz     loc_14006E070
0x14006dfb9  mov     rax, [rbp+arg_0]
0x14006dfbd  mov     [rax], rbx
0x14006dfc0  mov     rcx, [rbp+DataBuffer]; DataBuffer
0x14006dfc4  test    rcx, rcx
0x14006dfc7  jnz     loc_14006E089
0x14006dfcd  mov     rcx, [rbp+var_50]; DataBuffer
0x14006dfd1  test    rcx, rcx
0x14006dfd4  jnz     loc_14006E09A
0x14006dfda  mov     rcx, [rbp+var_48]; DataBuffer
0x14006dfde  test    rcx, rcx
0x14006dfe1  jnz     loc_14006E0AB
0x14006dfe7  test    edi, edi
0x14006dfe9  js      short loc_14006E01E
0x14006dfeb  mov     rbx, [rsp+80h+arg_18]
0x14006dff3  mov     eax, edi
0x14006dff5  add     rsp, 80h
0x14006dffc  pop     r15
0x14006dffe  pop     r14
0x14006e000  pop     r13
0x14006e002  pop     r12
0x14006e004  pop     rdi
0x14006e005  pop     rsi
0x14006e006  pop     rbp
0x14006e007  retn
0x14006e009  mov     edi, 0C000009Ah
0x14006e00e  jmp     short loc_14006DFC0
0x14006e010  mov     edi, 0C000009Ah
0x14006e015  jmp     short loc_14006DFC0
0x14006e017  mov     edi, 0C000009Ah
0x14006e01c  jmp     short loc_14006DFC0
0x14006e01e  test    rbx, rbx
0x14006e021  jz      short loc_14006DFEB
0x14006e023  mov     rcx, rbx; P
0x14006e026  call    RxpFreeCredential
0x14006e02b  jmp     short loc_14006DFEB
0x14006e02d  mov     edi, 0C000009Ah
0x14006e032  jmp     short loc_14006DFC0
0x14006e034  mov     edi, 0C000009Ah
0x14006e039  jmp     short loc_14006DFC0
0x14006e03b  cmp     [rbp+arg_38], rcx
0x14006e03f  jnz     loc_14006DEDA
0x14006e045  test    r12, r12
0x14006e048  jnz     loc_14006DEDA
0x14006e04e  mov     eax, ecx
0x14006e050  jmp     short loc_14006DFF5
0x14006e052  mov     rcx, r12; SecurityDescriptor
0x14006e055  call    cs:__imp_RtlLengthSecurityDescriptor
0x14006e05c  nop     dword ptr [rax+rax+00h]
0x14006e061  jmp     loc_14006DEED
0x14006e066  mov     edi, 0C000009Ah
0x14006e06b  jmp     loc_14006DFC0
0x14006e070  mov     r8, [rbp+Size]; Size
0x14006e074  lea     rcx, [rbx+48h]; void *
0x14006e078  mov     rdx, r12; Src
0x14006e07b  mov     [rbx+38h], rcx
0x14006e07f  call    memmove
0x14006e084  jmp     loc_14006DFB9
0x14006e089  call    cs:__imp_SspiLocalFree
0x14006e090  nop     dword ptr [rax+rax+00h]
0x14006e095  jmp     loc_14006DFCD
0x14006e09a  call    cs:__imp_SspiLocalFree
0x14006e0a1  nop     dword ptr [rax+rax+00h]
0x14006e0a6  jmp     loc_14006DFDA
0x14006e0ab  call    cs:__imp_SspiLocalFree
0x14006e0b2  nop     dword ptr [rax+rax+00h]
0x14006e0b7  jmp     loc_14006DFE7
0x14007f05e  mov     ecx, [rbp+AuthIdentityLength]; AuthIdentityLength
0x14007f061  lea     r8, [rbx+8]; ppAuthIdentity
0x14007f065  mov     rdx, rsi; AuthIdentityByteArray
0x14007f068  call    cs:__imp_SspiUnmarshalAuthIdentity
0x14007f06f  nop     dword ptr [rax+rax+00h]
0x14007f074  mov     ecx, eax; SecStatus
0x14007f076  mov     esi, eax
0x14007f078  call    cs:__imp_MapSecurityError
0x14007f07f  nop     dword ptr [rax+rax+00h]
0x14007f084  mov     edi, eax
0x14007f086  test    eax, eax
0x14007f088  jns     short loc_14007F0E0
0x14007f08a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f091  lea     rdx, WPP_GLOBAL_Control
0x14007f098  cmp     rcx, rdx
0x14007f09b  jz      loc_14006DFC0
0x14007f0a1  mov     edx, [rcx+2Ch]
0x14007f0a4  test    dl, 1
0x14007f0a7  jz      loc_14006DFC0
0x14007f0ad  cmp     byte ptr [rcx+29h], 1
0x14007f0b1  jb      loc_14006DFC0
0x14007f0b7  mov     edx, 0Eh
0x14007f0bc  jmp     short loc_14007F0C3
0x14007f0be  mov     edx, 0Fh
0x14007f0c3  mov     rcx, [rcx+18h]
0x14007f0c7  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14007f0ce  mov     r9d, eax
0x14007f0d1  mov     [rsp+80h+var_60], esi
0x14007f0d5  call    WPP_SF_Dd
0x14007f0da  nop
0x14007f0db  jmp     loc_14006DFC0
0x14007f0e0  mov     rcx, [rbx+8]; pAuthIdentity
0x14007f0e4  lea     r9, [rbp+var_48]; ppszPackedCredentialsString
0x14007f0e8  lea     r8, [rbp+var_50]; ppszDomainName
0x14007f0ec  lea     rdx, [rbp+DataBuffer]; ppszUserName
0x14007f0f0  call    cs:__imp_SspiEncodeAuthIdentityAsStrings
0x14007f0f7  nop     dword ptr [rax+rax+00h]
0x14007f0fc  mov     ecx, eax; SecStatus
0x14007f0fe  mov     esi, eax
0x14007f100  call    cs:__imp_MapSecurityError
0x14007f107  nop     dword ptr [rax+rax+00h]
0x14007f10c  mov     edi, eax
0x14007f10e  test    eax, eax
0x14007f110  jns     short loc_14007F144
0x14007f112  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f119  lea     rdx, WPP_GLOBAL_Control
0x14007f120  cmp     rcx, rdx
0x14007f123  jz      loc_14006DFC0
0x14007f129  mov     edx, [rcx+2Ch]
0x14007f12c  test    dl, 1
0x14007f12f  jz      loc_14006DFC0
0x14007f135  cmp     byte ptr [rcx+29h], 1
0x14007f139  jb      loc_14006DFC0
0x14007f13f  jmp     loc_14007F0BE
0x14007f144  mov     rdx, [rbp+DataBuffer]
0x14007f148  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14007f14f  test    rdx, rdx
0x14007f152  jz      short loc_14007F174
0x14007f154  mov     rcx, rax
0x14007f157  inc     rcx
0x14007f15a  cmp     word ptr [rdx+rcx*2], 0
0x14007f15f  jnz     short loc_14007F157
0x14007f161  add     cx, cx
0x14007f164  mov     qword ptr [rbp+var_38+8], rdx
0x14007f168  mov     word ptr [rbp+var_38+2], cx
0x14007f16c  lea     r14, [rbp+var_38]
0x14007f170  mov     word ptr [rbp+var_38], cx
0x14007f174  mov     rdx, [rbp+var_50]
0x14007f178  test    rdx, rdx
0x14007f17b  jz      short loc_14007F19D
0x14007f17d  mov     rcx, rax
0x14007f180  inc     rcx
0x14007f183  cmp     word ptr [rdx+rcx*2], 0
0x14007f188  jnz     short loc_14007F180
0x14007f18a  add     cx, cx
0x14007f18d  mov     qword ptr [rbp+var_28+8], rdx
0x14007f191  mov     word ptr [rbp+var_28+2], cx
0x14007f195  lea     r13, [rbp+var_28]
0x14007f199  mov     word ptr [rbp+var_28], cx
0x14007f19d  mov     rcx, [rbp+var_48]
0x14007f1a1  test    rcx, rcx
0x14007f1a4  jz      loc_14006DF52
0x14007f1aa  inc     rax
0x14007f1ad  cmp     word ptr [rcx+rax*2], 0
0x14007f1b2  jnz     short loc_14007F1AA
0x14007f1b4  add     ax, ax
0x14007f1b7  mov     qword ptr [rbp+var_18+8], rcx
0x14007f1bb  mov     word ptr [rbp+var_18+2], ax
0x14007f1bf  lea     r15, [rbp+var_18]
0x14007f1c3  mov     word ptr [rbp+var_18], ax
0x14007f1c7  jmp     loc_14006DF52
```
