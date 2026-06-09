# PmCheckCriticalPartitions(_DEVICE_EXTENSION *,SC_DISK_LAYOUT *)

- ea: `0x140020778`
- end: `0x1400208c1`
- name: `?PmCheckCriticalPartitions@@YAJPEAU_DEVICE_EXTENSION@@PEAVSC_DISK_LAYOUT@@@Z`
- size: `329`
- prototype: `int(struct _DEVICE_EXTENSION *, struct SC_DISK_LAYOUT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140020afc`

## callees

- `0x140004ef8`
- `0x140005ad0`
- `0x1400060ac`
- `0x14000c238`
- `0x140010e56`
- `0x140020778`

## pseudocode

```c
__int64 __fastcall PmCheckCriticalPartitions(struct _DEVICE_EXTENSION *a1, struct SC_DISK_LAYOUT *a2)
{
  _BYTE *DeviceExtension; // r15
  unsigned __int8 v5; // bp
  __int64 *i; // rbx
  __int64 v7; // rcx
  unsigned int v8; // r10d
  SC_PART_ENTRY *Entry; // rax
  __int64 v10; // r9
  int v11; // r10d
  unsigned int v12; // r11d
  unsigned int v13; // edi

  if ( *((_BYTE *)a1 + 604) )
  {
    DeviceExtension = PmControlObject->DeviceExtension;
    v5 = PmEnforceService(a1);
    for ( i = (__int64 *)*((_QWORD *)a1 + 112); i != (__int64 *)((char *)a1 + 896); i = (__int64 *)*i )
    {
      v7 = *((unsigned int *)i - 26);
      if ( (v7 & 0x400) == 0 )
      {
        if ( !DeviceExtension[168] && (v7 = *(unsigned int *)(*(i - 17) + 48), (v7 & 0x20000000) != 0)
          || v5 && *((_BYTE *)i + 53) )
        {
          if ( !*((_DWORD *)a2 + 1) )
            goto LABEL_13;
          v8 = 0;
          while ( 1 )
          {
            Entry = SC_DISK_LAYOUT::GetEntry(a2, v8);
            if ( !SC_PART_ENTRY::IsUnused(Entry) )
            {
              v7 = i[4];
              if ( *(_QWORD *)(v10 + 8) == v7 )
                break;
            }
            v8 = v11 + 1;
            if ( v8 >= v12 )
              goto LABEL_13;
          }
          if ( v5
            && *((_BYTE *)i + 53)
            && (*(_QWORD *)(v10 + 16) != i[5]
             || *(_QWORD *)(v10 + 64) != i[11]
             || *(_QWORD *)(v10 + 32) != i[7]
             || *(_QWORD *)(v10 + 40) != i[8]
             || wcsncmp_0((const wchar_t *)(v10 + 72), (const wchar_t *)i + 48, 0x24u)) )
          {
LABEL_13:
            v13 = -1073741790;
            if ( (Microsoft_Windows_PartitionEnableBits & 1) != 0 )
              McTemplateK0qq_EtwWriteTransfer(
                v7,
                CriticalDiskSetLayoutError,
                0,
                *((unsigned int *)a1 + 42),
                *((_DWORD *)i + 12));
            return v13;
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140020778  push    rbx
0x14002077a  push    rbp
0x14002077b  push    rsi
0x14002077c  push    rdi
0x14002077d  push    r14
0x14002077f  push    r15
0x140020781  sub     rsp, 38h
0x140020785  cmp     byte ptr [rcx+25Ch], 0
0x14002078c  mov     r14, rdx
0x14002078f  mov     rsi, rcx
0x140020792  jz      loc_1400208AF
0x140020798  mov     rax, cs:?PmControlObject@@3PEAU_DEVICE_OBJECT@@EA; _DEVICE_OBJECT * PmControlObject
0x14002079f  mov     r15, [rax+40h]
0x1400207a3  call    ?PmEnforceService@@YAEPEAU_DEVICE_EXTENSION@@@Z; PmEnforceService(_DEVICE_EXTENSION *)
0x1400207a8  lea     rdi, [rsi+380h]
0x1400207af  mov     bpl, al
0x1400207b2  mov     rbx, [rdi]
0x1400207b5  jmp     loc_1400208A6
0x1400207ba  mov     ecx, [rbx-68h]
0x1400207bd  bt      ecx, 0Ah
0x1400207c1  jb      loc_1400208A3
0x1400207c7  cmp     byte ptr [r15+0A8h], 0
0x1400207cf  jnz     short loc_1400207E1
0x1400207d1  mov     rax, [rbx-88h]
0x1400207d8  mov     ecx, [rax+30h]
0x1400207db  bt      ecx, 1Dh
0x1400207df  jb      short loc_1400207F4
0x1400207e1  test    bpl, bpl
0x1400207e4  jz      loc_1400208A3
0x1400207ea  cmp     byte ptr [rbx+35h], 0
0x1400207ee  jz      loc_1400208A3
0x1400207f4  mov     r11d, [r14+4]
0x1400207f8  test    r11d, r11d
0x1400207fb  jz      short loc_14002082C
0x1400207fd  xor     r10d, r10d
0x140020800  mov     edx, r10d; unsigned int
0x140020803  mov     rcx, r14; this
0x140020806  call    ?GetEntry@SC_DISK_LAYOUT@@QEAAPEAVSC_PART_ENTRY@@K@Z; SC_DISK_LAYOUT::GetEntry(ulong)
0x14002080b  mov     rcx, rax; this
0x14002080e  mov     r9, rax
0x140020811  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140020816  test    al, al
0x140020818  jnz     short loc_140020824
0x14002081a  mov     rcx, [rbx+20h]
0x14002081e  cmp     [r9+8], rcx
0x140020822  jz      short loc_140020859
0x140020824  inc     r10d
0x140020827  cmp     r10d, r11d
0x14002082a  jb      short loc_140020800
0x14002082c  test    cs:Microsoft_Windows_PartitionEnableBits, 1
0x140020833  mov     edi, 0C0000022h
0x140020838  jz      short loc_1400208B1
0x14002083a  mov     eax, [rbx+30h]
0x14002083d  lea     rdx, CriticalDiskSetLayoutError
0x140020844  mov     r9d, [rsi+0A8h]
0x14002084b  xor     r8d, r8d
0x14002084e  mov     [rsp+68h+var_48], eax
0x140020852  call    McTemplateK0qq_EtwWriteTransfer
0x140020857  jmp     short loc_1400208B1
0x140020859  test    bpl, bpl
0x14002085c  jz      short loc_1400208A3
0x14002085e  cmp     byte ptr [rbx+35h], 0
0x140020862  jz      short loc_1400208A3
0x140020864  mov     rax, [rbx+28h]
0x140020868  cmp     [r9+10h], rax
0x14002086c  jnz     short loc_14002082C
0x14002086e  mov     rax, [rbx+58h]
0x140020872  cmp     [r9+40h], rax
0x140020876  jnz     short loc_14002082C
0x140020878  mov     rax, [r9+20h]
0x14002087c  cmp     rax, [rbx+38h]
0x140020880  jnz     short loc_14002082C
0x140020882  mov     rax, [r9+28h]
0x140020886  cmp     rax, [rbx+40h]
0x14002088a  jnz     short loc_14002082C
0x14002088c  lea     rdx, [rbx+60h]; Str2
0x140020890  mov     r8d, 24h ; '$'; MaxCount
0x140020896  lea     rcx, [r9+48h]; Str1
0x14002089a  call    wcsncmp_0
0x14002089f  test    eax, eax
0x1400208a1  jnz     short loc_14002082C
0x1400208a3  mov     rbx, [rbx]
0x1400208a6  cmp     rbx, rdi
0x1400208a9  jnz     loc_1400207BA
0x1400208af  xor     edi, edi
0x1400208b1  mov     eax, edi
0x1400208b3  add     rsp, 38h
0x1400208b7  pop     r15
0x1400208b9  pop     r14
0x1400208bb  pop     rdi
0x1400208bc  pop     rsi
0x1400208bd  pop     rbp
0x1400208be  pop     rbx
0x1400208bf  retn
```
