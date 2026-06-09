# KsecIoctlClientCallback(void *,ulong,void *,ulong,ulong *)

- ea: `0x18000d01c`
- end: `0x18000d2e8`
- name: `?KsecIoctlClientCallback@@YAJPEAXK0KPEAK@Z`
- size: `716`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800053e0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180007a64`
- `0x180007ba8`
- `0x180007bd8`
- `0x18000d01c`
- `0x18000e044`
- `0x180010980`
- `0x18001f520`

## import_xrefs

- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000d214`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x18000d214`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d0ce`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d1a5`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d0ce`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x18000d1a5`
- `ntoskrnl!ProbeForRead` at `0x18000d0f3`
- `ntoskrnl!ProbeForRead` at `0x18000d114`
- `ntoskrnl!ProbeForRead` at `0x18000d0f3`
- `ntoskrnl!ProbeForRead` at `0x18000d114`

## pseudocode

```c
__int64 __fastcall KsecIoctlClientCallback(void *Src, int a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v9; // r8
  int v10; // ebx
  __int128 Srca; // [rsp+38h] [rbp-70h] BYREF
  __int128 v13; // [rsp+48h] [rbp-60h] BYREF
  __int128 v14; // [rsp+58h] [rbp-50h]
  __int128 Length; // [rsp+68h] [rbp-40h] BYREF
  __int64 v16; // [rsp+B0h] [rbp+8h] BYREF

  v13 = 0;
  v14 = 0;
  Length = 0;
  Srca = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
  if ( Src && a3 && (v9 = 48, a2 == 48) )
  {
    if ( a4 < 0x10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 38, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, a4);
      v10 = -1073741789;
      goto LABEL_26;
    }
    if ( !v16 )
    {
      v10 = -1073741058;
LABEL_26:
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
      return (unsigned int)v10;
    }
    v10 = -1073741822;
    if ( ((unsigned __int8)Src & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(&v13, Src, 0x30u);
    ProbeForRead(a3, 0x10u, 8u);
    if ( (_DWORD)Length )
      ProbeForRead(*((volatile void **)&Length + 1), (unsigned int)Length, 1u);
    if ( (_DWORD)v13 == 3 )
    {
      if ( WPP_MAIN_CB.DeviceObjectExtension && *(_QWORD *)WPP_MAIN_CB.DeviceObjectExtension )
      {
        v10 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int128 *, __int128 *))WPP_MAIN_CB.DeviceObjectExtension->Type)(
                *((_QWORD *)&v13 + 1),
                v14,
                *((_QWORD *)&v14 + 1),
                &Length,
                &Srca);
      }
      else
      {
        v10 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 3), 39, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids);
      }
    }
    if ( v10 < 0 )
      goto LABEL_26;
    if ( ((unsigned __int8)a3 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyToUser(a3, &Srca, 0x10u);
    *a5 = 16;
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qqL(*((_QWORD *)WPP_GLOBAL_Control + 3), 37, v9, Src, a3, a2);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v16);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x18000d01c  mov     rax, rsp
0x18000d01f  push    rbx
0x18000d020  push    rsi
0x18000d021  push    rdi
0x18000d022  push    r14
0x18000d024  sub     rsp, 88h
0x18000d02b  mov     r14d, r9d
0x18000d02e  mov     rdi, r8
0x18000d031  mov     ebx, edx
0x18000d033  mov     rsi, rcx
0x18000d036  xorps   xmm0, xmm0
0x18000d039  movups  xmmword ptr [rax-60h], xmm0
0x18000d03d  movups  xmmword ptr [rax-50h], xmm0
0x18000d041  movups  xmmword ptr [rax-40h], xmm0
0x18000d045  movups  xmmword ptr [rax-70h], xmm0
0x18000d049  lea     rcx, [rax+8]; this
0x18000d04d  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x18000d052  test    rsi, rsi
0x18000d055  jz      loc_18000D294
0x18000d05b  test    rdi, rdi
0x18000d05e  jz      loc_18000D294
0x18000d064  mov     r8d, 30h ; '0'
0x18000d06a  cmp     ebx, r8d
0x18000d06d  jnz     loc_18000D294
0x18000d073  cmp     r14d, 10h
0x18000d077  jnb     short loc_18000D0B4
0x18000d079  lea     rax, WPP_GLOBAL_Control
0x18000d080  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d087  cmp     rcx, rax
0x18000d08a  jz      short loc_18000D0AA
0x18000d08c  mov     eax, [rcx+2Ch]
0x18000d08f  test    al, 1
0x18000d091  jz      short loc_18000D0AA
0x18000d093  lea     edx, [r8-0Ah]
0x18000d097  mov     r9d, r14d
0x18000d09a  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000d0a1  mov     rcx, [rcx+18h]
0x18000d0a5  call    WPP_SF_D
0x18000d0aa  mov     ebx, 0C0000023h
0x18000d0af  jmp     loc_18000D283
0x18000d0b4  cmp     [rsp+0A8h+arg_0], 0
0x18000d0bd  jz      loc_18000D27E
0x18000d0c3  mov     ebx, 0C0000002h
0x18000d0c8  test    sil, 7
0x18000d0cc  jz      short loc_18000D0DA
0x18000d0ce  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000d0d5  nop     dword ptr [rax+rax+00h]
0x18000d0da  mov     rdx, rsi; Src
0x18000d0dd  lea     rcx, [rsp+0A8h+var_60]; void *
0x18000d0e2  call    RtlCopyFromUser
0x18000d0e7  mov     edx, 10h; Length
0x18000d0ec  lea     r8d, [rdx-8]; Alignment
0x18000d0f0  mov     rcx, rdi; Address
0x18000d0f3  call    cs:__imp_ProbeForRead
0x18000d0fa  nop     dword ptr [rax+rax+00h]
0x18000d0ff  mov     eax, dword ptr [rsp+0A8h+Length]
0x18000d103  test    eax, eax
0x18000d105  jz      short loc_18000D121
0x18000d107  mov     edx, eax; Length
0x18000d109  mov     r8d, 1; Alignment
0x18000d10f  mov     rcx, [rsp+0A8h+Address]; Address
0x18000d114  call    cs:__imp_ProbeForRead
0x18000d11b  nop     dword ptr [rax+rax+00h]
0x18000d120  nop
0x18000d121  cmp     [rsp+0A8h+var_60], 3
0x18000d126  jnz     short loc_18000D197
0x18000d128  mov     rax, cs:WPP_MAIN_CB.DeviceObjectExtension
0x18000d12f  test    rax, rax
0x18000d132  jz      short loc_18000D163
0x18000d134  mov     rax, [rax]
0x18000d137  test    rax, rax
0x18000d13a  jz      short loc_18000D163
0x18000d13c  lea     rcx, [rsp+0A8h+Src]
0x18000d141  mov     [rsp+0A8h+var_88], rcx
0x18000d146  lea     r9, [rsp+0A8h+Length]
0x18000d14b  mov     r8, [rsp+0A8h+var_48]
0x18000d150  mov     rdx, [rsp+0A8h+var_50]
0x18000d155  mov     rcx, [rsp+0A8h+var_58]
0x18000d15a  call    _guard_dispatch_icall
0x18000d15f  mov     ebx, eax
0x18000d161  jmp     short loc_18000D197
0x18000d163  mov     ebx, 0C00000BBh
0x18000d168  lea     rax, WPP_GLOBAL_Control
0x18000d16f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d176  cmp     rcx, rax
0x18000d179  jz      short loc_18000D197
0x18000d17b  mov     eax, [rcx+2Ch]
0x18000d17e  test    al, 4
0x18000d180  jz      short loc_18000D197
0x18000d182  mov     edx, 27h ; '''
0x18000d187  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000d18e  mov     rcx, [rcx+18h]
0x18000d192  call    WPP_SF_
0x18000d197  test    ebx, ebx
0x18000d199  js      loc_18000D283
0x18000d19f  test    dil, 7
0x18000d1a3  jz      short loc_18000D1B1
0x18000d1a5  call    cs:__imp_ExRaiseDatatypeMisalignment
0x18000d1ac  nop     dword ptr [rax+rax+00h]
0x18000d1b1  mov     r8d, 10h; Size
0x18000d1b7  lea     rdx, [rsp+0A8h+Src]; Src
0x18000d1bc  mov     rcx, rdi; void *
0x18000d1bf  call    RtlCopyToUser
0x18000d1c4  nop
0x18000d1c5  mov     rax, [rsp+0A8h+arg_20]
0x18000d1cd  mov     dword ptr [rax], 10h
0x18000d1d3  lea     rcx, [rsp+0A8h+arg_0]; this
0x18000d1db  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d1e0  xor     eax, eax
0x18000d1e2  jmp     loc_18000D2DA
0x18000d1e7  cmp     [rsp+0A8h+BaseAddress], 0
0x18000d1ed  jz      short loc_18000D256
0x18000d1ef  mov     [rsp+0A8h+RegionSize], 0
0x18000d1f8  mov     r9d, 8000h; FreeType
0x18000d1fe  lea     r8, [rsp+0A8h+RegionSize]; RegionSize
0x18000d203  lea     rdx, [rsp+0A8h+BaseAddress]; BaseAddress
0x18000d208  mov     rcx, [rsp+0A8h+arg_0]
0x18000d210  mov     rcx, [rcx+8]; ProcessHandle
0x18000d214  call    cs:__imp_ZwFreeVirtualMemory
0x18000d21b  nop     dword ptr [rax+rax+00h]
0x18000d220  mov     r9d, eax
0x18000d223  test    eax, eax
0x18000d225  jns     short loc_18000D256
0x18000d227  lea     rax, WPP_GLOBAL_Control
0x18000d22e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d235  cmp     rcx, rax
0x18000d238  jz      short loc_18000D256
0x18000d23a  mov     eax, [rcx+2Ch]
0x18000d23d  test    al, 1
0x18000d23f  jz      short loc_18000D256
0x18000d241  mov     edx, 28h ; '('
0x18000d246  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000d24d  mov     rcx, [rcx+18h]
0x18000d251  call    WPP_SF_D
0x18000d256  lea     rcx, [rsp+0A8h+arg_0]; this
0x18000d25e  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d263  mov     eax, 0C0000005h
0x18000d268  jmp     short loc_18000D2DA
0x18000d26a  lea     rcx, [rsp+0A8h+arg_0]; this
0x18000d272  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d277  mov     eax, 0C0000005h
0x18000d27c  jmp     short loc_18000D2DA
0x18000d27e  mov     ebx, 0C00002FEh
0x18000d283  lea     rcx, [rsp+0A8h+arg_0]; this
0x18000d28b  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d290  mov     eax, ebx
0x18000d292  jmp     short loc_18000D2DA
0x18000d294  lea     rax, WPP_GLOBAL_Control
0x18000d29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2a2  cmp     rcx, rax
0x18000d2a5  jz      short loc_18000D2C8
0x18000d2a7  mov     eax, [rcx+2Ch]
0x18000d2aa  test    al, 1
0x18000d2ac  jz      short loc_18000D2C8
0x18000d2ae  mov     edx, 25h ; '%'
0x18000d2b3  mov     [rsp+0A8h+var_80], ebx
0x18000d2b7  mov     [rsp+0A8h+var_88], rdi
0x18000d2bc  mov     r9, rsi
0x18000d2bf  mov     rcx, [rcx+18h]
0x18000d2c3  call    WPP_SF_qqL
0x18000d2c8  lea     rcx, [rsp+0A8h+arg_0]; this
0x18000d2d0  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000d2d5  mov     eax, 0C000000Dh
0x18000d2da  add     rsp, 88h
0x18000d2e1  pop     r14
0x18000d2e3  pop     rdi
0x18000d2e4  pop     rsi
0x18000d2e5  pop     rbx
0x18000d2e6  retn
```
