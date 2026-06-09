# KsecIoctlDupLsaHandle(void *,ulong,void *,ulong,ulong *)

- ea: `0x180005160`
- end: `0x1800053d4`
- name: `?KsecIoctlDupLsaHandle@@YAJPEAXK0KPEAK@Z`
- size: `628`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, unsigned int@<edx>, void *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800053e0`

## callees

- `0x180001c00`
- `0x180001cf0`
- `0x180005160`
- `0x180007a64`
- `0x180007bd8`
- `0x18000dc78`
- `0x18000dce0`
- `0x18000e044`
- `0x18001f5c0`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x180005221`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1800052e8`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x180005221`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x1800052e8`
- `ntoskrnl!ProbeForRead` at `0x180005243`
- `ntoskrnl!ProbeForRead` at `0x180005243`
- `ntoskrnl!ZwDuplicateObject` at `0x18000528c`
- `ntoskrnl!ZwDuplicateObject` at `0x18000528c`

## pseudocode

```c
__int64 __fastcall KsecIoctlDupLsaHandle(void *Src, int a2, void *a3, unsigned int a4, unsigned int *a5)
{
  __int64 v9; // r8
  NTSTATUS v10; // ebx
  __int64 v11; // rbx
  HANDLE v13; // r8
  ULONG HandleAttributes; // eax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // r8
  HANDLE TargetHandle; // [rsp+40h] [rbp-48h] BYREF
  HANDLE SourceHandle[2]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h]
  __int64 v22; // [rsp+90h] [rbp+8h] BYREF

  *(_OWORD *)SourceHandle = 0;
  v21 = 0;
  TargetHandle = 0;
  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v22);
  if ( Src && a3 && (v9 = 24, a2 == 24) )
  {
    if ( a4 < 8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 3), 23, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids, a4);
      v10 = -1073741789;
      goto LABEL_11;
    }
    v11 = v22;
    if ( !v22 )
    {
      v10 = -1073741058;
LABEL_11:
      KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v22);
      return (unsigned int)v10;
    }
    if ( ((unsigned __int8)Src & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlCopyFromUser(SourceHandle, Src, 0x18u);
    ProbeForRead(a3, 8u, 8u);
    v13 = SourceHandle[1];
    if ( SourceHandle[1] )
    {
      HandleAttributes = 0;
    }
    else
    {
      v13 = KsecSystemProcessHandle;
      HandleAttributes = 512;
    }
    v10 = ZwDuplicateObject(*(HANDLE *)(v11 + 8), SourceHandle[0], v13, &TargetHandle, 0, HandleAttributes, 2u);
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v16 = *((unsigned int *)WPP_GLOBAL_Control + 11);
        if ( (v16 & 1) != 0 )
          WPP_SF_LqD(*((_QWORD *)WPP_GLOBAL_Control + 3), v16, v15, (unsigned int)v21, SourceHandle[0], v10);
      }
      goto LABEL_11;
    }
    if ( ((unsigned __int8)a3 & 7) != 0 )
      ExRaiseDatatypeMisalignment();
    RtlWriteULong64ToUser(a3, TargetHandle);
    *a5 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0 )
      WPP_SF_Lqq(*((_QWORD *)WPP_GLOBAL_Control + 3), v17, v18, (unsigned int)v21, SourceHandle[0], TargetHandle);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v22);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_qqL(*((_QWORD *)WPP_GLOBAL_Control + 3), 22, v9, Src, a3, a2);
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v22);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x180005160  mov     r11, rsp
0x180005163  push    rbx
0x180005164  push    rsi
0x180005165  push    rdi
0x180005166  push    r14
0x180005168  sub     rsp, 68h
0x18000516c  mov     ebx, r9d
0x18000516f  mov     rdi, r8
0x180005172  mov     r14d, edx
0x180005175  mov     rsi, rcx
0x180005178  xorps   xmm0, xmm0
0x18000517b  xor     eax, eax
0x18000517d  movups  xmmword ptr [rsp+88h+SourceHandle], xmm0
0x180005182  mov     [r11-30h], rax
0x180005186  mov     [r11-48h], rax
0x18000518a  lea     rcx, [r11+8]; this
0x18000518e  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x180005193  test    rsi, rsi
0x180005196  jz      loc_180005382
0x18000519c  test    rdi, rdi
0x18000519f  jz      loc_180005382
0x1800051a5  mov     r8d, 18h
0x1800051ab  cmp     r14d, r8d
0x1800051ae  jnz     loc_180005382
0x1800051b4  lea     r14d, [r8-10h]
0x1800051b8  cmp     ebx, r14d
0x1800051bb  jnb     short loc_1800051F5
0x1800051bd  lea     rax, WPP_GLOBAL_Control
0x1800051c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051cb  cmp     rcx, rax
0x1800051ce  jz      short loc_1800051EE
0x1800051d0  mov     eax, [rcx+2Ch]
0x1800051d3  test    al, 1
0x1800051d5  jz      short loc_1800051EE
0x1800051d7  lea     edx, [r8-1]
0x1800051db  mov     r9d, ebx
0x1800051de  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x1800051e5  mov     rcx, [rcx+18h]
0x1800051e9  call    WPP_SF_D
0x1800051ee  mov     ebx, 0C0000023h
0x1800051f3  jmp     short loc_180005207
0x1800051f5  mov     rbx, [rsp+88h+arg_0]
0x1800051fd  test    rbx, rbx
0x180005200  jnz     short loc_18000521B
0x180005202  mov     ebx, 0C00002FEh
0x180005207  lea     rcx, [rsp+88h+arg_0]; this
0x18000520f  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005214  mov     eax, ebx
0x180005216  jmp     loc_1800053C9
0x18000521b  test    sil, 7
0x18000521f  jz      short loc_18000522D
0x180005221  call    cs:__imp_ExRaiseDatatypeMisalignment
0x180005228  nop     dword ptr [rax+rax+00h]
0x18000522d  mov     rdx, rsi; Src
0x180005230  lea     rcx, [rsp+88h+SourceHandle]; void *
0x180005235  call    RtlCopyFromUser
0x18000523a  mov     r8d, r14d; Alignment
0x18000523d  mov     rdx, r14; Length
0x180005240  mov     rcx, rdi; Address
0x180005243  call    cs:__imp_ProbeForRead
0x18000524a  nop     dword ptr [rax+rax+00h]
0x18000524f  nop
0x180005250  mov     r8, [rsp+88h+SourceHandle+8]; TargetProcessHandle
0x180005255  test    r8, r8
0x180005258  jnz     short loc_180005268
0x18000525a  mov     r8, cs:KsecSystemProcessHandle
0x180005261  mov     eax, 200h
0x180005266  jmp     short loc_18000526A
0x180005268  xor     eax, eax
0x18000526a  mov     [rsp+88h+Options], 2; Options
0x180005272  mov     [rsp+88h+HandleAttributes], eax; HandleAttributes
0x180005276  mov     [rsp+88h+DesiredAccess], 0; DesiredAccess
0x18000527e  lea     r9, [rsp+88h+TargetHandle]; TargetHandle
0x180005283  mov     rdx, [rsp+88h+SourceHandle]; SourceHandle
0x180005288  mov     rcx, [rbx+8]; SourceProcessHandle
0x18000528c  call    cs:__imp_ZwDuplicateObject
0x180005293  nop     dword ptr [rax+rax+00h]
0x180005298  mov     ebx, eax
0x18000529a  test    eax, eax
0x18000529c  jns     short loc_1800052E2
0x18000529e  lea     rax, WPP_GLOBAL_Control
0x1800052a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052ac  cmp     rcx, rax
0x1800052af  jz      loc_180005207
0x1800052b5  mov     edx, [rcx+2Ch]
0x1800052b8  test    dl, 1
0x1800052bb  jz      loc_180005207
0x1800052c1  mov     [rsp+88h+HandleAttributes], ebx
0x1800052c5  mov     rax, [rsp+88h+SourceHandle]
0x1800052ca  mov     qword ptr [rsp+88h+DesiredAccess], rax
0x1800052cf  mov     r9d, dword ptr [rsp+88h+var_30]
0x1800052d4  mov     rcx, [rcx+18h]
0x1800052d8  call    WPP_SF_LqD
0x1800052dd  jmp     loc_180005207
0x1800052e2  test    dil, 7
0x1800052e6  jz      short loc_1800052F4
0x1800052e8  call    cs:__imp_ExRaiseDatatypeMisalignment
0x1800052ef  nop     dword ptr [rax+rax+00h]
0x1800052f4  mov     rdx, [rsp+88h+TargetHandle]
0x1800052f9  mov     rcx, rdi
0x1800052fc  call    RtlWriteULong64ToUser
0x180005301  nop
0x180005302  mov     rax, [rsp+88h+arg_20]
0x18000530a  mov     [rax], r14d
0x18000530d  lea     rax, WPP_GLOBAL_Control
0x180005314  mov     rcx, cs:WPP_GLOBAL_Control
0x18000531b  cmp     rcx, rax
0x18000531e  jz      short loc_180005349
0x180005320  mov     eax, [rcx+2Ch]
0x180005323  test    al, 10h
0x180005325  jz      short loc_180005349
0x180005327  mov     rax, [rsp+88h+TargetHandle]
0x18000532c  mov     qword ptr [rsp+88h+HandleAttributes], rax
0x180005331  mov     rax, [rsp+88h+SourceHandle]
0x180005336  mov     qword ptr [rsp+88h+DesiredAccess], rax
0x18000533b  mov     r9d, dword ptr [rsp+88h+var_30]
0x180005340  mov     rcx, [rcx+18h]
0x180005344  call    WPP_SF_Lqq
0x180005349  lea     rcx, [rsp+88h+arg_0]; this
0x180005351  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005356  xor     eax, eax
0x180005358  jmp     short loc_1800053C9
0x18000535a  lea     rcx, [rsp+88h+arg_0]; this
0x180005362  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180005367  mov     eax, 0C0000005h
0x18000536c  jmp     short loc_1800053C9
0x18000536e  lea     rcx, [rsp+88h+arg_0]; this
0x180005376  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000537b  mov     eax, 0C0000005h
0x180005380  jmp     short loc_1800053C9
0x180005382  lea     rax, WPP_GLOBAL_Control
0x180005389  mov     rcx, cs:WPP_GLOBAL_Control
0x180005390  cmp     rcx, rax
0x180005393  jz      short loc_1800053B7
0x180005395  mov     eax, [rcx+2Ch]
0x180005398  test    al, 1
0x18000539a  jz      short loc_1800053B7
0x18000539c  mov     edx, 16h
0x1800053a1  mov     [rsp+88h+HandleAttributes], r14d
0x1800053a6  mov     qword ptr [rsp+88h+DesiredAccess], rdi
0x1800053ab  mov     r9, rsi
0x1800053ae  mov     rcx, [rcx+18h]
0x1800053b2  call    WPP_SF_qqL
0x1800053b7  lea     rcx, [rsp+88h+arg_0]; this
0x1800053bf  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x1800053c4  mov     eax, 0C000000Dh
0x1800053c9  add     rsp, 68h
0x1800053cd  pop     r14
0x1800053cf  pop     rdi
0x1800053d0  pop     rsi
0x1800053d1  pop     rbx
0x1800053d2  retn
```
