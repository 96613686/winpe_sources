# FatCompleteRequest_Real

- ea: `0x140038eb4`
- end: `0x140038f24`
- name: `FatCompleteRequest_Real`
- size: `112`
- prototype: `__int64 __fastcall(PVOID Entry, PIRP Irp)`
- caller_count: `51`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400053ac`
- `0x140005604`
- `0x140005d78`
- `0x140023d4c`
- `0x140024bd4`
- `0x1400260d0`
- `0x14002a4b0`
- `0x14002d0d4`
- `0x14002e9ac`
- `0x14002ebb4`
- `0x14002ed1c`
- `0x1400345b0`
- `0x140036d14`
- `0x140037240`
- `0x140037ab0`
- `0x14003816c`
- `0x14003960c`
- `0x140039ad8`
- `0x140039e94`
- `0x14003dba0`
- `0x14003ebd8`
- `0x14003ec78`
- `0x14003f104`
- `0x14003f3d4`
- `0x14003f5d4`
- `0x14003f6e0`
- `0x14003fcfc`
- `0x1400400d8`
- `0x140040210`
- `0x140040408`
- `0x1400412a8`
- `0x140042018`
- `0x1400424c4`
- `0x1400428fc`
- `0x140042a0c`
- `0x140042ac0`
- `0x140042ec8`
- `0x1400438e0`
- `0x140043c80`
- `0x140044ff8`
- `0x1400451fc`
- `0x1400452a0`
- `0x1400454a0`
- `0x1400455f4`
- `0x14004573c`
- `0x140046cb0`
- `0x140049d44`
- `0x14004a538`
- `0x14004a7e8`
- `0x14004aee0`

## callees

- `0x14002486c`
- `0x140038eb4`
- `0x1400483bc`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140038f07`
- `ntoskrnl!IofCompleteRequest` at `0x140038f07`

## pseudocode

```c
void __fastcall FatCompleteRequest_Real(PVOID Entry, PIRP Irp, __int64 a3, __int64 a4)
{
  NTSTATUS v4; // esi

  v4 = a3;
  if ( Entry )
  {
    FatUnpinRepinnedBcbs(Entry, Irp, a3, a4);
    FatDeleteIrpContext_Real(Entry);
  }
  if ( Irp )
  {
    if ( (v4 & 0xC0000000) == 0xC0000000 && (Irp->Flags & 0x40) != 0 )
      Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v4;
    IofCompleteRequest(Irp, 1);
  }
}

```

## disassembly

```asm
0x140038eb4  mov     [rsp+arg_0], rbx
0x140038eb9  mov     [rsp+arg_8], rsi
0x140038ebe  push    rdi
0x140038ebf  sub     rsp, 20h
0x140038ec3  mov     esi, r8d
0x140038ec6  mov     rbx, rdx
0x140038ec9  mov     rdi, rcx
0x140038ecc  test    rcx, rcx
0x140038ecf  jz      short loc_140038EDE
0x140038ed1  call    FatUnpinRepinnedBcbs
0x140038ed6  mov     rcx, rdi; Entry
0x140038ed9  call    FatDeleteIrpContext_Real
0x140038ede  test    rbx, rbx
0x140038ee1  jz      short loc_140038F13
0x140038ee3  mov     ecx, 0C0000000h
0x140038ee8  mov     eax, esi
0x140038eea  and     eax, ecx
0x140038eec  cmp     eax, ecx
0x140038eee  jnz     short loc_140038EFF
0x140038ef0  mov     eax, [rbx+10h]
0x140038ef3  test    al, 40h
0x140038ef5  jz      short loc_140038EFF
0x140038ef7  mov     qword ptr [rbx+38h], 0
0x140038eff  mov     dl, 1; PriorityBoost
0x140038f01  mov     [rbx+30h], esi
0x140038f04  mov     rcx, rbx; Irp
0x140038f07  call    cs:__imp_IofCompleteRequest
0x140038f0e  nop     dword ptr [rax+rax+00h]
0x140038f13  mov     rbx, [rsp+28h+arg_0]
0x140038f18  mov     rsi, [rsp+28h+arg_8]
0x140038f1d  add     rsp, 20h
0x140038f21  pop     rdi
0x140038f22  retn
```
