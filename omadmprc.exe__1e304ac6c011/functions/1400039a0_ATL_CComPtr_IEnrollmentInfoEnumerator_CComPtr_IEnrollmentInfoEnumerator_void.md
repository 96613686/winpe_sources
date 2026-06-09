# ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(void)

- ea: `0x1400039a0`
- end: `0x1400039bf`
- name: `??1?$CComPtr@UIEnrollmentInfoEnumerator@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001583f`
- `0x140015851`

## callees

- `0x1400039a0`
- `0x140017010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1400039a0  sub     rsp, 28h
0x1400039a4  mov     rcx, [rcx]
0x1400039a7  test    rcx, rcx
0x1400039aa  jz      short loc_1400039B9
0x1400039ac  mov     rax, [rcx]
0x1400039af  mov     rax, [rax+10h]
0x1400039b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039b8  nop
0x1400039b9  add     rsp, 28h
0x1400039bd  retn
```
