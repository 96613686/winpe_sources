# CipInitializeBootDriverState

- ea: `0x18005f744`
- end: `0x18005f81c`
- name: `CipInitializeBootDriverState`
- size: `216`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005f3c8`

## callees

- `0x18005f744`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f7d1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18005f7d1`
- `ntoskrnl!ExAllocatePool2` at `0x18005f798`
- `ntoskrnl!ExAllocatePool2` at `0x18005f798`

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
      v9 = (__int64 *)qword_18004A608;
      if ( *(PVOID **)qword_18004A608 != &g_BootDriverList )
        __fastfail(3u);
      *(_QWORD *)v8 = &g_BootDriverList;
      *(_QWORD *)(v8 + 8) = v9;
      *v9 = v8;
      qword_18004A608 = v8;
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
0x18005f744  push    rbx
0x18005f746  push    rbp
0x18005f747  push    rsi
0x18005f748  push    rdi
0x18005f749  push    r14
0x18005f74b  sub     rsp, 20h
0x18005f74f  xor     esi, esi
0x18005f751  mov     ebp, r8d
0x18005f754  mov     edi, edx
0x18005f756  mov     r14, rcx
0x18005f759  cmp     edx, 0C0000428h
0x18005f75f  jz      short loc_18005F786
0x18005f761  cmp     edx, 0C0E90002h
0x18005f767  jz      short loc_18005F786
0x18005f769  cmp     edx, 0C0000603h
0x18005f76f  jz      short loc_18005F786
0x18005f771  test    edx, edx
0x18005f773  js      loc_18005F80E
0x18005f779  test    r8d, 321h
0x18005f780  jz      loc_18005F80E
0x18005f786  movzx   edx, word ptr [rcx]
0x18005f789  mov     r8d, 63734943h
0x18005f78f  add     rdx, 28h ; '('
0x18005f793  mov     ecx, 102h
0x18005f798  call    cs:__imp_ExAllocatePool2
0x18005f79f  nop     dword ptr [rax+rax+00h]
0x18005f7a4  mov     rbx, rax
0x18005f7a7  test    rax, rax
0x18005f7aa  jnz     short loc_18005F7B3
0x18005f7ac  mov     esi, 0C0000017h
0x18005f7b1  jmp     short loc_18005F80E
0x18005f7b3  lea     rcx, [rax+10h]; DestinationString
0x18005f7b7  mov     rdx, r14; SourceString
0x18005f7ba  movzx   eax, word ptr [r14]
0x18005f7be  mov     [rcx], ax
0x18005f7c1  movzx   eax, word ptr [r14]
0x18005f7c5  mov     [rbx+12h], ax
0x18005f7c9  lea     rax, [rbx+28h]
0x18005f7cd  mov     [rbx+18h], rax
0x18005f7d1  call    cs:__imp_RtlCopyUnicodeString
0x18005f7d8  nop     dword ptr [rax+rax+00h]
0x18005f7dd  mov     [rbx+20h], edi
0x18005f7e0  lea     rcx, g_BootDriverList
0x18005f7e7  mov     [rbx+24h], ebp
0x18005f7ea  mov     rax, cs:qword_18004A608
0x18005f7f1  cmp     [rax], rcx
0x18005f7f4  jz      short loc_18005F7FD
0x18005f7f6  mov     ecx, 3
0x18005f7fb  int     29h; Win8: RtlFailFast(ecx)
0x18005f7fd  mov     [rbx], rcx
0x18005f800  mov     [rbx+8], rax
0x18005f804  mov     [rax], rbx
0x18005f807  mov     cs:qword_18004A608, rbx
0x18005f80e  mov     eax, esi
0x18005f810  add     rsp, 20h
0x18005f814  pop     r14
0x18005f816  pop     rdi
0x18005f817  pop     rsi
0x18005f818  pop     rbp
0x18005f819  pop     rbx
0x18005f81a  retn
```
