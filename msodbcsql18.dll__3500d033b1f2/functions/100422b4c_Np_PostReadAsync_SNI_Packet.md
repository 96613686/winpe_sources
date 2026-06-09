# Np::PostReadAsync(SNI_Packet *)

- ea: `0x100422b4c`
- end: `0x100422f9d`
- name: `?PostReadAsync@Np@@AEAAKPEAVSNI_Packet@@@Z`
- size: `1105`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100422fb0`

## callees

- `0x100422b4c`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043b1c4`
- `0x10043b1f8`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546b88`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetOverlappedResult` at `0x100422cd1`
- `KERNEL32!GetOverlappedResult` at `0x100422cd1`
- `KERNEL32!GetLastError` at `0x100422c4c`
- `KERNEL32!GetLastError` at `0x100422cdf`
- `KERNEL32!GetLastError` at `0x100422c4c`
- `KERNEL32!GetLastError` at `0x100422cdf`
- `KERNEL32!ReadFile` at `0x100422c3f`
- `KERNEL32!ReadFile` at `0x100422c3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::PostReadAsync(Np *this, struct _OVERLAPPED *a2)
{
  char *v4; // rbx
  DWORD v5; // ebp
  DWORD v6; // ebx
  wchar_t *v7; // r8
  __int64 v8; // rdx
  DWORD LastError; // eax
  __int64 v10; // r9
  int v12; // [rsp+28h] [rbp-30h]
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+8h] BYREF
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF

  v14 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7A20[0] )
    bidScopeEnterW(&v14, off_1005E7A20[0], *((unsigned int *)this + 11));
  v4 = (char *)a2[2].Pointer + LODWORD(a2[3].Internal);
  v5 = HIDWORD(a2[2].hEvent) - LODWORD(a2[2].hEvent);
  a2->Offset = 0;
  a2->OffsetHigh = 0;
  if ( *((_QWORD *)this + 10) )
  {
    v6 = 5023;
    if ( (bidGblFlags & 2) == 0 || !off_1005E4E00[0] )
      goto LABEL_9;
    SniErrorIdFromStringId(0xC3B4u);
    v7 = off_1005E4E00[0];
    v8 = 848896;
LABEL_8:
    bidTraceW(0, v8, v7, *((unsigned int *)this + 18));
LABEL_9:
    SNISetLastError(*((unsigned int *)this + 18), v6, 50100);
    goto LABEL_49;
  }
  SNI::detail::Transport::PrepareForAsyncCall(this, (struct SNI_Packet *)a2);
  if ( !ReadFile(*((HANDLE *)this + 8), v4, v5, 0, a2) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 997 )
      goto LABEL_49;
    if ( LastError != 234 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4E10[0] )
        bidTraceW(0, 878592, off_1005E4E10[0], LastError);
      if ( (bidGblFlags & 2) == 0 || !off_1005E4E18[0] )
        goto LABEL_9;
      SniErrorIdFromStringId(0xC3B4u);
      v7 = off_1005E4E18[0];
      v8 = 879616;
      goto LABEL_8;
    }
    if ( (bidGblFlags & 2) != 0 && off_1005E4E08[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        873472,
        off_1005E4E08[0],
        0);
  }
  if ( SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(this) )
  {
    if ( GetOverlappedResult(*((HANDLE *)this + 8), a2, &NumberOfBytesTransferred, 0) )
    {
      v10 = NumberOfBytesTransferred;
      if ( NumberOfBytesTransferred )
      {
        v6 = 0;
        LODWORD(a2[2].hEvent) += NumberOfBytesTransferred;
        if ( (bidGblFlags & 0x24002) == 0x24002 )
        {
          v10 = NumberOfBytesTransferred;
          if ( off_1005E4E40[0] )
          {
            bidTraceW(0, 914432, off_1005E4E40[0], NumberOfBytesTransferred);
            v10 = NumberOfBytesTransferred;
          }
        }
        if ( (bidGblFlags & 0x24002) == 0x24002 )
          bidWriteBin(bidID, 16, (char *)a2[2].Pointer + LODWORD(a2[3].Internal), v10, 0);
      }
      else
      {
        v6 = 233;
        if ( (bidGblFlags & 2) != 0 && off_1005E4E30[0] )
        {
          v12 = 233;
          SniErrorIdFromStringId(0xC3B6u);
          bidTraceW(0, 903168, off_1005E4E30[0], *((unsigned int *)this + 18));
        }
        SNISetLastError(*((unsigned int *)this + 18), 233, 50102);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4E38[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD, int, __int64))off_1005D39E0[0])(
            bidID,
            0,
            904192,
            off_1005E4E38[0],
            0,
            v12,
            -2);
      }
    }
    else
    {
      v6 = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E4E20[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 893952, off_1005E4E20[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), v6, 50100);
      if ( (bidGblFlags & 2) != 0 && off_1005E4E28[0] )
        bidTraceW(0, 897024, off_1005E4E28[0], v6);
    }
  }
  else
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4E48[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, _QWORD, __int64, wchar_t *, _QWORD))off_1005D39E0[0])(
        bidID,
        0,
        921600,
        off_1005E4E48[0],
        0);
    v6 = 997;
  }
LABEL_49:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4E50[0] )
    bidTraceW(0, 926720, off_1005E4E50[0], v6);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v14);
  return v6;
}

```

## disassembly

```asm
0x100422b4c  mov     r11, rsp
0x100422b4f  push    rsi
0x100422b50  push    rdi
0x100422b51  push    r15
0x100422b53  sub     rsp, 40h
0x100422b57  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x100422b5f  mov     [r11+18h], rbx
0x100422b63  mov     [r11+20h], rbp
0x100422b67  mov     rsi, rdx
0x100422b6a  mov     rdi, rcx
0x100422b6d  or      qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x100422b72  mov     eax, cs:_bidGblFlags
0x100422b78  mov     ecx, 20004h
0x100422b7d  and     eax, ecx
0x100422b7f  cmp     eax, ecx
0x100422b81  jnz     short loc_100422BA6
0x100422b83  mov     rax, cs:off_1005E7A20; "<Np::PostReadAsync|API|SNI> %u#, pPacke"...
0x100422b8a  test    rax, rax
0x100422b8d  jz      short loc_100422BA6
0x100422b8f  mov     r9, rdx
0x100422b92  mov     r8d, [rdi+2Ch]
0x100422b96  mov     rdx, cs:off_1005E7A20; "<Np::PostReadAsync|API|SNI> %u#, pPacke"...
0x100422b9d  lea     rcx, [r11+10h]
0x100422ba1  call    _bidScopeEnterW
0x100422ba6  mov     ebx, [rsi+60h]
0x100422ba9  add     rbx, [rsi+50h]
0x100422bad  mov     ebp, [rsi+5Ch]
0x100422bb0  sub     ebp, [rsi+58h]
0x100422bb3  and     dword ptr [rsi+10h], 0
0x100422bb7  and     dword ptr [rsi+14h], 0
0x100422bbb  mov     r15d, 20002h
0x100422bc1  cmp     qword ptr [rdi+50h], 0
0x100422bc6  jz      short loc_100422C22
0x100422bc8  mov     ebx, 139Fh
0x100422bcd  mov     esi, 0C3B4h
0x100422bd2  mov     bpl, 2
0x100422bd5  test    byte ptr cs:_bidGblFlags, bpl
0x100422bdc  jz      short loc_100422C10
0x100422bde  mov     rax, cs:off_1005E4E00; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422be5  test    rax, rax
0x100422be8  jz      short loc_100422C10
0x100422bea  mov     ecx, esi; unsigned int
0x100422bec  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422bf1  mov     r8, cs:off_1005E4E00; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422bf8  mov     edx, 0CF400h
0x100422bfd  mov     [rsp+58h+var_30], ebx
0x100422c01  mov     r9d, [rdi+48h]
0x100422c05  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x100422c09  xor     ecx, ecx
0x100422c0b  call    _bidTraceW
0x100422c10  mov     r8d, esi
0x100422c13  mov     edx, ebx
0x100422c15  mov     ecx, [rdi+48h]
0x100422c18  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422c1d  jmp     loc_100422F4D
0x100422c22  mov     rdx, rsi; struct SNI_Packet *
0x100422c25  mov     rcx, rdi; this
0x100422c28  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x100422c2d  mov     [rsp+58h+lpOverlapped], rsi; lpOverlapped
0x100422c32  xor     r9d, r9d; lpNumberOfBytesRead
0x100422c35  mov     r8d, ebp; nNumberOfBytesToRead
0x100422c38  mov     rdx, rbx; lpBuffer
0x100422c3b  mov     rcx, [rdi+40h]; hFile
0x100422c3f  call    cs:__imp_ReadFile
0x100422c45  mov     bpl, 2
0x100422c48  test    eax, eax
0x100422c4a  jnz     short loc_100422CB2
0x100422c4c  call    cs:__imp_GetLastError
0x100422c52  mov     ebx, eax
0x100422c54  cmp     eax, 3E5h
0x100422c59  jz      loc_100422F4D
0x100422c5f  cmp     eax, 0EAh
0x100422c64  jnz     loc_100422D6C
0x100422c6a  test    byte ptr cs:_bidGblFlags, bpl
0x100422c71  jz      short loc_100422CB2
0x100422c73  mov     rax, cs:off_1005E4E08; "<Np::PostReadAsync|ERR|SNI> ReadFile re"...
0x100422c7a  test    rax, rax
0x100422c7d  jz      short loc_100422CB2
0x100422c7f  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100422c87  jz      short loc_100422CB2
0x100422c89  mov     rax, cs:off_1005D39E0
0x100422c90  and     [rsp+58h+lpOverlapped], 0
0x100422c96  mov     r9, cs:off_1005E4E08; "<Np::PostReadAsync|ERR|SNI> ReadFile re"...
0x100422c9d  xor     edx, edx
0x100422c9f  mov     r8d, 0D5400h
0x100422ca5  mov     rcx, cs:_bidID
0x100422cac  call    cs:__guard_dispatch_icall_fptr
0x100422cb2  mov     rcx, rdi; this
0x100422cb5  call    ?FWillSkipCompletionPortOnSuccess@Transport@detail@SNI@@IEBA_NXZ; SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(void)
0x100422cba  test    al, al
0x100422cbc  jz      loc_100422EFB
0x100422cc2  xor     r9d, r9d; bWait
0x100422cc5  lea     r8, [rsp+58h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x100422cca  mov     rdx, rsi; lpOverlapped
0x100422ccd  mov     rcx, [rdi+40h]; hFile
0x100422cd1  call    cs:__imp_GetOverlappedResult
0x100422cd7  test    eax, eax
0x100422cd9  jnz     loc_100422DD1
0x100422cdf  call    cs:__imp_GetLastError
0x100422ce5  mov     ebx, eax
0x100422ce7  mov     esi, 0C3B4h
0x100422cec  test    byte ptr cs:_bidGblFlags, bpl
0x100422cf3  jz      short loc_100422D27
0x100422cf5  mov     rax, cs:off_1005E4E20; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422cfc  test    rax, rax
0x100422cff  jz      short loc_100422D27
0x100422d01  mov     ecx, esi; unsigned int
0x100422d03  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422d08  mov     [rsp+58h+var_30], ebx
0x100422d0c  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x100422d10  mov     r9d, [rdi+48h]
0x100422d14  mov     r8, cs:off_1005E4E20; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422d1b  mov     edx, 0DA400h
0x100422d20  xor     ecx, ecx
0x100422d22  call    _bidTraceW
0x100422d27  mov     r8d, esi
0x100422d2a  mov     edx, ebx
0x100422d2c  mov     ecx, [rdi+48h]
0x100422d2f  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422d34  test    byte ptr cs:_bidGblFlags, bpl
0x100422d3b  jz      loc_100422F4D
0x100422d41  mov     rax, cs:off_1005E4E28; "<Np::PostReadAsync|ERR|SNI> GetOverlapp"...
0x100422d48  test    rax, rax
0x100422d4b  jz      loc_100422F4D
0x100422d51  mov     r9d, ebx
0x100422d54  mov     r8, cs:off_1005E4E28; "<Np::PostReadAsync|ERR|SNI> GetOverlapp"...
0x100422d5b  mov     edx, 0DB000h
0x100422d60  xor     ecx, ecx
0x100422d62  call    _bidTraceW
0x100422d67  jmp     loc_100422F4D
0x100422d6c  test    byte ptr cs:_bidGblFlags, bpl
0x100422d73  jz      short loc_100422D97
0x100422d75  mov     rax, cs:off_1005E4E10; "<Np::PostReadAsync|ERR|SNI> ReadFile: %"...
0x100422d7c  test    rax, rax
0x100422d7f  jz      short loc_100422D97
0x100422d81  mov     r9d, ebx
0x100422d84  mov     r8, cs:off_1005E4E10; "<Np::PostReadAsync|ERR|SNI> ReadFile: %"...
0x100422d8b  mov     edx, 0D6800h
0x100422d90  xor     ecx, ecx
0x100422d92  call    _bidTraceW
0x100422d97  mov     esi, 0C3B4h
0x100422d9c  test    byte ptr cs:_bidGblFlags, bpl
0x100422da3  jz      loc_100422C10
0x100422da9  mov     rax, cs:off_1005E4E18; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422db0  test    rax, rax
0x100422db3  jz      loc_100422C10
0x100422db9  mov     ecx, esi; unsigned int
0x100422dbb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422dc0  mov     r8, cs:off_1005E4E18; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422dc7  mov     edx, 0D6C00h
0x100422dcc  jmp     loc_100422BFD
0x100422dd1  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x100422dd6  test    r9d, r9d
0x100422dd9  jnz     loc_100422E8F
0x100422ddf  mov     ebx, 0E9h
0x100422de4  mov     esi, 0C3B6h
0x100422de9  test    byte ptr cs:_bidGblFlags, bpl
0x100422df0  jz      short loc_100422E24
0x100422df2  mov     rax, cs:off_1005E4E30; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422df9  test    rax, rax
0x100422dfc  jz      short loc_100422E24
0x100422dfe  mov     ecx, esi; unsigned int
0x100422e00  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422e05  mov     [rsp+58h+var_30], ebx
0x100422e09  mov     dword ptr [rsp+58h+lpOverlapped], eax
0x100422e0d  mov     r9d, [rdi+48h]
0x100422e11  mov     r8, cs:off_1005E4E30; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x100422e18  mov     edx, 0DC800h
0x100422e1d  xor     ecx, ecx
0x100422e1f  call    _bidTraceW
0x100422e24  mov     r8d, esi
0x100422e27  mov     edx, ebx
0x100422e29  mov     ecx, [rdi+48h]
0x100422e2c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422e31  mov     eax, cs:_bidGblFlags
0x100422e37  and     eax, r15d
0x100422e3a  cmp     eax, r15d
0x100422e3d  jnz     loc_100422F4D
0x100422e43  mov     rax, cs:off_1005E4E38; "<Np::PostReadAsync|SNI> 0-byte successf"...
0x100422e4a  test    rax, rax
0x100422e4d  jz      loc_100422F4D
0x100422e53  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100422e5b  jz      loc_100422F4D
0x100422e61  mov     rax, cs:off_1005D39E0
0x100422e68  and     [rsp+58h+lpOverlapped], 0
0x100422e6e  mov     r9, cs:off_1005E4E38; "<Np::PostReadAsync|SNI> 0-byte successf"...
0x100422e75  xor     edx, edx
0x100422e77  mov     r8d, 0DCC00h
0x100422e7d  mov     rcx, cs:_bidID
0x100422e84  call    cs:__guard_dispatch_icall_fptr
0x100422e8a  jmp     loc_100422F4D
0x100422e8f  xor     ebx, ebx
0x100422e91  add     [rsi+58h], r9d
0x100422e95  mov     eax, cs:_bidGblFlags
0x100422e9b  mov     edi, 24002h
0x100422ea0  and     eax, edi
0x100422ea2  cmp     eax, edi
0x100422ea4  jnz     short loc_100422ECF
0x100422ea6  mov     rax, cs:off_1005E4E40; "<Np::PostReadAsync|SNI> Receive Packet,"...
0x100422ead  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x100422eb2  test    rax, rax
0x100422eb5  jz      short loc_100422ECF
0x100422eb7  mov     r8, cs:off_1005E4E40; "<Np::PostReadAsync|SNI> Receive Packet,"...
0x100422ebe  mov     edx, 0DF400h
0x100422ec3  xor     ecx, ecx
0x100422ec5  call    _bidTraceW
0x100422eca  mov     r9d, [rsp+58h+NumberOfBytesTransferred]
0x100422ecf  mov     eax, cs:_bidGblFlags
0x100422ed5  and     eax, edi
0x100422ed7  cmp     eax, edi
0x100422ed9  jnz     short loc_100422F4D
0x100422edb  mov     r8d, [rsi+60h]
0x100422edf  add     r8, [rsi+50h]
0x100422ee3  and     [rsp+58h+lpOverlapped], rbx
0x100422ee8  mov     edx, 10h
0x100422eed  mov     rcx, cs:_bidID
0x100422ef4  call    _bidWriteBin
0x100422ef9  jmp     short loc_100422F4D
0x100422efb  mov     eax, cs:_bidGblFlags
0x100422f01  and     eax, r15d
0x100422f04  cmp     eax, r15d
0x100422f07  jnz     short loc_100422F48
0x100422f09  mov     rax, cs:off_1005E4E48; "<Np::PostReadAsync|SNI> Suppressing suc"...
0x100422f10  test    rax, rax
0x100422f13  jz      short loc_100422F48
0x100422f15  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x100422f1d  jz      short loc_100422F48
0x100422f1f  mov     rax, cs:off_1005D39E0
0x100422f26  and     [rsp+58h+lpOverlapped], 0
0x100422f2c  mov     r9, cs:off_1005E4E48; "<Np::PostReadAsync|SNI> Suppressing suc"...
0x100422f33  xor     edx, edx
0x100422f35  mov     r8d, 0E1000h
0x100422f3b  mov     rcx, cs:_bidID
0x100422f42  call    cs:__guard_dispatch_icall_fptr
0x100422f48  mov     ebx, 3E5h
0x100422f4d  mov     eax, cs:_bidGblFlags
0x100422f53  and     eax, r15d
0x100422f56  cmp     eax, r15d
0x100422f59  jnz     short loc_100422F7E
0x100422f5b  mov     rax, cs:off_1005E4E50; "<Np::PostReadAsync|RET|SNI> %d{WINERR}"...
0x100422f62  test    rax, rax
0x100422f65  jz      short loc_100422F7E
0x100422f67  mov     r9d, ebx
0x100422f6a  mov     r8, cs:off_1005E4E50; "<Np::PostReadAsync|RET|SNI> %d{WINERR}"...
0x100422f71  mov     edx, 0E2400h
0x100422f76  xor     ecx, ecx
0x100422f78  call    _bidTraceW
0x100422f7d  nop
0x100422f7e  lea     rcx, [rsp+58h+arg_8]; this
0x100422f83  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x100422f88  mov     eax, ebx
0x100422f8a  mov     rbx, [rsp+58h+arg_10]
0x100422f8f  mov     rbp, [rsp+58h+arg_18]
0x100422f94  add     rsp, 40h
0x100422f98  pop     r15
0x100422f9a  pop     rdi
0x100422f9b  pop     rsi
0x100422f9c  retn
```
