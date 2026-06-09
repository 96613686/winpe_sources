# FreeRepairInfoExs(tagRepairInfoEx *,ulong,int)

- ea: `0x18001a4e4`
- end: `0x18001a530`
- name: `?FreeRepairInfoExs@@YAXPEAUtagRepairInfoEx@@KH@Z`
- size: `76`
- prototype: `void __fastcall(struct tagRepairInfoEx *pv, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001a538`

## callees

- `0x180005ff8`
- `0x18001a4e4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a521`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a521`

## pseudocode

```c
void __fastcall FreeRepairInfoExs(struct tagRepairInfoEx *pv, unsigned int a2, int a3)
{
  unsigned int i; // edi

  if ( pv && a2 )
  {
    for ( i = 0; i < a2; ++i )
      FreeRepairInfos(&pv[i].repair, 1u, 0);
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x18001a4e4  test    rcx, rcx
0x18001a4e7  jz      short locret_18001A52F
0x18001a4e9  push    rbx
0x18001a4ea  push    rbp
0x18001a4eb  push    rsi
0x18001a4ec  push    rdi
0x18001a4ed  sub     rsp, 28h
0x18001a4f1  mov     ebp, r8d
0x18001a4f4  mov     esi, edx
0x18001a4f6  mov     rbx, rcx
0x18001a4f9  test    edx, edx
0x18001a4fb  jz      short loc_18001A527
0x18001a4fd  xor     edi, edi
0x18001a4ff  mov     eax, edi
0x18001a501  xor     r8d, r8d; int
0x18001a504  imul    rcx, rax, 78h ; 'x'
0x18001a508  lea     edx, [r8+1]; unsigned int
0x18001a50c  add     rcx, rbx; pv
0x18001a50f  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x18001a514  inc     edi
0x18001a516  cmp     edi, esi
0x18001a518  jb      short loc_18001A4FF
0x18001a51a  test    ebp, ebp
0x18001a51c  jz      short loc_18001A527
0x18001a51e  mov     rcx, rbx; pv
0x18001a521  call    cs:__imp_CoTaskMemFree
0x18001a527  add     rsp, 28h
0x18001a52b  pop     rdi
0x18001a52c  pop     rsi
0x18001a52d  pop     rbp
0x18001a52e  pop     rbx
0x18001a52f  retn
```
