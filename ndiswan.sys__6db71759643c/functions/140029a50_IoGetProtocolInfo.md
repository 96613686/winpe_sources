# IoGetProtocolInfo

- ea: `0x140029a50`
- end: `0x140029b5d`
- name: `IoGetProtocolInfo`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000a5f4`
- `0x140029a50`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140029b3c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140029b3c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029aca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140029aca`

## pseudocode

```c
__int64 __fastcall IoGetProtocolInfo(__int64 a1, unsigned int a2, unsigned int *a3, unsigned int a4, _DWORD *a5)
{
  unsigned int v6; // edi
  unsigned int v7; // esi
  KIRQL v8; // al
  PKSPIN_LOCK v9; // r9
  unsigned int v10; // r8d
  unsigned int v11; // r10d
  KSPIN_LOCK v12; // rdx
  __int64 v13; // rcx

  *a5 = 516;
  if ( a4 >= 0x204 )
  {
    v6 = 0;
    v7 = 0;
    v8 = KeAcquireSpinLockRaiseToDpc(ProtocolInfoTable);
    v9 = ProtocolInfoTable;
    v10 = 0;
    v11 = *((_DWORD *)ProtocolInfoTable + 5);
    v12 = ProtocolInfoTable[5];
    *((_BYTE *)ProtocolInfoTable + 8) = v8;
    if ( v11 )
    {
      do
      {
        if ( (*(_DWORD *)(v12 + 4) & 2) != 0 )
        {
          v13 = 2LL * v7++;
          LOWORD(a3[2 * v13 + 1]) = *(_WORD *)v12;
          HIWORD(a3[2 * v13 + 1]) = *(_WORD *)(v12 + 2);
          a3[2 * v13 + 2] = *(_DWORD *)(v12 + 8);
          a3[2 * v13 + 3] = *(_DWORD *)(v12 + 12);
          a3[2 * v13 + 4] = *(_DWORD *)(v12 + 16);
        }
        ++v10;
        v12 += 20LL;
      }
      while ( v10 < v11 );
    }
    KeReleaseSpinLock(ProtocolInfoTable, *((_BYTE *)v9 + 8));
    *a3 = v7;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_5659416b879e33cc7e241cd80588418e_Traceguids, a2, 516);
    }
    return (unsigned int)-1073741820;
  }
  return v6;
}

```

## disassembly

```asm
0x140029a50  mov     [rsp+arg_0], rbx
0x140029a55  mov     [rsp+arg_8], rsi
0x140029a5a  push    rdi
0x140029a5b  sub     rsp, 30h
0x140029a5f  mov     rax, [rsp+38h+arg_20]
0x140029a64  mov     r10d, 204h
0x140029a6a  mov     rbx, r8
0x140029a6d  mov     r8d, edx
0x140029a70  mov     [rax], r10d
0x140029a73  cmp     r9d, r10d
0x140029a76  jnb     short loc_140029ABF
0x140029a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140029a7f  lea     rax, WPP_GLOBAL_Control
0x140029a86  cmp     rcx, rax
0x140029a89  jz      short loc_140029AB5
0x140029a8b  mov     eax, [rcx+2Ch]
0x140029a8e  test    al, 20h
0x140029a90  jz      short loc_140029AB5
0x140029a92  cmp     byte ptr [rcx+29h], 3
0x140029a96  jb      short loc_140029AB5
0x140029a98  mov     rcx, [rcx+18h]
0x140029a9c  mov     r9d, r8d
0x140029a9f  lea     r8, WPP_5659416b879e33cc7e241cd80588418e_Traceguids
0x140029aa6  mov     [rsp+38h+var_18], r10d
0x140029aab  mov     edx, 6Fh ; 'o'
0x140029ab0  call    WPP_SF_dd
0x140029ab5  mov     edi, 0C0000004h
0x140029aba  jmp     loc_140029B4A
0x140029abf  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140029ac6  xor     edi, edi
0x140029ac8  xor     esi, esi
0x140029aca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140029ad1  nop     dword ptr [rax+rax+00h]
0x140029ad6  mov     r9, cs:ProtocolInfoTable
0x140029add  xor     r8d, r8d
0x140029ae0  mov     r10d, [r9+14h]
0x140029ae4  mov     rdx, [r9+28h]
0x140029ae8  mov     [r9+8], al
0x140029aec  test    r10d, r10d
0x140029aef  jz      short loc_140029B31
0x140029af1  mov     eax, [rdx+4]
0x140029af4  test    al, 2
0x140029af6  jz      short loc_140029B25
0x140029af8  movzx   eax, word ptr [rdx]
0x140029afb  mov     ecx, esi
0x140029afd  add     rcx, rcx
0x140029b00  inc     esi
0x140029b02  mov     [rbx+rcx*8+4], ax
0x140029b07  movzx   eax, word ptr [rdx+2]
0x140029b0b  mov     [rbx+rcx*8+6], ax
0x140029b10  mov     eax, [rdx+8]
0x140029b13  mov     [rbx+rcx*8+8], eax
0x140029b17  mov     eax, [rdx+0Ch]
0x140029b1a  mov     [rbx+rcx*8+0Ch], eax
0x140029b1e  mov     eax, [rdx+10h]
0x140029b21  mov     [rbx+rcx*8+10h], eax
0x140029b25  inc     r8d
0x140029b28  add     rdx, 14h
0x140029b2c  cmp     r8d, r10d
0x140029b2f  jb      short loc_140029AF1
0x140029b31  mov     dl, [r9+8]; NewIrql
0x140029b35  mov     rcx, cs:ProtocolInfoTable; SpinLock
0x140029b3c  call    cs:__imp_KeReleaseSpinLock
0x140029b43  nop     dword ptr [rax+rax+00h]
0x140029b48  mov     [rbx], esi
0x140029b4a  mov     rbx, [rsp+38h+arg_0]
0x140029b4f  mov     eax, edi
0x140029b51  mov     rsi, [rsp+38h+arg_8]
0x140029b56  add     rsp, 30h
0x140029b5a  pop     rdi
0x140029b5b  retn
```
