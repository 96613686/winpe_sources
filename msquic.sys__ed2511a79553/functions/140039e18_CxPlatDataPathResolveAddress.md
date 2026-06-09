# CxPlatDataPathResolveAddress

- ea: `0x140039e18`
- end: `0x14003a058`
- name: `CxPlatDataPathResolveAddress`
- size: `576`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140003fac`
- `0x14002db50`

## callees

- `0x140039e18`
- `0x14003a060`
- `0x14003c8e0`
- `0x14003c980`
- `0x14003cb00`
- `0x14003ce00`
- `0x14003e928`
- `0x14003ead8`
- `0x14003ed00`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140039fe4`
- `ntoskrnl!_snprintf_s` at `0x140039fe4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a02f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a02f`
- `ntoskrnl!strnlen` at `0x140039e68`
- `ntoskrnl!strnlen` at `0x140039e68`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140039f00`
- `ntoskrnl!RtlUTF8ToUnicodeN` at `0x140039f00`
- `ntoskrnl!ExAllocatePool2` at `0x140039e9f`
- `ntoskrnl!ExAllocatePool2` at `0x140039e9f`

## pseudocode

```c
__int64 __fastcall CxPlatDataPathResolveAddress(_QWORD *a1, const char *a2, unsigned __int16 *a3)
{
  size_t v6; // rax
  ULONG UTF8StringByteCount; // ebx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  ULONG UnicodeStringActualByteCount; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v19; // [rsp+38h] [rbp-C8h] BYREF
  PWSTR UnicodeStringDestination[2]; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v21[20]; // [rsp+50h] [rbp-B0h] BYREF
  char DstBuf[128]; // [rsp+A0h] [rbp-60h] BYREF

  *(_OWORD *)UnicodeStringDestination = 0;
  memset(v21, 0, 0x48u);
  v19 = 0;
  v6 = strnlen(a2, 0x400u);
  UTF8StringByteCount = v6;
  if ( v6 < 0x400 )
  {
    WORD1(UnicodeStringDestination[0]) = 2 * v6;
    UnicodeStringDestination[1] = (PWSTR)ExAllocatePool2(258, (unsigned __int16)(2 * v6), 942826321);
    if ( UnicodeStringDestination[1] )
    {
      v11 = *a3;
      UnicodeStringActualByteCount = 0;
      v21[1] = v11;
      v12 = RtlUTF8ToUnicodeN(
              UnicodeStringDestination[1],
              WORD1(UnicodeStringDestination[0]),
              &UnicodeStringActualByteCount,
              a2,
              UTF8StringByteCount);
      v8 = v12;
      if ( v12 >= 0 )
      {
        LOWORD(UnicodeStringDestination[0]) = UnicodeStringActualByteCount;
        v21[0] = 4;
        v8 = CxPlatDataPathResolveAddressWithHint(a1, UnicodeStringDestination, v21, &v19);
        if ( v8 >= 0
          || (v21[0] = 2, v8 = CxPlatDataPathResolveAddressWithHint(a1, UnicodeStringDestination, v21, &v19), v8 >= 0) )
        {
          memmove(a3, *(const void **)(v19 + 32), *(_QWORD *)(v19 + 16));
        }
        else
        {
          if ( (Microsoft_QuicEnableBits & 4) != 0 )
            McTemplateU0s_EtwWriteTransfer(v15, (const EVENT_DESCRIPTOR *)QuicLibraryError, "Resolving hostname to IP");
          if ( (byte_14005C48E & 0x10) != 0 )
          {
            _snprintf_s(
              DstBuf,
              0x80u,
              0xFFFFFFFFFFFFFFFFuLL,
              "[%p] Couldn't resolve hostname '%s' to an IP address",
              a1,
              a2);
            McTemplateU0s_EtwWriteTransfer(v16, (const EVENT_DESCRIPTOR *)QuicLogError, DstBuf);
          }
          v8 = -1073741275;
        }
      }
      else if ( (Microsoft_QuicEnableBits & 4) != 0 )
      {
        McTemplateU0qs_EtwWriteTransfer(v14, v13, (unsigned int)v12, "Convert hostname to unicode");
      }
    }
    else
    {
      v8 = -1073741801;
      if ( (Microsoft_QuicEnableBits & 2) != 0 )
        McTemplateU0sx_EtwWriteTransfer(v10, v9, "Unicode Hostname", WORD1(UnicodeStringDestination[0]));
    }
  }
  else
  {
    v8 = -1073741811;
  }
  if ( v19 )
    (*(void (__fastcall **)(_QWORD))(a1[13] + 40LL))(a1[12]);
  if ( UnicodeStringDestination[1] )
    ExFreePoolWithTag(UnicodeStringDestination[1], 0x38326351u);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140039e18  push    rbp
0x140039e1a  push    rbx
0x140039e1b  push    rsi
0x140039e1c  push    rdi
0x140039e1d  push    r14
0x140039e1f  lea     rbp, [rsp-30h]
0x140039e24  sub     rsp, 130h
0x140039e2b  mov     rax, cs:__security_cookie
0x140039e32  xor     rax, rsp
0x140039e35  mov     [rbp+50h+var_30], rax
0x140039e39  mov     r14, rdx
0x140039e3c  mov     rsi, r8
0x140039e3f  xor     edx, edx; Val
0x140039e41  mov     rdi, rcx
0x140039e44  xorps   xmm0, xmm0
0x140039e47  lea     rcx, [rsp+150h+var_100]; void *
0x140039e4c  movups  xmmword ptr [rsp+150h+UnicodeStringDestination], xmm0
0x140039e51  lea     r8d, [rdx+48h]; Size
0x140039e55  call    memset
0x140039e5a  and     [rsp+150h+var_118], 0
0x140039e60  mov     edx, 400h; MaxCount
0x140039e65  mov     rcx, r14; Str
0x140039e68  call    cs:__imp_strnlen
0x140039e6f  nop     dword ptr [rax+rax+00h]
0x140039e74  mov     rbx, rax
0x140039e77  cmp     rax, 400h
0x140039e7d  jb      short loc_140039E89
0x140039e7f  mov     ebx, 0C000000Dh
0x140039e84  jmp     loc_14003A005
0x140039e89  add     ax, ax
0x140039e8c  mov     ecx, 102h
0x140039e91  movzx   edx, ax
0x140039e94  mov     r8d, 38326351h
0x140039e9a  mov     word ptr [rsp+150h+UnicodeStringDestination+2], dx
0x140039e9f  call    cs:__imp_ExAllocatePool2
0x140039ea6  nop     dword ptr [rax+rax+00h]
0x140039eab  mov     [rsp+150h+UnicodeStringDestination+8], rax
0x140039eb0  test    rax, rax
0x140039eb3  jnz     short loc_140039EDE
0x140039eb5  test    cs:Microsoft_QuicEnableBits, 2
0x140039ebc  mov     ebx, 0C0000017h
0x140039ec1  jz      loc_14003A005
0x140039ec7  movzx   r9d, word ptr [rsp+150h+UnicodeStringDestination+2]
0x140039ecd  lea     r8, aUnicodeHostnam; "Unicode Hostname"
0x140039ed4  call    McTemplateU0sx_EtwWriteTransfer
0x140039ed9  jmp     loc_14003A005
0x140039ede  movzx   eax, word ptr [rsi]
0x140039ee1  lea     r8, [rsp+150h+UnicodeStringActualByteCount]; UnicodeStringActualByteCount
0x140039ee6  movzx   edx, word ptr [rsp+150h+UnicodeStringDestination+2]; UnicodeStringMaxByteCount
0x140039eeb  mov     r9, r14; UTF8StringSource
0x140039eee  mov     rcx, [rsp+150h+UnicodeStringDestination+8]; UnicodeStringDestination
0x140039ef3  and     [rsp+150h+UnicodeStringActualByteCount], 0
0x140039ef8  mov     [rsp+150h+var_FC], eax
0x140039efc  mov     [rsp+150h+UTF8StringByteCount], ebx; UTF8StringByteCount
0x140039f00  call    cs:__imp_RtlUTF8ToUnicodeN
0x140039f07  nop     dword ptr [rax+rax+00h]
0x140039f0c  mov     ebx, eax
0x140039f0e  test    eax, eax
0x140039f10  jns     short loc_140039F33
0x140039f12  test    cs:Microsoft_QuicEnableBits, 4
0x140039f19  jz      loc_14003A005
0x140039f1f  lea     r9, aConvertHostnam; "Convert hostname to unicode"
0x140039f26  mov     r8d, eax
0x140039f29  call    McTemplateU0qs_EtwWriteTransfer
0x140039f2e  jmp     loc_14003A005
0x140039f33  movzx   eax, word ptr [rsp+150h+UnicodeStringActualByteCount]
0x140039f38  lea     r9, [rsp+150h+var_118]
0x140039f3d  lea     r8, [rsp+150h+var_100]
0x140039f42  mov     word ptr [rsp+150h+UnicodeStringDestination], ax
0x140039f47  lea     rdx, [rsp+150h+UnicodeStringDestination]
0x140039f4c  mov     [rsp+150h+var_100], 4
0x140039f54  mov     rcx, rdi
0x140039f57  call    CxPlatDataPathResolveAddressWithHint
0x140039f5c  mov     ebx, eax
0x140039f5e  test    eax, eax
0x140039f60  js      short loc_140039F7C
0x140039f62  mov     rdx, [rsp+150h+var_118]
0x140039f67  mov     rcx, rsi; void *
0x140039f6a  mov     r8, [rdx+10h]; Size
0x140039f6e  mov     rdx, [rdx+20h]; Src
0x140039f72  call    memmove
0x140039f77  jmp     loc_14003A005
0x140039f7c  lea     r9, [rsp+150h+var_118]
0x140039f81  mov     [rsp+150h+var_100], 2
0x140039f89  lea     r8, [rsp+150h+var_100]
0x140039f8e  mov     rcx, rdi
0x140039f91  lea     rdx, [rsp+150h+UnicodeStringDestination]
0x140039f96  call    CxPlatDataPathResolveAddressWithHint
0x140039f9b  mov     ebx, eax
0x140039f9d  test    eax, eax
0x140039f9f  jns     short loc_140039F62
0x140039fa1  test    cs:Microsoft_QuicEnableBits, 4
0x140039fa8  jz      short loc_140039FBD
0x140039faa  lea     r8, aResolvingHostn; "Resolving hostname to IP"
0x140039fb1  lea     rdx, QuicLibraryError
0x140039fb8  call    McTemplateU0s_EtwWriteTransfer
0x140039fbd  test    cs:byte_14005C48E, 10h
0x140039fc4  jz      short loc_14003A000
0x140039fc6  mov     [rsp+150h+var_128], r14
0x140039fcb  lea     r9, aPCouldnTResolv; "[%p] Couldn't resolve hostname '%s' to "...
0x140039fd2  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140039fd6  mov     qword ptr [rsp+150h+UTF8StringByteCount], rdi
0x140039fdb  mov     edx, 80h; SizeInBytes
0x140039fe0  lea     rcx, [rbp+50h+DstBuf]; DstBuf
0x140039fe4  call    cs:__imp__snprintf_s
0x140039feb  nop     dword ptr [rax+rax+00h]
0x140039ff0  lea     r8, [rbp+50h+DstBuf]
0x140039ff4  lea     rdx, QuicLogError
0x140039ffb  call    McTemplateU0s_EtwWriteTransfer
0x14003a000  mov     ebx, 0C0000225h
0x14003a005  mov     rdx, [rsp+150h+var_118]
0x14003a00a  test    rdx, rdx
0x14003a00d  jz      short loc_14003A020
0x14003a00f  mov     rax, [rdi+68h]
0x14003a013  mov     rcx, [rdi+60h]
0x14003a017  mov     rax, [rax+28h]
0x14003a01b  call    _guard_dispatch_icall
0x14003a020  mov     rcx, [rsp+150h+UnicodeStringDestination+8]; P
0x14003a025  test    rcx, rcx
0x14003a028  jz      short loc_14003A03B
0x14003a02a  mov     edx, 38326351h; Tag
0x14003a02f  call    cs:__imp_ExFreePoolWithTag
0x14003a036  nop     dword ptr [rax+rax+00h]
0x14003a03b  mov     eax, ebx
0x14003a03d  mov     rcx, [rbp+50h+var_30]
0x14003a041  xor     rcx, rsp; StackCookie
0x14003a044  call    __security_check_cookie
0x14003a049  add     rsp, 130h
0x14003a050  pop     r14
0x14003a052  pop     rdi
0x14003a053  pop     rsi
0x14003a054  pop     rbx
0x14003a055  pop     rbp
0x14003a056  retn
```
