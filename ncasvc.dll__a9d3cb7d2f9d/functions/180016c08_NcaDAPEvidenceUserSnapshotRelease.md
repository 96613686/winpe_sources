# NcaDAPEvidenceUserSnapshotRelease

- ea: `0x180016c08`
- end: `0x180016ca0`
- name: `NcaDAPEvidenceUserSnapshotRelease`
- size: `152`
- prototype: `__int64 __fastcall(char *lpMem)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x180001400`
- `0x180009998`
- `0x180015f20`
- `0x180016468`
- `0x180016798`

## callees

- `0x180003770`
- `0x180004f04`
- `0x180016c08`
- `0x1800190a0`

## pseudocode

```c
__int64 __fastcall NcaDAPEvidenceUserSnapshotRelease(char *lpMem)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_618387925699392817eae358b6323a44_Traceguids);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)lpMem + 162, 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
  {
    NcaCriticalSectionDestroy((LPCRITICAL_SECTION)(lpMem + 16));
    NcaCriticalSectionDestroy((LPCRITICAL_SECTION)(lpMem + 64));
    result = NcaFree(lpMem);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_618387925699392817eae358b6323a44_Traceguids);
  return result;
}

```

## disassembly

```asm
0x180016c08  mov     [rsp+arg_8], rbx
0x180016c0d  push    rdi
0x180016c0e  sub     rsp, 20h
0x180016c12  mov     rbx, rcx
0x180016c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c1c  lea     rdi, WPP_GLOBAL_Control
0x180016c23  cmp     rcx, rdi
0x180016c26  jz      short loc_180016C43
0x180016c28  test    byte ptr [rcx+1Ch], 8
0x180016c2c  jz      short loc_180016C43
0x180016c2e  mov     rcx, [rcx+10h]
0x180016c32  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180016c39  mov     edx, 11h
0x180016c3e  call    WPP_SF_
0x180016c43  or      eax, 0FFFFFFFFh
0x180016c46  lock xadd [rbx+288h], eax
0x180016c4e  cmp     eax, 1
0x180016c51  jnz     short loc_180016C6D
0x180016c53  lea     rcx, [rbx+10h]; lpCriticalSection
0x180016c57  call    NcaCriticalSectionDestroy
0x180016c5c  lea     rcx, [rbx+40h]; lpCriticalSection
0x180016c60  call    NcaCriticalSectionDestroy
0x180016c65  mov     rcx, rbx; lpMem
0x180016c68  call    NcaFree
0x180016c6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c74  cmp     rcx, rdi
0x180016c77  jz      short loc_180016C94
0x180016c79  test    byte ptr [rcx+1Ch], 8
0x180016c7d  jz      short loc_180016C94
0x180016c7f  mov     rcx, [rcx+10h]
0x180016c83  lea     r8, WPP_618387925699392817eae358b6323a44_Traceguids
0x180016c8a  mov     edx, 12h
0x180016c8f  call    WPP_SF_
0x180016c94  mov     rbx, [rsp+28h+arg_8]
0x180016c99  add     rsp, 20h
0x180016c9d  pop     rdi
0x180016c9e  retn
```
