# CldiPortAccessCheck

- ea: `0x14007e674`
- end: `0x14007e7ab`
- name: `CldiPortAccessCheck`
- size: `311`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140039320`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140033f48`
- `0x1400561e8`
- `0x140056ccc`
- `0x1400577f8`
- `0x14007e674`

## import_xrefs

- `FLTMGR!FltReleasePushLockEx` at `0x14007e6b3`
- `FLTMGR!FltReleasePushLockEx` at `0x14007e6b3`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14007e694`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14007e694`

## pseudocode

```c
__int64 __fastcall CldiPortAccessCheck(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v7; // rdi
  __int64 v8; // rbx
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
    LODWORD(v8) = 0;
    v11 = CldSyncReferenceStream(v7, a3, 0);
    v12 = v11;
    if ( v11 )
    {
      v8 = (unsigned int)HsmpAccessCheckByFileId(
                           **(_QWORD **)(**(_QWORD **)(v11 + 8) + 8LL),
                           *(_QWORD *)(*(_QWORD *)(***(_QWORD ***)(v11 + 8) + 16LL) + 32LL));
      HsmDbgBreakOnStatus(v8);
      CldiSyncReleaseRundown(v12);
    }
    HsmDbgBreakOnStatus((unsigned int)v8);
    if ( (int)v8 < 0 )
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
    LODWORD(v8) = -1073688831;
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
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14007e674  push    rbx
0x14007e676  push    rbp
0x14007e677  push    rsi
0x14007e678  push    rdi
0x14007e679  push    r14
0x14007e67b  sub     rsp, 40h
0x14007e67f  lea     rbx, [rcx+90h]
0x14007e686  mov     r14, rdx
0x14007e689  mov     rbp, rcx
0x14007e68c  xor     edx, edx
0x14007e68e  mov     rcx, rbx
0x14007e691  mov     rsi, r8
0x14007e694  call    cs:__imp_FltAcquirePushLockSharedEx
0x14007e69b  nop     dword ptr [rax+rax+00h]
0x14007e6a0  mov     rdx, r14
0x14007e6a3  mov     rcx, rbp
0x14007e6a6  call    CldiPortLookupSyncRootNoLock
0x14007e6ab  xor     edx, edx
0x14007e6ad  mov     rcx, rbx
0x14007e6b0  mov     rdi, rax
0x14007e6b3  call    cs:__imp_FltReleasePushLockEx
0x14007e6ba  nop     dword ptr [rax+rax+00h]
0x14007e6bf  test    rdi, rdi
0x14007e6c2  jnz     short loc_14007E703
0x14007e6c4  mov     ebx, 0C000CF01h
0x14007e6c9  mov     ecx, ebx
0x14007e6cb  call    HsmDbgBreakOnStatus
0x14007e6d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e6d7  lea     rax, WPP_GLOBAL_Control
0x14007e6de  cmp     rcx, rax
0x14007e6e1  jz      loc_14007E79D
0x14007e6e7  test    dword ptr [rcx+2Ch], 100h
0x14007e6ee  jz      loc_14007E79D
0x14007e6f4  cmp     byte ptr [rcx+29h], 2
0x14007e6f8  jb      loc_14007E79D
0x14007e6fe  lea     edx, [rdi+2Eh]
0x14007e701  jmp     short loc_14007E77C
0x14007e703  xor     r8d, r8d
0x14007e706  mov     rdx, rsi
0x14007e709  mov     rcx, rdi
0x14007e70c  xor     ebx, ebx
0x14007e70e  call    CldSyncReferenceStream
0x14007e713  mov     rdi, rax
0x14007e716  test    rax, rax
0x14007e719  jz      short loc_14007E74A
0x14007e71b  mov     rcx, [rax+8]
0x14007e71f  mov     r8, [rcx]
0x14007e722  mov     rcx, [r8]
0x14007e725  mov     rdx, [rcx+10h]
0x14007e729  mov     rcx, [r8+8]
0x14007e72d  mov     rdx, [rdx+20h]
0x14007e731  mov     rcx, [rcx]
0x14007e734  call    HsmpAccessCheckByFileId
0x14007e739  mov     ecx, eax
0x14007e73b  mov     ebx, eax
0x14007e73d  call    HsmDbgBreakOnStatus
0x14007e742  mov     rcx, rdi
0x14007e745  call    CldiSyncReleaseRundown
0x14007e74a  mov     ecx, ebx
0x14007e74c  call    HsmDbgBreakOnStatus
0x14007e751  test    ebx, ebx
0x14007e753  jns     short loc_14007E79D
0x14007e755  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e75c  lea     rax, WPP_GLOBAL_Control
0x14007e763  cmp     rcx, rax
0x14007e766  jz      short loc_14007E79D
0x14007e768  test    dword ptr [rcx+2Ch], 100h
0x14007e76f  jz      short loc_14007E79D
0x14007e771  cmp     byte ptr [rcx+29h], 2
0x14007e775  jb      short loc_14007E79D
0x14007e777  mov     edx, 2Fh ; '/'
0x14007e77c  mov     rcx, [rcx+18h]
0x14007e780  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x14007e787  mov     [rsp+68h+var_38], ebx
0x14007e78b  mov     r9, rbp
0x14007e78e  mov     [rsp+68h+var_40], rsi
0x14007e793  mov     [rsp+68h+var_48], r14
0x14007e798  call    WPP_SF_qqqd
0x14007e79d  mov     eax, ebx
0x14007e79f  add     rsp, 40h
0x14007e7a3  pop     r14
0x14007e7a5  pop     rdi
0x14007e7a6  pop     rsi
0x14007e7a7  pop     rbp
0x14007e7a8  pop     rbx
0x14007e7a9  retn
```
