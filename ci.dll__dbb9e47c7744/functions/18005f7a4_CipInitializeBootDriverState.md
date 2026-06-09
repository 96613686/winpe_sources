# CipInitializeBootDriverState

- ea: `0x18005f7a4`
- end: `0x18005f87c`
- name: `CipInitializeBootDriverState`
- size: `216`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005f428`

## callees

- `0x18005f7a4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f831`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f831`
- `ntoskrnl!ExAllocatePool2` at `0x18005f7f8`
- `ntoskrnl!ExAllocatePool2` at `0x18005f7f8`

## pseudocode

```c
__int64 __fastcall CipInitializeBootDriverState(PCUNICODE_STRING SourceString, int a2, int a3)
{
  unsigned int v3; // esi
  struct _UNICODE_STRING *Pool2; // rax
  __int64 v8; // rbx
  __int64 *v9; // rax

  v3 = 0;
  if ( a2 == -1073740760 || a2 == -1058471934 || a2 == -1073740285 || a2 >= 0 && (a3 & 0x321) != 0 )
  {
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(258, SourceString->Length + 40LL, 1668499779);
    v8 = (__int64)Pool2;
    if ( Pool2 )
    {
      Pool2[1].Length = SourceString->Length;
      Pool2[1].MaximumLength = SourceString->Length;
      Pool2[1].Buffer = (PWSTR)&Pool2[2].Buffer;
      RtlCopyUnicodeString(Pool2 + 1, SourceString);
      *(_DWORD *)(v8 + 32) = a2;
      *(_DWORD *)(v8 + 36) = a3;
      v9 = (__int64 *)qword_18004A568;
      if ( *(PVOID **)qword_18004A568 != &g_BootDriverList )
        __fastfail(3u);
      *(_QWORD *)v8 = &g_BootDriverList;
      *(_QWORD *)(v8 + 8) = v9;
      *v9 = v8;
      qword_18004A568 = v8;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005f7a4  push    rbx
0x18005f7a6  push    rbp
0x18005f7a7  push    rsi
0x18005f7a8  push    rdi
0x18005f7a9  push    r14
0x18005f7ab  sub     rsp, 20h
0x18005f7af  xor     esi, esi
0x18005f7b1  mov     ebp, r8d
0x18005f7b4  mov     edi, edx
0x18005f7b6  mov     r14, rcx
0x18005f7b9  cmp     edx, 0C0000428h
0x18005f7bf  jz      short loc_18005F7E6
0x18005f7c1  cmp     edx, 0C0E90002h
0x18005f7c7  jz      short loc_18005F7E6
0x18005f7c9  cmp     edx, 0C0000603h
0x18005f7cf  jz      short loc_18005F7E6
0x18005f7d1  test    edx, edx
0x18005f7d3  js      loc_18005F86E
0x18005f7d9  test    r8d, 321h
0x18005f7e0  jz      loc_18005F86E
0x18005f7e6  movzx   edx, word ptr [rcx]
0x18005f7e9  mov     r8d, 63734943h
0x18005f7ef  add     rdx, 28h ; '('
0x18005f7f3  mov     ecx, 102h
0x18005f7f8  call    cs:__imp_ExAllocatePool2
0x18005f7ff  nop     dword ptr [rax+rax+00h]
0x18005f804  mov     rbx, rax
0x18005f807  test    rax, rax
0x18005f80a  jnz     short loc_18005F813
0x18005f80c  mov     esi, 0C0000017h
0x18005f811  jmp     short loc_18005F86E
0x18005f813  lea     rcx, [rax+10h]; DestinationString
0x18005f817  mov     rdx, r14; SourceString
0x18005f81a  movzx   eax, word ptr [r14]
0x18005f81e  mov     [rcx], ax
0x18005f821  movzx   eax, word ptr [r14]
0x18005f825  mov     [rbx+12h], ax
0x18005f829  lea     rax, [rbx+28h]
0x18005f82d  mov     [rbx+18h], rax
0x18005f831  call    cs:__imp_RtlCopyUnicodeString
0x18005f838  nop     dword ptr [rax+rax+00h]
0x18005f83d  mov     [rbx+20h], edi
0x18005f840  lea     rcx, g_BootDriverList
0x18005f847  mov     [rbx+24h], ebp
0x18005f84a  mov     rax, cs:qword_18004A568
0x18005f851  cmp     [rax], rcx
0x18005f854  jz      short loc_18005F85D
0x18005f856  mov     ecx, 3
0x18005f85b  int     29h; Win8: RtlFailFast(ecx)
0x18005f85d  mov     [rbx], rcx
0x18005f860  mov     [rbx+8], rax
0x18005f864  mov     [rax], rbx
0x18005f867  mov     cs:qword_18004A568, rbx
0x18005f86e  mov     eax, esi
0x18005f870  add     rsp, 20h
0x18005f874  pop     r14
0x18005f876  pop     rdi
0x18005f877  pop     rsi
0x18005f878  pop     rbp
0x18005f879  pop     rbx
0x18005f87a  retn
```
