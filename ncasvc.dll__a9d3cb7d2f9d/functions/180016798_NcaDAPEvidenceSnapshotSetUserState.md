# NcaDAPEvidenceSnapshotSetUserState

- ea: `0x180016798`
- end: `0x180016880`
- name: `NcaDAPEvidenceSnapshotSetUserState`
- size: `232`
- prototype: `__int64 __fastcall(int, int, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001c70`
- `0x180011d54`
- `0x180012fe0`
- `0x1800134c0`

## callees

- `0x180003540`
- `0x1800163cc`
- `0x180016798`
- `0x180016c08`
- `0x18001cc70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016829`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016819`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180016819`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167e7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800167e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800167cc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800167cc`

## pseudocode

```c
__int64 __fastcall NcaDAPEvidenceSnapshotSetUserState(int a1, int a2, unsigned int a3)
{
  __int64 v3; // r14
  __int64 v6; // rbx
  int v7; // esi
  __int64 v8; // rdx
  __int64 v9; // rcx
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-48h] BYREF

  v3 = a1;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v6 = NcaDAPEvidenceUserSnapshotFind(a3);
  EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
  v7 = *(_DWORD *)(v6 + 20 * v3 + 112);
  if ( v7 != a2 )
  {
    *(_DWORD *)(v6 + 20 * v3 + 112) = a2;
    *(struct _SYSTEMTIME *)(v6 + 20 * v3 + 116) = SystemTime;
    SetEvent(*(HANDLE *)(*(_QWORD *)(v6 + 624) + 8LL));
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 64));
  if ( v7 != a2 && (Microsoft_Windows_NcasvcEnableBits & 1) != 0 )
    McTemplateU0qttx_EventWriteTransfer(v9, v8, (unsigned int)v3, v7, a2, a3);
  return NcaDAPEvidenceUserSnapshotRelease((LPVOID)v6);
}

```

## disassembly

```asm
0x180016798  mov     [rsp+arg_8], rbx
0x18001679d  push    rbp
0x18001679e  push    rsi
0x18001679f  push    rdi
0x1800167a0  push    r14
0x1800167a2  push    r15
0x1800167a4  sub     rsp, 50h
0x1800167a8  mov     rax, cs:__security_cookie
0x1800167af  xor     rax, rsp
0x1800167b2  mov     [rsp+78h+var_38], rax
0x1800167b7  movsxd  r14, ecx
0x1800167ba  xorps   xmm0, xmm0
0x1800167bd  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x1800167c2  mov     r15d, r8d
0x1800167c5  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x1800167ca  mov     edi, edx
0x1800167cc  call    cs:__imp_GetSystemTime
0x1800167d3  nop     dword ptr [rax+rax+00h]
0x1800167d8  mov     ecx, r15d
0x1800167db  call    NcaDAPEvidenceUserSnapshotFind
0x1800167e0  mov     rbx, rax
0x1800167e3  lea     rcx, [rax+40h]; lpCriticalSection
0x1800167e7  call    cs:__imp_EnterCriticalSection
0x1800167ee  nop     dword ptr [rax+rax+00h]
0x1800167f3  lea     rax, [r14+r14*4]
0x1800167f7  mov     esi, [rbx+rax*4+70h]
0x1800167fb  cmp     esi, edi
0x1800167fd  jz      short loc_180016825
0x1800167ff  mov     [rbx+rax*4+70h], edi
0x180016803  movups  xmm0, xmmword ptr [rsp+78h+SystemTime.wYear]
0x180016808  movdqu  xmmword ptr [rbx+rax*4+74h], xmm0
0x18001680e  mov     rcx, [rbx+270h]
0x180016815  mov     rcx, [rcx+8]; hEvent
0x180016819  call    cs:__imp_SetEvent
0x180016820  nop     dword ptr [rax+rax+00h]
0x180016825  lea     rcx, [rbx+40h]; lpCriticalSection
0x180016829  call    cs:__imp_LeaveCriticalSection
0x180016830  nop     dword ptr [rax+rax+00h]
0x180016835  cmp     esi, edi
0x180016837  jz      short loc_180016856
0x180016839  test    cs:Microsoft_Windows_NcasvcEnableBits, 1
0x180016840  jz      short loc_180016856
0x180016842  mov     [rsp+78h+var_50], r15
0x180016847  mov     r9d, esi
0x18001684a  mov     r8d, r14d
0x18001684d  mov     [rsp+78h+var_58], edi
0x180016851  call    McTemplateU0qttx_EventWriteTransfer
0x180016856  mov     rcx, rbx; lpMem
0x180016859  call    NcaDAPEvidenceUserSnapshotRelease
0x18001685e  mov     rcx, [rsp+78h+var_38]
0x180016863  xor     rcx, rsp; StackCookie
0x180016866  call    __security_check_cookie
0x18001686b  mov     rbx, [rsp+78h+arg_8]
0x180016873  add     rsp, 50h
0x180016877  pop     r15
0x180016879  pop     r14
0x18001687b  pop     rdi
0x18001687c  pop     rsi
0x18001687d  pop     rbp
0x18001687e  retn
```
