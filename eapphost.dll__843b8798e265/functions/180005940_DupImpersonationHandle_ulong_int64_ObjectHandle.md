# DupImpersonationHandle(ulong,__int64,ObjectHandle &)

- ea: `0x180005940`
- end: `0x180005a7a`
- name: `?DupImpersonationHandle@@YAJK_JAEAVObjectHandle@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(DWORD dwProcessId, HANDLE hSourceHandle, struct ObjectHandle *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180005a80`
- `0x180006580`

## callees

- `0x180005940`
- `0x18000a24c`
- `0x18003032c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800059d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800059d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a11`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005a01`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180005a01`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000596e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000596e`

## pseudocode

```c
__int64 __fastcall DupImpersonationHandle(DWORD dwProcessId, HANDLE hSourceHandle, HANDLE *this)
{
  HANDLE v5; // rsi
  DWORD LastError; // ebx
  EapHost::Peer::Host *v7; // rcx
  __int64 v8; // rdx
  HANDLE CurrentProcess; // rax
  void **v11; // [rsp+40h] [rbp-38h] BYREF
  HANDLE v12; // [rsp+48h] [rbp-30h]

  v12 = 0;
  v11 = &ObjectHandle::`vftable';
  v5 = OpenProcess(0x40u, 0, dwProcessId);
  ObjectHandle::Clear((ObjectHandle *)&v11);
  v12 = v5;
  if ( v5 )
  {
    LastError = 0;
    if ( !hSourceHandle )
      goto LABEL_13;
    ObjectHandle::Clear((ObjectHandle *)this);
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(v5, hSourceHandle, CurrentProcess, this + 1, 0, 0, 2u) )
      goto LABEL_13;
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 11;
      goto LABEL_10;
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v8 = 10;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, LastError);
    }
  }
  if ( (int)LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  v11 = &ObjectHandle::`vftable';
  ObjectHandle::Clear((ObjectHandle *)&v11);
  return LastError;
}

```

## disassembly

```asm
0x180005940  push    rbx
0x180005942  push    rbp
0x180005943  push    rsi
0x180005944  push    rdi
0x180005945  push    r15
0x180005947  sub     rsp, 50h
0x18000594b  mov     rdi, rdx
0x18000594e  mov     [rsp+78h+var_30], 0
0x180005957  xor     edx, edx; bInheritHandle
0x180005959  lea     r15, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180005960  mov     rbp, r8
0x180005963  mov     [rsp+78h+var_38], r15
0x180005968  mov     r8d, ecx; dwProcessId
0x18000596b  lea     ecx, [rdx+40h]; dwDesiredAccess
0x18000596e  call    cs:__imp_OpenProcess
0x180005975  nop     dword ptr [rax+rax+00h]
0x18000597a  lea     rcx, [rsp+78h+var_38]; this
0x18000597f  mov     rsi, rax
0x180005982  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180005987  mov     [rsp+78h+var_30], rsi
0x18000598c  test    rsi, rsi
0x18000598f  jnz     short loc_1800059C5
0x180005991  call    cs:__imp_GetLastError
0x180005998  nop     dword ptr [rax+rax+00h]
0x18000599d  mov     ebx, eax
0x18000599f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059a6  lea     rax, WPP_GLOBAL_Control
0x1800059ad  cmp     rcx, rax
0x1800059b0  jz      loc_180005A50
0x1800059b6  test    byte ptr [rcx+1Ch], 1
0x1800059ba  jz      loc_180005A50
0x1800059c0  lea     edx, [rsi+0Ah]
0x1800059c3  jmp     short loc_180005A3D
0x1800059c5  xor     ebx, ebx
0x1800059c7  test    rdi, rdi
0x1800059ca  jz      loc_180005A5D
0x1800059d0  mov     rcx, rbp; this
0x1800059d3  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x1800059d8  call    cs:__imp_GetCurrentProcess
0x1800059df  nop     dword ptr [rax+rax+00h]
0x1800059e4  mov     [rsp+78h+dwOptions], 2; dwOptions
0x1800059ec  lea     r9, [rbp+8]; lpTargetHandle
0x1800059f0  mov     r8, rax; hTargetProcessHandle
0x1800059f3  mov     [rsp+78h+bInheritHandle], ebx; bInheritHandle
0x1800059f7  mov     rdx, rdi; hSourceHandle
0x1800059fa  mov     [rsp+78h+dwDesiredAccess], ebx; dwDesiredAccess
0x1800059fe  mov     rcx, rsi; hSourceProcessHandle
0x180005a01  call    cs:__imp_DuplicateHandle
0x180005a08  nop     dword ptr [rax+rax+00h]
0x180005a0d  test    eax, eax
0x180005a0f  jnz     short loc_180005A5D
0x180005a11  call    cs:__imp_GetLastError
0x180005a18  nop     dword ptr [rax+rax+00h]
0x180005a1d  mov     ebx, eax
0x180005a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a26  lea     rax, WPP_GLOBAL_Control
0x180005a2d  cmp     rcx, rax
0x180005a30  jz      short loc_180005A50
0x180005a32  test    byte ptr [rcx+1Ch], 1
0x180005a36  jz      short loc_180005A50
0x180005a38  mov     edx, 0Bh
0x180005a3d  mov     rcx, [rcx+10h]
0x180005a41  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180005a48  mov     r9d, ebx
0x180005a4b  call    WPP_SF_d
0x180005a50  test    ebx, ebx
0x180005a52  jle     short loc_180005A5D
0x180005a54  movzx   ebx, bx
0x180005a57  or      ebx, 80070000h
0x180005a5d  lea     rcx, [rsp+78h+var_38]; this
0x180005a62  mov     [rsp+78h+var_38], r15
0x180005a67  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180005a6c  mov     eax, ebx
0x180005a6e  add     rsp, 50h
0x180005a72  pop     r15
0x180005a74  pop     rdi
0x180005a75  pop     rsi
0x180005a76  pop     rbp
0x180005a77  pop     rbx
0x180005a78  retn
```
