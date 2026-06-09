# EdppIsExcludedName

- ea: `0x14005323c`
- end: `0x14005330d`
- name: `EdppIsExcludedName`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400510ac`

## callees

- `0x14000a7d4`
- `0x140053184`
- `0x14005323c`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400532bf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400532bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400532a8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400532a8`

## pseudocode

```c
char __fastcall EdppIsExcludedName(unsigned __int16 *a1)
{
  __int64 v1; // rdx
  WCHAR *v3; // rbx
  WCHAR *v4; // rcx
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  int v8; // [rsp+50h] [rbp+10h] BYREF
  WCHAR *v9; // [rsp+58h] [rbp+18h] BYREF

  v1 = *((_QWORD *)a1 + 1) + *a1;
  v9 = 0;
  v8 = 0;
  if ( (unsigned __int8)EdppGetExtensionLocation(a1, v1, &v9, &v8, 0, 0, 0, 0) )
  {
    v3 = v9;
    String2.Buffer = v9;
    String2.Length = 2 * v8;
    String2.MaximumLength = 2 * v8;
    RtlInitUnicodeString(&DestinationString, L"part");
    if ( RtlCompareUnicodeString(&DestinationString, &String2, 1u) )
    {
      v4 = v3;
      return IsExcludedExtension(v4, v8);
    }
    if ( (unsigned __int8)EdppGetExtensionLocation(
                            a1,
                            v3 - 1,
                            &v9,
                            &v8,
                            *(_QWORD *)&String2.Length,
                            String2.Buffer,
                            *(_QWORD *)&DestinationString.Length,
                            DestinationString.Buffer) )
    {
      v4 = v9;
      return IsExcludedExtension(v4, v8);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14005323c  mov     [rsp-8+arg_10], rbx
0x140053241  mov     [rsp-8+arg_18], rdi
0x140053246  push    rbp
0x140053247  mov     rbp, rsp
0x14005324a  sub     rsp, 40h
0x14005324e  movzx   edx, word ptr [rcx]
0x140053251  lea     r9, [rbp+arg_0]
0x140053255  add     rdx, [rcx+8]
0x140053259  lea     r8, [rbp+arg_8]
0x14005325d  xorps   xmm0, xmm0
0x140053260  mov     [rbp+arg_8], 0
0x140053268  xorps   xmm1, xmm1
0x14005326b  mov     [rbp+arg_0], 0
0x140053272  mov     rdi, rcx
0x140053275  movups  xmmword ptr [rbp+String2.Length], xmm0
0x140053279  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14005327d  call    EdppGetExtensionLocation
0x140053282  test    al, al
0x140053284  jz      short loc_1400532FA
0x140053286  movzx   eax, word ptr [rbp+arg_0]
0x14005328a  lea     rdx, aPart; "part"
0x140053291  mov     rbx, [rbp+arg_8]
0x140053295  lea     rcx, [rbp+DestinationString]; DestinationString
0x140053299  add     ax, ax
0x14005329c  mov     [rbp+String2.Buffer], rbx
0x1400532a0  mov     [rbp+String2.Length], ax
0x1400532a4  mov     [rbp+String2.MaximumLength], ax
0x1400532a8  call    cs:__imp_RtlInitUnicodeString
0x1400532af  nop     dword ptr [rax+rax+00h]
0x1400532b4  mov     r8b, 1; CaseInSensitive
0x1400532b7  lea     rdx, [rbp+String2]; String2
0x1400532bb  lea     rcx, [rbp+DestinationString]; String1
0x1400532bf  call    cs:__imp_RtlCompareUnicodeString
0x1400532c6  nop     dword ptr [rax+rax+00h]
0x1400532cb  test    eax, eax
0x1400532cd  jz      short loc_1400532DC
0x1400532cf  mov     rcx, rbx
0x1400532d2  mov     edx, [rbp+arg_0]
0x1400532d5  call    IsExcludedExtension
0x1400532da  jmp     short loc_1400532FC
0x1400532dc  lea     rdx, [rbx-2]
0x1400532e0  mov     rcx, rdi
0x1400532e3  lea     r9, [rbp+arg_0]
0x1400532e7  lea     r8, [rbp+arg_8]
0x1400532eb  call    EdppGetExtensionLocation
0x1400532f0  test    al, al
0x1400532f2  jz      short loc_1400532FA
0x1400532f4  mov     rcx, [rbp+arg_8]
0x1400532f8  jmp     short loc_1400532D2
0x1400532fa  xor     al, al
0x1400532fc  mov     rbx, [rsp+40h+arg_10]
0x140053301  mov     rdi, [rsp+40h+arg_18]
0x140053306  add     rsp, 40h
0x14005330a  pop     rbp
0x14005330b  retn
```
