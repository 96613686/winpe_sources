# CscSetExtensionList

- ea: `0x1400502a8`
- end: `0x14005047a`
- name: `CscSetExtensionList`
- size: `466`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x14004d3e8`
- `0x14004dc44`
- `0x14005027c`
- `0x140050480`

## callees

- `0x1400190ec`
- `0x1400197a0`
- `0x1400213ac`
- `0x14002f140`
- `0x1400502a8`
- `0x140051f84`
- `0x14008e628`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140050346`
- `ntoskrnl!ExAllocatePool2` at `0x140050346`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050427`
- `ntoskrnl!ExFreePoolWithTag` at `0x140050427`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400503a1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400503bc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400503a1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400503bc`

## pseudocode

```c
__int64 __fastcall CscSetExtensionList(__int64 a1, unsigned int a2, UNICODE_STRING *a3)
{
  UNICODE_STRING *p_String2; // rbx
  WCHAR *Pool2; // rax
  int v7; // edi
  int v8; // ebx
  char v9; // si
  UNICODE_STRING String2; // [rsp+30h] [rbp-38h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-28h] BYREF
  UNICODE_STRING v13; // [rsp+50h] [rbp-18h] BYREF

  *(_QWORD *)&String1.Length = 262146;
  String1.Buffer = L"*";
  *(_QWORD *)&v13.Length = 524294;
  v13.Buffer = L"*.*";
  p_String2 = a3;
  String2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dq(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, a3->Length, a3);
  if ( p_String2->Length )
  {
    Pool2 = (WCHAR *)ExAllocatePool2(258, p_String2->Length, 1061124178);
    String2.Buffer = Pool2;
    if ( !Pool2 )
    {
      v7 = -1073741670;
      v8 = 455;
      goto LABEL_18;
    }
    memmove(Pool2, p_String2->Buffer, p_String2->Length);
  }
  else
  {
    String2.Buffer = 0;
  }
  String2.Length = p_String2->Length;
  String2.MaximumLength = String2.Length;
  CscStringTableRemoveRedundantSpace(0, &String2);
  if ( RtlEqualUnicodeString(&String1, &String2, 0) || RtlEqualUnicodeString(&v13, &String2, 0) )
  {
    v9 = 1;
    String2.Length = 0;
  }
  else
  {
    v9 = 0;
    p_String2 = &String2;
  }
  v7 = CscStringTableSetStringList((PERESOURCE)(a1 + 8));
  if ( v7 >= 0 )
  {
    *(_BYTE *)(a1 + 1) = v9;
    v7 = CscRegistrySetValue(a2, p_String2);
    v8 = 0;
    if ( v7 < 0 )
      v8 = 511;
  }
  else
  {
    v8 = 499;
  }
  Pool2 = String2.Buffer;
LABEL_18:
  if ( Pool2 )
  {
    ExFreePoolWithTag(Pool2, 0);
    String2.Buffer = 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)v7,
      v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400502a8  push    rbp
0x1400502aa  push    rbx
0x1400502ab  push    rsi
0x1400502ac  push    rdi
0x1400502ad  push    r12
0x1400502af  push    r13
0x1400502b1  push    r14
0x1400502b3  push    r15
0x1400502b5  mov     rbp, rsp
0x1400502b8  sub     rsp, 68h
0x1400502bc  lea     rax, asc_140031BA0; "*"
0x1400502c3  mov     qword ptr [rbp+String1.Length], 40002h
0x1400502cb  mov     [rbp+String1.Buffer], rax
0x1400502cf  xorps   xmm0, xmm0
0x1400502d2  lea     rax, asc_140031BA8; "*.*"
0x1400502d9  mov     qword ptr [rbp+var_18.Length], 80006h
0x1400502e1  xor     r12d, r12d
0x1400502e4  mov     [rbp+var_18.Buffer], rax
0x1400502e8  mov     rbx, r8
0x1400502eb  mov     [rbp+arg_10], r12b
0x1400502ef  mov     r15d, edx
0x1400502f2  mov     r14, rcx
0x1400502f5  movups  xmmword ptr [rbp+String2.Length], xmm0
0x1400502f9  mov     rcx, cs:WPP_GLOBAL_Control
0x140050300  lea     r13, WPP_GLOBAL_Control
0x140050307  cmp     rcx, r13
0x14005030a  jz      short loc_140050331
0x14005030c  mov     eax, [rcx+2Ch]
0x14005030f  test    al, 20h
0x140050311  jz      short loc_140050331
0x140050313  movzx   r9d, word ptr [r8]
0x140050317  lea     edx, [r12+0Ah]
0x14005031c  mov     rcx, [rcx+18h]
0x140050320  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140050327  mov     [rsp+68h+var_48], rbx
0x14005032c  call    WPP_SF_Dq
0x140050331  movzx   eax, word ptr [rbx]
0x140050334  test    ax, ax
0x140050337  jz      short loc_14005037C
0x140050339  mov     edx, eax
0x14005033b  mov     ecx, 102h
0x140050340  mov     r8d, 3F3F7852h
0x140050346  call    cs:__imp_ExAllocatePool2
0x14005034d  nop     dword ptr [rax+rax+00h]
0x140050352  mov     [rbp+String2.Buffer], rax
0x140050356  test    rax, rax
0x140050359  jnz     short loc_14005036A
0x14005035b  mov     edi, 0C000009Ah
0x140050360  mov     ebx, 1C7h
0x140050365  jmp     loc_14005041D
0x14005036a  movzx   r8d, word ptr [rbx]; Size
0x14005036e  mov     rcx, rax; void *
0x140050371  mov     rdx, [rbx+8]; Src
0x140050375  call    memmove
0x14005037a  jmp     short loc_140050380
0x14005037c  mov     [rbp+String2.Buffer], r12
0x140050380  movzx   eax, word ptr [rbx]
0x140050383  lea     rdx, [rbp+String2]
0x140050387  xor     ecx, ecx
0x140050389  mov     [rbp+String2.Length], ax
0x14005038d  mov     [rbp+String2.MaximumLength], ax
0x140050391  call    CscStringTableRemoveRedundantSpace
0x140050396  xor     r8d, r8d; CaseInSensitive
0x140050399  lea     rdx, [rbp+String2]; String2
0x14005039d  lea     rcx, [rbp+String1]; String1
0x1400503a1  call    cs:__imp_RtlEqualUnicodeString
0x1400503a8  nop     dword ptr [rax+rax+00h]
0x1400503ad  test    al, al
0x1400503af  jnz     short loc_1400503D5
0x1400503b1  xor     r8d, r8d; CaseInSensitive
0x1400503b4  lea     rdx, [rbp+String2]; String2
0x1400503b8  lea     rcx, [rbp+var_18]; String1
0x1400503bc  call    cs:__imp_RtlEqualUnicodeString
0x1400503c3  nop     dword ptr [rax+rax+00h]
0x1400503c8  test    al, al
0x1400503ca  jnz     short loc_1400503D5
0x1400503cc  mov     sil, r12b
0x1400503cf  lea     rbx, [rbp+String2]
0x1400503d3  jmp     short loc_1400503DD
0x1400503d5  mov     sil, 1
0x1400503d8  mov     [rbp+String2.Length], r12w
0x1400503dd  lea     rcx, [r14+8]; Resource
0x1400503e1  lea     r8, [rbp+arg_10]
0x1400503e5  lea     rdx, [rbp+String2]
0x1400503e9  call    CscStringTableSetStringList
0x1400503ee  mov     edi, eax
0x1400503f0  test    eax, eax
0x1400503f2  jns     short loc_1400503FB
0x1400503f4  mov     ebx, 1F3h
0x1400503f9  jmp     short loc_140050419
0x1400503fb  mov     rdx, rbx
0x1400503fe  mov     [r14+1], sil
0x140050402  mov     ecx, r15d
0x140050405  call    CscRegistrySetValue
0x14005040a  mov     edi, eax
0x14005040c  mov     ebx, r12d
0x14005040f  test    edi, edi
0x140050411  mov     eax, 1FFh
0x140050416  cmovs   ebx, eax
0x140050419  mov     rax, [rbp+String2.Buffer]
0x14005041d  test    rax, rax
0x140050420  jz      short loc_140050437
0x140050422  xor     edx, edx; Tag
0x140050424  mov     rcx, rax; P
0x140050427  call    cs:__imp_ExFreePoolWithTag
0x14005042e  nop     dword ptr [rax+rax+00h]
0x140050433  mov     [rbp+String2.Buffer], r12
0x140050437  mov     rcx, cs:WPP_GLOBAL_Control
0x14005043e  cmp     rcx, r13
0x140050441  jz      short loc_140050466
0x140050443  mov     eax, [rcx+2Ch]
0x140050446  test    al, 20h
0x140050448  jz      short loc_140050466
0x14005044a  mov     rcx, [rcx+18h]
0x14005044e  lea     r8, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids
0x140050455  mov     edx, 0Bh
0x14005045a  mov     dword ptr [rsp+68h+var_48], ebx
0x14005045e  mov     r9d, edi
0x140050461  call    WPP_SF_Dd
0x140050466  mov     eax, edi
0x140050468  add     rsp, 68h
0x14005046c  pop     r15
0x14005046e  pop     r14
0x140050470  pop     r13
0x140050472  pop     r12
0x140050474  pop     rdi
0x140050475  pop     rsi
0x140050476  pop     rbx
0x140050477  pop     rbp
0x140050478  retn
```
