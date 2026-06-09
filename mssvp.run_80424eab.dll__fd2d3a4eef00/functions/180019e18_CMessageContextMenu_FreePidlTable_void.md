# CMessageContextMenu::FreePidlTable(void)

- ea: `0x180019e18`
- end: `0x180019e6f`
- name: `?FreePidlTable@CMessageContextMenu@@IEAAXXZ`
- size: `87`
- prototype: `void __fastcall(CMessageContextMenu *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018bac`
- `0x18001bb40`

## callees

- `0x180019e18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019e56`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180019e3d`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180019e3d`

## pseudocode

```c
void __fastcall CMessageContextMenu::FreePidlTable(CMessageContextMenu *this)
{
  _QWORD *v1; // rdx
  int v3; // edi

  v1 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v1 )
  {
    if ( *v1 )
    {
      v3 = 0;
      do
      {
        ILFree((LPITEMIDLIST)v1[v3]);
        v1 = (_QWORD *)*((_QWORD *)this + 13);
        ++v3;
      }
      while ( v1[v3] );
    }
    CoTaskMemFree(v1);
    *((_QWORD *)this + 13) = 0;
  }
}

```

## disassembly

```asm
0x180019e18  mov     [rsp+arg_0], rbx
0x180019e1d  push    rdi
0x180019e1e  sub     rsp, 20h
0x180019e22  mov     rdx, [rcx+68h]
0x180019e26  mov     rbx, rcx
0x180019e29  test    rdx, rdx
0x180019e2c  jz      short loc_180019E64
0x180019e2e  cmp     qword ptr [rdx], 0
0x180019e32  jz      short loc_180019E53
0x180019e34  xor     edi, edi
0x180019e36  movsxd  rcx, edi
0x180019e39  mov     rcx, [rdx+rcx*8]; pidl
0x180019e3d  call    cs:__imp_ILFree
0x180019e43  mov     rdx, [rbx+68h]
0x180019e47  inc     edi
0x180019e49  movsxd  rax, edi
0x180019e4c  cmp     qword ptr [rdx+rax*8], 0
0x180019e51  jnz     short loc_180019E36
0x180019e53  mov     rcx, rdx; pv
0x180019e56  call    cs:__imp_CoTaskMemFree
0x180019e5c  mov     qword ptr [rbx+68h], 0
0x180019e64  mov     rbx, [rsp+28h+arg_0]
0x180019e69  add     rsp, 20h
0x180019e6d  pop     rdi
0x180019e6e  retn
```
