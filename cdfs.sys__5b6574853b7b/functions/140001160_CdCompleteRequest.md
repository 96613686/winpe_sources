# CdCompleteRequest

- ea: `0x140001160`
- end: `0x1400011bd`
- name: `CdCompleteRequest`
- size: `93`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001240`
- `0x140001474`
- `0x1400016b0`
- `0x140001d0c`
- `0x140002250`
- `0x1400028e0`
- `0x14000b62c`
- `0x14000c0c8`
- `0x14000c374`
- `0x14000c6d8`
- `0x14000c8b4`
- `0x14000e844`
- `0x140010ee0`
- `0x140011674`
- `0x140011744`
- `0x140012d24`
- `0x140013140`
- `0x140013a70`
- `0x140013ac8`
- `0x1400141e0`
- `0x1400142d8`
- `0x140014c38`
- `0x140014e4c`
- `0x140015090`
- `0x1400156c0`
- `0x140016fe8`
- `0x140017148`
- `0x14001734c`
- `0x1400174c8`
- `0x140017ab8`
- `0x14001a688`
- `0x14001a900`
- `0x14001aa78`
- `0x14001af0c`

## callees

- `0x140001160`
- `0x1400183c8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400011a5`
- `ntoskrnl!IofCompleteRequest` at `0x1400011a5`

## pseudocode

```c
void __fastcall CdCompleteRequest(void *a1, IRP *a2, NTSTATUS a3)
{
  if ( a1 )
    CdCleanupIrpContext(a1);
  if ( a2 )
  {
    if ( (a3 & 0xC0000000) == 0xC0000000 && (a2->Flags & 0x40) != 0 )
      a2->IoStatus.Information = 0;
    a2->IoStatus.Status = a3;
    IofCompleteRequest(a2, 1);
  }
}

```

## disassembly

```asm
0x140001160  mov     [rsp+arg_0], rbx
0x140001165  push    rdi
0x140001166  sub     rsp, 20h
0x14000116a  mov     edi, r8d
0x14000116d  mov     rbx, rdx
0x140001170  test    rcx, rcx
0x140001173  jz      short loc_14000117C
0x140001175  xor     edx, edx
0x140001177  call    CdCleanupIrpContext
0x14000117c  test    rbx, rbx
0x14000117f  jz      short loc_1400011B1
0x140001181  mov     ecx, 0C0000000h
0x140001186  mov     eax, edi
0x140001188  and     eax, ecx
0x14000118a  cmp     eax, ecx
0x14000118c  jnz     short loc_14000119D
0x14000118e  mov     eax, [rbx+10h]
0x140001191  test    al, 40h
0x140001193  jz      short loc_14000119D
0x140001195  mov     qword ptr [rbx+38h], 0
0x14000119d  mov     dl, 1; PriorityBoost
0x14000119f  mov     [rbx+30h], edi
0x1400011a2  mov     rcx, rbx; Irp
0x1400011a5  call    cs:__imp_IofCompleteRequest
0x1400011ac  nop     dword ptr [rax+rax+00h]
0x1400011b1  mov     rbx, [rsp+28h+arg_0]
0x1400011b6  add     rsp, 20h
0x1400011ba  pop     rdi
0x1400011bb  retn
```
