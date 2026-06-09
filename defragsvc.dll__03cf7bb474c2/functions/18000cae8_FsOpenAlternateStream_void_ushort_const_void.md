# FsOpenAlternateStream(void *,ushort const *,void * *)

- ea: `0x18000cae8`
- end: `0x18000cd41`
- name: `?FsOpenAlternateStream@@YAJPEAXPEBGPEAPEAX@Z`
- size: `601`
- prototype: `int(void *, const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cf94`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18000cae8`
- `0x180038c3c`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000cbf1`
- `ntdll!NtOpenFile` at `0x18000cbf1`
- `ntdll!RtlInitUnicodeString` at `0x18000cb96`
- `ntdll!RtlInitUnicodeString` at `0x18000cb96`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cc64`

## string_xrefs

- `0x18000cb17`: `FsOpenAlternateStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FsOpenAlternateStream(void *a1, const unsigned __int16 *a2, void **a3)
{
  __int16 v6; // ax
  unsigned int v7; // ebx
  NTSTATUS v8; // eax
  unsigned int v10; // [rsp+30h] [rbp-49h] BYREF
  __int16 v11; // [rsp+34h] [rbp-45h]
  __int16 v12; // [rsp+36h] [rbp-43h]
  _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-11h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-1h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp+2Fh] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "FsOpenAlternateStream", 445, 1);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  DestinationString = 0;
  FileHandle = (void *)-1LL;
  v6 = 455;
  if ( a1 == (void *)-1LL || (v11 = 455, v6 = 456, !a2) || (v11 = 456, v6 = 457, !a3) )
  {
    v7 = -2147024809;
LABEL_4:
    v12 = v6;
    v10 = v7;
    goto LABEL_13;
  }
  v10 = 0;
  v11 = 457;
  *a3 = (void *)-1LL;
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(FileHandle);
    FileHandle = (void *)-1LL;
  }
  v8 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x204020u);
  if ( v8 == -1073741810 || v8 == -1073741202 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
    }
    v7 = -1996488687;
    v6 = 480;
    goto LABEL_4;
  }
  if ( v8 == -1073741774 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
    }
    v7 = -1996488675;
    v6 = 485;
    goto LABEL_4;
  }
  if ( v8 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
    }
    v7 = -1996488674;
    v6 = 490;
    goto LABEL_4;
  }
  *a3 = FileHandle;
  FileHandle = (void *)-1LL;
  v7 = v10;
LABEL_13:
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(FileHandle);
    FileHandle = (void *)-1LL;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10);
  return v7;
}

```

## disassembly

```asm
0x18000cae8  mov     [rsp-8+arg_8], rbx
0x18000caed  mov     [rsp-8+arg_10], rsi
0x18000caf2  push    rbp
0x18000caf3  push    rdi
0x18000caf4  push    r14
0x18000caf6  lea     rbp, [rsp-47h]
0x18000cafb  sub     rsp, 0C0h
0x18000cb02  mov     rbx, r8
0x18000cb05  mov     rdi, rdx
0x18000cb08  mov     rsi, rcx
0x18000cb0b  mov     r9d, 1; unsigned __int16
0x18000cb11  mov     r8d, 1BDh; unsigned __int16
0x18000cb17  lea     rdx, aFsopenalternat; "FsOpenAlternateStream"
0x18000cb1e  lea     rcx, [rbp+57h+var_A0]; this
0x18000cb22  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000cb27  nop
0x18000cb28  xorps   xmm0, xmm0
0x18000cb2b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000cb2f  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000cb33  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cb37  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000cb3b  xorps   xmm1, xmm1
0x18000cb3e  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000cb42  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000cb46  mov     [rbp+57h+FileHandle], r14
0x18000cb4a  mov     eax, 1C7h
0x18000cb4f  cmp     rsi, r14
0x18000cb52  jz      short loc_18000CB62
0x18000cb54  mov     [rbp+57h+var_9C], ax
0x18000cb58  mov     eax, 1C8h
0x18000cb5d  test    rdi, rdi
0x18000cb60  jnz     short loc_18000CB73
0x18000cb62  mov     ebx, 80070057h
0x18000cb67  mov     [rbp+57h+var_9A], ax
0x18000cb6b  mov     [rbp+57h+var_A0], ebx
0x18000cb6e  jmp     loc_18000CC26
0x18000cb73  mov     [rbp+57h+var_9C], ax
0x18000cb77  mov     eax, 1C9h
0x18000cb7c  test    rbx, rbx
0x18000cb7f  jz      short loc_18000CB62
0x18000cb81  mov     [rbp+57h+var_A0], 0
0x18000cb88  mov     [rbp+57h+var_9C], ax
0x18000cb8c  mov     [rbx], r14
0x18000cb8f  mov     rdx, rdi; SourceString
0x18000cb92  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000cb96  call    cs:__imp_RtlInitUnicodeString
0x18000cb9c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000cba3  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x18000cba7  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000cbae  lea     rax, [rbp+57h+DestinationString]
0x18000cbb2  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000cbb6  xorps   xmm0, xmm0
0x18000cbb9  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000cbbe  mov     rcx, [rbp+57h+FileHandle]; hObject
0x18000cbc2  lea     rax, [rcx-1]
0x18000cbc6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000cbca  jbe     loc_18000CC64
0x18000cbd0  mov     [rsp+0D0h+OpenOptions], 204020h; OpenOptions
0x18000cbd8  mov     [rsp+0D0h+ShareAccess], 7; ShareAccess
0x18000cbe0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000cbe4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000cbe8  mov     edx, 100080h; DesiredAccess
0x18000cbed  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000cbf1  call    cs:__imp_NtOpenFile
0x18000cbf7  cmp     eax, 0C000000Eh
0x18000cbfc  jz      short loc_18000CC73
0x18000cbfe  cmp     eax, 0C000026Eh
0x18000cc03  jz      short loc_18000CC73
0x18000cc05  cmp     eax, 0C0000032h
0x18000cc0a  jz      loc_18000CC99
0x18000cc10  test    eax, eax
0x18000cc12  js      loc_18000CCD9
0x18000cc18  mov     rax, [rbp+57h+FileHandle]
0x18000cc1c  mov     [rbx], rax
0x18000cc1f  mov     [rbp+57h+FileHandle], r14
0x18000cc23  mov     ebx, [rbp+57h+var_A0]
0x18000cc26  mov     rcx, [rbp+57h+FileHandle]; hObject
0x18000cc2a  lea     rdx, [rcx-1]
0x18000cc2e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000cc32  jbe     short loc_18000CC57
0x18000cc34  lea     rcx, [rbp+57h+var_A0]; this
0x18000cc38  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000cc3d  mov     eax, ebx
0x18000cc3f  lea     r11, [rsp+0D0h+var_10]
0x18000cc47  mov     rbx, [r11+28h]
0x18000cc4b  mov     rsi, [r11+30h]
0x18000cc4f  mov     rsp, r11
0x18000cc52  pop     r14
0x18000cc54  pop     rdi
0x18000cc55  pop     rbp
0x18000cc56  retn
0x18000cc57  call    cs:__imp_CloseHandle
0x18000cc5d  nop
0x18000cc5e  mov     [rbp+57h+FileHandle], r14
0x18000cc62  jmp     short loc_18000CC34
0x18000cc64  call    cs:__imp_CloseHandle
0x18000cc6a  mov     [rbp+57h+FileHandle], r14
0x18000cc6e  jmp     loc_18000CBD0
0x18000cc73  lea     rax, WPP_GLOBAL_Control
0x18000cc7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cc81  cmp     rcx, rax
0x18000cc84  jnz     loc_18000CD19
0x18000cc8a  mov     ebx, 89000011h
0x18000cc8f  mov     eax, 1E0h
0x18000cc94  jmp     loc_18000CB67
0x18000cc99  lea     rax, WPP_GLOBAL_Control
0x18000cca0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cca7  cmp     rcx, rax
0x18000ccaa  jz      short loc_18000CCCA
0x18000ccac  test    dword ptr [rcx+1Ch], 2000000h
0x18000ccb3  jz      short loc_18000CCCA
0x18000ccb5  mov     edx, 11h
0x18000ccba  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000ccc1  mov     rcx, [rcx+10h]
0x18000ccc5  call    WPP_SF_
0x18000ccca  mov     ebx, 8900001Dh
0x18000cccf  mov     eax, 1E5h
0x18000ccd4  jmp     loc_18000CB67
0x18000ccd9  lea     rax, WPP_GLOBAL_Control
0x18000cce0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cce7  cmp     rcx, rax
0x18000ccea  jz      short loc_18000CD0A
0x18000ccec  test    dword ptr [rcx+1Ch], 2000000h
0x18000ccf3  jz      short loc_18000CD0A
0x18000ccf5  mov     edx, 12h
0x18000ccfa  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000cd01  mov     rcx, [rcx+10h]
0x18000cd05  call    WPP_SF_
0x18000cd0a  mov     ebx, 8900001Eh
0x18000cd0f  mov     eax, 1EAh
0x18000cd14  jmp     loc_18000CB67
0x18000cd19  test    dword ptr [rcx+1Ch], 2000000h
0x18000cd20  jz      loc_18000CC8A
0x18000cd26  mov     edx, 10h
0x18000cd2b  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000cd32  mov     rcx, [rcx+10h]
0x18000cd36  call    WPP_SF_
0x18000cd3b  jmp     loc_18000CC8A
```
