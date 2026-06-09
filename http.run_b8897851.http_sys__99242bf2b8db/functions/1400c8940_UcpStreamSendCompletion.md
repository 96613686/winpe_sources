# UcpStreamSendCompletion

- ea: `0x1400c8940`
- end: `0x1400c8b7f`
- name: `UcpStreamSendCompletion`
- size: `575`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400c8760`

## callees

- `0x14000a350`
- `0x1400bc67c`
- `0x1400c45fc`
- `0x1400c8940`
- `0x140165148`
- `0x1401652f4`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401d95e0`
- `0x1401d9c5c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400c898d`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c898d`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8afc`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8b1d`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8afc`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8b1d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c8ad7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c8ad7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c8acb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c8acb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c89d1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c89d1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c89b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c89b9`

## pseudocode

```c
__int64 __fastcall UcpStreamSendCompletion(_QWORD *P, __int64 a2, __int64 a3)
{
  IRP *v3; // r15
  unsigned int v4; // esi
  _QWORD *v6; // rbx
  __int64 v7; // r8
  _QWORD *v8; // rdi
  __int64 v9; // rax
  _QWORD *v10; // rcx
  IRP *v11; // rbp
  __int64 result; // rax
  IRP *v13; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v4 = a2;
  v13 = 0;
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_qqdP(P, a2, a3, P, P[1], a2, a3);
  if ( UxEnableIrqlEnforcement && KeGetCurrentIrql() )
    UlBugCheckEx(4u, 0, (ULONG_PTR)"minio\\http\\client\\core\\stream.c", 0x268u);
  v6 = (_QWORD *)P[1];
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(v6 + 17, 0);
  v6[29] -= *((unsigned int *)P + 1);
  v7 = v6[29];
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    WPP_SF_qqP(1053, 26, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids, v6, v7, v6[30]);
  v8 = P + 2;
  v9 = P[2];
  if ( *(_QWORD **)(v9 + 8) != P + 2 || (v10 = (_QWORD *)P[3], (_QWORD *)*v10 != v8) )
    __fastfail(3u);
  *v10 = v9;
  v11 = 0;
  *(_QWORD *)(v9 + 8) = v10;
  if ( *((_BYTE *)P + 32) )
  {
    UcpStreamMarkSendDisconnected(v6, &v13, v7);
    v3 = v13;
  }
  if ( v4 || v6[29] < v6[30] )
  {
    if ( v6[26] )
    {
      if ( (unsigned __int8)UcpStreamResetIrpCancellationRoutine(v6) )
      {
        v11 = (IRP *)v6[26];
        v6[26] = 0;
        if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
          WPP_SF_qq(1053, 27, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids, v6, v11);
      }
    }
  }
  ExReleasePushLockExclusiveEx(v6 + 17, 0);
  KeLeaveCriticalRegion();
  if ( v11 )
  {
    v11->IoStatus.Status = v4;
    if ( v4 )
      v11->IoStatus.Information = 0;
    IofCompleteRequest(v11, 0);
  }
  P[3] = P + 2;
  *v8 = v8;
  if ( v3 )
  {
    v3->IoStatus.Status = v4;
    IofCompleteRequest(v3, 0);
  }
  if ( v4 )
    UcAbortStream(v6, v4);
  result = UcStreamFreeSendTracker(P);
  if ( (BYTE3(xmmword_1401A2CA0) & 0x20) != 0 )
    return WPP_SF_(1053, 28, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids);
  return result;
}

```

## disassembly

```asm
0x1400c8940  mov     rax, rsp
0x1400c8943  mov     [rax+10h], rbx
0x1400c8947  mov     [rax+18h], rbp
0x1400c894b  push    rsi
0x1400c894c  push    rdi
0x1400c894d  push    r12
0x1400c894f  push    r14
0x1400c8951  push    r15
0x1400c8953  sub     rsp, 40h
0x1400c8957  xor     r15d, r15d
0x1400c895a  mov     esi, edx
0x1400c895c  mov     [rax+8], r15
0x1400c8960  mov     r14, rcx
0x1400c8963  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c896a  jz      short loc_1400C8984
0x1400c896c  mov     [rax-38h], r8
0x1400c8970  mov     r9, rcx
0x1400c8973  mov     [rax-40h], edx
0x1400c8976  mov     rax, [rcx+8]
0x1400c897a  mov     [rsp+68h+var_48], rax
0x1400c897f  call    WPP_SF_qqdP
0x1400c8984  cmp     cs:UxEnableIrqlEnforcement, r15b
0x1400c898b  jz      short loc_1400C89B5
0x1400c898d  call    cs:__imp_KeGetCurrentIrql
0x1400c8994  nop     dword ptr [rax+rax+00h]
0x1400c8999  test    al, al
0x1400c899b  jz      short loc_1400C89B5
0x1400c899d  xor     edx, edx; BugCheckParameter2
0x1400c899f  lea     r8, aMinioHttpClien_0; "minio\\http\\client\\core\\stream.c"
0x1400c89a6  mov     r9d, 268h; BugCheckParameter4
0x1400c89ac  lea     ecx, [rdx+4]; BugCheckParameter1
0x1400c89af  call    UlBugCheckEx
0x1400c89b5  mov     rbx, [r14+8]
0x1400c89b9  call    cs:__imp_KeEnterCriticalRegion
0x1400c89c0  nop     dword ptr [rax+rax+00h]
0x1400c89c5  lea     r12, [rbx+88h]
0x1400c89cc  xor     edx, edx
0x1400c89ce  mov     rcx, r12
0x1400c89d1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c89d8  nop     dword ptr [rax+rax+00h]
0x1400c89dd  mov     eax, [r14+4]
0x1400c89e1  sub     [rbx+0E8h], rax
0x1400c89e8  mov     r8, [rbx+0E8h]
0x1400c89ef  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c89f6  jz      short loc_1400C8A22
0x1400c89f8  mov     rax, [rbx+0F0h]
0x1400c89ff  mov     edx, 1Ah
0x1400c8a04  mov     [rsp+68h+var_40], rax
0x1400c8a09  mov     ecx, 41Dh
0x1400c8a0e  mov     [rsp+68h+var_48], r8
0x1400c8a13  mov     r9, rbx
0x1400c8a16  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c8a1d  call    WPP_SF_qqP
0x1400c8a22  lea     rdi, [r14+10h]
0x1400c8a26  mov     rax, [rdi]
0x1400c8a29  cmp     [rax+8], rdi
0x1400c8a2d  jnz     loc_1400C8B78
0x1400c8a33  mov     rcx, [rdi+8]
0x1400c8a37  cmp     [rcx], rdi
0x1400c8a3a  jnz     loc_1400C8B78
0x1400c8a40  mov     [rcx], rax
0x1400c8a43  xor     ebp, ebp
0x1400c8a45  mov     [rax+8], rcx
0x1400c8a49  cmp     [r14+20h], bpl
0x1400c8a4d  jz      short loc_1400C8A61
0x1400c8a4f  lea     rdx, [rsp+68h+arg_0]
0x1400c8a54  mov     rcx, rbx
0x1400c8a57  call    UcpStreamMarkSendDisconnected
0x1400c8a5c  mov     r15, [rsp+68h+arg_0]
0x1400c8a61  test    esi, esi
0x1400c8a63  jnz     short loc_1400C8A75
0x1400c8a65  mov     rax, [rbx+0F0h]
0x1400c8a6c  cmp     [rbx+0E8h], rax
0x1400c8a73  jnb     short loc_1400C8AC6
0x1400c8a75  mov     rdx, [rbx+0D0h]
0x1400c8a7c  test    rdx, rdx
0x1400c8a7f  jz      short loc_1400C8AC6
0x1400c8a81  mov     rcx, rbx; P
0x1400c8a84  call    UcpStreamResetIrpCancellationRoutine
0x1400c8a89  test    al, al
0x1400c8a8b  jz      short loc_1400C8AC6
0x1400c8a8d  mov     rbp, [rbx+0D0h]
0x1400c8a94  mov     qword ptr [rbx+0D0h], 0
0x1400c8a9f  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c8aa6  jz      short loc_1400C8AC6
0x1400c8aa8  mov     edx, 1Bh
0x1400c8aad  mov     [rsp+68h+var_48], rbp
0x1400c8ab2  mov     ecx, 41Dh
0x1400c8ab7  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c8abe  mov     r9, rbx
0x1400c8ac1  call    WPP_SF_qq
0x1400c8ac6  xor     edx, edx
0x1400c8ac8  mov     rcx, r12
0x1400c8acb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400c8ad2  nop     dword ptr [rax+rax+00h]
0x1400c8ad7  call    cs:__imp_KeLeaveCriticalRegion
0x1400c8ade  nop     dword ptr [rax+rax+00h]
0x1400c8ae3  test    rbp, rbp
0x1400c8ae6  jz      short loc_1400C8B08
0x1400c8ae8  mov     [rbp+30h], esi
0x1400c8aeb  test    esi, esi
0x1400c8aed  jz      short loc_1400C8AF7
0x1400c8aef  mov     qword ptr [rbp+38h], 0
0x1400c8af7  xor     edx, edx; PriorityBoost
0x1400c8af9  mov     rcx, rbp; Irp
0x1400c8afc  call    cs:__imp_IofCompleteRequest
0x1400c8b03  nop     dword ptr [rax+rax+00h]
0x1400c8b08  mov     [rdi+8], rdi
0x1400c8b0c  mov     [rdi], rdi
0x1400c8b0f  test    r15, r15
0x1400c8b12  jz      short loc_1400C8B29
0x1400c8b14  xor     edx, edx; PriorityBoost
0x1400c8b16  mov     [r15+30h], esi
0x1400c8b1a  mov     rcx, r15; Irp
0x1400c8b1d  call    cs:__imp_IofCompleteRequest
0x1400c8b24  nop     dword ptr [rax+rax+00h]
0x1400c8b29  test    esi, esi
0x1400c8b2b  jz      short loc_1400C8B37
0x1400c8b2d  mov     edx, esi
0x1400c8b2f  mov     rcx, rbx
0x1400c8b32  call    UcAbortStream
0x1400c8b37  mov     rcx, r14; P
0x1400c8b3a  call    UcStreamFreeSendTracker
0x1400c8b3f  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c8b46  jz      short loc_1400C8B5E
0x1400c8b48  mov     edx, 1Ch
0x1400c8b4d  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c8b54  mov     ecx, 41Dh
0x1400c8b59  call    WPP_SF_
0x1400c8b5e  lea     r11, [rsp+68h+var_28]
0x1400c8b63  mov     rbx, [r11+38h]
0x1400c8b67  mov     rbp, [r11+40h]
0x1400c8b6b  mov     rsp, r11
0x1400c8b6e  pop     r15
0x1400c8b70  pop     r14
0x1400c8b72  pop     r12
0x1400c8b74  pop     rdi
0x1400c8b75  pop     rsi
0x1400c8b76  retn
0x1400c8b78  mov     ecx, 3
0x1400c8b7d  int     29h; Win8: RtlFailFast(ecx)
```
