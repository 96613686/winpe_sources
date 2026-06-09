# CSchedule::NewWorkItem(ushort const *,_GUID const &,_GUID const &,IUnknown * *)

- ea: `0x18000f9e0`
- end: `0x18000fb6a`
- name: `?NewWorkItem@CSchedule@@UEAAJPEBGAEBU_GUID@@1PEAPEAUIUnknown@@@Z`
- size: `394`
- prototype: `__int64 __usercall@<rax>(CSchedule *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, const struct _GUID *@<r8>, const struct _GUID *@<r9>, struct IUnknown **)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180002ab0`
- `0x180006120`
- `0x180007180`
- `0x18000865c`
- `0x180009f38`
- `0x18000f9e0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000faf6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000faf6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb2c`

## pseudocode

```c
signed int __fastcall CSchedule::NewWorkItem(
        LPCWSTR *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        struct IUnknown **a5)
{
  signed int result; // eax
  struct IUnknown **v10; // rsi
  __int64 v11; // rax
  struct CJob *v12; // rax
  CJob *v13; // rdi
  int v14; // eax
  WCHAR *v15; // rbp
  unsigned int v16; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v19; // edx
  void *Block; // [rsp+60h] [rbp+8h] BYREF

  if ( this[7] || (result = FolderAccessCheckOnThreadToken(this[8], 2u), result >= 0) )
  {
    if ( a2 && (v10 = a5) != 0 )
    {
      *a5 = 0;
      v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&CLSID_CTask.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&CLSID_CTask.Data1 )
        v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)CLSID_CTask.Data4;
      if ( v11 )
        return -2147221231;
      Block = 0;
      result = CSchedule::CheckJobName((CSchedule *)this, a2, (unsigned __int16 **)&Block);
      if ( result >= 0 )
      {
        v12 = CJob::Create();
        v13 = v12;
        if ( !v12 )
        {
          operator delete(Block);
          return -2147024882;
        }
        v14 = (**(__int64 (__fastcall ***)(struct CJob *, const struct _GUID *, struct IUnknown **))v12)(v12, a4, v10);
        v15 = (WCHAR *)Block;
        v16 = v14;
        if ( v14 >= 0 )
        {
          (*(void (__fastcall **)(CJob *))(*(_QWORD *)v13 + 16LL))(v13);
          FileW = CreateFileW(v15, 0, 3u, 0, 3u, 0, 0);
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError == 2 )
            {
              *((_QWORD *)v13 + 19) = v15;
              return 0;
            }
            if ( LastError > 0 )
              v16 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            CloseHandle(FileW);
            v16 = -2147024816;
          }
        }
        operator delete(v15);
        CJob::`scalar deleting destructor'(v13, v19);
        result = v16;
        *v10 = 0;
      }
    }
    else
    {
      return -2147024809;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f9e0  mov     [rsp+arg_8], rbx
0x18000f9e5  mov     [rsp+arg_10], rbp
0x18000f9ea  push    rsi
0x18000f9eb  push    rdi
0x18000f9ec  push    r14
0x18000f9ee  sub     rsp, 40h
0x18000f9f2  cmp     qword ptr [rcx+38h], 0
0x18000f9f7  mov     rbp, r9
0x18000f9fa  mov     r14, r8
0x18000f9fd  mov     rdi, rdx
0x18000fa00  mov     rbx, rcx
0x18000fa03  jnz     short loc_18000FA1B
0x18000fa05  mov     rcx, [rcx+40h]; lpFileName
0x18000fa09  mov     edx, 2; DesiredAccess
0x18000fa0e  call    ?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z; FolderAccessCheckOnThreadToken(ushort const *,ulong)
0x18000fa13  test    eax, eax
0x18000fa15  js      loc_18000FB57
0x18000fa1b  test    rdi, rdi
0x18000fa1e  jz      loc_18000FB52
0x18000fa24  mov     rsi, [rsp+58h+arg_20]
0x18000fa2c  test    rsi, rsi
0x18000fa2f  jz      loc_18000FB52
0x18000fa35  mov     qword ptr [rsi], 0
0x18000fa3c  mov     rax, [r14]
0x18000fa3f  sub     rax, qword ptr cs:CLSID_CTask.Data1
0x18000fa46  jnz     short loc_18000FA53
0x18000fa48  mov     rax, [r14+8]
0x18000fa4c  sub     rax, qword ptr cs:CLSID_CTask.Data4
0x18000fa53  test    rax, rax
0x18000fa56  jz      short loc_18000FA62
0x18000fa58  mov     eax, 80040111h
0x18000fa5d  jmp     loc_18000FB57
0x18000fa62  lea     r8, [rsp+58h+Block]; unsigned __int16 **
0x18000fa67  mov     [rsp+58h+Block], 0
0x18000fa70  mov     rdx, rdi; unsigned __int16 *
0x18000fa73  mov     rcx, rbx; this
0x18000fa76  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x18000fa7b  test    eax, eax
0x18000fa7d  js      loc_18000FB57
0x18000fa83  call    ?Create@CJob@@SAPEAV1@XZ; CJob::Create(void)
0x18000fa88  mov     rdi, rax
0x18000fa8b  test    rax, rax
0x18000fa8e  jnz     short loc_18000FAA4
0x18000fa90  mov     rcx, [rsp+58h+Block]; Block
0x18000fa95  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fa9a  mov     eax, 8007000Eh
0x18000fa9f  jmp     loc_18000FB57
0x18000faa4  mov     rax, [rax]
0x18000faa7  mov     r8, rsi
0x18000faaa  mov     rdx, rbp
0x18000faad  mov     rcx, rdi
0x18000fab0  mov     rax, [rax]
0x18000fab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fab8  mov     rbp, [rsp+58h+Block]
0x18000fabd  mov     ebx, eax
0x18000fabf  test    eax, eax
0x18000fac1  js      short loc_18000FB37
0x18000fac3  mov     rax, [rdi]
0x18000fac6  mov     rcx, rdi
0x18000fac9  mov     rax, [rax+10h]
0x18000facd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fad2  mov     r8d, 3; dwShareMode
0x18000fad8  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18000fae1  mov     [rsp+58h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18000fae9  xor     r9d, r9d; lpSecurityAttributes
0x18000faec  xor     edx, edx; dwDesiredAccess
0x18000faee  mov     [rsp+58h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000faf3  mov     rcx, rbp; lpFileName
0x18000faf6  call    cs:__imp_CreateFileW
0x18000fafc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000fb00  jnz     short loc_18000FB29
0x18000fb02  call    cs:__imp_GetLastError
0x18000fb08  mov     ebx, eax
0x18000fb0a  cmp     eax, 2
0x18000fb0d  jnz     short loc_18000FB1A
0x18000fb0f  mov     [rdi+98h], rbp
0x18000fb16  xor     eax, eax
0x18000fb18  jmp     short loc_18000FB57
0x18000fb1a  test    eax, eax
0x18000fb1c  jle     short loc_18000FB37
0x18000fb1e  movzx   ebx, ax
0x18000fb21  or      ebx, 80070000h
0x18000fb27  jmp     short loc_18000FB37
0x18000fb29  mov     rcx, rax; hObject
0x18000fb2c  call    cs:__imp_CloseHandle
0x18000fb32  mov     ebx, 80070050h
0x18000fb37  mov     rcx, rbp; Block
0x18000fb3a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fb3f  mov     rcx, rdi; this
0x18000fb42  call    ??_GCJob@@QEAAPEAXI@Z; CJob::`scalar deleting destructor'(uint)
0x18000fb47  mov     eax, ebx
0x18000fb49  mov     qword ptr [rsi], 0
0x18000fb50  jmp     short loc_18000FB57
0x18000fb52  mov     eax, 80070057h
0x18000fb57  mov     rbx, [rsp+58h+arg_8]
0x18000fb5c  mov     rbp, [rsp+58h+arg_10]
0x18000fb61  add     rsp, 40h
0x18000fb65  pop     r14
0x18000fb67  pop     rdi
0x18000fb68  pop     rsi
0x18000fb69  retn
```
