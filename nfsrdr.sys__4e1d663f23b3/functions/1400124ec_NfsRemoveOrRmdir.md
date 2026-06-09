# NfsRemoveOrRmdir

- ea: `0x1400124ec`
- end: `0x140012c39`
- name: `NfsRemoveOrRmdir`
- size: `1869`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `23`
- tags: ``

## callers

- `0x14001c694`
- `0x140030ef0`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140008140`
- `0x14000d99c`
- `0x14000d9f0`
- `0x14000fa80`
- `0x14000fb40`
- `0x140010870`
- `0x140011960`
- `0x140011f84`
- `0x1400124ec`
- `0x140013ac0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140018310`
- `0x14001837c`
- `0x1400200d0`
- `0x140020154`
- `0x140022220`
- `0x14002ba4c`
- `0x14002bf9c`
- `0x14002c764`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140012652`
- `ntoskrnl!KeReleaseMutex` at `0x14001288c`
- `ntoskrnl!KeReleaseMutex` at `0x140012a06`
- `ntoskrnl!KeReleaseMutex` at `0x140012a5a`
- `ntoskrnl!KeReleaseMutex` at `0x140012652`
- `ntoskrnl!KeReleaseMutex` at `0x14001288c`
- `ntoskrnl!KeReleaseMutex` at `0x140012a06`
- `ntoskrnl!KeReleaseMutex` at `0x140012a5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012be4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012b13`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012be4`
- `ntoskrnl!ExAllocatePool2` at `0x1400125c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400125c3`
- `rpcxdr!OncRpcDestroy` at `0x140012af2`
- `rpcxdr!OncRpcDestroy` at `0x140012b01`
- `rpcxdr!OncRpcDestroy` at `0x140012b8b`
- `rpcxdr!OncRpcDestroy` at `0x140012bd2`
- `rpcxdr!OncRpcDestroy` at `0x140012af2`
- `rpcxdr!OncRpcDestroy` at `0x140012b01`
- `rpcxdr!OncRpcDestroy` at `0x140012b8b`
- `rpcxdr!OncRpcDestroy` at `0x140012bd2`

## pseudocode

```c
__int64 __fastcall NfsRemoveOrRmdir(__int64 a1, __int64 a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rdi
  __int64 v6; // rsi
  __int64 v8; // rcx
  _DWORD *v9; // r15
  int v10; // r12d
  __int64 v11; // r14
  CHAR *Pool2; // rax
  int v14; // edi
  int v15; // r8d
  int v16; // eax
  PCHAR Buffer; // rdx
  unsigned __int16 v18; // cx
  int v19; // r14d
  CHAR v20; // r10
  __int64 v21; // rsi
  CHAR v22; // r8
  int v23; // edx
  __int64 v24; // r14
  __int64 v25; // r8
  unsigned int v26; // r9d
  __int64 v27; // rcx
  int v28; // edx
  __int64 v29; // rax
  __int64 v30; // r15
  __int64 v31; // r8
  unsigned int v32; // eax
  unsigned int v33; // edi
  __int64 v34; // r8
  __int64 v35; // [rsp+58h] [rbp-21h] BYREF
  PVOID P; // [rsp+60h] [rbp-19h]
  __int64 v37; // [rsp+68h] [rbp-11h]
  __int64 v38; // [rsp+70h] [rbp-9h]
  STRING SourceString; // [rsp+78h] [rbp-1h] BYREF
  int v40; // [rsp+E0h] [rbp+67h]

  v40 = a2;
  v5 = *(_QWORD *)(a2 + 80);
  v37 = v5;
  v6 = a4;
  SourceString = 0;
  v35 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  v8 = *(_QWORD *)(a1 + 32);
  v9 = *(_DWORD **)(*(_QWORD *)(v8 + 32) + 32LL);
  v38 = *(_QWORD *)(v8 + 40);
  v10 = v9[22];
  if ( !v38 )
    return 3221225662LL;
  if ( !v9 )
    return 3221225662LL;
  v11 = *(_QWORD *)(a1 + 40);
  if ( !v11 )
    return 3221225662LL;
  if ( (unsigned __int8)HacIsEntryFake(v6) )
    return 3221225506LL;
  Pool2 = (CHAR *)ExAllocatePool2(258, 1024, 827483726);
  P = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v14 = -1073741670;
    goto LABEL_98;
  }
  *(_DWORD *)&SourceString.Length = 0x1000000;
  SourceString.Buffer = Pool2 + 512;
  HacAcquireLock(a5);
  v14 = NfsConvertUnicodeToAnsi(v5, &SourceString, a5 + 80);
  KeReleaseMutex(*(PRKMUTEX *)(a5 + 40), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0 )
    WPP_SF_s(
      WPP_GLOBAL_Control->AttachedDevice,
      98,
      WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
      SourceString.Buffer);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_97;
  }
  v16 = *(_DWORD *)(v11 + 32);
  if ( (v16 & 0x40) != 0 )
  {
    DsSjisToEuc(&SourceString, &SourceString);
    goto LABEL_43;
  }
  if ( (v16 & 0x4000) != 0 )
  {
    if ( SourceString.Length )
    {
      Buffer = SourceString.Buffer;
      if ( SourceString.Buffer )
      {
        v18 = 0;
        v19 = SourceString.Length - 1;
        if ( v19 > 0 )
        {
          while ( 1 )
          {
            v20 = Buffer[v18];
            if ( (unsigned __int8)(v20 + 127) <= 0x1Fu )
            {
              LOBYTE(v15) = Buffer[v18 + 1];
              if ( (unsigned __int8)(v15 - 65) <= 0x39u )
              {
                v21 = 0x3FFFFFF03FFFFFFLL;
                if ( _bittest64(&v21, (unsigned int)(v15 - 65)) )
                  break;
              }
              if ( (unsigned __int8)(v15 + 127) <= 0x1Fu || (unsigned __int8)(v15 + 95) <= 0x5Du )
                break;
            }
            if ( (unsigned __int8)(v20 + 95) <= 0x5Du )
            {
              v22 = Buffer[v18 + 1];
              if ( (unsigned __int8)(v22 - 65) <= 0x19u
                || (unsigned __int8)(v22 - 97) <= 0x19u
                || (unsigned __int8)(v22 + 127) <= 0x1Fu )
              {
                break;
              }
            }
            if ( (unsigned __int8)(v20 + 127) <= 0x7Du )
              goto LABEL_38;
LABEL_39:
            if ( ++v18 >= v19 )
            {
              v6 = a4;
              goto LABEL_43;
            }
          }
          *(_WORD *)&Buffer[v18] = 16191;
LABEL_38:
          ++v18;
          goto LABEL_39;
        }
      }
    }
  }
  else if ( (v16 & 0x2000) != 0 )
  {
    DsCnsToEuc(SourceString.Buffer, SourceString.Length, SourceString.Buffer, &SourceString);
  }
LABEL_43:
  if ( a3 == 2 )
  {
    v23 = 13;
    if ( v10 != 3 )
      v23 = 15;
  }
  else
  {
    v23 = 10;
    if ( v10 == 3 )
      v23 = 12;
  }
  v24 = NfsRdrBuildCall(
          (int)v9 + 116,
          v9[20],
          v9[21],
          v9[22],
          v23,
          SourceString.Length + 72 + (-SourceString.Length & 3u),
          a1);
  if ( !v24 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v14 = -1073741670;
    goto LABEL_97;
  }
  HacAcquireLock(v6);
  LOBYTE(v25) = v10 == 3;
  XdrEncodeNfsFileHandleUnsafe(v24, v6 + 216, v25);
  KeReleaseMutex(*(PRKMUTEX *)(v6 + 40), 0);
  XdrEncodeIntUnsafe(v24, SourceString.Length, SourceString.Buffer);
  XdrEncodeOpaqueUnsafe(v27, v26);
  if ( *(int *)(v24 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v14 = *(_DWORD *)(v24 + 264);
    goto LABEL_96;
  }
  v29 = (__int64)(v9 + 18);
  v30 = v37;
  v14 = NfsSendWaitReply(v37, v28, a1, v40, *(_QWORD *)(a1 + 40), v29, v24, (__int64)&v35, 2);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    goto LABEL_96;
  }
  v14 = OncRpcMapRpcStatusToNtStatus(v35);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_91;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_63:
    v31 = v35;
LABEL_91:
    OncRpcDestroy(v31);
LABEL_96:
    OncRpcDestroy(v24);
LABEL_97:
    ExFreePoolWithTag(P, 0);
LABEL_98:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    return (unsigned int)v14;
  }
  v32 = XdrDecodeInt(v31);
  v31 = v35;
  v33 = v32;
  if ( *(int *)(v35 + 264) < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
      v31 = v35;
    }
    v14 = *(_DWORD *)(v31 + 264);
    goto LABEL_91;
  }
  if ( v10 == 3 )
  {
    if ( (unsigned __int8)XdrDecodeBool(v35) )
      XdrDecodeSkipBytes(v35, 24);
    if ( (unsigned __int8)XdrDecodeBool(v35) )
    {
      HacAcquireLock(v6);
      LOBYTE(v34) = v10 == 3;
      XdrDecodeNfsFileAttributes(v35, v6 + 128, v34);
      KeReleaseMutex(*(PRKMUTEX *)(v6 + 40), 0);
    }
    else
    {
      HacInvalidateAttributes(v6);
    }
    if ( *(_DWORD *)(v38 + 152) || *(_DWORD *)(v38 + 156) > 0x64u )
      HacPurgePostfix(v30, v6);
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    HacInvalidateAttributes(v6);
    HacPurgePostfix(v30, v6);
  }
  HacAcquireLock(v6);
  DeleteDirCache(v30, v6);
  KeReleaseMutex(*(PRKMUTEX *)(v6 + 40), 0);
  if ( v33 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
    v14 = MapNFSStatusToNtStatus(v33);
    goto LABEL_63;
  }
  OncRpcDestroy(v35);
  OncRpcDestroy(v24);
  ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x1400124ec  mov     rax, rsp
0x1400124ef  mov     [rax+20h], r9
0x1400124f3  mov     [rax+18h], r8d
0x1400124f7  mov     [rax+10h], rdx
0x1400124fb  push    rbp
0x1400124fc  push    rbx
0x1400124fd  push    rsi
0x1400124fe  push    rdi
0x1400124ff  push    r12
0x140012501  push    r13
0x140012503  push    r14
0x140012505  push    r15
0x140012507  lea     rbp, [rax-57h]
0x14001250b  sub     rsp, 88h
0x140012512  mov     rdi, [rdx+50h]
0x140012516  xorps   xmm0, xmm0
0x140012519  mov     [rbp+4Fh+var_60], rdi
0x14001251d  mov     rsi, r9
0x140012520  movups  xmmword ptr [rbp+4Fh+SourceString.Length], xmm0
0x140012524  mov     r13, rcx
0x140012527  mov     [rbp+4Fh+var_70], 0
0x14001252f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012536  lea     rax, WPP_GLOBAL_Control
0x14001253d  cmp     rcx, rax
0x140012540  jz      short loc_14001255E
0x140012542  mov     eax, [rcx+2Ch]
0x140012545  test    al, 40h
0x140012547  jz      short loc_14001255E
0x140012549  mov     rcx, [rcx+18h]
0x14001254d  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012554  mov     edx, 60h ; '`'
0x140012559  call    WPP_SF_
0x14001255e  mov     rcx, [r13+20h]
0x140012562  mov     rax, [rcx+20h]
0x140012566  mov     r15, [rax+20h]
0x14001256a  mov     rax, [rcx+28h]
0x14001256e  mov     [rbp+4Fh+var_58], rax
0x140012572  mov     r12d, [r15+58h]
0x140012576  cmp     r12d, 3
0x14001257a  setz    [rbp+4Fh+arg_0]
0x14001257e  test    rax, rax
0x140012581  jz      loc_140012C1F
0x140012587  test    r15, r15
0x14001258a  jz      loc_140012C1F
0x140012590  mov     r14, [r13+28h]
0x140012594  test    r14, r14
0x140012597  jz      loc_140012C1F
0x14001259d  mov     rcx, rsi
0x1400125a0  call    HacIsEntryFake
0x1400125a5  test    al, al
0x1400125a7  jz      short loc_1400125B3
0x1400125a9  mov     eax, 0C0000022h
0x1400125ae  jmp     loc_140012C24
0x1400125b3  mov     edx, 400h
0x1400125b8  mov     ecx, 102h
0x1400125bd  mov     r8d, 3152664Eh
0x1400125c3  call    cs:__imp_ExAllocatePool2
0x1400125ca  nop     dword ptr [rax+rax+00h]
0x1400125cf  mov     [rbp+4Fh+P], rax
0x1400125d3  test    rax, rax
0x1400125d6  jnz     short loc_140012615
0x1400125d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125df  lea     r12, WPP_GLOBAL_Control
0x1400125e6  mov     bx, 1
0x1400125ea  cmp     rcx, r12
0x1400125ed  jz      short loc_14001260B
0x1400125ef  mov     eax, [rcx+2Ch]
0x1400125f2  test    bl, al
0x1400125f4  jz      short loc_14001260B
0x1400125f6  mov     rcx, [rcx+18h]
0x1400125fa  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012601  mov     edx, 61h ; 'a'
0x140012606  call    WPP_SF_
0x14001260b  mov     edi, 0C000009Ah
0x140012610  jmp     loc_140012BF0
0x140012615  mov     rbx, [rbp+4Fh+arg_20]
0x140012619  add     rax, 200h
0x14001261f  mov     rcx, rbx
0x140012622  mov     dword ptr [rbp+4Fh+SourceString.Length], 1000000h
0x140012629  mov     [rbp+4Fh+SourceString.Buffer], rax
0x14001262d  call    HacAcquireLock
0x140012632  mov     eax, [r14+20h]
0x140012636  lea     r8, [rbx+50h]
0x14001263a  lea     rdx, [rbp+4Fh+SourceString]
0x14001263e  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140012642  mov     rcx, rdi
0x140012645  call    NfsConvertUnicodeToAnsi
0x14001264a  mov     rcx, [rbx+28h]; Mutex
0x14001264e  xor     edx, edx; Wait
0x140012650  mov     edi, eax
0x140012652  call    cs:__imp_KeReleaseMutex
0x140012659  nop     dword ptr [rax+rax+00h]
0x14001265e  mov     rcx, cs:WPP_GLOBAL_Control
0x140012665  lea     rax, WPP_GLOBAL_Control
0x14001266c  cmp     rcx, rax
0x14001266f  jz      short loc_140012691
0x140012671  mov     edx, [rcx+2Ch]
0x140012674  test    dl, dl
0x140012676  jns     short loc_140012691
0x140012678  mov     r9, [rbp+4Fh+SourceString.Buffer]
0x14001267c  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012683  mov     rcx, [rcx+18h]
0x140012687  mov     edx, 62h ; 'b'
0x14001268c  call    WPP_SF_s
0x140012691  mov     bx, 1
0x140012695  test    edi, edi
0x140012697  jns     short loc_1400126D8
0x140012699  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126a0  lea     r12, WPP_GLOBAL_Control
0x1400126a7  cmp     rcx, r12
0x1400126aa  jz      loc_140012BDE
0x1400126b0  mov     eax, [rcx+2Ch]
0x1400126b3  test    bl, al
0x1400126b5  jz      loc_140012BDE
0x1400126bb  mov     rcx, [rcx+18h]
0x1400126bf  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x1400126c6  mov     edx, 63h ; 'c'
0x1400126cb  mov     r9d, edi
0x1400126ce  call    WPP_SF_d
0x1400126d3  jmp     loc_140012BDE
0x1400126d8  mov     eax, [r14+20h]
0x1400126dc  test    al, 40h
0x1400126de  jz      short loc_1400126F2
0x1400126e0  lea     rdx, [rbp+4Fh+SourceString]; DestinationString
0x1400126e4  lea     rcx, [rbp+4Fh+SourceString]; SourceString
0x1400126e8  call    DsSjisToEuc
0x1400126ed  jmp     loc_1400127D3
0x1400126f2  bt      eax, 0Eh
0x1400126f6  jnb     loc_1400127B9
0x1400126fc  xor     eax, eax
0x1400126fe  cmp     ax, [rbp+4Fh+SourceString.Length]
0x140012702  jz      loc_1400127D3
0x140012708  mov     rdx, [rbp+4Fh+SourceString.Buffer]
0x14001270c  test    rdx, rdx
0x14001270f  jz      loc_1400127D3
0x140012715  movzx   r14d, [rbp+4Fh+SourceString.Length]
0x14001271a  xor     ecx, ecx
0x14001271c  dec     r14d
0x14001271f  test    r14d, r14d
0x140012722  jle     loc_1400127D3
0x140012728  movzx   r11d, cx
0x14001272c  mov     r10b, [r11+rdx]
0x140012730  lea     edi, [r10+7Fh]
0x140012734  cmp     dil, 1Fh
0x140012738  ja      short loc_140012772
0x14001273a  mov     r8b, [r11+rdx+1]
0x14001273f  lea     eax, [r8-41h]
0x140012743  cmp     al, 39h ; '9'
0x140012745  ja      short loc_140012757
0x140012747  mov     rsi, 3FFFFFF03FFFFFFh
0x140012751  bt      rsi, rax
0x140012755  jb      short loc_140012769
0x140012757  lea     eax, [r8+7Fh]
0x14001275b  cmp     al, 1Fh
0x14001275d  jbe     short loc_140012769
0x14001275f  add     r8b, 5Fh ; '_'
0x140012763  cmp     r8b, 5Dh ; ']'
0x140012767  ja      short loc_140012772
0x140012769  mov     word ptr [r11+rdx], 3F3Fh
0x140012770  jmp     short loc_1400127A1
0x140012772  add     r10b, 5Fh ; '_'
0x140012776  cmp     r10b, 5Dh ; ']'
0x14001277a  ja      short loc_14001279B
0x14001277c  mov     r8b, [r11+rdx+1]
0x140012781  lea     eax, [r8-41h]
0x140012785  cmp     al, 19h
0x140012787  jbe     short loc_140012769
0x140012789  lea     eax, [r8-61h]
0x14001278d  cmp     al, 19h
0x14001278f  jbe     short loc_140012769
0x140012791  add     r8b, 7Fh
0x140012795  cmp     r8b, 1Fh
0x140012799  jbe     short loc_140012769
0x14001279b  cmp     dil, 7Dh ; '}'
0x14001279f  ja      short loc_1400127A4
0x1400127a1  add     cx, bx
0x1400127a4  add     cx, bx
0x1400127a7  movzx   eax, cx
0x1400127aa  cmp     eax, r14d
0x1400127ad  jl      loc_140012728
0x1400127b3  mov     rsi, [rbp+4Fh+arg_18]
0x1400127b7  jmp     short loc_1400127D3
0x1400127b9  bt      eax, 0Dh
0x1400127bd  jnb     short loc_1400127D3
0x1400127bf  mov     r8, [rbp+4Fh+SourceString.Buffer]
0x1400127c3  lea     r9, [rbp+4Fh+SourceString]
0x1400127c7  movzx   edx, [rbp+4Fh+SourceString.Length]
0x1400127cb  mov     rcx, r8
0x1400127ce  call    DsCnsToEuc
0x1400127d3  cmp     [rbp+4Fh+arg_10], 2
0x1400127d7  jnz     short loc_1400127EA
0x1400127d9  mov     edx, 0Dh
0x1400127de  cmp     r12d, 3
0x1400127e2  lea     eax, [rdx+2]
0x1400127e5  cmovnz  edx, eax
0x1400127e8  jmp     short loc_1400127F9
0x1400127ea  mov     edx, 0Ah
0x1400127ef  cmp     r12d, 3
0x1400127f3  lea     eax, [rdx+2]
0x1400127f6  cmovz   edx, eax
0x1400127f9  movzx   ecx, [rbp+4Fh+SourceString.Length]
0x1400127fd  mov     r9d, [r15+58h]
0x140012801  mov     eax, ecx
0x140012803  mov     r8d, [r15+54h]
0x140012807  neg     eax
0x140012809  add     ecx, 48h ; 'H'
0x14001280c  mov     [rsp+0C0h+var_90], r13
0x140012811  and     eax, 3
0x140012814  add     eax, ecx
0x140012816  lea     rcx, [r15+74h]
0x14001281a  mov     dword ptr [rsp+0C0h+var_98], eax
0x14001281e  mov     dword ptr [rsp+0C0h+var_A0], edx
0x140012822  mov     edx, [r15+50h]
0x140012826  call    NfsRdrBuildCall
0x14001282b  mov     r14, rax
0x14001282e  test    rax, rax
0x140012831  jnz     short loc_14001286B
0x140012833  mov     rcx, cs:WPP_GLOBAL_Control
0x14001283a  lea     r12, WPP_GLOBAL_Control
0x140012841  cmp     rcx, r12
0x140012844  jz      short loc_140012861
0x140012846  mov     eax, [rcx+2Ch]
0x140012849  test    bl, al
0x14001284b  jz      short loc_140012861
0x14001284d  mov     rcx, [rcx+18h]
0x140012851  lea     edx, [r14+64h]
0x140012855  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14001285c  call    WPP_SF_
0x140012861  mov     edi, 0C000009Ah
0x140012866  jmp     loc_140012BDE
0x14001286b  mov     rcx, rsi
0x14001286e  call    HacAcquireLock
0x140012873  mov     r8b, [rbp+4Fh+arg_0]
0x140012877  lea     rdx, [rsi+0D8h]
0x14001287e  mov     rcx, r14
0x140012881  call    XdrEncodeNfsFileHandleUnsafe
0x140012886  mov     rcx, [rsi+28h]; Mutex
0x14001288a  xor     edx, edx; Wait
0x14001288c  call    cs:__imp_KeReleaseMutex
0x140012893  nop     dword ptr [rax+rax+00h]
0x140012898  movzx   r9d, [rbp+4Fh+SourceString.Length]
0x14001289d  mov     rcx, r14
0x1400128a0  mov     r8, [rbp+4Fh+SourceString.Buffer]
0x1400128a4  mov     edx, r9d
0x1400128a7  call    XdrEncodeIntUnsafe
0x1400128ac  mov     edx, r9d
0x1400128af  call    XdrEncodeOpaqueUnsafe
0x1400128b4  cmp     dword ptr [r14+108h], 0
0x1400128bc  jl      loc_140012B99
0x1400128c2  mov     r9, [rbp+4Fh+arg_8]
0x1400128c6  lea     rax, [r15+48h]
0x1400128ca  mov     r15, [rbp+4Fh+var_60]
0x1400128ce  lea     rcx, [rbp+4Fh+var_70]
0x1400128d2  mov     dword ptr [rsp+40h], 2
0x1400128da  mov     r8, r13
0x1400128dd  mov     qword ptr [rsp+0C0h+var_88], rcx
0x1400128e2  mov     rcx, r15
0x1400128e5  mov     [rsp+0C0h+var_90], r14
0x1400128ea  mov     [rsp+0C0h+var_98], rax
0x1400128ef  mov     rax, [r13+28h]
0x1400128f3  mov     [rsp+0C0h+var_A0], rax
0x1400128f8  call    NfsSendWaitReply
0x1400128fd  mov     edi, eax
0x1400128ff  test    eax, eax
0x140012901  jns     short loc_140012942
0x140012903  mov     rcx, cs:WPP_GLOBAL_Control
0x14001290a  lea     r12, WPP_GLOBAL_Control
0x140012911  cmp     rcx, r12
0x140012914  jz      loc_140012BCF
0x14001291a  mov     eax, [rcx+2Ch]
0x14001291d  test    bl, al
0x14001291f  jz      loc_140012BCF
0x140012925  mov     rcx, [rcx+18h]
0x140012929  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012930  mov     edx, 66h ; 'f'
0x140012935  mov     r9d, edi
0x140012938  call    WPP_SF_d
0x14001293d  jmp     loc_140012BCF
0x140012942  mov     r8, [rbp+4Fh+var_70]
0x140012946  mov     rcx, r8
0x140012949  call    OncRpcMapRpcStatusToNtStatus
0x14001294e  mov     edi, eax
0x140012950  test    eax, eax
0x140012952  jns     short loc_140012997
0x140012954  mov     rcx, cs:WPP_GLOBAL_Control
0x14001295b  lea     r12, WPP_GLOBAL_Control
0x140012962  cmp     rcx, r12
0x140012965  jz      loc_140012B88
0x14001296b  mov     eax, [rcx+2Ch]
0x14001296e  test    bl, al
0x140012970  jz      loc_140012B88
0x140012976  mov     rcx, [rcx+18h]
0x14001297a  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x140012981  mov     edx, 67h ; 'g'
0x140012986  mov     r9d, edi
0x140012989  call    WPP_SF_d
0x14001298e  mov     r8, [rbp+4Fh+var_70]
0x140012992  jmp     loc_140012B88
0x140012997  mov     rcx, r8
0x14001299a  call    XdrDecodeInt
  ... truncated ...
```
