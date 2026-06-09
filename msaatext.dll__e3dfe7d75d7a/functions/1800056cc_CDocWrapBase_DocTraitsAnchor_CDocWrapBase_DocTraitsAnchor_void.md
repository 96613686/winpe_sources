# CDocWrapBase<DocTraitsAnchor>::~CDocWrapBase<DocTraitsAnchor>(void)

- ea: `0x1800056cc`
- end: `0x1800057db`
- name: `??1?$CDocWrapBase@VDocTraitsAnchor@@@@QEAA@XZ`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800054d4`

## callees

- `0x1800026d0`
- `0x1800056cc`
- `0x180005a44`
- `0x1800074c8`
- `0x180014010`

## string_xrefs

- `0x1800057a9`: `~Link_dl(), link still on a list?`

## pseudocode

```c
void __fastcall CDocWrapBase<DocTraitsAnchor>::~CDocWrapBase<DocTraitsAnchor>(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // [rsp+20h] [rbp-28h]

  if ( !*(_QWORD *)(a1 + 152) )
    InternalTrace(
      L"windows\\oleacc\\msaatext\\docwrap.cpp",
      0x407u,
      8u,
      0,
      v5,
      0,
      (wchar_t *)L"CDocWrapBase::Init never got called?");
  v2 = *(_QWORD *)(a1 + 112);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 112) = 0;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 144) + 16LL))(*(_QWORD *)(a1 + 144));
    *(_QWORD *)(a1 + 144) = 0;
    *(_DWORD *)(a1 + 136) = 0;
    if ( *(_QWORD *)(a1 + 152) )
      CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription();
  }
  v3 = *(_QWORD *)(a1 + 152);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *(_QWORD *)(a1 + 168);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  CVersionInfo::~CVersionInfo((CVersionInfo *)(a1 + 40));
  if ( *(_QWORD *)(a1 + 96) || *(_QWORD *)(a1 + 88) )
    InternalTrace(
      L"windows\\oleacc\\inc\\list_dl.h",
      0x1Fu,
      8u,
      0,
      v5,
      0,
      (wchar_t *)L"~Link_dl(), link still on a list?");
}

```

## disassembly

```asm
0x1800056cc  push    rbx
0x1800056ce  sub     rsp, 40h
0x1800056d2  mov     rbx, rcx
0x1800056d5  cmp     qword ptr [rcx+98h], 0
0x1800056dd  jnz     short loc_18000570B
0x1800056df  lea     rax, aCdocwrapbaseIn; "CDocWrapBase::Init never got called?"
0x1800056e6  mov     [rsp+48h+var_18], rax; __int64
0x1800056eb  mov     [rsp+48h+var_20], 0; int
0x1800056f3  xor     r9d, r9d
0x1800056f6  mov     edx, 407h; Value
0x1800056fb  lea     r8d, [r9+8]
0x1800056ff  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x180005706  call    InternalTrace
0x18000570b  mov     rcx, [rbx+70h]
0x18000570f  test    rcx, rcx
0x180005712  jz      short loc_180005761
0x180005714  mov     rax, [rcx]
0x180005717  mov     rax, [rax+10h]
0x18000571b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005720  mov     qword ptr [rbx+70h], 0
0x180005728  mov     rcx, [rbx+90h]
0x18000572f  mov     rax, [rcx]
0x180005732  mov     rax, [rax+10h]
0x180005736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000573b  mov     qword ptr [rbx+90h], 0
0x180005746  mov     dword ptr [rbx+88h], 0
0x180005750  mov     rcx, [rbx+98h]
0x180005757  test    rcx, rcx
0x18000575a  jz      short loc_180005761
0x18000575c  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsAnchor@@@@QEAAJXZ; CWrapMgr<DocTraitsAnchor>::DocWrap_UpdateSubscription(void)
0x180005761  mov     rcx, [rbx+98h]
0x180005768  test    rcx, rcx
0x18000576b  jz      short loc_180005779
0x18000576d  mov     rax, [rcx]
0x180005770  mov     rax, [rax+10h]
0x180005774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005779  mov     rcx, [rbx+0A8h]
0x180005780  test    rcx, rcx
0x180005783  jz      short loc_180005791
0x180005785  mov     rax, [rcx]
0x180005788  mov     rax, [rax+10h]
0x18000578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005791  lea     rcx, [rbx+28h]; this
0x180005795  call    ??1CVersionInfo@@QEAA@XZ; CVersionInfo::~CVersionInfo(void)
0x18000579a  nop
0x18000579b  cmp     qword ptr [rbx+60h], 0
0x1800057a0  jnz     short loc_1800057A9
0x1800057a2  cmp     qword ptr [rbx+58h], 0
0x1800057a7  jz      short loc_1800057D5
0x1800057a9  lea     rax, aLinkDlLinkStil; "~Link_dl(), link still on a list?"
0x1800057b0  mov     [rsp+48h+var_18], rax; __int64
0x1800057b5  mov     [rsp+48h+var_20], 0; int
0x1800057bd  xor     r9d, r9d
0x1800057c0  lea     edx, [r9+1Fh]; Value
0x1800057c4  lea     r8d, [r9+8]
0x1800057c8  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x1800057cf  call    InternalTrace
0x1800057d4  nop
0x1800057d5  add     rsp, 40h
0x1800057d9  pop     rbx
0x1800057da  retn
```
