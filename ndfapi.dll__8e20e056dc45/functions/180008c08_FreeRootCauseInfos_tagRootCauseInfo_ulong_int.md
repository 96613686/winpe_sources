# FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)

- ea: `0x180008c08`
- end: `0x180008cb0`
- name: `?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z`
- size: `168`
- prototype: `void __fastcall(struct tagRootCauseInfo *pv, unsigned int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x180008450`
- `0x180008500`
- `0x1800112c0`
- `0x18001977c`
- `0x180019af8`

## callees

- `0x180008b08`
- `0x180008c08`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180008c3d`
- `ole32!CoTaskMemFree` at `0x180008c81`
- `ole32!CoTaskMemFree` at `0x180008c99`
- `ole32!CoTaskMemFree` at `0x180008c3d`
- `ole32!CoTaskMemFree` at `0x180008c81`
- `ole32!CoTaskMemFree` at `0x180008c99`

## pseudocode

```c
void __fastcall FreeRootCauseInfos(struct tagRootCauseInfo *pv, unsigned int a2, int a3)
{
  unsigned int v6; // esi
  __int64 v7; // rbp
  __int64 v8; // rdi
  RepairInfoEx *pRepairs; // r15
  unsigned int v10; // r12d
  unsigned int v11; // edi

  if ( pv && a2 )
  {
    v6 = 0;
    v7 = 0;
    do
    {
      v8 = v7 << 6;
      CoTaskMemFree(pv[v7].pwszDescription);
      pRepairs = pv[v7].pRepairs;
      pv[v7].pwszDescription = 0;
      if ( pRepairs )
      {
        v10 = *(unsigned __int16 *)((char *)&pv->repairCount + v8);
        if ( *(USHORT *)((char *)&pv->repairCount + v8) )
        {
          v11 = 0;
          do
            FreeRepairInfos(&pRepairs[v11++].repair, 1u, 0);
          while ( v11 < v10 );
          CoTaskMemFree(pRepairs);
        }
      }
      ++v6;
      ++v7;
    }
    while ( v6 < a2 );
    if ( a3 )
      CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180008c08  test    rcx, rcx
0x180008c0b  jz      locret_180008CAF
0x180008c11  push    rbx
0x180008c12  push    rbp
0x180008c13  push    rsi
0x180008c14  push    rdi
0x180008c15  push    r12
0x180008c17  push    r13
0x180008c19  push    r14
0x180008c1b  push    r15
0x180008c1d  sub     rsp, 28h
0x180008c21  mov     r13d, r8d
0x180008c24  mov     r14d, edx
0x180008c27  mov     rbx, rcx
0x180008c2a  test    edx, edx
0x180008c2c  jz      short loc_180008C9F
0x180008c2e  xor     esi, esi
0x180008c30  xor     ebp, ebp
0x180008c32  mov     rdi, rbp
0x180008c35  shl     rdi, 6
0x180008c39  mov     rcx, [rdi+rbx]; pv
0x180008c3d  call    cs:__imp_CoTaskMemFree
0x180008c43  mov     r15, [rdi+rbx+30h]
0x180008c48  mov     qword ptr [rdi+rbx], 0
0x180008c50  test    r15, r15
0x180008c53  jz      short loc_180008C87
0x180008c55  movzx   r12d, word ptr [rdi+rbx+38h]
0x180008c5b  test    r12d, r12d
0x180008c5e  jz      short loc_180008C87
0x180008c60  xor     edi, edi
0x180008c62  mov     eax, edi
0x180008c64  xor     r8d, r8d; int
0x180008c67  imul    rcx, rax, 78h ; 'x'
0x180008c6b  lea     edx, [r8+1]; unsigned int
0x180008c6f  add     rcx, r15; pv
0x180008c72  call    ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180008c77  inc     edi
0x180008c79  cmp     edi, r12d
0x180008c7c  jb      short loc_180008C62
0x180008c7e  mov     rcx, r15; pv
0x180008c81  call    cs:__imp_CoTaskMemFree
0x180008c87  inc     esi
0x180008c89  inc     rbp
0x180008c8c  cmp     esi, r14d
0x180008c8f  jb      short loc_180008C32
0x180008c91  test    r13d, r13d
0x180008c94  jz      short loc_180008C9F
0x180008c96  mov     rcx, rbx; pv
0x180008c99  call    cs:__imp_CoTaskMemFree
0x180008c9f  add     rsp, 28h
0x180008ca3  pop     r15
0x180008ca5  pop     r14
0x180008ca7  pop     r13
0x180008ca9  pop     r12
0x180008cab  pop     rdi
0x180008cac  pop     rsi
0x180008cad  pop     rbp
0x180008cae  pop     rbx
0x180008caf  retn
```
