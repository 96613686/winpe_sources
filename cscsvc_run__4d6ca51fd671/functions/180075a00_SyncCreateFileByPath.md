# SyncCreateFileByPath

- ea: `0x180075a00`
- end: `0x180075c2f`
- name: `SyncCreateFileByPath`
- size: `559`
- prototype: `__int64 __usercall@<rax>(PHANDLE FileHandle@<rcx>, int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180078390`
- `0x180078900`

## callees

- `0x180004c40`
- `0x180014a60`
- `0x180020ef0`
- `0x1800360c0`
- `0x180036394`
- `0x18003c488`
- `0x1800725d8`
- `0x18007291c`
- `0x180075a00`
- `0x180075c38`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180075b3d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180075b3d`
- `ntdll!RtlFreeHeap` at `0x180075bd9`
- `ntdll!RtlFreeHeap` at `0x180075bd9`

## string_xrefs

- `0x180075a61`: `SyncCreateFileByPath: Handle: 0x%p Path: 0x%p FileName: 0x%p Disposition: 0x%x`
- `0x180075abc`: `SyncCreateFileByPath: DesiredAccess: 0x%x FileAttributes 0x%x ShareAccess: 0x%x CreateOptions: 0x%x`
- `0x180075b5f`: `SyncCreateFileByPath: RtlDosPathNameToNtPathName_U failed for [%ws]`
- `0x180075bf3`: `SyncCreateFileByPath: 0x%x`

## pseudocode

```c
__int64 __fastcall SyncCreateFileByPath(
        PHANDLE FileHandle,
        __int64 a2,
        const wchar_t *a3,
        __int64 a4,
        int a5,
        ULONG a6)
{
  CObjectMonitor *v8; // rax
  __int64 v9; // rax
  unsigned int v10; // ebx
  wchar_t *v11; // rax
  const WCHAR *v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // r9
  PWSTR Buffer; // rsi
  ULONG v17[2]; // [rsp+20h] [rbp-68h]
  int v18; // [rsp+28h] [rbp-60h]
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-48h] BYREF

  NtPathName = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 )
    {
      SyncTraceOutputInternal(
        L"SyncCreateFileByPath: Handle: 0x%p Path: 0x%p FileName: 0x%p Disposition: 0x%x",
        FileHandle,
        &dword_1800966F4,
        a3,
        2);
      WPP_SF_qqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        24,
        WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
        FileHandle,
        &dword_1800966F4,
        a3,
        2);
      v8 = WPP_GLOBAL_Control;
    }
    if ( v8 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 108) & 4) != 0 )
    {
      v17[0] = 0;
      SyncTraceOutputInternal(
        L"SyncCreateFileByPath: DesiredAccess: 0x%x FileAttributes 0x%x ShareAccess: 0x%x CreateOptions: 0x%x",
        65923,
        a6,
        5,
        *(_QWORD *)v17);
      WPP_SF_DDDD(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        25,
        WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids,
        65923,
        a6,
        5,
        0);
    }
  }
  v9 = -1;
  do
    ++v9;
  while ( a3[v9] );
  v10 = v9 + 2;
  v11 = (wchar_t *)SyncAlloc((unsigned int)(2 * (v9 + 2)));
  v12 = v11;
  if ( v11 )
  {
    StringCchCopyW(v11, v10, a3);
    if ( RtlDosPathNameToNtPathName_U(v12, &NtPathName, 0, 0) )
    {
      Buffer = NtPathName.Buffer;
      v13 = SyncCreateFileInternal(FileHandle, 0x10183u, a6, v14, 2u, v18, &NtPathName);
    }
    else
    {
      Buffer = 0;
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        SyncTraceOutputInternal(L"SyncCreateFileByPath: RtlDosPathNameToNtPathName_U failed for [%ws]", v12);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 26, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v12);
      }
      v13 = -1073741766;
    }
    SyncFree(v12);
    if ( Buffer )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  }
  else
  {
    v13 = -1073741670;
  }
  if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 8) != 0 )
  {
    SyncTraceOutputInternal(L"SyncCreateFileByPath: 0x%x", v13);
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 27, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids, v13);
  }
  return v13;
}

```

## disassembly

```asm
0x180075a00  push    rbx
0x180075a02  push    rbp
0x180075a03  push    rsi
0x180075a04  push    rdi
0x180075a05  push    r12
0x180075a07  push    r14
0x180075a09  push    r15
0x180075a0b  sub     rsp, 50h
0x180075a0f  xorps   xmm0, xmm0
0x180075a12  mov     rsi, r8
0x180075a15  movups  xmmword ptr [rsp+88h+NtPathName.Length], xmm0
0x180075a1a  mov     r14, rcx
0x180075a1d  mov     rax, cs:WPP_GLOBAL_Control
0x180075a24  lea     r12, WPP_GLOBAL_Control
0x180075a2b  mov     ebp, [rsp+88h+arg_28]
0x180075a32  xor     r15d, r15d
0x180075a35  mov     edi, 10183h
0x180075a3a  cmp     rax, r12
0x180075a3d  jz      loc_180075AF7
0x180075a43  test    byte ptr [rax+6Ch], 4
0x180075a47  jz      short loc_180075AA4
0x180075a49  mov     r9, r8
0x180075a4c  mov     [rsp+88h+var_68], 2
0x180075a54  mov     rdx, rcx
0x180075a57  lea     rbx, dword_1800966F4
0x180075a5e  mov     r8, rbx
0x180075a61  lea     rcx, aSynccreatefile_4; "SyncCreateFileByPath: Handle: 0x%p Path"...
0x180075a68  call    SyncTraceOutputInternal
0x180075a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180075a74  lea     edx, [r15+18h]
0x180075a78  mov     dword ptr [rsp+88h+var_58], 2
0x180075a80  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075a87  mov     qword ptr [rsp+88h+var_60], rsi
0x180075a8c  mov     r9, r14
0x180075a8f  mov     qword ptr [rsp+88h+var_68], rbx
0x180075a94  mov     rcx, [rcx+60h]
0x180075a98  call    WPP_SF_qqqD
0x180075a9d  mov     rax, cs:WPP_GLOBAL_Control
0x180075aa4  cmp     rax, r12
0x180075aa7  jz      short loc_180075AF7
0x180075aa9  test    byte ptr [rax+6Ch], 4
0x180075aad  jz      short loc_180075AF7
0x180075aaf  mov     ebx, 5
0x180075ab4  mov     [rsp+88h+var_68], r15d
0x180075ab9  mov     r9d, ebx
0x180075abc  lea     rcx, aSynccreatefile_3; "SyncCreateFileByPath: DesiredAccess: 0x"...
0x180075ac3  mov     r8d, ebp
0x180075ac6  mov     edx, edi
0x180075ac8  call    SyncTraceOutputInternal
0x180075acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180075ad4  lea     edx, [rbx+14h]
0x180075ad7  mov     dword ptr [rsp+88h+var_58], r15d
0x180075adc  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075ae3  mov     [rsp+88h+var_60], ebx; int
0x180075ae7  mov     r9d, edi
0x180075aea  mov     [rsp+88h+var_68], ebp
0x180075aee  mov     rcx, [rcx+60h]
0x180075af2  call    WPP_SF_DDDD
0x180075af7  or      rax, 0FFFFFFFFFFFFFFFFh
0x180075afb  inc     rax
0x180075afe  cmp     [rsi+rax*2], r15w
0x180075b03  jnz     short loc_180075AFB
0x180075b05  lea     ebx, [rax+2]
0x180075b08  lea     ecx, [rbx+rbx]
0x180075b0b  call    SyncAlloc
0x180075b10  mov     rdi, rax
0x180075b13  test    rax, rax
0x180075b16  jnz     short loc_180075B22
0x180075b18  mov     ebx, 0C000009Ah
0x180075b1d  jmp     loc_180075BDF
0x180075b22  mov     edx, ebx; cchDest
0x180075b24  mov     r8, rsi; pszSrc
0x180075b27  mov     rcx, rdi; pszDest
0x180075b2a  call    StringCchCopyW
0x180075b2f  xor     r9d, r9d; DirectoryInfo
0x180075b32  lea     rdx, [rsp+88h+NtPathName]; NtPathName
0x180075b37  xor     r8d, r8d; NtFileNamePart
0x180075b3a  mov     rcx, rdi; DosPathName
0x180075b3d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180075b43  test    al, al
0x180075b45  jnz     short loc_180075B91
0x180075b47  mov     rsi, r15
0x180075b4a  mov     rax, cs:WPP_GLOBAL_Control
0x180075b51  cmp     rax, r12
0x180075b54  jz      short loc_180075B8A
0x180075b56  test    byte ptr [rax+6Ch], 1
0x180075b5a  jz      short loc_180075B8A
0x180075b5c  mov     rdx, rdi
0x180075b5f  lea     rcx, aSynccreatefile_0; "SyncCreateFileByPath: RtlDosPathNameToN"...
0x180075b66  call    SyncTraceOutputInternal
0x180075b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180075b72  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075b79  mov     edx, 1Ah
0x180075b7e  mov     r9, rdi
0x180075b81  mov     rcx, [rcx+60h]
0x180075b85  call    WPP_SF_S
0x180075b8a  mov     ebx, 0C000003Ah
0x180075b8f  jmp     short loc_180075BBA
0x180075b91  mov     rsi, [rsp+88h+NtPathName.Buffer]
0x180075b96  lea     rax, [rsp+88h+NtPathName]
0x180075b9b  mov     [rsp+88h+var_58], rax; __int64
0x180075ba0  mov     r8d, ebp
0x180075ba3  mov     edx, 10183h
0x180075ba8  mov     [rsp+88h+var_68], 2; ULONG
0x180075bb0  mov     rcx, r14; FileHandle
0x180075bb3  call    SyncCreateFileInternal
0x180075bb8  mov     ebx, eax
0x180075bba  mov     rcx, rdi
0x180075bbd  call    SyncFree
0x180075bc2  test    rsi, rsi
0x180075bc5  jz      short loc_180075BDF
0x180075bc7  mov     rcx, gs:60h
0x180075bd0  mov     r8, rsi; P
0x180075bd3  xor     edx, edx; Flags
0x180075bd5  mov     rcx, [rcx+30h]; HeapHandle
0x180075bd9  call    cs:__imp_RtlFreeHeap
0x180075bdf  mov     rax, cs:WPP_GLOBAL_Control
0x180075be6  cmp     rax, r12
0x180075be9  jz      short loc_180075C1E
0x180075beb  test    byte ptr [rax+6Ch], 8
0x180075bef  jz      short loc_180075C1E
0x180075bf1  mov     edx, ebx
0x180075bf3  lea     rcx, aSynccreatefile_5; "SyncCreateFileByPath: 0x%x"
0x180075bfa  call    SyncTraceOutputInternal
0x180075bff  mov     rcx, cs:WPP_GLOBAL_Control
0x180075c06  lea     r8, WPP_f6d51691bbaf371b29701e2ead3867a6_Traceguids
0x180075c0d  mov     edx, 1Bh
0x180075c12  mov     r9d, ebx
0x180075c15  mov     rcx, [rcx+60h]
0x180075c19  call    WPP_SF_d
0x180075c1e  mov     eax, ebx
0x180075c20  add     rsp, 50h
0x180075c24  pop     r15
0x180075c26  pop     r14
0x180075c28  pop     r12
0x180075c2a  pop     rdi
0x180075c2b  pop     rsi
0x180075c2c  pop     rbp
0x180075c2d  pop     rbx
0x180075c2e  retn
```
