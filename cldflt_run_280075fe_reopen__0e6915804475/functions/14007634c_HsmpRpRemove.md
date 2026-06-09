# HsmpRpRemove

- ea: `0x14007634c`
- end: `0x140076548`
- name: `HsmpRpRemove`
- size: `508`
- prototype: `__int64 __fastcall(PFLT_CONTEXT Context, PFILE_OBJECT FileObject)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x140034010`
- `0x140035f60`
- `0x140048910`
- `0x14004caa0`
- `0x140051c80`
- `0x140075fc0`

## callees

- `0x140003c50`
- `0x140009300`
- `0x140034dac`
- `0x1400350c0`
- `0x140059618`
- `0x140067b50`
- `0x14007634c`
- `0x140076550`
- `0x14007658c`

## import_xrefs

- `FLTMGR!FltUntagFile` at `0x1400764a0`
- `FLTMGR!FltUntagFile` at `0x1400764a0`
- `FLTMGR!FltDeleteContext` at `0x140076518`
- `FLTMGR!FltDeleteContext` at `0x140076518`
- `FLTMGR!FltReleasePushLockEx` at `0x14007652e`
- `FLTMGR!FltReleasePushLockEx` at `0x14007652e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007636e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140076397`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007636e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140076397`

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
      HsmDbgBreakOnStatus(3221278475LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          29,
          WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids,
          Context,
          v3[4]);
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
  HsmDbgBreakOnStatus((unsigned int)v9);
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
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids, Context, v3[4]);
  }
LABEL_22:
  FltReleasePushLockEx(Context[2] + 24LL, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14007634c  push    rbx
0x14007634e  push    rbp
0x14007634f  push    rsi
0x140076350  push    rdi
0x140076351  push    r14
0x140076353  sub     rsp, 30h
0x140076357  mov     rsi, [rcx+10h]
0x14007635b  mov     rbp, rdx
0x14007635e  mov     rbx, rcx
0x140076361  xor     edx, edx
0x140076363  mov     r14b, r8b
0x140076366  mov     rdi, [rsi+10h]
0x14007636a  lea     rcx, [rsi+18h]
0x14007636e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140076375  nop     dword ptr [rax+rax+00h]
0x14007637a  mov     eax, [rbx+1Ch]
0x14007637d  test    al, 2
0x14007637f  jnz     loc_140076436
0x140076385  mov     rcx, [rbx+0A0h]
0x14007638c  test    rcx, rcx
0x14007638f  jz      short loc_1400763A3
0x140076391  add     rcx, 28h ; '('
0x140076395  xor     edx, edx
0x140076397  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14007639e  nop     dword ptr [rax+rax+00h]
0x1400763a3  test    r14b, r14b
0x1400763a6  jnz     short loc_14007640F
0x1400763a8  test    dword ptr [rbx+1Ch], 100h
0x1400763af  jnz     short loc_14007640F
0x1400763b1  mov     edi, 0C000CF0Bh
0x1400763b6  mov     ecx, edi
0x1400763b8  call    HsmDbgBreakOnStatus
0x1400763bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400763c4  lea     rax, WPP_GLOBAL_Control
0x1400763cb  cmp     rcx, rax
0x1400763ce  jz      short loc_140076402
0x1400763d0  mov     eax, [rcx+2Ch]
0x1400763d3  test    al, 1
0x1400763d5  jz      short loc_140076402
0x1400763d7  cmp     byte ptr [rcx+29h], 2
0x1400763db  jb      short loc_140076402
0x1400763dd  mov     rax, [rsi+20h]
0x1400763e1  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x1400763e8  mov     rcx, [rcx+18h]
0x1400763ec  mov     edx, 1Dh
0x1400763f1  mov     [rsp+58h+var_30], edi
0x1400763f5  mov     r9, rbx
0x1400763f8  mov     [rsp+58h+var_38], rax
0x1400763fd  call    WPP_SF_qqd
0x140076402  mov     rcx, rbx
0x140076405  call    HsmpReleaseBitmapLock
0x14007640a  jmp     loc_140076524
0x14007640f  mov     rcx, rbx
0x140076412  call    HsmpDeleteExternalBitmapsNoLock
0x140076417  mov     rcx, rbx
0x14007641a  call    HsmpReleaseBitmapLock
0x14007641f  mov     r8d, [rbx+1Ch]
0x140076423  mov     rdx, rbp
0x140076426  shr     r8d, 5
0x14007642a  mov     rcx, rdi
0x14007642d  and     r8b, 1
0x140076431  call    HsmpToggleFileSparseAttribute
0x140076436  mov     rdx, rsi
0x140076439  mov     rcx, rdi
0x14007643c  xor     r14b, r14b
0x14007643f  call    HsmpDeletePropertyStream
0x140076444  xor     r9d, r9d
0x140076447  mov     dword ptr [rsp+58h+var_38], 401000h
0x14007644f  mov     rdx, rbp
0x140076452  mov     rcx, rdi
0x140076455  lea     r8d, [r9+8]
0x140076459  call    HsmpToggleFileAttributesNotify
0x14007645e  cmp     [rbp+4Bh], r14b
0x140076462  jnz     short loc_14007646B
0x140076464  mov     byte ptr [rbp+4Bh], 1
0x140076468  mov     r14b, 1
0x14007646b  mov     edx, [rbx+1Ch]
0x14007646e  xor     r9d, r9d; Guid
0x140076471  mov     rcx, [rdi+20h]; InitiatingInstance
0x140076475  mov     r8d, edx
0x140076478  and     r8d, 40h
0x14007647c  mov     eax, edx
0x14007647e  shl     r8d, 6
0x140076482  and     edx, 1000h
0x140076488  and     eax, 6000h
0x14007648d  or      r8d, eax
0x140076490  add     r8d, r8d
0x140076493  or      r8d, edx
0x140076496  mov     rdx, rbp; FileObject
0x140076499  or      r8d, cs:dword_140029670; FileTag
0x1400764a0  call    cs:__imp_FltUntagFile
0x1400764a7  nop     dword ptr [rax+rax+00h]
0x1400764ac  mov     ecx, eax
0x1400764ae  mov     edi, eax
0x1400764b0  call    HsmDbgBreakOnStatus
0x1400764b5  test    r14b, r14b
0x1400764b8  jz      short loc_1400764BE
0x1400764ba  mov     byte ptr [rbp+4Bh], 0
0x1400764be  test    edi, edi
0x1400764c0  jns     short loc_140076509
0x1400764c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400764c9  lea     rax, WPP_GLOBAL_Control
0x1400764d0  cmp     rcx, rax
0x1400764d3  jz      short loc_140076524
0x1400764d5  mov     eax, [rcx+2Ch]
0x1400764d8  test    al, 1
0x1400764da  jz      short loc_140076524
0x1400764dc  cmp     byte ptr [rcx+29h], 2
0x1400764e0  jb      short loc_140076524
0x1400764e2  mov     rax, [rsi+20h]
0x1400764e6  lea     r8, WPP_1b967c8d739c32210f02f2d42c5aa5c3_Traceguids
0x1400764ed  mov     rcx, [rcx+18h]
0x1400764f1  mov     edx, 1Fh
0x1400764f6  mov     [rsp+58h+var_30], edi
0x1400764fa  mov     r9, rbx
0x1400764fd  mov     [rsp+58h+var_38], rax
0x140076502  call    WPP_SF_qqd
0x140076507  jmp     short loc_140076524
0x140076509  and     dword ptr [rbx+1Ch], 0FFFFFFFEh
0x14007650d  mov     rcx, rbx; Context
0x140076510  call    HsmpCldNullifyStreamContext
0x140076515  mov     rcx, rsi; Context
0x140076518  call    cs:__imp_FltDeleteContext
0x14007651f  nop     dword ptr [rax+rax+00h]
0x140076524  mov     rcx, [rbx+10h]
0x140076528  xor     edx, edx
0x14007652a  add     rcx, 18h
0x14007652e  call    cs:__imp_FltReleasePushLockEx
0x140076535  nop     dword ptr [rax+rax+00h]
0x14007653a  mov     eax, edi
0x14007653c  add     rsp, 30h
0x140076540  pop     r14
0x140076542  pop     rdi
0x140076543  pop     rsi
0x140076544  pop     rbp
0x140076545  pop     rbx
0x140076546  retn
```
