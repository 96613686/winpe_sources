# ATL::CComObject<CPersistSession>::Release(void)

- ea: `0x180015370`
- end: `0x1800153af`
- name: `?Release@?$CComObject@VCPersistSession@@@ATL@@UEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800153c0`
- `0x1800153d0`
- `0x1800153e0`

## callees

- `0x180001db8`
- `0x18000ca08`
- `0x180013d84`
- `0x180015370`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CPersistSession>::Release(int *a1)
{
  unsigned int v2; // edi

  v2 = ATL::SafeDecrementReferenceMultiThread(a1 + 8);
  if ( !v2 && a1 )
  {
    ATL::CComObject<CPersistSession>::~CComObject<CPersistSession>(a1);
    operator delete((unsigned __int8 *)a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180015370  mov     [rsp+arg_0], rbx
0x180015375  push    rdi
0x180015376  sub     rsp, 20h
0x18001537a  mov     rbx, rcx
0x18001537d  add     rcx, 20h ; ' '; int *
0x180015381  call    ?SafeDecrementReferenceMultiThread@ATL@@YAKPEAJ@Z; ATL::SafeDecrementReferenceMultiThread(long *)
0x180015386  mov     edi, eax
0x180015388  test    eax, eax
0x18001538a  jnz     short loc_1800153A1
0x18001538c  test    rbx, rbx
0x18001538f  jz      short loc_1800153A1
0x180015391  mov     rcx, rbx
0x180015394  call    ??1?$CComObject@VCPersistSession@@@ATL@@QEAA@XZ; ATL::CComObject<CPersistSession>::~CComObject<CPersistSession>(void)
0x180015399  mov     rcx, rbx; void *
0x18001539c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800153a1  mov     rbx, [rsp+28h+arg_0]
0x1800153a6  mov     eax, edi
0x1800153a8  add     rsp, 20h
0x1800153ac  pop     rdi
0x1800153ad  retn
```
