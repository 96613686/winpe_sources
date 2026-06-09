# CRdpHintManager::OnGeometryChanged(IRdpWindowTracker *,unsigned __int64)

- ea: `0x1400349c0`
- end: `0x140034c23`
- name: `?OnGeometryChanged@CRdpHintManager@@UEAAJPEAVIRdpWindowTracker@@_K@Z`
- size: `611`
- prototype: `int(CRdpHintManager *__hidden this, struct IRdpWindowTracker *, unsigned __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x14000d350`
- `0x14000efb8`
- `0x1400304c8`
- `0x140032ee0`
- `0x140033cd4`
- `0x1400349c0`
- `0x1400366a0`
- `0x14006b010`

## import_xrefs

- `USER32!CopyRect` at `0x140034b92`
- `USER32!CopyRect` at `0x140034ba3`
- `USER32!CopyRect` at `0x140034b92`
- `USER32!CopyRect` at `0x140034ba3`

## pseudocode

```c
__int64 __fastcall CRdpHintManager::OnGeometryChanged(CRdpHintManager *this, struct IRdpWindowTracker *a2, HWND a3)
{
  RDPGraphicsTraceLogging *v6; // rcx
  int v7; // ebx
  unsigned int v8; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 i; // rdx
  __int128 *v13; // rax
  __int128 *v14; // rcx
  __int64 v15; // rdx
  __int128 v16; // xmm0
  __int128 v17; // xmm0
  __int64 NextOf; // rax
  __int64 v19; // rbx
  char *v21; // [rsp+70h] [rbp+8h] BYREF

  v21 = (char *)this + 8;
  CTSCriticalSection::Lock((CRdpHintManager *)((char *)this + 8));
  v7 = (*(__int64 (__fastcall **)(struct IRdpWindowTracker *, HWND, char *))(*(_QWORD *)a2 + 32LL))(
         a2,
         a3,
         (char *)this + 536);
  if ( v7 >= 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsVOBRHintWindowTracker(v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    for ( i = 0; ; i = v19 )
    {
      NextOf = CTEntryList<RDP_TRACKED_WINDOW_NODE,0>::GetNextOfEx((char *)this + 56, i);
      v19 = NextOf;
      if ( !NextOf )
        break;
      if ( *(HWND *)(NextOf + 32) == a3 )
      {
        v13 = (__int128 *)(NextOf + 1176);
        v14 = (__int128 *)((char *)this + 536);
        v15 = 8;
        do
        {
          v16 = *v14;
          v14 += 8;
          *v13 = v16;
          v13 += 8;
          *(v13 - 7) = *(v14 - 7);
          *(v13 - 6) = *(v14 - 6);
          *(v13 - 5) = *(v14 - 5);
          *(v13 - 4) = *(v14 - 4);
          *(v13 - 3) = *(v14 - 3);
          *(v13 - 2) = *(v14 - 2);
          *(v13 - 1) = *(v14 - 1);
          --v15;
        }
        while ( v15 );
        *v13 = *v14;
        v13[1] = v14[1];
        v13[2] = v14[2];
        v13[3] = v14[3];
        v13[4] = v14[4];
        v13[5] = v14[5];
        v17 = v14[6];
        *(_DWORD *)(v19 + 1160) = 1;
        *(_DWORD *)(v19 + 1164) = 1;
        v13[6] = v17;
        *(_QWORD *)(v19 + 64) = *((_QWORD *)this + 68);
        *(_QWORD *)(v19 + 72) = *((_QWORD *)this + 70);
        CopyRect((LPRECT)(v19 + 80), (const RECT *)((char *)this + 584));
        CopyRect((LPRECT)(v19 + 96), (const RECT *)((char *)this + 568));
      }
    }
    v7 = CRdpHintManager::AdjustGeometryForWindow((CRdpHintManager *)((char *)this - 48), a3);
    if ( v7 >= 0 )
    {
      CRdpHintManager::UpdateHints((CRdpHintManager *)((char *)this - 48));
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 36;
      v10 = "AdjustGeometryForWindow() failed";
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 34;
    v10 = "pSender->GetWindowState() failed";
LABEL_6:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)&WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids,
      v8,
      (__int64)v10,
      v7);
  }
LABEL_24:
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v21);
  return 0;
}

```

## disassembly

```asm
0x1400349c0  push    rbx
0x1400349c2  push    rbp
0x1400349c3  push    rsi
0x1400349c4  push    rdi
0x1400349c5  push    r14
0x1400349c7  push    r15
0x1400349c9  sub     rsp, 38h
0x1400349cd  mov     rsi, rcx
0x1400349d0  mov     rbp, r8
0x1400349d3  add     rcx, 8; this
0x1400349d7  mov     rbx, rdx
0x1400349da  mov     [rsp+68h+arg_0], rcx
0x1400349df  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1400349e4  mov     rax, [rbx]
0x1400349e7  lea     r15, [rsi+218h]
0x1400349ee  mov     r8, r15
0x1400349f1  mov     rdx, rbp
0x1400349f4  mov     rcx, rbx
0x1400349f7  mov     rax, [rax+20h]
0x1400349fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140034a00  mov     ebx, eax
0x140034a02  test    eax, eax
0x140034a04  jns     short loc_140034A6A
0x140034a06  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a0d  lea     rdi, WPP_GLOBAL_Control
0x140034a14  cmp     rcx, rdi
0x140034a17  jz      loc_140034C0A
0x140034a1d  test    byte ptr [rcx+1Ch], 8
0x140034a21  jz      loc_140034C0A
0x140034a27  cmp     byte ptr [rcx+19h], 2
0x140034a2b  jb      loc_140034C0A
0x140034a31  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034a36  mov     edx, 22h ; '"'
0x140034a3b  lea     rcx, aPsenderGetwind_0; "pSender->GetWindowState() failed"
0x140034a42  mov     [rsp+68h+var_40], ebx
0x140034a46  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140034a4d  mov     [rsp+68h+var_48], rcx
0x140034a52  mov     r9d, eax
0x140034a55  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a5c  mov     rcx, [rcx+10h]
0x140034a60  call    WPP_SF_DsD
0x140034a65  jmp     loc_140034C0A
0x140034a6a  call    ?LogRDPGraphicsVOBRHintWindowTracker@RDPGraphicsTraceLogging@@YAXXZ; RDPGraphicsTraceLogging::LogRDPGraphicsVOBRHintWindowTracker(void)
0x140034a6f  mov     rax, cs:WPP_GLOBAL_Control
0x140034a76  lea     rdi, WPP_GLOBAL_Control
0x140034a7d  cmp     rax, rdi
0x140034a80  jz      short loc_140034AB5
0x140034a82  test    dword ptr [rax+1Ch], 200h
0x140034a89  jz      short loc_140034AB5
0x140034a8b  cmp     byte ptr [rax+19h], 2
0x140034a8f  jb      short loc_140034AB5
0x140034a91  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140034a9d  lea     r8, WPP_7fbfedf3cb2c3dda177afd18a098990f_Traceguids
0x140034aa4  mov     edx, 23h ; '#'
0x140034aa9  mov     r9d, eax
0x140034aac  mov     rcx, [rcx+10h]
0x140034ab0  call    WPP_SF_d
0x140034ab5  xor     edx, edx
0x140034ab7  jmp     loc_140034BAC
0x140034abc  cmp     [rbx+20h], rbp
0x140034ac0  jnz     loc_140034BA9
0x140034ac6  lea     rax, [rbx+498h]
0x140034acd  mov     rcx, r15
0x140034ad0  mov     edx, 8
0x140034ad5  movups  xmm0, xmmword ptr [rcx]
0x140034ad8  lea     rcx, [rcx+80h]
0x140034adf  movups  xmmword ptr [rax], xmm0
0x140034ae2  lea     rax, [rax+80h]
0x140034ae9  movups  xmm1, xmmword ptr [rcx-70h]
0x140034aed  movups  xmmword ptr [rax-70h], xmm1
0x140034af1  movups  xmm0, xmmword ptr [rcx-60h]
0x140034af5  movups  xmmword ptr [rax-60h], xmm0
0x140034af9  movups  xmm1, xmmword ptr [rcx-50h]
0x140034afd  movups  xmmword ptr [rax-50h], xmm1
0x140034b01  movups  xmm0, xmmword ptr [rcx-40h]
0x140034b05  movups  xmmword ptr [rax-40h], xmm0
0x140034b09  movups  xmm1, xmmword ptr [rcx-30h]
0x140034b0d  movups  xmmword ptr [rax-30h], xmm1
0x140034b11  movups  xmm0, xmmword ptr [rcx-20h]
0x140034b15  movups  xmmword ptr [rax-20h], xmm0
0x140034b19  movups  xmm1, xmmword ptr [rcx-10h]
0x140034b1d  movups  xmmword ptr [rax-10h], xmm1
0x140034b21  sub     rdx, 1
0x140034b25  jnz     short loc_140034AD5
0x140034b27  movups  xmm0, xmmword ptr [rcx]
0x140034b2a  lea     rdx, [rsi+248h]; lprcSrc
0x140034b31  movups  xmmword ptr [rax], xmm0
0x140034b34  movups  xmm1, xmmword ptr [rcx+10h]
0x140034b38  movups  xmmword ptr [rax+10h], xmm1
0x140034b3c  movups  xmm0, xmmword ptr [rcx+20h]
0x140034b40  movups  xmmword ptr [rax+20h], xmm0
0x140034b44  movups  xmm1, xmmword ptr [rcx+30h]
0x140034b48  movups  xmmword ptr [rax+30h], xmm1
0x140034b4c  movups  xmm0, xmmword ptr [rcx+40h]
0x140034b50  movups  xmmword ptr [rax+40h], xmm0
0x140034b54  movups  xmm1, xmmword ptr [rcx+50h]
0x140034b58  movups  xmmword ptr [rax+50h], xmm1
0x140034b5c  movups  xmm0, xmmword ptr [rcx+60h]
0x140034b60  mov     dword ptr [rbx+488h], 1
0x140034b6a  lea     rcx, [rbx+50h]; lprcDst
0x140034b6e  mov     dword ptr [rbx+48Ch], 1
0x140034b78  movups  xmmword ptr [rax+60h], xmm0
0x140034b7c  mov     rax, [rsi+220h]
0x140034b83  mov     [rbx+40h], rax
0x140034b87  mov     rax, [rsi+230h]
0x140034b8e  mov     [rbx+48h], rax
0x140034b92  call    cs:__imp_CopyRect
0x140034b98  lea     rdx, [rsi+238h]; lprcSrc
0x140034b9f  lea     rcx, [rbx+60h]; lprcDst
0x140034ba3  call    cs:__imp_CopyRect
0x140034ba9  mov     rdx, rbx
0x140034bac  lea     rcx, [rsi+38h]
0x140034bb0  call    ?GetNextOfEx@?$CTEntryList@URDP_TRACKED_WINDOW_NODE@@$0A@@@QEAAPEAURDP_TRACKED_WINDOW_NODE@@PEAU2@@Z; CTEntryList<RDP_TRACKED_WINDOW_NODE,0>::GetNextOfEx(RDP_TRACKED_WINDOW_NODE *)
0x140034bb5  mov     rbx, rax
0x140034bb8  test    rax, rax
0x140034bbb  jnz     loc_140034ABC
0x140034bc1  mov     rdx, rbp; HWND
0x140034bc4  lea     rcx, [rsi-30h]; this
0x140034bc8  call    ?AdjustGeometryForWindow@CRdpHintManager@@EEAAJPEAUHWND__@@@Z; CRdpHintManager::AdjustGeometryForWindow(HWND__ *)
0x140034bcd  mov     ebx, eax
0x140034bcf  test    eax, eax
0x140034bd1  jns     short loc_140034C01
0x140034bd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140034bda  cmp     rcx, rdi
0x140034bdd  jz      short loc_140034C0A
0x140034bdf  test    byte ptr [rcx+1Ch], 8
0x140034be3  jz      short loc_140034C0A
0x140034be5  cmp     byte ptr [rcx+19h], 2
0x140034be9  jb      short loc_140034C0A
0x140034beb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140034bf0  mov     edx, 24h ; '$'
0x140034bf5  lea     rcx, aAdjustgeometry; "AdjustGeometryForWindow() failed"
0x140034bfc  jmp     loc_140034A42
0x140034c01  lea     rcx, [rsi-30h]; this
0x140034c05  call    ?UpdateHints@CRdpHintManager@@AEAAXXZ; CRdpHintManager::UpdateHints(void)
0x140034c0a  lea     rcx, [rsp+68h+arg_0]; this
0x140034c0f  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x140034c14  xor     eax, eax
0x140034c16  add     rsp, 38h
0x140034c1a  pop     r15
0x140034c1c  pop     r14
0x140034c1e  pop     rdi
0x140034c1f  pop     rsi
0x140034c20  pop     rbp
0x140034c21  pop     rbx
0x140034c22  retn
```
