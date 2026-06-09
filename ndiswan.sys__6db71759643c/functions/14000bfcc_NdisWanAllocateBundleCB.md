# NdisWanAllocateBundleCB

- ea: `0x14000bfcc`
- end: `0x14000c253`
- name: `NdisWanAllocateBundleCB`
- size: `647`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a310`
- `0x140024008`

## callees

- `0x140005750`
- `0x14000a290`
- `0x14000a648`
- `0x14000bfcc`
- `0x14000c67c`
- `0x140010f7c`
- `0x140016700`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000c05a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000c05a`
- `ntoskrnl!KeInitializeEvent` at `0x14000c18b`
- `ntoskrnl!KeInitializeEvent` at `0x14000c18b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000c1c9`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14000c1c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c15a`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000c15a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000bfdc`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14000bfdc`

## string_xrefs

- `0x14000c1f1`: `I/O ProtocolCB`

## pseudocode

```c
char *NdisWanAllocateBundleCB()
{
  char *v0; // rax
  char *v1; // rdi
  char *result; // rax
  __int64 v3; // rsi
  __int64 v4; // rdx
  char *v5; // rcx
  int v6; // eax
  __int64 v7; // rbx
  __int64 RecvDesc; // rax
  __int64 v9; // rcx
  __int64 v10; // r9
  unsigned __int64 v11; // rbp
  int v12; // ecx
  int v13; // eax
  __int64 v14; // rbx
  ULONG TimeIncrement; // eax

  v0 = (char *)ExAllocateFromNPagedLookasideList(&BundleCBList);
  v1 = v0;
  if ( v0 )
  {
    memset(v0, 0, 0xC50u);
    *((_QWORD *)v1 + 33) = (unsigned __int64)(v1 + 2896) & 0xFFFFFFFFFFFFFFF8uLL;
    KeInitializeSpinLock((PKSPIN_LOCK)v1 + 221);
    v3 = 0;
    *((_QWORD *)v1 + 7) = v1 + 48;
    *((_QWORD *)v1 + 6) = v1 + 48;
    while ( 1 )
    {
      if ( (_DWORD)v3 )
      {
        *((_QWORD *)v1 + 36) = v1 + 280;
        v11 = (unsigned __int64)(v1 + 2544) & 0xFFFFFFFFFFFFFFF8uLL;
        *((_QWORD *)v1 + 35) = v1 + 280;
        KeInitializeEvent((PRKEVENT)(v1 + 176), SynchronizationEvent, 0);
        v12 = glMaxMTU;
        v13 = glMRRU;
        *((_DWORD *)v1 + 5) = 2;
        *((_DWORD *)v1 + 19) = v12;
        *((_DWORD *)v1 + 20) = v13;
        *((_DWORD *)v1 + 88) = v12;
        *((_DWORD *)v1 + 96) = v13;
        v14 = MEMORY[0xFFFFF78000000320];
        TimeIncrement = KeQueryTimeIncrement();
        v1[848] = -1;
        v1[472] = -1;
        *((_DWORD *)v1 + 447) = -1;
        *(_OWORD *)(v1 + 2340) = xmmword_140019890;
        v1[2436] = 0;
        *((_QWORD *)v1 + 40) = v14 * TimeIncrement;
        *(_DWORD *)(v11 + 212) = 11250432;
        *(_QWORD *)(v11 + 64) = v1;
        *(_DWORD *)(v11 + 20) = 3;
        NdisWanStringToNdisString((PUNICODE_STRING)(v11 + 272));
        result = v1;
        *((_QWORD *)v1 + 38) = v11;
        *((_DWORD *)v1 + 4) = 0x100000;
        return result;
      }
      v4 = 5 * v3;
      v5 = &v1[40 * v3 + 112];
      *(_QWORD *)&v1[40 * v3 + 120] = v5;
      v6 = glMinFragSize;
      v7 = (__int64)&v1[40 * v3 + 208];
      *(_QWORD *)v5 = v5;
      *(_DWORD *)&v1[8 * v4 + 136] = v6;
      *(_DWORD *)&v1[8 * v4 + 140] = glMaxFragSize;
      *(_QWORD *)&v1[8 * v4 + 216] = v7;
      *(_QWORD *)v7 = v7;
      RecvDesc = NdisWanAllocateRecvDesc();
      if ( !RecvDesc )
        break;
      *(_DWORD *)(RecvDesc + 44) = 1;
      *(_QWORD *)(v7 + 24) = RecvDesc;
      v9 = *(_QWORD *)v7;
      if ( *(_QWORD *)(*(_QWORD *)v7 + 8LL) != v7 )
        __fastfail(3u);
      *(_QWORD *)RecvDesc = v9;
      *(_QWORD *)(RecvDesc + 8) = v7;
      *(_QWORD *)(v9 + 8) = RecvDesc;
      *(_QWORD *)v7 = RecvDesc;
      ++*(_DWORD *)(v7 + 16);
      v3 = 1;
    }
    v10 = *((_QWORD *)v1 + 29);
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids, v10);
      }
      NdisWanFreeRecvDesc(*((_QWORD *)v1 + 29));
    }
    ExFreeToNPagedLookasideList(&BundleCBList, v1);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14000bfcc  push    rbx
0x14000bfce  push    rbp
0x14000bfcf  push    rsi
0x14000bfd0  push    rdi
0x14000bfd1  sub     rsp, 28h
0x14000bfd5  lea     rcx, BundleCBList; Lookaside
0x14000bfdc  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14000bfe3  nop     dword ptr [rax+rax+00h]
0x14000bfe8  mov     rdi, rax
0x14000bfeb  test    rax, rax
0x14000bfee  jnz     short loc_14000C02A
0x14000bff0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bff7  lea     rax, WPP_GLOBAL_Control
0x14000bffe  cmp     rcx, rax
0x14000c001  jz      short loc_14000C023
0x14000c003  mov     eax, [rcx+2Ch]
0x14000c006  test    al, 40h
0x14000c008  jz      short loc_14000C023
0x14000c00a  cmp     byte ptr [rcx+29h], 2
0x14000c00e  jb      short loc_14000C023
0x14000c010  mov     rcx, [rcx+18h]
0x14000c014  lea     edx, [rdi+1Fh]
0x14000c017  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c01e  call    WPP_SF_
0x14000c023  xor     eax, eax
0x14000c025  jmp     loc_14000C249
0x14000c02a  xor     edx, edx; Val
0x14000c02c  mov     r8d, 0C50h; Size
0x14000c032  mov     rcx, rdi; void *
0x14000c035  call    memset
0x14000c03a  lea     rbp, [rdi+9F0h]
0x14000c041  lea     rax, [rbp+160h]
0x14000c048  and     rax, 0FFFFFFFFFFFFFFF8h
0x14000c04c  lea     rcx, [rdi+6E8h]; SpinLock
0x14000c053  mov     [rdi+108h], rax
0x14000c05a  call    cs:__imp_KeInitializeSpinLock
0x14000c061  nop     dword ptr [rax+rax+00h]
0x14000c066  lea     rax, [rdi+30h]
0x14000c06a  xor     esi, esi
0x14000c06c  mov     [rax+8], rax
0x14000c070  mov     [rax], rax
0x14000c073  cmp     esi, 1
0x14000c076  jnb     loc_14000C16B
0x14000c07c  lea     rdx, [rsi+rsi*4]
0x14000c080  lea     rax, [rsi+rsi*4]
0x14000c084  lea     rcx, [rdi+70h]
0x14000c088  lea     rcx, [rcx+rdx*8]
0x14000c08c  mov     [rdi+rax*8+78h], rcx
0x14000c091  lea     rbx, [rdi+0D0h]
0x14000c098  mov     eax, cs:glMinFragSize
0x14000c09e  lea     rbx, [rbx+rdx*8]
0x14000c0a2  mov     [rcx], rcx
0x14000c0a5  mov     [rdi+rdx*8+88h], eax
0x14000c0ac  mov     eax, cs:glMaxFragSize
0x14000c0b2  mov     [rdi+rdx*8+8Ch], eax
0x14000c0b9  mov     [rdi+rdx*8+0D8h], rbx
0x14000c0c1  mov     [rbx], rbx
0x14000c0c4  call    NdisWanAllocateRecvDesc
0x14000c0c9  test    rax, rax
0x14000c0cc  jz      short loc_14000C101
0x14000c0ce  mov     dword ptr [rax+2Ch], 1
0x14000c0d5  mov     [rbx+18h], rax
0x14000c0d9  mov     rcx, [rbx]
0x14000c0dc  cmp     [rcx+8], rbx
0x14000c0e0  jnz     short loc_14000C0FA
0x14000c0e2  mov     [rax], rcx
0x14000c0e5  mov     [rax+8], rbx
0x14000c0e9  mov     [rcx+8], rax
0x14000c0ed  mov     [rbx], rax
0x14000c0f0  inc     dword ptr [rbx+10h]
0x14000c0f3  inc     esi
0x14000c0f5  jmp     loc_14000C073
0x14000c0fa  mov     ecx, 3
0x14000c0ff  int     29h; Win8: RtlFailFast(ecx)
0x14000c101  mov     r9, [rdi+0E8h]
0x14000c108  test    r9, r9
0x14000c10b  jz      short loc_14000C150
0x14000c10d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c114  lea     rax, WPP_GLOBAL_Control
0x14000c11b  cmp     rcx, rax
0x14000c11e  jz      short loc_14000C144
0x14000c120  test    dword ptr [rcx+2Ch], 8000h
0x14000c127  jz      short loc_14000C144
0x14000c129  cmp     byte ptr [rcx+29h], 5
0x14000c12d  jb      short loc_14000C144
0x14000c12f  mov     rcx, [rcx+18h]
0x14000c133  lea     r8, WPP_02ddcb2c9bbd3de8df0861afc8432e81_Traceguids
0x14000c13a  mov     edx, 20h ; ' '
0x14000c13f  call    WPP_SF_q
0x14000c144  mov     rcx, [rdi+0E8h]
0x14000c14b  call    NdisWanFreeRecvDesc
0x14000c150  mov     rdx, rdi; Entry
0x14000c153  lea     rcx, BundleCBList; Lookaside
0x14000c15a  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000c161  nop     dword ptr [rax+rax+00h]
0x14000c166  jmp     loc_14000C023
0x14000c16b  lea     rax, [rdi+118h]
0x14000c172  xor     r8d, r8d; State
0x14000c175  lea     rcx, [rdi+0B0h]; Event
0x14000c17c  mov     [rax+8], rax
0x14000c180  and     rbp, 0FFFFFFFFFFFFFFF8h
0x14000c184  mov     [rax], rax
0x14000c187  lea     edx, [r8+1]; Type
0x14000c18b  call    cs:__imp_KeInitializeEvent
0x14000c192  nop     dword ptr [rax+rax+00h]
0x14000c197  mov     ecx, cs:glMaxMTU
0x14000c19d  mov     rbx, 0FFFFF78000000320h
0x14000c1a7  mov     eax, cs:glMRRU
0x14000c1ad  mov     dword ptr [rdi+14h], 2
0x14000c1b4  mov     [rdi+4Ch], ecx
0x14000c1b7  mov     [rdi+50h], eax
0x14000c1ba  mov     [rdi+160h], ecx
0x14000c1c0  mov     [rdi+180h], eax
0x14000c1c6  mov     rbx, [rbx]
0x14000c1c9  call    cs:__imp_KeQueryTimeIncrement
0x14000c1d0  nop     dword ptr [rax+rax+00h]
0x14000c1d5  movups  xmm0, cs:xmmword_140019890
0x14000c1dc  mov     byte ptr [rdi+350h], 0FFh
0x14000c1e3  lea     rcx, [rbp+110h]; DestinationString
0x14000c1ea  mov     byte ptr [rdi+1D8h], 0FFh
0x14000c1f1  lea     rdx, aIOProtocolcb; "I/O ProtocolCB"
0x14000c1f8  mov     dword ptr [rdi+6FCh], 0FFFFFFFFh
0x14000c202  movdqu  xmmword ptr [rdi+924h], xmm0
0x14000c20a  mov     byte ptr [rdi+984h], 0
0x14000c211  mov     eax, eax
0x14000c213  imul    rax, rbx
0x14000c217  mov     [rdi+140h], rax
0x14000c21e  mov     dword ptr [rbp+0D4h], 0ABAB00h
0x14000c228  mov     [rbp+40h], rdi
0x14000c22c  mov     dword ptr [rbp+14h], 3
0x14000c233  call    NdisWanStringToNdisString
0x14000c238  mov     rax, rdi
0x14000c23b  mov     [rdi+130h], rbp
0x14000c242  mov     dword ptr [rdi+10h], 100000h
0x14000c249  add     rsp, 28h
0x14000c24d  pop     rdi
0x14000c24e  pop     rsi
0x14000c24f  pop     rbp
0x14000c250  pop     rbx
0x14000c251  retn
```
