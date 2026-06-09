# FreeAttestationResults(void *,wchar_t *,uint,AttestationResult *)

- ea: `0x180007990`
- end: `0x1800079e9`
- name: `?FreeAttestationResults@@YAJPEAXPEA_WIPEAUAttestationResult@@@Z`
- size: `89`
- prototype: `__int64 __fastcall(void *, wchar_t *, unsigned int, struct AttestationResult *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180007990`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800079cf`
- `hgattest!ReleaseAttestationResult` at `0x1800079ad`
- `hgattest!ReleaseAttestationResult` at `0x1800079ad`

## pseudocode

```c
__int64 __fastcall FreeAttestationResults(void *a1, wchar_t *a2, unsigned int a3, struct AttestationResult *a4)
{
  unsigned int v5; // edi

  if ( a3 && a4 )
  {
    v5 = ReleaseAttestationResult(a3, a4);
    if ( a2 )
      CoTaskMemFree(a2);
    return v5;
  }
  else
  {
    if ( a2 )
      CoTaskMemFree(a2);
    return 0;
  }
}

```

## disassembly

```asm
0x180007990  mov     [rsp+arg_0], rbx
0x180007995  push    rdi
0x180007996  sub     rsp, 20h
0x18000799a  mov     rbx, rdx
0x18000799d  test    r8d, r8d
0x1800079a0  jz      short loc_1800079C7
0x1800079a2  test    r9, r9
0x1800079a5  jz      short loc_1800079C7
0x1800079a7  mov     rdx, r9
0x1800079aa  mov     ecx, r8d
0x1800079ad  call    cs:__imp_ReleaseAttestationResult
0x1800079b3  mov     edi, eax
0x1800079b5  test    rbx, rbx
0x1800079b8  jz      short loc_1800079C3
0x1800079ba  mov     rcx, rbx; pv
0x1800079bd  call    cs:__imp_CoTaskMemFree
0x1800079c3  mov     eax, edi
0x1800079c5  jmp     short loc_1800079DD
0x1800079c7  test    rbx, rbx
0x1800079ca  jz      short loc_1800079D5
0x1800079cc  mov     rcx, rbx; pv
0x1800079cf  call    cs:__imp_CoTaskMemFree
0x1800079d5  xor     eax, eax
0x1800079d7  jmp     short loc_1800079DD
0x1800079d9  mov     eax, [rsp+28h+arg_10]
0x1800079dd  mov     rbx, [rsp+28h+arg_0]
0x1800079e2  add     rsp, 20h
0x1800079e6  pop     rdi
0x1800079e7  retn
```
