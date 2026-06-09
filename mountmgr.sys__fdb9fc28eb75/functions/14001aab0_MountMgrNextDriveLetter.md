# MountMgrNextDriveLetter

- ea: `0x14001aab0`
- end: `0x14001acab`
- name: `MountMgrNextDriveLetter`
- size: `507`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400147a0`

## callees

- `0x140001ae0`
- `0x1400144a0`
- `0x140019af0`
- `0x14001aab0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001abac`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001abac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ac96`

## pseudocode

```c
__int64 __fastcall MountMgrNextDriveLetter(_QWORD *Context, _QWORD *a2, USHORT *a3)
{
  __int64 v3; // rax
  unsigned int v6; // edx
  int v7; // ecx
  int DriveLetterWorker; // ebx
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  const UNICODE_STRING *v12; // rbx
  struct _UNICODE_STRING ObjectName; // [rsp+20h] [rbp-28h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-18h] BYREF

  v3 = a2[23];
  ObjectName = 0;
  String1 = 0;
  v6 = *(_DWORD *)(v3 + 16);
  if ( v6 < 4 || *(_DWORD *)(v3 + 8) < 2u )
  {
    DriveLetterWorker = -1073741811;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v10 = 232;
      goto LABEL_25;
    }
  }
  else
  {
    a3 = (USHORT *)a2[3];
    v7 = *a3;
    if ( v7 + 2 <= v6 )
    {
      ObjectName.Length = *a3;
      ObjectName.MaximumLength = v7;
      ObjectName.Buffer = a3 + 1;
      DriveLetterWorker = QueryDeviceName(&ObjectName, &String1);
      if ( DriveLetterWorker >= 0 )
      {
        v12 = (const UNICODE_STRING *)Context[2];
        if ( v12 == (const UNICODE_STRING *)(Context + 2) )
        {
LABEL_14:
          DriveLetterWorker = -1073741772;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_27;
          }
          v10 = 235;
          v11 = 3221225524LL;
        }
        else
        {
          while ( RtlCompareUnicodeString(&String1, v12 + 5, 1u) )
          {
            v12 = *(const UNICODE_STRING **)&v12->Length;
            if ( v12 == (const UNICODE_STRING *)(Context + 2) )
              goto LABEL_14;
          }
          DriveLetterWorker = MountMgrNextDriveLetterWorker(Context);
          if ( DriveLetterWorker >= 0 )
          {
            *(_WORD *)a2[3] = 0;
            a2[7] = 2;
            goto LABEL_27;
          }
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_27;
          }
          v10 = 236;
          v11 = (unsigned int)DriveLetterWorker;
        }
      }
      else
      {
        v9 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_27;
        v10 = 234;
        v11 = (unsigned int)DriveLetterWorker;
      }
LABEL_26:
      WPP_SF_L(v9->AttachedDevice, v10, a3, v11);
      goto LABEL_27;
    }
    DriveLetterWorker = -1073741811;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v10 = 233;
LABEL_25:
      v11 = 3221225485LL;
      goto LABEL_26;
    }
  }
LABEL_27:
  if ( String1.Buffer )
    ExFreePoolWithTag(String1.Buffer, 0);
  return (unsigned int)DriveLetterWorker;
}

```

## disassembly

```asm
0x14001aab0  push    rbx
0x14001aab2  sub     rsp, 40h
0x14001aab6  mov     rax, [rdx+0B8h]
0x14001aabd  xorps   xmm0, xmm0
0x14001aac0  mov     [rsp+48h+arg_0], rsi
0x14001aac5  mov     rsi, rcx
0x14001aac8  mov     [rsp+48h+arg_10], rdi
0x14001aacd  xor     ecx, ecx
0x14001aacf  mov     rdi, rdx
0x14001aad2  mov     [rsp+48h+arg_18], r14
0x14001aad7  movups  xmmword ptr [rsp+48h+ObjectName.Length], xmm0
0x14001aadc  mov     [rsp+48h+arg_8], cx
0x14001aae1  movups  xmmword ptr [rsp+48h+String1.Length], xmm0
0x14001aae6  mov     edx, [rax+10h]
0x14001aae9  cmp     edx, 4
0x14001aaec  jb      loc_14001AC48
0x14001aaf2  cmp     dword ptr [rax+8], 2
0x14001aaf6  jb      loc_14001AC48
0x14001aafc  mov     r8, [rdi+18h]
0x14001ab00  movzx   ecx, word ptr [r8]
0x14001ab04  lea     eax, [rcx+2]
0x14001ab07  cmp     eax, edx
0x14001ab09  jbe     short loc_14001AB3C
0x14001ab0b  mov     ebx, 0C000000Dh
0x14001ab10  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab17  lea     rax, WPP_GLOBAL_Control
0x14001ab1e  cmp     rcx, rax
0x14001ab21  jz      loc_14001AC7B
0x14001ab27  mov     eax, [rcx+2Ch]
0x14001ab2a  test    al, 1
0x14001ab2c  jz      loc_14001AC7B
0x14001ab32  mov     edx, 0E9h
0x14001ab37  jmp     loc_14001AC6C
0x14001ab3c  mov     [rsp+48h+ObjectName.Length], cx
0x14001ab41  lea     rax, [r8+2]
0x14001ab45  mov     [rsp+48h+ObjectName.MaximumLength], cx
0x14001ab4a  lea     rdx, [rsp+48h+String1]; StringOut
0x14001ab4f  lea     rcx, [rsp+48h+ObjectName]; ObjectName
0x14001ab54  mov     [rsp+48h+ObjectName.Buffer], rax
0x14001ab59  call    QueryDeviceName
0x14001ab5e  mov     ebx, eax
0x14001ab60  test    eax, eax
0x14001ab62  jns     short loc_14001AB93
0x14001ab64  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab6b  lea     rax, WPP_GLOBAL_Control
0x14001ab72  cmp     rcx, rax
0x14001ab75  jz      loc_14001AC7B
0x14001ab7b  mov     eax, [rcx+2Ch]
0x14001ab7e  test    al, 1
0x14001ab80  jz      loc_14001AC7B
0x14001ab86  mov     edx, 0EAh
0x14001ab8b  mov     r9d, ebx
0x14001ab8e  jmp     loc_14001AC72
0x14001ab93  mov     rbx, [rsi+10h]
0x14001ab97  lea     r14, [rsi+10h]
0x14001ab9b  cmp     rbx, r14
0x14001ab9e  jz      short loc_14001ABC4
0x14001aba0  lea     rdx, [rbx+50h]; String2
0x14001aba4  mov     r8b, 1; CaseInSensitive
0x14001aba7  lea     rcx, [rsp+48h+String1]; String1
0x14001abac  call    cs:__imp_RtlCompareUnicodeString
0x14001abb3  nop     dword ptr [rax+rax+00h]
0x14001abb8  test    eax, eax
0x14001abba  jz      short loc_14001ABF8
0x14001abbc  mov     rbx, [rbx]
0x14001abbf  cmp     rbx, r14
0x14001abc2  jnz     short loc_14001ABA0
0x14001abc4  mov     ebx, 0C0000034h
0x14001abc9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001abd0  lea     rax, WPP_GLOBAL_Control
0x14001abd7  cmp     rcx, rax
0x14001abda  jz      loc_14001AC7B
0x14001abe0  mov     eax, [rcx+2Ch]
0x14001abe3  test    al, 1
0x14001abe5  jz      loc_14001AC7B
0x14001abeb  mov     edx, 0EBh
0x14001abf0  mov     r9d, 0C0000034h
0x14001abf6  jmp     short loc_14001AC72
0x14001abf8  lea     r8, [rsp+48h+arg_8]
0x14001abfd  mov     rdx, rbx
0x14001ac00  mov     rcx, rsi; Context
0x14001ac03  call    MountMgrNextDriveLetterWorker
0x14001ac08  mov     ebx, eax
0x14001ac0a  test    eax, eax
0x14001ac0c  jns     short loc_14001AC32
0x14001ac0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac15  lea     rax, WPP_GLOBAL_Control
0x14001ac1c  cmp     rcx, rax
0x14001ac1f  jz      short loc_14001AC7B
0x14001ac21  mov     eax, [rcx+2Ch]
0x14001ac24  test    al, 1
0x14001ac26  jz      short loc_14001AC7B
0x14001ac28  mov     edx, 0ECh
0x14001ac2d  mov     r9d, ebx
0x14001ac30  jmp     short loc_14001AC72
0x14001ac32  mov     rcx, [rdi+18h]
0x14001ac36  movzx   eax, [rsp+48h+arg_8]
0x14001ac3b  mov     [rcx], ax
0x14001ac3e  mov     qword ptr [rdi+38h], 2
0x14001ac46  jmp     short loc_14001AC7B
0x14001ac48  mov     ebx, 0C000000Dh
0x14001ac4d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ac54  lea     rax, WPP_GLOBAL_Control
0x14001ac5b  cmp     rcx, rax
0x14001ac5e  jz      short loc_14001AC7B
0x14001ac60  mov     eax, [rcx+2Ch]
0x14001ac63  test    al, 1
0x14001ac65  jz      short loc_14001AC7B
0x14001ac67  mov     edx, 0E8h
0x14001ac6c  mov     r9d, 0C000000Dh
0x14001ac72  mov     rcx, [rcx+18h]
0x14001ac76  call    WPP_SF_L
0x14001ac7b  mov     rcx, [rsp+48h+String1.Buffer]; P
0x14001ac80  mov     r14, [rsp+48h+arg_18]
0x14001ac85  mov     rdi, [rsp+48h+arg_10]
0x14001ac8a  mov     rsi, [rsp+48h+arg_0]
0x14001ac8f  test    rcx, rcx
0x14001ac92  jz      short loc_14001ACA2
0x14001ac94  xor     edx, edx; Tag
0x14001ac96  call    cs:__imp_ExFreePoolWithTag
0x14001ac9d  nop     dword ptr [rax+rax+00h]
0x14001aca2  mov     eax, ebx
0x14001aca4  add     rsp, 40h
0x14001aca8  pop     rbx
0x14001aca9  retn
```
