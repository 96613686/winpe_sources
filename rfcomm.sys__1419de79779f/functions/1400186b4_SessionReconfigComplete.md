# SessionReconfigComplete

- ea: `0x1400186b4`
- end: `0x140018986`
- name: `SessionReconfigComplete`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000da70`

## callees

- `0x140005f2c`
- `0x140007350`
- `0x14000ab70`
- `0x1400133b0`
- `0x1400186b4`
- `0x140018bd0`
- `0x140018e9c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400186db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400188ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400186db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400188ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400186f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018856`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400188d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400186f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018856`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400188d2`

## string_xrefs

- `0x140018900`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`
- `0x14001891b`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\session.c`

## pseudocode

```c
__int64 __fastcall SessionReconfigComplete(__int64 a1, _OWORD *a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  bool v6; // zf
  int v8; // ecx
  int v9; // eax
  _QWORD *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdi
  __int64 v13; // rsi
  int v14; // edx
  _QWORD *v15; // rcx
  __int64 v16; // rax
  __int128 v17; // [rsp+50h] [rbp-28h] BYREF
  __int128 v18; // [rsp+60h] [rbp-18h] BYREF

  v2 = (KSPIN_LOCK *)(a1 + 56);
  v17 = 0;
  v18 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v6 = *(_DWORD *)(a1 + 48) == 4;
  *(_BYTE *)(a1 + 64) = v5;
  if ( v6 )
  {
    *(_OWORD *)(a1 + 384) = a2[21];
    *(_OWORD *)(a1 + 400) = a2[22];
    *(_OWORD *)(a1 + 416) = a2[23];
    *(_OWORD *)(a1 + 432) = a2[24];
    *(_OWORD *)(a1 + 448) = a2[25];
    *(_OWORD *)(a1 + 304) = *(_OWORD *)((char *)a2 + 248);
    *(_OWORD *)(a1 + 320) = *(_OWORD *)((char *)a2 + 264);
    *(_OWORD *)(a1 + 336) = *(_OWORD *)((char *)a2 + 280);
    *(_OWORD *)(a1 + 352) = *(_OWORD *)((char *)a2 + 296);
    *(_OWORD *)(a1 + 368) = *(_OWORD *)((char *)a2 + 312);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qdDdD(
        WPP_GLOBAL_Control->DeviceExtension,
        *(unsigned __int8 *)(a1 + 430),
        *(unsigned __int16 *)(a1 + 388),
        26);
    v8 = 3;
    if ( *(_BYTE *)(a1 + 350) != 3 )
      v8 = 1;
    v9 = *(_DWORD *)(a1 + 288);
    *(_DWORD *)(a1 + 296) = v8;
    *(_DWORD *)(a1 + 292) = ~v8 & v9;
    *((_QWORD *)&v17 + 1) = &v17;
    *(_QWORD *)&v17 = &v17;
    *((_QWORD *)&v18 + 1) = &v18;
    *(_QWORD *)&v18 = &v18;
    ListDrainLocked(&v17, a1 + 96);
    ListDrainLocked(&v18, a1 + 112);
    KeReleaseSpinLock(v2, *(_BYTE *)(a1 + 64));
    while ( 1 )
    {
      v10 = (_QWORD *)v17;
      if ( (__int128 *)v17 == &v17 )
        break;
      if ( *(__int128 **)(v17 + 8) != &v17 || (v11 = *(_QWORD *)v17, *(_QWORD *)(*(_QWORD *)v17 + 8LL) != (_QWORD)v17) )
LABEL_19:
        __fastfail(3u);
      *(_QWORD *)&v17 = *(_QWORD *)v17;
      *(_QWORD *)(v11 + 8) = &v17;
      v12 = (__int64)(v10 - 35);
      v10[1] = v10;
      *v10 = v10;
      *(_BYTE *)(v12 + 56) = KeAcquireSpinLockRaiseToDpc(v10 - 29);
      v13 = TdiReferenceAddrLocked(v12, 1313754947);
      KeReleaseSpinLock((PKSPIN_LOCK)(v12 + 48), *(_BYTE *)(v12 + 56));
      if ( v13 )
      {
        ChannelConnect(v12, v14);
        RefObj_ReleaseEx(v13 + 24, 1313754947, 556, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
      }
      else
      {
        TdiCompleteConnect(v12, 3221225787LL);
      }
      RefObj_ReleaseEx(v12 + 24, 1313754947, 559, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\session.c");
    }
    while ( 1 )
    {
      v15 = (_QWORD *)v18;
      if ( (__int128 *)v18 == &v18 )
        return 0;
      if ( *(__int128 **)(v18 + 8) != &v18 )
        goto LABEL_19;
      v16 = *(_QWORD *)v18;
      if ( *(_QWORD *)(*(_QWORD *)v18 + 8LL) != (_QWORD)v18 )
        goto LABEL_19;
      *(_QWORD *)&v18 = *(_QWORD *)v18;
      *(_QWORD *)(v16 + 8) = &v18;
      v15[1] = v15;
      *v15 = v15;
      TdiAccept(v15 - 30);
    }
  }
  else
  {
    KeReleaseSpinLock(v2, v5);
    return 3221225860LL;
  }
}

```

## disassembly

```asm
0x1400186b4  push    rbp
0x1400186b6  push    rbx
0x1400186b7  push    rsi
0x1400186b8  push    rdi
0x1400186b9  mov     rbp, rsp
0x1400186bc  sub     rsp, 78h
0x1400186c0  lea     rsi, [rcx+38h]
0x1400186c4  mov     rbx, rcx
0x1400186c7  xorps   xmm0, xmm0
0x1400186ca  xorps   xmm1, xmm1
0x1400186cd  mov     rcx, rsi; SpinLock
0x1400186d0  mov     rdi, rdx
0x1400186d3  movups  [rbp+var_28], xmm0
0x1400186d7  movups  [rbp+var_18], xmm1
0x1400186db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400186e2  nop     dword ptr [rax+rax+00h]
0x1400186e7  cmp     dword ptr [rbx+30h], 4
0x1400186eb  mov     [rbx+40h], al
0x1400186ee  jz      short loc_14001870B
0x1400186f0  mov     dl, al; NewIrql
0x1400186f2  mov     rcx, rsi; SpinLock
0x1400186f5  call    cs:__imp_KeReleaseSpinLock
0x1400186fc  nop     dword ptr [rax+rax+00h]
0x140018701  mov     eax, 0C0000184h
0x140018706  jmp     loc_14001897C
0x14001870b  movups  xmm0, xmmword ptr [rdi+150h]
0x140018712  movups  xmmword ptr [rbx+180h], xmm0
0x140018719  movups  xmm1, xmmword ptr [rdi+160h]
0x140018720  movups  xmmword ptr [rbx+190h], xmm1
0x140018727  movups  xmm0, xmmword ptr [rdi+170h]
0x14001872e  movups  xmmword ptr [rbx+1A0h], xmm0
0x140018735  movups  xmm1, xmmword ptr [rdi+180h]
0x14001873c  movups  xmmword ptr [rbx+1B0h], xmm1
0x140018743  movups  xmm0, xmmword ptr [rdi+190h]
0x14001874a  movups  xmmword ptr [rbx+1C0h], xmm0
0x140018751  movups  xmm0, xmmword ptr [rdi+0F8h]
0x140018758  movups  xmmword ptr [rbx+130h], xmm0
0x14001875f  movups  xmm1, xmmword ptr [rdi+108h]
0x140018766  movups  xmmword ptr [rbx+140h], xmm1
0x14001876d  movups  xmm0, xmmword ptr [rdi+118h]
0x140018774  movups  xmmword ptr [rbx+150h], xmm0
0x14001877b  movups  xmm1, xmmword ptr [rdi+128h]
0x140018782  movups  xmmword ptr [rbx+160h], xmm1
0x140018789  movups  xmm0, xmmword ptr [rdi+138h]
0x140018790  movups  xmmword ptr [rbx+170h], xmm0
0x140018797  lea     rax, WPP_RECORDER_INITIALIZED
0x14001879e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400187a5  lea     rdi, [rbx+15Eh]
0x1400187ac  jz      short loc_1400187F3
0x1400187ae  movzx   ecx, word ptr [rbx+134h]
0x1400187b5  mov     r9d, 1Ah
0x1400187bb  movzx   eax, byte ptr [rdi]
0x1400187be  movzx   edx, byte ptr [rbx+1AEh]
0x1400187c5  movzx   r8d, word ptr [rbx+184h]
0x1400187cd  mov     [rsp+78h+var_30], eax
0x1400187d1  mov     [rsp+78h+var_38], ecx
0x1400187d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400187dc  mov     [rsp+78h+var_40], edx
0x1400187e0  mov     [rsp+78h+var_48], r8d
0x1400187e5  mov     [rsp+78h+var_50], rbx
0x1400187ea  mov     rcx, [rcx+40h]
0x1400187ee  call    WPP_RECORDER_SF_qdDdD
0x1400187f3  mov     ecx, 3
0x1400187f8  lea     rdx, [rbx+60h]
0x1400187fc  cmp     [rdi], cl
0x1400187fe  lea     eax, [rcx-2]
0x140018801  cmovnz  ecx, eax
0x140018804  mov     eax, [rbx+120h]
0x14001880a  mov     [rbx+128h], ecx
0x140018810  not     ecx
0x140018812  and     eax, ecx
0x140018814  lea     rcx, [rbp+var_28]
0x140018818  mov     [rbx+124h], eax
0x14001881e  lea     rax, [rbp+var_28]
0x140018822  mov     qword ptr [rbp+var_28+8], rax
0x140018826  lea     rax, [rbp+var_28]
0x14001882a  mov     qword ptr [rbp+var_28], rax
0x14001882e  lea     rax, [rbp+var_18]
0x140018832  mov     qword ptr [rbp+var_18+8], rax
0x140018836  lea     rax, [rbp+var_18]
0x14001883a  mov     qword ptr [rbp+var_18], rax
0x14001883e  call    ListDrainLocked
0x140018843  lea     rcx, [rbp+var_18]
0x140018847  lea     rdx, [rbx+70h]
0x14001884b  call    ListDrainLocked
0x140018850  mov     dl, [rbx+40h]; NewIrql
0x140018853  mov     rcx, rsi; SpinLock
0x140018856  call    cs:__imp_KeReleaseSpinLock
0x14001885d  nop     dword ptr [rax+rax+00h]
0x140018862  mov     rax, qword ptr [rbp+var_28]
0x140018866  lea     rcx, [rbp+var_28]
0x14001886a  cmp     rax, rcx
0x14001886d  jz      loc_140018932
0x140018873  lea     rcx, [rbp+var_28]
0x140018877  cmp     [rax+8], rcx
0x14001887b  jnz     loc_140018973
0x140018881  mov     rcx, [rax]
0x140018884  cmp     [rcx+8], rax
0x140018888  jnz     loc_140018973
0x14001888e  mov     qword ptr [rbp+var_28], rcx
0x140018892  lea     rdx, [rbp+var_28]
0x140018896  mov     [rcx+8], rdx
0x14001889a  lea     rdi, [rax-118h]
0x1400188a1  lea     rcx, [rdi+30h]; SpinLock
0x1400188a5  mov     [rax+8], rax
0x1400188a9  mov     [rax], rax
0x1400188ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400188b3  nop     dword ptr [rax+rax+00h]
0x1400188b8  mov     edx, 4E4E4F43h
0x1400188bd  mov     rcx, rdi
0x1400188c0  mov     [rdi+38h], al
0x1400188c3  call    TdiReferenceAddrLocked
0x1400188c8  mov     dl, [rdi+38h]; NewIrql
0x1400188cb  lea     rcx, [rdi+30h]; SpinLock
0x1400188cf  mov     rsi, rax
0x1400188d2  call    cs:__imp_KeReleaseSpinLock
0x1400188d9  nop     dword ptr [rax+rax+00h]
0x1400188de  mov     rcx, rdi
0x1400188e1  test    rsi, rsi
0x1400188e4  jnz     short loc_1400188F2
0x1400188e6  mov     edx, 0C000013Bh
0x1400188eb  call    TdiCompleteConnect
0x1400188f0  jmp     short loc_140018912
0x1400188f2  call    ChannelConnect
0x1400188f7  lea     rcx, [rsi+18h]
0x1400188fb  mov     edx, 4E4E4F43h
0x140018900  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018907  mov     r8d, 22Ch
0x14001890d  call    RefObj_ReleaseEx
0x140018912  lea     rcx, [rdi+18h]
0x140018916  mov     edx, 4E4E4F43h
0x14001891b  lea     r9, aOnecoreDrivers; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018922  mov     r8d, 22Fh
0x140018928  call    RefObj_ReleaseEx
0x14001892d  jmp     loc_140018862
0x140018932  mov     rcx, qword ptr [rbp+var_18]
0x140018936  lea     rax, [rbp+var_18]
0x14001893a  cmp     rcx, rax
0x14001893d  jz      short loc_14001897A
0x14001893f  lea     rax, [rbp+var_18]
0x140018943  cmp     [rcx+8], rax
0x140018947  jnz     short loc_140018973
0x140018949  mov     rax, [rcx]
0x14001894c  cmp     [rax+8], rcx
0x140018950  jnz     short loc_140018973
0x140018952  mov     qword ptr [rbp+var_18], rax
0x140018956  lea     rdx, [rbp+var_18]
0x14001895a  mov     [rax+8], rdx
0x14001895e  mov     [rcx+8], rcx
0x140018962  mov     [rcx], rcx
0x140018965  add     rcx, 0FFFFFFFFFFFFFF10h
0x14001896c  call    TdiAccept
0x140018971  jmp     short loc_140018932
0x140018973  mov     ecx, 3
0x140018978  int     29h; Win8: RtlFailFast(ecx)
0x14001897a  xor     eax, eax
0x14001897c  add     rsp, 78h
0x140018980  pop     rdi
0x140018981  pop     rsi
0x140018982  pop     rbx
0x140018983  pop     rbp
0x140018984  retn
```
