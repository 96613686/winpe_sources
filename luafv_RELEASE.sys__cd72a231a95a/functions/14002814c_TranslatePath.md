# TranslatePath

- ea: `0x14002814c`
- end: `0x14002835c`
- name: `TranslatePath`
- size: `528`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _UNICODE_STRING *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140028364`

## callees

- `0x14001b650`
- `0x14001dd40`
- `0x1400219ac`
- `0x14002814c`
- `0x140028f24`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002830c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14002830c`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140028208`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14002829f`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x140028208`
- `ntoskrnl!ZwOpenSymbolicLinkObject` at `0x14002829f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028257`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400282f4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140028257`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400282f4`
- `ntoskrnl!ZwClose` at `0x14002827e`
- `ntoskrnl!ZwClose` at `0x14002832b`
- `ntoskrnl!ZwClose` at `0x14002827e`
- `ntoskrnl!ZwClose` at `0x14002832b`

## pseudocode

```c
__int64 __fastcall TranslatePath(unsigned __int16 *a1, struct _UNICODE_STRING *a2, __int64 a3)
{
  __int16 v5; // dx
  unsigned __int64 v7; // rcx
  char v8; // r14
  __int64 v9; // rax
  unsigned int Length; // edx
  char *Pool; // rax
  int v12; // ebx
  NTSTATUS v13; // eax
  unsigned int v14; // edx
  char *v15; // rax
  UNICODE_STRING SourceString; // [rsp+20h] [rbp-39h] BYREF
  __int128 v18; // [rsp+30h] [rbp-29h] BYREF
  UNICODE_STRING LinkTarget; // [rsp+40h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  void *LinkHandle; // [rsp+C0h] [rbp+67h] BYREF

  LinkHandle = 0;
  v5 = *a1;
  v7 = (unsigned __int64)*a1 >> 1;
  v8 = 0;
  memset(&ObjectAttributes, 0, 44);
  v9 = *((_QWORD *)a1 + 1);
  LinkTarget = 0;
  v18 = 0;
  SourceString = 0;
  if ( *(_WORD *)(v9 + 2 * v7 - 2) == 92 )
    *a1 = v5 - 2;
  v18 = *(_OWORD *)a1;
  while ( 1 )
  {
    if ( !LuafvSplitPathLeft((unsigned __int16 *)&v18, (__int64)&SourceString) || !(_WORD)v18 )
    {
      v12 = -1073741823;
      goto LABEL_23;
    }
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&v18;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes) >= 0 )
      break;
    LinkHandle = 0;
  }
  if ( !a3 )
    goto LABEL_12;
  Length = SourceString.Length;
  *(_WORD *)(a3 + 2) = SourceString.Length;
  Pool = LuafvAllocatePool(1, Length, 1);
  *(_QWORD *)(a3 + 8) = Pool;
  if ( Pool )
  {
    v8 = 1;
    RtlCopyUnicodeString((PUNICODE_STRING)a3, &SourceString);
LABEL_12:
    while ( 1 )
    {
      v12 = QuerySymbolicLink(LinkHandle, &LinkTarget);
      if ( v12 < 0 )
        break;
      ZwClose(LinkHandle);
      ObjectAttributes.ObjectName = &LinkTarget;
      v13 = ZwOpenSymbolicLinkObject(&LinkHandle, 1u, &ObjectAttributes);
      v12 = v13;
      if ( v13 < 0 )
      {
        LinkHandle = 0;
        if ( v13 != -1073741788 )
          goto LABEL_26;
        if ( a3 )
          v14 = LinkTarget.Length;
        else
          v14 = LinkTarget.Length + SourceString.Length;
        a2->MaximumLength = v14;
        v15 = LuafvAllocatePool(1, v14, 1);
        a2->Buffer = (PWSTR)v15;
        if ( v15 )
        {
          RtlCopyUnicodeString(a2, &LinkTarget);
          if ( !a3 )
            RtlAppendUnicodeStringToString(a2, &SourceString);
          v12 = 0;
          break;
        }
        goto LABEL_10;
      }
    }
  }
  else
  {
LABEL_10:
    v12 = -1073741670;
  }
LABEL_23:
  if ( LinkHandle )
    ZwClose(LinkHandle);
  if ( v12 < 0 )
  {
LABEL_26:
    if ( v8 )
      LuafvFreePool(*(_QWORD *)(a3 + 8));
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14002814c  push    rbp
0x14002814e  push    rbx
0x14002814f  push    rsi
0x140028150  push    rdi
0x140028151  push    r14
0x140028153  push    r15
0x140028155  lea     rbp, [rsp-2Fh]
0x14002815a  sub     rsp, 88h
0x140028161  xorps   xmm0, xmm0
0x140028164  xor     r15d, r15d
0x140028167  xor     eax, eax
0x140028169  mov     [rbp+57h+LinkHandle], r15
0x14002816d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140028171  mov     rdi, r8
0x140028174  mov     rsi, rdx
0x140028177  movzx   edx, word ptr [rcx]
0x14002817a  mov     r8, rcx
0x14002817d  mov     ecx, edx
0x14002817f  xorps   xmm1, xmm1
0x140028182  shr     rcx, 1
0x140028185  mov     r14b, r15b
0x140028188  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14002818c  mov     rax, [r8+8]
0x140028190  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140028194  movups  xmmword ptr [rbp+57h+LinkTarget.Length], xmm0
0x140028198  movups  [rbp+57h+var_80], xmm1
0x14002819c  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x1400281a0  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400281a6  jnz     short loc_1400281B0
0x1400281a8  sub     dx, 2
0x1400281ac  mov     [r8], dx
0x1400281b0  movups  xmm0, xmmword ptr [r8]
0x1400281b4  movdqu  [rbp+57h+var_80], xmm0
0x1400281b9  lea     rdx, [rbp+57h+SourceString]
0x1400281bd  lea     rcx, [rbp+57h+var_80]
0x1400281c1  call    LuafvSplitPathLeft
0x1400281c6  test    al, al
0x1400281c8  jz      loc_14002831D
0x1400281ce  cmp     word ptr [rbp+57h+var_80], r15w
0x1400281d3  jz      loc_14002831D
0x1400281d9  lea     rax, [rbp+57h+var_80]
0x1400281dd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400281e4  xorps   xmm0, xmm0
0x1400281e7  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400281eb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400281ef  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1400281f3  mov     edx, 1; DesiredAccess
0x1400281f8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1400281ff  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140028203  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028208  call    cs:__imp_ZwOpenSymbolicLinkObject
0x14002820f  nop     dword ptr [rax+rax+00h]
0x140028214  test    eax, eax
0x140028216  jns     short loc_14002821E
0x140028218  mov     [rbp+57h+LinkHandle], r15
0x14002821c  jmp     short loc_1400281B9
0x14002821e  test    rdi, rdi
0x140028221  jz      short loc_140028263
0x140028223  movzx   eax, [rbp+57h+SourceString.Length]
0x140028227  mov     r8b, 1
0x14002822a  mov     edx, eax
0x14002822c  mov     [rdi+2], ax
0x140028230  mov     ecx, 1
0x140028235  call    LuafvAllocatePool
0x14002823a  mov     [rdi+8], rax
0x14002823e  test    rax, rax
0x140028241  jnz     short loc_14002824D
0x140028243  mov     ebx, 0C000009Ah
0x140028248  jmp     loc_140028322
0x14002824d  lea     rdx, [rbp+57h+SourceString]; SourceString
0x140028251  mov     rcx, rdi; DestinationString
0x140028254  mov     r14b, 1
0x140028257  call    cs:__imp_RtlCopyUnicodeString
0x14002825e  nop     dword ptr [rax+rax+00h]
0x140028263  mov     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x140028267  lea     rdx, [rbp+57h+LinkTarget]; LinkTarget
0x14002826b  call    QuerySymbolicLink
0x140028270  mov     ebx, eax
0x140028272  test    eax, eax
0x140028274  js      loc_140028322
0x14002827a  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x14002827e  call    cs:__imp_ZwClose
0x140028285  nop     dword ptr [rax+rax+00h]
0x14002828a  lea     rax, [rbp+57h+LinkTarget]
0x14002828e  mov     edx, 1; DesiredAccess
0x140028293  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140028297  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002829b  lea     rcx, [rbp+57h+LinkHandle]; LinkHandle
0x14002829f  call    cs:__imp_ZwOpenSymbolicLinkObject
0x1400282a6  nop     dword ptr [rax+rax+00h]
0x1400282ab  mov     ebx, eax
0x1400282ad  test    eax, eax
0x1400282af  jns     short loc_140028263
0x1400282b1  mov     [rbp+57h+LinkHandle], r15
0x1400282b5  cmp     eax, 0C0000024h
0x1400282ba  jnz     short loc_14002833B
0x1400282bc  movzx   eax, [rbp+57h+LinkTarget.Length]
0x1400282c0  test    rdi, rdi
0x1400282c3  jnz     short loc_1400282CD
0x1400282c5  movzx   edx, [rbp+57h+SourceString.Length]
0x1400282c9  add     edx, eax
0x1400282cb  jmp     short loc_1400282CF
0x1400282cd  mov     edx, eax
0x1400282cf  mov     r8b, 1
0x1400282d2  mov     [rsi+2], dx
0x1400282d6  mov     ecx, 1
0x1400282db  call    LuafvAllocatePool
0x1400282e0  mov     [rsi+8], rax
0x1400282e4  test    rax, rax
0x1400282e7  jz      loc_140028243
0x1400282ed  lea     rdx, [rbp+57h+LinkTarget]; SourceString
0x1400282f1  mov     rcx, rsi; DestinationString
0x1400282f4  call    cs:__imp_RtlCopyUnicodeString
0x1400282fb  nop     dword ptr [rax+rax+00h]
0x140028300  test    rdi, rdi
0x140028303  jnz     short loc_140028318
0x140028305  lea     rdx, [rbp+57h+SourceString]; Source
0x140028309  mov     rcx, rsi; Destination
0x14002830c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140028313  nop     dword ptr [rax+rax+00h]
0x140028318  mov     ebx, r15d
0x14002831b  jmp     short loc_140028322
0x14002831d  mov     ebx, 0C0000001h
0x140028322  mov     rcx, [rbp+57h+LinkHandle]; Handle
0x140028326  test    rcx, rcx
0x140028329  jz      short loc_140028337
0x14002832b  call    cs:__imp_ZwClose
0x140028332  nop     dword ptr [rax+rax+00h]
0x140028337  test    ebx, ebx
0x140028339  jns     short loc_140028349
0x14002833b  test    r14b, r14b
0x14002833e  jz      short loc_140028349
0x140028340  mov     rcx, [rdi+8]
0x140028344  call    LuafvFreePool
0x140028349  mov     eax, ebx
0x14002834b  add     rsp, 88h
0x140028352  pop     r15
0x140028354  pop     r14
0x140028356  pop     rdi
0x140028357  pop     rsi
0x140028358  pop     rbx
0x140028359  pop     rbp
0x14002835a  retn
```
