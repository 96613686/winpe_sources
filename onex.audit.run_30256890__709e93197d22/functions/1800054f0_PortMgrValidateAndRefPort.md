# PortMgrValidateAndRefPort

- ea: `0x1800054f0`
- end: `0x180005633`
- name: `PortMgrValidateAndRefPort`
- size: `323`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180003c80`
- `0x180005640`
- `0x18000e230`
- `0x18000f8c0`

## callees

- `0x180005440`
- `0x1800054f0`
- `0x1800214f0`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x1800055cb`
- `MobileNetworking!ReleaseWriteLock` at `0x1800055ee`
- `MobileNetworking!ReleaseWriteLock` at `0x1800055cb`
- `MobileNetworking!ReleaseWriteLock` at `0x1800055ee`
- `MobileNetworking!AcquireWriteLock` at `0x180005587`
- `MobileNetworking!AcquireWriteLock` at `0x180005587`

## pseudocode

```c
__int64 __fastcall PortMgrValidateAndRefPort(__int64 a1)
{
  _QWORD *v2; // rcx
  unsigned int v3; // ebx
  __int64 i; // rax

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 54, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    AcquireWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 633);
    for ( i = qword_18003DD68; (__int64 *)i != &qword_18003DD68; i = *(_QWORD *)i )
    {
      if ( a1 == i )
      {
        v3 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(i + 16));
        ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 650);
        goto LABEL_14;
      }
    }
    ReleaseWriteLock(g_OneXInfo, qword_18003DD98, "PortMgrValidateAndRefPort", 650);
    v3 = 6;
    goto LABEL_14;
  }
  v3 = 6;
  if ( v2 == &WPP_GLOBAL_Control )
    return v3;
  if ( (*((_BYTE *)v2 + 68) & 1) != 0 )
  {
    WPP_SF_(v2[7], 55, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids);
LABEL_14:
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 17) & 0x800) != 0 )
    WPP_SF_D(v2[7], 56, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x1800054f0  mov     [rsp+arg_0], rbx
0x1800054f5  push    rdi
0x1800054f6  sub     rsp, 20h
0x1800054fa  mov     rbx, rcx
0x1800054fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180005504  lea     rdi, WPP_GLOBAL_Control
0x18000550b  cmp     rcx, rdi
0x18000550e  jz      short loc_180005535
0x180005510  test    dword ptr [rcx+44h], 800h
0x180005517  jz      short loc_180005535
0x180005519  mov     rcx, [rcx+38h]
0x18000551d  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180005524  mov     edx, 36h ; '6'
0x180005529  call    WPP_SF_
0x18000552e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005535  test    rbx, rbx
0x180005538  jnz     short loc_18000556C
0x18000553a  mov     ebx, 6
0x18000553f  cmp     rcx, rdi
0x180005542  jz      loc_180005626
0x180005548  test    byte ptr [rcx+44h], 1
0x18000554c  jz      loc_180005600
0x180005552  mov     rcx, [rcx+38h]
0x180005556  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x18000555d  mov     edx, 37h ; '7'
0x180005562  call    WPP_SF_
0x180005567  jmp     loc_1800055F9
0x18000556c  mov     r9d, 279h
0x180005572  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x180005579  lea     rdx, qword_18003DD98
0x180005580  lea     rcx, g_OneXInfo
0x180005587  call    cs:__imp_AcquireWriteLock
0x18000558d  mov     rax, cs:qword_18003DD68
0x180005594  lea     rcx, qword_18003DD68
0x18000559b  cmp     rax, rcx
0x18000559e  jz      short loc_1800055D3
0x1800055a0  cmp     rbx, rax
0x1800055a3  jz      short loc_1800055AA
0x1800055a5  mov     rax, [rax]
0x1800055a8  jmp     short loc_18000559B
0x1800055aa  xor     ebx, ebx
0x1800055ac  lock inc dword ptr [rax+10h]
0x1800055b0  mov     r9d, 28Ah
0x1800055b6  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x1800055bd  lea     rdx, qword_18003DD98
0x1800055c4  lea     rcx, g_OneXInfo
0x1800055cb  call    cs:__imp_ReleaseWriteLock
0x1800055d1  jmp     short loc_1800055F9
0x1800055d3  mov     r9d, 28Ah
0x1800055d9  lea     r8, aPortmgrvalidat_0; "PortMgrValidateAndRefPort"
0x1800055e0  lea     rdx, qword_18003DD98
0x1800055e7  lea     rcx, g_OneXInfo
0x1800055ee  call    cs:__imp_ReleaseWriteLock
0x1800055f4  mov     ebx, 6
0x1800055f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180005600  cmp     rcx, rdi
0x180005603  jz      short loc_180005626
0x180005605  test    dword ptr [rcx+44h], 800h
0x18000560c  jz      short loc_180005626
0x18000560e  mov     rcx, [rcx+38h]
0x180005612  lea     r8, WPP_8e7e87f3b7d83ebea5ef6487a1a09a34_Traceguids
0x180005619  mov     edx, 38h ; '8'
0x18000561e  mov     r9d, ebx
0x180005621  call    WPP_SF_D
0x180005626  mov     eax, ebx
0x180005628  mov     rbx, [rsp+28h+arg_0]
0x18000562d  add     rsp, 20h
0x180005631  pop     rdi
0x180005632  retn
```
