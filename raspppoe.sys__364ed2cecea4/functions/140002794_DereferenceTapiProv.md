# DereferenceTapiProv

- ea: `0x140002794`
- end: `0x1400028c5`
- name: `DereferenceTapiProv`
- size: `305`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140001608`
- `0x140003d18`
- `0x140010e50`
- `0x14001169c`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400011b4`
- `0x140002794`
- `0x140003c44`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000280b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000280b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400027de`

## pseudocode

```c
void __fastcall DereferenceTapiProv(__int64 a1)
{
  char v2; // si
  KIRQL v3; // al
  bool v4; // zf
  int v5; // ebp

  v2 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xCu, (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
  v4 = (*(_DWORD *)(a1 + 80))-- == 1;
  v5 = *(_DWORD *)(a1 + 80);
  *(_BYTE *)(a1 + 16) = v3;
  if ( v4 )
  {
    v2 = 1;
    *(_DWORD *)(a1 + 84) = *(_DWORD *)(a1 + 84) & 0xFFFFFFF8 | 4;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), v3);
  if ( !v2 )
    goto LABEL_16;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x2Eu,
      (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
  }
  TpProviderCleanup(a1);
  DereferenceAdapter(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Fu,
        (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids);
LABEL_16:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xDu,
        (__int64)WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids,
        v5);
    }
  }
}

```

## disassembly

```asm
0x140002794  push    rbx
0x140002796  push    rbp
0x140002797  push    rsi
0x140002798  push    rdi
0x140002799  push    r15
0x14000279b  sub     rsp, 20h
0x14000279f  mov     rbx, rcx
0x1400027a2  xor     sil, sil
0x1400027a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400027ac  lea     r15, WPP_GLOBAL_Control
0x1400027b3  cmp     rcx, r15
0x1400027b6  jz      short loc_1400027DA
0x1400027b8  mov     eax, [rcx+2Ch]
0x1400027bb  test    al, 2
0x1400027bd  jz      short loc_1400027DA
0x1400027bf  cmp     byte ptr [rcx+29h], 4
0x1400027c3  jb      short loc_1400027DA
0x1400027c5  mov     rcx, [rcx+18h]
0x1400027c9  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x1400027d0  mov     edx, 0Ch
0x1400027d5  call    WPP_SF_
0x1400027da  lea     rcx, [rbx+8]; SpinLock
0x1400027de  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400027e5  nop     dword ptr [rax+rax+00h]
0x1400027ea  sub     dword ptr [rbx+50h], 1
0x1400027ee  mov     ebp, [rbx+50h]
0x1400027f1  mov     [rbx+10h], al
0x1400027f4  jnz     short loc_140002805
0x1400027f6  mov     edx, [rbx+54h]
0x1400027f9  mov     sil, 1
0x1400027fc  and     edx, 0FFFFFFFCh
0x1400027ff  or      edx, 4
0x140002802  mov     [rbx+54h], edx
0x140002805  mov     dl, al; NewIrql
0x140002807  lea     rcx, [rbx+8]; SpinLock
0x14000280b  call    cs:__imp_KeReleaseSpinLock
0x140002812  nop     dword ptr [rax+rax+00h]
0x140002817  test    sil, sil
0x14000281a  jz      short loc_140002888
0x14000281c  mov     rcx, cs:WPP_GLOBAL_Control
0x140002823  cmp     rcx, r15
0x140002826  jz      short loc_14000284A
0x140002828  mov     eax, [rcx+2Ch]
0x14000282b  test    al, 2
0x14000282d  jz      short loc_14000284A
0x14000282f  cmp     byte ptr [rcx+29h], 3
0x140002833  jb      short loc_14000284A
0x140002835  mov     rcx, [rcx+18h]
0x140002839  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x140002840  mov     edx, 2Eh ; '.'
0x140002845  call    WPP_SF_
0x14000284a  mov     rcx, rbx
0x14000284d  call    TpProviderCleanup
0x140002852  mov     rcx, rbx
0x140002855  call    DereferenceAdapter
0x14000285a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002861  cmp     rcx, r15
0x140002864  jz      short loc_1400028B9
0x140002866  mov     eax, [rcx+2Ch]
0x140002869  test    al, 2
0x14000286b  jz      short loc_140002888
0x14000286d  cmp     byte ptr [rcx+29h], 3
0x140002871  jb      short loc_140002888
0x140002873  mov     rcx, [rcx+18h]
0x140002877  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x14000287e  mov     edx, 2Fh ; '/'
0x140002883  call    WPP_SF_
0x140002888  mov     rcx, cs:WPP_GLOBAL_Control
0x14000288f  cmp     rcx, r15
0x140002892  jz      short loc_1400028B9
0x140002894  mov     eax, [rcx+2Ch]
0x140002897  test    al, 2
0x140002899  jz      short loc_1400028B9
0x14000289b  cmp     byte ptr [rcx+29h], 4
0x14000289f  jb      short loc_1400028B9
0x1400028a1  mov     rcx, [rcx+18h]
0x1400028a5  lea     r8, WPP_eede4ab680e836baf17aa34f2eb64c0f_Traceguids
0x1400028ac  mov     edx, 0Dh
0x1400028b1  mov     r9d, ebp
0x1400028b4  call    WPP_SF_d
0x1400028b9  add     rsp, 20h
0x1400028bd  pop     r15
0x1400028bf  pop     rdi
0x1400028c0  pop     rsi
0x1400028c1  pop     rbp
0x1400028c2  pop     rbx
0x1400028c3  retn
```
