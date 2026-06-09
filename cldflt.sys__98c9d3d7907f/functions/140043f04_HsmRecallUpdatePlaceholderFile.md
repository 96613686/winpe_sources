# HsmRecallUpdatePlaceholderFile

- ea: `0x140043f04`
- end: `0x140044108`
- name: `HsmRecallUpdatePlaceholderFile`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140040d04`
- `0x1400412b4`

## callees

- `0x140003c50`
- `0x140017ce4`
- `0x140043f04`
- `0x14005cd20`
- `0x14005e64c`
- `0x14007b5ec`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400440cb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400440cb`
- `FLTMGR!FltClose` at `0x1400440e4`
- `FLTMGR!FltClose` at `0x1400440e4`

## pseudocode

```c
__int64 __fastcall HsmRecallUpdatePlaceholderFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        void *a4,
        int a5,
        __int64 *a6,
        _DWORD *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  __int64 v10; // rax
  __int64 v14; // r14
  int updated; // ebx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  int v18; // edx
  __int64 v20; // [rsp+20h] [rbp-78h]
  PVOID Object; // [rsp+A0h] [rbp+8h] BYREF
  HANDLE FileHandle; // [rsp+A8h] [rbp+10h] BYREF

  v10 = *(_QWORD *)(a2 + 16);
  Object = 0;
  FileHandle = 0;
  v14 = *(_QWORD *)(v10 + 32);
  updated = HsmpOpenFileByIdEx(
              (const UNICODE_STRING *)a1,
              *(struct _FLT_INSTANCE **)(a1 + 32),
              v14,
              0x100180u,
              v20,
              2097184,
              0,
              &FileHandle,
              (PFILE_OBJECT *)&Object);
  HsmDbgBreakOnStatus((unsigned int)updated);
  if ( updated >= 0 )
  {
    updated = HsmpPrepareForMgmtOperation(a1, Object, 8, 0);
    HsmDbgBreakOnStatus((unsigned int)updated);
    if ( updated >= 0 )
    {
      updated = HsmiOpUpdatePlaceholderFile(
                  a1,
                  a2,
                  (struct _FILE_OBJECT *)Object,
                  a3,
                  0,
                  0,
                  a4,
                  a5,
                  a6,
                  a7,
                  a8,
                  a9,
                  a10,
                  0);
      HsmDbgBreakOnStatus((unsigned int)updated);
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
      v18 = 105;
      goto LABEL_6;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v18 = 104;
LABEL_6:
    WPP_SF_qLid(
      (_DWORD)AttachedDevice,
      v18,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v14,
      updated);
  }
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x140043f04  mov     r11, rsp
0x140043f07  mov     [r11+18h], rbx
0x140043f0b  push    rbp
0x140043f0c  push    rdi
0x140043f0d  push    r12
0x140043f0f  push    r14
0x140043f11  push    r15
0x140043f13  sub     rsp, 70h
0x140043f17  mov     rax, [rdx+10h]
0x140043f1b  mov     r15, r9
0x140043f1e  mov     r12d, r8d
0x140043f21  mov     qword ptr [r11+8], 0
0x140043f29  mov     rdi, rdx
0x140043f2c  mov     qword ptr [r11+10h], 0
0x140043f34  mov     rdx, [rcx+20h]
0x140043f38  mov     r9d, 100180h
0x140043f3e  mov     r14, [rax+20h]
0x140043f42  mov     rbp, rcx
0x140043f45  lea     rax, [r11+8]
0x140043f49  mov     r8, r14
0x140043f4c  mov     [r11-58h], rax
0x140043f50  lea     rax, [r11+10h]
0x140043f54  mov     [r11-60h], rax
0x140043f58  mov     byte ptr [rsp+98h+var_68], 0
0x140043f5d  mov     dword ptr [rsp+98h+var_70], 200020h
0x140043f65  call    HsmpOpenFileByIdEx
0x140043f6a  mov     ecx, eax
0x140043f6c  mov     ebx, eax
0x140043f6e  call    HsmDbgBreakOnStatus
0x140043f73  test    ebx, ebx
0x140043f75  jns     short loc_140043FD3
0x140043f77  mov     r10, cs:WPP_GLOBAL_Control
0x140043f7e  lea     rax, WPP_GLOBAL_Control
0x140043f85  cmp     r10, rax
0x140043f88  jz      loc_1400440B8
0x140043f8e  mov     ecx, [r10+2Ch]
0x140043f92  test    cl, 1
0x140043f95  jz      loc_1400440B8
0x140043f9b  cmp     byte ptr [r10+29h], 2
0x140043fa0  jb      loc_1400440B8
0x140043fa6  mov     rcx, [r10+18h]
0x140043faa  mov     edx, 68h ; 'h'
0x140043faf  mov     eax, [rdi+1Ch]
0x140043fb2  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x140043fb9  mov     dword ptr [rsp+98h+var_68], ebx
0x140043fbd  mov     r9, rdi
0x140043fc0  mov     [rsp+98h+var_70], r14
0x140043fc5  mov     dword ptr [rsp+98h+var_78], eax
0x140043fc9  call    WPP_SF_qLid
0x140043fce  jmp     loc_1400440B8
0x140043fd3  mov     rdx, [rsp+98h+Object]
0x140043fdb  xor     r9d, r9d
0x140043fde  mov     rcx, rbp
0x140043fe1  lea     r8d, [r9+8]
0x140043fe5  call    HsmpPrepareForMgmtOperation
0x140043fea  mov     ecx, eax
0x140043fec  mov     ebx, eax
0x140043fee  call    HsmDbgBreakOnStatus
0x140043ff3  test    ebx, ebx
0x140043ff5  jns     short loc_14004402E
0x140043ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ffe  lea     rax, WPP_GLOBAL_Control
0x140044005  cmp     rcx, rax
0x140044008  jz      loc_1400440B8
0x14004400e  mov     eax, [rcx+2Ch]
0x140044011  test    al, 1
0x140044013  jz      loc_1400440B8
0x140044019  cmp     byte ptr [rcx+29h], 2
0x14004401d  jb      loc_1400440B8
0x140044023  mov     rcx, [rcx+18h]
0x140044027  mov     edx, 69h ; 'i'
0x14004402c  jmp     short loc_140043FAF
0x14004402e  mov     rax, [rsp+98h+arg_48]
0x140044036  mov     r9d, r12d
0x140044039  mov     r8, [rsp+98h+Object]
0x140044041  mov     rdx, rdi
0x140044044  mov     [rsp+98h+var_30], 0
0x14004404d  mov     rcx, rbp
0x140044050  mov     [rsp+98h+var_38], rax
0x140044055  mov     rax, [rsp+98h+arg_40]
0x14004405d  mov     [rsp+98h+var_40], rax
0x140044062  mov     rax, [rsp+98h+arg_38]
0x14004406a  mov     [rsp+98h+var_48], rax
0x14004406f  mov     rax, [rsp+98h+arg_30]
0x140044077  mov     [rsp+98h+var_50], rax
0x14004407c  mov     rax, [rsp+98h+arg_28]
0x140044084  mov     [rsp+98h+var_58], rax
0x140044089  mov     eax, [rsp+98h+arg_20]
0x140044090  mov     [rsp+98h+var_60], eax
0x140044094  mov     [rsp+98h+var_68], r15
0x140044099  mov     dword ptr [rsp+98h+var_70], 0
0x1400440a1  mov     [rsp+98h+var_78], 0
0x1400440aa  call    HsmiOpUpdatePlaceholderFile
0x1400440af  mov     ecx, eax
0x1400440b1  mov     ebx, eax
0x1400440b3  call    HsmDbgBreakOnStatus
0x1400440b8  cmp     [rsp+98h+Object], 0
0x1400440c1  jz      short loc_1400440D7
0x1400440c3  mov     rcx, [rsp+98h+Object]; Object
0x1400440cb  call    cs:__imp_ObfDereferenceObject
0x1400440d2  nop     dword ptr [rax+rax+00h]
0x1400440d7  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x1400440df  test    rcx, rcx
0x1400440e2  jz      short loc_1400440F0
0x1400440e4  call    cs:__imp_FltClose
0x1400440eb  nop     dword ptr [rax+rax+00h]
0x1400440f0  mov     eax, ebx
0x1400440f2  mov     rbx, [rsp+98h+arg_10]
0x1400440fa  add     rsp, 70h
0x1400440fe  pop     r15
0x140044100  pop     r14
0x140044102  pop     r12
0x140044104  pop     rdi
0x140044105  pop     rbp
0x140044106  retn
```
