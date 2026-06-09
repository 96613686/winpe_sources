# HidpFdoDrainDevicePresenceNotifications

- ea: `0x180016188`
- end: `0x1800163b5`
- name: `HidpFdoDrainDevicePresenceNotifications`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18003b444`
- `0x18003f2b4`

## callees

- `0x18000a15c`
- `0x18000ff44`
- `0x180016188`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18001638f`
- `ntoskrnl!IofCompleteRequest` at `0x18001638f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800162c1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1800162c1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800161b5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800161b5`

## pseudocode

```c
__int64 *__fastcall HidpFdoDrainDevicePresenceNotifications(__int64 a1)
{
  KSPIN_LOCK *v2; // rbx
  int v3; // edx
  KIRQL v4; // si
  int v5; // r8d
  __int64 ****v6; // rdx
  __int64 ***v7; // rcx
  __int64 **v8; // rax
  _QWORD *v9; // rax
  int v10; // r8d
  __int64 *result; // rax
  __int64 *v12; // rcx
  __int64 **v13; // rdx
  IRP *v14; // rbx
  __int64 *v15; // [rsp+60h] [rbp-18h] BYREF
  __int64 **v16; // [rsp+68h] [rbp-10h]

  v16 = &v15;
  v2 = (KSPIN_LOCK *)(a1 + 1944);
  v15 = (__int64 *)&v15;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1944));
  if ( !*(_BYTE *)(a1 + 1952) )
  {
    *(_BYTE *)(a1 + 1952) = 1;
    LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        v5,
        *(_QWORD *)(a1 + 672),
        4,
        12,
        15,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        *(_QWORD *)a1);
    }
    v16 = &v15;
    v6 = (__int64 ****)(a1 + 1960);
    v15 = (__int64 *)&v15;
    while ( 1 )
    {
      v7 = *v6;
      if ( *v6 == (__int64 ***)v6 )
        break;
      if ( v7[1] != (__int64 **)v6
        || (v8 = *v7, (*v7)[1] != (__int64 *)v7)
        || (*v6 = (__int64 ***)v8, v8[1] = (__int64 *)v6, v9 = v16, *v16 != (__int64 *)&v15) )
      {
LABEL_29:
        __fastfail(3u);
      }
      v7[1] = v16;
      *v7 = &v15;
      *v9 = v7;
      v16 = (__int64 **)v7;
      _InterlockedExchange64((volatile __int64 *)v7 - 8, 0);
    }
  }
  KeReleaseSpinLock(v2, v4);
  while ( 1 )
  {
    result = v15;
    if ( v15 == (__int64 *)&v15 )
      return result;
    if ( (__int64 **)v15[1] != &v15 )
      goto LABEL_29;
    v12 = (__int64 *)*v15;
    if ( *(__int64 **)(*v15 + 8) != v15 )
      goto LABEL_29;
    v15 = (__int64 *)*v15;
    v13 = &v15;
    v14 = (IRP *)(result - 21);
    v12[1] = (__int64)&v15;
    *((_DWORD *)result - 30) = -1073741536;
    LOBYTE(v13) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x800) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        (_DWORD)v13,
        v10,
        *(_QWORD *)(a1 + 672),
        4,
        12,
        10,
        (__int64)WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids,
        *(_QWORD *)a1,
        (_BYTE)result + 88,
        32);
    }
    IofCompleteRequest(v14, 0);
  }
}

```

## disassembly

```asm
0x180016188  push    rbp
0x18001618a  push    rbx
0x18001618b  push    rsi
0x18001618c  push    rdi
0x18001618d  push    r12
0x18001618f  push    r15
0x180016191  mov     rbp, rsp
0x180016194  sub     rsp, 78h
0x180016198  lea     rax, [rbp+var_18]
0x18001619c  mov     rdi, rcx
0x18001619f  mov     [rbp+var_10], rax
0x1800161a3  lea     rbx, [rcx+798h]
0x1800161aa  lea     rax, [rbp+var_18]
0x1800161ae  mov     rcx, rbx; SpinLock
0x1800161b1  mov     [rbp+var_18], rax
0x1800161b5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800161bc  nop     dword ptr [rax+rax+00h]
0x1800161c1  cmp     byte ptr [rdi+7A0h], 0
0x1800161c8  lea     r12, WPP_GLOBAL_Control
0x1800161cf  mov     sil, al
0x1800161d2  lea     r15, WPP_RECORDER_INITIALIZED
0x1800161d9  lea     r10, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x1800161e0  jnz     loc_1800162BB
0x1800161e6  mov     byte ptr [rdi+7A0h], 1
0x1800161ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800161f4  cmp     rcx, r12
0x1800161f7  jz      short loc_18001620C
0x1800161f9  test    dword ptr [rcx+2Ch], 800h
0x180016200  jz      short loc_18001620C
0x180016202  cmp     byte ptr [rcx+29h], 4
0x180016206  jb      short loc_18001620C
0x180016208  mov     dl, 1
0x18001620a  jmp     short loc_18001620E
0x18001620c  xor     dl, dl
0x18001620e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180016215  setnz   r8b
0x180016219  test    dl, dl
0x18001621b  jnz     short loc_180016222
0x18001621d  test    r8b, r8b
0x180016220  jz      short loc_180016253
0x180016222  mov     rax, [rdi]
0x180016225  mov     r9, [rdi+2A0h]
0x18001622c  mov     rcx, [rcx+18h]
0x180016230  mov     [rsp+78h+var_38], rax
0x180016235  mov     [rsp+78h+var_40], r10
0x18001623a  mov     [rsp+78h+var_48], 0Fh
0x180016241  mov     [rsp+78h+var_50], 0Ch
0x180016249  mov     [rsp+78h+var_58], 4
0x18001624e  call    WPP_RECORDER_AND_TRACE_SF_q
0x180016253  lea     rax, [rbp+var_18]
0x180016257  mov     [rbp+var_10], rax
0x18001625b  lea     rdx, [rdi+7A8h]
0x180016262  lea     rax, [rbp+var_18]
0x180016266  mov     [rbp+var_18], rax
0x18001626a  mov     rcx, [rdx]
0x18001626d  cmp     rcx, rdx
0x180016270  jz      short loc_1800162BB
0x180016272  cmp     [rcx+8], rdx
0x180016276  jnz     loc_1800163A0
0x18001627c  mov     rax, [rcx]
0x18001627f  cmp     [rax+8], rcx
0x180016283  jnz     loc_1800163A0
0x180016289  mov     [rdx], rax
0x18001628c  lea     r8, [rbp+var_18]
0x180016290  mov     [rax+8], rdx
0x180016294  mov     rax, [rbp+var_10]
0x180016298  cmp     [rax], r8
0x18001629b  jnz     loc_1800163A0
0x1800162a1  mov     [rcx+8], rax
0x1800162a5  lea     r8, [rbp+var_18]
0x1800162a9  mov     [rcx], r8
0x1800162ac  mov     [rax], rcx
0x1800162af  xor     eax, eax
0x1800162b1  mov     [rbp+var_10], rcx
0x1800162b5  xchg    rax, [rcx-40h]
0x1800162b9  jmp     short loc_18001626A
0x1800162bb  mov     dl, sil; NewIrql
0x1800162be  mov     rcx, rbx; SpinLock
0x1800162c1  call    cs:__imp_KeReleaseSpinLock
0x1800162c8  nop     dword ptr [rax+rax+00h]
0x1800162cd  mov     esi, 0C0000120h
0x1800162d2  mov     rax, [rbp+var_18]
0x1800162d6  lea     rcx, [rbp+var_18]
0x1800162da  cmp     rax, rcx
0x1800162dd  jz      loc_1800163A7
0x1800162e3  lea     rcx, [rbp+var_18]
0x1800162e7  cmp     [rax+8], rcx
0x1800162eb  jnz     loc_1800163A0
0x1800162f1  mov     rcx, [rax]
0x1800162f4  cmp     [rcx+8], rax
0x1800162f8  jnz     loc_1800163A0
0x1800162fe  mov     [rbp+var_18], rcx
0x180016302  lea     rdx, [rbp+var_18]
0x180016306  lea     rbx, [rax-0A8h]
0x18001630d  mov     [rcx+8], rdx
0x180016311  mov     [rbx+30h], esi
0x180016314  mov     rcx, cs:WPP_GLOBAL_Control
0x18001631b  cmp     rcx, r12
0x18001631e  jz      short loc_180016333
0x180016320  test    dword ptr [rcx+2Ch], 800h
0x180016327  jz      short loc_180016333
0x180016329  cmp     byte ptr [rcx+29h], 4
0x18001632d  jb      short loc_180016333
0x18001632f  mov     dl, 1
0x180016331  jmp     short loc_180016335
0x180016333  xor     dl, dl
0x180016335  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001633c  setnz   r8b
0x180016340  test    dl, dl
0x180016342  jnz     short loc_180016349
0x180016344  test    r8b, r8b
0x180016347  jz      short loc_18001638A
0x180016349  mov     rax, [rdi]
0x18001634c  mov     r9, [rdi+2A0h]
0x180016353  mov     rcx, [rcx+18h]
0x180016357  mov     [rsp+78h+var_28], esi
0x18001635b  mov     [rsp+78h+var_30], rbx
0x180016360  mov     [rsp+78h+var_38], rax
0x180016365  lea     rax, WPP_aade66d4a7573ba4c5e58b1ed440a39c_Traceguids
0x18001636c  mov     [rsp+78h+var_40], rax
0x180016371  mov     [rsp+78h+var_48], 0Ah
0x180016378  mov     [rsp+78h+var_50], 0Ch
0x180016380  mov     [rsp+78h+var_58], 4
0x180016385  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x18001638a  xor     edx, edx; PriorityBoost
0x18001638c  mov     rcx, rbx; Irp
0x18001638f  call    cs:__imp_IofCompleteRequest
0x180016396  nop     dword ptr [rax+rax+00h]
0x18001639b  jmp     loc_1800162D2
0x1800163a0  mov     ecx, 3
0x1800163a5  int     29h; Win8: RtlFailFast(ecx)
0x1800163a7  add     rsp, 78h
0x1800163ab  pop     r15
0x1800163ad  pop     r12
0x1800163af  pop     rdi
0x1800163b0  pop     rsi
0x1800163b1  pop     rbx
0x1800163b2  pop     rbp
0x1800163b3  retn
```
