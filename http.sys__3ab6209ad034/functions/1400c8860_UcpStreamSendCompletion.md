# UcpStreamSendCompletion

- ea: `0x1400c8860`
- end: `0x1400c8a9f`
- name: `UcpStreamSendCompletion`
- size: `575`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400c8680`

## callees

- `0x14000a350`
- `0x1400bc59c`
- `0x1400c451c`
- `0x1400c8860`
- `0x140165258`
- `0x140165404`
- `0x1401c3008`
- `0x1401c3f58`
- `0x1401d95e0`
- `0x1401d9c5c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400c88ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400c88ad`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8a1c`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8a3d`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8a1c`
- `ntoskrnl!IofCompleteRequest` at `0x1400c8a3d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c89f7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400c89f7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c89eb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400c89eb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c88f1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400c88f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c88d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400c88d9`

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
0x1400c8860  mov     rax, rsp
0x1400c8863  mov     [rax+10h], rbx
0x1400c8867  mov     [rax+18h], rbp
0x1400c886b  push    rsi
0x1400c886c  push    rdi
0x1400c886d  push    r12
0x1400c886f  push    r14
0x1400c8871  push    r15
0x1400c8873  sub     rsp, 40h
0x1400c8877  xor     r15d, r15d
0x1400c887a  mov     esi, edx
0x1400c887c  mov     [rax+8], r15
0x1400c8880  mov     r14, rcx
0x1400c8883  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c888a  jz      short loc_1400C88A4
0x1400c888c  mov     [rax-38h], r8
0x1400c8890  mov     r9, rcx
0x1400c8893  mov     [rax-40h], edx
0x1400c8896  mov     rax, [rcx+8]
0x1400c889a  mov     [rsp+68h+var_48], rax
0x1400c889f  call    WPP_SF_qqdP
0x1400c88a4  cmp     cs:UxEnableIrqlEnforcement, r15b
0x1400c88ab  jz      short loc_1400C88D5
0x1400c88ad  call    cs:__imp_KeGetCurrentIrql
0x1400c88b4  nop     dword ptr [rax+rax+00h]
0x1400c88b9  test    al, al
0x1400c88bb  jz      short loc_1400C88D5
0x1400c88bd  xor     edx, edx; BugCheckParameter2
0x1400c88bf  lea     r8, aMinioHttpClien_0; "minio\\http\\client\\core\\stream.c"
0x1400c88c6  mov     r9d, 268h; BugCheckParameter4
0x1400c88cc  lea     ecx, [rdx+4]; BugCheckParameter1
0x1400c88cf  call    UlBugCheckEx
0x1400c88d5  mov     rbx, [r14+8]
0x1400c88d9  call    cs:__imp_KeEnterCriticalRegion
0x1400c88e0  nop     dword ptr [rax+rax+00h]
0x1400c88e5  lea     r12, [rbx+88h]
0x1400c88ec  xor     edx, edx
0x1400c88ee  mov     rcx, r12
0x1400c88f1  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400c88f8  nop     dword ptr [rax+rax+00h]
0x1400c88fd  mov     eax, [r14+4]
0x1400c8901  sub     [rbx+0E8h], rax
0x1400c8908  mov     r8, [rbx+0E8h]
0x1400c890f  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c8916  jz      short loc_1400C8942
0x1400c8918  mov     rax, [rbx+0F0h]
0x1400c891f  mov     edx, 1Ah
0x1400c8924  mov     [rsp+68h+var_40], rax
0x1400c8929  mov     ecx, 41Dh
0x1400c892e  mov     [rsp+68h+var_48], r8
0x1400c8933  mov     r9, rbx
0x1400c8936  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c893d  call    WPP_SF_qqP
0x1400c8942  lea     rdi, [r14+10h]
0x1400c8946  mov     rax, [rdi]
0x1400c8949  cmp     [rax+8], rdi
0x1400c894d  jnz     loc_1400C8A98
0x1400c8953  mov     rcx, [rdi+8]
0x1400c8957  cmp     [rcx], rdi
0x1400c895a  jnz     loc_1400C8A98
0x1400c8960  mov     [rcx], rax
0x1400c8963  xor     ebp, ebp
0x1400c8965  mov     [rax+8], rcx
0x1400c8969  cmp     [r14+20h], bpl
0x1400c896d  jz      short loc_1400C8981
0x1400c896f  lea     rdx, [rsp+68h+arg_0]
0x1400c8974  mov     rcx, rbx
0x1400c8977  call    UcpStreamMarkSendDisconnected
0x1400c897c  mov     r15, [rsp+68h+arg_0]
0x1400c8981  test    esi, esi
0x1400c8983  jnz     short loc_1400C8995
0x1400c8985  mov     rax, [rbx+0F0h]
0x1400c898c  cmp     [rbx+0E8h], rax
0x1400c8993  jnb     short loc_1400C89E6
0x1400c8995  mov     rdx, [rbx+0D0h]
0x1400c899c  test    rdx, rdx
0x1400c899f  jz      short loc_1400C89E6
0x1400c89a1  mov     rcx, rbx; P
0x1400c89a4  call    UcpStreamResetIrpCancellationRoutine
0x1400c89a9  test    al, al
0x1400c89ab  jz      short loc_1400C89E6
0x1400c89ad  mov     rbp, [rbx+0D0h]
0x1400c89b4  mov     qword ptr [rbx+0D0h], 0
0x1400c89bf  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c89c6  jz      short loc_1400C89E6
0x1400c89c8  mov     edx, 1Bh
0x1400c89cd  mov     [rsp+68h+var_48], rbp
0x1400c89d2  mov     ecx, 41Dh
0x1400c89d7  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c89de  mov     r9, rbx
0x1400c89e1  call    WPP_SF_qq
0x1400c89e6  xor     edx, edx
0x1400c89e8  mov     rcx, r12
0x1400c89eb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400c89f2  nop     dword ptr [rax+rax+00h]
0x1400c89f7  call    cs:__imp_KeLeaveCriticalRegion
0x1400c89fe  nop     dword ptr [rax+rax+00h]
0x1400c8a03  test    rbp, rbp
0x1400c8a06  jz      short loc_1400C8A28
0x1400c8a08  mov     [rbp+30h], esi
0x1400c8a0b  test    esi, esi
0x1400c8a0d  jz      short loc_1400C8A17
0x1400c8a0f  mov     qword ptr [rbp+38h], 0
0x1400c8a17  xor     edx, edx; PriorityBoost
0x1400c8a19  mov     rcx, rbp; Irp
0x1400c8a1c  call    cs:__imp_IofCompleteRequest
0x1400c8a23  nop     dword ptr [rax+rax+00h]
0x1400c8a28  mov     [rdi+8], rdi
0x1400c8a2c  mov     [rdi], rdi
0x1400c8a2f  test    r15, r15
0x1400c8a32  jz      short loc_1400C8A49
0x1400c8a34  xor     edx, edx; PriorityBoost
0x1400c8a36  mov     [r15+30h], esi
0x1400c8a3a  mov     rcx, r15; Irp
0x1400c8a3d  call    cs:__imp_IofCompleteRequest
0x1400c8a44  nop     dword ptr [rax+rax+00h]
0x1400c8a49  test    esi, esi
0x1400c8a4b  jz      short loc_1400C8A57
0x1400c8a4d  mov     edx, esi
0x1400c8a4f  mov     rcx, rbx
0x1400c8a52  call    UcAbortStream
0x1400c8a57  mov     rcx, r14; P
0x1400c8a5a  call    UcStreamFreeSendTracker
0x1400c8a5f  test    byte ptr cs:xmmword_1401A2CA0+3, 20h
0x1400c8a66  jz      short loc_1400C8A7E
0x1400c8a68  mov     edx, 1Ch
0x1400c8a6d  lea     r8, WPP_56575c1994d736914fbc76cb9eeef0ce_Traceguids
0x1400c8a74  mov     ecx, 41Dh
0x1400c8a79  call    WPP_SF_
0x1400c8a7e  lea     r11, [rsp+68h+var_28]
0x1400c8a83  mov     rbx, [r11+38h]
0x1400c8a87  mov     rbp, [r11+40h]
0x1400c8a8b  mov     rsp, r11
0x1400c8a8e  pop     r15
0x1400c8a90  pop     r14
0x1400c8a92  pop     r12
0x1400c8a94  pop     rdi
0x1400c8a95  pop     rsi
0x1400c8a96  retn
0x1400c8a98  mov     ecx, 3
0x1400c8a9d  int     29h; Win8: RtlFailFast(ecx)
```
