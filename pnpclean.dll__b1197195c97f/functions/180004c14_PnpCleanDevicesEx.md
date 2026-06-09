# PnpCleanDevicesEx

- ea: `0x180004c14`
- end: `0x180004e06`
- name: `PnpCleanDevicesEx`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 (__fastcall *)(), __int64, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001cd4`
- `0x1800034b0`

## callees

- `0x180004690`
- `0x180004c14`
- `0x180004e0c`
- `0x180004e74`
- `0x180008dfe`
- `0x18000a010`

## string_xrefs

- `0x180004c66`: `Searching for not-recently detected devices that may be removed from the system.`
- `0x180004ca2`: `Devices %ws be removed during this pass.`
- `0x180004db7`: `removed`
- `0x180004dac`: `to remove`

## pseudocode

```c
__int64 __fastcall PnpCleanDevicesEx(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 (__fastcall *a5)(),
        __int64 a6,
        int a7)
{
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(); // rdi
  const wchar_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int CurrentConfiguration; // eax
  int v15; // ecx
  unsigned int v16; // eax
  const wchar_t *v17; // r8
  __int64 v19; // [rsp+20h] [rbp-61h]
  _QWORD v20[3]; // [rsp+40h] [rbp-41h] BYREF
  _QWORD v21[5]; // [rsp+58h] [rbp-29h] BYREF
  __int64 v22; // [rsp+80h] [rbp-1h]
  int v23; // [rsp+88h] [rbp+7h]
  int v24; // [rsp+8Ch] [rbp+Bh]

  memset_0(v20, 0, 0x50u);
  if ( (a7 & 0xFFFFFFFC) != 0 )
  {
    return 87;
  }
  else
  {
    v10 = guard_check_icall_nop;
    if ( a5 )
      v10 = a5;
    ((void (__fastcall *)(__int64, __int64, __int64, const char *))v10)(
      a6,
      3,
      1,
      "Searching for not-recently detected devices that may be removed from the system.");
    v11 = L"will";
    if ( (a7 & 1) != 0 )
      v11 = L"will NOT";
    ((void (*)(__int64, __int64, _QWORD, const char *, ...))v10)(
      a6,
      3,
      0,
      "Devices %ws be removed during this pass.",
      v11);
    v21[0] = 0;
    v23 = 0;
    memset(v20, 0, sizeof(v20));
    v21[1] = a3;
    v24 = (a7 & 2) == 0 ? 0x1E : 0;
    v21[2] = a4;
    v21[3] = v10;
    v21[4] = a6;
    v22 = (a7 & 1) == 0;
    CurrentConfiguration = HwCfgGetCurrentConfiguration(v13, v12, (BYTE *)v21);
    v15 = v21[0];
    HIDWORD(v22) = 0;
    if ( CurrentConfiguration )
      v15 = -1;
    LODWORD(v21[0]) = v15;
    if ( (unsigned int)PnpCleanDevicesNotifyCallback(v20)
      && (HIDWORD(v22) = ((a7 & 1) == 0) + 2, (unsigned int)PnpCleanDevicesNotifyCallback(v20)) )
    {
      ((void (__fastcall *)(__int64, __int64, __int64, const char *))v10)(a6, 4, 1, "Processing devices...");
      v16 = ProcessDevicesToRemove(v20);
      v9 = v16;
      if ( v16 )
      {
        LODWORD(v19) = v16;
        ((void (*)(__int64, __int64, __int64, const char *, ...))v10)(
          a6,
          1,
          1,
          "Failed to process devices for removal, Err = 0x%lx",
          v19);
      }
      else
      {
        v17 = L"removed";
        if ( !(_DWORD)v22 )
          v17 = L"to remove";
        ((void (__fastcall *)(__int64, __int64, __int64, const char *, const wchar_t *, int))v10)(
          a6,
          3,
          1,
          "Devices %ws: %d",
          v17,
          v23);
        HIDWORD(v22) = 4;
        PnpCleanDevicesNotifyCallback(v20);
      }
    }
    else
    {
      return 1223;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180004c14  push    rbp
0x180004c16  push    rbx
0x180004c17  push    rsi
0x180004c18  push    rdi
0x180004c19  push    r12
0x180004c1b  push    r14
0x180004c1d  push    r15
0x180004c1f  lea     rbp, [rsp-0Fh]
0x180004c24  sub     rsp, 90h
0x180004c2b  xor     edx, edx; Val
0x180004c2d  lea     rcx, [rbp+3Fh+var_80]; void *
0x180004c31  mov     r12, r8
0x180004c34  mov     r15, r9
0x180004c37  lea     r8d, [rdx+50h]; Size
0x180004c3b  call    memset_0
0x180004c40  mov     r14d, [rbp+3Fh+arg_30]
0x180004c44  test    r14d, 0FFFFFFFCh
0x180004c4b  jz      short loc_180004C57
0x180004c4d  mov     ebx, 57h ; 'W'
0x180004c52  jmp     loc_180004DF2
0x180004c57  mov     rax, [rbp+3Fh+arg_20]
0x180004c5b  lea     rdi, _guard_check_icall_nop
0x180004c62  mov     rsi, [rbp+3Fh+arg_28]
0x180004c66  lea     r9, aSearchingForNo; "Searching for not-recently detected dev"...
0x180004c6d  test    rax, rax
0x180004c70  mov     edx, 3
0x180004c75  mov     ebx, r14d
0x180004c78  mov     rcx, rsi
0x180004c7b  cmovnz  rdi, rax
0x180004c7f  not     ebx
0x180004c81  mov     rax, rdi
0x180004c84  lea     r8d, [rdx-2]
0x180004c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c8d  lea     rcx, aWillNot; "will NOT"
0x180004c94  and     ebx, 1
0x180004c97  lea     rax, aWill; "will"
0x180004c9e  cmovz   rax, rcx
0x180004ca2  lea     r9, aDevicesWsBeRem; "Devices %ws be removed during this pass"...
0x180004ca9  xor     r8d, r8d
0x180004cac  mov     [rsp+0C0h+var_A0], rax
0x180004cb1  mov     rcx, rsi
0x180004cb4  mov     rax, rdi
0x180004cb7  lea     edx, [r8+3]
0x180004cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc0  and     r14b, 2
0x180004cc4  mov     [rbp+3Fh+var_68], 0
0x180004ccc  neg     r14b
0x180004ccf  mov     [rbp+3Fh+var_3C], 0
0x180004cd7  lea     r8, [rbp+3Fh+var_68]
0x180004cdb  mov     [rbp+3Fh+var_80], 0
0x180004ce3  sbb     eax, eax
0x180004ce5  mov     [rbp+3Fh+var_78], 0
0x180004ced  not     eax
0x180004cef  mov     [rbp+3Fh+var_70], 0
0x180004cf7  and     eax, 1Eh
0x180004cfa  mov     [rbp+3Fh+var_60], r12
0x180004cfe  mov     [rbp+3Fh+var_34], eax
0x180004d01  mov     [rbp+3Fh+var_58], r15
0x180004d05  mov     [rbp+3Fh+var_50], rdi
0x180004d09  mov     [rbp+3Fh+var_48], rsi
0x180004d0d  mov     [rbp+3Fh+var_40], ebx
0x180004d10  call    HwCfgGetCurrentConfiguration
0x180004d15  mov     ecx, dword ptr [rbp+3Fh+var_68]
0x180004d18  or      edx, 0FFFFFFFFh
0x180004d1b  test    eax, eax
0x180004d1d  mov     dword ptr [rbp+3Fh+var_3C], 0
0x180004d24  cmovnz  ecx, edx
0x180004d27  mov     dword ptr [rbp+3Fh+var_68], ecx
0x180004d2a  lea     rcx, [rbp+3Fh+var_80]
0x180004d2e  call    PnpCleanDevicesNotifyCallback
0x180004d33  test    eax, eax
0x180004d35  jnz     short loc_180004D41
0x180004d37  mov     ebx, 4C7h
0x180004d3c  jmp     loc_180004DF2
0x180004d41  neg     ebx
0x180004d43  lea     rcx, [rbp+3Fh+var_80]
0x180004d47  sbb     eax, eax
0x180004d49  neg     eax
0x180004d4b  add     eax, 2
0x180004d4e  mov     dword ptr [rbp+3Fh+var_3C], eax
0x180004d51  call    PnpCleanDevicesNotifyCallback
0x180004d56  test    eax, eax
0x180004d58  jz      short loc_180004D37
0x180004d5a  mov     r14d, 1
0x180004d60  lea     r9, aProcessingDevi_0; "Processing devices..."
0x180004d67  mov     r8d, r14d
0x180004d6a  mov     rcx, rsi
0x180004d6d  mov     rax, rdi
0x180004d70  lea     r15d, [r14+3]
0x180004d74  mov     edx, r15d
0x180004d77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d7c  lea     rcx, [rbp+3Fh+var_80]
0x180004d80  call    ProcessDevicesToRemove
0x180004d85  mov     ebx, eax
0x180004d87  test    eax, eax
0x180004d89  jz      short loc_180004DA9
0x180004d8b  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180004d8f  lea     r9, aFailedToProces; "Failed to process devices for removal, "...
0x180004d96  mov     rax, rdi
0x180004d99  mov     r8d, r14d
0x180004d9c  mov     edx, r14d
0x180004d9f  mov     rcx, rsi
0x180004da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da7  jmp     short loc_180004DF2
0x180004da9  mov     ecx, dword ptr [rbp+3Fh+var_3C+4]
0x180004dac  lea     rax, aToRemove; "to remove"
0x180004db3  cmp     [rbp+3Fh+var_40], 0
0x180004db7  lea     r8, aRemoved; "removed"
0x180004dbe  mov     [rsp+0C0h+var_98], ecx
0x180004dc2  lea     r9, aDevicesWsD; "Devices %ws: %d"
0x180004dc9  cmovz   r8, rax
0x180004dcd  mov     edx, 3
0x180004dd2  mov     [rsp+0C0h+var_A0], r8
0x180004dd7  mov     rcx, rsi
0x180004dda  mov     r8d, r14d
0x180004ddd  mov     rax, rdi
0x180004de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de5  lea     rcx, [rbp+3Fh+var_80]
0x180004de9  mov     dword ptr [rbp+3Fh+var_3C], r15d
0x180004ded  call    PnpCleanDevicesNotifyCallback
0x180004df2  mov     eax, ebx
0x180004df4  add     rsp, 90h
0x180004dfb  pop     r15
0x180004dfd  pop     r14
0x180004dff  pop     r12
0x180004e01  pop     rdi
0x180004e02  pop     rsi
0x180004e03  pop     rbx
0x180004e04  pop     rbp
0x180004e05  retn
```
