# SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting

- ea: `0x14004de4c`
- end: `0x14004dfa0`
- name: `SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14007fd3c`

## callees

- `0x14004dce4`
- `0x14004de4c`
- `0x140059dc0`
- `0x140059ea0`
- `0x140059f00`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValues` at `0x14004defd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004df72`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004df72`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004deda`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14004deda`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004deca`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004deca`

## string_xrefs

- `0x14004de8f`: `RtlQueryRegistryValuesEx`
- `0x14004def6`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanWorkstation`
- `0x14004dea8`: `CompressionAlgorithmSuiteOrder`

## pseudocode

```c
__int64 __fastcall SmbCompressionReadCompressionAlgorithmSuiteOrderPolicySetting(
        __int64 a1,
        void *a2,
        unsigned __int16 *a3)
{
  PVOID SystemRoutineAddress; // rax
  int v6; // eax
  int v7; // ebx
  unsigned __int16 v8; // bx
  unsigned __int16 v10; // [rsp+30h] [rbp-79h] BYREF
  UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-71h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v13[14]; // [rsp+60h] [rbp-49h] BYREF
  __int128 Src; // [rsp+D0h] [rbp+27h] BYREF
  int v15; // [rsp+E0h] [rbp+37h]

  memset(v13, 0, sizeof(v13));
  LODWORD(v13[1]) = 304;
  v15 = 0;
  v10 = 0;
  LODWORD(v13[4]) = 117440512;
  v13[2] = L"CompressionAlgorithmSuiteOrder";
  v13[3] = &UnicodeString;
  UnicodeString = 0;
  Src = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = RtlQueryRegistryValues;
  v6 = ((__int64 (__fastcall *)(_QWORD, const wchar_t *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
         0,
         L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanWorkstation",
         v13,
         0,
         0);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( !UnicodeString.Buffer )
    {
      v7 = -1073741772;
      goto LABEL_11;
    }
    v7 = SmbCompressionParseAlgorithmSuiteOrder(&Src, &v10, UnicodeString.Buffer, UnicodeString.Length);
    if ( v7 < 0 )
      goto LABEL_11;
    v8 = v10;
    if ( v10 )
    {
      memmove(a2, &Src, 4LL * v10);
      *a3 = v8;
      v7 = 0;
      goto LABEL_11;
    }
    goto LABEL_5;
  }
  if ( v6 == -1073741788 )
LABEL_5:
    v7 = -1073739509;
LABEL_11:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14004de4c  mov     [rsp-8+arg_0], rbx
0x14004de51  push    rbp
0x14004de52  push    rsi
0x14004de53  push    rdi
0x14004de54  lea     rbp, [rsp-47h]
0x14004de59  sub     rsp, 0F0h
0x14004de60  mov     rax, cs:__security_cookie
0x14004de67  xor     rax, rsp
0x14004de6a  mov     [rbp+57h+var_18], rax
0x14004de6e  mov     rdi, rdx
0x14004de71  lea     rcx, [rbp+57h+var_A0]; void *
0x14004de75  xor     edx, edx; Val
0x14004de77  mov     rsi, r8
0x14004de7a  lea     r8d, [rdx+70h]; Size
0x14004de7e  call    memset
0x14004de83  xor     eax, eax
0x14004de85  mov     [rbp+57h+var_98], 130h
0x14004de8c  mov     [rbp+57h+var_20], eax
0x14004de8f  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14004de96  mov     [rbp+57h+var_D0], ax
0x14004de9a  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004de9e  xorps   xmm0, xmm0
0x14004dea1  mov     [rbp+57h+var_80], 7000000h
0x14004dea8  lea     rax, aCompressionalg; "CompressionAlgorithmSuiteOrder"
0x14004deaf  xorps   xmm1, xmm1
0x14004deb2  mov     [rbp+57h+var_90], rax
0x14004deb6  lea     rax, [rbp+57h+UnicodeString]
0x14004deba  mov     [rbp+57h+var_88], rax
0x14004debe  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x14004dec2  movups  [rbp+57h+Src], xmm1
0x14004dec6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14004deca  call    cs:__imp_RtlInitUnicodeString
0x14004ded1  nop     dword ptr [rax+rax+00h]
0x14004ded6  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14004deda  call    cs:__imp_MmGetSystemRoutineAddress
0x14004dee1  nop     dword ptr [rax+rax+00h]
0x14004dee6  lea     r8, [rbp+57h+var_A0]
0x14004deea  mov     [rsp+100h+var_E0], 0
0x14004def3  test    rax, rax
0x14004def6  lea     rdx, aRegistryMachin_13; "\\Registry\\Machine\\Software\\Policies"...
0x14004defd  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14004df05  xor     r9d, r9d
0x14004df08  xor     ecx, ecx
0x14004df0a  call    _guard_dispatch_icall
0x14004df0f  mov     ebx, eax
0x14004df11  test    eax, eax
0x14004df13  jns     short loc_14004DF23
0x14004df15  cmp     eax, 0C0000024h
0x14004df1a  jnz     short loc_14004DF6E
0x14004df1c  mov     ebx, 0C000090Bh
0x14004df21  jmp     short loc_14004DF6E
0x14004df23  mov     r8, [rbp+57h+UnicodeString.Buffer]
0x14004df27  test    r8, r8
0x14004df2a  jnz     short loc_14004DF33
0x14004df2c  mov     ebx, 0C0000034h
0x14004df31  jmp     short loc_14004DF6E
0x14004df33  movzx   r9d, [rbp+57h+UnicodeString.Length]
0x14004df38  lea     rdx, [rbp+57h+var_D0]
0x14004df3c  lea     rcx, [rbp+57h+Src]
0x14004df40  call    SmbCompressionParseAlgorithmSuiteOrder
0x14004df45  mov     ebx, eax
0x14004df47  test    eax, eax
0x14004df49  js      short loc_14004DF6E
0x14004df4b  movzx   ebx, [rbp+57h+var_D0]
0x14004df4f  xor     eax, eax
0x14004df51  cmp     ax, bx
0x14004df54  jz      short loc_14004DF1C
0x14004df56  mov     r8d, ebx
0x14004df59  lea     rdx, [rbp+57h+Src]; Src
0x14004df5d  shl     r8, 2; Size
0x14004df61  mov     rcx, rdi; void *
0x14004df64  call    memmove
0x14004df69  mov     [rsi], bx
0x14004df6c  xor     ebx, ebx
0x14004df6e  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14004df72  call    cs:__imp_RtlFreeUnicodeString
0x14004df79  nop     dword ptr [rax+rax+00h]
0x14004df7e  mov     eax, ebx
0x14004df80  mov     rcx, [rbp+57h+var_18]
0x14004df84  xor     rcx, rsp; StackCookie
0x14004df87  call    __security_check_cookie
0x14004df8c  mov     rbx, [rsp+100h+arg_0]
0x14004df94  add     rsp, 0F0h
0x14004df9b  pop     rdi
0x14004df9c  pop     rsi
0x14004df9d  pop     rbp
0x14004df9e  retn
```
