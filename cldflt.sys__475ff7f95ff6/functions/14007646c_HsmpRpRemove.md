# HsmpRpRemove

- ea: `0x14007646c`
- end: `0x140076668`
- name: `HsmpRpRemove`
- size: `508`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, PFILE_OBJECT FileObject)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x140034010`
- `0x140035f60`
- `0x140048a00`
- `0x14004cb90`
- `0x140051da0`
- `0x1400760e0`

## callees

- `0x140003c50`
- `0x140009300`
- `0x140034dac`
- `0x1400350c0`
- `0x140059738`
- `0x140067c70`
- `0x14007646c`
- `0x140076670`
- `0x1400766ac`

## import_xrefs

- `FLTMGR!FltUntagFile` at `0x1400765c0`
- `FLTMGR!FltUntagFile` at `0x1400765c0`
- `FLTMGR!FltDeleteContext` at `0x140076638`
- `FLTMGR!FltDeleteContext` at `0x140076638`
- `FLTMGR!FltReleasePushLockEx` at `0x14007664e`
- `FLTMGR!FltReleasePushLockEx` at `0x14007664e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007648e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400764b7`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007648e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400764b7`

## pseudocode

```c
__int64 __fastcall HsmpRpRemove(_QWORD *Context, PFILE_OBJECT FileObject, char a3)
{
  _QWORD *v3; // rsi
  __int64 v7; // rdi
  __int64 v8; // rcx
  NTSTATUS v9; // edi
  __int64 v10; // r8
  char v11; // r14

  v3 = (_QWORD *)Context[2];
  v7 = v3[2];
  FltAcquirePushLockExclusiveEx(v3 + 3, 0);
  if ( (*((_DWORD *)Context + 7) & 2) == 0 )
  {
    v8 = Context[20];
    if ( v8 )
      FltAcquirePushLockExclusiveEx(v8 + 40, 0);
    if ( !a3 && (*((_DWORD *)Context + 7) & 0x100) == 0 )
    {
      v9 = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
          Context,
          v3[4],
          -1073688821);
      }
      HsmpReleaseBitmapLock(Context);
      goto LABEL_22;
    }
    HsmpDeleteExternalBitmapsNoLock(Context);
    HsmpReleaseBitmapLock(Context);
    v10 = *((_DWORD *)Context + 7) >> 5;
    LOBYTE(v10) = (*((_DWORD *)Context + 7) & 0x20) != 0;
    HsmpToggleFileSparseAttribute(v7, FileObject, v10);
  }
  v11 = 0;
  HsmpDeletePropertyStream(v7, v3);
  HsmpToggleFileAttributesNotify(v7, (_DWORD)FileObject, 8, 0, 4198400);
  if ( !FileObject->WriteAccess )
  {
    FileObject->WriteAccess = 1;
    v11 = 1;
  }
  v9 = FltUntagFile(
         *(PFLT_INSTANCE *)(v7 + 32),
         FileObject,
         dword_140029670
       | *((_DWORD *)Context + 7) & 0x1000
       | (2 * (*((_DWORD *)Context + 7) & 0x6000 | ((*((_DWORD *)Context + 7) & 0x40) << 6))),
         0);
  HsmDbgBreakOnStatus(v9);
  if ( v11 )
    FileObject->WriteAccess = 0;
  if ( v9 >= 0 )
  {
    *((_DWORD *)Context + 7) &= ~1u;
    HsmpCldNullifyStreamContext(Context);
    FltDeleteContext(v3);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      31,
      WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
      Context,
      v3[4],
      v9);
  }
LABEL_22:
  FltReleasePushLockEx(Context[2] + 24LL, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14007646c  push    rbx
0x14007646e  push    rbp
0x14007646f  push    rsi
0x140076470  push    rdi
0x140076471  push    r14
0x140076473  sub     rsp, 30h
0x140076477  mov     rsi, [rcx+10h]
0x14007647b  mov     rbp, rdx
0x14007647e  mov     rbx, rcx
0x140076481  xor     edx, edx
0x140076483  mov     r14b, r8b
0x140076486  mov     rdi, [rsi+10h]
0x14007648a  lea     rcx, [rsi+18h]
0x14007648e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140076495  nop     dword ptr [rax+rax+00h]
0x14007649a  mov     eax, [rbx+1Ch]
0x14007649d  test    al, 2
0x14007649f  jnz     loc_140076556
0x1400764a5  mov     rcx, [rbx+0A0h]
0x1400764ac  test    rcx, rcx
0x1400764af  jz      short loc_1400764C3
0x1400764b1  add     rcx, 28h ; '('
0x1400764b5  xor     edx, edx
0x1400764b7  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400764be  nop     dword ptr [rax+rax+00h]
0x1400764c3  test    r14b, r14b
0x1400764c6  jnz     short loc_14007652F
0x1400764c8  test    dword ptr [rbx+1Ch], 100h
0x1400764cf  jnz     short loc_14007652F
0x1400764d1  mov     edi, 0C000CF0Bh
0x1400764d6  mov     ecx, edi
0x1400764d8  call    HsmDbgBreakOnStatus
0x1400764dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400764e4  lea     rax, WPP_GLOBAL_Control
0x1400764eb  cmp     rcx, rax
0x1400764ee  jz      short loc_140076522
0x1400764f0  mov     eax, [rcx+2Ch]
0x1400764f3  test    al, 1
0x1400764f5  jz      short loc_140076522
0x1400764f7  cmp     byte ptr [rcx+29h], 2
0x1400764fb  jb      short loc_140076522
0x1400764fd  mov     rax, [rsi+20h]
0x140076501  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x140076508  mov     rcx, [rcx+18h]
0x14007650c  mov     edx, 1Dh
0x140076511  mov     [rsp+58h+var_30], edi
0x140076515  mov     r9, rbx
0x140076518  mov     [rsp+58h+var_38], rax
0x14007651d  call    WPP_SF_qqd
0x140076522  mov     rcx, rbx
0x140076525  call    HsmpReleaseBitmapLock
0x14007652a  jmp     loc_140076644
0x14007652f  mov     rcx, rbx
0x140076532  call    HsmpDeleteExternalBitmapsNoLock
0x140076537  mov     rcx, rbx
0x14007653a  call    HsmpReleaseBitmapLock
0x14007653f  mov     r8d, [rbx+1Ch]
0x140076543  mov     rdx, rbp
0x140076546  shr     r8d, 5
0x14007654a  mov     rcx, rdi
0x14007654d  and     r8b, 1
0x140076551  call    HsmpToggleFileSparseAttribute
0x140076556  mov     rdx, rsi
0x140076559  mov     rcx, rdi
0x14007655c  xor     r14b, r14b
0x14007655f  call    HsmpDeletePropertyStream
0x140076564  xor     r9d, r9d
0x140076567  mov     dword ptr [rsp+58h+var_38], 401000h
0x14007656f  mov     rdx, rbp
0x140076572  mov     rcx, rdi
0x140076575  lea     r8d, [r9+8]
0x140076579  call    HsmpToggleFileAttributesNotify
0x14007657e  cmp     [rbp+4Bh], r14b
0x140076582  jnz     short loc_14007658B
0x140076584  mov     byte ptr [rbp+4Bh], 1
0x140076588  mov     r14b, 1
0x14007658b  mov     edx, [rbx+1Ch]
0x14007658e  xor     r9d, r9d; Guid
0x140076591  mov     rcx, [rdi+20h]; InitiatingInstance
0x140076595  mov     r8d, edx
0x140076598  and     r8d, 40h
0x14007659c  mov     eax, edx
0x14007659e  shl     r8d, 6
0x1400765a2  and     edx, 1000h
0x1400765a8  and     eax, 6000h
0x1400765ad  or      r8d, eax
0x1400765b0  add     r8d, r8d
0x1400765b3  or      r8d, edx
0x1400765b6  mov     rdx, rbp; FileObject
0x1400765b9  or      r8d, cs:dword_140029670; FileTag
0x1400765c0  call    cs:__imp_FltUntagFile
0x1400765c7  nop     dword ptr [rax+rax+00h]
0x1400765cc  mov     ecx, eax
0x1400765ce  mov     edi, eax
0x1400765d0  call    HsmDbgBreakOnStatus
0x1400765d5  test    r14b, r14b
0x1400765d8  jz      short loc_1400765DE
0x1400765da  mov     byte ptr [rbp+4Bh], 0
0x1400765de  test    edi, edi
0x1400765e0  jns     short loc_140076629
0x1400765e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400765e9  lea     rax, WPP_GLOBAL_Control
0x1400765f0  cmp     rcx, rax
0x1400765f3  jz      short loc_140076644
0x1400765f5  mov     eax, [rcx+2Ch]
0x1400765f8  test    al, 1
0x1400765fa  jz      short loc_140076644
0x1400765fc  cmp     byte ptr [rcx+29h], 2
0x140076600  jb      short loc_140076644
0x140076602  mov     rax, [rsi+20h]
0x140076606  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x14007660d  mov     rcx, [rcx+18h]
0x140076611  mov     edx, 1Fh
0x140076616  mov     [rsp+58h+var_30], edi
0x14007661a  mov     r9, rbx
0x14007661d  mov     [rsp+58h+var_38], rax
0x140076622  call    WPP_SF_qqd
0x140076627  jmp     short loc_140076644
0x140076629  and     dword ptr [rbx+1Ch], 0FFFFFFFEh
0x14007662d  mov     rcx, rbx; Context
0x140076630  call    HsmpCldNullifyStreamContext
0x140076635  mov     rcx, rsi; Context
0x140076638  call    cs:__imp_FltDeleteContext
0x14007663f  nop     dword ptr [rax+rax+00h]
0x140076644  mov     rcx, [rbx+10h]
0x140076648  xor     edx, edx
0x14007664a  add     rcx, 18h
0x14007664e  call    cs:__imp_FltReleasePushLockEx
0x140076655  nop     dword ptr [rax+rax+00h]
0x14007665a  mov     eax, edi
0x14007665c  add     rsp, 30h
0x140076660  pop     r14
0x140076662  pop     rdi
0x140076663  pop     rsi
0x140076664  pop     rbp
0x140076665  pop     rbx
0x140076666  retn
```
