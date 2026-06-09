# BaseCheckElevation

- ea: `0x1800214c0`
- end: `0x1800216bd`
- name: `BaseCheckElevation`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180023220`

## callees

- `0x1800214c0`
- `0x1800216c4`
- `0x180022fc0`
- `0x180071adc`
- `0x180071b2c`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180021652`
- `ntdll!NtOpenProcessToken` at `0x18002168d`
- `ntdll!NtOpenProcessToken` at `0x180021652`
- `ntdll!NtOpenProcessToken` at `0x18002168d`
- `ntdll!NtClose` at `0x180021602`
- `ntdll!NtClose` at `0x180021616`
- `ntdll!NtClose` at `0x180021602`
- `ntdll!NtClose` at `0x180021616`
- `ntdll!RtlQueryElevationFlags` at `0x180021500`
- `ntdll!RtlQueryElevationFlags` at `0x180021500`

## pseudocode

```c
__int64 __fastcall BaseCheckElevation(
        void *a1,
        int a2,
        int a3,
        int *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        HANDLE a9,
        int *a10,
        int *a11)
{
  void *v12; // rdi
  NTSTATUS v15; // ebx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ecx
  HANDLE v20; // rcx
  int v21; // eax
  NTSTATUS v22; // eax
  int v23; // eax
  int v24; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-24h] BYREF
  int v26; // [rsp+58h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-18h] BYREF
  void *v28; // [rsp+68h] [rbp-10h] BYREF

  v24 = 0;
  v12 = 0;
  Handle = 0;
  v28 = 0;
  v25 = 0;
  v26 = 6;
  v15 = RtlQueryElevationFlags(&v25);
  if ( v15 >= 0 )
  {
    v16 = v25;
    v15 = 0;
    if ( (v25 & 1) != 0 )
    {
      *a4 |= 2u;
      v17 = (v16 >> 2) & 1;
      if ( (a5 & 0x200000000LL) != 0 )
        *a4 |= 8u;
      v15 = BaseCheckDetectionMethods(a2, a3, (_DWORD)a4, a5, a6, a7, a8, v17, (__int64)&v24, (__int64)&v26);
      if ( v15 >= 0 )
      {
        v18 = *a4;
        if ( (a5 & 0x100000000LL) != 0 )
        {
          v18 &= ~2u;
          *a4 = v18;
        }
        if ( (a5 & 0x400000000LL) != 0 )
        {
          v21 = v24;
          if ( !v24 )
            v21 = 1;
          v24 = v21;
        }
        if ( (v18 & 1) != 0 && v24 )
        {
          if ( a9 )
          {
            v20 = a9;
            Handle = a9;
          }
          else
          {
            v22 = NtOpenProcessToken(a1, 8u, &Handle);
            v15 = v22;
            if ( v22 < 0 )
            {
              if ( v22 != -1073741790
                || (v23 = BaseRevertToSelf(&v28), v12 = v28, v23 < 0)
                || !v28
                || (v15 = NtOpenProcessToken(a1, 8u, &Handle), BaseRestoreImpersonation(v12), v15 < 0) )
              {
                Handle = 0;
LABEL_20:
                if ( v12 )
                  NtClose(v12);
                goto LABEL_11;
              }
            }
            v20 = Handle;
          }
          v15 = BasepCheckForElevatedCaller(v20, a4, &v24);
          goto LABEL_20;
        }
      }
    }
  }
LABEL_11:
  if ( Handle && Handle != a9 )
    NtClose(Handle);
  if ( a10 )
    *a10 = v24;
  if ( a11 )
    *a11 = v26;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800214c0  mov     [rsp-30h+arg_8], rdx
0x1800214c5  push    rbp
0x1800214c6  push    rbx
0x1800214c7  push    rsi
0x1800214c8  push    rdi
0x1800214c9  push    r12
0x1800214cb  push    r13
0x1800214cd  mov     rbp, rsp
0x1800214d0  sub     rsp, 78h
0x1800214d4  mov     r12, rcx
0x1800214d7  mov     [rbp+var_28], 0
0x1800214de  xor     edi, edi
0x1800214e0  mov     [rbp+Handle], 0
0x1800214e8  lea     rcx, [rbp+var_24]
0x1800214ec  mov     [rbp+var_10], rdi
0x1800214f0  mov     [rbp+var_24], edi
0x1800214f3  mov     rsi, r9
0x1800214f6  mov     r13, r8
0x1800214f9  mov     [rbp+var_20], 6
0x180021500  call    cs:__imp_RtlQueryElevationFlags
0x180021507  nop     dword ptr [rax+rax+00h]
0x18002150c  mov     ebx, eax
0x18002150e  test    eax, eax
0x180021510  js      loc_18002159F
0x180021516  mov     eax, [rbp+var_24]
0x180021519  lea     ecx, [rdi+1]
0x18002151c  xor     ebx, ebx
0x18002151e  test    cl, al
0x180021520  jz      short loc_18002159F
0x180021522  or      dword ptr [rsi], 2
0x180021525  shr     eax, 2
0x180021528  and     eax, ecx
0x18002152a  test    [rbp+arg_24], 2
0x18002152e  jnz     loc_180021624
0x180021534  mov     r9d, [rbp+arg_20]
0x180021538  lea     rcx, [rbp+var_20]
0x18002153c  mov     [rsp+78h+var_30], rcx
0x180021541  mov     r8, rsi
0x180021544  lea     rcx, [rbp+var_28]
0x180021548  mov     rdx, r13
0x18002154b  mov     [rsp+78h+var_38], rcx
0x180021550  mov     rcx, [rbp+arg_8]
0x180021554  mov     [rsp+78h+var_40], eax
0x180021558  mov     eax, [rbp+arg_38]
0x18002155b  mov     [rsp+78h+var_48], eax
0x18002155f  mov     rax, [rbp+arg_30]
0x180021563  mov     [rsp+78h+var_50], rax
0x180021568  mov     rax, [rbp+arg_28]
0x18002156c  mov     [rsp+78h+var_58], rax
0x180021571  call    BaseCheckDetectionMethods
0x180021576  mov     ebx, eax
0x180021578  test    eax, eax
0x18002157a  js      short loc_18002159F
0x18002157c  mov     ecx, [rsi]
0x18002157e  mov     edx, 1
0x180021583  test    [rbp+arg_24], dl
0x180021586  jnz     loc_18002162C
0x18002158c  test    [rbp+arg_24], 4
0x180021590  jnz     loc_180021636
0x180021596  test    dl, cl
0x180021598  jz      short loc_18002159F
0x18002159a  cmp     [rbp+var_28], edi
0x18002159d  jnz     short loc_1800215DE
0x18002159f  mov     rcx, [rbp+Handle]; Handle
0x1800215a3  test    rcx, rcx
0x1800215a6  jnz     short loc_180021610
0x1800215a8  mov     rcx, [rbp+arg_48]
0x1800215af  test    rcx, rcx
0x1800215b2  jnz     short loc_1800215D0
0x1800215b4  mov     rcx, [rbp+arg_50]
0x1800215bb  test    rcx, rcx
0x1800215be  jnz     short loc_1800215D7
0x1800215c0  mov     eax, ebx
0x1800215c2  add     rsp, 78h
0x1800215c6  pop     r13
0x1800215c8  pop     r12
0x1800215ca  pop     rdi
0x1800215cb  pop     rsi
0x1800215cc  pop     rbx
0x1800215cd  pop     rbp
0x1800215ce  retn
0x1800215d0  mov     eax, [rbp+var_28]
0x1800215d3  mov     [rcx], eax
0x1800215d5  jmp     short loc_1800215B4
0x1800215d7  mov     eax, [rbp+var_20]
0x1800215da  mov     [rcx], eax
0x1800215dc  jmp     short loc_1800215C0
0x1800215de  cmp     [rbp+arg_40], rdi
0x1800215e2  jz      short loc_180021646
0x1800215e4  mov     rcx, [rbp+arg_40]
0x1800215e8  mov     [rbp+Handle], rcx
0x1800215ec  lea     r8, [rbp+var_28]
0x1800215f0  mov     rdx, rsi
0x1800215f3  call    BasepCheckForElevatedCaller
0x1800215f8  mov     ebx, eax
0x1800215fa  test    rdi, rdi
0x1800215fd  jz      short loc_18002159F
0x1800215ff  mov     rcx, rdi; Handle
0x180021602  call    cs:__imp_NtClose
0x180021609  nop     dword ptr [rax+rax+00h]
0x18002160e  jmp     short loc_18002159F
0x180021610  cmp     rcx, [rbp+arg_40]
0x180021614  jz      short loc_1800215A8
0x180021616  call    cs:__imp_NtClose
0x18002161d  nop     dword ptr [rax+rax+00h]
0x180021622  jmp     short loc_1800215A8
0x180021624  or      dword ptr [rsi], 8
0x180021627  jmp     loc_180021534
0x18002162c  and     ecx, 0FFFFFFFDh
0x18002162f  mov     [rsi], ecx
0x180021631  jmp     loc_18002158C
0x180021636  mov     eax, [rbp+var_28]
0x180021639  test    eax, eax
0x18002163b  cmovz   eax, edx
0x18002163e  mov     [rbp+var_28], eax
0x180021641  jmp     loc_180021596
0x180021646  lea     r8, [rbp+Handle]; TokenHandle
0x18002164a  mov     edx, 8; DesiredAccess
0x18002164f  mov     rcx, r12; ProcessHandle
0x180021652  call    cs:__imp_NtOpenProcessToken
0x180021659  nop     dword ptr [rax+rax+00h]
0x18002165e  mov     ebx, eax
0x180021660  test    eax, eax
0x180021662  jns     short loc_1800216B4
0x180021664  cmp     eax, 0C0000022h
0x180021669  jnz     short loc_1800216A7
0x18002166b  lea     rcx, [rbp+var_10]
0x18002166f  call    BaseRevertToSelf
0x180021674  mov     rdi, [rbp+var_10]
0x180021678  test    eax, eax
0x18002167a  js      short loc_1800216A7
0x18002167c  test    rdi, rdi
0x18002167f  jz      short loc_1800216A7
0x180021681  lea     r8, [rbp+Handle]; TokenHandle
0x180021685  mov     edx, 8; DesiredAccess
0x18002168a  mov     rcx, r12; ProcessHandle
0x18002168d  call    cs:__imp_NtOpenProcessToken
0x180021694  nop     dword ptr [rax+rax+00h]
0x180021699  mov     rcx, rdi
0x18002169c  mov     ebx, eax
0x18002169e  call    BaseRestoreImpersonation
0x1800216a3  test    ebx, ebx
0x1800216a5  jns     short loc_1800216B4
0x1800216a7  mov     [rbp+Handle], 0
0x1800216af  jmp     loc_1800215FA
0x1800216b4  mov     rcx, [rbp+Handle]
0x1800216b8  jmp     loc_1800215EC
```
