# ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(void)

- ea: `0x180005ebc`
- end: `0x180005edb`
- name: `??1?$CComPtr@UIEnrollmentInfoEnumerator@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006c5c`
- `0x180006c80`

## callees

- `0x180005ebc`
- `0x180007010`

## pseudocode

```c
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
0x180005ebc  sub     rsp, 28h
0x180005ec0  mov     rcx, [rcx]
0x180005ec3  test    rcx, rcx
0x180005ec6  jz      short loc_180005ED5
0x180005ec8  mov     rax, [rcx]
0x180005ecb  mov     rax, [rax+10h]
0x180005ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed4  nop
0x180005ed5  add     rsp, 28h
0x180005ed9  retn
```
