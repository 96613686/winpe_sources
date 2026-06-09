# ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(void)

- ea: `0x180002d90`
- end: `0x180002d95`
- name: `??1?$CComPtr@UIEnrollmentInfoEnumerator@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800119e6`
- `0x180011ba8`
- `0x180011bba`
- `0x180011bcc`
- `0x180011bf0`
- `0x180011c02`
- `0x180011c14`
- `0x180011c26`

## callees

- `0x180002d9c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(__int64 a1)
{
  return ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(a1);
}

```

## disassembly

```asm
0x180002d90  jmp     ??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)
```
