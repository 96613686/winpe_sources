# DfscCreateTreeConnectName

- ea: `0x140013a00`
- end: `0x140013cb5`
- name: `DfscCreateTreeConnectName`
- size: `693`
- prototype: `NTSTATUS __fastcall(unsigned __int16 *, __int64, ULONG, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001338c`

## callees

- `0x140003f20`
- `0x140005f70`
- `0x140013a00`
- `0x140026f60`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013bf5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013c75`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013bf5`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140013c75`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013adb`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013b20`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013adb`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140013b20`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013bd7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013c4c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013bd7`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140013c4c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140013b57`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x140013b57`
- `ntoskrnl!wcschr` at `0x140013af9`
- `ntoskrnl!wcschr` at `0x140013af9`
- `ntoskrnl!ExAllocatePool2` at `0x140013b95`
- `ntoskrnl!ExAllocatePool2` at `0x140013b95`

## pseudocode

```c
NTSTATUS __fastcall DfscCreateTreeConnectName(unsigned __int16 *a1, __int64 a2, ULONG a3, struct _UNICODE_STRING *a4)
{
  unsigned __int64 v4; // rax
  _WORD *v8; // rcx
  NTSTATUS result; // eax
  wchar_t *v10; // rax
  unsigned int v11; // edx
  __int64 Pool2; // rax
  struct _LUID AuthenticationId; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-21h] BYREF
  UNICODE_STRING Source; // [rsp+48h] [rbp-11h] BYREF
  wchar_t pszDest[20]; // [rsp+58h] [rbp-1h] BYREF

  v4 = *a1;
  AuthenticationId = 0;
  Source = 0;
  DestinationString = 0;
  if ( (unsigned int)v4 < 6 )
    return -1073741592;
  v8 = (_WORD *)*((_QWORD *)a1 + 1);
  if ( *v8 != 92 || v8[1] == 92 || !v8[(v4 >> 1) - 1] )
    return -1073741592;
  if ( !a2 )
    goto LABEL_12;
  if ( *(_WORD *)a2 < 2u )
    return -1073741592;
  if ( DfsLUIDDeviceMapsEnabled == 1 )
  {
    result = DfscGetLogonId(&AuthenticationId);
    if ( result )
      return result;
    result = RtlStringCbPrintfW(
               pszDest,
               0x22u,
               L"%08x%08x",
               (unsigned int)AuthenticationId.HighPart,
               AuthenticationId.LowPart);
    if ( result )
      return result;
    result = RtlInitUnicodeStringEx(&DestinationString, pszDest);
  }
  else
  {
    DestinationString.MaximumLength = 34;
    DestinationString.Buffer = pszDest;
    result = RtlIntegerToUnicodeString(a3, 0xAu, &DestinationString);
  }
  if ( result )
    return result;
LABEL_12:
  v10 = wcschr(L"Device\\DfsClient", 0x5Cu);
  if ( !v10 || !v10[1] )
    return -1073741811;
  if ( RtlInitUnicodeStringEx(&Source, v10) )
    return -1073740768;
  v11 = DestinationString.Length + Source.Length + 30 + *a1;
  if ( v11 > 0xFFFF )
    return -1073741811;
  a4->MaximumLength = v11;
  Pool2 = ExAllocatePool2(258, (unsigned __int16)v11, 1950574148);
  a4->Buffer = (PWSTR)Pool2;
  if ( !Pool2 )
    return -1073741670;
  a4->Length = 22;
  *(_OWORD *)Pool2 = *(_OWORD *)L"\\Device\\Mup";
  *(_QWORD *)(Pool2 + 14) = *(_QWORD *)L"\\Mup";
  result = RtlAppendUnicodeStringToString(a4, &Source);
  if ( result >= 0 )
  {
    result = RtlAppendUnicodeToString(a4, L"\\;");
    if ( result >= 0 )
    {
      if ( a2 )
      {
        a4->Buffer[(unsigned __int64)a4->Length >> 1] = **(_WORD **)(a2 + 8);
        a4->Length += 2;
      }
      a4->Buffer[(unsigned __int64)a4->Length >> 1] = 58;
      a4->Length += 2;
      if ( DestinationString.Length )
      {
        RtlAppendUnicodeStringToString(a4, &DestinationString);
      }
      else
      {
        a4->Buffer[(unsigned __int64)a4->Length >> 1] = 48;
        a4->Length += 2;
      }
      RtlAppendUnicodeToString(a4, *((PCWSTR *)a1 + 1));
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140013a00  mov     [rsp-8+arg_8], rbx
0x140013a05  push    rbp
0x140013a06  push    rsi
0x140013a07  push    rdi
0x140013a08  push    r12
0x140013a0a  push    r14
0x140013a0c  lea     rbp, [rsp-37h]
0x140013a11  sub     rsp, 90h
0x140013a18  mov     rax, cs:__security_cookie
0x140013a1f  xor     rax, rsp
0x140013a22  mov     [rbp+57h+var_30], rax
0x140013a26  movzx   eax, word ptr [rcx]
0x140013a29  xor     r14d, r14d
0x140013a2c  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r14
0x140013a30  xorps   xmm0, xmm0
0x140013a33  xorps   xmm1, xmm1
0x140013a36  mov     rbx, r9
0x140013a39  mov     r9d, r8d
0x140013a3c  mov     rdi, rdx
0x140013a3f  mov     rsi, rcx
0x140013a42  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140013a46  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140013a4a  cmp     eax, 6
0x140013a4d  jb      loc_140013C8C
0x140013a53  mov     rcx, [rcx+8]
0x140013a57  lea     r12d, [r14+5Ch]
0x140013a5b  cmp     [rcx], r12w
0x140013a5f  jnz     loc_140013C8C
0x140013a65  cmp     [rcx+2], r12w
0x140013a6a  jz      loc_140013C8C
0x140013a70  shr     rax, 1
0x140013a73  cmp     [rcx+rax*2-2], r14w
0x140013a79  jz      loc_140013C8C
0x140013a7f  test    rdx, rdx
0x140013a82  jz      short loc_140013AEF
0x140013a84  cmp     word ptr [rdx], 2
0x140013a88  jb      loc_140013C8C
0x140013a8e  cmp     cs:DfsLUIDDeviceMapsEnabled, 1
0x140013a95  jnz     loc_140013B3A
0x140013a9b  lea     rcx, [rbp+57h+AuthenticationId]; AuthenticationId
0x140013a9f  call    DfscGetLogonId
0x140013aa4  test    eax, eax
0x140013aa6  jnz     loc_140013C91
0x140013aac  mov     eax, [rbp+57h+AuthenticationId.LowPart]
0x140013aaf  lea     r8, a08x08x; "%08x%08x"
0x140013ab6  mov     r9d, [rbp+57h+AuthenticationId.HighPart]
0x140013aba  lea     edx, [r14+22h]; cbDest
0x140013abe  lea     rcx, [rbp+57h+pszDest]; pszDest
0x140013ac2  mov     [rsp+0B0h+var_90], eax
0x140013ac6  call    RtlStringCbPrintfW
0x140013acb  test    eax, eax
0x140013acd  jnz     loc_140013C91
0x140013ad3  lea     rdx, [rbp+57h+pszDest]; SourceString
0x140013ad7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140013adb  call    cs:__imp_RtlInitUnicodeStringEx
0x140013ae2  nop     dword ptr [rax+rax+00h]
0x140013ae7  test    eax, eax
0x140013ae9  jnz     loc_140013C91
0x140013aef  mov     edx, r12d; Ch
0x140013af2  lea     rcx, SourceString+2; Str
0x140013af9  call    cs:__imp_wcschr
0x140013b00  nop     dword ptr [rax+rax+00h]
0x140013b05  test    rax, rax
0x140013b08  jz      loc_140013C85
0x140013b0e  cmp     [rax+2], r14w
0x140013b13  jz      loc_140013C85
0x140013b19  mov     rdx, rax; SourceString
0x140013b1c  lea     rcx, [rbp+57h+Source]; DestinationString
0x140013b20  call    cs:__imp_RtlInitUnicodeStringEx
0x140013b27  nop     dword ptr [rax+rax+00h]
0x140013b2c  test    eax, eax
0x140013b2e  jz      short loc_140013B65
0x140013b30  mov     eax, 0C0000420h
0x140013b35  jmp     loc_140013C91
0x140013b3a  mov     eax, 22h ; '"'
0x140013b3f  lea     r8, [rbp+57h+DestinationString]; String
0x140013b43  mov     [rbp+57h+DestinationString.MaximumLength], ax
0x140013b47  mov     edx, 0Ah; Base
0x140013b4c  lea     rax, [rbp+57h+pszDest]
0x140013b50  mov     ecx, r9d; Value
0x140013b53  mov     [rbp+57h+DestinationString.Buffer], rax
0x140013b57  call    cs:__imp_RtlIntegerToUnicodeString
0x140013b5e  nop     dword ptr [rax+rax+00h]
0x140013b63  jmp     short loc_140013AE7
0x140013b65  movzx   ecx, [rbp+57h+Source.Length]
0x140013b69  movzx   eax, [rbp+57h+DestinationString.Length]
0x140013b6d  add     ecx, 1Eh
0x140013b70  movzx   edx, word ptr [rsi]
0x140013b73  add     ecx, eax
0x140013b75  add     edx, ecx
0x140013b77  cmp     edx, 0FFFFh
0x140013b7d  ja      loc_140013C85
0x140013b83  movzx   edx, dx
0x140013b86  mov     ecx, 102h
0x140013b8b  mov     r8d, 74436644h
0x140013b91  mov     [rbx+2], dx
0x140013b95  call    cs:__imp_ExAllocatePool2
0x140013b9c  nop     dword ptr [rax+rax+00h]
0x140013ba1  mov     [rbx+8], rax
0x140013ba5  test    rax, rax
0x140013ba8  jnz     short loc_140013BB4
0x140013baa  mov     eax, 0C000009Ah
0x140013baf  jmp     loc_140013C91
0x140013bb4  mov     word ptr [rbx], 16h
0x140013bb9  lea     rdx, [rbp+57h+Source]; Source
0x140013bbd  movups  xmm0, xmmword ptr cs:aDeviceMup; "\\Device\\Mup"
0x140013bc4  mov     rcx, rbx; Destination
0x140013bc7  movups  xmmword ptr [rax], xmm0
0x140013bca  movsd   xmm1, qword ptr cs:aDeviceMup+0Eh; "\\Mup"
0x140013bd2  movsd   qword ptr [rax+0Eh], xmm1
0x140013bd7  call    cs:__imp_RtlAppendUnicodeStringToString
0x140013bde  nop     dword ptr [rax+rax+00h]
0x140013be3  test    eax, eax
0x140013be5  js      loc_140013C91
0x140013beb  lea     rdx, asc_140008D1C; "\\;"
0x140013bf2  mov     rcx, rbx; Destination
0x140013bf5  call    cs:__imp_RtlAppendUnicodeToString
0x140013bfc  nop     dword ptr [rax+rax+00h]
0x140013c01  test    eax, eax
0x140013c03  js      loc_140013C91
0x140013c09  test    rdi, rdi
0x140013c0c  jz      short loc_140013C27
0x140013c0e  mov     rax, [rdi+8]
0x140013c12  movzx   edx, word ptr [rbx]
0x140013c15  mov     rcx, [rbx+8]
0x140013c19  shr     rdx, 1
0x140013c1c  movzx   eax, word ptr [rax]
0x140013c1f  mov     [rcx+rdx*2], ax
0x140013c23  add     word ptr [rbx], 2
0x140013c27  movzx   ecx, word ptr [rbx]
0x140013c2a  mov     rax, [rbx+8]
0x140013c2e  shr     rcx, 1
0x140013c31  mov     word ptr [rax+rcx*2], 3Ah ; ':'
0x140013c37  add     word ptr [rbx], 2
0x140013c3b  movzx   eax, word ptr [rbx]
0x140013c3e  cmp     [rbp+57h+DestinationString.Length], r14w
0x140013c43  jz      short loc_140013C5A
0x140013c45  lea     rdx, [rbp+57h+DestinationString]; Source
0x140013c49  mov     rcx, rbx; Destination
0x140013c4c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140013c53  nop     dword ptr [rax+rax+00h]
0x140013c58  jmp     short loc_140013C6E
0x140013c5a  mov     rdx, rax
0x140013c5d  mov     rax, [rbx+8]
0x140013c61  shr     rdx, 1
0x140013c64  mov     word ptr [rax+rdx*2], 30h ; '0'
0x140013c6a  add     word ptr [rbx], 2
0x140013c6e  mov     rdx, [rsi+8]; Source
0x140013c72  mov     rcx, rbx; Destination
0x140013c75  call    cs:__imp_RtlAppendUnicodeToString
0x140013c7c  nop     dword ptr [rax+rax+00h]
0x140013c81  xor     eax, eax
0x140013c83  jmp     short loc_140013C91
0x140013c85  mov     eax, 0C000000Dh
0x140013c8a  jmp     short loc_140013C91
0x140013c8c  mov     eax, 0C00000E8h
0x140013c91  mov     rcx, [rbp+57h+var_30]
0x140013c95  xor     rcx, rsp; StackCookie
0x140013c98  call    __security_check_cookie
0x140013c9d  mov     rbx, [rsp+0B0h+arg_8]
0x140013ca5  add     rsp, 90h
0x140013cac  pop     r14
0x140013cae  pop     r12
0x140013cb0  pop     rdi
0x140013cb1  pop     rsi
0x140013cb2  pop     rbp
0x140013cb3  retn
```
