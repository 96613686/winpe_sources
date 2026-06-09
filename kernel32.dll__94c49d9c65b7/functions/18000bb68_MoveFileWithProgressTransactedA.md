# MoveFileWithProgressTransactedA

- ea: `0x18000bb68`
- end: `0x18000bc27`
- name: `MoveFileWithProgressTransactedA`
- size: `191`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000bb40`
- `0x180056090`
- `0x18006c010`
- `0x18006c040`

## callees

- `0x18000bb68`
- `0x18000d6c0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18000bbbe`
- `ntdll!RtlFreeUnicodeString` at `0x18000bc04`
- `ntdll!RtlFreeUnicodeString` at `0x18000bc0f`
- `ntdll!RtlFreeUnicodeString` at `0x18000bbbe`
- `ntdll!RtlFreeUnicodeString` at `0x18000bc04`
- `ntdll!RtlFreeUnicodeString` at `0x18000bc0f`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x18000bbf7`
- `KERNELBASE!MoveFileWithProgressTransactedW` at `0x18000bbf7`

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
0x18000bb68  mov     rax, rsp
0x18000bb6b  mov     [rax+8], rbx
0x18000bb6f  mov     [rax+10h], rsi
0x18000bb73  push    rdi
0x18000bb74  sub     rsp, 50h
0x18000bb78  mov     rbx, rdx
0x18000bb7b  xorps   xmm0, xmm0
0x18000bb7e  mov     rdx, rcx
0x18000bb81  xorps   xmm1, xmm1
0x18000bb84  lea     rcx, [rax-28h]
0x18000bb88  mov     rdi, r9
0x18000bb8b  mov     rsi, r8
0x18000bb8e  movups  xmmword ptr [rax-28h], xmm0
0x18000bb92  movups  xmmword ptr [rax-18h], xmm1
0x18000bb96  call    Basep8BitStringToDynamicUnicodeString
0x18000bb9b  test    eax, eax
0x18000bb9d  jnz     short loc_18000BBA3
0x18000bb9f  xor     eax, eax
0x18000bba1  jmp     short loc_18000BC17
0x18000bba3  test    rbx, rbx
0x18000bba6  jz      short loc_18000BBCD
0x18000bba8  mov     rdx, rbx
0x18000bbab  lea     rcx, [rsp+58h+var_18]
0x18000bbb0  call    Basep8BitStringToDynamicUnicodeString
0x18000bbb5  test    eax, eax
0x18000bbb7  jnz     short loc_18000BBC6
0x18000bbb9  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x18000bbbe  call    cs:__imp_RtlFreeUnicodeString
0x18000bbc4  jmp     short loc_18000BB9F
0x18000bbc6  mov     rdx, [rsp+58h+var_18.Buffer]
0x18000bbcb  jmp     short loc_18000BBD4
0x18000bbcd  xor     edx, edx
0x18000bbcf  mov     [rsp+58h+var_18.Buffer], rdx
0x18000bbd4  mov     rax, [rsp+58h+arg_28]
0x18000bbdc  mov     r9, rdi
0x18000bbdf  mov     rcx, [rsp+58h+UnicodeString.Buffer]
0x18000bbe4  mov     r8, rsi
0x18000bbe7  mov     [rsp+58h+var_30], rax
0x18000bbec  mov     eax, [rsp+58h+arg_20]
0x18000bbf3  mov     [rsp+58h+var_38], eax
0x18000bbf7  call    cs:__imp_MoveFileWithProgressTransactedW
0x18000bbfd  lea     rcx, [rsp+58h+UnicodeString]; UnicodeString
0x18000bc02  mov     ebx, eax
0x18000bc04  call    cs:__imp_RtlFreeUnicodeString
0x18000bc0a  lea     rcx, [rsp+58h+var_18]; UnicodeString
0x18000bc0f  call    cs:__imp_RtlFreeUnicodeString
0x18000bc15  mov     eax, ebx
0x18000bc17  mov     rbx, [rsp+58h+arg_0]
0x18000bc1c  mov     rsi, [rsp+58h+arg_8]
0x18000bc21  add     rsp, 50h
0x18000bc25  pop     rdi
0x18000bc26  retn
```
