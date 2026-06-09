# DirectComposition::CSharedSection::Create(DirectComposition::CDevice *,bool,unsigned __int64,DirectComposition::CSharedSection * *)

- ea: `0x180083cbc`
- end: `0x180083eee`
- name: `?Create@CSharedSection@DirectComposition@@SAJPEAVCDevice@2@_N_KPEAPEAV12@@Z`
- size: `562`
- prototype: `__int64 __fastcall(struct DirectComposition::CDevice *this, bool, unsigned __int64, struct DirectComposition::CSharedSection **)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002fffc`

## callees

- `0x18001358c`
- `0x180016578`
- `0x180017128`
- `0x1800189dc`
- `0x18001a494`
- `0x180083c84`
- `0x180083cbc`
- `0x180083ef4`
- `0x1800df108`
- `0x1800f6f10`
- `0x1800f7a80`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180083d6e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180083d6e`
- `ntdll!RtlCreateHeap` at `0x180083dcd`
- `ntdll!RtlCreateHeap` at `0x180083dcd`

## string_xrefs

- `0x180083e6c`: `onecoreuap\windows\dwm\dcomp\sharedsection.cpp`
- `0x180083e93`: `onecoreuap\windows\dwm\dcomp\sharedsection.cpp`
- `0x180083ec2`: `onecoreuap\windows\dwm\dcomp\sharedsection.cpp`

## pseudocode

```c
__int64 __fastcall DirectComposition::CSharedSection::Create(
        struct DirectComposition::CDevice *this,
        char a2,
        SIZE_T a3,
        struct DirectComposition::CSharedSection **a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // r15d
  int v10; // eax
  LPVOID v11; // rax
  HANDLE v12; // rbx
  void *v13; // rsi
  PVOID v14; // r12
  _QWORD *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r9
  HANDLE v18; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int dwNumberOfBytesToMap; // [rsp+20h] [rbp-69h]
  int dwNumberOfBytesToMapa; // [rsp+20h] [rbp-69h]
  unsigned int v25; // [rsp+34h] [rbp-55h] BYREF
  HANDLE hFileMappingObject; // [rsp+38h] [rbp-51h] BYREF
  struct _RTL_HEAP_PARAMETERS Parameters; // [rsp+40h] [rbp-49h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v25 = 0;
  hFileMappingObject = 0;
  v7 = DirectComposition::CDevice::ChannelCreateResource(this, 0x85u, 0, &v25);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\sharedsection.cpp",
      (const char *)(unsigned int)v7,
      dwNumberOfBytesToMap);
    return v8;
  }
  v9 = v25;
  v10 = DirectComposition::CDevice::TryFlushKernelCommands(this, 0);
  v8 = v10;
  if ( v10 < 0 )
  {
    v20 = 59;
    goto LABEL_12;
  }
  v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, SIZE_T, HANDLE *))(**((_QWORD **)this + 21) + 104LL))(
          *((_QWORD *)this + 21),
          v9,
          a3,
          &hFileMappingObject);
  v8 = v10;
  if ( v10 < 0 )
  {
    v20 = 63;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\sharedsection.cpp",
      (const char *)(unsigned int)v10,
      dwNumberOfBytesToMap);
LABEL_13:
    DirectComposition::CDevice::ChannelReleaseResource(this, v9);
    return v8;
  }
  v11 = MapViewOfFile(hFileMappingObject, 6u, 0, 0, a3);
  v12 = hFileMappingObject;
  v13 = v11;
  if ( !v11 )
  {
    v21 = 75;
    goto LABEL_16;
  }
  v14 = 0;
  if ( a2 )
  {
    memset_0(&Parameters, 0, sizeof(Parameters));
    Parameters.Length = 96;
    Parameters.InitialCommit = a3;
    Parameters.InitialReserve = a3;
    v14 = RtlCreateHeap(1u, v13, a3, a3, 0, &Parameters);
    if ( !v14 )
    {
      v21 = 94;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\sharedsection.cpp",
        (const char *)0x8007000ELL,
        dwNumberOfBytesToMapa);
      DirectComposition::CSharedSection::UnmapSharedMemory(v12, (unsigned __int8 *)v13);
      v8 = -2147024882;
      goto LABEL_13;
    }
  }
  v15 = DefaultHeap::AllocClear(0x58u);
  if ( !v15 )
    ModuleFailFastForHRESULT(2147942414LL, retaddr, v16, v17);
  v18 = hFileMappingObject;
  *v15 = &DirectComposition::CSharedSection::`vftable';
  v15[8] = v18;
  v15[3] = this;
  *((_DWORD *)v15 + 12) = v9;
  v15[7] = v13;
  v15[9] = v14;
  v15[10] = a3;
  if ( (Microsoft_Windows_DirectCompositionEnableBits & 0x20) != 0 )
    McTemplateU0xq_EventWriteTransfer(
      &DirectComposition::CSharedSection::`vftable',
      DCOMPEVENT_CREATE_SHARED_MEMORY_SECTION,
      v15,
      (unsigned int)a3);
  *a4 = (struct DirectComposition::CSharedSection *)v15;
  return 0;
}

```

## disassembly

```asm
0x180083cbc  mov     [rsp-8+arg_8], rbx
0x180083cc1  push    rbp
0x180083cc2  push    rsi
0x180083cc3  push    rdi
0x180083cc4  push    r12
0x180083cc6  push    r13
0x180083cc8  push    r14
0x180083cca  push    r15
0x180083ccc  lea     rbp, [rsp-27h]
0x180083cd1  sub     rsp, 0B0h
0x180083cd8  mov     rax, cs:__security_cookie
0x180083cdf  xor     rax, rsp
0x180083ce2  mov     [rbp+57h+var_40], rax
0x180083ce6  mov     r13, r9
0x180083ce9  mov     [rbp+57h+var_B0], dl
0x180083cec  mov     rdi, r8
0x180083cef  mov     [rbp+57h+var_AC], 0
0x180083cf6  lea     r9, [rbp+57h+var_AC]; unsigned int *
0x180083cfa  mov     [rbp+57h+hFileMappingObject], 0
0x180083d02  xor     r8d, r8d; bool
0x180083d05  mov     edx, 85h; unsigned int
0x180083d0a  mov     r14, rcx
0x180083d0d  call    ?ChannelCreateResource@CDevice@DirectComposition@@QEAAJI_NPEAI@Z; DirectComposition::CDevice::ChannelCreateResource(uint,bool,uint *)
0x180083d12  mov     ebx, eax
0x180083d14  test    eax, eax
0x180083d16  js      loc_180083EBE
0x180083d1c  mov     r15d, [rbp+57h+var_AC]
0x180083d20  xor     edx, edx; bool
0x180083d22  mov     rcx, r14; this
0x180083d25  call    ?TryFlushKernelCommands@CDevice@DirectComposition@@AEAAJ_N@Z; DirectComposition::CDevice::TryFlushKernelCommands(bool)
0x180083d2a  mov     ebx, eax
0x180083d2c  test    eax, eax
0x180083d2e  js      loc_180083EB7
0x180083d34  mov     rcx, [r14+0A8h]
0x180083d3b  lea     r9, [rbp+57h+hFileMappingObject]
0x180083d3f  mov     r8, rdi
0x180083d42  mov     edx, r15d
0x180083d45  mov     rax, [rcx]
0x180083d48  mov     rax, [rax+68h]
0x180083d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083d51  mov     ebx, eax
0x180083d53  test    eax, eax
0x180083d55  js      loc_180083E63
0x180083d5b  mov     rcx, [rbp+57h+hFileMappingObject]; hFileMappingObject
0x180083d5f  xor     r9d, r9d; dwFileOffsetLow
0x180083d62  xor     r8d, r8d; dwFileOffsetHigh
0x180083d65  mov     [rsp+0E0h+dwNumberOfBytesToMap], rdi; dwNumberOfBytesToMap
0x180083d6a  lea     edx, [r9+6]; dwDesiredAccess
0x180083d6e  call    cs:__imp_MapViewOfFile
0x180083d74  mov     rbx, [rbp+57h+hFileMappingObject]
0x180083d78  mov     rsi, rax
0x180083d7b  test    rax, rax
0x180083d7e  jz      loc_180083ED8
0x180083d84  xor     r12d, r12d
0x180083d87  cmp     [rbp+57h+var_B0], r12b
0x180083d8b  jz      short loc_180083DDF
0x180083d8d  mov     r12d, 60h ; '`'
0x180083d93  lea     rcx, [rbp+57h+var_A0]; void *
0x180083d97  mov     r8d, r12d; Size
0x180083d9a  xor     edx, edx; Val
0x180083d9c  call    memset_0
0x180083da1  lea     rax, [rbp+57h+var_A0]
0x180083da5  mov     [rbp+57h+var_A0.Length], r12d
0x180083da9  mov     [rsp+0E0h+Parameters], rax; Parameters
0x180083dae  lea     ecx, [r12-5Fh]; Flags
0x180083db3  mov     r9, rdi; SizeToCommit
0x180083db6  mov     [rsp+0E0h+dwNumberOfBytesToMap], 0; int
0x180083dbf  mov     r8, rdi; SizeToReserve
0x180083dc2  mov     [rbp+57h+var_A0.InitialCommit], rdi
0x180083dc6  mov     rdx, rsi; BaseAddress
0x180083dc9  mov     [rbp+57h+var_A0.InitialReserve], rdi
0x180083dcd  call    cs:__imp_RtlCreateHeap
0x180083dd3  mov     r12, rax
0x180083dd6  test    rax, rax
0x180083dd9  jz      loc_180083E8A
0x180083ddf  mov     ecx, 58h ; 'X'; unsigned __int64
0x180083de4  call    ?AllocClear@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::AllocClear(unsigned __int64)
0x180083de9  mov     rbx, rax
0x180083dec  test    rax, rax
0x180083def  jz      loc_180083EDF
0x180083df5  mov     rax, [rbp+57h+hFileMappingObject]
0x180083df9  lea     rcx, ??_7CSharedSection@DirectComposition@@6B@; const DirectComposition::CSharedSection::`vftable'
0x180083e00  mov     [rbx], rcx
0x180083e03  mov     [rbx+40h], rax
0x180083e07  mov     [rbx+18h], r14
0x180083e0b  mov     [rbx+30h], r15d
0x180083e0f  mov     [rbx+38h], rsi
0x180083e13  mov     [rbx+48h], r12
0x180083e17  mov     [rbx+50h], rdi
0x180083e1b  test    byte ptr cs:Microsoft_Windows_DirectCompositionEnableBits, 20h
0x180083e22  jz      short loc_180083E36
0x180083e24  mov     r9d, edi
0x180083e27  lea     rdx, DCOMPEVENT_CREATE_SHARED_MEMORY_SECTION
0x180083e2e  mov     r8, rbx
0x180083e31  call    McTemplateU0xq_EventWriteTransfer
0x180083e36  mov     [r13+0], rbx
0x180083e3a  xor     eax, eax
0x180083e3c  mov     rcx, [rbp+57h+var_40]
0x180083e40  xor     rcx, rsp; StackCookie
0x180083e43  call    __security_check_cookie
0x180083e48  mov     rbx, [rsp+0E0h+arg_8]
0x180083e50  add     rsp, 0B0h
0x180083e57  pop     r15
0x180083e59  pop     r14
0x180083e5b  pop     r13
0x180083e5d  pop     r12
0x180083e5f  pop     rdi
0x180083e60  pop     rsi
0x180083e61  pop     rbp
0x180083e62  retn
0x180083e63  mov     edx, 3Fh ; '?'; void *
0x180083e68  mov     rcx, [rbp+5Fh]; this
0x180083e6c  lea     r8, aOnecoreuapWind_253; "onecoreuap\\windows\\dwm\\dcomp\\shared"...
0x180083e73  mov     r9d, eax; char *
0x180083e76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083e7b  mov     edx, r15d; unsigned int
0x180083e7e  mov     rcx, r14; this
0x180083e81  call    ?ChannelReleaseResource@CDevice@DirectComposition@@QEAAXI@Z; DirectComposition::CDevice::ChannelReleaseResource(uint)
0x180083e86  mov     eax, ebx
0x180083e88  jmp     short loc_180083E3C
0x180083e8a  mov     edx, 5Eh ; '^'; void *
0x180083e8f  mov     rcx, [rbp+5Fh]; this
0x180083e93  lea     r8, aOnecoreuapWind_253; "onecoreuap\\windows\\dwm\\dcomp\\shared"...
0x180083e9a  mov     r9d, 8007000Eh; char *
0x180083ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ea5  mov     rdx, rsi; unsigned __int8 *
0x180083ea8  mov     rcx, rbx; void *
0x180083eab  call    ?UnmapSharedMemory@CSharedSection@DirectComposition@@CAXPEAXPEAE@Z; DirectComposition::CSharedSection::UnmapSharedMemory(void *,uchar *)
0x180083eb0  mov     ebx, 8007000Eh
0x180083eb5  jmp     short loc_180083E7B
0x180083eb7  mov     edx, 3Bh ; ';'
0x180083ebc  jmp     short loc_180083E68
0x180083ebe  mov     rcx, [rbp+5Fh]; this
0x180083ec2  lea     r8, aOnecoreuapWind_253; "onecoreuap\\windows\\dwm\\dcomp\\shared"...
0x180083ec9  mov     r9d, ebx; char *
0x180083ecc  mov     edx, 33h ; '3'; void *
0x180083ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083ed6  jmp     short loc_180083E86
0x180083ed8  mov     edx, 4Bh ; 'K'
0x180083edd  jmp     short loc_180083E8F
0x180083edf  mov     rdx, [rbp+5Fh]
0x180083ee3  mov     ecx, 8007000Eh
0x180083ee8  call    ModuleFailFastForHRESULT
```
