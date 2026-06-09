# SetProtocolInfo

- ea: `0x140006e18`
- end: `0x140006ff6`
- name: `SetProtocolInfo`
- size: `478`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400010c0`
- `0x140006d9c`
- `0x14000c930`
- `0x140039b38`

## callees

- `0x140006e18`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140006f77`
- `ntoskrnl!IofCompleteRequest` at `0x140006f77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f5f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006fd9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f5f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006fd9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f8d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006e3f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006f8d`

## pseudocode

```c
void __fastcall SetProtocolInfo(__int64 a1)
{
  PKSPIN_LOCK v2; // rbx
  unsigned int v3; // r8d
  KSPIN_LOCK v4; // rdx
  unsigned int v5; // r9d
  KSPIN_LOCK v6; // rcx
  __int16 v7; // ax
  int v8; // eax
  unsigned int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  unsigned int v13; // eax
  int v14; // eax
  KSPIN_LOCK v15; // rbx
  PKSPIN_LOCK v16; // rcx
  KIRQL v17; // dl
  PKSPIN_LOCK v18; // rbx
  unsigned int i; // eax

  if ( *(_WORD *)a1 )
  {
    v2 = ProtocolInfoTable;
    *((_BYTE *)v2 + 8) = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
    v3 = 0;
    v4 = ProtocolInfoTable[5];
    v5 = *((_DWORD *)ProtocolInfoTable + 5);
    v6 = v4;
    while ( v3 < v5 )
    {
      if ( *(_WORD *)v6 == *(_WORD *)a1 )
      {
        v7 = *(_WORD *)(a1 + 2);
        if ( v7 )
          *(_WORD *)(v6 + 2) = v7;
        v8 = *(_DWORD *)(a1 + 12);
        if ( v8 )
          *(_DWORD *)(v6 + 12) = v8;
        v9 = *(_DWORD *)(a1 + 8);
        if ( v9 )
        {
          *(_DWORD *)(v6 + 8) = v9;
          if ( v9 < *(_DWORD *)(v6 + 12) )
            *(_DWORD *)(v6 + 12) = v9;
        }
        if ( *(_DWORD *)(a1 + 8) > (unsigned int)glMaxMTU )
          glMaxMTU = *(_DWORD *)(a1 + 8);
        v10 = *(_DWORD *)(a1 + 16);
        if ( v10 )
          *(_DWORD *)(v6 + 16) = v10;
        v11 = *(_DWORD *)(a1 + 4);
        if ( v11 )
        {
          if ( (v11 & 2) != 0 )
          {
            v12 = *(_DWORD *)(v6 + 4);
            if ( (v12 & 1) != 0 )
            {
              v13 = v12 & 0xFFFFFFF4 | 0xA;
              goto LABEL_24;
            }
            if ( (v12 & 2) != 0 && *(_WORD *)a1 == 2048 )
            {
              v13 = v12 | 0xE;
LABEL_24:
              *(_DWORD *)(v6 + 4) = v13;
              *((_DWORD *)ProtocolInfoTable + 6) |= 8u;
            }
          }
          if ( (*(_DWORD *)(a1 + 4) & 1) != 0 )
          {
            v14 = *(_DWORD *)(v6 + 4);
            if ( (v14 & 2) != 0 )
            {
              *(_DWORD *)(v6 + 4) = v14 & 0xFFFFFFF0 | 9;
              *((_DWORD *)ProtocolInfoTable + 6) |= 8u;
            }
          }
        }
        if ( (ProtocolInfoTable[3] & 0x18) == 8 )
        {
          v15 = ProtocolInfoTable[4];
          if ( v15 )
          {
            if ( _InterlockedExchange64((volatile __int64 *)(v15 + 104), 0) )
            {
              v16 = ProtocolInfoTable;
              v17 = *((_BYTE *)ProtocolInfoTable + 8);
              *((_DWORD *)ProtocolInfoTable + 6) |= 0x10u;
              v16[4] = 0;
              KeReleaseSpinLock(v16, v17);
              *(_DWORD *)(v15 + 48) = 0;
              *(_QWORD *)(v15 + 56) = 0;
              IofCompleteRequest((PIRP)v15, 2);
              v18 = ProtocolInfoTable;
              *((_BYTE *)v18 + 8) = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
            }
          }
        }
        goto LABEL_38;
      }
      ++v3;
      v6 += 20LL;
    }
    for ( i = 0; i < v5; ++i )
    {
      if ( !*(_WORD *)v4 )
      {
        *(_OWORD *)v4 = *(_OWORD *)a1;
        *(_DWORD *)(v4 + 16) = *(_DWORD *)(a1 + 16);
        if ( *(_DWORD *)(a1 + 8) > (unsigned int)glMaxMTU )
          glMaxMTU = *(_DWORD *)(a1 + 8);
        break;
      }
      v4 += 20LL;
    }
LABEL_38:
    KeReleaseSpinLock(ProtocolInfoTable, *((_BYTE *)ProtocolInfoTable + 8));
  }
}

```

## disassembly

```asm
0x140006e18  mov     [rsp+arg_0], rbx
0x140006e1d  mov     [rsp+arg_8], rsi
0x140006e22  push    rdi
0x140006e23  sub     rsp, 20h
0x140006e27  xor     esi, esi
0x140006e29  mov     rdi, rcx
0x140006e2c  cmp     [rcx], si
0x140006e2f  jz      loc_140006FE5
0x140006e35  mov     rbx, cs:ProtocolInfoTable
0x140006e3c  mov     rcx, rbx; SpinLock
0x140006e3f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006e46  nop     dword ptr [rax+rax+00h]
0x140006e4b  mov     [rbx+8], al
0x140006e4e  mov     r8d, esi
0x140006e51  mov     rax, cs:ProtocolInfoTable
0x140006e58  mov     rdx, [rax+28h]
0x140006e5c  mov     r9d, [rax+14h]
0x140006e60  mov     rcx, rdx
0x140006e63  cmp     r8d, r9d
0x140006e66  jnb     loc_140006F9E
0x140006e6c  movzx   eax, word ptr [rdi]
0x140006e6f  cmp     [rcx], ax
0x140006e72  jz      short loc_140006E7D
0x140006e74  inc     r8d
0x140006e77  add     rcx, 14h
0x140006e7b  jmp     short loc_140006E63
0x140006e7d  movzx   eax, word ptr [rdi+2]
0x140006e81  test    ax, ax
0x140006e84  jz      short loc_140006E8A
0x140006e86  mov     [rcx+2], ax
0x140006e8a  mov     eax, [rdi+0Ch]
0x140006e8d  test    eax, eax
0x140006e8f  jz      short loc_140006E94
0x140006e91  mov     [rcx+0Ch], eax
0x140006e94  mov     eax, [rdi+8]
0x140006e97  test    eax, eax
0x140006e99  jz      short loc_140006EA6
0x140006e9b  mov     [rcx+8], eax
0x140006e9e  cmp     eax, [rcx+0Ch]
0x140006ea1  jnb     short loc_140006EA6
0x140006ea3  mov     [rcx+0Ch], eax
0x140006ea6  mov     eax, [rdi+8]
0x140006ea9  cmp     eax, cs:glMaxMTU
0x140006eaf  jbe     short loc_140006EB7
0x140006eb1  mov     cs:glMaxMTU, eax
0x140006eb7  mov     eax, [rdi+10h]
0x140006eba  test    eax, eax
0x140006ebc  jz      short loc_140006EC1
0x140006ebe  mov     [rcx+10h], eax
0x140006ec1  mov     eax, [rdi+4]
0x140006ec4  test    eax, eax
0x140006ec6  jz      short loc_140006F1C
0x140006ec8  test    al, 2
0x140006eca  jz      short loc_140006EFA
0x140006ecc  mov     eax, [rcx+4]
0x140006ecf  test    al, 1
0x140006ed1  jz      short loc_140006EDB
0x140006ed3  and     eax, 0FFFFFFFEh
0x140006ed6  or      eax, 0Ah
0x140006ed9  jmp     short loc_140006EEC
0x140006edb  test    al, 2
0x140006edd  jz      short loc_140006EFA
0x140006edf  mov     edx, 800h
0x140006ee4  cmp     [rdi], dx
0x140006ee7  jnz     short loc_140006EFA
0x140006ee9  or      eax, 0Eh
0x140006eec  mov     [rcx+4], eax
0x140006eef  mov     rax, cs:ProtocolInfoTable
0x140006ef6  or      dword ptr [rax+18h], 8
0x140006efa  mov     eax, [rdi+4]
0x140006efd  test    al, 1
0x140006eff  jz      short loc_140006F1C
0x140006f01  mov     eax, [rcx+4]
0x140006f04  test    al, 2
0x140006f06  jz      short loc_140006F1C
0x140006f08  and     eax, 0FFFFFFF9h
0x140006f0b  or      eax, 9
0x140006f0e  mov     [rcx+4], eax
0x140006f11  mov     rax, cs:ProtocolInfoTable
0x140006f18  or      dword ptr [rax+18h], 8
0x140006f1c  mov     rbx, cs:ProtocolInfoTable
0x140006f23  mov     eax, [rbx+18h]
0x140006f26  and     al, 18h
0x140006f28  cmp     al, 8
0x140006f2a  jnz     loc_140006FCF
0x140006f30  mov     rbx, [rbx+20h]
0x140006f34  test    rbx, rbx
0x140006f37  jz      loc_140006FCF
0x140006f3d  mov     rax, rsi
0x140006f40  xchg    rax, [rbx+68h]
0x140006f44  test    rax, rax
0x140006f47  jz      loc_140006FCF
0x140006f4d  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140006f54  mov     dl, [rcx+8]; NewIrql
0x140006f57  or      dword ptr [rcx+18h], 10h
0x140006f5b  mov     [rcx+20h], rsi
0x140006f5f  call    cs:__imp_KeReleaseSpinLock
0x140006f66  nop     dword ptr [rax+rax+00h]
0x140006f6b  mov     dl, 2; PriorityBoost
0x140006f6d  mov     [rbx+30h], esi
0x140006f70  mov     rcx, rbx; Irp
0x140006f73  mov     [rbx+38h], rsi
0x140006f77  call    cs:__imp_IofCompleteRequest
0x140006f7e  nop     dword ptr [rax+rax+00h]
0x140006f83  mov     rbx, cs:ProtocolInfoTable
0x140006f8a  mov     rcx, rbx; SpinLock
0x140006f8d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006f94  nop     dword ptr [rax+rax+00h]
0x140006f99  mov     [rbx+8], al
0x140006f9c  jmp     short loc_140006FCF
0x140006f9e  mov     eax, esi
0x140006fa0  cmp     eax, r9d
0x140006fa3  jnb     short loc_140006FCF
0x140006fa5  cmp     [rdx], si
0x140006fa8  jz      short loc_140006FB2
0x140006faa  inc     eax
0x140006fac  add     rdx, 14h
0x140006fb0  jmp     short loc_140006FA0
0x140006fb2  movups  xmm0, xmmword ptr [rdi]
0x140006fb5  movups  xmmword ptr [rdx], xmm0
0x140006fb8  mov     eax, [rdi+10h]
0x140006fbb  mov     [rdx+10h], eax
0x140006fbe  mov     eax, [rdi+8]
0x140006fc1  cmp     eax, cs:glMaxMTU
0x140006fc7  jbe     short loc_140006FCF
0x140006fc9  mov     cs:glMaxMTU, eax
0x140006fcf  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140006fd6  mov     dl, [rcx+8]; NewIrql
0x140006fd9  call    cs:__imp_KeReleaseSpinLock
0x140006fe0  nop     dword ptr [rax+rax+00h]
0x140006fe5  mov     rbx, [rsp+28h+arg_0]
0x140006fea  mov     rsi, [rsp+28h+arg_8]
0x140006fef  add     rsp, 20h
0x140006ff3  pop     rdi
0x140006ff4  retn
```
