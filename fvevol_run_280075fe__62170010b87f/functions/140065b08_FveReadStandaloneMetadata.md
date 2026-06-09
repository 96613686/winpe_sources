# FveReadStandaloneMetadata

- ea: `0x140065b08`
- end: `0x140065e59`
- name: `FveReadStandaloneMetadata`
- size: `849`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, GUID *Guid, PVOID P)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140067d6c`
- `0x140068234`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x14000a150`
- `0x140017f38`
- `0x1400218c0`
- `0x140065b08`
- `0x140087bf0`
- `0x1400909ec`

## import_xrefs

- `ntoskrnl!ZwQueryInformationFile` at `0x140065c3c`
- `ntoskrnl!ZwQueryInformationFile` at `0x140065c3c`
- `ntoskrnl!ZwReadFile` at `0x140065d5e`
- `ntoskrnl!ZwReadFile` at `0x140065d5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065dff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065dff`
- `ntoskrnl!ExAllocatePool2` at `0x140065cd7`
- `ntoskrnl!ExAllocatePool2` at `0x140065cd7`

## pseudocode

```c
__int64 __fastcall FveReadStandaloneMetadata(PCUNICODE_STRING SourceString, GUID *Guid, _QWORD *P)
{
  void *Buffer; // rsi
  int v7; // ebx
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  ULONG Length; // edi
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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 159, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
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
              *P = Buffer;
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
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, v11);
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
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 162, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids);
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
      WPP_SF_d(v8->AttachedDevice, v9, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v7);
    }
  }
  if ( FileHandle )
    FveFileClose(FileHandle);
  if ( Buffer )
    ExFreePoolWithTag(P, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 166, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids, (unsigned int)v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140065b08  push    rbp
0x140065b0a  push    rbx
0x140065b0b  push    rsi
0x140065b0c  push    rdi
0x140065b0d  push    r15
0x140065b0f  lea     rbp, [rsp-37h]
0x140065b14  sub     rsp, 0A0h
0x140065b1b  mov     rax, cs:__security_cookie
0x140065b22  xor     rax, rsp
0x140065b25  mov     [rbp+57h+var_28], rax
0x140065b29  xor     eax, eax
0x140065b2b  mov     [rbp+57h+FileHandle], 0
0x140065b33  xorps   xmm0, xmm0
0x140065b36  mov     [rbp+57h+var_30], rax
0x140065b3a  xorps   xmm1, xmm1
0x140065b3d  mov     qword ptr [rbp+57h+var_58], 0
0x140065b45  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140065b49  xor     esi, esi
0x140065b4b  mov     r15, r8
0x140065b4e  movups  [rbp+57h+FileInformation], xmm1
0x140065b52  mov     rdi, rdx
0x140065b55  mov     rbx, rcx
0x140065b58  mov     rcx, cs:WPP_GLOBAL_Control
0x140065b5f  lea     rax, WPP_GLOBAL_Control
0x140065b66  cmp     rcx, rax
0x140065b69  jz      short loc_140065B8D
0x140065b6b  mov     eax, [rcx+2Ch]
0x140065b6e  test    al, 10h
0x140065b70  jz      short loc_140065B8D
0x140065b72  cmp     byte ptr [rcx+29h], 5
0x140065b76  jb      short loc_140065B8D
0x140065b78  mov     rcx, [rcx+18h]
0x140065b7c  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140065b83  mov     edx, 9Fh
0x140065b88  call    WPP_SF_
0x140065b8d  lea     rax, [rbp+57h+FileHandle]
0x140065b91  xor     r8d, r8d
0x140065b94  mov     [rsp+0C0h+var_68], rax; __int64
0x140065b99  lea     r9, aFvestdmd; "FVESTDMD."
0x140065ba0  mov     [rsp+0C0h+var_70], rsi; __int64
0x140065ba5  mov     rdx, rdi; Guid
0x140065ba8  mov     [rsp+0C0h+var_78], rsi; __int64
0x140065bad  mov     rcx, rbx; SourceString
0x140065bb0  mov     byte ptr [rsp+0C0h+Key], sil; char
0x140065bb5  mov     dword ptr [rsp+0C0h+ByteOffset], 886Ah; ULONG
0x140065bbd  mov     [rsp+0C0h+Length], 1; ULONG
0x140065bc5  mov     dword ptr [rsp+0C0h+Buffer], esi; ULONG
0x140065bc9  mov     byte ptr [rsp+0C0h+FileInformationClass], sil; char
0x140065bce  call    FveFileOpenEx
0x140065bd3  mov     ebx, eax
0x140065bd5  test    eax, eax
0x140065bd7  jns     short loc_140065C22
0x140065bd9  mov     rcx, cs:WPP_GLOBAL_Control
0x140065be0  lea     rdi, WPP_GLOBAL_Control
0x140065be7  cmp     rcx, rdi
0x140065bea  jz      loc_140065DE0
0x140065bf0  mov     eax, [rcx+2Ch]
0x140065bf3  test    al, 10h
0x140065bf5  jz      loc_140065DE0
0x140065bfb  cmp     byte ptr [rcx+29h], 2
0x140065bff  jb      loc_140065DE0
0x140065c05  mov     edx, 0A0h
0x140065c0a  mov     rcx, [rcx+18h]
0x140065c0e  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140065c15  mov     r9d, ebx
0x140065c18  call    WPP_SF_d
0x140065c1d  jmp     loc_140065DE0
0x140065c22  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140065c26  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140065c2a  mov     r9d, 18h; Length
0x140065c30  mov     [rsp+0C0h+FileInformationClass], 5; FileInformationClass
0x140065c38  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140065c3c  call    cs:__imp_ZwQueryInformationFile
0x140065c43  nop     dword ptr [rax+rax+00h]
0x140065c48  mov     ebx, eax
0x140065c4a  test    eax, eax
0x140065c4c  jns     short loc_140065C81
0x140065c4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c55  lea     rdi, WPP_GLOBAL_Control
0x140065c5c  cmp     rcx, rdi
0x140065c5f  jz      loc_140065DE0
0x140065c65  mov     eax, [rcx+2Ch]
0x140065c68  test    al, 10h
0x140065c6a  jz      loc_140065DE0
0x140065c70  cmp     byte ptr [rcx+29h], 2
0x140065c74  jb      loc_140065DE0
0x140065c7a  mov     edx, 0A1h
0x140065c7f  jmp     short loc_140065C0A
0x140065c81  cmp     dword ptr [rbp+57h+FileInformation+0Ch], esi
0x140065c84  jle     short loc_140065CC5
0x140065c86  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c8d  lea     rdi, WPP_GLOBAL_Control
0x140065c94  cmp     rcx, rdi
0x140065c97  jz      short loc_140065CBB
0x140065c99  mov     eax, [rcx+2Ch]
0x140065c9c  test    al, 10h
0x140065c9e  jz      short loc_140065CBB
0x140065ca0  cmp     byte ptr [rcx+29h], 2
0x140065ca4  jb      short loc_140065CBB
0x140065ca6  mov     rcx, [rcx+18h]
0x140065caa  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140065cb1  mov     edx, 0A2h
0x140065cb6  call    WPP_SF_
0x140065cbb  mov     ebx, 0C021000Ah
0x140065cc0  jmp     loc_140065DE0
0x140065cc5  mov     edi, dword ptr [rbp+57h+FileInformation+8]
0x140065cc8  mov     r8d, 30455646h
0x140065cce  mov     edx, edi
0x140065cd0  mov     ecx, 108h
0x140065cd5  mov     ebx, edi
0x140065cd7  call    cs:__imp_ExAllocatePool2
0x140065cde  nop     dword ptr [rax+rax+00h]
0x140065ce3  mov     rsi, rax
0x140065ce6  test    rax, rax
0x140065ce9  jnz     short loc_140065D2E
0x140065ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140065cf2  lea     rdi, WPP_GLOBAL_Control
0x140065cf9  cmp     rcx, rdi
0x140065cfc  jz      short loc_140065D24
0x140065cfe  mov     edx, [rcx+2Ch]
0x140065d01  test    dl, 10h
0x140065d04  jz      short loc_140065D24
0x140065d06  cmp     byte ptr [rcx+29h], 2
0x140065d0a  jb      short loc_140065D24
0x140065d0c  mov     rcx, [rcx+18h]
0x140065d10  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140065d17  mov     edx, 0A3h
0x140065d1c  mov     r9d, ebx
0x140065d1f  call    WPP_SF_q
0x140065d24  mov     ebx, 0C000009Ah
0x140065d29  jmp     loc_140065DE0
0x140065d2e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140065d32  lea     rax, [rbp+57h+var_58]
0x140065d36  mov     [rsp+0C0h+Key], 0; Key
0x140065d3f  xor     r9d, r9d; ApcContext
0x140065d42  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x140065d47  xor     r8d, r8d; ApcRoutine
0x140065d4a  mov     [rsp+0C0h+Length], edi; Length
0x140065d4e  lea     rax, [rbp+57h+IoStatusBlock]
0x140065d52  mov     [rsp+0C0h+Buffer], rsi; Buffer
0x140065d57  xor     edx, edx; Event
0x140065d59  mov     qword ptr [rsp+0C0h+FileInformationClass], rax; IoStatusBlock
0x140065d5e  call    cs:__imp_ZwReadFile
0x140065d65  nop     dword ptr [rax+rax+00h]
0x140065d6a  mov     ebx, eax
0x140065d6c  test    eax, eax
0x140065d6e  jns     short loc_140065D9A
0x140065d70  mov     rcx, cs:WPP_GLOBAL_Control
0x140065d77  lea     rdi, WPP_GLOBAL_Control
0x140065d7e  cmp     rcx, rdi
0x140065d81  jz      short loc_140065DE0
0x140065d83  mov     eax, [rcx+2Ch]
0x140065d86  test    al, 10h
0x140065d88  jz      short loc_140065DE0
0x140065d8a  cmp     byte ptr [rcx+29h], 2
0x140065d8e  jb      short loc_140065DE0
0x140065d90  mov     edx, 0A4h
0x140065d95  jmp     loc_140065C0A
0x140065d9a  mov     edx, edi
0x140065d9c  mov     rcx, rsi
0x140065d9f  call    FveValidateStandaloneMetadata
0x140065da4  mov     ebx, eax
0x140065da6  test    eax, eax
0x140065da8  jns     short loc_140065DD4
0x140065daa  mov     rcx, cs:WPP_GLOBAL_Control
0x140065db1  lea     rdi, WPP_GLOBAL_Control
0x140065db8  cmp     rcx, rdi
0x140065dbb  jz      short loc_140065DE0
0x140065dbd  mov     eax, [rcx+2Ch]
0x140065dc0  test    al, 10h
0x140065dc2  jz      short loc_140065DE0
0x140065dc4  cmp     byte ptr [rcx+29h], 2
0x140065dc8  jb      short loc_140065DE0
0x140065dca  mov     edx, 0A5h
0x140065dcf  jmp     loc_140065C0A
0x140065dd4  mov     [r15], rsi
0x140065dd7  lea     rdi, WPP_GLOBAL_Control
0x140065dde  xor     esi, esi
0x140065de0  cmp     [rbp+57h+FileHandle], 0
0x140065de5  jz      short loc_140065DF2
0x140065de7  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140065deb  xor     edx, edx
0x140065ded  call    FveFileClose
0x140065df2  test    rsi, rsi
0x140065df5  jz      short loc_140065E0B
0x140065df7  mov     edx, 30455646h; Tag
0x140065dfc  mov     rcx, r15; P
0x140065dff  call    cs:__imp_ExFreePoolWithTag
0x140065e06  nop     dword ptr [rax+rax+00h]
0x140065e0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140065e12  cmp     rcx, rdi
0x140065e15  jz      short loc_140065E3C
0x140065e17  mov     eax, [rcx+2Ch]
0x140065e1a  test    al, 10h
0x140065e1c  jz      short loc_140065E3C
0x140065e1e  cmp     byte ptr [rcx+29h], 5
0x140065e22  jb      short loc_140065E3C
0x140065e24  mov     rcx, [rcx+18h]
0x140065e28  lea     r8, WPP_6f5eafb572893a1aac70ee2625a5ec36_Traceguids
0x140065e2f  mov     edx, 0A6h
0x140065e34  mov     r9d, ebx
0x140065e37  call    WPP_SF_d
0x140065e3c  mov     eax, ebx
0x140065e3e  mov     rcx, [rbp+57h+var_28]
0x140065e42  xor     rcx, rsp; StackCookie
0x140065e45  call    __security_check_cookie
0x140065e4a  add     rsp, 0A0h
0x140065e51  pop     r15
0x140065e53  pop     rdi
0x140065e54  pop     rsi
0x140065e55  pop     rbx
0x140065e56  pop     rbp
0x140065e57  retn
```
