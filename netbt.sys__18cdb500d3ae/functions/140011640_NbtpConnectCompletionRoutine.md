# NbtpConnectCompletionRoutine

- ea: `0x140011640`
- end: `0x140011737`
- name: `NbtpConnectCompletionRoutine`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14000da94`
- `0x1400103c0`
- `0x1400103e8`
- `0x1400104d8`
- `0x140010644`
- `0x140011640`
- `0x140011740`
- `0x140041e70`

## pseudocode

```c
__int64 __fastcall NbtpConnectCompletionRoutine(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  unsigned int DelayedNbtProcessConnect; // eax
  int v7; // edx
  void *v8; // rdx
  int v9; // eax

  v4 = *(_QWORD *)(a3 + 16);
  v5 = *(unsigned int *)(*(_QWORD *)(a3 + 32) + 48LL);
  *(_DWORD *)(a3 + 160) = v5;
  if ( (BYTE2(xmmword_140038420) & 8) != 0 )
    WPP_SF_qdq(v5, a2, a3, a2, v5, *(_QWORD *)(a3 + 24));
  *(_WORD *)(a3 + 174) |= 4u;
  if ( !*(_DWORD *)(a3 + 160) )
  {
    NbtQueryWfpAndCleanupConnection(a3);
    DoneDelayedNbtProcessConnect((PVOID)a3);
    return 3221225494LL;
  }
  DelayedNbtProcessConnect = NextDelayedNbtProcessConnect(a3);
  if ( !(unsigned int)NbtIsPotentialConnectivityFailure(*(unsigned int *)(a3 + 160), DelayedNbtProcessConnect) )
  {
    if ( !v7 )
      goto LABEL_14;
LABEL_13:
    *(_DWORD *)(a3 + 160) = v7;
    goto LABEL_14;
  }
  if ( v7 )
    goto LABEL_13;
  if ( *(_DWORD *)(a3 + 120) < *(_DWORD *)(a3 + 124) )
  {
    v8 = &::DelayedNbtProcessConnect;
    goto LABEL_8;
  }
LABEL_14:
  v8 = DelayedNbtCleanupConnectAttempts;
LABEL_8:
  v9 = NTQueueToWorkerThread(0, (__int64)v8, 0, a3, 0, v4, 0, 12);
  if ( v9 < 0 )
  {
    *(_DWORD *)(a3 + 160) = v9;
    DelayedNbtCleanupConnectAttempts(0, a3, 0, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x140011640  mov     [rsp+arg_0], rbx
0x140011645  push    rdi
0x140011646  sub     rsp, 40h
0x14001164a  mov     rax, [r8+20h]
0x14001164e  mov     rbx, r8
0x140011651  mov     rdi, [r8+10h]
0x140011655  mov     ecx, [rax+30h]
0x140011658  mov     [r8+0A0h], ecx
0x14001165f  test    byte ptr cs:xmmword_140038420+2, 8
0x140011666  jnz     loc_1400116F2
0x14001166c  or      word ptr [rbx+0AEh], 4
0x140011674  mov     rcx, rbx
0x140011677  cmp     dword ptr [rbx+0A0h], 0
0x14001167e  jz      short loc_1400116E3
0x140011680  call    NextDelayedNbtProcessConnect
0x140011685  mov     ecx, [rbx+0A0h]
0x14001168b  mov     edx, eax
0x14001168d  call    NbtIsPotentialConnectivityFailure
0x140011692  test    eax, eax
0x140011694  jz      short loc_14001170C
0x140011696  test    edx, edx
0x140011698  jnz     short loc_140011710
0x14001169a  mov     eax, [rbx+7Ch]
0x14001169d  cmp     [rbx+78h], eax
0x1400116a0  jge     short loc_140011716
0x1400116a2  lea     rdx, DelayedNbtProcessConnect
0x1400116a9  mov     [rsp+48h+var_10], 0Ch
0x1400116ae  mov     r9, rbx
0x1400116b1  mov     [rsp+48h+var_18], 0
0x1400116b6  xor     r8d, r8d
0x1400116b9  mov     [rsp+48h+var_20], rdi
0x1400116be  xor     ecx, ecx
0x1400116c0  mov     [rsp+48h+var_28], 0
0x1400116c9  call    NTQueueToWorkerThread
0x1400116ce  test    eax, eax
0x1400116d0  js      short loc_14001171F
0x1400116d2  mov     rbx, [rsp+48h+arg_0]
0x1400116d7  mov     eax, 0C0000016h
0x1400116dc  add     rsp, 40h
0x1400116e0  pop     rdi
0x1400116e1  retn
0x1400116e3  call    NbtQueryWfpAndCleanupConnection
0x1400116e8  mov     rcx, rbx; P
0x1400116eb  call    DoneDelayedNbtProcessConnect
0x1400116f0  jmp     short loc_1400116D2
0x1400116f2  mov     rax, [r8+18h]
0x1400116f6  mov     r9, rdx
0x1400116f9  mov     [rsp+48h+var_20], rax
0x1400116fe  mov     dword ptr [rsp+48h+var_28], ecx
0x140011702  call    WPP_SF_qdq
0x140011707  jmp     loc_14001166C
0x14001170c  test    edx, edx
0x14001170e  jz      short loc_140011716
0x140011710  mov     [rbx+0A0h], edx
0x140011716  lea     rdx, DelayedNbtCleanupConnectAttempts
0x14001171d  jmp     short loc_1400116A9
0x14001171f  xor     r9d, r9d
0x140011722  mov     [rbx+0A0h], eax
0x140011728  xor     r8d, r8d
0x14001172b  mov     rdx, rbx
0x14001172e  xor     ecx, ecx
0x140011730  call    DelayedNbtCleanupConnectAttempts
0x140011735  jmp     short loc_1400116D2
```
