# CddBitmapSw::RecreateDeviceAllocations(void)

- ea: `0x140031d40`
- end: `0x140031ff4`
- name: `?RecreateDeviceAllocations@CddBitmapSw@@UEAAJXZ`
- size: `692`
- prototype: `__int64 __fastcall(CddBitmapSw *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14001b448`
- `0x14001b6e8`
- `0x140031840`
- `0x140031d40`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x140031de1`
- `ntoskrnl!PsGetCurrentProcess` at `0x140031de1`
- `watchdog!WdLogSingleEntry1` at `0x140031f56`
- `watchdog!WdLogSingleEntry1` at `0x140031f56`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140031d7f`
- `watchdog!WdLogNewEntry5_WdAssertion` at `0x140031d7f`
- `watchdog!WdLogSingleEntry0` at `0x140031d68`
- `watchdog!WdLogSingleEntry0` at `0x140031e43`
- `watchdog!WdLogSingleEntry0` at `0x140031eb0`
- `watchdog!WdLogSingleEntry0` at `0x140031fa8`
- `watchdog!WdLogSingleEntry0` at `0x140031d68`
- `watchdog!WdLogSingleEntry0` at `0x140031e43`
- `watchdog!WdLogSingleEntry0` at `0x140031eb0`
- `watchdog!WdLogSingleEntry0` at `0x140031fa8`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140031e5a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140031f6d`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140031e5a`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x140031f6d`

## pseudocode

```c
__int64 __fastcall CddBitmapSw::RecreateDeviceAllocations(CddBitmapSw *this)
{
  unsigned int *v1; // r14
  __int64 v3; // rdx
  __int64 v4; // rcx
  _QWORD *v5; // rax
  int v6; // esi
  void *v7; // rbp
  int v8; // esi
  int v9; // r15d
  CDDPDEV *v10; // rbx
  struct _EPROCESS *CurrentProcess; // rax
  unsigned int v12; // eax
  int v13; // ebx
  _QWORD *v14; // rax
  unsigned int v15; // ebx
  int v16; // ecx
  __int64 v17; // r10
  unsigned int v18; // r9d
  int Allocation; // eax
  int v20; // edi
  _QWORD *v21; // rax
  void *SysMemBits; // rax
  unsigned int v23; // ecx
  unsigned int v25; // [rsp+B0h] [rbp+8h] BYREF

  v1 = (unsigned int *)((char *)this + 40);
  if ( *((_DWORD *)this + 10) )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 516;
    v5 = (_QWORD *)WdLogNewEntry5_WdAssertion(v4, v3);
    v5[3] = gCddImageInfo;
    v5[4] = (unsigned int)dword_14003E570;
    v5[5] = 215857758;
    WdLogGlobalForLineNumber = 516;
  }
  v6 = *((_DWORD *)this + 32);
  if ( (v6 & 0x10) == 0 || (v7 = (void *)*((_QWORD *)this + 70)) == 0 )
  {
    v16 = (v6 & 0x80u) != 0 ? 8 : 6;
    *((_DWORD *)this + 9) = v16;
    v17 = *((_QWORD *)this + 1);
    v18 = 21;
    v25 = 0;
    if ( (v6 & 2) == 0 )
      v18 = *(_DWORD *)(v17 + 1032);
    Allocation = CDDPDEV::CreateAllocation(
                   v17,
                   (__int64)this,
                   *((_DWORD *)this + 4),
                   *((_DWORD *)this + 5),
                   v16,
                   v18,
                   0,
                   v1,
                   (__int64)&v25,
                   (unsigned __int64)this + 888,
                   (__int64)this + 24,
                   1);
    v15 = Allocation;
    if ( Allocation >= 0 )
    {
      if ( v25 )
      {
        *((_QWORD *)this + 70) = v25;
        goto LABEL_23;
      }
      WdLogSingleEntry0(4);
      v20 = 599;
    }
    else
    {
      WdLogSingleEntry1(4, Allocation);
      v20 = 593;
    }
    WdLogGlobalForLineNumber = v20;
    v21 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v21[3] = gCddImageInfo;
    v21[4] = (unsigned int)dword_14003E570;
    v21[5] = 215857758;
    WdLogGlobalForLineNumber = v20;
    return v15;
  }
  v8 = *((_DWORD *)this + 32) & 0x40;
  if ( v8 )
  {
    v9 = 0;
  }
  else
  {
    v9 = *((_DWORD *)this + 140);
    v7 = 0;
  }
  v10 = (CDDPDEV *)*((_QWORD *)this + 1);
  CurrentProcess = (struct _EPROCESS *)PsGetCurrentProcess();
  v12 = CDDPDEV::OpenResource(
          v10,
          v9,
          v7,
          *((_DWORD *)this + 132),
          CurrentProcess,
          (unsigned int *)this + 6,
          (void **)this + 111,
          (unsigned __int64 *)this + 114,
          (void **)(((unsigned __int64)this + 176) & -(__int64)(v8 != 0)));
  if ( !v12 )
  {
    WdLogSingleEntry0(4);
    v13 = 549;
LABEL_10:
    WdLogGlobalForLineNumber = v13;
    v14 = (_QWORD *)WdLogNewEntry5_WdEvent();
    v14[3] = gCddImageInfo;
    v14[4] = (unsigned int)dword_14003E570;
    v14[5] = 215857758;
    WdLogGlobalForLineNumber = v13;
    return (unsigned int)-1073741823;
  }
  if ( !*((_DWORD *)this + 6) || !*((_QWORD *)this + 111) )
  {
    WdLogSingleEntry0(4);
    v13 = 556;
    goto LABEL_10;
  }
  v15 = 0;
  *v1 = v12;
LABEL_23:
  SysMemBits = CddBitmapSw::GetSysMemBits(this);
  v23 = v15;
  *((_QWORD *)this + 116) = SysMemBits;
  if ( !SysMemBits )
    return (unsigned int)-1073741823;
  return v23;
}

```

## disassembly

```asm
0x140031d40  push    rbx
0x140031d42  push    rbp
0x140031d43  push    rsi
0x140031d44  push    rdi
0x140031d45  push    r12
0x140031d47  push    r13
0x140031d49  push    r14
0x140031d4b  push    r15
0x140031d4d  sub     rsp, 68h
0x140031d51  lea     r14, [rcx+28h]
0x140031d55  mov     rdi, rcx
0x140031d58  cmp     dword ptr [r14], 0
0x140031d5c  mov     ebp, 0CDDBA5Eh
0x140031d61  jz      short loc_140031DAA
0x140031d63  mov     ecx, 1
0x140031d68  call    cs:__imp_WdLogSingleEntry0
0x140031d6f  nop     dword ptr [rax+rax+00h]
0x140031d74  mov     ebx, 204h
0x140031d79  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031d7f  call    cs:__imp_WdLogNewEntry5_WdAssertion
0x140031d86  nop     dword ptr [rax+rax+00h]
0x140031d8b  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140031d92  mov     [rax+18h], rcx
0x140031d96  mov     ecx, cs:dword_14003E570
0x140031d9c  mov     [rax+20h], rcx
0x140031da0  mov     [rax+28h], rbp
0x140031da4  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031daa  mov     esi, [rdi+80h]
0x140031db0  test    sil, 10h
0x140031db4  jz      loc_140031EC8
0x140031dba  mov     rbp, [rdi+230h]
0x140031dc1  test    rbp, rbp
0x140031dc4  jz      loc_140031EC3
0x140031dca  and     esi, 40h
0x140031dcd  jz      short loc_140031DD4
0x140031dcf  xor     r15d, r15d
0x140031dd2  jmp     short loc_140031DDD
0x140031dd4  mov     r15d, [rdi+230h]
0x140031ddb  xor     ebp, ebp
0x140031ddd  mov     rbx, [rdi+8]
0x140031de1  call    cs:__imp_PsGetCurrentProcess
0x140031de8  nop     dword ptr [rax+rax+00h]
0x140031ded  lea     r9, [rdi+0B0h]
0x140031df4  neg     esi
0x140031df6  lea     r12, [rdi+378h]
0x140031dfd  mov     r8, rbp; void *
0x140031e00  sbb     r10, r10
0x140031e03  lea     r13, [rdi+18h]
0x140031e07  and     r10, r9
0x140031e0a  mov     edx, r15d; unsigned int
0x140031e0d  mov     [rsp+0A8h+var_68], r10; void **
0x140031e12  lea     r9, [rdi+390h]
0x140031e19  mov     [rsp+0A8h+var_70], r9; unsigned __int64 *
0x140031e1e  mov     rcx, rbx; this
0x140031e21  mov     r9d, [rdi+210h]; unsigned int
0x140031e28  mov     [rsp+0A8h+var_78], r12; void **
0x140031e2d  mov     [rsp+0A8h+var_80], r13; unsigned int *
0x140031e32  mov     [rsp+0A8h+var_88], rax; struct _EPROCESS *
0x140031e37  call    ?OpenResource@CDDPDEV@@QEAAIIPEAXIPEAU_EPROCESS@@PEAIPEAPEAXPEA_K3@Z; CDDPDEV::OpenResource(uint,void *,uint,_EPROCESS *,uint *,void * *,unsigned __int64 *,void * *)
0x140031e3c  test    eax, eax
0x140031e3e  jnz     short loc_140031E93
0x140031e40  lea     ecx, [rax+4]
0x140031e43  call    cs:__imp_WdLogSingleEntry0
0x140031e4a  nop     dword ptr [rax+rax+00h]
0x140031e4f  mov     ebx, 225h
0x140031e54  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031e5a  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140031e61  nop     dword ptr [rax+rax+00h]
0x140031e66  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140031e6d  mov     [rax+18h], rcx
0x140031e71  mov     ecx, cs:dword_14003E570
0x140031e77  mov     [rax+20h], rcx
0x140031e7b  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140031e83  mov     cs:WdLogGlobalForLineNumber, ebx
0x140031e89  mov     ebx, 0C0000001h
0x140031e8e  jmp     loc_140031FE0
0x140031e93  cmp     dword ptr [r13+0], 0
0x140031e98  jz      short loc_140031EAB
0x140031e9a  cmp     qword ptr [r12], 0
0x140031e9f  jz      short loc_140031EAB
0x140031ea1  xor     ebx, ebx
0x140031ea3  mov     [r14], eax
0x140031ea6  jmp     loc_140031FC2
0x140031eab  mov     ecx, 4
0x140031eb0  call    cs:__imp_WdLogSingleEntry0
0x140031eb7  nop     dword ptr [rax+rax+00h]
0x140031ebc  mov     ebx, 22Ch
0x140031ec1  jmp     short loc_140031E54
0x140031ec3  mov     ebp, 0CDDBA5Eh
0x140031ec8  mov     eax, esi
0x140031eca  and     al, 80h
0x140031ecc  neg     al
0x140031ece  sbb     ecx, ecx
0x140031ed0  xor     eax, eax
0x140031ed2  and     ecx, 2
0x140031ed5  add     ecx, 6
0x140031ed8  mov     [rdi+24h], ecx
0x140031edb  mov     r10, [rdi+8]
0x140031edf  lea     r9d, [rax+15h]
0x140031ee3  mov     [rsp+0A8h+arg_0], 0
0x140031eee  test    sil, 2
0x140031ef2  jnz     short loc_140031EFB
0x140031ef4  mov     r9d, [r10+408h]
0x140031efb  mov     [rsp+0A8h+var_50], 1
0x140031f00  lea     r8, [rdi+378h]
0x140031f07  lea     rdx, [rdi+18h]
0x140031f0b  mov     [rsp+0A8h+var_58], rdx
0x140031f10  lea     rdx, [rsp+0A8h+arg_0]
0x140031f18  mov     [rsp+0A8h+var_60], r8
0x140031f1d  mov     r8d, [rdi+10h]
0x140031f21  mov     [rsp+0A8h+var_68], rdx
0x140031f26  mov     rdx, rdi
0x140031f29  mov     [rsp+0A8h+var_70], r14
0x140031f2e  mov     dword ptr [rsp+0A8h+var_78], eax
0x140031f32  mov     dword ptr [rsp+0A8h+var_80], r9d
0x140031f37  mov     r9d, [rdi+14h]
0x140031f3b  mov     dword ptr [rsp+0A8h+var_88], ecx
0x140031f3f  mov     rcx, r10
0x140031f42  call    ?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z; CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)
0x140031f47  movsxd  rbx, eax
0x140031f4a  test    eax, eax
0x140031f4c  jns     short loc_140031F9A
0x140031f4e  mov     rdx, rbx
0x140031f51  mov     ecx, 4
0x140031f56  call    cs:__imp_WdLogSingleEntry1
0x140031f5d  nop     dword ptr [rax+rax+00h]
0x140031f62  mov     edi, 251h
0x140031f67  mov     cs:WdLogGlobalForLineNumber, edi
0x140031f6d  call    cs:__imp_WdLogNewEntry5_WdEvent
0x140031f74  nop     dword ptr [rax+rax+00h]
0x140031f79  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x140031f80  mov     [rax+18h], rcx
0x140031f84  mov     ecx, cs:dword_14003E570
0x140031f8a  mov     [rax+20h], rcx
0x140031f8e  mov     [rax+28h], rbp
0x140031f92  mov     cs:WdLogGlobalForLineNumber, edi
0x140031f98  jmp     short loc_140031FE0
0x140031f9a  mov     eax, [rsp+0A8h+arg_0]
0x140031fa1  test    eax, eax
0x140031fa3  jnz     short loc_140031FBB
0x140031fa5  lea     ecx, [rax+4]
0x140031fa8  call    cs:__imp_WdLogSingleEntry0
0x140031faf  nop     dword ptr [rax+rax+00h]
0x140031fb4  mov     edi, 257h
0x140031fb9  jmp     short loc_140031F67
0x140031fbb  mov     [rdi+230h], rax
0x140031fc2  mov     rcx, rdi; this
0x140031fc5  call    ?GetSysMemBits@CddBitmapSw@@IEAAPEAXXZ; CddBitmapSw::GetSysMemBits(void)
0x140031fca  mov     ecx, ebx
0x140031fcc  mov     [rdi+3A0h], rax
0x140031fd3  mov     ebx, 0C0000001h
0x140031fd8  test    rax, rax
0x140031fdb  cmovz   ecx, ebx
0x140031fde  mov     ebx, ecx
0x140031fe0  mov     eax, ebx
0x140031fe2  add     rsp, 68h
0x140031fe6  pop     r15
0x140031fe8  pop     r14
0x140031fea  pop     r13
0x140031fec  pop     r12
0x140031fee  pop     rdi
0x140031fef  pop     rsi
0x140031ff0  pop     rbp
0x140031ff1  pop     rbx
0x140031ff2  retn
```
