# PerfEnumTextValue

- ea: `0x180008b58`
- end: `0x180008c2a`
- name: `PerfEnumTextValue`
- size: `210`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, unsigned int *, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000a638`
- `0x18000a7b8`

## callees

- `0x180008b58`
- `0x1800093a8`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180008ba6`
- `ntdll!RtlCopyUnicodeString` at `0x180008ba6`
- `ntdll!RtlInitUnicodeString` at `0x180008b98`
- `ntdll!RtlInitUnicodeString` at `0x180008b98`

## pseudocode

```c
__int64 __fastcall PerfEnumTextValue(
        HKEY a1,
        int a2,
        struct _UNICODE_STRING *a3,
        __int64 a4,
        unsigned int *a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned int *a8)
{
  const WCHAR *v10; // rdx
  unsigned __int64 Length; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  if ( a2 )
  {
    if ( a2 != 1 )
      return 259;
    v10 = L"Help";
  }
  else
  {
    v10 = L"Counter";
  }
  a3->Length = 0;
  RtlInitUnicodeString(&DestinationString, v10);
  RtlCopyUnicodeString(a3, &DestinationString);
  Length = a3->Length;
  if ( Length + 2 <= a3->MaximumLength )
  {
    a3->Buffer[Length >> 1] = 0;
    a3->Length += 2;
  }
  return PerfRegQueryValueEx(a1, &stru_1800206B8, &DestinationString, 0, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x180008b58  mov     [rsp+arg_0], rbx
0x180008b5d  push    rdi
0x180008b5e  sub     rsp, 50h
0x180008b62  xorps   xmm0, xmm0
0x180008b65  mov     rbx, r8
0x180008b68  mov     rdi, rcx
0x180008b6b  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x180008b70  test    edx, edx
0x180008b72  jnz     short loc_180008B7D
0x180008b74  lea     rdx, ?CounterValue@@3QBGB; "Counter"
0x180008b7b  jmp     short loc_180008B8D
0x180008b7d  cmp     edx, 1
0x180008b80  jnz     loc_180008C1A
0x180008b86  lea     rdx, ?HelpValue@@3QBGB; "Help"
0x180008b8d  xor     eax, eax
0x180008b8f  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x180008b94  mov     [r8], ax
0x180008b98  call    cs:__imp_RtlInitUnicodeString
0x180008b9e  lea     rdx, [rsp+58h+DestinationString]; SourceString
0x180008ba3  mov     rcx, rbx; DestinationString
0x180008ba6  call    cs:__imp_RtlCopyUnicodeString
0x180008bac  movzx   edx, word ptr [rbx]
0x180008baf  movzx   ecx, word ptr [rbx+2]
0x180008bb3  lea     rax, [rdx+2]
0x180008bb7  cmp     rax, rcx
0x180008bba  ja      short loc_180008BCD
0x180008bbc  mov     rcx, [rbx+8]
0x180008bc0  xor     eax, eax
0x180008bc2  shr     rdx, 1
0x180008bc5  mov     [rcx+rdx*2], ax
0x180008bc9  add     word ptr [rbx], 2
0x180008bcd  mov     rax, [rsp+58h+arg_38]
0x180008bd5  lea     r8, [rsp+58h+DestinationString]; struct _UNICODE_STRING *
0x180008bda  mov     [rsp+58h+var_20], rax; unsigned int *
0x180008bdf  lea     rdx, stru_1800206B8; struct _UNICODE_STRING *
0x180008be6  mov     rax, [rsp+58h+arg_30]
0x180008bee  xor     r9d, r9d; unsigned int *
0x180008bf1  mov     [rsp+58h+var_28], rax; unsigned int *
0x180008bf6  mov     rcx, rdi; HKEY
0x180008bf9  mov     rax, [rsp+58h+arg_28]
0x180008c01  mov     [rsp+58h+var_30], rax; unsigned __int8 *
0x180008c06  mov     rax, [rsp+58h+arg_20]
0x180008c0e  mov     [rsp+58h+var_38], rax; unsigned int *
0x180008c13  call    ?PerfRegQueryValueEx@@YAJPEAUHKEY__@@PEBU_UNICODE_STRING@@1PEAK2PEAE22@Z; PerfRegQueryValueEx(HKEY__ *,_UNICODE_STRING const *,_UNICODE_STRING const *,ulong *,ulong *,uchar *,ulong *,ulong *)
0x180008c18  jmp     short loc_180008C1F
0x180008c1a  mov     eax, 103h
0x180008c1f  mov     rbx, [rsp+58h+arg_0]
0x180008c24  add     rsp, 50h
0x180008c28  pop     rdi
0x180008c29  retn
```
