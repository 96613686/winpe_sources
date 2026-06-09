# CreateCombinedHashTable

- ea: `0x1800115f4`
- end: `0x180011679`
- name: `CreateCombinedHashTable`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011588`

## callees

- `0x180007e38`
- `0x180011500`
- `0x1800115f4`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x180011624`
- `ntdll!RtlCreateHashTable` at `0x180011624`

## string_xrefs

- `0x18001163a`: `RtlCreateHashTable`
- `0x18001164e`: `CreateCombinedHashTable`

## pseudocode

```c
__int64 __fastcall CreateCombinedHashTable(_DWORD *a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  __int64 v3; // rbx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rcx

  v2 = a1 + 2;
  v3 = 0;
  if ( *a1 )
  {
    ++*a1;
    *a2 = *v2;
  }
  else if ( (unsigned __int8)RtlCreateHashTable(a1 + 2, 0, 0) )
  {
    v8 = *v2;
    *a1 = 1;
    *a2 = v8;
  }
  else
  {
    v7 = WfpReportSysErrorAsNtStatus(v6, "RtlCreateHashTable", 3221225473LL);
    v3 = v7;
    if ( v7 )
      WfpReportError(v7, "CreateCombinedHashTable");
  }
  return v3;
}

```

## disassembly

```asm
0x1800115f4  push    rbx
0x1800115f6  push    rsi
0x1800115f7  push    rdi
0x1800115f8  push    r14
0x1800115fa  sub     rsp, 28h
0x1800115fe  mov     eax, [rcx]
0x180011600  lea     rsi, [rcx+8]
0x180011604  xor     ebx, ebx
0x180011606  mov     r14, rdx
0x180011609  mov     rdi, rcx
0x18001160c  test    eax, eax
0x18001160e  jz      short loc_18001161C
0x180011610  inc     eax
0x180011612  mov     [rcx], eax
0x180011614  mov     rax, [rsi]
0x180011617  mov     [rdx], rax
0x18001161a  jmp     short loc_18001166B
0x18001161c  xor     r8d, r8d
0x18001161f  xor     edx, edx
0x180011621  mov     rcx, rsi
0x180011624  call    cs:__imp_RtlCreateHashTable
0x18001162b  nop     dword ptr [rax+rax+00h]
0x180011630  test    al, al
0x180011632  jnz     short loc_18001165F
0x180011634  mov     r8d, 0C0000001h
0x18001163a  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x180011641  call    WfpReportSysErrorAsNtStatus
0x180011646  mov     rbx, rax
0x180011649  test    rax, rax
0x18001164c  jz      short loc_18001166B
0x18001164e  lea     rdx, aCreatecombined; "CreateCombinedHashTable"
0x180011655  mov     rcx, rax
0x180011658  call    WfpReportError
0x18001165d  jmp     short loc_18001166B
0x18001165f  mov     rcx, [rsi]
0x180011662  mov     dword ptr [rdi], 1
0x180011668  mov     [r14], rcx
0x18001166b  mov     rax, rbx
0x18001166e  add     rsp, 28h
0x180011672  pop     r14
0x180011674  pop     rdi
0x180011675  pop     rsi
0x180011676  pop     rbx
0x180011677  retn
```
