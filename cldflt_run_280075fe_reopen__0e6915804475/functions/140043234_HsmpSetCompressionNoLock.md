# HsmpSetCompressionNoLock

- ea: `0x140043234`
- end: `0x140043485`
- name: `HsmpSetCompressionNoLock`
- size: `593`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004348c`
- `0x140047b30`
- `0x14005fcc4`
- `0x14007b5ec`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000c12c`
- `0x140043234`
- `0x140055250`
- `0x14005e64c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140043447`
- `ntoskrnl!ObfDereferenceObject` at `0x140043447`
- `FLTMGR!FltClose` at `0x14004345d`
- `FLTMGR!FltClose` at `0x14004345d`
- `FLTMGR!FltFsControlFile` at `0x1400433ba`
- `FLTMGR!FltFsControlFile` at `0x1400433ba`
- `FLTMGR!FltReleaseContext` at `0x14004342e`
- `FLTMGR!FltReleaseContext` at `0x14004342e`

## pseudocode

```c
__int64 __fastcall HsmpSetCompressionNoLock(const UNICODE_STRING *a1, struct _FILE_OBJECT *a2, __int16 a3, __int64 a4)
{
  struct _FLT_INSTANCE **v6; // r14
  int v8; // esi
  struct _FILE_OBJECT *v9; // rbx
  _DWORD *StreamContext; // rax
  _DWORD *v11; // rdi
  __int64 InputBufferLength; // [rsp+20h] [rbp-68h]
  HANDLE FileHandle; // [rsp+50h] [rbp-38h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp+10h] BYREF
  __int16 InputBuffer; // [rsp+A0h] [rbp+18h] BYREF

  InputBuffer = a3;
  FileHandle = 0;
  FileObject = 0;
  v6 = (struct _FLT_INSTANCE **)&a1[2];
  if ( a2 )
  {
    v8 = 0;
    v9 = a2;
  }
  else
  {
    v8 = HsmpOpenFileByIdEx(a1, *v6, a4, 0x100180u, InputBufferLength, 2097248, 1, &FileHandle, &FileObject);
    HsmDbgBreakOnStatus((unsigned int)v8);
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a4, v8);
      }
      v9 = FileObject;
      goto LABEL_22;
    }
    v9 = FileObject;
  }
  StreamContext = HsmpGetStreamContext(0, *v6, v9);
  v11 = StreamContext;
  if ( StreamContext )
  {
    StreamContext[7] |= 0x20000u;
    *((_QWORD *)StreamContext + 19) = KeGetCurrentThread();
    v8 = FltFsControlFile(*v6, v9, 0x9C040u, &InputBuffer, 2u, 0, 0, 0);
    HsmDbgBreakOnStatus((unsigned int)v8);
    if ( v8 >= 0 )
    {
      v11[7] &= ~0x20000u;
      *((_QWORD *)v11 + 19) = 0;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        a1,
        a4,
        v11,
        v8);
    }
    FltReleaseContext(v11);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a4);
  }
LABEL_22:
  if ( v9 && v9 != a2 )
    ObfDereferenceObject(v9);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140043234  mov     r11, rsp
0x140043237  mov     [r11+8], rbx
0x14004323b  mov     [r11+20h], rbp
0x14004323f  mov     [r11+18h], r8w
0x140043244  push    rsi
0x140043245  push    rdi
0x140043246  push    r12
0x140043248  push    r14
0x14004324a  push    r15
0x14004324c  sub     rsp, 60h
0x140043250  mov     qword ptr [r11-38h], 0
0x140043258  mov     r15, r9
0x14004325b  mov     qword ptr [r11+10h], 0
0x140043263  mov     r12, rdx
0x140043266  lea     r14, [rcx+20h]
0x14004326a  mov     rbp, rcx
0x14004326d  test    rdx, rdx
0x140043270  jnz     loc_140043305
0x140043276  mov     rdx, [r14]
0x140043279  lea     rax, [r11+10h]
0x14004327d  mov     [r11-48h], rax
0x140043281  mov     r9d, 100180h
0x140043287  lea     rax, [r11-38h]
0x14004328b  mov     r8, r15
0x14004328e  mov     [r11-50h], rax
0x140043292  mov     byte ptr [rsp+88h+OutputBufferLength], 1
0x140043297  mov     dword ptr [rsp+88h+OutputBuffer], 200060h
0x14004329f  call    HsmpOpenFileByIdEx
0x1400432a4  mov     ecx, eax
0x1400432a6  mov     esi, eax
0x1400432a8  call    HsmDbgBreakOnStatus
0x1400432ad  test    esi, esi
0x1400432af  jns     short loc_1400432FB
0x1400432b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400432b8  lea     rax, WPP_GLOBAL_Control
0x1400432bf  cmp     rcx, rax
0x1400432c2  jz      short loc_1400432EE
0x1400432c4  mov     edx, [rcx+2Ch]
0x1400432c7  test    dl, 10h
0x1400432ca  jz      short loc_1400432EE
0x1400432cc  cmp     byte ptr [rcx+29h], 2
0x1400432d0  jb      short loc_1400432EE
0x1400432d2  mov     rcx, [rcx+18h]
0x1400432d6  lea     edx, [r12+18h]
0x1400432db  mov     r9, r15
0x1400432de  mov     [rsp+88h+InputBufferLength], esi
0x1400432e2  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x1400432e9  call    WPP_SF_qd
0x1400432ee  mov     rbx, [rsp+88h+FileObject]
0x1400432f6  jmp     loc_14004343A
0x1400432fb  mov     rbx, [rsp+88h+FileObject]
0x140043303  jmp     short loc_14004330A
0x140043305  xor     esi, esi
0x140043307  mov     rbx, r12
0x14004330a  mov     rdx, [r14]; Instance
0x14004330d  mov     r8, rbx; FileObject
0x140043310  xor     ecx, ecx; CallbackData
0x140043312  call    HsmpGetStreamContext
0x140043317  mov     rdi, rax
0x14004331a  test    rax, rax
0x14004331d  jnz     short loc_14004336F
0x14004331f  mov     rcx, cs:WPP_GLOBAL_Control
0x140043326  lea     rax, WPP_GLOBAL_Control
0x14004332d  cmp     rcx, rax
0x140043330  jz      loc_14004343A
0x140043336  mov     eax, [rcx+2Ch]
0x140043339  test    al, 10h
0x14004333b  jz      loc_14004343A
0x140043341  cmp     byte ptr [rcx+29h], 2
0x140043345  jb      loc_14004343A
0x14004334b  mov     rcx, [rcx+18h]
0x14004334f  lea     edx, [rdi+19h]
0x140043352  mov     dword ptr [rsp+88h+OutputBuffer], esi
0x140043356  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004335d  mov     r9, rbp
0x140043360  mov     qword ptr [rsp+88h+InputBufferLength], r15
0x140043365  call    WPP_SF_qqd
0x14004336a  jmp     loc_14004343A
0x14004336f  bts     dword ptr [rax+1Ch], 11h
0x140043374  lea     r9, [rsp+88h+InputBuffer]; InputBuffer
0x14004337c  mov     rax, gs:188h
0x140043385  mov     r8d, 9C040h; FsControlCode
0x14004338b  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x140043394  mov     rdx, rbx; FileObject
0x140043397  mov     [rdi+98h], rax
0x14004339e  mov     rcx, [r14]; Instance
0x1400433a1  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x1400433a9  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x1400433b2  mov     [rsp+88h+InputBufferLength], 2; InputBufferLength
0x1400433ba  call    cs:__imp_FltFsControlFile
0x1400433c1  nop     dword ptr [rax+rax+00h]
0x1400433c6  mov     ecx, eax
0x1400433c8  mov     esi, eax
0x1400433ca  call    HsmDbgBreakOnStatus
0x1400433cf  test    esi, esi
0x1400433d1  jns     short loc_14004341B
0x1400433d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400433da  lea     rax, WPP_GLOBAL_Control
0x1400433e1  cmp     rcx, rax
0x1400433e4  jz      short loc_14004342B
0x1400433e6  mov     eax, [rcx+2Ch]
0x1400433e9  test    al, 10h
0x1400433eb  jz      short loc_14004342B
0x1400433ed  cmp     byte ptr [rcx+29h], 2
0x1400433f1  jb      short loc_14004342B
0x1400433f3  mov     rcx, [rcx+18h]
0x1400433f7  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x1400433fe  mov     [rsp+88h+OutputBufferLength], esi
0x140043402  mov     edx, 1Ah
0x140043407  mov     [rsp+88h+OutputBuffer], rdi
0x14004340c  mov     r9, rbp
0x14004340f  mov     qword ptr [rsp+88h+InputBufferLength], r15
0x140043414  call    WPP_SF_qqqd
0x140043419  jmp     short loc_14004342B
0x14004341b  btr     dword ptr [rdi+1Ch], 11h
0x140043420  mov     qword ptr [rdi+98h], 0
0x14004342b  mov     rcx, rdi; Context
0x14004342e  call    cs:__imp_FltReleaseContext
0x140043435  nop     dword ptr [rax+rax+00h]
0x14004343a  test    rbx, rbx
0x14004343d  jz      short loc_140043453
0x14004343f  cmp     rbx, r12
0x140043442  jz      short loc_140043453
0x140043444  mov     rcx, rbx; Object
0x140043447  call    cs:__imp_ObfDereferenceObject
0x14004344e  nop     dword ptr [rax+rax+00h]
0x140043453  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140043458  test    rcx, rcx
0x14004345b  jz      short loc_140043469
0x14004345d  call    cs:__imp_FltClose
0x140043464  nop     dword ptr [rax+rax+00h]
0x140043469  lea     r11, [rsp+88h+var_28]
0x14004346e  mov     eax, esi
0x140043470  mov     rbx, [r11+30h]
0x140043474  mov     rbp, [r11+48h]
0x140043478  mov     rsp, r11
0x14004347b  pop     r15
0x14004347d  pop     r14
0x14004347f  pop     r12
0x140043481  pop     rdi
0x140043482  pop     rsi
0x140043483  retn
```
