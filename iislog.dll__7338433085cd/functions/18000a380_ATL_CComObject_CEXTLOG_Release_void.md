# ATL::CComObject<CEXTLOG>::Release(void)

- ea: `0x18000a380`
- end: `0x18000a3e1`
- name: `?Release@?$CComObject@VCEXTLOG@@@ATL@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a3f0`

## callees

- `0x18000a380`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CEXTLOG>::Release(volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v2; // ebx

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v2 = i - 1;
  if ( i == 1 )
  {
    _InterlockedAdd(&dword_180017A78, 1u);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)a1 + 80LL))(a1);
    _InterlockedDecrement(&dword_180017A78);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a380  push    rbx
0x18000a382  sub     rsp, 20h
0x18000a386  mov     r8d, [rcx+8]
0x18000a38a  mov     r9, rcx
0x18000a38d  mov     ecx, 7FFFFFFFh
0x18000a392  jmp     short loc_18000A3A7
0x18000a394  lea     edx, [r8-1]
0x18000a398  mov     eax, r8d
0x18000a39b  lock cmpxchg [r9+8], edx
0x18000a3a1  jz      short loc_18000A3AC
0x18000a3a3  mov     r8d, [r9+8]
0x18000a3a7  cmp     r8d, ecx
0x18000a3aa  jnz     short loc_18000A394
0x18000a3ac  lea     ebx, [r8-1]
0x18000a3b0  test    ebx, ebx
0x18000a3b2  jnz     short loc_18000A3D9
0x18000a3b4  lea     edx, [rbx+1]
0x18000a3b7  lock add cs:dword_180017A78, edx
0x18000a3be  test    r9, r9
0x18000a3c1  jz      short loc_18000A3D2
0x18000a3c3  mov     rcx, [r9]
0x18000a3c6  mov     rax, [rcx+50h]
0x18000a3ca  mov     rcx, r9
0x18000a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d2  lock dec cs:dword_180017A78
0x18000a3d9  mov     eax, ebx
0x18000a3db  add     rsp, 20h
0x18000a3df  pop     rbx
0x18000a3e0  retn
```
