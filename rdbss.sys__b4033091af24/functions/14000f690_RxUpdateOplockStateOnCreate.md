# RxUpdateOplockStateOnCreate

- ea: `0x14000f690`
- end: `0x14000f878`
- name: `RxUpdateOplockStateOnCreate`
- size: `488`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140054ca0`

## callees

- `0x140008030`
- `0x140008190`
- `0x14000f690`
- `0x140017220`
- `0x140017370`
- `0x140017420`
- `0x14001d5e8`
- `0x140071700`
- `0x140072a80`

## import_xrefs

- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14000f775`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14000f775`

## pseudocode

```c
void __fastcall RxUpdateOplockStateOnCreate(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v5; // r14
  int v7; // ebx
  __int64 v8; // rcx
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  NTSTATUS v11; // r9d
  unsigned int v12; // r15d
  UCHAR Flags; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+28h] [rbp-50h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-38h] BYREF

  v5 = a3;
  v7 = *(_DWORD *)(a2 + 164);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LODWORD(v14) = *(_DWORD *)(a2 + 164);
    Flags = a3;
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, a2);
  }
  if ( (v7 & 2) != 0 && (a4 & 2) == 0 )
  {
    v10 = RxFlushFcbInSystemCache((PFCB)a2, 1u);
    v12 = v10;
    if ( v10 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids, a2, v10);
      }
      RxCcLogError((PDEVICE_OBJECT)a2, (PUNICODE_STRING)v12, a3, v11, Flags, v14);
    }
  }
  if ( (v7 & 1) != 0 && (a4 & 1) == 0 )
  {
    IoStatus = 0;
    LOBYTE(a3) = 1;
    RxAcquirePagingIoResource(0, a2, a3);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v8, CcPurgeRequest, 0, a2);
    CcCoherencyFlushAndPurgeCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a2 + 304) + 8LL), 0, 0xFFFFFFFF, &IoStatus, 0);
    if ( (BYTE4(WPP_MAIN_CB.Dpc.DpcListEntry.Next) & 8) != 0 )
      McTemplateK0p_EtwWriteTransfer(v9, CcPurgeCompletion, 0, a2);
    RxReleasePagingIoResource(0, a2);
  }
  if ( ((v7 & 0x10) != 0 || (v7 & 0x20) != 0) && (a4 & 0x10) == 0 && (a4 & 0x20) == 0 )
    RxPurgeConflictingSrvOpens(a2, 0, v5);
  *(_DWORD *)(a2 + 164) = a4;
  if ( v5 && (*(_DWORD *)(a2 + 156) & 0x10) == 0 && !a4 )
    *(_DWORD *)(v5 + 72) |= 0x40u;
}

```

## disassembly

```asm
0x14000f690  mov     [rsp+arg_0], rbx
0x14000f695  mov     [rsp+arg_18], r9d
0x14000f69a  mov     [rsp+arg_10], r8
0x14000f69f  mov     [rsp+arg_8], rdx
0x14000f6a4  push    rsi
0x14000f6a5  push    rdi
0x14000f6a6  push    r12
0x14000f6a8  push    r14
0x14000f6aa  push    r15
0x14000f6ac  sub     rsp, 50h
0x14000f6b0  mov     esi, r9d
0x14000f6b3  mov     r14, r8
0x14000f6b6  mov     rdi, rdx
0x14000f6b9  mov     ebx, [rdx+0A4h]
0x14000f6bf  lea     r12, WPP_GLOBAL_Control
0x14000f6c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6cd  cmp     rcx, r12
0x14000f6d0  jz      short loc_14000F6DD
0x14000f6d2  mov     eax, [rcx+2Ch]
0x14000f6d5  test    al, 40h
0x14000f6d7  jnz     loc_14000F810
0x14000f6dd  test    bl, 2
0x14000f6e0  jnz     loc_14000F7AB
0x14000f6e6  test    bl, 1
0x14000f6e9  jnz     short loc_14000F71F
0x14000f6eb  test    bl, 10h
0x14000f6ee  jnz     short loc_14000F6F9
0x14000f6f0  test    bl, 20h
0x14000f6f3  jz      loc_14000F844
0x14000f6f9  test    sil, 10h
0x14000f6fd  jnz     loc_14000F844
0x14000f703  test    sil, 20h
0x14000f707  jnz     loc_14000F844
0x14000f70d  mov     r8, r14
0x14000f710  xor     edx, edx
0x14000f712  mov     rcx, rdi
0x14000f715  call    RxPurgeConflictingSrvOpens
0x14000f71a  jmp     loc_14000F844
0x14000f71f  test    sil, 1
0x14000f723  jnz     short loc_14000F6EB
0x14000f725  xorps   xmm0, xmm0
0x14000f728  movups  xmmword ptr [rsp+78h+IoStatus], xmm0
0x14000f72d  mov     r8b, 1
0x14000f730  mov     rdx, rdi
0x14000f733  xor     ecx, ecx
0x14000f735  call    RxAcquirePagingIoResource
0x14000f73a  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14000f741  jz      short loc_14000F755
0x14000f743  mov     r9, rdi
0x14000f746  xor     r8d, r8d
0x14000f749  lea     rdx, CcPurgeRequest
0x14000f750  call    McTemplateK0p_EtwWriteTransfer
0x14000f755  mov     rcx, [rdi+130h]
0x14000f75c  add     rcx, 8; SectionObjectPointer
0x14000f760  mov     [rsp+78h+Flags], 0; Flags
0x14000f768  lea     r9, [rsp+78h+IoStatus]; IoStatus
0x14000f76d  xor     edx, edx; FileOffset
0x14000f76f  mov     r8d, 0FFFFFFFFh; Length
0x14000f775  call    cs:__imp_CcCoherencyFlushAndPurgeCache
0x14000f77c  nop     dword ptr [rax+rax+00h]
0x14000f781  test    byte ptr cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next+4, 8
0x14000f788  jz      short loc_14000F79C
0x14000f78a  mov     r9, rdi
0x14000f78d  xor     r8d, r8d
0x14000f790  lea     rdx, CcPurgeCompletion
0x14000f797  call    McTemplateK0p_EtwWriteTransfer
0x14000f79c  mov     rdx, rdi
0x14000f79f  xor     ecx, ecx
0x14000f7a1  call    RxReleasePagingIoResource
0x14000f7a6  jmp     loc_14000F6EB
0x14000f7ab  test    sil, 2
0x14000f7af  jnz     loc_14000F6E6
0x14000f7b5  mov     dl, 1; SynchronizeWithLazyWriter
0x14000f7b7  mov     rcx, rdi; Fcb
0x14000f7ba  call    RxFlushFcbInSystemCache
0x14000f7bf  mov     r15d, eax
0x14000f7c2  test    eax, eax
0x14000f7c4  jns     loc_14000F6E6
0x14000f7ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7d1  cmp     rcx, r12
0x14000f7d4  jz      short loc_14000F800
0x14000f7d6  mov     edx, [rcx+2Ch]
0x14000f7d9  test    dl, 1
0x14000f7dc  jz      short loc_14000F800
0x14000f7de  cmp     byte ptr [rcx+29h], 1
0x14000f7e2  jb      short loc_14000F800
0x14000f7e4  mov     edx, 32h ; '2'
0x14000f7e9  mov     [rsp+78h+Flags], eax; IrpMajorCode
0x14000f7ed  mov     r9, rdi
0x14000f7f0  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x14000f7f7  mov     rcx, [rcx+18h]
0x14000f7fb  call    WPP_SF_qD
0x14000f800  mov     edx, r15d; FileName
0x14000f803  mov     rcx, rdi; DeviceObject
0x14000f806  call    RxCcLogError
0x14000f80b  jmp     loc_14000F6E6
0x14000f810  cmp     byte ptr [rcx+29h], 2
0x14000f814  jb      loc_14000F6DD
0x14000f81a  mov     edx, 31h ; '1'
0x14000f81f  mov     [rsp+78h+var_48], esi
0x14000f823  mov     dword ptr [rsp+78h+var_50], ebx
0x14000f827  mov     qword ptr [rsp+78h+Flags], r14
0x14000f82c  mov     r9, rdi
0x14000f82f  lea     r8, WPP_2a2c931366f233ae252535abde3f9a0d_Traceguids
0x14000f836  mov     rcx, [rcx+18h]
0x14000f83a  call    WPP_SF_qqDD
0x14000f83f  jmp     loc_14000F6DD
0x14000f844  mov     [rdi+0A4h], esi
0x14000f84a  test    r14, r14
0x14000f84d  jz      short loc_14000F862
0x14000f84f  mov     eax, [rdi+9Ch]
0x14000f855  test    al, 10h
0x14000f857  jnz     short loc_14000F862
0x14000f859  test    esi, esi
0x14000f85b  jnz     short loc_14000F862
0x14000f85d  or      dword ptr [r14+48h], 40h
0x14000f862  mov     rbx, [rsp+78h+arg_0]
0x14000f86a  add     rsp, 50h
0x14000f86e  pop     r15
0x14000f870  pop     r14
0x14000f872  pop     r12
0x14000f874  pop     rdi
0x14000f875  pop     rsi
0x14000f876  retn
0x140026990  push    rbp
0x140026992  sub     rsp, 40h
0x140026996  mov     rbp, rdx
0x140026999  mov     edx, [rbp+98h]
0x14002699f  mov     rax, [rbp+88h]
0x1400269a6  mov     [rax+0A4h], edx
0x1400269ac  mov     rcx, [rbp+90h]
0x1400269b3  test    rcx, rcx
0x1400269b6  jz      short loc_1400269CA
0x1400269b8  mov     eax, [rax+9Ch]
0x1400269be  test    al, 10h
0x1400269c0  jnz     short loc_1400269CA
0x1400269c2  test    edx, edx
0x1400269c4  jnz     short loc_1400269CA
0x1400269c6  or      dword ptr [rcx+48h], 40h
0x1400269ca  add     rsp, 40h
0x1400269ce  pop     rbp
0x1400269cf  retn
```
