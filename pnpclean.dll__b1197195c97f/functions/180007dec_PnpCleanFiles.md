# PnpCleanFiles

- ea: `0x180007dec`
- end: `0x180007f3f`
- name: `PnpCleanFiles`
- size: `339`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 (__fastcall *)(), __int64, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180001cd4`
- `0x180002fc0`
- `0x1800034b0`
- `0x180003d70`

## callees

- `0x180007dec`
- `0x180007f48`
- `0x18000829c`
- `0x18000880c`
- `0x180008dfe`
- `0x18000a010`

## string_xrefs

- `0x180007e2e`: `Searching for files/directories that may be removed from the system.`
- `0x180007e5f`: `Files %ws be removed during this pass.`

## pseudocode

```c
__int64 __fastcall PnpCleanFiles(__int64 a1, __int64 a2, __int64 (__fastcall *a3)(), __int64 a4, int a5)
{
  unsigned int v8; // ebx
  __int64 (__fastcall *v9)(); // rsi
  const wchar_t *v10; // rax
  int SystemDriveClusterSize; // eax
  int v12; // edx
  unsigned int v13; // eax
  __int64 v15; // [rsp+20h] [rbp-51h]
  _BYTE v16[24]; // [rsp+30h] [rbp-41h] BYREF
  __int64 v17; // [rsp+48h] [rbp-29h]
  __int64 v18; // [rsp+50h] [rbp-21h]
  __int64 (__fastcall *v19)(); // [rsp+58h] [rbp-19h]
  __int64 v20; // [rsp+60h] [rbp-11h]
  BOOL v21; // [rsp+68h] [rbp-9h]
  int v22; // [rsp+6Ch] [rbp-5h]
  int v23; // [rsp+70h] [rbp-1h]
  _DWORD v24[16]; // [rsp+80h] [rbp+Fh] BYREF

  if ( (a5 & 0xFFFFFFFC) != 0 )
  {
    return 87;
  }
  else
  {
    v9 = guard_check_icall_nop;
    if ( a3 )
      v9 = a3;
    ((void (__fastcall *)(__int64, __int64, __int64, const char *))v9)(
      a4,
      3,
      1,
      "Searching for files/directories that may be removed from the system.");
    v10 = L"will";
    if ( (a5 & 1) != 0 )
      v10 = L"will NOT";
    ((void (*)(__int64, __int64, _QWORD, const char *, ...))v9)(a4, 3, 0, "Files %ws be removed during this pass.", v10);
    memset_0(v16, 0, 0x58u);
    v17 = a1;
    v18 = a2;
    v19 = v9;
    v20 = a4;
    v21 = (a5 & 1) == 0;
    v23 = 0;
    SystemDriveClusterSize = pUtilGetSystemDriveClusterSize(v24);
    v12 = v24[0];
    v22 = 0;
    if ( SystemDriveClusterSize )
      v12 = 0;
    v24[0] = v12;
    if ( (unsigned int)PnpCleanFilesNotifyCallback(v16)
      && (v22 = ((a5 & 1) == 0) + 2, (unsigned int)PnpCleanFilesNotifyCallback(v16)) )
    {
      v13 = ProcessDeviceDirectoriesToRemove(v16);
      v8 = v13;
      if ( v13 )
      {
        LODWORD(v15) = v13;
        ((void (*)(__int64, __int64, __int64, const char *, ...))v9)(
          a4,
          1,
          1,
          "Failed to process device directories for removal, Err = 0x%lx",
          v15);
      }
      else
      {
        v22 = 4;
        PnpCleanFilesNotifyCallback(v16);
      }
    }
    else
    {
      return 1223;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180007dec  push    rbp
0x180007dee  push    rbx
0x180007def  push    rsi
0x180007df0  push    rdi
0x180007df1  push    r14
0x180007df3  push    r15
0x180007df5  lea     rbp, [rsp-27h]
0x180007dfa  sub     rsp, 98h
0x180007e01  mov     ebx, [rbp+4Fh+arg_20]
0x180007e04  mov     rdi, r9
0x180007e07  mov     r14, rdx
0x180007e0a  mov     r15, rcx
0x180007e0d  test    ebx, 0FFFFFFFCh
0x180007e13  jz      short loc_180007E1F
0x180007e15  mov     ebx, 57h ; 'W'
0x180007e1a  jmp     loc_180007F2D
0x180007e1f  test    r8, r8
0x180007e22  lea     rsi, _guard_check_icall_nop
0x180007e29  mov     edx, 3
0x180007e2e  lea     r9, aSearchingForFi; "Searching for files/directories that ma"...
0x180007e35  cmovnz  rsi, r8
0x180007e39  mov     rcx, rdi
0x180007e3c  mov     rax, rsi
0x180007e3f  not     ebx
0x180007e41  lea     r8d, [rdx-2]
0x180007e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4a  lea     rcx, aWillNot; "will NOT"
0x180007e51  and     ebx, 1
0x180007e54  lea     rax, aWill; "will"
0x180007e5b  cmovz   rax, rcx
0x180007e5f  lea     r9, aFilesWsBeRemov; "Files %ws be removed during this pass."
0x180007e66  xor     r8d, r8d
0x180007e69  mov     [rsp+0C0h+var_A0], rax
0x180007e6e  mov     rcx, rdi
0x180007e71  mov     rax, rsi
0x180007e74  lea     edx, [r8+3]
0x180007e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7d  xor     edx, edx; Val
0x180007e7f  lea     rcx, [rbp+4Fh+var_90]; void *
0x180007e83  lea     r8d, [rdx+58h]; Size
0x180007e87  call    memset_0
0x180007e8c  lea     rcx, [rbp+4Fh+var_40]
0x180007e90  mov     [rbp+4Fh+var_78], r15
0x180007e94  mov     [rbp+4Fh+var_70], r14
0x180007e98  mov     [rbp+4Fh+var_68], rsi
0x180007e9c  mov     [rbp+4Fh+var_60], rdi
0x180007ea0  mov     [rbp+4Fh+var_58], ebx
0x180007ea3  mov     [rbp+4Fh+var_50], 0
0x180007eaa  call    pUtilGetSystemDriveClusterSize
0x180007eaf  mov     edx, [rbp+4Fh+var_40]
0x180007eb2  mov     ecx, eax
0x180007eb4  xor     eax, eax
0x180007eb6  test    ecx, ecx
0x180007eb8  mov     [rbp+4Fh+var_54], eax
0x180007ebb  lea     rcx, [rbp+4Fh+var_90]
0x180007ebf  cmovnz  edx, eax
0x180007ec2  mov     [rbp+4Fh+var_40], edx
0x180007ec5  call    PnpCleanFilesNotifyCallback
0x180007eca  test    eax, eax
0x180007ecc  jnz     short loc_180007ED5
0x180007ece  mov     ebx, 4C7h
0x180007ed3  jmp     short loc_180007F2D
0x180007ed5  neg     ebx
0x180007ed7  lea     rcx, [rbp+4Fh+var_90]
0x180007edb  sbb     eax, eax
0x180007edd  neg     eax
0x180007edf  add     eax, 2
0x180007ee2  mov     [rbp+4Fh+var_54], eax
0x180007ee5  call    PnpCleanFilesNotifyCallback
0x180007eea  test    eax, eax
0x180007eec  jz      short loc_180007ECE
0x180007eee  lea     rcx, [rbp+4Fh+var_90]
0x180007ef2  call    ProcessDeviceDirectoriesToRemove
0x180007ef7  mov     ebx, eax
0x180007ef9  test    eax, eax
0x180007efb  jz      short loc_180007F1D
0x180007efd  mov     edx, 1
0x180007f02  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180007f06  mov     r8d, edx
0x180007f09  lea     r9, aFailedToProces_0; "Failed to process device directories fo"...
0x180007f10  mov     rcx, rdi
0x180007f13  mov     rax, rsi
0x180007f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f1b  jmp     short loc_180007F2D
0x180007f1d  lea     rcx, [rbp+4Fh+var_90]
0x180007f21  mov     [rbp+4Fh+var_54], 4
0x180007f28  call    PnpCleanFilesNotifyCallback
0x180007f2d  mov     eax, ebx
0x180007f2f  add     rsp, 98h
0x180007f36  pop     r15
0x180007f38  pop     r14
0x180007f3a  pop     rdi
0x180007f3b  pop     rsi
0x180007f3c  pop     rbx
0x180007f3d  pop     rbp
0x180007f3e  retn
```
