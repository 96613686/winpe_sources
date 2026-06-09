# DetermineSystemProvider(MiniDumpAllocationProvider *,MiniDumpStatusProvider *,void *,_MINIDUMP_CALLBACK_INFORMATION * const,MiniDumpSystemProvider * *)

- ea: `0x1800062f4`
- end: `0x180006576`
- name: `?DetermineSystemProvider@@YAJPEAVMiniDumpAllocationProvider@@PEAVMiniDumpStatusProvider@@PEAXQEAU_MINIDUMP_CALLBACK_INFORMATION@@PEAPEAVMiniDumpSystemProvider@@@Z`
- size: `642`
- prototype: `int __fastcall(struct MiniDumpAllocationProvider *, struct MiniDumpStatusProvider *, struct HPSS__ *, struct _MINIDUMP_CALLBACK_INFORMATION *const, struct MiniDumpSystemProvider **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800100f0`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x1800062f4`
- `0x1800167a0`
- `0x1800203cc`
- `0x1800251f4`
- `0x18002c010`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x1800063de`
- `ntdll!RtlGetVersion` at `0x1800063de`

## pseudocode

```c
int __fastcall DetermineSystemProvider(
        struct MiniDumpAllocationProvider *a1,
        struct MiniDumpStatusProvider *a2,
        struct HPSS__ *a3,
        struct _MINIDUMP_CALLBACK_INFORMATION *const a4,
        struct MiniDumpSystemProvider **a5)
{
  MINIDUMP_CALLBACK_ROUTINE CallbackRoutine; // rax
  PVOID CallbackParam; // rcx
  NTSTATUS Version; // eax
  int result; // eax
  DWORD dwBuildNumber; // ebx
  _QWORD *v14; // rax
  PssNtWin32LiveSystemProvider *v15; // rax
  struct MiniDumpSystemProvider *v16; // rbx
  int v17; // r15d
  MINIDUMP_CALLBACK_ROUTINE v18; // rax
  PVOID v19; // rcx
  _QWORD *v20; // rdx
  _OWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+60h] [rbp-A0h]
  int v23; // [rsp+70h] [rbp-90h] BYREF
  struct HPSS__ *v24; // [rsp+74h] [rbp-8Ch]
  int v25; // [rsp+7Ch] [rbp-84h]
  struct _OSVERSIONINFOW v26; // [rsp+590h] [rbp+490h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+6B0h] [rbp+5B0h] BYREF

  memset_0(&v23, 0, 0x520u);
  v22 = 0;
  *a5 = 0;
  memset(v21, 0, sizeof(v21));
  if ( !a4 )
    goto LABEL_18;
  CallbackRoutine = a4->CallbackRoutine;
  if ( !a4->CallbackRoutine )
    goto LABEL_18;
  CallbackParam = a4->CallbackParam;
  v24 = a3;
  v23 = 0;
  v25 = 16;
  LODWORD(v21[0]) = -2147467263;
  if ( !((unsigned int (__fastcall *)(PVOID, int *, _OWORD *))CallbackRoutine)(CallbackParam, &v23, v21)
    || LODWORD(v21[0]) != 1 )
  {
LABEL_17:
    if ( *a5 )
    {
LABEL_20:
      v18 = a4->CallbackRoutine;
      if ( a4->CallbackRoutine )
      {
        v19 = a4->CallbackParam;
        v24 = a3;
        v23 = 0;
        v25 = 17;
        LODWORD(v21[0]) = -2147467263;
        if ( ((unsigned int (__fastcall *)(PVOID, int *, _OWORD *))v18)(v19, &v23, v21) )
        {
          if ( LODWORD(v21[0]) == 1 )
          {
            v20 = (_QWORD *)(((unsigned __int64)*a5 + 8) & -(__int64)(*a5 != 0));
            v20[1] = VmProviderQueryCallback;
            v20[2] = VmProviderPreReadCallback;
            v20[3] = VmProviderPostReadCallback;
            v20[4] = a4;
          }
        }
      }
      return 0;
    }
LABEL_18:
    result = MiniDumpCreateLiveSystemProvider(a1, a2);
    if ( result )
      return result;
    if ( !a4 )
      return 0;
    goto LABEL_20;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
    return Version | 0x10000000;
  if ( VersionInformation.dwPlatformId != 2 )
    return -2147024846;
  memset_0(&v26.dwMajorVersion, 0, 0x110u);
  v26.dwOSVersionInfoSize = 276;
  result = NtWin32LiveSystemProvider::GetTrueNTVersion(&v26);
  if ( result >= 0 )
  {
    dwBuildNumber = v26.dwBuildNumber;
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(struct MiniDumpAllocationProvider *, __int64))(*(_QWORD *)a1 + 8LL))(
                      a1,
                      1344);
    if ( v14 )
      *v14 = a1;
    if ( v14 == (_QWORD *)-8LL )
      return -2147024882;
    v15 = PssNtWin32LiveSystemProvider::PssNtWin32LiveSystemProvider(
            (PssNtWin32LiveSystemProvider *)(v14 + 1),
            a1,
            a2,
            a3,
            dwBuildNumber);
    v16 = v15;
    if ( !v15 )
      return -2147024882;
    v17 = (*(__int64 (__fastcall **)(PssNtWin32LiveSystemProvider *))(*(_QWORD *)v15 + 568LL))(v15);
    if ( v17 )
    {
      (**(void (__fastcall ***)(struct MiniDumpSystemProvider *))v16)(v16);
      return v17;
    }
    *a5 = v16;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x1800062f4  push    rbp
0x1800062f6  push    rbx
0x1800062f7  push    rsi
0x1800062f8  push    rdi
0x1800062f9  push    r12
0x1800062fb  push    r13
0x1800062fd  push    r14
0x1800062ff  push    r15
0x180006301  lea     rbp, [rsp-6E8h]
0x180006309  sub     rsp, 7E8h
0x180006310  mov     rax, cs:__security_cookie
0x180006317  xor     rax, rsp
0x18000631a  mov     [rbp+720h+var_50], rax
0x180006321  mov     rsi, [rbp+720h+arg_20]
0x180006328  mov     r12, r8
0x18000632b  mov     r13, rdx
0x18000632e  mov     r14, rcx
0x180006331  xor     edx, edx; Val
0x180006333  lea     rcx, [rsp+820h+var_7B0]; void *
0x180006338  mov     r8d, 520h; Size
0x18000633e  mov     rdi, r9
0x180006341  call    memset_0
0x180006346  xor     eax, eax
0x180006348  xorps   xmm0, xmm0
0x18000634b  mov     [rsp+820h+var_7C0], eax
0x18000634f  mov     [rsi], rax
0x180006352  movups  [rsp+820h+var_7F0], xmm0
0x180006357  movups  [rsp+820h+var_7E0], xmm0
0x18000635c  movups  [rsp+820h+var_7D0], xmm0
0x180006361  test    rdi, rdi
0x180006364  jz      loc_1800064BB
0x18000636a  mov     rax, [rdi]
0x18000636d  test    rax, rax
0x180006370  jz      loc_1800064BB
0x180006376  mov     rcx, [rdi+8]
0x18000637a  lea     r8, [rsp+820h+var_7F0]
0x18000637f  lea     rdx, [rsp+820h+var_7B0]
0x180006384  mov     [rsp+820h+var_7AC], r12
0x180006389  mov     [rsp+820h+var_7B0], 0
0x180006391  mov     [rsp+820h+var_7A4], 10h
0x180006399  mov     dword ptr [rsp+820h+var_7F0], 80004001h
0x1800063a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a6  test    eax, eax
0x1800063a8  jz      loc_1800064B5
0x1800063ae  cmp     dword ptr [rsp+820h+var_7F0], 1
0x1800063b3  jnz     loc_1800064B5
0x1800063b9  xor     edx, edx; Val
0x1800063bb  lea     rcx, [rbp+720h+VersionInformation.dwMajorVersion]; void *
0x1800063c2  mov     r8d, 118h; Size
0x1800063c8  call    memset_0
0x1800063cd  lea     rcx, [rbp+720h+VersionInformation]; lpVersionInformation
0x1800063d4  mov     [rbp+720h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800063de  call    cs:__imp_RtlGetVersion
0x1800063e4  test    eax, eax
0x1800063e6  jns     short loc_1800063F1
0x1800063e8  bts     eax, 1Ch
0x1800063ec  jmp     loc_18000654C
0x1800063f1  cmp     [rbp+720h+VersionInformation.dwPlatformId], 2
0x1800063f8  jz      short loc_180006404
0x1800063fa  mov     eax, 80070032h
0x1800063ff  jmp     loc_18000654C
0x180006404  xor     edx, edx; Val
0x180006406  lea     rcx, [rbp+720h+var_290.dwMajorVersion]; void *
0x18000640d  mov     r8d, 110h; Size
0x180006413  call    memset_0
0x180006418  lea     rcx, [rbp+720h+var_290]; struct _OSVERSIONINFOW *
0x18000641f  mov     [rbp+720h+var_290.dwOSVersionInfoSize], 114h
0x180006429  call    ?GetTrueNTVersion@NtWin32LiveSystemProvider@@SAJPEAU_OSVERSIONINFOW@@@Z; NtWin32LiveSystemProvider::GetTrueNTVersion(_OSVERSIONINFOW *)
0x18000642e  test    eax, eax
0x180006430  js      loc_18000654C
0x180006436  mov     rax, [r14]
0x180006439  mov     edx, 540h
0x18000643e  mov     ebx, [rbp+720h+var_290.dwBuildNumber]
0x180006444  mov     rcx, r14
0x180006447  mov     rax, [rax+8]
0x18000644b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006450  test    rax, rax
0x180006453  jz      short loc_180006458
0x180006455  mov     [rax], r14
0x180006458  lea     rcx, [rax+8]; this
0x18000645c  test    rcx, rcx
0x18000645f  jz      loc_18000656F
0x180006465  mov     r9, r12; struct HPSS__ *
0x180006468  mov     [rsp+820h+var_800], ebx; unsigned int
0x18000646c  mov     r8, r13; struct MiniDumpStatusProvider *
0x18000646f  mov     rdx, r14; struct MiniDumpAllocationProvider *
0x180006472  call    ??0PssNtWin32LiveSystemProvider@@QEAA@PEAVMiniDumpAllocationProvider@@PEAVMiniDumpStatusProvider@@PEAUHPSS__@@K@Z; PssNtWin32LiveSystemProvider::PssNtWin32LiveSystemProvider(MiniDumpAllocationProvider *,MiniDumpStatusProvider *,HPSS__ *,ulong)
0x180006477  mov     rbx, rax
0x18000647a  test    rax, rax
0x18000647d  jz      loc_18000656F
0x180006483  mov     rcx, [rax]
0x180006486  mov     rax, [rcx+238h]
0x18000648d  mov     rcx, rbx
0x180006490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006495  mov     r15d, eax
0x180006498  test    eax, eax
0x18000649a  jz      short loc_1800064B2
0x18000649c  mov     rcx, [rbx]
0x18000649f  mov     rax, [rcx]
0x1800064a2  mov     rcx, rbx
0x1800064a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064aa  mov     eax, r15d
0x1800064ad  jmp     loc_18000654C
0x1800064b2  mov     [rsi], rbx
0x1800064b5  cmp     qword ptr [rsi], 0
0x1800064b9  jnz     short loc_1800064D2
0x1800064bb  mov     r8, rsi
0x1800064be  mov     rdx, r13; struct MiniDumpStatusProvider *
0x1800064c1  mov     rcx, r14; struct MiniDumpAllocationProvider *
0x1800064c4  call    MiniDumpCreateLiveSystemProvider
0x1800064c9  test    eax, eax
0x1800064cb  jnz     short loc_18000654C
0x1800064cd  test    rdi, rdi
0x1800064d0  jz      short loc_18000654A
0x1800064d2  mov     rax, [rdi]
0x1800064d5  test    rax, rax
0x1800064d8  jz      short loc_18000654A
0x1800064da  mov     rcx, [rdi+8]
0x1800064de  lea     r8, [rsp+820h+var_7F0]
0x1800064e3  lea     rdx, [rsp+820h+var_7B0]
0x1800064e8  mov     [rsp+820h+var_7AC], r12
0x1800064ed  mov     [rsp+820h+var_7B0], 0
0x1800064f5  mov     [rsp+820h+var_7A4], 11h
0x1800064fd  mov     dword ptr [rsp+820h+var_7F0], 80004001h
0x180006505  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650a  test    eax, eax
0x18000650c  jz      short loc_18000654A
0x18000650e  cmp     dword ptr [rsp+820h+var_7F0], 1
0x180006513  jnz     short loc_18000654A
0x180006515  mov     rax, [rsi]
0x180006518  lea     rcx, [rax+8]
0x18000651c  neg     rax
0x18000651f  lea     rax, VmProviderQueryCallback
0x180006526  sbb     rdx, rdx
0x180006529  and     rdx, rcx
0x18000652c  mov     [rdx+8], rax
0x180006530  lea     rax, VmProviderPreReadCallback
0x180006537  mov     [rdx+10h], rax
0x18000653b  lea     rax, VmProviderPostReadCallback
0x180006542  mov     [rdx+18h], rax
0x180006546  mov     [rdx+20h], rdi
0x18000654a  xor     eax, eax
0x18000654c  mov     rcx, [rbp+720h+var_50]
0x180006553  xor     rcx, rsp; StackCookie
0x180006556  call    __security_check_cookie
0x18000655b  add     rsp, 7E8h
0x180006562  pop     r15
0x180006564  pop     r14
0x180006566  pop     r13
0x180006568  pop     r12
0x18000656a  pop     rdi
0x18000656b  pop     rsi
0x18000656c  pop     rbx
0x18000656d  pop     rbp
0x18000656e  retn
0x18000656f  mov     eax, 8007000Eh
0x180006574  jmp     short loc_18000654C
```
