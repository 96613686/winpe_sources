# RefsFsdDirectoryControl

- ea: `0x1c017b0b0`
- end: `0x1c017b256`
- name: `RefsFsdDirectoryControl`
- size: `422`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c017b0b0`
- `0x1c017b25c`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c017b1a2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c017b1a2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c017b10a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c017b10a`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c017b123`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c017b123`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c018b759`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c018b759`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c017b21d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c017b21d`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c017b161`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c017b161`

## pseudocode

```c
__int64 __fastcall RefsFsdDirectoryControl(__int64 a1, IRP *a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // r8
  PIRP v7; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LIST_ENTRY *v9; // rbx
  unsigned int v10; // edi
  struct _LIST_ENTRY *v12; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v13; // [rsp+28h] [rbp-70h]
  BOOL v14; // [rsp+2Ch] [rbp-6Ch]
  __int64 v15; // [rsp+30h] [rbp-68h] BYREF
  PIRP Irp; // [rsp+38h] [rbp-60h]
  IRP *v17; // [rsp+40h] [rbp-58h]
  IRP *v18; // [rsp+48h] [rbp-50h]
  _OWORD v19[2]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v20; // [rsp+70h] [rbp-28h]
  __int128 v21; // [rsp+78h] [rbp-20h] BYREF

  v18 = a2;
  memset(v19, 0, sizeof(v19));
  v20 = 0;
  v12 = 0;
  v21 = 0;
  v15 = 0;
  a2->IoStatus.Information = 0;
  KeEnterCriticalRegion();
  v14 = (int)IoPropagateActivityIdToThread(a2, &v21, &v15) >= 0;
  LOBYTE(v3) = 1;
  LOBYTE(v4) = 1;
  v17 = (IRP *)RefsInitializeTopLevelIrp(v19, v4, v3);
  Irp = v17;
  LOBYTE(v5) = IoIsOperationSynchronous(a2);
  LOBYTE(v6) = 1;
  RefsInitializeIrpContext(a2, v5, v6, &v12);
  v7 = Irp;
  Flink = Irp->ThreadListEntry.Flink;
  if ( Flink )
  {
    v9 = v12;
  }
  else
  {
    *(_DWORD *)(&Irp->Size + 1) = 1397140410;
    v9 = v12;
    v7->ThreadListEntry.Flink = v12;
    LODWORD(v9->Blink) |= 0x100000u;
    IoSetTopLevelIrp(v7);
    Flink = v17->ThreadListEntry.Flink;
  }
  v9[6].Blink = Flink;
  RefsPreRequestProcessingExtend(v9);
  v10 = RefsCommonDirectoryControl((_DWORD)v9, (_DWORD)a2);
  v13 = v10;
  if ( v14 )
    IoClearActivityIdThread(v15);
  KeLeaveCriticalRegion();
  return v10;
}

```

## disassembly

```asm
0x1c017b0b0  mov     r11, rsp
0x1c017b0b3  mov     [r11+8], rbx
0x1c017b0b7  mov     [r11+18h], rsi
0x1c017b0bb  mov     [r11+20h], rdi
0x1c017b0bf  push    r14
0x1c017b0c1  sub     rsp, 90h
0x1c017b0c8  mov     rax, cs:__security_cookie
0x1c017b0cf  xor     rax, rsp
0x1c017b0d2  mov     [rsp+98h+var_10], rax
0x1c017b0da  mov     rsi, rdx
0x1c017b0dd  mov     [rsp+98h+var_50], rdx
0x1c017b0e2  xorps   xmm0, xmm0
0x1c017b0e5  xor     eax, eax
0x1c017b0e7  movups  [rsp+98h+var_48], xmm0
0x1c017b0ec  movups  [rsp+98h+var_38], xmm0
0x1c017b0f1  mov     [r11-28h], rax
0x1c017b0f5  xor     edi, edi
0x1c017b0f7  xor     ebx, ebx
0x1c017b0f9  mov     [r11-78h], rbx
0x1c017b0fd  movups  [rsp+98h+var_20], xmm0
0x1c017b102  and     [r11-68h], rax
0x1c017b106  and     [rdx+38h], rax
0x1c017b10a  call    cs:__imp_KeEnterCriticalRegion
0x1c017b111  nop     dword ptr [rax+rax+00h]
0x1c017b116  lea     r8, [rsp+98h+var_68]
0x1c017b11b  lea     rdx, [rsp+98h+var_20]
0x1c017b120  mov     rcx, rsi
0x1c017b123  call    cs:__imp_IoPropagateActivityIdToThread
0x1c017b12a  nop     dword ptr [rax+rax+00h]
0x1c017b12f  xor     ecx, ecx
0x1c017b131  lea     r14d, [rdi+1]
0x1c017b135  test    eax, eax
0x1c017b137  cmovns  ecx, r14d
0x1c017b13b  mov     [rsp+98h+var_6C], ecx
0x1c017b13f  mov     r8b, r14b
0x1c017b142  mov     dl, r14b
0x1c017b145  lea     rcx, [rsp+98h+var_48]
0x1c017b14a  call    RefsInitializeTopLevelIrp
0x1c017b14f  mov     [rsp+98h+var_58], rax
0x1c017b154  mov     [rsp+98h+Irp], rax
0x1c017b159  test    rbx, rbx
0x1c017b15c  jnz     short loc_1C017B1C4
0x1c017b15e  mov     rcx, rsi; Irp
0x1c017b161  call    cs:__imp_IoIsOperationSynchronous
0x1c017b168  nop     dword ptr [rax+rax+00h]
0x1c017b16d  mov     dl, al
0x1c017b16f  lea     r9, [rsp+98h+var_78]
0x1c017b174  mov     r8b, r14b
0x1c017b177  mov     rcx, rsi
0x1c017b17a  call    RefsInitializeIrpContext
0x1c017b17f  mov     rcx, [rsp+98h+Irp]; Irp
0x1c017b184  mov     rax, [rcx+20h]
0x1c017b188  test    rax, rax
0x1c017b18b  jnz     short loc_1C017B1BD
0x1c017b18d  mov     dword ptr [rcx+4], 5346ABBAh
0x1c017b194  mov     rbx, [rsp+98h+var_78]
0x1c017b199  mov     [rcx+20h], rbx
0x1c017b19d  bts     dword ptr [rbx+8], 14h
0x1c017b1a2  call    cs:__imp_IoSetTopLevelIrp
0x1c017b1a9  nop     dword ptr [rax+rax+00h]
0x1c017b1ae  mov     rax, [rsp+98h+var_58]
0x1c017b1b3  mov     rax, [rax+20h]
0x1c017b1b7  mov     [rbx+68h], rax
0x1c017b1bb  jmp     short loc_1C017B1D4
0x1c017b1bd  mov     rbx, [rsp+98h+var_78]
0x1c017b1c2  jmp     short loc_1C017B1B7
0x1c017b1c4  cmp     edi, 0C0000188h
0x1c017b1ca  jnz     short loc_1C017B1D4
0x1c017b1cc  mov     rcx, rbx
0x1c017b1cf  call    RefsCheckpointForLogFileFull
0x1c017b1d4  mov     rcx, rbx
0x1c017b1d7  call    RefsPreRequestProcessingExtend
0x1c017b1dc  mov     rdx, rsi
0x1c017b1df  mov     rcx, rbx
0x1c017b1e2  call    RefsCommonDirectoryControl
0x1c017b1e7  mov     edi, eax
0x1c017b1e9  mov     [rsp+98h+var_70], eax
0x1c017b1ed  jmp     short loc_1C017B212
0x1c017b1ef  mov     r8d, eax
0x1c017b1f2  mov     rsi, [rsp+98h+var_50]
0x1c017b1f7  mov     rdx, rsi
0x1c017b1fa  mov     rbx, [rsp+98h+var_78]
0x1c017b1ff  mov     rcx, rbx
0x1c017b202  call    RefsProcessException
0x1c017b207  mov     edi, eax
0x1c017b209  mov     [rsp+98h+var_70], eax
0x1c017b20d  jmp     loc_1C018B730
0x1c017b212  cmp     [rsp+98h+var_6C], 0
0x1c017b217  jnz     loc_1C018B754
0x1c017b21d  call    cs:__imp_KeLeaveCriticalRegion
0x1c017b224  nop     dword ptr [rax+rax+00h]
0x1c017b229  mov     eax, edi
0x1c017b22b  mov     rcx, [rsp+98h+var_10]
0x1c017b233  xor     rcx, rsp; StackCookie
0x1c017b236  call    __security_check_cookie
0x1c017b23b  lea     r11, [rsp+98h+var_8]
0x1c017b243  mov     rbx, [r11+10h]
0x1c017b247  mov     rsi, [r11+20h]
0x1c017b24b  mov     rdi, [r11+28h]
0x1c017b24f  mov     rsp, r11
0x1c017b252  pop     r14
0x1c017b254  retn
0x1c0180c0e  push    rbp
0x1c0180c10  sub     rsp, 20h
0x1c0180c14  mov     rbp, rdx
0x1c0180c17  mov     rdx, rcx
0x1c0180c1a  mov     rcx, [rbp+20h]
0x1c0180c1e  call    RefsExceptionFilter
0x1c0180c23  nop
0x1c0180c24  add     rsp, 20h
0x1c0180c28  pop     rbp
0x1c0180c29  retn
0x1c018b730  cmp     eax, 0C00000D8h
0x1c018b735  jz      short loc_1C018B749
0x1c018b737  cmp     eax, 0C00001A8h
0x1c018b73c  jz      short loc_1C018B749
0x1c018b73e  cmp     eax, 0C0000188h
0x1c018b743  jnz     loc_1C017B212
0x1c018b749  mov     r14d, 1
0x1c018b74f  jmp     loc_1C017B159
0x1c018b754  mov     rcx, [rsp+98h+var_68]
0x1c018b759  call    cs:__imp_IoClearActivityIdThread
0x1c018b760  nop     dword ptr [rax+rax+00h]
0x1c018b765  nop
0x1c018b766  jmp     loc_1C017B21D
```
