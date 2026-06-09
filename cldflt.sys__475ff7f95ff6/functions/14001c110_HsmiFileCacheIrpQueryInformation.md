# HsmiFileCacheIrpQueryInformation

- ea: `0x14001c110`
- end: `0x14001c2f5`
- name: `HsmiFileCacheIrpQueryInformation`
- size: `485`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140003c50`
- `0x1400054c0`
- `0x14000c12c`
- `0x14000d95c`
- `0x14001888c`
- `0x14001c110`
- `0x14001cb84`
- `0x14001d2ac`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14001c2a8`
- `ntoskrnl!IofCompleteRequest` at `0x14001c2a8`

## pseudocode

```c
__int64 __fastcall HsmiFileCacheIrpQueryInformation(__int64 a1, IRP *a2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // r14
  ULONG Options; // esi
  ULONG Length; // ebp
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r8
  struct _IRP *MasterIrp; // rdx
  __int64 v12; // rcx
  __int64 v14; // [rsp+88h] [rbp+10h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v14 = 0;
  FileObject = CurrentStackLocation->FileObject;
  Options = CurrentStackLocation->Parameters.Create.Options;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqqlD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, a2, FileObject, Options, Length);
  }
  v8 = HsmiFileCacheValidateFileObject(FileObject, 0, &v14);
  HsmDbgBreakOnStatus(v8);
  if ( v8 >= 0 )
  {
    if ( Options == 5 )
    {
      if ( Length == 24 )
      {
        MasterIrp = a2->AssociatedIrp.MasterIrp;
        v8 = 0;
        v12 = v14;
        *(_QWORD *)&MasterIrp->Type = *(_QWORD *)(v14 + 24);
        MasterIrp->MdlAddress = *(PMDL *)(v12 + 32);
        MasterIrp->Flags = 1;
        *((_WORD *)&MasterIrp->Flags + 2) = 0;
      }
      else
      {
        v8 = -1073741811;
        HsmDbgBreakOnStatus(-1073741811);
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
      v8 = -1073741808;
      HsmDbgBreakOnStatus(-1073741808);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_ld(WPP_GLOBAL_Control->AttachedDevice, v9, v10, Options);
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, FileObject, v8);
  }
  a2->IoStatus.Status = v8;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids, (unsigned int)v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14001c110  mov     r11, rsp
0x14001c113  push    rbx
0x14001c114  push    rbp
0x14001c115  push    rsi
0x14001c116  push    rdi
0x14001c117  push    r13
0x14001c119  push    r14
0x14001c11b  sub     rsp, 48h
0x14001c11f  mov     rax, [rdx+0B8h]
0x14001c126  mov     rdi, rdx
0x14001c129  mov     r9, rcx
0x14001c12c  mov     qword ptr [r11+10h], 0
0x14001c134  mov     r14, [rax+30h]
0x14001c138  mov     esi, [rax+10h]
0x14001c13b  mov     ebp, [rax+8]
0x14001c13e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c145  lea     r13, WPP_GLOBAL_Control
0x14001c14c  cmp     rcx, r13
0x14001c14f  jz      short loc_14001C177
0x14001c151  mov     eax, [rcx+2Ch]
0x14001c154  test    al, 8
0x14001c156  jz      short loc_14001C177
0x14001c158  cmp     byte ptr [rcx+29h], 5
0x14001c15c  jb      short loc_14001C177
0x14001c15e  mov     rcx, [rcx+18h]
0x14001c162  mov     [rsp+78h+var_40], ebp
0x14001c166  mov     [rsp+78h+var_48], esi
0x14001c16a  mov     [r11-50h], r14
0x14001c16e  mov     [r11-58h], rdx
0x14001c172  call    WPP_SF_qqqlD
0x14001c177  lea     r8, [rsp+78h+arg_8]
0x14001c17f  xor     edx, edx
0x14001c181  mov     rcx, r14
0x14001c184  call    HsmiFileCacheValidateFileObject
0x14001c189  mov     ecx, eax
0x14001c18b  mov     ebx, eax
0x14001c18d  call    HsmDbgBreakOnStatus
0x14001c192  test    ebx, ebx
0x14001c194  jns     short loc_14001C1DD
0x14001c196  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c19d  cmp     rcx, r13
0x14001c1a0  jz      loc_14001C298
0x14001c1a6  mov     edx, [rcx+2Ch]
0x14001c1a9  test    dl, 8
0x14001c1ac  jz      loc_14001C298
0x14001c1b2  cmp     byte ptr [rcx+29h], 2
0x14001c1b6  jb      loc_14001C298
0x14001c1bc  mov     rcx, [rcx+18h]
0x14001c1c0  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c1c7  mov     edx, 66h ; 'f'
0x14001c1cc  mov     [rsp+78h+var_58], ebx
0x14001c1d0  mov     r9, r14
0x14001c1d3  call    WPP_SF_qd
0x14001c1d8  jmp     loc_14001C298
0x14001c1dd  cmp     esi, 5
0x14001c1e0  jz      short loc_14001C221
0x14001c1e2  mov     ebx, 0C0000010h
0x14001c1e7  mov     ecx, ebx
0x14001c1e9  call    HsmDbgBreakOnStatus
0x14001c1ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c1f5  cmp     rcx, r13
0x14001c1f8  jz      loc_14001C298
0x14001c1fe  mov     eax, [rcx+2Ch]
0x14001c201  test    al, 8
0x14001c203  jz      loc_14001C298
0x14001c209  cmp     byte ptr [rcx+29h], 2
0x14001c20d  jb      loc_14001C298
0x14001c213  mov     rcx, [rcx+18h]
0x14001c217  mov     r9d, esi
0x14001c21a  call    WPP_SF_ld
0x14001c21f  jmp     short loc_14001C298
0x14001c221  cmp     ebp, 18h
0x14001c224  jz      short loc_14001C26E
0x14001c226  mov     ebx, 0C000000Dh
0x14001c22b  mov     ecx, ebx
0x14001c22d  call    HsmDbgBreakOnStatus
0x14001c232  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c239  cmp     rcx, r13
0x14001c23c  jz      short loc_14001C298
0x14001c23e  mov     eax, [rcx+2Ch]
0x14001c241  test    al, 8
0x14001c243  jz      short loc_14001C298
0x14001c245  cmp     byte ptr [rcx+29h], 2
0x14001c249  jb      short loc_14001C298
0x14001c24b  mov     rcx, [rcx+18h]
0x14001c24f  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c256  mov     edx, 68h ; 'h'
0x14001c25b  mov     [rsp+78h+var_50], ebx
0x14001c25f  mov     [rsp+78h+var_58], ebp
0x14001c263  lea     r9d, [rdx-50h]
0x14001c267  call    WPP_SF_DDd
0x14001c26c  jmp     short loc_14001C298
0x14001c26e  mov     rdx, [rdi+18h]
0x14001c272  xor     ebx, ebx
0x14001c274  mov     rcx, [rsp+78h+arg_8]
0x14001c27c  mov     rax, [rcx+18h]
0x14001c280  mov     [rdx], rax
0x14001c283  mov     rax, [rcx+20h]
0x14001c287  mov     [rdx+8], rax
0x14001c28b  mov     dword ptr [rdx+10h], 1
0x14001c292  mov     word ptr [rdx+14h], 0
0x14001c298  xor     edx, edx; PriorityBoost
0x14001c29a  mov     [rdi+30h], ebx
0x14001c29d  mov     rcx, rdi; Irp
0x14001c2a0  mov     qword ptr [rdi+38h], 0
0x14001c2a8  call    cs:__imp_IofCompleteRequest
0x14001c2af  nop     dword ptr [rax+rax+00h]
0x14001c2b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001c2bb  cmp     rcx, r13
0x14001c2be  jz      short loc_14001C2E5
0x14001c2c0  mov     eax, [rcx+2Ch]
0x14001c2c3  test    al, 8
0x14001c2c5  jz      short loc_14001C2E5
0x14001c2c7  cmp     byte ptr [rcx+29h], 5
0x14001c2cb  jb      short loc_14001C2E5
0x14001c2cd  mov     rcx, [rcx+18h]
0x14001c2d1  lea     r8, WPP_eedb54661d013ed432adc8f9abc3a2eb_Traceguids
0x14001c2d8  mov     edx, 69h ; 'i'
0x14001c2dd  mov     r9d, ebx
0x14001c2e0  call    WPP_SF_d
0x14001c2e5  mov     eax, ebx
0x14001c2e7  add     rsp, 48h
0x14001c2eb  pop     r14
0x14001c2ed  pop     r13
0x14001c2ef  pop     rdi
0x14001c2f0  pop     rsi
0x14001c2f1  pop     rbp
0x14001c2f2  pop     rbx
0x14001c2f3  retn
```
