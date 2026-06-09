# CW32System::ImmGetCompositionStringW(ulong,ulong,void *,ulong,int)

- ea: `0x18008e7f8`
- end: `0x18008e896`
- name: `?ImmGetCompositionStringW@CW32System@@SAJKKPEAXKH@Z`
- size: `158`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180064e28`

## callees

- `0x18008e7f8`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008e862`: `ImmGetCompositionStringW`

## pseudocode

```c
__int64 __fastcall CW32System::ImmGetCompositionStringW(
        unsigned int a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        int a5)
{
  __int64 (__fastcall *v10)(_QWORD, _QWORD, void *, _QWORD); // rax

  if ( a5 )
  {
    (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A44B8 + 160LL))(qword_1800A44B8, a1, a2);
    return 0;
  }
  else
  {
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A40F8;
    if ( !qword_1800A40F8 )
    {
      SetIMEProcAddr(&qword_1800A40F8, 0, "ImmGetCompositionStringW");
      v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A40F8;
    }
    return v10(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x18008e7f8  mov     r11, rsp
0x18008e7fb  push    rbx
0x18008e7fc  push    rbp
0x18008e7fd  push    rsi
0x18008e7fe  push    rdi
0x18008e7ff  sub     rsp, 48h
0x18008e803  cmp     [rsp+68h+arg_20], 0
0x18008e80b  mov     ebx, r9d
0x18008e80e  mov     rdi, r8
0x18008e811  mov     esi, edx
0x18008e813  mov     ebp, ecx
0x18008e815  jz      short loc_18008E856
0x18008e817  mov     rcx, cs:qword_1800A44B8
0x18008e81e  lea     rdx, [r11+28h]
0x18008e822  mov     [r11-40h], r8
0x18008e826  mov     r8d, esi
0x18008e829  mov     dword ptr [r11+28h], 0
0x18008e831  mov     [r11-48h], rdx
0x18008e835  mov     edx, ebp
0x18008e837  mov     rax, [rcx]
0x18008e83a  mov     rax, [rax+0A0h]
0x18008e841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e846  xor     ecx, ecx
0x18008e848  test    eax, eax
0x18008e84a  cmovns  ecx, [rsp+68h+arg_20]
0x18008e852  mov     eax, ecx
0x18008e854  jmp     short loc_18008E88D
0x18008e856  mov     rax, cs:qword_1800A40F8
0x18008e85d  test    rax, rax
0x18008e860  jnz     short loc_18008E87E
0x18008e862  lea     r8, aImmgetcomposit; "ImmGetCompositionStringW"
0x18008e869  xor     edx, edx
0x18008e86b  lea     rcx, qword_1800A40F8
0x18008e872  call    SetIMEProcAddr
0x18008e877  mov     rax, cs:qword_1800A40F8
0x18008e87e  mov     r9d, ebx
0x18008e881  mov     r8, rdi
0x18008e884  mov     edx, esi
0x18008e886  mov     ecx, ebp
0x18008e888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e88d  add     rsp, 48h
0x18008e891  pop     rdi
0x18008e892  pop     rsi
0x18008e893  pop     rbp
0x18008e894  pop     rbx
0x18008e895  retn
```
