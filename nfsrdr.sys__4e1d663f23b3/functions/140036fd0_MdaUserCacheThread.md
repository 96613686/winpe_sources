# MdaUserCacheThread

- ea: `0x140036fd0`
- end: `0x14003723d`
- name: `MdaUserCacheThread`
- size: `621`
- prototype: `void __fastcall(char *StartContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000b680`
- `0x140018310`
- `0x140036fd0`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1400370b0`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400370b0`
- `ntoskrnl!KeSetEvent` at `0x14003720c`
- `ntoskrnl!KeSetEvent` at `0x14003720c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400370fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400370fc`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003721a`
- `ntoskrnl!PsTerminateSystemThread` at `0x14003721a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400371f2`
- `ntoskrnl!ExAllocatePool2` at `0x140037054`
- `ntoskrnl!ExAllocatePool2` at `0x140037054`

## string_xrefs

- `0x140036feb`: `MdaUserCacheThread`
- `0x140037120`: `CacheRefreshInterval`

## pseudocode

```c
void __fastcall MdaUserCacheThread(char *StartContext)
{
  void *Pool2; // rdi
  union _LARGE_INTEGER *Timeout; // rdx
  __int64 v4; // rax
  union _LARGE_INTEGER v5; // rax
  char v6; // al
  unsigned int v7; // [rsp+30h] [rbp-48h] BYREF
  union _LARGE_INTEGER v8; // [rsp+38h] [rbp-40h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+40h] [rbp-38h] BYREF
  char v10[24]; // [rsp+48h] [rbp-30h] BYREF

  v7 = 900;
  strcpy(v10, "MdaUserCacheThread");
  v8.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids, v10);
  Pool2 = (void *)ExAllocatePool2(258, 544, 1112696398);
  if ( Pool2 )
  {
    while ( (_InterlockedCompareExchange((volatile signed __int32 *)StartContext + 579, 0, 0) & 0x18) == 0 )
    {
      Interval.QuadPart = -50000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v8.QuadPart = 0;
    Timeout = &v8;
    while ( 1 )
    {
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)StartContext + 579, 0, 0) & 8) != 0 )
        goto LABEL_21;
      KeWaitForSingleObject(StartContext + 2264, Executive, 0, 0, Timeout);
      if ( (_InterlockedCompareExchange((volatile signed __int32 *)StartContext + 579, 0, 0) & 8) != 0 )
        goto LABEL_21;
      if ( (int)NfsReadUserRegistry(
                  &stru_140041090,
                  L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Mapping",
                  L"CacheRefreshInterval",
                  &v7) < 0 )
        break;
      v4 = v7;
      *((_DWORD *)StartContext + 578) = v7;
      if ( (_DWORD)v4 )
      {
        if ( (unsigned int)v4 < 0x12C )
        {
          *((_DWORD *)StartContext + 578) = 300;
          v4 = 300;
        }
        goto LABEL_19;
      }
      Timeout = 0;
      v5.QuadPart = 0;
LABEL_20:
      v8 = v5;
      _InterlockedOr((volatile signed __int32 *)StartContext + 579, 0x20u);
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 579, 0, 0);
      _InterlockedAnd((volatile signed __int32 *)StartContext + 579, 0xFFFFFFDF);
      if ( (v6 & 8) != 0 )
        goto LABEL_21;
    }
    *((_DWORD *)StartContext + 578) = 900;
    v4 = 900;
LABEL_19:
    Timeout = &v8;
    v5.QuadPart = -10000000 * v4;
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids, v10);
LABEL_21:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids, v10);
  _InterlockedAnd((volatile signed __int32 *)StartContext + 579, 0xFFFFFFDF);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  KeSetEvent((PRKEVENT)(StartContext + 2288), 16, 0);
  PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140036fd0  push    rbp
0x140036fd2  push    rbx
0x140036fd3  push    rdi
0x140036fd4  push    r14
0x140036fd6  mov     rbp, rsp
0x140036fd9  sub     rsp, 78h
0x140036fdd  mov     rax, cs:__security_cookie
0x140036fe4  xor     rax, rsp
0x140036fe7  mov     [rbp+var_18], rax
0x140036feb  movups  xmm0, xmmword ptr cs:aMdausercacheth; "MdaUserCacheThread"
0x140036ff2  mov     eax, dword ptr cs:aMdausercacheth+0Fh; "ead"
0x140036ff8  mov     rbx, rcx
0x140036ffb  mov     [rbp+var_48], 384h
0x140037002  movups  xmmword ptr [rbp+var_30], xmm0
0x140037006  mov     dword ptr [rbp+var_30+0Fh], eax
0x140037009  mov     qword ptr [rbp+var_40], 0
0x140037011  mov     rcx, cs:WPP_GLOBAL_Control
0x140037018  lea     r14, WPP_GLOBAL_Control
0x14003701f  cmp     rcx, r14
0x140037022  jz      short loc_140037044
0x140037024  mov     eax, [rcx+2Ch]
0x140037027  test    al, 8
0x140037029  jz      short loc_140037044
0x14003702b  mov     rcx, [rcx+18h]
0x14003702f  lea     r9, [rbp+var_30]
0x140037033  mov     edx, 14h
0x140037038  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x14003703f  call    WPP_SF_s
0x140037044  mov     edx, 220h
0x140037049  mov     ecx, 102h
0x14003704e  mov     r8d, 4252664Eh
0x140037054  call    cs:__imp_ExAllocatePool2
0x14003705b  nop     dword ptr [rax+rax+00h]
0x140037060  mov     rdi, rax
0x140037063  test    rax, rax
0x140037066  jnz     short loc_1400370BC
0x140037068  mov     rcx, cs:WPP_GLOBAL_Control
0x14003706f  cmp     rcx, r14
0x140037072  jz      loc_1400371B2
0x140037078  mov     edx, [rcx+2Ch]
0x14003707b  test    dl, 4
0x14003707e  jz      loc_1400371B2
0x140037084  mov     rcx, [rcx+18h]
0x140037088  lea     edx, [rax+15h]
0x14003708b  lea     r9, [rbp+var_30]
0x14003708f  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x140037096  call    WPP_SF_s
0x14003709b  jmp     loc_1400371B2
0x1400370a0  lea     r8, [rbp+Interval]; Interval
0x1400370a4  mov     qword ptr [rbp+Interval], 0FFFFFFFFFFFF3CB0h
0x1400370ac  xor     edx, edx; Alertable
0x1400370ae  xor     ecx, ecx; WaitMode
0x1400370b0  call    cs:__imp_KeDelayExecutionThread
0x1400370b7  nop     dword ptr [rax+rax+00h]
0x1400370bc  xor     eax, eax
0x1400370be  xor     ecx, ecx
0x1400370c0  lock cmpxchg [rbx+90Ch], ecx
0x1400370c8  test    al, 18h
0x1400370ca  jz      short loc_1400370A0
0x1400370cc  mov     qword ptr [rbp+var_40], rcx
0x1400370d0  lea     rdx, [rbp+var_40]
0x1400370d4  xor     ecx, ecx
0x1400370d6  xor     eax, eax
0x1400370d8  lock cmpxchg [rbx+90Ch], ecx
0x1400370e0  test    al, 8
0x1400370e2  jnz     loc_1400371B2
0x1400370e8  mov     [rsp+78h+Timeout], rdx; Timeout
0x1400370ed  lea     rcx, [rbx+8D8h]; Object
0x1400370f4  xor     edx, edx; WaitReason
0x1400370f6  xor     r9d, r9d; Alertable
0x1400370f9  xor     r8d, r8d; WaitMode
0x1400370fc  call    cs:__imp_KeWaitForSingleObject
0x140037103  nop     dword ptr [rax+rax+00h]
0x140037108  xor     ecx, ecx
0x14003710a  xor     eax, eax
0x14003710c  lock cmpxchg [rbx+90Ch], ecx
0x140037114  test    al, 8
0x140037116  jnz     loc_1400371B2
0x14003711c  lea     rax, [rbp+var_48]
0x140037120  lea     r8, aCacherefreshin; "CacheRefreshInterval"
0x140037127  mov     [rsp+78h+Timeout], rax; void *
0x14003712c  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140037133  lea     rcx, stru_140041090; SourceString
0x14003713a  call    NfsReadUserRegistry
0x14003713f  test    eax, eax
0x140037141  js      short loc_14003716E
0x140037143  mov     eax, [rbp+var_48]
0x140037146  mov     [rbx+908h], eax
0x14003714c  test    eax, eax
0x14003714e  jz      short loc_140037168
0x140037150  cmp     eax, 12Ch
0x140037155  jnb     short loc_14003717D
0x140037157  mov     dword ptr [rbx+908h], 12Ch
0x140037161  mov     eax, 12Ch
0x140037166  jmp     short loc_14003717D
0x140037168  xor     edx, edx
0x14003716a  xor     eax, eax
0x14003716c  jmp     short loc_140037188
0x14003716e  mov     dword ptr [rbx+908h], 384h
0x140037178  mov     eax, 384h
0x14003717d  lea     rdx, [rbp+var_40]
0x140037181  imul    rax, 0FFFFFFFFFF676980h
0x140037188  mov     qword ptr [rbp+var_40], rax
0x14003718c  lock or dword ptr [rbx+90Ch], 20h
0x140037194  xor     ecx, ecx
0x140037196  xor     eax, eax
0x140037198  lock cmpxchg [rbx+90Ch], ecx
0x1400371a0  lock and dword ptr [rbx+90Ch], 0FFFFFFDFh
0x1400371a8  bt      eax, 3
0x1400371ac  jnb     loc_1400370D4
0x1400371b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371b9  cmp     rcx, r14
0x1400371bc  jz      short loc_1400371E0
0x1400371be  test    dword ptr [rcx+2Ch], 100000h
0x1400371c5  jz      short loc_1400371E0
0x1400371c7  mov     rcx, [rcx+18h]
0x1400371cb  lea     r9, [rbp+var_30]
0x1400371cf  mov     edx, 16h
0x1400371d4  lea     r8, WPP_79d83ead2ad137bf3d81eedca2281543_Traceguids
0x1400371db  call    WPP_SF_s
0x1400371e0  lock and dword ptr [rbx+90Ch], 0FFFFFFDFh
0x1400371e8  test    rdi, rdi
0x1400371eb  jz      short loc_1400371FE
0x1400371ed  xor     edx, edx; Tag
0x1400371ef  mov     rcx, rdi; P
0x1400371f2  call    cs:__imp_ExFreePoolWithTag
0x1400371f9  nop     dword ptr [rax+rax+00h]
0x1400371fe  xor     r8d, r8d; Wait
0x140037201  lea     rcx, [rbx+8F0h]; Event
0x140037208  lea     edx, [r8+10h]; Increment
0x14003720c  call    cs:__imp_KeSetEvent
0x140037213  nop     dword ptr [rax+rax+00h]
0x140037218  xor     ecx, ecx; ExitStatus
0x14003721a  call    cs:__imp_PsTerminateSystemThread
0x140037221  nop     dword ptr [rax+rax+00h]
0x140037226  mov     rcx, [rbp+var_18]
0x14003722a  xor     rcx, rsp; StackCookie
0x14003722d  call    __security_check_cookie
0x140037232  add     rsp, 78h
0x140037236  pop     r14
0x140037238  pop     rdi
0x140037239  pop     rbx
0x14003723a  pop     rbp
0x14003723b  retn
```
