# CMemoryMappedCache::Commit(IMemoryMappedHeap *)

- ea: `0x180020fa0`
- end: `0x1800212f2`
- name: `?Commit@CMemoryMappedCache@@UEAAJPEAUIMemoryMappedHeap@@@Z`
- size: `850`
- prototype: `__int64 __fastcall(CMemoryMappedCache *__hidden this, struct IMemoryMappedHeap *)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callees

- `0x180020bdc`
- `0x180020fa0`
- `0x180021350`
- `0x180022070`
- `0x180024418`
- `0x180024a18`
- `0x18002568c`
- `0x180025c14`
- `0x180025e58`
- `0x18006ed20`
- `0x18006fb80`
- `0x1800a71ec`
- `0x1800a7250`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800211f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020fe9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020fe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002124f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002128b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800212cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800211a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002124f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002128b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800212cd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800210e7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800210e7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800212d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800212d7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002119c`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18002119c`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002115f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002115f`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180021137`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180021137`

## pseudocode

```c
__int64 __fastcall CMemoryMappedCache::Commit(CMemoryMappedCache *this, struct IMemoryMappedHeap *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r15
  int ObjectName; // ebx
  __int64 FileW; // rsi
  _QWORD *v7; // r14
  unsigned int v8; // r8d
  struct _SECURITY_ATTRIBUTES *v9; // r9
  __int64 v10; // rcx
  HANDLE FileMappingW; // rax
  void *v12; // r13
  void *v13; // r15
  __int64 v14; // rcx
  int v15; // r14d
  unsigned __int64 v17; // rdx
  DWORD dwMaximumSizeLow; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h] BYREF
  PSECURITY_DESCRIPTOR v20; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_ATTRIBUTES *v21; // [rsp+58h] [rbp-A8h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+80h] [rbp-80h]
  __int64 v25; // [rsp+88h] [rbp-78h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v28[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
  ObjectName = -2147467259;
  FileW = -1;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  if ( a2 )
  {
    if ( !*((_DWORD *)this + 4) )
    {
      ObjectName = CVersionManager::BeginCommitVersion(*((_QWORD *)this + 6), *((unsigned int *)this + 5));
      if ( ObjectName >= 0 )
      {
        v7 = (_QWORD *)((char *)this + 24);
        if ( (int)CVersionManager::GetNewestVersion(
                    *((_QWORD *)this + 6),
                    (char *)this + 32,
                    *((unsigned int *)this + 5),
                    (char *)this + 24) < 0 )
          *v7 = 1;
        else
          ++*v7;
        ObjectName = CMemoryMappedCache::_GetObjectName(this, v28, v8);
        if ( ObjectName >= 0 )
        {
          ObjectName = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", (char *)this + 88, v28);
          if ( ObjectName >= 0 )
          {
            LODWORD(v20) = *((_DWORD *)this + 5);
            v24 = 0;
            v9 = 0;
            v21 = 0;
            v22 = 0;
            v25 = 0;
            v26 = 0;
            v23 = 0;
            LODWORD(v23) = 24;
            if ( ((unsigned __int8)v20 & 2) != 0 )
            {
              CSecurityAttributesForSharedObjects::_InitializeWithInheritance(&v20, (const unsigned __int16 *)this + 44);
              v9 = v21;
            }
            FileW = (__int64)CreateFileW(FileName, 0xC0000000, 0, v9, 2u, 0, 0);
            if ( FileW == -1 )
            {
              ObjectName = ResultFromKnownLastError();
            }
            else
            {
              v10 = *(_QWORD *)a2;
              dwMaximumSizeLow = 0;
              ObjectName = (*(__int64 (__fastcall **)(struct IMemoryMappedHeap *, DWORD *))(v10 + 32))(
                             a2,
                             &dwMaximumSizeLow);
              if ( ObjectName < 0 )
                goto LABEL_31;
              FileMappingW = CreateFileMappingW((HANDLE)FileW, 0, 4u, 0, dwMaximumSizeLow, 0);
              v12 = FileMappingW;
              if ( FileMappingW )
              {
                v13 = MapViewOfFile(FileMappingW, 2u, 0, 0, dwMaximumSizeLow);
                if ( v13 )
                {
                  v14 = *(_QWORD *)a2;
                  Src = 0;
                  ObjectName = (*(__int64 (__fastcall **)(struct IMemoryMappedHeap *, void **))(v14 + 40))(a2, &Src);
                  if ( ObjectName >= 0 )
                  {
                    memcpy_0(v13, Src, dwMaximumSizeLow);
                    CloseHandle(*((HANDLE *)this + 9));
                    v17 = dwMaximumSizeLow;
                    *((_QWORD *)this + 9) = 0;
                    ObjectName = FlushView(v13, v17);
                  }
                  UnmapViewOfFile(v13);
                }
                else
                {
                  ObjectName = ResultFromKnownLastError();
                }
                CloseHandle(v12);
              }
              else
              {
                ObjectName = ResultFromKnownLastError();
              }
              if ( ObjectName < 0 )
              {
LABEL_31:
                CloseHandle((HANDLE)FileW);
                DeleteFileW(FileName);
                FileW = -1;
              }
            }
            CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects((CSecurityAttributesForSharedObjects *)&v20);
          }
          v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 608);
        }
        v15 = CVersionManager::EndCommitVersion(
                *((_QWORD *)this + 6),
                (char *)this + 32,
                *((unsigned int *)this + 5),
                *v7,
                ObjectName >= 0);
        if ( ObjectName >= 0 )
        {
          if ( v15 >= 0 )
          {
            *((_DWORD *)this + 4) = 1;
            CMemoryMappedCache::_CleanupOldCacheFiles(this);
          }
          ObjectName = v15;
        }
      }
    }
  }
  LeaveCriticalSection(v2);
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)ObjectName;
}

```

## disassembly

```asm
0x180020fa0  mov     [rsp-8+arg_10], rbx
0x180020fa5  push    rbp
0x180020fa6  push    rsi
0x180020fa7  push    rdi
0x180020fa8  push    r12
0x180020faa  push    r13
0x180020fac  push    r14
0x180020fae  push    r15
0x180020fb0  lea     rbp, [rsp-3D0h]
0x180020fb8  sub     rsp, 4D0h
0x180020fbf  mov     rax, cs:__security_cookie
0x180020fc6  xor     rax, rsp
0x180020fc9  mov     [rbp+400h+var_40], rax
0x180020fd0  lea     r15, [rcx+260h]
0x180020fd7  mov     rdi, rcx
0x180020fda  mov     rcx, r15; lpCriticalSection
0x180020fdd  mov     r12, rdx
0x180020fe0  mov     ebx, 80004005h
0x180020fe5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020fe9  call    cs:__imp_EnterCriticalSection
0x180020fef  xor     r13d, r13d
0x180020ff2  test    r12, r12
0x180020ff5  jz      loc_1800211EE
0x180020ffb  cmp     [rdi+10h], r13d
0x180020fff  jnz     loc_1800211EE
0x180021005  mov     edx, [rdi+14h]
0x180021008  mov     rcx, [rdi+30h]
0x18002100c  call    ?BeginCommitVersion@CVersionManager@@QEAAJW4CM_SCOPEFLAGS@@K@Z; CVersionManager::BeginCommitVersion(CM_SCOPEFLAGS,ulong)
0x180021011  mov     ebx, eax
0x180021013  test    eax, eax
0x180021015  js      loc_1800211EE
0x18002101b  mov     r8d, [rdi+14h]
0x18002101f  lea     r14, [rdi+18h]
0x180021023  mov     rcx, [rdi+30h]
0x180021027  lea     rdx, [rdi+20h]
0x18002102b  mov     r9, r14
0x18002102e  call    ?GetNewestVersion@CVersionManager@@QEAAJAEBU_GUID@@W4CM_SCOPEFLAGS@@PEA_K@Z; CVersionManager::GetNewestVersion(_GUID const &,CM_SCOPEFLAGS,unsigned __int64 *)
0x180021033  test    eax, eax
0x180021035  js      loc_18002122D
0x18002103b  inc     qword ptr [r14]
0x18002103e  lea     rdx, [rbp+400h+var_250]; unsigned __int16 *
0x180021045  mov     rcx, rdi; this
0x180021048  call    ?_GetObjectName@CMemoryMappedCache@@AEAAJPEAGK@Z; CMemoryMappedCache::_GetObjectName(ushort *,ulong)
0x18002104d  mov     ebx, eax
0x18002104f  test    eax, eax
0x180021051  js      loc_1800211C4
0x180021057  lea     rax, [rbp+400h+var_250]
0x18002105e  mov     edx, 104h; unsigned __int64
0x180021063  lea     r9, [rdi+58h]
0x180021067  mov     qword ptr [rsp+500h+dwCreationDisposition], rax
0x18002106c  lea     r8, aSS; "%s\\%s"
0x180021073  lea     rcx, [rbp+400h+FileName]; unsigned __int16 *
0x180021077  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002107c  mov     ebx, eax
0x18002107e  test    eax, eax
0x180021080  js      loc_1800211BD
0x180021086  mov     eax, [rdi+14h]
0x180021089  xorps   xmm0, xmm0
0x18002108c  xor     ecx, ecx
0x18002108e  mov     dword ptr [rsp+500h+var_4B0], eax
0x180021092  mov     [rbp+400h+var_480], rcx
0x180021096  xorps   xmm1, xmm1
0x180021099  mov     dword ptr [rbp+400h+var_480], r13d
0x18002109d  mov     r9, r13; lpSecurityAttributes
0x1800210a0  mov     [rsp+500h+var_4A8], r13
0x1800210a5  movdqa  [rsp+500h+var_4A0], xmm0
0x1800210ab  mov     [rbp+400h+var_478], r13
0x1800210af  movdqa  [rbp+400h+var_470], xmm1
0x1800210b4  movups  [rsp+500h+var_490], xmm0
0x1800210b9  mov     dword ptr [rsp+500h+var_490], 18h
0x1800210c1  test    al, 2
0x1800210c3  jnz     loc_180021270
0x1800210c9  mov     [rsp+500h+hTemplateFile], r13; hTemplateFile
0x1800210ce  lea     rcx, [rbp+400h+FileName]; lpFileName
0x1800210d2  mov     [rsp+500h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x1800210d7  xor     r8d, r8d; dwShareMode
0x1800210da  mov     edx, 0C0000000h; dwDesiredAccess
0x1800210df  mov     [rsp+500h+dwCreationDisposition], 2; dwCreationDisposition
0x1800210e7  call    cs:__imp_CreateFileW
0x1800210ed  mov     rsi, rax
0x1800210f0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800210f4  jz      loc_1800212E6
0x1800210fa  mov     rcx, [r12]
0x1800210fe  lea     rdx, [rsp+500h+dwMaximumSizeLow]
0x180021103  mov     [rsp+500h+dwMaximumSizeLow], r13d
0x180021108  mov     rax, [rcx+20h]
0x18002110c  mov     rcx, r12
0x18002110f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021114  mov     ebx, eax
0x180021116  test    eax, eax
0x180021118  js      loc_1800212CA
0x18002111e  mov     eax, [rsp+500h+dwMaximumSizeLow]
0x180021122  xor     r9d, r9d; dwMaximumSizeHigh
0x180021125  mov     qword ptr [rsp+500h+dwFlagsAndAttributes], r13; lpName
0x18002112a  xor     edx, edx; lpFileMappingAttributes
0x18002112c  mov     rcx, rsi; hFile
0x18002112f  mov     [rsp+500h+dwCreationDisposition], eax; dwMaximumSizeLow
0x180021133  lea     r8d, [r9+4]; flProtect
0x180021137  call    cs:__imp_CreateFileMappingW
0x18002113d  mov     r13, rax
0x180021140  test    rax, rax
0x180021143  jz      loc_1800212BE
0x180021149  mov     ecx, [rsp+500h+dwMaximumSizeLow]
0x18002114d  xor     r9d, r9d; dwFileOffsetLow
0x180021150  mov     qword ptr [rsp+500h+dwCreationDisposition], rcx; dwNumberOfBytesToMap
0x180021155  xor     r8d, r8d; dwFileOffsetHigh
0x180021158  mov     rcx, rax; hFileMappingObject
0x18002115b  lea     edx, [r9+2]; dwDesiredAccess
0x18002115f  call    cs:__imp_MapViewOfFile
0x180021165  mov     r15, rax
0x180021168  test    rax, rax
0x18002116b  jz      loc_1800212B2
0x180021171  mov     rcx, [r12]
0x180021175  lea     rdx, [rsp+500h+Src]
0x18002117a  mov     [rsp+500h+Src], 0
0x180021183  mov     rax, [rcx+28h]
0x180021187  mov     rcx, r12
0x18002118a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002118f  mov     ebx, eax
0x180021191  test    eax, eax
0x180021193  jns     loc_180021239
0x180021199  mov     rcx, r15; lpBaseAddress
0x18002119c  call    cs:__imp_UnmapViewOfFile
0x1800211a2  mov     rcx, r13; hObject
0x1800211a5  call    cs:__imp_CloseHandle
0x1800211ab  test    ebx, ebx
0x1800211ad  js      loc_1800212CA
0x1800211b3  lea     rcx, [rsp+500h+var_4B0]; this
0x1800211b8  call    ??1CSecurityAttributesForSharedObjects@@QEAA@XZ; CSecurityAttributesForSharedObjects::~CSecurityAttributesForSharedObjects(void)
0x1800211bd  lea     r15, [rdi+260h]
0x1800211c4  mov     r9, [r14]
0x1800211c7  lea     rdx, [rdi+20h]
0x1800211cb  mov     r8d, [rdi+14h]
0x1800211cf  mov     eax, ebx
0x1800211d1  mov     rcx, [rdi+30h]
0x1800211d5  not     eax
0x1800211d7  shr     eax, 1Fh
0x1800211da  mov     [rsp+500h+dwCreationDisposition], eax
0x1800211de  call    ?EndCommitVersion@CVersionManager@@QEAAJAEBU_GUID@@W4CM_SCOPEFLAGS@@_KHK@Z; CVersionManager::EndCommitVersion(_GUID const &,CM_SCOPEFLAGS,unsigned __int64,int,ulong)
0x1800211e3  mov     r14d, eax
0x1800211e6  test    ebx, ebx
0x1800211e8  jns     loc_180021296
0x1800211ee  mov     rcx, r15; lpCriticalSection
0x1800211f1  call    cs:__imp_LeaveCriticalSection
0x1800211f7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800211fb  jnz     loc_180021288
0x180021201  mov     eax, ebx
0x180021203  mov     rcx, [rbp+400h+var_40]
0x18002120a  xor     rcx, rsp; StackCookie
0x18002120d  call    __security_check_cookie
0x180021212  mov     rbx, [rsp+500h+arg_10]
0x18002121a  add     rsp, 4D0h
0x180021221  pop     r15
0x180021223  pop     r14
0x180021225  pop     r13
0x180021227  pop     r12
0x180021229  pop     rdi
0x18002122a  pop     rsi
0x18002122b  pop     rbp
0x18002122c  retn
0x18002122d  mov     qword ptr [r14], 1
0x180021234  jmp     loc_18002103E
0x180021239  mov     r8d, [rsp+500h+dwMaximumSizeLow]; Size
0x18002123e  mov     rcx, r15; void *
0x180021241  mov     rdx, [rsp+500h+Src]; Src
0x180021246  call    memcpy_0
0x18002124b  mov     rcx, [rdi+48h]; hObject
0x18002124f  call    cs:__imp_CloseHandle
0x180021255  mov     edx, [rsp+500h+dwMaximumSizeLow]; unsigned __int64
0x180021259  mov     rcx, r15; volatile void *
0x18002125c  mov     qword ptr [rdi+48h], 0
0x180021264  call    ?FlushView@@YAJPEDX_K@Z; FlushView(void const volatile *,unsigned __int64)
0x180021269  mov     ebx, eax
0x18002126b  jmp     loc_180021199
0x180021270  lea     rdx, [rdi+58h]; unsigned __int16 *
0x180021274  lea     rcx, [rsp+500h+var_4B0]; this
0x180021279  call    ?_InitializeWithInheritance@CSecurityAttributesForSharedObjects@@AEAAJPEBG@Z; CSecurityAttributesForSharedObjects::_InitializeWithInheritance(ushort const *)
0x18002127e  mov     r9, [rsp+500h+var_4A8]
0x180021283  jmp     loc_1800210C9
0x180021288  mov     rcx, rsi; hObject
0x18002128b  call    cs:__imp_CloseHandle
0x180021291  jmp     loc_180021201
0x180021296  test    r14d, r14d
0x180021299  js      short loc_1800212AA
0x18002129b  mov     rcx, rdi; this
0x18002129e  mov     dword ptr [rdi+10h], 1
0x1800212a5  call    ?_CleanupOldCacheFiles@CMemoryMappedCache@@AEAAXXZ; CMemoryMappedCache::_CleanupOldCacheFiles(void)
0x1800212aa  mov     ebx, r14d
0x1800212ad  jmp     loc_1800211EE
0x1800212b2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800212b7  mov     ebx, eax
0x1800212b9  jmp     loc_1800211A2
0x1800212be  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800212c3  mov     ebx, eax
0x1800212c5  jmp     loc_1800211AB
0x1800212ca  mov     rcx, rsi; hObject
0x1800212cd  call    cs:__imp_CloseHandle
0x1800212d3  lea     rcx, [rbp+400h+FileName]; lpFileName
0x1800212d7  call    cs:__imp_DeleteFileW
0x1800212dd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800212e1  jmp     loc_1800211B3
0x1800212e6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800212eb  mov     ebx, eax
0x1800212ed  jmp     loc_1800211B3
```
