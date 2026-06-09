# HidpDistributeInterruptReport

- ea: `0x180002560`
- end: `0x180002a3f`
- name: `HidpDistributeInterruptReport`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800017d0`

## callees

- `0x18000150c`
- `0x180002560`
- `0x180002a50`
- `0x18001c734`

## import_xrefs

- `ntoskrnl!RtlGetActiveConsoleId` at `0x1800028fd`
- `ntoskrnl!RtlGetActiveConsoleId` at `0x1800028fd`
- `ntoskrnl!IofCompleteRequest` at `0x1800027cb`
- `ntoskrnl!IofCompleteRequest` at `0x1800027cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000276e`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000276e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800025a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800025a3`

## pseudocode

```c
__int64 **__fastcall HidpDistributeInterruptReport(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        char a5)
{
  KSPIN_LOCK *v6; // r15
  int v9; // ebp
  KIRQL v10; // al
  int v11; // r8d
  __int64 *v12; // rbx
  KIRQL v13; // r12
  int v14; // r15d
  __int64 **v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 *v19; // rcx
  __int64 **result; // rax
  __int64 *v21; // rax
  __int64 v22; // [rsp+C0h] [rbp-58h] BYREF
  __int64 *v23; // [rsp+C8h] [rbp-50h] BYREF
  __int64 **v24; // [rsp+D0h] [rbp-48h]
  KIRQL v26; // [rsp+128h] [rbp+10h]

  v24 = &v23;
  v6 = (KSPIN_LOCK *)(a2 + 40);
  v23 = (__int64 *)&v23;
  v9 = 0;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 40));
  v12 = *(__int64 **)(a2 + 24);
  v26 = v10;
  v13 = v10;
  if ( v12 == (__int64 *)(a2 + 24) )
  {
    v17 = a1;
    if ( *(_DWORD *)(a2 + 12) == 2 )
      HidpProcessInterruptReportForCollection(a1, a2, a3, a4);
  }
  else
  {
    v14 = *(_DWORD *)(a2 + 336);
    do
    {
      v22 = 0;
      if ( (!v14 || *((_BYTE *)v12 + 62)) && (!a5 || *((_DWORD *)v12 + 17) == (unsigned int)RtlGetActiveConsoleId()) )
      {
        HidpProcessInterruptReport(a2, (__int64)(v12 - 7), a3, a4, &v22);
        if ( v22 )
        {
          v15 = v24;
          if ( *v24 != (__int64 *)&v23 )
LABEL_44:
            __fastfail(3u);
          v16 = (__int64 *)(v22 + 168);
          ++v9;
          *(_QWORD *)(v22 + 168) = &v23;
          v16[1] = (__int64)v15;
          *v15 = v16;
          v24 = (__int64 **)v16;
        }
      }
      v12 = (__int64 *)*v12;
    }
    while ( v12 != (__int64 *)(a2 + 24) );
    v6 = (KSPIN_LOCK *)(a2 + 40);
    v13 = v26;
    v17 = a1;
  }
  *(_QWORD *)(a2 + 360) = MEMORY[0xFFFFF78000000014];
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 376));
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 384));
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 400));
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 392));
  _InterlockedIncrement64((volatile signed __int64 *)(a2 + 416));
  LODWORD(v18) = 0;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 356), 0, 0) )
    _InterlockedIncrement64((volatile signed __int64 *)(a2 + 408));
  if ( *(_DWORD *)(a2 + 12) == 2
    || (v18 = *(_QWORD *)(a2 + 368)) == 0
    || (unsigned __int64)(*(_QWORD *)(a2 + 360) - v18) >= 0x2FAF080 )
  {
    *(_QWORD *)(a2 + 368) = *(_QWORD *)(a2 + 360);
    LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v18 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdLLiiIIIIIIIII(WPP_GLOBAL_Control->AttachedDevice, v18, v11, *(_QWORD *)(v17 + 688), 4);
    }
  }
  else
  {
    LOBYTE(v18) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
               && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)v18 || (_BYTE)v11 )
      WPP_RECORDER_AND_TRACE_SF_qdLLiiIIIIIIIII(WPP_GLOBAL_Control->AttachedDevice, v18, v11, *(_QWORD *)(v17 + 688), 5);
  }
  KeReleaseSpinLock(v6, v13);
  while ( 1 )
  {
    v19 = v23;
    result = &v23;
    if ( v23 == (__int64 *)&v23 )
      return result;
    if ( (__int64 **)v23[1] != &v23 )
      goto LABEL_44;
    v21 = (__int64 *)*v23;
    if ( *(__int64 **)(*v23 + 8) != v23 )
      goto LABEL_44;
    v23 = (__int64 *)*v23;
    v21[1] = (__int64)&v23;
    IofCompleteRequest((PIRP)(v19 - 21), 6);
  }
}

```

## disassembly

```asm
0x180002560  mov     r11, rsp
0x180002563  mov     [r11+18h], rbx
0x180002567  mov     [r11+20h], r9d
0x18000256b  mov     [r11+8], rcx
0x18000256f  push    rbp
0x180002570  push    rsi
0x180002571  push    rdi
0x180002572  push    r12
0x180002574  push    r13
0x180002576  push    r14
0x180002578  push    r15
0x18000257a  sub     rsp, 0E0h
0x180002581  lea     rax, [r11-50h]
0x180002585  mov     esi, r9d
0x180002588  mov     [r11-48h], rax
0x18000258c  lea     r15, [rdx+28h]
0x180002590  lea     rax, [r11-50h]
0x180002594  mov     rcx, r15; SpinLock
0x180002597  mov     [r11-50h], rax
0x18000259b  mov     r13, r8
0x18000259e  mov     rdi, rdx
0x1800025a1  xor     ebp, ebp
0x1800025a3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800025aa  nop     dword ptr [rax+rax+00h]
0x1800025af  mov     rbx, [rdi+18h]
0x1800025b3  lea     r14, [rdi+18h]
0x1800025b7  mov     [rsp+118h+arg_8], al
0x1800025be  movzx   r12d, al
0x1800025c2  cmp     rbx, r14
0x1800025c5  jz      loc_180002935
0x1800025cb  mov     r15d, [rdi+150h]
0x1800025d2  movzx   r12d, [rsp+118h+arg_20]
0x1800025db  mov     [rsp+118h+var_58], 0
0x1800025e7  test    r15d, r15d
0x1800025ea  jnz     loc_18000295D
0x1800025f0  test    r12b, r12b
0x1800025f3  jnz     loc_1800028FD
0x1800025f9  mov     r9d, [rsp+118h+arg_18]
0x180002601  lea     rax, [rsp+118h+var_58]
0x180002609  mov     r8, r13
0x18000260c  mov     [rsp+118h+var_F8], rax
0x180002611  lea     rdx, [rbx-38h]
0x180002615  mov     rcx, rdi
0x180002618  call    HidpProcessInterruptReport
0x18000261d  mov     rax, [rsp+118h+var_58]
0x180002625  test    rax, rax
0x180002628  jz      short loc_180002665
0x18000262a  mov     rcx, [rsp+118h+var_48]
0x180002632  lea     rdx, [rsp+118h+var_50]
0x18000263a  cmp     [rcx], rdx
0x18000263d  jnz     loc_18000296C
0x180002643  add     rax, 0A8h
0x180002649  lea     rdx, [rsp+118h+var_50]
0x180002651  inc     ebp
0x180002653  mov     [rax], rdx
0x180002656  mov     [rax+8], rcx
0x18000265a  mov     [rcx], rax
0x18000265d  mov     [rsp+118h+var_48], rax
0x180002665  mov     rbx, [rbx]
0x180002668  cmp     rbx, r14
0x18000266b  jnz     loc_1800025DB
0x180002671  mov     esi, [rsp+118h+arg_18]
0x180002678  lea     r15, [rdi+28h]
0x18000267c  movzx   r12d, [rsp+118h+arg_8]
0x180002685  mov     rbx, [rsp+118h+arg_0]
0x18000268d  mov     rax, ds:0FFFFF78000000014h
0x180002697  mov     rcx, [rdi+168h]
0x18000269e  mov     [rdi+168h], rax
0x1800026a5  lock inc qword ptr [rdi+178h]
0x1800026ad  lock inc qword ptr [rdi+180h]
0x1800026b5  lock inc qword ptr [rdi+190h]
0x1800026bd  lock inc qword ptr [rdi+188h]
0x1800026c5  lock inc qword ptr [rdi+1A0h]
0x1800026cd  xor     edx, edx
0x1800026cf  xor     eax, eax
0x1800026d1  lock cmpxchg [rdi+164h], edx
0x1800026d9  jz      short loc_1800026E3
0x1800026db  lock inc qword ptr [rdi+198h]
0x1800026e3  cmp     dword ptr [rdi+0Ch], 2
0x1800026e7  jz      loc_1800027F5
0x1800026ed  mov     rdx, [rdi+170h]
0x1800026f4  test    rdx, rdx
0x1800026f7  jz      loc_1800027F5
0x1800026fd  mov     r9, [rdi+168h]
0x180002704  mov     rax, r9
0x180002707  sub     rax, rdx
0x18000270a  cmp     rax, 2FAF080h
0x180002710  jnb     loc_1800027F5
0x180002716  mov     r10, cs:WPP_GLOBAL_Control
0x18000271d  lea     rax, WPP_GLOBAL_Control
0x180002724  cmp     r10, rax
0x180002727  jz      short loc_180002735
0x180002729  mov     eax, [r10+2Ch]
0x18000272d  test    al, 10h
0x18000272f  jnz     loc_180002973
0x180002735  xor     dl, dl
0x180002737  lea     rax, WPP_RECORDER_INITIALIZED
0x18000273e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180002745  jz      short loc_180002753
0x180002747  cmp     word ptr [r10+48h], 0
0x18000274d  jnz     loc_180002985
0x180002753  xor     r8b, r8b
0x180002756  test    dl, dl
0x180002758  jnz     loc_18000298D
0x18000275e  test    r8b, r8b
0x180002761  jnz     loc_18000298D
0x180002767  movzx   edx, r12b; NewIrql
0x18000276b  mov     rcx, r15; SpinLock
0x18000276e  call    cs:__imp_KeReleaseSpinLock
0x180002775  nop     dword ptr [rax+rax+00h]
0x18000277a  mov     rcx, [rsp+118h+var_50]
0x180002782  lea     rax, [rsp+118h+var_50]
0x18000278a  cmp     rcx, rax
0x18000278d  jz      short loc_1800027D9
0x18000278f  lea     rax, [rsp+118h+var_50]
0x180002797  cmp     [rcx+8], rax
0x18000279b  jnz     loc_18000296C
0x1800027a1  mov     rax, [rcx]
0x1800027a4  cmp     [rax+8], rcx
0x1800027a8  jnz     loc_18000296C
0x1800027ae  lea     rdx, [rsp+118h+var_50]
0x1800027b6  mov     [rsp+118h+var_50], rax
0x1800027be  mov     [rax+8], rdx
0x1800027c2  add     rcx, 0FFFFFFFFFFFFFF58h; Irp
0x1800027c9  mov     dl, 6; PriorityBoost
0x1800027cb  call    cs:__imp_IofCompleteRequest
0x1800027d2  nop     dword ptr [rax+rax+00h]
0x1800027d7  jmp     short loc_18000277A
0x1800027d9  mov     rbx, [rsp+118h+arg_10]
0x1800027e1  add     rsp, 0E0h
0x1800027e8  pop     r15
0x1800027ea  pop     r14
0x1800027ec  pop     r13
0x1800027ee  pop     r12
0x1800027f0  pop     rdi
0x1800027f1  pop     rsi
0x1800027f2  pop     rbp
0x1800027f3  retn
0x1800027f5  mov     r9, [rdi+168h]
0x1800027fc  mov     [rdi+170h], r9
0x180002803  mov     r10, cs:WPP_GLOBAL_Control
0x18000280a  lea     rax, WPP_GLOBAL_Control
0x180002811  cmp     r10, rax
0x180002814  jnz     loc_180002917
0x18000281a  xor     dl, dl
0x18000281c  lea     rax, WPP_RECORDER_INITIALIZED
0x180002823  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000282a  setnz   r8b
0x18000282e  test    dl, dl
0x180002830  jnz     short loc_18000283B
0x180002832  test    r8b, r8b
0x180002835  jz      loc_180002767
0x18000283b  mov     rax, [rdi+198h]
0x180002842  mov     [rsp+118h+var_68], rax
0x18000284a  mov     rax, [rdi+190h]
0x180002851  mov     [rsp+118h+var_70], rax
0x180002859  mov     rax, [rdi+188h]
0x180002860  mov     [rsp+118h+var_78], rax
0x180002868  mov     rax, [rdi+180h]
0x18000286f  mov     [rsp+118h+var_80], rax
0x180002877  mov     rax, [rdi+178h]
0x18000287e  mov     [rsp+118h+var_88], rax
0x180002886  mov     rax, [rbx+828h]
0x18000288d  mov     [rsp+118h+var_90], rax
0x180002895  mov     rax, [rbx+820h]
0x18000289c  mov     [rsp+118h+var_98], rax
0x1800028a4  mov     rax, [rbx+818h]
0x1800028ab  mov     [rsp+118h+var_A0], rax
0x1800028b0  mov     rax, [rbx+810h]
0x1800028b7  mov     [rsp+118h+var_A8], rax
0x1800028bc  mov     eax, [rdi]
0x1800028be  mov     [rsp+118h+var_B0], rcx
0x1800028c3  mov     [rsp+118h+var_B8], r9
0x1800028c8  mov     [rsp+118h+var_C0], esi
0x1800028cc  mov     [rsp+118h+var_C8], ebp
0x1800028d0  mov     [rsp+118h+var_D0], eax
0x1800028d4  mov     rax, [rbx]
0x1800028d7  mov     [rsp+118h+var_D8], rax
0x1800028dc  mov     [rsp+118h+var_E8], 19h
0x1800028e3  mov     byte ptr [rsp+118h+var_F8], 4
0x1800028e8  mov     r9, [rbx+2B0h]
0x1800028ef  mov     rcx, [r10+18h]
0x1800028f3  call    WPP_RECORDER_AND_TRACE_SF_qdLLiiIIIIIIIII
0x1800028f8  jmp     loc_180002767
0x1800028fd  call    cs:__imp_RtlGetActiveConsoleId
0x180002904  nop     dword ptr [rax+rax+00h]
0x180002909  cmp     [rbx+44h], eax
0x18000290c  jz      loc_1800025F9
0x180002912  jmp     loc_180002665
0x180002917  mov     eax, [r10+2Ch]
0x18000291b  test    al, 10h
0x18000291d  jz      loc_18000281A
0x180002923  cmp     byte ptr [r10+29h], 4
0x180002928  jb      loc_18000281A
0x18000292e  mov     dl, 1
0x180002930  jmp     loc_18000281C
0x180002935  cmp     dword ptr [rdi+0Ch], 2
0x180002939  mov     rbx, [rsp+118h+arg_0]
0x180002941  jnz     loc_18000268D
0x180002947  mov     r9d, esi
0x18000294a  mov     r8, r13
0x18000294d  mov     rdx, rdi
0x180002950  mov     rcx, rbx
0x180002953  call    HidpProcessInterruptReportForCollection
0x180002958  jmp     loc_18000268D
0x18000295d  cmp     byte ptr [rbx+3Eh], 0
0x180002961  jnz     loc_1800025F0
0x180002967  jmp     loc_180002665
0x18000296c  mov     ecx, 3
0x180002971  int     29h; Win8: RtlFailFast(ecx)
0x180002973  cmp     byte ptr [r10+29h], 5
0x180002978  jb      loc_180002735
0x18000297e  mov     dl, 1
0x180002980  jmp     loc_180002737
0x180002985  mov     r8b, 1
0x180002988  jmp     loc_180002756
0x18000298d  mov     rax, [rdi+198h]
0x180002994  mov     [rsp+118h+var_68], rax
0x18000299c  mov     rax, [rdi+190h]
0x1800029a3  mov     [rsp+118h+var_70], rax
0x1800029ab  mov     rax, [rdi+188h]
0x1800029b2  mov     [rsp+118h+var_78], rax
0x1800029ba  mov     rax, [rdi+180h]
0x1800029c1  mov     [rsp+118h+var_80], rax
0x1800029c9  mov     rax, [rdi+178h]
0x1800029d0  mov     [rsp+118h+var_88], rax
0x1800029d8  mov     rax, [rbx+828h]
0x1800029df  mov     [rsp+118h+var_90], rax
0x1800029e7  mov     rax, [rbx+820h]
0x1800029ee  mov     [rsp+118h+var_98], rax
0x1800029f6  mov     rax, [rbx+818h]
0x1800029fd  mov     [rsp+118h+var_A0], rax
0x180002a02  mov     rax, [rbx+810h]
0x180002a09  mov     [rsp+118h+var_A8], rax
0x180002a0e  mov     eax, [rdi]
0x180002a10  mov     [rsp+118h+var_B0], rcx
0x180002a15  mov     [rsp+118h+var_B8], r9
0x180002a1a  mov     [rsp+118h+var_C0], esi
0x180002a1e  mov     [rsp+118h+var_C8], ebp
0x180002a22  mov     [rsp+118h+var_D0], eax
0x180002a26  mov     rax, [rbx]
0x180002a29  mov     [rsp+118h+var_D8], rax
0x180002a2e  mov     [rsp+118h+var_E8], 18h
0x180002a35  mov     byte ptr [rsp+118h+var_F8], 5
0x180002a3a  jmp     loc_1800028E8
```
