# HsmpSetCompressionNoLock

- ea: `0x140043324`
- end: `0x140043575`
- name: `HsmpSetCompressionNoLock`
- size: `593`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14004357c`
- `0x140047c20`
- `0x14005fde4`
- `0x14007b72c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14000abb8`
- `0x14000c12c`
- `0x140043324`
- `0x140055370`
- `0x14005e76c`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140043537`
- `ntoskrnl!ObfDereferenceObject` at `0x140043537`
- `FLTMGR!FltClose` at `0x14004354d`
- `FLTMGR!FltClose` at `0x14004354d`
- `FLTMGR!FltFsControlFile` at `0x1400434aa`
- `FLTMGR!FltFsControlFile` at `0x1400434aa`
- `FLTMGR!FltReleaseContext` at `0x14004351e`
- `FLTMGR!FltReleaseContext` at `0x14004351e`

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
    HsmDbgBreakOnStatus(v8);
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
    HsmDbgBreakOnStatus(v8);
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
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a4, v8);
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
0x140043324  mov     r11, rsp
0x140043327  mov     [r11+8], rbx
0x14004332b  mov     [r11+20h], rbp
0x14004332f  mov     [r11+18h], r8w
0x140043334  push    rsi
0x140043335  push    rdi
0x140043336  push    r12
0x140043338  push    r14
0x14004333a  push    r15
0x14004333c  sub     rsp, 60h
0x140043340  mov     qword ptr [r11-38h], 0
0x140043348  mov     r15, r9
0x14004334b  mov     qword ptr [r11+10h], 0
0x140043353  mov     r12, rdx
0x140043356  lea     r14, [rcx+20h]
0x14004335a  mov     rbp, rcx
0x14004335d  test    rdx, rdx
0x140043360  jnz     loc_1400433F5
0x140043366  mov     rdx, [r14]
0x140043369  lea     rax, [r11+10h]
0x14004336d  mov     [r11-48h], rax
0x140043371  mov     r9d, 100180h
0x140043377  lea     rax, [r11-38h]
0x14004337b  mov     r8, r15
0x14004337e  mov     [r11-50h], rax
0x140043382  mov     byte ptr [rsp+88h+OutputBufferLength], 1
0x140043387  mov     dword ptr [rsp+88h+OutputBuffer], 200060h
0x14004338f  call    HsmpOpenFileByIdEx
0x140043394  mov     ecx, eax
0x140043396  mov     esi, eax
0x140043398  call    HsmDbgBreakOnStatus
0x14004339d  test    esi, esi
0x14004339f  jns     short loc_1400433EB
0x1400433a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400433a8  lea     rax, WPP_GLOBAL_Control
0x1400433af  cmp     rcx, rax
0x1400433b2  jz      short loc_1400433DE
0x1400433b4  mov     edx, [rcx+2Ch]
0x1400433b7  test    dl, 10h
0x1400433ba  jz      short loc_1400433DE
0x1400433bc  cmp     byte ptr [rcx+29h], 2
0x1400433c0  jb      short loc_1400433DE
0x1400433c2  mov     rcx, [rcx+18h]
0x1400433c6  lea     edx, [r12+18h]
0x1400433cb  mov     r9, r15
0x1400433ce  mov     [rsp+88h+InputBufferLength], esi
0x1400433d2  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x1400433d9  call    WPP_SF_qd
0x1400433de  mov     rbx, [rsp+88h+FileObject]
0x1400433e6  jmp     loc_14004352A
0x1400433eb  mov     rbx, [rsp+88h+FileObject]
0x1400433f3  jmp     short loc_1400433FA
0x1400433f5  xor     esi, esi
0x1400433f7  mov     rbx, r12
0x1400433fa  mov     rdx, [r14]; Instance
0x1400433fd  mov     r8, rbx; FileObject
0x140043400  xor     ecx, ecx; CallbackData
0x140043402  call    HsmpGetStreamContext
0x140043407  mov     rdi, rax
0x14004340a  test    rax, rax
0x14004340d  jnz     short loc_14004345F
0x14004340f  mov     rcx, cs:WPP_GLOBAL_Control
0x140043416  lea     rax, WPP_GLOBAL_Control
0x14004341d  cmp     rcx, rax
0x140043420  jz      loc_14004352A
0x140043426  mov     eax, [rcx+2Ch]
0x140043429  test    al, 10h
0x14004342b  jz      loc_14004352A
0x140043431  cmp     byte ptr [rcx+29h], 2
0x140043435  jb      loc_14004352A
0x14004343b  mov     rcx, [rcx+18h]
0x14004343f  lea     edx, [rdi+19h]
0x140043442  mov     dword ptr [rsp+88h+OutputBuffer], esi
0x140043446  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14004344d  mov     r9, rbp
0x140043450  mov     qword ptr [rsp+88h+InputBufferLength], r15
0x140043455  call    WPP_SF_qqd
0x14004345a  jmp     loc_14004352A
0x14004345f  bts     dword ptr [rax+1Ch], 11h
0x140043464  lea     r9, [rsp+88h+InputBuffer]; InputBuffer
0x14004346c  mov     rax, gs:188h
0x140043475  mov     r8d, 9C040h; FsControlCode
0x14004347b  mov     [rsp+88h+LengthReturned], 0; LengthReturned
0x140043484  mov     rdx, rbx; FileObject
0x140043487  mov     [rdi+98h], rax
0x14004348e  mov     rcx, [r14]; Instance
0x140043491  mov     [rsp+88h+OutputBufferLength], 0; OutputBufferLength
0x140043499  mov     [rsp+88h+OutputBuffer], 0; OutputBuffer
0x1400434a2  mov     [rsp+88h+InputBufferLength], 2; InputBufferLength
0x1400434aa  call    cs:__imp_FltFsControlFile
0x1400434b1  nop     dword ptr [rax+rax+00h]
0x1400434b6  mov     ecx, eax
0x1400434b8  mov     esi, eax
0x1400434ba  call    HsmDbgBreakOnStatus
0x1400434bf  test    esi, esi
0x1400434c1  jns     short loc_14004350B
0x1400434c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400434ca  lea     rax, WPP_GLOBAL_Control
0x1400434d1  cmp     rcx, rax
0x1400434d4  jz      short loc_14004351B
0x1400434d6  mov     eax, [rcx+2Ch]
0x1400434d9  test    al, 10h
0x1400434db  jz      short loc_14004351B
0x1400434dd  cmp     byte ptr [rcx+29h], 2
0x1400434e1  jb      short loc_14004351B
0x1400434e3  mov     rcx, [rcx+18h]
0x1400434e7  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x1400434ee  mov     [rsp+88h+OutputBufferLength], esi
0x1400434f2  mov     edx, 1Ah
0x1400434f7  mov     [rsp+88h+OutputBuffer], rdi
0x1400434fc  mov     r9, rbp
0x1400434ff  mov     qword ptr [rsp+88h+InputBufferLength], r15
0x140043504  call    WPP_SF_qqqd
0x140043509  jmp     short loc_14004351B
0x14004350b  btr     dword ptr [rdi+1Ch], 11h
0x140043510  mov     qword ptr [rdi+98h], 0
0x14004351b  mov     rcx, rdi; Context
0x14004351e  call    cs:__imp_FltReleaseContext
0x140043525  nop     dword ptr [rax+rax+00h]
0x14004352a  test    rbx, rbx
0x14004352d  jz      short loc_140043543
0x14004352f  cmp     rbx, r12
0x140043532  jz      short loc_140043543
0x140043534  mov     rcx, rbx; Object
0x140043537  call    cs:__imp_ObfDereferenceObject
0x14004353e  nop     dword ptr [rax+rax+00h]
0x140043543  mov     rcx, [rsp+88h+FileHandle]; FileHandle
0x140043548  test    rcx, rcx
0x14004354b  jz      short loc_140043559
0x14004354d  call    cs:__imp_FltClose
0x140043554  nop     dword ptr [rax+rax+00h]
0x140043559  lea     r11, [rsp+88h+var_28]
0x14004355e  mov     eax, esi
0x140043560  mov     rbx, [r11+30h]
0x140043564  mov     rbp, [r11+48h]
0x140043568  mov     rsp, r11
0x14004356b  pop     r15
0x14004356d  pop     r14
0x14004356f  pop     r12
0x140043571  pop     rdi
0x140043572  pop     rsi
0x140043573  retn
```
