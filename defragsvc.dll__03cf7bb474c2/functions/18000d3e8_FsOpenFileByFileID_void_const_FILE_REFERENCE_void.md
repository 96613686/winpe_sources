# FsOpenFileByFileID(void * const,FILE_REFERENCE,void * *)

- ea: `0x18000d3e8`
- end: `0x18000d735`
- name: `?FsOpenFileByFileID@@YAJQEAXUFILE_REFERENCE@@PEAPEAX@Z`
- size: `845`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000cf94`

## callees

- `0x180006400`
- `0x18000d3e8`
- `0x180038c3c`
- `0x180046494`
- `0x18004a92c`
- `0x1800621f4`
- `0x180067b30`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000d550`
- `ntdll!NtOpenFile` at `0x18000d550`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d5f5`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000d459`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x18000d459`

## string_xrefs

- `0x18000d43a`: `FsOpenFileByFileID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FsOpenFileByFileID(void *a1, unsigned __int64 a2, void **a3)
{
  unsigned __int64 v6; // rsi
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v8; // rcx
  __int16 v9; // ax
  NTSTATUS v10; // ecx
  __int64 v11; // r8
  unsigned int v12; // ebx
  __int64 v14; // rdx
  void *FileHandle; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-81h] BYREF
  __int64 v17; // [rsp+3Ch] [rbp-7Dh]
  __int16 v18; // [rsp+44h] [rbp-75h]
  const char *v19; // [rsp+48h] [rbp-71h]
  __int128 v20; // [rsp+50h] [rbp-69h] BYREF
  __int64 v21; // [rsp+60h] [rbp-59h]
  int v22; // [rsp+68h] [rbp-51h]
  __int128 v23; // [rsp+70h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-9h] BYREF
  __int128 v26; // [rsp+C0h] [rbp+7h] BYREF

  v6 = HIDWORD(a2);
  v16 = 0;
  v17 = 59;
  v18 = 1;
  v19 = "FsOpenFileByFileID";
  v20 = 0;
  v21 = 0;
  v22 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v20 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v20 = *(_QWORD *)(*((_QWORD *)&v20 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v20 + 1) + 32LL) = &v16;
LABEL_3:
    v8 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( v18 )
  {
    if ( v18 == 1 )
    {
      if ( v8 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v8 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v14 = 12;
LABEL_28:
      WPP_SF_s(*((_QWORD *)v8 + 2), v14, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v19);
      goto LABEL_8;
    }
    if ( v8 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x20000) != 0 )
    {
      v14 = 13;
      goto LABEL_28;
    }
  }
  else if ( v8 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x8000000) != 0 )
  {
    v14 = 11;
    goto LABEL_28;
  }
LABEL_8:
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v23 = 0;
  v26 = 0;
  FileHandle = (void *)-1LL;
  v9 = 70;
  if ( !a3 )
  {
    v12 = -2147024809;
LABEL_12:
    WORD1(v17) = v9;
    v16 = v12;
    goto LABEL_13;
  }
  v16 = 0;
  LOWORD(v17) = 70;
  *a3 = (void *)-1LL;
  *((_QWORD *)&v23 + 1) = &v26;
  LODWORD(v23) = 524296;
  *(_QWORD *)&v26 = a2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v23;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x202000u);
  if ( v10 == -1073741810 || v10 == -1073741202 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
    }
    v12 = -1996488687;
    v9 = 97;
    goto LABEL_12;
  }
  if ( v10 == -1073741774 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids);
    }
    v12 = -1996488675;
    v9 = 102;
    goto LABEL_12;
  }
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      WPP_SF_IL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        WPP_GLOBAL_Control,
        v11,
        (unsigned int)a2 | ((unsigned __int64)(unsigned __int16)v6 << 32),
        v10);
    }
    v12 = -1996488674;
    v9 = 108;
    goto LABEL_12;
  }
  *a3 = FileHandle;
  FileHandle = (void *)-1LL;
  v12 = v16;
LABEL_13:
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(FileHandle);
    FileHandle = (void *)-1LL;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return v12;
}

```

## disassembly

```asm
0x18000d3e8  mov     [rsp-8+arg_18], rbx
0x18000d3ed  push    rbp
0x18000d3ee  push    rsi
0x18000d3ef  push    rdi
0x18000d3f0  push    r12
0x18000d3f2  push    r13
0x18000d3f4  push    r14
0x18000d3f6  push    r15
0x18000d3f8  lea     rbp, [rsp-27h]
0x18000d3fd  sub     rsp, 0E0h
0x18000d404  mov     rax, cs:__security_cookie
0x18000d40b  xor     rax, rsp
0x18000d40e  mov     [rbp+57h+var_40], rax
0x18000d412  mov     rdi, r8
0x18000d415  mov     rbx, rdx
0x18000d418  mov     r14, rcx
0x18000d41b  mov     rsi, rdx
0x18000d41e  shr     rsi, 20h
0x18000d422  xor     r13d, r13d
0x18000d425  mov     [rsp+110h+var_D8], r13d
0x18000d42a  mov     [rbp+57h+var_D4], 3Bh ; ';'
0x18000d432  lea     eax, [r13+1]
0x18000d436  mov     [rbp+57h+var_CC], ax
0x18000d43a  lea     rax, aFsopenfilebyfi; "FsOpenFileByFileID"
0x18000d441  mov     [rbp+57h+var_C8], rax
0x18000d445  xorps   xmm0, xmm0
0x18000d448  movdqu  [rbp+57h+var_C0], xmm0
0x18000d44d  mov     [rbp+57h+var_B0], r13
0x18000d451  mov     [rbp+57h+var_A8], r13d
0x18000d455  lea     rcx, [rbp+57h+var_C0+8]
0x18000d459  call    cs:__imp_SxTracerGetThreadContextRetail
0x18000d45f  lea     r12, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x18000d466  lea     r15, WPP_GLOBAL_Control
0x18000d46d  test    eax, eax
0x18000d46f  js      loc_18000D65A
0x18000d475  mov     rcx, qword ptr [rbp+57h+var_C0+8]
0x18000d479  mov     rax, [rcx+20h]
0x18000d47d  mov     qword ptr [rbp+57h+var_C0], rax
0x18000d481  lea     rax, [rsp+110h+var_D8]
0x18000d486  mov     [rcx+20h], rax
0x18000d48a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d491  mov     edx, 1
0x18000d496  movzx   eax, [rbp+57h+var_CC]
0x18000d49a  test    ax, ax
0x18000d49d  jz      loc_18000D691
0x18000d4a3  cmp     ax, dx
0x18000d4a6  jnz     loc_18000D62A
0x18000d4ac  cmp     rcx, r15
0x18000d4af  jz      short loc_18000D4BE
0x18000d4b1  test    dword ptr [rcx+1Ch], 20000000h
0x18000d4b8  jnz     loc_18000D6AE
0x18000d4be  xorps   xmm0, xmm0
0x18000d4c1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000d4c5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000d4c9  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d4cd  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000d4d1  xorps   xmm1, xmm1
0x18000d4d4  movups  [rbp+57h+var_A0], xmm1
0x18000d4d8  movups  [rbp+57h+var_50], xmm0
0x18000d4dc  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000d4e0  mov     [rsp+110h+FileHandle], r12
0x18000d4e5  lea     eax, [r12+47h]
0x18000d4ea  test    rdi, rdi
0x18000d4ed  jz      loc_18000D5C3
0x18000d4f3  mov     [rsp+110h+var_D8], r13d
0x18000d4f8  mov     word ptr [rbp+57h+var_D4], ax
0x18000d4fc  mov     [rdi], r12
0x18000d4ff  lea     rax, [rbp+57h+var_50]
0x18000d503  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18000d507  mov     dword ptr [rbp+57h+var_A0], 80008h
0x18000d50e  mov     qword ptr [rbp+57h+var_50], rbx
0x18000d512  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000d519  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18000d51d  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000d524  lea     rax, [rbp+57h+var_A0]
0x18000d528  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000d52c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000d531  mov     [rsp+110h+OpenOptions], 202000h; OpenOptions
0x18000d539  mov     [rsp+110h+ShareAccess], r13d; ShareAccess
0x18000d53e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000d542  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000d546  mov     edx, 100080h; DesiredAccess
0x18000d54b  lea     rcx, [rsp+110h+FileHandle]; FileHandle
0x18000d550  call    cs:__imp_NtOpenFile
0x18000d556  mov     ecx, eax
0x18000d558  cmp     eax, 0C000000Eh
0x18000d55d  jnz     short loc_18000D5CA
0x18000d55f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d566  cmp     rcx, r15
0x18000d569  jnz     loc_18000D70D
0x18000d56f  mov     ebx, 89000011h
0x18000d574  mov     eax, 61h ; 'a'
0x18000d579  mov     word ptr [rbp+57h+var_D4+2], ax
0x18000d57d  mov     [rsp+110h+var_D8], ebx
0x18000d581  mov     rcx, [rsp+110h+FileHandle]; hObject
0x18000d586  lea     rdx, [rcx-1]
0x18000d58a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000d58e  jbe     short loc_18000D5F5
0x18000d590  lea     rcx, [rsp+110h+var_D8]; this
0x18000d595  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d59a  mov     eax, ebx
0x18000d59c  mov     rcx, [rbp+57h+var_40]
0x18000d5a0  xor     rcx, rsp; StackCookie
0x18000d5a3  call    __security_check_cookie
0x18000d5a8  mov     rbx, [rsp+110h+arg_18]
0x18000d5b0  add     rsp, 0E0h
0x18000d5b7  pop     r15
0x18000d5b9  pop     r14
0x18000d5bb  pop     r13
0x18000d5bd  pop     r12
0x18000d5bf  pop     rdi
0x18000d5c0  pop     rsi
0x18000d5c1  pop     rbp
0x18000d5c2  retn
0x18000d5c3  mov     ebx, 80070057h
0x18000d5c8  jmp     short loc_18000D579
0x18000d5ca  cmp     ecx, 0C000026Eh
0x18000d5d0  jz      short loc_18000D55F
0x18000d5d2  cmp     ecx, 0C0000032h
0x18000d5d8  jz      loc_18000D6B5
0x18000d5de  test    ecx, ecx
0x18000d5e0  js      short loc_18000D602
0x18000d5e2  mov     rax, [rsp+110h+FileHandle]
0x18000d5e7  mov     [rdi], rax
0x18000d5ea  mov     [rsp+110h+FileHandle], r12
0x18000d5ef  mov     ebx, [rsp+110h+var_D8]
0x18000d5f3  jmp     short loc_18000D581
0x18000d5f5  call    cs:__imp_CloseHandle
0x18000d5fb  mov     [rsp+110h+FileHandle], r12
0x18000d600  jmp     short loc_18000D590
0x18000d602  mov     rdx, cs:WPP_GLOBAL_Control
0x18000d609  cmp     rdx, r15
0x18000d60c  jz      short loc_18000D61B
0x18000d60e  test    dword ptr [rdx+1Ch], 2000000h
0x18000d615  jnz     loc_18000D6EE
0x18000d61b  mov     ebx, 8900001Eh
0x18000d620  mov     eax, 6Ch ; 'l'
0x18000d625  jmp     loc_18000D579
0x18000d62a  cmp     rcx, r15
0x18000d62d  jz      loc_18000D4BE
0x18000d633  test    dword ptr [rcx+1Ch], 20000h
0x18000d63a  jz      loc_18000D4BE
0x18000d640  mov     edx, 0Dh
0x18000d645  mov     r9, [rbp+57h+var_C8]
0x18000d649  mov     r8, r12
0x18000d64c  mov     rcx, [rcx+10h]
0x18000d650  call    WPP_SF_s
0x18000d655  jmp     loc_18000D4BE
0x18000d65a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d661  cmp     rcx, r15
0x18000d664  jz      loc_18000D491
0x18000d66a  mov     edx, 1
0x18000d66f  test    [rcx+1Ch], dl
0x18000d672  jz      loc_18000D496
0x18000d678  mov     edx, 0Ah
0x18000d67d  mov     r9d, eax
0x18000d680  mov     r8, r12
0x18000d683  mov     rcx, [rcx+10h]
0x18000d687  call    WPP_SF_d
0x18000d68c  jmp     loc_18000D48A
0x18000d691  cmp     rcx, r15
0x18000d694  jz      loc_18000D4BE
0x18000d69a  test    dword ptr [rcx+1Ch], 8000000h
0x18000d6a1  jz      loc_18000D4BE
0x18000d6a7  mov     edx, 0Bh
0x18000d6ac  jmp     short loc_18000D645
0x18000d6ae  mov     edx, 0Ch
0x18000d6b3  jmp     short loc_18000D645
0x18000d6b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d6bc  cmp     rcx, r15
0x18000d6bf  jz      short loc_18000D6DF
0x18000d6c1  test    dword ptr [rcx+1Ch], 2000000h
0x18000d6c8  jz      short loc_18000D6DF
0x18000d6ca  mov     edx, 0Bh
0x18000d6cf  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000d6d6  mov     rcx, [rcx+10h]
0x18000d6da  call    WPP_SF_
0x18000d6df  mov     ebx, 8900001Dh
0x18000d6e4  mov     eax, 66h ; 'f'
0x18000d6e9  jmp     loc_18000D579
0x18000d6ee  movzx   r9d, si
0x18000d6f2  shl     r9, 20h
0x18000d6f6  mov     eax, ebx
0x18000d6f8  or      r9, rax
0x18000d6fb  mov     [rsp+110h+ShareAccess], ecx
0x18000d6ff  mov     rcx, [rdx+10h]
0x18000d703  call    WPP_SF_IL
0x18000d708  jmp     loc_18000D61B
0x18000d70d  test    dword ptr [rcx+1Ch], 2000000h
0x18000d714  jz      loc_18000D56F
0x18000d71a  mov     edx, 0Ah
0x18000d71f  lea     r8, WPP_4f8c356de1ed38d999e93e3ab0e0aef2_Traceguids
0x18000d726  mov     rcx, [rcx+10h]
0x18000d72a  call    WPP_SF_
0x18000d72f  jmp     loc_18000D56F
```
