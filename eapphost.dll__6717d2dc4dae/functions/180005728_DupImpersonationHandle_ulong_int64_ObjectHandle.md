# DupImpersonationHandle(ulong,__int64,ObjectHandle &)

- ea: `0x180005728`
- end: `0x18000583b`
- name: `?DupImpersonationHandle@@YAJK_JAEAVObjectHandle@@@Z`
- size: `275`
- prototype: `__int64 __fastcall(DWORD dwProcessId, HANDLE hSourceHandle, HANDLE *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180005850`
- `0x180006310`

## callees

- `0x180005728`
- `0x180009dec`
- `0x18002f1f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800057ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800057ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800057d9`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800057cf`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800057cf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005756`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180005756`

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
0x180005728  push    rbx
0x18000572a  push    rbp
0x18000572b  push    rsi
0x18000572c  push    rdi
0x18000572d  push    r15
0x18000572f  sub     rsp, 50h
0x180005733  mov     rdi, rdx
0x180005736  mov     [rsp+78h+var_30], 0
0x18000573f  xor     edx, edx; bInheritHandle
0x180005741  lea     r15, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180005748  mov     rbp, r8
0x18000574b  mov     [rsp+78h+var_38], r15
0x180005750  mov     r8d, ecx; dwProcessId
0x180005753  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180005756  call    cs:__imp_OpenProcess
0x18000575c  lea     rcx, [rsp+78h+var_38]; this
0x180005761  mov     rsi, rax
0x180005764  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180005769  mov     [rsp+78h+var_30], rsi
0x18000576e  test    rsi, rsi
0x180005771  jnz     short loc_18000579D
0x180005773  call    cs:__imp_GetLastError
0x180005779  mov     ebx, eax
0x18000577b  mov     rcx, cs:WPP_GLOBAL_Control
0x180005782  lea     rax, WPP_GLOBAL_Control
0x180005789  cmp     rcx, rax
0x18000578c  jz      loc_180005812
0x180005792  test    byte ptr [rcx+1Ch], 1
0x180005796  jz      short loc_180005812
0x180005798  lea     edx, [rsi+0Ah]
0x18000579b  jmp     short loc_1800057FF
0x18000579d  xor     ebx, ebx
0x18000579f  test    rdi, rdi
0x1800057a2  jz      short loc_18000581F
0x1800057a4  mov     rcx, rbp; this
0x1800057a7  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x1800057ac  call    cs:__imp_GetCurrentProcess
0x1800057b2  mov     [rsp+78h+dwOptions], 2; dwOptions
0x1800057ba  lea     r9, [rbp+8]; lpTargetHandle
0x1800057be  mov     r8, rax; hTargetProcessHandle
0x1800057c1  mov     [rsp+78h+bInheritHandle], ebx; bInheritHandle
0x1800057c5  mov     rdx, rdi; hSourceHandle
0x1800057c8  mov     [rsp+78h+dwDesiredAccess], ebx; dwDesiredAccess
0x1800057cc  mov     rcx, rsi; hSourceProcessHandle
0x1800057cf  call    cs:__imp_DuplicateHandle
0x1800057d5  test    eax, eax
0x1800057d7  jnz     short loc_18000581F
0x1800057d9  call    cs:__imp_GetLastError
0x1800057df  mov     ebx, eax
0x1800057e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057e8  lea     rax, WPP_GLOBAL_Control
0x1800057ef  cmp     rcx, rax
0x1800057f2  jz      short loc_180005812
0x1800057f4  test    byte ptr [rcx+1Ch], 1
0x1800057f8  jz      short loc_180005812
0x1800057fa  mov     edx, 0Bh
0x1800057ff  mov     rcx, [rcx+10h]
0x180005803  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000580a  mov     r9d, ebx
0x18000580d  call    WPP_SF_d
0x180005812  test    ebx, ebx
0x180005814  jle     short loc_18000581F
0x180005816  movzx   ebx, bx
0x180005819  or      ebx, 80070000h
0x18000581f  lea     rcx, [rsp+78h+var_38]; this
0x180005824  mov     [rsp+78h+var_38], r15
0x180005829  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000582e  mov     eax, ebx
0x180005830  add     rsp, 50h
0x180005834  pop     r15
0x180005836  pop     rdi
0x180005837  pop     rsi
0x180005838  pop     rbp
0x180005839  pop     rbx
0x18000583a  retn
```
