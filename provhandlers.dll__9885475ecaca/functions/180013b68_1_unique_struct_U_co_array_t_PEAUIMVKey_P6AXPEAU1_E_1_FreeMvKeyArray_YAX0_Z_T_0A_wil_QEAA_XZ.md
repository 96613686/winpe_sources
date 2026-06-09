# ??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ

- ea: `0x180013b68`
- end: `0x180013bb8`
- name: `??1?$unique_struct@U?$co_array_t@PEAUIMVKey@@@@P6AXPEAU1@@_E$1?FreeMvKeyArray@@YAX0@Z$$T$0A@@wil@@QEAA@XZ`
- size: `80`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002eb90`
- `0x18003ca24`
- `0x18003cbb7`
- `0x18003d111`
- `0x18003dc26`

## callees

- `0x180013b68`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ba8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013ba8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __1__unique_struct_U__co_array_t_PEAUIMVKey____P6AXPEAU1___E_1_FreeMvKeyArray__YAX0_Z__T_0A__wil__QEAA_XZ(
        __int64 a1)
{
  _QWORD *v1; // rdi
  unsigned int v2; // esi
  __int64 i; // rbx
  __int64 v4; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v2 = *(_DWORD *)(a1 + 8);
    for ( i = 0; (unsigned int)i < v2; i = (unsigned int)(i + 1) )
    {
      v4 = v1[i];
      if ( v4 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        v1[i] = 0;
      }
    }
    CoTaskMemFree(v1);
  }
}

```

## disassembly

```asm
0x180013b68  push    rbx
0x180013b6a  push    rbp
0x180013b6b  push    rsi
0x180013b6c  push    rdi
0x180013b6d  sub     rsp, 28h
0x180013b71  mov     rdi, [rcx]
0x180013b74  test    rdi, rdi
0x180013b77  jz      short loc_180013BAF
0x180013b79  mov     esi, [rcx+8]
0x180013b7c  xor     ebx, ebx
0x180013b7e  test    esi, esi
0x180013b80  jz      short loc_180013BA5
0x180013b82  mov     rcx, [rdi+rbx*8]
0x180013b86  test    rcx, rcx
0x180013b89  jz      short loc_180013B9F
0x180013b8b  mov     rax, [rcx]
0x180013b8e  mov     rax, [rax+10h]
0x180013b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b97  mov     qword ptr [rdi+rbx*8], 0
0x180013b9f  inc     ebx
0x180013ba1  cmp     ebx, esi
0x180013ba3  jb      short loc_180013B82
0x180013ba5  mov     rcx, rdi; pv
0x180013ba8  call    cs:__imp_CoTaskMemFree
0x180013bae  nop
0x180013baf  add     rsp, 28h
0x180013bb3  pop     rdi
0x180013bb4  pop     rsi
0x180013bb5  pop     rbp
0x180013bb6  pop     rbx
0x180013bb7  retn
```
