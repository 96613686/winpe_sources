# BaseDllOpenMappingTarget

- ea: `0x18001299c`
- end: `0x180012e2f`
- name: `BaseDllOpenMappingTarget`
- size: `1171`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180012384`
- `0x1800125d4`
- `0x180012f68`
- `0x180013550`
- `0x1800449e0`
- `0x18006a978`

## callees

- `0x18001299c`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180012bf9`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180012bf9`
- `ntdll!NtOpenKey` at `0x180012b81`
- `ntdll!NtOpenKey` at `0x180012c33`
- `ntdll!NtOpenKey` at `0x180012b81`
- `ntdll!NtOpenKey` at `0x180012c33`
- `ntdll!RtlAppendUnicodeToString` at `0x180012b0b`
- `ntdll!RtlAppendUnicodeToString` at `0x180012b31`
- `ntdll!RtlAppendUnicodeToString` at `0x180012c9a`
- `ntdll!RtlAppendUnicodeToString` at `0x180012b0b`
- `ntdll!RtlAppendUnicodeToString` at `0x180012b31`
- `ntdll!RtlAppendUnicodeToString` at `0x180012c9a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012af4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012b1a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012b3f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012c88`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012af4`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012b1a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012b3f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180012c88`
- `ntdll!NtClose` at `0x180012c41`
- `ntdll!NtClose` at `0x180012dda`
- `ntdll!NtClose` at `0x180012c41`
- `ntdll!NtClose` at `0x180012dda`
- `ntdll!RtlFreeUnicodeString` at `0x180012c53`
- `ntdll!RtlFreeUnicodeString` at `0x180012cb3`
- `ntdll!RtlFreeUnicodeString` at `0x180012cd2`
- `ntdll!RtlFreeUnicodeString` at `0x180012c53`
- `ntdll!RtlFreeUnicodeString` at `0x180012cb3`
- `ntdll!RtlFreeUnicodeString` at `0x180012cd2`
- `ntdll!NtCreateKey` at `0x180012d03`
- `ntdll!NtCreateKey` at `0x180012dc8`
- `ntdll!NtCreateKey` at `0x180012e02`
- `ntdll!NtCreateKey` at `0x180012d03`
- `ntdll!NtCreateKey` at `0x180012dc8`
- `ntdll!NtCreateKey` at `0x180012e02`
- `ntdll!RtlInitUnicodeString` at `0x180012a58`
- `ntdll!RtlInitUnicodeString` at `0x180012c60`
- `ntdll!RtlInitUnicodeString` at `0x180012a58`
- `ntdll!RtlInitUnicodeString` at `0x180012c60`
- `ntdll!RtlFreeHeap` at `0x180012b9d`
- `ntdll!RtlFreeHeap` at `0x180012b9d`
- `ntdll!RtlAllocateHeap` at `0x180012ac0`
- `ntdll!RtlAllocateHeap` at `0x180012ac0`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180012be4`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180012be4`

## pseudocode

```c
__int64 __fastcall BaseDllOpenMappingTarget(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        char a4,
        PHANDLE KeyHandle)
{
  void **v5; // r12
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  unsigned __int64 v12; // xmm0_8
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const UNICODE_STRING *p_DestinationString; // rbx
  int v19; // ecx
  int v20; // edx
  int v21; // r14d
  char v22; // di
  USHORT v23; // si
  unsigned int v24; // ebx
  char v26; // di
  NTSTATUS i; // eax
  USHORT Length; // cx
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-91h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-81h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-71h] BYREF
  struct _OBJECT_ATTRIBUTES v32; // [rsp+70h] [rbp-61h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp-31h] BYREF
  struct _UNICODE_STRING v34; // [rsp+B0h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-11h] BYREF
  ULONG Disposition; // [rsp+138h] [rbp+67h] BYREF
  char v37; // [rsp+148h] [rbp+77h]

  v37 = a4;
  v5 = KeyHandle;
  Disposition = 0;
  *KeyHandle = (void *)-1LL;
  v9 = *(_QWORD *)(a2 + 32);
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  Source = 0;
  if ( !v9 )
    return 0;
  v10 = *(_QWORD *)(BaseStaticServerData + 2536);
  v11 = v9 - v10 + BaseStaticServerData;
  if ( !v11 )
    return 0;
  Source = *(UNICODE_STRING *)(v11 + 8);
  v12 = _mm_srli_si128((__m128i)Source, 8).m128i_u64[0];
  Source.Buffer = v12 ? (PWSTR)(BaseStaticServerData - v10 + v12) : 0LL;
  if ( !Source.Length )
    return 0;
  v13 = *(_DWORD *)(a2 + 24);
  RtlInitUnicodeString(&DestinationString, 0);
  if ( v13 < 0 )
  {
    KeyHandle = 0;
    memset(&v32, 0, 44);
    if ( *(_BYTE *)(KernelBaseGetGlobalData(v15, v14, v16, v17) + 4) == 1 )
      return 3221225506LL;
    if ( RtlFormatCurrentUserKeyPath(&DestinationString) >= 0 )
    {
      v32.Length = 48;
      v32.ObjectName = &DestinationString;
      v32.RootDirectory = 0;
      v32.Attributes = 64;
      *(_OWORD *)&v32.SecurityDescriptor = 0;
      if ( NtOpenKey((PHANDLE)&KeyHandle, 0x80000000, &v32) >= 0 )
      {
        NtClose(KeyHandle);
        p_DestinationString = &DestinationString;
        goto LABEL_31;
      }
      RtlFreeUnicodeString(&DestinationString);
      RtlInitUnicodeString(&DestinationString, 0);
    }
    p_DestinationString = (const UNICODE_STRING *)L".0";
LABEL_31:
    if ( p_DestinationString )
      goto LABEL_9;
LABEL_32:
    v19 = 2;
    goto LABEL_10;
  }
  if ( (v13 & 0x40000000) == 0 )
  {
    p_DestinationString = 0;
    goto LABEL_32;
  }
  p_DestinationString = &BaseDllIniSoftwareKeyPath;
LABEL_9:
  v19 = p_DestinationString->Length + 4;
LABEL_10:
  v20 = v19 + Source.Length;
  v21 = v13 & 0x10000000;
  if ( (v13 & 0x10000000) != 0 )
    v20 += *(unsigned __int16 *)(a1 + 24) + 2;
  if ( a3 && (v13 & 0x20000000) != 0 )
  {
    v22 = 1;
    v20 += a3->Length + 2;
  }
  else
  {
    v22 = 0;
  }
  v23 = v20 + 2;
  Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)(v20 + 2));
  if ( Destination.Buffer )
  {
    Destination.MaximumLength = v23;
    Destination.Length = 0;
    if ( p_DestinationString )
    {
      RtlAppendUnicodeStringToString(&Destination, p_DestinationString);
      RtlAppendUnicodeToString(&Destination, L"\\");
      if ( p_DestinationString == &DestinationString )
        RtlFreeUnicodeString(&DestinationString);
    }
    RtlAppendUnicodeStringToString(&Destination, &Source);
    if ( v21 )
    {
      RtlAppendUnicodeToString(&Destination, L"\\");
      RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(a1 + 24));
    }
    if ( v22 )
    {
      RtlAppendUnicodeToString(&Destination, L"\\");
      RtlAppendUnicodeStringToString(&Destination, a3);
    }
    ObjectAttributes.Attributes = 192;
    ObjectAttributes.ObjectName = &Destination;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    if ( v37 )
    {
      v26 = 0;
      for ( i = NtCreateKey(v5, 0x2000Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
            ;
            i = NtCreateKey(v5, 0x2000Fu, &ObjectAttributes, 0, 0, 0, &Disposition) )
      {
        v24 = i;
        if ( i != -1073741772 || v26 )
          break;
        LODWORD(KeyHandle) = 0;
        Handle = 0;
        memset(&v32, 0, 44);
        v34 = Destination;
        if ( *(_WORD *)(_mm_srli_si128((__m128i)Destination, 8).m128i_u64[0]
                      + 2 * ((unsigned __int64)(unsigned __int16)_mm_cvtsi128_si32((__m128i)Destination) >> 1)) != 92 )
        {
          Length = v34.Length;
          do
          {
            Length -= 2;
            v34.Length = Length;
          }
          while ( v34.Buffer[(unsigned __int64)Length >> 1] != 92 );
        }
        v32.Length = 48;
        v32.ObjectName = &v34;
        v32.RootDirectory = 0;
        v32.Attributes = 192;
        *(_OWORD *)&v32.SecurityDescriptor = 0;
        if ( NtCreateKey(&Handle, 0x2000Fu, &v32, 0, 0, 0, (PULONG)&KeyHandle) < 0 )
          break;
        NtClose(Handle);
        v26 = 1;
      }
    }
    else
    {
      v24 = NtOpenKey(v5, 0x80000000, &ObjectAttributes);
    }
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
    return v24;
  }
  else
  {
    if ( p_DestinationString == &DestinationString )
      RtlFreeUnicodeString(&DestinationString);
    return 3221225495LL;
  }
}

```

## disassembly

```asm
0x18001299c  mov     [rsp-8+arg_0], rbx
0x1800129a1  mov     [rsp-8+arg_18], r9b
0x1800129a6  push    rbp
0x1800129a7  push    rsi
0x1800129a8  push    rdi
0x1800129a9  push    r12
0x1800129ab  push    r13
0x1800129ad  push    r14
0x1800129af  push    r15
0x1800129b1  lea     rbp, [rsp-1Fh]
0x1800129b6  sub     rsp, 0F0h
0x1800129bd  mov     r12, [rbp+4Fh+KeyHandle]
0x1800129c1  xorps   xmm0, xmm0
0x1800129c4  xor     esi, esi
0x1800129c6  mov     r13, rcx
0x1800129c9  xor     eax, eax
0x1800129cb  mov     [rbp+4Fh+arg_8], esi
0x1800129ce  xorps   xmm1, xmm1
0x1800129d1  mov     r15, r8
0x1800129d4  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x1800129dc  mov     rdi, rdx
0x1800129df  mov     rcx, [rdx+20h]
0x1800129e3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800129e7  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1800129ec  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800129f0  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800129f4  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x1800129f9  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm1
0x1800129fd  test    rcx, rcx
0x180012a00  jz      loc_180012E28
0x180012a06  mov     rax, cs:BaseStaticServerData
0x180012a0d  mov     rdx, [rax+9E8h]
0x180012a14  sub     rcx, rdx
0x180012a17  lea     r8, [rcx+rax]
0x180012a1b  test    r8, r8
0x180012a1e  jz      loc_180012E28
0x180012a24  movups  xmm0, xmmword ptr [r8+8]
0x180012a29  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x180012a2d  psrldq  xmm0, 8
0x180012a32  movq    rcx, xmm0
0x180012a37  test    rcx, rcx
0x180012a3a  jnz     loc_180012BC0
0x180012a40  mov     [rbp+4Fh+Source.Buffer], rsi
0x180012a44  cmp     [rbp+4Fh+Source.Length], si
0x180012a48  jz      loc_180012E28
0x180012a4e  mov     edi, [rdi+18h]
0x180012a51  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180012a56  xor     edx, edx; SourceString
0x180012a58  call    cs:__imp_RtlInitUnicodeString
0x180012a5e  test    edi, edi
0x180012a60  js      loc_180012BCF
0x180012a66  bt      edi, 1Eh
0x180012a6a  jnb     loc_180012CBE
0x180012a70  lea     rbx, BaseDllIniSoftwareKeyPath
0x180012a77  movzx   ecx, word ptr [rbx]
0x180012a7a  add     ecx, 4
0x180012a7d  movzx   edx, [rbp+4Fh+Source.Length]
0x180012a81  mov     r14d, edi
0x180012a84  add     edx, ecx
0x180012a86  and     r14d, 10000000h
0x180012a8d  jz      short loc_180012A99
0x180012a8f  movzx   eax, word ptr [r13+18h]
0x180012a94  add     eax, 2
0x180012a97  add     edx, eax
0x180012a99  test    r15, r15
0x180012a9c  jz      short loc_180012AA8
0x180012a9e  bt      edi, 1Dh
0x180012aa2  jb      loc_180012E17
0x180012aa8  mov     dil, sil
0x180012aab  mov     rcx, gs:60h
0x180012ab4  lea     esi, [rdx+2]
0x180012ab7  mov     r8d, esi; Size
0x180012aba  xor     edx, edx; Flags
0x180012abc  mov     rcx, [rcx+30h]; HeapHandle
0x180012ac0  call    cs:__imp_RtlAllocateHeap
0x180012ac6  mov     [rsp+120h+Destination.Buffer], rax
0x180012acb  test    rax, rax
0x180012ace  jz      loc_180012CC3
0x180012ad4  xor     eax, eax
0x180012ad6  mov     [rsp+120h+Destination.MaximumLength], si
0x180012adb  xor     esi, esi
0x180012add  mov     [rsp+120h+Destination.Length], ax
0x180012ae2  test    rbx, rbx
0x180012ae5  jnz     loc_180012C80
0x180012aeb  lea     rdx, [rbp+4Fh+Source]; Source
0x180012aef  lea     rcx, [rsp+120h+Destination]; Destination
0x180012af4  call    cs:__imp_RtlAppendUnicodeStringToString
0x180012afa  test    r14d, r14d
0x180012afd  jz      short loc_180012B20
0x180012aff  lea     rdx, Source; "\\"
0x180012b06  lea     rcx, [rsp+120h+Destination]; Destination
0x180012b0b  call    cs:__imp_RtlAppendUnicodeToString
0x180012b11  lea     rdx, [r13+18h]; Source
0x180012b15  lea     rcx, [rsp+120h+Destination]; Destination
0x180012b1a  call    cs:__imp_RtlAppendUnicodeStringToString
0x180012b20  test    dil, dil
0x180012b23  jz      short loc_180012B45
0x180012b25  lea     rdx, Source; "\\"
0x180012b2c  lea     rcx, [rsp+120h+Destination]; Destination
0x180012b31  call    cs:__imp_RtlAppendUnicodeToString
0x180012b37  mov     rdx, r15; Source
0x180012b3a  lea     rcx, [rsp+120h+Destination]; Destination
0x180012b3f  call    cs:__imp_RtlAppendUnicodeStringToString
0x180012b45  lea     rax, [rsp+120h+Destination]
0x180012b4a  mov     r15d, 0C0h
0x180012b50  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180012b54  xorps   xmm0, xmm0
0x180012b57  mov     rcx, r12; KeyHandle
0x180012b5a  mov     [rbp+4Fh+ObjectAttributes.Attributes], r15d
0x180012b5e  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180012b62  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x180012b67  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180012b6e  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x180012b72  cmp     [rbp+4Fh+arg_18], sil
0x180012b76  jnz     loc_180012CE2
0x180012b7c  mov     edx, 80000000h; DesiredAccess
0x180012b81  call    cs:__imp_NtOpenKey
0x180012b87  mov     ebx, eax
0x180012b89  mov     rcx, gs:60h
0x180012b92  xor     edx, edx; Flags
0x180012b94  mov     r8, [rsp+120h+Destination.Buffer]; P
0x180012b99  mov     rcx, [rcx+30h]; HeapHandle
0x180012b9d  call    cs:__imp_RtlFreeHeap
0x180012ba3  mov     eax, ebx
0x180012ba5  mov     rbx, [rsp+120h+arg_0]
0x180012bad  add     rsp, 0F0h
0x180012bb4  pop     r15
0x180012bb6  pop     r14
0x180012bb8  pop     r13
0x180012bba  pop     r12
0x180012bbc  pop     rdi
0x180012bbd  pop     rsi
0x180012bbe  pop     rbp
0x180012bbf  retn
0x180012bc0  sub     rax, rdx
0x180012bc3  add     rcx, rax
0x180012bc6  mov     [rbp+4Fh+Source.Buffer], rcx
0x180012bca  jmp     loc_180012A44
0x180012bcf  xorps   xmm0, xmm0
0x180012bd2  mov     [rbp+4Fh+KeyHandle], rsi
0x180012bd6  movups  xmmword ptr [rbp+4Fh+var_B0.ObjectName], xmm0
0x180012bda  xor     eax, eax
0x180012bdc  movups  xmmword ptr [rbp+4Fh+var_B0+1Ch], xmm0
0x180012be0  movups  xmmword ptr [rbp+4Fh+var_B0.Length], xmm0
0x180012be4  call    cs:__imp_KernelBaseGetGlobalData
0x180012bea  cmp     byte ptr [rax+4], 1
0x180012bee  jz      loc_180012E0D
0x180012bf4  lea     rcx, [rsp+120h+DestinationString]; KeyPath
0x180012bf9  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180012bff  test    eax, eax
0x180012c01  js      short loc_180012C66
0x180012c03  lea     rax, [rsp+120h+DestinationString]
0x180012c08  mov     [rbp+4Fh+var_B0.Length], 30h ; '0'
0x180012c0f  xorps   xmm0, xmm0
0x180012c12  mov     [rbp+4Fh+var_B0.ObjectName], rax
0x180012c16  lea     r8, [rbp+4Fh+var_B0]; ObjectAttributes
0x180012c1a  mov     [rbp+4Fh+var_B0.RootDirectory], rsi
0x180012c1e  mov     edx, 80000000h; DesiredAccess
0x180012c23  mov     [rbp+4Fh+var_B0.Attributes], 40h ; '@'
0x180012c2a  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x180012c2e  movdqu  xmmword ptr [rbp+4Fh+var_B0.SecurityDescriptor], xmm0
0x180012c33  call    cs:__imp_NtOpenKey
0x180012c39  test    eax, eax
0x180012c3b  js      short loc_180012C4E
0x180012c3d  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x180012c41  call    cs:__imp_NtClose
0x180012c47  lea     rbx, [rsp+120h+DestinationString]
0x180012c4c  jmp     short loc_180012C6D
0x180012c4e  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x180012c53  call    cs:__imp_RtlFreeUnicodeString
0x180012c59  xor     edx, edx; SourceString
0x180012c5b  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180012c60  call    cs:__imp_RtlInitUnicodeString
0x180012c66  lea     rbx, BaseDllIniDefaultUserKeyPath; ".0"
0x180012c6d  test    rbx, rbx
0x180012c70  jnz     loc_180012A77
0x180012c76  mov     ecx, 2
0x180012c7b  jmp     loc_180012A7D
0x180012c80  mov     rdx, rbx; Source
0x180012c83  lea     rcx, [rsp+120h+Destination]; Destination
0x180012c88  call    cs:__imp_RtlAppendUnicodeStringToString
0x180012c8e  lea     rdx, Source; "\\"
0x180012c95  lea     rcx, [rsp+120h+Destination]; Destination
0x180012c9a  call    cs:__imp_RtlAppendUnicodeToString
0x180012ca0  lea     rax, [rsp+120h+DestinationString]
0x180012ca5  cmp     rbx, rax
0x180012ca8  jnz     loc_180012AEB
0x180012cae  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x180012cb3  call    cs:__imp_RtlFreeUnicodeString
0x180012cb9  jmp     loc_180012AEB
0x180012cbe  mov     rbx, rsi
0x180012cc1  jmp     short loc_180012C76
0x180012cc3  lea     rax, [rsp+120h+DestinationString]
0x180012cc8  cmp     rbx, rax
0x180012ccb  jnz     short loc_180012CD8
0x180012ccd  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x180012cd2  call    cs:__imp_RtlFreeUnicodeString
0x180012cd8  mov     eax, 0C0000017h
0x180012cdd  jmp     loc_180012BA5
0x180012ce2  lea     rax, [rbp+4Fh+arg_8]
0x180012ce6  mov     r14d, 2000Fh
0x180012cec  mov     [rsp+120h+Disposition], rax; Disposition
0x180012cf1  xor     r9d, r9d; TitleIndex
0x180012cf4  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x180012cf8  mov     edx, r14d; DesiredAccess
0x180012cfb  mov     [rsp+120h+Class], rsi; Class
0x180012d00  mov     dil, sil
0x180012d03  call    cs:__imp_NtCreateKey
0x180012d09  mov     r13d, 0C0000034h
0x180012d0f  mov     ebx, eax
0x180012d11  cmp     eax, r13d
0x180012d14  jnz     loc_180012B89
0x180012d1a  test    dil, dil
0x180012d1d  jnz     loc_180012B89
0x180012d23  xorps   xmm0, xmm0
0x180012d26  mov     dword ptr [rbp+4Fh+KeyHandle], esi
0x180012d29  movups  xmmword ptr [rbp+4Fh+var_B0.ObjectName], xmm0
0x180012d2d  xor     eax, eax
0x180012d2f  mov     [rbp+4Fh+Handle], rsi
0x180012d33  movups  xmmword ptr [rbp+4Fh+var_B0+1Ch], xmm0
0x180012d37  movups  xmmword ptr [rbp+4Fh+var_B0.Length], xmm0
0x180012d3b  movaps  xmm0, xmmword ptr [rsp+120h+Destination.Length]
0x180012d40  movd    eax, xmm0
0x180012d44  movdqa  [rbp+4Fh+var_70], xmm0
0x180012d49  psrldq  xmm0, 8
0x180012d4e  movzx   ecx, ax
0x180012d51  movq    rax, xmm0
0x180012d56  shr     rcx, 1
0x180012d59  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180012d5e  jz      short loc_180012D89
0x180012d60  mov     rdx, qword ptr [rbp+4Fh+var_70+8]
0x180012d64  mov     r13d, 2
0x180012d6a  movzx   ecx, word ptr [rbp+4Fh+var_70]
0x180012d6e  sub     cx, r13w
0x180012d72  movzx   eax, cx
0x180012d75  shr     rax, 1
0x180012d78  mov     word ptr [rbp+4Fh+var_70], cx
0x180012d7c  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x180012d81  jnz     short loc_180012D6E
0x180012d83  mov     r13d, 0C0000034h
0x180012d89  lea     rax, [rbp+4Fh+var_70]
0x180012d8d  mov     [rbp+4Fh+var_B0.Length], 30h ; '0'
0x180012d94  mov     [rbp+4Fh+var_B0.ObjectName], rax
0x180012d98  lea     r8, [rbp+4Fh+var_B0]; ObjectAttributes
0x180012d9c  lea     rax, [rbp+4Fh+KeyHandle]
0x180012da0  mov     [rbp+4Fh+var_B0.RootDirectory], rsi
0x180012da4  mov     [rsp+120h+Disposition], rax; Disposition
0x180012da9  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x180012dad  xorps   xmm0, xmm0
0x180012db0  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x180012db4  xor     r9d, r9d; TitleIndex
0x180012db7  mov     [rsp+120h+Class], rsi; Class
0x180012dbc  mov     edx, r14d; DesiredAccess
0x180012dbf  mov     [rbp+4Fh+var_B0.Attributes], r15d
0x180012dc3  movdqu  xmmword ptr [rbp+4Fh+var_B0.SecurityDescriptor], xmm0
0x180012dc8  call    cs:__imp_NtCreateKey
0x180012dce  test    eax, eax
0x180012dd0  js      loc_180012B89
0x180012dd6  mov     rcx, [rbp+4Fh+Handle]; Handle
0x180012dda  call    cs:__imp_NtClose
0x180012de0  lea     rax, [rbp+4Fh+arg_8]
0x180012de4  xor     r9d, r9d; TitleIndex
0x180012de7  mov     [rsp+120h+Disposition], rax; Disposition
0x180012dec  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180012df0  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x180012df4  mov     edx, r14d; DesiredAccess
0x180012df7  mov     rcx, r12; KeyHandle
0x180012dfa  mov     [rsp+120h+Class], rsi; Class
0x180012dff  mov     dil, 1
0x180012e02  call    cs:__imp_NtCreateKey
0x180012e08  jmp     loc_180012D0F
0x180012e0d  mov     eax, 0C0000022h
0x180012e12  jmp     loc_180012BA5
0x180012e17  movzx   eax, word ptr [r15]
0x180012e1b  mov     dil, 1
0x180012e1e  add     eax, 2
0x180012e21  add     edx, eax
0x180012e23  jmp     loc_180012AAB
0x180012e28  xor     eax, eax
0x180012e2a  jmp     loc_180012BA5
```
