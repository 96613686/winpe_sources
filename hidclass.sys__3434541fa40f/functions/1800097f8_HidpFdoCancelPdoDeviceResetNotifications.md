# HidpFdoCancelPdoDeviceResetNotifications

- ea: `0x1800097f8`
- end: `0x180009a6f`
- name: `HidpFdoCancelPdoDeviceResetNotifications`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003e5b0`

## callees

- `0x1800097f8`
- `0x18000a15c`
- `0x180018978`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180009a47`
- `ntoskrnl!IofCompleteRequest` at `0x180009a47`
- `ntoskrnl!KeReleaseSpinLock` at `0x180009943`
- `ntoskrnl!KeReleaseSpinLock` at `0x180009943`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180009821`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180009821`

## pseudocode

```c
__int64 __fastcall HidpFdoCancelPdoDeviceResetNotifications(_QWORD *a1, __int64 a2)
{
  KSPIN_LOCK *v2; // rsi
  KIRQL v5; // al
  __int64 *v6; // rdx
  _UNKNOWN **v7; // r8
  KIRQL v8; // r12
  __int64 v9; // rbx
  __int64 *v10; // r9
  __int64 **v11; // rax
  int v12; // r8d
  __int64 result; // rax
  __int64 v14; // rcx
  __int128 *v15; // rdx
  IRP *v16; // rbx
  __int64 **v17; // rax
  __int128 v18; // [rsp+60h] [rbp-10h] BYREF

  v2 = a1 + 237;
  v18 = 0;
  v5 = KeAcquireSpinLockRaiseToDpc(a1 + 237);
  v6 = (__int64 *)a1[239];
  v7 = &WPP_RECORDER_INITIALIZED;
  v8 = v5;
  *((_QWORD *)&v18 + 1) = &v18;
  *(_QWORD *)&v18 = &v18;
  if ( v6 != a1 + 239 )
  {
    do
    {
      v9 = *v6;
      v10 = v6 - 21;
      if ( *(v6 - 6) == a2 )
      {
        if ( *(__int64 **)(v9 + 8) != v6 || (v11 = (__int64 **)v6[1], *v11 != v6) )
LABEL_31:
          __fastfail(3u);
        *v11 = (__int64 *)v9;
        *(_QWORD *)(v9 + 8) = v11;
        if ( _InterlockedExchange64(v10 + 13, 0) )
        {
          v17 = (__int64 **)*((_QWORD *)&v18 + 1);
          if ( **((__int128 ***)&v18 + 1) != &v18 )
            goto LABEL_31;
          v6[1] = *((_QWORD *)&v18 + 1);
          *v6 = (__int64)&v18;
          *v17 = v6;
          *((_QWORD *)&v18 + 1) = v6;
        }
        else
        {
          v6[1] = (__int64)v6;
          *v6 = (__int64)v6;
          LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
          if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              (_DWORD)v6,
              (_DWORD)v7,
              a1[84],
              4,
              10,
              10,
              (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
              *a1,
              (char)v10);
          }
          v7 = &WPP_RECORDER_INITIALIZED;
        }
      }
      v6 = (__int64 *)v9;
    }
    while ( (_QWORD *)v9 != a1 + 239 );
  }
  KeReleaseSpinLock(v2, v8);
  while ( 1 )
  {
    result = v18;
    if ( (__int128 *)v18 == &v18 )
      return result;
    if ( *(__int128 **)(v18 + 8) != &v18 )
      goto LABEL_31;
    v14 = *(_QWORD *)v18;
    if ( *(_QWORD *)(*(_QWORD *)v18 + 8LL) != (_QWORD)v18 )
      goto LABEL_31;
    *(_QWORD *)&v18 = *(_QWORD *)v18;
    v15 = &v18;
    v16 = (IRP *)(result - 168);
    *(_QWORD *)(v14 + 8) = &v18;
    *(_DWORD *)(result - 168 + 48) = -1073741536;
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v15,
        v12,
        a1[84],
        4,
        10,
        12,
        (__int64)WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids,
        *a1,
        result + 88,
        32);
    }
    IofCompleteRequest(v16, 0);
  }
}

```

## disassembly

```asm
0x1800097f8  push    rbp
0x1800097fa  push    rbx
0x1800097fb  push    rsi
0x1800097fc  push    rdi
0x1800097fd  push    r12
0x1800097ff  push    r14
0x180009801  push    r15
0x180009803  mov     rbp, rsp
0x180009806  sub     rsp, 70h
0x18000980a  lea     rsi, [rcx+768h]
0x180009811  mov     r14, rcx
0x180009814  xorps   xmm0, xmm0
0x180009817  mov     rcx, rsi; SpinLock
0x18000981a  mov     r15, rdx
0x18000981d  movups  [rbp+var_10], xmm0
0x180009821  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180009828  nop     dword ptr [rax+rax+00h]
0x18000982d  lea     rdi, [r14+778h]
0x180009834  mov     r11d, 0Ah
0x18000983a  mov     rdx, [rdi]
0x18000983d  lea     r10, WPP_GLOBAL_Control
0x180009844  lea     r8, WPP_RECORDER_INITIALIZED
0x18000984b  mov     r12b, al
0x18000984e  lea     rax, [rbp+var_10]
0x180009852  mov     qword ptr [rbp+var_10+8], rax
0x180009856  lea     rax, [rbp+var_10]
0x18000985a  mov     qword ptr [rbp+var_10], rax
0x18000985e  cmp     rdx, rdi
0x180009861  jz      loc_18000993D
0x180009867  mov     rbx, [rdx]
0x18000986a  lea     r9, [rdx-0A8h]
0x180009871  cmp     [r9+78h], r15
0x180009875  jnz     loc_180009931
0x18000987b  cmp     [rbx+8], rdx
0x18000987f  jnz     loc_180009A58
0x180009885  mov     rax, [rdx+8]
0x180009889  cmp     [rax], rdx
0x18000988c  jnz     loc_180009A58
0x180009892  mov     [rax], rbx
0x180009895  mov     [rbx+8], rax
0x180009899  xor     eax, eax
0x18000989b  xchg    rax, [r9+68h]
0x18000989f  test    rax, rax
0x1800098a2  jnz     loc_1800099C3
0x1800098a8  mov     [rdx+8], rdx
0x1800098ac  mov     [rdx], rdx
0x1800098af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098b6  cmp     rcx, r10
0x1800098b9  jz      short loc_1800098CE
0x1800098bb  test    dword ptr [rcx+2Ch], 200h
0x1800098c2  jz      short loc_1800098CE
0x1800098c4  cmp     byte ptr [rcx+29h], 4
0x1800098c8  jb      short loc_1800098CE
0x1800098ca  mov     dl, 1
0x1800098cc  jmp     short loc_1800098D0
0x1800098ce  xor     dl, dl
0x1800098d0  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1800098d7  setnz   r8b
0x1800098db  test    dl, dl
0x1800098dd  jnz     short loc_1800098E4
0x1800098df  test    r8b, r8b
0x1800098e2  jz      short loc_18000992A
0x1800098e4  mov     rax, [r14]
0x1800098e7  mov     rcx, [rcx+18h]
0x1800098eb  mov     [rsp+70h+var_28], r9
0x1800098f0  mov     r9, [r14+2A0h]
0x1800098f7  mov     [rsp+70h+var_30], rax
0x1800098fc  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180009903  mov     [rsp+70h+var_38], rax
0x180009908  mov     [rsp+70h+var_40], r11w
0x18000990e  mov     [rsp+70h+var_48], r11d
0x180009913  mov     [rsp+70h+var_50], 4
0x180009918  call    WPP_RECORDER_AND_TRACE_SF_qq
0x18000991d  lea     r10, WPP_GLOBAL_Control
0x180009924  mov     r11d, 0Ah
0x18000992a  lea     r8, WPP_RECORDER_INITIALIZED
0x180009931  mov     rdx, rbx
0x180009934  cmp     rbx, rdi
0x180009937  jnz     loc_180009867
0x18000993d  mov     dl, r12b; NewIrql
0x180009940  mov     rcx, rsi; SpinLock
0x180009943  call    cs:__imp_KeReleaseSpinLock
0x18000994a  nop     dword ptr [rax+rax+00h]
0x18000994f  mov     edi, 0C0000120h
0x180009954  lea     rsi, WPP_RECORDER_INITIALIZED
0x18000995b  lea     r15, WPP_GLOBAL_Control
0x180009962  mov     rax, qword ptr [rbp+var_10]
0x180009966  lea     rcx, [rbp+var_10]
0x18000996a  cmp     rax, rcx
0x18000996d  jz      loc_180009A5F
0x180009973  lea     rcx, [rbp+var_10]
0x180009977  cmp     [rax+8], rcx
0x18000997b  jnz     loc_180009A58
0x180009981  mov     rcx, [rax]
0x180009984  cmp     [rcx+8], rax
0x180009988  jnz     loc_180009A58
0x18000998e  mov     qword ptr [rbp+var_10], rcx
0x180009992  lea     rdx, [rbp+var_10]
0x180009996  lea     rbx, [rax-0A8h]
0x18000999d  mov     [rcx+8], rdx
0x1800099a1  mov     [rbx+30h], edi
0x1800099a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099ab  cmp     rcx, r15
0x1800099ae  jz      short loc_1800099EB
0x1800099b0  test    dword ptr [rcx+2Ch], 200h
0x1800099b7  jz      short loc_1800099EB
0x1800099b9  cmp     byte ptr [rcx+29h], 4
0x1800099bd  jb      short loc_1800099EB
0x1800099bf  mov     dl, 1
0x1800099c1  jmp     short loc_1800099ED
0x1800099c3  mov     rax, qword ptr [rbp+var_10+8]
0x1800099c7  lea     rcx, [rbp+var_10]
0x1800099cb  cmp     [rax], rcx
0x1800099ce  jnz     loc_180009A58
0x1800099d4  mov     [rdx+8], rax
0x1800099d8  lea     rcx, [rbp+var_10]
0x1800099dc  mov     [rdx], rcx
0x1800099df  mov     [rax], rdx
0x1800099e2  mov     qword ptr [rbp+var_10+8], rdx
0x1800099e6  jmp     loc_180009931
0x1800099eb  xor     dl, dl
0x1800099ed  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800099f4  setnz   r8b
0x1800099f8  test    dl, dl
0x1800099fa  jnz     short loc_180009A01
0x1800099fc  test    r8b, r8b
0x1800099ff  jz      short loc_180009A42
0x180009a01  mov     rax, [r14]
0x180009a04  mov     r9, [r14+2A0h]
0x180009a0b  mov     rcx, [rcx+18h]
0x180009a0f  mov     [rsp+70h+var_20], edi
0x180009a13  mov     [rsp+70h+var_28], rbx
0x180009a18  mov     [rsp+70h+var_30], rax
0x180009a1d  lea     rax, WPP_7dfbfdf723c8332f637dd0f8a651f634_Traceguids
0x180009a24  mov     [rsp+70h+var_38], rax
0x180009a29  mov     [rsp+70h+var_40], 0Ch
0x180009a30  mov     [rsp+70h+var_48], 0Ah
0x180009a38  mov     [rsp+70h+var_50], 4
0x180009a3d  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180009a42  xor     edx, edx; PriorityBoost
0x180009a44  mov     rcx, rbx; Irp
0x180009a47  call    cs:__imp_IofCompleteRequest
0x180009a4e  nop     dword ptr [rax+rax+00h]
0x180009a53  jmp     loc_180009962
0x180009a58  mov     ecx, 3
0x180009a5d  int     29h; Win8: RtlFailFast(ecx)
0x180009a5f  add     rsp, 70h
0x180009a63  pop     r15
0x180009a65  pop     r14
0x180009a67  pop     r12
0x180009a69  pop     rdi
0x180009a6a  pop     rsi
0x180009a6b  pop     rbx
0x180009a6c  pop     rbp
0x180009a6d  retn
```
