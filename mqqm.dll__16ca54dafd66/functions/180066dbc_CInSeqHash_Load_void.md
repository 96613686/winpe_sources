# CInSeqHash::Load(void *)

- ea: `0x180066dbc`
- end: `0x180067195`
- name: `?Load@CInSeqHash@@AEAAHPEAX@Z`
- size: `985`
- prototype: `int(CInSeqHash *__hidden this, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800675e0`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f430`
- `0x18000faec`
- `0x18002c61c`
- `0x180064b14`
- `0x1800650ac`
- `0x1800651ec`
- `0x180066dbc`
- `0x18006719c`
- `0x18006753c`
- `0x18009aed4`
- `0x18009bd1c`
- `0x1800d6e32`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180066fa4`
- `msvcrt!free` at `0x18006703e`
- `msvcrt!free` at `0x180066fa4`
- `msvcrt!free` at `0x18006703e`
- `KERNEL32!GetLastError` at `0x180066e19`
- `KERNEL32!GetLastError` at `0x180066ebe`
- `KERNEL32!GetLastError` at `0x180066e19`
- `KERNEL32!GetLastError` at `0x180066ebe`
- `KERNEL32!ReadFile` at `0x180066e0f`
- `KERNEL32!ReadFile` at `0x180066f85`
- `KERNEL32!ReadFile` at `0x180066fc5`
- `KERNEL32!ReadFile` at `0x1800670fd`
- `KERNEL32!ReadFile` at `0x18006712e`
- `KERNEL32!ReadFile` at `0x180066e0f`
- `KERNEL32!ReadFile` at `0x180066f85`
- `KERNEL32!ReadFile` at `0x180066fc5`
- `KERNEL32!ReadFile` at `0x1800670fd`
- `KERNEL32!ReadFile` at `0x18006712e`
- `KERNEL32!SetFilePointer` at `0x180066eaf`
- `KERNEL32!SetFilePointer` at `0x180066eaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CInSeqHash::Load(CInSeqHash *this, void *a2)
{
  signed int LastError; // ebx
  bool v5; // sf
  unsigned __int16 v6; // r8
  unsigned __int16 v7; // ax
  unsigned __int16 v8; // cx
  bool v9; // sf
  unsigned int i; // r14d
  CInSequence *v12; // rax
  CInSequence *v13; // rbx
  __int64 v14; // rax
  _DWORD *v15; // rbx
  DWORD v16; // [rsp+30h] [rbp-49h] BYREF
  DWORD NumberOfBytesRead; // [rsp+34h] [rbp-45h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-41h] BYREF
  void *Block; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-31h] BYREF
  _QWORD Buffer[2]; // [rsp+58h] [rbp-21h] BYREF
  int v22; // [rsp+68h] [rbp-11h]
  __int128 v23; // [rsp+70h] [rbp-9h] BYREF
  __int128 v24; // [rsp+80h] [rbp+7h]
  __int128 v25; // [rsp+90h] [rbp+17h]
  __int64 v26; // [rsp+A0h] [rbp+27h]

  NumberOfBytesRead = 0;
  Buffer[0] = 0;
  Buffer[1] = 0;
  v22 = 0;
  if ( !ReadFile(a2, Buffer, 0x14u, &NumberOfBytesRead, 0) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 57),
        41,
        &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids,
        (unsigned int)LastError);
    v5 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = LastError < 0;
    }
    if ( !v5 )
      return 0;
    v6 = 21;
    goto LABEL_20;
  }
  if ( NumberOfBytesRead >= 0x14 && !memcmp_0(&xmmword_180103898, Buffer, 0x10u) )
  {
    v7 = HIWORD(v22);
    v8 = v22;
  }
  else
  {
    if ( SetFilePointer(a2, 0, 0, 0) == -1 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 468) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 57),
          42,
          &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids,
          (unsigned int)LastError);
      v9 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v9 = LastError < 0;
      }
      if ( !v9 )
        return 0;
      v6 = 22;
LABEL_20:
      LogMsgHR(LastError, (wchar_t *)L"xactin", v6);
      return 0;
    }
    v8 = 0;
    v22 = 0;
    v7 = 0;
  }
  v16 = 0;
  if ( v8 >= 2u && v7 )
  {
    Block = MmAllocate(v7);
    if ( !ReadFile(a2, &Block, HIWORD(v22), &v16, 0) || HIWORD(v22) != v16 )
    {
      free(Block);
      return 0;
    }
    free(Block);
  }
  v18 = 0;
  if ( !ReadFile(a2, &v18, 4u, &v16, 0) || v16 != 4 )
    return 0;
  for ( i = 0; i < v18; ++i )
  {
    v24 = 0;
    v25 = 0;
    v26 = 0;
    v23 = 0;
    LOWORD(v24) = 0;
    if ( !(unsigned int)CKeyInSeq::Load((CKeyInSeq *)&v23, a2) )
      goto LABEL_42;
    v12 = (CInSequence *)MmAllocate(0x210u);
    v20[1] = v12;
    if ( v12 )
      v13 = CInSequence::CInSequence(v12, (const struct CKeyInSeq *)&v23);
    else
      v13 = 0;
    Block = v13;
    if ( !(unsigned int)CInSequence::Load(v13, a2, v22) )
    {
      SafeRelease<CSockTransport>(v13);
LABEL_42:
      CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v23);
      return 0;
    }
    v14 = CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::operator[]((char *)this + 32, &v23);
    R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(v14, &Block);
    if ( !*((_DWORD *)this + 674) )
    {
      v20[0] = 10000LL * (unsigned int)(1000 * *((_DWORD *)this + 672));
      ExSetTimer((CInSeqHash *)((char *)this + 2704), (const struct CTimeDuration *)v20);
      *((_DWORD *)this + 674) = 1;
    }
    SafeRelease<CSockTransport>(v13);
    CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v23);
  }
  if ( !ReadFile(a2, (char *)this + 80, 4u, &v16, 0) )
    return 0;
  if ( v16 != 4 )
    return 0;
  v15 = (_DWORD *)((char *)this + 84);
  if ( !ReadFile(a2, (char *)this + 84, 4u, &v16, 0) || v16 != 4 )
    return 0;
  if ( *((_DWORD *)this + 22) && !*v15 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 42), 43, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids);
    *v15 = 4660;
  }
  return 1;
}

```

## disassembly

```asm
0x180066dbc  mov     [rsp-8+arg_10], rbx
0x180066dc1  push    rbp
0x180066dc2  push    rsi
0x180066dc3  push    rdi
0x180066dc4  push    r14
0x180066dc6  push    r15
0x180066dc8  lea     rbp, [rsp-37h]
0x180066dcd  sub     rsp, 0B0h
0x180066dd4  mov     rax, cs:__security_cookie
0x180066ddb  xor     rax, rsp
0x180066dde  mov     [rbp+57h+var_28], rax
0x180066de2  mov     rdi, rdx
0x180066de5  mov     rsi, rcx
0x180066de8  xor     r15d, r15d
0x180066deb  mov     [rbp+57h+NumberOfBytesRead], r15d
0x180066def  mov     [rbp+57h+Buffer], r15
0x180066df3  mov     [rbp+57h+var_70], r15
0x180066df7  mov     [rbp+57h+var_68], r15d
0x180066dfb  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x180066e00  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180066e04  lea     r8d, [r15+14h]; nNumberOfBytesToRead
0x180066e08  lea     rdx, [rbp+57h+Buffer]; lpBuffer
0x180066e0c  mov     rcx, rdi; hFile
0x180066e0f  call    cs:__imp_ReadFile
0x180066e15  test    eax, eax
0x180066e17  jnz     short loc_180066E77
0x180066e19  call    cs:__imp_GetLastError
0x180066e1f  mov     ebx, eax
0x180066e21  lea     rax, WPP_GLOBAL_Control
0x180066e28  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e2f  cmp     rcx, rax
0x180066e32  jz      short loc_180066E57
0x180066e34  test    byte ptr [rcx+1D4h], 1
0x180066e3b  jz      short loc_180066E57
0x180066e3d  lea     edx, [r15+29h]
0x180066e41  mov     r9d, ebx
0x180066e44  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180066e4b  mov     rcx, [rcx+1C8h]
0x180066e52  call    WPP_SF_d
0x180066e57  test    ebx, ebx
0x180066e59  jle     short loc_180066E66
0x180066e5b  movzx   ebx, bx
0x180066e5e  or      ebx, 80070000h
0x180066e64  test    ebx, ebx
0x180066e66  jns     loc_180066F22
0x180066e6c  mov     r8d, 15h
0x180066e72  jmp     loc_180066F14
0x180066e77  cmp     [rbp+57h+NumberOfBytesRead], 14h
0x180066e7b  jb      short loc_180066EA4
0x180066e7d  mov     r8d, 10h; Size
0x180066e83  lea     rdx, [rbp+57h+Buffer]; Buf2
0x180066e87  lea     rcx, xmmword_180103898; Buf1
0x180066e8e  call    memcmp_0
0x180066e93  test    eax, eax
0x180066e95  jnz     short loc_180066EA4
0x180066e97  movzx   eax, word ptr [rbp+57h+var_68+2]
0x180066e9b  movzx   ecx, word ptr [rbp+57h+var_68]
0x180066e9f  jmp     loc_180066F55
0x180066ea4  xor     r9d, r9d; dwMoveMethod
0x180066ea7  xor     r8d, r8d; lpDistanceToMoveHigh
0x180066eaa  xor     edx, edx; lDistanceToMove
0x180066eac  mov     rcx, rdi; hFile
0x180066eaf  call    cs:__imp_SetFilePointer
0x180066eb5  cmp     eax, 0FFFFFFFFh
0x180066eb8  jnz     loc_180066F47
0x180066ebe  call    cs:__imp_GetLastError
0x180066ec4  mov     ebx, eax
0x180066ec6  lea     rax, WPP_GLOBAL_Control
0x180066ecd  mov     rcx, cs:WPP_GLOBAL_Control
0x180066ed4  cmp     rcx, rax
0x180066ed7  jz      short loc_180066EFD
0x180066ed9  test    byte ptr [rcx+1D4h], 1
0x180066ee0  jz      short loc_180066EFD
0x180066ee2  mov     edx, 2Ah ; '*'
0x180066ee7  mov     r9d, ebx
0x180066eea  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180066ef1  mov     rcx, [rcx+1C8h]
0x180066ef8  call    WPP_SF_d
0x180066efd  test    ebx, ebx
0x180066eff  jle     short loc_180066F0C
0x180066f01  movzx   ebx, bx
0x180066f04  or      ebx, 80070000h
0x180066f0a  test    ebx, ebx
0x180066f0c  jns     short loc_180066F22
0x180066f0e  mov     r8d, 16h; unsigned __int16
0x180066f14  lea     rdx, aXactin; "xactin"
0x180066f1b  mov     ecx, ebx; int
0x180066f1d  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180066f22  xor     eax, eax
0x180066f24  mov     rcx, [rbp+57h+var_28]
0x180066f28  xor     rcx, rsp; StackCookie
0x180066f2b  call    __security_check_cookie
0x180066f30  mov     rbx, [rsp+0D0h+arg_10]
0x180066f38  add     rsp, 0B0h
0x180066f3f  pop     r15
0x180066f41  pop     r14
0x180066f43  pop     rdi
0x180066f44  pop     rsi
0x180066f45  pop     rbp
0x180066f46  retn
0x180066f47  mov     ecx, r15d
0x180066f4a  mov     word ptr [rbp+57h+var_68], cx
0x180066f4e  mov     eax, r15d
0x180066f51  mov     word ptr [rbp+57h+var_68+2], ax
0x180066f55  mov     [rbp+57h+var_A0], r15d
0x180066f59  cmp     cx, 2
0x180066f5d  jb      short loc_180066FAB
0x180066f5f  test    ax, ax
0x180066f62  jz      short loc_180066FAB
0x180066f64  movzx   ecx, ax; unsigned __int64
0x180066f67  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180066f6c  mov     [rbp+57h+Block], rax
0x180066f70  movzx   r8d, word ptr [rbp+57h+var_68+2]; nNumberOfBytesToRead
0x180066f75  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x180066f7a  lea     r9, [rbp+57h+var_A0]; lpNumberOfBytesRead
0x180066f7e  lea     rdx, [rbp+57h+Block]; lpBuffer
0x180066f82  mov     rcx, rdi; hFile
0x180066f85  call    cs:__imp_ReadFile
0x180066f8b  test    eax, eax
0x180066f8d  jz      loc_18006703A
0x180066f93  movzx   eax, word ptr [rbp+57h+var_68+2]
0x180066f97  cmp     eax, [rbp+57h+var_A0]
0x180066f9a  jnz     loc_18006703A
0x180066fa0  mov     rcx, [rbp+57h+Block]; Block
0x180066fa4  call    cs:__imp_free
0x180066faa  nop
0x180066fab  mov     [rbp+57h+var_98], r15d
0x180066faf  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x180066fb4  lea     r9, [rbp+57h+var_A0]; lpNumberOfBytesRead
0x180066fb8  mov     r8d, 4; nNumberOfBytesToRead
0x180066fbe  lea     rdx, [rbp+57h+var_98]; lpBuffer
0x180066fc2  mov     rcx, rdi; hFile
0x180066fc5  call    cs:__imp_ReadFile
0x180066fcb  test    eax, eax
0x180066fcd  jz      loc_180066F22
0x180066fd3  cmp     [rbp+57h+var_A0], 4
0x180066fd7  jnz     loc_180066F22
0x180066fdd  mov     r14d, r15d
0x180066fe0  cmp     r14d, [rbp+57h+var_98]
0x180066fe4  jnb     loc_1800670E7
0x180066fea  xorps   xmm0, xmm0
0x180066fed  movups  [rbp+57h+var_50], xmm0
0x180066ff1  movups  [rbp+57h+var_40], xmm0
0x180066ff5  mov     [rbp+57h+var_30], r15
0x180066ff9  movups  [rbp+57h+var_60], xmm0
0x180066ffd  mov     word ptr [rbp+57h+var_50], r15w
0x180067002  mov     rdx, rdi; void *
0x180067005  lea     rcx, [rbp+57h+var_60]; this
0x180067009  call    ?Load@CKeyInSeq@@QEAAHPEAX@Z; CKeyInSeq::Load(void *)
0x18006700e  test    eax, eax
0x180067010  jz      loc_1800670D9
0x180067016  mov     ecx, 210h; unsigned __int64
0x18006701b  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180067020  mov     [rbp+57h+var_80], rax
0x180067024  test    rax, rax
0x180067027  jz      short loc_18006704A
0x180067029  lea     rdx, [rbp+57h+var_60]; struct CKeyInSeq *
0x18006702d  mov     rcx, rax; this
0x180067030  call    ??0CInSequence@@QEAA@AEBVCKeyInSeq@@@Z; CInSequence::CInSequence(CKeyInSeq const &)
0x180067035  mov     rbx, rax
0x180067038  jmp     short loc_18006704D
0x18006703a  mov     rcx, [rbp+57h+Block]; Block
0x18006703e  call    cs:__imp_free
0x180067044  nop
0x180067045  jmp     loc_180066F22
0x18006704a  mov     rbx, r15
0x18006704d  mov     [rbp+57h+Block], rbx
0x180067051  movzx   r8d, word ptr [rbp+57h+var_68]; unsigned __int16
0x180067056  mov     rdx, rdi; void *
0x180067059  mov     rcx, rbx; this
0x18006705c  call    ?Load@CInSequence@@QEAAHPEAXG@Z; CInSequence::Load(void *,ushort)
0x180067061  test    eax, eax
0x180067063  jz      short loc_1800670D0
0x180067065  lea     rcx, [rsi+20h]
0x180067069  lea     rdx, [rbp+57h+var_60]
0x18006706d  call    ??A?$CMap@VCKeyInSeq@@AEAV1@V?$R@VCInSequence@@@@AEAV2@@@QEAAAEAV?$R@VCInSequence@@@@AEAVCKeyInSeq@@@Z; CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::operator[](CKeyInSeq &)
0x180067072  mov     rcx, rax
0x180067075  lea     rdx, [rbp+57h+Block]
0x180067079  call    ??4?$R@UCTX_OPENREMOTE_HANDLE_TYPE@@@@QEAAAEAV0@AEBV0@@Z; R<CTX_OPENREMOTE_HANDLE_TYPE>::operator=(R<CTX_OPENREMOTE_HANDLE_TYPE> const &)
0x18006707e  cmp     [rsi+0A88h], r15d
0x180067085  jnz     short loc_1800670B6
0x180067087  imul    ecx, [rsi+0A80h], 3E8h
0x180067091  imul    rax, rcx, 2710h
0x180067098  mov     [rbp+57h+var_88], rax
0x18006709c  lea     rcx, [rsi+0A90h]; struct CTimer *
0x1800670a3  lea     rdx, [rbp+57h+var_88]; struct CTimeDuration *
0x1800670a7  call    ?ExSetTimer@@YAXPEAVCTimer@@AEBVCTimeDuration@@@Z; ExSetTimer(CTimer *,CTimeDuration const &)
0x1800670ac  mov     dword ptr [rsi+0A88h], 1
0x1800670b6  mov     rcx, rbx
0x1800670b9  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800670be  nop
0x1800670bf  lea     rcx, [rbp+57h+var_60]; this
0x1800670c3  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x1800670c8  inc     r14d
0x1800670cb  jmp     loc_180066FE0
0x1800670d0  mov     rcx, rbx
0x1800670d3  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x1800670d8  nop
0x1800670d9  lea     rcx, [rbp+57h+var_60]; this
0x1800670dd  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x1800670e2  jmp     loc_180066F22
0x1800670e7  lea     rdx, [rsi+50h]; lpBuffer
0x1800670eb  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x1800670f0  lea     r9, [rbp+57h+var_A0]; lpNumberOfBytesRead
0x1800670f4  mov     r8d, 4; nNumberOfBytesToRead
0x1800670fa  mov     rcx, rdi; hFile
0x1800670fd  call    cs:__imp_ReadFile
0x180067103  test    eax, eax
0x180067105  jz      loc_180066F22
0x18006710b  cmp     [rbp+57h+var_A0], 4
0x18006710f  jnz     loc_180066F22
0x180067115  lea     rbx, [rsi+54h]
0x180067119  mov     [rsp+0D0h+lpOverlapped], r15; lpOverlapped
0x18006711e  lea     r9, [rbp+57h+var_A0]; lpNumberOfBytesRead
0x180067122  mov     r8d, 4; nNumberOfBytesToRead
0x180067128  mov     rdx, rbx; lpBuffer
0x18006712b  mov     rcx, rdi; hFile
0x18006712e  call    cs:__imp_ReadFile
0x180067134  test    eax, eax
0x180067136  jz      loc_180066F22
0x18006713c  cmp     [rbp+57h+var_A0], 4
0x180067140  jnz     loc_180066F22
0x180067146  cmp     [rsi+58h], r15d
0x18006714a  jz      short loc_18006718B
0x18006714c  cmp     [rbx], r15d
0x18006714f  jnz     short loc_18006718B
0x180067151  lea     rax, WPP_GLOBAL_Control
0x180067158  mov     rcx, cs:WPP_GLOBAL_Control
0x18006715f  cmp     rcx, rax
0x180067162  jz      short loc_180067185
0x180067164  test    byte ptr [rcx+15Ch], 1
0x18006716b  jz      short loc_180067185
0x18006716d  mov     edx, 2Bh ; '+'
0x180067172  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180067179  mov     rcx, [rcx+150h]
0x180067180  call    WPP_SF_
0x180067185  mov     dword ptr [rbx], 1234h
0x18006718b  mov     eax, 1
0x180067190  jmp     loc_180066F24
```
