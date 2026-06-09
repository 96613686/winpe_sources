# MdaCloseSrvOpen

- ea: `0x140030ef0`
- end: `0x1400316b6`
- name: `MdaCloseSrvOpen`
- size: `1990`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140003510`
- `0x140005c90`
- `0x140008140`
- `0x140009380`
- `0x14000df64`
- `0x14000e940`
- `0x1400124ec`
- `0x1400145f0`
- `0x140014650`
- `0x1400159cc`
- `0x1400159fc`
- `0x14002030c`
- `0x1400204c0`
- `0x140020af4`
- `0x14002fe10`
- `0x140030934`
- `0x140030ef0`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400311f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400311f4`
- `ntoskrnl!KeReleaseMutex` at `0x14003109a`
- `ntoskrnl!KeReleaseMutex` at `0x14003117e`
- `ntoskrnl!KeReleaseMutex` at `0x14003119e`
- `ntoskrnl!KeReleaseMutex` at `0x14003126f`
- `ntoskrnl!KeReleaseMutex` at `0x140031280`
- `ntoskrnl!KeReleaseMutex` at `0x14003142f`
- `ntoskrnl!KeReleaseMutex` at `0x14003156b`
- `ntoskrnl!KeReleaseMutex` at `0x140031583`
- `ntoskrnl!KeReleaseMutex` at `0x14003109a`
- `ntoskrnl!KeReleaseMutex` at `0x14003117e`
- `ntoskrnl!KeReleaseMutex` at `0x14003119e`
- `ntoskrnl!KeReleaseMutex` at `0x14003126f`
- `ntoskrnl!KeReleaseMutex` at `0x140031280`
- `ntoskrnl!KeReleaseMutex` at `0x14003142f`
- `ntoskrnl!KeReleaseMutex` at `0x14003156b`
- `ntoskrnl!KeReleaseMutex` at `0x140031583`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400315d1`
- `ntoskrnl!ExAllocatePool2` at `0x14003136f`
- `ntoskrnl!ExAllocatePool2` at `0x14003136f`

## pseudocode

```c
__int64 __fastcall MdaCloseSrvOpen(_QWORD *a1)
{
  __int64 v1; // r15
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 *v6; // rdi
  int TempNameForDelRenaming; // esi
  __int64 v8; // r15
  int v9; // eax
  __int64 v10; // rcx
  int v11; // r12d
  __int64 v12; // rcx
  __int16 v13; // ax
  struct _KMUTANT *v14; // rcx
  char v15; // al
  __int64 v16; // rcx
  int v17; // ebx
  struct _KMUTANT *v18; // rcx
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 v22; // r9
  void *Pool2; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  PVOID P[2]; // [rsp+50h] [rbp-19h] BYREF
  __int128 v27; // [rsp+60h] [rbp-9h] BYREF
  _OWORD v28[5]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v29; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v30; // [rsp+D8h] [rbp+6Fh]
  __int64 v31; // [rsp+E0h] [rbp+77h]
  __int64 v32; // [rsp+E8h] [rbp+7Fh]

  v1 = a1[8];
  v3 = a1[7];
  v4 = a1[10];
  v30 = v1;
  v5 = *(_QWORD *)(v1 + 32);
  v6 = *(__int64 **)(v3 + 136);
  v31 = v4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 133, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        134,
        WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
        *(unsigned int *)(v5 + 92));
  }
  if ( *(_WORD *)v3 != 0xEC24 )
  {
    if ( (*(_DWORD *)(v3 + 156) & 0x80u) != 0 || *(int *)(v5 + 92) > 1 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 146, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids, 0);
      }
      return 0;
    }
    TempNameForDelRenaming = 0;
    v8 = *(_QWORD *)(*(_QWORD *)(v1 + 32) + 40LL);
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 32) + 32LL) + 32LL) + 88LL) == 3
      && (*(_DWORD *)(*(_QWORD *)(v8 + 40) + 32LL) & 8) != 0 )
    {
      v9 = NfsCommit(
             v8,
             (__int64)a1,
             *(_QWORD *)(*(_QWORD *)(v3 + 136) + 8LL),
             (const void *)(*(_QWORD *)(v3 + 136) + 16LL),
             0,
             0);
      TempNameForDelRenaming = v9;
      if ( v9 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          137,
          WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
          (unsigned int)v9);
      }
    }
    HacAcquireLock(v6[1]);
    v10 = v6[1];
    v11 = *(_DWORD *)(v10 + 56);
    *(_DWORD *)(v10 + 56) = v11 - 1;
    if ( (*(_DWORD *)(v3 + 156) & 1) != 0 )
      *(_WORD *)(v6[1] + 48) |= 0x10u;
    v12 = v6[1];
    v13 = *(_WORD *)(v12 + 48);
    v14 = *(struct _KMUTANT **)(v12 + 40);
    LOWORD(v29) = v13;
    KeReleaseMutex(v14, 0);
    if ( (*(_DWORD *)(v5 + 72) & 0x30) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 138, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      if ( (*(_DWORD *)(v3 + 156) & 1) == 0 )
        goto LABEL_38;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 139, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        goto LABEL_38;
      }
    }
    else
    {
      v15 = v29;
      LODWORD(v29) = (unsigned __int16)v29;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            140,
            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
            *(unsigned int *)(v5 + 92));
        v15 = v29;
      }
      if ( v11 != 1 || (v15 & 0x10) == 0 )
      {
        if ( (v15 & 0x20) == 0 && (*(_BYTE *)(v3 + 156) & 1) != 0 )
        {
          v22 = *v6;
          Pool2 = 0;
          v29 = 0;
          *(_OWORD *)P = 0;
          v28[0] = 0;
          v27 = 0;
          TempNameForDelRenaming = GetTempNameForDelRenaming(v8, a1, P, v22);
          if ( TempNameForDelRenaming >= 0 )
          {
            if ( !WORD1(P[0]) || (Pool2 = (void *)ExAllocatePool2(258, WORD1(P[0]), 827483726)) != 0 )
            {
              HacAcquireLock(v6[1]);
              v24 = v6[1];
              v32 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 32) + 40LL) + 32LL) + 40LL);
              MdaNotifyFullReportChange(
                *(PFAST_MUTEX *)(v32 + 104),
                (_QWORD **)(v32 + 88),
                v24 + 64,
                *(_WORD *)(v24 + 64) - *(_WORD *)(v24 + 80),
                0,
                0,
                (*(_DWORD *)(v24 + 128) == 2) + 1,
                2);
              KeReleaseMutex(*(PRKMUTEX *)(v6[1] + 40), 0);
              MdaDissectNameTail(P, v28, &v27);
              TempNameForDelRenaming = NfsRename(v8, (__int64)a1, *v6, *v6, v6[1] + 80, (__int64)&v27);
              if ( TempNameForDelRenaming >= 0 )
              {
                RemoveNegativeCacheEntry(v31, v32, P);
                *(_WORD *)(v6[1] + 48) |= 0x20u;
                TempNameForDelRenaming = CaseInsensitiveLookup(v8, (__int64)a1, (const UNICODE_STRING *)P, *v6, 1, &v29);
                if ( TempNameForDelRenaming >= 0 )
                {
                  HacAcquireLock(v29);
                  v25 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 32) + 40LL) + 32LL) + 40LL);
                  MdaNotifyFullReportChange(
                    *(PFAST_MUTEX *)(v25 + 104),
                    (_QWORD **)(v25 + 88),
                    v29 + 64,
                    *(_WORD *)(v29 + 64) - *(_WORD *)(v29 + 80),
                    0,
                    0,
                    (*(_DWORD *)(v29 + 128) == 2) + 1,
                    1);
                  HacAcquireLock(v6[1]);
                  HacOrphanEntry(v29);
                  HacRenameEntry(v31, v6[1], v29, Pool2);
                  KeReleaseMutex(*(PRKMUTEX *)(v6[1] + 40), 0);
                  Pool2 = 0;
                  KeReleaseMutex(*(PRKMUTEX *)(v29 + 40), 0);
                  HacDereference(v31, v29);
                  HacUpdateTimeStamp(v6[1]);
                  *(_DWORD *)(v5 + 72) |= 0x10u;
                }
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 144, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
              }
              TempNameForDelRenaming = -1073741670;
            }
            ExFreePoolWithTag(P[1], 0);
            if ( Pool2 )
              ExFreePoolWithTag(Pool2, 0);
          }
        }
        goto LABEL_38;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
      HacAcquireLock(v6[1]);
      v16 = v6[1];
      if ( !*(_WORD *)(v16 + 64) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
        KeReleaseMutex(*(PRKMUTEX *)(v6[1] + 40), 0);
        goto LABEL_38;
      }
      v17 = *(_DWORD *)(v16 + 128);
      v18 = *(struct _KMUTANT **)(v16 + 40);
      LODWORD(v29) = v17;
      KeReleaseMutex(v18, 0);
      TempNameForDelRenaming = NfsRemoveOrRmdir(v8, (__int64)a1, v17, *v6, v6[1]);
      if ( TempNameForDelRenaming >= 0 )
      {
        v19 = v31;
        *(_DWORD *)(v5 + 72) |= 0x20u;
        KeWaitForSingleObject((PVOID)(v19 + 2096), Executive, 0, 0, 0);
        HacAcquireLock(v6[1]);
        v20 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v30 + 32) + 40LL) + 32LL) + 40LL);
        MdaNotifyFullReportChange(
          *(PFAST_MUTEX *)(v20 + 104),
          (_QWORD **)(v20 + 88),
          v6[1] + 64,
          *(_WORD *)(v6[1] + 64) - *(_WORD *)(v6[1] + 80),
          0,
          0,
          ((_DWORD)v29 == 2) + 1,
          2);
        KeReleaseMutex(*(PRKMUTEX *)(v6[1] + 40), 0);
        KeReleaseMutex((PRKMUTEX)(v19 + 2096), 0);
        HacOrphanStaleEntry(v19, v6[1]);
LABEL_38:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            145,
            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
            (unsigned int)TempNameForDelRenaming);
        return (unsigned int)TempNameForDelRenaming;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            143,
            WPP_4a26443b46aa335a1d99573c845c5512_Traceguids,
            (unsigned int)TempNameForDelRenaming);
        goto LABEL_38;
      }
    }
    return (unsigned int)TempNameForDelRenaming;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140030ef0  push    rbp
0x140030ef2  push    rbx
0x140030ef3  push    rsi
0x140030ef4  push    rdi
0x140030ef5  push    r12
0x140030ef7  push    r13
0x140030ef9  push    r14
0x140030efb  push    r15
0x140030efd  lea     rbp, [rsp-1Fh]
0x140030f02  sub     rsp, 88h
0x140030f09  mov     r15, [rcx+40h]
0x140030f0d  mov     r14, rcx
0x140030f10  mov     rbx, [rcx+38h]
0x140030f14  mov     rax, [rcx+50h]
0x140030f18  mov     [rbp+57h+arg_8], r15
0x140030f1c  mov     r13, [r15+20h]
0x140030f20  mov     rdi, [rbx+88h]
0x140030f27  mov     [rbp+57h+arg_10], rax
0x140030f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f32  lea     r12, WPP_GLOBAL_Control
0x140030f39  lea     rsi, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140030f40  cmp     rcx, r12
0x140030f43  jz      short loc_140030F85
0x140030f45  mov     eax, [rcx+2Ch]
0x140030f48  test    al, 8
0x140030f4a  jz      short loc_140030F5D
0x140030f4c  mov     rcx, [rcx+18h]
0x140030f50  mov     edx, 85h
0x140030f55  mov     r8, rsi
0x140030f58  call    WPP_SF_
0x140030f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f64  cmp     rcx, r12
0x140030f67  jz      short loc_140030F85
0x140030f69  mov     eax, [rcx+2Ch]
0x140030f6c  test    al, 4
0x140030f6e  jz      short loc_140030F85
0x140030f70  mov     r9d, [r13+5Ch]
0x140030f74  mov     edx, 86h
0x140030f79  mov     rcx, [rcx+18h]
0x140030f7d  mov     r8, rsi
0x140030f80  call    WPP_SF_d
0x140030f85  mov     eax, 0EC24h
0x140030f8a  cmp     [rbx], ax
0x140030f8d  jnz     short loc_140030FC0
0x140030f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030f96  cmp     rcx, r12
0x140030f99  jz      loc_14003169F
0x140030f9f  mov     eax, [rcx+2Ch]
0x140030fa2  test    al, 8
0x140030fa4  jz      loc_14003169F
0x140030faa  mov     rcx, [rcx+18h]
0x140030fae  mov     edx, 87h
0x140030fb3  mov     r8, rsi
0x140030fb6  call    WPP_SF_
0x140030fbb  jmp     loc_14003169F
0x140030fc0  mov     eax, [rbx+9Ch]
0x140030fc6  test    al, al
0x140030fc8  js      loc_140031654
0x140030fce  cmp     dword ptr [r13+5Ch], 1
0x140030fd3  jg      loc_140031654
0x140030fd9  mov     rax, [r15+20h]
0x140030fdd  xor     edx, edx
0x140030fdf  mov     esi, edx
0x140030fe1  mov     r15, [rax+28h]
0x140030fe5  mov     rax, [r15+20h]
0x140030fe9  mov     rcx, [rax+20h]
0x140030fed  mov     rax, [rcx+20h]
0x140030ff1  cmp     dword ptr [rax+58h], 3
0x140030ff5  jnz     short loc_140031058
0x140030ff7  mov     rax, [r15+28h]
0x140030ffb  mov     ecx, [rax+20h]
0x140030ffe  test    cl, 8
0x140031001  jz      short loc_140031058
0x140031003  mov     r8, [rbx+88h]
0x14003100a  mov     rcx, r15
0x14003100d  mov     [rsp+0C0h+var_98], edx
0x140031011  mov     [rsp+0C0h+Timeout], rdx
0x140031016  mov     rdx, r14
0x140031019  lea     r9, [r8+10h]
0x14003101d  mov     r8, [r8+8]
0x140031021  call    NfsCommit
0x140031026  mov     esi, eax
0x140031028  test    eax, eax
0x14003102a  jns     short loc_140031058
0x14003102c  mov     rcx, cs:WPP_GLOBAL_Control
0x140031033  cmp     rcx, r12
0x140031036  jz      short loc_140031058
0x140031038  mov     edx, [rcx+2Ch]
0x14003103b  test    dl, 1
0x14003103e  jz      short loc_140031058
0x140031040  mov     rcx, [rcx+18h]
0x140031044  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14003104b  mov     edx, 89h
0x140031050  mov     r9d, eax
0x140031053  call    WPP_SF_d
0x140031058  mov     rcx, [rdi+8]
0x14003105c  call    HacAcquireLock
0x140031061  mov     rcx, [rdi+8]
0x140031065  mov     r12d, [rcx+38h]
0x140031069  lea     eax, [r12-1]
0x14003106e  mov     [rcx+38h], eax
0x140031071  mov     ecx, 10h
0x140031076  mov     eax, [rbx+9Ch]
0x14003107c  test    al, 1
0x14003107e  jz      short loc_140031088
0x140031080  mov     rax, [rdi+8]
0x140031084  or      [rax+30h], cx
0x140031088  mov     rcx, [rdi+8]
0x14003108c  xor     edx, edx; Wait
0x14003108e  movzx   eax, word ptr [rcx+30h]
0x140031092  mov     rcx, [rcx+28h]; Mutex
0x140031096  mov     word ptr [rbp+57h+arg_0], ax
0x14003109a  call    cs:__imp_KeReleaseMutex
0x1400310a1  nop     dword ptr [rax+rax+00h]
0x1400310a6  mov     eax, [r13+48h]
0x1400310aa  test    al, 30h
0x1400310ac  jnz     loc_1400315E2
0x1400310b2  movzx   eax, word ptr [rbp+57h+arg_0]
0x1400310b6  mov     dword ptr [rbp+57h+arg_0], eax
0x1400310b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400310c0  lea     rdx, WPP_GLOBAL_Control
0x1400310c7  cmp     rcx, rdx
0x1400310ca  jz      short loc_1400310F6
0x1400310cc  mov     eax, [rcx+2Ch]
0x1400310cf  test    al, 4
0x1400310d1  jz      short loc_1400310F3
0x1400310d3  mov     r9d, [r13+5Ch]
0x1400310d7  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400310de  mov     rcx, [rcx+18h]
0x1400310e2  mov     edx, 8Ch
0x1400310e7  call    WPP_SF_d
0x1400310ec  lea     rdx, WPP_GLOBAL_Control
0x1400310f3  mov     eax, dword ptr [rbp+57h+arg_0]
0x1400310f6  cmp     r12d, 1
0x1400310fa  jnz     loc_140031305
0x140031100  test    al, 10h
0x140031102  jz      loc_140031305
0x140031108  mov     rcx, cs:WPP_GLOBAL_Control
0x14003110f  cmp     rcx, rdx
0x140031112  jz      short loc_140031130
0x140031114  mov     eax, [rcx+2Ch]
0x140031117  test    al, 4
0x140031119  jz      short loc_140031130
0x14003111b  mov     rcx, [rcx+18h]
0x14003111f  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x140031126  mov     edx, 8Dh
0x14003112b  call    WPP_SF_
0x140031130  mov     rcx, [rdi+8]
0x140031134  call    HacAcquireLock
0x140031139  mov     rcx, [rdi+8]
0x14003113d  xor     eax, eax
0x14003113f  cmp     [rcx+40h], ax
0x140031143  jnz     short loc_14003118F
0x140031145  mov     rcx, cs:WPP_GLOBAL_Control
0x14003114c  lea     r14, WPP_GLOBAL_Control
0x140031153  cmp     rcx, r14
0x140031156  jz      short loc_140031174
0x140031158  mov     eax, [rcx+2Ch]
0x14003115b  test    al, 2
0x14003115d  jz      short loc_140031174
0x14003115f  mov     rcx, [rcx+18h]
0x140031163  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x14003116a  mov     edx, 8Eh
0x14003116f  call    WPP_SF_
0x140031174  mov     rcx, [rdi+8]
0x140031178  xor     edx, edx; Wait
0x14003117a  mov     rcx, [rcx+28h]; Mutex
0x14003117e  call    cs:__imp_KeReleaseMutex
0x140031185  nop     dword ptr [rax+rax+00h]
0x14003118a  jmp     loc_14003129F
0x14003118f  mov     ebx, [rcx+80h]
0x140031195  xor     edx, edx; Wait
0x140031197  mov     rcx, [rcx+28h]; Mutex
0x14003119b  mov     dword ptr [rbp+57h+arg_0], ebx
0x14003119e  call    cs:__imp_KeReleaseMutex
0x1400311a5  nop     dword ptr [rax+rax+00h]
0x1400311aa  mov     rax, [rdi+8]
0x1400311ae  mov     r8d, ebx
0x1400311b1  mov     r9, [rdi]
0x1400311b4  mov     rdx, r14
0x1400311b7  mov     rcx, r15
0x1400311ba  mov     [rsp+0C0h+Timeout], rax
0x1400311bf  call    NfsRemoveOrRmdir
0x1400311c4  xor     r15d, r15d
0x1400311c7  mov     esi, eax
0x1400311c9  test    eax, eax
0x1400311cb  js      loc_1400312D1
0x1400311d1  mov     r14, [rbp+57h+arg_10]
0x1400311d5  lea     r12d, [r15+20h]
0x1400311d9  or      [r13+48h], r12d
0x1400311dd  xor     r9d, r9d; Alertable
0x1400311e0  xor     r8d, r8d; WaitMode
0x1400311e3  mov     [rsp+0C0h+Timeout], r15; Timeout
0x1400311e8  xor     edx, edx; WaitReason
0x1400311ea  lea     rbx, [r14+830h]
0x1400311f1  mov     rcx, rbx; Object
0x1400311f4  call    cs:__imp_KeWaitForSingleObject
0x1400311fb  nop     dword ptr [rax+rax+00h]
0x140031200  mov     rcx, [rdi+8]
0x140031204  call    HacAcquireLock
0x140031209  mov     rcx, [rbp+57h+arg_8]
0x14003120d  mov     r10d, r15d
0x140031210  cmp     dword ptr [rbp+57h+arg_0], 2
0x140031214  mov     qword ptr [rsp+0C0h+var_80], r15; int
0x140031219  setz    r10b
0x14003121d  mov     [rsp+0C0h+var_88], 2; int
0x140031225  mov     rax, [rcx+20h]
0x140031229  inc     r10d
0x14003122c  mov     [rsp+0C0h+var_90], r10d; int
0x140031231  mov     qword ptr [rsp+0C0h+var_98], r15; int
0x140031236  mov     [rsp+0C0h+Timeout], r15; __int16
0x14003123b  mov     rcx, [rax+28h]
0x14003123f  mov     rax, [rcx+20h]
0x140031243  mov     rcx, [rax+28h]
0x140031247  mov     rax, [rdi+8]
0x14003124b  lea     rdx, [rcx+58h]
0x14003124f  mov     rcx, [rcx+68h]; FastMutex
0x140031253  lea     r8, [rax+40h]
0x140031257  movzx   r9d, word ptr [r8]
0x14003125b  sub     r9w, [rax+50h]
0x140031260  call    MdaNotifyFullReportChange
0x140031265  mov     rcx, [rdi+8]
0x140031269  xor     edx, edx; Wait
0x14003126b  mov     rcx, [rcx+28h]; Mutex
0x14003126f  call    cs:__imp_KeReleaseMutex
0x140031276  nop     dword ptr [rax+rax+00h]
0x14003127b  xor     edx, edx; Wait
0x14003127d  mov     rcx, rbx; Mutex
0x140031280  call    cs:__imp_KeReleaseMutex
0x140031287  nop     dword ptr [rax+rax+00h]
0x14003128c  mov     rdx, [rdi+8]
0x140031290  mov     rcx, r14
0x140031293  call    HacOrphanStaleEntry
0x140031298  lea     r14, WPP_GLOBAL_Control
0x14003129f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400312a6  cmp     rcx, r14
0x1400312a9  jz      short loc_1400312CA
0x1400312ab  mov     eax, [rcx+2Ch]
0x1400312ae  test    al, 8
0x1400312b0  jz      short loc_1400312CA
0x1400312b2  mov     rcx, [rcx+18h]
0x1400312b6  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400312bd  mov     edx, 91h
0x1400312c2  mov     r9d, esi
0x1400312c5  call    WPP_SF_d
0x1400312ca  mov     eax, esi
0x1400312cc  jmp     loc_1400316A1
0x1400312d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400312d8  lea     r14, WPP_GLOBAL_Control
0x1400312df  cmp     rcx, r14
0x1400312e2  jz      short loc_1400312CA
0x1400312e4  mov     eax, [rcx+2Ch]
0x1400312e7  test    al, 1
0x1400312e9  jz      short loc_14003129F
0x1400312eb  mov     rcx, [rcx+18h]
0x1400312ef  lea     r8, WPP_4a26443b46aa335a1d99573c845c5512_Traceguids
0x1400312f6  mov     edx, 8Fh
0x1400312fb  mov     r9d, esi
0x1400312fe  call    WPP_SF_d
0x140031303  jmp     short loc_14003129F
0x140031305  mov     r12d, 20h ; ' '
0x14003130b  test    r12b, al
0x14003130e  setz    cl
0x140031311  test    byte ptr [rbx+9Ch], 1
0x140031318  setnz   al
0x14003131b  test    al, cl
0x14003131d  jz      loc_140031298
0x140031323  mov     r9, [rdi]
0x140031326  lea     r8, [rbp+57h+P]
0x14003132a  xorps   xmm0, xmm0
0x14003132d  xorps   xmm1, xmm1
0x140031330  xor     ebx, ebx
0x140031332  mov     rdx, r14
0x140031335  mov     rcx, r15
0x140031338  mov     [rbp+57h+arg_0], rbx
0x14003133c  movups  xmmword ptr [rbp+57h+P], xmm0
0x140031340  movups  [rbp+57h+var_50], xmm1
0x140031344  movups  [rbp+57h+var_60], xmm0
0x140031348  call    GetTempNameForDelRenaming
0x14003134d  mov     esi, eax
0x14003134f  test    eax, eax
0x140031351  js      loc_140031298
0x140031357  movzx   eax, word ptr [rbp+57h+P+2]
0x14003135b  xor     esi, esi
0x14003135d  test    ax, ax
0x140031360  jz      short loc_1400313BD
0x140031362  mov     edx, eax
0x140031364  mov     ecx, 102h
0x140031369  mov     r8d, 3152664Eh
0x14003136f  call    cs:__imp_ExAllocatePool2
0x140031376  nop     dword ptr [rax+rax+00h]
0x14003137b  mov     rbx, rax
0x14003137e  test    rax, rax
0x140031381  jnz     short loc_1400313BD
0x140031383  mov     rcx, cs:WPP_GLOBAL_Control
0x14003138a  lea     r14, WPP_GLOBAL_Control
0x140031391  cmp     rcx, r14
0x140031394  jz      short loc_1400313B3
0x140031396  mov     edx, [rcx+2Ch]
0x140031399  test    dl, 1
  ... truncated ...
```
