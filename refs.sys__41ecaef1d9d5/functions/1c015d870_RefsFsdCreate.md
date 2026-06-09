# RefsFsdCreate

- ea: `0x1c015d870`
- end: `0x1c015dbb0`
- name: `RefsFsdCreate`
- size: `832`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1c0003cdc`
- `0x1c0005564`
- `0x1c0005650`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c00588cc`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c015d870`
- `0x1c0179bd4`
- `0x1c017baec`
- `0x1c01cd29c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c015d99a`
- `ntoskrnl!KeInitializeEvent` at `0x1c015d99a`
- `ntoskrnl!IofCompleteRequest` at `0x1c0183a3e`
- `ntoskrnl!IofCompleteRequest` at `0x1c0183a3e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015d97c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c015d97c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015d924`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c015d924`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015d940`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1c015d940`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0183a8b`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c0183a8b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015db4a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c015db4a`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c015d8f4`
- `ntoskrnl!IoIsOperationSynchronous` at `0x1c015d8f4`

## string_xrefs

- `0x1c015da39`: `Create.c`
- `0x1c015db1f`: `Create.c`
- `0x1c0183a61`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsFsdCreate(__int64 a1, IRP *a2)
{
  __int64 v3; // r14
  __int64 v4; // rdx
  NTSTATUS v5; // eax
  int v6; // esi
  BOOL v7; // r15d
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r9
  unsigned int Status; // [rsp+20h] [rbp-178h]
  int v14[2]; // [rsp+28h] [rbp-170h] BYREF
  BOOL v15; // [rsp+30h] [rbp-168h]
  _QWORD v16[2]; // [rsp+38h] [rbp-160h] BYREF
  _QWORD Event[4]; // [rsp+48h] [rbp-150h] BYREF
  _OWORD v18[2]; // [rsp+68h] [rbp-130h] BYREF
  __int64 v19; // [rsp+88h] [rbp-110h]
  _QWORD v20[26]; // [rsp+90h] [rbp-108h] BYREF
  __int128 v21; // [rsp+160h] [rbp-38h] BYREF

  v16[1] = a2;
  memset(v18, 0, sizeof(v18));
  v19 = 0;
  *(_QWORD *)v14 = 0;
  memset(Event, 0, sizeof(Event));
  v21 = 0;
  v16[0] = 0;
  if ( *(_WORD *)(a1 + 2) == 336 )
  {
    a2->IoStatus.Status = 0;
    a2->IoStatus.Information = 1;
    IofCompleteRequest(a2, 1);
    return 0;
  }
  else
  {
    v3 = RefsInitializeTopLevelIrp(v18, 0, 0);
    IoIsOperationSynchronous(a2);
    LOBYTE(v4) = 1;
    v5 = RefsInitializeIrpContext(a2, v4, 0, v14);
    v6 = v5;
    Status = v5;
    if ( v5 < 0 )
    {
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(v5);
      RefsExtendedCompleteRequestInternal(0, a2, Status);
    }
    else
    {
      KeEnterCriticalRegion();
      v7 = (int)IoPropagateActivityIdToThread(a2, &v21, v16) >= 0;
      v15 = v7;
      v8 = *(_QWORD *)(v3 + 32);
      v9 = *(_QWORD *)v14;
      if ( !v8 )
      {
        *(_DWORD *)(v3 + 4) = 1397140410;
        *(_QWORD *)(v3 + 32) = v9;
        *(_DWORD *)(v9 + 8) |= 0x100000u;
        IoSetTopLevelIrp((PIRP)v3);
        v8 = *(_QWORD *)(v3 + 32);
      }
      *(_QWORD *)(v9 + 104) = v8;
      KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
      do
      {
        memset(v20, 0, sizeof(v20));
        v20[21] = a2->Tail.Overlay.CurrentStackLocation;
        if ( v6 == -1073741432 )
          RefsCheckpointForLogFileFull(v9);
        if ( v9 )
          RefsPreRequestProcessingExtend(v9);
        v20[9] = Event;
        *(_DWORD *)(v9 + 8) |= 0x10002u;
        if ( (*(_DWORD *)(v9 + 8) & 0x200) != 0 )
        {
          v6 = RefsCommonVolumeOpen(v9, (__int64)a2, v10, v11);
          Status = v6;
        }
        else
        {
          v6 = RefsCommonCreateOnNewStack(v9, a2, v20);
          Status = v6;
          if ( v6 == 871 )
          {
            *(_DWORD *)(v9 + 4) |= 0x400u;
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(871);
            v9 = *(_QWORD *)v14;
            RefsExtendedCompleteRequestInternal(*(_QWORD *)v14, 0, 871);
            RefsWaitForCreateEvent(a2);
            *(_BYTE *)(v20[21] + 3LL) &= ~1u;
            v6 = 871;
          }
        }
      }
      while ( v6 == -1073741608 || v6 == -1073741400 || v6 == -1073741432 || v6 == 871 );
      if ( v6 == 259 )
      {
        RefsWaitForCreateEvent(a2);
        Status = a2->IoStatus.Status;
        v20[21] = a2->Tail.Overlay.CurrentStackLocation;
        *(_BYTE *)(v20[21] + 3LL) &= ~1u;
      }
      *(_DWORD *)(v9 + 8) &= ~0x10000u;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsExtendedCompleteRequestInternal(*(_QWORD *)v14, a2, Status);
      if ( v7 )
        IoClearActivityIdThread(v16[0]);
      KeLeaveCriticalRegion();
    }
    return Status;
  }
}

```

## disassembly

```asm
0x1c015d870  mov     r11, rsp
0x1c015d873  mov     [r11+8], rbx
0x1c015d877  mov     [r11+18h], rsi
0x1c015d87b  push    rdi
0x1c015d87c  push    r14
0x1c015d87e  push    r15
0x1c015d880  sub     rsp, 180h
0x1c015d887  mov     rax, cs:__security_cookie
0x1c015d88e  xor     rax, rsp
0x1c015d891  mov     [rsp+198h+var_28], rax
0x1c015d899  mov     rdi, rdx
0x1c015d89c  mov     [rsp+198h+var_158], rdx
0x1c015d8a1  xorps   xmm0, xmm0
0x1c015d8a4  xor     eax, eax
0x1c015d8a6  movups  [rsp+198h+var_130], xmm0
0x1c015d8ab  movups  [rsp+198h+var_120], xmm0
0x1c015d8b0  mov     [r11-110h], rax
0x1c015d8b7  and     qword ptr [rsp+198h+var_170], rax
0x1c015d8bc  movups  xmmword ptr [rsp+198h+Event], xmm0
0x1c015d8c1  movups  xmmword ptr [rsp+198h+Event+10h], xmm0
0x1c015d8c6  movups  xmmword ptr [r11-38h], xmm0
0x1c015d8cb  and     [rsp+198h+var_160], rax
0x1c015d8d0  mov     eax, 150h
0x1c015d8d5  cmp     [rcx+2], ax
0x1c015d8d9  jz      loc_1C0183A2C
0x1c015d8df  xor     r8d, r8d
0x1c015d8e2  xor     edx, edx
0x1c015d8e4  lea     rcx, [rsp+198h+var_130]
0x1c015d8e9  call    RefsInitializeTopLevelIrp
0x1c015d8ee  mov     r14, rax
0x1c015d8f1  mov     rcx, rdi; Irp
0x1c015d8f4  call    cs:__imp_IoIsOperationSynchronous
0x1c015d8fb  nop     dword ptr [rax+rax+00h]
0x1c015d900  lea     r9, [rsp+198h+var_170]
0x1c015d905  xor     r8d, r8d
0x1c015d908  lea     ebx, [r8+1]
0x1c015d90c  mov     dl, bl
0x1c015d90e  mov     rcx, rdi
0x1c015d911  call    RefsInitializeIrpContext
0x1c015d916  mov     esi, eax
0x1c015d918  mov     [rsp+198h+Status], eax
0x1c015d91c  test    eax, eax
0x1c015d91e  js      loc_1C0183A51
0x1c015d924  call    cs:__imp_KeEnterCriticalRegion
0x1c015d92b  nop     dword ptr [rax+rax+00h]
0x1c015d930  lea     r8, [rsp+198h+var_160]
0x1c015d935  lea     rdx, [rsp+198h+var_38]
0x1c015d93d  mov     rcx, rdi
0x1c015d940  call    cs:__imp_IoPropagateActivityIdToThread
0x1c015d947  nop     dword ptr [rax+rax+00h]
0x1c015d94c  xor     r15d, r15d
0x1c015d94f  test    eax, eax
0x1c015d951  cmovns  r15d, ebx
0x1c015d955  mov     [rsp+198h+var_168], r15d
0x1c015d95a  mov     rax, [r14+20h]
0x1c015d95e  mov     rbx, qword ptr [rsp+198h+var_170]
0x1c015d963  test    rax, rax
0x1c015d966  jnz     short loc_1C015D98C
0x1c015d968  mov     dword ptr [r14+4], 5346ABBAh
0x1c015d970  mov     [r14+20h], rbx
0x1c015d974  bts     dword ptr [rbx+8], 14h
0x1c015d979  mov     rcx, r14; Irp
0x1c015d97c  call    cs:__imp_IoSetTopLevelIrp
0x1c015d983  nop     dword ptr [rax+rax+00h]
0x1c015d988  mov     rax, [r14+20h]
0x1c015d98c  mov     [rbx+68h], rax
0x1c015d990  xor     r8d, r8d; State
0x1c015d993  xor     edx, edx; Type
0x1c015d995  lea     rcx, [rsp+198h+Event+8]; Event
0x1c015d99a  call    cs:__imp_KeInitializeEvent
0x1c015d9a1  nop     dword ptr [rax+rax+00h]
0x1c015d9a6  mov     r14d, 367h
0x1c015d9ac  xor     edx, edx; Val
0x1c015d9ae  mov     r8d, 0D0h; Size
0x1c015d9b4  lea     rcx, [rsp+198h+var_108]; void *
0x1c015d9bc  call    memset
0x1c015d9c1  mov     rax, [rdi+0B8h]
0x1c015d9c8  mov     [rsp+198h+var_60], rax
0x1c015d9d0  cmp     esi, 0C0000188h
0x1c015d9d6  jz      loc_1C015DA89
0x1c015d9dc  test    rbx, rbx
0x1c015d9df  jz      short loc_1C015D9E9
0x1c015d9e1  mov     rcx, rbx
0x1c015d9e4  call    RefsPreRequestProcessingExtend
0x1c015d9e9  lea     rax, [rsp+198h+Event]
0x1c015d9ee  mov     [rsp+198h+var_C0], rax
0x1c015d9f6  or      dword ptr [rbx+8], 10002h
0x1c015d9fd  mov     rdx, rdi
0x1c015da00  mov     rcx, rbx; int
0x1c015da03  test    dword ptr [rbx+8], 200h
0x1c015da0a  jnz     short loc_1C015DA7C
0x1c015da0c  lea     r8, [rsp+198h+var_108]
0x1c015da14  call    RefsCommonCreateOnNewStack
0x1c015da19  mov     esi, eax
0x1c015da1b  mov     [rsp+198h+Status], eax
0x1c015da1f  cmp     eax, r14d
0x1c015da22  jnz     short loc_1C015DA96
0x1c015da24  bts     dword ptr [rbx+4], 0Ah
0x1c015da29  mov     al, cs:RefsStatusDebugEnabled
0x1c015da2f  test    al, al
0x1c015da31  jz      short loc_1C015DA48
0x1c015da33  mov     r8d, 460h
0x1c015da39  lea     rdx, aCreateC; "Create.c"
0x1c015da40  mov     ecx, r14d; Status
0x1c015da43  call    RefsStatusDebug
0x1c015da48  mov     r8d, r14d
0x1c015da4b  xor     edx, edx
0x1c015da4d  mov     rbx, qword ptr [rsp+198h+var_170]
0x1c015da52  mov     rcx, rbx
0x1c015da55  call    RefsExtendedCompleteRequestInternal
0x1c015da5a  mov     rdx, [rsp+198h+var_C0]
0x1c015da62  mov     rcx, rdi; Irp
0x1c015da65  call    RefsWaitForCreateEvent
0x1c015da6a  mov     rax, [rsp+198h+var_60]
0x1c015da72  and     byte ptr [rax+3], 0FEh
0x1c015da76  mov     esi, [rsp+198h+Status]
0x1c015da7a  jmp     short loc_1C015DA96
0x1c015da7c  call    RefsCommonVolumeOpen
0x1c015da81  mov     esi, eax
0x1c015da83  mov     [rsp+198h+Status], eax
0x1c015da87  jmp     short loc_1C015DA96
0x1c015da89  mov     rcx, rbx
0x1c015da8c  call    RefsCheckpointForLogFileFull
0x1c015da91  jmp     loc_1C015D9DC
0x1c015da96  jmp     short loc_1C015DAD5
0x1c015da98  mov     rbx, qword ptr [rsp+198h+var_170]
0x1c015da9d  test    rbx, rbx
0x1c015daa0  jz      short loc_1C015DAB1
0x1c015daa2  lea     rcx, [rsp+198h+var_108]
0x1c015daaa  mov     [rbx+90h], rcx
0x1c015dab1  mov     r8d, eax
0x1c015dab4  mov     rdi, [rsp+198h+var_158]
0x1c015dab9  mov     rdx, rdi
0x1c015dabc  mov     rcx, rbx
0x1c015dabf  call    RefsProcessException
0x1c015dac4  mov     esi, eax
0x1c015dac6  mov     [rsp+198h+Status], eax
0x1c015daca  mov     r14d, 367h
0x1c015dad0  mov     r15d, [rsp+198h+var_168]
0x1c015dad5  cmp     esi, 0C00000D8h
0x1c015dadb  jz      loc_1C015D9AC
0x1c015dae1  cmp     esi, 0C00001A8h
0x1c015dae7  jz      loc_1C015D9AC
0x1c015daed  cmp     esi, 0C0000188h
0x1c015daf3  jz      loc_1C015D9AC
0x1c015daf9  cmp     esi, r14d
0x1c015dafc  jz      loc_1C015D9AC
0x1c015db02  cmp     esi, 103h
0x1c015db08  jz      short loc_1C015DB84
0x1c015db0a  btr     dword ptr [rbx+8], 10h
0x1c015db0f  mov     al, cs:RefsStatusDebugEnabled
0x1c015db15  test    al, al
0x1c015db17  jz      short loc_1C015DB2F
0x1c015db19  mov     r8d, 58Eh
0x1c015db1f  lea     rdx, aCreateC; "Create.c"
0x1c015db26  mov     ecx, [rsp+198h+Status]; Status
0x1c015db2a  call    RefsStatusDebug
0x1c015db2f  mov     r8d, [rsp+198h+Status]
0x1c015db34  mov     rdx, rdi
0x1c015db37  mov     rcx, qword ptr [rsp+198h+var_170]
0x1c015db3c  call    RefsExtendedCompleteRequestInternal
0x1c015db41  test    r15d, r15d
0x1c015db44  jnz     loc_1C0183A86
0x1c015db4a  call    cs:__imp_KeLeaveCriticalRegion
0x1c015db51  nop     dword ptr [rax+rax+00h]
0x1c015db56  mov     eax, [rsp+198h+Status]
0x1c015db5a  mov     rcx, [rsp+198h+var_28]
0x1c015db62  xor     rcx, rsp; StackCookie
0x1c015db65  call    __security_check_cookie
0x1c015db6a  lea     r11, [rsp+198h+var_18]
0x1c015db72  mov     rbx, [r11+20h]
0x1c015db76  mov     rsi, [r11+30h]
0x1c015db7a  mov     rsp, r11
0x1c015db7d  pop     r15
0x1c015db7f  pop     r14
0x1c015db81  pop     rdi
0x1c015db82  retn
0x1c015db84  lea     rdx, [rsp+198h+Event]
0x1c015db89  mov     rcx, rdi; Irp
0x1c015db8c  call    RefsWaitForCreateEvent
0x1c015db91  mov     eax, [rdi+30h]
0x1c015db94  mov     [rsp+198h+Status], eax
0x1c015db98  mov     rax, [rdi+0B8h]
0x1c015db9f  mov     [rsp+198h+var_60], rax
0x1c015dba7  and     byte ptr [rax+3], 0FEh
0x1c015dbab  jmp     loc_1C015DB0A
0x1c017ea7e  push    rbp
0x1c017ea80  sub     rsp, 20h
0x1c017ea84  mov     rbp, rdx
0x1c017ea87  mov     rdx, rcx
0x1c017ea8a  mov     rcx, [rbp+28h]
0x1c017ea8e  call    RefsExceptionFilter
0x1c017ea93  nop
0x1c017ea94  add     rsp, 20h
0x1c017ea98  pop     rbp
0x1c017ea99  retn
0x1c0183a2c  and     dword ptr [rdx+30h], 0
0x1c0183a30  mov     ebx, 1
0x1c0183a35  mov     [rdx+38h], rbx
0x1c0183a39  mov     dl, bl; PriorityBoost
0x1c0183a3b  mov     rcx, rdi; Irp
0x1c0183a3e  call    cs:__imp_IofCompleteRequest
0x1c0183a45  nop     dword ptr [rax+rax+00h]
0x1c0183a4a  xor     eax, eax
0x1c0183a4c  jmp     loc_1C015DB5A
0x1c0183a51  mov     al, cs:RefsStatusDebugEnabled
0x1c0183a57  test    al, al
0x1c0183a59  jz      short loc_1C0183A71
0x1c0183a5b  mov     r8d, 40Dh
0x1c0183a61  lea     rdx, aCreateC; "Create.c"
0x1c0183a68  mov     ecx, [rsp+198h+Status]; Status
0x1c0183a6c  call    RefsStatusDebug
0x1c0183a71  mov     r8d, [rsp+198h+Status]
0x1c0183a76  mov     rdx, rdi
0x1c0183a79  xor     ecx, ecx
0x1c0183a7b  call    RefsExtendedCompleteRequestInternal
0x1c0183a80  nop
0x1c0183a81  jmp     loc_1C015DB56
0x1c0183a86  mov     rcx, [rsp+198h+var_160]
0x1c0183a8b  call    cs:__imp_IoClearActivityIdThread
0x1c0183a92  nop     dword ptr [rax+rax+00h]
0x1c0183a97  nop
0x1c0183a98  jmp     loc_1C015DB4A
```
