# VidSchTerminateDevice

- ea: `0x1400ace00`
- end: `0x1400acfe9`
- name: `VidSchTerminateDevice`
- size: `489`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ad8b0`
- `0x140113fb0`

## callees

- `0x140004268`
- `0x14002fc10`
- `0x1400438e4`
- `0x140046a30`
- `0x1400ace00`
- `0x1400e1500`
- `0x14010a5b0`
- `0x14011d8bc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400acef3`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400acef3`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ace7e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400ace7e`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ace97`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400ace97`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400acfc2`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400acfc2`
- `watchdog!WdLogSingleEntry1` at `0x1400ace26`
- `watchdog!WdLogSingleEntry1` at `0x1400ace26`

## pseudocode

```c
__int64 __fastcall VidSchTerminateDevice(char *P)
{
  int v2; // ecx
  int v3; // r8d
  __int64 v5; // rbp
  __int64 v6; // r8
  HANDLE CurrentProcessId; // r9
  void *v8; // rdx
  bool v9; // zf
  unsigned int v10; // ebx
  unsigned int i; // ebx

  if ( P )
  {
    v5 = *((_QWORD *)P + 5);
    ExAcquireResourceExclusiveLite((PERESOURCE)(v5 + 3208), 1u);
    _InterlockedCompareExchange((volatile signed __int32 *)P + 490, 1, 0);
    ExReleaseResourceLite((PERESOURCE)(v5 + 3208));
    VidSchFlushDevice((int)P);
    if ( (*((_DWORD *)P + 14) & 1) != 0 )
    {
      v8 = (void *)*((_QWORD *)P + 3);
      if ( v8 )
      {
        ADAPTER_RENDER::DdiDestroyDevice(*(ADAPTER_RENDER **)(v5 + 8), v8);
        v9 = bTracingEnabled == 0;
        *((_QWORD *)P + 3) = 0;
        if ( !v9 )
        {
          v10 = *((_DWORD *)P + 14);
          CurrentProcessId = PsGetCurrentProcessId();
          if ( (byte_140087201 & 8) != 0 )
            McTemplateK0ppqpttqpqp_EtwWriteTransfer(
              (v10 >> 2) & 1,
              (unsigned int)EventDestroyDevice,
              v6,
              (_DWORD)CurrentProcessId,
              *(_QWORD *)(v5 + 16));
        }
      }
    }
    if ( *(_BYTE *)(v5 + 2580) )
    {
      for ( i = 0; i < *(_DWORD *)(v5 + 48); ++i )
      {
        if ( *(_DWORD *)&P[4 * i + 1336] )
        {
          *(_DWORD *)&P[4 * i + 1336] = 1;
          VidSchControlVSyncDevice(P, 4, 0, i);
        }
      }
    }
    else if ( *((_DWORD *)P + 334) )
    {
      *((_DWORD *)P + 334) = 1;
      VidSchControlVSyncDevice(P, 4, 0, 4294967293LL);
    }
    if ( P[248] )
      VidSchiCloseProcessAdapterInfo(*((_QWORD *)P + 6), v5, v6, CurrentProcessId);
    ExDeleteResourceLite((PERESOURCE)(P + 1232));
    VidSchiDecrementDeviceReference(P);
    return 0;
  }
  else
  {
    WdLogSingleEntry1(1, -1073741811);
    WdLogGlobalForLineNumber = 3965;
    DxgkLogInternalTriageEvent(
      v2,
      0x40000,
      v3,
      (unsigned int)L"NULL pointer in pVidSchDevice, returning 0x%I64x",
      -1073741811,
      0,
      0,
      0);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1400ace00  push    rbx
0x1400ace02  push    rbp
0x1400ace03  push    rsi
0x1400ace04  push    rdi
0x1400ace05  push    r14
0x1400ace07  sub     rsp, 80h
0x1400ace0e  xor     r14d, r14d
0x1400ace11  mov     rdi, rcx
0x1400ace14  test    rcx, rcx
0x1400ace17  jnz     short loc_1400ACE68
0x1400ace19  mov     rbx, 0FFFFFFFFC000000Dh
0x1400ace20  lea     ecx, [rdi+1]
0x1400ace23  mov     rdx, rbx
0x1400ace26  call    cs:__imp_WdLogSingleEntry1
0x1400ace2d  nop     dword ptr [rax+rax+00h]
0x1400ace32  mov     [rsp+0A8h+var_70], r14
0x1400ace37  lea     r9, aNullPointerInP; "NULL pointer in pVidSchDevice, returnin"...
0x1400ace3e  mov     [rsp+0A8h+var_78], r14
0x1400ace43  mov     edx, 40000h
0x1400ace48  mov     [rsp+0A8h+var_80], r14
0x1400ace4d  mov     [rsp+0A8h+var_88], rbx
0x1400ace52  mov     cs:WdLogGlobalForLineNumber, 0F7Dh
0x1400ace5c  call    DxgkLogInternalTriageEvent
0x1400ace61  mov     eax, ebx
0x1400ace63  jmp     loc_1400ACFDA
0x1400ace68  mov     rbp, [rcx+28h]
0x1400ace6c  mov     esi, 1
0x1400ace71  mov     dl, sil; Wait
0x1400ace74  lea     rbx, [rbp+0C88h]
0x1400ace7b  mov     rcx, rbx; Resource
0x1400ace7e  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400ace85  nop     dword ptr [rax+rax+00h]
0x1400ace8a  xor     eax, eax
0x1400ace8c  lock cmpxchg [rdi+7A8h], esi
0x1400ace94  mov     rcx, rbx; Resource
0x1400ace97  call    cs:__imp_ExReleaseResourceLite
0x1400ace9e  nop     dword ptr [rax+rax+00h]
0x1400acea3  xorps   xmm0, xmm0
0x1400acea6  lea     rdx, [rsp+0A8h+var_38]
0x1400aceab  movups  [rsp+0A8h+var_38], xmm0
0x1400aceb0  xor     r9d, r9d
0x1400aceb3  mov     dword ptr [rsp+0A8h+var_38], 0Fh
0x1400acebb  mov     r8d, 0FFFFFFFDh
0x1400acec1  mov     rcx, rdi; int
0x1400acec4  call    VidSchFlushDevice
0x1400acec9  mov     eax, [rdi+38h]
0x1400acecc  test    sil, al
0x1400acecf  jz      short loc_1400ACF42
0x1400aced1  mov     rdx, [rdi+18h]; void *
0x1400aced5  test    rdx, rdx
0x1400aced8  jz      short loc_1400ACF42
0x1400aceda  mov     rcx, [rbp+8]; this
0x1400acede  call    ?DdiDestroyDevice@ADAPTER_RENDER@@QEAAJPEAX@Z; ADAPTER_RENDER::DdiDestroyDevice(void *)
0x1400acee3  cmp     cs:bTracingEnabled, r14b
0x1400aceea  mov     [rdi+18h], r14
0x1400aceee  jz      short loc_1400ACF42
0x1400acef0  mov     ebx, [rdi+38h]
0x1400acef3  call    cs:__imp_PsGetCurrentProcessId
0x1400acefa  nop     dword ptr [rax+rax+00h]
0x1400aceff  test    cs:byte_140087201, 8
0x1400acf06  mov     r9, rax
0x1400acf09  jz      short loc_1400ACF42
0x1400acf0b  mov     rax, [rbp+10h]
0x1400acf0f  lea     rdx, EventDestroyDevice
0x1400acf16  mov     [rsp+0A8h+var_48], r14
0x1400acf1b  mov     ecx, ebx
0x1400acf1d  mov     [rsp+0A8h+var_58], r14
0x1400acf22  shr     ecx, 2
0x1400acf25  shr     ebx, 1
0x1400acf27  and     ecx, esi
0x1400acf29  mov     [rsp+0A8h+var_68], ecx
0x1400acf2d  and     ebx, esi
0x1400acf2f  mov     dword ptr [rsp+0A8h+var_70], ebx
0x1400acf33  mov     [rsp+0A8h+var_78], rdi
0x1400acf38  mov     [rsp+0A8h+var_88], rax
0x1400acf3d  call    McTemplateK0ppqpttqpqp_EtwWriteTransfer
0x1400acf42  cmp     [rbp+0A14h], r14b
0x1400acf49  jnz     short loc_1400ACF71
0x1400acf4b  cmp     [rdi+538h], r14d
0x1400acf52  jz      short loc_1400ACFA6
0x1400acf54  xor     r8d, r8d
0x1400acf57  mov     [rdi+538h], esi
0x1400acf5d  mov     r9d, 0FFFFFFFDh
0x1400acf63  mov     rcx, rdi
0x1400acf66  lea     edx, [r8+4]
0x1400acf6a  call    VidSchControlVSyncDevice
0x1400acf6f  jmp     short loc_1400ACFA6
0x1400acf71  mov     ebx, r14d
0x1400acf74  cmp     [rbp+30h], r14d
0x1400acf78  jbe     short loc_1400ACFA6
0x1400acf7a  mov     eax, ebx
0x1400acf7c  cmp     [rdi+rax*4+538h], r14d
0x1400acf84  jz      short loc_1400ACF9F
0x1400acf86  xor     r8d, r8d
0x1400acf89  mov     [rdi+rax*4+538h], esi
0x1400acf90  mov     r9d, ebx
0x1400acf93  mov     rcx, rdi
0x1400acf96  lea     edx, [r8+4]
0x1400acf9a  call    VidSchControlVSyncDevice
0x1400acf9f  add     ebx, esi
0x1400acfa1  cmp     ebx, [rbp+30h]
0x1400acfa4  jb      short loc_1400ACF7A
0x1400acfa6  cmp     [rdi+0F8h], r14b
0x1400acfad  jz      short loc_1400ACFBB
0x1400acfaf  mov     rcx, [rdi+30h]
0x1400acfb3  mov     rdx, rbp
0x1400acfb6  call    VidSchiCloseProcessAdapterInfo
0x1400acfbb  lea     rcx, [rdi+4D0h]; Resource
0x1400acfc2  call    cs:__imp_ExDeleteResourceLite
0x1400acfc9  nop     dword ptr [rax+rax+00h]
0x1400acfce  xor     edx, edx
0x1400acfd0  mov     rcx, rdi; P
0x1400acfd3  call    VidSchiDecrementDeviceReference
0x1400acfd8  xor     eax, eax
0x1400acfda  add     rsp, 80h
0x1400acfe1  pop     r14
0x1400acfe3  pop     rdi
0x1400acfe4  pop     rsi
0x1400acfe5  pop     rbp
0x1400acfe6  pop     rbx
0x1400acfe7  retn
```
