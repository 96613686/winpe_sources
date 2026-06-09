# FveReadStandaloneMetadata

- ea: `0x140067b98`
- end: `0x140067ee9`
- name: `FveReadStandaloneMetadata`
- size: `849`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, GUID *Guid)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140069dfc`
- `0x14006a2c4`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000a210`
- `0x140018948`
- `0x140022bf0`
- `0x140067b98`
- `0x140089c90`
- `0x140092a9c`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140067ccc`
- `ntoskrnl!ZwQueryInformationFile` at `0x140067ccc`
- `ntoskrnl!ZwReadFile` at `0x140067dee`
- `ntoskrnl!ZwReadFile` at `0x140067dee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067e8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140067e8f`
- `ntoskrnl!ExAllocatePool2` at `0x140067d67`
- `ntoskrnl!ExAllocatePool2` at `0x140067d67`

## pseudocode

```c
__int64 __fastcall FveReadStandaloneMetadata(PCUNICODE_STRING SourceString, GUID *Guid, _QWORD *a3)
{
  void *Buffer; // rdi
  int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  ULONG Length; // esi
  unsigned int v11; // ebx
  HANDLE FileHandle; // [rsp+60h] [rbp-9h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+68h] [rbp-1h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  __int128 FileInformation; // [rsp+80h] [rbp+17h] BYREF
  __int64 v17; // [rsp+90h] [rbp+27h]

  FileHandle = 0;
  v17 = 0;
  ByteOffset.QuadPart = 0;
  IoStatusBlock = 0;
  Buffer = 0;
  FileInformation = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
  }
  v7 = FveFileOpenEx(SourceString, Guid, 0, (__int64)L"FVESTDMD.", 0, 0, 1u, 0x886Au, 0, 0, 0, &FileHandle);
  if ( v7 >= 0 )
  {
    v7 = ZwQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
    if ( v7 >= 0 )
    {
      if ( SHIDWORD(FileInformation) <= 0 )
      {
        Length = DWORD2(FileInformation);
        v11 = DWORD2(FileInformation);
        Buffer = (void *)ExAllocatePool2(264, DWORD2(FileInformation), 809850438);
        if ( Buffer )
        {
          v7 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, Length, &ByteOffset, 0);
          if ( v7 >= 0 )
          {
            v7 = FveValidateStandaloneMetadata(Buffer, Length);
            if ( v7 >= 0 )
            {
              *a3 = Buffer;
              Buffer = 0;
            }
            else
            {
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v9 = 165;
                goto LABEL_10;
              }
            }
          }
          else
          {
            v8 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              v9 = 164;
              goto LABEL_10;
            }
          }
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, v11);
          }
          v7 = -1073741670;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids);
        }
        v7 = -1071579126;
      }
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v9 = 161;
        goto LABEL_10;
      }
    }
  }
  else
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v9 = 160;
LABEL_10:
      WPP_SF_d(v8->AttachedDevice, v9, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v7);
    }
  }
  if ( FileHandle )
    FveFileClose(FileHandle);
  if ( Buffer )
    ExFreePoolWithTag(Buffer, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140067b98  push    rbp
0x140067b9a  push    rbx
0x140067b9b  push    rsi
0x140067b9c  push    rdi
0x140067b9d  push    r15
0x140067b9f  lea     rbp, [rsp-37h]
0x140067ba4  sub     rsp, 0A0h
0x140067bab  mov     rax, cs:__security_cookie
0x140067bb2  xor     rax, rsp
0x140067bb5  mov     [rbp+57h+var_28], rax
0x140067bb9  xor     eax, eax
0x140067bbb  mov     [rbp+57h+FileHandle], 0
0x140067bc3  xorps   xmm0, xmm0
0x140067bc6  mov     [rbp+57h+var_30], rax
0x140067bca  xorps   xmm1, xmm1
0x140067bcd  mov     qword ptr [rbp+57h+var_58], 0
0x140067bd5  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140067bd9  xor     edi, edi
0x140067bdb  mov     r15, r8
0x140067bde  movups  [rbp+57h+FileInformation], xmm1
0x140067be2  mov     rsi, rdx
0x140067be5  mov     rbx, rcx
0x140067be8  mov     rcx, cs:WPP_GLOBAL_Control
0x140067bef  lea     rax, WPP_GLOBAL_Control
0x140067bf6  cmp     rcx, rax
0x140067bf9  jz      short loc_140067C1D
0x140067bfb  mov     eax, [rcx+2Ch]
0x140067bfe  test    al, 10h
0x140067c00  jz      short loc_140067C1D
0x140067c02  cmp     byte ptr [rcx+29h], 5
0x140067c06  jb      short loc_140067C1D
0x140067c08  mov     rcx, [rcx+18h]
0x140067c0c  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140067c13  mov     edx, 9Fh
0x140067c18  call    WPP_SF_
0x140067c1d  lea     rax, [rbp+57h+FileHandle]
0x140067c21  xor     r8d, r8d
0x140067c24  mov     [rsp+0C0h+var_68], rax; __int64
0x140067c29  lea     r9, aFvestdmd; "FVESTDMD."
0x140067c30  mov     [rsp+0C0h+var_70], rdi; __int64
0x140067c35  mov     rdx, rsi; Guid
0x140067c38  mov     [rsp+0C0h+var_78], rdi; __int64
0x140067c3d  mov     rcx, rbx; SourceString
0x140067c40  mov     byte ptr [rsp+0C0h+Key], dil; char
0x140067c45  mov     dword ptr [rsp+0C0h+ByteOffset], 886Ah; ULONG
0x140067c4d  mov     [rsp+0C0h+Length], 1; ULONG
0x140067c55  mov     dword ptr [rsp+0C0h+Buffer], edi; ULONG
0x140067c59  mov     byte ptr [rsp+0C0h+FileInformationClass], dil; char
0x140067c5e  call    FveFileOpenEx
0x140067c63  mov     ebx, eax
0x140067c65  test    eax, eax
0x140067c67  jns     short loc_140067CB2
0x140067c69  mov     rcx, cs:WPP_GLOBAL_Control
0x140067c70  lea     rsi, WPP_GLOBAL_Control
0x140067c77  cmp     rcx, rsi
0x140067c7a  jz      loc_140067E70
0x140067c80  mov     eax, [rcx+2Ch]
0x140067c83  test    al, 10h
0x140067c85  jz      loc_140067E70
0x140067c8b  cmp     byte ptr [rcx+29h], 2
0x140067c8f  jb      loc_140067E70
0x140067c95  mov     edx, 0A0h
0x140067c9a  mov     rcx, [rcx+18h]
0x140067c9e  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140067ca5  mov     r9d, ebx
0x140067ca8  call    WPP_SF_d
0x140067cad  jmp     loc_140067E70
0x140067cb2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140067cb6  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140067cba  mov     r9d, 18h; Length
0x140067cc0  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x140067cc8  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140067ccc  call    cs:__imp_ZwQueryInformationFile
0x140067cd3  nop     dword ptr [rax+rax+00h]
0x140067cd8  mov     ebx, eax
0x140067cda  test    eax, eax
0x140067cdc  jns     short loc_140067D11
0x140067cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ce5  lea     rsi, WPP_GLOBAL_Control
0x140067cec  cmp     rcx, rsi
0x140067cef  jz      loc_140067E70
0x140067cf5  mov     eax, [rcx+2Ch]
0x140067cf8  test    al, 10h
0x140067cfa  jz      loc_140067E70
0x140067d00  cmp     byte ptr [rcx+29h], 2
0x140067d04  jb      loc_140067E70
0x140067d0a  mov     edx, 0A1h
0x140067d0f  jmp     short loc_140067C9A
0x140067d11  cmp     dword ptr [rbp+57h+FileInformation+0Ch], edi
0x140067d14  jle     short loc_140067D55
0x140067d16  mov     rcx, cs:WPP_GLOBAL_Control
0x140067d1d  lea     rsi, WPP_GLOBAL_Control
0x140067d24  cmp     rcx, rsi
0x140067d27  jz      short loc_140067D4B
0x140067d29  mov     eax, [rcx+2Ch]
0x140067d2c  test    al, 10h
0x140067d2e  jz      short loc_140067D4B
0x140067d30  cmp     byte ptr [rcx+29h], 2
0x140067d34  jb      short loc_140067D4B
0x140067d36  mov     rcx, [rcx+18h]
0x140067d3a  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140067d41  mov     edx, 0A2h
0x140067d46  call    WPP_SF_
0x140067d4b  mov     ebx, 0C021000Ah
0x140067d50  jmp     loc_140067E70
0x140067d55  mov     esi, dword ptr [rbp+57h+FileInformation+8]
0x140067d58  mov     r8d, 30455646h
0x140067d5e  mov     edx, esi
0x140067d60  mov     ecx, 108h
0x140067d65  mov     ebx, esi
0x140067d67  call    cs:__imp_ExAllocatePool2
0x140067d6e  nop     dword ptr [rax+rax+00h]
0x140067d73  mov     rdi, rax
0x140067d76  test    rax, rax
0x140067d79  jnz     short loc_140067DBE
0x140067d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140067d82  lea     rsi, WPP_GLOBAL_Control
0x140067d89  cmp     rcx, rsi
0x140067d8c  jz      short loc_140067DB4
0x140067d8e  mov     edx, [rcx+2Ch]
0x140067d91  test    dl, 10h
0x140067d94  jz      short loc_140067DB4
0x140067d96  cmp     byte ptr [rcx+29h], 2
0x140067d9a  jb      short loc_140067DB4
0x140067d9c  mov     rcx, [rcx+18h]
0x140067da0  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140067da7  mov     edx, 0A3h
0x140067dac  mov     r9d, ebx
0x140067daf  call    WPP_SF_q
0x140067db4  mov     ebx, 0C000009Ah
0x140067db9  jmp     loc_140067E70
0x140067dbe  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140067dc2  lea     rax, [rbp+57h+var_58]
0x140067dc6  mov     [rsp+0C0h+Key], 0; Key
0x140067dcf  xor     r9d, r9d; ApcContext
0x140067dd2  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x140067dd7  xor     r8d, r8d; ApcRoutine
0x140067dda  mov     [rsp+0C0h+Length], esi; Length
0x140067dde  lea     rax, [rbp+57h+IoStatusBlock]
0x140067de2  mov     [rsp+0C0h+Buffer], rdi; Buffer
0x140067de7  xor     edx, edx; Event
0x140067de9  mov     qword ptr [rsp+0C0h+FileInformationClass], rax; IoStatusBlock
0x140067dee  call    cs:__imp_ZwReadFile
0x140067df5  nop     dword ptr [rax+rax+00h]
0x140067dfa  mov     ebx, eax
0x140067dfc  test    eax, eax
0x140067dfe  jns     short loc_140067E2A
0x140067e00  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e07  lea     rsi, WPP_GLOBAL_Control
0x140067e0e  cmp     rcx, rsi
0x140067e11  jz      short loc_140067E70
0x140067e13  mov     eax, [rcx+2Ch]
0x140067e16  test    al, 10h
0x140067e18  jz      short loc_140067E70
0x140067e1a  cmp     byte ptr [rcx+29h], 2
0x140067e1e  jb      short loc_140067E70
0x140067e20  mov     edx, 0A4h
0x140067e25  jmp     loc_140067C9A
0x140067e2a  mov     edx, esi
0x140067e2c  mov     rcx, rdi
0x140067e2f  call    FveValidateStandaloneMetadata
0x140067e34  mov     ebx, eax
0x140067e36  test    eax, eax
0x140067e38  jns     short loc_140067E64
0x140067e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140067e41  lea     rsi, WPP_GLOBAL_Control
0x140067e48  cmp     rcx, rsi
0x140067e4b  jz      short loc_140067E70
0x140067e4d  mov     eax, [rcx+2Ch]
0x140067e50  test    al, 10h
0x140067e52  jz      short loc_140067E70
0x140067e54  cmp     byte ptr [rcx+29h], 2
0x140067e58  jb      short loc_140067E70
0x140067e5a  mov     edx, 0A5h
0x140067e5f  jmp     loc_140067C9A
0x140067e64  mov     [r15], rdi
0x140067e67  lea     rsi, WPP_GLOBAL_Control
0x140067e6e  xor     edi, edi
0x140067e70  cmp     [rbp+57h+FileHandle], 0
0x140067e75  jz      short loc_140067E82
0x140067e77  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140067e7b  xor     edx, edx
0x140067e7d  call    FveFileClose
0x140067e82  test    rdi, rdi
0x140067e85  jz      short loc_140067E9B
0x140067e87  mov     edx, 30455646h; Tag
0x140067e8c  mov     rcx, rdi; P
0x140067e8f  call    cs:__imp_ExFreePoolWithTag
0x140067e96  nop     dword ptr [rax+rax+00h]
0x140067e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ea2  cmp     rcx, rsi
0x140067ea5  jz      short loc_140067ECC
0x140067ea7  mov     eax, [rcx+2Ch]
0x140067eaa  test    al, 10h
0x140067eac  jz      short loc_140067ECC
0x140067eae  cmp     byte ptr [rcx+29h], 5
0x140067eb2  jb      short loc_140067ECC
0x140067eb4  mov     rcx, [rcx+18h]
0x140067eb8  lea     r8, WPP_41f10b29aed5302dc99000bce2319ea3_Traceguids
0x140067ebf  mov     edx, 0A6h
0x140067ec4  mov     r9d, ebx
0x140067ec7  call    WPP_SF_d
0x140067ecc  mov     eax, ebx
0x140067ece  mov     rcx, [rbp+57h+var_28]
0x140067ed2  xor     rcx, rsp; StackCookie
0x140067ed5  call    __security_check_cookie
0x140067eda  add     rsp, 0A0h
0x140067ee1  pop     r15
0x140067ee3  pop     rdi
0x140067ee4  pop     rsi
0x140067ee5  pop     rbx
0x140067ee6  pop     rbp
0x140067ee7  retn
```
