# HsmCldPersistSyncRootInfo

- ea: `0x140035184`
- end: `0x140035360`
- name: `HsmCldPersistSyncRootInfo`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14003baf0`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x140035184`
- `0x14005cd20`
- `0x14005eb40`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140035328`
- `ntoskrnl!ObfDereferenceObject` at `0x140035328`
- `FLTMGR!FltWriteFile` at `0x1400352cb`
- `FLTMGR!FltWriteFile` at `0x1400352cb`
- `FLTMGR!FltClose` at `0x14003533d`
- `FLTMGR!FltClose` at `0x14003533d`

## pseudocode

```c
__int64 __fastcall HsmCldPersistSyncRootInfo(__int64 a1, struct _FILE_OBJECT *a2, void *a3, ULONG a4)
{
  struct _FLT_INSTANCE *v4; // r13
  int v9; // ebx
  PFILE_OBJECT v10; // rdi
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  PULONG BytesWritten; // [rsp+30h] [rbp-39h]
  PFILE_OBJECT FileObject; // [rsp+50h] [rbp-19h] BYREF
  HANDLE FileHandle; // [rsp+58h] [rbp-11h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+60h] [rbp-9h] BYREF
  struct _UNICODE_STRING v18[5]; // [rsp+68h] [rbp-1h] BYREF
  ULONG v19; // [rsp+D0h] [rbp+67h] BYREF

  v4 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v18[0].Buffer = L":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0}.SyncRootIdentity";
  *(_QWORD *)&v18[0].Length = 7602290;
  FileHandle = 0;
  FileObject = 0;
  ByteOffset.QuadPart = 0;
  v19 = 0;
  v9 = HsmpRelativeStreamOpen(a1, a2, v18, 0x100000u, 5u, 32, BytesWritten, &FileHandle, &FileObject);
  HsmDbgBreakOnStatus((unsigned int)v9);
  v10 = FileObject;
  if ( v9 >= 0 )
  {
    v9 = HsmpPrepareForMgmtOperation(a1, FileObject, 8, 0);
    HsmDbgBreakOnStatus((unsigned int)v9);
    if ( v9 >= 0 )
    {
      v10->WriteAccess = 1;
      v9 = FltWriteFile(v4, v10, &ByteOffset, a4, a3, 0, &v19, 0, 0);
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( v9 < 0 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 71;
          goto LABEL_16;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 70;
        goto LABEL_16;
      }
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v12 = 69;
LABEL_16:
      WPP_SF_qd(v11->AttachedDevice, v12, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids, a2, v9);
    }
  }
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140035184  push    rbp
0x140035186  push    rbx
0x140035187  push    rsi
0x140035188  push    rdi
0x140035189  push    r12
0x14003518b  push    r13
0x14003518d  push    r14
0x14003518f  push    r15
0x140035191  lea     rbp, [rsp-1Fh]
0x140035196  sub     rsp, 88h
0x14003519d  mov     r13, [rcx+20h]
0x1400351a1  lea     rax, a3d0ce612Fdee43_2; ":${3D0CE612-FDEE-43f7-8ACA-957BEC0CCBA0"...
0x1400351a8  mov     [rbp+57h+var_50], rax
0x1400351ac  mov     r15d, r9d
0x1400351af  xor     eax, eax
0x1400351b1  mov     qword ptr [rbp+57h+var_58], 740072h
0x1400351b9  mov     [rbp+57h+FileHandle], rax
0x1400351bd  mov     r12, r8
0x1400351c0  mov     [rbp+57h+FileObject], rax
0x1400351c4  lea     r8, [rbp+57h+var_58]; int
0x1400351c8  mov     qword ptr [rbp+57h+ByteOffset], rax
0x1400351cc  mov     r9d, 100000h; int
0x1400351d2  mov     [rbp+57h+arg_0], eax
0x1400351d5  mov     rsi, rdx
0x1400351d8  lea     rax, [rbp+57h+FileObject]
0x1400351dc  mov     r14, rcx
0x1400351df  mov     [rsp+0C0h+CallbackContext], rax; __int64
0x1400351e4  lea     rax, [rbp+57h+FileHandle]
0x1400351e8  mov     [rsp+0C0h+CallbackRoutine], rax; __int64
0x1400351ed  mov     [rsp+0C0h+Flags], 20h ; ' '; int
0x1400351f5  mov     dword ptr [rsp+0C0h+Buffer], 5; ULONG
0x1400351fd  call    HsmpRelativeStreamOpen
0x140035202  mov     ecx, eax
0x140035204  mov     ebx, eax
0x140035206  call    HsmDbgBreakOnStatus
0x14003520b  mov     rdi, [rbp+57h+FileObject]
0x14003520f  test    ebx, ebx
0x140035211  jns     short loc_14003524A
0x140035213  mov     rcx, cs:WPP_GLOBAL_Control
0x14003521a  lea     rax, WPP_GLOBAL_Control
0x140035221  cmp     rcx, rax
0x140035224  jz      loc_140035320
0x14003522a  mov     edx, [rcx+2Ch]
0x14003522d  test    dl, 1
0x140035230  jz      loc_140035320
0x140035236  cmp     byte ptr [rcx+29h], 2
0x14003523a  jb      loc_140035320
0x140035240  mov     edx, 45h ; 'E'
0x140035245  jmp     loc_140035309
0x14003524a  xor     r9d, r9d
0x14003524d  mov     rdx, rdi
0x140035250  mov     rcx, r14
0x140035253  lea     r8d, [r9+8]
0x140035257  call    HsmpPrepareForMgmtOperation
0x14003525c  mov     ecx, eax
0x14003525e  mov     ebx, eax
0x140035260  call    HsmDbgBreakOnStatus
0x140035265  xor     ecx, ecx
0x140035267  test    ebx, ebx
0x140035269  jns     short loc_14003529E
0x14003526b  mov     rcx, cs:WPP_GLOBAL_Control
0x140035272  lea     rax, WPP_GLOBAL_Control
0x140035279  cmp     rcx, rax
0x14003527c  jz      loc_140035320
0x140035282  mov     eax, [rcx+2Ch]
0x140035285  test    al, 1
0x140035287  jz      loc_140035320
0x14003528d  cmp     byte ptr [rcx+29h], 2
0x140035291  jb      loc_140035320
0x140035297  mov     edx, 46h ; 'F'
0x14003529c  jmp     short loc_140035309
0x14003529e  mov     [rsp+0C0h+CallbackContext], rcx; CallbackContext
0x1400352a3  lea     rax, [rbp+57h+arg_0]
0x1400352a7  mov     [rsp+0C0h+CallbackRoutine], rcx; CallbackRoutine
0x1400352ac  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x1400352b0  mov     [rsp+0C0h+BytesWritten], rax; BytesWritten
0x1400352b5  mov     r9d, r15d; Length
0x1400352b8  mov     [rsp+0C0h+Flags], ecx; Flags
0x1400352bc  mov     rdx, rdi; FileObject
0x1400352bf  mov     rcx, r13; InitiatingInstance
0x1400352c2  mov     byte ptr [rdi+4Bh], 1
0x1400352c6  mov     [rsp+0C0h+Buffer], r12; Buffer
0x1400352cb  call    cs:__imp_FltWriteFile
0x1400352d2  nop     dword ptr [rax+rax+00h]
0x1400352d7  mov     ecx, eax
0x1400352d9  mov     ebx, eax
0x1400352db  call    HsmDbgBreakOnStatus
0x1400352e0  test    ebx, ebx
0x1400352e2  jns     short loc_140035320
0x1400352e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400352eb  lea     rax, WPP_GLOBAL_Control
0x1400352f2  cmp     rcx, rax
0x1400352f5  jz      short loc_140035320
0x1400352f7  mov     eax, [rcx+2Ch]
0x1400352fa  test    al, 1
0x1400352fc  jz      short loc_140035320
0x1400352fe  cmp     byte ptr [rcx+29h], 2
0x140035302  jb      short loc_140035320
0x140035304  mov     edx, 47h ; 'G'
0x140035309  mov     rcx, [rcx+18h]
0x14003530d  lea     r8, WPP_6e1e33f79617319dc28b4de987ec2fe8_Traceguids
0x140035314  mov     r9, rsi
0x140035317  mov     dword ptr [rsp+0C0h+Buffer], ebx
0x14003531b  call    WPP_SF_qd
0x140035320  test    rdi, rdi
0x140035323  jz      short loc_140035334
0x140035325  mov     rcx, rdi; Object
0x140035328  call    cs:__imp_ObfDereferenceObject
0x14003532f  nop     dword ptr [rax+rax+00h]
0x140035334  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140035338  test    rcx, rcx
0x14003533b  jz      short loc_140035349
0x14003533d  call    cs:__imp_FltClose
0x140035344  nop     dword ptr [rax+rax+00h]
0x140035349  mov     eax, ebx
0x14003534b  add     rsp, 88h
0x140035352  pop     r15
0x140035354  pop     r14
0x140035356  pop     r13
0x140035358  pop     r12
0x14003535a  pop     rdi
0x14003535b  pop     rsi
0x14003535c  pop     rbx
0x14003535d  pop     rbp
0x14003535e  retn
```
