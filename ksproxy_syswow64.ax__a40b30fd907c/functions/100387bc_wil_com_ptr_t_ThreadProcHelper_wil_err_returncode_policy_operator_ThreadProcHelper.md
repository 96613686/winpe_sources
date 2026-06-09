# wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)

- ea: `0x100387bc`
- end: `0x100387fe`
- name: `??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QAEAAV01@PAVThreadProcHelper@@@Z`
- size: `66`
- prototype: `int *__thiscall(int *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10037eb2`
- `0x10039550`
- `0x10039e3c`

## callees

- `0x1002d510`
- `0x100387bc`

## pseudocode

```c
int *__thiscall wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(int *this, int a2)
{
  int v3; // ebx

  v3 = *this;
  *this = a2;
  if ( a2 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)a2 + 4))(*(_DWORD *)(*(_DWORD *)a2 + 4), a2);
  if ( v3 )
    (*(void (__thiscall **)(_DWORD, int))(*(_DWORD *)v3 + 8))(*(_DWORD *)(*(_DWORD *)v3 + 8), v3);
  return this;
}

```

## disassembly

```asm
0x100387bc  mov     edi, edi
0x100387be  push    ebp
0x100387bf  mov     ebp, esp
0x100387c1  mov     edx, [ebp+arg_0]
0x100387c4  push    ebx
0x100387c5  push    esi
0x100387c6  push    edi
0x100387c7  mov     edi, ecx
0x100387c9  mov     ebx, [edi]
0x100387cb  mov     [edi], edx
0x100387cd  test    edx, edx
0x100387cf  jz      short loc_100387E1
0x100387d1  mov     eax, [edx]
0x100387d3  push    edx
0x100387d4  mov     esi, [eax+4]
0x100387d7  mov     ecx, esi; this
0x100387d9  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100387df  call    esi
0x100387e1  test    ebx, ebx
0x100387e3  jz      short loc_100387F5
0x100387e5  mov     eax, [ebx]
0x100387e7  push    ebx
0x100387e8  mov     esi, [eax+8]
0x100387eb  mov     ecx, esi; this
0x100387ed  call    ds:___guard_check_icall_fptr; CD3DSurfaceAllocator::Free(void) ...
0x100387f3  call    esi
0x100387f5  mov     eax, edi
0x100387f7  pop     edi
0x100387f8  pop     esi
0x100387f9  pop     ebx
0x100387fa  pop     ebp
0x100387fb  retn    4
```
