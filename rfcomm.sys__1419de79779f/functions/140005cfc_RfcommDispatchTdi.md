# RfcommDispatchTdi

- ea: `0x140005cfc`
- end: `0x140005f24`
- name: `RfcommDispatchTdi`
- size: `552`
- prototype: `__int64 __fastcall(__int64, IRP *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140001ec0`

## callees

- `0x140001eec`
- `0x140004550`
- `0x140004c5c`
- `0x140005c38`
- `0x140005cfc`
- `0x140006750`
- `0x140007d40`
- `0x140008cdc`
- `0x14000bd80`
- `0x140033a70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005dec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e8b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005dec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e8b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ea8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ecb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e09`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e25`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ea8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ecb`

## pseudocode

```c
__int64 __fastcall RfcommDispatchTdi(__int64 a1, IRP *a2, int a3)
{
  __int64 v3; // rsi
  char *CurrentStackLocation; // r14
  unsigned int v7; // ebx
  unsigned int v8; // eax
  KIRQL v9; // al
  bool v10; // zf
  KSPIN_LOCK *v11; // rcx
  int v12; // edx
  int v13; // r8d
  KIRQL v14; // al
  KSPIN_LOCK *v15; // rcx
  int v16; // edx
  int v17; // r8d
  int v19; // [rsp+20h] [rbp-58h]
  __int64 v20; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = (char *)a2->Tail.Overlay.CurrentStackLocation;
  v20 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_cqq(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      15,
      157,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      *CurrentStackLocation,
      a1,
      (char)a2);
  switch ( *CurrentStackLocation )
  {
    case 0:
      v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 48));
      v10 = *(_BYTE *)(v3 + 128) == 0;
      v15 = (KSPIN_LOCK *)(v3 + 48);
      *(_BYTE *)(v3 + 56) = v14;
      if ( !v10 )
      {
        KeReleaseSpinLock(v15, v14);
        v7 = -1073741667;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_cd(WPP_GLOBAL_Control->DeviceExtension, v16, v17, 158, v19, *CurrentStackLocation);
        goto LABEL_27;
      }
      KeReleaseSpinLock(v15, v14);
      v8 = TdiCreate(a1, a2);
      goto LABEL_22;
    case 2:
      v8 = TdiClose((unsigned int)(unsigned __int8)*CurrentStackLocation - 2, a2);
      goto LABEL_22;
    case 14:
      v8 = RfcommDispatchDeviceControl(a1, a2, CurrentStackLocation, &v20);
      goto LABEL_22;
  }
  if ( *CurrentStackLocation != 15 )
  {
    if ( *CurrentStackLocation != 18 )
    {
      if ( *CurrentStackLocation != 22
        && *CurrentStackLocation != 27
        && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_qc(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned __int8)*CurrentStackLocation,
          a3,
          160,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
          (char)a2,
          *CurrentStackLocation);
      }
      v7 = -1073741808;
      goto LABEL_27;
    }
    v8 = TdiCleanup(a1, a2);
    goto LABEL_22;
  }
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 48));
  v10 = *(_BYTE *)(v3 + 128) == 0;
  v11 = (KSPIN_LOCK *)(v3 + 48);
  *(_BYTE *)(v3 + 56) = v9;
  if ( v10 )
  {
    KeReleaseSpinLock(v11, v9);
    v8 = TdiDispatchInternal(a1, a2);
LABEL_22:
    v7 = v8;
    goto LABEL_23;
  }
  KeReleaseSpinLock(v11, v9);
  v7 = -1073741667;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
LABEL_27:
    RfcommCompleteTdiIrp(a2);
    return v7;
  }
  WPP_RECORDER_SF_cd(WPP_GLOBAL_Control->DeviceExtension, v12, v13, 159, v19, *CurrentStackLocation);
LABEL_23:
  if ( v7 != 259 )
    goto LABEL_27;
  return v7;
}

```

## disassembly

```asm
0x140005cfc  mov     r11, rsp
0x140005cff  push    rbx
0x140005d00  push    rbp
0x140005d01  push    rsi
0x140005d02  push    rdi
0x140005d03  push    r12
0x140005d05  push    r14
0x140005d07  sub     rsp, 48h
0x140005d0b  mov     rsi, [rcx+40h]
0x140005d0f  mov     rdi, rdx
0x140005d12  mov     r14, [rdx+0B8h]
0x140005d19  mov     rbx, rcx
0x140005d1c  mov     qword ptr [r11+8], 0
0x140005d24  lea     r12, WPP_RECORDER_INITIALIZED
0x140005d2b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005d32  lea     rbp, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140005d39  jz      short loc_140005D6A
0x140005d3b  mov     al, [r14]
0x140005d3e  mov     r9d, 9Dh
0x140005d44  mov     [r11-40h], rdx
0x140005d48  mov     r8d, 0Fh
0x140005d4e  mov     [r11-48h], rcx
0x140005d52  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d59  mov     byte ptr [rsp+78h+var_50], al
0x140005d5d  mov     [r11-58h], rbp
0x140005d61  mov     rcx, [rcx+40h]
0x140005d65  call    WPP_RECORDER_SF_cqq
0x140005d6a  movzx   edx, byte ptr [r14]
0x140005d6e  mov     ecx, edx
0x140005d70  test    edx, edx
0x140005d72  jz      loc_140005E84
0x140005d78  sub     ecx, 2
0x140005d7b  jz      loc_140005E7A
0x140005d81  sub     ecx, 0Ch
0x140005d84  jz      loc_140005E62
0x140005d8a  sub     ecx, 1
0x140005d8d  jz      short loc_140005DE5
0x140005d8f  sub     ecx, 3
0x140005d92  jz      short loc_140005DD5
0x140005d94  sub     ecx, 4
0x140005d97  jz      short loc_140005DCB
0x140005d99  cmp     ecx, 5
0x140005d9c  jz      short loc_140005DCB
0x140005d9e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005da5  jz      short loc_140005DCB
0x140005da7  mov     rcx, cs:WPP_GLOBAL_Control
0x140005dae  mov     r9d, 0A0h
0x140005db4  mov     [rsp+78h+var_48], dl
0x140005db8  mov     [rsp+78h+var_50], rdi
0x140005dbd  mov     [rsp+78h+var_58], rbp
0x140005dc2  mov     rcx, [rcx+40h]
0x140005dc6  call    WPP_RECORDER_SF_qc
0x140005dcb  mov     ebx, 0C0000010h
0x140005dd0  jmp     loc_140005F02
0x140005dd5  mov     rdx, rdi
0x140005dd8  mov     rcx, rbx
0x140005ddb  call    TdiCleanup
0x140005de0  jmp     loc_140005EBF
0x140005de5  lea     rbp, [rsi+30h]
0x140005de9  mov     rcx, rbp; SpinLock
0x140005dec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005df3  nop     dword ptr [rax+rax+00h]
0x140005df8  cmp     byte ptr [rsi+80h], 0
0x140005dff  mov     rcx, rbp; SpinLock
0x140005e02  mov     [rsi+38h], al
0x140005e05  mov     dl, al; NewIrql
0x140005e07  jnz     short loc_140005E25
0x140005e09  call    cs:__imp_KeReleaseSpinLock
0x140005e10  nop     dword ptr [rax+rax+00h]
0x140005e15  mov     rdx, rdi
0x140005e18  mov     rcx, rbx
0x140005e1b  call    TdiDispatchInternal
0x140005e20  jmp     loc_140005EBF
0x140005e25  call    cs:__imp_KeReleaseSpinLock
0x140005e2c  nop     dword ptr [rax+rax+00h]
0x140005e31  mov     ebx, 0C000009Dh
0x140005e36  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005e3d  jz      loc_140005F02
0x140005e43  mov     rcx, cs:WPP_GLOBAL_Control
0x140005e4a  mov     r9d, 9Fh
0x140005e50  mov     al, [r14]
0x140005e53  mov     byte ptr [rsp+78h+var_50], al
0x140005e57  mov     rcx, [rcx+40h]
0x140005e5b  call    WPP_RECORDER_SF_cd
0x140005e60  jmp     short loc_140005EC1
0x140005e62  lea     r9, [rsp+78h+arg_0]
0x140005e6a  mov     r8, r14
0x140005e6d  mov     rdx, rdi
0x140005e70  mov     rcx, rbx
0x140005e73  call    RfcommDispatchDeviceControl
0x140005e78  jmp     short loc_140005EBF
0x140005e7a  mov     rdx, rdi
0x140005e7d  call    TdiClose
0x140005e82  jmp     short loc_140005EBF
0x140005e84  lea     rbp, [rsi+30h]
0x140005e88  mov     rcx, rbp; SpinLock
0x140005e8b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005e92  nop     dword ptr [rax+rax+00h]
0x140005e97  cmp     byte ptr [rsi+80h], 0
0x140005e9e  mov     rcx, rbp; SpinLock
0x140005ea1  mov     [rsi+38h], al
0x140005ea4  mov     dl, al; NewIrql
0x140005ea6  jnz     short loc_140005ECB
0x140005ea8  call    cs:__imp_KeReleaseSpinLock
0x140005eaf  nop     dword ptr [rax+rax+00h]
0x140005eb4  mov     rdx, rdi
0x140005eb7  mov     rcx, rbx
0x140005eba  call    TdiCreate
0x140005ebf  mov     ebx, eax
0x140005ec1  cmp     ebx, 103h
0x140005ec7  jz      short loc_140005F14
0x140005ec9  jmp     short loc_140005F02
0x140005ecb  call    cs:__imp_KeReleaseSpinLock
0x140005ed2  nop     dword ptr [rax+rax+00h]
0x140005ed7  mov     ebx, 0C000009Dh
0x140005edc  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140005ee3  jz      short loc_140005F02
0x140005ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005eec  mov     r9d, 9Eh
0x140005ef2  mov     al, [r14]
0x140005ef5  mov     byte ptr [rsp+78h+var_50], al
0x140005ef9  mov     rcx, [rcx+40h]
0x140005efd  call    WPP_RECORDER_SF_cd
0x140005f02  mov     r8, [rsp+78h+arg_0]
0x140005f0a  mov     edx, ebx
0x140005f0c  mov     rcx, rdi; Irp
0x140005f0f  call    RfcommCompleteTdiIrp
0x140005f14  mov     eax, ebx
0x140005f16  add     rsp, 48h
0x140005f1a  pop     r14
0x140005f1c  pop     r12
0x140005f1e  pop     rdi
0x140005f1f  pop     rsi
0x140005f20  pop     rbp
0x140005f21  pop     rbx
0x140005f22  retn
```
