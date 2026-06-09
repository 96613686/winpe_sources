# CSidContainer::FreeBlobs(void)

- ea: `0x180024c74`
- end: `0x180024cdd`
- name: `?FreeBlobs@CSidContainer@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(CSidContainer *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020ecc`
- `0x180021770`
- `0x1800219a0`
- `0x180024be0`
- `0x180024bec`

## callees

- `0x180024c74`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024cc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024c9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024cc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CSidContainer::FreeBlobs(CSidContainer *this)
{
  unsigned int v2; // edi
  __int64 v3; // rbp
  __int64 v4; // rsi
  void *v5; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    v2 = 0;
    do
    {
      v3 = *(_QWORD *)this;
      v4 = 2LL * v2;
      v5 = *(void **)(*(_QWORD *)this + 16LL * v2 + 8);
      if ( v5 )
        CoTaskMemFree(v5);
      ++v2;
      *(_QWORD *)(v3 + 8 * v4 + 8) = 0;
      *(_DWORD *)(v3 + 8 * v4) = 0;
    }
    while ( v2 < *((_DWORD *)this + 2) );
    CoTaskMemFree(*(LPVOID *)this);
    *(_QWORD *)this = 0;
    *((_DWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180024c74  push    rbx
0x180024c76  push    rbp
0x180024c77  push    rsi
0x180024c78  push    rdi
0x180024c79  sub     rsp, 28h
0x180024c7d  mov     eax, [rcx+8]
0x180024c80  mov     rbx, rcx
0x180024c83  test    eax, eax
0x180024c85  jz      short loc_180024CD4
0x180024c87  xor     edi, edi
0x180024c89  test    eax, eax
0x180024c8b  jz      short loc_180024CBD
0x180024c8d  mov     rbp, [rbx]
0x180024c90  mov     esi, edi
0x180024c92  add     rsi, rsi
0x180024c95  mov     rcx, [rbp+rsi*8+8]; pv
0x180024c9a  test    rcx, rcx
0x180024c9d  jz      short loc_180024CA5
0x180024c9f  call    cs:__imp_CoTaskMemFree
0x180024ca5  inc     edi
0x180024ca7  mov     qword ptr [rbp+rsi*8+8], 0
0x180024cb0  mov     dword ptr [rbp+rsi*8+0], 0
0x180024cb8  cmp     edi, [rbx+8]
0x180024cbb  jb      short loc_180024C8D
0x180024cbd  mov     rcx, [rbx]; pv
0x180024cc0  call    cs:__imp_CoTaskMemFree
0x180024cc6  mov     qword ptr [rbx], 0
0x180024ccd  mov     dword ptr [rbx+8], 0
0x180024cd4  add     rsp, 28h
0x180024cd8  pop     rdi
0x180024cd9  pop     rsi
0x180024cda  pop     rbp
0x180024cdb  pop     rbx
0x180024cdc  retn
```
