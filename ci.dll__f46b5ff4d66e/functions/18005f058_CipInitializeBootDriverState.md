# CipInitializeBootDriverState

- ea: `0x18005f058`
- end: `0x18005f130`
- name: `CipInitializeBootDriverState`
- size: `216`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005ecdc`

## callees

- `0x18005f058`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f0e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f0e5`
- `ntoskrnl!ExAllocatePool2` at `0x18005f0ac`
- `ntoskrnl!ExAllocatePool2` at `0x18005f0ac`

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
      v9 = (__int64 *)qword_180049608;
      if ( *(PVOID **)qword_180049608 != &g_BootDriverList )
        __fastfail(3u);
      *(_QWORD *)v8 = &g_BootDriverList;
      *(_QWORD *)(v8 + 8) = v9;
      *v9 = v8;
      qword_180049608 = v8;
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
0x18005f058  push    rbx
0x18005f05a  push    rbp
0x18005f05b  push    rsi
0x18005f05c  push    rdi
0x18005f05d  push    r14
0x18005f05f  sub     rsp, 20h
0x18005f063  xor     esi, esi
0x18005f065  mov     ebp, r8d
0x18005f068  mov     edi, edx
0x18005f06a  mov     r14, rcx
0x18005f06d  cmp     edx, 0C0000428h
0x18005f073  jz      short loc_18005F09A
0x18005f075  cmp     edx, 0C0E90002h
0x18005f07b  jz      short loc_18005F09A
0x18005f07d  cmp     edx, 0C0000603h
0x18005f083  jz      short loc_18005F09A
0x18005f085  test    edx, edx
0x18005f087  js      loc_18005F122
0x18005f08d  test    r8d, 321h
0x18005f094  jz      loc_18005F122
0x18005f09a  movzx   edx, word ptr [rcx]
0x18005f09d  mov     r8d, 63734943h
0x18005f0a3  add     rdx, 28h ; '('
0x18005f0a7  mov     ecx, 102h
0x18005f0ac  call    cs:__imp_ExAllocatePool2
0x18005f0b3  nop     dword ptr [rax+rax+00h]
0x18005f0b8  mov     rbx, rax
0x18005f0bb  test    rax, rax
0x18005f0be  jnz     short loc_18005F0C7
0x18005f0c0  mov     esi, 0C0000017h
0x18005f0c5  jmp     short loc_18005F122
0x18005f0c7  lea     rcx, [rax+10h]; DestinationString
0x18005f0cb  mov     rdx, r14; SourceString
0x18005f0ce  movzx   eax, word ptr [r14]
0x18005f0d2  mov     [rcx], ax
0x18005f0d5  movzx   eax, word ptr [r14]
0x18005f0d9  mov     [rbx+12h], ax
0x18005f0dd  lea     rax, [rbx+28h]
0x18005f0e1  mov     [rbx+18h], rax
0x18005f0e5  call    cs:__imp_RtlCopyUnicodeString
0x18005f0ec  nop     dword ptr [rax+rax+00h]
0x18005f0f1  mov     [rbx+20h], edi
0x18005f0f4  lea     rcx, g_BootDriverList
0x18005f0fb  mov     [rbx+24h], ebp
0x18005f0fe  mov     rax, cs:qword_180049608
0x18005f105  cmp     [rax], rcx
0x18005f108  jz      short loc_18005F111
0x18005f10a  mov     ecx, 3
0x18005f10f  int     29h; Win8: RtlFailFast(ecx)
0x18005f111  mov     [rbx], rcx
0x18005f114  mov     [rbx+8], rax
0x18005f118  mov     [rax], rbx
0x18005f11b  mov     cs:qword_180049608, rbx
0x18005f122  mov     eax, esi
0x18005f124  add     rsp, 20h
0x18005f128  pop     r14
0x18005f12a  pop     rdi
0x18005f12b  pop     rsi
0x18005f12c  pop     rbp
0x18005f12d  pop     rbx
0x18005f12e  retn
```
