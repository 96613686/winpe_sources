# AslStringAnsiToUnicode

- ea: `0x1400096a0`
- end: `0x1400097cc`
- name: `AslStringAnsiToUnicode`
- size: `300`
- prototype: `__int64 __fastcall(PWSTR *, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000cb60`
- `0x14000cc48`
- `0x14000d190`
- `0x14000d704`

## callees

- `0x140007074`
- `0x1400096a0`

## import_xrefs

- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x1400096cb`
- `ntdll!RtlxAnsiStringToUnicodeSize` at `0x1400096cb`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x140009770`
- `ntdll!RtlAnsiStringToUnicodeString` at `0x140009770`
- `ntdll!RtlFreeHeap` at `0x1400097bb`
- `ntdll!RtlFreeHeap` at `0x1400097bb`
- `ntdll!RtlAllocateHeap` at `0x140009729`
- `ntdll!RtlAllocateHeap` at `0x140009729`
- `ntdll!RtlInitString` at `0x1400096c1`
- `ntdll!RtlInitString` at `0x1400096c1`

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
0x1400096a0  push    rbp
0x1400096a2  push    rbx
0x1400096a3  push    rsi
0x1400096a4  push    rdi
0x1400096a5  mov     rbp, rsp
0x1400096a8  sub     rsp, 58h
0x1400096ac  mov     rsi, rcx
0x1400096af  xorps   xmm0, xmm0
0x1400096b2  xorps   xmm1, xmm1
0x1400096b5  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400096b9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400096bd  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x1400096c1  call    cs:__imp_RtlInitString
0x1400096c7  lea     rcx, [rbp+DestinationString]; AnsiString
0x1400096cb  call    cs:__imp_RtlxAnsiStringToUnicodeSize
0x1400096d1  xorps   xmm0, xmm0
0x1400096d4  mov     qword ptr [rsi], 0
0x1400096db  mov     edi, eax
0x1400096dd  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x1400096e1  cmp     eax, 0FFFFh
0x1400096e6  jbe     short loc_140009714
0x1400096e8  mov     ebx, 0C000000Dh
0x1400096ed  mov     [rsp+58h+var_38], edi
0x1400096f1  lea     r9, aAnsiStringIsTo; "Ansi string is too long to convert at %"...
0x1400096f8  mov     r8d, 18Dh
0x1400096fe  lea     rdx, aAslstringansit; "AslStringAnsiToUnicode"
0x140009705  mov     ecx, 1
0x14000970a  call    AslLogCallPrintf
0x14000970f  jmp     loc_1400097A3
0x140009714  mov     rcx, gs:60h
0x14000971d  mov     r8, rdi; Size
0x140009720  mov     edx, 8; Flags
0x140009725  mov     rcx, [rcx+30h]; HeapHandle
0x140009729  call    cs:__imp_RtlAllocateHeap
0x14000972f  mov     [rbp+var_28.Buffer], rax
0x140009733  test    rax, rax
0x140009736  jnz     short loc_14000975B
0x140009738  lea     r9, aOutOfMemory; "Out of memory"
0x14000973f  mov     r8d, 194h
0x140009745  lea     rdx, aAslstringansit; "AslStringAnsiToUnicode"
0x14000974c  mov     ebx, 0C0000017h
0x140009751  lea     ecx, [rax+1]
0x140009754  call    AslLogCallPrintf
0x140009759  jmp     short loc_1400097A3
0x14000975b  xor     eax, eax
0x14000975d  mov     [rbp+var_28.MaximumLength], di
0x140009761  xor     r8d, r8d; AllocateDestinationString
0x140009764  mov     [rbp+var_28.Length], ax
0x140009768  lea     rdx, [rbp+DestinationString]; SourceString
0x14000976c  lea     rcx, [rbp+var_28]; DestinationString
0x140009770  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140009776  mov     ebx, eax
0x140009778  test    eax, eax
0x14000977a  jns     short loc_140009792
0x14000977c  mov     [rsp+58h+var_38], eax
0x140009780  lea     r9, aRtlansistringt; "RtlAnsiStringToUnicodeString failed [%x"...
0x140009787  mov     r8d, 19Dh
0x14000978d  jmp     loc_1400096FE
0x140009792  mov     rax, [rbp+var_28.Buffer]
0x140009796  xor     ebx, ebx
0x140009798  mov     [rsi], rax
0x14000979b  mov     [rbp+var_28.Buffer], 0
0x1400097a3  mov     r8, [rbp+var_28.Buffer]; P
0x1400097a7  test    r8, r8
0x1400097aa  jz      short loc_1400097C1
0x1400097ac  mov     rcx, gs:60h
0x1400097b5  xor     edx, edx; Flags
0x1400097b7  mov     rcx, [rcx+30h]; HeapHandle
0x1400097bb  call    cs:__imp_RtlFreeHeap
0x1400097c1  mov     eax, ebx
0x1400097c3  add     rsp, 58h
0x1400097c7  pop     rdi
0x1400097c8  pop     rsi
0x1400097c9  pop     rbx
0x1400097ca  pop     rbp
0x1400097cb  retn
```
