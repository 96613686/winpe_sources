# DrDeviceManager::OnDeviceListRemove(tagRDPDR_HEADER *,ulong,int *)

- ea: `0x1400205a8`
- end: `0x140020782`
- name: `?OnDeviceListRemove@DrDeviceManager@@AEAAJPEAUtagRDPDR_HEADER@@KPEAH@Z`
- size: `474`
- prototype: `__int64 __fastcall(DrSession **this, struct tagRDPDR_HEADER *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001ff80`

## callees

- `0x14000324c`
- `0x14000327c`
- `0x1400065c0`
- `0x1400205a8`
- `0x140020788`
- `0x140023cf0`

## pseudocode

```c
__int64 __fastcall DrDeviceManager::OnDeviceListRemove(
        DrSession **this,
        struct tagRDPDR_HEADER *a2,
        unsigned int a3,
        int *a4)
{
  __int64 v5; // rdi
  unsigned int v8; // r8d
  unsigned int v9; // esi
  struct tagRDPDR_DEVICE_REMOVE *v10; // r13
  char *v11; // r15
  unsigned int v13; // r15d
  unsigned int v14; // esi

  v5 = a3;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids, a3);
  v8 = 12;
  *a4 = 0;
  if ( (unsigned int)v5 < 0xC )
    return (unsigned int)DrSession::ReadMore(this[24], v5, v8) == 0 ? 0xC0000001 : 0;
  v9 = *((_DWORD *)a2 + 1);
  v10 = (struct tagRDPDR_HEADER *)((char *)a2 + 8);
  v11 = (char *)a2 + v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids, v9);
  if ( v9 )
  {
    while ( (char *)v10 + 4 <= v11 )
    {
      DrDeviceManager::ProcessDeviceRemove((DrDeviceManager *)this, v10);
      v10 = (struct tagRDPDR_DEVICE_REMOVE *)((char *)v10 + 4);
      if ( !--v9 )
        goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
    if ( v9 < *((_DWORD *)a2 + 1) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
      v13 = (_DWORD)v11 - (_DWORD)v10;
      memmove((char *)a2 + 8, v10, v13);
      *((_DWORD *)a2 + 1) = v9;
      LODWORD(v5) = v13 + 8;
    }
    v14 = 4 * v9;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids, v14);
    v8 = v14;
    return (unsigned int)DrSession::ReadMore(this[24], v5, v8) == 0 ? 0xC0000001 : 0;
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids);
  *a4 = 1;
  return 0;
}

```

## disassembly

```asm
0x1400205a8  push    rbx
0x1400205aa  push    rbp
0x1400205ab  push    rsi
0x1400205ac  push    rdi
0x1400205ad  push    r12
0x1400205af  push    r13
0x1400205b1  push    r14
0x1400205b3  push    r15
0x1400205b5  sub     rsp, 28h
0x1400205b9  mov     rbx, r9
0x1400205bc  mov     edi, r8d
0x1400205bf  mov     rbp, rdx
0x1400205c2  mov     r12, rcx
0x1400205c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400205cc  lea     rdx, WPP_GLOBAL_Control
0x1400205d3  cmp     rcx, rdx
0x1400205d6  jz      short loc_1400205FD
0x1400205d8  cmp     byte ptr [rcx+29h], 4
0x1400205dc  jb      short loc_1400205FD
0x1400205de  mov     rcx, [rcx+18h]
0x1400205e2  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x1400205e9  mov     edx, 1Ah
0x1400205ee  mov     r9d, edi
0x1400205f1  call    WPP_SF_d
0x1400205f6  lea     rdx, WPP_GLOBAL_Control
0x1400205fd  mov     r8d, 0Ch
0x140020603  mov     dword ptr [rbx], 0
0x140020609  cmp     edi, r8d
0x14002060c  jb      loc_140020756
0x140020612  mov     esi, [rbp+4]
0x140020615  lea     r13, [rbp+8]
0x140020619  lea     r15, [rdi+rbp]
0x14002061d  mov     rcx, cs:WPP_GLOBAL_Control
0x140020624  cmp     rcx, rdx
0x140020627  jz      short loc_140020646
0x140020629  cmp     byte ptr [rcx+29h], 4
0x14002062d  jb      short loc_140020646
0x14002062f  mov     rcx, [rcx+18h]
0x140020633  lea     edx, [r8+0Fh]
0x140020637  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x14002063e  mov     r9d, esi
0x140020641  call    WPP_SF_d
0x140020646  test    esi, esi
0x140020648  jz      short loc_140020666
0x14002064a  lea     r14, [r13+4]
0x14002064e  cmp     r14, r15
0x140020651  ja      short loc_1400206A1
0x140020653  mov     rdx, r13; struct tagRDPDR_DEVICE_REMOVE *
0x140020656  mov     rcx, r12; this
0x140020659  call    ?ProcessDeviceRemove@DrDeviceManager@@AEAAXPEAUtagRDPDR_DEVICE_REMOVE@@@Z; DrDeviceManager::ProcessDeviceRemove(tagRDPDR_DEVICE_REMOVE *)
0x14002065e  mov     r13, r14
0x140020661  add     esi, 0FFFFFFFFh
0x140020664  jnz     short loc_14002064A
0x140020666  mov     rcx, cs:WPP_GLOBAL_Control
0x14002066d  lea     rax, WPP_GLOBAL_Control
0x140020674  cmp     rcx, rax
0x140020677  jz      short loc_140020694
0x140020679  cmp     byte ptr [rcx+29h], 4
0x14002067d  jb      short loc_140020694
0x14002067f  mov     rcx, [rcx+18h]
0x140020683  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x14002068a  mov     edx, 1Ch
0x14002068f  call    WPP_SF_
0x140020694  mov     dword ptr [rbx], 1
0x14002069a  xor     eax, eax
0x14002069c  jmp     loc_140020770
0x1400206a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206a8  lea     rdx, WPP_GLOBAL_Control
0x1400206af  cmp     rcx, rdx
0x1400206b2  jz      short loc_1400206D6
0x1400206b4  cmp     byte ptr [rcx+29h], 4
0x1400206b8  jb      short loc_1400206D6
0x1400206ba  mov     rcx, [rcx+18h]
0x1400206be  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x1400206c5  mov     edx, 1Dh
0x1400206ca  call    WPP_SF_
0x1400206cf  lea     rdx, WPP_GLOBAL_Control
0x1400206d6  cmp     esi, [rbp+4]
0x1400206d9  jnb     short loc_14002071F
0x1400206db  lea     rdi, [rbp+8]
0x1400206df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400206e6  cmp     rcx, rdx
0x1400206e9  jz      short loc_140020706
0x1400206eb  cmp     byte ptr [rcx+29h], 4
0x1400206ef  jb      short loc_140020706
0x1400206f1  mov     rcx, [rcx+18h]
0x1400206f5  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x1400206fc  mov     edx, 1Eh
0x140020701  call    WPP_SF_
0x140020706  sub     r15d, r13d
0x140020709  mov     rdx, r13; Src
0x14002070c  mov     r8d, r15d; Size
0x14002070f  mov     rcx, rdi; void *
0x140020712  call    memmove
0x140020717  sub     edi, ebp
0x140020719  mov     [rbp+4], esi
0x14002071c  add     edi, r15d
0x14002071f  shl     esi, 2
0x140020722  mov     rcx, cs:WPP_GLOBAL_Control
0x140020729  lea     rax, WPP_GLOBAL_Control
0x140020730  cmp     rcx, rax
0x140020733  jz      short loc_140020753
0x140020735  cmp     byte ptr [rcx+29h], 4
0x140020739  jb      short loc_140020753
0x14002073b  mov     rcx, [rcx+18h]
0x14002073f  lea     r8, WPP_ca599e18d9603d4a21e3811f2d0b0278_Traceguids
0x140020746  mov     edx, 1Fh
0x14002074b  mov     r9d, esi
0x14002074e  call    WPP_SF_d
0x140020753  mov     r8d, esi; unsigned int
0x140020756  mov     rcx, [r12+0C0h]; this
0x14002075e  mov     edx, edi; unsigned int
0x140020760  call    ?ReadMore@DrSession@@QEAAHKK@Z; DrSession::ReadMore(ulong,ulong)
0x140020765  neg     eax
0x140020767  sbb     eax, eax
0x140020769  not     eax
0x14002076b  and     eax, 0C0000001h
0x140020770  add     rsp, 28h
0x140020774  pop     r15
0x140020776  pop     r14
0x140020778  pop     r13
0x14002077a  pop     r12
0x14002077c  pop     rdi
0x14002077d  pop     rsi
0x14002077e  pop     rbp
0x14002077f  pop     rbx
0x140020780  retn
```
