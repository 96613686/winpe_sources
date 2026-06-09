# DrDrive::OnNotifyChangeDirectoryCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140012ff0`
- end: `0x1400131d1`
- name: `?OnNotifyChangeDirectoryCompletion@DrDrive@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `481`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _DWORD *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1400016a0`
- `0x14000324c`
- `0x1400032c0`
- `0x140003704`
- `0x1400117e0`
- `0x140011870`
- `0x140012ff0`
- `0x140023cf0`
- `0x140024020`

## string_xrefs

- `0x1400130c5`: `IRP_MJ_CREATE                  `

## pseudocode

```c
__int64 __fastcall DrDrive::OnNotifyChangeDirectoryCompletion(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _DWORD *a4,
        __int64 a5)
{
  __int64 v9; // rdx
  __int64 v10; // rsi
  __int64 v11; // rcx
  int v12; // r10d
  unsigned int v13; // r8d

  v9 = *(_QWORD *)(*(_QWORD *)a5 + 32LL);
  v10 = *(_QWORD *)(v9 + 48);
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
LABEL_18:
    if ( v10 )
      DrDevice::CompleteBusyExchange(a1, a5, -1073741434, 0);
    else
      DrDevice::DiscardBusyExchange(a1, a5);
    *a4 = 0;
    SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
    return 3221225862LL;
  }
  v11 = a3 - 20;
  v12 = *(_DWORD *)(v9 + 40);
  v13 = *(_DWORD *)(a2 + 16) - v12;
  if ( a3 != 21 || *(_DWORD *)(a2 + 16) )
  {
    if ( (unsigned int)v11 > v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          93,
          WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
          (unsigned int)v11,
          v13);
      goto LABEL_18;
    }
  }
  else
  {
    v11 = v13;
  }
  *(_DWORD *)(v9 + 40) = v12 + v11;
  if ( (_DWORD)v11 == v13 )
  {
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_sL(
          WPP_GLOBAL_Control->AttachedDevice,
          94,
          (unsigned int)WPP_83886b54412a34bbe371408c37660ab5_Traceguids,
          (unsigned int)&(&IrpNames)[5 * *(unsigned __int8 *)(v10 + 32)],
          *(_DWORD *)(a2 + 12));
      *(_QWORD *)(v10 + 184) = 0;
      *(_DWORD *)(v10 + 176) = *(_DWORD *)(a2 + 12);
      DrDevice::CompleteBusyExchange(a1, a5, *(_DWORD *)(a2 + 12), 0);
    }
    else
    {
      DrDevice::DiscardBusyExchange(a1, a5);
    }
    *a4 = 1;
  }
  else
  {
    DrDevice::MarkIdle(v11, a5);
    DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
    *a4 = 0;
  }
  SmartPtr<DrFile>::~SmartPtr<DrFile>(a5);
  return 0;
}

```

## disassembly

```asm
0x140012ff0  push    rbx
0x140012ff2  push    rbp
0x140012ff3  push    rsi
0x140012ff4  push    rdi
0x140012ff5  push    r14
0x140012ff7  sub     rsp, 30h
0x140012ffb  mov     rbx, [rsp+58h+arg_20]
0x140013003  mov     rbp, rdx
0x140013006  mov     r14, r9
0x140013009  mov     r9d, r8d
0x14001300c  mov     rdi, rcx
0x14001300f  mov     rax, [rbx]
0x140013012  mov     rdx, [rax+20h]
0x140013016  mov     rsi, [rdx+30h]
0x14001301a  cmp     r8d, 14h
0x14001301e  jnb     short loc_14001305B
0x140013020  mov     rcx, cs:WPP_GLOBAL_Control
0x140013027  lea     rax, WPP_GLOBAL_Control
0x14001302e  cmp     rcx, rax
0x140013031  jz      loc_14001314C
0x140013037  cmp     byte ptr [rcx+29h], 2
0x14001303b  jb      loc_14001314C
0x140013041  mov     rcx, [rcx+18h]
0x140013045  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x14001304c  mov     edx, 5Ch ; '\'
0x140013051  call    WPP_SF_
0x140013056  jmp     loc_14001314C
0x14001305b  mov     eax, [rbp+10h]
0x14001305e  lea     ecx, [r9-14h]
0x140013062  mov     r10d, [rdx+28h]
0x140013066  mov     r8d, eax
0x140013069  sub     r8d, r10d
0x14001306c  cmp     ecx, 1
0x14001306f  jnz     loc_14001310C
0x140013075  test    eax, eax
0x140013077  jnz     loc_14001310C
0x14001307d  mov     ecx, r8d
0x140013080  lea     eax, [r10+rcx]
0x140013084  mov     [rdx+28h], eax
0x140013087  cmp     ecx, r8d
0x14001308a  jnz     loc_140013195
0x140013090  test    rsi, rsi
0x140013093  jz      loc_140013181
0x140013099  mov     rcx, cs:WPP_GLOBAL_Control
0x1400130a0  lea     rax, WPP_GLOBAL_Control
0x1400130a7  cmp     rcx, rax
0x1400130aa  jz      short loc_1400130E1
0x1400130ac  cmp     byte ptr [rcx+29h], 5
0x1400130b0  jb      short loc_1400130E1
0x1400130b2  movzx   eax, byte ptr [rsi+20h]
0x1400130b6  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x1400130bd  mov     rcx, [rcx+18h]
0x1400130c1  lea     rdx, [rax+rax*4]
0x1400130c5  lea     rax, ?IrpNames@@3PAY0CI@DA; "IRP_MJ_CREATE                  "
0x1400130cc  lea     r9, [rax+rdx*8]
0x1400130d0  mov     eax, [rbp+0Ch]
0x1400130d3  mov     edx, 5Eh ; '^'
0x1400130d8  mov     [rsp+58h+var_38], eax
0x1400130dc  call    WPP_SF_sL
0x1400130e1  mov     qword ptr [rsi+0B8h], 0
0x1400130ec  xor     r9d, r9d
0x1400130ef  mov     eax, [rbp+0Ch]
0x1400130f2  mov     rdx, rbx
0x1400130f5  mov     [rsi+0B0h], eax
0x1400130fb  mov     rcx, rdi
0x1400130fe  mov     r8d, [rbp+0Ch]
0x140013102  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140013107  jmp     loc_14001318C
0x14001310c  cmp     ecx, r8d
0x14001310f  jbe     loc_140013080
0x140013115  mov     r10, cs:WPP_GLOBAL_Control
0x14001311c  lea     rax, WPP_GLOBAL_Control
0x140013123  cmp     r10, rax
0x140013126  jz      short loc_14001314C
0x140013128  cmp     byte ptr [r10+29h], 2
0x14001312d  jb      short loc_14001314C
0x14001312f  mov     [rsp+58h+var_38], r8d
0x140013134  mov     r9d, ecx
0x140013137  mov     rcx, [r10+18h]
0x14001313b  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140013142  mov     edx, 5Dh ; ']'
0x140013147  call    WPP_SF_dd
0x14001314c  mov     ebp, 0C0000186h
0x140013151  mov     rdx, rbx
0x140013154  mov     rcx, rdi
0x140013157  test    rsi, rsi
0x14001315a  jz      short loc_140013169
0x14001315c  xor     r9d, r9d
0x14001315f  mov     r8d, ebp
0x140013162  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140013167  jmp     short loc_14001316E
0x140013169  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14001316e  mov     rcx, rbx
0x140013171  mov     dword ptr [r14], 0
0x140013178  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14001317d  mov     eax, ebp
0x14001317f  jmp     short loc_1400131C5
0x140013181  mov     rdx, rbx
0x140013184  mov     rcx, rdi
0x140013187  call    ?DiscardBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::DiscardBusyExchange(SmartPtr<DrExchange> &)
0x14001318c  mov     dword ptr [r14], 1
0x140013193  jmp     short loc_1400131BB
0x140013195  mov     rdx, rbx
0x140013198  call    ?MarkIdle@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@@Z; DrDevice::MarkIdle(SmartPtr<DrExchange> &)
0x14001319d  mov     rcx, [rdi+20h]
0x1400131a1  xor     r8d, r8d; unsigned int
0x1400131a4  mov     rcx, [rcx+2E0h]; this
0x1400131ab  lea     edx, [r8+14h]; unsigned int
0x1400131af  call    ?ReadMore@DrSession@@QEAAHKK@Z; DrSession::ReadMore(ulong,ulong)
0x1400131b4  mov     dword ptr [r14], 0
0x1400131bb  mov     rcx, rbx
0x1400131be  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x1400131c3  xor     eax, eax
0x1400131c5  add     rsp, 30h
0x1400131c9  pop     r14
0x1400131cb  pop     rdi
0x1400131cc  pop     rsi
0x1400131cd  pop     rbp
0x1400131ce  pop     rbx
0x1400131cf  retn
```
