# AslStringAnsiToUnicode

- ea: `0x18000edc0`
- end: `0x18000eeec`
- name: `AslStringAnsiToUnicode`
- size: `300`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f6e4`
- `0x18000f7cc`
- `0x18000fd14`
- `0x180010288`

## callees

- `0x18000e240`
- `0x18000edc0`

## import_xrefs

- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x18000edeb`
- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x18000edeb`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000ee90`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x18000ee90`
- `ntdll!RtlFreeHeap` at `0x18000eedb`
- `ntdll!RtlFreeHeap` at `0x18000eedb`
- `ntdll!RtlAllocateHeap` at `0x18000ee49`
- `ntdll!RtlAllocateHeap` at `0x18000ee49`
- `ntdll!RtlInitString` at `0x18000ede1`
- `ntdll!RtlInitString` at `0x18000ede1`

## pseudocode

```c
__int64 __fastcall AslStringAnsiToUnicode(PWSTR *a1, const char *a2)
{
  ULONG v3; // eax
  USHORT v4; // di
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  struct _UNICODE_STRING v8; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF

  DestinationString = 0;
  RtlInitString(&DestinationString, a2);
  v3 = RtlxAnsiStringToUnicodeSize(&DestinationString);
  *a1 = 0;
  v4 = v3;
  v8 = 0;
  if ( v3 <= 0xFFFF )
  {
    v8.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v3);
    if ( v8.Buffer )
    {
      v8.MaximumLength = v4;
      v8.Length = 0;
      v6 = RtlAnsiStringToUnicodeString(&v8, &DestinationString, 0);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v5 = 0;
        *a1 = v8.Buffer;
        v8.Buffer = 0;
      }
      else
      {
        AslLogCallPrintf(1, "AslStringAnsiToUnicode", 413, "RtlAnsiStringToUnicodeString failed [%x]", v6);
      }
    }
    else
    {
      v5 = -1073741801;
      AslLogCallPrintf(1, "AslStringAnsiToUnicode", 404, "Out of memory");
    }
  }
  else
  {
    v5 = -1073741811;
    AslLogCallPrintf(1, "AslStringAnsiToUnicode", 397, "Ansi string is too long to convert at %d", v3);
  }
  if ( v8.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8.Buffer);
  return v5;
}

```

## disassembly

```asm
0x18000edc0  push    rbp
0x18000edc2  push    rbx
0x18000edc3  push    rsi
0x18000edc4  push    rdi
0x18000edc5  mov     rbp, rsp
0x18000edc8  sub     rsp, 58h
0x18000edcc  mov     rsi, rcx
0x18000edcf  xorps   xmm0, xmm0
0x18000edd2  xorps   xmm1, xmm1
0x18000edd5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000edd9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000eddd  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x18000ede1  call    cs:__imp_RtlInitString
0x18000ede7  lea     rcx, [rbp+DestinationString]; AnsiString
0x18000edeb  call    cs:__imp_RtlxAnsiStringToUnicodeSize
0x18000edf1  xorps   xmm0, xmm0
0x18000edf4  mov     qword ptr [rsi], 0
0x18000edfb  mov     edi, eax
0x18000edfd  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x18000ee01  cmp     eax, 0FFFFh
0x18000ee06  jbe     short loc_18000EE34
0x18000ee08  mov     ebx, 0C000000Dh
0x18000ee0d  mov     [rsp+58h+var_38], edi
0x18000ee11  lea     r9, aAnsiStringIsTo; "Ansi string is too long to convert at %"...
0x18000ee18  mov     r8d, 18Dh
0x18000ee1e  lea     rdx, aAslstringansit; "AslStringAnsiToUnicode"
0x18000ee25  mov     ecx, 1
0x18000ee2a  call    AslLogCallPrintf
0x18000ee2f  jmp     loc_18000EEC3
0x18000ee34  mov     rcx, gs:60h
0x18000ee3d  mov     r8, rdi; Size
0x18000ee40  mov     edx, 8; Flags
0x18000ee45  mov     rcx, [rcx+30h]; HeapHandle
0x18000ee49  call    cs:__imp_RtlAllocateHeap
0x18000ee4f  mov     [rbp+var_28.Buffer], rax
0x18000ee53  test    rax, rax
0x18000ee56  jnz     short loc_18000EE7B
0x18000ee58  lea     r9, aOutOfMemory; "Out of memory"
0x18000ee5f  mov     r8d, 194h
0x18000ee65  lea     rdx, aAslstringansit; "AslStringAnsiToUnicode"
0x18000ee6c  mov     ebx, 0C0000017h
0x18000ee71  lea     ecx, [rax+1]
0x18000ee74  call    AslLogCallPrintf
0x18000ee79  jmp     short loc_18000EEC3
0x18000ee7b  xor     eax, eax
0x18000ee7d  mov     [rbp+var_28.MaximumLength], di
0x18000ee81  xor     r8d, r8d; AllocateDestinationString
0x18000ee84  mov     [rbp+var_28.Length], ax
0x18000ee88  lea     rdx, [rbp+DestinationString]; SourceString
0x18000ee8c  lea     rcx, [rbp+var_28]; DestinationString
0x18000ee90  call    cs:__imp_RtlAnsiStringToUnicodeString
0x18000ee96  mov     ebx, eax
0x18000ee98  test    eax, eax
0x18000ee9a  jns     short loc_18000EEB2
0x18000ee9c  mov     [rsp+58h+var_38], eax
0x18000eea0  lea     r9, aRtlansistringt; "RtlAnsiStringToUnicodeString failed [%x"...
0x18000eea7  mov     r8d, 19Dh
0x18000eead  jmp     loc_18000EE1E
0x18000eeb2  mov     rax, [rbp+var_28.Buffer]
0x18000eeb6  xor     ebx, ebx
0x18000eeb8  mov     [rsi], rax
0x18000eebb  mov     [rbp+var_28.Buffer], 0
0x18000eec3  mov     r8, [rbp+var_28.Buffer]; P
0x18000eec7  test    r8, r8
0x18000eeca  jz      short loc_18000EEE1
0x18000eecc  mov     rcx, gs:60h
0x18000eed5  xor     edx, edx; Flags
0x18000eed7  mov     rcx, [rcx+30h]; HeapHandle
0x18000eedb  call    cs:__imp_RtlFreeHeap
0x18000eee1  mov     eax, ebx
0x18000eee3  add     rsp, 58h
0x18000eee7  pop     rdi
0x18000eee8  pop     rsi
0x18000eee9  pop     rbx
0x18000eeea  pop     rbp
0x18000eeeb  retn
```
