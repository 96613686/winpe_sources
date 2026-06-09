# DfscNetUseIncrementOpenHandleCount

- ea: `0x14000141c`
- end: `0x1400015b9`
- name: `DfscNetUseIncrementOpenHandleCount`
- size: `413`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14001e3d0`

## callees

- `0x14000141c`
- `0x140004bd4`
- `0x140005f70`
- `0x140025efc`
- `0x1400264e0`
- `0x140026ed0`
- `0x140026f60`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001587`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001587`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000157b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000157b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400014f7`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400014f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400014d3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400014d3`

## pseudocode

```c
__int64 __fastcall DfscNetUseIncrementOpenHandleCount(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  int LogonId; // ebx
  __int64 DriveLetterNetUseTable; // r15
  struct _ERESOURCE *p_WaitListHead; // rsi
  struct _ERESOURCE *v11; // rcx
  __int64 v12; // rax
  int v14; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  __int128 v16; // [rsp+40h] [rbp-19h] BYREF
  __int128 v17; // [rsp+50h] [rbp-9h] BYREF
  __int128 v18; // [rsp+60h] [rbp+7h]
  __int128 v19; // [rsp+70h] [rbp+17h]
  __int16 v20; // [rsp+80h] [rbp+27h] BYREF
  int v21; // [rsp+82h] [rbp+29h]

  v15 = 0;
  v14 = 0;
  v19 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  LogonId = DfscGetLogonId((PLUID)((char *)&v17 + 4));
  if ( LogonId >= 0 )
  {
    LogonId = DfscGetEffectiveRequestorSessionId(a4, (ULONG *)&v17);
    if ( LogonId >= 0 )
    {
      v20 = *(_WORD *)(*(_QWORD *)(a2 + 8) + 4LL);
      v21 = 58;
      DriveLetterNetUseTable = DfscGetDriveLetterNetUseTable(a1);
      DWORD2(v18) = 1;
      *((_QWORD *)&v16 + 1) = &v20;
      LODWORD(v16) = 393222;
      DWORD1(v16) = DWORD1(v19);
      KeEnterCriticalRegion();
      p_WaitListHead = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      v11 = (struct _ERESOURCE *)(a1 + 152);
      if ( !a1 )
        v11 = (struct _ERESOURCE *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      ExAcquireResourceExclusiveLite(v11, 1u);
      v12 = DfscNetUseTableLookup(DriveLetterNetUseTable, &v16, &v15, &v14);
      if ( v12 )
      {
        ++*(_DWORD *)(v12 + 144);
        *(_QWORD *)(a3 + 8) = v12;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
        {
          WPP_SF_qZq(WPP_GLOBAL_Control->AttachedDevice, 24, v12 + 88, v12, v12 + 88, *(_QWORD *)(v12 + 112));
        }
      }
      else
      {
        LogonId = -1073741772;
      }
      if ( a1 )
        p_WaitListHead = (struct _ERESOURCE *)(a1 + 152);
      ExReleaseResourceLite(p_WaitListHead);
      KeLeaveCriticalRegion();
    }
  }
  return (unsigned int)LogonId;
}

```

## disassembly

```asm
0x14000141c  mov     [rsp-8+arg_8], rbx
0x140001421  push    rbp
0x140001422  push    rsi
0x140001423  push    rdi
0x140001424  push    r14
0x140001426  push    r15
0x140001428  lea     rbp, [rsp-37h]
0x14000142d  sub     rsp, 90h
0x140001434  mov     rax, cs:__security_cookie
0x14000143b  xor     rax, rsp
0x14000143e  mov     [rbp+57h+var_28], rax
0x140001442  xorps   xmm0, xmm0
0x140001445  mov     [rbp+57h+var_78], 0
0x14000144d  mov     rdi, rcx
0x140001450  mov     [rbp+57h+var_80], 0
0x140001457  lea     rcx, [rbp+57h+AuthenticationId]; AuthenticationId
0x14000145b  mov     rsi, r9
0x14000145e  movups  [rbp+57h+var_40], xmm0
0x140001462  mov     r14, r8
0x140001465  mov     r15, rdx
0x140001468  movups  [rbp+57h+var_70], xmm0
0x14000146c  movups  xmmword ptr [rbp-9], xmm0
0x140001470  movups  [rbp+57h+var_50], xmm0
0x140001474  call    DfscGetLogonId
0x140001479  mov     ebx, eax
0x14000147b  test    eax, eax
0x14000147d  js      loc_140001593
0x140001483  lea     rdx, [rbp+57h+var_60]
0x140001487  mov     rcx, rsi
0x14000148a  call    DfscGetEffectiveRequestorSessionId
0x14000148f  mov     ebx, eax
0x140001491  test    eax, eax
0x140001493  js      loc_140001593
0x140001499  mov     rax, [r15+8]
0x14000149d  movzx   ecx, word ptr [rax+4]
0x1400014a1  mov     [rbp+57h+var_30], cx
0x1400014a5  mov     rcx, rdi
0x1400014a8  mov     [rbp+57h+var_2E], 3Ah ; ':'
0x1400014af  call    DfscGetDriveLetterNetUseTable
0x1400014b4  mov     ecx, dword ptr [rbp+57h+var_40+4]
0x1400014b7  mov     r15, rax
0x1400014ba  lea     rax, [rbp+57h+var_30]
0x1400014be  mov     dword ptr [rbp+57h+var_50+8], 1
0x1400014c5  mov     qword ptr [rbp+57h+var_70+8], rax
0x1400014c9  mov     dword ptr [rbp+57h+var_70], 60006h
0x1400014d0  mov     dword ptr [rbp+57h+var_70+4], ecx
0x1400014d3  call    cs:__imp_KeEnterCriticalRegion
0x1400014da  nop     dword ptr [rax+rax+00h]
0x1400014df  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400014e6  lea     rcx, [rdi+98h]
0x1400014ed  test    rdi, rdi
0x1400014f0  jnz     short loc_1400014F5
0x1400014f2  mov     rcx, rsi; Resource
0x1400014f5  mov     dl, 1; Wait
0x1400014f7  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400014fe  nop     dword ptr [rax+rax+00h]
0x140001503  lea     r9, [rbp+57h+var_80]
0x140001507  mov     rcx, r15
0x14000150a  lea     r8, [rbp+57h+var_78]
0x14000150e  lea     rdx, [rbp+57h+var_70]
0x140001512  call    DfscNetUseTableLookup
0x140001517  mov     r9, rax
0x14000151a  test    rax, rax
0x14000151d  jz      short loc_140001567
0x14000151f  inc     dword ptr [rax+90h]
0x140001525  mov     [r14+8], rax
0x140001529  mov     rcx, cs:WPP_GLOBAL_Control
0x140001530  lea     rax, WPP_GLOBAL_Control
0x140001537  cmp     rcx, rax
0x14000153a  jz      short loc_14000156C
0x14000153c  test    dword ptr [rcx+2Ch], 400000h
0x140001543  jz      short loc_14000156C
0x140001545  mov     rax, [r9+70h]
0x140001549  lea     r8, [r9+58h]
0x14000154d  mov     rcx, [rcx+18h]
0x140001551  mov     edx, 18h
0x140001556  mov     [rsp+0B0h+var_88], rax
0x14000155b  mov     [rsp+0B0h+var_90], r8
0x140001560  call    WPP_SF_qZq
0x140001565  jmp     short loc_14000156C
0x140001567  mov     ebx, 0C0000034h
0x14000156c  test    rdi, rdi
0x14000156f  jz      short loc_140001578
0x140001571  lea     rsi, [rdi+98h]
0x140001578  mov     rcx, rsi; Resource
0x14000157b  call    cs:__imp_ExReleaseResourceLite
0x140001582  nop     dword ptr [rax+rax+00h]
0x140001587  call    cs:__imp_KeLeaveCriticalRegion
0x14000158e  nop     dword ptr [rax+rax+00h]
0x140001593  mov     eax, ebx
0x140001595  mov     rcx, [rbp+57h+var_28]
0x140001599  xor     rcx, rsp; StackCookie
0x14000159c  call    __security_check_cookie
0x1400015a1  mov     rbx, [rsp+0B0h+arg_8]
0x1400015a9  add     rsp, 90h
0x1400015b0  pop     r15
0x1400015b2  pop     r14
0x1400015b4  pop     rdi
0x1400015b5  pop     rsi
0x1400015b6  pop     rbp
0x1400015b7  retn
```
