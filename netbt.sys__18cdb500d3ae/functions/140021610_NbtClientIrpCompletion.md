# NbtClientIrpCompletion

- ea: `0x140021610`
- end: `0x140021aa7`
- name: `NbtClientIrpCompletion`
- size: `1175`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140006878`
- `0x140013184`
- `0x140021610`
- `0x140021ab0`
- `0x140021c1c`
- `0x140024cc0`
- `0x140027e60`
- `0x14002f40c`
- `0x1400401c4`
- `0x1400406e8`
- `0x1400434f8`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140021a43`
- `ntoskrnl!IofCompleteRequest` at `0x140021a43`
- `ntoskrnl!IoFreeMdl` at `0x140021a6b`
- `ntoskrnl!IoFreeMdl` at `0x140021a6b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021648`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021a52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021648`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140021a52`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400219b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021a32`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400219b1`
- `ntoskrnl!KeReleaseSpinLock` at `0x140021a32`

## pseudocode

```c
__int64 __fastcall NbtClientIrpCompletion(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  KSPIN_LOCK *v4; // r12
  int v5; // esi
  __int64 v6; // rbp
  char v9; // r13
  __int64 v10; // rcx
  __int64 v11; // r8
  KIRQL v12; // r15
  unsigned int v13; // eax
  int v14; // esi
  __int64 v15; // rcx
  ULONG v16; // r12d
  __int64 v17; // rdx
  __int64 v18; // rdx
  PIRP v19; // rbp
  __int64 v20; // rdx
  ULONG v21; // esi
  int v22; // eax
  int v23; // edx
  int v24; // r8d
  __int64 result; // rax
  KIRQL NewIrql; // [rsp+88h] [rbp+10h]
  PIRP Irp; // [rsp+90h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a3 + 24);
  v4 = (KSPIN_LOCK *)(a3 + 104);
  v5 = *(_DWORD *)(a2 + 48);
  v6 = *(unsigned int *)(a2 + 56);
  Irp = 0;
  v9 = 1;
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 104));
  NewIrql = v12;
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
    WPP_SF_qqqdd(v10, 17, v11, a3, v3, a2, v5, v6);
  v13 = *(_DWORD *)(a3 + 284);
  *(_QWORD *)(a3 + 264) += v6;
  *(_QWORD *)(a3 + 216) = 0;
  *(_DWORD *)(a3 + 284) = (unsigned int)v6 < v13 ? v13 - v6 : 0;
  if ( !v3 || *(_DWORD *)(a3 + 88) != 7 )
  {
    v5 = -1073741299;
    *(_QWORD *)(a2 + 8) = *(_QWORD *)(a3 + 288);
    goto LABEL_40;
  }
  if ( v5 >= 0 )
  {
    *(_DWORD *)(v3 + 216) += v6;
    *(_DWORD *)(v3 + 212) += v6;
    v14 = *(_DWORD *)(v3 + 208) - *(_DWORD *)(v3 + 212);
    v15 = *(unsigned int *)(v3 + 216);
    v16 = *(_DWORD *)(v3 + 220) - v15;
    *(_QWORD *)(a2 + 56) = v15;
    if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      WPP_SF_qqqdd(v15, 18, v11, a3, v3, a2, v14, v16);
    if ( !v14 )
    {
      v5 = 0;
      v9 = 0;
      *(_QWORD *)(*(_QWORD *)(v3 + 192) + 8LL) = *(_QWORD *)(v3 + 200);
      *(_QWORD *)(v3 + 192) = 0;
      *(_QWORD *)(v3 + 200) = 0;
      if ( (int)NbtBuildIrpForIndicateBuffer(a3, &Irp) < 0 )
      {
        LOBYTE(v17) = 6;
        OutOfRsrcKillUnderLock(a3, v17);
        v5 = -1073741299;
      }
      if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      {
        v18 = 19;
LABEL_16:
        v19 = Irp;
        WPP_SF_qqq(1051, v18, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, a3, v3, Irp);
        goto LABEL_32;
      }
LABEL_24:
      v19 = Irp;
      goto LABEL_32;
    }
    if ( v16 )
    {
      v19 = (PIRP)a2;
      v21 = *(_DWORD *)(v3 + 208) - *(_DWORD *)(v3 + 212);
      if ( (BYTE3(xmmword_140038420) & 8) != 0 )
      {
        v22 = *(_DWORD *)(v3 + 208) - *(_DWORD *)(v3 + 212);
        if ( v21 >= v16 )
          v22 = v16;
        WPP_SF_qqqdd(v15, 21, v11, a3, v3, a2, v21, v22);
      }
      v5 = NbtProcessClientIrp((struct _MDL **)a3, v21, a2, 0);
      if ( v5 != -1073741802 )
        v19 = 0;
    }
    else
    {
      v5 = -2147483643;
      *(_QWORD *)(*(_QWORD *)(v3 + 192) + 8LL) = *(_QWORD *)(v3 + 200);
      *(_QWORD *)(v3 + 192) = 0;
      *(_QWORD *)(v3 + 200) = 0;
      Irp = (PIRP)NbtDequeueClientIrp(a3, v3);
      v19 = Irp;
      if ( Irp )
        goto LABEL_32;
      if ( *(_DWORD *)(v3 + 212) == *(_DWORD *)(v3 + 208) )
      {
        v5 = NbtBuildIrpForIndicateBuffer(a3, &Irp);
        v9 = 0;
        if ( v5 < 0 )
        {
          LOBYTE(v20) = 6;
          OutOfRsrcKillUnderLock(a3, v20);
          v5 = -1073741299;
        }
        if ( (BYTE3(xmmword_140038420) & 8) != 0 )
        {
          v18 = 20;
          goto LABEL_16;
        }
        goto LABEL_24;
      }
      *(_DWORD *)(a3 + 92) = 0;
      *(_QWORD *)(a3 + 200) = PartialReceive;
      *(_DWORD *)(a3 + 208) = 13;
    }
LABEL_32:
    if ( v19 )
    {
      if ( (unsigned __int8)NbtQueueDeferredPostIrp((PVOID)a3) )
      {
        v9 = 0;
LABEL_38:
        v4 = (KSPIN_LOCK *)(a3 + 104);
LABEL_39:
        v12 = NewIrql;
        goto LABEL_40;
      }
      if ( v19 != (PIRP)a2 )
      {
        if ( v9 )
        {
          v19->IoStatus.Status = -1073741299;
          *(_QWORD *)(*(_QWORD *)(v3 + 192) + 8LL) = *(_QWORD *)(v3 + 200);
          *(_QWORD *)(v3 + 192) = 0;
          *(_QWORD *)(v3 + 200) = 0;
          v4 = (KSPIN_LOCK *)(a3 + 104);
          KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 104), v12);
          IofCompleteRequest(v19, 0);
          NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 104));
        }
        else
        {
          IoFreeMdl(v19->MdlAddress);
          v19->MdlAddress = 0;
          NbtFreeIrp(v19);
          v4 = (KSPIN_LOCK *)(a3 + 104);
        }
        v5 = -1073741299;
        v9 = 1;
        goto LABEL_39;
      }
      v5 = -1073741299;
      *(_QWORD *)(*(_QWORD *)(v3 + 192) + 8LL) = *(_QWORD *)(v3 + 200);
      *(_QWORD *)(v3 + 192) = 0;
      *(_QWORD *)(v3 + 200) = 0;
    }
    v9 = 1;
    goto LABEL_38;
  }
  if ( v5 == -1073741801 )
  {
    *(_DWORD *)(a3 + 92) = 0;
    *(_QWORD *)(a3 + 200) = PartialReceive;
    *(_DWORD *)(a3 + 208) = 26;
  }
  *(_QWORD *)(*(_QWORD *)(v3 + 192) + 8LL) = *(_QWORD *)(v3 + 200);
  *(_QWORD *)(v3 + 192) = 0;
  *(_QWORD *)(v3 + 200) = 0;
LABEL_40:
  if ( (BYTE3(xmmword_140038420) & 8) != 0 )
    WPP_SF_qqqd(1051, 22, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, a3, v3, a2, v5);
  KeReleaseSpinLock(v4, v12);
  if ( v9 )
    NbtDereferenceLowerConnection(a3, v23, v24, 984, (__int64)"minio\\netbt\\sys\\nt\\tdihndlr.c");
  result = (unsigned int)v5;
  *(_DWORD *)(a2 + 48) = v5;
  return result;
}

```

## disassembly

```asm
0x140021610  mov     rax, rsp
0x140021613  mov     [rax+8], rbx
0x140021617  push    rbp
0x140021618  push    rsi
0x140021619  push    rdi
0x14002161a  push    r12
0x14002161c  push    r13
0x14002161e  push    r14
0x140021620  push    r15
0x140021622  sub     rsp, 40h
0x140021626  mov     rbx, [r8+18h]
0x14002162a  lea     r12, [r8+68h]
0x14002162e  mov     esi, [rdx+30h]
0x140021631  mov     rcx, r12; SpinLock
0x140021634  mov     ebp, [rdx+38h]
0x140021637  mov     rdi, r8
0x14002163a  mov     r14, rdx
0x14002163d  mov     qword ptr [rax+18h], 0
0x140021645  mov     r13b, 1
0x140021648  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002164f  nop     dword ptr [rax+rax+00h]
0x140021654  mov     r15b, al
0x140021657  mov     [rsp+78h+NewIrql], al
0x14002165e  test    byte ptr cs:xmmword_140038420+3, 8
0x140021665  jz      short loc_140021686
0x140021667  mov     [rsp+78h+var_40], ebp
0x14002166b  mov     edx, 11h
0x140021670  mov     [rsp+78h+var_48], esi
0x140021674  mov     r9, rdi
0x140021677  mov     [rsp+78h+var_50], r14
0x14002167c  mov     [rsp+78h+var_58], rbx
0x140021681  call    WPP_SF_qqqdd
0x140021686  mov     eax, [rdi+11Ch]
0x14002168c  mov     ecx, eax
0x14002168e  add     [rdi+108h], rbp
0x140021695  sub     ecx, ebp
0x140021697  cmp     ebp, eax
0x140021699  mov     qword ptr [rdi+0D8h], 0
0x1400216a4  sbb     eax, eax
0x1400216a6  and     eax, ecx
0x1400216a8  mov     [rdi+11Ch], eax
0x1400216ae  test    rbx, rbx
0x1400216b1  jz      loc_140021A92
0x1400216b7  cmp     dword ptr [rdi+58h], 7
0x1400216bb  jnz     loc_140021A92
0x1400216c1  test    esi, esi
0x1400216c3  jns     short loc_140021719
0x1400216c5  cmp     esi, 0C0000017h
0x1400216cb  jnz     short loc_1400216EC
0x1400216cd  lea     rax, PartialReceive
0x1400216d4  mov     dword ptr [rdi+5Ch], 0
0x1400216db  mov     [rdi+0C8h], rax
0x1400216e2  mov     dword ptr [rdi+0D0h], 1Ah
0x1400216ec  mov     rcx, [rbx+0C0h]
0x1400216f3  mov     rax, [rbx+0C8h]
0x1400216fa  mov     [rcx+8], rax
0x1400216fe  mov     qword ptr [rbx+0C0h], 0
0x140021709  mov     qword ptr [rbx+0C8h], 0
0x140021714  jmp     loc_14002197B
0x140021719  add     [rbx+0D8h], ebp
0x14002171f  add     [rbx+0D4h], ebp
0x140021725  mov     esi, [rbx+0D0h]
0x14002172b  sub     esi, [rbx+0D4h]
0x140021731  mov     ecx, [rbx+0D8h]
0x140021737  mov     r12d, [rbx+0DCh]
0x14002173e  sub     r12d, ecx
0x140021741  mov     [r14+38h], rcx
0x140021745  test    byte ptr cs:xmmword_140038420+3, 8
0x14002174c  jz      short loc_14002176E
0x14002174e  mov     [rsp+78h+var_40], r12d
0x140021753  mov     edx, 12h
0x140021758  mov     [rsp+78h+var_48], esi
0x14002175c  mov     r9, rdi
0x14002175f  mov     [rsp+78h+var_50], r14
0x140021764  mov     [rsp+78h+var_58], rbx
0x140021769  call    WPP_SF_qqqdd
0x14002176e  mov     r15d, 0C000020Dh
0x140021774  test    esi, esi
0x140021776  jnz     loc_140021803
0x14002177c  mov     rcx, [rbx+0C0h]
0x140021783  lea     rdx, [rsp+78h+Irp]
0x14002178b  mov     rax, [rbx+0C8h]
0x140021792  xor     r12d, r12d
0x140021795  mov     esi, r12d
0x140021798  mov     r13b, r12b
0x14002179b  mov     [rcx+8], rax
0x14002179f  mov     rcx, rdi
0x1400217a2  mov     [rbx+0C0h], r12
0x1400217a9  mov     [rbx+0C8h], r12
0x1400217b0  call    NbtBuildIrpForIndicateBuffer
0x1400217b5  test    eax, eax
0x1400217b7  jns     short loc_1400217C6
0x1400217b9  mov     dl, 6
0x1400217bb  mov     rcx, rdi
0x1400217be  call    OutOfRsrcKillUnderLock
0x1400217c3  mov     esi, r15d
0x1400217c6  test    byte ptr cs:xmmword_140038420+3, 8
0x1400217cd  jz      loc_14002189A
0x1400217d3  mov     edx, 13h
0x1400217d8  mov     rbp, [rsp+78h+Irp]
0x1400217e0  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x1400217e7  mov     [rsp+78h+var_50], rbp
0x1400217ec  mov     ecx, 41Bh
0x1400217f1  mov     r9, rdi
0x1400217f4  mov     [rsp+78h+var_58], rbx
0x1400217f9  call    WPP_SF_qqq
0x1400217fe  jmp     loc_140021920
0x140021803  test    r12d, r12d
0x140021806  jnz     loc_1400218C2
0x14002180c  mov     rcx, [rbx+0C0h]
0x140021813  xor     r12d, r12d
0x140021816  mov     rax, [rbx+0C8h]
0x14002181d  mov     rdx, rbx
0x140021820  mov     esi, 80000005h
0x140021825  mov     [rcx+8], rax
0x140021829  mov     rcx, rdi
0x14002182c  mov     [rbx+0C0h], r12
0x140021833  mov     [rbx+0C8h], r12
0x14002183a  call    NbtDequeueClientIrp
0x14002183f  mov     [rsp+78h+Irp], rax
0x140021847  mov     rbp, rax
0x14002184a  test    rax, rax
0x14002184d  jnz     loc_140021920
0x140021853  mov     eax, [rbx+0D0h]
0x140021859  cmp     [rbx+0D4h], eax
0x14002185f  jnz     short loc_1400218A4
0x140021861  lea     rdx, [rsp+78h+Irp]
0x140021869  mov     rcx, rdi
0x14002186c  call    NbtBuildIrpForIndicateBuffer
0x140021871  mov     esi, eax
0x140021873  mov     r13b, r12b
0x140021876  test    eax, eax
0x140021878  jns     short loc_140021887
0x14002187a  mov     dl, 6
0x14002187c  mov     rcx, rdi
0x14002187f  call    OutOfRsrcKillUnderLock
0x140021884  mov     esi, r15d
0x140021887  test    byte ptr cs:xmmword_140038420+3, 8
0x14002188e  jz      short loc_14002189A
0x140021890  mov     edx, 14h
0x140021895  jmp     loc_1400217D8
0x14002189a  mov     rbp, [rsp+78h+Irp]
0x1400218a2  jmp     short loc_140021920
0x1400218a4  lea     rax, PartialReceive
0x1400218ab  mov     [rdi+5Ch], r12d
0x1400218af  mov     [rdi+0C8h], rax
0x1400218b6  mov     dword ptr [rdi+0D0h], 0Dh
0x1400218c0  jmp     short loc_140021920
0x1400218c2  mov     esi, [rbx+0D0h]
0x1400218c8  mov     rbp, r14
0x1400218cb  sub     esi, [rbx+0D4h]
0x1400218d1  test    byte ptr cs:xmmword_140038420+3, 8
0x1400218d8  jz      short loc_140021902
0x1400218da  cmp     esi, r12d
0x1400218dd  mov     eax, esi
0x1400218df  mov     edx, 15h
0x1400218e4  mov     r9, rdi
0x1400218e7  cmovnb  eax, r12d
0x1400218eb  mov     [rsp+78h+var_40], eax
0x1400218ef  mov     [rsp+78h+var_48], esi
0x1400218f3  mov     [rsp+78h+var_50], r14
0x1400218f8  mov     [rsp+78h+var_58], rbx
0x1400218fd  call    WPP_SF_qqqdd
0x140021902  xor     r9d, r9d
0x140021905  mov     r8, r14
0x140021908  mov     edx, esi
0x14002190a  mov     rcx, rdi
0x14002190d  call    NbtProcessClientIrp
0x140021912  xor     r12d, r12d
0x140021915  mov     esi, eax
0x140021917  cmp     eax, 0C0000016h
0x14002191c  cmovnz  rbp, r12
0x140021920  test    rbp, rbp
0x140021923  jz      short loc_14002196C
0x140021925  movzx   r9d, r13b
0x140021929  mov     r8, rbp
0x14002192c  mov     rdx, rbx
0x14002192f  mov     rcx, rdi; Context
0x140021932  call    NbtQueueDeferredPostIrp
0x140021937  test    al, al
0x140021939  jz      short loc_140021940
0x14002193b  mov     r13b, r12b
0x14002193e  jmp     short loc_14002196F
0x140021940  cmp     rbp, r14
0x140021943  jnz     loc_1400219FB
0x140021949  mov     rcx, [rbx+0C0h]
0x140021950  mov     esi, r15d
0x140021953  mov     rax, [rbx+0C8h]
0x14002195a  mov     [rcx+8], rax
0x14002195e  mov     [rbx+0C0h], r12
0x140021965  mov     [rbx+0C8h], r12
0x14002196c  mov     r13b, 1
0x14002196f  lea     r12, [rdi+68h]
0x140021973  mov     r15b, [rsp+78h+NewIrql]
0x14002197b  test    byte ptr cs:xmmword_140038420+3, 8
0x140021982  jz      short loc_1400219AB
0x140021984  mov     [rsp+78h+var_48], esi
0x140021988  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x14002198f  mov     [rsp+78h+var_50], r14
0x140021994  mov     edx, 16h
0x140021999  mov     ecx, 41Bh
0x14002199e  mov     [rsp+78h+var_58], rbx
0x1400219a3  mov     r9, rdi
0x1400219a6  call    WPP_SF_qqqd
0x1400219ab  mov     dl, r15b; NewIrql
0x1400219ae  mov     rcx, r12; SpinLock
0x1400219b1  call    cs:__imp_KeReleaseSpinLock
0x1400219b8  nop     dword ptr [rax+rax+00h]
0x1400219bd  test    r13b, r13b
0x1400219c0  jz      short loc_1400219DC
0x1400219c2  lea     rax, aMinioNetbtSysN_2; "minio\\netbt\\sys\\nt\\tdihndlr.c"
0x1400219c9  mov     r9d, 3D8h
0x1400219cf  mov     rcx, rdi
0x1400219d2  mov     [rsp+78h+var_58], rax
0x1400219d7  call    NbtDereferenceLowerConnection
0x1400219dc  mov     rbx, [rsp+78h+arg_0]
0x1400219e4  mov     eax, esi
0x1400219e6  mov     [r14+30h], esi
0x1400219ea  add     rsp, 40h
0x1400219ee  pop     r15
0x1400219f0  pop     r14
0x1400219f2  pop     r13
0x1400219f4  pop     r12
0x1400219f6  pop     rdi
0x1400219f7  pop     rsi
0x1400219f8  pop     rbp
0x1400219f9  retn
0x1400219fb  test    r13b, r13b
0x1400219fe  jz      short loc_140021A67
0x140021a00  mov     dl, [rsp+78h+NewIrql]; NewIrql
0x140021a07  mov     [rbp+30h], r15d
0x140021a0b  mov     rcx, [rbx+0C0h]
0x140021a12  mov     rax, [rbx+0C8h]
0x140021a19  mov     [rcx+8], rax
0x140021a1d  mov     [rbx+0C0h], r12
0x140021a24  mov     [rbx+0C8h], r12
0x140021a2b  lea     r12, [rdi+68h]
0x140021a2f  mov     rcx, r12; SpinLock
0x140021a32  call    cs:__imp_KeReleaseSpinLock
0x140021a39  nop     dword ptr [rax+rax+00h]
0x140021a3e  xor     edx, edx; PriorityBoost
0x140021a40  mov     rcx, rbp; Irp
0x140021a43  call    cs:__imp_IofCompleteRequest
0x140021a4a  nop     dword ptr [rax+rax+00h]
0x140021a4f  mov     rcx, r12; SpinLock
0x140021a52  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140021a59  nop     dword ptr [rax+rax+00h]
0x140021a5e  mov     [rsp+78h+NewIrql], al
0x140021a65  jmp     short loc_140021A87
0x140021a67  mov     rcx, [rbp+8]; Mdl
0x140021a6b  call    cs:__imp_IoFreeMdl
0x140021a72  nop     dword ptr [rax+rax+00h]
0x140021a77  mov     rcx, rbp; Irp
0x140021a7a  mov     [rbp+8], r12
0x140021a7e  call    NbtFreeIrp
0x140021a83  lea     r12, [rdi+68h]
0x140021a87  mov     esi, r15d
0x140021a8a  mov     r13b, 1
0x140021a8d  jmp     loc_140021973
0x140021a92  mov     rax, [rdi+120h]
0x140021a99  mov     esi, 0C000020Dh
0x140021a9e  mov     [r14+8], rax
0x140021aa2  jmp     loc_14002197B
```
