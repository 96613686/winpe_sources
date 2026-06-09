# PmGetLayout(_DEVICE_EXTENSION *,SC_DISK_LAYOUT * *)

- ea: `0x1400066a0`
- end: `0x140006837`
- name: `?PmGetLayout@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct SC_DISK_LAYOUT **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140007bcc`

## callees

- `0x1400066a0`
- `0x140010f20`
- `0x14001d13c`
- `0x140023da8`
- `0x140024690`
- `0x1400246c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400067f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400067f6`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400067c7`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x1400067c7`
- `ntoskrnl!ExAllocatePool2` at `0x140006740`
- `ntoskrnl!ExAllocatePool2` at `0x140006740`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400067e0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400067e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400067a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400067a4`

## pseudocode

```c
__int64 __fastcall PmGetLayout(struct _DEVICE_EXTENSION *a1, struct SC_DISK_LAYOUT **a2)
{
  struct SC_DISK_LAYOUT *v4; // rsi
  struct _DEVICE_OBJECT *v5; // rdx
  int v6; // ebp
  char v7; // bl
  int PartitionTable; // eax
  __int64 Pool2; // rax
  KIRQL v10; // al
  KIRQL v11; // bl
  unsigned __int64 QpcTimeStamp[2]; // [rsp+20h] [rbp-1D8h] BYREF
  _BYTE v14[208]; // [rsp+30h] [rbp-1C8h] BYREF
  __int64 v15; // [rsp+100h] [rbp-F8h]

  PM_DISK::PM_DISK((PM_DISK *)v14);
  v4 = 0;
  *a2 = 0;
  v5 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 1);
  QpcTimeStamp[0] = 0;
  v6 = PM_DISK::Initialize((PM_DISK *)v14, v5, 1u);
  if ( v6 < 0
    || (v7 = 0, (*((_QWORD *)a1 + 66) & 0x80u) == 0LL)
    && (PartitionTable = PM_DISK::ReadPartitionTable((PM_DISK *)v14, (struct SC_DISK_LAYOUT **)QpcTimeStamp),
        v4 = (struct SC_DISK_LAYOUT *)QpcTimeStamp[0],
        v6 = PartitionTable,
        PartitionTable < 0) )
  {
    if ( (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 1) == 0 )
    {
      v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 14);
      *((_DWORD *)a1 + 278) = v6;
      v11 = v10;
      QpcTimeStamp[0] = 0;
      *((_QWORD *)a1 + 140) = KeQueryUnbiasedInterruptTimePrecise(QpcTimeStamp);
      KeReleaseSpinLock((PKSPIN_LOCK)a1 + 14, v11);
      goto LABEL_13;
    }
    v7 = 1;
  }
  if ( !v4 )
  {
    Pool2 = ExAllocatePool2(64, 192, 1414557008);
    v4 = (struct SC_DISK_LAYOUT *)Pool2;
    if ( !Pool2 )
    {
      v6 = -1073741670;
      goto LABEL_13;
    }
    *(_DWORD *)Pool2 = 0;
    *(_DWORD *)(Pool2 + 4) = 1;
    *(_DWORD *)(Pool2 + 48) = 0;
    if ( !v7 )
    {
      *(_DWORD *)(Pool2 + 8) = 1;
      *(_QWORD *)(Pool2 + 64) = v15;
      *(_WORD *)(Pool2 + 80) = 4;
      *(_BYTE *)(Pool2 + 82) = 1;
      *(_DWORD *)(Pool2 + 88) = *(_DWORD *)(Pool2 + 8);
    }
  }
  *a2 = v4;
  v4 = 0;
LABEL_13:
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  PM_DISK::~PM_DISK((PM_DISK *)v14);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1400066a0  mov     [rsp+arg_10], rbx
0x1400066a5  mov     [rsp+arg_18], rbp
0x1400066aa  push    rsi
0x1400066ab  push    rdi
0x1400066ac  push    r14
0x1400066ae  sub     rsp, 1E0h
0x1400066b5  mov     rax, cs:__security_cookie
0x1400066bc  xor     rax, rsp
0x1400066bf  mov     [rsp+1F8h+var_28], rax
0x1400066c7  mov     r14, rcx
0x1400066ca  mov     rdi, rdx
0x1400066cd  lea     rcx, [rsp+1F8h+var_1C8]; this
0x1400066d2  call    ??0PM_DISK@@QEAA@XZ; PM_DISK::PM_DISK(void)
0x1400066d7  xor     esi, esi
0x1400066d9  lea     rcx, [rsp+1F8h+var_1C8]; this
0x1400066de  mov     [rdi], rsi
0x1400066e1  mov     r8b, 1; unsigned __int8
0x1400066e4  mov     rdx, [r14+8]; DeviceObject
0x1400066e8  mov     [rsp+1F8h+QpcTimeStamp], rsi
0x1400066ed  call    ?Initialize@PM_DISK@@QEAAJPEAU_DEVICE_OBJECT@@E@Z; PM_DISK::Initialize(_DEVICE_OBJECT *,uchar)
0x1400066f2  mov     ebp, eax
0x1400066f4  test    eax, eax
0x1400066f6  js      short loc_14000671F
0x1400066f8  mov     rcx, [r14+210h]
0x1400066ff  xor     bl, bl
0x140006701  test    cl, cl
0x140006703  js      short loc_14000672D
0x140006705  lea     rdx, [rsp+1F8h+QpcTimeStamp]; struct SC_DISK_LAYOUT **
0x14000670a  lea     rcx, [rsp+1F8h+var_1C8]; this
0x14000670f  call    ?ReadPartitionTable@PM_DISK@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z; PM_DISK::ReadPartitionTable(SC_DISK_LAYOUT * *)
0x140006714  mov     rsi, [rsp+1F8h+QpcTimeStamp]
0x140006719  mov     ebp, eax
0x14000671b  test    eax, eax
0x14000671d  jns     short loc_14000672D
0x14000671f  mov     rax, [r14+8]
0x140006723  mov     ecx, [rax+34h]
0x140006726  test    cl, 1
0x140006729  jz      short loc_1400067A0
0x14000672b  mov     bl, 1
0x14000672d  test    rsi, rsi
0x140006730  jnz     short loc_140006799
0x140006732  mov     edx, 0C0h
0x140006737  lea     ecx, [rsi+40h]
0x14000673a  mov     r8d, 54506D50h
0x140006740  call    cs:__imp_ExAllocatePool2
0x140006747  nop     dword ptr [rax+rax+00h]
0x14000674c  mov     rsi, rax
0x14000674f  test    rax, rax
0x140006752  jnz     short loc_14000675E
0x140006754  mov     ebp, 0C000009Ah
0x140006759  jmp     loc_1400067EC
0x14000675e  mov     dword ptr [rax], 0
0x140006764  mov     dword ptr [rax+4], 1
0x14000676b  mov     dword ptr [rax+30h], 0
0x140006772  test    bl, bl
0x140006774  jnz     short loc_140006799
0x140006776  mov     dword ptr [rax+8], 1
0x14000677d  mov     rax, [rsp+1F8h+var_F8]
0x140006785  mov     [rsi+40h], rax
0x140006789  mov     word ptr [rsi+50h], 4
0x14000678f  mov     byte ptr [rsi+52h], 1
0x140006793  mov     eax, [rsi+8]
0x140006796  mov     [rsi+58h], eax
0x140006799  mov     [rdi], rsi
0x14000679c  xor     esi, esi
0x14000679e  jmp     short loc_1400067EC
0x1400067a0  lea     rcx, [r14+70h]; SpinLock
0x1400067a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400067ab  nop     dword ptr [rax+rax+00h]
0x1400067b0  lea     rcx, [rsp+1F8h+QpcTimeStamp]; QpcTimeStamp
0x1400067b5  mov     [r14+458h], ebp
0x1400067bc  mov     bl, al
0x1400067be  mov     [rsp+1F8h+QpcTimeStamp], 0
0x1400067c7  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x1400067ce  nop     dword ptr [rax+rax+00h]
0x1400067d3  mov     dl, bl; NewIrql
0x1400067d5  lea     rcx, [r14+70h]; SpinLock
0x1400067d9  mov     [r14+460h], rax
0x1400067e0  call    cs:__imp_KeReleaseSpinLock
0x1400067e7  nop     dword ptr [rax+rax+00h]
0x1400067ec  test    rsi, rsi
0x1400067ef  jz      short loc_140006802
0x1400067f1  xor     edx, edx; Tag
0x1400067f3  mov     rcx, rsi; P
0x1400067f6  call    cs:__imp_ExFreePoolWithTag
0x1400067fd  nop     dword ptr [rax+rax+00h]
0x140006802  lea     rcx, [rsp+1F8h+var_1C8]; this
0x140006807  call    ??1PM_DISK@@UEAA@XZ; PM_DISK::~PM_DISK(void)
0x14000680c  mov     eax, ebp
0x14000680e  mov     rcx, [rsp+1F8h+var_28]
0x140006816  xor     rcx, rsp; StackCookie
0x140006819  call    __security_check_cookie
0x14000681e  lea     r11, [rsp+1F8h+var_18]
0x140006826  mov     rbx, [r11+30h]
0x14000682a  mov     rbp, [r11+38h]
0x14000682e  mov     rsp, r11
0x140006831  pop     r14
0x140006833  pop     rdi
0x140006834  pop     rsi
0x140006835  retn
```
