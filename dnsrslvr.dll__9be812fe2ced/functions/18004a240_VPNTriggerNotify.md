# VPNTriggerNotify

- ea: `0x18004a240`
- end: `0x18004a3cb`
- name: `VPNTriggerNotify`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180046ec0`
- `0x180049474`
- `0x18004a240`
- `0x18004a3d4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a279`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18004a279`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a2b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a347`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a2b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004a347`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a2bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a2bf`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004a31e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004a31e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a33a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004a33a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a354`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a354`

## pseudocode

```c
void __fastcall VPNTriggerNotify(__int64 a1)
{
  int v2; // edi
  int v3; // ebp
  HANDLE v4; // rax
  int v5; // esi
  int v6; // eax
  __int64 v7; // rbx
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  LPCWSTR lpName; // [rsp+28h] [rbp-30h] BYREF

  v2 = 0;
  lpName = 0;
  v8 = 0;
  AcquireSRWLockShared(&stru_1800ABCA8);
  v3 = 1;
  if ( (Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(MS_VPN_PLGN_PLATFORM_Operational_Context, VpnAutoTriggerNRPTQuery, a1);
  v4 = qword_1800ABCA0;
  if ( !qword_1800ABCA0 )
  {
    ReleaseSRWLockShared(&stru_1800ABCA8);
    v3 = 0;
    AcquireSRWLockExclusive(&stru_1800ABCA8);
    v4 = qword_1800ABCA0;
    v2 = 1;
    if ( !qword_1800ABCA0 )
    {
      v5 = 0;
      v6 = VPNTriggerOpenBFEEngineHandle(&v8);
      v7 = v8;
      if ( v6
        || !qword_1800ABCD0
        || (unsigned int)qword_1800ABCD0(v8, &lpName)
        || (v5 = 1, (v4 = OpenEventW(2u, 0, lpName)) == 0) )
      {
        if ( v7 )
        {
          if ( v5 && qword_1800ABCD8 )
            qword_1800ABCD8(v7);
          if ( qword_1800ABCC8 )
            qword_1800ABCC8(v7);
        }
        goto LABEL_13;
      }
      qword_1800ABC98 = v7;
      qword_1800ABCA0 = v4;
    }
  }
  SetEvent(v4);
  if ( v3 )
    ReleaseSRWLockShared(&stru_1800ABCA8);
  if ( v2 )
LABEL_13:
    ReleaseSRWLockExclusive(&stru_1800ABCA8);
  if ( lpName )
  {
    if ( qword_1800ABCE0 )
      qword_1800ABCE0(&lpName);
  }
}

```

## disassembly

```asm
0x18004a240  mov     r11, rsp
0x18004a243  mov     [r11+10h], rbx
0x18004a247  mov     [r11+18h], rbp
0x18004a24b  push    rsi
0x18004a24c  push    rdi
0x18004a24d  push    r15
0x18004a24f  sub     rsp, 40h
0x18004a253  mov     rax, cs:__security_cookie
0x18004a25a  xor     rax, rsp
0x18004a25d  mov     [rsp+58h+var_28], rax
0x18004a262  mov     rbx, rcx
0x18004a265  lea     r15, stru_1800ABCA8
0x18004a26c  xor     edi, edi
0x18004a26e  mov     rcx, r15; SRWLock
0x18004a271  mov     [r11-30h], rdi
0x18004a275  mov     [r11-38h], rdi
0x18004a279  call    cs:__imp_AcquireSRWLockShared
0x18004a27f  test    cs:Microsoft_Windows_Networking_VPN_Plugin_PlatformEnableBits, 8
0x18004a286  lea     ebp, [rdi+1]
0x18004a289  jz      short loc_18004A2A1
0x18004a28b  mov     r8, rbx
0x18004a28e  lea     rdx, VpnAutoTriggerNRPTQuery
0x18004a295  lea     rcx, MS_VPN_PLGN_PLATFORM_Operational_Context
0x18004a29c  call    McTemplateU0z_EventWriteTransfer
0x18004a2a1  mov     rax, cs:qword_1800ABCA0
0x18004a2a8  test    rax, rax
0x18004a2ab  jnz     loc_18004A337
0x18004a2b1  mov     rcx, r15; SRWLock
0x18004a2b4  call    cs:__imp_ReleaseSRWLockShared
0x18004a2ba  mov     rcx, r15; SRWLock
0x18004a2bd  xor     ebp, ebp
0x18004a2bf  call    cs:__imp_AcquireSRWLockExclusive
0x18004a2c5  mov     rax, cs:qword_1800ABCA0
0x18004a2cc  lea     edi, [rbp+1]
0x18004a2cf  test    rax, rax
0x18004a2d2  jnz     short loc_18004A337
0x18004a2d4  lea     rcx, [rsp+58h+var_38]
0x18004a2d9  xor     esi, esi
0x18004a2db  call    VPNTriggerOpenBFEEngineHandle
0x18004a2e0  mov     rbx, [rsp+58h+var_38]
0x18004a2e5  test    eax, eax
0x18004a2e7  jnz     loc_18004A398
0x18004a2ed  mov     rax, cs:qword_1800ABCD0
0x18004a2f4  test    rax, rax
0x18004a2f7  jz      loc_18004A398
0x18004a2fd  lea     rdx, [rsp+58h+lpName]
0x18004a302  mov     rcx, rbx
0x18004a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a30a  test    eax, eax
0x18004a30c  jnz     loc_18004A398
0x18004a312  mov     r8, [rsp+58h+lpName]; lpName
0x18004a317  lea     ecx, [rbp+2]; dwDesiredAccess
0x18004a31a  xor     edx, edx; bInheritHandle
0x18004a31c  mov     esi, edi
0x18004a31e  call    cs:__imp_OpenEventW
0x18004a324  test    rax, rax
0x18004a327  jz      short loc_18004A398
0x18004a329  mov     cs:qword_1800ABC98, rbx
0x18004a330  mov     cs:qword_1800ABCA0, rax
0x18004a337  mov     rcx, rax; hEvent
0x18004a33a  call    cs:__imp_SetEvent
0x18004a340  test    ebp, ebp
0x18004a342  jz      short loc_18004A34D
0x18004a344  mov     rcx, r15; SRWLock
0x18004a347  call    cs:__imp_ReleaseSRWLockShared
0x18004a34d  test    edi, edi
0x18004a34f  jz      short loc_18004A35A
0x18004a351  mov     rcx, r15; SRWLock
0x18004a354  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a35a  cmp     [rsp+58h+lpName], 0
0x18004a360  jz      short loc_18004A378
0x18004a362  mov     rax, cs:qword_1800ABCE0
0x18004a369  test    rax, rax
0x18004a36c  jz      short loc_18004A378
0x18004a36e  lea     rcx, [rsp+58h+lpName]
0x18004a373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a378  mov     rcx, [rsp+58h+var_28]
0x18004a37d  xor     rcx, rsp; StackCookie
0x18004a380  call    __security_check_cookie
0x18004a385  mov     rbx, [rsp+58h+arg_8]
0x18004a38a  mov     rbp, [rsp+58h+arg_10]
0x18004a38f  add     rsp, 40h
0x18004a393  pop     r15
0x18004a395  pop     rdi
0x18004a396  pop     rsi
0x18004a397  retn
0x18004a398  test    rbx, rbx
0x18004a39b  jz      short loc_18004A351
0x18004a39d  test    esi, esi
0x18004a39f  jz      short loc_18004A3B5
0x18004a3a1  mov     rax, cs:qword_1800ABCD8
0x18004a3a8  test    rax, rax
0x18004a3ab  jz      short loc_18004A3B5
0x18004a3ad  mov     rcx, rbx
0x18004a3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3b5  mov     rax, cs:qword_1800ABCC8
0x18004a3bc  test    rax, rax
0x18004a3bf  jz      short loc_18004A351
0x18004a3c1  mov     rcx, rbx
0x18004a3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a3c9  jmp     short loc_18004A351
```
