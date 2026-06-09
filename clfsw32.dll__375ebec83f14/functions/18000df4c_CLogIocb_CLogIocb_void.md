# CLogIocb::~CLogIocb(void)

- ea: `0x18000df4c`
- end: `0x18000dffd`
- name: `??1CLogIocb@@QEAA@XZ`
- size: `177`
- prototype: `void __fastcall(CLogIocb *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ddd8`
- `0x18000e750`
- `0x18001031c`
- `0x180010bdc`

## callees

- `0x18000df4c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dfef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dfdf`

## pseudocode

```c
void __fastcall CLogIocb::~CLogIocb(CLogIocb *this)
{
  void *v1; // r8
  void (__fastcall *v3)(_QWORD, _QWORD); // rax
  void *v4; // rcx

  v1 = (void *)*((_QWORD *)this + 8);
  if ( v1 )
  {
    v3 = (void (__fastcall *)(_QWORD, _QWORD))*((_QWORD *)this + 26);
    if ( v3 )
    {
      v3(*((_QWORD *)this + 8), *((_QWORD *)this + 27));
LABEL_4:
      *((_QWORD *)this + 8) = 0;
      goto LABEL_5;
    }
    if ( HeapFree(g_hMarshalHeap, 0, v1) )
      goto LABEL_4;
    GetLastError();
  }
LABEL_5:
  v4 = (void *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 7) = 0;
  }
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18000df4c  push    rbx
0x18000df4e  sub     rsp, 20h
0x18000df52  mov     r8, [rcx+40h]; lpMem
0x18000df56  mov     rbx, rcx
0x18000df59  test    r8, r8
0x18000df5c  jz      short loc_18000DF81
0x18000df5e  mov     rax, [rcx+0D0h]
0x18000df65  test    rax, rax
0x18000df68  jz      short loc_18000DFD6
0x18000df6a  mov     rdx, [rcx+0D8h]
0x18000df71  mov     rcx, r8
0x18000df74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df79  mov     qword ptr [rbx+40h], 0
0x18000df81  mov     rcx, [rbx+38h]; hObject
0x18000df85  test    rcx, rcx
0x18000df88  jz      short loc_18000DF9E
0x18000df8a  call    cs:__imp_CloseHandle
0x18000df91  nop     dword ptr [rax+rax+00h]
0x18000df96  mov     qword ptr [rbx+38h], 0
0x18000df9e  mov     qword ptr [rbx+0C0h], 0
0x18000dfa9  mov     qword ptr [rbx+78h], 0
0x18000dfb1  mov     qword ptr [rbx+0C8h], 0
0x18000dfbc  mov     qword ptr [rbx+0D0h], 0
0x18000dfc7  mov     qword ptr [rbx+10h], 0
0x18000dfcf  add     rsp, 20h
0x18000dfd3  pop     rbx
0x18000dfd4  retn
0x18000dfd6  mov     rcx, cs:?g_hMarshalHeap@@3PEAXEA; hHeap
0x18000dfdd  xor     edx, edx; dwFlags
0x18000dfdf  call    cs:__imp_HeapFree
0x18000dfe6  nop     dword ptr [rax+rax+00h]
0x18000dfeb  test    eax, eax
0x18000dfed  jnz     short loc_18000DF79
0x18000dfef  call    cs:__imp_GetLastError
0x18000dff6  nop     dword ptr [rax+rax+00h]
0x18000dffb  jmp     short loc_18000DF81
```
