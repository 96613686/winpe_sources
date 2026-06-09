# CW32System::ImmGetCompositionStringA(ulong,ulong,void *,ulong,int)

- ea: `0x180091008`
- end: `0x1800910a7`
- name: `?ImmGetCompositionStringA@CW32System@@SAJKKPEAXKH@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void *, unsigned int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180066898`

## callees

- `0x180091008`
- `0x180092fb0`
- `0x180095010`

## string_xrefs

- `0x180091072`: `ImmGetCompositionStringA`

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
    (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)qword_1800A7598 + 152LL))(qword_1800A7598, a1, a2);
    return 0;
  }
  else
  {
    v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A71D0;
    if ( !qword_1800A71D0 )
    {
      SetIMEProcAddr(&qword_1800A71D0, 0, "ImmGetCompositionStringA");
      v10 = (__int64 (__fastcall *)(_QWORD, _QWORD, void *, _QWORD))qword_1800A71D0;
    }
    return v10(a1, a2, a3, a4);
  }
}

```

## disassembly

```asm
0x180091008  mov     r11, rsp
0x18009100b  push    rbx
0x18009100c  push    rbp
0x18009100d  push    rsi
0x18009100e  push    rdi
0x18009100f  sub     rsp, 48h
0x180091013  cmp     [rsp+68h+arg_20], 0
0x18009101b  mov     ebx, r9d
0x18009101e  mov     rdi, r8
0x180091021  mov     esi, edx
0x180091023  mov     ebp, ecx
0x180091025  jz      short loc_180091066
0x180091027  mov     rcx, cs:qword_1800A7598
0x18009102e  lea     rdx, [r11+28h]
0x180091032  mov     [r11-40h], r8
0x180091036  mov     r8d, esi
0x180091039  mov     dword ptr [r11+28h], 0
0x180091041  mov     [r11-48h], rdx
0x180091045  mov     edx, ebp
0x180091047  mov     rax, [rcx]
0x18009104a  mov     rax, [rax+98h]
0x180091051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091056  xor     ecx, ecx
0x180091058  test    eax, eax
0x18009105a  cmovns  ecx, [rsp+68h+arg_20]
0x180091062  mov     eax, ecx
0x180091064  jmp     short loc_18009109D
0x180091066  mov     rax, cs:qword_1800A71D0
0x18009106d  test    rax, rax
0x180091070  jnz     short loc_18009108E
0x180091072  lea     r8, aImmgetcomposit_0; "ImmGetCompositionStringA"
0x180091079  xor     edx, edx
0x18009107b  lea     rcx, qword_1800A71D0
0x180091082  call    SetIMEProcAddr
0x180091087  mov     rax, cs:qword_1800A71D0
0x18009108e  mov     r9d, ebx
0x180091091  mov     r8, rdi
0x180091094  mov     edx, esi
0x180091096  mov     ecx, ebp
0x180091098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009109d  add     rsp, 48h
0x1800910a1  pop     rdi
0x1800910a2  pop     rsi
0x1800910a3  pop     rbp
0x1800910a4  pop     rbx
0x1800910a5  retn
```
