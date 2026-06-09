# CreateTermDD(void * *,void *,ulong,char const *,int)

- ea: `0x14001b210`
- end: `0x14001b4c8`
- name: `?CreateTermDD@@YAJPEAPEAXPEAXKPEBDH@Z`
- size: `696`
- prototype: `__int64 __fastcall(void **, void *, ULONG, const char *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001b144`
- `0x14001bf2c`

## callees

- `0x140001e30`
- `0x14000324c`
- `0x140006480`
- `0x14001b210`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b37d`
- `ntoskrnl!ExAllocatePool2` at `0x14001b37d`
- `ntoskrnl!ZwCreateFile` at `0x14001b44a`
- `ntoskrnl!ZwCreateFile` at `0x14001b44a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b2a0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b2de`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b2a0`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14001b2de`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001b324`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x14001b324`

## string_xrefs

- `0x14001b3a8`: `TermddOpenPacketXX`

## pseudocode

```c
__int64 __fastcall CreateTermDD(void **a1, void *a2, ULONG a3, const char *a4, int a5)
{
  NTSTATUS appended; // ebx
  __int64 Pool2; // rax
  __int64 EaBuffer; // rdi
  __int64 v12; // rdx
  _BYTE *v13; // rcx
  __int64 v14; // rax
  _BYTE *v15; // rax
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING String; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  char v22; // [rsp+D0h] [rbp-30h] BYREF

  Destination.Buffer = (wchar_t *)&v22;
  FileHandle = 0;
  *(_QWORD *)&Destination.Length = 34078720;
  String = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  if ( a5 )
  {
    appended = RtlAppendUnicodeToString(&Destination, L"\\Device\\FakeTermdd\\");
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids);
  }
  else
  {
    appended = RtlAppendUnicodeToString(&Destination, L"\\Device\\Termdd\\");
  }
  if ( appended >= 0 )
  {
    String.Buffer = (wchar_t *)((char *)Destination.Buffer + Destination.Length);
    String.Length = 0;
    String.MaximumLength = Destination.MaximumLength - Destination.Length;
    appended = RtlIntegerToUnicodeString(a3, 0xAu, &String);
    if ( appended >= 0 )
    {
      Destination.Length += String.Length;
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      Pool2 = ExAllocatePool2(256, 54, 1917088324);
      EaBuffer = Pool2;
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 0;
        v12 = 8;
        *(_WORD *)(Pool2 + 4) = 4608;
        v13 = (_BYTE *)(Pool2 + 43);
        strcpy((char *)(Pool2 + 8), "TermddOpenPacketXX");
        v14 = 2147483646;
        *(_WORD *)(EaBuffer + 6) = 24;
        *(_QWORD *)(EaBuffer + 27) = a2;
        *(_DWORD *)(EaBuffer + 35) = 1;
        *(_DWORD *)(EaBuffer + 39) = 5;
        do
        {
          if ( !v14 )
            break;
          if ( !*a4 )
            break;
          *v13++ = *a4++;
          --v14;
          --v12;
        }
        while ( v12 );
        v15 = v13 - 1;
        if ( v12 )
          v15 = v13;
        *v15 = 0;
        appended = ZwCreateFile(
                     &FileHandle,
                     0xC0000000,
                     &ObjectAttributes,
                     &IoStatusBlock,
                     0,
                     0x80u,
                     0,
                     3u,
                     4u,
                     (PVOID)EaBuffer,
                     0x36u);
        operator delete((void *)EaBuffer);
        if ( appended >= 0 )
          *a1 = FileHandle;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids);
        return (unsigned int)-1073741670;
      }
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x14001b210  mov     [rsp-8+arg_8], rbx
0x14001b215  mov     [rsp-8+arg_18], rsi
0x14001b21a  push    rbp
0x14001b21b  push    rdi
0x14001b21c  push    r13
0x14001b21e  push    r14
0x14001b220  push    r15
0x14001b222  lea     rbp, [rsp-1F0h]
0x14001b22a  sub     rsp, 2F0h
0x14001b231  mov     rax, cs:__security_cookie
0x14001b238  xor     rax, rsp
0x14001b23b  mov     [rbp+210h+var_30], rax
0x14001b242  cmp     [rbp+210h+arg_20], 0
0x14001b249  lea     rax, [rbp+210h+var_240]
0x14001b24d  xorps   xmm1, xmm1
0x14001b250  mov     [rsp+310h+Destination.Buffer], rax
0x14001b255  xorps   xmm0, xmm0
0x14001b258  mov     [rsp+310h+FileHandle], 0
0x14001b261  mov     r14, rcx
0x14001b264  mov     qword ptr [rsp+310h+Destination.Length], 2080000h
0x14001b26d  movups  xmmword ptr [rsp+310h+String.Length], xmm0
0x14001b272  mov     rsi, r9
0x14001b275  mov     edi, r8d
0x14001b278  movups  xmmword ptr [rbp+210h+ObjectAttributes.Length], xmm1
0x14001b27c  mov     r15, rdx
0x14001b27f  lea     r13, WPP_GLOBAL_Control
0x14001b286  movups  xmmword ptr [rbp+210h+ObjectAttributes.ObjectName], xmm1
0x14001b28a  lea     rcx, [rsp+310h+Destination]; Destination
0x14001b28f  movups  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm1
0x14001b293  movups  xmmword ptr [rbp+210h+IoStatusBlock], xmm0
0x14001b297  jz      short loc_14001B2D7
0x14001b299  lea     rdx, Source; "\\Device\\FakeTermdd\\"
0x14001b2a0  call    cs:__imp_RtlAppendUnicodeToString
0x14001b2a7  nop     dword ptr [rax+rax+00h]
0x14001b2ac  mov     ebx, eax
0x14001b2ae  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b2b5  cmp     rcx, r13
0x14001b2b8  jz      short loc_14001B2EC
0x14001b2ba  cmp     byte ptr [rcx+29h], 2
0x14001b2be  jb      short loc_14001B2EC
0x14001b2c0  mov     rcx, [rcx+18h]
0x14001b2c4  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x14001b2cb  mov     edx, 11h
0x14001b2d0  call    WPP_SF_
0x14001b2d5  jmp     short loc_14001B2EC
0x14001b2d7  lea     rdx, aDeviceTermdd; "\\Device\\Termdd\\"
0x14001b2de  call    cs:__imp_RtlAppendUnicodeToString
0x14001b2e5  nop     dword ptr [rax+rax+00h]
0x14001b2ea  mov     ebx, eax
0x14001b2ec  test    ebx, ebx
0x14001b2ee  js      loc_14001B49A
0x14001b2f4  movzx   eax, [rsp+310h+Destination.Length]
0x14001b2f9  lea     r8, [rsp+310h+String]; String
0x14001b2fe  add     rax, [rsp+310h+Destination.Buffer]
0x14001b303  mov     edx, 0Ah; Base
0x14001b308  mov     [rbp+210h+String.Buffer], rax
0x14001b30c  mov     ecx, edi; Value
0x14001b30e  xor     eax, eax
0x14001b310  mov     [rsp+310h+String.Length], ax
0x14001b315  movzx   eax, [rsp+310h+Destination.MaximumLength]
0x14001b31a  sub     ax, [rsp+310h+Destination.Length]
0x14001b31f  mov     [rsp+310h+String.MaximumLength], ax
0x14001b324  call    cs:__imp_RtlIntegerToUnicodeString
0x14001b32b  nop     dword ptr [rax+rax+00h]
0x14001b330  mov     ebx, eax
0x14001b332  test    eax, eax
0x14001b334  js      loc_14001B49A
0x14001b33a  movzx   eax, [rsp+310h+String.Length]
0x14001b33f  xorps   xmm0, xmm0
0x14001b342  add     [rsp+310h+Destination.Length], ax
0x14001b347  mov     ebx, 36h ; '6'
0x14001b34c  lea     rax, [rsp+310h+Destination]
0x14001b351  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x14001b358  mov     r8d, 72447244h
0x14001b35e  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x14001b362  mov     edx, ebx
0x14001b364  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x14001b36c  mov     ecx, 100h
0x14001b371  mov     [rbp+210h+ObjectAttributes.Attributes], 240h
0x14001b378  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x14001b37d  call    cs:__imp_ExAllocatePool2
0x14001b384  nop     dword ptr [rax+rax+00h]
0x14001b389  mov     rdi, rax
0x14001b38c  test    rax, rax
0x14001b38f  jz      loc_14001B46E
0x14001b395  mov     dword ptr [rax], 0
0x14001b39b  lea     edx, [rbx-2Eh]
0x14001b39e  mov     word ptr [rax+4], 1200h
0x14001b3a4  lea     rcx, [rdi+2Bh]
0x14001b3a8  movups  xmm0, xmmword ptr cs:aTermddopenpack; "TermddOpenPacketXX"
0x14001b3af  movups  xmmword ptr [rax+8], xmm0
0x14001b3b3  mov     eax, dword ptr cs:aTermddopenpack+0Fh; "tXX"
0x14001b3b9  mov     [rdi+17h], eax
0x14001b3bc  mov     eax, 7FFFFFFEh
0x14001b3c1  mov     word ptr [rdi+6], 18h
0x14001b3c7  mov     [rdi+1Bh], r15
0x14001b3cb  mov     dword ptr [rdi+23h], 1
0x14001b3d2  mov     dword ptr [rdi+27h], 5
0x14001b3d9  test    rax, rax
0x14001b3dc  jz      short loc_14001B3F8
0x14001b3de  mov     r8b, [rsi]
0x14001b3e1  test    r8b, r8b
0x14001b3e4  jz      short loc_14001B3F8
0x14001b3e6  mov     [rcx], r8b
0x14001b3e9  inc     rsi
0x14001b3ec  inc     rcx
0x14001b3ef  dec     rax
0x14001b3f2  sub     rdx, 1
0x14001b3f6  jnz     short loc_14001B3D9
0x14001b3f8  mov     [rsp+310h+EaLength], ebx; EaLength
0x14001b3fc  lea     rax, [rcx-1]
0x14001b400  mov     [rsp+310h+EaBuffer], rdi; EaBuffer
0x14001b405  lea     r9, [rbp+210h+IoStatusBlock]; IoStatusBlock
0x14001b409  mov     [rsp+310h+CreateOptions], 4; CreateOptions
0x14001b411  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x14001b415  test    rdx, rdx
0x14001b418  mov     [rsp+310h+CreateDisposition], 3; CreateDisposition
0x14001b420  mov     [rsp+310h+ShareAccess], 0; ShareAccess
0x14001b428  mov     edx, 0C0000000h; DesiredAccess
0x14001b42d  cmovnz  rax, rcx
0x14001b431  mov     [rsp+310h+FileAttributes], 80h; FileAttributes
0x14001b439  lea     rcx, [rsp+310h+FileHandle]; FileHandle
0x14001b43e  mov     [rsp+310h+AllocationSize], 0; AllocationSize
0x14001b447  mov     byte ptr [rax], 0
0x14001b44a  call    cs:__imp_ZwCreateFile
0x14001b451  nop     dword ptr [rax+rax+00h]
0x14001b456  mov     rcx, rdi; void *
0x14001b459  mov     ebx, eax
0x14001b45b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001b460  test    ebx, ebx
0x14001b462  js      short loc_14001B49A
0x14001b464  mov     rax, [rsp+310h+FileHandle]
0x14001b469  mov     [r14], rax
0x14001b46c  jmp     short loc_14001B49A
0x14001b46e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b475  cmp     rcx, r13
0x14001b478  jz      short loc_14001B495
0x14001b47a  cmp     byte ptr [rcx+29h], 2
0x14001b47e  jb      short loc_14001B495
0x14001b480  mov     rcx, [rcx+18h]
0x14001b484  lea     r8, WPP_8ecd16b07aab3e5d2130d6f744ebb8b4_Traceguids
0x14001b48b  mov     edx, 12h
0x14001b490  call    WPP_SF_
0x14001b495  mov     ebx, 0C000009Ah
0x14001b49a  mov     eax, ebx
0x14001b49c  mov     rcx, [rbp+210h+var_30]
0x14001b4a3  xor     rcx, rsp; StackCookie
0x14001b4a6  call    __security_check_cookie
0x14001b4ab  lea     r11, [rsp+310h+var_20]
0x14001b4b3  mov     rbx, [r11+38h]
0x14001b4b7  mov     rsi, [r11+48h]
0x14001b4bb  mov     rsp, r11
0x14001b4be  pop     r15
0x14001b4c0  pop     r14
0x14001b4c2  pop     r13
0x14001b4c4  pop     rdi
0x14001b4c5  pop     rbp
0x14001b4c6  retn
```
