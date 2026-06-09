# UpdateNameState

- ea: `0x140017214`
- end: `0x14001763e`
- name: `UpdateNameState`
- size: `1066`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x140015818`

## callees

- `0x140007ed8`
- `0x140007ff8`
- `0x140008110`
- `0x140008160`
- `0x1400089c8`
- `0x14000c3ec`
- `0x14000dd3c`
- `0x140017214`
- `0x140028c9c`
- `0x1400400a4`
- `0x14004025c`
- `0x140040294`
- `0x1400439bc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001743c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001743c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400173f4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400173f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001747a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001747a`
- `ntoskrnl!ExAllocatePool2` at `0x14001727a`
- `ntoskrnl!ExAllocatePool2` at `0x1400173a9`
- `ntoskrnl!ExAllocatePool2` at `0x14001727a`
- `ntoskrnl!ExAllocatePool2` at `0x1400173a9`

## pseudocode

```c
__int64 __fastcall UpdateNameState(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        KIRQL NewIrql)
{
  bool v8; // cf
  __int16 v12; // di
  __int64 v13; // rsi
  __int64 Pool2; // rax
  unsigned int i; // edx
  __int64 v16; // r8
  unsigned int v17; // ecx
  unsigned __int32 v18; // ecx
  int v19; // eax
  int v20; // r10d
  int v21; // eax
  int v22; // eax
  __int64 v23; // rbp
  int v24; // eax
  int v25; // esi
  _QWORD *v26; // rax
  void *v27; // rsi
  int v28; // ebp

  v8 = (_BYTE)a6 != 0;
  LOBYTE(a6) = -(char)a6;
  v12 = v8 ? 16 : 32;
  v13 = a3 / 6;
  if ( (unsigned int)v13 <= 0x3E8 && 6 * (_DWORD)v13 == a3 )
  {
    Pool2 = ExAllocatePool2(64, 4LL * (unsigned int)(v13 + 1), 947151438);
    *(_QWORD *)(a2 + 48) = Pool2;
    if ( Pool2 )
    {
      for ( i = 0; i < (unsigned int)v13; *(_DWORD *)(*(_QWORD *)(a2 + 48) + 4 * v16) = v18 )
      {
        v16 = i;
        v17 = *(_DWORD *)(a1 + 6LL * i + 2);
        if ( v17 == -1 )
          v18 = 0;
        else
          v18 = _byteswap_ulong(v17);
        ++i;
      }
      *(_DWORD *)(*(_QWORD *)(a2 + 48) + 4 * v13) = -1;
      v19 = *(_DWORD *)(a2 + 72);
      if ( (v19 & 0x80u) == 0 )
        goto LABEL_40;
      *(_DWORD *)(a2 + 72) = v19 & 0xFFFFFF0F | 0x10;
      NbtCheckNameAddrTimer(a2);
      if ( (__int16)__ROR2__(*(_WORD *)a1, 8) < 0 )
      {
        *(_DWORD *)(a2 + 72) &= 0xFFFFFFF0;
        v21 = *(_DWORD *)(a2 + 72);
        if ( (_DWORD)v13 == 1 && *(_DWORD *)(a1 + 2) == v20 )
        {
          *(_DWORD *)(a2 + 32) = 0;
          v22 = v21 | 4;
        }
        else
        {
          v12 |= 0x200u;
          v22 = v21 | 8;
        }
        *(_DWORD *)(a2 + 72) = v22;
        goto LABEL_40;
      }
      if ( (unsigned int)v13 <= 1 )
      {
        *(_DWORD *)(a2 + 32) = _byteswap_ulong(*(_DWORD *)(a1 + 2));
        goto LABEL_40;
      }
      v23 = a7;
      a6 = 0;
      if ( byte_140039675 && a7 && (*(_DWORD *)(a7 + 240) & 0x2000) != 0 )
      {
        v24 = ChooseBestIpAddress(a1, a3, a5, a7, (__int64)&a6, 1);
        v25 = v24;
        if ( v24 >= 0 )
        {
          v26 = (_QWORD *)ExAllocatePool2(64, 72, 1215586894);
          v27 = v26;
          if ( v26 )
          {
            v26[2] = 0;
            v26[3] = v23;
            v26[4] = SessionSetupContinue;
            v26[5] = *(_QWORD *)(v23 + 32);
            StartLmHostTimer(v26);
            KeReleaseSpinLock(&SpinLock, NewIrql);
            if ( (BYTE3(xmmword_140038420) & 2) != 0 )
              WPP_SF_q(1049, 46, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, a1);
            v28 = NbtProcessLmhSvcRequest((__int64)v27, 0, *(_DWORD *)(a5 + 568));
            KeAcquireSpinLockRaiseToDpc(&SpinLock);
            if ( v28 >= 0 )
            {
              NbtDereferenceName((PVOID)a2, (__int64)"minio\\netbt\\sys\\inbound.c");
              return (unsigned int)v28;
            }
            ExFreePoolWithTag(v27, 0);
            if ( (BYTE3(xmmword_140038420) & 2) != 0 )
              WPP_SF_d(1049, 47, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, (unsigned int)v28);
          }
          else if ( (BYTE3(xmmword_140038420) & 2) != 0 )
          {
            WPP_SF_(1049, 48, WPP_80b00531435b366d117ee6d697c26c58_Traceguids);
          }
          v25 = 0;
          goto LABEL_36;
        }
        if ( (BYTE3(xmmword_140038420) & 2) != 0 )
          WPP_SF_d(1049, 49, WPP_80b00531435b366d117ee6d697c26c58_Traceguids, (unsigned int)v24);
      }
      else
      {
        if ( (BYTE3(xmmword_140038420) & 2) != 0 )
          WPP_SF_(1049, 50, WPP_80b00531435b366d117ee6d697c26c58_Traceguids);
        v25 = ChooseBestIpAddress(a1, a3, a5, v23, (__int64)&a6, 0);
        if ( v25 >= 0 )
LABEL_36:
          *(_DWORD *)(a2 + 32) = a6;
      }
      if ( v25 < 0 )
      {
        NbtDereferenceName((PVOID)a2, (__int64)"minio\\netbt\\sys\\inbound.c");
        return 0;
      }
LABEL_40:
      AddToHashTable(qword_140039468, a2 + 164, Str2, *(unsigned int *)(a2 + 32), 0, a2, 0, a5, v12);
      return 0;
    }
  }
  if ( (BYTE9(xmmword_140038420) & 0x40) != 0 )
    WPP_SF_qddds(
      *(_DWORD *)(a2 + 20),
      81,
      (unsigned int)WPP_8017b60c53a232e581eda6237e04704c_Traceguids,
      a2,
      *(_DWORD *)(a2 + 20),
      *(_DWORD *)(a2 + 20) - 1,
      242,
      (__int64)"minio\\netbt\\sys\\inbound.c");
  if ( *(_DWORD *)(a2 + 16) == -87097344 )
    --dword_140039760;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 20), 0xFFFFFFFF) == 1 )
  {
    NbtUnlinkNameFromHashTable(a2);
    NbtFreeNameAddr((PVOID)a2);
  }
  else
  {
    NbtCheckNameAddrTimer(a2);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140017214  push    rbx
0x140017216  push    rbp
0x140017217  push    rsi
0x140017218  push    rdi
0x140017219  push    r12
0x14001721b  push    r13
0x14001721d  push    r14
0x14001721f  push    r15
0x140017221  sub     rsp, 58h
0x140017225  neg     byte ptr [rsp+98h+arg_28]
0x14001722c  mov     eax, 0AAAAAAABh
0x140017231  mov     rbx, rdx
0x140017234  mov     r15d, r8d
0x140017237  sbb     di, di
0x14001723a  mov     r14, rcx
0x14001723d  mul     r8d
0x140017240  and     di, 0FFF0h
0x140017245  mov     esi, edx
0x140017247  add     di, 20h ; ' '
0x14001724b  shr     esi, 2
0x14001724e  cmp     esi, 3E8h
0x140017254  ja      loc_1400175B0
0x14001725a  lea     eax, [rsi+rsi*2]
0x14001725d  add     eax, eax
0x14001725f  cmp     eax, r8d
0x140017262  jnz     loc_1400175B0
0x140017268  lea     edx, [rsi+1]
0x14001726b  mov     ecx, 40h ; '@'
0x140017270  shl     rdx, 2
0x140017274  mov     r8d, 3874624Eh
0x14001727a  call    cs:__imp_ExAllocatePool2
0x140017281  nop     dword ptr [rax+rax+00h]
0x140017286  xor     r12d, r12d
0x140017289  mov     [rbx+30h], rax
0x14001728d  test    rax, rax
0x140017290  jz      loc_1400175B0
0x140017296  or      r10d, 0FFFFFFFFh
0x14001729a  mov     edx, r12d
0x14001729d  test    esi, esi
0x14001729f  jz      short loc_1400172C7
0x1400172a1  mov     r8d, edx
0x1400172a4  lea     rax, [r8+r8*2]
0x1400172a8  mov     ecx, [r14+rax*2+2]
0x1400172ad  cmp     ecx, r10d
0x1400172b0  jnz     short loc_1400172B7
0x1400172b2  mov     ecx, r12d
0x1400172b5  jmp     short loc_1400172B9
0x1400172b7  bswap   ecx
0x1400172b9  mov     rax, [rbx+30h]
0x1400172bd  inc     edx
0x1400172bf  mov     [rax+r8*4], ecx
0x1400172c3  cmp     edx, esi
0x1400172c5  jb      short loc_1400172A1
0x1400172c7  mov     rax, [rbx+30h]
0x1400172cb  mov     r13, [rsp+98h+arg_20]
0x1400172d3  mov     [rax+rsi*4], r10d
0x1400172d7  mov     eax, [rbx+48h]
0x1400172da  test    al, al
0x1400172dc  jns     loc_140017575
0x1400172e2  and     eax, 0FFFFFF1Fh
0x1400172e7  mov     rcx, rbx
0x1400172ea  or      eax, 10h
0x1400172ed  mov     [rbx+48h], eax
0x1400172f0  call    NbtCheckNameAddrTimer
0x1400172f5  movzx   r9d, word ptr [r14]
0x1400172f9  ror     r9w, 8
0x1400172fe  test    r9w, r9w
0x140017302  jns     short loc_14001732F
0x140017304  and     dword ptr [rbx+48h], 0FFFFFFF0h
0x140017308  mov     eax, [rbx+48h]
0x14001730b  cmp     esi, 1
0x14001730e  jnz     short loc_14001731F
0x140017310  cmp     [r14+2], r10d
0x140017314  jnz     short loc_14001731F
0x140017316  mov     [rbx+20h], r12d
0x14001731a  or      eax, 4
0x14001731d  jmp     short loc_140017327
0x14001731f  or      di, 200h
0x140017324  or      eax, 8
0x140017327  mov     [rbx+48h], eax
0x14001732a  jmp     loc_140017575
0x14001732f  cmp     esi, 1
0x140017332  jbe     loc_14001756C
0x140017338  cmp     cs:byte_140039675, r12b
0x14001733f  mov     rbp, [rsp+98h+arg_30]
0x140017347  mov     [rsp+98h+arg_28], r12d
0x14001734f  jz      loc_1400174F2
0x140017355  test    rbp, rbp
0x140017358  jz      loc_1400174F2
0x14001735e  test    dword ptr [rbp+0F0h], 2000h
0x140017368  jz      loc_1400174F2
0x14001736e  lea     rax, [rsp+98h+arg_28]
0x140017376  mov     byte ptr [rsp+98h+var_70], 1
0x14001737b  mov     r9, rbp
0x14001737e  mov     [rsp+98h+var_78], rax
0x140017383  mov     r8, r13
0x140017386  mov     edx, r15d
0x140017389  mov     rcx, r14
0x14001738c  call    ChooseBestIpAddress
0x140017391  mov     esi, eax
0x140017393  test    eax, eax
0x140017395  js      loc_1400174CE
0x14001739b  mov     edx, 48h ; 'H'
0x1400173a0  mov     r8d, 4874624Eh
0x1400173a6  lea     ecx, [rdx-8]
0x1400173a9  call    cs:__imp_ExAllocatePool2
0x1400173b0  nop     dword ptr [rax+rax+00h]
0x1400173b5  mov     rsi, rax
0x1400173b8  test    rax, rax
0x1400173bb  jz      loc_1400174AA
0x1400173c1  mov     [rax+10h], r12
0x1400173c5  mov     dl, 1
0x1400173c7  mov     [rax+18h], rbp
0x1400173cb  lea     rax, SessionSetupContinue
0x1400173d2  mov     [rsi+20h], rax
0x1400173d6  mov     rcx, [rbp+20h]
0x1400173da  mov     [rsi+28h], rcx
0x1400173de  mov     rcx, rsi
0x1400173e1  call    StartLmHostTimer
0x1400173e6  mov     dl, [rsp+98h+NewIrql]; NewIrql
0x1400173ed  lea     rcx, SpinLock; SpinLock
0x1400173f4  call    cs:__imp_KeReleaseSpinLock
0x1400173fb  nop     dword ptr [rax+rax+00h]
0x140017400  test    byte ptr cs:xmmword_140038420+3, 2
0x140017407  jz      short loc_140017422
0x140017409  mov     edx, 2Eh ; '.'
0x14001740e  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x140017415  mov     ecx, 419h
0x14001741a  mov     r9, r14
0x14001741d  call    WPP_SF_q
0x140017422  mov     r8d, [r13+238h]
0x140017429  xor     edx, edx
0x14001742b  mov     rcx, rsi
0x14001742e  call    NbtProcessLmhSvcRequest
0x140017433  lea     rcx, SpinLock; SpinLock
0x14001743a  mov     ebp, eax
0x14001743c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140017443  nop     dword ptr [rax+rax+00h]
0x140017448  test    ebp, ebp
0x14001744a  js      short loc_140017475
0x14001744c  lea     r8, aMinioNetbtSysI; "minio\\netbt\\sys\\inbound.c"
0x140017453  mov     r9d, 0E6Bh
0x140017459  mov     [rsp+98h+var_78], r8; __int64
0x14001745e  mov     edx, 1
0x140017463  mov     r8b, 1
0x140017466  mov     rcx, rbx; P
0x140017469  call    NbtDereferenceName
0x14001746e  mov     eax, ebp
0x140017470  jmp     loc_14001762C
0x140017475  xor     edx, edx; Tag
0x140017477  mov     rcx, rsi; P
0x14001747a  call    cs:__imp_ExFreePoolWithTag
0x140017481  nop     dword ptr [rax+rax+00h]
0x140017486  test    byte ptr cs:xmmword_140038420+3, 2
0x14001748d  jz      short loc_1400174C9
0x14001748f  mov     edx, 2Fh ; '/'
0x140017494  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x14001749b  mov     ecx, 419h
0x1400174a0  mov     r9d, ebp
0x1400174a3  call    WPP_SF_d
0x1400174a8  jmp     short loc_1400174C9
0x1400174aa  test    byte ptr cs:xmmword_140038420+3, 2
0x1400174b1  jz      short loc_1400174C9
0x1400174b3  mov     edx, 30h ; '0'
0x1400174b8  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x1400174bf  mov     ecx, 419h
0x1400174c4  call    WPP_SF_
0x1400174c9  mov     esi, r12d
0x1400174cc  jmp     short loc_14001753A
0x1400174ce  test    byte ptr cs:xmmword_140038420+3, 2
0x1400174d5  jz      short loc_140017544
0x1400174d7  mov     edx, 31h ; '1'
0x1400174dc  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x1400174e3  mov     ecx, 419h
0x1400174e8  mov     r9d, eax
0x1400174eb  call    WPP_SF_d
0x1400174f0  jmp     short loc_140017544
0x1400174f2  test    byte ptr cs:xmmword_140038420+3, 2
0x1400174f9  jz      short loc_140017511
0x1400174fb  mov     edx, 32h ; '2'
0x140017500  lea     r8, WPP_80b00531435b366d117ee6d697c26c58_Traceguids
0x140017507  mov     ecx, 419h
0x14001750c  call    WPP_SF_
0x140017511  lea     rax, [rsp+98h+arg_28]
0x140017519  mov     byte ptr [rsp+98h+var_70], r12b
0x14001751e  mov     r9, rbp
0x140017521  mov     [rsp+98h+var_78], rax
0x140017526  mov     r8, r13
0x140017529  mov     edx, r15d
0x14001752c  mov     rcx, r14
0x14001752f  call    ChooseBestIpAddress
0x140017534  mov     esi, eax
0x140017536  test    eax, eax
0x140017538  js      short loc_140017544
0x14001753a  mov     eax, [rsp+98h+arg_28]
0x140017541  mov     [rbx+20h], eax
0x140017544  test    esi, esi
0x140017546  jns     short loc_140017575
0x140017548  lea     r8, aMinioNetbtSysI; "minio\\netbt\\sys\\inbound.c"
0x14001754f  mov     r9d, 0EA7h
0x140017555  mov     [rsp+98h+var_78], r8; __int64
0x14001755a  mov     edx, 1
0x14001755f  mov     r8b, 1
0x140017562  mov     rcx, rbx; P
0x140017565  call    NbtDereferenceName
0x14001756a  jmp     short loc_1400175AC
0x14001756c  mov     eax, [r14+2]
0x140017570  bswap   eax
0x140017572  mov     [rbx+20h], eax
0x140017575  mov     r9d, [rbx+20h]
0x140017579  lea     rdx, [rbx+0A4h]
0x140017580  mov     r8, cs:Str2
0x140017587  mov     rcx, cs:qword_140039468
0x14001758e  mov     [rsp+98h+var_58], di
0x140017593  mov     [rsp+98h+var_60], r13
0x140017598  mov     [rsp+98h+var_68], r12
0x14001759d  mov     [rsp+98h+var_70], rbx
0x1400175a2  mov     dword ptr [rsp+98h+var_78], r12d
0x1400175a7  call    AddToHashTable
0x1400175ac  xor     eax, eax
0x1400175ae  jmp     short loc_14001762C
0x1400175b0  test    byte ptr cs:xmmword_140038420+9, 40h
0x1400175b7  jz      short loc_1400175EF
0x1400175b9  mov     ecx, [rbx+14h]
0x1400175bc  lea     r8, aMinioNetbtSysI; "minio\\netbt\\sys\\inbound.c"
0x1400175c3  mov     [rsp+98h+var_60], r8
0x1400175c8  mov     edx, 51h ; 'Q'
0x1400175cd  mov     dword ptr [rsp+98h+var_68], 0DF2h
0x1400175d5  lea     r8, WPP_8017b60c53a232e581eda6237e04704c_Traceguids
0x1400175dc  mov     r9, rbx
0x1400175df  lea     eax, [rcx-1]
0x1400175e2  mov     dword ptr [rsp+98h+var_70], eax
0x1400175e6  mov     dword ptr [rsp+98h+var_78], ecx
0x1400175ea  call    WPP_SF_qddds
0x1400175ef  cmp     dword ptr [rbx+10h], 0FACF0000h
0x1400175f6  jnz     short loc_140017603
0x1400175f8  or      r10d, 0FFFFFFFFh
0x1400175fc  add     cs:dword_140039760, r10d
0x140017603  or      eax, 0FFFFFFFFh
0x140017606  lock xadd [rbx+14h], eax
0x14001760b  mov     rcx, rbx
0x14001760e  cmp     eax, 1
0x140017611  jz      short loc_14001761A
0x140017613  call    NbtCheckNameAddrTimer
0x140017618  jmp     short loc_140017627
0x14001761a  call    NbtUnlinkNameFromHashTable
0x14001761f  mov     rcx, rbx; P
0x140017622  call    NbtFreeNameAddr
0x140017627  mov     eax, 0C0000001h
0x14001762c  add     rsp, 58h
0x140017630  pop     r15
0x140017632  pop     r14
0x140017634  pop     r13
0x140017636  pop     r12
0x140017638  pop     rdi
0x140017639  pop     rsi
0x14001763a  pop     rbp
0x14001763b  pop     rbx
0x14001763c  retn
```
