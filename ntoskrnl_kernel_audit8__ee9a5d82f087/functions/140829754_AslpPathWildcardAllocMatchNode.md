# AslpPathWildcardAllocMatchNode

- ea: `0x140829754`
- end: `0x14082996d`
- name: `AslpPathWildcardAllocMatchNode`
- size: `537`
- prototype: `__int64 __usercall@<rax>(PUNICODE_STRING DestinationString@<rcx>, PCUNICODE_STRING SourceString@<rdx>, NTSTRSAFE_PCWSTR pszSrc, __int16)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14074209c`
- `0x1407431f8`

## callees

- `0x1404021a0`
- `0x1404131d4`
- `0x140456670`
- `0x1406ce5a4`
- `0x1406dda40`
- `0x140743950`
- `0x140829754`
- `0x1408bf658`
- `0x1408c2f88`

## string_xrefs

- `0x14082992a`: `Failed to open dir [%x]`
- `0x140829863`: `RtlUnicodeStringCopy failed [%x]`
- `0x140829937`: `AslpPathWildcardAllocMatchNode`

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
0x140829754  mov     [rsp-18h+arg_8], rbx
0x140829759  mov     [rsp-18h+arg_10], rdi
0x14082975e  push    rbp
0x14082975f  push    r14
0x140829761  push    r15
0x140829763  mov     rbp, rsp
0x140829766  sub     rsp, 70h
0x14082976a  xorps   xmm0, xmm0
0x14082976d  xor     eax, eax
0x14082976f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140829773  xor     r15d, r15d
0x140829776  mov     r14, rdx
0x140829779  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14082977d  mov     rdi, rcx
0x140829780  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140829784  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x140829788  mov     [rcx], r15
0x14082978b  mov     [rcx+8], r15
0x14082978f  mov     [rcx+18h], r15
0x140829793  jmp     short loc_140829799
0x140829795  add     r8, 2
0x140829799  mov     [rcx+10h], r8
0x14082979d  cmp     [r8], r15w
0x1408297a1  jnz     short loc_140829795
0x1408297a3  lea     rax, [r8+2]
0x1408297a7  mov     [rcx+10h], rax
0x1408297ab  cmp     [rax], r15w
0x1408297af  jnz     short loc_1408297C7
0x1408297b1  neg     r9d
0x1408297b4  sbb     ebx, ebx
0x1408297b6  and     ebx, 0FFFFFE47h
0x1408297bc  add     ebx, 0C0000273h
0x1408297c2  jmp     loc_14082994C
0x1408297c7  test    r9d, r9d
0x1408297ca  jnz     short loc_1408297D6
0x1408297cc  mov     ebx, 0C0000103h
0x1408297d1  jmp     loc_14082994C
0x1408297d6  movzx   ecx, word ptr [rdx]; usAugend
0x1408297d9  lea     r8, [rbp+pusResult]; pusResult
0x1408297dd  movzx   edx, [rbp+arg_28]; usAddend
0x1408297e1  mov     [rbp+pusResult], cx
0x1408297e5  call    RtlUShortAdd
0x1408297ea  mov     ebx, eax
0x1408297ec  test    eax, eax
0x1408297ee  jns     short loc_140829802
0x1408297f0  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1408297f7  mov     r8d, 0B46h
0x1408297fd  jmp     loc_140829937
0x140829802  movzx   ecx, [rbp+pusResult]; usAugend
0x140829806  lea     r8, [rbp+pusResult]; pusResult
0x14082980a  mov     edx, 4; usAddend
0x14082980f  call    RtlUShortAdd
0x140829814  mov     ebx, eax
0x140829816  test    eax, eax
0x140829818  jns     short loc_14082982C
0x14082981a  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x140829821  mov     r8d, 0B4Ch
0x140829827  jmp     loc_140829937
0x14082982c  movzx   ecx, [rbp+pusResult]
0x140829830  mov     edx, ecx
0x140829832  mov     [rdi+2], cx
0x140829836  mov     [rdi], r15w
0x14082983a  call    AslAlloc
0x14082983f  mov     [rdi+8], rax
0x140829843  test    rax, rax
0x140829846  jnz     short loc_140829852
0x140829848  mov     ebx, 0C0000017h
0x14082984d  jmp     loc_14082994C
0x140829852  mov     rdx, r14; SourceString
0x140829855  mov     rcx, rdi; DestinationString
0x140829858  call    RtlUnicodeStringCopy
0x14082985d  mov     ebx, eax
0x14082985f  test    eax, eax
0x140829861  jns     short loc_140829875
0x140829863  lea     r9, aRtlunicodestri_7; "RtlUnicodeStringCopy failed [%x]"
0x14082986a  mov     r8d, 0B5Bh
0x140829870  jmp     loc_140829937
0x140829875  movzx   ecx, word ptr [rdi]
0x140829878  mov     rax, [rdi+8]
0x14082987c  shr     rcx, 1
0x14082987f  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x140829885  jz      short loc_1408298AE
0x140829887  lea     rdx, asc_1400211F4; "\\"
0x14082988e  mov     rcx, rdi; DestinationString
0x140829891  call    RtlUnicodeStringCatString
0x140829896  mov     ebx, eax
0x140829898  test    eax, eax
0x14082989a  jns     short loc_1408298AE
0x14082989c  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x1408298a3  mov     r8d, 0B6Bh
0x1408298a9  jmp     loc_140829937
0x1408298ae  mov     rdx, [rbp+pszSrc]; pszSrc
0x1408298b2  test    rdx, rdx
0x1408298b5  jz      short loc_1408298E0
0x1408298b7  cmp     [rbp+arg_28], r15w
0x1408298bc  jbe     short loc_1408298E0
0x1408298be  movzx   r8d, [rbp+arg_28]; cbToAppend
0x1408298c3  mov     rcx, rdi; DestinationString
0x1408298c6  call    RtlUnicodeStringCbCatStringN
0x1408298cb  mov     ebx, eax
0x1408298cd  test    eax, eax
0x1408298cf  jns     short loc_1408298E0
0x1408298d1  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x1408298d8  mov     r8d, 0B73h
0x1408298de  jmp     short loc_140829937
0x1408298e0  xorps   xmm0, xmm0
0x1408298e3  mov     [rsp+70h+OpenOptions], 21h ; '!'; OpenOptions
0x1408298eb  lea     rcx, [rdi+18h]; FileHandle
0x1408298ef  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1408298f6  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x1408298fa  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x1408298fe  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140829902  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140829909  mov     edx, 100001h; DesiredAccess
0x14082990e  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x140829912  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140829917  mov     [rsp+70h+ShareAccess], 1; ShareAccess
0x14082991f  call    ZwOpenFile
0x140829924  mov     ebx, eax
0x140829926  test    eax, eax
0x140829928  jns     short loc_140829954
0x14082992a  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x140829931  mov     r8d, 0B81h
0x140829937  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x14082993e  mov     [rsp+70h+ShareAccess], eax
0x140829942  mov     ecx, 1
0x140829947  call    AslLogCallPrintf
0x14082994c  mov     rcx, rdi
0x14082994f  call    AslpPathWildcardFreeMatchNode
0x140829954  lea     r11, [rsp+70h+var_s0]
0x140829959  mov     eax, ebx
0x14082995b  mov     rbx, [r11+28h]
0x14082995f  mov     rdi, [r11+30h]
0x140829963  mov     rsp, r11
0x140829966  pop     r15
0x140829968  pop     r14
0x14082996a  pop     rbp
0x14082996b  retn
```
