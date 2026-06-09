# XpsSerializerPibo::~XpsSerializerPibo(void)

- ea: `0x14002b72c`
- end: `0x14002b87e`
- name: `??1XpsSerializerPibo@@UEAA@XZ`
- size: `338`
- prototype: `void __fastcall(XpsSerializerPibo *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14002bf30`

## callees

- `0x14000fa68`
- `0x14000fb28`
- `0x140016660`
- `0x140024710`
- `0x14002b72c`
- `0x140039de4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14002b807`
- `KERNEL32!DeleteCriticalSection` at `0x14002b807`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
void __fastcall XpsSerializerPibo::~XpsSerializerPibo(XpsSerializerPibo *this)
{
  *(_QWORD *)this = &XpsSerializerPibo::`vftable'{for `NCOMLibrary::TUnknown'};
  *((_QWORD *)this + 2) = &XpsSerializerPibo::`vftable'{for `IXpsDocumentConsumer'};
  *((_QWORD *)this + 3) = &XpsSerializerPibo::`vftable'{for `IShutdownComponent'};
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids, this);
  }
  XpsSerializerPibo::ReleaseCloseMusl(this);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 18);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 17);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 15);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 14);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 13);
  PrnExcept::SmartRelease<IPartResourceDictionary>((__int64 *)this + 12);
  PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>((__int64 *)this + 11);
  if ( *((int *)this + 20) >= 0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    *((_DWORD *)this + 20) = -2147467259;
  }
  *(_QWORD *)this = &NCOMLibrary::TUnknown::`vftable';
  _InterlockedDecrement(&NCOMLibrary::TUnknown::g_cOutStandingObjectCount);
}

```

## disassembly

```asm
0x14002b72c  mov     [rsp+arg_10], rbx
0x14002b731  mov     [rsp+arg_0], rcx
0x14002b736  push    rdi
0x14002b737  sub     rsp, 50h
0x14002b73b  mov     rbx, rcx
0x14002b73e  lea     rax, ??_7XpsSerializerPibo@@6BTUnknown@NCOMLibrary@@@; const XpsSerializerPibo::`vftable'{for `NCOMLibrary::TUnknown'}
0x14002b745  mov     [rcx], rax
0x14002b748  lea     rax, ??_7XpsSerializerPibo@@6BIXpsDocumentConsumer@@@; const XpsSerializerPibo::`vftable'{for `IXpsDocumentConsumer'}
0x14002b74f  mov     [rcx+10h], rax
0x14002b753  lea     rax, ??_7XpsSerializerPibo@@6BIShutdownComponent@@@; const XpsSerializerPibo::`vftable'{for `IShutdownComponent'}
0x14002b75a  mov     [rcx+18h], rax
0x14002b75e  lea     rax, WPP_GLOBAL_Control
0x14002b765  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b76c  cmp     rcx, rax
0x14002b76f  jz      short loc_14002B796
0x14002b771  test    byte ptr [rcx+1Ch], 10h
0x14002b775  jz      short loc_14002B796
0x14002b777  cmp     byte ptr [rcx+19h], 3
0x14002b77b  jb      short loc_14002B796
0x14002b77d  mov     edx, 0EAh
0x14002b782  mov     r9, rbx
0x14002b785  lea     r8, WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids
0x14002b78c  mov     rcx, [rcx+10h]
0x14002b790  call    WPP_SF_q
0x14002b795  nop
0x14002b796  mov     rcx, rbx; this
0x14002b799  call    ?ReleaseCloseMusl@XpsSerializerPibo@@AEAAXXZ; XpsSerializerPibo::ReleaseCloseMusl(void)
0x14002b79e  nop
0x14002b79f  jmp     short loc_14002B7B1
0x14002b7a1  cmp     [rsp+58h+arg_8], 0
0x14002b7a6  jl      loc_14002B832
0x14002b7ac  mov     rbx, [rsp+58h+arg_0]
0x14002b7b1  lea     rcx, [rbx+90h]
0x14002b7b8  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7bd  nop
0x14002b7be  lea     rcx, [rbx+88h]
0x14002b7c5  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7ca  nop
0x14002b7cb  lea     rcx, [rbx+78h]
0x14002b7cf  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7d4  nop
0x14002b7d5  lea     rcx, [rbx+70h]
0x14002b7d9  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7de  nop
0x14002b7df  lea     rcx, [rbx+68h]
0x14002b7e3  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7e8  nop
0x14002b7e9  lea     rcx, [rbx+60h]
0x14002b7ed  call    ??$SmartRelease@UIPartResourceDictionary@@@PrnExcept@@YAXPEAPEAUIPartResourceDictionary@@@Z; PrnExcept::SmartRelease<IPartResourceDictionary>(IPartResourceDictionary * *)
0x14002b7f2  nop
0x14002b7f3  lea     rcx, [rbx+58h]
0x14002b7f7  call    ??$SmartRelease@V?$PiboThumbnail@VSpillBufferStream@@@@@PrnExcept@@YAXPEAPEAV?$PiboThumbnail@VSpillBufferStream@@@@@Z; PrnExcept::SmartRelease<PiboThumbnail<SpillBufferStream>>(PiboThumbnail<SpillBufferStream> * *)
0x14002b7fc  nop
0x14002b7fd  cmp     dword ptr [rbx+50h], 0
0x14002b801  jl      short loc_14002B814
0x14002b803  lea     rcx, [rbx+20h]; lpCriticalSection
0x14002b807  call    cs:__imp_DeleteCriticalSection
0x14002b80d  mov     dword ptr [rbx+50h], 80004005h
0x14002b814  lea     rax, ??_7TUnknown@NCOMLibrary@@6B@; const NCOMLibrary::TUnknown::`vftable'
0x14002b81b  mov     [rbx], rax
0x14002b81e  lock dec cs:?g_cOutStandingObjectCount@TUnknown@NCOMLibrary@@0JA; long NCOMLibrary::TUnknown::g_cOutStandingObjectCount
0x14002b825  mov     rbx, [rsp+58h+arg_10]
0x14002b82a  add     rsp, 50h
0x14002b82e  pop     rdi
0x14002b82f  retn
0x14002b830  jmp     short $+2
0x14002b832  lea     rax, WPP_GLOBAL_Control
0x14002b839  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b840  cmp     rcx, rax
0x14002b843  jz      loc_14002B7AC
0x14002b849  test    byte ptr [rcx+1Ch], 10h
0x14002b84d  jz      loc_14002B7AC
0x14002b853  mov     edx, 0EBh
0x14002b858  mov     eax, [rsp+58h+arg_8]
0x14002b85c  mov     [rsp+58h+var_38], eax
0x14002b860  mov     rbx, [rsp+58h+arg_0]
0x14002b865  mov     r9, rbx
0x14002b868  lea     r8, WPP_41d7cebc581d3d4839d2beaa2a2cc904_Traceguids
0x14002b86f  mov     rcx, [rcx+10h]
0x14002b873  call    WPP_SF_qD
0x14002b878  jmp     loc_14002B7B1
```
