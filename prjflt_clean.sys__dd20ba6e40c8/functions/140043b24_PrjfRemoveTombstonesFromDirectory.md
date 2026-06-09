# PrjfRemoveTombstonesFromDirectory

- ea: `0x140043b24`
- end: `0x140043d81`
- name: `PrjfRemoveTombstonesFromDirectory`
- size: `605`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14003cc14`
- `0x14003d620`

## callees

- `0x14000d128`
- `0x14003a4d0`
- `0x14003d2c8`
- `0x140042658`
- `0x140043b24`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043d30`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043d30`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140043c14`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140043c32`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140043c14`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140043c32`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043bc3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140043bc3`
- `ntoskrnl!ObfDereferenceObject` at `0x140043d5a`
- `ntoskrnl!ObfDereferenceObject` at `0x140043d5a`
- `ntoskrnl!ExAllocatePool2` at `0x140043b72`
- `ntoskrnl!ExAllocatePool2` at `0x140043b72`
- `FLTMGR!FltClose` at `0x140043d45`
- `FLTMGR!FltClose` at `0x140043d45`

## pseudocode

```c
__int64 __fastcall PrjfRemoveTombstonesFromDirectory(PFLT_INSTANCE Instance, PFILE_OBJECT FileObject)
{
  unsigned int *Pool2; // rsi
  int v6; // ebx
  int v7; // eax
  int v8; // edx
  int v9; // r8d
  unsigned int *i; // rdi
  __int64 v11; // rax
  HANDLE FileHandle; // [rsp+60h] [rbp+17h] BYREF
  UNICODE_STRING String1; // [rsp+68h] [rbp+1Fh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp+2Fh] BYREF
  char v15; // [rsp+C0h] [rbp+77h] BYREF
  PVOID Object; // [rsp+C8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  Object = 0;
  DestinationString = 0;
  String1 = 0;
  Pool2 = (unsigned int *)ExAllocatePool2(256, 0x10000, 1701071440);
  if ( !Pool2 )
    return 3221225626LL;
  v6 = PrjfReopenFile(Instance, FileObject, 0x80000000, &FileHandle, (PFILE_OBJECT *)&Object);
  if ( v6 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"*");
    v7 = PrjfEnumerateDirectory(
           (_DWORD)Instance,
           (_DWORD)Object,
           12,
           (unsigned int)&DestinationString,
           0,
           1,
           0x10000,
           (__int64)Pool2,
           (__int64)&v15);
LABEL_12:
    v6 = v7;
    if ( v7 >= 0 )
    {
      for ( i = Pool2; ; i = (unsigned int *)((char *)i + v11) )
      {
        String1.Buffer = (PWSTR)(i + 3);
        String1.Length = *((_WORD *)i + 4);
        String1.MaximumLength = String1.Length;
        if ( !RtlEqualUnicodeString(&String1, &stru_1400155A0, 1u)
          && !RtlEqualUnicodeString(&String1, &stru_140015590, 1u) )
        {
          v6 = PrjfDeleteTombstoneIfExists(Instance, (PFILE_OBJECT)Object, (__int64)FileHandle, &String1);
          if ( v6 < 0 )
            break;
        }
        v11 = *i;
        if ( !(_DWORD)v11 )
        {
          v7 = PrjfEnumerateDirectory(
                 (_DWORD)Instance,
                 (_DWORD)Object,
                 12,
                 (unsigned int)&DestinationString,
                 0,
                 0,
                 0x10000,
                 (__int64)Pool2,
                 (__int64)&v15);
          goto LABEL_12;
        }
      }
    }
    else if ( v7 == -2147483642 )
    {
      v6 = 0;
    }
    else if ( (BYTE2(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = BYTE2(xmmword_14001A3D0) & 8;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        531,
        v8,
        v9,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        19,
        21,
        (__int64)&WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\tombstone.c",
        47,
        v7);
    }
  }
  ExFreePoolWithTag(Pool2, 0x65644A50u);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140043b24  mov     [rsp-8+arg_0], rbx
0x140043b29  mov     [rsp-8+arg_8], rsi
0x140043b2e  push    rbp
0x140043b2f  push    rdi
0x140043b30  push    r14
0x140043b32  lea     rbp, [rsp-47h]
0x140043b37  sub     rsp, 90h
0x140043b3e  mov     rbx, rdx
0x140043b41  mov     [rbp+57h+FileHandle], 0
0x140043b49  mov     r14, rcx
0x140043b4c  mov     [rbp+57h+Object], 0
0x140043b54  xorps   xmm0, xmm0
0x140043b57  xorps   xmm1, xmm1
0x140043b5a  mov     edx, 10000h
0x140043b5f  mov     ecx, 100h
0x140043b64  mov     r8d, 65644A50h
0x140043b6a  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140043b6e  movups  xmmword ptr [rbp+57h+String1.Length], xmm1
0x140043b72  call    cs:__imp_ExAllocatePool2
0x140043b79  nop     dword ptr [rax+rax+00h]
0x140043b7e  mov     rsi, rax
0x140043b81  test    rax, rax
0x140043b84  jnz     short loc_140043B90
0x140043b86  mov     eax, 0C000009Ah
0x140043b8b  jmp     loc_140043D68
0x140043b90  lea     rax, [rbp+57h+Object]
0x140043b94  mov     r8d, 80000000h; DesiredAccess
0x140043b9a  lea     r9, [rbp+57h+FileHandle]; FileHandle
0x140043b9e  mov     [rsp+0A0h+var_80], rax; PFILE_OBJECT *
0x140043ba3  mov     rdx, rbx; FileObject
0x140043ba6  mov     rcx, r14; Instance
0x140043ba9  call    PrjfReopenFile
0x140043bae  mov     ebx, eax
0x140043bb0  test    eax, eax
0x140043bb2  js      loc_140043D28
0x140043bb8  lea     rdx, asc_140015960; "*"
0x140043bbf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140043bc3  call    cs:__imp_RtlInitUnicodeString
0x140043bca  nop     dword ptr [rax+rax+00h]
0x140043bcf  lea     rax, [rbp+57h+arg_10]
0x140043bd3  mov     [rsp+0A0h+var_60], rax
0x140043bd8  mov     [rsp+0A0h+var_68], rsi
0x140043bdd  mov     [rsp+0A0h+var_70], 10000h
0x140043be5  mov     byte ptr [rsp+0A0h+var_78], 1
0x140043bea  jmp     loc_140043C86
0x140043bef  mov     rdi, rsi
0x140043bf2  lea     rax, [rdi+0Ch]
0x140043bf6  mov     r8b, 1; CaseInSensitive
0x140043bf9  mov     [rbp+57h+String1.Buffer], rax
0x140043bfd  lea     rdx, stru_1400155A0; String2
0x140043c04  movzx   eax, word ptr [rdi+8]
0x140043c08  lea     rcx, [rbp+57h+String1]; String1
0x140043c0c  mov     [rbp+57h+String1.Length], ax
0x140043c10  mov     [rbp+57h+String1.MaximumLength], ax
0x140043c14  call    cs:__imp_RtlEqualUnicodeString
0x140043c1b  nop     dword ptr [rax+rax+00h]
0x140043c20  test    al, al
0x140043c22  jnz     short loc_140043C60
0x140043c24  mov     r8b, 1; CaseInSensitive
0x140043c27  lea     rdx, stru_140015590; String2
0x140043c2e  lea     rcx, [rbp+57h+String1]; String1
0x140043c32  call    cs:__imp_RtlEqualUnicodeString
0x140043c39  nop     dword ptr [rax+rax+00h]
0x140043c3e  test    al, al
0x140043c40  jnz     short loc_140043C60
0x140043c42  mov     r8, [rbp+57h+FileHandle]
0x140043c46  lea     r9, [rbp+57h+String1]
0x140043c4a  mov     rdx, [rbp+57h+Object]; FileObject
0x140043c4e  mov     rcx, r14; Instance
0x140043c51  call    PrjfDeleteTombstoneIfExists
0x140043c56  mov     ebx, eax
0x140043c58  test    eax, eax
0x140043c5a  js      loc_140043D28
0x140043c60  mov     eax, [rdi]
0x140043c62  test    eax, eax
0x140043c64  jz      short loc_140043C6B
0x140043c66  add     rdi, rax
0x140043c69  jmp     short loc_140043BF2
0x140043c6b  lea     rax, [rbp+57h+arg_10]
0x140043c6f  mov     [rsp+0A0h+var_60], rax
0x140043c74  mov     [rsp+0A0h+var_68], rsi
0x140043c79  mov     [rsp+0A0h+var_70], 10000h
0x140043c81  mov     byte ptr [rsp+0A0h+var_78], 0
0x140043c86  mov     rdx, [rbp+57h+Object]
0x140043c8a  lea     r9, [rbp+57h+DestinationString]
0x140043c8e  mov     r8d, 0Ch
0x140043c94  mov     dword ptr [rsp+0A0h+var_80], 0
0x140043c9c  mov     rcx, r14
0x140043c9f  call    PrjfEnumerateDirectory
0x140043ca4  mov     ebx, eax
0x140043ca6  test    eax, eax
0x140043ca8  jns     loc_140043BEF
0x140043cae  cmp     eax, 80000006h
0x140043cb3  jnz     short loc_140043CB9
0x140043cb5  xor     ebx, ebx
0x140043cb7  jmp     short loc_140043D28
0x140043cb9  mov     dl, byte ptr cs:xmmword_14001A3D0+2
0x140043cbf  lea     rax, WPP_RECORDER_INITIALIZED
0x140043cc6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140043ccd  setnz   r8b
0x140043cd1  and     dl, 8
0x140043cd4  jnz     short loc_140043CDB
0x140043cd6  test    r8b, r8b
0x140043cd9  jz      short loc_140043D28
0x140043cdb  mov     r9, cs:WPP_GLOBAL_Control
0x140043ce2  lea     rax, aOnecoreBaseFsG_6; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140043ce9  mov     [rsp+0A0h+var_50], ebx
0x140043ced  mov     ecx, 213h
0x140043cf2  mov     [rsp+0A0h+var_58], 32Fh
0x140043cfa  mov     [rsp+0A0h+var_60], rax
0x140043cff  lea     rax, WPP_3f08b24f959433411191d1ccab0ccd17_Traceguids
0x140043d06  mov     r9, [r9+40h]
0x140043d0a  mov     [rsp+0A0h+var_68], rax
0x140043d0f  mov     word ptr [rsp+0A0h+var_70], 15h
0x140043d16  mov     [rsp+0A0h+var_78], 13h
0x140043d1e  mov     byte ptr [rsp+0A0h+var_80], 2
0x140043d23  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140043d28  mov     edx, 65644A50h; Tag
0x140043d2d  mov     rcx, rsi; P
0x140043d30  call    cs:__imp_ExFreePoolWithTag
0x140043d37  nop     dword ptr [rax+rax+00h]
0x140043d3c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x140043d40  test    rcx, rcx
0x140043d43  jz      short loc_140043D51
0x140043d45  call    cs:__imp_FltClose
0x140043d4c  nop     dword ptr [rax+rax+00h]
0x140043d51  mov     rcx, [rbp+57h+Object]; Object
0x140043d55  test    rcx, rcx
0x140043d58  jz      short loc_140043D66
0x140043d5a  call    cs:__imp_ObfDereferenceObject
0x140043d61  nop     dword ptr [rax+rax+00h]
0x140043d66  mov     eax, ebx
0x140043d68  lea     r11, [rsp+0A0h+var_10]
0x140043d70  mov     rbx, [r11+20h]
0x140043d74  mov     rsi, [r11+28h]
0x140043d78  mov     rsp, r11
0x140043d7b  pop     r14
0x140043d7d  pop     rdi
0x140043d7e  pop     rbp
0x140043d7f  retn
```
