# CRedbookTracks::RecordDisc(IDiscRecorder2 *,CMyUpdateList *,ulong)

- ea: `0x1800168f8`
- end: `0x180016b0b`
- name: `?RecordDisc@CRedbookTracks@@QEAAJPEAUIDiscRecorder2@@PEAVCMyUpdateList@@K@Z`
- size: `531`
- prototype: `__int64 __fastcall(CRedbookTracks *this, struct IDiscRecorder2 *, struct CMyUpdateList *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000d830`

## callees

- `0x180007bd4`
- `0x180010aac`
- `0x180015810`
- `0x1800165b4`
- `0x1800168f8`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall CRedbookTracks::RecordDisc(
        CRedbookTracks *this,
        struct IDiscRecorder2 *a2,
        struct CMyUpdateList *a3,
        int a4)
{
  int v8; // eax
  unsigned int v9; // esi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  _DWORD *v12; // rdi
  unsigned int *v13; // rbp
  unsigned int v14; // eax
  int v15; // eax
  __int64 *v16; // rdx
  int v17; // eax
  int v18; // ecx
  _QWORD *i; // r15
  int v20; // ecx
  unsigned int v21; // eax
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  unsigned int v25; // eax

  v8 = CRedbookTracks::OpenDisc(this, a3);
  v9 = v8;
  if ( v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v11 = 16;
LABEL_5:
      WPP_SF_d(v10[7], v11, &WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids, (unsigned int)v8);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD, struct IDiscRecorder2 *))(**((_QWORD **)this + 3) + 136LL))(
         *((_QWORD *)this + 3),
         a2);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v12 = (_DWORD *)((char *)a3 + 100);
    v13 = (unsigned int *)((char *)a3 + 132);
    if ( *((_DWORD *)a3 + 3) )
    {
      v14 = *((_DWORD *)this + 4);
      *v12 |= 0x10u;
      *((_QWORD *)a3 + 10) = v14;
      *v13 = v14;
    }
    CMyUpdateList::UpdateAll(a3);
    v15 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 96LL))(*((_QWORD *)this + 3));
    v9 = v15;
    if ( v15 >= 0 )
    {
      v16 = *(__int64 **)this;
      v17 = 0;
      while ( v16 )
      {
        v18 = *((_DWORD *)v16 + 4);
        v16 = (__int64 *)*v16;
        v17 += v18;
      }
      if ( *((_DWORD *)a3 + 3) )
      {
        *v12 |= 0x100u;
        *((_DWORD *)a3 + 22) = v17;
        *((_DWORD *)a3 + 23) = 0;
        *((_DWORD *)a3 + 27) = v17;
      }
      CMyUpdateList::UpdateAll(a3);
      for ( i = *(_QWORD **)this; ; i = (_QWORD *)*i )
      {
        v22 = (__int64 *)*((_QWORD *)this + 3);
        v23 = *v22;
        if ( !i )
          break;
        (*(void (__fastcall **)(__int64 *, _QWORD))(v23 + 104))(v22, i[1]);
        if ( *((_DWORD *)a3 + 3) )
        {
          v20 = ++*((_DWORD *)a3 + 21);
          v21 = *((_DWORD *)a3 + 20);
          *v12 |= 0x20u;
          *((_DWORD *)a3 + 32) = v20;
          *v13 = v21;
        }
        CMyUpdateList::UpdateAll(a3);
      }
      (*(void (**)(void))(v23 + 120))();
      if ( !*((_DWORD *)a3 + 3) )
        goto LABEL_35;
      v24 = *((_DWORD *)a3 + 22);
      if ( *((_DWORD *)a3 + 23) != v24 )
      {
        *v12 |= 0x400u;
        *((_DWORD *)a3 + 27) = v24;
      }
      *((_DWORD *)a3 + 22) = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          18,
          &WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids,
          (unsigned int)v15);
      if ( !*((_DWORD *)a3 + 3) )
        goto LABEL_35;
    }
    v25 = *((_DWORD *)a3 + 20);
    if ( *((_DWORD *)a3 + 21) != v25 )
    {
      *v12 |= 0x40u;
      *v13 = v25;
    }
    *((_DWORD *)a3 + 20) = 0;
LABEL_35:
    CMyUpdateList::UpdateAll(a3);
    goto LABEL_36;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v11 = 17;
    goto LABEL_5;
  }
LABEL_36:
  if ( *((_DWORD *)a3 + 3) )
  {
    *((_DWORD *)a3 + 25) |= 0x2000u;
    *((_DWORD *)a3 + 28) = a4;
  }
  CMyUpdateList::UpdateAll(a3);
  CRedbookTracks::CloseDisc(this);
  return v9;
}

```

## disassembly

```asm
0x1800168f8  push    rbx
0x1800168fa  push    rbp
0x1800168fb  push    rsi
0x1800168fc  push    rdi
0x1800168fd  push    r12
0x1800168ff  push    r14
0x180016901  push    r15
0x180016903  sub     rsp, 20h
0x180016907  mov     rdi, rdx
0x18001690a  mov     r12d, r9d
0x18001690d  mov     rdx, r8; struct CMyUpdateList *
0x180016910  mov     rbx, r8
0x180016913  mov     r14, rcx
0x180016916  call    ?OpenDisc@CRedbookTracks@@IEAAJPEAVCMyUpdateList@@@Z; CRedbookTracks::OpenDisc(CMyUpdateList *)
0x18001691b  mov     esi, eax
0x18001691d  test    eax, eax
0x18001691f  jns     short loc_18001695F
0x180016921  mov     rcx, cs:WPP_GLOBAL_Control
0x180016928  lea     rdx, WPP_GLOBAL_Control
0x18001692f  cmp     rcx, rdx
0x180016932  jz      loc_180016ADB
0x180016938  test    byte ptr [rcx+44h], 1
0x18001693c  jz      loc_180016ADB
0x180016942  mov     edx, 10h
0x180016947  mov     rcx, [rcx+38h]
0x18001694b  lea     r8, WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids
0x180016952  mov     r9d, eax
0x180016955  call    WPP_SF_d
0x18001695a  jmp     loc_180016ADB
0x18001695f  mov     rcx, [r14+18h]
0x180016963  mov     rdx, rdi
0x180016966  mov     rax, [rcx]
0x180016969  mov     rax, [rax+88h]
0x180016970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016975  mov     esi, eax
0x180016977  test    eax, eax
0x180016979  jns     short loc_1800169A3
0x18001697b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016982  lea     rdx, WPP_GLOBAL_Control
0x180016989  cmp     rcx, rdx
0x18001698c  jz      loc_180016ADB
0x180016992  test    byte ptr [rcx+44h], 1
0x180016996  jz      loc_180016ADB
0x18001699c  mov     edx, 11h
0x1800169a1  jmp     short loc_180016947
0x1800169a3  cmp     dword ptr [rbx+0Ch], 0
0x1800169a7  lea     rdi, [rbx+64h]
0x1800169ab  lea     rbp, [rbx+84h]
0x1800169b2  jz      short loc_1800169C8
0x1800169b4  mov     eax, [r14+10h]
0x1800169b8  or      dword ptr [rdi], 10h
0x1800169bb  mov     [rbx+50h], eax
0x1800169be  mov     dword ptr [rbx+54h], 0
0x1800169c5  mov     [rbp+0], eax
0x1800169c8  mov     rcx, rbx; this
0x1800169cb  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x1800169d0  mov     rcx, [r14+18h]
0x1800169d4  mov     rax, [rcx]
0x1800169d7  mov     rax, [rax+60h]
0x1800169db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169e0  mov     esi, eax
0x1800169e2  test    eax, eax
0x1800169e4  jns     short loc_180016A26
0x1800169e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800169ed  lea     rdx, WPP_GLOBAL_Control
0x1800169f4  cmp     rcx, rdx
0x1800169f7  jz      short loc_180016A17
0x1800169f9  test    byte ptr [rcx+44h], 1
0x1800169fd  jz      short loc_180016A17
0x1800169ff  mov     rcx, [rcx+38h]
0x180016a03  lea     r8, WPP_748693ba6e733a71ff8f81489f91c19c_Traceguids
0x180016a0a  mov     edx, 12h
0x180016a0f  mov     r9d, eax
0x180016a12  call    WPP_SF_d
0x180016a17  cmp     dword ptr [rbx+0Ch], 0
0x180016a1b  jz      loc_180016AD3
0x180016a21  jmp     loc_180016ABE
0x180016a26  mov     rdx, [r14]
0x180016a29  xor     eax, eax
0x180016a2b  jmp     short loc_180016A36
0x180016a2d  mov     ecx, [rdx+10h]
0x180016a30  mov     rdx, [rdx]
0x180016a33  add     rax, rcx
0x180016a36  test    rdx, rdx
0x180016a39  jnz     short loc_180016A2D
0x180016a3b  cmp     [rbx+0Ch], edx
0x180016a3e  jz      short loc_180016A4D
0x180016a40  bts     dword ptr [rdi], 8
0x180016a44  mov     [rbx+58h], eax
0x180016a47  mov     [rbx+5Ch], edx
0x180016a4a  mov     [rbx+6Ch], eax
0x180016a4d  mov     rcx, rbx; this
0x180016a50  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x180016a55  mov     r15, [r14]
0x180016a58  jmp     short loc_180016A8D
0x180016a5a  mov     rdx, [r15+8]
0x180016a5e  mov     rax, [rax+68h]
0x180016a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a67  cmp     dword ptr [rbx+0Ch], 0
0x180016a6b  jz      short loc_180016A82
0x180016a6d  inc     dword ptr [rbx+54h]
0x180016a70  mov     ecx, [rbx+54h]
0x180016a73  mov     eax, [rbx+50h]
0x180016a76  or      dword ptr [rdi], 20h
0x180016a79  mov     [rbx+80h], ecx
0x180016a7f  mov     [rbp+0], eax
0x180016a82  mov     rcx, rbx; this
0x180016a85  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x180016a8a  mov     r15, [r15]
0x180016a8d  mov     rcx, [r14+18h]
0x180016a91  mov     rax, [rcx]
0x180016a94  test    r15, r15
0x180016a97  jnz     short loc_180016A5A
0x180016a99  mov     rax, [rax+78h]
0x180016a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aa2  cmp     [rbx+0Ch], r15d
0x180016aa6  jz      short loc_180016AD3
0x180016aa8  mov     eax, [rbx+58h]
0x180016aab  cmp     [rbx+5Ch], eax
0x180016aae  jz      short loc_180016AB7
0x180016ab0  bts     dword ptr [rdi], 0Ah
0x180016ab4  mov     [rbx+6Ch], eax
0x180016ab7  mov     dword ptr [rbx+58h], 0
0x180016abe  mov     eax, [rbx+50h]
0x180016ac1  cmp     [rbx+54h], eax
0x180016ac4  jz      short loc_180016ACC
0x180016ac6  or      dword ptr [rdi], 40h
0x180016ac9  mov     [rbp+0], eax
0x180016acc  mov     dword ptr [rbx+50h], 0
0x180016ad3  mov     rcx, rbx; this
0x180016ad6  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x180016adb  cmp     dword ptr [rbx+0Ch], 0
0x180016adf  jz      short loc_180016AEA
0x180016ae1  bts     dword ptr [rbx+64h], 0Dh
0x180016ae6  mov     [rbx+70h], r12d
0x180016aea  mov     rcx, rbx; this
0x180016aed  call    ?UpdateAll@CMyUpdateList@@QEAAXXZ; CMyUpdateList::UpdateAll(void)
0x180016af2  mov     rcx, r14; this
0x180016af5  call    ?CloseDisc@CRedbookTracks@@IEAAXXZ; CRedbookTracks::CloseDisc(void)
0x180016afa  mov     eax, esi
0x180016afc  add     rsp, 20h
0x180016b00  pop     r15
0x180016b02  pop     r14
0x180016b04  pop     r12
0x180016b06  pop     rdi
0x180016b07  pop     rsi
0x180016b08  pop     rbp
0x180016b09  pop     rbx
0x180016b0a  retn
```
