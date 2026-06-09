# CldiPortAccessCheck

- ea: `0x14007e4dc`
- end: `0x14007e613`
- name: `CldiPortAccessCheck`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140039300`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140033f48`
- `0x1400560c8`
- `0x140056bac`
- `0x1400576d8`
- `0x14007e4dc`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14007e51b`
- `FLTMGR!FltReleasePushLockEx` at `0x14007e51b`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14007e4fc`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14007e4fc`

## pseudocode

```c
__int64 __fastcall CldiPortAccessCheck(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v7; // rdi
  unsigned int v8; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rdi

  v3 = a1 + 144;
  FltAcquirePushLockSharedEx(a1 + 144, 0);
  v7 = CldiPortLookupSyncRootNoLock(a1, a2);
  FltReleasePushLockEx(v3, 0);
  if ( v7 )
  {
    v8 = 0;
    v11 = CldSyncReferenceStream(v7, a3, 0);
    v12 = v11;
    if ( v11 )
    {
      v8 = HsmpAccessCheckByFileId(
             **(_QWORD **)(**(_QWORD **)(v11 + 8) + 8LL),
             *(_QWORD *)(*(_QWORD *)(***(_QWORD ***)(v11 + 8) + 16LL) + 32LL));
      HsmDbgBreakOnStatus(v8);
      CldiSyncReleaseRundown(v12);
    }
    HsmDbgBreakOnStatus(v8);
    if ( (v8 & 0x80000000) != 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v10 = 47;
        goto LABEL_13;
      }
    }
  }
  else
  {
    v8 = -1073688831;
    HsmDbgBreakOnStatus(3221278465LL);
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v10 = 46;
LABEL_13:
      WPP_SF_qqqd(v9->AttachedDevice, v10, WPP_452df49304b034ad87c0baec305776b3_Traceguids, a1, a2, a3, v8);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14007e4dc  push    rbx
0x14007e4de  push    rbp
0x14007e4df  push    rsi
0x14007e4e0  push    rdi
0x14007e4e1  push    r14
0x14007e4e3  sub     rsp, 40h
0x14007e4e7  lea     rbx, [rcx+90h]
0x14007e4ee  mov     r14, rdx
0x14007e4f1  mov     rbp, rcx
0x14007e4f4  xor     edx, edx
0x14007e4f6  mov     rcx, rbx
0x14007e4f9  mov     rsi, r8
0x14007e4fc  call    cs:__imp_FltAcquirePushLockSharedEx
0x14007e503  nop     dword ptr [rax+rax+00h]
0x14007e508  mov     rdx, r14
0x14007e50b  mov     rcx, rbp
0x14007e50e  call    CldiPortLookupSyncRootNoLock
0x14007e513  xor     edx, edx
0x14007e515  mov     rcx, rbx
0x14007e518  mov     rdi, rax
0x14007e51b  call    cs:__imp_FltReleasePushLockEx
0x14007e522  nop     dword ptr [rax+rax+00h]
0x14007e527  test    rdi, rdi
0x14007e52a  jnz     short loc_14007E56B
0x14007e52c  mov     ebx, 0C000CF01h
0x14007e531  mov     ecx, ebx
0x14007e533  call    HsmDbgBreakOnStatus
0x14007e538  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e53f  lea     rax, WPP_GLOBAL_Control
0x14007e546  cmp     rcx, rax
0x14007e549  jz      loc_14007E605
0x14007e54f  test    dword ptr [rcx+2Ch], 100h
0x14007e556  jz      loc_14007E605
0x14007e55c  cmp     byte ptr [rcx+29h], 2
0x14007e560  jb      loc_14007E605
0x14007e566  lea     edx, [rdi+2Eh]
0x14007e569  jmp     short loc_14007E5E4
0x14007e56b  xor     r8d, r8d
0x14007e56e  mov     rdx, rsi
0x14007e571  mov     rcx, rdi
0x14007e574  xor     ebx, ebx
0x14007e576  call    CldSyncReferenceStream
0x14007e57b  mov     rdi, rax
0x14007e57e  test    rax, rax
0x14007e581  jz      short loc_14007E5B2
0x14007e583  mov     rcx, [rax+8]
0x14007e587  mov     r8, [rcx]
0x14007e58a  mov     rcx, [r8]
0x14007e58d  mov     rdx, [rcx+10h]
0x14007e591  mov     rcx, [r8+8]
0x14007e595  mov     rdx, [rdx+20h]
0x14007e599  mov     rcx, [rcx]
0x14007e59c  call    HsmpAccessCheckByFileId
0x14007e5a1  mov     ecx, eax
0x14007e5a3  mov     ebx, eax
0x14007e5a5  call    HsmDbgBreakOnStatus
0x14007e5aa  mov     rcx, rdi
0x14007e5ad  call    CldiSyncReleaseRundown
0x14007e5b2  mov     ecx, ebx
0x14007e5b4  call    HsmDbgBreakOnStatus
0x14007e5b9  test    ebx, ebx
0x14007e5bb  jns     short loc_14007E605
0x14007e5bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e5c4  lea     rax, WPP_GLOBAL_Control
0x14007e5cb  cmp     rcx, rax
0x14007e5ce  jz      short loc_14007E605
0x14007e5d0  test    dword ptr [rcx+2Ch], 100h
0x14007e5d7  jz      short loc_14007E605
0x14007e5d9  cmp     byte ptr [rcx+29h], 2
0x14007e5dd  jb      short loc_14007E605
0x14007e5df  mov     edx, 2Fh ; '/'
0x14007e5e4  mov     rcx, [rcx+18h]
0x14007e5e8  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x14007e5ef  mov     [rsp+68h+var_38], ebx
0x14007e5f3  mov     r9, rbp
0x14007e5f6  mov     [rsp+68h+var_40], rsi
0x14007e5fb  mov     [rsp+68h+var_48], r14
0x14007e600  call    WPP_SF_qqqd
0x14007e605  mov     eax, ebx
0x14007e607  add     rsp, 40h
0x14007e60b  pop     r14
0x14007e60d  pop     rdi
0x14007e60e  pop     rsi
0x14007e60f  pop     rbp
0x14007e610  pop     rbx
0x14007e611  retn
```
