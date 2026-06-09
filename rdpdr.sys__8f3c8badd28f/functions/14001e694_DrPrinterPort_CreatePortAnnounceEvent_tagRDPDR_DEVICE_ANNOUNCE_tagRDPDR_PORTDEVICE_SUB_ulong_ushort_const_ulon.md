# DrPrinterPort::CreatePortAnnounceEvent(tagRDPDR_DEVICE_ANNOUNCE *,tagRDPDR_PORTDEVICE_SUB *,ulong,ushort const *,ulong *)

- ea: `0x14001e694`
- end: `0x14001e83c`
- name: `?CreatePortAnnounceEvent@DrPrinterPort@@QEAAJPEAUtagRDPDR_DEVICE_ANNOUNCE@@PEAUtagRDPDR_PORTDEVICE_SUB@@KPEBGPEAK@Z`
- size: `424`
- prototype: `__int64 __fastcall(DrPrinterPort *this, struct tagRDPDR_DEVICE_ANNOUNCE *, wchar_t *, unsigned int, const unsigned __int16 *pszSrc, unsigned int *)`
- caller_count: `3`
- callee_count: `8`
- tags: ``

## callers

- `0x14001dd70`
- `0x14001e10c`
- `0x14001e3f0`

## callees

- `0x1400024f0`
- `0x14000324c`
- `0x14000327c`
- `0x1400035a0`
- `0x140006480`
- `0x140006560`
- `0x1400065c0`
- `0x14001e694`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::CreatePortAnnounceEvent(
        DrPrinterPort *this,
        struct tagRDPDR_DEVICE_ANNOUNCE *a2,
        wchar_t *a3,
        unsigned int a4,
        const unsigned __int16 *pszSrc,
        unsigned int *a6)
{
  __int64 v7; // rax
  unsigned int v10; // ebx
  unsigned int v11; // ebx
  unsigned int v13; // ebx
  __int64 v14; // [rsp+20h] [rbp-118h] BYREF
  NTSTRSAFE_PCWSTR v15; // [rsp+28h] [rbp-110h]
  char v16; // [rsp+30h] [rbp-108h] BYREF

  v15 = (NTSTRSAFE_PCWSTR)&v16;
  v7 = *(_QWORD *)this;
  v14 = 11796480;
  v10 = (*(__int64 (__fastcall **)(DrPrinterPort *, __int64 *))(v7 + 32))(this, &v14);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids, &v14);
  if ( (v10 & 0xC0000000) == 0xC0000000 )
    return v10;
  v11 = *((_DWORD *)a2 + 4);
  if ( v11 <= 0xC4 )
  {
    v13 = v11 + 216;
    if ( a4 >= v13 )
    {
      RtlStringCchCopyW(a3, 9u, pszSrc);
      v15[(unsigned __int64)(unsigned __int16)v14 >> 1] = 0;
      RtlStringCchCopyW(a3 + 9, 0x59u, v15);
      memmove(a3 + 98, a2, *((unsigned int *)a2 + 4) + 20LL);
      if ( a6 )
        *a6 = v13;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids);
      return 0;
    }
    else
    {
      if ( a6 )
        *a6 = v13;
      return 3221225507LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids, v11);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14001e694  push    rbx
0x14001e696  push    rbp
0x14001e697  push    rsi
0x14001e698  push    rdi
0x14001e699  push    r13
0x14001e69b  push    r14
0x14001e69d  push    r15
0x14001e69f  sub     rsp, 100h
0x14001e6a6  mov     rax, cs:__security_cookie
0x14001e6ad  xor     rax, rsp
0x14001e6b0  mov     [rsp+138h+var_48], rax
0x14001e6b8  mov     r15, [rsp+138h+pszSrc]
0x14001e6c0  lea     rax, [rsp+138h+var_108]
0x14001e6c5  mov     rdi, [rsp+138h+arg_28]
0x14001e6cd  mov     rsi, rdx
0x14001e6d0  mov     [rsp+138h+var_110], rax
0x14001e6d5  lea     rdx, [rsp+138h+var_118]
0x14001e6da  mov     rax, [rcx]
0x14001e6dd  mov     r14d, r9d
0x14001e6e0  mov     rbp, r8
0x14001e6e3  mov     [rsp+138h+var_118], 0B40000h
0x14001e6ec  mov     rax, [rax+20h]
0x14001e6f0  call    _guard_dispatch_icall
0x14001e6f5  mov     ebx, eax
0x14001e6f7  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e6fe  lea     r13, WPP_GLOBAL_Control
0x14001e705  cmp     rcx, r13
0x14001e708  jz      short loc_14001E72A
0x14001e70a  cmp     byte ptr [rcx+29h], 4
0x14001e70e  jb      short loc_14001E72A
0x14001e710  mov     rcx, [rcx+18h]
0x14001e714  lea     r9, [rsp+138h+var_118]
0x14001e719  mov     edx, 1Ah
0x14001e71e  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x14001e725  call    WPP_SF_Z
0x14001e72a  mov     ecx, 0C0000000h
0x14001e72f  mov     eax, ebx
0x14001e731  and     eax, ecx
0x14001e733  cmp     eax, ecx
0x14001e735  jz      loc_14001E817
0x14001e73b  mov     ebx, [rsi+10h]
0x14001e73e  cmp     ebx, 0C4h
0x14001e744  jbe     short loc_14001E77A
0x14001e746  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e74d  cmp     rcx, r13
0x14001e750  jz      short loc_14001E770
0x14001e752  cmp     byte ptr [rcx+29h], 2
0x14001e756  jb      short loc_14001E770
0x14001e758  mov     rcx, [rcx+18h]
0x14001e75c  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x14001e763  mov     edx, 1Bh
0x14001e768  mov     r9d, ebx
0x14001e76b  call    WPP_SF_d
0x14001e770  mov     eax, 0C000000Dh
0x14001e775  jmp     loc_14001E819
0x14001e77a  add     ebx, 0D8h
0x14001e780  cmp     r14d, ebx
0x14001e783  jnb     short loc_14001E796
0x14001e785  test    rdi, rdi
0x14001e788  jz      short loc_14001E78C
0x14001e78a  mov     [rdi], ebx
0x14001e78c  mov     eax, 0C0000023h
0x14001e791  jmp     loc_14001E819
0x14001e796  mov     r8, r15; pszSrc
0x14001e799  mov     edx, 9; cchDest
0x14001e79e  mov     rcx, rbp; pszDest
0x14001e7a1  call    RtlStringCchCopyW
0x14001e7a6  movzx   r11d, word ptr [rsp+138h+var_118]
0x14001e7ac  xor     ecx, ecx
0x14001e7ae  mov     rax, [rsp+138h+var_110]
0x14001e7b3  mov     edx, 59h ; 'Y'; cchDest
0x14001e7b8  shr     r11, 1
0x14001e7bb  mov     [rax+r11*2], cx
0x14001e7c0  lea     rcx, [rbp+12h]; pszDest
0x14001e7c4  mov     r8, [rsp+138h+var_110]; pszSrc
0x14001e7c9  call    RtlStringCchCopyW
0x14001e7ce  mov     r8d, [rsi+10h]
0x14001e7d2  lea     rcx, [rbp+0C4h]; void *
0x14001e7d9  add     r8, 14h; Size
0x14001e7dd  mov     rdx, rsi; Src
0x14001e7e0  call    memmove
0x14001e7e5  test    rdi, rdi
0x14001e7e8  jz      short loc_14001E7EC
0x14001e7ea  mov     [rdi], ebx
0x14001e7ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e7f3  cmp     rcx, r13
0x14001e7f6  jz      short loc_14001E813
0x14001e7f8  cmp     byte ptr [rcx+29h], 4
0x14001e7fc  jb      short loc_14001E813
0x14001e7fe  mov     rcx, [rcx+18h]
0x14001e802  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x14001e809  mov     edx, 1Ch
0x14001e80e  call    WPP_SF_
0x14001e813  xor     eax, eax
0x14001e815  jmp     short loc_14001E819
0x14001e817  mov     eax, ebx
0x14001e819  mov     rcx, [rsp+138h+var_48]
0x14001e821  xor     rcx, rsp; StackCookie
0x14001e824  call    __security_check_cookie
0x14001e829  add     rsp, 100h
0x14001e830  pop     r15
0x14001e832  pop     r14
0x14001e834  pop     r13
0x14001e836  pop     rdi
0x14001e837  pop     rsi
0x14001e838  pop     rbp
0x14001e839  pop     rbx
0x14001e83a  retn
```
