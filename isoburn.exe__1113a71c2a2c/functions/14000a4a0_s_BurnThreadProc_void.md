# s_BurnThreadProc(void *)

- ea: `0x14000a4a0`
- end: `0x14000a50b`
- name: `?s_BurnThreadProc@@YAKPEAX@Z`
- size: `107`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140009e64`
- `0x14000a4a0`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000a4b9`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000a4b9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000a4ee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000a4ee`

## pseudocode

```c
__int64 __fastcall s_BurnThreadProc(CIsoBurn *lpThreadParameter)
{
  __int64 v2; // rcx

  (*(void (__fastcall **)(CIsoBurn *))(*(_QWORD *)lpThreadParameter + 8LL))(lpThreadParameter);
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    CIsoBurn::_WriteImageToDisc(lpThreadParameter);
    v2 = *((_QWORD *)lpThreadParameter + 19);
    if ( v2 )
    {
      *((_QWORD *)lpThreadParameter + 19) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    }
    CoUninitialize();
  }
  (*(void (__fastcall **)(CIsoBurn *))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x14000a4a0  push    rbx
0x14000a4a2  sub     rsp, 20h
0x14000a4a6  mov     rax, [rcx]
0x14000a4a9  mov     rbx, rcx
0x14000a4ac  mov     rax, [rax+8]
0x14000a4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4b5  xor     edx, edx; dwCoInit
0x14000a4b7  xor     ecx, ecx; pvReserved
0x14000a4b9  call    cs:__imp_CoInitializeEx
0x14000a4bf  test    eax, eax
0x14000a4c1  js      short loc_14000A4F4
0x14000a4c3  mov     rcx, rbx; this
0x14000a4c6  call    ?_WriteImageToDisc@CIsoBurn@@AEAAXXZ; CIsoBurn::_WriteImageToDisc(void)
0x14000a4cb  mov     rcx, [rbx+98h]
0x14000a4d2  test    rcx, rcx
0x14000a4d5  jz      short loc_14000A4EE
0x14000a4d7  mov     qword ptr [rbx+98h], 0
0x14000a4e2  mov     rax, [rcx]
0x14000a4e5  mov     rax, [rax+10h]
0x14000a4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4ee  call    cs:__imp_CoUninitialize
0x14000a4f4  mov     rax, [rbx]
0x14000a4f7  mov     rcx, rbx
0x14000a4fa  mov     rax, [rax+10h]
0x14000a4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a503  xor     eax, eax
0x14000a505  add     rsp, 20h
0x14000a509  pop     rbx
0x14000a50a  retn
```
