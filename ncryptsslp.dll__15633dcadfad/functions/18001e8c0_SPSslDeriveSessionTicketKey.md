# SPSslDeriveSessionTicketKey

- ea: `0x18001e8c0`
- end: `0x18001ead1`
- name: `SPSslDeriveSessionTicketKey`
- size: `529`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180003ef0`
- `0x1800068e0`
- `0x180007940`
- `0x18000b654`
- `0x18001e8c0`
- `0x180020d10`
- `0x180021104`

## string_xrefs

- `0x18001e8f0`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x18001ea95`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall SPSslDeriveSessionTicketKey(
        __int64 a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4,
        UCHAR *a5,
        ULONG a6,
        _QWORD *a7,
        int a8)
{
  int v9; // edx
  int v10; // r9d
  unsigned int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // rcx
  int NcryptObjectSizes; // eax
  int v15; // ebx
  unsigned int v16; // esi
  __int64 v17; // rax
  _BYTE *v18; // rdi
  __int64 v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rax
  _BYTE *v24; // rcx
  UCHAR pbOutput[4]; // [rsp+50h] [rbp-38h] BYREF
  int v27; // [rsp+54h] [rbp-34h]

  if ( !SslpValidateProvHandle(a1) )
  {
    v11 = -2146893786;
    v12 = 7094;
    v13 = 2148073510LL;
LABEL_3:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v12);
    return v11;
  }
  if ( a7 && a3 && a5 && a6 )
  {
    if ( v9 || v10 != 16 )
    {
      v11 = -2146893785;
      v12 = 7112;
      v13 = 2148073511LL;
      goto LABEL_3;
    }
    if ( a8 )
    {
      v11 = -2146893815;
      v12 = 7119;
      v13 = 2148073481LL;
      goto LABEL_3;
    }
    v27 = 0;
    *(_DWORD *)pbOutput = 0;
    NcryptObjectSizes = GetNcryptObjectSizes(pbOutput);
    v11 = NcryptObjectSizes;
    if ( NcryptObjectSizes < 0 )
    {
      v12 = 7135;
      v13 = (unsigned int)NcryptObjectSizes;
      goto LABEL_3;
    }
    v15 = v27;
    v16 = v27 + *(_DWORD *)pbOutput + 88;
    v17 = SafeAllocaAllocateFromHeap(v16);
    v18 = (_BYTE *)v17;
    if ( v17 )
    {
      *(_QWORD *)(v17 + 64) = v17 + 72;
      *(_DWORD *)(v17 + 56) = 16;
      *(_DWORD *)v17 = v16;
      *(_QWORD *)(v17 + 4) = 1936944185;
      *(_QWORD *)(v17 + 32) = v17 + 88;
      *(_DWORD *)(v17 + 24) = *(_DWORD *)pbOutput;
      v21 = *(unsigned int *)pbOutput;
      *(_DWORD *)(v17 + 40) = v15;
      *(_QWORD *)(v17 + 48) = v17 + v21 + 88;
      *(_OWORD *)(v17 + 72) = *a3;
      v22 = DeriveProtectionHandlesFromKeyMaterial(
              *(_QWORD *)(v17 + 64),
              *(_DWORD *)(v17 + 56),
              a5,
              a6,
              (BCRYPT_KEY_HANDLE *)(v17 + 16),
              *(UCHAR **)(v17 + 32),
              *(_DWORD *)(v17 + 24),
              *(_BYTE **)(v17 + 48),
              *(_DWORD *)(v17 + 40));
      v11 = v22;
      if ( v22 >= 0 )
      {
        *a7 = v18;
        return v11;
      }
      v19 = (unsigned int)v22;
      v20 = 7172;
    }
    else
    {
      v11 = -2146893810;
      v19 = 2148073486LL;
      v20 = 7144;
    }
  }
  else
  {
    v18 = 0;
    v11 = -2146893785;
    v16 = 0;
    v19 = 2148073511LL;
    v20 = 7104;
  }
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c", v20);
  if ( v18 )
  {
    v23 = v16;
    v24 = v18;
    if ( v16 )
    {
      do
      {
        *v24++ = 0;
        --v23;
      }
      while ( v23 );
    }
    MSCryptFree(v18);
  }
  return v11;
}

```

## disassembly

```asm
0x18001e8c0  push    rbx
0x18001e8c2  push    rsi
0x18001e8c3  push    rdi
0x18001e8c4  push    r12
0x18001e8c6  push    r14
0x18001e8c8  sub     rsp, 60h
0x18001e8cc  mov     r12, r8
0x18001e8cf  call    SslpValidateProvHandle
0x18001e8d4  test    rax, rax
0x18001e8d7  jnz     short loc_18001E901
0x18001e8d9  mov     ebx, 80090026h
0x18001e8de  mov     r9d, 1BB6h
0x18001e8e4  mov     ecx, 80090026h
0x18001e8e9  lea     rdx, aStatus; "Status"
0x18001e8f0  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001e8f7  call    DebugTraceError
0x18001e8fc  jmp     loc_18001EAC3
0x18001e901  mov     r14, [rsp+88h+arg_30]
0x18001e909  test    r14, r14
0x18001e90c  jz      loc_18001EA7A
0x18001e912  test    r12, r12
0x18001e915  jz      loc_18001EA7A
0x18001e91b  cmp     [rsp+88h+arg_20], 0
0x18001e924  jz      loc_18001EA7A
0x18001e92a  cmp     [rsp+88h+arg_28], 0
0x18001e932  jz      loc_18001EA7A
0x18001e938  test    edx, edx
0x18001e93a  jnz     loc_18001EA65
0x18001e940  cmp     r9d, 10h
0x18001e944  jnz     loc_18001EA65
0x18001e94a  cmp     [rsp+88h+arg_38], edx
0x18001e951  jz      short loc_18001E965
0x18001e953  mov     ebx, 80090009h
0x18001e958  mov     r9d, 1BCFh
0x18001e95e  mov     ecx, 80090009h
0x18001e963  jmp     short loc_18001E8E9
0x18001e965  lea     rdx, [rsp+88h+var_34]
0x18001e96a  mov     [rsp+88h+var_34], 0
0x18001e972  lea     rcx, [rsp+88h+pbOutput]; pbOutput
0x18001e977  mov     dword ptr [rsp+88h+pbOutput], 0
0x18001e97f  call    GetNcryptObjectSizes
0x18001e984  mov     ebx, eax
0x18001e986  test    eax, eax
0x18001e988  jns     short loc_18001E997
0x18001e98a  mov     r9d, 1BDFh
0x18001e990  mov     ecx, eax
0x18001e992  jmp     loc_18001E8E9
0x18001e997  mov     esi, dword ptr [rsp+88h+pbOutput]
0x18001e99b  mov     ebx, [rsp+88h+var_34]
0x18001e99f  add     esi, 58h ; 'X'
0x18001e9a2  add     esi, ebx
0x18001e9a4  mov     ecx, esi
0x18001e9a6  call    SafeAllocaAllocateFromHeap
0x18001e9ab  mov     rdi, rax
0x18001e9ae  test    rax, rax
0x18001e9b1  jnz     short loc_18001E9C8
0x18001e9b3  mov     ebx, 8009000Eh
0x18001e9b8  mov     ecx, 8009000Eh
0x18001e9bd  mov     r9d, 1BE8h
0x18001e9c3  jmp     loc_18001EA8E
0x18001e9c8  mov     r9d, [rsp+88h+arg_28]
0x18001e9d0  lea     rdx, [rax+48h]
0x18001e9d4  mov     r8, [rsp+88h+arg_20]
0x18001e9dc  lea     r10, [rax+10h]
0x18001e9e0  mov     [rax+40h], rdx
0x18001e9e4  mov     dword ptr [rax+38h], 10h
0x18001e9eb  mov     [rax], esi
0x18001e9ed  mov     qword ptr [rax+4], 73736C39h
0x18001e9f5  lea     rax, [r10+48h]
0x18001e9f9  mov     [rdi+20h], rax
0x18001e9fd  mov     eax, dword ptr [rsp+88h+pbOutput]
0x18001ea01  mov     [rdi+18h], eax
0x18001ea04  mov     ecx, dword ptr [rsp+88h+pbOutput]
0x18001ea08  mov     [rdi+28h], ebx
0x18001ea0b  add     rcx, 58h ; 'X'
0x18001ea0f  add     rcx, rdi
0x18001ea12  mov     [rdi+30h], rcx
0x18001ea16  movups  xmm0, xmmword ptr [r12]
0x18001ea1b  movdqu  xmmword ptr [rdx], xmm0
0x18001ea1f  mov     eax, [rdi+28h]
0x18001ea22  mov     edx, [rdi+38h]
0x18001ea25  mov     rcx, [rdi+40h]
0x18001ea29  mov     [rsp+88h+var_48], eax
0x18001ea2d  mov     rax, [rdi+30h]
0x18001ea31  mov     [rsp+88h+var_50], rax
0x18001ea36  mov     eax, [rdi+18h]
0x18001ea39  mov     [rsp+88h+var_58], eax
0x18001ea3d  mov     rax, [rdi+20h]
0x18001ea41  mov     [rsp+88h+var_60], rax
0x18001ea46  mov     [rsp+88h+var_68], r10
0x18001ea4b  call    DeriveProtectionHandlesFromKeyMaterial
0x18001ea50  mov     ebx, eax
0x18001ea52  test    eax, eax
0x18001ea54  jns     short loc_18001EA60
0x18001ea56  mov     ecx, eax
0x18001ea58  mov     r9d, 1C04h
0x18001ea5e  jmp     short loc_18001EA8E
0x18001ea60  mov     [r14], rdi
0x18001ea63  jmp     short loc_18001EAC3
0x18001ea65  mov     ebx, 80090027h
0x18001ea6a  mov     r9d, 1BC8h
0x18001ea70  mov     ecx, 80090027h
0x18001ea75  jmp     loc_18001E8E9
0x18001ea7a  xor     edi, edi
0x18001ea7c  mov     ebx, 80090027h
0x18001ea81  xor     esi, esi
0x18001ea83  mov     ecx, 80090027h
0x18001ea88  mov     r9d, 1BC0h
0x18001ea8e  lea     rdx, aStatus; "Status"
0x18001ea95  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ea9c  call    DebugTraceError
0x18001eaa1  test    rdi, rdi
0x18001eaa4  jz      short loc_18001EAC3
0x18001eaa6  mov     eax, esi
0x18001eaa8  mov     rcx, rdi
0x18001eaab  test    esi, esi
0x18001eaad  jz      short loc_18001EABB
0x18001eaaf  mov     byte ptr [rcx], 0
0x18001eab2  inc     rcx
0x18001eab5  sub     rax, 1
0x18001eab9  jnz     short loc_18001EAAF
0x18001eabb  mov     rcx, rdi
0x18001eabe  call    MSCryptFree
0x18001eac3  mov     eax, ebx
0x18001eac5  add     rsp, 60h
0x18001eac9  pop     r14
0x18001eacb  pop     r12
0x18001eacd  pop     rdi
0x18001eace  pop     rsi
0x18001eacf  pop     rbx
0x18001ead0  retn
```
