# CVPNDiagHelper::Repair(tagRepairInfo *,long *,tagREPAIR_STATUS *)

- ea: `0x1800097d0`
- end: `0x180009878`
- name: `?Repair@CVPNDiagHelper@@UEAAJPEAUtagRepairInfo@@PEAJPEAW4tagREPAIR_STATUS@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(CVPNDiagHelper *__hidden this, struct tagRepairInfo *, int *, enum tagREPAIR_STATUS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x1800097d0`
- `0x18000b864`
- `0x18000c7f0`

## string_xrefs

- `0x180009831`: `Repair: InstallMiniportDevice failed, Error= 0x%x`

## pseudocode

```c
__int64 __fastcall CVPNDiagHelper::Repair(
        CVPNDiagHelper *this,
        struct tagRepairInfo *a2,
        int *a3,
        enum tagREPAIR_STATUS *a4)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // [rsp+28h] [rbp-10h]

  if ( ID_RASHC_LOWH_REPAIR_MINIPORT_NOT_INSTALLED != *(_OWORD *)&a2->guid )
    return 2147500033LL;
  v6 = InstallMiniportDevice((const unsigned __int16 *)(&off_180017170)[3 * *((int *)this + 358)]);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = v6;
    *a4 = RS_UNREPAIRED;
    CRasLogger::Log(
      (_QWORD *)this + 177,
      2u,
      1u,
      (__int64)L"CVPNDiagHelper",
      L"Repair: InstallMiniportDevice failed, Error= 0x%x",
      v9);
  }
  else
  {
    *a4 = RS_REPAIRED;
  }
  return v7;
}

```

## disassembly

```asm
0x1800097d0  mov     [rsp+arg_0], rbx
0x1800097d5  mov     [rsp+arg_8], rsi
0x1800097da  push    rdi
0x1800097db  sub     rsp, 30h
0x1800097df  mov     rax, qword ptr cs:ID_RASHC_LOWH_REPAIR_MINIPORT_NOT_INSTALLED
0x1800097e6  mov     rdi, r9
0x1800097e9  mov     rsi, rcx
0x1800097ec  cmp     rax, [rdx]
0x1800097ef  jnz     short loc_180009862
0x1800097f1  mov     rax, qword ptr cs:ID_RASHC_LOWH_REPAIR_MINIPORT_NOT_INSTALLED+8
0x1800097f8  cmp     rax, [rdx+8]
0x1800097fc  jnz     short loc_180009862
0x1800097fe  movsxd  rax, dword ptr [rcx+598h]
0x180009805  lea     rcx, [rax+rax*2]
0x180009809  lea     rax, off_180017170
0x180009810  mov     rcx, [rax+rcx*8]; unsigned __int16 *
0x180009814  call    ?InstallMiniportDevice@@YAJPEBG@Z; InstallMiniportDevice(ushort const *)
0x180009819  mov     ebx, eax
0x18000981b  test    eax, eax
0x18000981d  js      short loc_180009827
0x18000981f  mov     dword ptr [rdi], 1
0x180009825  jmp     short loc_18000985E
0x180009827  mov     r10d, 2
0x18000982d  mov     [rsp+38h+var_10], ebx
0x180009831  lea     rax, aRepairInstallm; "Repair: InstallMiniportDevice failed, E"...
0x180009838  mov     [rdi], r10d
0x18000983b  lea     rcx, [rsi+588h]
0x180009842  mov     [rsp+38h+var_18], rax
0x180009847  lea     r9, aCvpndiaghelper; "CVPNDiagHelper"
0x18000984e  lea     edx, [r10-1]
0x180009852  movsx   r8d, dx
0x180009856  mov     edx, r10d
0x180009859  call    ?Log@CRasLogger@@QEAAJW4tagNDFEventChannel@@FPEBG1ZZ; CRasLogger::Log(tagNDFEventChannel,short,ushort const *,ushort const *,...)
0x18000985e  mov     eax, ebx
0x180009860  jmp     short loc_180009867
0x180009862  mov     eax, 80004001h
0x180009867  mov     rbx, [rsp+38h+arg_0]
0x18000986c  mov     rsi, [rsp+38h+arg_8]
0x180009871  add     rsp, 30h
0x180009875  pop     rdi
0x180009876  retn
```
