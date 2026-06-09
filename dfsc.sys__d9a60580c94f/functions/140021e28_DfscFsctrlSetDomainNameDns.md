# DfscFsctrlSetDomainNameDns

- ea: `0x140021e28`
- end: `0x140021f98`
- name: `DfscFsctrlSetDomainNameDns`
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
- `0x140021e28`
- `0x140021fa0`
- `0x140022118`
- `0x140022620`
- `0x140022710`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140021e9f`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140021e9f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021f1a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140021f1a`

## pseudocode

```c
__int64 __fastcall DfscFsctrlSetDomainNameDns(__int64 a1, const WCHAR *a2, unsigned int a3)
{
  unsigned int v4; // r8d
  unsigned int i; // ecx
  __int64 v6; // rdx
  __int64 v7; // rcx
  NTSTATUS inited; // ebx
  __int64 DcContext; // rax
  UNICODE_STRING *v10; // rdi
  const UNICODE_STRING *CurrentDcContext; // rax
  UNICODE_STRING *v12; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-28h] BYREF
  __int64 v15; // [rsp+58h] [rbp+10h] BYREF

  v15 = 0;
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
    inited = DfscCreateNameFromUnicodeString(DcContext + 16, &DestinationString, 1849910852);
    if ( inited >= 0 )
    {
      inited = DfscGetContainerContextFromIrp(a1, &v15);
      if ( inited >= 0 )
      {
        CurrentDcContext = (const UNICODE_STRING *)DfscGetCurrentDcContext(v15);
        v12 = (UNICODE_STRING *)CurrentDcContext;
        if ( CurrentDcContext )
        {
          if ( !RtlCompareUnicodeString(CurrentDcContext + 1, v10 + 1, 0) )
          {
            DfscReleaseDcContext(v12);
            goto LABEL_22;
          }
          inited = DfscCreateNameFromUnicodeString(&v10[2], &v12[2], 1849910852);
          if ( inited >= 0 )
            inited = DfscCopyDcList(v10, v12);
          DfscReleaseDcContext(v12);
          if ( inited < 0 )
            goto LABEL_22;
        }
        DfscSetCurrentDcContext(v10, v15);
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
0x140021e28  mov     rax, rsp
0x140021e2b  mov     [rax+8], rbx
0x140021e2f  mov     [rax+18h], rbp
0x140021e33  push    rsi
0x140021e34  push    rdi
0x140021e35  push    r14
0x140021e37  sub     rsp, 30h
0x140021e3b  xor     r14d, r14d
0x140021e3e  xorps   xmm0, xmm0
0x140021e41  mov     [rax+10h], r14
0x140021e45  mov     rsi, rcx
0x140021e48  movups  xmmword ptr [rax-28h], xmm0
0x140021e4c  test    r8b, 1
0x140021e50  jnz     loc_140021F7D
0x140021e56  lea     eax, [r8-1]
0x140021e5a  cmp     eax, 0FFFDh
0x140021e5f  ja      loc_140021F7D
0x140021e65  shr     r8d, 1
0x140021e68  mov     ecx, r14d
0x140021e6b  jz      short loc_140021E7D
0x140021e6d  mov     eax, ecx
0x140021e6f  cmp     [rdx+rax*2], r14w
0x140021e74  jz      short loc_140021E7D
0x140021e76  inc     ecx
0x140021e78  cmp     ecx, r8d
0x140021e7b  jb      short loc_140021E6D
0x140021e7d  cmp     ecx, r8d
0x140021e80  jnb     loc_140021F7D
0x140021e86  cmp     word ptr [rdx], 5Ch ; '\'
0x140021e8a  jnz     short loc_140021E9A
0x140021e8c  add     rdx, 2
0x140021e90  cmp     word ptr [rdx], 5Ch ; '\'
0x140021e94  jnz     short loc_140021E9A
0x140021e96  add     rdx, 2; SourceString
0x140021e9a  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140021e9f  call    cs:__imp_RtlInitUnicodeStringEx
0x140021ea6  nop     dword ptr [rax+rax+00h]
0x140021eab  mov     ebx, eax
0x140021ead  test    eax, eax
0x140021eaf  jnz     loc_140021F82
0x140021eb5  call    DfscCreateDcContext
0x140021eba  mov     rdi, rax
0x140021ebd  test    rax, rax
0x140021ec0  jnz     short loc_140021ECC
0x140021ec2  mov     ebx, 0C000009Ah
0x140021ec7  jmp     loc_140021F82
0x140021ecc  mov     r8d, 6E436644h
0x140021ed2  lea     rdx, [rsp+48h+DestinationString]
0x140021ed7  lea     rcx, [rax+10h]
0x140021edb  call    DfscCreateNameFromUnicodeString
0x140021ee0  mov     ebx, eax
0x140021ee2  test    eax, eax
0x140021ee4  js      loc_140021F73
0x140021eea  lea     rdx, [rsp+48h+arg_8]
0x140021eef  mov     rcx, rsi
0x140021ef2  call    DfscGetContainerContextFromIrp
0x140021ef7  mov     ebx, eax
0x140021ef9  test    eax, eax
0x140021efb  js      short loc_140021F73
0x140021efd  mov     rcx, [rsp+48h+arg_8]
0x140021f02  call    DfscGetCurrentDcContext
0x140021f07  mov     rsi, rax
0x140021f0a  test    rax, rax
0x140021f0d  jz      short loc_140021F66
0x140021f0f  lea     rcx, [rax+10h]; String1
0x140021f13  xor     r8d, r8d; CaseInSensitive
0x140021f16  lea     rdx, [rdi+10h]; String2
0x140021f1a  call    cs:__imp_RtlCompareUnicodeString
0x140021f21  nop     dword ptr [rax+rax+00h]
0x140021f26  test    eax, eax
0x140021f28  jnz     short loc_140021F34
0x140021f2a  mov     rcx, rsi; P
0x140021f2d  call    DfscReleaseDcContext
0x140021f32  jmp     short loc_140021F73
0x140021f34  lea     rdx, [rsi+20h]
0x140021f38  mov     r8d, 6E436644h
0x140021f3e  lea     rcx, [rdi+20h]
0x140021f42  call    DfscCreateNameFromUnicodeString
0x140021f47  mov     ebx, eax
0x140021f49  test    eax, eax
0x140021f4b  js      short loc_140021F5A
0x140021f4d  mov     rdx, rsi
0x140021f50  mov     rcx, rdi
0x140021f53  call    DfscCopyDcList
0x140021f58  mov     ebx, eax
0x140021f5a  mov     rcx, rsi; P
0x140021f5d  call    DfscReleaseDcContext
0x140021f62  test    ebx, ebx
0x140021f64  js      short loc_140021F73
0x140021f66  mov     rdx, [rsp+48h+arg_8]
0x140021f6b  mov     rcx, rdi
0x140021f6e  call    DfscSetCurrentDcContext
0x140021f73  mov     rcx, rdi; P
0x140021f76  call    DfscReleaseDcContext
0x140021f7b  jmp     short loc_140021F82
0x140021f7d  mov     ebx, 0C000000Dh
0x140021f82  mov     rbp, [rsp+48h+arg_10]
0x140021f87  mov     eax, ebx
0x140021f89  mov     rbx, [rsp+48h+arg_0]
0x140021f8e  add     rsp, 30h
0x140021f92  pop     r14
0x140021f94  pop     rdi
0x140021f95  pop     rsi
0x140021f96  retn
```
