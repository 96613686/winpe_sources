# DrDrive::OnDirectoryControlCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x1400127a0`
- end: `0x140012856`
- name: `?OnDirectoryControlCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `182`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, RefCount **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x140001890`
- `0x140006560`
- `0x1400117e0`
- `0x1400127a0`
- `0x140024020`

## pseudocode

```c
__int64 __fastcall DrDrive::OnDirectoryControlCompletion(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, RefCount **a5)
{
  __int64 v5; // r10
  RefCount *v7; // rcx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(__int64); // rax
  unsigned int v10; // edi

  v5 = a1;
  v7 = *a5;
  v8 = *((_QWORD *)*a5 + 4);
  if ( *(_BYTE *)(v8 + 57) < 2u )
  {
    v9 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 296LL);
    if ( v7 )
      RefCount::AddRef(v7);
    goto LABEL_12;
  }
  if ( *(_BYTE *)(v8 + 57) == 2 )
  {
    v9 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 304LL);
    if ( v7 )
      RefCount::AddRef(v7);
LABEL_12:
    v10 = v9(v5);
    goto LABEL_13;
  }
  if ( *(_QWORD *)(v8 + 48) )
    DrDevice::CompleteBusyExchange(v5, (__int64)a5, -1073741434, 0);
  else
    DrDevice::DiscardBusyExchange(v5, a5);
  *a4 = 0;
  v10 = -1073741434;
LABEL_13:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return v10;
}

```

## disassembly

```asm
0x1400127a0  mov     [rsp+arg_0], rbx
0x1400127a5  push    rdi
0x1400127a6  sub     rsp, 40h
0x1400127aa  mov     rbx, [rsp+48h+arg_20]
0x1400127af  mov     r10, rcx
0x1400127b2  mov     rdi, r9
0x1400127b5  mov     rcx, [rbx]; this
0x1400127b8  mov     rax, [rcx+20h]
0x1400127bc  cmp     byte ptr [rax+39h], 2
0x1400127c0  jb      short loc_140012813
0x1400127c2  jnz     short loc_1400127E4
0x1400127c4  mov     rax, [r10]
0x1400127c7  mov     [rsp+48h+arg_20], rcx
0x1400127cc  mov     rax, [rax+130h]
0x1400127d3  test    rcx, rcx
0x1400127d6  jz      short loc_1400127DD
0x1400127d8  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x1400127dd  lea     rcx, [rsp+48h+arg_20]
0x1400127e2  jmp     short loc_140012831
0x1400127e4  cmp     qword ptr [rax+30h], 0
0x1400127e9  mov     rdx, rbx
0x1400127ec  mov     rcx, r10
0x1400127ef  jz      short loc_140012801
0x1400127f1  xor     r9d, r9d
0x1400127f4  mov     r8d, 0C0000186h
0x1400127fa  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400127ff  jmp     short loc_140012806
0x140012801  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x140012806  mov     dword ptr [rdi], 0
0x14001280c  mov     edi, 0C0000186h
0x140012811  jmp     short loc_140012840
0x140012813  mov     rax, [r10]
0x140012816  mov     [rsp+48h+var_18], rcx
0x14001281b  mov     rax, [rax+128h]
0x140012822  test    rcx, rcx
0x140012825  jz      short loc_14001282C
0x140012827  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14001282c  lea     rcx, [rsp+48h+var_18]
0x140012831  mov     [rsp+48h+var_28], rcx
0x140012836  mov     rcx, r10
0x140012839  call    _guard_dispatch_icall
0x14001283e  mov     edi, eax
0x140012840  mov     rcx, rbx
0x140012843  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140012848  mov     rbx, [rsp+48h+arg_0]
0x14001284d  mov     eax, edi
0x14001284f  add     rsp, 40h
0x140012853  pop     rdi
0x140012854  retn
```
