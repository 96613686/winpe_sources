# MRxDAVDeallocateForFobx

- ea: `0x140023950`
- end: `0x140023ba4`
- name: `MRxDAVDeallocateForFobx`
- size: `596`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140001680`
- `0x1400017e4`
- `0x140002ac4`
- `0x140023950`
- `0x1400269d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x1400239cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023a10`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023a7f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023afc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023b69`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400239cc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023a10`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023a7f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023afc`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140023b69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023b3c`
- `rdbss!RxCreateRxContext` at `0x140023a45`
- `rdbss!RxCreateRxContext` at `0x140023a45`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140023b2b`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x140023b2b`

## pseudocode

```c
__int64 __fastcall MRxDAVDeallocateForFobx(PRX_CONTEXT RxContext, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  __int64 *v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rax
  char v9; // r15
  struct _RDBSS_DEVICE_OBJECT *v10; // r12
  __int64 v11; // rbx
  __int64 v12; // rdi
  unsigned int CurrentThreadId; // eax
  __int64 v14; // rbx
  __int64 v15; // rdi
  HANDLE v16; // rax
  PRX_CONTEXT v17; // rax
  __int64 v18; // rbx
  HANDLE v19; // rax
  __int64 v20; // rbx
  HANDLE v21; // rax
  __int64 v22; // rbx
  HANDLE v23; // rax

  v3 = 0;
  if ( a2 )
  {
    v6 = *(__int64 **)(a2 + 56);
    if ( v6 )
    {
      if ( *v6 )
      {
        v7 = *(_QWORD *)(a2 + 32);
        v8 = *(_QWORD *)(*(_QWORD *)(v7 + 32) + 120LL);
        if ( v8 )
        {
          v9 = 0;
          v10 = *(struct _RDBSS_DEVICE_OBJECT **)(*(_QWORD *)(v8 + 32) + 48LL);
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v11 = *(_QWORD *)(v7 + 80);
              v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              CurrentThreadId = (unsigned int)PsGetCurrentThreadId();
              WPP_SF_qZ(v12, 10, (unsigned int)WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, CurrentThreadId, v11);
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
            {
              v14 = *v6;
              v15 = *((_QWORD *)WPP_GLOBAL_Control + 3);
              v16 = PsGetCurrentThreadId();
              WPP_SF_qq(v15, 11, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v16, v14);
            }
          }
          if ( !RxContext )
          {
            v17 = RxCreateRxContext(0, v10, 0);
            RxContext = v17;
            if ( !v17 )
            {
              v3 = -1073741670;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
              {
                v18 = *((_QWORD *)WPP_GLOBAL_Control + 3);
                v19 = PsGetCurrentThreadId();
                WPP_SF_qD(v18, 12, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v19, -1073741670);
              }
              goto LABEL_23;
            }
            v9 = 1;
            v17->MRxContext[3] = (PVOID)a2;
          }
          v3 = UMRxAsyncEngOuterWrapper(
                 (__int64)RxContext,
                 a2,
                 a3,
                 1u,
                 (__int64 (__fastcall *)(__int64, __int64))MRxDAVDeallocateForFobxContinuation,
                 (__int64)"MRxDAVDeallocateForFobx");
          if ( v3
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
          {
            v20 = *((_QWORD *)WPP_GLOBAL_Control + 3);
            v21 = PsGetCurrentThreadId();
            WPP_SF_qD(v20, 13, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v21, v3);
          }
          if ( v9 )
            RxDereferenceAndDeleteRxContext_Real(RxContext);
        }
      }
LABEL_23:
      ExFreePoolWithTag(v6, 0);
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
  {
    v22 = *((_QWORD *)WPP_GLOBAL_Control + 3);
    v23 = PsGetCurrentThreadId();
    WPP_SF_qD(v22, 14, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids, v23, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x140023950  push    rbx
0x140023952  push    rbp
0x140023953  push    rsi
0x140023954  push    rdi
0x140023955  push    r12
0x140023957  push    r13
0x140023959  push    r14
0x14002395b  push    r15
0x14002395d  sub     rsp, 38h
0x140023961  xor     edi, edi
0x140023963  lea     r13, WPP_GLOBAL_Control
0x14002396a  mov     rbp, rdx
0x14002396d  mov     rsi, rcx
0x140023970  test    rdx, rdx
0x140023973  jz      loc_140023B50
0x140023979  mov     r14, [rdx+38h]
0x14002397d  test    r14, r14
0x140023980  jz      loc_140023B50
0x140023986  cmp     [r14], rdi
0x140023989  jz      loc_140023B37
0x14002398f  mov     rbx, [rdx+20h]
0x140023993  mov     rax, [rbx+20h]
0x140023997  mov     rax, [rax+78h]
0x14002399b  test    rax, rax
0x14002399e  jz      loc_140023B37
0x1400239a4  mov     rax, [rax+20h]
0x1400239a8  xor     r15b, r15b
0x1400239ab  mov     r12, [rax+30h]
0x1400239af  mov     rdi, cs:WPP_GLOBAL_Control
0x1400239b6  cmp     rdi, r13
0x1400239b9  jz      short loc_140023A38
0x1400239bb  test    dword ptr [rdi+2Ch], 4000h
0x1400239c2  jz      short loc_1400239F4
0x1400239c4  mov     rbx, [rbx+50h]
0x1400239c8  mov     rdi, [rdi+18h]
0x1400239cc  call    cs:__imp_PsGetCurrentThreadId
0x1400239d3  nop     dword ptr [rax+rax+00h]
0x1400239d8  mov     edx, 0Ah
0x1400239dd  mov     [rsp+78h+var_58], rbx
0x1400239e2  mov     r9, rax
0x1400239e5  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x1400239ec  mov     rcx, rdi
0x1400239ef  call    WPP_SF_qZ
0x1400239f4  mov     rdi, cs:WPP_GLOBAL_Control
0x1400239fb  cmp     rdi, r13
0x1400239fe  jz      short loc_140023A38
0x140023a00  test    dword ptr [rdi+2Ch], 4000h
0x140023a07  jz      short loc_140023A38
0x140023a09  mov     rbx, [r14]
0x140023a0c  mov     rdi, [rdi+18h]
0x140023a10  call    cs:__imp_PsGetCurrentThreadId
0x140023a17  nop     dword ptr [rax+rax+00h]
0x140023a1c  mov     edx, 0Bh
0x140023a21  mov     [rsp+78h+var_58], rbx
0x140023a26  mov     r9, rax
0x140023a29  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023a30  mov     rcx, rdi
0x140023a33  call    WPP_SF_qq
0x140023a38  test    rsi, rsi
0x140023a3b  jnz     short loc_140023AB7
0x140023a3d  xor     r8d, r8d; InitialContextFlags
0x140023a40  mov     rdx, r12; RxDeviceObject
0x140023a43  xor     ecx, ecx; Irp
0x140023a45  call    cs:__imp_RxCreateRxContext
0x140023a4c  nop     dword ptr [rax+rax+00h]
0x140023a51  mov     rsi, rax
0x140023a54  test    rax, rax
0x140023a57  jnz     short loc_140023AAD
0x140023a59  mov     edi, 0C000009Ah
0x140023a5e  mov     rbx, cs:WPP_GLOBAL_Control
0x140023a65  cmp     rbx, r13
0x140023a68  jz      loc_140023B37
0x140023a6e  test    dword ptr [rbx+2Ch], 2000h
0x140023a75  jz      loc_140023B37
0x140023a7b  mov     rbx, [rbx+18h]
0x140023a7f  call    cs:__imp_PsGetCurrentThreadId
0x140023a86  nop     dword ptr [rax+rax+00h]
0x140023a8b  lea     edx, [rsi+0Ch]
0x140023a8e  mov     dword ptr [rsp+78h+var_58], 0C000009Ah
0x140023a96  mov     r9, rax
0x140023a99  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023aa0  mov     rcx, rbx
0x140023aa3  call    WPP_SF_qD
0x140023aa8  jmp     loc_140023B37
0x140023aad  mov     r15b, 1
0x140023ab0  mov     [rax+0D8h], rbp
0x140023ab7  lea     rax, aMrxdavdealloca; "MRxDAVDeallocateForFobx"
0x140023abe  mov     r9d, 1
0x140023ac4  mov     [rsp+78h+var_50], rax
0x140023ac9  mov     rcx, rsi
0x140023acc  lea     rax, MRxDAVDeallocateForFobxContinuation
0x140023ad3  mov     [rsp+78h+var_58], rax
0x140023ad8  call    UMRxAsyncEngOuterWrapper
0x140023add  mov     edi, eax
0x140023adf  test    eax, eax
0x140023ae1  jz      short loc_140023B23
0x140023ae3  mov     rbx, cs:WPP_GLOBAL_Control
0x140023aea  cmp     rbx, r13
0x140023aed  jz      short loc_140023B23
0x140023aef  test    dword ptr [rbx+2Ch], 2000h
0x140023af6  jz      short loc_140023B23
0x140023af8  mov     rbx, [rbx+18h]
0x140023afc  call    cs:__imp_PsGetCurrentThreadId
0x140023b03  nop     dword ptr [rax+rax+00h]
0x140023b08  mov     edx, 0Dh
0x140023b0d  mov     dword ptr [rsp+78h+var_58], edi
0x140023b11  mov     r9, rax
0x140023b14  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023b1b  mov     rcx, rbx
0x140023b1e  call    WPP_SF_qD
0x140023b23  test    r15b, r15b
0x140023b26  jz      short loc_140023B37
0x140023b28  mov     rcx, rsi; RxContext
0x140023b2b  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140023b32  nop     dword ptr [rax+rax+00h]
0x140023b37  xor     edx, edx; Tag
0x140023b39  mov     rcx, r14; P
0x140023b3c  call    cs:__imp_ExFreePoolWithTag
0x140023b43  nop     dword ptr [rax+rax+00h]
0x140023b48  mov     qword ptr [rbp+38h], 0
0x140023b50  mov     rbx, cs:WPP_GLOBAL_Control
0x140023b57  cmp     rbx, r13
0x140023b5a  jz      short loc_140023B90
0x140023b5c  test    dword ptr [rbx+2Ch], 4000h
0x140023b63  jz      short loc_140023B90
0x140023b65  mov     rbx, [rbx+18h]
0x140023b69  call    cs:__imp_PsGetCurrentThreadId
0x140023b70  nop     dword ptr [rax+rax+00h]
0x140023b75  mov     edx, 0Eh
0x140023b7a  mov     dword ptr [rsp+78h+var_58], edi
0x140023b7e  mov     r9, rax
0x140023b81  lea     r8, WPP_5c72cb21a1353022f2b3482a62d37e3d_Traceguids
0x140023b88  mov     rcx, rbx
0x140023b8b  call    WPP_SF_qD
0x140023b90  mov     eax, edi
0x140023b92  add     rsp, 38h
0x140023b96  pop     r15
0x140023b98  pop     r14
0x140023b9a  pop     r13
0x140023b9c  pop     r12
0x140023b9e  pop     rdi
0x140023b9f  pop     rsi
0x140023ba0  pop     rbp
0x140023ba1  pop     rbx
0x140023ba2  retn
```
