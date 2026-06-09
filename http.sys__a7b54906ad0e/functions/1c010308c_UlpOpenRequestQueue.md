# UlpOpenRequestQueue

- ea: `0x1c010308c`
- end: `0x1c0103450`
- name: `UlpOpenRequestQueue`
- size: `964`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c00a2ccc`

## callees

- `0x1c008f21c`
- `0x1c008f570`
- `0x1c0090288`
- `0x1c009077c`
- `0x1c00a3000`
- `0x1c00a4a34`
- `0x1c00a5768`
- `0x1c00a931c`
- `0x1c0102a4c`
- `0x1c010308c`
- `0x1c0103af4`

## import_xrefs

- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010335d`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c01033b9`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c010335d`
- `ntoskrnl!ExReleaseCacheAwarePushLockExclusive` at `0x1c01033b9`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01032a6`
- `ntoskrnl!ExAcquireCacheAwarePushLockExclusive` at `0x1c01032a6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c01033e1`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1c01033e1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0103248`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0103248`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0103369`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01033c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01033ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0103369`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01033c5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c01033ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103225`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103293`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103225`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0103293`

## pseudocode

```c
__int64 __fastcall UlpOpenRequestQueue(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        struct _ACCESS_STATE *a4,
        ACCESS_MASK DesiredAccess,
        __int64 a6,
        unsigned int a7,
        char a8,
        _QWORD *a9)
{
  unsigned __int16 v9; // bx
  int v12; // edi
  __int64 v13; // rcx
  __int64 RequestQueue; // rax
  __int64 v15; // rsi
  int v16; // edx
  PVOID v17; // rax
  PVOID P; // [rsp+68h] [rbp-8h] BYREF
  unsigned __int16 v21; // [rsp+BAh] [rbp+4Ah]
  char v23[8]; // [rsp+E0h] [rbp+70h]

  v21 = HIWORD(a2);
  v9 = a2;
  P = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qllSqLqLq(
      HIWORD(a2),
      a1,
      a1,
      (unsigned __int16)a2,
      SBYTE2(a2),
      *(_QWORD *)(a3 + 8),
      (char)a4,
      DesiredAccess,
      a6,
      a7,
      (char)a9);
  *a9 = 0;
  if ( a7 != 1 && a7 != 4 )
  {
    v12 = -1073741637;
    goto LABEL_42;
  }
  if ( (a8 & 0x10) != 0 )
  {
    v23[0] = 1;
    if ( (a8 & 2) != 0 )
    {
      v12 = -1073741811;
      if ( (WPP_MAIN_CB.DeviceType & 0x80) == 0 )
        goto LABEL_42;
      v13 = 64;
    }
    else if ( (a8 & 4) != 0 )
    {
      v12 = -1073741811;
      if ( (WPP_MAIN_CB.DeviceType & 0x80) == 0 )
        goto LABEL_42;
      v13 = 65;
    }
    else
    {
      if ( (a8 & 8) == 0 )
      {
        if ( DesiredAccess != 917504 )
        {
          v12 = -1073741811;
          if ( (WPP_MAIN_CB.DeviceType & 0x80) == 0 )
            goto LABEL_42;
          v13 = 67;
          goto LABEL_13;
        }
        goto LABEL_21;
      }
      v12 = -1073741811;
      if ( (WPP_MAIN_CB.DeviceType & 0x80) == 0 )
        goto LABEL_42;
      v13 = 66;
    }
LABEL_13:
    WPP_SF_(v13, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
    goto LABEL_42;
  }
  v23[0] = 0;
LABEL_21:
  if ( *(_QWORD *)(a3 + 8) )
  {
    v12 = UlpValidateRequestQueueName((PCUNICODE_STRING)a3);
    if ( v12 >= 0 )
    {
      if ( a7 != 4 || (DesiredAccess & 0x20) != 0 )
      {
        v12 = UlpAllocateConsumer(a6, a7, &P);
        if ( v12 >= 0 )
        {
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(a1 + 3952, 0);
          RequestQueue = UlpFindRequestQueue(a1, a3, 0);
          v15 = RequestQueue;
          if ( RequestQueue )
          {
            if ( *(_DWORD *)(RequestQueue + 276) == __PAIR32__(v21, v9) )
            {
              KeEnterCriticalRegion();
              ExAcquireCacheAwarePushLockExclusive(*(_QWORD *)(v15 + 280));
              v12 = UlAccessCheck(
                      *(PSECURITY_DESCRIPTOR *)(v15 + 144),
                      a4,
                      DesiredAccess,
                      *(_BYTE *)(a6 + 64),
                      *(_QWORD *)(a3 + 8),
                      0);
              if ( (v12 >= 0
                 || v23[0]
                 && (v12 = UlAccessCheck(UxAdminSDBytes, a4, 0x20000u, *(_BYTE *)(a6 + 64), 0, 0), v12 >= 0)
                 && (v12 = UlAccessCheck(
                             *(PSECURITY_DESCRIPTOR *)(v15 + 144),
                             a4,
                             DesiredAccess,
                             *(_BYTE *)(a6 + 64),
                             *(_QWORD *)(a3 + 8),
                             1),
                     v12 >= 0))
                && (v12 = UlpAttachConsumerToRequestQueue(v15, P), v12 >= 0) )
              {
                ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v15 + 280));
                KeLeaveCriticalRegion();
                if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x200000) != 0 )
                  WPP_SF_qZqL(68, v16, v15, v15 + 152, (char)P, a7);
                v17 = P;
                P = 0;
                *a9 = v17;
              }
              else
              {
                ExReleaseCacheAwarePushLockExclusive(*(_QWORD *)(v15 + 280));
                KeLeaveCriticalRegion();
              }
            }
            else
            {
              v12 = -1073741637;
            }
          }
          else
          {
            v12 = -1073741772;
          }
          ExReleasePushLockExclusiveEx(a1 + 3952, 0);
          KeLeaveCriticalRegion();
        }
      }
      else
      {
        v12 = -1073741790;
      }
    }
  }
  else
  {
    v12 = -1073741811;
  }
LABEL_42:
  if ( P )
  {
    _InterlockedDecrement((volatile signed __int32 *)P);
    UlpFreeConsumer(P);
    P = 0;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qD(69, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids, *a9, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1c010308c  mov     r11, rsp
0x1c010308f  mov     [r11+18h], rbx
0x1c0103093  mov     [r11+20h], r9
0x1c0103097  mov     [rsp-38h+arg_8], edx
0x1c010309b  mov     [r11+8], rcx
0x1c010309f  push    rbp
0x1c01030a0  push    rsi
0x1c01030a1  push    rdi
0x1c01030a2  push    r12
0x1c01030a4  push    r13
0x1c01030a6  push    r14
0x1c01030a8  push    r15
0x1c01030aa  mov     rbp, rsp
0x1c01030ad  sub     rsp, 70h
0x1c01030b1  xor     edi, edi
0x1c01030b3  mov     ebx, edx
0x1c01030b5  mov     [rbp+var_10], edi
0x1c01030b8  mov     r10, r9
0x1c01030bb  mov     [rbp+P], rdi
0x1c01030bf  mov     r15, r8
0x1c01030c2  mov     rdx, rcx
0x1c01030c5  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c01030cb  mov     cl, 80h
0x1c01030cd  mov     r13, [rbp+arg_40]
0x1c01030d4  mov     r14d, dword ptr [rbp+arg_30]
0x1c01030d8  mov     r12d, [rbp+DesiredAccess]
0x1c01030dc  mov     rsi, [rbp+arg_28]
0x1c01030e0  test    cl, al
0x1c01030e2  jz      short loc_1C0103117
0x1c01030e4  mov     rax, [r8+8]
0x1c01030e8  mov     ecx, ebx
0x1c01030ea  mov     [r11-58h], r13
0x1c01030ee  mov     r8, rdx
0x1c01030f1  mov     [r11-60h], r14d
0x1c01030f5  mov     [r11-68h], rsi
0x1c01030f9  mov     [r11-70h], r12d
0x1c01030fd  mov     [r11-78h], r10
0x1c0103101  shr     ecx, 10h
0x1c0103104  mov     [r11-80h], rax
0x1c0103108  movzx   r9d, bx
0x1c010310c  mov     dword ptr [rsp+70h+var_50], ecx
0x1c0103110  call    WPP_SF_qllSqLqLq
0x1c0103115  mov     cl, 80h
0x1c0103117  mov     [r13+0], rdi
0x1c010311b  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0103122  cmp     r14d, 1
0x1c0103126  jz      short loc_1C0103138
0x1c0103128  cmp     r14d, 4
0x1c010312c  jz      short loc_1C0103138
0x1c010312e  mov     edi, 0C00000BBh
0x1c0103133  jmp     loc_1C01033F9
0x1c0103138  mov     eax, dword ptr [rbp+arg_38]
0x1c010313b  test    al, 10h
0x1c010313d  jz      loc_1C01031CC
0x1c0103143  mov     [rbp+arg_30], 1
0x1c0103147  test    al, 2
0x1c0103149  jnz     short loc_1C01031B2
0x1c010314b  test    al, 4
0x1c010314d  jnz     short loc_1C0103198
0x1c010314f  test    al, 8
0x1c0103151  jnz     short loc_1C010317E
0x1c0103153  cmp     r12d, 0E0000h
0x1c010315a  jz      short loc_1C01031D0
0x1c010315c  mov     edi, 0C000000Dh
0x1c0103161  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c0103167  test    cl, al
0x1c0103169  jz      loc_1C01033F9
0x1c010316f  mov     ecx, 43h ; 'C'
0x1c0103174  call    WPP_SF_
0x1c0103179  jmp     loc_1C01033F9
0x1c010317e  mov     edi, 0C000000Dh
0x1c0103183  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c0103189  test    cl, al
0x1c010318b  jz      loc_1C01033F9
0x1c0103191  mov     ecx, 42h ; 'B'
0x1c0103196  jmp     short loc_1C0103174
0x1c0103198  mov     edi, 0C000000Dh
0x1c010319d  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c01031a3  test    cl, al
0x1c01031a5  jz      loc_1C01033F9
0x1c01031ab  mov     ecx, 41h ; 'A'
0x1c01031b0  jmp     short loc_1C0103174
0x1c01031b2  mov     edi, 0C000000Dh
0x1c01031b7  mov     eax, cs:WPP_MAIN_CB.DeviceType
0x1c01031bd  test    cl, al
0x1c01031bf  jz      loc_1C01033F9
0x1c01031c5  mov     ecx, 40h ; '@'
0x1c01031ca  jmp     short loc_1C0103174
0x1c01031cc  mov     [rbp+arg_30], dil
0x1c01031d0  cmp     [r15+8], rdi
0x1c01031d4  jnz     short loc_1C01031E0
0x1c01031d6  mov     edi, 0C000000Dh
0x1c01031db  jmp     loc_1C01033F9
0x1c01031e0  lea     rdx, [rbp+var_10]
0x1c01031e4  mov     rcx, r15; String
0x1c01031e7  call    UlpValidateRequestQueueName
0x1c01031ec  mov     edi, eax
0x1c01031ee  test    eax, eax
0x1c01031f0  js      loc_1C01033F9
0x1c01031f6  cmp     r14d, 4
0x1c01031fa  jnz     short loc_1C010320C
0x1c01031fc  test    r12b, 20h
0x1c0103200  jnz     short loc_1C010320C
0x1c0103202  mov     edi, 0C0000022h
0x1c0103207  jmp     loc_1C01033F9
0x1c010320c  lea     r8, [rbp+P]
0x1c0103210  mov     edx, r14d
0x1c0103213  mov     rcx, rsi
0x1c0103216  call    UlpAllocateConsumer
0x1c010321b  mov     edi, eax
0x1c010321d  test    eax, eax
0x1c010321f  js      loc_1C01033F9
0x1c0103225  call    cs:__imp_KeEnterCriticalRegion
0x1c010322c  nop     dword ptr [rax+rax+00h]
0x1c0103231  mov     rdi, [rbp+arg_0]
0x1c0103235  xor     edx, edx
0x1c0103237  lea     rax, [rdi+0F70h]
0x1c010323e  mov     rcx, rax
0x1c0103241  mov     [rbp+arg_40], rax
0x1c0103248  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1c010324f  nop     dword ptr [rax+rax+00h]
0x1c0103254  mov     r8d, [rbp+var_10]
0x1c0103258  mov     rdx, r15
0x1c010325b  mov     rcx, rdi
0x1c010325e  call    UlpFindRequestQueue
0x1c0103263  mov     rsi, rax
0x1c0103266  test    rax, rax
0x1c0103269  jnz     short loc_1C0103275
0x1c010326b  mov     edi, 0C0000034h
0x1c0103270  jmp     loc_1C01033D8
0x1c0103275  cmp     [rax+114h], bx
0x1c010327c  jnz     loc_1C01033D3
0x1c0103282  movzx   eax, word ptr [rbp+arg_8+2]
0x1c0103286  cmp     [rsi+116h], ax
0x1c010328d  jnz     loc_1C01033D3
0x1c0103293  call    cs:__imp_KeEnterCriticalRegion
0x1c010329a  nop     dword ptr [rax+rax+00h]
0x1c010329f  mov     rcx, [rsi+118h]
0x1c01032a6  call    cs:__imp_ExAcquireCacheAwarePushLockExclusive
0x1c01032ad  nop     dword ptr [rax+rax+00h]
0x1c01032b2  mov     rax, [r15+8]
0x1c01032b6  mov     r8d, r12d; DesiredAccess
0x1c01032b9  mov     rbx, [rbp+arg_28]
0x1c01032bd  mov     rdx, [rbp+AccessState]; AccessState
0x1c01032c1  mov     rcx, [rsi+90h]; SecurityDescriptor
0x1c01032c8  mov     [rsp+70h+var_48], 0; char
0x1c01032cd  mov     r9b, [rbx+40h]; AccessMode
0x1c01032d1  mov     [rsp+70h+var_50], rax; __int64
0x1c01032d6  call    UlAccessCheck
0x1c01032db  mov     edi, eax
0x1c01032dd  xor     eax, eax
0x1c01032df  test    edi, edi
0x1c01032e1  jns     short loc_1C0103344
0x1c01032e3  cmp     [rbp+arg_30], al
0x1c01032e6  jz      loc_1C01033B2
0x1c01032ec  mov     r9b, [rbx+40h]; AccessMode
0x1c01032f0  lea     rcx, UxAdminSDBytes; SecurityDescriptor
0x1c01032f7  mov     rdx, [rbp+AccessState]; AccessState
0x1c01032fb  mov     r8d, 20000h; DesiredAccess
0x1c0103301  mov     [rsp+70h+var_48], al; char
0x1c0103305  mov     [rsp+70h+var_50], rax; __int64
0x1c010330a  call    UlAccessCheck
0x1c010330f  mov     edi, eax
0x1c0103311  test    eax, eax
0x1c0103313  js      loc_1C01033B2
0x1c0103319  mov     rax, [r15+8]
0x1c010331d  mov     r8d, r12d; DesiredAccess
0x1c0103320  mov     r9b, [rbx+40h]; AccessMode
0x1c0103324  mov     rdx, [rbp+AccessState]; AccessState
0x1c0103328  mov     rcx, [rsi+90h]; SecurityDescriptor
0x1c010332f  mov     [rsp+70h+var_48], 1; char
0x1c0103334  mov     [rsp+70h+var_50], rax; __int64
0x1c0103339  call    UlAccessCheck
0x1c010333e  mov     edi, eax
0x1c0103340  test    eax, eax
0x1c0103342  js      short loc_1C01033B2
0x1c0103344  mov     rdx, [rbp+P]
0x1c0103348  mov     rcx, rsi
0x1c010334b  call    UlpAttachConsumerToRequestQueue
0x1c0103350  mov     edi, eax
0x1c0103352  test    eax, eax
0x1c0103354  js      short loc_1C01033B2
0x1c0103356  mov     rcx, [rsi+118h]
0x1c010335d  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c0103364  nop     dword ptr [rax+rax+00h]
0x1c0103369  call    cs:__imp_KeLeaveCriticalRegion
0x1c0103370  nop     dword ptr [rax+rax+00h]
0x1c0103375  test    dword ptr cs:WPP_MAIN_CB.Queue, 200000h
0x1c010337f  jz      short loc_1C01033A3
0x1c0103381  mov     rax, [rbp+P]
0x1c0103385  lea     r9, [rsi+98h]
0x1c010338c  mov     ecx, 44h ; 'D'
0x1c0103391  mov     dword ptr [rsp+70h+var_48], r14d
0x1c0103396  mov     r8, rsi
0x1c0103399  mov     [rsp+70h+var_50], rax
0x1c010339e  call    WPP_SF_qZqL
0x1c01033a3  mov     rax, [rbp+P]
0x1c01033a7  and     [rbp+P], 0
0x1c01033ac  mov     [r13+0], rax
0x1c01033b0  jmp     short loc_1C01033D8
0x1c01033b2  mov     rcx, [rsi+118h]
0x1c01033b9  call    cs:__imp_ExReleaseCacheAwarePushLockExclusive
0x1c01033c0  nop     dword ptr [rax+rax+00h]
0x1c01033c5  call    cs:__imp_KeLeaveCriticalRegion
0x1c01033cc  nop     dword ptr [rax+rax+00h]
0x1c01033d1  jmp     short loc_1C01033D8
0x1c01033d3  mov     edi, 0C00000BBh
0x1c01033d8  mov     rcx, [rbp+arg_40]
0x1c01033df  xor     edx, edx
0x1c01033e1  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1c01033e8  nop     dword ptr [rax+rax+00h]
0x1c01033ed  call    cs:__imp_KeLeaveCriticalRegion
0x1c01033f4  nop     dword ptr [rax+rax+00h]
0x1c01033f9  mov     rax, [rbp+P]
0x1c01033fd  test    rax, rax
0x1c0103400  jz      short loc_1C0103413
0x1c0103402  lock dec dword ptr [rax]
0x1c0103405  mov     rcx, [rbp+P]; P
0x1c0103409  call    UlpFreeConsumer
0x1c010340e  and     [rbp+P], 0
0x1c0103413  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0103419  test    al, al
0x1c010341b  jns     short loc_1C0103435
0x1c010341d  mov     r8, [r13+0]
0x1c0103421  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0103428  mov     ecx, 45h ; 'E'
0x1c010342d  mov     r9d, edi
0x1c0103430  call    WPP_SF_qD
0x1c0103435  mov     rbx, [rsp+70h+arg_10]
0x1c010343d  mov     eax, edi
0x1c010343f  add     rsp, 70h
0x1c0103443  pop     r15
0x1c0103445  pop     r14
0x1c0103447  pop     r13
0x1c0103449  pop     r12
0x1c010344b  pop     rdi
0x1c010344c  pop     rsi
0x1c010344d  pop     rbp
0x1c010344e  retn
```
