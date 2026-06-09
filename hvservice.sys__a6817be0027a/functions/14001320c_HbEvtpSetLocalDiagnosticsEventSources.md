# HbEvtpSetLocalDiagnosticsEventSources

- ea: `0x14001320c`
- end: `0x140013473`
- name: `HbEvtpSetLocalDiagnosticsEventSources`
- size: `615`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140012170`

## callees

- `0x14001320c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001344c`
- `ntoskrnl!ZwClose` at `0x14001344c`
- `ntoskrnl!ExAllocatePool2` at `0x1400132c2`
- `ntoskrnl!ExAllocatePool2` at `0x140013350`
- `ntoskrnl!ExAllocatePool2` at `0x1400132c2`
- `ntoskrnl!ExAllocatePool2` at `0x140013350`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001331d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001341f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001331d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013408`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001341f`
- `ntoskrnl!ZwQueryValueKey` at `0x140013301`
- `ntoskrnl!ZwQueryValueKey` at `0x14001338f`
- `ntoskrnl!ZwQueryValueKey` at `0x140013301`
- `ntoskrnl!ZwQueryValueKey` at `0x14001338f`
- `ntoskrnl!ZwOpenKey` at `0x140013297`
- `ntoskrnl!ZwOpenKey` at `0x140013297`
- `winhvr!WinHvSetEventLogGroupSources` at `0x140013435`
- `winhvr!WinHvSetEventLogGroupSources` at `0x140013435`
- `winhvr!WinHvSetEventLogGranularSources` at `0x1400133e9`
- `winhvr!WinHvSetEventLogGranularSources` at `0x1400133e9`

## pseudocode

```c
__int64 __fastcall HbEvtpSetLocalDiagnosticsEventSources(__int64 a1)
{
  unsigned __int64 v1; // r14
  unsigned __int64 v2; // r14
  NTSTATUS v3; // ebx
  _DWORD *Pool2; // rsi
  unsigned int v5; // r12d
  _DWORD *v6; // r13
  _DWORD *v7; // rdi
  _DWORD *v8; // rbx
  int v9; // r15d
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+A0h] [rbp+40h] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+48h] BYREF

  v1 = (unsigned __int64)*(unsigned int *)(a1 + 8) << 32;
  ResultLength = 0;
  v2 = *(unsigned int *)(a1 + 4) | v1;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (v2 & 1) == 0 || (v2 & 0xFE) != 6 )
  {
    v3 = WinHvSetEventLogGroupSources(1, v2);
    goto LABEL_24;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&qword_1400090D0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( v3 < 0 )
    goto LABEL_24;
  Pool2 = (_DWORD *)ExAllocatePool2(258, 272, 1967284808);
  if ( !Pool2 )
  {
    v3 = -1073741670;
    goto LABEL_24;
  }
  if ( ZwQueryValueKey(KeyHandle, &stru_140009110, KeyValuePartialInformation, Pool2, 0x110u, &ResultLength) < 0 )
  {
    v5 = 0;
    v6 = 0;
    ExFreePoolWithTag(Pool2, 0x75426248u);
    Pool2 = 0;
    goto LABEL_11;
  }
  if ( Pool2[1] == 3 )
  {
    v5 = Pool2[2];
    v6 = Pool2 + 3;
LABEL_11:
    v7 = (_DWORD *)ExAllocatePool2(258, 272, 1967284808);
    if ( !v7 )
    {
      v3 = -1073741670;
      goto LABEL_19;
    }
    if ( ZwQueryValueKey(KeyHandle, &stru_1400090C0, KeyValuePartialInformation, v7, 0x110u, &ResultLength) >= 0 )
    {
      if ( v7[1] != 3 )
      {
        v3 = -1073741788;
        goto LABEL_19;
      }
      v9 = v7[2];
      v8 = v7 + 3;
    }
    else
    {
      v8 = 0;
      v9 = 0;
      ExFreePoolWithTag(v7, 0x75426248u);
      v7 = 0;
    }
    v3 = WinHvSetEventLogGranularSources(1, v2, v6, v5, v8, v9);
LABEL_19:
    if ( !Pool2 )
      goto LABEL_21;
    goto LABEL_20;
  }
  v7 = 0;
  v3 = -1073741788;
LABEL_20:
  ExFreePoolWithTag(Pool2, 0x75426248u);
LABEL_21:
  if ( v7 )
    ExFreePoolWithTag(v7, 0x75426248u);
LABEL_24:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14001320c  mov     [rsp-38h+arg_10], rbx
0x140013211  push    rbp
0x140013212  push    rsi
0x140013213  push    rdi
0x140013214  push    r12
0x140013216  push    r13
0x140013218  push    r14
0x14001321a  push    r15
0x14001321c  mov     rbp, rsp
0x14001321f  sub     rsp, 60h
0x140013223  mov     r14d, [rcx+8]
0x140013227  xor     eax, eax
0x140013229  xorps   xmm0, xmm0
0x14001322c  shl     r14, 20h
0x140013230  mov     [rbp+arg_0], eax
0x140013233  mov     eax, [rcx+4]
0x140013236  or      r14, rax
0x140013239  mov     [rbp+KeyHandle], 0
0x140013241  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140013245  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140013249  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001324d  test    r14b, 1
0x140013251  jz      loc_14001342D
0x140013257  mov     al, r14b
0x14001325a  and     al, 0FEh
0x14001325c  cmp     al, 6
0x14001325e  jnz     loc_14001342D
0x140013264  lea     rax, qword_1400090D0
0x14001326b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140013272  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013276  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14001327a  mov     edx, 20019h; DesiredAccess
0x14001327f  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140013287  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14001328b  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140013292  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140013297  call    cs:__imp_ZwOpenKey
0x14001329e  nop     dword ptr [rax+rax+00h]
0x1400132a3  mov     ebx, eax
0x1400132a5  test    eax, eax
0x1400132a7  js      loc_140013443
0x1400132ad  mov     ebx, 110h
0x1400132b2  mov     r15d, 75426248h
0x1400132b8  mov     r8d, r15d
0x1400132bb  mov     edx, ebx
0x1400132bd  lea     edi, [rbx-0Eh]
0x1400132c0  mov     ecx, edi
0x1400132c2  call    cs:__imp_ExAllocatePool2
0x1400132c9  nop     dword ptr [rax+rax+00h]
0x1400132ce  mov     rsi, rax
0x1400132d1  test    rax, rax
0x1400132d4  jnz     short loc_1400132E0
0x1400132d6  mov     ebx, 0C000009Ah
0x1400132db  jmp     loc_140013443
0x1400132e0  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400132e4  lea     rax, [rbp+arg_0]
0x1400132e8  mov     [rsp+60h+ResultLength], rax; ResultLength
0x1400132ed  lea     rdx, stru_140009110; ValueName
0x1400132f4  mov     r9, rsi; KeyValueInformation
0x1400132f7  mov     [rsp+60h+Length], ebx; Length
0x1400132fb  mov     r8d, 2; KeyValueInformationClass
0x140013301  call    cs:__imp_ZwQueryValueKey
0x140013308  nop     dword ptr [rax+rax+00h]
0x14001330d  test    eax, eax
0x14001330f  jns     short loc_14001332D
0x140013311  mov     edx, r15d; Tag
0x140013314  mov     rcx, rsi; P
0x140013317  xor     r12d, r12d
0x14001331a  xor     r13d, r13d
0x14001331d  call    cs:__imp_ExFreePoolWithTag
0x140013324  nop     dword ptr [rax+rax+00h]
0x140013329  xor     esi, esi
0x14001332b  jmp     short loc_140013347
0x14001332d  cmp     dword ptr [rsi+4], 3
0x140013331  jz      short loc_14001333F
0x140013333  xor     edi, edi
0x140013335  mov     ebx, 0C0000024h
0x14001333a  jmp     loc_140013402
0x14001333f  mov     r12d, [rsi+8]
0x140013343  lea     r13, [rsi+0Ch]
0x140013347  mov     r8d, r15d
0x14001334a  mov     rdx, rbx
0x14001334d  mov     rcx, rdi
0x140013350  call    cs:__imp_ExAllocatePool2
0x140013357  nop     dword ptr [rax+rax+00h]
0x14001335c  mov     rdi, rax
0x14001335f  test    rax, rax
0x140013362  jnz     short loc_14001336E
0x140013364  mov     ebx, 0C000009Ah
0x140013369  jmp     loc_1400133FD
0x14001336e  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x140013372  lea     rax, [rbp+arg_0]
0x140013376  mov     [rsp+60h+ResultLength], rax; ResultLength
0x14001337b  lea     rdx, stru_1400090C0; ValueName
0x140013382  mov     r9, rdi; KeyValueInformation
0x140013385  mov     [rsp+60h+Length], ebx; Length
0x140013389  mov     r8d, 2; KeyValueInformationClass
0x14001338f  call    cs:__imp_ZwQueryValueKey
0x140013396  nop     dword ptr [rax+rax+00h]
0x14001339b  test    eax, eax
0x14001339d  jns     short loc_1400133BC
0x14001339f  mov     edx, 75426248h; Tag
0x1400133a4  mov     rcx, rdi; P
0x1400133a7  xor     ebx, ebx
0x1400133a9  xor     r15d, r15d
0x1400133ac  call    cs:__imp_ExFreePoolWithTag
0x1400133b3  nop     dword ptr [rax+rax+00h]
0x1400133b8  xor     edi, edi
0x1400133ba  jmp     short loc_1400133D1
0x1400133bc  cmp     dword ptr [rdi+4], 3
0x1400133c0  jz      short loc_1400133C9
0x1400133c2  mov     ebx, 0C0000024h
0x1400133c7  jmp     short loc_1400133FD
0x1400133c9  mov     r15d, [rdi+8]
0x1400133cd  lea     rbx, [rdi+0Ch]
0x1400133d1  mov     dword ptr [rsp+60h+ResultLength], r15d
0x1400133d6  mov     r9d, r12d
0x1400133d9  mov     r8, r13
0x1400133dc  mov     qword ptr [rsp+60h+Length], rbx
0x1400133e1  mov     rdx, r14
0x1400133e4  mov     ecx, 1
0x1400133e9  call    cs:__imp_WinHvSetEventLogGranularSources
0x1400133f0  nop     dword ptr [rax+rax+00h]
0x1400133f5  mov     ebx, eax
0x1400133f7  mov     r15d, 75426248h
0x1400133fd  test    rsi, rsi
0x140013400  jz      short loc_140013414
0x140013402  mov     edx, r15d; Tag
0x140013405  mov     rcx, rsi; P
0x140013408  call    cs:__imp_ExFreePoolWithTag
0x14001340f  nop     dword ptr [rax+rax+00h]
0x140013414  test    rdi, rdi
0x140013417  jz      short loc_140013443
0x140013419  mov     edx, r15d; Tag
0x14001341c  mov     rcx, rdi; P
0x14001341f  call    cs:__imp_ExFreePoolWithTag
0x140013426  nop     dword ptr [rax+rax+00h]
0x14001342b  jmp     short loc_140013443
0x14001342d  mov     rdx, r14
0x140013430  mov     ecx, 1
0x140013435  call    cs:__imp_WinHvSetEventLogGroupSources
0x14001343c  nop     dword ptr [rax+rax+00h]
0x140013441  mov     ebx, eax
0x140013443  mov     rcx, [rbp+KeyHandle]; Handle
0x140013447  test    rcx, rcx
0x14001344a  jz      short loc_140013458
0x14001344c  call    cs:__imp_ZwClose
0x140013453  nop     dword ptr [rax+rax+00h]
0x140013458  mov     eax, ebx
0x14001345a  mov     rbx, [rsp+60h+arg_10]
0x140013462  add     rsp, 60h
0x140013466  pop     r15
0x140013468  pop     r14
0x14001346a  pop     r13
0x14001346c  pop     r12
0x14001346e  pop     rdi
0x14001346f  pop     rsi
0x140013470  pop     rbp
0x140013471  retn
```
