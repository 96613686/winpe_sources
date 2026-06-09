# PmLogError(_DEVICE_EXTENSION *,_DEVICE_EXTENSION *,long)

- ea: `0x14002133c`
- end: `0x140021479`
- name: `?PmLogError@@YAXPEAU_DEVICE_EXTENSION@@0J@Z`
- size: `317`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _DEVICE_EXTENSION *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400210a8`

## callees

- `0x140004504`
- `0x14002133c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002145f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002145f`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14002144e`
- `ntoskrnl!IoReportTargetDeviceChangeAsynchronous` at `0x14002144e`
- `ntoskrnl!ExAllocatePool2` at `0x140021407`
- `ntoskrnl!ExAllocatePool2` at `0x140021407`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400213e4`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x1400213e4`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140021358`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x140021358`

## pseudocode

```c
void __fastcall PmLogError(PVOID *a1, struct _DEVICE_EXTENSION *a2, int a3)
{
  wchar_t *ErrorLogEntry; // rax
  wchar_t *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rdx
  wchar_t *v10; // rcx
  char *Pool2; // rax
  void *v12; // rbx
  int v13; // ecx
  struct _DEVICE_OBJECT *v14; // rcx

  ErrorLogEntry = (wchar_t *)IoAllocateErrorLogEntry(a1[1], 0xB0u);
  v7 = ErrorLogEntry;
  if ( ErrorLogEntry )
  {
    *((_DWORD *)ErrorLogEntry + 1) = 3145730;
    *((_DWORD *)ErrorLogEntry + 3) = a3;
    ErrorLogEntry[1] = 0;
    RtlStringCbPrintfW(ErrorLogEntry + 24, 0x80u, L"%d", *((unsigned int *)a1 + 42));
    v8 = -1;
    do
      ++v8;
    while ( v7[v8 + 24] );
    v9 = -1;
    v10 = &v7[v8 + 25];
    do
      ++v9;
    while ( v10[v9] );
    RtlStringCbPrintfW(v10, (unsigned int)(2 * (63 - v9)), L"%d", *((unsigned int *)a2 + 42));
    IoWriteErrorLogEntry(v7);
    if ( a3 == -2147221446 )
    {
      Pool2 = (char *)ExAllocatePool2(66, 40, 1112108368);
      v12 = Pool2;
      if ( Pool2 )
      {
        v13 = *((_DWORD *)a2 + 42);
        *(_DWORD *)Pool2 = 2621441;
        *((_QWORD *)Pool2 + 3) = 0;
        *(GUID *)(Pool2 + 4) = GUID_IO_DISK_CLONE_ARRIVAL;
        *((_DWORD *)Pool2 + 9) = v13;
        v14 = (struct _DEVICE_OBJECT *)*((_QWORD *)a2 + 3);
        *((_DWORD *)Pool2 + 8) = -1;
        IoReportTargetDeviceChangeAsynchronous(v14, Pool2, 0, 0);
        ExFreePoolWithTag(v12, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x14002133c  push    rbx
0x14002133e  push    rbp
0x14002133f  push    rsi
0x140021340  push    rdi
0x140021341  push    r14
0x140021343  push    r15
0x140021345  sub     rsp, 28h
0x140021349  mov     rbp, rdx
0x14002134c  mov     rdi, rcx
0x14002134f  mov     rcx, [rcx+8]; IoObject
0x140021353  mov     dl, 0B0h; EntrySize
0x140021355  mov     r14d, r8d
0x140021358  call    cs:__imp_IoAllocateErrorLogEntry
0x14002135f  nop     dword ptr [rax+rax+00h]
0x140021364  xor     r15d, r15d
0x140021367  mov     rbx, rax
0x14002136a  test    rax, rax
0x14002136d  jz      loc_14002146B
0x140021373  mov     dword ptr [rax+4], 300002h
0x14002137a  lea     r8, aD; "%d"
0x140021381  mov     [rax+0Ch], r14d
0x140021385  lea     rcx, [rax+30h]; pszDest
0x140021389  mov     [rax+2], r15w
0x14002138e  mov     edx, 80h; cbDest
0x140021393  mov     r9d, [rdi+0A8h]
0x14002139a  call    RtlStringCbPrintfW
0x14002139f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400213a3  inc     rax
0x1400213a6  cmp     [rbx+rax*2+30h], r15w
0x1400213ac  jnz     short loc_1400213A3
0x1400213ae  lea     rcx, [rbx+32h]
0x1400213b2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400213b6  lea     rcx, [rcx+rax*2]; pszDest
0x1400213ba  inc     rdx
0x1400213bd  cmp     [rcx+rdx*2], r15w
0x1400213c2  jnz     short loc_1400213BA
0x1400213c4  mov     r9d, [rbp+0A8h]
0x1400213cb  lea     r8, aD; "%d"
0x1400213d2  mov     eax, 3Fh ; '?'
0x1400213d7  sub     eax, edx
0x1400213d9  lea     edx, [rax+rax]; cbDest
0x1400213dc  call    RtlStringCbPrintfW
0x1400213e1  mov     rcx, rbx; ElEntry
0x1400213e4  call    cs:__imp_IoWriteErrorLogEntry
0x1400213eb  nop     dword ptr [rax+rax+00h]
0x1400213f0  cmp     r14d, 8004003Ah
0x1400213f7  jnz     short loc_14002146B
0x1400213f9  mov     edx, 28h ; '('
0x1400213fe  mov     r8d, 42496D50h
0x140021404  lea     ecx, [rdx+1Ah]
0x140021407  call    cs:__imp_ExAllocatePool2
0x14002140e  nop     dword ptr [rax+rax+00h]
0x140021413  mov     rbx, rax
0x140021416  test    rax, rax
0x140021419  jz      short loc_14002146B
0x14002141b  mov     ecx, [rbp+0A8h]
0x140021421  xor     r9d, r9d; Context
0x140021424  movups  xmm0, xmmword ptr cs:GUID_IO_DISK_CLONE_ARRIVAL.Data1
0x14002142b  mov     dword ptr [rax], 280001h
0x140021431  xor     r8d, r8d; Callback
0x140021434  mov     rdx, rax; NotificationStructure
0x140021437  mov     [rax+18h], r15
0x14002143b  movdqu  xmmword ptr [rax+4], xmm0
0x140021440  mov     [rax+24h], ecx
0x140021443  mov     rcx, [rbp+18h]; PhysicalDeviceObject
0x140021447  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x14002144e  call    cs:__imp_IoReportTargetDeviceChangeAsynchronous
0x140021455  nop     dword ptr [rax+rax+00h]
0x14002145a  xor     edx, edx; Tag
0x14002145c  mov     rcx, rbx; P
0x14002145f  call    cs:__imp_ExFreePoolWithTag
0x140021466  nop     dword ptr [rax+rax+00h]
0x14002146b  add     rsp, 28h
0x14002146f  pop     r15
0x140021471  pop     r14
0x140021473  pop     rdi
0x140021474  pop     rsi
0x140021475  pop     rbp
0x140021476  pop     rbx
0x140021477  retn
```
