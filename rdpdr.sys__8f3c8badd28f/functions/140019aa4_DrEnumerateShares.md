# DrEnumerateShares

- ea: `0x140019aa4`
- end: `0x140019f0f`
- name: `DrEnumerateShares`
- size: `1131`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x14002acc0`

## callees

- `0x1400016a0`
- `0x140001c50`
- `0x140001c70`
- `0x140001e60`
- `0x140001ef0`
- `0x14000327c`
- `0x1400064b0`
- `0x140006560`
- `0x140011bfc`
- `0x140011c60`
- `0x140011ce4`
- `0x140018c98`
- `0x140019aa4`
- `0x140027f30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140019bfa`
- `ntoskrnl!ExAllocatePool2` at `0x140019bfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ecc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019ecc`
- `ntoskrnl!ProbeForWrite` at `0x140019b74`
- `ntoskrnl!ProbeForWrite` at `0x140019b8b`
- `ntoskrnl!ProbeForWrite` at `0x140019b74`
- `ntoskrnl!ProbeForWrite` at `0x140019b8b`

## pseudocode

```c
__int64 __fastcall DrEnumerateShares(__int64 a1)
{
  char *v1; // rbx
  SIZE_T v2; // rsi
  __int64 v3; // r13
  __int64 v4; // rax
  unsigned int *v5; // r15
  int v6; // r12d
  unsigned int v7; // ecx
  char *v8; // r14
  char *Pool2; // rax
  unsigned int *v11; // rcx
  unsigned int ULongFromUser; // eax
  unsigned int v13; // eax
  int v14; // r15d
  int v15; // ebx
  __int64 v16; // rbx
  struct ListEntry *v17; // rax
  struct DrDevice *v18; // rbx
  struct _RX_CONTEXT *v19; // rcx
  _DWORD *v20; // rcx
  _DWORD *v21; // rcx
  __int64 v22; // [rsp+40h] [rbp-78h]
  unsigned int v23[2]; // [rsp+48h] [rbp-70h] BYREF
  char *v24; // [rsp+50h] [rbp-68h]
  unsigned int *v25; // [rsp+58h] [rbp-60h]
  char *v26; // [rsp+60h] [rbp-58h]
  char *v27; // [rsp+68h] [rbp-50h]
  SIZE_T v28; // [rsp+70h] [rbp-48h]
  __int64 v29; // [rsp+78h] [rbp-40h]
  unsigned int v30; // [rsp+C0h] [rbp+8h]
  struct ListEntry *v31; // [rsp+C0h] [rbp+8h]
  struct ListEntry *v32; // [rsp+C0h] [rbp+8h]
  __int64 v33; // [rsp+C8h] [rbp+10h] BYREF
  char *v34; // [rsp+D0h] [rbp+18h] BYREF
  char *v35; // [rsp+D8h] [rbp+20h] BYREF

  v1 = *(char **)(a1 + 560);
  v26 = v1;
  v2 = *(unsigned int *)(a1 + 572);
  v35 = v1;
  v34 = &v1[v2];
  v33 = 0;
  if ( !(_DWORD)v2 )
  {
    v35 = 0;
    v34 = 0;
  }
  if ( (*(_BYTE *)(a1 + 540) & 3) != 3 || (v3 = a1 + 40, v4 = *(_QWORD *)(a1 + 40), *(_QWORD *)(v4 + 8)) )
  {
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v33);
    return 3221225488LL;
  }
  else
  {
    v5 = *(unsigned int **)(a1 + 552);
    v25 = v5;
    if ( !v5 || !v1 )
    {
LABEL_12:
      SmartPtr<DrFile>::~SmartPtr<DrFile>(&v33);
      return 3221225485LL;
    }
    v27 = v1;
    v28 = v2;
    v29 = a1 + 40;
    v6 = 0;
    v7 = *(_DWORD *)(a1 + 568);
    v30 = v7;
    v8 = 0;
    v24 = 0;
    if ( *(_BYTE *)(v4 + 64) )
    {
      ProbeForWrite(v5, v7, 1u);
      ProbeForWrite(v1, v2, 1u);
      if ( (unsigned int)v2 > 0xA0000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids,
            (unsigned int)v2);
        goto LABEL_12;
      }
      if ( (_DWORD)v2 )
      {
        Pool2 = (char *)ExAllocatePool2(64, v2, 1917088324);
        v8 = Pool2;
        v24 = Pool2;
        if ( !Pool2 )
        {
          SmartPtr<DrFile>::~SmartPtr<DrFile>(&v33);
          return 3221225626LL;
        }
        v35 = Pool2;
        v34 = &Pool2[v2];
      }
      v7 = v30;
    }
    if ( v7 >= 0x18 )
    {
      *(_QWORD *)v23 = 0;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlReadULongFromUser(v5);
      v11 = v5 + 5;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        ULongFromUser = RtlReadULongFromUser(v11);
      else
        ULongFromUser = *v11;
      v23[1] = ULongFromUser;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        v13 = RtlReadULongFromUser(v5 + 1);
      else
        v13 = v5[1];
      v14 = 0;
      v22 = 0;
      v15 = 0;
      v23[0] = 0;
      if ( (unsigned int)DrSessionManager::FindSessionById(WPP_MAIN_CB.Queue.Wcb.DeviceContext, v13, &v33) )
      {
        v16 = v33;
        KernelResource::AcquireResourceShared((KernelResource *)(v33 + 976));
        v17 = DoubleList::First((DoubleList *)(v16 + 944));
        v31 = v17;
        while ( v17 )
        {
          v18 = (struct DrDevice *)*((_QWORD *)v17 + 2);
          if ( (*(unsigned int (__fastcall **)(struct DrDevice *))(*(_QWORD *)v18 + 96LL))(v18)
            && *((_DWORD *)v18 + 11) == 8 )
          {
            ++HIDWORD(v22);
            if ( DrPackShareEntry(v19, &v35, &v34, v18, v23) )
            {
              v14 = v22 + 1;
              LODWORD(v22) = v22 + 1;
            }
            else
            {
              v6 = -1073741789;
              v14 = v22;
            }
          }
          v17 = DoubleList::Next((DoubleList *)(v33 + 944), v31);
          v31 = v17;
        }
        DoubleList::Unlock((DoubleList *)(v33 + 944));
        v15 = HIDWORD(v22);
      }
      v20 = v25 + 2;
      v32 = (struct ListEntry *)(v25 + 2);
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
      {
        RtlWriteULongToUser(v20, v14);
        v20 = v32;
      }
      else
      {
        *v20 = v14;
      }
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
      {
        RtlWriteULongToUser(v20 + 1, v15);
        v20 = v32;
      }
      else
      {
        v20[1] = v15;
      }
      v21 = v20 + 2;
      if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
        RtlWriteULongToUser(v21, v23[0]);
      else
        *v21 = v23[0];
      v1 = v26;
    }
    else
    {
      v6 = -1073741789;
    }
    if ( v8 )
    {
      if ( v6 >= 0 )
      {
        if ( *(_BYTE *)(*(_QWORD *)v3 + 64LL) )
          RtlCopyToUser(v1, v8, v2);
        else
          RtlCopyVolatileMemory(v1, v8, v2);
      }
      ExFreePoolWithTag(v8, 0);
    }
    SmartPtr<DrFile>::~SmartPtr<DrFile>(&v33);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x140019aa4  mov     r11, rsp
0x140019aa7  push    rbx
0x140019aa8  push    rsi
0x140019aa9  push    r12
0x140019aab  push    r13
0x140019aad  push    r14
0x140019aaf  push    r15
0x140019ab1  sub     rsp, 88h
0x140019ab8  mov     rbx, [rcx+230h]
0x140019abf  mov     [rsp+0B8h+var_58], rbx
0x140019ac4  mov     esi, [rcx+23Ch]
0x140019aca  mov     [r11+20h], rbx
0x140019ace  lea     rax, [rsi+rbx]
0x140019ad2  mov     [r11+18h], rax
0x140019ad6  mov     qword ptr [r11+10h], 0
0x140019ade  test    esi, esi
0x140019ae0  jnz     short loc_140019AF2
0x140019ae2  mov     qword ptr [r11+20h], 0
0x140019aea  mov     qword ptr [r11+18h], 0
0x140019af2  mov     eax, [rcx+21Ch]
0x140019af8  and     eax, 3
0x140019afb  cmp     al, 3
0x140019afd  jnz     loc_140019EEA
0x140019b03  lea     r13, [rcx+28h]
0x140019b07  mov     rax, [r13+0]
0x140019b0b  cmp     qword ptr [rax+8], 0
0x140019b10  jnz     loc_140019EEA
0x140019b16  mov     r15, [rcx+228h]
0x140019b1d  mov     [rsp+0B8h+var_60], r15
0x140019b22  test    r15, r15
0x140019b25  jz      loc_140019BD1
0x140019b2b  test    rbx, rbx
0x140019b2e  jz      loc_140019BD1
0x140019b34  mov     [rsp+0B8h+var_50], rbx
0x140019b39  mov     [rsp+0B8h+var_48], rsi
0x140019b3e  mov     [rsp+0B8h+var_40], r13
0x140019b43  xor     r12d, r12d
0x140019b46  mov     ecx, [rcx+238h]
0x140019b4c  mov     dword ptr [rsp+0B8h+arg_0], ecx
0x140019b53  xor     r14d, r14d
0x140019b56  mov     [rsp+0B8h+var_68], r14
0x140019b5b  mov     [rsp+0B8h+var_88], r12b
0x140019b60  cmp     [rax+40h], r12b
0x140019b64  jz      loc_140019C5E
0x140019b6a  mov     edx, ecx; Length
0x140019b6c  lea     r8d, [r12+1]; Alignment
0x140019b71  mov     rcx, r15; Address
0x140019b74  call    cs:__imp_ProbeForWrite
0x140019b7b  nop     dword ptr [rax+rax+00h]
0x140019b80  lea     r8d, [r12+1]; Alignment
0x140019b85  mov     rdx, rsi; Length
0x140019b88  mov     rcx, rbx; Address
0x140019b8b  call    cs:__imp_ProbeForWrite
0x140019b92  nop     dword ptr [rax+rax+00h]
0x140019b97  nop
0x140019b98  cmp     esi, 0A0000h
0x140019b9e  jbe     short loc_140019BE8
0x140019ba0  lea     rax, WPP_GLOBAL_Control
0x140019ba7  mov     rcx, cs:WPP_GLOBAL_Control
0x140019bae  cmp     rcx, rax
0x140019bb1  jz      short loc_140019BD1
0x140019bb3  cmp     byte ptr [rcx+29h], 2
0x140019bb7  jb      short loc_140019BD1
0x140019bb9  mov     edx, 28h ; '('
0x140019bbe  mov     r9d, esi
0x140019bc1  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x140019bc8  mov     rcx, [rcx+18h]
0x140019bcc  call    WPP_SF_d
0x140019bd1  lea     rcx, [rsp+0B8h+arg_8]
0x140019bd9  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019bde  mov     eax, 0C000000Dh
0x140019be3  jmp     loc_140019EFC
0x140019be8  test    esi, esi
0x140019bea  jz      short loc_140019C57
0x140019bec  mov     r8d, 72447244h
0x140019bf2  mov     rdx, rsi
0x140019bf5  mov     ecx, 40h ; '@'
0x140019bfa  call    cs:__imp_ExAllocatePool2
0x140019c01  nop     dword ptr [rax+rax+00h]
0x140019c06  mov     r14, rax
0x140019c09  mov     [rsp+0B8h+var_68], rax
0x140019c0e  test    rax, rax
0x140019c11  jnz     short loc_140019C2A
0x140019c13  lea     rcx, [rsp+0B8h+arg_8]
0x140019c1b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019c20  mov     eax, 0C000009Ah
0x140019c25  jmp     loc_140019EFC
0x140019c2a  mov     [rsp+0B8h+arg_18], rax
0x140019c32  lea     rax, [rsi+rax]
0x140019c36  mov     [rsp+0B8h+arg_10], rax
0x140019c3e  jmp     short loc_140019C57
0x140019c40  lea     rcx, [rsp+0B8h+arg_8]
0x140019c48  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019c4d  mov     eax, 0C000000Dh
0x140019c52  jmp     loc_140019EFC
0x140019c57  mov     ecx, dword ptr [rsp+0B8h+arg_0]
0x140019c5e  cmp     ecx, 18h
0x140019c61  jnb     short loc_140019C73
0x140019c63  mov     r12d, 0C0000023h
0x140019c69  mov     [rsp+0B8h+var_84], r12d
0x140019c6e  jmp     loc_140019E76
0x140019c73  xorps   xmm0, xmm0
0x140019c76  xor     eax, eax
0x140019c78  movups  [rsp+0B8h+var_80], xmm0
0x140019c7d  mov     qword ptr [rsp+0B8h+var_70], rax
0x140019c82  mov     rax, [r13+0]
0x140019c86  cmp     byte ptr [rax+40h], 0
0x140019c8a  jz      short loc_140019C96
0x140019c8c  mov     rcx, r15
0x140019c8f  call    RtlReadULongFromUser
0x140019c94  jmp     short loc_140019C99
0x140019c96  mov     eax, [r15]
0x140019c99  mov     dword ptr [rsp+0B8h+var_80], eax
0x140019c9d  lea     rcx, [r15+14h]
0x140019ca1  mov     rax, [r13+0]
0x140019ca5  cmp     byte ptr [rax+40h], 0
0x140019ca9  jz      short loc_140019CB2
0x140019cab  call    RtlReadULongFromUser
0x140019cb0  jmp     short loc_140019CB4
0x140019cb2  mov     eax, [rcx]
0x140019cb4  mov     [rsp+0B8h+var_70+4], eax
0x140019cb8  mov     rax, [r13+0]
0x140019cbc  cmp     byte ptr [rax+40h], 0
0x140019cc0  jz      short loc_140019CCD
0x140019cc2  lea     rcx, [r15+4]
0x140019cc6  call    RtlReadULongFromUser
0x140019ccb  jmp     short loc_140019CD1
0x140019ccd  mov     eax, [r15+4]
0x140019cd1  mov     dword ptr [rsp+0B8h+var_80+4], eax
0x140019cd5  xor     r15d, r15d
0x140019cd8  mov     qword ptr [rsp+0B8h+var_80+8], r15
0x140019cdd  xor     ebx, ebx
0x140019cdf  mov     [rsp+0B8h+var_70], ebx
0x140019ce3  lea     r8, [rsp+0B8h+arg_8]
0x140019ceb  mov     edx, eax
0x140019ced  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+20h
0x140019cf4  call    ?FindSessionById@DrSessionManager@@QEAAHKAEAV?$SmartPtr@VDrSession@@@@@Z; DrSessionManager::FindSessionById(ulong,SmartPtr<DrSession> &)
0x140019cf9  test    eax, eax
0x140019cfb  jz      loc_140019DE3
0x140019d01  mov     rbx, [rsp+0B8h+arg_8]
0x140019d09  lea     rcx, [rbx+3D0h]; this
0x140019d10  call    ?AcquireResourceShared@KernelResource@@QEAAXXZ; KernelResource::AcquireResourceShared(void)
0x140019d15  mov     [rsp+0B8h+var_88], 1
0x140019d1a  lea     rcx, [rbx+3B0h]; this
0x140019d21  call    ?First@DoubleList@@QEAAPEAVListEntry@@XZ; DoubleList::First(void)
0x140019d26  mov     [rsp+0B8h+arg_0], rax
0x140019d2e  test    rax, rax
0x140019d31  jz      loc_140019DC6
0x140019d37  mov     rbx, [rax+10h]
0x140019d3b  mov     rax, [rbx]
0x140019d3e  mov     rax, [rax+60h]
0x140019d42  mov     rcx, rbx
0x140019d45  call    _guard_dispatch_icall
0x140019d4a  test    eax, eax
0x140019d4c  jz      short loc_140019D9D
0x140019d4e  cmp     dword ptr [rbx+2Ch], 8
0x140019d52  jnz     short loc_140019D9D
0x140019d54  inc     dword ptr [rsp+0B8h+var_80+0Ch]
0x140019d58  lea     rax, [rsp+0B8h+var_70]
0x140019d5d  mov     [rsp+0B8h+var_98], rax; unsigned int *
0x140019d62  mov     r9, rbx; struct DrDevice *
0x140019d65  lea     r8, [rsp+0B8h+arg_10]; char **
0x140019d6d  lea     rdx, [rsp+0B8h+arg_18]; char **
0x140019d75  call    ?DrPackShareEntry@@YAEPEAU_RX_CONTEXT@@PEAPEAD1PEAVDrDevice@@PEAK@Z; DrPackShareEntry(_RX_CONTEXT *,char * *,char * *,DrDevice *,ulong *)
0x140019d7a  test    al, al
0x140019d7c  jz      short loc_140019D8D
0x140019d7e  mov     r15d, dword ptr [rsp+0B8h+var_80+8]
0x140019d83  inc     r15d
0x140019d86  mov     dword ptr [rsp+0B8h+var_80+8], r15d
0x140019d8b  jmp     short loc_140019D9D
0x140019d8d  mov     r12d, 0C0000023h
0x140019d93  mov     [rsp+0B8h+var_84], r12d
0x140019d98  mov     r15d, dword ptr [rsp+0B8h+var_80+8]
0x140019d9d  mov     rcx, [rsp+0B8h+arg_8]
0x140019da5  add     rcx, 3B0h; this
0x140019dac  mov     rdx, [rsp+0B8h+arg_0]; struct ListEntry *
0x140019db4  call    ?Next@DoubleList@@QEAAPEAVListEntry@@PEAV2@@Z; DoubleList::Next(ListEntry *)
0x140019db9  mov     [rsp+0B8h+arg_0], rax
0x140019dc1  jmp     loc_140019D2E
0x140019dc6  mov     rcx, [rsp+0B8h+arg_8]
0x140019dce  add     rcx, 3B0h; this
0x140019dd5  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x140019dda  mov     [rsp+0B8h+var_88], 0
0x140019ddf  mov     ebx, dword ptr [rsp+0B8h+var_80+0Ch]
0x140019de3  mov     rcx, [rsp+0B8h+var_60]
0x140019de8  add     rcx, 8
0x140019dec  mov     [rsp+0B8h+arg_0], rcx
0x140019df4  mov     rax, [r13+0]
0x140019df8  cmp     byte ptr [rax+40h], 0
0x140019dfc  jz      short loc_140019E10
0x140019dfe  mov     edx, r15d
0x140019e01  call    RtlWriteULongToUser
0x140019e06  mov     rcx, [rsp+0B8h+arg_0]
0x140019e0e  jmp     short loc_140019E13
0x140019e10  mov     [rcx], r15d
0x140019e13  mov     rax, [r13+0]
0x140019e17  cmp     byte ptr [rax+40h], 0
0x140019e1b  jz      short loc_140019E32
0x140019e1d  mov     edx, ebx
0x140019e1f  add     rcx, 4
0x140019e23  call    RtlWriteULongToUser
0x140019e28  mov     rcx, [rsp+0B8h+arg_0]
0x140019e30  jmp     short loc_140019E35
0x140019e32  mov     [rcx+4], ebx
0x140019e35  mov     edx, [rsp+0B8h+var_70]
0x140019e39  add     rcx, 8
0x140019e3d  mov     rax, [r13+0]
0x140019e41  cmp     byte ptr [rax+40h], 0
0x140019e45  jz      short loc_140019E4E
0x140019e47  call    RtlWriteULongToUser
0x140019e4c  jmp     short loc_140019E50
0x140019e4e  mov     [rcx], edx
0x140019e50  mov     rbx, [rsp+0B8h+var_58]
0x140019e55  jmp     short loc_140019E76
0x140019e57  mov     r12d, 0C000000Dh
0x140019e5d  mov     [rsp+0B8h+var_84], r12d
0x140019e62  mov     rbx, [rsp+0B8h+var_50]
0x140019e67  mov     r14, [rsp+0B8h+var_68]
0x140019e6c  mov     rsi, [rsp+0B8h+var_48]
0x140019e71  mov     r13, [rsp+0B8h+var_40]
0x140019e76  cmp     [rsp+0B8h+var_88], 0
0x140019e7b  jz      short loc_140019E91
0x140019e7d  mov     rcx, [rsp+0B8h+arg_8]
0x140019e85  add     rcx, 3B0h; this
0x140019e8c  call    ?Unlock@DoubleList@@QEAAXXZ; DoubleList::Unlock(void)
0x140019e91  test    r14, r14
0x140019e94  jz      short loc_140019ED8
0x140019e96  test    r12d, r12d
0x140019e99  js      short loc_140019EC7
0x140019e9b  mov     rax, [r13+0]
0x140019e9f  mov     r8, rsi; Size
0x140019ea2  mov     rdx, r14; Src
0x140019ea5  mov     rcx, rbx; void *
0x140019ea8  cmp     byte ptr [rax+40h], 0
0x140019eac  jz      short loc_140019EB5
0x140019eae  call    RtlCopyToUser
0x140019eb3  jmp     short loc_140019EBA
0x140019eb5  call    RtlCopyVolatileMemory
0x140019eba  jmp     short loc_140019EC7
0x140019ebc  mov     r12d, 0C000000Dh
0x140019ec2  mov     r14, [rsp+0B8h+var_68]
0x140019ec7  xor     edx, edx; Tag
0x140019ec9  mov     rcx, r14; P
0x140019ecc  call    cs:__imp_ExFreePoolWithTag
0x140019ed3  nop     dword ptr [rax+rax+00h]
0x140019ed8  lea     rcx, [rsp+0B8h+arg_8]
0x140019ee0  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019ee5  mov     eax, r12d
0x140019ee8  jmp     short loc_140019EFC
0x140019eea  lea     rcx, [rsp+0B8h+arg_8]
0x140019ef2  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140019ef7  mov     eax, 0C0000010h
0x140019efc  add     rsp, 88h
0x140019f03  pop     r15
0x140019f05  pop     r14
0x140019f07  pop     r13
0x140019f09  pop     r12
0x140019f0b  pop     rsi
0x140019f0c  pop     rbx
0x140019f0d  retn
```
