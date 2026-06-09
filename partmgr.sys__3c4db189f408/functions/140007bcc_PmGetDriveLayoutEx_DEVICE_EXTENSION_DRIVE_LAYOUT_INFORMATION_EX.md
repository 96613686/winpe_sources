# PmGetDriveLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX * *)

- ea: `0x140007bcc`
- end: `0x140007f68`
- name: `?PmGetDriveLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z`
- size: `924`
- prototype: `__int64 __fastcall(KSPIN_LOCK *, struct _DRIVE_LAYOUT_INFORMATION_EX **)`
- caller_count: `27`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140007674`
- `0x14000c730`
- `0x14001c3d8`
- `0x14001ca0c`
- `0x14001d25c`
- `0x14001d370`
- `0x14001d538`
- `0x14001d604`
- `0x14001da78`
- `0x14001dc08`
- `0x14001de70`
- `0x14001e2bc`
- `0x14001ec94`
- `0x14001f5c4`
- `0x14001f650`
- `0x1400208c8`
- `0x140020afc`
- `0x140020ba8`
- `0x140020ce0`
- `0x140021970`
- `0x140021c90`
- `0x14002470c`
- `0x140024b3c`
- `0x140024bf8`
- `0x140024d04`
- `0x140025ab8`
- `0x140026640`

## callees

- `0x140004ef8`
- `0x140005b2c`
- `0x1400060ac`
- `0x1400066a0`
- `0x140007bcc`
- `0x14000a760`
- `0x140011140`
- `0x140023310`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007f3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007f3d`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140007c1a`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x140007c1a`
- `ntoskrnl!ExAllocatePool2` at `0x140007e84`
- `ntoskrnl!ExAllocatePool2` at `0x140007e84`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c41`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007ca3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007e02`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f27`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007c41`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007ca3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007e02`
- `ntoskrnl!KeReleaseSpinLock` at `0x140007f27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007bf9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007dd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ebc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007bf9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007c58`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007dd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007ebc`

## string_xrefs

- `0x140007cd8`: `PartitionTableCache`

## pseudocode

```c
__int64 __fastcall PmGetDriveLayoutEx(KSPIN_LOCK *a1, struct _DRIVE_LAYOUT_INFORMATION_EX **a2)
{
  signed int updated; // esi
  KSPIN_LOCK *v5; // r15
  KIRQL v6; // di
  KIRQL v7; // al
  unsigned __int64 v8; // r14
  KIRQL v9; // dl
  __int64 v10; // rbp
  unsigned int v11; // eax
  size_t v12; // r12
  int Layout; // eax
  int v14; // ecx
  int v15; // edi
  int v16; // edi
  int v17; // r9d
  char v18; // r12
  __int64 v19; // r10
  __int64 v20; // r9
  int v21; // r10d
  char v22; // r11
  __int64 v23; // r9
  __int64 v24; // r11
  KIRQL v25; // al
  unsigned int v26; // ecx
  unsigned __int64 v27; // rax
  unsigned int v28; // eax
  struct _DRIVE_LAYOUT_INFORMATION_EX *Pool2; // rax
  struct _DRIVE_LAYOUT_INFORMATION_EX *v30; // rdi
  KIRQL v31; // di
  unsigned __int64 QpcTimeStamp; // [rsp+60h] [rbp+8h] BYREF
  int v34; // [rsp+68h] [rbp+10h]

  updated = 0;
  if ( a2 )
    *a2 = 0;
  v5 = a1 + 14;
  v6 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  if ( *((int *)a1 + 278) < 0 )
  {
    QpcTimeStamp = 0;
    if ( KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp) - a1[140] < 0x11E1A300 )
      updated = *((_DWORD *)a1 + 278);
  }
  KeReleaseSpinLock(v5, v6);
  if ( updated >= 0 )
  {
    v7 = KeAcquireSpinLockRaiseToDpc(v5);
    v8 = a1[138];
    a1[138] = 0;
    v9 = v7;
    v10 = 1;
    LODWORD(v12) = *((_DWORD *)a1 + 129) >> 3;
    v11 = *((_DWORD *)a1 + 129) & 0xFFFFFFF7;
    LOBYTE(v12) = (*((_DWORD *)a1 + 129) & 8) != 0;
    QpcTimeStamp = v8;
    v34 = v12;
    *((_DWORD *)a1 + 129) = v11;
    KeReleaseSpinLock(v5, v9);
    if ( !v8 )
    {
      Layout = PmGetLayout((struct _DEVICE_EXTENSION *)a1, (struct SC_DISK_LAYOUT **)&QpcTimeStamp);
      v8 = QpcTimeStamp;
      updated = Layout;
      if ( Layout < 0 )
        goto LABEL_47;
      v14 = *(_DWORD *)(QpcTimeStamp + 4);
      LOBYTE(v12) = 0;
      v34 = v12;
      PmSetDeviceParameterBinary(
        (struct _DEVICE_EXTENSION *)a1,
        L"PartitionTableCache",
        (void *)QpcTimeStamp,
        144 * v14 + 48);
      v15 = 0;
      if ( !*(_DWORD *)v8 && *(_DWORD *)(v8 + 4) == 1 && !*(_QWORD *)(v8 + 56) )
        v15 = *(_QWORD *)(v8 + 64) != 0;
      v16 = v15 << 13;
      if ( PmEnforceService((struct _DEVICE_EXTENSION *)a1) && v17 == 1 )
      {
        v18 = 0;
        v19 = 0;
        LOBYTE(QpcTimeStamp) = 0;
        if ( !*(_DWORD *)(v8 + 4) )
          goto LABEL_27;
        while ( 1 )
        {
          if ( !SC_PART_ENTRY::IsUnused((SC_PART_ENTRY *)(v8 + 144 * v19 + 48)) )
          {
            if ( *(_DWORD *)(v20 + 48) == 1 )
            {
              if ( SC_PART_ENTRY::IsRecognized((SC_PART_ENTRY *)(v20 + 48)) )
              {
                if ( (v24 & 0x200000000000000LL) != 0 )
                  goto LABEL_26;
              }
              else if ( (v24 & 1) != 0 )
              {
LABEL_26:
                v22 = QpcTimeStamp;
                v18 = 1;
                *(_BYTE *)(v23 + 77) = 1;
                goto LABEL_21;
              }
            }
            v22 = 1;
            LOBYTE(QpcTimeStamp) = 1;
          }
LABEL_21:
          v19 = (unsigned int)(v21 + 1);
          if ( (unsigned int)v19 >= *(_DWORD *)(v8 + 4) )
          {
            if ( v18 )
            {
              LODWORD(v12) = v34;
              if ( !v22 )
                v16 |= 0x4000u;
              break;
            }
LABEL_27:
            LODWORD(v12) = v34;
            break;
          }
        }
      }
      if ( (*((_DWORD *)a1 + 129) & 0x6000) != v16 )
      {
        v25 = KeAcquireSpinLockRaiseToDpc(v5);
        *((_DWORD *)a1 + 129) &= 0xFFFF9FFF;
        *((_DWORD *)a1 + 129) |= v16;
        KeReleaseSpinLock(v5, v25);
      }
    }
    if ( (*((_DWORD *)a1 + 129) & 1) != 0 && !(_BYTE)v12 )
    {
      updated = PmUpdateLayoutEx((struct _DEVICE_EXTENSION *)a1, (struct _DRIVE_LAYOUT_INFORMATION_EX *)v8);
      if ( updated < 0 )
        goto LABEL_47;
      LOBYTE(v12) = 1;
      v34 = v12;
    }
    if ( a2 )
    {
      v26 = -1;
      v27 = 144LL * *(unsigned int *)(v8 + 4);
      if ( v27 > 0xFFFFFFFF )
      {
        updated = -1073741675;
LABEL_47:
        if ( v8 )
          ExFreePoolWithTag((PVOID)v8, 0);
        return (unsigned int)updated;
      }
      v28 = v27 + 48;
      if ( v28 >= 0x30 )
        v26 = v28;
      updated = v28 < 0x30 ? 0xC0000095 : 0;
      if ( v28 < 0x30 )
        goto LABEL_47;
      v12 = v26;
      Pool2 = (struct _DRIVE_LAYOUT_INFORMATION_EX *)ExAllocatePool2(66, v26, 1414557008);
      v30 = Pool2;
      if ( !Pool2 )
      {
        updated = -1073741670;
        goto LABEL_47;
      }
      memmove(Pool2, (const void *)v8, v12);
      LOBYTE(v12) = v34;
      *a2 = v30;
    }
    v31 = KeAcquireSpinLockRaiseToDpc(v5);
    if ( !*(_DWORD *)(v8 + 4) )
      v10 = 0;
    memmove(a1 + 114, (const void *)v8, 144 * v10 + 48);
    a1[138] = v8;
    v8 = 0;
    if ( (_BYTE)v12 )
      *((_DWORD *)a1 + 129) |= 8u;
    *((_DWORD *)a1 + 278) = updated;
    a1[140] = 0;
    KeReleaseSpinLock(v5, v31);
    goto LABEL_47;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140007bcc  mov     [rsp+arg_10], rbx
0x140007bd1  push    rbp
0x140007bd2  push    rsi
0x140007bd3  push    rdi
0x140007bd4  push    r12
0x140007bd6  push    r13
0x140007bd8  push    r14
0x140007bda  push    r15
0x140007bdc  sub     rsp, 20h
0x140007be0  xor     ebp, ebp
0x140007be2  mov     r13, rdx
0x140007be5  mov     rbx, rcx
0x140007be8  mov     esi, ebp
0x140007bea  test    rdx, rdx
0x140007bed  jz      short loc_140007BF2
0x140007bef  mov     [rdx], rbp
0x140007bf2  lea     r15, [rcx+70h]
0x140007bf6  mov     rcx, r15; SpinLock
0x140007bf9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c00  nop     dword ptr [rax+rax+00h]
0x140007c05  mov     dil, al
0x140007c08  cmp     [rbx+458h], ebp
0x140007c0e  jge     short loc_140007C3B
0x140007c10  lea     rcx, [rsp+58h+QpcTimeStamp]; QpcTimeStamp
0x140007c15  mov     [rsp+58h+QpcTimeStamp], rbp
0x140007c1a  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x140007c21  nop     dword ptr [rax+rax+00h]
0x140007c26  sub     rax, [rbx+460h]
0x140007c2d  cmp     rax, 11E1A300h
0x140007c33  jnb     short loc_140007C3B
0x140007c35  mov     esi, [rbx+458h]
0x140007c3b  mov     dl, dil; NewIrql
0x140007c3e  mov     rcx, r15; SpinLock
0x140007c41  call    cs:__imp_KeReleaseSpinLock
0x140007c48  nop     dword ptr [rax+rax+00h]
0x140007c4d  test    esi, esi
0x140007c4f  js      loc_140007F49
0x140007c55  mov     rcx, r15; SpinLock
0x140007c58  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007c5f  nop     dword ptr [rax+rax+00h]
0x140007c64  mov     r14, [rbx+450h]
0x140007c6b  mov     rcx, r15; SpinLock
0x140007c6e  mov     [rbx+450h], rbp
0x140007c75  mov     dl, al; NewIrql
0x140007c77  mov     r12d, [rbx+204h]
0x140007c7e  mov     ebp, 1
0x140007c83  mov     eax, [rbx+204h]
0x140007c89  shr     r12d, 3
0x140007c8d  and     eax, 0FFFFFFF7h
0x140007c90  and     r12b, bpl
0x140007c93  mov     [rsp+58h+QpcTimeStamp], r14
0x140007c98  mov     [rsp+58h+arg_8], r12d
0x140007c9d  mov     [rbx+204h], eax
0x140007ca3  call    cs:__imp_KeReleaseSpinLock
0x140007caa  nop     dword ptr [rax+rax+00h]
0x140007caf  test    r14, r14
0x140007cb2  jnz     loc_140007E0E
0x140007cb8  lea     rdx, [rsp+58h+QpcTimeStamp]; struct SC_DISK_LAYOUT **
0x140007cbd  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007cc0  call    ?PmGetLayout@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAVSC_DISK_LAYOUT@@@Z; PmGetLayout(_DEVICE_EXTENSION *,SC_DISK_LAYOUT * *)
0x140007cc5  mov     r14, [rsp+58h+QpcTimeStamp]
0x140007cca  mov     esi, eax
0x140007ccc  test    eax, eax
0x140007cce  js      loc_140007F33
0x140007cd4  mov     ecx, [r14+4]
0x140007cd8  lea     rdx, aPartitiontable; "PartitionTableCache"
0x140007cdf  xor     r12b, r12b
0x140007ce2  mov     r8, r14; void *
0x140007ce5  mov     [rsp+58h+arg_8], r12d
0x140007cea  lea     r9d, [rcx+rcx*8]
0x140007cee  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007cf1  shl     r9d, 4
0x140007cf5  add     r9d, 30h ; '0'; unsigned int
0x140007cf9  call    ?PmSetDeviceParameterBinary@@YAJPEAU_DEVICE_EXTENSION@@PEAGPEAXK@Z; PmSetDeviceParameterBinary(_DEVICE_EXTENSION *,ushort *,void *,ulong)
0x140007cfe  mov     r9d, [r14]
0x140007d01  xor     edi, edi
0x140007d03  test    r9d, r9d
0x140007d06  jnz     short loc_140007D1B
0x140007d08  cmp     [r14+4], ebp
0x140007d0c  jnz     short loc_140007D1B
0x140007d0e  cmp     [r14+38h], rdi
0x140007d12  jnz     short loc_140007D1B
0x140007d14  cmp     [r14+40h], rdi
0x140007d18  cmovnz  edi, ebp
0x140007d1b  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007d1e  shl     edi, 0Dh
0x140007d21  call    ?PmEnforceService@@YAEPEAU_DEVICE_EXTENSION@@@Z; PmEnforceService(_DEVICE_EXTENSION *)
0x140007d26  test    al, al
0x140007d28  jz      loc_140007DBF
0x140007d2e  cmp     r9d, ebp
0x140007d31  jnz     loc_140007DBF
0x140007d37  xor     r11b, r11b
0x140007d3a  xor     r12b, r12b
0x140007d3d  xor     r10d, r10d
0x140007d40  mov     byte ptr [rsp+58h+QpcTimeStamp], r11b
0x140007d45  cmp     [r14+4], r10d
0x140007d49  jbe     short loc_140007DBA
0x140007d4b  lea     r9, [r10+r10*8]
0x140007d4f  shl     r9, 4
0x140007d53  add     r9, r14
0x140007d56  lea     rcx, [r9+30h]; this
0x140007d5a  call    ?IsUnused@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsUnused(void)
0x140007d5f  test    al, al
0x140007d61  jnz     short loc_140007D89
0x140007d63  cmp     [r9+30h], ebp
0x140007d67  jnz     short loc_140007D81
0x140007d69  mov     r11, [r9+70h]
0x140007d6d  lea     rcx, [r9+30h]; this
0x140007d71  call    ?IsRecognized@SC_PART_ENTRY@@QEAAEXZ; SC_PART_ENTRY::IsRecognized(void)
0x140007d76  test    al, al
0x140007d78  jz      short loc_140007DA7
0x140007d7a  bt      r11, 39h ; '9'
0x140007d7f  jb      short loc_140007DAC
0x140007d81  mov     r11b, bpl
0x140007d84  mov     byte ptr [rsp+58h+QpcTimeStamp], bpl
0x140007d89  add     r10d, ebp
0x140007d8c  cmp     r10d, [r14+4]
0x140007d90  jb      short loc_140007D4B
0x140007d92  test    r12b, r12b
0x140007d95  jz      short loc_140007DBA
0x140007d97  mov     r12d, [rsp+58h+arg_8]
0x140007d9c  test    r11b, r11b
0x140007d9f  jnz     short loc_140007DBF
0x140007da1  bts     edi, 0Eh
0x140007da5  jmp     short loc_140007DBF
0x140007da7  test    bpl, r11b
0x140007daa  jz      short loc_140007D81
0x140007dac  mov     r11b, byte ptr [rsp+58h+QpcTimeStamp]
0x140007db1  mov     r12b, bpl
0x140007db4  mov     [r9+4Dh], bpl
0x140007db8  jmp     short loc_140007D89
0x140007dba  mov     r12d, [rsp+58h+arg_8]
0x140007dbf  mov     eax, [rbx+204h]
0x140007dc5  and     eax, 6000h
0x140007dca  cmp     eax, edi
0x140007dcc  jz      short loc_140007E0E
0x140007dce  mov     rcx, r15; SpinLock
0x140007dd1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007dd8  nop     dword ptr [rax+rax+00h]
0x140007ddd  mov     ecx, [rbx+204h]
0x140007de3  mov     dl, al; NewIrql
0x140007de5  and     ecx, 0FFFF9FFFh
0x140007deb  mov     [rbx+204h], ecx
0x140007df1  mov     ecx, [rbx+204h]
0x140007df7  or      ecx, edi
0x140007df9  mov     [rbx+204h], ecx
0x140007dff  mov     rcx, r15; SpinLock
0x140007e02  call    cs:__imp_KeReleaseSpinLock
0x140007e09  nop     dword ptr [rax+rax+00h]
0x140007e0e  mov     eax, [rbx+204h]
0x140007e14  test    bpl, al
0x140007e17  jz      short loc_140007E3B
0x140007e19  test    r12b, r12b
0x140007e1c  jnz     short loc_140007E3B
0x140007e1e  mov     rdx, r14; struct _DRIVE_LAYOUT_INFORMATION_EX *
0x140007e21  mov     rcx, rbx; struct _DEVICE_EXTENSION *
0x140007e24  call    ?PmUpdateLayoutEx@@YAJPEAU_DEVICE_EXTENSION@@PEAU_DRIVE_LAYOUT_INFORMATION_EX@@@Z; PmUpdateLayoutEx(_DEVICE_EXTENSION *,_DRIVE_LAYOUT_INFORMATION_EX *)
0x140007e29  mov     esi, eax
0x140007e2b  test    eax, eax
0x140007e2d  js      loc_140007F33
0x140007e33  mov     r12b, bpl
0x140007e36  mov     [rsp+58h+arg_8], r12d
0x140007e3b  test    r13, r13
0x140007e3e  jz      short loc_140007EB9
0x140007e40  mov     eax, [r14+4]
0x140007e44  mov     ecx, 0FFFFFFFFh
0x140007e49  lea     rax, [rax+rax*8]
0x140007e4d  shl     rax, 4
0x140007e51  cmp     rax, rcx
0x140007e54  ja      loc_140007F61
0x140007e5a  add     eax, 30h ; '0'
0x140007e5d  cmp     eax, 30h ; '0'
0x140007e60  cmovnb  ecx, eax
0x140007e63  sbb     esi, esi
0x140007e65  and     esi, 0C0000095h
0x140007e6b  cmp     eax, 30h ; '0'
0x140007e6e  jb      loc_140007F33
0x140007e74  mov     r12d, ecx
0x140007e77  mov     r8d, 54506D50h
0x140007e7d  mov     edx, ecx
0x140007e7f  mov     ecx, 42h ; 'B'
0x140007e84  call    cs:__imp_ExAllocatePool2
0x140007e8b  nop     dword ptr [rax+rax+00h]
0x140007e90  mov     rdi, rax
0x140007e93  test    rax, rax
0x140007e96  jnz     short loc_140007EA2
0x140007e98  mov     esi, 0C000009Ah
0x140007e9d  jmp     loc_140007F33
0x140007ea2  mov     r8, r12; Size
0x140007ea5  mov     rdx, r14; Src
0x140007ea8  mov     rcx, rdi; void *
0x140007eab  call    memmove
0x140007eb0  mov     r12d, [rsp+58h+arg_8]
0x140007eb5  mov     [r13+0], rdi
0x140007eb9  mov     rcx, r15; SpinLock
0x140007ebc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007ec3  nop     dword ptr [rax+rax+00h]
0x140007ec8  mov     ecx, [r14+4]
0x140007ecc  mov     rdx, r14; Src
0x140007ecf  cmp     ecx, ebp
0x140007ed1  mov     dil, al
0x140007ed4  cmovb   ebp, ecx
0x140007ed7  lea     rcx, [rbx+390h]; void *
0x140007ede  lea     r8, ds:0[rbp*8]
0x140007ee6  add     r8, rbp
0x140007ee9  shl     r8, 4
0x140007eed  add     r8, 30h ; '0'; Size
0x140007ef1  call    memmove
0x140007ef6  mov     [rbx+450h], r14
0x140007efd  xor     r14d, r14d
0x140007f00  test    r12b, r12b
0x140007f03  jz      short loc_140007F14
0x140007f05  mov     eax, [rbx+204h]
0x140007f0b  or      eax, 8
0x140007f0e  mov     [rbx+204h], eax
0x140007f14  mov     dl, dil; NewIrql
0x140007f17  mov     [rbx+458h], esi
0x140007f1d  mov     rcx, r15; SpinLock
0x140007f20  mov     [rbx+460h], r14
0x140007f27  call    cs:__imp_KeReleaseSpinLock
0x140007f2e  nop     dword ptr [rax+rax+00h]
0x140007f33  test    r14, r14
0x140007f36  jz      short loc_140007F49
0x140007f38  xor     edx, edx; Tag
0x140007f3a  mov     rcx, r14; P
0x140007f3d  call    cs:__imp_ExFreePoolWithTag
0x140007f44  nop     dword ptr [rax+rax+00h]
0x140007f49  mov     rbx, [rsp+58h+arg_10]
0x140007f4e  mov     eax, esi
0x140007f50  add     rsp, 20h
0x140007f54  pop     r15
0x140007f56  pop     r14
0x140007f58  pop     r13
0x140007f5a  pop     r12
0x140007f5c  pop     rdi
0x140007f5d  pop     rsi
0x140007f5e  pop     rbp
0x140007f5f  retn
0x140007f61  mov     esi, 0C0000095h
0x140007f66  jmp     short loc_140007F33
```
