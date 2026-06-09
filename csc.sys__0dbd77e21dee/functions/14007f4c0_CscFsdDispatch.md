# CscFsdDispatch

- ea: `0x14007f4c0`
- end: `0x14007f864`
- name: `CscFsdDispatch`
- size: `932`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400017c0`
- `0x14000a634`
- `0x14001328c`
- `0x140015fd4`
- `0x1400169d4`
- `0x140018930`
- `0x14001a5b4`
- `0x14001a624`
- `0x14001b710`
- `0x14001b770`
- `0x14007f4c0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f67d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f7de`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f67d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14007f7de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007f7f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007f839`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007f7f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007f839`
- `ntoskrnl!IofCompleteRequest` at `0x14007f605`
- `ntoskrnl!IofCompleteRequest` at `0x14007f605`
- `rdbss!RxFsdDispatch` at `0x14007f53e`
- `rdbss!RxFsdDispatch` at `0x14007f53e`

## pseudocode

```c
__int64 __fastcall CscFsdDispatch(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  PFILE_OBJECT FileObject; // rbp
  UCHAR MajorFunction; // al
  NTSTATUS v7; // eax
  unsigned int v8; // ebx
  _DWORD *FsContext2; // rax
  char *FsContext; // rbx
  __int64 v12; // r9
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rcx
  _OWORD v16[3]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v17; // [rsp+80h] [rbp+8h] BYREF
  __int64 v18; // [rsp+88h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v17 = 0;
  FileObject = CurrentStackLocation->FileObject;
  v18 = 0;
  v16[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, a1, a2);
  if ( a1 != CscDeviceObject )
  {
    v8 = -1073741808;
    goto LABEL_20;
  }
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( CurrentStackLocation->MajorFunction == 23 )
  {
    v7 = CscProcessSystemControlIrp(CscDeviceObject, a2);
  }
  else
  {
    if ( MajorFunction == 16 )
    {
      KeEnterCriticalRegion();
      LOBYTE(v15) = 1;
      v8 = CscStoreFlushState(v15);
      KeLeaveCriticalRegion();
      goto LABEL_20;
    }
    if ( MajorFunction )
    {
      if ( MajorFunction == 14
        && ((CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 1311119) & 0xFFFFFFFB) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids);
        }
LABEL_19:
        v8 = -1073741634;
LABEL_20:
        a2->IoStatus.Status = v8;
        a2->IoStatus.Information = 0;
        IofCompleteRequest(a2, 0);
        goto LABEL_9;
      }
    }
    else
    {
      FsContext2 = FileObject->FsContext2;
      if ( !FsContext2 || *(_WORD *)FsContext2 != 0xEB0F || FsContext2[1] != -977269668 )
      {
        FsContext = (char *)FileObject->FsContext;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids);
        }
        if ( FileObject->FsContext && *((_WORD *)FsContext + 20) > *((_WORD *)FsContext + 28) )
        {
          KeEnterCriticalRegion();
          v16[0] = *(_OWORD *)(FsContext + 40);
          LOWORD(v16[0]) = *((_WORD *)FsContext + 20) - *((_WORD *)FsContext + 28);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, v16);
          }
          if ( (int)CscStoreFindEntry(&v17, 0, v16, v12) < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids);
            }
          }
          else
          {
            v13 = v17;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_qqq(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids,
                v17,
                0,
                0);
            }
            v18 = 0x400000000000LL;
            v14 = CscStoreSetInformationEntry(v13, (__int64)&v18, 0, 0, 0, 0, 0);
            if ( v14 < 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids,
                (unsigned int)v14);
            }
            CscStoreDereferenceEntry(&v17);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_qqq(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids,
                v17,
                0,
                0);
            }
          }
          KeLeaveCriticalRegion();
        }
        goto LABEL_19;
      }
    }
    v7 = RxFsdDispatch((PRDBSS_DEVICE_OBJECT)CscDeviceObject, a2);
  }
  v8 = v7;
LABEL_9:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x14007f4c0  mov     rax, rsp
0x14007f4c3  mov     [rax+18h], rbx
0x14007f4c7  push    rbp
0x14007f4c8  push    rsi
0x14007f4c9  push    rdi
0x14007f4ca  push    r14
0x14007f4cc  push    r15
0x14007f4ce  sub     rsp, 50h
0x14007f4d2  mov     rbx, [rdx+0B8h]
0x14007f4d9  xor     r15d, r15d
0x14007f4dc  xorps   xmm0, xmm0
0x14007f4df  mov     [rax+8], r15
0x14007f4e3  mov     rdi, rdx
0x14007f4e6  mov     rsi, rcx
0x14007f4e9  mov     rbp, [rbx+30h]
0x14007f4ed  mov     [rax+10h], r15
0x14007f4f1  movups  xmmword ptr [rax-38h], xmm0
0x14007f4f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f4fc  lea     r14, WPP_GLOBAL_Control
0x14007f503  cmp     rcx, r14
0x14007f506  jnz     short loc_14007F56F
0x14007f508  mov     rcx, cs:CscDeviceObject; RxDeviceObject
0x14007f50f  cmp     rsi, rcx
0x14007f512  jnz     loc_14007F616
0x14007f518  movzx   eax, byte ptr [rbx]
0x14007f51b  cmp     al, 17h
0x14007f51d  jz      loc_14007F804
0x14007f523  cmp     al, 10h
0x14007f525  jz      loc_14007F7DE
0x14007f52b  test    al, al
0x14007f52d  jz      loc_14007F61D
0x14007f533  cmp     al, 0Eh
0x14007f535  jz      loc_14007F5CA
0x14007f53b  mov     rdx, rdi; Irp
0x14007f53e  call    cs:__imp_RxFsdDispatch
0x14007f545  nop     dword ptr [rax+rax+00h]
0x14007f54a  mov     ebx, eax
0x14007f54c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f553  cmp     rcx, r14
0x14007f556  jnz     short loc_14007F5A9
0x14007f558  mov     eax, ebx
0x14007f55a  mov     rbx, [rsp+78h+arg_10]
0x14007f562  add     rsp, 50h
0x14007f566  pop     r15
0x14007f568  pop     r14
0x14007f56a  pop     rdi
0x14007f56b  pop     rsi
0x14007f56c  pop     rbp
0x14007f56d  retn
0x14007f56f  mov     eax, [rcx+2Ch]
0x14007f572  test    al, 20h
0x14007f574  jz      short loc_14007F508
0x14007f576  movzx   r8d, byte ptr [rbx]
0x14007f57a  mov     edx, 11h
0x14007f57f  movzx   eax, byte ptr [rbx+1]
0x14007f583  mov     r9, rsi
0x14007f586  mov     rcx, [rcx+18h]
0x14007f58a  mov     dword ptr [rsp+78h+var_48], eax
0x14007f58e  mov     dword ptr [rsp+78h+var_50], r8d
0x14007f593  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f59a  mov     [rsp+78h+var_58], rdi
0x14007f59f  call    WPP_SF_qqDD
0x14007f5a4  jmp     loc_14007F508
0x14007f5a9  mov     eax, [rcx+2Ch]
0x14007f5ac  test    al, 20h
0x14007f5ae  jz      short loc_14007F558
0x14007f5b0  mov     rcx, [rcx+18h]
0x14007f5b4  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f5bb  mov     edx, 19h
0x14007f5c0  mov     r9d, ebx
0x14007f5c3  call    WPP_SF_d
0x14007f5c8  jmp     short loc_14007F558
0x14007f5ca  mov     eax, [rbx+18h]
0x14007f5cd  sub     eax, 14018Fh
0x14007f5d2  test    eax, 0FFFFFFFBh
0x14007f5d7  jnz     loc_14007F53B
0x14007f5dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f5e4  cmp     rcx, r14
0x14007f5e7  jz      short loc_14007F5F4
0x14007f5e9  mov     eax, [rcx+2Ch]
0x14007f5ec  test    al, 20h
0x14007f5ee  jnz     loc_14007F84A
0x14007f5f4  mov     ebx, 0C00000BEh
0x14007f5f9  xor     edx, edx; PriorityBoost
0x14007f5fb  mov     [rdi+30h], ebx
0x14007f5fe  mov     rcx, rdi; Irp
0x14007f601  mov     [rdi+38h], r15
0x14007f605  call    cs:__imp_IofCompleteRequest
0x14007f60c  nop     dword ptr [rax+rax+00h]
0x14007f611  jmp     loc_14007F54C
0x14007f616  mov     ebx, 0C0000010h
0x14007f61b  jmp     short loc_14007F5F9
0x14007f61d  mov     rax, [rbp+20h]
0x14007f621  test    rax, rax
0x14007f624  jz      short loc_14007F63D
0x14007f626  mov     edx, 0EB0Fh
0x14007f62b  cmp     dx, [rax]
0x14007f62e  jnz     short loc_14007F63D
0x14007f630  cmp     dword ptr [rax+4], 0C5C00C5Ch
0x14007f637  jz      loc_14007F53B
0x14007f63d  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f644  mov     rbx, [rbp+18h]
0x14007f648  cmp     rcx, r14
0x14007f64b  jz      short loc_14007F669
0x14007f64d  mov     eax, [rcx+2Ch]
0x14007f650  test    al, 20h
0x14007f652  jz      short loc_14007F669
0x14007f654  mov     rcx, [rcx+18h]
0x14007f658  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f65f  mov     edx, 12h
0x14007f664  call    WPP_SF_
0x14007f669  cmp     [rbp+18h], r15
0x14007f66d  jz      short loc_14007F5F4
0x14007f66f  movzx   eax, word ptr [rbx+38h]
0x14007f673  cmp     [rbx+28h], ax
0x14007f677  jbe     loc_14007F5F4
0x14007f67d  call    cs:__imp_KeEnterCriticalRegion
0x14007f684  nop     dword ptr [rax+rax+00h]
0x14007f689  movups  xmm0, xmmword ptr [rbx+28h]
0x14007f68d  movups  [rsp+78h+var_38], xmm0
0x14007f692  movzx   ecx, word ptr [rbx+28h]
0x14007f696  sub     cx, [rbx+38h]
0x14007f69a  mov     word ptr [rsp+78h+var_38], cx
0x14007f69f  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f6a6  cmp     rcx, r14
0x14007f6a9  jz      short loc_14007F6CC
0x14007f6ab  mov     eax, [rcx+2Ch]
0x14007f6ae  test    al, 20h
0x14007f6b0  jz      short loc_14007F6CC
0x14007f6b2  mov     rcx, [rcx+18h]
0x14007f6b6  lea     r9, [rsp+78h+var_38]
0x14007f6bb  mov     edx, 13h
0x14007f6c0  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f6c7  call    WPP_SF_Z
0x14007f6cc  lea     r8, [rsp+78h+var_38]
0x14007f6d1  xor     edx, edx
0x14007f6d3  lea     rcx, [rsp+78h+arg_0]
0x14007f6db  call    CscStoreFindEntry
0x14007f6e0  test    eax, eax
0x14007f6e2  js      loc_14007F811
0x14007f6e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f6ef  mov     rbx, [rsp+78h+arg_0]
0x14007f6f7  cmp     rcx, r14
0x14007f6fa  jz      short loc_14007F725
0x14007f6fc  mov     eax, [rcx+2Ch]
0x14007f6ff  test    al, 40h
0x14007f701  jz      short loc_14007F725
0x14007f703  mov     rcx, [rcx+18h]
0x14007f707  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f70e  mov     edx, 14h
0x14007f713  mov     [rsp+78h+var_50], r15
0x14007f718  mov     r9, rbx
0x14007f71b  mov     [rsp+78h+var_58], r15
0x14007f720  call    WPP_SF_qqq
0x14007f725  mov     [rsp+78h+var_48], r15
0x14007f72a  lea     rdx, [rsp+78h+arg_8]
0x14007f732  mov     [rsp+78h+var_50], r15
0x14007f737  xor     r9d, r9d
0x14007f73a  xor     r8d, r8d
0x14007f73d  mov     [rsp+78h+var_58], r15
0x14007f742  mov     rcx, rbx
0x14007f745  mov     [rsp+78h+arg_C], 4000h
0x14007f750  mov     [rsp+78h+arg_8], r15d
0x14007f758  call    CscStoreSetInformationEntry
0x14007f75d  test    eax, eax
0x14007f75f  jns     short loc_14007F78D
0x14007f761  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f768  cmp     rcx, r14
0x14007f76b  jz      short loc_14007F78D
0x14007f76d  mov     edx, [rcx+2Ch]
0x14007f770  test    dl, 40h
0x14007f773  jz      short loc_14007F78D
0x14007f775  mov     rcx, [rcx+18h]
0x14007f779  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f780  mov     edx, 15h
0x14007f785  mov     r9d, eax
0x14007f788  call    WPP_SF_d
0x14007f78d  lea     rcx, [rsp+78h+arg_0]
0x14007f795  call    CscStoreDereferenceEntry
0x14007f79a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f7a1  cmp     rcx, r14
0x14007f7a4  jz      loc_14007F839
0x14007f7aa  mov     eax, [rcx+2Ch]
0x14007f7ad  test    al, 40h
0x14007f7af  jz      loc_14007F839
0x14007f7b5  mov     r9, [rsp+78h+arg_0]
0x14007f7bd  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f7c4  mov     rcx, [rcx+18h]
0x14007f7c8  mov     edx, 16h
0x14007f7cd  mov     [rsp+78h+var_50], r15
0x14007f7d2  mov     [rsp+78h+var_58], r15
0x14007f7d7  call    WPP_SF_qqq
0x14007f7dc  jmp     short loc_14007F839
0x14007f7de  call    cs:__imp_KeEnterCriticalRegion
0x14007f7e5  nop     dword ptr [rax+rax+00h]
0x14007f7ea  mov     cl, 1
0x14007f7ec  call    CscStoreFlushState
0x14007f7f1  mov     ebx, eax
0x14007f7f3  call    cs:__imp_KeLeaveCriticalRegion
0x14007f7fa  nop     dword ptr [rax+rax+00h]
0x14007f7ff  jmp     loc_14007F5F9
0x14007f804  mov     rdx, rdi
0x14007f807  call    CscProcessSystemControlIrp
0x14007f80c  jmp     loc_14007F54A
0x14007f811  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f818  cmp     rcx, r14
0x14007f81b  jz      short loc_14007F839
0x14007f81d  mov     eax, [rcx+2Ch]
0x14007f820  test    al, 40h
0x14007f822  jz      short loc_14007F839
0x14007f824  mov     rcx, [rcx+18h]
0x14007f828  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f82f  mov     edx, 17h
0x14007f834  call    WPP_SF_
0x14007f839  call    cs:__imp_KeLeaveCriticalRegion
0x14007f840  nop     dword ptr [rax+rax+00h]
0x14007f845  jmp     loc_14007F5F4
0x14007f84a  mov     rcx, [rcx+18h]
0x14007f84e  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14007f855  mov     edx, 18h
0x14007f85a  call    WPP_SF_
0x14007f85f  jmp     loc_14007F5F4
```
