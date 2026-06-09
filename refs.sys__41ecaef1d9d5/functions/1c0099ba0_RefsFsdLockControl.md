# RefsFsdLockControl

- ea: `0x1c0099ba0`
- end: `0x1c0099d7e`
- name: `RefsFsdLockControl`
- size: `478`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1c0005650`
- `0x1c000f480`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c0099ba0`
- `0x1c01bea90`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0099c8d`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0099c8d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0099bf6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0099bf6`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0099c0f`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c0099c0f`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0099d1c`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0099d1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0099d28`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0099d28`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0099c4c`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c0099c4c`

## pseudocode

```c
__int64 __fastcall RefsFsdLockControl(__int64 a1, IRP *a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  PIRP v5; // rcx
  struct _LIST_ENTRY *Flink; // rax
  _DWORD *v7; // rbx
  unsigned int v8; // edi
  PVOID Context; // [rsp+20h] [rbp-78h] BYREF
  unsigned int v11; // [rsp+28h] [rbp-70h]
  BOOL v12; // [rsp+2Ch] [rbp-6Ch]
  __int64 v13; // [rsp+30h] [rbp-68h] BYREF
  PIRP Irp; // [rsp+38h] [rbp-60h]
  IRP *v15; // [rsp+40h] [rbp-58h]
  IRP *v16; // [rsp+48h] [rbp-50h]
  _OWORD v17[2]; // [rsp+50h] [rbp-48h] BYREF
  __int64 v18; // [rsp+70h] [rbp-28h]
  __int128 v19; // [rsp+78h] [rbp-20h] BYREF

  v16 = a2;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  Context = 0;
  v19 = 0;
  v13 = 0;
  KeEnterCriticalRegion();
  v12 = (int)IoPropagateActivityIdToThread(a2, &v19, &v13) >= 0;
  v15 = (IRP *)RefsInitializeTopLevelIrp(v17, 0, 0);
  Irp = v15;
  LOBYTE(v3) = IoIsOperationSynchronous(a2);
  LOBYTE(v4) = 1;
  RefsInitializeIrpContext(a2, v3, v4, &Context);
  v5 = Irp;
  Flink = Irp->ThreadListEntry.Flink;
  if ( Flink )
  {
    v7 = Context;
  }
  else
  {
    *(_DWORD *)(&Irp->Size + 1) = 1397140410;
    v7 = Context;
    v5->ThreadListEntry.Flink = (struct _LIST_ENTRY *)Context;
    v7[2] |= 0x100000u;
    IoSetTopLevelIrp(v5);
    Flink = v15->ThreadListEntry.Flink;
  }
  *((_QWORD *)v7 + 13) = Flink;
  v8 = RefsCommonLockControl(v7, a2);
  v11 = v8;
  if ( v12 )
    IoClearActivityIdThread(v13);
  KeLeaveCriticalRegion();
  return v8;
}

```

## disassembly

```asm
0x1c0099ba0  mov     r11, rsp
0x1c0099ba3  mov     [r11+8], rbx
0x1c0099ba7  mov     [r11+18h], rsi
0x1c0099bab  mov     [r11+20h], rdi
0x1c0099baf  push    r14
0x1c0099bb1  sub     rsp, 90h
0x1c0099bb8  mov     rax, cs:__security_cookie
0x1c0099bbf  xor     rax, rsp
0x1c0099bc2  mov     [rsp+98h+var_10], rax
0x1c0099bca  mov     rsi, rdx
0x1c0099bcd  mov     [rsp+98h+var_50], rdx
0x1c0099bd2  xorps   xmm0, xmm0
0x1c0099bd5  xor     eax, eax
0x1c0099bd7  movups  [rsp+98h+var_48], xmm0
0x1c0099bdc  movups  [rsp+98h+var_38], xmm0
0x1c0099be1  mov     [r11-28h], rax
0x1c0099be5  xor     edi, edi
0x1c0099be7  xor     ebx, ebx
0x1c0099be9  mov     [r11-78h], rbx
0x1c0099bed  movups  [rsp+98h+var_20], xmm0
0x1c0099bf2  and     [r11-68h], rax
0x1c0099bf6  call    cs:__imp_KeEnterCriticalRegion
0x1c0099bfd  nop     dword ptr [rax+rax+00h]
0x1c0099c02  lea     r8, [rsp+98h+var_68]
0x1c0099c07  lea     rdx, [rsp+98h+var_20]
0x1c0099c0c  mov     rcx, rsi
0x1c0099c0f  call    cs:__imp_IoPropagateActivityIdToThread
0x1c0099c16  nop     dword ptr [rax+rax+00h]
0x1c0099c1b  xor     ecx, ecx
0x1c0099c1d  lea     r14d, [rdi+1]
0x1c0099c21  test    eax, eax
0x1c0099c23  cmovns  ecx, r14d
0x1c0099c27  mov     [rsp+98h+var_6C], ecx
0x1c0099c2b  xor     r8d, r8d
0x1c0099c2e  xor     edx, edx
0x1c0099c30  lea     rcx, [rsp+98h+var_48]
0x1c0099c35  call    RefsInitializeTopLevelIrp
0x1c0099c3a  mov     [rsp+98h+var_58], rax
0x1c0099c3f  mov     [rsp+98h+Irp], rax
0x1c0099c44  test    rbx, rbx
0x1c0099c47  jnz     short loc_1C0099CAF
0x1c0099c49  mov     rcx, rsi; Irp
0x1c0099c4c  call    cs:__imp_IoIsOperationSynchronous
0x1c0099c53  nop     dword ptr [rax+rax+00h]
0x1c0099c58  mov     dl, al
0x1c0099c5a  lea     r9, [rsp+98h+Context]
0x1c0099c5f  mov     r8b, r14b
0x1c0099c62  mov     rcx, rsi
0x1c0099c65  call    RefsInitializeIrpContext
0x1c0099c6a  mov     rcx, [rsp+98h+Irp]; Irp
0x1c0099c6f  mov     rax, [rcx+20h]
0x1c0099c73  test    rax, rax
0x1c0099c76  jnz     short loc_1C0099CA4
0x1c0099c78  mov     dword ptr [rcx+4], 5346ABBAh
0x1c0099c7f  mov     rbx, [rsp+98h+Context]
0x1c0099c84  mov     [rcx+20h], rbx
0x1c0099c88  bts     dword ptr [rbx+8], 14h
0x1c0099c8d  call    cs:__imp_IoSetTopLevelIrp
0x1c0099c94  nop     dword ptr [rax+rax+00h]
0x1c0099c99  mov     rax, [rsp+98h+var_58]
0x1c0099c9e  mov     rax, [rax+20h]
0x1c0099ca2  jmp     short loc_1C0099CA9
0x1c0099ca4  mov     rbx, [rsp+98h+Context]
0x1c0099ca9  mov     [rbx+68h], rax
0x1c0099cad  jmp     short loc_1C0099CBF
0x1c0099caf  cmp     edi, 0C0000188h
0x1c0099cb5  jnz     short loc_1C0099CBF
0x1c0099cb7  mov     rcx, rbx
0x1c0099cba  call    RefsCheckpointForLogFileFull
0x1c0099cbf  mov     rdx, rsi; Irp
0x1c0099cc2  mov     rcx, rbx; Context
0x1c0099cc5  call    RefsCommonLockControl
0x1c0099cca  mov     edi, eax
0x1c0099ccc  mov     [rsp+98h+var_70], eax
0x1c0099cd0  jmp     short loc_1C0099D10
0x1c0099cd2  mov     r8d, eax
0x1c0099cd5  mov     rsi, [rsp+98h+var_50]
0x1c0099cda  mov     rdx, rsi
0x1c0099cdd  mov     rbx, [rsp+98h+Context]
0x1c0099ce2  mov     rcx, rbx
0x1c0099ce5  call    RefsProcessException
0x1c0099cea  mov     edi, eax
0x1c0099cec  mov     [rsp+98h+var_70], eax
0x1c0099cf0  cmp     eax, 0C00000D8h
0x1c0099cf5  jz      short loc_1C0099CFE
0x1c0099cf7  cmp     eax, 0C00001A8h
0x1c0099cfc  jnz     short loc_1C0099D09
0x1c0099cfe  mov     r14d, 1
0x1c0099d04  jmp     loc_1C0099C44
0x1c0099d09  cmp     eax, 0C0000188h
0x1c0099d0e  jz      short loc_1C0099CFE
0x1c0099d10  cmp     [rsp+98h+var_6C], 0
0x1c0099d15  jz      short loc_1C0099D28
0x1c0099d17  mov     rcx, [rsp+98h+var_68]
0x1c0099d1c  call    cs:__imp_IoClearActivityIdThread
0x1c0099d23  nop     dword ptr [rax+rax+00h]
0x1c0099d28  call    cs:__imp_KeLeaveCriticalRegion
0x1c0099d2f  nop     dword ptr [rax+rax+00h]
0x1c0099d34  mov     eax, edi
0x1c0099d36  mov     rcx, [rsp+98h+var_10]
0x1c0099d3e  xor     rcx, rsp; StackCookie
0x1c0099d41  call    __security_check_cookie
0x1c0099d46  lea     r11, [rsp+98h+var_8]
0x1c0099d4e  mov     rbx, [r11+10h]
0x1c0099d52  mov     rsi, [r11+20h]
0x1c0099d56  mov     rdi, [r11+28h]
0x1c0099d5a  mov     rsp, r11
0x1c0099d5d  pop     r14
0x1c0099d5f  retn
0x1c0099d61  push    rbp
0x1c0099d63  sub     rsp, 20h
0x1c0099d67  mov     rbp, rdx
0x1c0099d6a  mov     rdx, rcx
0x1c0099d6d  mov     rcx, [rbp+20h]
0x1c0099d71  call    RefsExceptionFilter
0x1c0099d76  nop
0x1c0099d77  add     rsp, 20h
0x1c0099d7b  pop     rbp
0x1c0099d7c  retn
```
