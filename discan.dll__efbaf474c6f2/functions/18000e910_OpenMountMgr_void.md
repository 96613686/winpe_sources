# OpenMountMgr(void * *)

- ea: `0x18000e910`
- end: `0x18000ea77`
- name: `?OpenMountMgr@@YAJPEAPEAX@Z`
- size: `359`
- prototype: `__int64 __fastcall(PHANDLE FileHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000f1dc`
- `0x1800142d8`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x18000e910`
- `0x1800129b0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000ea0d`
- `ntdll!NtOpenFile` at `0x18000ea0d`

## string_xrefs

- `0x18000e928`: `OpenMountMgr`

## pseudocode

```c
__int64 __fastcall OpenMountMgr(PHANDLE FileHandle)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v3; // r8
  NTSTATUS v4; // ebx
  unsigned int v5; // ebx
  const char *v7; // [rsp+40h] [rbp-19h] BYREF
  unsigned int v8; // [rsp+48h] [rbp-11h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+7h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  v7 = "OpenMountMgr";
  v3 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v3 + 16) = "OpenMountMgr";
  ++*(_WORD *)(v3 + 8);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"OpenMountMgr");
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"24";
  memset(&ObjectAttributes.Attributes, 0, 24);
  ObjectAttributes.RootDirectory = 0;
  IoStatusBlock = 0;
  v4 = NtOpenFile(FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v4 >= 0 )
  {
    v8 = 0;
    v5 = 0;
  }
  else
  {
    v5 = v4 | 0x10000000;
    v8 = v5;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (unsigned int)L"24",
        v5);
    }
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v7);
  return v5;
}

```

## disassembly

```asm
0x18000e910  push    rbp
0x18000e912  push    rbx
0x18000e913  push    rsi
0x18000e914  push    r14
0x18000e916  lea     rbp, [rsp-3Fh]
0x18000e91b  sub     rsp, 98h
0x18000e922  mov     edx, cs:_tls_index
0x18000e928  lea     r9, aOpenmountmgr; "OpenMountMgr"
0x18000e92f  mov     rax, gs:58h
0x18000e938  mov     rbx, rcx
0x18000e93b  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000e942  mov     [rbp+57h+var_70], r9
0x18000e946  mov     r8, [rax+rdx*8]
0x18000e94a  mov     eax, 10h
0x18000e94f  mov     edx, 8
0x18000e954  mov     [rax+r8], r9
0x18000e958  movzx   eax, cx
0x18000e95b  inc     word ptr [rdx+r8]
0x18000e960  movzx   edx, word ptr [rdx+r8]
0x18000e965  cmp     dx, cx
0x18000e968  cmovb   ax, dx
0x18000e96c  cmovb   cx, dx
0x18000e970  mov     [rbp+57h+var_80], ax
0x18000e974  xor     eax, eax
0x18000e976  mov     [rbp+57h+var_7C], eax
0x18000e979  mov     rax, cs:off_180047060; "                                       "...
0x18000e980  mov     [rbp+57h+var_78], rax
0x18000e984  mov     [rbp+57h+var_7E], cx
0x18000e988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e98f  lea     r14, WPP_GLOBAL_Control
0x18000e996  cmp     rcx, r14
0x18000e999  jz      short loc_18000E9BE
0x18000e99b  test    byte ptr [rcx+1Ch], 1
0x18000e99f  jz      short loc_18000E9BE
0x18000e9a1  cmp     byte ptr [rcx+19h], 5
0x18000e9a5  jb      short loc_18000E9BE
0x18000e9a7  mov     rcx, [rcx+10h]; LoggerHandle
0x18000e9ab  mov     edx, 0Dh
0x18000e9b0  mov     qword ptr [rsp+0B0h+ShareAccess], r9; __int64
0x18000e9b5  lea     r9, [rbp+57h+var_80]
0x18000e9b9  call    WPP_SF_aZs
0x18000e9be  xorps   xmm0, xmm0
0x18000e9c1  mov     [rsp+0B0h+OpenOptions], 60h ; '`'; OpenOptions
0x18000e9c9  lea     rsi, ?MountMgrName@@3U_UNICODE_STRING@@B; "24"
0x18000e9d0  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000e9d8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000e9dc  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x18000e9e0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000e9e4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x18000e9ec  mov     edx, 100000h; DesiredAccess
0x18000e9f1  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000e9f9  mov     rcx, rbx; FileHandle
0x18000e9fc  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x18000ea04  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000ea08  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ea0d  call    cs:__imp_NtOpenFile
0x18000ea13  mov     ebx, eax
0x18000ea15  test    eax, eax
0x18000ea17  jns     short loc_18000EA56
0x18000ea19  bts     ebx, 1Ch
0x18000ea1d  mov     [rbp+57h+var_68], ebx
0x18000ea20  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea27  cmp     rcx, r14
0x18000ea2a  jz      short loc_18000EA5F
0x18000ea2c  test    byte ptr [rcx+1Ch], 1
0x18000ea30  jz      short loc_18000EA5F
0x18000ea32  cmp     byte ptr [rcx+19h], 2
0x18000ea36  jb      short loc_18000EA5F
0x18000ea38  mov     rcx, [rcx+10h]
0x18000ea3c  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000ea43  mov     edx, 17h
0x18000ea48  mov     [rsp+0B0h+ShareAccess], ebx
0x18000ea4c  mov     r9, rsi
0x18000ea4f  call    WPP_SF_Zd
0x18000ea54  jmp     short loc_18000EA5F
0x18000ea56  mov     [rbp+57h+var_68], 0
0x18000ea5d  xor     ebx, ebx
0x18000ea5f  lea     rcx, [rbp+57h+var_70]; this
0x18000ea63  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000ea68  mov     eax, ebx
0x18000ea6a  add     rsp, 98h
0x18000ea71  pop     r14
0x18000ea73  pop     rsi
0x18000ea74  pop     rbx
0x18000ea75  pop     rbp
0x18000ea76  retn
```
