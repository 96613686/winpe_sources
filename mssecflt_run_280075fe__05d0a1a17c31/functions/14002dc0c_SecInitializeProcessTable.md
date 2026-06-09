# SecInitializeProcessTable

- ea: `0x14002dc0c`
- end: `0x14002de5f`
- name: `SecInitializeProcessTable`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a1d4`

## callees

- `0x140010587`
- `0x140011610`
- `0x140011650`
- `0x1400119c0`
- `0x14002d78c`
- `0x14002db60`
- `0x14002dc0c`
- `0x140042df0`

## import_xrefs

- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002dcd4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002dd0c`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002dcd4`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002dd0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002de14`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002de14`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dc55`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dd41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dc55`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dd41`
- `ntoskrnl!KeInitializeEvent` at `0x14002de33`
- `ntoskrnl!KeInitializeEvent` at `0x14002de33`

## pseudocode

```c
__int64 SecInitializeProcessTable()
{
  unsigned int v0; // ebx
  PVOID PoolWithTag; // rax
  PVOID v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // rax
  PVOID v7; // rcx
  PVOID P; // [rsp+48h] [rbp-20h] BYREF

  v0 = 0;
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(64, 384, 1416651603);
  else
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x180u, 0x54706353u);
  SecProcessTable = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  memset(PoolWithTag, 0, 0x180u);
  *(_WORD *)SecProcessTable = -5624;
  *((_WORD *)SecProcessTable + 1) = 384;
  FltInitializePushLock_0((PULONG_PTR)SecProcessTable + 1);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)SecProcessTable + 64), 0, 0, 0, 0x2D8u, 0x78706353u, 0);
  ExInitializePagedLookasideList((PPAGED_LOOKASIDE_LIST)((char *)SecProcessTable + 192), 0, 0, 0, 0x18u, 0x65706353u, 0);
  if ( qword_140020008 )
    v3 = (PVOID)qword_140020008(256, 2048, 1416651603);
  else
    v3 = ExAllocatePoolWithTag(PagedPool, 0x800u, 0x54706353u);
  *((_QWORD *)SecProcessTable + 40) = v3;
  if ( *((_QWORD *)SecProcessTable + 40) )
  {
    v4 = 0;
    v5 = 128;
    do
    {
      v6 = (_QWORD *)(v4 + *((_QWORD *)SecProcessTable + 40));
      v4 += 16;
      v6[1] = v6;
      *v6 = v6;
      --v5;
    }
    while ( v5 );
    *((_DWORD *)SecProcessTable + 90) = 0;
    *((_QWORD *)SecProcessTable + 46) = -1;
    if ( (int)SecGetRunningProcessIdByName(&SecSecureSystemProcessName) >= 0 )
    {
      P = 0;
      if ( (int)SecGetProcessNameByPid(0, &P) >= 0 )
      {
        v7 = P;
        if ( *(_WORD *)P <= 4u )
        {
          *((_QWORD *)SecProcessTable + 46) = 0;
          v7 = P;
        }
        ExFreePoolWithTag(v7, 0);
      }
    }
    KeInitializeEvent((PRKEVENT)SecProcessTable + 14, NotificationEvent, 1u);
    SecInitializePhase1InitCompleteCallback();
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v0;
}

```

## disassembly

```asm
0x14002dc0c  mov     [rsp+arg_0], rbx
0x14002dc11  push    rsi
0x14002dc12  sub     rsp, 60h
0x14002dc16  mov     rax, cs:__security_cookie
0x14002dc1d  xor     rax, rsp
0x14002dc20  mov     [rsp+68h+var_18], rax
0x14002dc25  mov     rax, cs:qword_140020008
0x14002dc2c  xor     ebx, ebx
0x14002dc2e  mov     [rsp+68h+var_28], rbx
0x14002dc33  mov     esi, 180h
0x14002dc38  mov     r8d, 54706353h; Tag
0x14002dc3e  mov     edx, esi; NumberOfBytes
0x14002dc40  test    rax, rax
0x14002dc43  jz      short loc_14002DC50
0x14002dc45  lea     ecx, [rbx+40h]
0x14002dc48  call    cs:__guard_dispatch_icall_fptr
0x14002dc4e  jmp     short loc_14002DC61
0x14002dc50  mov     ecx, 200h; PoolType
0x14002dc55  call    cs:__imp_ExAllocatePoolWithTag
0x14002dc5c  nop     dword ptr [rax+rax+00h]
0x14002dc61  mov     cs:SecProcessTable, rax
0x14002dc68  test    rax, rax
0x14002dc6b  jnz     short loc_14002DC77
0x14002dc6d  mov     eax, 0C000009Ah
0x14002dc72  jmp     loc_14002DE46
0x14002dc77  mov     r8, rsi; Size
0x14002dc7a  xor     edx, edx; Val
0x14002dc7c  mov     rcx, rax; void *
0x14002dc7f  call    memset
0x14002dc84  mov     rax, cs:SecProcessTable
0x14002dc8b  mov     word ptr [rax], 0EA08h
0x14002dc90  mov     rax, cs:SecProcessTable
0x14002dc97  mov     [rax+2], si
0x14002dc9b  mov     rcx, cs:SecProcessTable
0x14002dca2  add     rcx, 8; PushLock
0x14002dca6  call    FltInitializePushLock_0
0x14002dcab  mov     rcx, cs:SecProcessTable
0x14002dcb2  xor     r9d, r9d; Flags
0x14002dcb5  mov     [rsp+68h+Depth], bx; Depth
0x14002dcba  add     rcx, 40h ; '@'; Lookaside
0x14002dcbe  mov     [rsp+68h+Tag], 78706353h; Tag
0x14002dcc6  xor     r8d, r8d; Free
0x14002dcc9  xor     edx, edx; Allocate
0x14002dccb  mov     [rsp+68h+Size], 2D8h; Size
0x14002dcd4  call    cs:__imp_ExInitializePagedLookasideList
0x14002dcdb  nop     dword ptr [rax+rax+00h]
0x14002dce0  mov     rcx, cs:SecProcessTable
0x14002dce7  xor     r9d, r9d; Flags
0x14002dcea  mov     [rsp+68h+Depth], bx; Depth
0x14002dcef  add     rcx, 0C0h; Lookaside
0x14002dcf6  mov     [rsp+68h+Tag], 65706353h; Tag
0x14002dcfe  xor     r8d, r8d; Free
0x14002dd01  xor     edx, edx; Allocate
0x14002dd03  mov     [rsp+68h+Size], 18h; Size
0x14002dd0c  call    cs:__imp_ExInitializePagedLookasideList
0x14002dd13  nop     dword ptr [rax+rax+00h]
0x14002dd18  mov     rax, cs:qword_140020008
0x14002dd1f  mov     edx, 800h; NumberOfBytes
0x14002dd24  mov     r8d, 54706353h; Tag
0x14002dd2a  test    rax, rax
0x14002dd2d  jz      short loc_14002DD3C
0x14002dd2f  mov     ecx, 100h
0x14002dd34  call    cs:__guard_dispatch_icall_fptr
0x14002dd3a  jmp     short loc_14002DD4D
0x14002dd3c  mov     ecx, 1; PoolType
0x14002dd41  call    cs:__imp_ExAllocatePoolWithTag
0x14002dd48  nop     dword ptr [rax+rax+00h]
0x14002dd4d  mov     rcx, rax
0x14002dd50  mov     rax, cs:SecProcessTable
0x14002dd57  mov     [rax+140h], rcx
0x14002dd5e  mov     rax, cs:SecProcessTable
0x14002dd65  cmp     [rax+140h], rbx
0x14002dd6c  jnz     short loc_14002DD78
0x14002dd6e  mov     ebx, 0C000009Ah
0x14002dd73  jmp     loc_14002DE44
0x14002dd78  mov     rdx, rbx
0x14002dd7b  mov     r8d, 80h
0x14002dd81  mov     rax, cs:SecProcessTable
0x14002dd88  mov     rax, [rax+140h]
0x14002dd8f  add     rax, rdx
0x14002dd92  add     rdx, 10h
0x14002dd96  mov     [rax+8], rax
0x14002dd9a  mov     [rax], rax
0x14002dd9d  sub     r8, 1
0x14002dda1  jnz     short loc_14002DD81
0x14002dda3  mov     rax, cs:SecProcessTable
0x14002ddaa  lea     rdx, [rsp+68h+var_28]
0x14002ddaf  lea     rcx, SecSecureSystemProcessName; String1
0x14002ddb6  mov     [rax+168h], ebx
0x14002ddbc  mov     rax, cs:SecProcessTable
0x14002ddc3  mov     qword ptr [rax+170h], 0FFFFFFFFFFFFFFFFh
0x14002ddce  call    SecGetRunningProcessIdByName
0x14002ddd3  test    eax, eax
0x14002ddd5  js      short loc_14002DE20
0x14002ddd7  mov     rcx, [rsp+68h+var_28]
0x14002dddc  lea     rdx, [rsp+68h+P]
0x14002dde1  mov     [rsp+68h+P], rbx
0x14002dde6  call    SecGetProcessNameByPid
0x14002ddeb  test    eax, eax
0x14002dded  js      short loc_14002DE20
0x14002ddef  mov     rcx, [rsp+68h+P]
0x14002ddf4  cmp     word ptr [rcx], 4
0x14002ddf8  ja      short loc_14002DE12
0x14002ddfa  mov     rcx, [rsp+68h+var_28]
0x14002ddff  mov     rax, cs:SecProcessTable
0x14002de06  mov     [rax+170h], rcx
0x14002de0d  mov     rcx, [rsp+68h+P]; P
0x14002de12  xor     edx, edx; Tag
0x14002de14  call    cs:__imp_ExFreePoolWithTag
0x14002de1b  nop     dword ptr [rax+rax+00h]
0x14002de20  mov     rcx, cs:SecProcessTable
0x14002de27  mov     r8b, 1; State
0x14002de2a  add     rcx, 150h; Event
0x14002de31  xor     edx, edx; Type
0x14002de33  call    cs:__imp_KeInitializeEvent
0x14002de3a  nop     dword ptr [rax+rax+00h]
0x14002de3f  call    SecInitializePhase1InitCompleteCallback
0x14002de44  mov     eax, ebx
0x14002de46  mov     rcx, [rsp+68h+var_18]
0x14002de4b  xor     rcx, rsp; StackCookie
0x14002de4e  call    __security_check_cookie
0x14002de53  mov     rbx, [rsp+68h+arg_0]
0x14002de58  add     rsp, 60h
0x14002de5c  pop     rsi
0x14002de5d  retn
```
