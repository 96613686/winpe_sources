# DrParallelPort::CreateLptPort(tagRDPDR_DEVICE_ANNOUNCE *)

- ea: `0x14001e10c`
- end: `0x14001e2ba`
- name: `?CreateLptPort@DrParallelPort@@AEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(CHAR *this, struct tagRDPDR_DEVICE_ANNOUNCE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x14001e2c0`

## callees

- `0x140001e30`
- `0x1400027b0`
- `0x140003188`
- `0x14000324c`
- `0x140006480`
- `0x14001e10c`
- `0x14001e694`

## import_xrefs

- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x14001e16a`
- `ntoskrnl!RtlMultiByteToUnicodeN` at `0x14001e16a`

## pseudocode

```c
__int64 __fastcall DrParallelPort::CreateLptPort(CHAR *this, struct tagRDPDR_DEVICE_ANNOUNCE *a2)
{
  const CHAR *v4; // r9
  __int64 BytesInMultiByteString; // rax
  unsigned int PortAnnounceEvent; // ebx
  wchar_t *v7; // rdi
  ULONG BytesInUnicodeString; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v10; // [rsp+34h] [rbp-34h] BYREF
  __int128 v11; // [rsp+38h] [rbp-30h] BYREF

  BytesInUnicodeString = 0;
  v11 = 0;
  v10 = 0;
  v4 = this + 48;
  BytesInMultiByteString = -1;
  do
    ++BytesInMultiByteString;
  while ( v4[BytesInMultiByteString] );
  if ( RtlMultiByteToUnicodeN((PWCH)&v11, 0x10u, &BytesInUnicodeString, v4, BytesInMultiByteString) < 0
    || BytesInUnicodeString > 0xE )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_46f273b24e1b324fcb1b3a30dfeb1a4d_Traceguids);
    return (unsigned int)-1073741823;
  }
  else
  {
    *((_WORD *)&v11 + ((unsigned __int64)BytesInUnicodeString >> 1)) = 0;
    PortAnnounceEvent = DrPrinterPort::CreatePortAnnounceEvent((DrPrinterPort *)this, a2, 0, 0, &qword_140008DC8, &v10);
    if ( PortAnnounceEvent == -1073741789 )
    {
      v7 = (wchar_t *)operator new(v10, 0x40u);
      if ( v7 )
      {
        PortAnnounceEvent = DrPrinterPort::CreatePortAnnounceEvent(
                              (DrPrinterPort *)this,
                              a2,
                              v7,
                              v10,
                              (const unsigned __int16 *)&v11,
                              0);
        if ( PortAnnounceEvent )
          operator delete(v7);
        else
          return (unsigned int)RDPDYN_DispatchNewDevMgmtEvent(v7, *(_DWORD *)(*((_QWORD *)this + 4) + 1128LL), 4u, 0);
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_46f273b24e1b324fcb1b3a30dfeb1a4d_Traceguids);
        return (unsigned int)-1073741801;
      }
    }
  }
  return PortAnnounceEvent;
}

```

## disassembly

```asm
0x14001e10c  mov     [rsp+arg_10], rbx
0x14001e111  push    rbp
0x14001e112  push    rsi
0x14001e113  push    rdi
0x14001e114  sub     rsp, 50h
0x14001e118  mov     rax, cs:__security_cookie
0x14001e11f  xor     rax, rsp
0x14001e122  mov     [rsp+68h+var_20], rax
0x14001e127  xorps   xmm0, xmm0
0x14001e12a  mov     [rsp+68h+BytesInUnicodeString], 0
0x14001e132  movups  xmmword ptr [rsp+68h+var_34+4], xmm0
0x14001e137  mov     rbp, rdx
0x14001e13a  mov     [rsp+68h+var_34], 0
0x14001e142  mov     rsi, rcx
0x14001e145  lea     r9, [rcx+30h]; MultiByteString
0x14001e149  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001e14d  inc     rax
0x14001e150  cmp     byte ptr [r9+rax], 0
0x14001e155  jnz     short loc_14001E14D
0x14001e157  lea     r8, [rsp+68h+BytesInUnicodeString]; BytesInUnicodeString
0x14001e15c  mov     [rsp+68h+BytesInMultiByteString], eax; BytesInMultiByteString
0x14001e160  mov     edx, 10h; MaxBytesInUnicodeString
0x14001e165  lea     rcx, [rsp+68h+var_34+4]; UnicodeString
0x14001e16a  call    cs:__imp_RtlMultiByteToUnicodeN
0x14001e171  nop     dword ptr [rax+rax+00h]
0x14001e176  test    eax, eax
0x14001e178  js      loc_14001E267
0x14001e17e  cmp     [rsp+68h+BytesInUnicodeString], 0Eh
0x14001e183  ja      loc_14001E267
0x14001e189  mov     ecx, [rsp+68h+BytesInUnicodeString]
0x14001e18d  xor     eax, eax
0x14001e18f  shr     rcx, 1
0x14001e192  xor     r9d, r9d; unsigned int
0x14001e195  xor     r8d, r8d; struct tagRDPDR_PORTDEVICE_SUB *
0x14001e198  mov     rdx, rbp; struct tagRDPDR_DEVICE_ANNOUNCE *
0x14001e19b  mov     word ptr [rsp+rcx*2+68h+var_34+4], ax
0x14001e1a0  lea     rax, [rsp+68h+var_34]
0x14001e1a5  mov     [rsp+68h+var_40], rax; unsigned int *
0x14001e1aa  mov     rcx, rsi; this
0x14001e1ad  lea     rax, qword_140008DC8
0x14001e1b4  mov     qword ptr [rsp+68h+BytesInMultiByteString], rax; unsigned __int16 *
0x14001e1b9  call    ?CreatePortAnnounceEvent@DrPrinterPort@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_PORTDEVICE_SUB@@KPEBGPEAK@Z; DrPrinterPort::CreatePortAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_PORTDEVICE_SUB *,ulong,ushort const *,ulong *)
0x14001e1be  mov     ebx, eax
0x14001e1c0  cmp     eax, 0C0000023h
0x14001e1c5  jnz     loc_14001E29A
0x14001e1cb  mov     ecx, [rsp+68h+var_34]; unsigned __int64
0x14001e1cf  mov     edx, 40h ; '@'; unsigned __int64
0x14001e1d4  call    ??2@YAPEAX_K0@Z; operator new(unsigned __int64,unsigned __int64)
0x14001e1d9  mov     rdi, rax
0x14001e1dc  test    rax, rax
0x14001e1df  jnz     short loc_14001E217
0x14001e1e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e1e8  lea     rax, WPP_GLOBAL_Control
0x14001e1ef  cmp     rcx, rax
0x14001e1f2  jz      short loc_14001E20D
0x14001e1f4  cmp     byte ptr [rcx+29h], 2
0x14001e1f8  jb      short loc_14001E20D
0x14001e1fa  mov     rcx, [rcx+18h]
0x14001e1fe  lea     edx, [rdi+0Bh]
0x14001e201  lea     r8, WPP_46f273b24e1b324fcb1b3a30dfeb1a4d_Traceguids
0x14001e208  call    WPP_SF_
0x14001e20d  mov     ebx, 0C0000017h
0x14001e212  jmp     loc_14001E29A
0x14001e217  mov     r9d, [rsp+68h+var_34]; unsigned int
0x14001e21c  lea     rax, [rsp+68h+var_34+4]
0x14001e221  mov     [rsp+68h+var_40], 0; unsigned int *
0x14001e22a  mov     r8, rdi; struct tagRDPDR_PORTDEVICE_SUB *
0x14001e22d  mov     rdx, rbp; struct tagRDPDR_DEVICE_ANNOUNCE *
0x14001e230  mov     qword ptr [rsp+68h+BytesInMultiByteString], rax; unsigned __int16 *
0x14001e235  mov     rcx, rsi; this
0x14001e238  call    ?CreatePortAnnounceEvent@DrPrinterPort@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_PORTDEVICE_SUB@@KPEBGPEAK@Z; DrPrinterPort::CreatePortAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_PORTDEVICE_SUB *,ulong,ushort const *,ulong *)
0x14001e23d  mov     ebx, eax
0x14001e23f  mov     rcx, rdi; void *
0x14001e242  test    eax, eax
0x14001e244  jz      short loc_14001E24D
0x14001e246  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001e24b  jmp     short loc_14001E29A
0x14001e24d  mov     rdx, [rsi+20h]
0x14001e251  xor     r9d, r9d; struct DrDevice *
0x14001e254  mov     edx, [rdx+468h]; unsigned int
0x14001e25a  lea     r8d, [r9+4]; unsigned int
0x14001e25e  call    RDPDYN_DispatchNewDevMgmtEvent
0x14001e263  mov     ebx, eax
0x14001e265  jmp     short loc_14001E29A
0x14001e267  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e26e  lea     rax, WPP_GLOBAL_Control
0x14001e275  cmp     rcx, rax
0x14001e278  jz      short loc_14001E295
0x14001e27a  cmp     byte ptr [rcx+29h], 2
0x14001e27e  jb      short loc_14001E295
0x14001e280  mov     rcx, [rcx+18h]
0x14001e284  lea     r8, WPP_46f273b24e1b324fcb1b3a30dfeb1a4d_Traceguids
0x14001e28b  mov     edx, 0Ah
0x14001e290  call    WPP_SF_
0x14001e295  mov     ebx, 0C0000001h
0x14001e29a  mov     eax, ebx
0x14001e29c  mov     rcx, [rsp+68h+var_20]
0x14001e2a1  xor     rcx, rsp; StackCookie
0x14001e2a4  call    __security_check_cookie
0x14001e2a9  mov     rbx, [rsp+68h+arg_10]
0x14001e2b1  add     rsp, 50h
0x14001e2b5  pop     rdi
0x14001e2b6  pop     rsi
0x14001e2b7  pop     rbp
0x14001e2b8  retn
```
