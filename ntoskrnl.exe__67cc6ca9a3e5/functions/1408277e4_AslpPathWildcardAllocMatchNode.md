# AslpPathWildcardAllocMatchNode

- ea: `0x1408277e4`
- end: `0x1408279fd`
- name: `AslpPathWildcardAllocMatchNode`
- size: `537`
- prototype: `__int64 __usercall@<rax>(PUNICODE_STRING DestinationString@<rcx>, PCUNICODE_STRING SourceString@<rdx>, NTSTRSAFE_PCWSTR pszSrc, __int16)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14073d8dc`
- `0x14073ea34`

## callees

- `0x1403f2180`
- `0x1404001f4`
- `0x1404432a8`
- `0x1406cb944`
- `0x1406daef0`
- `0x14073f18c`
- `0x1408277e4`
- `0x140979890`
- `0x14097d158`

## string_xrefs

- `0x1408279ba`: `Failed to open dir [%x]`
- `0x1408278f3`: `RtlUnicodeStringCopy failed [%x]`
- `0x1408279c7`: `AslpPathWildcardAllocMatchNode`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        PUNICODE_STRING DestinationString,
        PCUNICODE_STRING SourceString,
        _WORD *a3,
        int a4,
        NTSTRSAFE_PCWSTR pszSrc,
        USHORT a6)
{
  NTSTATUS v8; // ebx
  const char *v9; // r9
  int v10; // r8d
  __int64 v11; // rcx
  __int64 v12; // rdx
  wchar_t *v13; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-40h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  USHORT pusResult; // [rsp+90h] [rbp+20h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)&DestinationString->Length = 0;
  DestinationString->Buffer = 0;
  DestinationString[1].Buffer = 0;
  while ( 1 )
  {
    *(_QWORD *)&DestinationString[1].Length = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *(_QWORD *)&DestinationString[1].Length = a3 + 1;
  if ( !a3[1] )
  {
    v8 = a4 != 0 ? -1073741638 : -1073741197;
LABEL_26:
    AslpPathWildcardFreeMatchNode(DestinationString, SourceString);
    return (unsigned int)v8;
  }
  if ( !a4 )
  {
    v8 = -1073741565;
    goto LABEL_26;
  }
  pusResult = SourceString->Length;
  v8 = RtlUShortAdd(pusResult, a6, &pusResult);
  if ( v8 < 0 )
  {
    v9 = "RtlUShortAdd failed [%x]";
    v10 = 2886;
LABEL_25:
    AslLogCallPrintf(1, (unsigned int)"AslpPathWildcardAllocMatchNode", v10, (_DWORD)v9);
    goto LABEL_26;
  }
  v8 = RtlUShortAdd(pusResult, 4u, &pusResult);
  if ( v8 < 0 )
  {
    v9 = "RtlUShortAdd failed [%x]";
    v10 = 2892;
    goto LABEL_25;
  }
  v11 = pusResult;
  v12 = pusResult;
  DestinationString->MaximumLength = pusResult;
  DestinationString->Length = 0;
  v13 = (wchar_t *)AslAlloc(v11, v12);
  DestinationString->Buffer = v13;
  if ( !v13 )
  {
    v8 = -1073741801;
    goto LABEL_26;
  }
  v8 = RtlUnicodeStringCopy(DestinationString, SourceString);
  if ( v8 < 0 )
  {
    v9 = "RtlUnicodeStringCopy failed [%x]";
    v10 = 2907;
    goto LABEL_25;
  }
  if ( DestinationString->Buffer[((unsigned __int64)DestinationString->Length >> 1) - 1] != 92 )
  {
    v8 = RtlUnicodeStringCatString(DestinationString, L"\\");
    if ( v8 < 0 )
    {
      v9 = "RtlUnicodeStringCatString failed [%x]";
      v10 = 2923;
      goto LABEL_25;
    }
  }
  if ( pszSrc )
  {
    if ( a6 )
    {
      v8 = RtlUnicodeStringCbCatStringN(DestinationString, pszSrc, a6);
      if ( v8 < 0 )
      {
        v9 = "RtlUnicodeStringCbCatStringN failed [%x]";
        v10 = 2931;
        goto LABEL_25;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenFile((PHANDLE)&DestinationString[1].Buffer, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
  if ( v8 < 0 )
  {
    v9 = "Failed to open dir [%x]";
    v10 = 2945;
    goto LABEL_25;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1408277e4  mov     [rsp-18h+arg_8], rbx
0x1408277e9  mov     [rsp-18h+arg_10], rdi
0x1408277ee  push    rbp
0x1408277ef  push    r14
0x1408277f1  push    r15
0x1408277f3  mov     rbp, rsp
0x1408277f6  sub     rsp, 70h
0x1408277fa  xorps   xmm0, xmm0
0x1408277fd  xor     eax, eax
0x1408277ff  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140827803  xor     r15d, r15d
0x140827806  mov     r14, rdx
0x140827809  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14082780d  mov     rdi, rcx
0x140827810  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140827814  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140827818  mov     [rcx], r15
0x14082781b  mov     [rcx+8], r15
0x14082781f  mov     [rcx+18h], r15
0x140827823  jmp     short loc_140827829
0x140827825  add     r8, 2
0x140827829  mov     [rcx+10h], r8
0x14082782d  cmp     [r8], r15w
0x140827831  jnz     short loc_140827825
0x140827833  lea     rax, [r8+2]
0x140827837  mov     [rcx+10h], rax
0x14082783b  cmp     [rax], r15w
0x14082783f  jnz     short loc_140827857
0x140827841  neg     r9d
0x140827844  sbb     ebx, ebx
0x140827846  and     ebx, 0FFFFFE47h
0x14082784c  add     ebx, 0C0000273h
0x140827852  jmp     loc_1408279DC
0x140827857  test    r9d, r9d
0x14082785a  jnz     short loc_140827866
0x14082785c  mov     ebx, 0C0000103h
0x140827861  jmp     loc_1408279DC
0x140827866  movzx   ecx, word ptr [rdx]; usAugend
0x140827869  lea     r8, [rbp+pusResult]; pusResult
0x14082786d  movzx   edx, [rbp+arg_28]; usAddend
0x140827871  mov     [rbp+pusResult], cx
0x140827875  call    RtlUShortAdd
0x14082787a  mov     ebx, eax
0x14082787c  test    eax, eax
0x14082787e  jns     short loc_140827892
0x140827880  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x140827887  mov     r8d, 0B46h
0x14082788d  jmp     loc_1408279C7
0x140827892  movzx   ecx, [rbp+pusResult]; usAugend
0x140827896  lea     r8, [rbp+pusResult]; pusResult
0x14082789a  mov     edx, 4; usAddend
0x14082789f  call    RtlUShortAdd
0x1408278a4  mov     ebx, eax
0x1408278a6  test    eax, eax
0x1408278a8  jns     short loc_1408278BC
0x1408278aa  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1408278b1  mov     r8d, 0B4Ch
0x1408278b7  jmp     loc_1408279C7
0x1408278bc  movzx   ecx, [rbp+pusResult]
0x1408278c0  mov     edx, ecx
0x1408278c2  mov     [rdi+2], cx
0x1408278c6  mov     [rdi], r15w
0x1408278ca  call    AslAlloc
0x1408278cf  mov     [rdi+8], rax
0x1408278d3  test    rax, rax
0x1408278d6  jnz     short loc_1408278E2
0x1408278d8  mov     ebx, 0C0000017h
0x1408278dd  jmp     loc_1408279DC
0x1408278e2  mov     rdx, r14; SourceString
0x1408278e5  mov     rcx, rdi; DestinationString
0x1408278e8  call    RtlUnicodeStringCopy
0x1408278ed  mov     ebx, eax
0x1408278ef  test    eax, eax
0x1408278f1  jns     short loc_140827905
0x1408278f3  lea     r9, aRtlunicodestri_7; "RtlUnicodeStringCopy failed [%x]"
0x1408278fa  mov     r8d, 0B5Bh
0x140827900  jmp     loc_1408279C7
0x140827905  movzx   ecx, word ptr [rdi]
0x140827908  mov     rax, [rdi+8]
0x14082790c  shr     rcx, 1
0x14082790f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140827915  jz      short loc_14082793E
0x140827917  lea     rdx, asc_1400211EC; "\\"
0x14082791e  mov     rcx, rdi; DestinationString
0x140827921  call    RtlUnicodeStringCatString
0x140827926  mov     ebx, eax
0x140827928  test    eax, eax
0x14082792a  jns     short loc_14082793E
0x14082792c  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x140827933  mov     r8d, 0B6Bh
0x140827939  jmp     loc_1408279C7
0x14082793e  mov     rdx, [rbp+pszSrc]; pszSrc
0x140827942  test    rdx, rdx
0x140827945  jz      short loc_140827970
0x140827947  cmp     [rbp+arg_28], r15w
0x14082794c  jbe     short loc_140827970
0x14082794e  movzx   r8d, [rbp+arg_28]; cbToAppend
0x140827953  mov     rcx, rdi; DestinationString
0x140827956  call    RtlUnicodeStringCbCatStringN
0x14082795b  mov     ebx, eax
0x14082795d  test    eax, eax
0x14082795f  jns     short loc_140827970
0x140827961  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x140827968  mov     r8d, 0B73h
0x14082796e  jmp     short loc_1408279C7
0x140827970  xorps   xmm0, xmm0
0x140827973  mov     [rsp+70h+OpenOptions], 21h ; '!'; OpenOptions
0x14082797b  lea     rcx, [rdi+18h]; FileHandle
0x14082797f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140827986  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x14082798a  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x14082798e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140827992  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140827999  mov     edx, 100001h; DesiredAccess
0x14082799e  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x1408279a2  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1408279a7  mov     [rsp+70h+ShareAccess], 1; ShareAccess
0x1408279af  call    ZwOpenFile
0x1408279b4  mov     ebx, eax
0x1408279b6  test    eax, eax
0x1408279b8  jns     short loc_1408279E4
0x1408279ba  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x1408279c1  mov     r8d, 0B81h
0x1408279c7  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x1408279ce  mov     [rsp+70h+ShareAccess], eax
0x1408279d2  mov     ecx, 1
0x1408279d7  call    AslLogCallPrintf
0x1408279dc  mov     rcx, rdi
0x1408279df  call    AslpPathWildcardFreeMatchNode
0x1408279e4  lea     r11, [rsp+70h+var_s0]
0x1408279e9  mov     eax, ebx
0x1408279eb  mov     rbx, [r11+28h]
0x1408279ef  mov     rdi, [r11+30h]
0x1408279f3  mov     rsp, r11
0x1408279f6  pop     r15
0x1408279f8  pop     r14
0x1408279fa  pop     rbp
0x1408279fb  retn
```
