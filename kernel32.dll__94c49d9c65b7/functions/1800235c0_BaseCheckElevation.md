# BaseCheckElevation

- ea: `0x1800235c0`
- end: `0x1800237c2`
- name: `BaseCheckElevation`
- size: `514`
- prototype: `__int64 __fastcall(void *, int, int, int *, __int64, __int64, __int64, int, HANDLE, int *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800253c0`

## callees

- `0x1800235c0`
- `0x1800237c8`
- `0x180025040`
- `0x18006a878`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180023795`
- `ntdll!NtSetInformationThread` at `0x180023795`
- `ntdll!NtOpenProcessToken` at `0x18002373f`
- `ntdll!NtOpenProcessToken` at `0x180023774`
- `ntdll!NtOpenProcessToken` at `0x18002373f`
- `ntdll!NtOpenProcessToken` at `0x180023774`
- `ntdll!NtClose` at `0x1800236fb`
- `ntdll!NtClose` at `0x180023709`
- `ntdll!NtClose` at `0x1800236fb`
- `ntdll!NtClose` at `0x180023709`
- `ntdll!RtlQueryElevationFlags` at `0x180023600`
- `ntdll!RtlQueryElevationFlags` at `0x180023600`
- `ntdll!RtlRaiseStatus` at `0x1800237a1`
- `ntdll!RtlRaiseStatus` at `0x1800237a1`

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
  int v15; // ebx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ecx
  HANDLE v20; // rcx
  int v21; // eax
  NTSTATUS v22; // eax
  int v23; // eax
  NTSTATUS v24; // eax
  int v25; // eax
  int v26; // [rsp+50h] [rbp-28h] BYREF
  unsigned int v27; // [rsp+54h] [rbp-24h] BYREF
  int v28; // [rsp+58h] [rbp-20h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-18h] BYREF
  _QWORD ThreadInformation[2]; // [rsp+68h] [rbp-10h] BYREF

  v26 = 0;
  v12 = 0;
  Handle = 0;
  ThreadInformation[0] = 0;
  v27 = 0;
  v28 = 6;
  v15 = RtlQueryElevationFlags(&v27);
  if ( v15 >= 0 )
  {
    v16 = v27;
    v15 = 0;
    if ( (v27 & 1) != 0 )
    {
      *a4 |= 2u;
      v17 = (v16 >> 2) & 1;
      if ( (a5 & 0x200000000LL) != 0 )
        *a4 |= 8u;
      v15 = BaseCheckDetectionMethods(a2, a3, (_DWORD)a4, a5, a6, a7, a8, v17, (__int64)&v26, (__int64)&v28);
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
          v21 = v26;
          if ( !v26 )
            v21 = 1;
          v26 = v21;
        }
        if ( (v18 & 1) != 0 && v26 )
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
              if ( v22 != -1073741790 )
                goto LABEL_34;
              v23 = BaseRevertToSelf(ThreadInformation);
              v12 = (void *)ThreadInformation[0];
              if ( v23 < 0 || !ThreadInformation[0] )
                goto LABEL_34;
              v24 = NtOpenProcessToken(a1, 8u, &Handle);
              ThreadInformation[0] = v12;
              v15 = v24;
              v25 = NtSetInformationThread(
                      (HANDLE)0xFFFFFFFFFFFFFFFELL,
                      ThreadImpersonationToken,
                      ThreadInformation,
                      8u);
              if ( v25 < 0 )
                RtlRaiseStatus(v25);
              if ( v15 < 0 )
              {
LABEL_34:
                Handle = 0;
LABEL_20:
                if ( v12 )
                  NtClose(v12);
                goto LABEL_11;
              }
            }
            v20 = Handle;
          }
          v15 = BasepCheckForElevatedCaller(v20, a4, &v26);
          goto LABEL_20;
        }
      }
    }
  }
LABEL_11:
  if ( Handle && Handle != a9 )
    NtClose(Handle);
  if ( a10 )
    *a10 = v26;
  if ( a11 )
    *a11 = v28;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800235c0  mov     [rsp-30h+arg_8], rdx
0x1800235c5  push    rbp
0x1800235c6  push    rbx
0x1800235c7  push    rsi
0x1800235c8  push    rdi
0x1800235c9  push    r12
0x1800235cb  push    r13
0x1800235cd  mov     rbp, rsp
0x1800235d0  sub     rsp, 78h
0x1800235d4  mov     r12, rcx
0x1800235d7  mov     [rbp+var_28], 0
0x1800235de  xor     edi, edi
0x1800235e0  mov     [rbp+Handle], 0
0x1800235e8  lea     rcx, [rbp+var_24]
0x1800235ec  mov     [rbp+ThreadInformation], rdi
0x1800235f0  mov     [rbp+var_24], edi
0x1800235f3  mov     rsi, r9
0x1800235f6  mov     r13, r8
0x1800235f9  mov     [rbp+var_20], 6
0x180023600  call    cs:__imp_RtlQueryElevationFlags
0x180023606  mov     ebx, eax
0x180023608  test    eax, eax
0x18002360a  js      loc_180023699
0x180023610  mov     eax, [rbp+var_24]
0x180023613  lea     ecx, [rdi+1]
0x180023616  xor     ebx, ebx
0x180023618  test    cl, al
0x18002361a  jz      short loc_180023699
0x18002361c  or      dword ptr [rsi], 2
0x18002361f  shr     eax, 2
0x180023622  and     eax, ecx
0x180023624  test    [rbp+arg_24], 2
0x180023628  jnz     loc_180023711
0x18002362e  mov     r9d, [rbp+arg_20]
0x180023632  lea     rcx, [rbp+var_20]
0x180023636  mov     [rsp+78h+var_30], rcx
0x18002363b  mov     r8, rsi
0x18002363e  lea     rcx, [rbp+var_28]
0x180023642  mov     rdx, r13
0x180023645  mov     [rsp+78h+var_38], rcx
0x18002364a  mov     rcx, [rbp+arg_8]
0x18002364e  mov     [rsp+78h+var_40], eax
0x180023652  mov     eax, [rbp+arg_38]
0x180023655  mov     [rsp+78h+var_48], eax
0x180023659  mov     rax, [rbp+arg_30]
0x18002365d  mov     [rsp+78h+var_50], rax
0x180023662  mov     rax, [rbp+arg_28]
0x180023666  mov     [rsp+78h+var_58], rax
0x18002366b  call    BaseCheckDetectionMethods
0x180023670  mov     ebx, eax
0x180023672  test    eax, eax
0x180023674  js      short loc_180023699
0x180023676  mov     ecx, [rsi]
0x180023678  mov     edx, 1
0x18002367d  test    [rbp+arg_24], dl
0x180023680  jnz     loc_180023719
0x180023686  test    [rbp+arg_24], 4
0x18002368a  jnz     loc_180023723
0x180023690  test    dl, cl
0x180023692  jz      short loc_180023699
0x180023694  cmp     [rbp+var_28], edi
0x180023697  jnz     short loc_1800236D7
0x180023699  mov     rcx, [rbp+Handle]; Handle
0x18002369d  test    rcx, rcx
0x1800236a0  jnz     short loc_180023703
0x1800236a2  mov     rcx, [rbp+arg_48]
0x1800236a9  test    rcx, rcx
0x1800236ac  jnz     short loc_1800236C9
0x1800236ae  mov     rcx, [rbp+arg_50]
0x1800236b5  test    rcx, rcx
0x1800236b8  jnz     short loc_1800236D0
0x1800236ba  mov     eax, ebx
0x1800236bc  add     rsp, 78h
0x1800236c0  pop     r13
0x1800236c2  pop     r12
0x1800236c4  pop     rdi
0x1800236c5  pop     rsi
0x1800236c6  pop     rbx
0x1800236c7  pop     rbp
0x1800236c8  retn
0x1800236c9  mov     eax, [rbp+var_28]
0x1800236cc  mov     [rcx], eax
0x1800236ce  jmp     short loc_1800236AE
0x1800236d0  mov     eax, [rbp+var_20]
0x1800236d3  mov     [rcx], eax
0x1800236d5  jmp     short loc_1800236BA
0x1800236d7  cmp     [rbp+arg_40], rdi
0x1800236db  jz      short loc_180023733
0x1800236dd  mov     rcx, [rbp+arg_40]
0x1800236e1  mov     [rbp+Handle], rcx
0x1800236e5  lea     r8, [rbp+var_28]
0x1800236e9  mov     rdx, rsi
0x1800236ec  call    BasepCheckForElevatedCaller
0x1800236f1  mov     ebx, eax
0x1800236f3  test    rdi, rdi
0x1800236f6  jz      short loc_180023699
0x1800236f8  mov     rcx, rdi; Handle
0x1800236fb  call    cs:__imp_NtClose
0x180023701  jmp     short loc_180023699
0x180023703  cmp     rcx, [rbp+arg_40]
0x180023707  jz      short loc_1800236A2
0x180023709  call    cs:__imp_NtClose
0x18002370f  jmp     short loc_1800236A2
0x180023711  or      dword ptr [rsi], 8
0x180023714  jmp     loc_18002362E
0x180023719  and     ecx, 0FFFFFFFDh
0x18002371c  mov     [rsi], ecx
0x18002371e  jmp     loc_180023686
0x180023723  mov     eax, [rbp+var_28]
0x180023726  test    eax, eax
0x180023728  cmovz   eax, edx
0x18002372b  mov     [rbp+var_28], eax
0x18002372e  jmp     loc_180023690
0x180023733  lea     r8, [rbp+Handle]; TokenHandle
0x180023737  mov     edx, 8; DesiredAccess
0x18002373c  mov     rcx, r12; ProcessHandle
0x18002373f  call    cs:__imp_NtOpenProcessToken
0x180023745  mov     ebx, eax
0x180023747  test    eax, eax
0x180023749  jns     short loc_1800237B9
0x18002374b  cmp     eax, 0C0000022h
0x180023750  jnz     short loc_1800237AC
0x180023752  lea     rcx, [rbp+ThreadInformation]
0x180023756  call    BaseRevertToSelf
0x18002375b  mov     rdi, [rbp+ThreadInformation]
0x18002375f  test    eax, eax
0x180023761  js      short loc_1800237AC
0x180023763  test    rdi, rdi
0x180023766  jz      short loc_1800237AC
0x180023768  lea     r8, [rbp+Handle]; TokenHandle
0x18002376c  mov     edx, 8; DesiredAccess
0x180023771  mov     rcx, r12; ProcessHandle
0x180023774  call    cs:__imp_NtOpenProcessToken
0x18002377a  mov     r9d, 8; ThreadInformationLength
0x180023780  mov     [rbp+ThreadInformation], rdi
0x180023784  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x180023788  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18002378f  mov     ebx, eax
0x180023791  lea     edx, [r9-3]; ThreadInformationClass
0x180023795  call    cs:__imp_NtSetInformationThread
0x18002379b  test    eax, eax
0x18002379d  jns     short loc_1800237A8
0x18002379f  mov     ecx, eax; Status
0x1800237a1  call    cs:__imp_RtlRaiseStatus
0x1800237a7  int     3; Trap to Debugger
0x1800237a8  test    ebx, ebx
0x1800237aa  jns     short loc_1800237B9
0x1800237ac  mov     [rbp+Handle], 0
0x1800237b4  jmp     loc_1800236F3
0x1800237b9  mov     rcx, [rbp+Handle]
0x1800237bd  jmp     loc_1800236E5
```
