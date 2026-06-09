# CDXGIMutexInSeparateThread::InitMutex(ushort const *)

- ea: `0x180081180`
- end: `0x180081279`
- name: `?InitMutex@CDXGIMutexInSeparateThread@@QEAAJPEBG@Z`
- size: `249`
- prototype: `__int64 __fastcall(CDXGIMutexInSeparateThread *__hidden this, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ef60`

## callees

- `0x18001fae8`
- `0x18005f488`
- `0x180080f88`
- `0x1800810f8`
- `0x180081180`
- `0x1800812d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800811d6`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800811d6`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800811bd`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x1800811bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081224`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081224`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081216`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800811f7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800811f7`

## pseudocode

```c
__int64 __fastcall CDXGIMutexInSeparateThread::InitMutex(CDXGIMutexInSeparateThread *this, LPCWSTR lpName)
{
  HANDLE MutexW; // rax
  int v5; // ebx
  bool v6; // cf
  struct _SECURITY_ATTRIBUTES v8[2]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v9; // [rsp+50h] [rbp-18h]
  PSID Sid; // [rsp+70h] [rbp+8h] BYREF

  memset(v8, 0, sizeof(v8));
  v9 = 0;
  DxSecurityAttributesCreate((struct _DX_SECURITY_ATTRIBUTES *)v8);
  MutexW = CreateMutexW(&v8[1], 0, lpName);
  *((_QWORD *)this + 7) = MutexW;
  if ( MutexW )
  {
    Sid = 0;
    if ( !ConvertStringSidToSidW(L"LW", &Sid)
      || (v5 = SetHandleIntegrityLevel(*((HANDLE *)this + 7), Sid), LocalFree(Sid), v5 < 0) )
    {
      CloseHandle(*((HANDLE *)this + 7));
      *((_QWORD *)this + 7) = 0;
    }
  }
  else
  {
    *((_QWORD *)this + 7) = OpenMutexW(0x100000u, 0, lpName);
  }
  DxSecurityAttributesRelease((struct _DX_SECURITY_ATTRIBUTES *)v8);
  if ( *((_QWORD *)this + 7) && (int)ThreadAffinitizedWorkerThread<enum MUTEX_COMMANDS>::InitThread(this) < 0 )
    CDXGIMutexInSeparateThread::DestroyMutex(this);
  v6 = *((_QWORD *)this + 7) != 0;
  *((_DWORD *)this + 16) = 0;
  return v6 ? 0 : 0x80004005;
}

```

## disassembly

```asm
0x180081180  mov     [rsp+arg_8], rbx
0x180081185  push    rdi
0x180081186  sub     rsp, 60h
0x18008118a  xorps   xmm0, xmm0
0x18008118d  mov     rdi, rcx
0x180081190  xor     eax, eax
0x180081192  lea     rcx, [rsp+68h+var_48]; struct _DX_SECURITY_ATTRIBUTES *
0x180081197  movups  [rsp+68h+var_48], xmm0
0x18008119c  mov     [rsp+68h+var_18], rax
0x1800811a1  mov     rbx, rdx
0x1800811a4  movups  xmmword ptr [rsp+68h+MutexAttributes.nLength], xmm0
0x1800811a9  movups  xmmword ptr [rsp+68h+MutexAttributes.bInheritHandle], xmm0
0x1800811ae  call    ?DxSecurityAttributesCreate@@YAXPEAU_DX_SECURITY_ATTRIBUTES@@@Z; DxSecurityAttributesCreate(_DX_SECURITY_ATTRIBUTES *)
0x1800811b3  mov     r8, rbx; lpName
0x1800811b6  lea     rcx, [rsp+68h+MutexAttributes.lpSecurityDescriptor]; lpMutexAttributes
0x1800811bb  xor     edx, edx; bInitialOwner
0x1800811bd  call    cs:__imp_CreateMutexW
0x1800811c3  mov     [rdi+38h], rax
0x1800811c7  test    rax, rax
0x1800811ca  jnz     short loc_1800811E2
0x1800811cc  mov     r8, rbx; lpName
0x1800811cf  xor     edx, edx; bInheritHandle
0x1800811d1  mov     ecx, 100000h; dwDesiredAccess
0x1800811d6  call    cs:__imp_OpenMutexW
0x1800811dc  mov     [rdi+38h], rax
0x1800811e0  jmp     short loc_180081232
0x1800811e2  lea     rdx, [rsp+68h+Sid]; Sid
0x1800811e7  mov     [rsp+68h+Sid], 0
0x1800811f0  lea     rcx, StringSid; "LW"
0x1800811f7  call    cs:__imp_ConvertStringSidToSidW
0x1800811fd  test    eax, eax
0x1800811ff  jz      short loc_180081220
0x180081201  mov     rdx, [rsp+68h+Sid]; pLabelSid
0x180081206  mov     rcx, [rdi+38h]; Handle
0x18008120a  call    ?SetHandleIntegrityLevel@@YAJPEAX0@Z; SetHandleIntegrityLevel(void *,void *)
0x18008120f  mov     rcx, [rsp+68h+Sid]; hMem
0x180081214  mov     ebx, eax
0x180081216  call    cs:__imp_LocalFree
0x18008121c  test    ebx, ebx
0x18008121e  jns     short loc_180081232
0x180081220  mov     rcx, [rdi+38h]; hObject
0x180081224  call    cs:__imp_CloseHandle
0x18008122a  mov     qword ptr [rdi+38h], 0
0x180081232  lea     rcx, [rsp+68h+var_48]; struct _DX_SECURITY_ATTRIBUTES *
0x180081237  call    ?DxSecurityAttributesRelease@@YAXPEAU_DX_SECURITY_ATTRIBUTES@@@Z; DxSecurityAttributesRelease(_DX_SECURITY_ATTRIBUTES *)
0x18008123c  cmp     qword ptr [rdi+38h], 0
0x180081241  jz      short loc_180081257
0x180081243  mov     rcx, rdi; lpParameter
0x180081246  call    ?InitThread@?$ThreadAffinitizedWorkerThread@W4MUTEX_COMMANDS@@@@IEAAJXZ; ThreadAffinitizedWorkerThread<MUTEX_COMMANDS>::InitThread(void)
0x18008124b  test    eax, eax
0x18008124d  jns     short loc_180081257
0x18008124f  mov     rcx, rdi; this
0x180081252  call    ?DestroyMutex@CDXGIMutexInSeparateThread@@QEAAXXZ; CDXGIMutexInSeparateThread::DestroyMutex(void)
0x180081257  mov     rax, [rdi+38h]
0x18008125b  mov     rbx, [rsp+68h+arg_8]
0x180081260  neg     rax
0x180081263  mov     dword ptr [rdi+40h], 0
0x18008126a  sbb     eax, eax
0x18008126c  not     eax
0x18008126e  and     eax, 80004005h
0x180081273  add     rsp, 60h
0x180081277  pop     rdi
0x180081278  retn
```
