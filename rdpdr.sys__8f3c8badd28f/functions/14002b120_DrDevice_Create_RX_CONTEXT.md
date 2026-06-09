# DrDevice::Create(_RX_CONTEXT *)

- ea: `0x14002b120`
- end: `0x14002b523`
- name: `?Create@DrDevice@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(DrDevice *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140005510`

## callees

- `0x140001660`
- `0x1400016a0`
- `0x140001890`
- `0x140001e30`
- `0x140003188`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x1400035a0`
- `0x140006560`
- `0x1400065c0`
- `0x1400068c0`
- `0x14002b120`
- `0x14002b530`
- `0x14002b698`

## import_xrefs

- `rdbss!RxDisableLocalBuffering` at `0x14002b1ec`
- `rdbss!RxDisableLocalBuffering` at `0x14002b1ec`
- `rdbss!RxCreateNetFobx` at `0x14002b206`
- `rdbss!RxCreateNetFobx` at `0x14002b206`

## pseudocode

```c
__int64 __fastcall DrDevice::Create(DrDevice *this, struct _RX_CONTEXT *a2)
{
  __int64 v2; // rbx
  PMRX_FCB pFcb; // r14
  PMRX_SRV_OPEN pRelevantSrvOpen; // rbp
  __int64 v7; // r9
  int Security; // edi
  PVOID Context2; // rcx
  struct _MRX_SRV_OPEN_ *v10; // rdx
  struct _MRX_FOBX_ *NetFobx; // rax
  const void **p_Resource; // rdi
  int v13; // eax
  unsigned int v14; // r13d
  char *v15; // rax
  char *v16; // r14
  int v17; // eax
  __int64 v18; // rax
  PMRX_FOBX pFobx; // rcx
  int v21; // [rsp+20h] [rbp-58h]
  __int64 v22; // [rsp+80h] [rbp+8h] BYREF
  __int64 v23; // [rsp+88h] [rbp+10h] BYREF

  v2 = *((_QWORD *)this + 4);
  pFcb = a2->pFcb;
  pRelevantSrvOpen = a2->pRelevantSrvOpen;
  v23 = v2;
  if ( v2 )
    RefCount::AddRef((RefCount *)v2);
  v22 = 0;
  v7 = *(unsigned int *)(v2 + 596);
  if ( (_DWORD)v7 != 3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids, v7);
    Security = -1073741667;
    goto LABEL_9;
  }
  Security = DrDevice::VerifyCreateSecurity(this, a2, *(_DWORD *)(v2 + 1128));
  if ( (Security & 0xC0000000) != 0xC0000000 )
  {
    if ( Security >= 0 )
    {
      Context2 = pRelevantSrvOpen->Context2;
      LODWORD(pRelevantSrvOpen->Key) |= 0x203u;
      RxDisableLocalBuffering(Context2);
      v10 = a2->pRelevantSrvOpen;
      a2->TrackerHistory[4].AcquireRelease = 0;
      NetFobx = RxCreateNetFobx(a2, v10);
      a2->pFobx = NetFobx;
      if ( !NetFobx )
        goto LABEL_51;
      RefCount::AddRef(this);
      p_Resource = (const void **)&pFcb[2].Header.Resource;
      a2->pFobx->UnicodeQueryTemplate.Buffer = (wchar_t *)this;
      if ( *((_DWORD *)this + 11) == 8 && (BYTE2(a2->TrackerHistory[4].FileName) & 2) != 0 && !*(_WORD *)p_Resource )
      {
        *(_DWORD *)p_Resource = 131074;
        pFcb[2].Header.PagingIoResource = (PERESOURCE)L"\\";
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          25,
          WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
          &pFcb[2].Header.Resource);
      v13 = *(unsigned __int16 *)p_Resource;
      v14 = v13 + 58;
      if ( !(_WORD)v13 )
        v14 = 56;
      v15 = (char *)operator new(v14, 0x100u);
      v16 = v15;
      if ( v15 )
      {
        memset(v15, 0, v14);
        *(_DWORD *)v16 = 1230128242;
        *((_DWORD *)v16 + 1) = *((_DWORD *)this + 10);
        *((_QWORD *)v16 + 2) = 0;
        *((_DWORD *)v16 + 6) = *((_DWORD *)&a2->9 + 28);
        *(_QWORD *)(v16 + 28) = *((_QWORD *)&a2->9 + 15);
        *((_DWORD *)v16 + 9) = a2->Create.PipeType;
        *((_DWORD *)v16 + 10) = a2->Create.PipeReadMode;
        *((_DWORD *)v16 + 11) = a2->Create.PipeCompletionMode;
        *((_DWORD *)v16 + 12) = *((_DWORD *)&a2->9 + 35);
        if ( *((_DWORD *)this + 11) == 8 && !*(_WORD *)p_Resource )
          *((_DWORD *)v16 + 12) = 1;
        v17 = *(unsigned __int16 *)p_Resource;
        if ( (_WORD)v17 )
        {
          *((_DWORD *)v16 + 13) = v17 + 2;
          memmove(v16 + 56, p_Resource[1], *(unsigned __int16 *)p_Resource);
        }
        else
        {
          *((_DWORD *)v16 + 13) = 0;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                27,
                WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                *((unsigned int *)v16 + 6));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  28,
                  WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                  *((unsigned int *)v16 + 8),
                  *((_DWORD *)v16 + 7));
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              {
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    29,
                    WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                    *((unsigned int *)v16 + 9));
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                {
                  if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      30,
                      WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                      *((unsigned int *)v16 + 10));
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                  {
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        31,
                        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                        *((unsigned int *)v16 + 11));
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        32,
                        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
                        *((unsigned int *)v16 + 12));
                    }
                  }
                }
              }
            }
          }
        }
        v18 = *(_QWORD *)this;
        v22 = -300000000;
        LOBYTE(v21) = 1;
        Security = (*(__int64 (__fastcall **)(DrDevice *, struct _RX_CONTEXT *, char *, _QWORD, int, __int64 *, _DWORD))(v18 + 24))(
                     this,
                     a2,
                     v16,
                     v14,
                     v21,
                     &v22,
                     0);
        operator delete(v16);
        if ( Security >= 0 )
        {
          DrDevice::FinishCreate(this, a2);
LABEL_54:
          RefCount::Release((RefCount *)v2);
          return (unsigned int)Security;
        }
      }
      else
      {
LABEL_51:
        Security = -1073741670;
      }
    }
    pFobx = a2->pFobx;
    if ( pFobx )
    {
      RefCount::Release((RefCount *)pFobx->UnicodeQueryTemplate.Buffer);
      a2->pFobx->UnicodeQueryTemplate.Buffer = 0;
    }
    goto LABEL_54;
  }
LABEL_9:
  SmartPtr<DrFile>::~SmartPtr<DrFile>(&v23);
  return (unsigned int)Security;
}

```

## disassembly

```asm
0x14002b120  mov     rax, rsp
0x14002b123  mov     [rax+18h], rbx
0x14002b127  push    rbp
0x14002b128  push    rsi
0x14002b129  push    rdi
0x14002b12a  push    r12
0x14002b12c  push    r13
0x14002b12e  push    r14
0x14002b130  push    r15
0x14002b132  sub     rsp, 40h
0x14002b136  mov     rbx, [rcx+20h]
0x14002b13a  xor     r15d, r15d
0x14002b13d  mov     r14, [rdx+38h]
0x14002b141  mov     rsi, rdx
0x14002b144  mov     rbp, [rdx+48h]
0x14002b148  mov     r12, rcx
0x14002b14b  mov     [rax+10h], rbx
0x14002b14f  test    rbx, rbx
0x14002b152  jz      short loc_14002B15C
0x14002b154  mov     rcx, rbx; this
0x14002b157  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002b15c  mov     [rsp+78h+arg_0], r15
0x14002b164  mov     r9d, [rbx+254h]
0x14002b16b  cmp     r9d, 3
0x14002b16f  jz      short loc_14002B1A9
0x14002b171  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b178  lea     rbp, WPP_GLOBAL_Control
0x14002b17f  cmp     rcx, rbp
0x14002b182  jz      short loc_14002B1A2
0x14002b184  mov     dil, 4
0x14002b187  cmp     [rcx+29h], dil
0x14002b18b  jb      short loc_14002B1A2
0x14002b18d  mov     rcx, [rcx+18h]
0x14002b191  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b198  mov     edx, 18h
0x14002b19d  call    WPP_SF_d
0x14002b1a2  mov     edi, 0C000009Dh
0x14002b1a7  jmp     short loc_14002B1C7
0x14002b1a9  mov     r8d, [rbx+468h]; unsigned int
0x14002b1b0  mov     rcx, r12; this
0x14002b1b3  call    ?VerifyCreateSecurity@DrDevice@@IEAAJPEAU_RX_CONTEXT@@K@Z; DrDevice::VerifyCreateSecurity(_RX_CONTEXT *,ulong)
0x14002b1b8  mov     ecx, eax
0x14002b1ba  mov     edi, eax
0x14002b1bc  mov     eax, 0C0000000h
0x14002b1c1  and     ecx, eax
0x14002b1c3  cmp     ecx, eax
0x14002b1c5  jnz     short loc_14002B1D9
0x14002b1c7  lea     rcx, [rsp+78h+arg_8]
0x14002b1cf  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x14002b1d4  jmp     loc_14002B508
0x14002b1d9  test    edi, edi
0x14002b1db  js      loc_14002B4E6
0x14002b1e1  mov     rcx, [rbp+20h]
0x14002b1e5  or      dword ptr [rbp+48h], 203h
0x14002b1ec  call    cs:__imp_RxDisableLocalBuffering
0x14002b1f3  nop     dword ptr [rax+rax+00h]
0x14002b1f8  mov     rdx, [rsi+48h]; MrxSrvOpen
0x14002b1fc  mov     rcx, rsi; RxContext
0x14002b1ff  mov     [rsi+2E0h], r15d
0x14002b206  call    cs:__imp_RxCreateNetFobx
0x14002b20d  nop     dword ptr [rax+rax+00h]
0x14002b212  mov     [rsi+40h], rax
0x14002b216  test    rax, rax
0x14002b219  jz      loc_14002B4E1
0x14002b21f  mov     rcx, r12; this
0x14002b222  call    ?AddRef@RefCount@@QEAAXXZ; RefCount::AddRef(void)
0x14002b227  mov     rax, [rsi+40h]
0x14002b22b  lea     rdi, [r14+168h]
0x14002b232  mov     ecx, 2
0x14002b237  mov     [rax+38h], r12
0x14002b23b  cmp     dword ptr [r12+2Ch], 8
0x14002b241  jnz     short loc_14002B262
0x14002b243  test    [rsi+2EAh], cl
0x14002b249  jz      short loc_14002B262
0x14002b24b  cmp     [rdi], r15w
0x14002b24f  jnz     short loc_14002B262
0x14002b251  lea     rax, asc_140008CF8; "\\"
0x14002b258  mov     dword ptr [rdi], 20002h
0x14002b25e  mov     [rdi+8], rax
0x14002b262  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b269  lea     rbp, WPP_GLOBAL_Control
0x14002b270  lea     r15, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002b277  cmp     rcx, rbp
0x14002b27a  jz      short loc_14002B296
0x14002b27c  cmp     byte ptr [rcx+29h], 5
0x14002b280  jb      short loc_14002B296
0x14002b282  mov     rcx, [rcx+18h]
0x14002b286  mov     edx, 19h
0x14002b28b  mov     r9, rdi
0x14002b28e  mov     r8, r15
0x14002b291  call    WPP_SF_Z
0x14002b296  movzx   eax, word ptr [rdi]
0x14002b299  lea     r13d, [rax+3Ah]
0x14002b29d  test    ax, ax
0x14002b2a0  jnz     short loc_14002B2A8
0x14002b2a2  mov     r13d, 38h ; '8'
0x14002b2a8  mov     ecx, r13d; unsigned __int64
0x14002b2ab  mov     edx, 100h; unsigned __int64
0x14002b2b0  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14002b2b5  mov     r14, rax
0x14002b2b8  test    rax, rax
0x14002b2bb  jz      loc_14002B4DE
0x14002b2c1  mov     r8d, r13d; Size
0x14002b2c4  xor     edx, edx; Val
0x14002b2c6  mov     rcx, rax; void *
0x14002b2c9  call    memset
0x14002b2ce  mov     dword ptr [r14], 49524472h
0x14002b2d5  mov     ecx, [r12+28h]
0x14002b2da  mov     [r14+4], ecx
0x14002b2de  xor     ecx, ecx
0x14002b2e0  mov     [r14+10h], rcx
0x14002b2e4  mov     eax, [rsi+200h]
0x14002b2ea  mov     [r14+18h], eax
0x14002b2ee  mov     rax, [rsi+208h]
0x14002b2f5  mov     [r14+1Ch], rax
0x14002b2f9  mov     eax, [rsi+210h]
0x14002b2ff  mov     [r14+24h], eax
0x14002b303  mov     eax, [rsi+214h]
0x14002b309  mov     [r14+28h], eax
0x14002b30d  mov     eax, [rsi+218h]
0x14002b313  mov     [r14+2Ch], eax
0x14002b317  mov     eax, [rsi+21Ch]
0x14002b31d  mov     [r14+30h], eax
0x14002b321  cmp     dword ptr [r12+2Ch], 8
0x14002b327  jnz     short loc_14002B336
0x14002b329  cmp     [rdi], cx
0x14002b32c  jnz     short loc_14002B336
0x14002b32e  mov     dword ptr [r14+30h], 1
0x14002b336  movzx   eax, word ptr [rdi]
0x14002b339  test    ax, ax
0x14002b33c  jz      short loc_14002B358
0x14002b33e  add     eax, 2
0x14002b341  lea     rcx, [r14+38h]; void *
0x14002b345  mov     [r14+34h], eax
0x14002b349  movzx   r8d, word ptr [rdi]; Size
0x14002b34d  mov     rdx, [rdi+8]; Src
0x14002b351  call    memmove
0x14002b356  jmp     short loc_14002B35C
0x14002b358  mov     [r14+34h], ecx
0x14002b35c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b363  cmp     rcx, rbp
0x14002b366  jz      loc_14002B484
0x14002b36c  mov     dil, 4
0x14002b36f  cmp     [rcx+29h], dil
0x14002b373  jb      short loc_14002B386
0x14002b375  mov     rcx, [rcx+18h]
0x14002b379  mov     edx, 1Ah
0x14002b37e  mov     r8, r15
0x14002b381  call    WPP_SF_
0x14002b386  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b38d  cmp     rcx, rbp
0x14002b390  jz      loc_14002B484
0x14002b396  cmp     [rcx+29h], dil
0x14002b39a  jb      short loc_14002B3B1
0x14002b39c  mov     r9d, [r14+18h]
0x14002b3a0  mov     edx, 1Bh
0x14002b3a5  mov     rcx, [rcx+18h]
0x14002b3a9  mov     r8, r15
0x14002b3ac  call    WPP_SF_d
0x14002b3b1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b3b8  cmp     rcx, rbp
0x14002b3bb  jz      loc_14002B484
0x14002b3c1  cmp     [rcx+29h], dil
0x14002b3c5  jb      short loc_14002B3E4
0x14002b3c7  mov     eax, [r14+1Ch]
0x14002b3cb  mov     edx, 1Ch
0x14002b3d0  mov     r9d, [r14+20h]
0x14002b3d4  mov     r8, r15
0x14002b3d7  mov     rcx, [rcx+18h]
0x14002b3db  mov     [rsp+78h+var_58], eax
0x14002b3df  call    WPP_SF_dd
0x14002b3e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b3eb  cmp     rcx, rbp
0x14002b3ee  jz      loc_14002B484
0x14002b3f4  cmp     [rcx+29h], dil
0x14002b3f8  jb      short loc_14002B40F
0x14002b3fa  mov     r9d, [r14+24h]
0x14002b3fe  mov     edx, 1Dh
0x14002b403  mov     rcx, [rcx+18h]
0x14002b407  mov     r8, r15
0x14002b40a  call    WPP_SF_d
0x14002b40f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b416  cmp     rcx, rbp
0x14002b419  jz      short loc_14002B484
0x14002b41b  cmp     [rcx+29h], dil
0x14002b41f  jb      short loc_14002B436
0x14002b421  mov     r9d, [r14+28h]
0x14002b425  mov     edx, 1Eh
0x14002b42a  mov     rcx, [rcx+18h]
0x14002b42e  mov     r8, r15
0x14002b431  call    WPP_SF_d
0x14002b436  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b43d  cmp     rcx, rbp
0x14002b440  jz      short loc_14002B484
0x14002b442  cmp     [rcx+29h], dil
0x14002b446  jb      short loc_14002B45D
0x14002b448  mov     r9d, [r14+2Ch]
0x14002b44c  mov     edx, 1Fh
0x14002b451  mov     rcx, [rcx+18h]
0x14002b455  mov     r8, r15
0x14002b458  call    WPP_SF_d
0x14002b45d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b464  cmp     rcx, rbp
0x14002b467  jz      short loc_14002B484
0x14002b469  cmp     [rcx+29h], dil
0x14002b46d  jb      short loc_14002B484
0x14002b46f  mov     r9d, [r14+30h]
0x14002b473  mov     edx, 20h ; ' '
0x14002b478  mov     rcx, [rcx+18h]
0x14002b47c  mov     r8, r15
0x14002b47f  call    WPP_SF_d
0x14002b484  mov     rax, [r12]
0x14002b488  lea     rcx, [rsp+78h+arg_0]
0x14002b490  xor     r15d, r15d
0x14002b493  mov     [rsp+78h+arg_0], 0FFFFFFFFEE1E5D00h
0x14002b49f  mov     [rsp+78h+var_48], r15d
0x14002b4a4  mov     r9d, r13d
0x14002b4a7  mov     [rsp+78h+var_50], rcx
0x14002b4ac  mov     r8, r14
0x14002b4af  mov     rax, [rax+18h]
0x14002b4b3  mov     rdx, rsi
0x14002b4b6  mov     rcx, r12
0x14002b4b9  mov     byte ptr [rsp+78h+var_58], 1
0x14002b4be  call    _guard_dispatch_icall
0x14002b4c3  mov     rcx, r14; void *
0x14002b4c6  mov     edi, eax
0x14002b4c8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002b4cd  test    edi, edi
0x14002b4cf  js      short loc_14002B4E6
0x14002b4d1  mov     rdx, rsi; struct _RX_CONTEXT *
0x14002b4d4  mov     rcx, r12; this
0x14002b4d7  call    ?FinishCreate@DrDevice@@IEAAXPEAU_RX_CONTEXT@@@Z; DrDevice::FinishCreate(_RX_CONTEXT *)
0x14002b4dc  jmp     short loc_14002B500
0x14002b4de  xor     r15d, r15d
0x14002b4e1  mov     edi, 0C000009Ah
0x14002b4e6  mov     rcx, [rsi+40h]
0x14002b4ea  test    rcx, rcx
0x14002b4ed  jz      short loc_14002B500
0x14002b4ef  mov     rcx, [rcx+38h]; this
0x14002b4f3  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002b4f8  mov     rax, [rsi+40h]
0x14002b4fc  mov     [rax+38h], r15
0x14002b500  mov     rcx, rbx; this
0x14002b503  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002b508  mov     rbx, [rsp+78h+arg_10]
0x14002b510  mov     eax, edi
0x14002b512  add     rsp, 40h
0x14002b516  pop     r15
0x14002b518  pop     r14
0x14002b51a  pop     r13
0x14002b51c  pop     r12
0x14002b51e  pop     rdi
0x14002b51f  pop     rsi
0x14002b520  pop     rbp
0x14002b521  retn
```
