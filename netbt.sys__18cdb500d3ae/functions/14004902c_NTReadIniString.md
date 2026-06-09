# NTReadIniString

- ea: `0x14004902c`
- end: `0x140049197`
- name: `NTReadIniString`
- size: `363`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140048e50`

## callees

- `0x140014910`
- `0x140042330`
- `0x14004902c`
- `0x1400491a0`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140049151`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140049151`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049099`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400490cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004916d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049186`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049099`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400490cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004916d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049186`
- `ntoskrnl!ExAllocatePool2` at `0x14004911c`
- `ntoskrnl!ExAllocatePool2` at `0x14004911c`

## pseudocode

```c
__int64 __fastcall NTReadIniString(HANDLE KeyHandle, __int64 a2, _QWORD *a3)
{
  int Element; // eax
  __int64 v6; // rcx
  NTSTATUS appended; // ebx
  void *Pool2; // rax
  void *v10; // rdi
  PVOID v11[2]; // [rsp+20h] [rbp-20h] BYREF
  PVOID P[2]; // [rsp+30h] [rbp-10h] BYREF

  *(_OWORD *)v11 = 0;
  Element = ReadElement(KeyHandle, L"ScopeId", (PUNICODE_STRING)v11);
  appended = Element;
  if ( Element < 0 || !LOWORD(v11[0]) )
  {
    *(_OWORD *)P = 0;
    if ( Element >= 0 )
      ExFreePoolWithTag(v11[1], 0);
    appended = NbtAppendString(v6, L"ScopeId", P);
    if ( appended >= 0 )
    {
      appended = ReadElement(KeyHandle, (PCWSTR)P[1], (PUNICODE_STRING)v11);
      ExFreePoolWithTag(P[1], 0);
    }
  }
  if ( (xmmword_140038420 & 8) != 0 )
    WPP_SF_S(1027, 23, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids, v11[1]);
  if ( appended >= 0 )
  {
    if ( (unsigned __int16)(LOWORD(v11[0]) - 1) <= 0x1DDu
      && (Pool2 = (void *)ExAllocatePool2(64, (unsigned __int64)WORD1(v11[0]) >> 1, 825451086), (v10 = Pool2) != 0) )
    {
      P[0] = 0;
      *(_DWORD *)((char *)P + 2) = WORD1(v11[0]) >> 1;
      P[1] = Pool2;
      appended = RtlUnicodeStringToAnsiString((PANSI_STRING)P, (PCUNICODE_STRING)v11, 0);
      if ( appended < 0 )
        ExFreePoolWithTag(v10, 0);
      else
        *a3 = v10;
    }
    else
    {
      appended = -1073741823;
    }
    ExFreePoolWithTag(v11[1], 0);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14004902c  push    rbp
0x14004902e  push    rbx
0x14004902f  push    rsi
0x140049030  push    rdi
0x140049031  push    r14
0x140049033  mov     rbp, rsp
0x140049036  sub     rsp, 40h
0x14004903a  mov     rsi, r8
0x14004903d  lea     rdx, aScopeid; "ScopeId"
0x140049044  xorps   xmm0, xmm0
0x140049047  lea     r8, [rbp+var_20]; ValueName
0x14004904b  movups  xmmword ptr [rbp+var_20], xmm0
0x14004904f  mov     rdi, rcx
0x140049052  call    ReadElement
0x140049057  xor     r14d, r14d
0x14004905a  mov     ebx, eax
0x14004905c  test    eax, eax
0x14004905e  jns     short loc_1400490C0
0x140049060  xorps   xmm0, xmm0
0x140049063  movups  xmmword ptr [rbp+P], xmm0
0x140049067  test    eax, eax
0x140049069  jns     short loc_1400490C9
0x14004906b  lea     r8, [rbp+P]
0x14004906f  lea     rdx, aScopeid; "ScopeId"
0x140049076  call    NbtAppendString
0x14004907b  mov     ebx, eax
0x14004907d  test    eax, eax
0x14004907f  js      short loc_1400490A5
0x140049081  mov     rdx, [rbp+P+8]; SourceString
0x140049085  lea     r8, [rbp+var_20]; ValueName
0x140049089  mov     rcx, rdi; KeyHandle
0x14004908c  call    ReadElement
0x140049091  mov     rcx, [rbp+P+8]; P
0x140049095  xor     edx, edx; Tag
0x140049097  mov     ebx, eax
0x140049099  call    cs:__imp_ExFreePoolWithTag
0x1400490a0  nop     dword ptr [rax+rax+00h]
0x1400490a5  test    byte ptr cs:xmmword_140038420, 8
0x1400490ac  jnz     short loc_1400490DD
0x1400490ae  test    ebx, ebx
0x1400490b0  jns     short loc_1400490F9
0x1400490b2  mov     eax, ebx
0x1400490b4  add     rsp, 40h
0x1400490b8  pop     r14
0x1400490ba  pop     rdi
0x1400490bb  pop     rsi
0x1400490bc  pop     rbx
0x1400490bd  pop     rbp
0x1400490be  retn
0x1400490c0  cmp     word ptr [rbp+var_20], r14w
0x1400490c5  jz      short loc_140049060
0x1400490c7  jmp     short loc_1400490A5
0x1400490c9  mov     rcx, [rbp+var_20+8]; P
0x1400490cd  xor     edx, edx; Tag
0x1400490cf  call    cs:__imp_ExFreePoolWithTag
0x1400490d6  nop     dword ptr [rax+rax+00h]
0x1400490db  jmp     short loc_14004906B
0x1400490dd  mov     r9, [rbp+var_20+8]
0x1400490e1  lea     r8, WPP_16017140470e3ea93dff34ba8a0dc815_Traceguids
0x1400490e8  mov     edx, 17h
0x1400490ed  mov     ecx, 403h
0x1400490f2  call    WPP_SF_S
0x1400490f7  jmp     short loc_1400490AE
0x1400490f9  movzx   eax, word ptr [rbp+var_20]
0x1400490fd  mov     ecx, 1DDh
0x140049102  dec     ax
0x140049105  cmp     ax, cx
0x140049108  ja      short loc_14004917B
0x14004910a  movzx   edx, word ptr [rbp+var_20+2]
0x14004910e  mov     ecx, 40h ; '@'
0x140049113  shr     rdx, 1
0x140049116  mov     r8d, 3133624Eh
0x14004911c  call    cs:__imp_ExAllocatePool2
0x140049123  nop     dword ptr [rax+rax+00h]
0x140049128  mov     rdi, rax
0x14004912b  test    rax, rax
0x14004912e  jz      short loc_14004917B
0x140049130  movzx   ecx, word ptr [rbp+var_20+2]
0x140049134  lea     rdx, [rbp+var_20]; SourceString
0x140049138  shr     cx, 1
0x14004913b  xorps   xmm0, xmm0
0x14004913e  movups  xmmword ptr [rbp+P], xmm0
0x140049142  mov     word ptr [rbp+P+2], cx
0x140049146  xor     r8d, r8d; AllocateDestinationString
0x140049149  lea     rcx, [rbp+P]; DestinationString
0x14004914d  mov     [rbp+P+8], rax
0x140049151  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140049158  nop     dword ptr [rax+rax+00h]
0x14004915d  mov     ebx, eax
0x14004915f  test    eax, eax
0x140049161  js      short loc_140049168
0x140049163  mov     [rsi], rdi
0x140049166  jmp     short loc_140049180
0x140049168  xor     edx, edx; Tag
0x14004916a  mov     rcx, rdi; P
0x14004916d  call    cs:__imp_ExFreePoolWithTag
0x140049174  nop     dword ptr [rax+rax+00h]
0x140049179  jmp     short loc_140049180
0x14004917b  mov     ebx, 0C0000001h
0x140049180  mov     rcx, [rbp+var_20+8]; P
0x140049184  xor     edx, edx; Tag
0x140049186  call    cs:__imp_ExFreePoolWithTag
0x14004918d  nop     dword ptr [rax+rax+00h]
0x140049192  jmp     loc_1400490B2
```
