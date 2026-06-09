# HsmiFileCacheIrpQueryInformation

- ea: `0x14001c090`
- end: `0x14001c275`
- name: `HsmiFileCacheIrpQueryInformation`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x14000c12c`
- `0x14000d95c`
- `0x14001880c`
- `0x14001c090`
- `0x14001cb04`
- `0x14001d22c`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001c228`
- `ntoskrnl!IofCompleteRequest` at `0x14001c228`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpQueryInformation(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 v5; // r9
  PFILE_OBJECT FileObject; // r14
  ULONG Options; // esi
  ULONG Length; // ebp
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  struct _IRP *MasterIrp; // rdx
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-58h]
  __int64 v16; // [rsp+88h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = a1;
  v16 = 0;
  FileObject = CurrentStackLocation->FileObject;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqqlD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, FileObject, Options, Length);
  }
  v9 = HsmiFileCacheValidateFileObject(FileObject, 0, &v16, v5);
  HsmDbgBreakOnStatus(v9);
  if ( (v9 & 0x80000000) == 0 )
  {
    if ( Options == 5 )
    {
      if ( Length == 24 )
      {
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        v9 = 0;
        v13 = v16;
        *(_QWORD *)&MasterIrp->Type = *(_QWORD *)(v16 + 24);
        MasterIrp->MdlAddress = *(PMDL *)(v13 + 32);
        MasterIrp->Flags = 1;
        *((_WORD *)&MasterIrp->Flags + 2) = 0;
      }
      else
      {
        v9 = -1073741811;
        HsmDbgBreakOnStatus(3221225485LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDd(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids,
            24,
            Length,
            -1073741811);
        }
      }
    }
    else
    {
      v9 = -1073741808;
      HsmDbgBreakOnStatus(3221225488LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_ld(WPP_GLOBAL_Control->AttachedDevice, v10, v11, Options);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LODWORD(v15) = v9;
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, FileObject, v15);
  }
  a2->IoStatus.Status = v9;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x14001c090  mov     r11, rsp
0x14001c093  push    rbx
0x14001c094  push    rbp
0x14001c095  push    rsi
0x14001c096  push    rdi
0x14001c097  push    r13
0x14001c099  push    r14
0x14001c09b  sub     rsp, 48h
0x14001c09f  mov     rax, [rdx+0B8h]
0x14001c0a6  mov     rdi, rdx
0x14001c0a9  mov     r9, rcx
0x14001c0ac  mov     qword ptr [r11+10h], 0
0x14001c0b4  mov     r14, [rax+30h]
0x14001c0b8  mov     esi, [rax+10h]
0x14001c0bb  mov     ebp, [rax+8]
0x14001c0be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c0c5  lea     r13, WPP_GLOBAL_Control
0x14001c0cc  cmp     rcx, r13
0x14001c0cf  jz      short loc_14001C0F7
0x14001c0d1  mov     eax, [rcx+2Ch]
0x14001c0d4  test    al, 8
0x14001c0d6  jz      short loc_14001C0F7
0x14001c0d8  cmp     byte ptr [rcx+29h], 5
0x14001c0dc  jb      short loc_14001C0F7
0x14001c0de  mov     rcx, [rcx+18h]
0x14001c0e2  mov     [rsp+78h+var_40], ebp
0x14001c0e6  mov     [rsp+78h+var_48], esi
0x14001c0ea  mov     [r11-50h], r14
0x14001c0ee  mov     [r11-58h], rdx
0x14001c0f2  call    WPP_SF_qqqlD
0x14001c0f7  lea     r8, [rsp+78h+arg_8]
0x14001c0ff  xor     edx, edx
0x14001c101  mov     rcx, r14
0x14001c104  call    HsmiFileCacheValidateFileObject
0x14001c109  mov     ecx, eax
0x14001c10b  mov     ebx, eax
0x14001c10d  call    HsmDbgBreakOnStatus
0x14001c112  test    ebx, ebx
0x14001c114  jns     short loc_14001C15D
0x14001c116  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c11d  cmp     rcx, r13
0x14001c120  jz      loc_14001C218
0x14001c126  mov     edx, [rcx+2Ch]
0x14001c129  test    dl, 8
0x14001c12c  jz      loc_14001C218
0x14001c132  cmp     byte ptr [rcx+29h], 2
0x14001c136  jb      loc_14001C218
0x14001c13c  mov     rcx, [rcx+18h]
0x14001c140  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c147  mov     edx, 66h ; 'f'
0x14001c14c  mov     dword ptr [rsp+78h+var_58], ebx
0x14001c150  mov     r9, r14
0x14001c153  call    WPP_SF_qd
0x14001c158  jmp     loc_14001C218
0x14001c15d  cmp     esi, 5
0x14001c160  jz      short loc_14001C1A1
0x14001c162  mov     ebx, 0C0000010h
0x14001c167  mov     ecx, ebx
0x14001c169  call    HsmDbgBreakOnStatus
0x14001c16e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c175  cmp     rcx, r13
0x14001c178  jz      loc_14001C218
0x14001c17e  mov     eax, [rcx+2Ch]
0x14001c181  test    al, 8
0x14001c183  jz      loc_14001C218
0x14001c189  cmp     byte ptr [rcx+29h], 2
0x14001c18d  jb      loc_14001C218
0x14001c193  mov     rcx, [rcx+18h]
0x14001c197  mov     r9d, esi
0x14001c19a  call    WPP_SF_ld
0x14001c19f  jmp     short loc_14001C218
0x14001c1a1  cmp     ebp, 18h
0x14001c1a4  jz      short loc_14001C1EE
0x14001c1a6  mov     ebx, 0C000000Dh
0x14001c1ab  mov     ecx, ebx
0x14001c1ad  call    HsmDbgBreakOnStatus
0x14001c1b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1b9  cmp     rcx, r13
0x14001c1bc  jz      short loc_14001C218
0x14001c1be  mov     eax, [rcx+2Ch]
0x14001c1c1  test    al, 8
0x14001c1c3  jz      short loc_14001C218
0x14001c1c5  cmp     byte ptr [rcx+29h], 2
0x14001c1c9  jb      short loc_14001C218
0x14001c1cb  mov     rcx, [rcx+18h]
0x14001c1cf  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c1d6  mov     edx, 68h ; 'h'
0x14001c1db  mov     [rsp+78h+var_50], ebx
0x14001c1df  mov     dword ptr [rsp+78h+var_58], ebp
0x14001c1e3  lea     r9d, [rdx-50h]
0x14001c1e7  call    WPP_SF_DDd
0x14001c1ec  jmp     short loc_14001C218
0x14001c1ee  mov     rdx, [rdi+18h]
0x14001c1f2  xor     ebx, ebx
0x14001c1f4  mov     rcx, [rsp+78h+arg_8]
0x14001c1fc  mov     rax, [rcx+18h]
0x14001c200  mov     [rdx], rax
0x14001c203  mov     rax, [rcx+20h]
0x14001c207  mov     [rdx+8], rax
0x14001c20b  mov     dword ptr [rdx+10h], 1
0x14001c212  mov     word ptr [rdx+14h], 0
0x14001c218  xor     edx, edx; PriorityBoost
0x14001c21a  mov     [rdi+30h], ebx
0x14001c21d  mov     rcx, rdi; Irp
0x14001c220  mov     qword ptr [rdi+38h], 0
0x14001c228  call    cs:__imp_IofCompleteRequest
0x14001c22f  nop     dword ptr [rax+rax+00h]
0x14001c234  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c23b  cmp     rcx, r13
0x14001c23e  jz      short loc_14001C265
0x14001c240  mov     eax, [rcx+2Ch]
0x14001c243  test    al, 8
0x14001c245  jz      short loc_14001C265
0x14001c247  cmp     byte ptr [rcx+29h], 5
0x14001c24b  jb      short loc_14001C265
0x14001c24d  mov     rcx, [rcx+18h]
0x14001c251  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c258  mov     edx, 69h ; 'i'
0x14001c25d  mov     r9d, ebx
0x14001c260  call    WPP_SF_d
0x14001c265  mov     eax, ebx
0x14001c267  add     rsp, 48h
0x14001c26b  pop     r14
0x14001c26d  pop     r13
0x14001c26f  pop     rdi
0x14001c270  pop     rsi
0x14001c271  pop     rbp
0x14001c272  pop     rbx
0x14001c273  retn
```
