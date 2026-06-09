# CLogFileCtrl::GetConfig(ulong,uchar *)

- ea: `0x1800023f0`
- end: `0x18000240a`
- name: `?GetConfig@CLogFileCtrl@@UEAAJKPEAE@Z`
- size: `26`
- prototype: `__int64 __fastcall(CLogFileCtrl *__hidden this, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180010010`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::GetConfig(CLogFileCtrl *this, __int64 a2, unsigned __int8 *a3)
{
  (*(void (__fastcall **)(CLogFileCtrl *, unsigned __int8 *))(*(_QWORD *)this + 104LL))(this, a3);
  return 0;
}

```

## disassembly

```asm
0x1800023f0  sub     rsp, 28h
0x1800023f4  mov     rax, [rcx]
0x1800023f7  mov     rdx, r8
0x1800023fa  mov     rax, [rax+68h]
0x1800023fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002403  xor     eax, eax
0x180002405  add     rsp, 28h
0x180002409  retn
```
