# FatLockVolumeInternal

- ea: `0x140005a94`
- end: `0x140005c77`
- name: `FatLockVolumeInternal`
- size: `483`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140040210`
- `0x1400452a0`

## callees

- `0x140005a94`
- `0x140006dbc`
- `0x140023cc4`
- `0x140026390`
- `0x14003dae0`
- `0x14003e4b4`
- `0x1400466c8`
- `0x140048e2c`

## import_xrefs

- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005bad`
- `ntoskrnl!IoAcquireVpbSpinLock` at `0x140005bad`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140005c14`
- `ntoskrnl!IoReleaseVpbSpinLock` at `0x140005c14`
- `ntoskrnl!CcIsThereDirtyData` at `0x140005c3f`
- `ntoskrnl!CcIsThereDirtyData` at `0x140005c3f`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140005b2c`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140005b78`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140005b2c`
- `ntoskrnl!CcWaitForCurrentLazyWriterActivity` at `0x140005b78`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005b20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005b6c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005b20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140005b6c`

## pseudocode

```c
__int64 __fastcall FatLockVolumeInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // r8
  __int64 v9; // rcx
  NTSTATUS v10; // edi
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int16 v17; // dx
  KIRQL Irql; // [rsp+50h] [rbp+8h] BYREF
  __int64 v19; // [rsp+58h] [rbp+10h]

  v19 = a2;
  Irql = 0;
  *(_DWORD *)(a1 + 68) |= 2u;
  if ( !(unsigned __int8)FatIsHandleCountZero(a1, a2, a3, a4) )
    return 3221225506LL;
  _InterlockedOr((volatile signed __int32 *)(a2 + 200), 0x1000000u);
  FatFlushFat(a1, a2);
  FatPurgeReferencedFileObjects(a1, *(_QWORD *)(a2 + 208), 1);
  LOBYTE(v8) = 1;
  FatCloseEaFile(v9, a2, v8);
  ExReleaseResourceLite((PERESOURCE)(a2 + 520));
  v10 = CcWaitForCurrentLazyWriterActivity();
  FatAcquireExclusiveVcb_Real(a1, a2, 0, v11);
  if ( v10 >= 0 )
  {
    FatPurgeReferencedFileObjects(a1, *(_QWORD *)(a2 + 208), 1);
    ExReleaseResourceLite((PERESOURCE)(a2 + 520));
    v10 = CcWaitForCurrentLazyWriterActivity();
    FatAcquireExclusiveVcb_Real(a1, a2, 0, v12);
    if ( v10 >= 0 )
    {
      FatFspClose(a2, v13, v14, v15);
      IoAcquireVpbSpinLock(&Irql);
      v16 = *(_QWORD *)(a2 + 192);
      v17 = *(_WORD *)(v16 + 4);
      if ( (v17 & 2) != 0 || *(_DWORD *)(v16 + 28) > (unsigned int)(a3 != 0) + 2 || *(_DWORD *)(a2 + 272) != (a3 != 0) )
      {
        v10 = -1073741790;
      }
      else
      {
        *(_WORD *)(v16 + 4) = v17 | 0x22;
        _InterlockedOr((volatile signed __int32 *)(a2 + 200), 1u);
        *(_QWORD *)(a2 + 792) = a3;
      }
      IoReleaseVpbSpinLock(Irql);
      if ( v10 >= 0
        && (*(_DWORD *)(a2 + 200) & 4) != 0
        && (*(_DWORD *)(a2 + 200) & 0x10) == 0
        && !CcIsThereDirtyData(*(PVPB *)(a2 + 192)) )
      {
        FatMarkVolume(a1, a2, 0);
        _InterlockedAnd((volatile signed __int32 *)(a2 + 200), 0xFFFFFFFB);
      }
    }
  }
  _InterlockedAnd((volatile signed __int32 *)(a2 + 200), 0xFEFFFFFF);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140005a94  mov     rax, rsp
0x140005a97  mov     [rax+18h], rbx
0x140005a9b  mov     [rax+20h], rsi
0x140005a9f  mov     [rax+10h], rdx
0x140005aa3  push    rdi
0x140005aa4  push    r14
0x140005aa6  push    r15
0x140005aa8  sub     rsp, 30h
0x140005aac  mov     r14, r8
0x140005aaf  mov     rbx, rdx
0x140005ab2  mov     rsi, rcx
0x140005ab5  mov     byte ptr [rax+8], 0
0x140005ab9  or      dword ptr [rcx+44h], 2
0x140005abd  call    FatIsHandleCountZero
0x140005ac2  test    al, al
0x140005ac4  jnz     short loc_140005AE0
0x140005ac6  mov     eax, 0C0000022h
0x140005acb  mov     rbx, [rsp+48h+arg_10]
0x140005ad0  mov     rsi, [rsp+48h+arg_18]
0x140005ad5  add     rsp, 30h
0x140005ad9  pop     r15
0x140005adb  pop     r14
0x140005add  pop     rdi
0x140005ade  retn
0x140005ae0  lock or dword ptr [rbx+0C8h], 1000000h
0x140005aeb  mov     rdx, rbx
0x140005aee  mov     rcx, rsi
0x140005af1  call    FatFlushFat
0x140005af6  mov     r8d, 1
0x140005afc  mov     rdx, [rbx+0D0h]
0x140005b03  mov     rcx, rsi
0x140005b06  call    FatPurgeReferencedFileObjects
0x140005b0b  mov     r8b, 1
0x140005b0e  mov     rdx, rbx
0x140005b11  call    FatCloseEaFile
0x140005b16  lea     r15, [rbx+208h]
0x140005b1d  mov     rcx, r15; Resource
0x140005b20  call    cs:__imp_ExReleaseResourceLite
0x140005b27  nop     dword ptr [rax+rax+00h]
0x140005b2c  call    cs:__imp_CcWaitForCurrentLazyWriterActivity
0x140005b33  nop     dword ptr [rax+rax+00h]
0x140005b38  mov     edi, eax
0x140005b3a  mov     [rsp+48h+var_28], eax
0x140005b3e  xor     r8d, r8d
0x140005b41  mov     rdx, rbx
0x140005b44  mov     rcx, rsi
0x140005b47  call    FatAcquireExclusiveVcb_Real
0x140005b4c  test    edi, edi
0x140005b4e  js      loc_140005C65
0x140005b54  mov     r8d, 1
0x140005b5a  mov     rdx, [rbx+0D0h]
0x140005b61  mov     rcx, rsi
0x140005b64  call    FatPurgeReferencedFileObjects
0x140005b69  mov     rcx, r15; Resource
0x140005b6c  call    cs:__imp_ExReleaseResourceLite
0x140005b73  nop     dword ptr [rax+rax+00h]
0x140005b78  call    cs:__imp_CcWaitForCurrentLazyWriterActivity
0x140005b7f  nop     dword ptr [rax+rax+00h]
0x140005b84  mov     edi, eax
0x140005b86  mov     [rsp+48h+var_28], eax
0x140005b8a  xor     r8d, r8d
0x140005b8d  mov     rdx, rbx
0x140005b90  mov     rcx, rsi
0x140005b93  call    FatAcquireExclusiveVcb_Real
0x140005b98  test    edi, edi
0x140005b9a  js      loc_140005C65
0x140005ba0  mov     rcx, rbx
0x140005ba3  call    FatFspClose
0x140005ba8  lea     rcx, [rsp+48h+Irql]; Irql
0x140005bad  call    cs:__imp_IoAcquireVpbSpinLock
0x140005bb4  nop     dword ptr [rax+rax+00h]
0x140005bb9  mov     r8, [rbx+0C0h]
0x140005bc0  movzx   edx, word ptr [r8+4]
0x140005bc5  test    dl, 2
0x140005bc8  jnz     short loc_140005C07
0x140005bca  mov     rax, r14
0x140005bcd  neg     rax
0x140005bd0  sbb     ecx, ecx
0x140005bd2  neg     ecx
0x140005bd4  add     ecx, 2
0x140005bd7  cmp     [r8+1Ch], ecx
0x140005bdb  ja      short loc_140005C07
0x140005bdd  xor     eax, eax
0x140005bdf  test    r14, r14
0x140005be2  setnz   al
0x140005be5  cmp     [rbx+110h], eax
0x140005beb  jnz     short loc_140005C07
0x140005bed  or      dx, 22h
0x140005bf1  mov     [r8+4], dx
0x140005bf6  lock or dword ptr [rbx+0C8h], 1
0x140005bfe  mov     [rbx+318h], r14
0x140005c05  jmp     short loc_140005C10
0x140005c07  mov     edi, 0C0000022h
0x140005c0c  mov     [rsp+48h+var_28], edi
0x140005c10  mov     cl, [rsp+48h+Irql]; Irql
0x140005c14  call    cs:__imp_IoReleaseVpbSpinLock
0x140005c1b  nop     dword ptr [rax+rax+00h]
0x140005c20  test    edi, edi
0x140005c22  js      short loc_140005C65
0x140005c24  mov     eax, [rbx+0C8h]
0x140005c2a  test    al, 4
0x140005c2c  jz      short loc_140005C65
0x140005c2e  mov     eax, [rbx+0C8h]
0x140005c34  test    al, 10h
0x140005c36  jnz     short loc_140005C65
0x140005c38  mov     rcx, [rbx+0C0h]; Vpb
0x140005c3f  call    cs:__imp_CcIsThereDirtyData
0x140005c46  nop     dword ptr [rax+rax+00h]
0x140005c4b  test    al, al
0x140005c4d  jnz     short loc_140005C65
0x140005c4f  xor     r8d, r8d
0x140005c52  mov     rdx, rbx
0x140005c55  mov     rcx, rsi
0x140005c58  call    FatMarkVolume
0x140005c5d  lock and dword ptr [rbx+0C8h], 0FFFFFFFBh
0x140005c65  lock and dword ptr [rbx+0C8h], 0FEFFFFFFh
0x140005c70  mov     eax, edi
0x140005c72  jmp     loc_140005ACB
0x14000d2a8  push    rbp
0x14000d2aa  sub     rsp, 20h
0x14000d2ae  mov     rbp, rdx
0x14000d2b1  mov     rax, [rbp+58h]
0x14000d2b5  lock and dword ptr [rax+0C8h], 0FEFFFFFFh
0x14000d2c0  add     rsp, 20h
0x14000d2c4  pop     rbp
0x14000d2c5  retn
```
