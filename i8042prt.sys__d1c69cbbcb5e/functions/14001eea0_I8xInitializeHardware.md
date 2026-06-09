# I8xInitializeHardware

- ea: `0x14001eea0`
- end: `0x14001f4d1`
- name: `I8xInitializeHardware`
- size: `1585`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1400171e8`
- `0x14001e950`

## callees

- `0x140004530`
- `0x1400059c0`
- `0x140006170`
- `0x140006950`
- `0x140007b10`
- `0x14001a19c`
- `0x14001ce6c`
- `0x14001d8b0`
- `0x14001eea0`

## import_xrefs

- `ntoskrnl!IoInvalidateDeviceState` at `0x14001f149`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001f278`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001f149`
- `ntoskrnl!IoInvalidateDeviceState` at `0x14001f278`

## pseudocode

```c
__int64 __fastcall I8xInitializeHardware(int *a1, int *a2, int a3)
{
  PDRIVER_CONTROL DeviceRoutine; // r13
  unsigned __int8 *DeviceContext; // rbp
  __int128 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // r9
  char v12; // bl
  bool v13; // dl
  char v14; // r12
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned __int16 v21; // r9
  int v22; // eax
  int v23; // edx
  __int64 result; // rax
  int v25; // eax
  int v26; // edx
  __int64 v27; // [rsp+28h] [rbp-60h]
  bool v28; // [rsp+A0h] [rbp+18h]

  DeviceRoutine = WPP_MAIN_CB.Queue.Wcb.DeviceRoutine;
  DeviceContext = (unsigned __int8 *)WPP_MAIN_CB.Queue.Wcb.DeviceContext;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      (__int64)a2,
      0xFu,
      0x26u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  v8 = *(_OWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL);
  I8xDrainOutputBuffer(
    *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 208LL),
    *(_QWORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 216LL));
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) == 0
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v9,
      0x10u,
      0x27u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) == 0
    && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      v9,
      0x10u,
      0x28u,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
  }
  if ( (a3 & 1) != 0 )
  {
    v12 = 1;
    v13 = 1;
    v14 = 1;
  }
  else
  {
    v14 = BYTE2(a3) & 1;
    v13 = (a3 & 0x20000) != 0;
    v12 = 0;
  }
  v28 = v13;
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0
    && !v12
    && v14
    && *((_DWORD *)DeviceContext + 22) == 2 )
  {
    LOBYTE(v11) = -83;
    LOBYTE(v10) = 3;
    I8xPutBytePolled(1, 0, v10, v11);
    v13 = v28;
  }
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0
    && !v12
    && v13
    && *((_DWORD *)DeviceRoutine + 22) == 2 )
  {
    LOBYTE(v11) = -89;
    LOBYTE(v10) = 3;
    I8xPutBytePolled(1, 0, v10, v11);
  }
  I8xDrainOutputBuffer(v8, *((__int64 *)&v8 + 1));
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) == 0 || !v14 )
  {
    *a1 = -1073741810;
    goto LABEL_38;
  }
  v18 = I8xInitializeKeyboard((__int64 *)DeviceContext, v15, v16, v17);
  *a1 = v18;
  if ( v18 < 0 )
  {
    if ( v18 != -1073741667 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x11u,
          0x2Du,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v18);
LABEL_28:
      I8xManuallyRemoveDevice((__int64)DeviceContext, v15);
      goto LABEL_38;
    }
    if ( !BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x10u,
          0x2Bu,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      goto LABEL_28;
    }
    if ( v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x10u,
          0x2Cu,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      *((_DWORD *)DeviceContext + 139) |= 2u;
      IoInvalidateDeviceState(*((PDEVICE_OBJECT *)DeviceContext + 4));
    }
  }
LABEL_38:
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) == 0 || !v28 )
  {
    *a2 = -1073741810;
    goto LABEL_54;
  }
  v19 = I8xInitializeMouse((__int64 *)DeviceRoutine, v15, v16, v17);
  *a2 = v19;
  if ( v19 < 0 && v12 )
  {
    if ( v19 != -1073741667 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v27) = v19;
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x11u,
          0x30u,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v27);
      }
LABEL_45:
      I8xManuallyRemoveDevice((__int64)DeviceRoutine, v15);
      goto LABEL_54;
    }
    if ( !BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x10u,
          0x2Eu,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      goto LABEL_45;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v15,
        0x10u,
        0x2Fu,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    *((_DWORD *)DeviceRoutine + 139) |= 2u;
    IoInvalidateDeviceState(*((PDEVICE_OBJECT *)DeviceRoutine + 4));
  }
LABEL_54:
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 && *a1 >= 0 && v14 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        (__int64)WPP_GLOBAL_Control->DeviceExtension,
        v15,
        0x10u,
        0x31u,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    LOBYTE(v16) = 1;
    LOBYTE(v17) = -19;
    v20 = I8xPutBytePolled(0, 1, v16, v17);
    if ( v20 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = 51;
        goto LABEL_65;
      }
    }
    else
    {
      LOBYTE(v16) = 1;
      v20 = I8xPutBytePolled(0, 1, v16, DeviceContext[732]);
      if ( v20 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = 50;
LABEL_65:
        LODWORD(v27) = v20;
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v15,
          0x10u,
          v21,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v27);
      }
    }
  }
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 && v14 )
  {
    LOBYTE(v17) = -82;
    LOBYTE(v16) = 3;
    v22 = I8xPutBytePolled(1, 0, v16, v17);
    if ( v22 < 0 && v12 )
    {
      *a1 = v22;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v27) = v22;
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v23,
          0x11u,
          0x34u,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v27);
      }
      I8xManuallyRemoveDevice((__int64)DeviceContext, v23);
    }
    I8xDrainOutputBuffer(v8, *((__int64 *)&v8 + 1));
  }
  result = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  if ( (**(_DWORD **)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 2) != 0 && v28 )
  {
    LOBYTE(v17) = -88;
    LOBYTE(v16) = 3;
    v25 = I8xPutBytePolled(1, 0, v16, v17);
    if ( v25 < 0 && v12 )
    {
      *a2 = v25;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LODWORD(v27) = v25;
        WPP_RECORDER_SF_D(
          (__int64)WPP_GLOBAL_Control->DeviceExtension,
          v26,
          0x11u,
          0x35u,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v27);
      }
      I8xManuallyRemoveDevice((__int64)DeviceRoutine, v26);
    }
    result = I8xDrainOutputBuffer(v8, *((__int64 *)&v8 + 1));
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_dD(
             WPP_GLOBAL_Control->DeviceExtension,
             v15,
             15,
             54,
             (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
             *a1,
             *a2);
  return result;
}

```

## disassembly

```asm
0x14001eea0  push    rbx
0x14001eea2  push    rbp
0x14001eea3  push    rsi
0x14001eea4  push    rdi
0x14001eea5  push    r12
0x14001eea7  push    r13
0x14001eea9  push    r14
0x14001eeab  push    r15
0x14001eead  sub     rsp, 48h
0x14001eeb1  mov     r13, qword ptr cs:WPP_MAIN_CB.Queue+18h
0x14001eeb8  mov     ebx, r8d
0x14001eebb  mov     rbp, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x14001eec2  mov     r14, rdx
0x14001eec5  mov     r15, rcx
0x14001eec8  lea     r12, WPP_RECORDER_INITIALIZED
0x14001eecf  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001eed6  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001eedd  jz      short loc_14001EF00
0x14001eedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001eee6  mov     r9d, 26h ; '&'
0x14001eeec  mov     r8d, 0Fh
0x14001eef2  mov     [rsp+88h+var_68], rax
0x14001eef7  mov     rcx, [rcx+40h]
0x14001eefb  call    WPP_RECORDER_SF_
0x14001ef00  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001ef07  mov     rdi, [rax+0D0h]
0x14001ef0e  mov     rsi, [rax+0D8h]
0x14001ef15  mov     rcx, rdi
0x14001ef18  mov     rdx, rsi
0x14001ef1b  call    I8xDrainOutputBuffer
0x14001ef20  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001ef27  mov     ecx, [rax]
0x14001ef29  test    cl, 2
0x14001ef2c  jnz     short loc_14001EF5F
0x14001ef2e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ef35  jz      short loc_14001EF5F
0x14001ef37  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef3e  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001ef45  mov     r9d, 27h ; '''
0x14001ef4b  mov     [rsp+88h+var_68], rax
0x14001ef50  mov     r8d, 10h
0x14001ef56  mov     rcx, [rcx+40h]
0x14001ef5a  call    WPP_RECORDER_SF_
0x14001ef5f  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001ef66  mov     ecx, [rax]
0x14001ef68  test    cl, 1
0x14001ef6b  jnz     short loc_14001EF9E
0x14001ef6d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ef74  jz      short loc_14001EF9E
0x14001ef76  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ef7d  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001ef84  mov     r9d, 28h ; '('
0x14001ef8a  mov     [rsp+88h+var_68], rax
0x14001ef8f  mov     r8d, 10h
0x14001ef95  mov     rcx, [rcx+40h]
0x14001ef99  call    WPP_RECORDER_SF_
0x14001ef9e  test    bl, 1
0x14001efa1  jz      short loc_14001EFAE
0x14001efa3  mov     bl, 1
0x14001efa5  movzx   edx, bl
0x14001efa8  movzx   r12d, bl
0x14001efac  jmp     short loc_14001EFC7
0x14001efae  mov     r12d, ebx
0x14001efb1  shr     r12d, 10h
0x14001efb5  and     r12b, 1
0x14001efb9  bt      ebx, 11h
0x14001efbd  jnb     short loc_14001EFC3
0x14001efbf  mov     dl, 1
0x14001efc1  jmp     short loc_14001EFC5
0x14001efc3  xor     dl, dl
0x14001efc5  xor     bl, bl
0x14001efc7  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001efce  mov     [rsp+88h+arg_10], dl
0x14001efd5  mov     ecx, [rax]
0x14001efd7  test    cl, 1
0x14001efda  jz      short loc_14001F002
0x14001efdc  test    bl, bl
0x14001efde  jnz     short loc_14001F002
0x14001efe0  test    r12b, r12b
0x14001efe3  jz      short loc_14001F002
0x14001efe5  cmp     dword ptr [rbp+58h], 2
0x14001efe9  jnz     short loc_14001F002
0x14001efeb  mov     r9b, 0ADh
0x14001efee  mov     r8b, 3
0x14001eff1  xor     edx, edx
0x14001eff3  mov     cl, 1
0x14001eff5  call    I8xPutBytePolled
0x14001effa  movzx   edx, [rsp+88h+arg_10]
0x14001f002  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001f009  mov     ecx, [rax]
0x14001f00b  test    cl, 2
0x14001f00e  jz      short loc_14001F02E
0x14001f010  test    bl, bl
0x14001f012  jnz     short loc_14001F02E
0x14001f014  test    dl, dl
0x14001f016  jz      short loc_14001F02E
0x14001f018  cmp     dword ptr [r13+58h], 2
0x14001f01d  jnz     short loc_14001F02E
0x14001f01f  mov     r9b, 0A7h
0x14001f022  mov     r8b, 3
0x14001f025  xor     edx, edx
0x14001f027  mov     cl, 1
0x14001f029  call    I8xPutBytePolled
0x14001f02e  mov     rdx, rsi
0x14001f031  mov     rcx, rdi
0x14001f034  call    I8xDrainOutputBuffer
0x14001f039  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001f040  mov     ecx, [rax]
0x14001f042  test    cl, 1
0x14001f045  jz      loc_14001F157
0x14001f04b  test    r12b, r12b
0x14001f04e  jz      loc_14001F157
0x14001f054  mov     rcx, rbp
0x14001f057  call    I8xInitializeKeyboard
0x14001f05c  mov     [r15], eax
0x14001f05f  test    eax, eax
0x14001f061  jns     loc_14001F15E
0x14001f067  cmp     eax, 0C000009Dh
0x14001f06c  jz      short loc_14001F0B7
0x14001f06e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001f075  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001f07c  jz      short loc_14001F0AA
0x14001f07e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f085  mov     r9d, 2Dh ; '-'
0x14001f08b  mov     dword ptr [rsp+88h+var_60], eax
0x14001f08f  mov     r8d, 11h
0x14001f095  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f09c  mov     [rsp+88h+var_68], rax
0x14001f0a1  mov     rcx, [rcx+40h]
0x14001f0a5  call    WPP_RECORDER_SF_D
0x14001f0aa  mov     rcx, rbp
0x14001f0ad  call    I8xManuallyRemoveDevice
0x14001f0b2  jmp     loc_14001F15E
0x14001f0b7  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 0
0x14001f0be  jnz     short loc_14001F102
0x14001f0c0  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f0c7  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f0ce  jz      short loc_14001F0F8
0x14001f0d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f0d7  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f0de  mov     r9d, 2Bh ; '+'
0x14001f0e4  mov     [rsp+88h+var_68], rax
0x14001f0e9  mov     r8d, 10h
0x14001f0ef  mov     rcx, [rcx+40h]
0x14001f0f3  call    WPP_RECORDER_SF_
0x14001f0f8  mov     rcx, rbp
0x14001f0fb  call    I8xManuallyRemoveDevice
0x14001f100  jmp     short loc_14001F15E
0x14001f102  test    bl, bl
0x14001f104  jz      short loc_14001F15E
0x14001f106  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f10d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f114  jz      short loc_14001F13E
0x14001f116  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f11d  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f124  mov     r9d, 2Ch ; ','
0x14001f12a  mov     [rsp+88h+var_68], rax
0x14001f12f  mov     r8d, 10h
0x14001f135  mov     rcx, [rcx+40h]
0x14001f139  call    WPP_RECORDER_SF_
0x14001f13e  or      dword ptr [rbp+22Ch], 2
0x14001f145  mov     rcx, [rbp+20h]; PhysicalDeviceObject
0x14001f149  call    cs:__imp_IoInvalidateDeviceState
0x14001f150  nop     dword ptr [rax+rax+00h]
0x14001f155  jmp     short loc_14001F15E
0x14001f157  mov     dword ptr [r15], 0C000000Eh
0x14001f15e  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001f165  mov     ecx, [rax]
0x14001f167  test    cl, 2
0x14001f16a  jz      loc_14001F286
0x14001f170  cmp     [rsp+88h+arg_10], 0
0x14001f178  jz      loc_14001F286
0x14001f17e  mov     rcx, r13
0x14001f181  call    I8xInitializeMouse
0x14001f186  mov     [r14], eax
0x14001f189  test    eax, eax
0x14001f18b  jns     loc_14001F28D
0x14001f191  test    bl, bl
0x14001f193  jz      loc_14001F28D
0x14001f199  cmp     eax, 0C000009Dh
0x14001f19e  jz      short loc_14001F1E9
0x14001f1a0  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001f1a7  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001f1ae  jz      short loc_14001F1DC
0x14001f1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f1b7  mov     r9d, 30h ; '0'
0x14001f1bd  mov     dword ptr [rsp+88h+var_60], eax
0x14001f1c1  mov     r8d, 11h
0x14001f1c7  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f1ce  mov     [rsp+88h+var_68], rax
0x14001f1d3  mov     rcx, [rcx+40h]
0x14001f1d7  call    WPP_RECORDER_SF_D
0x14001f1dc  mov     rcx, r13
0x14001f1df  call    I8xManuallyRemoveDevice
0x14001f1e4  jmp     loc_14001F28D
0x14001f1e9  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 0
0x14001f1f0  jnz     short loc_14001F234
0x14001f1f2  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f1f9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f200  jz      short loc_14001F22A
0x14001f202  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f209  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f210  mov     r9d, 2Eh ; '.'
0x14001f216  mov     [rsp+88h+var_68], rax
0x14001f21b  mov     r8d, 10h
0x14001f221  mov     rcx, [rcx+40h]
0x14001f225  call    WPP_RECORDER_SF_
0x14001f22a  mov     rcx, r13
0x14001f22d  call    I8xManuallyRemoveDevice
0x14001f232  jmp     short loc_14001F28D
0x14001f234  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f23b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f242  jz      short loc_14001F26C
0x14001f244  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f24b  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f252  mov     r9d, 2Fh ; '/'
0x14001f258  mov     [rsp+88h+var_68], rax
0x14001f25d  mov     r8d, 10h
0x14001f263  mov     rcx, [rcx+40h]
0x14001f267  call    WPP_RECORDER_SF_
0x14001f26c  or      dword ptr [r13+22Ch], 2
0x14001f274  mov     rcx, [r13+20h]; PhysicalDeviceObject
0x14001f278  call    cs:__imp_IoInvalidateDeviceState
0x14001f27f  nop     dword ptr [rax+rax+00h]
0x14001f284  jmp     short loc_14001F28D
0x14001f286  mov     dword ptr [r14], 0C000000Eh
0x14001f28d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001f294  mov     ecx, [rax]
0x14001f296  test    cl, 1
0x14001f299  jz      loc_14001F36D
0x14001f29f  cmp     dword ptr [r15], 0
0x14001f2a3  jl      loc_14001F36D
0x14001f2a9  test    r12b, r12b
0x14001f2ac  jz      loc_14001F36D
0x14001f2b2  lea     rax, WPP_RECORDER_INITIALIZED
0x14001f2b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14001f2c0  jz      short loc_14001F2EA
0x14001f2c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f2c9  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f2d0  mov     r9d, 31h ; '1'
0x14001f2d6  mov     [rsp+88h+var_68], rax
0x14001f2db  mov     r8d, 10h
0x14001f2e1  mov     rcx, [rcx+40h]
0x14001f2e5  call    WPP_RECORDER_SF_
0x14001f2ea  mov     r8b, 1
0x14001f2ed  mov     r9b, 0EDh
0x14001f2f0  movzx   edx, r8b
0x14001f2f4  xor     ecx, ecx
0x14001f2f6  call    I8xPutBytePolled
0x14001f2fb  test    eax, eax
0x14001f2fd  jnz     short loc_14001F331
0x14001f2ff  movzx   r9d, byte ptr [rbp+2DCh]
0x14001f307  mov     r8b, 1
0x14001f30a  movzx   edx, r8b
0x14001f30e  xor     ecx, ecx
0x14001f310  call    I8xPutBytePolled
0x14001f315  test    eax, eax
0x14001f317  jz      short loc_14001F36D
0x14001f319  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001f320  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001f327  jz      short loc_14001F36D
0x14001f329  mov     r9d, 32h ; '2'
0x14001f32f  jmp     short loc_14001F347
0x14001f331  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001f338  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001f33f  jz      short loc_14001F36D
0x14001f341  mov     r9d, 33h ; '3'
0x14001f347  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f34e  mov     r8d, 10h
0x14001f354  mov     dword ptr [rsp+88h+var_60], eax
0x14001f358  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f35f  mov     [rsp+88h+var_68], rax
0x14001f364  mov     rcx, [rcx+40h]
0x14001f368  call    WPP_RECORDER_SF_D
0x14001f36d  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14001f374  mov     ecx, [rax]
0x14001f376  test    cl, 1
0x14001f379  jz      short loc_14001F3F4
0x14001f37b  test    r12b, r12b
0x14001f37e  jz      short loc_14001F3F4
0x14001f380  mov     r9b, 0AEh
0x14001f383  mov     r8b, 3
0x14001f386  xor     edx, edx
0x14001f388  mov     cl, 1
0x14001f38a  call    I8xPutBytePolled
0x14001f38f  test    eax, eax
0x14001f391  jns     short loc_14001F3E0
0x14001f393  test    bl, bl
0x14001f395  jz      short loc_14001F3E0
0x14001f397  mov     [r15], eax
0x14001f39a  lea     r12, WPP_RECORDER_INITIALIZED
0x14001f3a1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001f3a8  jz      short loc_14001F3D6
0x14001f3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f3b1  mov     r9d, 34h ; '4'
0x14001f3b7  mov     dword ptr [rsp+88h+var_60], eax
0x14001f3bb  mov     r8d, 11h
0x14001f3c1  lea     rax, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x14001f3c8  mov     [rsp+88h+var_68], rax
0x14001f3cd  mov     rcx, [rcx+40h]
  ... truncated ...
```
