# DfsRegistryStore::DeleteStandaloneRoot(ushort const *,ushort const *,uchar,uchar)

- ea: `0x140022598`
- end: `0x140022949`
- name: `?DeleteStandaloneRoot@DfsRegistryStore@@QEAAKPEBG0EE@Z`
- size: `945`
- prototype: `unsigned int __usercall@<eax>(DfsRegistryStore *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int8@<r9b>, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140010b2c`

## callees

- `0x140005b28`
- `0x140005b90`
- `0x140005c10`
- `0x140005f20`
- `0x14000971c`
- `0x14000a354`
- `0x14000abc4`
- `0x14000e228`
- `0x14000ffbc`
- `0x140022598`
- `0x14002e1b8`
- `0x140038abc`
- `0x140057f64`
- `0x1400586a8`
- `0x14005e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400227ce`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1400227ce`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140022788`

## pseudocode

```c
__int64 __fastcall DfsRegistryStore::DeleteStandaloneRoot(
        DfsRegistryStore *this,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        char a4,
        unsigned __int8 a5)
{
  unsigned int inited; // ebx
  unsigned int v10; // eax
  unsigned int *v11; // r10
  DfsRootFolder *v12; // rax
  const WCHAR *v13; // r14
  unsigned __int8 v14; // r8
  unsigned int v15; // eax
  unsigned int v16; // eax
  DfsRootFolder *v18; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-30h]
  struct _UNICODE_STRING v21; // [rsp+58h] [rbp-28h] BYREF
  UNICODE_STRING String2; // [rsp+68h] [rbp-18h] BYREF

  v18 = 0;
  hKey = 0;
  v20 = 0;
  v21 = 0;
  String2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_S(*((_QWORD *)pWppControl + 2), 25, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, a3);
  }
  inited = DfsRtlInitUnicodeStringEx(&v21, a3);
  if ( inited )
    goto LABEL_36;
  inited = DfsRtlInitUnicodeStringEx(&String2, a2 & -(__int64)(a4 != 0));
  if ( inited )
    goto LABEL_36;
  v10 = DfsStore::LookupRoot(this, &String2, &v21, a4, &v18, 0, 0, 0);
  inited = v10;
  v11 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qd(*((_QWORD *)pWppControl + 2), 26, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids, v18, v10);
    v11 = pWppControl;
  }
  if ( !inited )
  {
    if ( *((_DWORD *)v18 + 78) != 256 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && v11
        && (v11[7] & 0x40) != 0
        && *((_BYTE *)v11 + 25) >= 2u )
      {
        WPP_SF_SS(
          *((_QWORD *)v11 + 2),
          27,
          (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
          a2,
          (__int64)a3);
        v11 = pWppControl;
      }
      inited = 87;
      goto LABEL_37;
    }
    if ( !a5
      || (inited = (*(__int64 (__fastcall **)(DfsRootFolder *, __int64))(*(_QWORD *)v18 + 152LL))(v18, 0x10000)) == 0 )
    {
      inited = DfsRootFolder::AcquireRootLock(v18, 1u);
      if ( !inited )
      {
        *((_DWORD *)v18 + 68) |= 0x4000u;
        v12 = v18;
        ++*((_DWORD *)v18 + 30);
        ReleaseSRWLockExclusive((PSRWLOCK)v12 + 14);
        v13 = (const WCHAR *)*((_QWORD *)v18 + 26);
        CRegistry::OpenKey(
          (CRegistry *)&hKey,
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Dfs\\Roots\\Standalone",
          0x20006u);
        inited = v20;
        if ( !v20 )
        {
          inited = RegDeleteTreeW(hKey, v13);
          if ( !inited )
          {
            v15 = DfsStore::RemoveRootFolder(this, v18, v14);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (((1 << (v15 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
              && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              WPP_SF_qSD(
                *((_QWORD *)pWppControl + 2),
                28,
                (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
                (_DWORD)v18,
                (__int64)a3,
                v15);
            }
            v16 = DfsRootFolder::ReleaseRootShareDirectory(v18);
            v11 = pWppControl;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && pWppControl
              && (((1 << (v16 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
              && *((_BYTE *)pWppControl + 25) >= 3u )
            {
              WPP_SF_SD(
                *((_QWORD *)pWppControl + 2),
                29,
                (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
                (_DWORD)a3,
                v16);
              v11 = pWppControl;
            }
            goto LABEL_37;
          }
        }
      }
    }
LABEL_36:
    v11 = pWppControl;
  }
LABEL_37:
  if ( v18 )
  {
    DfsGeneric::ReleaseReference(v18);
    v11 = pWppControl;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && v11
    && (((1 << (inited != 0 ? 11 : 31)) | 0x20) & v11[7]) != 0
    && *((_BYTE *)v11 + 25) >= 3u )
  {
    WPP_SF_SD(
      *((_QWORD *)v11 + 2),
      30,
      (unsigned int)WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids,
      (_DWORD)a3,
      inited);
  }
  CRegistry::~CRegistry((CRegistry *)&hKey);
  return inited;
}

```

## disassembly

```asm
0x140022598  mov     rax, rsp
0x14002259b  mov     [rax+8], rbx
0x14002259f  mov     [rax+10h], rsi
0x1400225a3  mov     [rax+18h], rdi
0x1400225a7  mov     [rax+20h], r12
0x1400225ab  push    rbp
0x1400225ac  push    r14
0x1400225ae  push    r15
0x1400225b0  mov     rbp, rsp
0x1400225b3  sub     rsp, 80h
0x1400225ba  and     [rbp+var_40], 0
0x1400225bf  xorps   xmm0, xmm0
0x1400225c2  and     [rbp+hKey], 0
0x1400225c7  xorps   xmm1, xmm1
0x1400225ca  and     [rbp+var_30], 0
0x1400225ce  mov     r14b, r9b
0x1400225d1  movups  xmmword ptr [rbp+var_28.Length], xmm0
0x1400225d5  mov     rsi, r8
0x1400225d8  mov     r15, rdx
0x1400225db  movups  xmmword ptr [rbp+String2.Length], xmm1
0x1400225df  mov     r12, rcx
0x1400225e2  lea     rax, WPP_GLOBAL_Control
0x1400225e9  mov     edi, 20h ; ' '
0x1400225ee  cmp     cs:WPP_GLOBAL_Control, rax
0x1400225f5  jz      short loc_140022625
0x1400225f7  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400225fe  test    rcx, rcx
0x140022601  jz      short loc_140022625
0x140022603  test    [rcx+1Ch], dil
0x140022607  jz      short loc_140022625
0x140022609  cmp     byte ptr [rcx+19h], 3
0x14002260d  jb      short loc_140022625
0x14002260f  mov     rcx, [rcx+10h]
0x140022613  lea     edx, [rdi-7]
0x140022616  mov     r9, r8
0x140022619  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140022620  call    WPP_SF_S
0x140022625  mov     rdx, rsi
0x140022628  lea     rcx, [rbp+var_28]
0x14002262c  call    DfsRtlInitUnicodeStringEx
0x140022631  mov     ebx, eax
0x140022633  test    eax, eax
0x140022635  jnz     loc_1400228B3
0x14002263b  mov     al, r14b
0x14002263e  lea     rcx, [rbp+String2]
0x140022642  neg     al
0x140022644  sbb     rdx, rdx
0x140022647  and     rdx, r15
0x14002264a  call    DfsRtlInitUnicodeStringEx
0x14002264f  mov     ebx, eax
0x140022651  test    eax, eax
0x140022653  jnz     loc_1400228B3
0x140022659  and     [rsp+80h+var_48], 0
0x14002265f  lea     r8, [rbp+var_28]; struct _UNICODE_STRING *
0x140022663  mov     [rsp+80h+var_50], al; unsigned __int8
0x140022667  lea     rdx, [rbp+String2]; String2
0x14002266b  and     [rsp+80h+var_58], 0
0x140022671  lea     rax, [rbp+var_40]
0x140022675  mov     r9b, r14b; unsigned __int8
0x140022678  mov     [rsp+80h+var_60], rax; struct DfsRootFolder **
0x14002267d  mov     rcx, r12; this
0x140022680  call    ?LookupRoot@DfsStore@@QEAAKPEAU_UNICODE_STRING@@0EPEAPEAVDfsRootFolder@@PEBGEPEAE@Z; DfsStore::LookupRoot(_UNICODE_STRING *,_UNICODE_STRING *,uchar,DfsRootFolder * *,ushort const *,uchar,uchar *)
0x140022685  mov     ebx, eax
0x140022687  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002268e  lea     r14, WPP_GLOBAL_Control
0x140022695  cmp     cs:WPP_GLOBAL_Control, r14
0x14002269c  jz      short loc_1400226D4
0x14002269e  test    r10, r10
0x1400226a1  jz      short loc_1400226D4
0x1400226a3  test    [r10+1Ch], dil
0x1400226a7  jz      short loc_1400226D4
0x1400226a9  cmp     byte ptr [r10+19h], 3
0x1400226ae  jb      short loc_1400226D4
0x1400226b0  mov     r9, [rbp+var_40]
0x1400226b4  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x1400226bb  mov     rcx, [r10+10h]
0x1400226bf  mov     edx, 1Ah
0x1400226c4  mov     dword ptr [rsp+80h+var_60], eax
0x1400226c8  call    WPP_SF_qd
0x1400226cd  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400226d4  test    ebx, ebx
0x1400226d6  jnz     loc_1400228BA
0x1400226dc  mov     rax, [rbp+var_40]
0x1400226e0  cmp     dword ptr [rax+138h], 100h
0x1400226ea  jz      short loc_140022734
0x1400226ec  cmp     cs:WPP_GLOBAL_Control, r14
0x1400226f3  jz      short loc_14002272A
0x1400226f5  test    r10, r10
0x1400226f8  jz      short loc_14002272A
0x1400226fa  test    byte ptr [r10+1Ch], 40h
0x1400226ff  jz      short loc_14002272A
0x140022701  cmp     byte ptr [r10+19h], 2
0x140022706  jb      short loc_14002272A
0x140022708  mov     rcx, [r10+10h]
0x14002270c  lea     edx, [rbx+1Bh]
0x14002270f  mov     r9, r15
0x140022712  mov     [rsp+80h+var_60], rsi
0x140022717  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x14002271e  call    WPP_SF_SS
0x140022723  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002272a  mov     ebx, 57h ; 'W'
0x14002272f  jmp     loc_1400228BA
0x140022734  cmp     [rbp+arg_20], 0
0x140022738  jz      short loc_14002275C
0x14002273a  mov     rcx, [rbp+var_40]
0x14002273e  mov     edx, 10000h
0x140022743  mov     rax, [rcx]
0x140022746  mov     rax, [rax+98h]
0x14002274d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022752  mov     ebx, eax
0x140022754  test    eax, eax
0x140022756  jnz     loc_1400228B3
0x14002275c  mov     rcx, [rbp+var_40]; this
0x140022760  mov     dl, 1; unsigned __int8
0x140022762  call    ?AcquireRootLock@DfsRootFolder@@QEAAKE@Z; DfsRootFolder::AcquireRootLock(uchar)
0x140022767  mov     ebx, eax
0x140022769  test    eax, eax
0x14002276b  jnz     loc_1400228B3
0x140022771  mov     rax, [rbp+var_40]
0x140022775  bts     dword ptr [rax+110h], 0Eh
0x14002277d  mov     rax, [rbp+var_40]
0x140022781  inc     dword ptr [rax+78h]
0x140022784  lea     rcx, [rax+70h]; SRWLock
0x140022788  call    cs:__imp_ReleaseSRWLockExclusive
0x14002278f  nop     dword ptr [rax+rax+00h]
0x140022794  mov     rax, [rbp+var_40]
0x140022798  lea     r8, aSoftwareMicros; "SOFTWARE\\Microsoft\\Dfs\\Roots\\Standa"...
0x14002279f  mov     r9d, 20006h; unsigned int
0x1400227a5  lea     rcx, [rbp+hKey]; this
0x1400227a9  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x1400227b0  mov     r14, [rax+0D0h]
0x1400227b7  call    ?OpenKey@CRegistry@@QEAAHPEAUHKEY__@@PEBGK@Z; CRegistry::OpenKey(HKEY__ *,ushort const *,ulong)
0x1400227bc  mov     ebx, [rbp+var_30]
0x1400227bf  test    ebx, ebx
0x1400227c1  jnz     loc_1400228B3
0x1400227c7  mov     rcx, [rbp+hKey]; hKey
0x1400227cb  mov     rdx, r14; lpSubKey
0x1400227ce  call    cs:__imp_RegDeleteTreeW
0x1400227d5  nop     dword ptr [rax+rax+00h]
0x1400227da  mov     ebx, eax
0x1400227dc  test    eax, eax
0x1400227de  jnz     loc_1400228B3
0x1400227e4  mov     rdx, [rbp+var_40]; struct DfsRootFolder *
0x1400227e8  mov     rcx, r12; this
0x1400227eb  call    ?RemoveRootFolder@DfsStore@@QEAAKPEAVDfsRootFolder@@E@Z; DfsStore::RemoveRootFolder(DfsRootFolder *,uchar)
0x1400227f0  mov     r8d, eax
0x1400227f3  lea     r14, WPP_GLOBAL_Control
0x1400227fa  cmp     cs:WPP_GLOBAL_Control, r14
0x140022801  jz      short loc_14002284E
0x140022803  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002280a  test    r10, r10
0x14002280d  jz      short loc_14002284E
0x14002280f  mov     ecx, eax
0x140022811  mov     eax, edi
0x140022813  neg     ecx
0x140022815  sbb     edx, edx
0x140022817  and     edx, 0FFFFFFECh
0x14002281a  add     edx, 1Fh
0x14002281d  bts     eax, edx
0x140022820  test    [r10+1Ch], eax
0x140022824  jz      short loc_14002284E
0x140022826  cmp     byte ptr [r10+19h], 3
0x14002282b  jb      short loc_14002284E
0x14002282d  mov     r9, [rbp+var_40]
0x140022831  lea     edx, [rbx+1Ch]
0x140022834  mov     rcx, [r10+10h]
0x140022838  mov     dword ptr [rsp+80h+var_58], r8d
0x14002283d  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x140022844  mov     [rsp+80h+var_60], rsi
0x140022849  call    WPP_SF_qSD
0x14002284e  mov     rcx, [rbp+var_40]; this
0x140022852  call    ?ReleaseRootShareDirectory@DfsRootFolder@@QEAAKXZ; DfsRootFolder::ReleaseRootShareDirectory(void)
0x140022857  mov     r8d, eax
0x14002285a  cmp     cs:WPP_GLOBAL_Control, r14
0x140022861  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140022868  jz      short loc_1400228C1
0x14002286a  test    r10, r10
0x14002286d  jz      short loc_1400228C1
0x14002286f  mov     ecx, eax
0x140022871  mov     eax, edi
0x140022873  neg     ecx
0x140022875  sbb     edx, edx
0x140022877  and     edx, 0FFFFFFECh
0x14002287a  add     edx, 1Fh
0x14002287d  bts     eax, edx
0x140022880  test    [r10+1Ch], eax
0x140022884  jz      short loc_1400228C1
0x140022886  cmp     byte ptr [r10+19h], 3
0x14002288b  jb      short loc_1400228C1
0x14002288d  mov     rcx, [r10+10h]
0x140022891  mov     edx, 1Dh
0x140022896  mov     dword ptr [rsp+80h+var_60], r8d
0x14002289b  mov     r9, rsi
0x14002289e  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x1400228a5  call    WPP_SF_SD
0x1400228aa  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400228b1  jmp     short loc_1400228C1
0x1400228b3  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400228ba  lea     r14, WPP_GLOBAL_Control
0x1400228c1  mov     rcx, [rbp+var_40]; this
0x1400228c5  test    rcx, rcx
0x1400228c8  jz      short loc_1400228D6
0x1400228ca  call    ?ReleaseReference@DfsGeneric@@QEAAJXZ; DfsGeneric::ReleaseReference(void)
0x1400228cf  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400228d6  cmp     cs:WPP_GLOBAL_Control, r14
0x1400228dd  jz      short loc_14002291C
0x1400228df  test    r10, r10
0x1400228e2  jz      short loc_14002291C
0x1400228e4  mov     eax, ebx
0x1400228e6  neg     eax
0x1400228e8  sbb     ecx, ecx
0x1400228ea  and     ecx, 0FFFFFFECh
0x1400228ed  add     ecx, 1Fh
0x1400228f0  bts     edi, ecx
0x1400228f3  test    [r10+1Ch], edi
0x1400228f7  jz      short loc_14002291C
0x1400228f9  cmp     byte ptr [r10+19h], 3
0x1400228fe  jb      short loc_14002291C
0x140022900  mov     rcx, [r10+10h]
0x140022904  lea     r8, WPP_0293571a81463cbd1aa3eade2d3ff20c_Traceguids
0x14002290b  mov     edx, 1Eh
0x140022910  mov     dword ptr [rsp+80h+var_60], ebx
0x140022914  mov     r9, rsi
0x140022917  call    WPP_SF_SD
0x14002291c  lea     rcx, [rbp+hKey]; this
0x140022920  call    ??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x140022925  lea     r11, [rsp+80h+var_s0]
0x14002292d  mov     eax, ebx
0x14002292f  mov     rbx, [r11+20h]
0x140022933  mov     rsi, [r11+28h]
0x140022937  mov     rdi, [r11+30h]
0x14002293b  mov     r12, [r11+38h]
0x14002293f  mov     rsp, r11
0x140022942  pop     r15
0x140022944  pop     r14
0x140022946  pop     rbp
0x140022947  retn
```
