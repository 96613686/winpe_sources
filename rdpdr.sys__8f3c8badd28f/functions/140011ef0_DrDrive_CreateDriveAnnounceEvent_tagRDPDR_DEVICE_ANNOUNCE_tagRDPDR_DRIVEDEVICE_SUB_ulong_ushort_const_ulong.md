# DrDrive::CreateDriveAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_DRIVEDEVICE_SUB *,ulong,ushort const *,ulong *)

- ea: `0x140011ef0`
- end: `0x140011ffd`
- name: `?CreateDriveAnnounceEvent@DrDrive@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_DRIVEDEVICE_SUB@@KPEBGPEAK@Z`
- size: `269`
- prototype: `__int64 __fastcall(DrDrive *this, struct tagRDPDR_DEVICE_ANNOUNCE *, wchar_t *, unsigned int, const unsigned __int16 *pszSrc, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140011df0`

## callees

- `0x1400024f0`
- `0x14000324c`
- `0x1400065c0`
- `0x140011ef0`

## pseudocode

```c
__int64 __fastcall DrDrive::CreateDriveAnnounceEvent(
        DrDrive *this,
        struct tagRDPDR_DEVICE_ANNOUNCE *a2,
        wchar_t *a3,
        unsigned int a4,
        const unsigned __int16 *pszSrc,
        unsigned int *a6)
{
  unsigned int v6; // ebx
  unsigned int v10; // ebx
  unsigned int *v11; // r11

  v6 = *((_DWORD *)a2 + 4);
  if ( v6 > 0x294 )
    return 3221225485LL;
  v10 = v6 + 680;
  if ( a4 >= v10 )
  {
    RtlStringCchCopyW(a3, 0xFAu, pszSrc);
    RtlStringCchCopyW(a3 + 250, 0x10u, L"tsclient");
    memmove(a3 + 330, v11, v11[4] + 20LL);
    RtlStringCchCopyW(
      a3 + 266,
      0x40u,
      (NTSTRSAFE_PCWSTR)(*((_QWORD *)this + 4) + 748LL + (*(_WORD *)(*((_QWORD *)this + 4) + 780LL) != 0 ? 0x20 : 0)));
    if ( a6 )
      *a6 = v10;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_83886b54412a34bbe371408c37660ab5_Traceguids);
    return 0;
  }
  else
  {
    if ( a6 )
      *a6 = v10;
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x140011ef0  mov     [rsp+arg_0], rbx
0x140011ef5  mov     [rsp+arg_8], rsi
0x140011efa  push    rdi
0x140011efb  sub     rsp, 20h
0x140011eff  mov     ebx, [rdx+10h]
0x140011f02  mov     rdi, r8
0x140011f05  mov     r11, rdx
0x140011f08  mov     rsi, rcx
0x140011f0b  cmp     ebx, 294h
0x140011f11  jbe     short loc_140011F1D
0x140011f13  mov     eax, 0C000000Dh
0x140011f18  jmp     loc_140011FEC
0x140011f1d  add     ebx, 2A8h
0x140011f23  cmp     r9d, ebx
0x140011f26  jnb     short loc_140011F3E
0x140011f28  mov     rax, [rsp+28h+arg_28]
0x140011f2d  test    rax, rax
0x140011f30  jz      short loc_140011F34
0x140011f32  mov     [rax], ebx
0x140011f34  mov     eax, 0C0000023h
0x140011f39  jmp     loc_140011FEC
0x140011f3e  mov     r8, [rsp+28h+pszSrc]; pszSrc
0x140011f43  mov     edx, 0FAh; cchDest
0x140011f48  mov     rcx, rdi; pszDest
0x140011f4b  call    RtlStringCchCopyW
0x140011f50  lea     rcx, [rdi+1F4h]; pszDest
0x140011f57  mov     edx, 10h; cchDest
0x140011f5c  lea     r8, aTsclient; "tsclient"
0x140011f63  call    RtlStringCchCopyW
0x140011f68  mov     r8d, [r11+10h]
0x140011f6c  lea     rcx, [rdi+294h]; void *
0x140011f73  add     r8, 14h; Size
0x140011f77  mov     rdx, r11; Src
0x140011f7a  call    memmove
0x140011f7f  mov     rcx, [rsi+20h]
0x140011f83  mov     edx, 40h ; '@'; cchDest
0x140011f88  movzx   eax, word ptr [rcx+30Ch]
0x140011f8f  neg     ax
0x140011f92  sbb     r8, r8
0x140011f95  add     rcx, 2ECh
0x140011f9c  and     r8d, 20h
0x140011fa0  add     r8, rcx; pszSrc
0x140011fa3  lea     rcx, [rdi+214h]; pszDest
0x140011faa  call    RtlStringCchCopyW
0x140011faf  mov     r11, [rsp+28h+arg_28]
0x140011fb4  test    r11, r11
0x140011fb7  jz      short loc_140011FBC
0x140011fb9  mov     [r11], ebx
0x140011fbc  mov     rcx, cs:WPP_GLOBAL_Control
0x140011fc3  lea     rax, WPP_GLOBAL_Control
0x140011fca  cmp     rcx, rax
0x140011fcd  jz      short loc_140011FEA
0x140011fcf  cmp     byte ptr [rcx+29h], 4
0x140011fd3  jb      short loc_140011FEA
0x140011fd5  mov     rcx, [rcx+18h]
0x140011fd9  lea     r8, WPP_83886b54412a34bbe371408c37660ab5_Traceguids
0x140011fe0  mov     edx, 0Fh
0x140011fe5  call    WPP_SF_
0x140011fea  xor     eax, eax
0x140011fec  mov     rbx, [rsp+28h+arg_0]
0x140011ff1  mov     rsi, [rsp+28h+arg_8]
0x140011ff6  add     rsp, 20h
0x140011ffa  pop     rdi
0x140011ffb  retn
```
