# HsmpTracePreCallbackEnter

- ea: `0x1400044f0`
- end: `0x14000518e`
- name: `HsmpTracePreCallbackEnter`
- size: `3230`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x140001e40`
- `0x1400021e0`
- `0x14004bce0`
- `0x14004c1b0`
- `0x14004cb90`
- `0x14004d8e0`
- `0x1400526d0`
- `0x140062060`
- `0x140062f30`
- `0x140080390`

## callees

- `0x1400044f0`
- `0x140006364`
- `0x1400063c0`
- `0x14000cc5c`
- `0x14000d1d4`
- `0x14000d528`
- `0x14000d638`
- `0x1400123c8`
- `0x140012478`
- `0x1400125b4`
- `0x140012664`
- `0x140058ddc`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140004b0b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004b9c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004c26`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004c8b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004d15`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004ecb`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004f47`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000513c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004b0b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004b9c`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004c26`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004c8b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004d15`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004ecb`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140004f47`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000513c`

## pseudocode

```c
__int64 __fastcall HsmpTracePreCallbackEnter(__int64 a1, char a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // r10
  char v7; // di
  __int64 result; // rax
  __int64 v10; // rdi
  __int64 StreamSize; // rax
  __int64 v12; // rcx
  __int64 v13; // r10
  __int64 v14; // rax
  __int64 v15; // r10
  __int64 v16; // rdx
  unsigned int v17; // ebp
  int v18; // r15d
  __int64 v19; // r14
  PDEVICE_OBJECT v20; // r8
  _QWORD *v21; // r14
  __int64 v22; // r10
  int v23; // ebp
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // r8
  PIRP TopLevelIrp; // rax
  PIRP v28; // rax
  __int64 v29; // rcx
  PIRP v30; // rax
  __int64 v31; // rcx
  PIRP v32; // rax
  __int64 v33; // rcx
  PIRP v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // edx
  PIRP v37; // rax
  PIRP v38; // rax
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r8
  PIRP v42; // rax

  v5 = *(_QWORD *)(a1 + 16);
  v7 = a3;
  result = *(unsigned __int8 *)(v5 + 4);
  if ( (_DWORD)result == 6 )
  {
    if ( a2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          TopLevelIrp = IoGetTopLevelIrp();
          result = WPP_SF_qDlLqq(
                     WPP_GLOBAL_Control->AttachedDevice,
                     26,
                     *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                     a1,
                     *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                     *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL),
                     **(_DWORD **)(a1 + 16),
                     *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                     TopLevelIrp);
        }
      }
    }
    if ( v7 && a4 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v42 = IoGetTopLevelIrp();
        result = WPP_SF_qDlLqq(
                   WPP_GLOBAL_Control->AttachedDevice,
                   27,
                   *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                   a1,
                   *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                   *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL),
                   **(_DWORD **)(a1 + 16),
                   *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                   v42);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          StreamSize = HsmpGetStreamSize(*(_QWORD *)(a4 + 16));
          return WPP_SF_qiqLi(
                   *(_QWORD *)(v13 + 24),
                   28,
                   *(_QWORD *)(v12 + 16),
                   a1,
                   *(_QWORD *)(*(_QWORD *)(v12 + 16) + 32LL),
                   v12,
                   *(_DWORD *)(v12 + 28),
                   StreamSize);
        }
      }
    }
  }
  else if ( (unsigned int)result <= 5 )
  {
    if ( (_DWORD)result == 5 )
    {
      if ( a2 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v37 = IoGetTopLevelIrp();
            result = WPP_SF_qDlLqq(
                       WPP_GLOBAL_Control->AttachedDevice,
                       23,
                       *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                       a1,
                       *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                       *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL),
                       **(_DWORD **)(a1 + 16),
                       *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                       v37);
          }
        }
      }
      if ( v7 && a4 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          v38 = IoGetTopLevelIrp();
          result = WPP_SF_qDlLqq(
                     WPP_GLOBAL_Control->AttachedDevice,
                     24,
                     *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                     a1,
                     *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                     *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL),
                     **(_DWORD **)(a1 + 16),
                     *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                     v38);
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            v39 = HsmpGetStreamSize(*(_QWORD *)(a4 + 16));
            return WPP_SF_qiqLi(
                     *(_QWORD *)(v22 + 24),
                     25,
                     *(_QWORD *)(v40 + 16),
                     a1,
                     *(_QWORD *)(*(_QWORD *)(v40 + 16) + 32LL),
                     v40,
                     *(_DWORD *)(v40 + 28),
                     v39);
          }
        }
      }
    }
    else if ( *(_BYTE *)(v5 + 4) )
    {
      if ( (_DWORD)result == 3 )
      {
        if ( a2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v34 = IoGetTopLevelIrp();
              v35 = *(_QWORD *)(a1 + 16);
              result = WPP_SF_qDLLqiDq(
                         WPP_GLOBAL_Control->AttachedDevice,
                         12,
                         *(unsigned __int8 *)(v35 + 5),
                         a1,
                         *(unsigned __int8 *)(v35 + 4),
                         *(unsigned __int8 *)(v35 + 5),
                         *(_DWORD *)v35,
                         *(_QWORD *)(v35 + 8),
                         *(_QWORD *)(v35 + 40),
                         *(_DWORD *)(v35 + 24),
                         v34);
            }
          }
        }
        if ( v7 )
        {
          v10 = a5;
          if ( a5 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              result = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v28 = IoGetTopLevelIrp();
                v29 = *(_QWORD *)(a1 + 16);
                result = WPP_SF_qDLLqiDq(
                           WPP_GLOBAL_Control->AttachedDevice,
                           13,
                           *(unsigned __int8 *)(v29 + 5),
                           a1,
                           *(unsigned __int8 *)(v29 + 4),
                           *(unsigned __int8 *)(v29 + 5),
                           *(_DWORD *)v29,
                           *(_QWORD *)(v29 + 8),
                           *(_QWORD *)(v29 + 40),
                           *(_DWORD *)(v29 + 24),
                           v28);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                result = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v14 = HsmpGetStreamSize(a5);
                  v16 = 14;
                  return WPP_SF_qiqLi(
                           *(_QWORD *)(v15 + 24),
                           v16,
                           *(_QWORD *)(v10 + 16),
                           a1,
                           *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL),
                           v10,
                           *(_DWORD *)(v10 + 28),
                           v14);
                }
              }
            }
          }
        }
      }
      else
      {
        if ( (_DWORD)result != 4 )
        {
LABEL_6:
          if ( a2
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            result = WPP_SF_qlq(
                       WPP_GLOBAL_Control->AttachedDevice,
                       35,
                       *(_QWORD *)(v5 + 8),
                       a1,
                       result,
                       *(_QWORD *)(v5 + 8));
          }
          if ( !v7 )
            return result;
          v10 = a5;
          if ( !a5 || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return result;
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            result = WPP_SF_qlq(
                       WPP_GLOBAL_Control->AttachedDevice,
                       36,
                       *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                       a1,
                       *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                       *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL));
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return result;
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            return result;
          v14 = HsmpGetStreamSize(a5);
          v16 = 37;
          return WPP_SF_qiqLi(
                   *(_QWORD *)(v15 + 24),
                   v16,
                   *(_QWORD *)(v10 + 16),
                   a1,
                   *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL),
                   v10,
                   *(_DWORD *)(v10 + 28),
                   v14);
        }
        if ( a2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v30 = IoGetTopLevelIrp();
              v31 = *(_QWORD *)(a1 + 16);
              result = WPP_SF_qDLLqiDq(
                         WPP_GLOBAL_Control->AttachedDevice,
                         15,
                         *(unsigned __int8 *)(v31 + 5),
                         a1,
                         *(unsigned __int8 *)(v31 + 4),
                         *(unsigned __int8 *)(v31 + 5),
                         *(_DWORD *)v31,
                         *(_QWORD *)(v31 + 8),
                         *(_QWORD *)(v31 + 40),
                         *(_DWORD *)(v31 + 24),
                         v30);
            }
          }
        }
        if ( v7 )
        {
          v10 = a5;
          if ( a5 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              result = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v32 = IoGetTopLevelIrp();
                v33 = *(_QWORD *)(a1 + 16);
                result = WPP_SF_qDLLqiDq(
                           WPP_GLOBAL_Control->AttachedDevice,
                           16,
                           *(unsigned __int8 *)(v33 + 5),
                           a1,
                           *(unsigned __int8 *)(v33 + 4),
                           *(unsigned __int8 *)(v33 + 5),
                           *(_DWORD *)v33,
                           *(_QWORD *)(v33 + 8),
                           *(_QWORD *)(v33 + 40),
                           *(_DWORD *)(v33 + 24),
                           v32);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                result = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v14 = HsmpGetStreamSize(a5);
                  v16 = 17;
                  return WPP_SF_qiqLi(
                           *(_QWORD *)(v15 + 24),
                           v16,
                           *(_QWORD *)(v10 + 16),
                           a1,
                           *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL),
                           v10,
                           *(_DWORD *)(v10 + 28),
                           v14);
                }
              }
            }
          }
        }
      }
    }
    else if ( a2 )
    {
      v36 = *(_DWORD *)(v5 + 32);
      if ( (v36 & 0x2000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            return WPP_SF_qDqilLLL(
                     WPP_GLOBAL_Control->AttachedDevice,
                     *(_QWORD *)(*(_QWORD *)(v5 + 8) + 96LL),
                     v36 > 0x18,
                     a1,
                     0,
                     *(_QWORD *)(v5 + 8),
                     **(_QWORD **)(*(_QWORD *)(v5 + 8) + 96LL),
                     v36 > 0x18,
                     v36 & 0xFFFFFF,
                     *(unsigned __int16 *)(v5 + 42),
                     *(_DWORD *)(*(_QWORD *)(v5 + 24) + 16LL));
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          return WPP_SF_qDqZlLLL(
                   WPP_GLOBAL_Control->AttachedDevice,
                   (unsigned int)*(_QWORD *)(v5 + 8) + 88,
                   v36 > 0x18,
                   a1,
                   0,
                   *(_QWORD *)(v5 + 8),
                   *(_QWORD *)(v5 + 8) + 88LL,
                   v36 > 0x18,
                   v36,
                   *(_WORD *)(v5 + 42),
                   *(_DWORD *)(*(_QWORD *)(v5 + 24) + 16LL));
      }
    }
  }
  else
  {
    switch ( (_DWORD)result )
    {
      case 0xD:
        v17 = *(_DWORD *)(v5 + 40);
        result = v17 & 0xFFFF0000;
        if ( (_DWORD)result == 589824 )
          v17 = (v17 >> 2) & 0xFFF;
        if ( a2 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          result = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            result = WPP_SF_qDLq(
                       WPP_GLOBAL_Control->AttachedDevice,
                       18,
                       *(unsigned __int8 *)(v5 + 5),
                       a1,
                       13,
                       *(unsigned __int8 *)(v5 + 5),
                       *(_QWORD *)(v5 + 8));
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              result = WPP_SF_ql(WPP_GLOBAL_Control->AttachedDevice, 19, a3, a1, v17);
          }
        }
        if ( v7 )
        {
          if ( a5 )
          {
            result = *(_QWORD *)(a5 + 16);
            v18 = *(_DWORD *)(a5 + 28);
            v19 = *(_QWORD *)(result + 32);
          }
          else
          {
            v19 = 0;
            v18 = 0;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              result = WPP_SF_qDLq(
                         WPP_GLOBAL_Control->AttachedDevice,
                         20,
                         *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 5LL),
                         a1,
                         *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                         *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 5LL),
                         *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL));
            v20 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              result = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v25 = HsmpGetStreamSize(a5);
                result = WPP_SF_qiqLi(*(_QWORD *)(v26 + 24), 21, v26, a1, v19, a5, v18, v25);
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                result = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  return WPP_SF_ql(WPP_GLOBAL_Control->AttachedDevice, 22, v20, a1, v17);
              }
            }
          }
        }
        break;
      case 0x11:
        v21 = *(_QWORD **)(v5 + 24);
        if ( v21 )
          v21 = (_QWORD *)*v21;
        if ( a2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              result = WPP_SF_qDlLqiiD(
                         WPP_GLOBAL_Control->AttachedDevice,
                         29,
                         *(unsigned __int8 *)(v5 + 5),
                         a1,
                         17,
                         *(unsigned __int8 *)(v5 + 5),
                         *(_DWORD *)v5,
                         *(_QWORD *)(v5 + 8),
                         *(_QWORD *)(v5 + 40),
                         v21,
                         *(_DWORD *)(v5 + 32));
          }
        }
        if ( v7 )
        {
          v10 = a5;
          if ( a5 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              result = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v41 = *(_QWORD *)(a1 + 16);
                result = WPP_SF_qDlLqiiD(
                           WPP_GLOBAL_Control->AttachedDevice,
                           30,
                           v41,
                           a1,
                           *(unsigned __int8 *)(v41 + 4),
                           *(unsigned __int8 *)(v41 + 5),
                           *(_DWORD *)v41,
                           *(_QWORD *)(v41 + 8),
                           *(_QWORD *)(v41 + 40),
                           v21,
                           *(_DWORD *)(v41 + 32));
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                result = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v14 = HsmpGetStreamSize(a5);
                  v16 = 31;
                  return WPP_SF_qiqLi(
                           *(_QWORD *)(v15 + 24),
                           v16,
                           *(_QWORD *)(v10 + 16),
                           a1,
                           *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL),
                           v10,
                           *(_DWORD *)(v10 + 28),
                           v14);
                }
              }
            }
          }
        }
        break;
      case 0xFF:
        v23 = *(_DWORD *)(v5 + 24);
        v24 = *(_DWORD *)(v5 + 28);
        if ( a2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            result = HIDWORD(WPP_GLOBAL_Control->Timer);
            if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              result = WPP_SF_qDqlL(
                         WPP_GLOBAL_Control->AttachedDevice,
                         32,
                         a3,
                         a1,
                         255,
                         *(_QWORD *)(v5 + 8),
                         v23,
                         *(_DWORD *)(v5 + 28));
          }
        }
        if ( v7 )
        {
          v10 = a5;
          if ( a5 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              result = HIDWORD(WPP_GLOBAL_Control->Timer);
              if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                result = WPP_SF_qDqlL(
                           WPP_GLOBAL_Control->AttachedDevice,
                           33,
                           *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                           a1,
                           *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 4LL),
                           *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                           v23,
                           v24);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                result = HIDWORD(WPP_GLOBAL_Control->Timer);
                if ( (result & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  v14 = HsmpGetStreamSize(a5);
                  v16 = 34;
                  return WPP_SF_qiqLi(
                           *(_QWORD *)(v15 + 24),
                           v16,
                           *(_QWORD *)(v10 + 16),
                           a1,
                           *(_QWORD *)(*(_QWORD *)(v10 + 16) + 32LL),
                           v10,
                           *(_DWORD *)(v10 + 28),
                           v14);
                }
              }
            }
          }
        }
        break;
      default:
        goto LABEL_6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400044f0  mov     [rsp+arg_10], rbx
0x1400044f5  push    rbp
0x1400044f6  push    rsi
0x1400044f7  push    rdi
0x1400044f8  sub     rsp, 60h
0x1400044fc  mov     r10, [rcx+10h]
0x140004500  mov     rbp, r9
0x140004503  movzx   edi, r8b
0x140004507  mov     rsi, rcx
0x14000450a  movzx   eax, byte ptr [r10+4]
0x14000450f  cmp     eax, 6
0x140004512  jz      loc_1400045BC
0x140004518  mov     [rsp+78h+arg_0], r14
0x140004520  cmp     eax, 5
0x140004523  jbe     loc_14000466F
0x140004529  cmp     eax, 0Dh
0x14000452c  jz      loc_140004714
0x140004532  cmp     eax, 11h
0x140004535  jz      loc_1400048B5
0x14000453b  cmp     eax, 0FFh
0x140004540  jz      loc_1400049E5
0x140004546  lea     rbx, WPP_GLOBAL_Control
0x14000454d  test    dl, dl
0x14000454f  jnz     loc_140004FE3
0x140004555  test    dil, dil
0x140004558  jz      short loc_1400045A3
0x14000455a  mov     rdi, [rsp+78h+arg_20]
0x140004562  test    rdi, rdi
0x140004565  jz      short loc_1400045A3
0x140004567  mov     rcx, cs:WPP_GLOBAL_Control
0x14000456e  cmp     rcx, rbx
0x140004571  jz      short loc_1400045A3
0x140004573  mov     eax, [rcx+2Ch]
0x140004576  test    al, 4
0x140004578  jz      short loc_140004584
0x14000457a  cmp     byte ptr [rcx+29h], 5
0x14000457e  jnb     loc_140004B5D
0x140004584  mov     r10, cs:WPP_GLOBAL_Control
0x14000458b  cmp     r10, rbx
0x14000458e  jz      short loc_1400045A3
0x140004590  mov     eax, [r10+2Ch]
0x140004594  test    al, 4
0x140004596  jz      short loc_1400045A3
0x140004598  cmp     byte ptr [r10+29h], 5
0x14000459d  jnb     loc_140004B8A
0x1400045a3  mov     r14, [rsp+78h+arg_0]
0x1400045ab  mov     rbx, [rsp+78h+arg_10]
0x1400045b3  add     rsp, 60h
0x1400045b7  pop     rdi
0x1400045b8  pop     rsi
0x1400045b9  pop     rbp
0x1400045ba  retn
0x1400045bc  lea     rbx, WPP_GLOBAL_Control
0x1400045c3  test    dl, dl
0x1400045c5  jz      short loc_1400045E4
0x1400045c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045ce  cmp     rcx, rbx
0x1400045d1  jz      short loc_1400045E4
0x1400045d3  mov     eax, [rcx+2Ch]
0x1400045d6  test    al, 4
0x1400045d8  jz      short loc_1400045E4
0x1400045da  cmp     byte ptr [rcx+29h], 5
0x1400045de  jnb     loc_140004B0B
0x1400045e4  test    dil, dil
0x1400045e7  jz      short loc_1400045AB
0x1400045e9  test    rbp, rbp
0x1400045ec  jz      short loc_1400045AB
0x1400045ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400045f5  cmp     rcx, rbx
0x1400045f8  jz      short loc_1400045AB
0x1400045fa  mov     eax, [rcx+2Ch]
0x1400045fd  test    al, 4
0x1400045ff  jz      short loc_14000460B
0x140004601  cmp     byte ptr [rcx+29h], 4
0x140004605  jnb     loc_14000513C
0x14000460b  mov     r10, cs:WPP_GLOBAL_Control
0x140004612  cmp     r10, rbx
0x140004615  jz      short loc_1400045AB
0x140004617  mov     eax, [r10+2Ch]
0x14000461b  test    al, 4
0x14000461d  jz      short loc_1400045AB
0x14000461f  cmp     byte ptr [r10+29h], 4
0x140004624  jb      short loc_1400045AB
0x140004626  mov     rcx, [rbp+10h]
0x14000462a  call    HsmpGetStreamSize
0x14000462f  mov     r8, [rcx+10h]
0x140004633  mov     edx, 1Ch
0x140004638  mov     [rsp+78h+var_40], rax
0x14000463d  mov     r9, rsi
0x140004640  mov     eax, [rcx+1Ch]
0x140004643  mov     dword ptr [rsp+78h+var_48], eax
0x140004647  mov     rax, [r8+20h]
0x14000464b  mov     [rsp+78h+var_50], rcx
0x140004650  mov     rcx, [r10+18h]
0x140004654  mov     [rsp+78h+var_58], rax
0x140004659  call    WPP_SF_qiqLi
0x14000465e  mov     rbx, [rsp+78h+arg_10]
0x140004666  add     rsp, 60h
0x14000466a  pop     rdi
0x14000466b  pop     rsi
0x14000466c  pop     rbp
0x14000466d  retn
0x14000466f  jz      loc_140004EA7
0x140004675  mov     ecx, eax
0x140004677  test    eax, eax
0x140004679  jz      loc_140004D7A
0x14000467f  sub     ecx, 3
0x140004682  jz      loc_1400047D2
0x140004688  cmp     ecx, 1
0x14000468b  jnz     loc_140004546
0x140004691  lea     rbx, WPP_GLOBAL_Control
0x140004698  test    dl, dl
0x14000469a  jnz     loc_140004C01
0x1400046a0  test    dil, dil
0x1400046a3  jz      loc_1400045A3
0x1400046a9  mov     rdi, [rsp+78h+arg_20]
0x1400046b1  test    rdi, rdi
0x1400046b4  jz      loc_1400045A3
0x1400046ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400046c1  cmp     rcx, rbx
0x1400046c4  jz      loc_1400045A3
0x1400046ca  mov     eax, [rcx+2Ch]
0x1400046cd  test    al, 4
0x1400046cf  jz      short loc_1400046DB
0x1400046d1  cmp     byte ptr [rcx+29h], 4
0x1400046d5  jnb     loc_140004C8B
0x1400046db  mov     r10, cs:WPP_GLOBAL_Control
0x1400046e2  cmp     r10, rbx
0x1400046e5  jz      loc_1400045A3
0x1400046eb  mov     eax, [r10+2Ch]
0x1400046ef  test    al, 4
0x1400046f1  jz      loc_1400045A3
0x1400046f7  cmp     byte ptr [r10+29h], 4
0x1400046fc  jb      loc_1400045A3
0x140004702  mov     rcx, rdi
0x140004705  call    HsmpGetStreamSize
0x14000470a  mov     edx, 11h
0x14000470f  jmp     loc_140004943
0x140004714  mov     ebp, [r10+28h]
0x140004718  mov     eax, ebp
0x14000471a  and     eax, 0FFFF0000h
0x14000471f  cmp     eax, 90000h
0x140004724  jnz     short loc_14000472F
0x140004726  shr     ebp, 2
0x140004729  and     ebp, 0FFFh
0x14000472f  lea     rbx, WPP_GLOBAL_Control
0x140004736  test    dl, dl
0x140004738  jnz     loc_140004855
0x14000473e  test    dil, dil
0x140004741  jz      loc_1400045A3
0x140004747  mov     rdi, [rsp+78h+arg_20]
0x14000474f  mov     [rsp+78h+arg_8], r15
0x140004757  test    rdi, rdi
0x14000475a  jz      loc_140004A92
0x140004760  mov     rax, [rdi+10h]
0x140004764  mov     r15d, [rdi+1Ch]
0x140004768  mov     r14, [rax+20h]
0x14000476c  mov     rcx, cs:WPP_GLOBAL_Control
0x140004773  cmp     rcx, rbx
0x140004776  jz      short loc_1400047C5
0x140004778  mov     eax, [rcx+2Ch]
0x14000477b  test    al, 4
0x14000477d  jz      short loc_140004789
0x14000477f  cmp     byte ptr [rcx+29h], 4
0x140004783  jnb     loc_140004AA2
0x140004789  mov     r8, cs:WPP_GLOBAL_Control
0x140004790  cmp     r8, rbx
0x140004793  jz      short loc_1400047C5
0x140004795  mov     eax, [r8+2Ch]
0x140004799  test    al, 4
0x14000479b  jz      short loc_1400047A8
0x14000479d  cmp     byte ptr [r8+29h], 4
0x1400047a2  jnb     loc_140004AD9
0x1400047a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400047af  cmp     rcx, rbx
0x1400047b2  jz      short loc_1400047C5
0x1400047b4  mov     eax, [rcx+2Ch]
0x1400047b7  test    al, 4
0x1400047b9  jz      short loc_1400047C5
0x1400047bb  cmp     byte ptr [rcx+29h], 4
0x1400047bf  jnb     loc_140004A70
0x1400047c5  mov     r15, [rsp+78h+arg_8]
0x1400047cd  jmp     loc_1400045A3
0x1400047d2  lea     rbx, WPP_GLOBAL_Control
0x1400047d9  test    dl, dl
0x1400047db  jnz     loc_140004CF0
0x1400047e1  test    dil, dil
0x1400047e4  jz      loc_1400045A3
0x1400047ea  mov     rdi, [rsp+78h+arg_20]
0x1400047f2  test    rdi, rdi
0x1400047f5  jz      loc_1400045A3
0x1400047fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140004802  cmp     rcx, rbx
0x140004805  jz      loc_1400045A3
0x14000480b  mov     eax, [rcx+2Ch]
0x14000480e  test    al, 4
0x140004810  jz      short loc_14000481C
0x140004812  cmp     byte ptr [rcx+29h], 4
0x140004816  jnb     loc_140004B9C
0x14000481c  mov     r10, cs:WPP_GLOBAL_Control
0x140004823  cmp     r10, rbx
0x140004826  jz      loc_1400045A3
0x14000482c  mov     eax, [r10+2Ch]
0x140004830  test    al, 4
0x140004832  jz      loc_1400045A3
0x140004838  cmp     byte ptr [r10+29h], 4
0x14000483d  jb      loc_1400045A3
0x140004843  mov     rcx, rdi
0x140004846  call    HsmpGetStreamSize
0x14000484b  mov     edx, 0Eh
0x140004850  jmp     loc_140004943
0x140004855  mov     rcx, cs:WPP_GLOBAL_Control
0x14000485c  cmp     rcx, rbx
0x14000485f  jz      loc_14000473E
0x140004865  mov     eax, [rcx+2Ch]
0x140004868  test    al, 4
0x14000486a  jz      short loc_140004876
0x14000486c  cmp     byte ptr [rcx+29h], 5
0x140004870  jnb     loc_14000510B
0x140004876  mov     rcx, cs:WPP_GLOBAL_Control
0x14000487d  cmp     rcx, rbx
0x140004880  jz      loc_14000473E
0x140004886  mov     eax, [rcx+2Ch]
0x140004889  test    al, 4
0x14000488b  jz      loc_14000473E
0x140004891  cmp     byte ptr [rcx+29h], 5
0x140004895  jb      loc_14000473E
0x14000489b  mov     rcx, [rcx+18h]
0x14000489f  mov     edx, 13h
0x1400048a4  mov     r9, rsi
0x1400048a7  mov     dword ptr [rsp+78h+var_58], ebp
0x1400048ab  call    WPP_SF_ql
0x1400048b0  jmp     loc_14000473E
0x1400048b5  mov     r14, [r10+18h]
0x1400048b9  test    r14, r14
0x1400048bc  jz      loc_140004A9D
0x1400048c2  mov     r14, [r14]
0x1400048c5  lea     rbx, WPP_GLOBAL_Control
0x1400048cc  test    dl, dl
0x1400048ce  jnz     loc_140004972
0x1400048d4  test    dil, dil
0x1400048d7  jz      loc_1400045A3
0x1400048dd  mov     rdi, [rsp+78h+arg_20]
0x1400048e5  test    rdi, rdi
0x1400048e8  jz      loc_1400045A3
0x1400048ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048f5  cmp     rcx, rbx
0x1400048f8  jz      loc_1400045A3
0x1400048fe  mov     eax, [rcx+2Ch]
0x140004901  test    al, 4
0x140004903  jz      short loc_14000490F
0x140004905  cmp     byte ptr [rcx+29h], 4
0x140004909  jnb     loc_1400050B7
0x14000490f  mov     r10, cs:WPP_GLOBAL_Control
0x140004916  cmp     r10, rbx
0x140004919  jz      loc_1400045A3
0x14000491f  mov     eax, [r10+2Ch]
0x140004923  test    al, 4
0x140004925  jz      loc_1400045A3
0x14000492b  cmp     byte ptr [r10+29h], 4
0x140004930  jb      loc_1400045A3
0x140004936  mov     rcx, rdi
0x140004939  call    HsmpGetStreamSize
0x14000493e  mov     edx, 1Fh
0x140004943  mov     r8, [rdi+10h]
0x140004947  mov     [rsp+78h+var_40], rax
0x14000494c  mov     eax, [rdi+1Ch]
0x14000494f  mov     dword ptr [rsp+78h+var_48], eax
0x140004953  mov     [rsp+78h+var_50], rdi
0x140004958  mov     rax, [r8+20h]
0x14000495c  mov     r9, rsi
0x14000495f  mov     rcx, [r10+18h]
0x140004963  mov     [rsp+78h+var_58], rax
0x140004968  call    WPP_SF_qiqLi
0x14000496d  jmp     loc_1400045A3
0x140004972  mov     rcx, cs:WPP_GLOBAL_Control
0x140004979  cmp     rcx, rbx
0x14000497c  jz      loc_1400048D4
0x140004982  mov     eax, [rcx+2Ch]
0x140004985  test    al, 4
0x140004987  jz      loc_1400048D4
0x14000498d  cmp     byte ptr [rcx+29h], 5
0x140004991  jb      loc_1400048D4
0x140004997  mov     eax, [r10+20h]
0x14000499b  mov     edx, 1Dh
0x1400049a0  movzx   r8d, byte ptr [r10+5]
0x1400049a5  mov     r9, rsi
0x1400049a8  mov     rcx, [rcx+18h]
0x1400049ac  mov     dword ptr [rsp+78h+var_28], eax
0x1400049b0  mov     rax, [r10+28h]
0x1400049b4  mov     [rsp+78h+var_30], r14
0x1400049b9  mov     [rsp+78h+var_38], rax
0x1400049be  mov     rax, [r10+8]
0x1400049c2  mov     [rsp+78h+var_40], rax
0x1400049c7  mov     eax, [r10]
0x1400049ca  mov     dword ptr [rsp+78h+var_48], eax
0x1400049ce  mov     dword ptr [rsp+78h+var_50], r8d
0x1400049d3  mov     dword ptr [rsp+78h+var_58], 11h
0x1400049db  call    WPP_SF_qDlLqiiD
0x1400049e0  jmp     loc_1400048D4
  ... truncated ...
```
