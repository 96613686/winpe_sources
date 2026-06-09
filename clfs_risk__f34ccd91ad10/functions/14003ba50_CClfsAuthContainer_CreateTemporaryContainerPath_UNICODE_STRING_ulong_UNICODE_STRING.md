# CClfsAuthContainer::CreateTemporaryContainerPath(_UNICODE_STRING &,ulong,_UNICODE_STRING &)

- ea: `0x14003ba50`
- end: `0x14003bc56`
- name: `?CreateTemporaryContainerPath@CClfsAuthContainer@@AEAAJAEAU_UNICODE_STRING@@K0@Z`
- size: `518`
- prototype: `int(CClfsAuthContainer *__hidden this, struct _UNICODE_STRING *, unsigned int, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x14003b7d0`

## callees

- `0x140010404`
- `0x140014240`
- `0x1400143d0`
- `0x140017e40`
- `0x140018280`
- `0x14003ba50`
- `0x14004e3d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14003baa6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003bb01`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003baa6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14003bb01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bb51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bc2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcfb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bb51`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003bc2a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dcfb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003bb86`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003bb86`
- `cng!BCryptGenRandom` at `0x14003bac4`
- `cng!BCryptGenRandom` at `0x14003bac4`

## string_xrefs

- `0x14003baf5`: `\SystemRoot\SystemTemp\`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::CreateTemporaryContainerPath(
        CClfsAuthContainer *this,
        struct _UNICODE_STRING *a2,
        __int64 a3,
        struct _UNICODE_STRING *a4)
{
  NTSTATUS v5; // ebx
  unsigned int v6; // edx
  unsigned int v7; // ecx
  unsigned int v8; // edi
  wchar_t *Buffer; // rcx
  wchar_t *PoolWithTag; // rax
  __int64 i; // rdi
  struct _UNICODE_STRING v13; // [rsp+28h] [rbp-90h] BYREF
  UNICODE_STRING v14; // [rsp+40h] [rbp-78h] BYREF
  PVOID P[2]; // [rsp+50h] [rbp-68h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-58h] BYREF
  UCHAR pbBuffer[8]; // [rsp+70h] [rbp-48h] BYREF
  char v18; // [rsp+78h] [rbp-40h] BYREF

  v14 = 0;
  *(_OWORD *)P = 0;
  DestinationString = 0;
  *(_QWORD *)&v13.Length = 0x100000;
  v13.Buffer = (wchar_t *)&v18;
  RtlInitUnicodeString(&DestinationString, L".clfs.tmp");
  v5 = BCryptGenRandom(0, pbBuffer, 8u, 2u);
  if ( v5 < 0 )
    goto LABEL_22;
  if ( (int)ClfsRegistryQuerySystemTempPath((PUNICODE_STRING)P) < 0 )
    RtlInitUnicodeString(&v14, L"\\SystemRoot\\SystemTemp\\");
  else
    v14 = *(UNICODE_STRING *)P;
  v6 = v14.Length + 32;
  if ( v6 < v14.Length || (v7 = v6 + DestinationString.Length + 2, v7 < v6) || (v8 = v7 + 2, v7 + 2 < v7) )
  {
    v5 = -1073741675;
    goto LABEL_22;
  }
  if ( a4->MaximumLength < v8 )
  {
    Buffer = a4->Buffer;
    if ( Buffer )
    {
      ExFreePoolWithTag(Buffer, 0);
      a4->Buffer = 0;
    }
    v5 = RtlULongToUShort(v8, &a4->MaximumLength);
    if ( v5 < 0 )
      goto LABEL_22;
    PoolWithTag = (wchar_t *)ExAllocatePoolWithTag(PagedPool, v8, 0x73666C43u);
    a4->Buffer = PoolWithTag;
    if ( !PoolWithTag )
    {
      v5 = -1073741670;
      goto LABEL_22;
    }
  }
  memset(a4->Buffer, 0, a4->MaximumLength);
  a4->Length = 0;
  v5 = RtlUnicodeStringCat(a4, &v14);
  if ( v5 >= 0 )
  {
    for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
    {
      v5 = RtlUnicodeStringPrintf(&v13, L"%02hhX", pbBuffer[i]);
      if ( v5 < 0 )
        goto LABEL_22;
      v5 = RtlUnicodeStringCat(a4, &v13);
      if ( v5 < 0 )
        goto LABEL_22;
    }
    v5 = RtlUnicodeStringCat(a4, &DestinationString);
  }
LABEL_22:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14003ba50  push    rbx
0x14003ba52  push    rsi
0x14003ba53  push    rdi
0x14003ba54  push    r14
0x14003ba56  sub     rsp, 98h
0x14003ba5d  mov     rax, cs:__security_cookie
0x14003ba64  xor     rax, rsp
0x14003ba67  mov     [rsp+0B8h+var_30], rax
0x14003ba6f  mov     rsi, r9
0x14003ba72  xorps   xmm0, xmm0
0x14003ba75  movups  xmmword ptr [rsp+0B8h+var_78.Length], xmm0
0x14003ba7a  xorps   xmm1, xmm1
0x14003ba7d  movups  xmmword ptr [rsp+0B8h+P], xmm1
0x14003ba82  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14003ba87  mov     qword ptr [rsp+0B8h+var_90.Length], 100000h
0x14003ba90  lea     rax, [rsp+0B8h+var_40]
0x14003ba95  mov     [rsp+0B8h+var_90.Buffer], rax
0x14003ba9a  lea     rdx, aClfsTmp; ".clfs.tmp"
0x14003baa1  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14003baa6  call    cs:__imp_RtlInitUnicodeString
0x14003baad  nop     dword ptr [rax+rax+00h]
0x14003bab2  nop
0x14003bab3  mov     r9d, 2; dwFlags
0x14003bab9  lea     r8d, [r9+6]; cbBuffer
0x14003babd  lea     rdx, [rsp+0B8h+pbBuffer]; pbBuffer
0x14003bac2  xor     ecx, ecx; hAlgorithm
0x14003bac4  call    cs:__imp_BCryptGenRandom
0x14003bacb  nop     dword ptr [rax+rax+00h]
0x14003bad0  mov     ebx, eax
0x14003bad2  test    eax, eax
0x14003bad4  js      loc_14003BC1E
0x14003bada  lea     rcx, [rsp+0B8h+P]; Destination
0x14003badf  call    ?ClfsRegistryQuerySystemTempPath@@YAJAEAU_UNICODE_STRING@@@Z; ClfsRegistryQuerySystemTempPath(_UNICODE_STRING &)
0x14003bae4  test    eax, eax
0x14003bae6  js      short loc_14003BAF5
0x14003bae8  movaps  xmm0, xmmword ptr [rsp+0B8h+P]
0x14003baed  movdqa  xmmword ptr [rsp+0B8h+var_78.Length], xmm0
0x14003baf3  jmp     short loc_14003BB0D
0x14003baf5  lea     rdx, aSystemrootSyst; "\\SystemRoot\\SystemTemp\\"
0x14003bafc  lea     rcx, [rsp+0B8h+var_78]; DestinationString
0x14003bb01  call    cs:__imp_RtlInitUnicodeString
0x14003bb08  nop     dword ptr [rax+rax+00h]
0x14003bb0d  movzx   eax, [rsp+0B8h+var_78.Length]
0x14003bb12  lea     edx, [rax+20h]
0x14003bb15  cmp     edx, eax
0x14003bb17  jb      loc_14003BC19
0x14003bb1d  movzx   eax, [rsp+0B8h+DestinationString.Length]
0x14003bb22  lea     ecx, [rax+2]
0x14003bb25  add     ecx, edx
0x14003bb27  cmp     ecx, edx
0x14003bb29  jb      loc_14003BC19
0x14003bb2f  lea     edi, [rcx+2]
0x14003bb32  cmp     edi, ecx
0x14003bb34  jb      loc_14003BC19
0x14003bb3a  lea     r14, [rsi+2]
0x14003bb3e  movzx   eax, word ptr [r14]
0x14003bb42  cmp     eax, edi
0x14003bb44  jnb     short loc_14003BBA2
0x14003bb46  mov     rcx, [rsi+8]; P
0x14003bb4a  test    rcx, rcx
0x14003bb4d  jz      short loc_14003BB65
0x14003bb4f  xor     edx, edx; Tag
0x14003bb51  call    cs:__imp_ExFreePoolWithTag
0x14003bb58  nop     dword ptr [rax+rax+00h]
0x14003bb5d  mov     qword ptr [rsi+8], 0
0x14003bb65  mov     rdx, r14; unsigned __int16 *
0x14003bb68  mov     ecx, edi; unsigned int
0x14003bb6a  call    ?RtlULongToUShort@@YAJKPEAG@Z; RtlULongToUShort(ulong,ushort *)
0x14003bb6f  mov     ebx, eax
0x14003bb71  test    eax, eax
0x14003bb73  js      loc_14003BC1E
0x14003bb79  mov     edx, edi; NumberOfBytes
0x14003bb7b  mov     ecx, 1; PoolType
0x14003bb80  mov     r8d, 73666C43h; Tag
0x14003bb86  call    cs:__imp_ExAllocatePoolWithTag
0x14003bb8d  nop     dword ptr [rax+rax+00h]
0x14003bb92  mov     [rsi+8], rax
0x14003bb96  test    rax, rax
0x14003bb99  jnz     short loc_14003BBA2
0x14003bb9b  mov     ebx, 0C000009Ah
0x14003bba0  jmp     short loc_14003BC1E
0x14003bba2  movzx   r8d, word ptr [r14]; Size
0x14003bba6  xor     edx, edx; Val
0x14003bba8  mov     rcx, [rsi+8]; void *
0x14003bbac  call    memset
0x14003bbb1  xor     eax, eax
0x14003bbb3  mov     [rsi], ax
0x14003bbb6  lea     rdx, [rsp+0B8h+var_78]; struct _UNICODE_STRING *
0x14003bbbb  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003bbbe  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14003bbc3  mov     ebx, eax
0x14003bbc5  test    eax, eax
0x14003bbc7  js      short loc_14003BC1E
0x14003bbc9  xor     edi, edi
0x14003bbcb  mov     [rsp+0B8h+var_98], edi
0x14003bbcf  cmp     edi, 8
0x14003bbd2  jnb     short loc_14003BC08
0x14003bbd4  movzx   r8d, [rsp+rdi+0B8h+pbBuffer]
0x14003bbda  lea     rdx, a02hhx; "%02hhX"
0x14003bbe1  lea     rcx, [rsp+0B8h+var_90]; struct _UNICODE_STRING *
0x14003bbe6  call    ?RtlUnicodeStringPrintf@@YAJPEAU_UNICODE_STRING@@PEBGZZ; RtlUnicodeStringPrintf(_UNICODE_STRING *,ushort const *,...)
0x14003bbeb  mov     ebx, eax
0x14003bbed  test    eax, eax
0x14003bbef  js      short loc_14003BC1E
0x14003bbf1  lea     rdx, [rsp+0B8h+var_90]; struct _UNICODE_STRING *
0x14003bbf6  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003bbf9  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14003bbfe  mov     ebx, eax
0x14003bc00  test    eax, eax
0x14003bc02  js      short loc_14003BC1E
0x14003bc04  inc     edi
0x14003bc06  jmp     short loc_14003BBCB
0x14003bc08  lea     rdx, [rsp+0B8h+DestinationString]; struct _UNICODE_STRING *
0x14003bc0d  mov     rcx, rsi; struct _UNICODE_STRING *
0x14003bc10  call    ?RtlUnicodeStringCat@@YAJPEAU_UNICODE_STRING@@PEBU1@@Z; RtlUnicodeStringCat(_UNICODE_STRING *,_UNICODE_STRING const *)
0x14003bc15  mov     ebx, eax
0x14003bc17  jmp     short loc_14003BC1E
0x14003bc19  mov     ebx, 0C0000095h
0x14003bc1e  mov     rcx, [rsp+0B8h+P+8]; P
0x14003bc23  test    rcx, rcx
0x14003bc26  jz      short loc_14003BC36
0x14003bc28  xor     edx, edx; Tag
0x14003bc2a  call    cs:__imp_ExFreePoolWithTag
0x14003bc31  nop     dword ptr [rax+rax+00h]
0x14003bc36  mov     eax, ebx
0x14003bc38  mov     rcx, [rsp+0B8h+var_30]
0x14003bc40  xor     rcx, rsp; StackCookie
0x14003bc43  call    __security_check_cookie
0x14003bc48  add     rsp, 98h
0x14003bc4f  pop     r14
0x14003bc51  pop     rdi
0x14003bc52  pop     rsi
0x14003bc53  pop     rbx
0x14003bc54  retn
0x14007dce7  push    rbp
0x14007dce9  sub     rsp, 20h
0x14007dced  mov     rbp, rdx
0x14007dcf0  mov     rcx, [rbp+58h]; P
0x14007dcf4  test    rcx, rcx
0x14007dcf7  jz      short loc_14007DD08
0x14007dcf9  xor     edx, edx; Tag
0x14007dcfb  call    cs:__imp_ExFreePoolWithTag
0x14007dd02  nop     dword ptr [rax+rax+00h]
0x14007dd07  nop
0x14007dd08  add     rsp, 20h
0x14007dd0c  pop     rbp
0x14007dd0d  retn
```
