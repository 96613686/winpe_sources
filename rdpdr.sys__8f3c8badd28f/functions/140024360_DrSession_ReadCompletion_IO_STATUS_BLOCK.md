# DrSession::ReadCompletion(_IO_STATUS_BLOCK *)

- ea: `0x140024360`
- end: `0x140024821`
- name: `?ReadCompletion@DrSession@@AEAAXPEAU_IO_STATUS_BLOCK@@@Z`
- size: `1217`
- prototype: `void __fastcall(DrSession *__hidden this, struct _IO_STATUS_BLOCK *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400242b0`

## callees

- `0x140001c50`
- `0x140001e60`
- `0x140001ef0`
- `0x140002a40`
- `0x14000324c`
- `0x14000327c`
- `0x1400036c0`
- `0x140005284`
- `0x140006560`
- `0x140024360`
- `0x140024830`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14002443d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002443d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002444f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14002444f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002451c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002451c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024544`
- `ntoskrnl!ExReleaseFastMutex` at `0x140024544`
- `rdbss!RxDestroyMidAtlas` at `0x1400247ec`
- `rdbss!RxDestroyMidAtlas` at `0x1400247ec`

## pseudocode

```c
void __fastcall DrSession::ReadCompletion(DrSession *this, struct _IO_STATUS_BLOCK *a2)
{
  bool v2; // cf
  __int16 *v4; // r14
  int v5; // edi
  struct ListEntry *i; // rax
  struct ListEntry *v7; // rdi
  __int64 v8; // rsi
  struct _RX_MID_ATLAS *v9; // rdi
  int v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 *v13; // r8
  int v14; // [rsp+80h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 154) < 4u;
  v14 = 1;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
LABEL_49:
    v5 = -1073741434;
    goto LABEL_19;
  }
  v4 = (__int16 *)*((_QWORD *)this + 76);
  *(struct _IO_STATUS_BLOCK *)((char *)this + 664) = *a2;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_LLcccc(
      WPP_GLOBAL_Control->AttachedDevice,
      (unsigned __int64)v4[1] >> 8,
      (unsigned __int64)*v4 >> 8,
      *((unsigned int *)this + 166),
      *((_DWORD *)this + 168),
      HIBYTE(*v4),
      *(_BYTE *)v4,
      HIBYTE(v4[1]),
      *((_BYTE *)v4 + 2));
  v5 = *((_DWORD *)this + 166);
  if ( (int)(v5 + 0x80000000) >= 0 && v5 != -2147483643 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        75,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        (unsigned int)v5);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
  *((_QWORD *)this + 84) += *((unsigned int *)this + 186);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      70,
      WPP_5c887063686c325024567ba4647d07cf_Traceguids,
      *((_QWORD *)this + 76));
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)((char *)this + 96), 1u);
  if ( *((_QWORD *)this + 84) < 4u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    v5 = -1073741434;
    DoubleList::Unlock((DrSession *)((char *)this + 48));
LABEL_19:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        78,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        (unsigned int)v5);
    *((_DWORD *)this + 149) = 0;
    DrSession::DeleteChannel(this, 0);
    v9 = 0;
    ExAcquireFastMutex(&DrMutex);
    v10 = *((_DWORD *)this + 182);
    *((_DWORD *)this + 182) = 0;
    if ( v10 == 1 )
    {
      v9 = (struct _RX_MID_ATLAS *)*((_QWORD *)this + 90);
      *((_QWORD *)this + 90) = 0;
    }
    ExReleaseFastMutex(&DrMutex);
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e59448592ec538b831cf1e49bf008190_Traceguids, v9);
      RxDestroyMidAtlas(v9, DrExchangeManager::DestroyAtlasCallback);
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v12 = 13;
        v13 = WPP_e59448592ec538b831cf1e49bf008190_Traceguids;
LABEL_58:
        WPP_SF_(v11->AttachedDevice, v12, v13);
      }
    }
    return;
  }
  for ( i = DoubleList::First((DrSession *)((char *)this + 48));
        ;
        i = DoubleList::Next((DrSession *)((char *)this + 48), v7) )
  {
    v7 = i;
    if ( !i )
    {
      (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 32LL))((char *)this + 80);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          74,
          WPP_5c887063686c325024567ba4647d07cf_Traceguids,
          (unsigned int)*v4);
      goto LABEL_49;
    }
    v8 = *((_QWORD *)i + 2);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        73,
        WPP_5c887063686c325024567ba4647d07cf_Traceguids,
        *((_QWORD *)i + 2));
    if ( (**(unsigned int (__fastcall ***)(__int64, __int16 *))v8)(v8, v4) )
      break;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int16 *, _QWORD, int *))(*(_QWORD *)v8 + 8LL))(
         v8,
         v4,
         *((unsigned int *)this + 168),
         &v14);
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 10) + 32LL))((char *)this + 80);
  if ( v5 < 0 )
    goto LABEL_19;
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 76, WPP_5c887063686c325024567ba4647d07cf_Traceguids);
    DrSession::ReadPacket(this);
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v12 = 77;
      v13 = WPP_5c887063686c325024567ba4647d07cf_Traceguids;
      goto LABEL_58;
    }
  }
}

```

## disassembly

```asm
0x140024360  mov     [rsp+arg_8], rbx
0x140024365  mov     [rsp+arg_10], rbp
0x14002436a  push    rsi
0x14002436b  push    rdi
0x14002436c  push    r13
0x14002436e  push    r14
0x140024370  push    r15
0x140024372  sub     rsp, 50h
0x140024376  cmp     dword ptr [rcx+268h], 4
0x14002437d  mov     rbx, rcx
0x140024380  mov     [rsp+78h+arg_0], 1
0x14002438b  jb      loc_140024626
0x140024391  movups  xmm0, xmmword ptr [rdx]
0x140024394  mov     r14, [rcx+260h]
0x14002439b  movups  xmmword ptr [rcx+298h], xmm0
0x1400243a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243a9  lea     rbp, WPP_GLOBAL_Control
0x1400243b0  cmp     rcx, rbp
0x1400243b3  jz      short loc_1400243BF
0x1400243b5  cmp     byte ptr [rcx+29h], 4
0x1400243b9  jnb     loc_140024661
0x1400243bf  mov     edi, [rbx+298h]
0x1400243c5  mov     ecx, 80000000h
0x1400243ca  lea     eax, [rdi+rcx]
0x1400243cd  test    ecx, eax
0x1400243cf  jnz     short loc_140024410
0x1400243d1  cmp     edi, 80000005h
0x1400243d7  jz      short loc_140024410
0x1400243d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400243e0  cmp     rcx, rbp
0x1400243e3  jz      loc_1400244F1
0x1400243e9  cmp     byte ptr [rcx+29h], 5
0x1400243ed  jb      loc_1400244F1
0x1400243f3  mov     rcx, [rcx+18h]
0x1400243f7  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400243fe  mov     edx, 4Bh ; 'K'
0x140024403  mov     r9d, edi
0x140024406  call    WPP_SF_d
0x14002440b  jmp     loc_1400244F1
0x140024410  mov     rcx, cs:WPP_GLOBAL_Control
0x140024417  cmp     rcx, rbp
0x14002441a  jnz     loc_1400246AB
0x140024420  mov     eax, [rbx+2E8h]
0x140024426  add     [rbx+2A0h], rax
0x14002442d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024434  cmp     rcx, rbp
0x140024437  jnz     loc_1400245D8
0x14002443d  call    cs:__imp_KeEnterCriticalRegion
0x140024444  nop     dword ptr [rax+rax+00h]
0x140024449  lea     rcx, [rbx+60h]; Resource
0x14002444d  mov     dl, 1; Wait
0x14002444f  call    cs:__imp_ExAcquireResourceSharedLite
0x140024456  nop     dword ptr [rax+rax+00h]
0x14002445b  cmp     qword ptr [rbx+2A0h], 4
0x140024463  jb      loc_140024603
0x140024469  lea     rcx, [rbx+30h]; this
0x14002446d  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x140024472  mov     rdi, rax
0x140024475  test    rax, rax
0x140024478  jz      loc_140024738
0x14002447e  mov     rsi, [rax+10h]
0x140024482  mov     rcx, cs:WPP_GLOBAL_Control
0x140024489  cmp     rcx, rbp
0x14002448c  jnz     loc_140024583
0x140024492  mov     rax, [rsi]
0x140024495  mov     rdx, r14
0x140024498  mov     rcx, rsi
0x14002449b  mov     rax, [rax]
0x14002449e  call    _guard_dispatch_icall
0x1400244a3  test    eax, eax
0x1400244a5  jnz     short loc_1400244B5
0x1400244a7  mov     rdx, rdi; struct ListEntry *
0x1400244aa  lea     rcx, [rbx+30h]; this
0x1400244ae  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x1400244b3  jmp     short loc_140024472
0x1400244b5  mov     rax, [rsi]
0x1400244b8  lea     r9, [rsp+78h+arg_0]
0x1400244c0  mov     r8d, [rbx+2A0h]
0x1400244c7  mov     rdx, r14
0x1400244ca  mov     rcx, rsi
0x1400244cd  mov     rax, [rax+8]
0x1400244d1  call    _guard_dispatch_icall
0x1400244d6  mov     edi, eax
0x1400244d8  lea     rcx, [rbx+50h]
0x1400244dc  mov     rax, [rbx+50h]
0x1400244e0  mov     rax, [rax+20h]
0x1400244e4  call    _guard_dispatch_icall
0x1400244e9  test    edi, edi
0x1400244eb  jns     loc_1400245AA
0x1400244f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400244f8  cmp     rcx, rbp
0x1400244fb  jnz     loc_14002477E
0x140024501  xor     esi, esi
0x140024503  xor     edx, edx; int
0x140024505  mov     rcx, rbx; this
0x140024508  mov     [rbx+254h], esi
0x14002450e  call    ?DeleteChannel@DrSession@@AEAAXH@Z; DrSession::DeleteChannel(int)
0x140024513  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002451a  mov     edi, esi
0x14002451c  call    cs:__imp_ExAcquireFastMutex
0x140024523  nop     dword ptr [rax+rax+00h]
0x140024528  mov     eax, [rbx+2D8h]
0x14002452e  mov     [rbx+2D8h], esi
0x140024534  cmp     eax, 1
0x140024537  jz      loc_1400247A5
0x14002453d  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140024544  call    cs:__imp_ExReleaseFastMutex
0x14002454b  nop     dword ptr [rax+rax+00h]
0x140024550  test    rdi, rdi
0x140024553  jnz     loc_1400247B8
0x140024559  mov     rcx, cs:WPP_GLOBAL_Control
0x140024560  cmp     rcx, rbp
0x140024563  jnz     loc_1400247FD
0x140024569  lea     r11, [rsp+78h+var_28]
0x14002456e  mov     rbx, [r11+38h]
0x140024572  mov     rbp, [r11+40h]
0x140024576  mov     rsp, r11
0x140024579  pop     r15
0x14002457b  pop     r14
0x14002457d  pop     r13
0x14002457f  pop     rdi
0x140024580  pop     rsi
0x140024581  retn
0x140024583  cmp     byte ptr [rcx+29h], 5
0x140024587  jb      loc_140024492
0x14002458d  mov     rcx, [rcx+18h]
0x140024591  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024598  mov     edx, 49h ; 'I'
0x14002459d  mov     r9, rsi
0x1400245a0  call    WPP_SF_q
0x1400245a5  jmp     loc_140024492
0x1400245aa  cmp     [rsp+78h+arg_0], 0
0x1400245b2  jz      loc_14002470D
0x1400245b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400245bf  cmp     rcx, rbp
0x1400245c2  jz      short loc_1400245CE
0x1400245c4  cmp     byte ptr [rcx+29h], 5
0x1400245c8  jnb     loc_1400246F3
0x1400245ce  mov     rcx, rbx; this
0x1400245d1  call    ?ReadPacket@DrSession@@AEAAXXZ; DrSession::ReadPacket(void)
0x1400245d6  jmp     short loc_140024569
0x1400245d8  cmp     byte ptr [rcx+29h], 5
0x1400245dc  jb      loc_14002443D
0x1400245e2  mov     r9, [rbx+260h]
0x1400245e9  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400245f0  mov     rcx, [rcx+18h]
0x1400245f4  mov     edx, 46h ; 'F'
0x1400245f9  call    WPP_SF_q
0x1400245fe  jmp     loc_14002443D
0x140024603  mov     rcx, cs:WPP_GLOBAL_Control
0x14002460a  cmp     rcx, rbp
0x14002460d  jnz     loc_1400246CF
0x140024613  lea     rcx, [rbx+30h]; this
0x140024617  mov     edi, 0C0000186h
0x14002461c  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x140024621  jmp     loc_1400244F1
0x140024626  mov     rcx, cs:WPP_GLOBAL_Control
0x14002462d  lea     rbp, WPP_GLOBAL_Control
0x140024634  cmp     rcx, rbp
0x140024637  jz      loc_140024774
0x14002463d  cmp     byte ptr [rcx+29h], 2
0x140024641  jb      loc_140024774
0x140024647  mov     rcx, [rcx+18h]
0x14002464b  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024652  mov     edx, 43h ; 'C'
0x140024657  call    WPP_SF_
0x14002465c  jmp     loc_140024774
0x140024661  movzx   eax, byte ptr [r14+2]
0x140024666  movsx   rdx, word ptr [r14+2]
0x14002466b  movsx   r8, word ptr [r14]
0x14002466f  mov     r9d, [rbx+298h]
0x140024676  mov     rcx, [rcx+18h]
0x14002467a  mov     [rsp+78h+var_38], al
0x14002467e  movzx   eax, byte ptr [r14]
0x140024682  shr     rdx, 8
0x140024686  mov     [rsp+78h+var_40], dl
0x14002468a  mov     [rsp+78h+var_48], al
0x14002468e  mov     eax, [rbx+2A0h]
0x140024694  shr     r8, 8
0x140024698  mov     [rsp+78h+var_50], r8b
0x14002469d  mov     [rsp+78h+var_58], eax
0x1400246a1  call    WPP_SF_LLcccc
0x1400246a6  jmp     loc_1400243BF
0x1400246ab  cmp     byte ptr [rcx+29h], 4
0x1400246af  jb      loc_140024420
0x1400246b5  mov     rcx, [rcx+18h]
0x1400246b9  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400246c0  mov     edx, 45h ; 'E'
0x1400246c5  call    WPP_SF_
0x1400246ca  jmp     loc_140024420
0x1400246cf  cmp     byte ptr [rcx+29h], 2
0x1400246d3  jb      loc_140024613
0x1400246d9  mov     rcx, [rcx+18h]
0x1400246dd  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400246e4  mov     edx, 48h ; 'H'
0x1400246e9  call    WPP_SF_
0x1400246ee  jmp     loc_140024613
0x1400246f3  mov     rcx, [rcx+18h]
0x1400246f7  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x1400246fe  mov     edx, 4Ch ; 'L'
0x140024703  call    WPP_SF_
0x140024708  jmp     loc_1400245CE
0x14002470d  mov     rcx, cs:WPP_GLOBAL_Control
0x140024714  cmp     rcx, rbp
0x140024717  jz      loc_140024569
0x14002471d  cmp     byte ptr [rcx+29h], 5
0x140024721  jb      loc_140024569
0x140024727  mov     edx, 4Dh ; 'M'
0x14002472c  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024733  jmp     loc_140024813
0x140024738  mov     rax, [rbx+50h]
0x14002473c  lea     rcx, [rbx+50h]
0x140024740  mov     rax, [rax+20h]
0x140024744  call    _guard_dispatch_icall
0x140024749  mov     rcx, cs:WPP_GLOBAL_Control
0x140024750  cmp     rcx, rbp
0x140024753  jz      short loc_140024774
0x140024755  cmp     byte ptr [rcx+29h], 2
0x140024759  jb      short loc_140024774
0x14002475b  movsx   r9d, word ptr [r14]
0x14002475f  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024766  mov     rcx, [rcx+18h]
0x14002476a  mov     edx, 4Ah ; 'J'
0x14002476f  call    WPP_SF_d
0x140024774  mov     edi, 0C0000186h
0x140024779  jmp     loc_1400244F1
0x14002477e  cmp     byte ptr [rcx+29h], 2
0x140024782  jb      loc_140024501
0x140024788  mov     rcx, [rcx+18h]
0x14002478c  lea     r8, WPP_5c887063686c325024567ba4647d07cf_Traceguids
0x140024793  mov     edx, 4Eh ; 'N'
0x140024798  mov     r9d, edi
0x14002479b  call    WPP_SF_d
0x1400247a0  jmp     loc_140024501
0x1400247a5  mov     rdi, [rbx+2D0h]
0x1400247ac  mov     [rbx+2D0h], rsi
0x1400247b3  jmp     loc_14002453D
0x1400247b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400247bf  cmp     rcx, rbp
0x1400247c2  jz      short loc_1400247E2
0x1400247c4  cmp     byte ptr [rcx+29h], 4
0x1400247c8  jb      short loc_1400247E2
0x1400247ca  mov     rcx, [rcx+18h]
0x1400247ce  lea     r8, WPP_e59448592ec538b831cf1e49bf008190_Traceguids
0x1400247d5  mov     edx, 0Ch
0x1400247da  mov     r9, rdi
0x1400247dd  call    WPP_SF_q
0x1400247e2  lea     rdx, ?DestroyAtlasCallback@DrExchangeManager@@CAXPEAVDrExchange@@@Z; ContextDestructor
0x1400247e9  mov     rcx, rdi; MidAtlas
0x1400247ec  call    cs:__imp_RxDestroyMidAtlas
0x1400247f3  nop     dword ptr [rax+rax+00h]
0x1400247f8  jmp     loc_140024569
0x1400247fd  cmp     byte ptr [rcx+29h], 5
0x140024801  jb      loc_140024569
0x140024807  mov     edx, 0Dh
0x14002480c  lea     r8, WPP_e59448592ec538b831cf1e49bf008190_Traceguids
0x140024813  mov     rcx, [rcx+18h]
0x140024817  call    WPP_SF_
0x14002481c  jmp     loc_140024569
```
