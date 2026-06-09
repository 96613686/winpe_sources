# HsmRecallUpdatePlaceholderFile

- ea: `0x140043ff4`
- end: `0x1400441f8`
- name: `HsmRecallUpdatePlaceholderFile`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140040d14`
- `0x1400412c4`

## callees

- `0x140003c50`
- `0x140017d64`
- `0x140043ff4`
- `0x14005ce40`
- `0x14005e76c`
- `0x14007b72c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400441bb`
- `ntoskrnl!ObfDereferenceObject` at `0x1400441bb`
- `FLTMGR!FltClose` at `0x1400441d4`
- `FLTMGR!FltClose` at `0x1400441d4`

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
  HsmDbgBreakOnStatus(updated);
  if ( updated >= 0 )
  {
    updated = HsmpPrepareForMgmtOperation(a1, Object, 8);
    HsmDbgBreakOnStatus(updated);
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
      HsmDbgBreakOnStatus(updated);
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
0x140043ff4  mov     r11, rsp
0x140043ff7  mov     [r11+18h], rbx
0x140043ffb  push    rbp
0x140043ffc  push    rdi
0x140043ffd  push    r12
0x140043fff  push    r14
0x140044001  push    r15
0x140044003  sub     rsp, 70h
0x140044007  mov     rax, [rdx+10h]
0x14004400b  mov     r15, r9
0x14004400e  mov     r12d, r8d
0x140044011  mov     qword ptr [r11+8], 0
0x140044019  mov     rdi, rdx
0x14004401c  mov     qword ptr [r11+10h], 0
0x140044024  mov     rdx, [rcx+20h]
0x140044028  mov     r9d, 100180h
0x14004402e  mov     r14, [rax+20h]
0x140044032  mov     rbp, rcx
0x140044035  lea     rax, [r11+8]
0x140044039  mov     r8, r14
0x14004403c  mov     [r11-58h], rax
0x140044040  lea     rax, [r11+10h]
0x140044044  mov     [r11-60h], rax
0x140044048  mov     byte ptr [rsp+98h+var_68], 0
0x14004404d  mov     dword ptr [rsp+98h+var_70], 200020h
0x140044055  call    HsmpOpenFileByIdEx
0x14004405a  mov     ecx, eax
0x14004405c  mov     ebx, eax
0x14004405e  call    HsmDbgBreakOnStatus
0x140044063  test    ebx, ebx
0x140044065  jns     short loc_1400440C3
0x140044067  mov     r10, cs:WPP_GLOBAL_Control
0x14004406e  lea     rax, WPP_GLOBAL_Control
0x140044075  cmp     r10, rax
0x140044078  jz      loc_1400441A8
0x14004407e  mov     ecx, [r10+2Ch]
0x140044082  test    cl, 1
0x140044085  jz      loc_1400441A8
0x14004408b  cmp     byte ptr [r10+29h], 2
0x140044090  jb      loc_1400441A8
0x140044096  mov     rcx, [r10+18h]
0x14004409a  mov     edx, 68h ; 'h'
0x14004409f  mov     eax, [rdi+1Ch]
0x1400440a2  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x1400440a9  mov     dword ptr [rsp+98h+var_68], ebx
0x1400440ad  mov     r9, rdi
0x1400440b0  mov     [rsp+98h+var_70], r14
0x1400440b5  mov     dword ptr [rsp+98h+var_78], eax
0x1400440b9  call    WPP_SF_qLid
0x1400440be  jmp     loc_1400441A8
0x1400440c3  mov     rdx, [rsp+98h+Object]
0x1400440cb  xor     r9d, r9d
0x1400440ce  mov     rcx, rbp
0x1400440d1  lea     r8d, [r9+8]
0x1400440d5  call    HsmpPrepareForMgmtOperation
0x1400440da  mov     ecx, eax
0x1400440dc  mov     ebx, eax
0x1400440de  call    HsmDbgBreakOnStatus
0x1400440e3  test    ebx, ebx
0x1400440e5  jns     short loc_14004411E
0x1400440e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400440ee  lea     rax, WPP_GLOBAL_Control
0x1400440f5  cmp     rcx, rax
0x1400440f8  jz      loc_1400441A8
0x1400440fe  mov     eax, [rcx+2Ch]
0x140044101  test    al, 1
0x140044103  jz      loc_1400441A8
0x140044109  cmp     byte ptr [rcx+29h], 2
0x14004410d  jb      loc_1400441A8
0x140044113  mov     rcx, [rcx+18h]
0x140044117  mov     edx, 69h ; 'i'
0x14004411c  jmp     short loc_14004409F
0x14004411e  mov     rax, [rsp+98h+arg_48]
0x140044126  mov     r9d, r12d
0x140044129  mov     r8, [rsp+98h+Object]
0x140044131  mov     rdx, rdi
0x140044134  mov     [rsp+98h+var_30], 0
0x14004413d  mov     rcx, rbp
0x140044140  mov     [rsp+98h+var_38], rax
0x140044145  mov     rax, [rsp+98h+arg_40]
0x14004414d  mov     [rsp+98h+var_40], rax
0x140044152  mov     rax, [rsp+98h+arg_38]
0x14004415a  mov     [rsp+98h+var_48], rax
0x14004415f  mov     rax, [rsp+98h+arg_30]
0x140044167  mov     [rsp+98h+var_50], rax
0x14004416c  mov     rax, [rsp+98h+arg_28]
0x140044174  mov     [rsp+98h+var_58], rax
0x140044179  mov     eax, [rsp+98h+arg_20]
0x140044180  mov     [rsp+98h+var_60], eax
0x140044184  mov     [rsp+98h+var_68], r15
0x140044189  mov     dword ptr [rsp+98h+var_70], 0
0x140044191  mov     [rsp+98h+var_78], 0
0x14004419a  call    HsmiOpUpdatePlaceholderFile
0x14004419f  mov     ecx, eax
0x1400441a1  mov     ebx, eax
0x1400441a3  call    HsmDbgBreakOnStatus
0x1400441a8  cmp     [rsp+98h+Object], 0
0x1400441b1  jz      short loc_1400441C7
0x1400441b3  mov     rcx, [rsp+98h+Object]; Object
0x1400441bb  call    cs:__imp_ObfDereferenceObject
0x1400441c2  nop     dword ptr [rax+rax+00h]
0x1400441c7  mov     rcx, [rsp+98h+FileHandle]; FileHandle
0x1400441cf  test    rcx, rcx
0x1400441d2  jz      short loc_1400441E0
0x1400441d4  call    cs:__imp_FltClose
0x1400441db  nop     dword ptr [rax+rax+00h]
0x1400441e0  mov     eax, ebx
0x1400441e2  mov     rbx, [rsp+98h+arg_10]
0x1400441ea  add     rsp, 70h
0x1400441ee  pop     r15
0x1400441f0  pop     r14
0x1400441f2  pop     r12
0x1400441f4  pop     rdi
0x1400441f5  pop     rbp
0x1400441f6  retn
```
