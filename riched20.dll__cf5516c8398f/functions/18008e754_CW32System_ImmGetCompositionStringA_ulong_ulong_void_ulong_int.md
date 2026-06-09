# CW32System::ImmGetCompositionStringA(ulong,ulong,void *,ulong,int)

- ea: `0x18008e754`
- end: `0x18008e7f2`
- name: `?ImmGetCompositionStringA@CW32System@@SAJKKPEAXKH@Z`
- size: `158`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180064e28`

## callees

- `0x18008e754`
- `0x1800905e8`
- `0x180092010`

## string_xrefs

- `0x18008e7be`: `ImmGetCompositionStringA`

## pseudocode

```c
__int64 __fastcall CW32System::ImmGetCompositionStringA(
        unsigned int a1,
        unsigned int a2,
        void *a3,
        unsigned int a4,
        int a5)
{
  __int64 (__fastcall *v10)(_QWORD, _QWORD, void *, _QWORD); // rax

  if ( a5 )
  {
    (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A44B8 + 152LL))(qword_1800A44B8, a1, a2);
    return 0;
  }
  else
  {
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A40F0;
    if ( !qword_1800A40F0 )
    {
      SetIMEProcAddr(&qword_1800A40F0, 0, "ImmGetCompositionStringA");
      v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A40F0;
    }
    return v10(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x18008e754  mov     r11, rsp
0x18008e757  push    rbx
0x18008e758  push    rbp
0x18008e759  push    rsi
0x18008e75a  push    rdi
0x18008e75b  sub     rsp, 48h
0x18008e75f  cmp     [rsp+68h+arg_20], 0
0x18008e767  mov     ebx, r9d
0x18008e76a  mov     rdi, r8
0x18008e76d  mov     esi, edx
0x18008e76f  mov     ebp, ecx
0x18008e771  jz      short loc_18008E7B2
0x18008e773  mov     rcx, cs:qword_1800A44B8
0x18008e77a  lea     rdx, [r11+28h]
0x18008e77e  mov     [r11-40h], r8
0x18008e782  mov     r8d, esi
0x18008e785  mov     dword ptr [r11+28h], 0
0x18008e78d  mov     [r11-48h], rdx
0x18008e791  mov     edx, ebp
0x18008e793  mov     rax, [rcx]
0x18008e796  mov     rax, [rax+98h]
0x18008e79d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7a2  xor     ecx, ecx
0x18008e7a4  test    eax, eax
0x18008e7a6  cmovns  ecx, [rsp+68h+arg_20]
0x18008e7ae  mov     eax, ecx
0x18008e7b0  jmp     short loc_18008E7E9
0x18008e7b2  mov     rax, cs:qword_1800A40F0
0x18008e7b9  test    rax, rax
0x18008e7bc  jnz     short loc_18008E7DA
0x18008e7be  lea     r8, aImmgetcomposit_0; "ImmGetCompositionStringA"
0x18008e7c5  xor     edx, edx
0x18008e7c7  lea     rcx, qword_1800A40F0
0x18008e7ce  call    SetIMEProcAddr
0x18008e7d3  mov     rax, cs:qword_1800A40F0
0x18008e7da  mov     r9d, ebx
0x18008e7dd  mov     r8, rdi
0x18008e7e0  mov     edx, esi
0x18008e7e2  mov     ecx, ebp
0x18008e7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7e9  add     rsp, 48h
0x18008e7ed  pop     rdi
0x18008e7ee  pop     rsi
0x18008e7ef  pop     rbp
0x18008e7f0  pop     rbx
0x18008e7f1  retn
```
