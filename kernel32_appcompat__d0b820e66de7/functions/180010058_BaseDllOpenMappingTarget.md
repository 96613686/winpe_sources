# BaseDllOpenMappingTarget

- ea: `0x180010058`
- end: `0x180010576`
- name: `BaseDllOpenMappingTarget`
- size: `1310`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f9e4`
- `0x18000fc4c`
- `0x1800106b8`
- `0x180010ce0`
- `0x180048ff8`
- `0x180071c4c`

## callees

- `0x180010058`

## import_xrefs

- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800102f2`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x1800102f2`
- `ntdll!NtOpenKey` at `0x180010267`
- `ntdll!NtOpenKey` at `0x180010332`
- `ntdll!NtOpenKey` at `0x180010267`
- `ntdll!NtOpenKey` at `0x180010332`
- `ntdll!RtlAppendUnicodeToString` at `0x1800101d9`
- `ntdll!RtlAppendUnicodeToString` at `0x18001020b`
- `ntdll!RtlAppendUnicodeToString` at `0x1800103b7`
- `ntdll!RtlAppendUnicodeToString` at `0x1800101d9`
- `ntdll!RtlAppendUnicodeToString` at `0x18001020b`
- `ntdll!RtlAppendUnicodeToString` at `0x1800103b7`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800101bc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800101ee`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001021f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001039f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800101bc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800101ee`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001021f`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001039f`
- `ntdll!NtClose` at `0x180010346`
- `ntdll!NtClose` at `0x180010515`
- `ntdll!NtClose` at `0x180010346`
- `ntdll!NtClose` at `0x180010515`
- `ntdll!RtlFreeUnicodeString` at `0x18001035e`
- `ntdll!RtlFreeUnicodeString` at `0x1800103d6`
- `ntdll!RtlFreeUnicodeString` at `0x1800103fb`
- `ntdll!RtlFreeUnicodeString` at `0x18001035e`
- `ntdll!RtlFreeUnicodeString` at `0x1800103d6`
- `ntdll!RtlFreeUnicodeString` at `0x1800103fb`
- `ntdll!NtCreateKey` at `0x180010432`
- `ntdll!NtCreateKey` at `0x1800104fd`
- `ntdll!NtCreateKey` at `0x180010543`
- `ntdll!NtCreateKey` at `0x180010432`
- `ntdll!NtCreateKey` at `0x1800104fd`
- `ntdll!NtCreateKey` at `0x180010543`
- `ntdll!RtlInitUnicodeString` at `0x180010114`
- `ntdll!RtlInitUnicodeString` at `0x180010371`
- `ntdll!RtlInitUnicodeString` at `0x180010114`
- `ntdll!RtlInitUnicodeString` at `0x180010371`
- `ntdll!RtlFreeHeap` at `0x180010289`
- `ntdll!RtlFreeHeap` at `0x180010289`
- `ntdll!RtlAllocateHeap` at `0x180010182`
- `ntdll!RtlAllocateHeap` at `0x180010182`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800102d7`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x1800102d7`

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
0x180010058  mov     [rsp-8+arg_0], rbx
0x18001005d  mov     [rsp-8+arg_18], r9b
0x180010062  push    rbp
0x180010063  push    rsi
0x180010064  push    rdi
0x180010065  push    r12
0x180010067  push    r13
0x180010069  push    r14
0x18001006b  push    r15
0x18001006d  lea     rbp, [rsp-1Fh]
0x180010072  sub     rsp, 0F0h
0x180010079  mov     r12, [rbp+4Fh+KeyHandle]
0x18001007d  xorps   xmm0, xmm0
0x180010080  xor     esi, esi
0x180010082  mov     r13, rcx
0x180010085  xor     eax, eax
0x180010087  mov     [rbp+4Fh+arg_8], esi
0x18001008a  xorps   xmm1, xmm1
0x18001008d  mov     r15, r8
0x180010090  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x180010098  mov     rdi, rdx
0x18001009b  mov     rcx, [rdx+20h]
0x18001009f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800100a3  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x1800100a8  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800100ac  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800100b0  movups  xmmword ptr [rsp+120h+Destination.Length], xmm0
0x1800100b5  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm1
0x1800100b9  test    rcx, rcx
0x1800100bc  jz      loc_18001056F
0x1800100c2  mov     rax, cs:BaseStaticServerData
0x1800100c9  mov     rdx, [rax+9E8h]
0x1800100d0  sub     rcx, rdx
0x1800100d3  lea     r8, [rcx+rax]
0x1800100d7  test    r8, r8
0x1800100da  jz      loc_18001056F
0x1800100e0  movups  xmm0, xmmword ptr [r8+8]
0x1800100e5  movups  xmmword ptr [rbp+4Fh+Source.Length], xmm0
0x1800100e9  psrldq  xmm0, 8
0x1800100ee  movq    rcx, xmm0
0x1800100f3  test    rcx, rcx
0x1800100f6  jnz     loc_1800102B3
0x1800100fc  mov     [rbp+4Fh+Source.Buffer], rsi
0x180010100  cmp     [rbp+4Fh+Source.Length], si
0x180010104  jz      loc_18001056F
0x18001010a  mov     edi, [rdi+18h]
0x18001010d  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180010112  xor     edx, edx; SourceString
0x180010114  call    cs:__imp_RtlInitUnicodeString
0x18001011b  nop     dword ptr [rax+rax+00h]
0x180010120  test    edi, edi
0x180010122  js      loc_1800102C2
0x180010128  bt      edi, 1Eh
0x18001012c  jnb     loc_1800103E7
0x180010132  lea     rbx, BaseDllIniSoftwareKeyPath
0x180010139  movzx   ecx, word ptr [rbx]
0x18001013c  add     ecx, 4
0x18001013f  movzx   edx, [rbp+4Fh+Source.Length]
0x180010143  mov     r14d, edi
0x180010146  add     edx, ecx
0x180010148  and     r14d, 10000000h
0x18001014f  jz      short loc_18001015B
0x180010151  movzx   eax, word ptr [r13+18h]
0x180010156  add     eax, 2
0x180010159  add     edx, eax
0x18001015b  test    r15, r15
0x18001015e  jz      short loc_18001016A
0x180010160  bt      edi, 1Dh
0x180010164  jb      loc_18001055E
0x18001016a  mov     dil, sil
0x18001016d  mov     rcx, gs:60h
0x180010176  lea     esi, [rdx+2]
0x180010179  mov     r8d, esi; Size
0x18001017c  xor     edx, edx; Flags
0x18001017e  mov     rcx, [rcx+30h]; HeapHandle
0x180010182  call    cs:__imp_RtlAllocateHeap
0x180010189  nop     dword ptr [rax+rax+00h]
0x18001018e  mov     [rsp+120h+Destination.Buffer], rax
0x180010193  test    rax, rax
0x180010196  jz      loc_1800103EC
0x18001019c  xor     eax, eax
0x18001019e  mov     [rsp+120h+Destination.MaximumLength], si
0x1800101a3  xor     esi, esi
0x1800101a5  mov     [rsp+120h+Destination.Length], ax
0x1800101aa  test    rbx, rbx
0x1800101ad  jnz     loc_180010397
0x1800101b3  lea     rdx, [rbp+4Fh+Source]; Source
0x1800101b7  lea     rcx, [rsp+120h+Destination]; Destination
0x1800101bc  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800101c3  nop     dword ptr [rax+rax+00h]
0x1800101c8  test    r14d, r14d
0x1800101cb  jz      short loc_1800101FA
0x1800101cd  lea     rdx, Source; "\\"
0x1800101d4  lea     rcx, [rsp+120h+Destination]; Destination
0x1800101d9  call    cs:__imp_RtlAppendUnicodeToString
0x1800101e0  nop     dword ptr [rax+rax+00h]
0x1800101e5  lea     rdx, [r13+18h]; Source
0x1800101e9  lea     rcx, [rsp+120h+Destination]; Destination
0x1800101ee  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800101f5  nop     dword ptr [rax+rax+00h]
0x1800101fa  test    dil, dil
0x1800101fd  jz      short loc_18001022B
0x1800101ff  lea     rdx, Source; "\\"
0x180010206  lea     rcx, [rsp+120h+Destination]; Destination
0x18001020b  call    cs:__imp_RtlAppendUnicodeToString
0x180010212  nop     dword ptr [rax+rax+00h]
0x180010217  mov     rdx, r15; Source
0x18001021a  lea     rcx, [rsp+120h+Destination]; Destination
0x18001021f  call    cs:__imp_RtlAppendUnicodeStringToString
0x180010226  nop     dword ptr [rax+rax+00h]
0x18001022b  lea     rax, [rsp+120h+Destination]
0x180010230  mov     r15d, 0C0h
0x180010236  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x18001023a  xorps   xmm0, xmm0
0x18001023d  mov     rcx, r12; KeyHandle
0x180010240  mov     [rbp+4Fh+ObjectAttributes.Attributes], r15d
0x180010244  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x180010248  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18001024d  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x180010254  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x180010258  cmp     [rbp+4Fh+arg_18], sil
0x18001025c  jnz     loc_180010411
0x180010262  mov     edx, 80000000h; DesiredAccess
0x180010267  call    cs:__imp_NtOpenKey
0x18001026e  nop     dword ptr [rax+rax+00h]
0x180010273  mov     ebx, eax
0x180010275  mov     rcx, gs:60h
0x18001027e  xor     edx, edx; Flags
0x180010280  mov     r8, [rsp+120h+Destination.Buffer]; P
0x180010285  mov     rcx, [rcx+30h]; HeapHandle
0x180010289  call    cs:__imp_RtlFreeHeap
0x180010290  nop     dword ptr [rax+rax+00h]
0x180010295  mov     eax, ebx
0x180010297  mov     rbx, [rsp+120h+arg_0]
0x18001029f  add     rsp, 0F0h
0x1800102a6  pop     r15
0x1800102a8  pop     r14
0x1800102aa  pop     r13
0x1800102ac  pop     r12
0x1800102ae  pop     rdi
0x1800102af  pop     rsi
0x1800102b0  pop     rbp
0x1800102b1  retn
0x1800102b3  sub     rax, rdx
0x1800102b6  add     rcx, rax
0x1800102b9  mov     [rbp+4Fh+Source.Buffer], rcx
0x1800102bd  jmp     loc_180010100
0x1800102c2  xorps   xmm0, xmm0
0x1800102c5  mov     [rbp+4Fh+KeyHandle], rsi
0x1800102c9  movups  xmmword ptr [rbp+4Fh+var_B0.ObjectName], xmm0
0x1800102cd  xor     eax, eax
0x1800102cf  movups  xmmword ptr [rbp+4Fh+var_B0+1Ch], xmm0
0x1800102d3  movups  xmmword ptr [rbp+4Fh+var_B0.Length], xmm0
0x1800102d7  call    cs:__imp_KernelBaseGetGlobalData
0x1800102de  nop     dword ptr [rax+rax+00h]
0x1800102e3  cmp     byte ptr [rax+4], 1
0x1800102e7  jz      loc_180010554
0x1800102ed  lea     rcx, [rsp+120h+DestinationString]; KeyPath
0x1800102f2  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x1800102f9  nop     dword ptr [rax+rax+00h]
0x1800102fe  test    eax, eax
0x180010300  js      short loc_18001037D
0x180010302  lea     rax, [rsp+120h+DestinationString]
0x180010307  mov     [rbp+4Fh+var_B0.Length], 30h ; '0'
0x18001030e  xorps   xmm0, xmm0
0x180010311  mov     [rbp+4Fh+var_B0.ObjectName], rax
0x180010315  lea     r8, [rbp+4Fh+var_B0]; ObjectAttributes
0x180010319  mov     [rbp+4Fh+var_B0.RootDirectory], rsi
0x18001031d  mov     edx, 80000000h; DesiredAccess
0x180010322  mov     [rbp+4Fh+var_B0.Attributes], 40h ; '@'
0x180010329  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x18001032d  movdqu  xmmword ptr [rbp+4Fh+var_B0.SecurityDescriptor], xmm0
0x180010332  call    cs:__imp_NtOpenKey
0x180010339  nop     dword ptr [rax+rax+00h]
0x18001033e  test    eax, eax
0x180010340  js      short loc_180010359
0x180010342  mov     rcx, [rbp+4Fh+KeyHandle]; Handle
0x180010346  call    cs:__imp_NtClose
0x18001034d  nop     dword ptr [rax+rax+00h]
0x180010352  lea     rbx, [rsp+120h+DestinationString]
0x180010357  jmp     short loc_180010384
0x180010359  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x18001035e  call    cs:__imp_RtlFreeUnicodeString
0x180010365  nop     dword ptr [rax+rax+00h]
0x18001036a  xor     edx, edx; SourceString
0x18001036c  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x180010371  call    cs:__imp_RtlInitUnicodeString
0x180010378  nop     dword ptr [rax+rax+00h]
0x18001037d  lea     rbx, BaseDllIniDefaultUserKeyPath; ".0"
0x180010384  test    rbx, rbx
0x180010387  jnz     loc_180010139
0x18001038d  mov     ecx, 2
0x180010392  jmp     loc_18001013F
0x180010397  mov     rdx, rbx; Source
0x18001039a  lea     rcx, [rsp+120h+Destination]; Destination
0x18001039f  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800103a6  nop     dword ptr [rax+rax+00h]
0x1800103ab  lea     rdx, Source; "\\"
0x1800103b2  lea     rcx, [rsp+120h+Destination]; Destination
0x1800103b7  call    cs:__imp_RtlAppendUnicodeToString
0x1800103be  nop     dword ptr [rax+rax+00h]
0x1800103c3  lea     rax, [rsp+120h+DestinationString]
0x1800103c8  cmp     rbx, rax
0x1800103cb  jnz     loc_1800101B3
0x1800103d1  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x1800103d6  call    cs:__imp_RtlFreeUnicodeString
0x1800103dd  nop     dword ptr [rax+rax+00h]
0x1800103e2  jmp     loc_1800101B3
0x1800103e7  mov     rbx, rsi
0x1800103ea  jmp     short loc_18001038D
0x1800103ec  lea     rax, [rsp+120h+DestinationString]
0x1800103f1  cmp     rbx, rax
0x1800103f4  jnz     short loc_180010407
0x1800103f6  lea     rcx, [rsp+120h+DestinationString]; UnicodeString
0x1800103fb  call    cs:__imp_RtlFreeUnicodeString
0x180010402  nop     dword ptr [rax+rax+00h]
0x180010407  mov     eax, 0C0000017h
0x18001040c  jmp     loc_180010297
0x180010411  lea     rax, [rbp+4Fh+arg_8]
0x180010415  mov     r14d, 2000Fh
0x18001041b  mov     [rsp+120h+Disposition], rax; Disposition
0x180010420  xor     r9d, r9d; TitleIndex
0x180010423  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x180010427  mov     edx, r14d; DesiredAccess
0x18001042a  mov     [rsp+120h+Class], rsi; Class
0x18001042f  mov     dil, sil
0x180010432  call    cs:__imp_NtCreateKey
0x180010439  nop     dword ptr [rax+rax+00h]
0x18001043e  mov     r13d, 0C0000034h
0x180010444  mov     ebx, eax
0x180010446  cmp     eax, r13d
0x180010449  jnz     loc_180010275
0x18001044f  test    dil, dil
0x180010452  jnz     loc_180010275
0x180010458  xorps   xmm0, xmm0
0x18001045b  mov     dword ptr [rbp+4Fh+KeyHandle], esi
0x18001045e  movups  xmmword ptr [rbp+4Fh+var_B0.ObjectName], xmm0
0x180010462  xor     eax, eax
0x180010464  mov     [rbp+4Fh+Handle], rsi
0x180010468  movups  xmmword ptr [rbp+4Fh+var_B0+1Ch], xmm0
0x18001046c  movups  xmmword ptr [rbp+4Fh+var_B0.Length], xmm0
0x180010470  movaps  xmm0, xmmword ptr [rsp+120h+Destination.Length]
0x180010475  movd    eax, xmm0
0x180010479  movdqa  [rbp+4Fh+var_70], xmm0
0x18001047e  psrldq  xmm0, 8
0x180010483  movzx   ecx, ax
0x180010486  movq    rax, xmm0
0x18001048b  shr     rcx, 1
0x18001048e  cmp     word ptr [rax+rcx*2], 5Ch ; '\'
0x180010493  jz      short loc_1800104BE
0x180010495  mov     rdx, qword ptr [rbp+4Fh+var_70+8]
0x180010499  mov     r13d, 2
0x18001049f  movzx   ecx, word ptr [rbp+4Fh+var_70]
0x1800104a3  sub     cx, r13w
0x1800104a7  movzx   eax, cx
0x1800104aa  shr     rax, 1
0x1800104ad  mov     word ptr [rbp+4Fh+var_70], cx
0x1800104b1  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x1800104b6  jnz     short loc_1800104A3
0x1800104b8  mov     r13d, 0C0000034h
0x1800104be  lea     rax, [rbp+4Fh+var_70]
0x1800104c2  mov     [rbp+4Fh+var_B0.Length], 30h ; '0'
0x1800104c9  mov     [rbp+4Fh+var_B0.ObjectName], rax
0x1800104cd  lea     r8, [rbp+4Fh+var_B0]; ObjectAttributes
0x1800104d1  lea     rax, [rbp+4Fh+KeyHandle]
0x1800104d5  mov     [rbp+4Fh+var_B0.RootDirectory], rsi
0x1800104d9  mov     [rsp+120h+Disposition], rax; Disposition
0x1800104de  lea     rcx, [rbp+4Fh+Handle]; KeyHandle
0x1800104e2  xorps   xmm0, xmm0
0x1800104e5  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x1800104e9  xor     r9d, r9d; TitleIndex
0x1800104ec  mov     [rsp+120h+Class], rsi; Class
0x1800104f1  mov     edx, r14d; DesiredAccess
0x1800104f4  mov     [rbp+4Fh+var_B0.Attributes], r15d
0x1800104f8  movdqu  xmmword ptr [rbp+4Fh+var_B0.SecurityDescriptor], xmm0
0x1800104fd  call    cs:__imp_NtCreateKey
0x180010504  nop     dword ptr [rax+rax+00h]
0x180010509  test    eax, eax
0x18001050b  js      loc_180010275
0x180010511  mov     rcx, [rbp+4Fh+Handle]; Handle
0x180010515  call    cs:__imp_NtClose
0x18001051c  nop     dword ptr [rax+rax+00h]
0x180010521  lea     rax, [rbp+4Fh+arg_8]
0x180010525  xor     r9d, r9d; TitleIndex
0x180010528  mov     [rsp+120h+Disposition], rax; Disposition
0x18001052d  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x180010531  mov     [rsp+120h+CreateOptions], esi; CreateOptions
0x180010535  mov     edx, r14d; DesiredAccess
0x180010538  mov     rcx, r12; KeyHandle
0x18001053b  mov     [rsp+120h+Class], rsi; Class
0x180010540  mov     dil, 1
0x180010543  call    cs:__imp_NtCreateKey
0x18001054a  nop     dword ptr [rax+rax+00h]
0x18001054f  jmp     loc_180010444
0x180010554  mov     eax, 0C0000022h
0x180010559  jmp     loc_180010297
0x18001055e  movzx   eax, word ptr [r15]
0x180010562  mov     dil, 1
0x180010565  add     eax, 2
0x180010568  add     edx, eax
  ... truncated ...
```
