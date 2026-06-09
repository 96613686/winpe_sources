# Smb2ComputeIncomingSignatureInitial

- ea: `0x14000d210`
- end: `0x14000d4d6`
- name: `Smb2ComputeIncomingSignatureInitial`
- size: `710`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, ULONG)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000d140`
- `0x140053130`

## callees

- `0x14000d210`
- `0x140029764`
- `0x14002a1dc`
- `0x14002a6a8`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000d366`
- `ntoskrnl!ExAllocatePool2` at `0x14000d366`
- `ksecdd!BCryptHashData` at `0x14000d312`
- `ksecdd!BCryptHashData` at `0x14000d312`
- `ksecdd!BCryptDuplicateHash` at `0x14000d296`
- `ksecdd!BCryptDuplicateHash` at `0x14000d296`
- `ksecdd!BCryptDestroyHash` at `0x14000d262`
- `ksecdd!BCryptDestroyHash` at `0x14000d262`
- `mrxsmb!SmbCryptoSigningAlgRequireIV` at `0x14000d2af`
- `mrxsmb!SmbCryptoSigningAlgRequireIV` at `0x14000d2af`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x140039a16`
- `mrxsmb!SmbCseDestroyHashHandle` at `0x140039a16`
- `mrxsmb!SmbCryptoCalculateAndSetIV` at `0x14000d2da`
- `mrxsmb!SmbCryptoCalculateAndSetIV` at `0x14000d2da`

## pseudocode

```c
NTSTATUS __fastcall Smb2ComputeIncomingSignatureInitial(__int64 a1, __int64 a2, __int64 a3, ULONG a4)
{
  void *v5; // rcx
  unsigned int v9; // r14d
  NTSTATUS v10; // eax
  int v11; // edi
  __int64 v12; // r8
  NTSTATUS result; // eax
  __int64 Pool2; // rax
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx

  v5 = *(void **)(a1 + 792);
  v9 = *(_DWORD *)(*(_QWORD *)(a2 + 392) + 600LL);
  if ( v5 )
  {
    if ( !*(_QWORD *)(a1 + 808) )
      __int2c();
    BCryptDestroyHash(v5);
    *(_QWORD *)(a1 + 792) = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56),
        a1);
    }
    Pool2 = ExAllocatePool2(66, *(unsigned int *)(a2 + 512), 1834184520);
    *(_QWORD *)(a1 + 808) = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741670;
      goto LABEL_14;
    }
    *(_DWORD *)(a1 + 800) = *(_DWORD *)(a2 + 516);
    *(_DWORD *)(a1 + 816) = *(_DWORD *)(a2 + 512);
  }
  v10 = BCryptDuplicateHash(
          *(BCRYPT_HASH_HANDLE *)(a2 + 496),
          (BCRYPT_HASH_HANDLE *)(a1 + 792),
          *(PUCHAR *)(a1 + 808),
          *(_DWORD *)(a1 + 816),
          0);
  v11 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        *(_QWORD *)(a1 + 56),
        a1,
        v10);
    }
    goto LABEL_14;
  }
  if ( (unsigned __int8)SmbCryptoSigningAlgRequireIV(v9) )
  {
    LOBYTE(v12) = 1;
    v11 = SmbCryptoCalculateAndSetIV(2, *(_QWORD *)(a3 + 24), v12, 0, *(_QWORD *)(a1 + 792));
    if ( v11 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || !BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        goto LABEL_14;
      }
      v16 = 29;
      goto LABEL_33;
    }
  }
  *(_OWORD *)(a1 + 820) = *(_OWORD *)(a3 + 48);
  *(_OWORD *)(a3 + 48) = 0;
  result = BCryptHashData(*(BCRYPT_HASH_HANDLE *)(a1 + 792), (PUCHAR)a3, a4, 0);
  v11 = result;
  if ( result >= 0 )
  {
    *(_OWORD *)(a3 + 48) = *(_OWORD *)(a1 + 820);
    return result;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v16 = 30;
LABEL_33:
    WPP_SF_qq(v15->AttachedDevice, v16, WPP_60db1590be613abca80435fd5891bee8_Traceguids, *(_QWORD *)(a1 + 56), a1);
  }
LABEL_14:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_60db1590be613abca80435fd5891bee8_Traceguids,
        (unsigned int)v11);
  }
  SmbCseDestroyHashHandle(a1);
  return v11;
}

```

## disassembly

```asm
0x14000d210  push    rbx
0x14000d212  push    rbp
0x14000d213  push    rsi
0x14000d214  push    rdi
0x14000d215  push    r12
0x14000d217  push    r13
0x14000d219  push    r14
0x14000d21b  push    r15
0x14000d21d  sub     rsp, 38h
0x14000d221  mov     rax, [rdx+188h]
0x14000d228  lea     r13, WPP_GLOBAL_Control
0x14000d22f  mov     rbx, rcx
0x14000d232  xor     r12d, r12d
0x14000d235  mov     rcx, [rcx+318h]; hHash
0x14000d23c  mov     r15d, r9d
0x14000d23f  mov     rbp, r8
0x14000d242  mov     rdi, rdx
0x14000d245  mov     r14d, [rax+258h]
0x14000d24c  test    rcx, rcx
0x14000d24f  jz      loc_14000D345
0x14000d255  cmp     [rbx+328h], r12
0x14000d25c  jz      loc_14000D459
0x14000d262  call    cs:__imp_BCryptDestroyHash
0x14000d269  nop     dword ptr [rax+rax+00h]
0x14000d26e  mov     [rbx+318h], r12
0x14000d275  mov     r9d, [rbx+330h]; cbHashObject
0x14000d27c  lea     rdx, [rbx+318h]; phNewHash
0x14000d283  mov     r8, [rbx+328h]; pbHashObject
0x14000d28a  mov     rcx, [rdi+1F0h]; hHash
0x14000d291  mov     [rsp+78h+dwFlags], r12d; dwFlags
0x14000d296  call    cs:__imp_BCryptDuplicateHash
0x14000d29d  nop     dword ptr [rax+rax+00h]
0x14000d2a2  mov     edi, eax
0x14000d2a4  test    eax, eax
0x14000d2a6  js      loc_14000D39F
0x14000d2ac  mov     ecx, r14d
0x14000d2af  call    cs:__imp_SmbCryptoSigningAlgRequireIV
0x14000d2b6  nop     dword ptr [rax+rax+00h]
0x14000d2bb  test    al, al
0x14000d2bd  jz      short loc_14000D2F0
0x14000d2bf  mov     rax, [rbx+318h]
0x14000d2c6  xor     r9d, r9d
0x14000d2c9  mov     rdx, [rbp+18h]
0x14000d2cd  mov     r8b, 1
0x14000d2d0  mov     ecx, 2
0x14000d2d5  mov     qword ptr [rsp+78h+dwFlags], rax
0x14000d2da  call    cs:__imp_SmbCryptoCalculateAndSetIV
0x14000d2e1  nop     dword ptr [rax+rax+00h]
0x14000d2e6  mov     edi, eax
0x14000d2e8  test    eax, eax
0x14000d2ea  js      loc_14000D42A
0x14000d2f0  movups  xmm0, xmmword ptr [rbp+30h]
0x14000d2f4  xor     r9d, r9d; dwFlags
0x14000d2f7  mov     r8d, r15d; cbInput
0x14000d2fa  xorps   xmm1, xmm1
0x14000d2fd  mov     rdx, rbp; pbInput
0x14000d300  movups  xmmword ptr [rbx+334h], xmm0
0x14000d307  movups  xmmword ptr [rbp+30h], xmm1
0x14000d30b  mov     rcx, [rbx+318h]; hHash
0x14000d312  call    cs:__imp_BCryptHashData
0x14000d319  nop     dword ptr [rax+rax+00h]
0x14000d31e  mov     edi, eax
0x14000d320  test    eax, eax
0x14000d322  js      loc_14000D4A7
0x14000d328  movups  xmm0, xmmword ptr [rbx+334h]
0x14000d32f  movups  xmmword ptr [rbp+30h], xmm0
0x14000d333  add     rsp, 38h
0x14000d337  pop     r15
0x14000d339  pop     r14
0x14000d33b  pop     r13
0x14000d33d  pop     r12
0x14000d33f  pop     rdi
0x14000d340  pop     rsi
0x14000d341  pop     rbp
0x14000d342  pop     rbx
0x14000d343  retn
0x14000d345  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d34c  cmp     rcx, r13
0x14000d34f  jnz     loc_14000D3F2
0x14000d355  mov     edx, [rdi+200h]
0x14000d35b  mov     ecx, 42h ; 'B'
0x14000d360  mov     r8d, 6D536F48h
0x14000d366  call    cs:__imp_ExAllocatePool2
0x14000d36d  nop     dword ptr [rax+rax+00h]
0x14000d372  mov     [rbx+328h], rax
0x14000d379  test    rax, rax
0x14000d37c  jz      loc_14000D460
0x14000d382  mov     eax, [rdi+204h]
0x14000d388  mov     [rbx+320h], eax
0x14000d38e  mov     eax, [rdi+200h]
0x14000d394  mov     [rbx+330h], eax
0x14000d39a  jmp     loc_14000D275
0x14000d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3a6  cmp     rcx, r13
0x14000d3a9  jnz     loc_14000D46A
0x14000d3af  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d3b6  cmp     rcx, r13
0x14000d3b9  jz      loc_140039A13
0x14000d3bf  mov     eax, [rcx+2Ch]
0x14000d3c2  test    al, 1
0x14000d3c4  jz      loc_140039A13
0x14000d3ca  cmp     byte ptr [rcx+29h], 1
0x14000d3ce  jb      loc_140039A13
0x14000d3d4  mov     rcx, [rcx+18h]
0x14000d3d8  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000d3df  mov     edx, 1Fh
0x14000d3e4  mov     r9d, edi
0x14000d3e7  call    WPP_SF_d
0x14000d3ec  nop
0x14000d3ed  jmp     loc_140039A13
0x14000d3f2  mov     eax, [rcx+2Ch]
0x14000d3f5  test    al, 8
0x14000d3f7  jz      loc_14000D355
0x14000d3fd  cmp     byte ptr [rcx+29h], 4
0x14000d401  jb      loc_14000D355
0x14000d407  mov     r9, [rbx+38h]
0x14000d40b  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000d412  mov     rcx, [rcx+18h]
0x14000d416  mov     edx, 1Bh
0x14000d41b  mov     qword ptr [rsp+78h+dwFlags], rbx
0x14000d420  call    WPP_SF_qq
0x14000d425  jmp     loc_14000D355
0x14000d42a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d431  cmp     rcx, r13
0x14000d434  jz      loc_14000D3AF
0x14000d43a  mov     eax, [rcx+2Ch]
0x14000d43d  test    al, 1
0x14000d43f  jz      loc_14000D3AF
0x14000d445  cmp     byte ptr [rcx+29h], 1
0x14000d449  jb      loc_14000D3AF
0x14000d44f  mov     edx, 1Dh
0x14000d454  jmp     loc_1400399F4
0x14000d459  int     2Ch; Windows NT - assertion failure
0x14000d45b  jmp     loc_14000D262
0x14000d460  mov     edi, 0C000009Ah
0x14000d465  jmp     loc_14000D3AF
0x14000d46a  mov     edx, [rcx+2Ch]
0x14000d46d  test    dl, 1
0x14000d470  jz      loc_14000D3AF
0x14000d476  cmp     byte ptr [rcx+29h], 1
0x14000d47a  jb      loc_14000D3AF
0x14000d480  mov     r9, [rbx+38h]
0x14000d484  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x14000d48b  mov     rcx, [rcx+18h]
0x14000d48f  mov     edx, 1Ch
0x14000d494  mov     [rsp+78h+var_50], eax
0x14000d498  mov     qword ptr [rsp+78h+dwFlags], rbx
0x14000d49d  call    WPP_SF_qqD
0x14000d4a2  jmp     loc_14000D3AF
0x14000d4a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d4ae  cmp     rcx, r13
0x14000d4b1  jz      loc_14000D3AF
0x14000d4b7  mov     eax, [rcx+2Ch]
0x14000d4ba  test    al, 1
0x14000d4bc  jz      loc_14000D3AF
0x14000d4c2  cmp     byte ptr [rcx+29h], 1
0x14000d4c6  jb      loc_14000D3AF
0x14000d4cc  mov     edx, 1Eh
0x14000d4d1  jmp     loc_1400399F4
0x1400399f4  mov     r9, [rbx+38h]
0x1400399f8  lea     r8, WPP_60db1590be613abca80435fd5891bee8_Traceguids
0x1400399ff  mov     rcx, [rcx+18h]
0x140039a03  mov     qword ptr [rsp+78h+dwFlags], rbx
0x140039a08  call    WPP_SF_qq
0x140039a0d  nop
0x140039a0e  jmp     loc_14000D3AF
0x140039a13  mov     rcx, rbx
0x140039a16  call    cs:__imp_SmbCseDestroyHashHandle
0x140039a1d  nop     dword ptr [rax+rax+00h]
0x140039a22  mov     eax, edi
0x140039a24  jmp     loc_14000D333
```
