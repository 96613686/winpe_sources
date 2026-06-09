# CW32System::ImmSetOpenStatus(ulong,int,int)

- ea: `0x18008ee3c`
- end: `0x18008eead`
- name: `?ImmSetOpenStatus@CW32System@@SAHKHH@Z`
- size: `113`
- prototype: `__int64 __fastcall(unsigned int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800526d8`
- `0x180052a18`

## callees

- `0x18008ee3c`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008ee7d`: `ImmSetOpenStatus`

## pseudocode

```c
__int64 __fastcall CW32System::ImmSetOpenStatus(unsigned int a1, unsigned int a2, int a3)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rax

  if ( a3 )
    return (*(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A44B8 + 440LL))(
             qword_1800A44B8,
             a1,
             a2) >= 0;
  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1800A4168;
  if ( !qword_1800A4168 )
  {
    SetIMEProcAddr(&qword_1800A4168, 0, "ImmSetOpenStatus");
    v6 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1800A4168;
  }
  return v6(a1, a2);
}

```

## disassembly

```asm
0x18008ee3c  mov     [rsp+arg_0], rbx
0x18008ee41  push    rdi
0x18008ee42  sub     rsp, 20h
0x18008ee46  mov     ebx, edx
0x18008ee48  mov     edi, ecx
0x18008ee4a  test    r8d, r8d
0x18008ee4d  jz      short loc_18008EE71
0x18008ee4f  mov     rcx, cs:qword_1800A44B8
0x18008ee56  mov     r8d, edx
0x18008ee59  mov     edx, edi
0x18008ee5b  mov     rax, [rcx]
0x18008ee5e  mov     rax, [rax+1B8h]
0x18008ee65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee6a  not     eax
0x18008ee6c  shr     eax, 1Fh
0x18008ee6f  jmp     short loc_18008EEA2
0x18008ee71  mov     rax, cs:qword_1800A4168
0x18008ee78  test    rax, rax
0x18008ee7b  jnz     short loc_18008EE99
0x18008ee7d  lea     r8, aImmsetopenstat; "ImmSetOpenStatus"
0x18008ee84  xor     edx, edx
0x18008ee86  lea     rcx, qword_1800A4168
0x18008ee8d  call    SetIMEProcAddr
0x18008ee92  mov     rax, cs:qword_1800A4168
0x18008ee99  mov     edx, ebx
0x18008ee9b  mov     ecx, edi
0x18008ee9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eea2  mov     rbx, [rsp+28h+arg_0]
0x18008eea7  add     rsp, 20h
0x18008eeab  pop     rdi
0x18008eeac  retn
```
