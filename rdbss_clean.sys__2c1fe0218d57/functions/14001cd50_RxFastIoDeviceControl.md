# RxFastIoDeviceControl

- ea: `0x14001cd50`
- end: `0x14001d0d3`
- name: `RxFastIoDeviceControl`
- size: `899`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, int, int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140016e20`
- `0x14001cd50`
- `0x140025c20`
- `0x140025c50`
- `0x140044280`
- `0x1400442e4`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ce83`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14001ce83`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d015`
- `ntoskrnl!ObfDereferenceObject` at `0x14001d015`
- `ntoskrnl!ExGetPreviousMode` at `0x14001cda4`
- `ntoskrnl!ExGetPreviousMode` at `0x14001ce56`
- `ntoskrnl!ExGetPreviousMode` at `0x14001cda4`
- `ntoskrnl!ExGetPreviousMode` at `0x14001ce56`
- `ntoskrnl!PsThreadType` at `0x14001ce4c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cf57`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cf57`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cef9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cef9`

## pseudocode

```c
char __fastcall RxFastIoDeviceControl(
        __int64 a1,
        __int64 a2,
        void **a3,
        unsigned int a4,
        void *a5,
        unsigned int a6,
        int a7,
        void *a8)
{
  char v10; // r14
  KPROCESSOR_MODE PreviousMode; // r15
  NTSTATUS v12; // esi
  void *ULong64FromUser; // rsi
  KPROCESSOR_MODE v14; // al
  __int64 i; // r12
  KIRQL v16; // r9
  struct _LIST_ENTRY *j; // rdx
  bool v18; // sf
  __int128 v20; // [rsp+48h] [rbp-A0h] BYREF
  PVOID Object[2]; // [rsp+58h] [rbp-90h] BYREF
  __int128 Src; // [rsp+68h] [rbp-80h] BYREF
  __int128 v23; // [rsp+78h] [rbp-70h]
  _BYTE v24[28]; // [rsp+88h] [rbp-60h] BYREF

  Object[1] = a8;
  v10 = 0;
  v20 = 0;
  PreviousMode = ExGetPreviousMode();
  if ( a7 == 1310960 || a7 == 1311639 || a7 == 1311643 )
  {
    *((_QWORD *)&v20 + 1) = 0;
    v12 = -1073741822;
  }
  else if ( a7 == 1311684 )
  {
    Object[0] = 0;
    *((_QWORD *)&v20 + 1) = 0;
    if ( a4 < 8 || a6 < 0x3C )
    {
      v12 = -1073741811;
      v10 = 1;
    }
    else
    {
      Src = 0;
      v23 = 0;
      memset(v24, 0, sizeof(v24));
      if ( PreviousMode )
        ULong64FromUser = (void *)RtlReadULong64FromUser(a3);
      else
        ULong64FromUser = *a3;
      v14 = ExGetPreviousMode();
      v12 = ObReferenceObjectByHandle(ULong64FromUser, 0x800u, (POBJECT_TYPE)PsThreadType, v14, Object, 0);
      v10 = 1;
      if ( v12 >= 0 )
      {
        Src = 0;
        v23 = 0;
        memset(v24, 0, sizeof(v24));
        v12 = -1073741275;
        for ( i = 0; (unsigned int)i < 0x40; i = (unsigned int)(i + 1) )
        {
          v16 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&unk_140035700 + 24 * i);
          for ( j = (&RxActiveContexts.Flink)[24 * i]; j != &RxActiveContexts + 12 * i; j = j->Flink )
          {
            if ( j[5].Flink == Object[0] )
            {
              LOBYTE(Src) = 1;
              _m_prefetchw(&j[7].Blink);
              BYTE1(Src) = (_InterlockedXor((volatile signed __int32 *)&j[7].Blink, 0) & 2) != 0;
              v12 = 0;
              break;
            }
          }
          KeReleaseSpinLock((PKSPIN_LOCK)&unk_140035700 + 24 * i, v16);
          v18 = v12 < 0;
          if ( !v12 )
            goto LABEL_22;
        }
        v18 = v12 < 0;
LABEL_22:
        if ( v18 )
        {
          if ( v12 == -1073741275 )
          {
            LOBYTE(Src) = 0;
            if ( PreviousMode )
              RtlCopyToUser(a5, &Src, 0x3Cu);
            else
              RtlCopyVolatileMemory(a5, &Src, 0x3Cu);
            *((_QWORD *)&v20 + 1) = 60;
            v12 = 0;
          }
        }
        else
        {
          if ( PreviousMode )
            RtlCopyToUser(a5, &Src, 0x3Cu);
          else
            RtlCopyVolatileMemory(a5, &Src, 0x3Cu);
          *((_QWORD *)&v20 + 1) = 60;
        }
      }
    }
    if ( Object[0] )
      ObfDereferenceObject(Object[0]);
  }
  else
  {
    v12 = 0;
  }
  LODWORD(v20) = v12;
  if ( PreviousMode )
    RtlCopyToUser(a8, &v20, 0x10u);
  else
    RtlCopyVolatileMemory(a8, &v20, 0x10u);
  return v10;
}

```

## disassembly

```asm
0x14001cd50  push    rbx
0x14001cd52  push    rsi
0x14001cd53  push    r12
0x14001cd55  push    r13
0x14001cd57  push    r14
0x14001cd59  push    r15
0x14001cd5b  sub     rsp, 0B8h
0x14001cd62  mov     rax, cs:__security_cookie
0x14001cd69  xor     rax, rsp
0x14001cd6c  mov     [rsp+0E8h+var_40], rax
0x14001cd74  mov     ebx, r9d
0x14001cd77  mov     rsi, r8
0x14001cd7a  mov     rax, [rsp+0E8h+arg_20]
0x14001cd82  mov     [rsp+0E8h+var_A8], rax
0x14001cd87  mov     r13, [rsp+0E8h+arg_38]
0x14001cd8f  mov     [rsp+0E8h+var_88], r13
0x14001cd94  xor     r14b, r14b
0x14001cd97  mov     [rsp+0E8h+var_B0], r14b
0x14001cd9c  xorps   xmm0, xmm0
0x14001cd9f  movups  [rsp+0E8h+var_A0], xmm0
0x14001cda4  call    cs:__imp_ExGetPreviousMode
0x14001cdab  nop     dword ptr [rax+rax+00h]
0x14001cdb0  mov     r15b, al
0x14001cdb3  mov     [rsp+0E8h+var_B8], al
0x14001cdb7  mov     ecx, [rsp+0E8h+arg_30]
0x14001cdbe  sub     ecx, 1400F0h
0x14001cdc4  jz      loc_14001D023
0x14001cdca  sub     ecx, 2A7h
0x14001cdd0  jz      loc_14001D023
0x14001cdd6  sub     ecx, 4
0x14001cdd9  jz      loc_14001D023
0x14001cddf  cmp     ecx, 29h ; ')'
0x14001cde2  jz      short loc_14001CDEB
0x14001cde4  xor     esi, esi
0x14001cde6  jmp     loc_14001D04C
0x14001cdeb  mov     [rsp+0E8h+var_90], 0
0x14001cdf4  mov     qword ptr [rsp+0E8h+var_A0+8], 0
0x14001cdfd  cmp     ebx, 8
0x14001ce00  jb      loc_14001CFDB
0x14001ce06  cmp     [rsp+0E8h+arg_28], 3Ch ; '<'
0x14001ce0e  jb      loc_14001CFDB
0x14001ce14  xorps   xmm0, xmm0
0x14001ce17  xor     eax, eax
0x14001ce19  movups  [rsp+0E8h+Src], xmm0
0x14001ce1e  movups  [rsp+0E8h+var_70], xmm0
0x14001ce23  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x14001ce2b  movups  xmmword ptr [rsp+0E8h+var_60+0Ch], xmm0
0x14001ce33  mov     [rsp+0E8h+var_B4], eax
0x14001ce37  test    r15b, r15b
0x14001ce3a  jz      short loc_14001CE49
0x14001ce3c  mov     rcx, rsi
0x14001ce3f  call    RtlReadULong64FromUser
0x14001ce44  mov     rsi, rax
0x14001ce47  jmp     short loc_14001CE4C
0x14001ce49  mov     rsi, [rsi]
0x14001ce4c  mov     rax, cs:__imp_PsThreadType
0x14001ce53  mov     rbx, [rax]
0x14001ce56  call    cs:__imp_ExGetPreviousMode
0x14001ce5d  nop     dword ptr [rax+rax+00h]
0x14001ce62  mov     r9b, al; AccessMode
0x14001ce65  mov     [rsp+0E8h+HandleInformation], 0; HandleInformation
0x14001ce6e  lea     rax, [rsp+0E8h+var_90]
0x14001ce73  mov     [rsp+0E8h+Object], rax; Object
0x14001ce78  mov     r8, rbx; ObjectType
0x14001ce7b  mov     edx, 800h; DesiredAccess
0x14001ce80  mov     rcx, rsi; Handle
0x14001ce83  call    cs:__imp_ObReferenceObjectByHandle
0x14001ce8a  nop     dword ptr [rax+rax+00h]
0x14001ce8f  mov     esi, eax
0x14001ce91  mov     [rsp+0E8h+var_B4], eax
0x14001ce95  mov     r14d, 1
0x14001ce9b  test    eax, eax
0x14001ce9d  js      loc_14001CFEA
0x14001cea3  mov     [rsp+0E8h+var_AC], 0
0x14001ceab  xorps   xmm0, xmm0
0x14001ceae  movups  [rsp+0E8h+Src], xmm0
0x14001ceb3  movups  [rsp+0E8h+var_70], xmm0
0x14001ceb8  movups  xmmword ptr [rsp+0E8h+var_60], xmm0
0x14001cec0  movups  xmmword ptr [rsp+0E8h+var_60+0Ch], xmm0
0x14001cec8  mov     esi, 0C0000225h
0x14001cecd  mov     [rsp+0E8h+var_B4], esi
0x14001ced1  xor     r12d, r12d
0x14001ced4  lea     rcx, RxActiveContexts
0x14001cedb  mov     [rsp+0E8h+var_AC], r12d
0x14001cee0  cmp     r12d, 40h ; '@'
0x14001cee4  jnb     loc_14001CF74
0x14001ceea  lea     rbx, [r12+r12*2]
0x14001ceee  shl     rbx, 6
0x14001cef2  add     rcx, 40h ; '@'
0x14001cef6  add     rcx, rbx; SpinLock
0x14001cef9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001cf00  nop     dword ptr [rax+rax+00h]
0x14001cf05  mov     r9b, al
0x14001cf08  lea     r10, RxActiveContexts
0x14001cf0f  lea     rcx, [rbx+r10]
0x14001cf13  mov     rdx, [rcx]
0x14001cf16  mov     r8, [rsp+0E8h+var_90]
0x14001cf1b  cmp     rdx, rcx
0x14001cf1e  jz      short loc_14001CF4D
0x14001cf20  cmp     [rdx+50h], r8
0x14001cf24  jnz     short loc_14001CF6F
0x14001cf26  mov     byte ptr [rsp+0E8h+Src], r14b
0x14001cf2b  prefetchw byte ptr [rdx+78h]
0x14001cf2f  mov     eax, [rdx+78h]
0x14001cf32  mov     ecx, eax
0x14001cf34  xor     ecx, 0
0x14001cf37  lock cmpxchg [rdx+78h], ecx
0x14001cf3c  jnz     short loc_14001CF32
0x14001cf3e  shr     eax, 1
0x14001cf40  and     al, r14b
0x14001cf43  mov     byte ptr [rsp+0E8h+Src+1], al
0x14001cf47  xor     esi, esi
0x14001cf49  mov     [rsp+0E8h+var_B4], esi
0x14001cf4d  mov     dl, r9b; NewIrql
0x14001cf50  lea     rcx, [r10+40h]
0x14001cf54  add     rcx, rbx; SpinLock
0x14001cf57  call    cs:__imp_KeReleaseSpinLock
0x14001cf5e  nop     dword ptr [rax+rax+00h]
0x14001cf63  test    esi, esi
0x14001cf65  jz      short loc_14001CF76
0x14001cf67  add     r12d, r14d
0x14001cf6a  jmp     loc_14001CED4
0x14001cf6f  mov     rdx, [rdx]
0x14001cf72  jmp     short loc_14001CF1B
0x14001cf74  test    esi, esi
0x14001cf76  js      short loc_14001CFA2
0x14001cf78  mov     ebx, 3Ch ; '<'
0x14001cf7d  lea     rdx, [rsp+0E8h+Src]; Src
0x14001cf82  mov     rcx, [rsp+0E8h+var_A8]; void *
0x14001cf87  mov     r8d, ebx; Size
0x14001cf8a  test    r15b, r15b
0x14001cf8d  jz      short loc_14001CF96
0x14001cf8f  call    RtlCopyToUser
0x14001cf94  jmp     short loc_14001CF9B
0x14001cf96  call    RtlCopyVolatileMemory
0x14001cf9b  mov     qword ptr [rsp+0E8h+var_A0+8], rbx
0x14001cfa0  jmp     short loc_14001CFEA
0x14001cfa2  cmp     esi, 0C0000225h
0x14001cfa8  jnz     short loc_14001CFEA
0x14001cfaa  mov     byte ptr [rsp+0E8h+Src], 0
0x14001cfaf  mov     ebx, 3Ch ; '<'
0x14001cfb4  lea     rdx, [rsp+0E8h+Src]; Src
0x14001cfb9  mov     rcx, [rsp+0E8h+var_A8]; void *
0x14001cfbe  mov     r8d, ebx; Size
0x14001cfc1  test    r15b, r15b
0x14001cfc4  jz      short loc_14001CFCD
0x14001cfc6  call    RtlCopyToUser
0x14001cfcb  jmp     short loc_14001CFD2
0x14001cfcd  call    RtlCopyVolatileMemory
0x14001cfd2  mov     qword ptr [rsp+0E8h+var_A0+8], rbx
0x14001cfd7  xor     esi, esi
0x14001cfd9  jmp     short loc_14001CFE6
0x14001cfdb  mov     esi, 0C000000Dh
0x14001cfe0  mov     r14d, 1
0x14001cfe6  mov     [rsp+0E8h+var_B4], esi
0x14001cfea  jmp     short loc_14001D00B
0x14001cfec  mov     esi, eax
0x14001cfee  mov     [rsp+0E8h+var_B4], eax
0x14001cff2  mov     qword ptr [rsp+0E8h+var_A0+8], 0
0x14001cffb  mov     r14d, 1
0x14001d001  mov     r15b, [rsp+0E8h+var_B8]
0x14001d006  mov     r13, [rsp+0E8h+var_88]
0x14001d00b  mov     rcx, [rsp+0E8h+var_90]; Object
0x14001d010  test    rcx, rcx
0x14001d013  jz      short loc_14001D04C
0x14001d015  call    cs:__imp_ObfDereferenceObject
0x14001d01c  nop     dword ptr [rax+rax+00h]
0x14001d021  jmp     short loc_14001D04C
0x14001d023  mov     qword ptr [rsp+0E8h+var_A0+8], 0
0x14001d02c  mov     esi, 0C0000002h
0x14001d031  mov     [rsp+0E8h+var_B4], esi
0x14001d035  jmp     short loc_14001D04C
0x14001d037  mov     esi, eax
0x14001d039  mov     [rsp+0E8h+var_B4], eax
0x14001d03d  mov     r14b, [rsp+0E8h+var_B0]
0x14001d042  mov     r15b, [rsp+0E8h+var_B8]
0x14001d047  mov     r13, [rsp+0E8h+var_88]
0x14001d04c  mov     dword ptr [rsp+0E8h+var_A0], esi
0x14001d050  mov     r8d, 10h; Size
0x14001d056  lea     rdx, [rsp+0E8h+var_A0]; Src
0x14001d05b  mov     rcx, r13; void *
0x14001d05e  test    r15b, r15b
0x14001d061  jz      short loc_14001D06A
0x14001d063  call    RtlCopyToUser
0x14001d068  jmp     short loc_14001D06F
0x14001d06a  call    RtlCopyVolatileMemory
0x14001d06f  jmp     short loc_14001D0AD
0x14001d071  lea     rdx, WPP_GLOBAL_Control
0x14001d078  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d07f  cmp     rcx, rdx
0x14001d082  jz      short loc_14001D0AA
0x14001d084  mov     edx, [rcx+2Ch]
0x14001d087  test    dl, 1
0x14001d08a  jz      short loc_14001D0AA
0x14001d08c  cmp     byte ptr [rcx+29h], 1
0x14001d090  jb      short loc_14001D0AA
0x14001d092  mov     edx, 13h
0x14001d097  mov     r9d, eax
0x14001d09a  lea     r8, WPP_1b57de22b73d3f557c58b461499d9993_Traceguids
0x14001d0a1  mov     rcx, [rcx+18h]
0x14001d0a5  call    WPP_SF_d
0x14001d0aa  xor     r14b, r14b
0x14001d0ad  mov     al, r14b
0x14001d0b0  mov     rcx, [rsp+0E8h+var_40]
0x14001d0b8  xor     rcx, rsp; StackCookie
0x14001d0bb  call    __security_check_cookie
0x14001d0c0  add     rsp, 0B8h
0x14001d0c7  pop     r15
0x14001d0c9  pop     r14
0x14001d0cb  pop     r13
0x14001d0cd  pop     r12
0x14001d0cf  pop     rsi
0x14001d0d0  pop     rbx
0x14001d0d1  retn
```
