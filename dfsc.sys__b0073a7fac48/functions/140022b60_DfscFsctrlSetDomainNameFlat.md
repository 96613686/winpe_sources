# DfscFsctrlSetDomainNameFlat

- ea: `0x140022b60`
- end: `0x140022cd0`
- name: `DfscFsctrlSetDomainNameFlat`
- size: `368`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140014910`

## callees

- `0x140001010`
- `0x140013100`
- `0x140014268`
- `0x140021fa0`
- `0x140022118`
- `0x140022620`
- `0x140022710`
- `0x140022b60`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140022bd7`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140022bd7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140022c52`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140022c52`

## pseudocode

```c
__int64 __fastcall DfscFsctrlSetDomainNameFlat(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v4; // r8d
  unsigned int i; // ecx
  __int64 v6; // rdx
  __int64 v7; // rcx
  NTSTATUS inited; // ebx
  __int64 DcContext; // rax
  UNICODE_STRING *v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  const UNICODE_STRING *CurrentDcContext; // rax
  UNICODE_STRING *v15; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  __int64 v18; // [rsp+58h] [rbp+10h] BYREF

  v18 = 0;
  DestinationString = 0;
  if ( (a3 & 1) != 0 || a3 - 1 > 0xFFFD )
    return (unsigned int)-1073741811;
  v4 = a3 >> 1;
  for ( i = 0; i < v4; ++i )
  {
    if ( !a2[i] )
      break;
  }
  if ( i >= v4 )
    return (unsigned int)-1073741811;
  if ( *a2 == 92 && *++a2 == 92 )
    ++a2;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  if ( !inited )
  {
    DcContext = DfscCreateDcContext(v7, v6);
    v10 = (UNICODE_STRING *)DcContext;
    if ( !DcContext )
      return (unsigned int)-1073741670;
    inited = DfscCreateNameFromUnicodeString(DcContext + 32, &DestinationString, 1849910852);
    if ( inited >= 0 )
    {
      inited = DfscGetContainerContextFromIrp(a1, &v18);
      if ( inited >= 0 )
      {
        CurrentDcContext = (const UNICODE_STRING *)DfscGetCurrentDcContext(v18, v11, v12, v13);
        v15 = (UNICODE_STRING *)CurrentDcContext;
        if ( CurrentDcContext )
        {
          if ( !RtlCompareUnicodeString(CurrentDcContext + 2, v10 + 2, 0) )
          {
            DfscReleaseDcContext(v15);
            goto LABEL_22;
          }
          inited = DfscCreateNameFromUnicodeString(&v10[1], &v15[1], 1849910852);
          if ( inited >= 0 )
            inited = DfscCopyDcList(v10, v15);
          DfscReleaseDcContext(v15);
          if ( inited < 0 )
            goto LABEL_22;
        }
        DfscSetCurrentDcContext(v10, v18);
      }
    }
LABEL_22:
    DfscReleaseDcContext(v10);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140022b60  mov     rax, rsp
0x140022b63  mov     [rax+8], rbx
0x140022b67  mov     [rax+18h], rbp
0x140022b6b  push    rsi
0x140022b6c  push    rdi
0x140022b6d  push    r14
0x140022b6f  sub     rsp, 30h
0x140022b73  xor     r14d, r14d
0x140022b76  xorps   xmm0, xmm0
0x140022b79  mov     [rax+10h], r14
0x140022b7d  mov     rsi, rcx
0x140022b80  movups  xmmword ptr [rax-28h], xmm0
0x140022b84  test    r8b, 1
0x140022b88  jnz     loc_140022CB5
0x140022b8e  lea     eax, [r8-1]
0x140022b92  cmp     eax, 0FFFDh
0x140022b97  ja      loc_140022CB5
0x140022b9d  shr     r8d, 1
0x140022ba0  mov     ecx, r14d
0x140022ba3  jz      short loc_140022BB5
0x140022ba5  mov     eax, ecx
0x140022ba7  cmp     [rdx+rax*2], r14w
0x140022bac  jz      short loc_140022BB5
0x140022bae  inc     ecx
0x140022bb0  cmp     ecx, r8d
0x140022bb3  jb      short loc_140022BA5
0x140022bb5  cmp     ecx, r8d
0x140022bb8  jnb     loc_140022CB5
0x140022bbe  cmp     word ptr [rdx], 5Ch ; '\'
0x140022bc2  jnz     short loc_140022BD2
0x140022bc4  add     rdx, 2
0x140022bc8  cmp     word ptr [rdx], 5Ch ; '\'
0x140022bcc  jnz     short loc_140022BD2
0x140022bce  add     rdx, 2; SourceString
0x140022bd2  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140022bd7  call    cs:__imp_RtlInitUnicodeStringEx
0x140022bde  nop     dword ptr [rax+rax+00h]
0x140022be3  mov     ebx, eax
0x140022be5  test    eax, eax
0x140022be7  jnz     loc_140022CBA
0x140022bed  call    DfscCreateDcContext
0x140022bf2  mov     rdi, rax
0x140022bf5  test    rax, rax
0x140022bf8  jnz     short loc_140022C04
0x140022bfa  mov     ebx, 0C000009Ah
0x140022bff  jmp     loc_140022CBA
0x140022c04  mov     r8d, 6E436644h
0x140022c0a  lea     rdx, [rsp+48h+DestinationString]
0x140022c0f  lea     rcx, [rax+20h]
0x140022c13  call    DfscCreateNameFromUnicodeString
0x140022c18  mov     ebx, eax
0x140022c1a  test    eax, eax
0x140022c1c  js      loc_140022CAB
0x140022c22  lea     rdx, [rsp+48h+arg_8]
0x140022c27  mov     rcx, rsi
0x140022c2a  call    DfscGetContainerContextFromIrp
0x140022c2f  mov     ebx, eax
0x140022c31  test    eax, eax
0x140022c33  js      short loc_140022CAB
0x140022c35  mov     rcx, [rsp+48h+arg_8]
0x140022c3a  call    DfscGetCurrentDcContext
0x140022c3f  mov     rsi, rax
0x140022c42  test    rax, rax
0x140022c45  jz      short loc_140022C9E
0x140022c47  lea     rcx, [rax+20h]; String1
0x140022c4b  xor     r8d, r8d; CaseInSensitive
0x140022c4e  lea     rdx, [rdi+20h]; String2
0x140022c52  call    cs:__imp_RtlCompareUnicodeString
0x140022c59  nop     dword ptr [rax+rax+00h]
0x140022c5e  test    eax, eax
0x140022c60  jnz     short loc_140022C6C
0x140022c62  mov     rcx, rsi; P
0x140022c65  call    DfscReleaseDcContext
0x140022c6a  jmp     short loc_140022CAB
0x140022c6c  lea     rdx, [rsi+10h]
0x140022c70  mov     r8d, 6E436644h
0x140022c76  lea     rcx, [rdi+10h]
0x140022c7a  call    DfscCreateNameFromUnicodeString
0x140022c7f  mov     ebx, eax
0x140022c81  test    eax, eax
0x140022c83  js      short loc_140022C92
0x140022c85  mov     rdx, rsi
0x140022c88  mov     rcx, rdi
0x140022c8b  call    DfscCopyDcList
0x140022c90  mov     ebx, eax
0x140022c92  mov     rcx, rsi; P
0x140022c95  call    DfscReleaseDcContext
0x140022c9a  test    ebx, ebx
0x140022c9c  js      short loc_140022CAB
0x140022c9e  mov     rdx, [rsp+48h+arg_8]
0x140022ca3  mov     rcx, rdi
0x140022ca6  call    DfscSetCurrentDcContext
0x140022cab  mov     rcx, rdi; P
0x140022cae  call    DfscReleaseDcContext
0x140022cb3  jmp     short loc_140022CBA
0x140022cb5  mov     ebx, 0C000000Dh
0x140022cba  mov     rbp, [rsp+48h+arg_10]
0x140022cbf  mov     eax, ebx
0x140022cc1  mov     rbx, [rsp+48h+arg_0]
0x140022cc6  add     rsp, 30h
0x140022cca  pop     r14
0x140022ccc  pop     rdi
0x140022ccd  pop     rsi
0x140022cce  retn
```
