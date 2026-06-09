# CddBitmapHw::RecreateDeviceAllocations(void)

- ea: `0x14001b170`
- end: `0x14001b43f`
- name: `?RecreateDeviceAllocations@CddBitmapHw@@UEAAJXZ`
- size: `719`
- prototype: `__int64 __fastcall(CddBitmapHw *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001b170`
- `0x14001b448`
- `0x14001b6e8`
- `0x14001ef90`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x14001b21a`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b21a`
- `watchdog!WdLogSingleEntry2` at `0x14001b3e1`
- `watchdog!WdLogSingleEntry2` at `0x14001b3e1`
- `watchdog!WdLogSingleEntry1` at `0x14001b369`
- `watchdog!WdLogSingleEntry1` at `0x14001b369`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001b3f8`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001b3f8`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001b1b5`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x14001b1b5`
- `watchdog!WdLogSingleEntry0` at `0x14001b19e`
- `watchdog!WdLogSingleEntry0` at `0x14001b276`
- `watchdog!WdLogSingleEntry0` at `0x14001b3a6`
- `watchdog!WdLogSingleEntry0` at `0x14001b19e`
- `watchdog!WdLogSingleEntry0` at `0x14001b276`
- `watchdog!WdLogSingleEntry0` at `0x14001b3a6`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b28d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b380`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b28d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b380`

## pseudocode

```c
__int64 __fastcall CddBitmapHw::RecreateDeviceAllocations(unsigned __int64 this, __int64 a2, __int64 a3)
{
  unsigned int *v3; // r15
  CddBitmapHw *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  int v8; // esi
  void *v9; // rbp
  int v10; // esi
  int v11; // r12d
  _QWORD *v12; // r14
  CDDPDEV *v13; // rbx
  struct _EPROCESS *CurrentProcess; // rax
  unsigned int v15; // eax
  _QWORD *v16; // rax
  unsigned int v17; // ebx
  int v18; // ecx
  __int64 v19; // r10
  unsigned int v20; // r8d
  int Allocation; // eax
  int v22; // edi
  _QWORD *v23; // rax
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  unsigned int v28; // [rsp+90h] [rbp+8h] BYREF

  v3 = (unsigned int *)(this + 40);
  v4 = (CddBitmapHw *)this;
  if ( *(_DWORD *)(this + 40) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 1055;
    v7 = (_QWORD *)WdLogNewEntry5_WdAssertion(v6, v5);
    v7[3] = gCddImageInfo;
    this = (unsigned int)dword_14003E570;
    v7[4] = (unsigned int)dword_14003E570;
    v7[5] = 215857758;
    WdLogGlobalForLineNumber = 1055;
  }
  v8 = *((_DWORD *)v4 + 32);
  if ( (v8 & 0x10) == 0 || (v9 = (void *)*((_QWORD *)v4 + 69)) == 0 )
  {
    if ( (v8 & 2) != 0 )
      v18 = (v8 & 0x80u) != 0 ? 7 : 1;
    else
      v18 = 3;
    *((_DWORD *)v4 + 9) = v18;
    v28 = 0;
    v12 = (_QWORD *)((char *)v4 + 8);
    v19 = *((_QWORD *)v4 + 1);
    v20 = 21;
    if ( (v8 & 2) == 0 )
      v20 = *(_DWORD *)(v19 + 1032);
    Allocation = CDDPDEV::CreateAllocation(
                   v19,
                   (__int64)v4,
                   *((_DWORD *)v4 + 4),
                   *((_DWORD *)v4 + 5),
                   v18,
                   v20,
                   0,
                   v3,
                   (__int64)&v28,
                   0,
                   (__int64)v4 + 24,
                   0);
    v17 = Allocation;
    if ( Allocation >= 0 )
    {
      if ( (*((_DWORD *)v4 + 32) & 2) == 0 )
        goto LABEL_23;
      if ( v28 )
      {
        *((_QWORD *)v4 + 69) = v28;
        goto LABEL_23;
      }
      WdLogSingleEntry0(4);
      v22 = 1141;
    }
    else
    {
      WdLogSingleEntry1(4, Allocation);
      v22 = 1133;
    }
    WdLogGlobalForLineNumber = v22;
    v23 = (_QWORD *)WdLogNewEntry5_WdEvent();
    goto LABEL_25;
  }
  v10 = *((_DWORD *)v4 + 32) & 0x40;
  if ( v10 )
  {
    v11 = 0;
  }
  else
  {
    v11 = *((_DWORD *)v4 + 138);
    v9 = 0;
  }
  v12 = (_QWORD *)((char *)v4 + 8);
  v13 = (CDDPDEV *)*((_QWORD *)v4 + 1);
  CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess(this, a2, a3);
  v15 = CDDPDEV::OpenResource(
          v13,
          v11,
          v9,
          *((_DWORD *)v4 + 132),
          CurrentProcess,
          0,
          0,
          0,
          (void **)(((unsigned __int64)v4 + 176) & -(__int64)(v10 != 0)));
  if ( v15 )
  {
    *v3 = v15;
LABEL_23:
    v24 = CDDSYNCOBJECT::Create((CddBitmapHw *)((char *)v4 + 208), v4);
    v17 = v24;
    if ( v24 >= 0 )
      return v17;
    WdLogSingleEntry2(2, v24, *v12);
    v22 = 1156;
    WdLogGlobalForLineNumber = 1156;
    v23 = (_QWORD *)WdLogNewEntry5_WdError(v26, v25);
LABEL_25:
    v23[3] = gCddImageInfo;
    v23[4] = (unsigned int)dword_14003E570;
    v23[5] = 215857758;
    WdLogGlobalForLineNumber = v22;
    return v17;
  }
  WdLogSingleEntry0(4);
  WdLogGlobalForLineNumber = 1080;
  v16 = (_QWORD *)WdLogNewEntry5_WdEvent();
  v16[3] = gCddImageInfo;
  v16[4] = (unsigned int)dword_14003E570;
  v16[5] = 215857758;
  WdLogGlobalForLineNumber = 1080;
  return (unsigned int)-1073741823;
}

```

## disassembly

```asm
0x14001b170  mov     [rsp+arg_8], rbx
0x14001b175  mov     [rsp+arg_10], rbp
0x14001b17a  push    rsi
0x14001b17b  push    rdi
0x14001b17c  push    r12
0x14001b17e  push    r14
0x14001b180  push    r15
0x14001b182  sub     rsp, 60h
0x14001b186  lea     r15, [rcx+28h]
0x14001b18a  mov     rdi, rcx
0x14001b18d  cmp     dword ptr [r15], 0
0x14001b191  mov     r12d, 0CDDBA5Eh
0x14001b197  jz      short loc_14001B1E0
0x14001b199  mov     ecx, 1
0x14001b19e  call    cs:__imp_WdLogSingleEntry0
0x14001b1a5  nop     dword ptr [rax+rax+00h]
0x14001b1aa  mov     ebx, 41Fh
0x14001b1af  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001b1b5  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x14001b1bc  nop     dword ptr [rax+rax+00h]
0x14001b1c1  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b1c8  mov     [rax+18h], rcx
0x14001b1cc  mov     ecx, cs:dword_14003E570
0x14001b1d2  mov     [rax+20h], rcx
0x14001b1d6  mov     [rax+28h], r12
0x14001b1da  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001b1e0  mov     esi, [rdi+80h]
0x14001b1e6  test    sil, 10h
0x14001b1ea  jz      loc_14001B2D4
0x14001b1f0  mov     rbp, [rdi+228h]
0x14001b1f7  test    rbp, rbp
0x14001b1fa  jz      loc_14001B2D4
0x14001b200  and     esi, 40h
0x14001b203  jz      short loc_14001B20A
0x14001b205  xor     r12d, r12d
0x14001b208  jmp     short loc_14001B213
0x14001b20a  mov     r12d, [rdi+228h]
0x14001b211  xor     ebp, ebp
0x14001b213  lea     r14, [rdi+8]
0x14001b217  mov     rbx, [r14]
0x14001b21a  call    cs:__imp_PsGetCurrentProcess
0x14001b221  nop     dword ptr [rax+rax+00h]
0x14001b226  lea     r10, [rdi+0B0h]
0x14001b22d  neg     esi
0x14001b22f  mov     r8, rbp; void *
0x14001b232  mov     edx, r12d; unsigned int
0x14001b235  sbb     r9, r9
0x14001b238  mov     rcx, rbx; this
0x14001b23b  and     r9, r10
0x14001b23e  mov     [rsp+88h+var_48], r9; void **
0x14001b243  mov     r9d, [rdi+210h]; unsigned int
0x14001b24a  mov     [rsp+88h+var_50], 0; unsigned __int64 *
0x14001b253  mov     [rsp+88h+var_58], 0; void **
0x14001b25c  mov     [rsp+88h+var_60], 0; unsigned int *
0x14001b265  mov     [rsp+88h+var_68], rax; struct _EPROCESS *
0x14001b26a  call    ?OpenResource@CDDPDEV@@QEAAIIPEAXIPEAU_EPROCESS@@PEAIPEAPEAXPEA_K3@Z; CDDPDEV::OpenResource(uint,void *,uint,_EPROCESS *,uint *,void * *,unsigned __int64 *,void * *)
0x14001b26f  test    eax, eax
0x14001b271  jnz     short loc_14001B2C6
0x14001b273  lea     ecx, [rax+4]
0x14001b276  call    cs:__imp_WdLogSingleEntry0
0x14001b27d  nop     dword ptr [rax+rax+00h]
0x14001b282  mov     ebx, 438h
0x14001b287  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001b28d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001b294  nop     dword ptr [rax+rax+00h]
0x14001b299  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b2a0  mov     [rax+18h], rcx
0x14001b2a4  mov     ecx, cs:dword_14003E570
0x14001b2aa  mov     [rax+20h], rcx
0x14001b2ae  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001b2b6  mov     cs:WdLogGlobalForLineNumber, ebx
0x14001b2bc  mov     ebx, 0C0000001h
0x14001b2c1  jmp     loc_14001B423
0x14001b2c6  mov     [r15], eax
0x14001b2c9  mov     r12d, 0CDDBA5Eh
0x14001b2cf  jmp     loc_14001B3C0
0x14001b2d4  mov     edx, esi
0x14001b2d6  and     edx, 2
0x14001b2d9  jz      short loc_14001B2EB
0x14001b2db  and     sil, 80h
0x14001b2df  neg     sil
0x14001b2e2  sbb     ecx, ecx
0x14001b2e4  and     ecx, 6
0x14001b2e7  inc     ecx
0x14001b2e9  jmp     short loc_14001B2F0
0x14001b2eb  mov     ecx, 3
0x14001b2f0  xor     eax, eax
0x14001b2f2  mov     [rdi+24h], ecx
0x14001b2f5  mov     [rsp+88h+arg_0], 0
0x14001b300  lea     r14, [rdi+8]
0x14001b304  mov     r10, [r14]
0x14001b307  lea     r8d, [rax+15h]
0x14001b30b  test    edx, edx
0x14001b30d  jnz     short loc_14001B316
0x14001b30f  mov     r8d, [r10+408h]
0x14001b316  mov     r9d, [rdi+14h]
0x14001b31a  lea     rdx, [rdi+18h]
0x14001b31e  mov     [rsp+88h+var_30], al
0x14001b322  mov     [rsp+88h+var_38], rdx
0x14001b327  lea     rdx, [rsp+88h+arg_0]
0x14001b32f  mov     [rsp+88h+var_40], rax
0x14001b334  mov     [rsp+88h+var_48], rdx
0x14001b339  mov     rdx, rdi
0x14001b33c  mov     [rsp+88h+var_50], r15
0x14001b341  mov     dword ptr [rsp+88h+var_58], eax
0x14001b345  mov     dword ptr [rsp+88h+var_60], r8d
0x14001b34a  mov     r8d, [rdi+10h]
0x14001b34e  mov     dword ptr [rsp+88h+var_68], ecx
0x14001b352  mov     rcx, r10
0x14001b355  call    ?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z; CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)
0x14001b35a  movsxd  rbx, eax
0x14001b35d  test    eax, eax
0x14001b35f  jns     short loc_14001B38E
0x14001b361  mov     rdx, rbx
0x14001b364  mov     ecx, 4
0x14001b369  call    cs:__imp_WdLogSingleEntry1
0x14001b370  nop     dword ptr [rax+rax+00h]
0x14001b375  mov     edi, 46Dh
0x14001b37a  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b380  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001b387  nop     dword ptr [rax+rax+00h]
0x14001b38c  jmp     short loc_14001B404
0x14001b38e  mov     eax, [rdi+80h]
0x14001b394  test    al, 2
0x14001b396  jz      short loc_14001B3C0
0x14001b398  mov     eax, [rsp+88h+arg_0]
0x14001b39f  test    eax, eax
0x14001b3a1  jnz     short loc_14001B3B9
0x14001b3a3  lea     ecx, [rax+4]
0x14001b3a6  call    cs:__imp_WdLogSingleEntry0
0x14001b3ad  nop     dword ptr [rax+rax+00h]
0x14001b3b2  mov     edi, 475h
0x14001b3b7  jmp     short loc_14001B37A
0x14001b3b9  mov     [rdi+228h], rax
0x14001b3c0  lea     rcx, [rdi+0D0h]; this
0x14001b3c7  mov     rdx, rdi; struct CddBitmap *
0x14001b3ca  call    ?Create@CDDSYNCOBJECT@@QEAAJPEAVCddBitmap@@@Z; CDDSYNCOBJECT::Create(CddBitmap *)
0x14001b3cf  movsxd  rbx, eax
0x14001b3d2  test    eax, eax
0x14001b3d4  jns     short loc_14001B423
0x14001b3d6  mov     r8, [r14]
0x14001b3d9  mov     rdx, rbx
0x14001b3dc  mov     ecx, 2
0x14001b3e1  call    cs:__imp_WdLogSingleEntry2
0x14001b3e8  nop     dword ptr [rax+rax+00h]
0x14001b3ed  mov     edi, 484h
0x14001b3f2  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b3f8  call    cs:__imp_WdLogNewEntry5_WdError
0x14001b3ff  nop     dword ptr [rax+rax+00h]
0x14001b404  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b40b  mov     [rax+18h], rcx
0x14001b40f  mov     ecx, cs:dword_14003E570
0x14001b415  mov     [rax+20h], rcx
0x14001b419  mov     [rax+28h], r12
0x14001b41d  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b423  lea     r11, [rsp+88h+var_28]
0x14001b428  mov     eax, ebx
0x14001b42a  mov     rbx, [r11+38h]
0x14001b42e  mov     rbp, [r11+40h]
0x14001b432  mov     rsp, r11
0x14001b435  pop     r15
0x14001b437  pop     r14
0x14001b439  pop     r12
0x14001b43b  pop     rdi
0x14001b43c  pop     rsi
0x14001b43d  retn
```
