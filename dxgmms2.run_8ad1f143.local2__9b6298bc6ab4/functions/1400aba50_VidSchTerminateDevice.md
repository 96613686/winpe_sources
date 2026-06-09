# VidSchTerminateDevice

- ea: `0x1400aba50`
- end: `0x1400abc39`
- name: `VidSchTerminateDevice`
- size: `489`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ac500`
- `0x140111370`

## callees

- `0x1400045ec`
- `0x140031d74`
- `0x140043774`
- `0x140046720`
- `0x1400aba50`
- `0x1400d90a0`
- `0x1401014b0`
- `0x14011a0cc`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x1400abb43`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400abb43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400abace`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400abace`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400abae7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400abae7`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400abc12`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400abc12`
- `watchdog!WdLogSingleEntry1` at `0x1400aba76`
- `watchdog!WdLogSingleEntry1` at `0x1400aba76`

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
          if ( (byte_140086201 & 8) != 0 )
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
0x1400aba50  push    rbx
0x1400aba52  push    rbp
0x1400aba53  push    rsi
0x1400aba54  push    rdi
0x1400aba55  push    r14
0x1400aba57  sub     rsp, 80h
0x1400aba5e  xor     r14d, r14d
0x1400aba61  mov     rdi, rcx
0x1400aba64  test    rcx, rcx
0x1400aba67  jnz     short loc_1400ABAB8
0x1400aba69  mov     rbx, 0FFFFFFFFC000000Dh
0x1400aba70  lea     ecx, [rdi+1]
0x1400aba73  mov     rdx, rbx
0x1400aba76  call    cs:__imp_WdLogSingleEntry1
0x1400aba7d  nop     dword ptr [rax+rax+00h]
0x1400aba82  mov     [rsp+0A8h+var_70], r14
0x1400aba87  lea     r9, aNullPointerInP; "NULL pointer in pVidSchDevice, returnin"...
0x1400aba8e  mov     [rsp+0A8h+var_78], r14
0x1400aba93  mov     edx, 40000h
0x1400aba98  mov     [rsp+0A8h+var_80], r14
0x1400aba9d  mov     [rsp+0A8h+var_88], rbx
0x1400abaa2  mov     cs:WdLogGlobalForLineNumber, 0F7Dh
0x1400abaac  call    DxgkLogInternalTriageEvent
0x1400abab1  mov     eax, ebx
0x1400abab3  jmp     loc_1400ABC2A
0x1400abab8  mov     rbp, [rcx+28h]
0x1400ababc  mov     esi, 1
0x1400abac1  mov     dl, sil; Wait
0x1400abac4  lea     rbx, [rbp+0C88h]
0x1400abacb  mov     rcx, rbx; Resource
0x1400abace  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400abad5  nop     dword ptr [rax+rax+00h]
0x1400abada  xor     eax, eax
0x1400abadc  lock cmpxchg [rdi+7A8h], esi
0x1400abae4  mov     rcx, rbx; Resource
0x1400abae7  call    cs:__imp_ExReleaseResourceLite
0x1400abaee  nop     dword ptr [rax+rax+00h]
0x1400abaf3  xorps   xmm0, xmm0
0x1400abaf6  lea     rdx, [rsp+0A8h+var_38]
0x1400abafb  movups  [rsp+0A8h+var_38], xmm0
0x1400abb00  xor     r9d, r9d
0x1400abb03  mov     dword ptr [rsp+0A8h+var_38], 0Fh
0x1400abb0b  mov     r8d, 0FFFFFFFDh
0x1400abb11  mov     rcx, rdi; int
0x1400abb14  call    VidSchFlushDevice
0x1400abb19  mov     eax, [rdi+38h]
0x1400abb1c  test    sil, al
0x1400abb1f  jz      short loc_1400ABB92
0x1400abb21  mov     rdx, [rdi+18h]; void *
0x1400abb25  test    rdx, rdx
0x1400abb28  jz      short loc_1400ABB92
0x1400abb2a  mov     rcx, [rbp+8]; this
0x1400abb2e  call    ?DdiDestroyDevice@ADAPTER_RENDER@@QEAAJPEAX@Z; ADAPTER_RENDER::DdiDestroyDevice(void *)
0x1400abb33  cmp     cs:bTracingEnabled, r14b
0x1400abb3a  mov     [rdi+18h], r14
0x1400abb3e  jz      short loc_1400ABB92
0x1400abb40  mov     ebx, [rdi+38h]
0x1400abb43  call    cs:__imp_PsGetCurrentProcessId
0x1400abb4a  nop     dword ptr [rax+rax+00h]
0x1400abb4f  test    cs:byte_140086201, 8
0x1400abb56  mov     r9, rax
0x1400abb59  jz      short loc_1400ABB92
0x1400abb5b  mov     rax, [rbp+10h]
0x1400abb5f  lea     rdx, EventDestroyDevice
0x1400abb66  mov     [rsp+0A8h+var_48], r14
0x1400abb6b  mov     ecx, ebx
0x1400abb6d  mov     [rsp+0A8h+var_58], r14
0x1400abb72  shr     ecx, 2
0x1400abb75  shr     ebx, 1
0x1400abb77  and     ecx, esi
0x1400abb79  mov     [rsp+0A8h+var_68], ecx
0x1400abb7d  and     ebx, esi
0x1400abb7f  mov     dword ptr [rsp+0A8h+var_70], ebx
0x1400abb83  mov     [rsp+0A8h+var_78], rdi
0x1400abb88  mov     [rsp+0A8h+var_88], rax
0x1400abb8d  call    McTemplateK0ppqpttqpqp_EtwWriteTransfer
0x1400abb92  cmp     [rbp+0A14h], r14b
0x1400abb99  jnz     short loc_1400ABBC1
0x1400abb9b  cmp     [rdi+538h], r14d
0x1400abba2  jz      short loc_1400ABBF6
0x1400abba4  xor     r8d, r8d
0x1400abba7  mov     [rdi+538h], esi
0x1400abbad  mov     r9d, 0FFFFFFFDh
0x1400abbb3  mov     rcx, rdi
0x1400abbb6  lea     edx, [r8+4]
0x1400abbba  call    VidSchControlVSyncDevice
0x1400abbbf  jmp     short loc_1400ABBF6
0x1400abbc1  mov     ebx, r14d
0x1400abbc4  cmp     [rbp+30h], r14d
0x1400abbc8  jbe     short loc_1400ABBF6
0x1400abbca  mov     eax, ebx
0x1400abbcc  cmp     [rdi+rax*4+538h], r14d
0x1400abbd4  jz      short loc_1400ABBEF
0x1400abbd6  xor     r8d, r8d
0x1400abbd9  mov     [rdi+rax*4+538h], esi
0x1400abbe0  mov     r9d, ebx
0x1400abbe3  mov     rcx, rdi
0x1400abbe6  lea     edx, [r8+4]
0x1400abbea  call    VidSchControlVSyncDevice
0x1400abbef  add     ebx, esi
0x1400abbf1  cmp     ebx, [rbp+30h]
0x1400abbf4  jb      short loc_1400ABBCA
0x1400abbf6  cmp     [rdi+0F8h], r14b
0x1400abbfd  jz      short loc_1400ABC0B
0x1400abbff  mov     rcx, [rdi+30h]
0x1400abc03  mov     rdx, rbp
0x1400abc06  call    VidSchiCloseProcessAdapterInfo
0x1400abc0b  lea     rcx, [rdi+4D0h]; Resource
0x1400abc12  call    cs:__imp_ExDeleteResourceLite
0x1400abc19  nop     dword ptr [rax+rax+00h]
0x1400abc1e  xor     edx, edx
0x1400abc20  mov     rcx, rdi; P
0x1400abc23  call    VidSchiDecrementDeviceReference
0x1400abc28  xor     eax, eax
0x1400abc2a  add     rsp, 80h
0x1400abc31  pop     r14
0x1400abc33  pop     rdi
0x1400abc34  pop     rsi
0x1400abc35  pop     rbp
0x1400abc36  pop     rbx
0x1400abc37  retn
```
