# FCpEncStreamStart

- ea: `0x14000d1a8`
- end: `0x14000d36a`
- name: `FCpEncStreamStart`
- size: `450`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140011fe0`

## callees

- `0x140002fd0`
- `0x14000d13c`
- `0x14000d1a8`
- `0x14000d9a8`
- `0x14000ea4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d335`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001397b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d335`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001397b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d1f1`
- `ntoskrnl!ExAllocatePool2` at `0x14000d2a7`
- `ntoskrnl!ExAllocatePool2` at `0x14000d1f1`
- `ntoskrnl!ExAllocatePool2` at `0x14000d2a7`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14000d2e0`
- `ksecdd!BCryptGenerateSymmetricKey` at `0x14000d2e0`

## pseudocode

```c
__int64 __fastcall FCpEncStreamStart(__int64 a1, const wchar_t *a2, unsigned int a3, __int64 a4)
{
  __int64 v8; // r12
  __int64 v9; // rdx
  void *pbSecret; // rdi
  UCHAR *Pool2; // r8
  int ChamberProfileKey; // ebx
  __int64 v13; // rcx
  int v14; // r9d
  const EVENT_DESCRIPTOR *v15; // rdx
  NTSTATUS SymmetricKey; // eax
  __int64 v17; // rcx
  _BYTE *v18; // rax
  unsigned int v20; // [rsp+48h] [rbp-40h]

  v8 = *(unsigned int *)(a1 + 8);
  *(_DWORD *)(a4 + 16) = v8;
  pbSecret = (void *)ExAllocatePool2(64, *(unsigned int *)(a1 + 20), 1917010758);
  if ( !pbSecret )
    goto LABEL_2;
  v13 = *(unsigned int *)(a1 + 20);
  v20 = *(_DWORD *)(a1 + 20);
  if ( a2 && a3 - 1 <= 1 )
  {
    ChamberProfileKey = StSecpGetChamberProfileKey(a2, a3, pbSecret, (unsigned int)v13);
    if ( ChamberProfileKey == -1073741772 )
      ChamberProfileKey = StSecpDeriveChamberProfileKey(a2, a3, pbSecret, v20);
  }
  else
  {
    ChamberProfileKey = -1073741811;
  }
  if ( ChamberProfileKey < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) == 0 )
      goto LABEL_16;
    v14 = ChamberProfileKey;
    v15 = (const EVENT_DESCRIPTOR *)&GetChamberProfileEncryptionKeyFailure;
    goto LABEL_15;
  }
  Pool2 = (UCHAR *)ExAllocatePool2(64, v8, 1917010758);
  *(_QWORD *)(a4 + 8) = Pool2;
  if ( !Pool2 )
  {
LABEL_2:
    ChamberProfileKey = -1073741670;
    goto LABEL_16;
  }
  SymmetricKey = BCryptGenerateSymmetricKey(
                   *(BCRYPT_ALG_HANDLE *)a1,
                   (BCRYPT_KEY_HANDLE *)a4,
                   Pool2,
                   v8,
                   (PUCHAR)pbSecret,
                   *(_DWORD *)(a1 + 20),
                   0);
  ChamberProfileKey = SymmetricKey;
  if ( SymmetricKey < 0 )
  {
    v13 = (unsigned int)Microsoft_Windows_FileCryptEnableBits;
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
    {
      v14 = SymmetricKey;
      v15 = (const EVENT_DESCRIPTOR *)&GenerateSymmetricKeyFailure;
LABEL_15:
      McTemplateK0d_EtwWriteTransfer(v13, v15, (__int64)Pool2, v14);
    }
  }
LABEL_16:
  if ( pbSecret )
  {
    v17 = *(unsigned int *)(a1 + 20);
    v18 = pbSecret;
    if ( *(_DWORD *)(a1 + 20) )
    {
      do
      {
        *v18++ = 0;
        --v17;
      }
      while ( v17 );
    }
    ExFreePoolWithTag(pbSecret, 0x72434346u);
  }
  if ( ChamberProfileKey < 0 )
    FCpEncStreamCleanup(a4, v9, Pool2);
  return (unsigned int)ChamberProfileKey;
}

```

## disassembly

```asm
0x14000d1a8  mov     rax, rsp
0x14000d1ab  mov     [rax+10h], rbx
0x14000d1af  mov     [rax+18h], rsi
0x14000d1b3  mov     [rax+20h], r9
0x14000d1b7  mov     [rax+8], rcx
0x14000d1bb  push    rdi
0x14000d1bc  push    r12
0x14000d1be  push    r13
0x14000d1c0  push    r14
0x14000d1c2  push    r15
0x14000d1c4  sub     rsp, 60h
0x14000d1c8  mov     r14, r9
0x14000d1cb  mov     r13d, r8d
0x14000d1ce  mov     r15, rdx
0x14000d1d1  mov     rsi, rcx
0x14000d1d4  xor     ebx, ebx
0x14000d1d6  mov     [rax-48h], ebx
0x14000d1d9  mov     [rax-38h], rbx
0x14000d1dd  mov     r12d, [rcx+8]
0x14000d1e1  mov     [r9+10h], r12d
0x14000d1e5  mov     edx, [rcx+14h]
0x14000d1e8  lea     ecx, [rbx+40h]
0x14000d1eb  mov     r8d, 72434346h
0x14000d1f1  call    cs:__imp_ExAllocatePool2
0x14000d1f8  nop     dword ptr [rax+rax+00h]
0x14000d1fd  mov     rdi, rax
0x14000d200  mov     [rsp+88h+var_38], rax
0x14000d205  test    rax, rax
0x14000d208  jnz     short loc_14000D218
0x14000d20a  mov     ebx, 0C000009Ah
0x14000d20f  mov     [rsp+88h+var_48], ebx
0x14000d213  jmp     loc_14000D311
0x14000d218  mov     ecx, [rsi+14h]
0x14000d21b  mov     [rsp+88h+var_40], ecx
0x14000d21f  mov     [rsp+88h+var_44], ebx
0x14000d223  test    r15, r15
0x14000d226  jz      short loc_14000D26E
0x14000d228  lea     eax, [r13-1]
0x14000d22c  cmp     eax, 1
0x14000d22f  ja      short loc_14000D26E
0x14000d231  mov     r9d, ecx
0x14000d234  mov     r8, rdi
0x14000d237  mov     edx, r13d
0x14000d23a  mov     rcx, r15
0x14000d23d  call    StSecpGetChamberProfileKey
0x14000d242  mov     ebx, eax
0x14000d244  mov     [rsp+88h+var_44], eax
0x14000d248  test    eax, eax
0x14000d24a  jns     short loc_14000D277
0x14000d24c  cmp     eax, 0C0000034h
0x14000d251  jnz     short loc_14000D277
0x14000d253  mov     r9d, [rsp+88h+var_40]
0x14000d258  mov     r8, rdi
0x14000d25b  mov     edx, r13d
0x14000d25e  mov     rcx, r15
0x14000d261  call    StSecpDeriveChamberProfileKey
0x14000d266  mov     ebx, eax
0x14000d268  mov     [rsp+88h+var_44], eax
0x14000d26c  jmp     short loc_14000D277
0x14000d26e  mov     ebx, 0C000000Dh
0x14000d273  mov     [rsp+88h+var_44], ebx
0x14000d277  mov     [rsp+88h+var_48], ebx
0x14000d27b  test    ebx, ebx
0x14000d27d  jns     short loc_14000D299
0x14000d27f  mov     eax, cs:Microsoft_Windows_FileCryptEnableBits
0x14000d285  test    al, 1
0x14000d287  jz      loc_14000D311
0x14000d28d  mov     r9d, ebx
0x14000d290  lea     rdx, GetChamberProfileEncryptionKeyFailure
0x14000d297  jmp     short loc_14000D30B
0x14000d299  mov     rdx, r12
0x14000d29c  mov     ecx, 40h ; '@'
0x14000d2a1  mov     r8d, 72434346h
0x14000d2a7  call    cs:__imp_ExAllocatePool2
0x14000d2ae  nop     dword ptr [rax+rax+00h]
0x14000d2b3  mov     r8, rax; pbKeyObject
0x14000d2b6  mov     [r14+8], rax
0x14000d2ba  test    rax, rax
0x14000d2bd  jz      loc_14000D20A
0x14000d2c3  mov     [rsp+88h+dwFlags], 0; dwFlags
0x14000d2cb  mov     eax, [rsi+14h]
0x14000d2ce  mov     [rsp+88h+cbSecret], eax; cbSecret
0x14000d2d2  mov     [rsp+88h+pbSecret], rdi; pbSecret
0x14000d2d7  mov     r9d, r12d; cbKeyObject
0x14000d2da  mov     rdx, r14; phKey
0x14000d2dd  mov     rcx, [rsi]; hAlgorithm
0x14000d2e0  call    cs:__imp_BCryptGenerateSymmetricKey
0x14000d2e7  nop     dword ptr [rax+rax+00h]
0x14000d2ec  mov     ebx, eax
0x14000d2ee  mov     [rsp+88h+var_48], eax
0x14000d2f2  test    eax, eax
0x14000d2f4  jns     short loc_14000D311
0x14000d2f6  mov     ecx, cs:Microsoft_Windows_FileCryptEnableBits
0x14000d2fc  test    cl, 1
0x14000d2ff  jz      short loc_14000D311
0x14000d301  mov     r9d, eax
0x14000d304  lea     rdx, GenerateSymmetricKeyFailure
0x14000d30b  call    McTemplateK0d_EtwWriteTransfer
0x14000d310  nop
0x14000d311  test    rdi, rdi
0x14000d314  jz      short loc_14000D341
0x14000d316  mov     ecx, [rsi+14h]
0x14000d319  mov     rax, rdi
0x14000d31c  test    rcx, rcx
0x14000d31f  jz      short loc_14000D32D
0x14000d321  mov     byte ptr [rax], 0
0x14000d324  inc     rax
0x14000d327  sub     rcx, 1
0x14000d32b  jnz     short loc_14000D321
0x14000d32d  mov     edx, 72434346h; Tag
0x14000d332  mov     rcx, rdi; P
0x14000d335  call    cs:__imp_ExFreePoolWithTag
0x14000d33c  nop     dword ptr [rax+rax+00h]
0x14000d341  test    ebx, ebx
0x14000d343  jns     short loc_14000D34D
0x14000d345  mov     rcx, r14
0x14000d348  call    FCpEncStreamCleanup
0x14000d34d  mov     eax, ebx
0x14000d34f  lea     r11, [rsp+88h+var_28]
0x14000d354  mov     rbx, [r11+38h]
0x14000d358  mov     rsi, [r11+40h]
0x14000d35c  mov     rsp, r11
0x14000d35f  pop     r15
0x14000d361  pop     r14
0x14000d363  pop     r13
0x14000d365  pop     r12
0x14000d367  pop     rdi
0x14000d368  retn
0x140013946  push    rbp
0x140013948  sub     rsp, 40h
0x14001394c  mov     rbp, rdx
0x14001394f  mov     rcx, [rbp+50h]; P
0x140013953  test    rcx, rcx
0x140013956  jz      short loc_140013988
0x140013958  mov     rax, [rbp+90h]
0x14001395f  mov     edx, [rax+14h]
0x140013962  mov     rax, rcx
0x140013965  test    rdx, rdx
0x140013968  jz      short loc_140013976
0x14001396a  mov     byte ptr [rax], 0
0x14001396d  inc     rax
0x140013970  sub     rdx, 1
0x140013974  jnz     short loc_14001396A
0x140013976  mov     edx, 72434346h; Tag
0x14001397b  call    cs:__imp_ExFreePoolWithTag
0x140013982  nop     dword ptr [rax+rax+00h]
0x140013987  nop
0x140013988  cmp     dword ptr [rbp+40h], 0
0x14001398c  jge     short loc_14001399B
0x14001398e  mov     rcx, [rbp+0A8h]
0x140013995  call    FCpEncStreamCleanup
0x14001399a  nop
0x14001399b  add     rsp, 40h
0x14001399f  pop     rbp
0x1400139a0  retn
```
