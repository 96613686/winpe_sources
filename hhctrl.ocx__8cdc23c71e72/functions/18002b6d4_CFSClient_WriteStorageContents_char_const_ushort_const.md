# CFSClient::WriteStorageContents(char const *,ushort const *)

- ea: `0x18002b6d4`
- end: `0x18002bb0b`
- name: `?WriteStorageContents@CFSClient@@QEAAXPEBDPEBG@Z`
- size: `1079`
- prototype: `void __fastcall(CFSClient *__hidden this, const char *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002b6d4`
- `0x18002d250`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x18001fff0`
- `0x18002624c`
- `0x18002a670`
- `0x18002b2e0`
- `0x18002b418`
- `0x18002b4dc`
- `0x18002b6d4`
- `0x180042d00`
- `0x180065384`
- `0x180065fc0`
- `0x180075c5a`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18002b98a`
- `KERNEL32!CloseHandle` at `0x18002ba80`
- `KERNEL32!CloseHandle` at `0x18002b98a`
- `KERNEL32!CloseHandle` at `0x18002ba80`
- `KERNEL32!GetFileAttributesA` at `0x18002b7b6`
- `KERNEL32!GetFileAttributesA` at `0x18002b7b6`
- `KERNEL32!CreateFileA` at `0x18002b962`
- `KERNEL32!CreateFileA` at `0x18002b962`
- `KERNEL32!WriteFile` at `0x18002ba6f`
- `KERNEL32!WriteFile` at `0x18002ba6f`
- `KERNEL32!DeleteFileA` at `0x18002ba8e`
- `KERNEL32!DeleteFileA` at `0x18002ba8e`
- `ole32!CoTaskMemFree` at `0x18002b847`
- `ole32!CoTaskMemFree` at `0x18002b847`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CFSClient::WriteStorageContents(CFSClient *this, const char *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  int v8; // r13d
  _QWORD *v9; // rcx
  int v10; // edx
  __int64 *v11; // r10
  __int64 v12; // rax
  int v13; // eax
  int v14; // eax
  char *v15; // rbx
  HANDLE v16; // r15
  unsigned int v17; // r8d
  unsigned int v18; // r10d
  int v19; // ebx
  char *v20; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+48h] [rbp-B8h] BYREF
  LPCVOID lpBuffer; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-98h] BYREF
  char *v26; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+98h] [rbp-68h]
  unsigned int v30; // [rsp+A0h] [rbp-60h]
  CHAR FileName[272]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v32[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  v24 = 0;
  v6 = *((_QWORD *)this + 11);
  if ( v6 )
  {
    v7 = *(_QWORD *)(v6 + 8);
    if ( a3 )
    {
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD, _QWORD, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v7 + 48LL))(
             v7,
             a3,
             0,
             0,
             0,
             0,
             &v24) < 0 )
        return;
      v8 = 1;
      v7 = v24;
    }
    else
    {
      v8 = 0;
      v24 = v7;
    }
    v23 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)v7 + 88LL))(v7, 0, 0, 0, &v23) >= 0 )
    {
      memset_0(&v28, 0, 0x50u);
      if ( GetFileAttributesA(a2) != -1 || (unsigned int)CreateFolder(a2) )
      {
        while ( 1 )
        {
          v9 = v23;
          LODWORD(v20) = 0;
          v10 = 1;
          if ( v23 )
          {
            v12 = *v23;
          }
          else
          {
            v11 = (__int64 *)*((_QWORD *)this + 10);
            if ( !v11 )
              goto LABEL_14;
            v12 = *v11;
            v9 = (_QWORD *)*((_QWORD *)this + 10);
          }
          v13 = (*(__int64 (__fastcall **)(_QWORD *, __int64, unsigned __int16 **, char **))(v12 + 24))(
                  v9,
                  1,
                  &v28,
                  &v20);
          v9 = v23;
          v10 = v13;
LABEL_14:
          v14 = 0;
          if ( v10 >= 0 )
            v14 = (int)v20;
          if ( !v14 )
          {
            if ( v9 )
            {
              (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
              v23 = 0;
            }
            if ( v8 && v24 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            return;
          }
          v20 = 0;
          CStr::operator=(&v20, v28);
          CoTaskMemFree(*(LPVOID *)this);
          v15 = v20;
          if ( v20 && (unsigned __int8)(*v20 - 35) > 1u )
          {
            if ( v29 == 1 )
            {
              StringCchCopyA(FileName, 0x104u, a2);
              AddTrailingBackslash(FileName, 0x104u);
              StringCchCatA(FileName, 0x104u, v15);
              v32[0] = 0;
              if ( a3 )
              {
                StringCbCopyW(v32, 0x208u, a3);
                StringCbCatW(v32, 0x208u, L"\\");
              }
              StringCbCatW(v32, 0x208u, v28);
              CFSClient::WriteStorageContents(this, FileName, v32);
            }
            else
            {
              StringCchCopyA(FileName, 0x104u, a2);
              AddTrailingBackslash(FileName, 0x104u);
              StringCchCatA(FileName, 0x104u, v15);
              *(_QWORD *)&SecurityAttributes.nLength = 24;
              *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
              SecurityAttributes.lpSecurityDescriptor = 0;
              v16 = CreateFileA(FileName, 0x40000000u, 0, &SecurityAttributes, 2u, 0x8000000u, 0);
              if ( v16 != (HANDLE)-1LL )
              {
                CMem::CMem((CMem *)&lpBuffer, v30);
                if ( lpBuffer )
                {
                  nNumberOfBytesToWrite = 0;
                  if ( a3 )
                  {
                    v26 = 0;
                    CStr::operator=(&v26, a3);
                    StringCchCopyA(FileName, 0x104u, v26);
                    AddTrailingBackslash(FileName, v18);
                    StringCchCatA(FileName, 0x104u, v15);
                    CStr::operator=(&v20);
                    CWStr::~CWStr((CWStr *)&v26);
                    v15 = v20;
                  }
                  v19 = CFSClient::OpenStream(this, v15, v17);
                  if ( v19 >= 0 )
                  {
                    v19 = CFSClient::Read(this, (void *)lpBuffer, v30, &nNumberOfBytesToWrite);
                    NumberOfBytesWritten = 0;
                    if ( v19 >= 0 )
                      WriteFile(v16, lpBuffer, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0);
                    CFSClient::CloseStream(this);
                  }
                  CloseHandle(v16);
                  if ( v19 < 0 )
                    DeleteFileA(FileName);
                  CWStr::~CWStr((CWStr *)&lpBuffer);
                }
                else
                {
                  CloseHandle(v16);
                  CWStr::~CWStr((CWStr *)&lpBuffer);
                }
              }
            }
          }
          CWStr::~CWStr((CWStr *)&v20);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18002b6d4  push    rbp
0x18002b6d6  push    rbx
0x18002b6d7  push    rsi
0x18002b6d8  push    r12
0x18002b6da  push    r13
0x18002b6dc  push    r14
0x18002b6de  push    r15
0x18002b6e0  lea     rbp, [rsp-310h]
0x18002b6e8  sub     rsp, 410h
0x18002b6ef  mov     rax, cs:__security_cookie
0x18002b6f6  xor     rax, rsp
0x18002b6f9  mov     [rbp+340h+var_40], rax
0x18002b700  mov     r14, r8
0x18002b703  mov     r12, rdx
0x18002b706  mov     rsi, rcx
0x18002b709  mov     [rsp+440h+var_3E0], 0
0x18002b712  mov     rcx, [rcx+58h]
0x18002b716  test    rcx, rcx
0x18002b719  jz      loc_18002BAE9
0x18002b71f  mov     rcx, [rcx+8]
0x18002b723  test    r8, r8
0x18002b726  jz      short loc_18002B76D
0x18002b728  mov     rax, [rcx]
0x18002b72b  lea     rdx, [rsp+440h+var_3E0]
0x18002b730  mov     [rsp+440h+hTemplateFile], rdx
0x18002b735  mov     [rsp+440h+dwFlagsAndAttributes], 0
0x18002b73d  mov     qword ptr [rsp+440h+dwCreationDisposition], 0
0x18002b746  xor     r9d, r9d
0x18002b749  xor     r8d, r8d
0x18002b74c  mov     rdx, r14
0x18002b74f  mov     rax, [rax+30h]
0x18002b753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b758  test    eax, eax
0x18002b75a  js      loc_18002BAE9
0x18002b760  mov     r13d, 1
0x18002b766  mov     rcx, [rsp+440h+var_3E0]
0x18002b76b  jmp     short loc_18002B775
0x18002b76d  xor     r13d, r13d
0x18002b770  mov     [rsp+440h+var_3E0], rcx
0x18002b775  mov     [rsp+440h+var_3E8], 0
0x18002b77e  mov     rax, [rcx]
0x18002b781  lea     rdx, [rsp+440h+var_3E8]
0x18002b786  mov     qword ptr [rsp+440h+dwCreationDisposition], rdx
0x18002b78b  xor     r9d, r9d
0x18002b78e  xor     r8d, r8d
0x18002b791  xor     edx, edx
0x18002b793  mov     rax, [rax+58h]
0x18002b797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b79c  test    eax, eax
0x18002b79e  js      loc_18002BAE9
0x18002b7a4  xor     edx, edx; Val
0x18002b7a6  lea     r8d, [rdx+50h]; Size
0x18002b7aa  lea     rcx, [rbp+340h+var_3B0]; void *
0x18002b7ae  call    memset_0
0x18002b7b3  mov     rcx, r12; lpFileName
0x18002b7b6  call    cs:__imp_GetFileAttributesA
0x18002b7bc  cmp     eax, 0FFFFFFFFh
0x18002b7bf  jnz     short loc_18002B7D1
0x18002b7c1  mov     rcx, r12; char *
0x18002b7c4  call    ?CreateFolder@@YAHPEBD@Z; CreateFolder(char const *)
0x18002b7c9  test    eax, eax
0x18002b7cb  jz      loc_18002BAE9
0x18002b7d1  mov     r15d, 104h
0x18002b7d7  mov     rcx, [rsp+440h+var_3E8]
0x18002b7dc  mov     dword ptr [rsp+440h+var_400], 0
0x18002b7e4  mov     edx, 1
0x18002b7e9  test    rcx, rcx
0x18002b7ec  jnz     short loc_18002B7FF
0x18002b7ee  mov     r10, [rsi+50h]
0x18002b7f2  test    r10, r10
0x18002b7f5  jz      short loc_18002B81B
0x18002b7f7  mov     rax, [r10]
0x18002b7fa  mov     rcx, r10
0x18002b7fd  jmp     short loc_18002B802
0x18002b7ff  mov     rax, [rcx]
0x18002b802  lea     r9, [rsp+440h+var_400]
0x18002b807  lea     r8, [rbp+340h+var_3B0]
0x18002b80b  mov     rax, [rax+18h]
0x18002b80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b814  mov     rcx, [rsp+440h+var_3E8]
0x18002b819  mov     edx, eax
0x18002b81b  xor     eax, eax
0x18002b81d  test    edx, edx
0x18002b81f  cmovns  eax, dword ptr [rsp+440h+var_400]
0x18002b824  test    eax, eax
0x18002b826  jz      loc_18002BAB4
0x18002b82c  mov     [rsp+440h+var_400], 0
0x18002b835  mov     rdx, [rbp+340h+var_3B0]
0x18002b839  lea     rcx, [rsp+440h+var_400]
0x18002b83e  call    ??4CStr@@QEAAXPEBG@Z; CStr::operator=(ushort const *)
0x18002b843  nop
0x18002b844  mov     rcx, [rsi]; pv
0x18002b847  call    cs:__imp_CoTaskMemFree
0x18002b84d  mov     rbx, [rsp+440h+var_400]
0x18002b852  test    rbx, rbx
0x18002b855  jz      loc_18002BAA5
0x18002b85b  mov     al, [rbx]
0x18002b85d  sub     al, 23h ; '#'
0x18002b85f  cmp     al, 1
0x18002b861  jbe     loc_18002BAA5
0x18002b867  mov     r8, r12; char *
0x18002b86a  mov     rdx, r15; unsigned __int64
0x18002b86d  lea     rcx, [rbp+340h+FileName]; char *
0x18002b871  cmp     [rbp+340h+var_3A8], 1
0x18002b875  jnz     loc_18002B8FF
0x18002b87b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002b880  mov     rdx, r15; unsigned __int64
0x18002b883  lea     rcx, [rbp+340h+FileName]; lpszStart
0x18002b887  call    ?AddTrailingBackslash@@YAXPEAD_K@Z; AddTrailingBackslash(char *,unsigned __int64)
0x18002b88c  mov     r8, rbx; char *
0x18002b88f  mov     rdx, r15; unsigned __int64
0x18002b892  lea     rcx, [rbp+340h+FileName]; char *
0x18002b896  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002b89b  xor     eax, eax
0x18002b89d  mov     [rbp+340h+var_250], ax
0x18002b8a4  mov     ebx, 208h
0x18002b8a9  test    r14, r14
0x18002b8ac  jz      short loc_18002B8D4
0x18002b8ae  mov     r8, r14; unsigned __int16 *
0x18002b8b1  mov     edx, ebx; unsigned __int64
0x18002b8b3  lea     rcx, [rbp+340h+var_250]; unsigned __int16 *
0x18002b8ba  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b8bf  lea     r8, asc_18007E934; "\\"
0x18002b8c6  mov     edx, ebx; unsigned __int64
0x18002b8c8  lea     rcx, [rbp+340h+var_250]; unsigned __int16 *
0x18002b8cf  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002b8d4  mov     r8, [rbp+340h+var_3B0]; unsigned __int16 *
0x18002b8d8  mov     rdx, rbx; unsigned __int64
0x18002b8db  lea     rcx, [rbp+340h+var_250]; unsigned __int16 *
0x18002b8e2  call    ?StringCbCatW@@YAJPEAG_KPEBG@Z; StringCbCatW(ushort *,unsigned __int64,ushort const *)
0x18002b8e7  lea     r8, [rbp+340h+var_250]; unsigned __int16 *
0x18002b8ee  lea     rdx, [rbp+340h+FileName]; char *
0x18002b8f2  mov     rcx, rsi; this
0x18002b8f5  call    ?WriteStorageContents@CFSClient@@QEAAXPEBDPEBG@Z; CFSClient::WriteStorageContents(char const *,ushort const *)
0x18002b8fa  jmp     loc_18002BAA5
0x18002b8ff  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002b904  mov     rdx, r15; unsigned __int64
0x18002b907  lea     rcx, [rbp+340h+FileName]; lpszStart
0x18002b90b  call    ?AddTrailingBackslash@@YAXPEAD_K@Z; AddTrailingBackslash(char *,unsigned __int64)
0x18002b910  mov     r8, rbx; char *
0x18002b913  mov     rdx, r15; unsigned __int64
0x18002b916  lea     rcx, [rbp+340h+FileName]; char *
0x18002b91a  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002b91f  mov     qword ptr [rsp+440h+SecurityAttributes.nLength], 18h
0x18002b928  mov     qword ptr [rbp+340h+SecurityAttributes.bInheritHandle], 0
0x18002b930  mov     [rbp+340h+SecurityAttributes.lpSecurityDescriptor], 0
0x18002b938  mov     [rsp+440h+hTemplateFile], 0; hTemplateFile
0x18002b941  mov     [rsp+440h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18002b949  mov     [rsp+440h+dwCreationDisposition], 2; dwCreationDisposition
0x18002b951  lea     r9, [rsp+440h+SecurityAttributes]; lpSecurityAttributes
0x18002b956  xor     r8d, r8d; dwShareMode
0x18002b959  mov     edx, 40000000h; dwDesiredAccess
0x18002b95e  lea     rcx, [rbp+340h+FileName]; lpFileName
0x18002b962  call    cs:__imp_CreateFileA
0x18002b968  mov     r15, rax
0x18002b96b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002b96f  jz      short loc_18002B99C
0x18002b971  mov     edx, [rbp+340h+var_3A0]; int
0x18002b974  lea     rcx, [rsp+440h+lpBuffer]; this
0x18002b979  call    ??0CMem@@QEAA@H@Z; CMem::CMem(int)
0x18002b97e  nop
0x18002b97f  cmp     [rsp+440h+lpBuffer], 0
0x18002b985  jnz     short loc_18002B9AB
0x18002b987  mov     rcx, r15; hObject
0x18002b98a  call    cs:__imp_CloseHandle
0x18002b990  nop
0x18002b991  lea     rcx, [rsp+440h+lpBuffer]; this
0x18002b996  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002b99b  nop
0x18002b99c  lea     rcx, [rsp+440h+var_400]; this
0x18002b9a1  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002b9a6  jmp     loc_18002B7D1
0x18002b9ab  mov     [rsp+440h+nNumberOfBytesToWrite], 0
0x18002b9b3  test    r14, r14
0x18002b9b6  jz      short loc_18002BA1F
0x18002b9b8  mov     [rsp+440h+var_3D0], 0
0x18002b9c1  mov     rdx, r14
0x18002b9c4  lea     rcx, [rsp+440h+var_3D0]
0x18002b9c9  call    ??4CStr@@QEAAXPEBG@Z; CStr::operator=(ushort const *)
0x18002b9ce  mov     r8, [rsp+440h+var_3D0]; char *
0x18002b9d3  mov     r10d, 104h
0x18002b9d9  mov     edx, r10d; unsigned __int64
0x18002b9dc  lea     rcx, [rbp+340h+FileName]; char *
0x18002b9e0  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002b9e5  mov     edx, r10d; unsigned __int64
0x18002b9e8  lea     rcx, [rbp+340h+FileName]; lpszStart
0x18002b9ec  call    ?AddTrailingBackslash@@YAXPEAD_K@Z; AddTrailingBackslash(char *,unsigned __int64)
0x18002b9f1  mov     r8, rbx; char *
0x18002b9f4  mov     edx, 104h; unsigned __int64
0x18002b9f9  lea     rcx, [rbp+340h+FileName]; char *
0x18002b9fd  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002ba02  lea     rdx, [rbp+340h+FileName]
0x18002ba06  lea     rcx, [rsp+440h+var_400]
0x18002ba0b  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18002ba10  lea     rcx, [rsp+440h+var_3D0]; this
0x18002ba15  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002ba1a  mov     rbx, [rsp+440h+var_400]
0x18002ba1f  mov     rdx, rbx; char *
0x18002ba22  mov     rcx, rsi; this
0x18002ba25  call    ?OpenStream@CFSClient@@QEAAJPEBDK@Z; CFSClient::OpenStream(char const *,ulong)
0x18002ba2a  mov     ebx, eax
0x18002ba2c  test    eax, eax
0x18002ba2e  js      short loc_18002BA7D
0x18002ba30  lea     r9, [rsp+440h+nNumberOfBytesToWrite]; unsigned int *
0x18002ba35  mov     r8d, [rbp+340h+var_3A0]; unsigned int
0x18002ba39  mov     rdx, [rsp+440h+lpBuffer]; void *
0x18002ba3e  mov     rcx, rsi; this
0x18002ba41  call    ?Read@CFSClient@@QEAAJPEAXKPEAK@Z; CFSClient::Read(void *,ulong,ulong *)
0x18002ba46  mov     ebx, eax
0x18002ba48  mov     [rsp+440h+NumberOfBytesWritten], 0
0x18002ba50  test    eax, eax
0x18002ba52  js      short loc_18002BA75
0x18002ba54  mov     qword ptr [rsp+440h+dwCreationDisposition], 0; lpOverlapped
0x18002ba5d  lea     r9, [rsp+440h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18002ba62  mov     r8d, [rsp+440h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18002ba67  mov     rdx, [rsp+440h+lpBuffer]; lpBuffer
0x18002ba6c  mov     rcx, r15; hFile
0x18002ba6f  call    cs:__imp_WriteFile
0x18002ba75  mov     rcx, rsi; this
0x18002ba78  call    ?CloseStream@CFSClient@@QEAAXXZ; CFSClient::CloseStream(void)
0x18002ba7d  mov     rcx, r15; hObject
0x18002ba80  call    cs:__imp_CloseHandle
0x18002ba86  test    ebx, ebx
0x18002ba88  jns     short loc_18002BA95
0x18002ba8a  lea     rcx, [rbp+340h+FileName]; lpFileName
0x18002ba8e  call    cs:__imp_DeleteFileA
0x18002ba94  nop
0x18002ba95  lea     rcx, [rsp+440h+lpBuffer]; this
0x18002ba9a  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002ba9f  mov     r15d, 104h
0x18002baa5  lea     rcx, [rsp+440h+var_400]; this
0x18002baaa  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002baaf  jmp     loc_18002B7D7
0x18002bab4  test    rcx, rcx
0x18002bab7  jz      short loc_18002BACE
0x18002bab9  mov     rax, [rcx]
0x18002babc  mov     rax, [rax+10h]
0x18002bac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bac5  mov     [rsp+440h+var_3E8], 0
0x18002bace  test    r13d, r13d
0x18002bad1  jz      short loc_18002BAE9
0x18002bad3  mov     rcx, [rsp+440h+var_3E0]
0x18002bad8  test    rcx, rcx
0x18002badb  jz      short loc_18002BAE9
0x18002badd  mov     rax, [rcx]
0x18002bae0  mov     rax, [rax+10h]
0x18002bae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bae9  mov     rcx, [rbp+340h+var_40]
0x18002baf0  xor     rcx, rsp; StackCookie
0x18002baf3  call    __security_check_cookie
0x18002baf8  add     rsp, 410h
0x18002baff  pop     r15
0x18002bb01  pop     r14
0x18002bb03  pop     r13
0x18002bb05  pop     r12
0x18002bb07  pop     rsi
0x18002bb08  pop     rbx
0x18002bb09  pop     rbp
0x18002bb0a  retn
```
