# EnrollmentInfoEnumerator::EnrollmentInfoEnumerator(void)

- ea: `0x18000ef20`
- end: `0x18000ef4c`
- name: `??0EnrollmentInfoEnumerator@@QEAA@XZ`
- size: `44`
- prototype: `EnrollmentInfoEnumerator *__fastcall(EnrollmentInfoEnumerator *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e410`
- `0x18000e4e0`
- `0x18000e5b0`
- `0x18000e674`
- `0x18000e750`
- `0x18000e860`

## pseudocode

```c
EnrollmentInfoEnumerator *__fastcall EnrollmentInfoEnumerator::EnrollmentInfoEnumerator(EnrollmentInfoEnumerator *this)
{
  *(_QWORD *)this = &EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'};
  *((_QWORD *)this + 1) = &EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'};
  *((_DWORD *)this + 4) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  return this;
}

```

## disassembly

```asm
0x18000ef20  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIEnrollmentInfoEnumerator@@@; const EnrollmentInfoEnumerator::`vftable'{for `IEnrollmentInfoEnumerator'}
0x18000ef27  mov     [rcx], rax
0x18000ef2a  lea     rax, ??_7EnrollmentInfoEnumerator@@6BIAttachEnrollEngine@@@; const EnrollmentInfoEnumerator::`vftable'{for `IAttachEnrollEngine'}
0x18000ef31  mov     [rcx+8], rax
0x18000ef35  xor     eax, eax
0x18000ef37  mov     [rcx+10h], eax
0x18000ef3a  mov     [rcx+20h], rax
0x18000ef3e  mov     [rcx+28h], eax
0x18000ef41  mov     [rcx+30h], rax
0x18000ef45  mov     [rcx+38h], eax
0x18000ef48  mov     rax, rcx
0x18000ef4b  retn
```
