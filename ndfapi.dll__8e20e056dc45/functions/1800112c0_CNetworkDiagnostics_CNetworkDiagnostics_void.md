# CNetworkDiagnostics::~CNetworkDiagnostics(void)

- ea: `0x1800112c0`
- end: `0x180011320`
- name: `??1CNetworkDiagnostics@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(CNetworkDiagnostics *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800116d0`

## callees

- `0x180008c08`
- `0x18000a160`
- `0x1800112c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011319`
- `KERNEL32!CloseHandle` at `0x1800112e2`
- `KERNEL32!CloseHandle` at `0x1800112e2`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800112d8`
- `KERNEL32!WaitForSingleObjectEx` at `0x1800112d8`

## pseudocode

```c
void __fastcall CNetworkDiagnostics::~CNetworkDiagnostics(CNetworkDiagnostics *this)
{
  void *v2; // rcx
  unsigned int v3; // edx
  void *v4; // rcx

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
    CloseHandle(*((HANDLE *)this + 5));
  }
  v3 = *((_DWORD *)this + 8);
  if ( v3 )
    FreeRootCauseInfos(*((struct tagRootCauseInfo **)this + 3), v3, 1);
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 != (void *)-1LL )
    NdfCloseIncident(v4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
}

```

## disassembly

```asm
0x1800112c0  push    rbx
0x1800112c2  sub     rsp, 20h
0x1800112c6  mov     rbx, rcx
0x1800112c9  mov     rcx, [rcx+28h]; hHandle
0x1800112cd  test    rcx, rcx
0x1800112d0  jz      short loc_1800112E8
0x1800112d2  xor     r8d, r8d; bAlertable
0x1800112d5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800112d8  call    cs:__imp_WaitForSingleObjectEx
0x1800112de  mov     rcx, [rbx+28h]; hObject
0x1800112e2  call    cs:__imp_CloseHandle
0x1800112e8  mov     edx, [rbx+20h]; unsigned int
0x1800112eb  test    edx, edx
0x1800112ed  jz      short loc_1800112FE
0x1800112ef  mov     rcx, [rbx+18h]; pv
0x1800112f3  mov     r8d, 1; int
0x1800112f9  call    ?FreeRootCauseInfos@@YAXPEAUtagRootCauseInfo@@KH@Z; FreeRootCauseInfos(tagRootCauseInfo *,ulong,int)
0x1800112fe  mov     rcx, [rbx+10h]; handle
0x180011302  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180011306  jz      short loc_18001130D
0x180011308  call    NdfCloseIncident
0x18001130d  lea     rcx, [rbx+80h]
0x180011314  add     rsp, 20h
0x180011318  pop     rbx
0x180011319  jmp     cs:__imp_DeleteCriticalSection
```
