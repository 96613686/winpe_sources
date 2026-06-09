# HsmpFileCachePreparePinWrite

- ea: `0x140005e84`
- end: `0x14000616a`
- name: `HsmpFileCachePreparePinWrite`
- size: `742`
- prototype: `__int64 __usercall@<rax>(PFILE_OBJECT FileObject@<rcx>, int, PVOID *, PVOID *, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: ``

## callers

- `0x140070864`
- `0x140071bb8`
- `0x140071fc4`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x140005e84`
- `0x14000dd64`
- `0x14001b85c`
- `0x14001cd4c`
- `0x14001cde8`
- `0x14001cf08`
- `0x14001d01c`

## import_xrefs

- `ntoskrnl!CcPreparePinWrite` at `0x140005fb4`
- `ntoskrnl!CcPreparePinWrite` at `0x140005fb4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005fef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ebcd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005fef`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001ebcd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f66`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140005f66`

## pseudocode

```c
__int64 __fastcall HsmpFileCachePreparePinWrite(
        PFILE_OBJECT FileObject,
        union _LARGE_INTEGER a2,
        __int64 a3,
        __int64 a4,
        int a5,
        PVOID *a6,
        PVOID *a7,
        BOOLEAN *a8)
{
  BOOLEAN v8; // r13
  __int64 v11; // rsi
  signed __int64 v12; // r14
  int v13; // ebx
  __int64 v14; // r8
  int Bcb; // [rsp+28h] [rbp-70h]
  PVOID *Buffer; // [rsp+30h] [rbp-68h]
  union _LARGE_INTEGER FileOffset; // [rsp+58h] [rbp-40h] BYREF

  v8 = a4;
  v11 = a2.QuadPart + 4096;
  FileOffset.QuadPart = a2.QuadPart + 4096;
  v12 = (a2.QuadPart & 0xFFFFFFFFFFFC0000uLL) + 0x40000;
  *a8 = 0;
  *a6 = 0;
  *a7 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qiDcL)(
      WPP_GLOBAL_Control->AttachedDevice,
      (union _LARGE_INTEGER)a2.QuadPart,
      a3,
      FileObject,
      (union _LARGE_INTEGER)a2.QuadPart);
  }
  if ( a2.QuadPart < 0 || v11 < 0 || v11 <= a2.QuadPart || v12 <= a2.QuadPart || v12 < v11 )
  {
    v13 = -1073741595;
    HsmDbgBreakOnStatus(3221225701LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      HIDWORD(Buffer) = HIDWORD(v11);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qiDiid)(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        v14,
        FileObject,
        (union _LARGE_INTEGER)a2.QuadPart);
    }
  }
  else
  {
    v13 = HsmiFileCacheValidateFileObject(FileObject, &FileOffset, 0, a4);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qDd)(
          WPP_GLOBAL_Control->AttachedDevice,
          47,
          WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
          (union _LARGE_INTEGER)a2.QuadPart,
          4096,
          v13);
      }
    }
    else
    {
      KeEnterCriticalRegion();
      FileOffset = a2;
      *a8 = CcPreparePinWrite(FileObject, &FileOffset, 0x1000u, v8, 0x20u, a6, a7);
      KeLeaveCriticalRegion();
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    LODWORD(Buffer) = v13;
    LOBYTE(Bcb) = *a8;
    WPP_SF_qqcd(WPP_GLOBAL_Control->AttachedDevice, *a7, v14, *a6, *a7, Bcb, Buffer);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140005e84  mov     rax, rsp
0x140005e87  mov     [rax+20h], r9b
0x140005e8b  mov     [rax+10h], rdx
0x140005e8f  mov     [rax+8], rcx
0x140005e93  push    rbx
0x140005e94  push    rsi
0x140005e95  push    rdi
0x140005e96  push    r12
0x140005e98  push    r13
0x140005e9a  push    r14
0x140005e9c  push    r15
0x140005e9e  sub     rsp, 60h
0x140005ea2  mov     r13b, r9b
0x140005ea5  mov     rdi, rdx
0x140005ea8  mov     r12, rcx
0x140005eab  lea     rsi, [rdx+1000h]
0x140005eb2  mov     [rax-40h], rsi
0x140005eb6  mov     r14, rdx
0x140005eb9  and     r14, 0FFFFFFFFFFFC0000h
0x140005ec0  add     r14, 40000h
0x140005ec7  mov     rax, [rsp+98h+arg_38]
0x140005ecf  mov     byte ptr [rax], 0
0x140005ed2  mov     rax, [rsp+98h+arg_28]
0x140005eda  mov     qword ptr [rax], 0
0x140005ee1  mov     rax, [rsp+98h+arg_30]
0x140005ee9  mov     qword ptr [rax], 0
0x140005ef0  lea     r15, WPP_GLOBAL_Control
0x140005ef7  mov     rcx, cs:WPP_GLOBAL_Control
0x140005efe  cmp     rcx, r15
0x140005f01  jz      short loc_140005F14
0x140005f03  mov     eax, [rcx+2Ch]
0x140005f06  test    al, 8
0x140005f08  jz      short loc_140005F14
0x140005f0a  cmp     byte ptr [rcx+29h], 5
0x140005f0e  jnb     loc_1400060BD
0x140005f14  test    rdi, rdi
0x140005f17  js      loc_140006067
0x140005f1d  test    rsi, rsi
0x140005f20  js      loc_140006067
0x140005f26  cmp     rsi, rdi
0x140005f29  jle     loc_140006067
0x140005f2f  cmp     r14, rdi
0x140005f32  jle     loc_140006067
0x140005f38  cmp     r14, rsi
0x140005f3b  jl      loc_140006067
0x140005f41  xor     r8d, r8d
0x140005f44  lea     rdx, [rsp+98h+FileOffset]
0x140005f49  mov     rcx, r12
0x140005f4c  call    HsmiFileCacheValidateFileObject
0x140005f51  mov     ebx, eax
0x140005f53  mov     [rsp+98h+var_48], eax
0x140005f57  mov     ecx, eax
0x140005f59  call    HsmDbgBreakOnStatus
0x140005f5e  test    ebx, ebx
0x140005f60  js      loc_1400060D8
0x140005f66  call    cs:__imp_KeEnterCriticalRegion
0x140005f6d  nop     dword ptr [rax+rax+00h]
0x140005f72  nop
0x140005f73  mov     qword ptr [rsp+98h+FileOffset], 0
0x140005f7c  mov     qword ptr [rsp+98h+FileOffset], rdi
0x140005f81  mov     rax, [rsp+98h+arg_30]
0x140005f89  mov     [rsp+98h+Buffer], rax; Buffer
0x140005f8e  mov     rax, [rsp+98h+arg_28]
0x140005f96  mov     [rsp+98h+Bcb], rax; Bcb
0x140005f9b  mov     [rsp+98h+Flags], 20h ; ' '; Flags
0x140005fa3  mov     r9b, r13b; Zero
0x140005fa6  mov     r8d, 1000h; Length
0x140005fac  lea     rdx, [rsp+98h+FileOffset]; FileOffset
0x140005fb1  mov     rcx, r12; FileObject
0x140005fb4  call    cs:__imp_CcPreparePinWrite
0x140005fbb  nop     dword ptr [rax+rax+00h]
0x140005fc0  mov     rcx, [rsp+98h+arg_38]
0x140005fc8  mov     [rcx], al
0x140005fca  jmp     short loc_140005FEF
0x140005fcc  lea     r15, WPP_GLOBAL_Control
0x140005fd3  mov     r13b, [rsp+98h+arg_18]
0x140005fdb  mov     rdi, [rsp+98h+arg_8]
0x140005fe3  mov     r12, [rsp+98h+arg_0]
0x140005feb  mov     ebx, [rsp+98h+var_48]
0x140005fef  call    cs:__imp_KeLeaveCriticalRegion
0x140005ff6  nop     dword ptr [rax+rax+00h]
0x140005ffb  test    ebx, ebx
0x140005ffd  js      loc_140006126
0x140006003  mov     rcx, cs:WPP_GLOBAL_Control
0x14000600a  cmp     rcx, r15
0x14000600d  jnz     short loc_140006022
0x14000600f  mov     eax, ebx
0x140006011  add     rsp, 60h
0x140006015  pop     r15
0x140006017  pop     r14
0x140006019  pop     r13
0x14000601b  pop     r12
0x14000601d  pop     rdi
0x14000601e  pop     rsi
0x14000601f  pop     rbx
0x140006020  retn
0x140006022  mov     eax, [rcx+2Ch]
0x140006025  test    al, 8
0x140006027  jz      short loc_14000600F
0x140006029  cmp     byte ptr [rcx+29h], 5
0x14000602d  jb      short loc_14000600F
0x14000602f  mov     dword ptr [rsp+98h+Buffer], ebx
0x140006033  mov     rax, [rsp+98h+arg_38]
0x14000603b  mov     dl, [rax]
0x14000603d  mov     byte ptr [rsp+98h+Bcb], dl
0x140006041  mov     rax, [rsp+98h+arg_30]
0x140006049  mov     rdx, [rax]
0x14000604c  mov     qword ptr [rsp+98h+Flags], rdx
0x140006051  mov     rax, [rsp+98h+arg_28]
0x140006059  mov     r9, [rax]
0x14000605c  mov     rcx, [rcx+18h]
0x140006060  call    WPP_SF_qqcd
0x140006065  jmp     short loc_14000600F
0x140006067  mov     ebx, 0C00000E5h
0x14000606c  mov     ecx, ebx
0x14000606e  call    HsmDbgBreakOnStatus
0x140006073  mov     rcx, cs:WPP_GLOBAL_Control
0x14000607a  cmp     rcx, r15
0x14000607d  jz      short loc_140006003
0x14000607f  mov     eax, [rcx+2Ch]
0x140006082  test    al, 8
0x140006084  jz      loc_140006003
0x14000608a  cmp     byte ptr [rcx+29h], 2
0x14000608e  jb      loc_140006003
0x140006094  mov     edx, 2Eh ; '.'
0x140006099  mov     [rsp+98h+var_58], ebx
0x14000609d  mov     [rsp+98h+var_60], r14
0x1400060a2  mov     [rsp+98h+Buffer], rsi
0x1400060a7  mov     qword ptr [rsp+98h+Flags], rdi
0x1400060ac  mov     r9, r12
0x1400060af  mov     rcx, [rcx+18h]
0x1400060b3  call    WPP_SF_qiDiid
0x1400060b8  jmp     loc_140006003
0x1400060bd  mov     byte ptr [rsp+98h+Buffer], r13b
0x1400060c2  mov     qword ptr [rsp+98h+Flags], rdi
0x1400060c7  mov     r9, r12
0x1400060ca  mov     rcx, [rcx+18h]
0x1400060ce  call    WPP_SF_qiDcL
0x1400060d3  jmp     loc_140005F14
0x1400060d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060df  cmp     rcx, r15
0x1400060e2  jz      loc_140006003
0x1400060e8  mov     eax, [rcx+2Ch]
0x1400060eb  test    al, 8
0x1400060ed  jz      loc_140006003
0x1400060f3  cmp     byte ptr [rcx+29h], 2
0x1400060f7  jb      loc_140006003
0x1400060fd  mov     edx, 2Fh ; '/'
0x140006102  mov     dword ptr [rsp+98h+Bcb], ebx
0x140006106  mov     [rsp+98h+Flags], 1000h
0x14000610e  mov     r9, rdi
0x140006111  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x140006118  mov     rcx, [rcx+18h]
0x14000611c  call    WPP_SF_qDd
0x140006121  jmp     loc_140006003
0x140006126  mov     rcx, cs:WPP_GLOBAL_Control
0x14000612d  cmp     rcx, r15
0x140006130  jz      loc_140006003
0x140006136  mov     eax, [rcx+2Ch]
0x140006139  test    al, 8
0x14000613b  jz      loc_140006003
0x140006141  cmp     byte ptr [rcx+29h], 2
0x140006145  jb      loc_140006003
0x14000614b  mov     [rsp+98h+var_58], ebx
0x14000614f  mov     byte ptr [rsp+98h+Buffer], r13b
0x140006154  mov     qword ptr [rsp+98h+Flags], rdi
0x140006159  mov     r9, r12
0x14000615c  mov     rcx, [rcx+18h]
0x140006160  call    WPP_SF_qiDcLd
0x140006165  jmp     loc_140006003
0x14001ebaa  push    rbp
0x14001ebac  sub     rsp, 50h
0x14001ebb0  mov     rbp, rdx
0x14001ebb3  lea     rdx, [rbp+50h]
0x14001ebb7  call    HsmFileCacheExceptionFilter
0x14001ebbc  nop
0x14001ebbd  add     rsp, 50h
0x14001ebc1  pop     rbp
0x14001ebc2  retn
0x14001ebc4  push    rbp
0x14001ebc6  sub     rsp, 50h
0x14001ebca  mov     rbp, rdx
0x14001ebcd  call    cs:__imp_KeLeaveCriticalRegion
0x14001ebd4  nop     dword ptr [rax+rax+00h]
0x14001ebd9  nop
0x14001ebda  add     rsp, 50h
0x14001ebde  pop     rbp
0x14001ebdf  retn
```
