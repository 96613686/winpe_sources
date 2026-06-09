# RxPurgeFcbInSystemCache

- ea: `0x140071c90`
- end: `0x140071ecd`
- name: `RxPurgeFcbInSystemCache`
- size: `573`
- prototype: `NTSTATUS __stdcall(PFCB Fcb, PLARGE_INTEGER FileOffset, ULONG Length, BOOLEAN UninitializeCacheMaps, BOOLEAN FlushFile)`
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x1400080b0`
- `0x140012030`
- `0x140044c78`
- `0x14005b620`
- `0x14006c5c0`

## callees

- `0x140008030`
- `0x140008190`
- `0x140015230`
- `0x140016e70`
- `0x140017280`
- `0x140017370`
- `0x140017420`
- `0x1400241d8`
- `0x1400242c0`
- `0x140071c90`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140071d74`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140071de6`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140071d74`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x140071de6`
- `ntoskrnl!RtlGetCallersAddress` at `0x14007f766`
- `ntoskrnl!RtlGetCallersAddress` at `0x14007f766`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall RxPurgeFcbInSystemCache(
        PFCB Fcb,
        PLARGE_INTEGER FileOffset,
        ULONG Length,
        BOOLEAN UninitializeCacheMaps,
        BOOLEAN FlushFile)
{
  ULONG v6; // ebp
  NTSTATUS v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // r8
  LONGLONG QuadPart; // rax
  NTSTATUS v16; // r8d
  NTSTATUS v17; // r9d
  UCHAR Context; // [rsp+20h] [rbp-98h]
  void *v19; // [rsp+28h] [rbp-90h]
  PVOID CallersCaller; // [rsp+40h] [rbp-78h] BYREF
  PVOID CallersAddress; // [rsp+48h] [rbp-70h] BYREF
  __int128 v22; // [rsp+50h] [rbp-68h] BYREF
  __int128 v23; // [rsp+60h] [rbp-58h]
  __int64 v24; // [rsp+70h] [rbp-48h]
  __int128 Parameter; // [rsp+78h] [rbp-40h] BYREF
  PUNICODE_STRING FileName[2]; // [rsp+88h] [rbp-30h]
  __int64 v27; // [rsp+98h] [rbp-20h]

  v6 = Length;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  if ( !FlushFile )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids);
  }
  Parameter = 0;
  v27 = 0;
  *(_OWORD *)FileName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids, Fcb);
  }
  LOBYTE(Length) = 1;
  RxAcquirePagingIoResource(0, Fcb, *(_QWORD *)&Length);
  Parameter = (unsigned __int64)Fcb;
  LODWORD(FileName[0]) = 0;
  KeExpandKernelStackAndCalloutEx(
    (PEXPAND_STACK_CALLOUT)RxpFlushFcbInSystemCacheCallout,
    &Parameter,
    0x6000u,
    0,
    *(PVOID *)&RxContextLookasideList.L.Depth);
  v9 = (NTSTATUS)FileName[1];
  RxReleasePagingIoResource(0, Fcb);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    LODWORD(v19) = 0;
    Context = (unsigned __int8)Fcb;
    WPP_SF_LqDi(WPP_GLOBAL_Control->AttachedDevice, v10, v11, (unsigned int)v9);
  }
  if ( v9 < 0 )
  {
    CallersAddress = 0;
    CallersCaller = 0;
    RtlGetCallersAddress(&CallersAddress, &CallersCaller);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        Context = v9;
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 26, &WPP_34a45793cf6d31669b6348460c85d061_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          27,
          &WPP_34a45793cf6d31669b6348460c85d061_Traceguids,
          CallersAddress,
          CallersCaller);
      }
    }
    RxCcLogError((PDEVICE_OBJECT)Fcb, (PUNICODE_STRING)(unsigned int)v9, v16, v17, Context, v19);
  }
  else
  {
LABEL_9:
    *(_QWORD *)&v22 = Fcb;
    *((_QWORD *)&v22 + 1) = FileOffset;
    LODWORD(v23) = v6;
    BYTE4(v23) = UninitializeCacheMaps;
    KeExpandKernelStackAndCalloutEx(
      (PEXPAND_STACK_CALLOUT)RxpPurgeFcbInSystemCacheCallout,
      &v22,
      0x6000u,
      0,
      (PVOID)RxContextLookasideList.L.ListHead.Region);
    v9 = DWORD2(v23);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    if ( FileOffset )
      QuadPart = FileOffset->QuadPart;
    else
      QuadPart = 0;
    WPP_SF_qDiD(WPP_GLOBAL_Control->AttachedDevice, v12, v13, Fcb, v6, QuadPart, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140071c90  mov     r11, rsp
0x140071c93  mov     [r11+18h], rbx
0x140071c97  push    rbp
0x140071c98  push    rdi
0x140071c99  push    r14
0x140071c9b  sub     rsp, 0A0h
0x140071ca2  xorps   xmm0, xmm0
0x140071ca5  mov     [r11+8], rsi
0x140071ca9  xor     eax, eax
0x140071cab  mov     [r11+10h], r15
0x140071caf  lea     r15, WPP_GLOBAL_Control
0x140071cb6  movzx   esi, r9b
0x140071cba  mov     ebp, r8d
0x140071cbd  mov     r14, rdx
0x140071cc0  mov     rdi, rcx
0x140071cc3  movups  [rsp+0B8h+var_68], xmm0
0x140071cc8  movups  [rsp+0B8h+var_58], xmm0
0x140071ccd  mov     [r11-48h], rax
0x140071cd1  cmp     [rsp+0B8h+FlushFile], al
0x140071cd8  jz      loc_140071DB2
0x140071cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140071ce5  cmp     rcx, r15
0x140071ce8  jz      short loc_140071CF7
0x140071cea  test    dword ptr [rcx+2Ch], 200h
0x140071cf1  jnz     loc_140071E36
0x140071cf7  xorps   xmm0, xmm0
0x140071cfa  xor     eax, eax
0x140071cfc  movups  [rsp+0B8h+Parameter], xmm0
0x140071d01  mov     [rsp+0B8h+var_20], rax
0x140071d09  movups  xmmword ptr [rsp+0B8h+FileName], xmm0
0x140071d11  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d18  cmp     rcx, r15
0x140071d1b  jz      short loc_140071D2A
0x140071d1d  test    dword ptr [rcx+2Ch], 200h
0x140071d24  jnz     loc_140071E5A
0x140071d2a  mov     r8b, 1
0x140071d2d  mov     rdx, rdi
0x140071d30  xor     ecx, ecx
0x140071d32  call    RxAcquirePagingIoResource
0x140071d37  mov     rax, qword ptr cs:RxContextLookasideList.L.Depth
0x140071d3e  lea     rdx, [rsp+0B8h+Parameter]; Parameter
0x140071d43  xor     r9d, r9d; Wait
0x140071d46  mov     [rsp+0B8h+Context], rax; Context
0x140071d4b  mov     r8d, 6000h; Size
0x140071d51  mov     qword ptr [rsp+0B8h+Parameter], rdi
0x140071d56  lea     rcx, RxpFlushFcbInSystemCacheCallout; Callout
0x140071d5d  mov     qword ptr [rsp+0B8h+Parameter+8], 0
0x140071d69  mov     dword ptr [rsp+0B8h+FileName], 0
0x140071d74  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140071d7b  nop     dword ptr [rax+rax+00h]
0x140071d80  mov     ebx, dword ptr [rsp+0B8h+FileName+8]
0x140071d87  mov     rdx, rdi
0x140071d8a  xor     ecx, ecx
0x140071d8c  call    RxReleasePagingIoResource
0x140071d91  mov     rcx, cs:WPP_GLOBAL_Control
0x140071d98  cmp     rcx, r15
0x140071d9b  jz      short loc_140071DAA
0x140071d9d  test    dword ptr [rcx+2Ch], 200h
0x140071da4  jnz     loc_140071E81
0x140071daa  test    ebx, ebx
0x140071dac  js      loc_14007F74A
0x140071db2  mov     rax, qword ptr cs:RxContextLookasideList.L+8
0x140071db9  lea     rdx, [rsp+0B8h+var_68]; Parameter
0x140071dbe  xor     r9d, r9d; Wait
0x140071dc1  mov     [rsp+0B8h+Context], rax; Context
0x140071dc6  mov     r8d, 6000h; Size
0x140071dcc  mov     qword ptr [rsp+0B8h+var_68], rdi
0x140071dd1  lea     rcx, RxpPurgeFcbInSystemCacheCallout; Callout
0x140071dd8  mov     qword ptr [rsp+0B8h+var_68+8], r14
0x140071ddd  mov     dword ptr [rsp+0B8h+var_58], ebp
0x140071de1  mov     byte ptr [rsp+0B8h+var_58+4], sil
0x140071de6  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x140071ded  nop     dword ptr [rax+rax+00h]
0x140071df2  mov     ebx, dword ptr [rsp+0B8h+var_58+8]
0x140071df6  mov     rcx, cs:WPP_GLOBAL_Control
0x140071dfd  mov     rsi, [rsp+0B8h+arg_0]
0x140071e05  cmp     rcx, r15
0x140071e08  mov     r15, [rsp+0B8h+arg_8]
0x140071e10  jz      short loc_140071E1F
0x140071e12  test    dword ptr [rcx+2Ch], 200h
0x140071e19  jnz     loc_140071EB2
0x140071e1f  mov     eax, ebx
0x140071e21  mov     rbx, [rsp+0B8h+arg_10]
0x140071e29  add     rsp, 0A0h
0x140071e30  pop     r14
0x140071e32  pop     rdi
0x140071e33  pop     rbp
0x140071e34  retn
0x140071e36  cmp     byte ptr [rcx+29h], 2
0x140071e3a  jb      loc_140071CF7
0x140071e40  mov     rcx, [rcx+18h]
0x140071e44  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x140071e4b  mov     edx, 19h
0x140071e50  call    WPP_SF_
0x140071e55  jmp     loc_140071CF7
0x140071e5a  cmp     byte ptr [rcx+29h], 2
0x140071e5e  jb      loc_140071D2A
0x140071e64  mov     rcx, [rcx+18h]
0x140071e68  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x140071e6f  mov     edx, 17h
0x140071e74  mov     r9, rdi
0x140071e77  call    WPP_SF_q
0x140071e7c  jmp     loc_140071D2A
0x140071e81  cmp     byte ptr [rcx+29h], 4
0x140071e85  jb      loc_140071DAA
0x140071e8b  mov     rcx, [rcx+18h]
0x140071e8f  mov     r9d, ebx
0x140071e92  mov     [rsp+0B8h+var_88], 0
0x140071e9b  mov     dword ptr [rsp+0B8h+var_90], 0
0x140071ea3  mov     [rsp+0B8h+Context], rdi
0x140071ea8  call    WPP_SF_LqDi
0x140071ead  jmp     loc_140071DAA
0x140071eb2  cmp     byte ptr [rcx+29h], 2
0x140071eb6  jb      loc_140071E1F
0x140071ebc  test    r14, r14
0x140071ebf  jz      loc_14007F7F6
0x140071ec5  mov     rax, [r14]
0x140071ec8  jmp     loc_14007F7F8
0x14007f74a  lea     rdx, [rsp+0B8h+CallersCaller]; CallersCaller
0x14007f74f  mov     [rsp+0B8h+CallersAddress], 0
0x14007f758  lea     rcx, [rsp+0B8h+CallersAddress]; CallersAddress
0x14007f75d  mov     [rsp+0B8h+CallersCaller], 0
0x14007f766  call    cs:__imp_RtlGetCallersAddress
0x14007f76d  nop     dword ptr [rax+rax+00h]
0x14007f772  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f779  cmp     rcx, r15
0x14007f77c  jz      short loc_14007F7E6
0x14007f77e  mov     eax, [rcx+2Ch]
0x14007f781  test    al, 1
0x14007f783  jz      short loc_14007F7A7
0x14007f785  cmp     byte ptr [rcx+29h], 1
0x14007f789  jb      short loc_14007F7A7
0x14007f78b  mov     rcx, [rcx+18h]
0x14007f78f  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x14007f796  mov     edx, 1Ah
0x14007f79b  mov     dword ptr [rsp+0B8h+Context], ebx
0x14007f79f  mov     r9, rdi
0x14007f7a2  call    WPP_SF_qD
0x14007f7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007f7ae  cmp     rcx, r15
0x14007f7b1  jz      short loc_14007F7E6
0x14007f7b3  test    dword ptr [rcx+2Ch], 200h
0x14007f7ba  jz      short loc_14007F7E6
0x14007f7bc  cmp     byte ptr [rcx+29h], 4
0x14007f7c0  jb      short loc_14007F7E6
0x14007f7c2  mov     rax, [rsp+0B8h+CallersCaller]
0x14007f7c7  lea     r8, WPP_34a45793cf6d31669b6348460c85d061_Traceguids
0x14007f7ce  mov     r9, [rsp+0B8h+CallersAddress]
0x14007f7d3  mov     edx, 1Bh
0x14007f7d8  mov     rcx, [rcx+18h]
0x14007f7dc  mov     [rsp+0B8h+Context], rax; IrpMajorCode
0x14007f7e1  call    WPP_SF_qq
0x14007f7e6  mov     edx, ebx; FileName
0x14007f7e8  mov     rcx, rdi; DeviceObject
0x14007f7eb  call    RxCcLogError
0x14007f7f0  nop
0x14007f7f1  jmp     loc_140071DF6
0x14007f7f6  xor     eax, eax
0x14007f7f8  mov     rcx, [rcx+18h]
0x14007f7fc  mov     r9, rdi
0x14007f7ff  mov     dword ptr [rsp+0B8h+var_88], ebx
0x14007f803  mov     [rsp+0B8h+var_90], rax
0x14007f808  mov     dword ptr [rsp+0B8h+Context], ebp
0x14007f80c  call    WPP_SF_qDiD
0x14007f811  nop
0x14007f812  jmp     loc_140071E1F
```
