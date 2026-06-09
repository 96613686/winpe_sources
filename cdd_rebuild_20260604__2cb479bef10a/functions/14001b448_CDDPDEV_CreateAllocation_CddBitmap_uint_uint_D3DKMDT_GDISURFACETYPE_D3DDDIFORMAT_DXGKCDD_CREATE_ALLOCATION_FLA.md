# CDDPDEV::CreateAllocation(CddBitmap *,uint,uint,_D3DKMDT_GDISURFACETYPE,_D3DDDIFORMAT,_DXGKCDD_CREATE_ALLOCATION_FLAGS,uint *,uint *,void * *,uint *,uchar)

- ea: `0x14001b448`
- end: `0x14001b6e0`
- name: `?CreateAllocation@CDDPDEV@@QEAAJPEAVCddBitmap@@IIW4_D3DKMDT_GDISURFACETYPE@@W4_D3DDDIFORMAT@@U_DXGKCDD_CREATE_ALLOCATION_FLAGS@@PEAI4PEAPEAX4E@Z`
- size: `664`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x14001b170`
- `0x14002d4b4`
- `0x140030434`
- `0x140030a74`
- `0x140031d40`

## callees

- `0x1400023c0`
- `0x140002420`
- `0x140015764`
- `0x14001b448`
- `0x140027b1c`
- `0x1400371f0`
- `0x1400372d0`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x14001b4d5`
- `ntoskrnl!KeStackAttachProcess` at `0x14001b4d5`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b6b1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14001b6b1`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b4b4`
- `ntoskrnl!PsGetCurrentProcess` at `0x14001b4b4`
- `watchdog!WdLogSingleEntry1` at `0x14001b5b5`
- `watchdog!WdLogSingleEntry1` at `0x14001b661`
- `watchdog!WdLogSingleEntry1` at `0x14001b5b5`
- `watchdog!WdLogSingleEntry1` at `0x14001b661`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001b678`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001b678`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b5cc`
- `watchdog!WdLogNewEntry5_WdEvent` at `0x14001b5cc`

## pseudocode

```c
__int64 __fastcall CDDPDEV::CreateAllocation(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int *a8,
        __int64 a9,
        unsigned __int64 a10,
        __int64 a11,
        char a12)
{
  __int64 v12; // rbx
  struct _KPROCESS *v17; // rbx
  int v18; // ecx
  __int128 *v19; // r8
  int v20; // eax
  _QWORD *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  unsigned __int64 v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+88h] [rbp-78h]
  __int128 v28; // [rsp+90h] [rbp-70h] BYREF
  __int128 v29; // [rsp+A0h] [rbp-60h]
  __int128 v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  struct _KAPC_STATE ApcState; // [rsp+C8h] [rbp-38h] BYREF
  char v33; // [rsp+F8h] [rbp-8h]

  LODWORD(v12) = 0;
  v26 = a10;
  v27 = a11;
  if ( *(_DWORD *)(a1 + 2520) )
  {
    v17 = *(struct _KPROCESS **)(a1 + 752);
    v33 = 0;
    if ( (struct _KPROCESS *)PsGetCurrentProcess() != v17 && v17 )
    {
      KeStackAttachProcess(v17, &ApcState);
      v33 = 1;
    }
    v31 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    if ( a5 == 1 || (unsigned int)(a5 - 6) <= 2 )
    {
      v18 = 56;
      *(_QWORD *)&v28 = 0x500000038LL;
      v19 = &v28;
      *((_QWORD *)&v28 + 1) = __PAIR64__(a4, a3);
      *(_QWORD *)&v29 = 0x100000057LL;
      DWORD2(v29) = 0;
    }
    else
    {
      v18 = 0;
      v19 = 0;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, int, __int64 (__fastcall *)(CddBitmapBase *__hidden), __int64, __int128 *, int, unsigned int *, __int64, unsigned __int64, __int64))(a1 + 208))(
            *(unsigned int *)(a1 + 2520),
            a6,
            a7,
            a3,
            a4,
            a5,
            CddBitmapBase::SubmitPresentHistory,
            a2,
            v19,
            v18,
            a8,
            a9,
            v26,
            v27);
    LODWORD(v12) = v20;
    if ( v20 >= 0 )
    {
      if ( *(_BYTE *)(a1 + 12716) )
      {
        if ( a12 )
        {
          v26 = 0;
          CDDPDEV::AcquireResidencyLock((CDDPDEV *)a1);
          v12 = (int)CDDPDEV::EnsureResident((CDDPDEV *)a1, *a8, 0, 1u, &v26);
          CDDPDEV::ReleaseResidencyLock((CDDPDEV *)a1);
          if ( (int)v12 < 0 )
          {
            WdLogSingleEntry1(2, v12);
            WdLogGlobalForLineNumber = 547;
            v24 = (_QWORD *)WdLogNewEntry5_WdError(v23, v22);
            v24[3] = gCddImageInfo;
            v24[4] = (unsigned int)dword_14003E570;
            v24[5] = 215857758;
            WdLogGlobalForLineNumber = 547;
          }
        }
      }
    }
    else
    {
      WdLogSingleEntry1(4, v20);
      WdLogGlobalForLineNumber = 527;
      v21 = (_QWORD *)WdLogNewEntry5_WdEvent();
      v21[3] = gCddImageInfo;
      v21[4] = (unsigned int)dword_14003E570;
      v21[5] = 215857758;
      WdLogGlobalForLineNumber = 527;
      CDDPDEV::CheckDeviceRemoved((CDDPDEV *)a1, v12);
    }
    if ( v33 )
      KeUnstackDetachProcess(&ApcState);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14001b448  push    rbp
0x14001b44a  push    rbx
0x14001b44b  push    rsi
0x14001b44c  push    rdi
0x14001b44d  push    r12
0x14001b44f  push    r13
0x14001b451  push    r14
0x14001b453  push    r15
0x14001b455  lea     rbp, [rsp-18h]
0x14001b45a  sub     rsp, 118h
0x14001b461  mov     rax, cs:__security_cookie
0x14001b468  xor     rax, rsp
0x14001b46b  mov     [rbp+50h+var_50], rax
0x14001b46f  mov     rax, [rbp+50h+arg_48]
0x14001b476  xor     ebx, ebx
0x14001b478  mov     r14d, r9d
0x14001b47b  mov     r15, [rbp+50h+arg_38]
0x14001b482  mov     esi, r8d
0x14001b485  mov     r13, [rbp+50h+arg_40]
0x14001b48c  mov     r12, rdx
0x14001b48f  mov     [rbp+50h+var_D0], rax
0x14001b493  mov     rdi, rcx
0x14001b496  mov     rax, [rbp+50h+arg_50]
0x14001b49d  mov     [rbp+50h+var_C8], rax
0x14001b4a1  cmp     [rcx+9D8h], ebx
0x14001b4a7  jz      loc_14001B6BD
0x14001b4ad  mov     rbx, [rcx+2F0h]
0x14001b4b4  call    cs:__imp_PsGetCurrentProcess
0x14001b4bb  nop     dword ptr [rax+rax+00h]
0x14001b4c0  mov     [rbp+50h+var_58], 0
0x14001b4c4  cmp     rax, rbx
0x14001b4c7  jz      short loc_14001B4E5
0x14001b4c9  test    rbx, rbx
0x14001b4cc  jz      short loc_14001B4E5
0x14001b4ce  lea     rdx, [rbp+50h+ApcState]; ApcState
0x14001b4d2  mov     rcx, rbx; PROCESS
0x14001b4d5  call    cs:__imp_KeStackAttachProcess
0x14001b4dc  nop     dword ptr [rax+rax+00h]
0x14001b4e1  mov     [rbp+50h+var_58], 1
0x14001b4e5  mov     edx, [rbp+50h+arg_20]
0x14001b4eb  xorps   xmm0, xmm0
0x14001b4ee  xor     eax, eax
0x14001b4f0  mov     [rbp+50h+var_90], rax
0x14001b4f4  movups  [rbp+50h+var_C0], xmm0
0x14001b4f8  movups  [rbp+50h+var_B0], xmm0
0x14001b4fc  movups  [rbp+50h+var_A0], xmm0
0x14001b500  cmp     edx, 1
0x14001b503  jz      short loc_14001B514
0x14001b505  lea     eax, [rdx-6]
0x14001b508  cmp     eax, 2
0x14001b50b  jbe     short loc_14001B514
0x14001b50d  xor     ecx, ecx
0x14001b50f  xor     r8d, r8d
0x14001b512  jmp     short loc_14001B543
0x14001b514  mov     ecx, 38h ; '8'
0x14001b519  mov     dword ptr [rbp+50h+var_C0+4], 5
0x14001b520  mov     dword ptr [rbp+50h+var_C0], ecx
0x14001b523  lea     r8, [rbp+50h+var_C0]
0x14001b527  mov     dword ptr [rbp+50h+var_C0+8], esi
0x14001b52a  mov     dword ptr [rbp+50h+var_C0+0Ch], r14d
0x14001b52e  mov     dword ptr [rbp+50h+var_B0+4], 1
0x14001b535  mov     dword ptr [rbp+50h+var_B0], 57h ; 'W'
0x14001b53c  mov     dword ptr [rbp+50h+var_B0+8], 0
0x14001b543  mov     r9, [rbp+50h+var_C8]
0x14001b547  mov     rax, [rdi+0D0h]
0x14001b54e  mov     [rsp+150h+var_E8], r9
0x14001b553  mov     r9, [rbp+50h+var_D0]
0x14001b557  mov     [rsp+150h+var_F0], r9
0x14001b55c  mov     r9d, esi
0x14001b55f  mov     [rsp+150h+var_F8], r13
0x14001b564  mov     [rsp+150h+var_100], r15
0x14001b569  mov     [rsp+150h+var_108], ecx
0x14001b56d  lea     rcx, ?SubmitPresentHistory@CddBitmapBase@@UEAAJXZ; CddBitmapBase::SubmitPresentHistory(void)
0x14001b574  mov     [rsp+150h+var_110], r8
0x14001b579  mov     r8d, [rbp+50h+arg_30]
0x14001b580  mov     [rsp+150h+var_118], r12
0x14001b585  mov     [rsp+150h+var_120], rcx
0x14001b58a  mov     ecx, [rdi+9D8h]
0x14001b590  mov     [rsp+150h+var_128], edx
0x14001b594  mov     edx, [rbp+50h+arg_28]
0x14001b59a  mov     dword ptr [rsp+150h+var_130], r14d
0x14001b59f  call    _guard_dispatch_icall
0x14001b5a4  xor     r14d, r14d
0x14001b5a7  movsxd  rbx, eax
0x14001b5aa  test    eax, eax
0x14001b5ac  jns     short loc_14001B60A
0x14001b5ae  mov     rdx, rbx
0x14001b5b1  lea     ecx, [r14+4]
0x14001b5b5  call    cs:__imp_WdLogSingleEntry1
0x14001b5bc  nop     dword ptr [rax+rax+00h]
0x14001b5c1  mov     esi, 20Fh
0x14001b5c6  mov     cs:WdLogGlobalForLineNumber, esi
0x14001b5cc  call    cs:__imp_WdLogNewEntry5_WdEvent
0x14001b5d3  nop     dword ptr [rax+rax+00h]
0x14001b5d8  mov     rdx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b5df  mov     rcx, rdi; this
0x14001b5e2  mov     [rax+18h], rdx
0x14001b5e6  mov     edx, cs:dword_14003E570
0x14001b5ec  mov     [rax+20h], rdx
0x14001b5f0  mov     edx, ebx; int
0x14001b5f2  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001b5fa  mov     cs:WdLogGlobalForLineNumber, esi
0x14001b600  call    ?CheckDeviceRemoved@CDDPDEV@@QEAAXJ@Z; CDDPDEV::CheckDeviceRemoved(long)
0x14001b605  jmp     loc_14001B6A7
0x14001b60a  cmp     [rdi+31ACh], r14b
0x14001b611  jz      loc_14001B6A7
0x14001b617  cmp     [rbp+50h+arg_58], r14b
0x14001b61e  jz      loc_14001B6A7
0x14001b624  mov     rcx, rdi; this
0x14001b627  mov     [rbp+50h+var_D0], r14
0x14001b62b  call    ?AcquireResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::AcquireResidencyLock(void)
0x14001b630  mov     edx, [r15]; unsigned int
0x14001b633  lea     rax, [rbp+50h+var_D0]
0x14001b637  mov     r9b, 1; unsigned __int8
0x14001b63a  mov     [rsp+150h+var_130], rax; unsigned __int64 *
0x14001b63f  xor     r8d, r8d; struct CHwCommandBuffer *
0x14001b642  mov     rcx, rdi; this
0x14001b645  call    ?EnsureResident@CDDPDEV@@QEAAJIPEAVCHwCommandBuffer@@EPEA_K@Z; CDDPDEV::EnsureResident(uint,CHwCommandBuffer *,uchar,unsigned __int64 *)
0x14001b64a  mov     rcx, rdi; this
0x14001b64d  movsxd  rbx, eax
0x14001b650  call    ?ReleaseResidencyLock@CDDPDEV@@QEAAXXZ; CDDPDEV::ReleaseResidencyLock(void)
0x14001b655  test    ebx, ebx
0x14001b657  jns     short loc_14001B6A7
0x14001b659  mov     rdx, rbx
0x14001b65c  mov     ecx, 2
0x14001b661  call    cs:__imp_WdLogSingleEntry1
0x14001b668  nop     dword ptr [rax+rax+00h]
0x14001b66d  mov     edi, 223h
0x14001b672  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b678  call    cs:__imp_WdLogNewEntry5_WdError
0x14001b67f  nop     dword ptr [rax+rax+00h]
0x14001b684  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001b68b  mov     [rax+18h], rcx
0x14001b68f  mov     ecx, cs:dword_14003E570
0x14001b695  mov     [rax+20h], rcx
0x14001b699  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001b6a1  mov     cs:WdLogGlobalForLineNumber, edi
0x14001b6a7  cmp     [rbp+50h+var_58], r14b
0x14001b6ab  jz      short loc_14001B6BD
0x14001b6ad  lea     rcx, [rbp+50h+ApcState]; ApcState
0x14001b6b1  call    cs:__imp_KeUnstackDetachProcess
0x14001b6b8  nop     dword ptr [rax+rax+00h]
0x14001b6bd  mov     eax, ebx
0x14001b6bf  mov     rcx, [rbp+50h+var_50]
0x14001b6c3  xor     rcx, rsp; StackCookie
0x14001b6c6  call    __security_check_cookie
0x14001b6cb  add     rsp, 118h
0x14001b6d2  pop     r15
0x14001b6d4  pop     r14
0x14001b6d6  pop     r13
0x14001b6d8  pop     r12
0x14001b6da  pop     rdi
0x14001b6db  pop     rsi
0x14001b6dc  pop     rbx
0x14001b6dd  pop     rbp
0x14001b6de  retn
```
