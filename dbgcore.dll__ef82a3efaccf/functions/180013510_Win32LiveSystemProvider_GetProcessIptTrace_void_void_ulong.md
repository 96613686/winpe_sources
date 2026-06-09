# Win32LiveSystemProvider::GetProcessIptTrace(void *,void * *,ulong *)

- ea: `0x180013510`
- end: `0x1800136a3`
- name: `?GetProcessIptTrace@Win32LiveSystemProvider@@UEAAJPEAXPEAPEAXPEAK@Z`
- size: `403`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, void *, void **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180001710`
- `0x180013510`
- `0x180026988`
- `0x1800269bc`
- `0x18002a13c`
- `0x18002c010`

## import_xrefs

- `ntdll!NtClose` at `0x1800135e7`
- `ntdll!NtClose` at `0x1800135e7`
- `ntdll!RtlNtStatusToDosError` at `0x180013614`
- `ntdll!RtlNtStatusToDosError` at `0x180013614`
- `ntdll!NtDeviceIoControlFile` at `0x1800135db`
- `ntdll!NtDeviceIoControlFile` at `0x1800135db`
- `ntdll!RtlReleasePrivilege` at `0x1800135f5`
- `ntdll!RtlReleasePrivilege` at `0x1800135f5`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::GetProcessIptTrace(
        Win32LiveSystemProvider *this,
        void *a2,
        void **a3,
        unsigned int *a4)
{
  int ProcessIptTrace; // edi
  char v9; // bl
  unsigned int v10; // edi
  signed int result; // eax
  __int64 v12; // rax
  _DWORD *v13; // rbx
  HANDLE FileHandle; // [rsp+50h] [rbp-49h] BYREF
  PVOID ReturnedState; // [rsp+58h] [rbp-41h] BYREF
  __int128 InputBuffer; // [rsp+60h] [rbp-39h] BYREF
  __int128 v17; // [rsp+70h] [rbp-29h]
  __int128 v18; // [rsp+80h] [rbp-19h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-9h] BYREF
  __int128 OutputBuffer; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+17h]

  FileHandle = 0;
  v21 = 0;
  InputBuffer = 0;
  ReturnedState = 0;
  v17 = 0;
  v18 = 0;
  OutputBuffer = 0;
  IoStatusBlock = 0;
  ProcessIptTrace = OpenIptDevice(&FileHandle);
  if ( ProcessIptTrace < 0 )
    goto LABEL_7;
  v9 = AcquireDebugPrivilege(&ReturnedState);
  *(_QWORD *)&InputBuffer = 1;
  DWORD2(InputBuffer) = 1;
  LOWORD(v17) = 1;
  *((_QWORD *)&v17 + 1) = a2;
  ProcessIptTrace = NtDeviceIoControlFile(
                      FileHandle,
                      0,
                      0,
                      0,
                      &IoStatusBlock,
                      0x220004u,
                      &InputBuffer,
                      0x30u,
                      &OutputBuffer,
                      0x18u);
  NtClose(FileHandle);
  if ( v9 )
    RtlReleasePrivilege(ReturnedState);
  if ( ProcessIptTrace < 0 )
    goto LABEL_7;
  v10 = DWORD2(OutputBuffer);
  if ( *((_QWORD *)&OutputBuffer + 1) > 0xFFFFFFFF )
  {
    ProcessIptTrace = -1073740757;
    goto LABEL_7;
  }
  if ( !DWORD2(OutputBuffer) )
    return 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 8LL))(
          *((_QWORD *)this + 6),
          DWORD2(OutputBuffer));
  v13 = (_DWORD *)v12;
  if ( !v12 )
    return -2147024882;
  ProcessIptTrace = GetProcessIptTrace(a2, v12, v10);
  if ( ProcessIptTrace >= 0 )
  {
    *a3 = v13;
    *a4 = v13[1] + 8;
    return 0;
  }
  (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6), v13);
LABEL_7:
  result = RtlNtStatusToDosError(ProcessIptTrace);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180013510  push    rbp
0x180013512  push    rbx
0x180013513  push    rsi
0x180013514  push    rdi
0x180013515  push    r12
0x180013517  push    r14
0x180013519  push    r15
0x18001351b  lea     rbp, [rsp-27h]
0x180013520  sub     rsp, 0C0h
0x180013527  mov     rax, cs:__security_cookie
0x18001352e  xor     rax, rsp
0x180013531  mov     [rbp+57h+var_38], rax
0x180013535  xorps   xmm0, xmm0
0x180013538  mov     [rbp+57h+FileHandle], 0
0x180013540  xor     eax, eax
0x180013542  mov     rsi, rcx
0x180013545  lea     rcx, [rbp+57h+FileHandle]
0x180013549  mov     [rbp+57h+var_40], rax
0x18001354d  movups  [rbp+57h+var_90], xmm0
0x180013551  mov     [rbp+57h+ReturnedState], rax
0x180013555  mov     r12, r9
0x180013558  movups  [rbp+57h+var_80], xmm0
0x18001355c  mov     r15, r8
0x18001355f  mov     r14, rdx
0x180013562  movups  [rbp+57h+var_70], xmm0
0x180013566  movups  [rbp+57h+var_50], xmm0
0x18001356a  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18001356e  call    OpenIptDevice
0x180013573  mov     edi, eax
0x180013575  test    eax, eax
0x180013577  js      loc_180013612
0x18001357d  lea     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x180013581  call    AcquireDebugPrivilege
0x180013586  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001358a  mov     bl, al
0x18001358c  mov     [rsp+0F0h+OutputBufferLength], 18h; OutputBufferLength
0x180013594  mov     eax, 1
0x180013599  mov     qword ptr [rbp+57h+var_90], rax
0x18001359d  xor     r9d, r9d; ApcContext
0x1800135a0  mov     dword ptr [rbp+57h+var_90+8], eax
0x1800135a3  xor     r8d, r8d; ApcRoutine
0x1800135a6  mov     word ptr [rbp+57h+var_80], ax
0x1800135aa  xor     edx, edx; Event
0x1800135ac  lea     rax, [rbp+57h+var_50]
0x1800135b0  mov     qword ptr [rbp+57h+var_80+8], r14
0x1800135b4  mov     [rsp+0F0h+OutputBuffer], rax; OutputBuffer
0x1800135b9  lea     rax, [rbp+57h+var_90]
0x1800135bd  mov     [rsp+0F0h+InputBufferLength], 30h ; '0'; InputBufferLength
0x1800135c5  mov     [rsp+0F0h+InputBuffer], rax; InputBuffer
0x1800135ca  lea     rax, [rbp+57h+var_60]
0x1800135ce  mov     [rsp+0F0h+IoControlCode], 220004h; IoControlCode
0x1800135d6  mov     [rsp+0F0h+IoStatusBlock], rax; IoStatusBlock
0x1800135db  call    cs:__imp_NtDeviceIoControlFile
0x1800135e1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800135e5  mov     edi, eax
0x1800135e7  call    cs:__imp_NtClose
0x1800135ed  test    bl, bl
0x1800135ef  jz      short loc_1800135FB
0x1800135f1  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x1800135f5  call    cs:__imp_RtlReleasePrivilege
0x1800135fb  test    edi, edi
0x1800135fd  js      short loc_180013612
0x1800135ff  mov     rdi, qword ptr [rbp+57h+var_50+8]
0x180013603  mov     eax, 0FFFFFFFFh
0x180013608  cmp     rdi, rax
0x18001360b  jbe     short loc_180013628
0x18001360d  mov     edi, 0C000042Bh
0x180013612  mov     ecx, edi; Status
0x180013614  call    cs:__imp_RtlNtStatusToDosError
0x18001361a  test    eax, eax
0x18001361c  jle     short loc_180013685
0x18001361e  movzx   eax, ax
0x180013621  or      eax, 80070000h
0x180013626  jmp     short loc_180013685
0x180013628  test    edi, edi
0x18001362a  jz      short loc_180013683
0x18001362c  mov     rcx, [rsi+30h]
0x180013630  mov     edx, edi
0x180013632  mov     rax, [rcx]
0x180013635  mov     rax, [rax+8]
0x180013639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001363e  mov     rbx, rax
0x180013641  test    rax, rax
0x180013644  jnz     short loc_18001364D
0x180013646  mov     eax, 8007000Eh
0x18001364b  jmp     short loc_180013685
0x18001364d  mov     r8d, edi
0x180013650  mov     rdx, rbx
0x180013653  mov     rcx, r14
0x180013656  call    GetProcessIptTrace
0x18001365b  mov     edi, eax
0x18001365d  test    eax, eax
0x18001365f  jns     short loc_180013676
0x180013661  mov     rcx, [rsi+30h]
0x180013665  mov     rdx, [rcx]
0x180013668  mov     rax, [rdx+18h]
0x18001366c  mov     rdx, rbx
0x18001366f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013674  jmp     short loc_180013612
0x180013676  mov     [r15], rbx
0x180013679  mov     eax, [rbx+4]
0x18001367c  add     eax, 8
0x18001367f  mov     [r12], eax
0x180013683  xor     eax, eax
0x180013685  mov     rcx, [rbp+57h+var_38]
0x180013689  xor     rcx, rsp; StackCookie
0x18001368c  call    __security_check_cookie
0x180013691  add     rsp, 0C0h
0x180013698  pop     r15
0x18001369a  pop     r14
0x18001369c  pop     r12
0x18001369e  pop     rdi
0x18001369f  pop     rsi
0x1800136a0  pop     rbx
0x1800136a1  pop     rbp
0x1800136a2  retn
```
