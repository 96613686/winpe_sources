# CscSidMappLoad

- ea: `0x140089e98`
- end: `0x14008a16d`
- name: `CscSidMappLoad`
- size: `725`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14008df70`

## callees

- `0x1400062ec`
- `0x14000b9d0`
- `0x140010f6c`
- `0x140016a04`
- `0x14001a494`
- `0x1400287bc`
- `0x140089e98`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140089fc8`
- `ntoskrnl!ExAllocatePool2` at `0x14008a060`
- `ntoskrnl!ExAllocatePool2` at `0x140089fc8`
- `ntoskrnl!ExAllocatePool2` at `0x14008a060`

## pseudocode

```c
__int64 __fastcall CscSidMappLoad(__int64 a1)
{
  __int64 v2; // rdx
  int File; // ebx
  int v4; // edi
  int v5; // edi
  int *Pool2; // rax
  int *v7; // rsi
  unsigned __int64 v8; // rdi
  int v9; // r13d
  unsigned int i; // edi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r9
  unsigned __int64 LowLimit; // [rsp+C0h] [rbp+48h] BYREF
  int v16; // [rsp+C8h] [rbp+50h] BYREF
  struct _LIST_ENTRY v17; // [rsp+D0h] [rbp+58h] BYREF

  v17.Flink = 0;
  v16 = 0;
  LODWORD(LowLimit) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, a1);
  File = CscStorepLowIoCreateFilePoster(
           &v17,
           *(struct _LIST_ENTRY **)(a1 + 16),
           (struct _LIST_ENTRY *)(a1 + 24),
           1179785,
           0,
           128,
           1,
           1,
           96,
           0,
           0,
           0,
           0);
  if ( File < 0 )
  {
    v4 = 360;
    goto LABEL_36;
  }
  File = CscStorepLowIoReadFile((int)v17.Flink, 0, 4, (int)&v16, (unsigned __int64)&LowLimit);
  if ( File < 0 )
  {
    v4 = 369;
    goto LABEL_36;
  }
  if ( (_DWORD)LowLimit != 4 )
  {
    File = -1073741596;
    v4 = 374;
    goto LABEL_36;
  }
  v5 = v16;
  if ( !v16 )
  {
    v4 = 381;
    goto LABEL_36;
  }
  if ( 16 * (unsigned __int64)(unsigned int)v16 > 0xFFFFFFFF )
  {
    File = -1073741675;
    goto LABEL_35;
  }
  Pool2 = (int *)ExAllocatePool2(256, (unsigned int)(16 * v16 + 8), 591426371);
  v7 = Pool2;
  if ( !Pool2 )
  {
    File = -1073741670;
LABEL_35:
    v4 = 385;
    goto LABEL_36;
  }
  *Pool2 = v5;
  v8 = 16LL * (unsigned int)v16;
  if ( v8 > 0xFFFFFFFF )
  {
    File = -1073741675;
    v4 = 392;
    goto LABEL_33;
  }
  File = CscStorepLowIoReadFile((int)v17.Flink, 4, v8, (int)Pool2 + 8, (unsigned __int64)&LowLimit);
  if ( File < 0 )
  {
    v4 = 399;
LABEL_33:
    CscSidMappDestroySidArray(v7);
    goto LABEL_36;
  }
  if ( (_DWORD)v8 != (_DWORD)LowLimit )
  {
    File = -1073741596;
    v4 = 404;
    goto LABEL_33;
  }
  v9 = LowLimit + 4;
  for ( i = 0; ; ++i )
  {
    if ( i >= v16 )
    {
      *(_QWORD *)(a1 + 56) = v7;
      v4 = 0;
      goto LABEL_36;
    }
    v11 = ExAllocatePool2(258, (unsigned int)v7[4 * i + 2], 591426371);
    *(_QWORD *)&v7[4 * i + 4] = v11;
    if ( !v11 )
      break;
    ++v7[1];
    File = CscStorepLowIoReadFile(
             (int)v17.Flink,
             v9,
             v7[4 * i + 2],
             *(_QWORD *)&v7[4 * i + 4],
             (unsigned __int64)&LowLimit);
    if ( File < 0 )
    {
      v4 = 424;
      goto LABEL_29;
    }
    if ( (_DWORD)LowLimit != v7[4 * i + 2] )
    {
      File = -1073741596;
      v4 = 429;
      goto LABEL_29;
    }
    v9 += LowLimit;
  }
  File = -1073741670;
  v4 = 415;
LABEL_29:
  if ( v7 )
    goto LABEL_33;
LABEL_36:
  if ( v17.Flink )
    CscStorepLowIoClosePoster(v17.Flink, v2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    v12 = *(_QWORD *)(a1 + 56);
    if ( v12 )
      v13 = *(unsigned int *)(v12 + 4);
    else
      v13 = 0;
    WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids, v13, File, v4);
  }
  return (unsigned int)File;
}

```

## disassembly

```asm
0x140089e98  push    rbp
0x140089e9a  push    rbx
0x140089e9b  push    rsi
0x140089e9c  push    rdi
0x140089e9d  push    r12
0x140089e9f  push    r13
0x140089ea1  push    r14
0x140089ea3  push    r15
0x140089ea5  mov     rbp, rsp
0x140089ea8  sub     rsp, 78h
0x140089eac  xor     r15d, r15d
0x140089eaf  mov     r14, rcx
0x140089eb2  mov     qword ptr [rbp+arg_10], r15
0x140089eb6  mov     [rbp+arg_8], r15d
0x140089eba  mov     dword ptr [rbp+arg_0], r15d
0x140089ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x140089ec5  lea     r12, WPP_GLOBAL_Control
0x140089ecc  cmp     rcx, r12
0x140089ecf  jz      short loc_140089EF1
0x140089ed1  test    dword ptr [rcx+2Ch], 40000h
0x140089ed8  jz      short loc_140089EF1
0x140089eda  mov     rcx, [rcx+18h]
0x140089ede  lea     edx, [r15+0Ah]
0x140089ee2  mov     r9, r14
0x140089ee5  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x140089eec  call    WPP_SF_q
0x140089ef1  mov     rdx, [r14+10h]
0x140089ef5  lea     r8, [r14+18h]
0x140089ef9  mov     [rsp+78h+var_18], r15
0x140089efe  lea     rcx, [rbp+arg_10]
0x140089f02  mov     [rsp+78h+var_20], r15
0x140089f07  mov     eax, 1
0x140089f0c  mov     [rsp+78h+var_28], r15d
0x140089f11  mov     r9d, 120089h
0x140089f17  mov     [rsp+78h+var_30], r15
0x140089f1c  mov     [rsp+78h+var_38], 60h ; '`'
0x140089f24  mov     [rsp+78h+var_40], eax
0x140089f28  mov     [rsp+78h+var_48], eax
0x140089f2c  mov     [rsp+78h+var_50], 80h
0x140089f34  mov     [rsp+78h+LowLimit], r15
0x140089f39  call    CscStorepLowIoCreateFilePoster
0x140089f3e  mov     ebx, eax
0x140089f40  test    eax, eax
0x140089f42  jns     short loc_140089F4E
0x140089f44  mov     edi, 168h
0x140089f49  jmp     loc_14008A107
0x140089f4e  mov     rcx, qword ptr [rbp+arg_10]; int
0x140089f52  lea     rax, [rbp+arg_0]
0x140089f56  mov     r12d, 4
0x140089f5c  mov     [rsp+78h+LowLimit], rax; LowLimit
0x140089f61  mov     r8d, r12d; int
0x140089f64  lea     r9, [rbp+arg_8]; int
0x140089f68  xor     edx, edx; int
0x140089f6a  call    CscStorepLowIoReadFile
0x140089f6f  mov     ebx, eax
0x140089f71  test    eax, eax
0x140089f73  jns     short loc_140089F7F
0x140089f75  mov     edi, 171h
0x140089f7a  jmp     loc_14008A100
0x140089f7f  cmp     dword ptr [rbp+arg_0], r12d
0x140089f83  jz      short loc_140089F94
0x140089f85  mov     ebx, 0C00000E4h
0x140089f8a  mov     edi, 176h
0x140089f8f  jmp     loc_14008A100
0x140089f94  mov     edi, [rbp+arg_8]
0x140089f97  test    edi, edi
0x140089f99  jnz     short loc_140089FA5
0x140089f9b  mov     edi, 17Dh
0x140089fa0  jmp     loc_14008A100
0x140089fa5  mov     rax, rdi
0x140089fa8  mov     ebx, 0FFFFFFFFh
0x140089fad  shl     rax, 4
0x140089fb1  cmp     rax, rbx
0x140089fb4  ja      loc_14008A0F6
0x140089fba  lea     edx, [rax+8]
0x140089fbd  mov     ecx, 100h
0x140089fc2  mov     r8d, 23407343h
0x140089fc8  call    cs:__imp_ExAllocatePool2
0x140089fcf  nop     dword ptr [rax+rax+00h]
0x140089fd4  mov     rsi, rax
0x140089fd7  test    rax, rax
0x140089fda  jnz     short loc_140089FE6
0x140089fdc  mov     ebx, 0C000009Ah
0x140089fe1  jmp     loc_14008A0FB
0x140089fe6  mov     [rax], edi
0x140089fe8  mov     edi, [rbp+arg_8]
0x140089feb  shl     rdi, 4
0x140089fef  cmp     rdi, rbx
0x140089ff2  ja      loc_14008A0E2
0x140089ff8  mov     rcx, qword ptr [rbp+arg_10]; int
0x140089ffc  lea     r9, [rax+8]; int
0x14008a000  lea     rax, [rbp+arg_0]
0x14008a004  mov     r8d, edi; int
0x14008a007  mov     rdx, r12; int
0x14008a00a  mov     [rsp+78h+LowLimit], rax; LowLimit
0x14008a00f  call    CscStorepLowIoReadFile
0x14008a014  mov     ebx, eax
0x14008a016  test    eax, eax
0x14008a018  jns     short loc_14008A024
0x14008a01a  mov     edi, 18Fh
0x14008a01f  jmp     loc_14008A0EC
0x14008a024  mov     eax, dword ptr [rbp+arg_0]
0x14008a027  cmp     edi, eax
0x14008a029  jz      short loc_14008A03A
0x14008a02b  mov     ebx, 0C00000E4h
0x14008a030  mov     edi, 194h
0x14008a035  jmp     loc_14008A0EC
0x14008a03a  lea     r13d, [rax+4]
0x14008a03e  mov     edi, r15d
0x14008a041  cmp     edi, [rbp+arg_8]
0x14008a044  jnb     loc_14008A0D6
0x14008a04a  mov     r15d, edi
0x14008a04d  mov     ecx, 102h
0x14008a052  add     r15, r15
0x14008a055  mov     r8d, 23407343h
0x14008a05b  mov     edx, [rsi+r15*8+8]
0x14008a060  call    cs:__imp_ExAllocatePool2
0x14008a067  nop     dword ptr [rax+rax+00h]
0x14008a06c  mov     [rsi+r15*8+10h], rax
0x14008a071  test    rax, rax
0x14008a074  jz      short loc_14008A0C2
0x14008a076  inc     dword ptr [rsi+4]
0x14008a079  lea     rax, [rbp+arg_0]
0x14008a07d  mov     r9, [rsi+r15*8+10h]; int
0x14008a082  mov     r8d, [rsi+r15*8+8]; int
0x14008a087  mov     rcx, qword ptr [rbp+arg_10]; int
0x14008a08b  mov     edx, r13d; int
0x14008a08e  mov     [rsp+78h+LowLimit], rax; LowLimit
0x14008a093  call    CscStorepLowIoReadFile
0x14008a098  mov     ebx, eax
0x14008a09a  test    eax, eax
0x14008a09c  js      short loc_14008A0BB
0x14008a09e  mov     eax, dword ptr [rbp+arg_0]
0x14008a0a1  cmp     eax, [rsi+r15*8+8]
0x14008a0a6  jnz     short loc_14008A0AF
0x14008a0a8  add     r13d, eax
0x14008a0ab  inc     edi
0x14008a0ad  jmp     short loc_14008A041
0x14008a0af  mov     ebx, 0C00000E4h
0x14008a0b4  mov     edi, 1ADh
0x14008a0b9  jmp     short loc_14008A0CC
0x14008a0bb  mov     edi, 1A8h
0x14008a0c0  jmp     short loc_14008A0CC
0x14008a0c2  mov     ebx, 0C000009Ah
0x14008a0c7  mov     edi, 19Fh
0x14008a0cc  xor     r15d, r15d
0x14008a0cf  test    rsi, rsi
0x14008a0d2  jnz     short loc_14008A0EC
0x14008a0d4  jmp     short loc_14008A100
0x14008a0d6  xor     r15d, r15d
0x14008a0d9  mov     [r14+38h], rsi
0x14008a0dd  mov     edi, r15d
0x14008a0e0  jmp     short loc_14008A100
0x14008a0e2  mov     ebx, 0C0000095h
0x14008a0e7  mov     edi, 188h
0x14008a0ec  mov     rcx, rsi; P
0x14008a0ef  call    CscSidMappDestroySidArray
0x14008a0f4  jmp     short loc_14008A100
0x14008a0f6  mov     ebx, 0C0000095h
0x14008a0fb  mov     edi, 181h
0x14008a100  lea     r12, WPP_GLOBAL_Control
0x14008a107  mov     rcx, qword ptr [rbp+arg_10]
0x14008a10b  test    rcx, rcx
0x14008a10e  jz      short loc_14008A115
0x14008a110  call    CscStorepLowIoClosePoster
0x14008a115  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a11c  cmp     rcx, r12
0x14008a11f  jz      short loc_14008A159
0x14008a121  test    dword ptr [rcx+2Ch], 40000h
0x14008a128  jz      short loc_14008A159
0x14008a12a  mov     rax, [r14+38h]
0x14008a12e  test    rax, rax
0x14008a131  jz      short loc_14008A139
0x14008a133  mov     r9d, [rax+4]
0x14008a137  jmp     short loc_14008A13C
0x14008a139  mov     r9d, r15d
0x14008a13c  mov     rcx, [rcx+18h]
0x14008a140  lea     r8, WPP_238132d70db8346a917bc6570ec5eca2_Traceguids
0x14008a147  mov     edx, 0Bh
0x14008a14c  mov     [rsp+78h+var_50], edi
0x14008a150  mov     dword ptr [rsp+78h+LowLimit], ebx
0x14008a154  call    WPP_SF_DDd
0x14008a159  mov     eax, ebx
0x14008a15b  add     rsp, 78h
0x14008a15f  pop     r15
0x14008a161  pop     r14
0x14008a163  pop     r13
0x14008a165  pop     r12
0x14008a167  pop     rdi
0x14008a168  pop     rsi
0x14008a169  pop     rbx
0x14008a16a  pop     rbp
0x14008a16b  retn
```
