# TranslateSisFsctlName

- ea: `0x140047558`
- end: `0x140047960`
- name: `TranslateSisFsctlName`
- size: `1032`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PUNICODE_STRING DestinationString, __int64, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140045410`

## callees

- `0x140025d80`
- `0x140047558`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140047745`
- `ntoskrnl!ExAllocatePool2` at `0x140047745`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400475b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400475b0`
- `ntoskrnl!wcschr` at `0x140047607`
- `ntoskrnl!wcschr` at `0x1400478a4`
- `ntoskrnl!wcschr` at `0x140047607`
- `ntoskrnl!wcschr` at `0x1400478a4`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x14004767e`
- `ntoskrnl!ZwOpenDirectoryObject` at `0x14004767e`
- `ntoskrnl!ZwClose` at `0x140047694`
- `ntoskrnl!ZwClose` at `0x140047786`
- `ntoskrnl!ZwClose` at `0x14004780b`
- `ntoskrnl!ZwClose` at `0x140047694`
- `ntoskrnl!ZwClose` at `0x140047786`
- `ntoskrnl!ZwClose` at `0x14004780b`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400476d5`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x1400476d5`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400476fe`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140047774`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x1400476fe`
- `ntoskrnl!ZwQuerySymbolicLinkObject` at `0x140047774`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140047862`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400478e6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140047862`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400478e6`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140047916`
- `ntoskrnl!RtlCreateUnicodeString` at `0x140047916`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047826`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047936`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400477e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047826`
- `ntoskrnl!ExFreePoolWithTag` at `0x140047936`

## pseudocode

```c
__int64 __fastcall TranslateSisFsctlName(
        PCWSTR SourceString,
        PUNICODE_STRING DestinationString,
        __int64 a3,
        const UNICODE_STRING *a4)
{
  UNICODE_STRING *v4; // rsi
  wchar_t *Buffer; // rdi
  wchar_t v8; // ax
  wchar_t *v9; // r15
  wchar_t *v10; // rbx
  const wchar_t *i; // rdi
  wchar_t *v12; // rax
  wchar_t *v13; // rsi
  unsigned __int16 Length; // ax
  unsigned int v15; // r12d
  NTSTATUS v16; // eax
  NTSTATUS v17; // ebx
  NTSTATUS v18; // eax
  unsigned int v19; // r14d
  wchar_t *Pool2; // rax
  void *v21; // rcx
  unsigned __int64 v22; // rax
  const WCHAR *v23; // rdx
  ULONG ReturnedLength; // [rsp+20h] [rbp-60h] BYREF
  void *DirectoryHandle; // [rsp+28h] [rbp-58h] BYREF
  UNICODE_STRING LinkTarget; // [rsp+30h] [rbp-50h] BYREF
  UNICODE_STRING DestinationStringa; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  v4 = DestinationString;
  DirectoryHandle = 0;
  ReturnedLength = 0;
  DestinationStringa = 0;
  LinkTarget = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationStringa, SourceString);
  Buffer = DestinationStringa.Buffer;
  if ( !DestinationStringa.Buffer )
    return 3221225485LL;
  v8 = *DestinationStringa.Buffer;
  v9 = 0;
  if ( *DestinationStringa.Buffer != 92 || (v10 = DestinationStringa.Buffer + 1, DestinationStringa.Buffer[1] != 92) )
  {
    while ( 1 )
    {
      if ( v8 != 92 )
        goto LABEL_44;
      for ( i = Buffer + 1; ; i = v13 + 1 )
      {
        v12 = wcschr(i, 0x5Cu);
        v13 = v12;
        if ( v12 )
        {
          Length = 2 * (v12 - DestinationStringa.Buffer);
          LinkTarget.MaximumLength = Length;
          LinkTarget.Length = Length;
        }
        else
        {
          LinkTarget.MaximumLength = DestinationStringa.Length;
          Length = DestinationStringa.Length;
          LinkTarget.Length = DestinationStringa.Length;
        }
        LinkTarget.Buffer = DestinationStringa.Buffer;
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.ObjectName = &LinkTarget;
        ObjectAttributes.Attributes = 576;
        v15 = DestinationStringa.Length - Length + 2;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v16 = ZwOpenDirectoryObject(&DirectoryHandle, 2u, &ObjectAttributes);
        v17 = v16;
        if ( v16 < 0 )
          break;
        ZwClose(DirectoryHandle);
        if ( !v13 )
        {
          v17 = -1073741788;
          goto LABEL_45;
        }
      }
      if ( v16 != -1073741788 )
        goto LABEL_45;
      v18 = ZwOpenSymbolicLinkObject(&DirectoryHandle, 1u, &ObjectAttributes);
      v17 = v18;
      if ( v18 < 0 )
        break;
      *(_DWORD *)&LinkTarget.Length = 0;
      v17 = ZwQuerySymbolicLinkObject(DirectoryHandle, &LinkTarget, &ReturnedLength);
      if ( (int)(v17 + 0x80000000) >= 0 && v17 != -1073741789 )
      {
        v21 = DirectoryHandle;
LABEL_28:
        ZwClose(v21);
        goto LABEL_45;
      }
      v19 = v15 + ReturnedLength;
      if ( v15 + ReturnedLength > 0xFFFE )
      {
        v17 = -1073741811;
        goto LABEL_45;
      }
      Pool2 = (wchar_t *)ExAllocatePool2(258, v19, 1934456914);
      v21 = DirectoryHandle;
      Buffer = Pool2;
      if ( !Pool2 )
      {
        v17 = -1073741670;
        goto LABEL_28;
      }
      LinkTarget.MaximumLength = ReturnedLength;
      LinkTarget.Buffer = Pool2;
      v17 = ZwQuerySymbolicLinkObject(DirectoryHandle, &LinkTarget, 0);
      ZwClose(DirectoryHandle);
      if ( v17 < 0 )
        goto LABEL_30;
      if ( LinkTarget.Length > ReturnedLength )
      {
        v17 = -1073741773;
LABEL_30:
        ExFreePoolWithTag(Buffer, 0);
        goto LABEL_45;
      }
      if ( v13 )
        memmove((char *)Buffer + LinkTarget.Length, v13, v15);
      DestinationStringa.MaximumLength = v19;
      DestinationStringa.Buffer = Buffer;
      DestinationStringa.Length = v19 - 2;
      if ( v9 )
        ExFreePoolWithTag(v9, 0);
      v8 = *Buffer;
      v9 = Buffer;
    }
    if ( v18 != -1073741788 )
      goto LABEL_45;
    if ( !RtlPrefixUnicodeString((PCUNICODE_STRING)(a3 + 360), &DestinationStringa, 1u) )
      goto LABEL_44;
    Buffer = DestinationStringa.Buffer;
    v10 = (wchar_t *)((char *)DestinationStringa.Buffer + ((unsigned __int64)*(unsigned __int16 *)(a3 + 360) >> 1));
    if ( *v10 != 92 )
      goto LABEL_44;
    if ( v10[1] == 59 )
    {
      v10 = wcschr(v10 + 1, 0x5Cu);
      if ( !v10 )
        goto LABEL_44;
      Buffer = DestinationStringa.Buffer;
    }
    v4 = DestinationString;
  }
  DestinationStringa.Buffer = v10;
  DestinationStringa.Length += -2 * (v10 - Buffer);
  if ( !RtlPrefixUnicodeString(a4, &DestinationStringa, 1u)
    || (v22 = (unsigned __int64)a4->Length >> 1, v10[v22] != 92)
    || (v23 = &v10[v22 + 1], !*v23) )
  {
LABEL_44:
    v17 = -1073741773;
    goto LABEL_45;
  }
  RtlCreateUnicodeString(v4, v23);
  v17 = 0;
LABEL_45:
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x140047558  mov     [rsp-38h+arg_0], rbx
0x14004755d  mov     [rsp-38h+arg_10], r8
0x140047562  mov     [rsp-38h+arg_8], rdx
0x140047567  push    rbp
0x140047568  push    rsi
0x140047569  push    rdi
0x14004756a  push    r12
0x14004756c  push    r13
0x14004756e  push    r14
0x140047570  push    r15
0x140047572  mov     rbp, rsp
0x140047575  sub     rsp, 80h
0x14004757c  xorps   xmm0, xmm0
0x14004757f  mov     rsi, rdx
0x140047582  mov     rdx, rcx; SourceString
0x140047585  xorps   xmm1, xmm1
0x140047588  xor     r14d, r14d
0x14004758b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004758f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140047593  xor     eax, eax
0x140047595  mov     [rbp+DirectoryHandle], r14
0x140047599  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14004759d  mov     r13, r9
0x1400475a0  mov     [rbp+ReturnedLength], r14d
0x1400475a4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400475a8  movups  xmmword ptr [rbp+LinkTarget.Length], xmm1
0x1400475ac  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400475b0  call    cs:__imp_RtlInitUnicodeString
0x1400475b7  nop     dword ptr [rax+rax+00h]
0x1400475bc  mov     rdi, [rbp+DestinationString.Buffer]
0x1400475c0  test    rdi, rdi
0x1400475c3  jnz     short loc_1400475CF
0x1400475c5  mov     eax, 0C000000Dh
0x1400475ca  jmp     loc_140047944
0x1400475cf  movzx   eax, word ptr [rdi]
0x1400475d2  mov     r12d, 5Ch ; '\'
0x1400475d8  mov     r15, r14
0x1400475db  cmp     ax, r12w
0x1400475df  jnz     short loc_1400475EF
0x1400475e1  lea     rbx, [rdi+2]
0x1400475e5  cmp     [rbx], r12w
0x1400475e9  jz      loc_1400478C0
0x1400475ef  mov     ebx, 2
0x1400475f4  cmp     ax, r12w
0x1400475f8  jnz     loc_140047927
0x1400475fe  add     rdi, rbx
0x140047601  mov     edx, r12d; Ch
0x140047604  mov     rcx, rdi; Str
0x140047607  call    cs:__imp_wcschr
0x14004760e  nop     dword ptr [rax+rax+00h]
0x140047613  mov     rdx, [rbp+DestinationString.Buffer]
0x140047617  mov     rsi, rax
0x14004761a  movzx   ecx, [rbp+DestinationString.Length]
0x14004761e  test    rax, rax
0x140047621  jnz     short loc_140047630
0x140047623  mov     [rbp+LinkTarget.MaximumLength], cx
0x140047627  movzx   eax, cx
0x14004762a  mov     [rbp+LinkTarget.Length], cx
0x14004762e  jmp     short loc_140047641
0x140047630  sub     rax, rdx
0x140047633  sar     rax, 1
0x140047636  add     ax, ax
0x140047639  mov     [rbp+LinkTarget.MaximumLength], ax
0x14004763d  mov     [rbp+LinkTarget.Length], ax
0x140047641  movzx   eax, ax
0x140047644  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140047648  mov     r12d, ecx
0x14004764b  mov     [rbp+LinkTarget.Buffer], rdx
0x14004764f  sub     r12d, eax
0x140047652  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140047659  lea     rax, [rbp+LinkTarget]
0x14004765d  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x140047661  xorps   xmm0, xmm0
0x140047664  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140047668  mov     edx, ebx; DesiredAccess
0x14004766a  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140047671  lea     rcx, [rbp+DirectoryHandle]; DirectoryHandle
0x140047675  add     r12d, 2
0x140047679  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14004767e  call    cs:__imp_ZwOpenDirectoryObject
0x140047685  nop     dword ptr [rax+rax+00h]
0x14004768a  mov     ebx, eax
0x14004768c  test    eax, eax
0x14004768e  js      short loc_1400476BB
0x140047690  mov     rcx, [rbp+DirectoryHandle]; Handle
0x140047694  call    cs:__imp_ZwClose
0x14004769b  nop     dword ptr [rax+rax+00h]
0x1400476a0  test    rsi, rsi
0x1400476a3  jz      loc_1400477FD
0x1400476a9  mov     ebx, 2
0x1400476ae  lea     rdi, [rsi+2]
0x1400476b2  lea     r12d, [rbx+5Ah]
0x1400476b6  jmp     loc_140047601
0x1400476bb  mov     edi, 0C0000024h
0x1400476c0  cmp     eax, edi
0x1400476c2  jnz     loc_14004792C
0x1400476c8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400476cc  mov     edx, 1; DesiredAccess
0x1400476d1  lea     rcx, [rbp+DirectoryHandle]; LinkHandle
0x1400476d5  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1400476dc  nop     dword ptr [rax+rax+00h]
0x1400476e1  mov     ebx, eax
0x1400476e3  test    eax, eax
0x1400476e5  js      loc_140047848
0x1400476eb  mov     rcx, [rbp+DirectoryHandle]; LinkHandle
0x1400476ef  lea     r8, [rbp+ReturnedLength]; ReturnedLength
0x1400476f3  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x1400476f7  mov     dword ptr [rbp+LinkTarget.Length], 0
0x1400476fe  call    cs:__imp_ZwQuerySymbolicLinkObject
0x140047705  nop     dword ptr [rax+rax+00h]
0x14004770a  mov     ecx, 80000000h
0x14004770f  mov     ebx, eax
0x140047711  add     eax, ecx
0x140047713  test    ecx, eax
0x140047715  jnz     short loc_140047723
0x140047717  cmp     ebx, 0C0000023h
0x14004771d  jnz     loc_140047807
0x140047723  mov     r14d, [rbp+ReturnedLength]
0x140047727  add     r14d, r12d
0x14004772a  cmp     r14d, 0FFFEh
0x140047731  ja      loc_14004783E
0x140047737  mov     edx, r14d
0x14004773a  mov     ecx, 102h
0x14004773f  mov     r8d, 734D7852h
0x140047745  call    cs:__imp_ExAllocatePool2
0x14004774c  nop     dword ptr [rax+rax+00h]
0x140047751  mov     rcx, [rbp+DirectoryHandle]; LinkHandle
0x140047755  mov     rdi, rax
0x140047758  test    rax, rax
0x14004775b  jz      loc_140047837
0x140047761  movzx   eax, word ptr [rbp+ReturnedLength]
0x140047765  lea     rdx, [rbp+LinkTarget]; LinkTarget
0x140047769  xor     r8d, r8d; ReturnedLength
0x14004776c  mov     [rbp+LinkTarget.MaximumLength], ax
0x140047770  mov     [rbp+LinkTarget.Buffer], rdi
0x140047774  call    cs:__imp_ZwQuerySymbolicLinkObject
0x14004777b  nop     dword ptr [rax+rax+00h]
0x140047780  mov     rcx, [rbp+DirectoryHandle]; Handle
0x140047784  mov     ebx, eax
0x140047786  call    cs:__imp_ZwClose
0x14004778d  nop     dword ptr [rax+rax+00h]
0x140047792  test    ebx, ebx
0x140047794  js      loc_140047821
0x14004779a  movzx   eax, [rbp+LinkTarget.Length]
0x14004779e  cmp     eax, [rbp+ReturnedLength]
0x1400477a1  ja      short loc_14004781C
0x1400477a3  test    rsi, rsi
0x1400477a6  jz      short loc_1400477BA
0x1400477a8  movzx   ecx, [rbp+LinkTarget.Length]
0x1400477ac  mov     rdx, rsi; Src
0x1400477af  add     rcx, rdi; void *
0x1400477b2  mov     r8d, r12d; Size
0x1400477b5  call    memmove
0x1400477ba  movzx   eax, r14w
0x1400477be  mov     [rbp+DestinationString.MaximumLength], r14w
0x1400477c3  mov     ebx, 2
0x1400477c8  mov     [rbp+DestinationString.Buffer], rdi
0x1400477cc  sub     ax, bx
0x1400477cf  xor     r14d, r14d
0x1400477d2  mov     [rbp+DestinationString.Length], ax
0x1400477d6  test    r15, r15
0x1400477d9  jz      short loc_1400477EC
0x1400477db  xor     edx, edx; Tag
0x1400477dd  mov     rcx, r15; P
0x1400477e0  call    cs:__imp_ExFreePoolWithTag
0x1400477e7  nop     dword ptr [rax+rax+00h]
0x1400477ec  movzx   eax, word ptr [rdi]
0x1400477ef  mov     r15, rdi
0x1400477f2  mov     r12d, 5Ch ; '\'
0x1400477f8  jmp     loc_1400475F4
0x1400477fd  mov     ebx, 0C0000024h
0x140047802  jmp     loc_14004792C
0x140047807  mov     rcx, [rbp+DirectoryHandle]; Handle
0x14004780b  call    cs:__imp_ZwClose
0x140047812  nop     dword ptr [rax+rax+00h]
0x140047817  jmp     loc_14004792C
0x14004781c  mov     ebx, 0C0000033h
0x140047821  xor     edx, edx; Tag
0x140047823  mov     rcx, rdi; P
0x140047826  call    cs:__imp_ExFreePoolWithTag
0x14004782d  nop     dword ptr [rax+rax+00h]
0x140047832  jmp     loc_14004792C
0x140047837  mov     ebx, 0C000009Ah
0x14004783c  jmp     short loc_14004780B
0x14004783e  mov     ebx, 0C000000Dh
0x140047843  jmp     loc_14004792C
0x140047848  cmp     eax, edi
0x14004784a  jnz     loc_14004792C
0x140047850  mov     rbx, [rbp+arg_10]
0x140047854  lea     rdx, [rbp+DestinationString]; String2
0x140047858  mov     r8b, 1; CaseInSensitive
0x14004785b  lea     rcx, [rbx+168h]; String1
0x140047862  call    cs:__imp_RtlPrefixUnicodeString
0x140047869  nop     dword ptr [rax+rax+00h]
0x14004786e  test    al, al
0x140047870  jz      loc_140047927
0x140047876  movzx   ebx, word ptr [rbx+168h]
0x14004787d  mov     r12d, 5Ch ; '\'
0x140047883  mov     rdi, [rbp+DestinationString.Buffer]
0x140047887  shr     rbx, 1
0x14004788a  add     rbx, rdi
0x14004788d  cmp     [rbx], r12w
0x140047891  jnz     loc_140047927
0x140047897  lea     rcx, [rbx+2]; Str
0x14004789b  cmp     word ptr [rcx], 3Bh ; ';'
0x14004789f  jnz     short loc_1400478BC
0x1400478a1  mov     edx, r12d; Ch
0x1400478a4  call    cs:__imp_wcschr
0x1400478ab  nop     dword ptr [rax+rax+00h]
0x1400478b0  mov     rbx, rax
0x1400478b3  test    rax, rax
0x1400478b6  jz      short loc_140047927
0x1400478b8  mov     rdi, [rbp+DestinationString.Buffer]
0x1400478bc  mov     rsi, [rbp+arg_8]
0x1400478c0  mov     eax, 0FFFEh
0x1400478c5  mov     [rbp+DestinationString.Buffer], rbx
0x1400478c9  mov     rcx, rbx
0x1400478cc  lea     rdx, [rbp+DestinationString]; String2
0x1400478d0  sub     rcx, rdi
0x1400478d3  mov     r8b, 1; CaseInSensitive
0x1400478d6  sar     rcx, 1
0x1400478d9  movzx   ecx, cx
0x1400478dc  imul    ecx, eax
0x1400478df  add     [rbp+DestinationString.Length], cx
0x1400478e3  mov     rcx, r13; String1
0x1400478e6  call    cs:__imp_RtlPrefixUnicodeString
0x1400478ed  nop     dword ptr [rax+rax+00h]
0x1400478f2  test    al, al
0x1400478f4  jz      short loc_140047927
0x1400478f6  movzx   eax, word ptr [r13+0]
0x1400478fb  shr     rax, 1
0x1400478fe  cmp     [rbx+rax*2], r12w
0x140047903  jnz     short loc_140047927
0x140047905  lea     rdx, [rax+1]
0x140047909  lea     rdx, [rbx+rdx*2]; SourceString
0x14004790d  cmp     [rdx], r14w
0x140047911  jz      short loc_140047927
0x140047913  mov     rcx, rsi; DestinationString
0x140047916  call    cs:__imp_RtlCreateUnicodeString
0x14004791d  nop     dword ptr [rax+rax+00h]
0x140047922  mov     ebx, r14d
0x140047925  jmp     short loc_14004792C
0x140047927  mov     ebx, 0C0000033h
0x14004792c  test    r15, r15
0x14004792f  jz      short loc_140047942
0x140047931  xor     edx, edx; Tag
0x140047933  mov     rcx, r15; P
0x140047936  call    cs:__imp_ExFreePoolWithTag
0x14004793d  nop     dword ptr [rax+rax+00h]
0x140047942  mov     eax, ebx
0x140047944  mov     rbx, [rsp+80h+arg_0]
0x14004794c  add     rsp, 80h
0x140047953  pop     r15
0x140047955  pop     r14
0x140047957  pop     r13
0x140047959  pop     r12
0x14004795b  pop     rdi
0x14004795c  pop     rsi
0x14004795d  pop     rbp
0x14004795e  retn
```
