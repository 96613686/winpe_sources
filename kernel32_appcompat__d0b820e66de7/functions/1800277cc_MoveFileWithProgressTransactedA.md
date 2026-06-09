# MoveFileWithProgressTransactedA

- ea: `0x1800277cc`
- end: `0x1800278a7`
- name: `MoveFileWithProgressTransactedA`
- size: `219`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800277a0`
- `0x18005ab00`
- `0x180073560`
- `0x180073590`

## callees

- `0x1800277cc`
- `0x180028f60`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180027825`
- `ntdll!RtlFreeUnicodeString` at `0x180027877`
- `ntdll!RtlFreeUnicodeString` at `0x180027888`
- `ntdll!RtlFreeUnicodeString` at `0x180027825`
- `ntdll!RtlFreeUnicodeString` at `0x180027877`
- `ntdll!RtlFreeUnicodeString` at `0x180027888`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x180027864`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x180027864`

## pseudocode

```c
__int64 __fastcall MoveFileWithProgressTransactedA(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  PWSTR Buffer; // rdx
  unsigned int v11; // ebx
  struct _UNICODE_STRING UnicodeString; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING v13; // [rsp+40h] [rbp-18h] BYREF

  UnicodeString = 0;
  v13 = 0;
  if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(&UnicodeString, a1) )
    return 0;
  if ( a2 )
  {
    if ( !(unsigned int)Basep8BitStringToDynamicUnicodeString(&v13, a2) )
    {
      RtlFreeUnicodeString(&UnicodeString);
      return 0;
    }
    Buffer = v13.Buffer;
  }
  else
  {
    Buffer = 0;
    v13.Buffer = 0;
  }
  v11 = MoveFileWithProgressTransactedW(UnicodeString.Buffer, Buffer, a3, a4, a5, a6);
  RtlFreeUnicodeString(&UnicodeString);
  RtlFreeUnicodeString(&v13);
  return v11;
}

```

## disassembly

```asm
0x1800277cc  mov     rax, rsp
0x1800277cf  mov     [rax+8], rbx
0x1800277d3  mov     [rax+10h], rsi
0x1800277d7  push    rdi
0x1800277d8  sub     rsp, 50h
0x1800277dc  mov     rbx, rdx
0x1800277df  xorps   xmm0, xmm0
0x1800277e2  mov     rdx, rcx
0x1800277e5  xorps   xmm1, xmm1
0x1800277e8  lea     rcx, [rax-28h]
0x1800277ec  mov     rdi, r9
0x1800277ef  mov     rsi, r8
0x1800277f2  movups  xmmword ptr [rax-28h], xmm0
0x1800277f6  movups  xmmword ptr [rax-18h], xmm1
0x1800277fa  call    Basep8BitStringToDynamicUnicodeString
0x1800277ff  test    eax, eax
0x180027801  jnz     short loc_18002780A
0x180027803  xor     eax, eax
0x180027805  jmp     loc_180027896
0x18002780a  test    rbx, rbx
0x18002780d  jz      short loc_18002783A
0x18002780f  mov     rdx, rbx
0x180027812  lea     rcx, [rsp+58h+var_18]
0x180027817  call    Basep8BitStringToDynamicUnicodeString
0x18002781c  test    eax, eax
0x18002781e  jnz     short loc_180027833
0x180027820  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180027825  call    cs:__imp_RtlFreeUnicodeString
0x18002782c  nop     dword ptr [rax+rax+00h]
0x180027831  jmp     short loc_180027803
0x180027833  mov     rdx, [rsp+58h+var_18.Buffer]
0x180027838  jmp     short loc_180027841
0x18002783a  xor     edx, edx
0x18002783c  mov     [rsp+58h+var_18.Buffer], rdx
0x180027841  mov     rax, [rsp+58h+arg_28]
0x180027849  mov     r9, rdi
0x18002784c  mov     rcx, [rsp+58h+UnicodeString.Buffer]
0x180027851  mov     r8, rsi
0x180027854  mov     [rsp+58h+var_30], rax
0x180027859  mov     eax, [rsp+58h+arg_20]
0x180027860  mov     [rsp+58h+var_38], eax
0x180027864  call    cs:__imp_MoveFileWithProgressTransactedW
0x18002786b  nop     dword ptr [rax+rax+00h]
0x180027870  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x180027875  mov     ebx, eax
0x180027877  call    cs:__imp_RtlFreeUnicodeString
0x18002787e  nop     dword ptr [rax+rax+00h]
0x180027883  lea     rcx, [rsp+58h+var_18]; UnicodeString
0x180027888  call    cs:__imp_RtlFreeUnicodeString
0x18002788f  nop     dword ptr [rax+rax+00h]
0x180027894  mov     eax, ebx
0x180027896  mov     rbx, [rsp+58h+arg_0]
0x18002789b  mov     rsi, [rsp+58h+arg_8]
0x1800278a0  add     rsp, 50h
0x1800278a4  pop     rdi
0x1800278a5  retn
```
