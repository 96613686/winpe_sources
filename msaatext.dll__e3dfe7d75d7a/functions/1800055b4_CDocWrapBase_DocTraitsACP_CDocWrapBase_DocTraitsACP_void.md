# CDocWrapBase<DocTraitsACP>::~CDocWrapBase<DocTraitsACP>(void)

- ea: `0x1800055b4`
- end: `0x1800056c3`
- name: `??1?$CDocWrapBase@VDocTraitsACP@@@@QEAA@XZ`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000a6c0`

## callees

- `0x1800026d0`
- `0x1800055b4`
- `0x180005a44`
- `0x1800071ac`
- `0x180014010`

## string_xrefs

- `0x180005691`: `~Link_dl(), link still on a list?`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDocWrapBase<DocTraitsACP>::~CDocWrapBase<DocTraitsACP>(__int64 a1)
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
      CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription();
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
0x1800055b4  push    rbx
0x1800055b6  sub     rsp, 40h
0x1800055ba  mov     rbx, rcx
0x1800055bd  cmp     qword ptr [rcx+98h], 0
0x1800055c5  jnz     short loc_1800055F3
0x1800055c7  lea     rax, aCdocwrapbaseIn; "CDocWrapBase::Init never got called?"
0x1800055ce  mov     [rsp+48h+var_18], rax; __int64
0x1800055d3  mov     [rsp+48h+var_20], 0; int
0x1800055db  xor     r9d, r9d
0x1800055de  mov     edx, 407h; Value
0x1800055e3  lea     r8d, [r9+8]
0x1800055e7  lea     rcx, aWindowsOleaccM; "windows\\oleacc\\msaatext\\docwrap.cpp"
0x1800055ee  call    InternalTrace
0x1800055f3  mov     rcx, [rbx+70h]
0x1800055f7  test    rcx, rcx
0x1800055fa  jz      short loc_180005649
0x1800055fc  mov     rax, [rcx]
0x1800055ff  mov     rax, [rax+10h]
0x180005603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005608  mov     qword ptr [rbx+70h], 0
0x180005610  mov     rcx, [rbx+90h]
0x180005617  mov     rax, [rcx]
0x18000561a  mov     rax, [rax+10h]
0x18000561e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005623  mov     qword ptr [rbx+90h], 0
0x18000562e  mov     dword ptr [rbx+88h], 0
0x180005638  mov     rcx, [rbx+98h]
0x18000563f  test    rcx, rcx
0x180005642  jz      short loc_180005649
0x180005644  call    ?DocWrap_UpdateSubscription@?$CWrapMgr@VDocTraitsACP@@@@QEAAJXZ; CWrapMgr<DocTraitsACP>::DocWrap_UpdateSubscription(void)
0x180005649  mov     rcx, [rbx+98h]
0x180005650  test    rcx, rcx
0x180005653  jz      short loc_180005661
0x180005655  mov     rax, [rcx]
0x180005658  mov     rax, [rax+10h]
0x18000565c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005661  mov     rcx, [rbx+0A8h]
0x180005668  test    rcx, rcx
0x18000566b  jz      short loc_180005679
0x18000566d  mov     rax, [rcx]
0x180005670  mov     rax, [rax+10h]
0x180005674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005679  lea     rcx, [rbx+28h]; this
0x18000567d  call    ??1CVersionInfo@@QEAA@XZ; CVersionInfo::~CVersionInfo(void)
0x180005682  nop
0x180005683  cmp     qword ptr [rbx+60h], 0
0x180005688  jnz     short loc_180005691
0x18000568a  cmp     qword ptr [rbx+58h], 0
0x18000568f  jz      short loc_1800056BD
0x180005691  lea     rax, aLinkDlLinkStil; "~Link_dl(), link still on a list?"
0x180005698  mov     [rsp+48h+var_18], rax; __int64
0x18000569d  mov     [rsp+48h+var_20], 0; int
0x1800056a5  xor     r9d, r9d
0x1800056a8  lea     edx, [r9+1Fh]; Value
0x1800056ac  lea     r8d, [r9+8]
0x1800056b0  lea     rcx, aWindowsOleaccI; "windows\\oleacc\\inc\\list_dl.h"
0x1800056b7  call    InternalTrace
0x1800056bc  nop
0x1800056bd  add     rsp, 40h
0x1800056c1  pop     rbx
0x1800056c2  retn
```
