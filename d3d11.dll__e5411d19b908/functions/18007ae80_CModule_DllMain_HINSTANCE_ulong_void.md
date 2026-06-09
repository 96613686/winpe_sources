# CModule::DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18007ae80`
- end: `0x18007b198`
- name: `?DllMain@CModule@@QEAAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `792`
- prototype: `int(CModule *__hidden this, HINSTANCE, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18007ae18`

## callees

- `0x18007ae80`
- `0x18007b1a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007aeb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b0a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b0f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b153`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007aeb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b0a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b0f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007b153`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b09a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b128`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b164`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b09a`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b128`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18007b164`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b104`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b0b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007b104`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007aec1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18007aec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007afce`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18007afce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007aef0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007af5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007aef0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007af5c`

## pseudocode

```c
_BOOL8 __fastcall CModule::DllMain(CModule *this, HINSTANCE a2, int a3, void *a4)
{
  unsigned int v5; // esi
  HANDLE v6; // rax
  WCHAR *v7; // rdi
  unsigned int v8; // ebp
  DWORD ModuleFileNameW; // eax
  DWORD v10; // ecx
  bool v11; // zf
  __int64 v12; // rcx
  unsigned int v13; // eax
  __int64 v14; // r14
  DWORD v15; // ebx
  DWORD v16; // eax
  DWORD v17; // ecx
  __int64 v18; // rcx
  int i; // eax
  unsigned int v20; // ebx
  WCHAR *v21; // r14
  UINT v22; // ebx
  UINT SystemDirectoryW; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // edx
  HANDLE v28; // rax
  WCHAR *v29; // rax
  HANDLE v30; // rax
  void *v31; // rbx
  HANDLE ProcessHeap; // rax
  HANDLE v33; // rax
  WCHAR *v34; // rax
  HANDLE v35; // rax
  WCHAR *v36; // rax

  v5 = 1;
  if ( !a3 )
  {
    UnregisterLeakedDeviceTrimNotifications();
    v31 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v31);
    }
    return 1;
  }
  if ( a3 != 1 )
    return 1;
  v6 = GetProcessHeap();
  v7 = (WCHAR *)HeapAlloc(v6, 0, 0x208u);
  if ( !v7 )
    return 0;
  v8 = 260;
  while ( 1 )
  {
    if ( v8 >= 2 )
    {
      ModuleFileNameW = GetModuleFileNameW(0, v7, v8 - 2);
      v10 = ModuleFileNameW;
      LODWORD(qword_18022B8E8) = ModuleFileNameW;
      if ( ModuleFileNameW != v8 - 2 )
        break;
    }
    v8 += 260;
    v28 = GetProcessHeap();
    v29 = (WCHAR *)HeapReAlloc(v28, 0, v7, 2LL * v8);
    if ( !v29 )
    {
LABEL_30:
      v30 = GetProcessHeap();
      HeapFree(v30, 0, v7);
      return 0;
    }
    v7 = v29;
  }
  if ( ModuleFileNameW )
  {
    do
    {
      if ( v7[v10] == 92 )
        break;
      v11 = v10-- == 1;
      LODWORD(qword_18022B8E8) = v10;
    }
    while ( !v11 );
  }
  v12 = v10 + 1;
  LODWORD(qword_18022B8E8) = v12;
  v7[v12] = 0;
  v13 = qword_18022B8E8 + 1;
  LODWORD(qword_18022B8E8) = qword_18022B8E8 + 1;
  while ( 1 )
  {
    if ( v8 - v13 >= 2 )
    {
      v14 = v13;
      v15 = v8 - v13 - 2;
      v16 = GetModuleFileNameW(a2, &v7[v13], v15);
      v17 = v16;
      HIDWORD(qword_18022B8E8) = v16;
      if ( v16 != v15 )
        break;
    }
    v8 += 260;
    v35 = GetProcessHeap();
    v36 = (WCHAR *)HeapReAlloc(v35, 0, v7, 2LL * v8);
    if ( !v36 )
      goto LABEL_30;
    v7 = v36;
    v13 = qword_18022B8E8;
  }
  if ( v16 )
  {
    do
    {
      if ( v7[v14 + v17] == 92 )
        break;
      v11 = v17-- == 1;
      HIDWORD(qword_18022B8E8) = v17;
    }
    while ( !v11 );
  }
  v18 = v17 + 1;
  HIDWORD(qword_18022B8E8) = v18;
  v7[v14 + v18] = 0;
  for ( i = ++HIDWORD(qword_18022B8E8); ; i = HIDWORD(qword_18022B8E8) )
  {
    v20 = v8 - i - qword_18022B8E8;
    if ( v20 >= 2 )
    {
      v21 = &v7[(unsigned int)(qword_18022B8E8 + i)];
      v22 = v20 - 2;
      SystemDirectoryW = GetSystemDirectoryW(v21, v22);
      LODWORD(qword_18022B8F0) = SystemDirectoryW;
      if ( SystemDirectoryW < v22 )
        break;
    }
    v8 += 260;
    v33 = GetProcessHeap();
    v34 = (WCHAR *)HeapReAlloc(v33, 0, v7, 2LL * v8);
    if ( !v34 )
      goto LABEL_30;
    v7 = v34;
  }
  if ( v21[SystemDirectoryW] || SystemDirectoryW <= 1 )
  {
    *v21 = 0;
    LODWORD(qword_18022B8F0) = 1;
  }
  else
  {
    v24 = SystemDirectoryW - 1;
    LODWORD(qword_18022B8F0) = SystemDirectoryW - 1;
    if ( v21[v24] != 92 )
    {
      LODWORD(qword_18022B8F0) = SystemDirectoryW;
      v21[SystemDirectoryW] = 92;
      LODWORD(v24) = qword_18022B8F0;
    }
    v25 = (unsigned int)(v24 + 1);
    LODWORD(qword_18022B8F0) = v25;
    v21[v25] = 0;
    LODWORD(qword_18022B8F0) = qword_18022B8F0 + 1;
    v5 = qword_18022B8F0;
  }
  lpMem = v7;
  *(&lpMem + 1) = &v7[(unsigned int)qword_18022B8E8];
  v26 = HIDWORD(qword_18022B8E8);
  qword_18022B8E0 = (__int64)&v7[(unsigned int)qword_18022B8E8 + (unsigned __int64)HIDWORD(qword_18022B8E8)];
  if ( (unsigned int)qword_18022B8E8 >= HIDWORD(qword_18022B8E8) )
    v26 = qword_18022B8E8;
  if ( v26 < v5 )
    v26 = v5;
  HIDWORD(qword_18022B8F0) = v26;
  return !ATL::CAtlBaseModule::m_bInitFailed;
}

```

## disassembly

```asm
0x18007ae80  push    rbx
0x18007ae82  push    rbp
0x18007ae83  push    rsi
0x18007ae84  push    rdi
0x18007ae85  push    r12
0x18007ae87  push    r13
0x18007ae89  push    r14
0x18007ae8b  push    r15
0x18007ae8d  sub     rsp, 28h
0x18007ae91  mov     r15, rdx
0x18007ae94  mov     eax, r8d
0x18007ae97  mov     esi, 1
0x18007ae9c  xor     r12d, r12d
0x18007ae9f  test    r8d, r8d
0x18007aea2  jz      loc_18007B0E5
0x18007aea8  cmp     eax, esi
0x18007aeaa  jnz     loc_18007B0C1
0x18007aeb0  call    cs:__imp_GetProcessHeap
0x18007aeb6  mov     rcx, rax; hHeap
0x18007aeb9  xor     edx, edx; dwFlags
0x18007aebb  mov     r8d, 208h; dwBytes
0x18007aec1  call    cs:__imp_HeapAlloc
0x18007aec7  mov     rdi, rax
0x18007aeca  test    rax, rax
0x18007aecd  jz      loc_18007B0BD
0x18007aed3  mov     r14d, 104h
0x18007aed9  mov     ebp, r14d
0x18007aedc  cmp     ebp, 2
0x18007aedf  jb      loc_18007B081
0x18007aee5  lea     ebx, [rbp-2]
0x18007aee8  mov     r8d, ebx; nSize
0x18007aeeb  mov     rdx, rdi; lpFilename
0x18007aeee  xor     ecx, ecx; hModule
0x18007aef0  call    cs:__imp_GetModuleFileNameW
0x18007aef6  mov     ecx, eax
0x18007aef8  mov     dword ptr cs:qword_18022B8E8, eax
0x18007aefe  cmp     eax, ebx
0x18007af00  jz      loc_18007B081
0x18007af06  mov     r13d, 5Ch ; '\'
0x18007af0c  test    eax, eax
0x18007af0e  jz      short loc_18007AF24
0x18007af10  mov     eax, ecx
0x18007af12  cmp     [rdi+rax*2], r13w
0x18007af17  jz      short loc_18007AF24
0x18007af19  add     ecx, 0FFFFFFFFh
0x18007af1c  mov     dword ptr cs:qword_18022B8E8, ecx
0x18007af22  jnz     short loc_18007AF10
0x18007af24  add     ecx, esi
0x18007af26  mov     dword ptr cs:qword_18022B8E8, ecx
0x18007af2c  mov     [rdi+rcx*2], r12w
0x18007af31  mov     eax, dword ptr cs:qword_18022B8E8
0x18007af37  add     eax, esi
0x18007af39  mov     dword ptr cs:qword_18022B8E8, eax
0x18007af3f  mov     ebx, ebp
0x18007af41  sub     ebx, eax
0x18007af43  cmp     ebx, 2
0x18007af46  jb      loc_18007B14B
0x18007af4c  mov     r14d, eax
0x18007af4f  add     ebx, 0FFFFFFFEh
0x18007af52  lea     rdx, [rdi+r14*2]; lpFilename
0x18007af56  mov     r8d, ebx; nSize
0x18007af59  mov     rcx, r15; hModule
0x18007af5c  call    cs:__imp_GetModuleFileNameW
0x18007af62  mov     ecx, eax
0x18007af64  mov     dword ptr cs:qword_18022B8E8+4, eax
0x18007af6a  cmp     eax, ebx
0x18007af6c  jz      loc_18007B145
0x18007af72  test    eax, eax
0x18007af74  jz      short loc_18007AF8D
0x18007af76  mov     eax, ecx
0x18007af78  add     rax, r14
0x18007af7b  cmp     [rdi+rax*2], r13w
0x18007af80  jz      short loc_18007AF8D
0x18007af82  add     ecx, 0FFFFFFFFh
0x18007af85  mov     dword ptr cs:qword_18022B8E8+4, ecx
0x18007af8b  jnz     short loc_18007AF76
0x18007af8d  add     ecx, esi
0x18007af8f  mov     dword ptr cs:qword_18022B8E8+4, ecx
0x18007af95  add     rcx, r14
0x18007af98  mov     [rdi+rcx*2], r12w
0x18007af9d  mov     eax, dword ptr cs:qword_18022B8E8+4
0x18007afa3  add     eax, esi
0x18007afa5  mov     dword ptr cs:qword_18022B8E8+4, eax
0x18007afab  mov     ebx, ebp
0x18007afad  sub     ebx, eax
0x18007afaf  mov     ecx, dword ptr cs:qword_18022B8E8
0x18007afb5  sub     ebx, ecx
0x18007afb7  cmp     ebx, 2
0x18007afba  jb      loc_18007B10C
0x18007afc0  add     eax, ecx
0x18007afc2  lea     r14, [rdi+rax*2]
0x18007afc6  add     ebx, 0FFFFFFFEh
0x18007afc9  mov     edx, ebx; uSize
0x18007afcb  mov     rcx, r14; lpBuffer
0x18007afce  call    cs:__imp_GetSystemDirectoryW
0x18007afd4  mov     edx, eax
0x18007afd6  mov     dword ptr cs:qword_18022B8F0, edx
0x18007afdc  cmp     eax, ebx
0x18007afde  jnb     loc_18007B10C
0x18007afe4  cmp     [r14+rdx*2], r12w
0x18007afe9  jnz     loc_18007B181
0x18007afef  cmp     edx, esi
0x18007aff1  jbe     loc_18007B181
0x18007aff7  lea     ecx, [rdx-1]
0x18007affa  mov     dword ptr cs:qword_18022B8F0, ecx
0x18007b000  cmp     [r14+rcx*2], r13w
0x18007b005  jz      short loc_18007B018
0x18007b007  mov     dword ptr cs:qword_18022B8F0, edx
0x18007b00d  mov     [r14+rdx*2], r13w
0x18007b012  mov     ecx, dword ptr cs:qword_18022B8F0
0x18007b018  add     ecx, esi
0x18007b01a  mov     dword ptr cs:qword_18022B8F0, ecx
0x18007b020  mov     [r14+rcx*2], r12w
0x18007b025  mov     eax, dword ptr cs:qword_18022B8F0
0x18007b02b  add     eax, esi
0x18007b02d  mov     dword ptr cs:qword_18022B8F0, eax
0x18007b033  mov     esi, eax
0x18007b035  mov     qword ptr cs:lpMem, rdi
0x18007b03c  mov     ecx, dword ptr cs:qword_18022B8E8
0x18007b042  lea     rax, [rdi+rcx*2]
0x18007b046  mov     qword ptr cs:lpMem+8, rax
0x18007b04d  mov     edx, dword ptr cs:qword_18022B8E8+4
0x18007b053  lea     rax, [rcx+rdx]
0x18007b057  lea     rax, [rdi+rax*2]
0x18007b05b  mov     cs:qword_18022B8E0, rax
0x18007b062  cmp     ecx, edx
0x18007b064  cmovnb  edx, ecx
0x18007b067  cmp     edx, esi
0x18007b069  cmovb   edx, esi
0x18007b06c  mov     dword ptr cs:qword_18022B8F0+4, edx
0x18007b072  mov     eax, r12d
0x18007b075  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, r12b; bool ATL::CAtlBaseModule::m_bInitFailed
0x18007b07c  setz    al
0x18007b07f  jmp     short loc_18007B0D4
0x18007b081  add     ebp, r14d
0x18007b084  mov     ebx, ebp
0x18007b086  add     rbx, rbx
0x18007b089  call    cs:__imp_GetProcessHeap
0x18007b08f  mov     rcx, rax; hHeap
0x18007b092  mov     r9, rbx; dwBytes
0x18007b095  mov     r8, rdi; lpMem
0x18007b098  xor     edx, edx; dwFlags
0x18007b09a  call    cs:__imp_HeapReAlloc
0x18007b0a0  test    rax, rax
0x18007b0a3  jnz     loc_18007B190
0x18007b0a9  call    cs:__imp_GetProcessHeap
0x18007b0af  mov     rcx, rax; hHeap
0x18007b0b2  mov     r8, rdi; lpMem
0x18007b0b5  xor     edx, edx; dwFlags
0x18007b0b7  call    cs:__imp_HeapFree
0x18007b0bd  xor     eax, eax
0x18007b0bf  jmp     short loc_18007B0D4
0x18007b0c1  cmp     r8d, esi
0x18007b0c4  jnz     short loc_18007B0D2
0x18007b0c6  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, r12b; bool ATL::CAtlBaseModule::m_bInitFailed
0x18007b0cd  jz      short loc_18007B0D2
0x18007b0cf  mov     esi, r12d
0x18007b0d2  mov     eax, esi
0x18007b0d4  add     rsp, 28h
0x18007b0d8  pop     r15
0x18007b0da  pop     r14
0x18007b0dc  pop     r13
0x18007b0de  pop     r12
0x18007b0e0  pop     rdi
0x18007b0e1  pop     rsi
0x18007b0e2  pop     rbp
0x18007b0e3  pop     rbx
0x18007b0e4  retn
0x18007b0e5  call    ?UnregisterLeakedDeviceTrimNotifications@@YAXXZ; UnregisterLeakedDeviceTrimNotifications(void)
0x18007b0ea  mov     rbx, qword ptr cs:lpMem
0x18007b0f1  test    rbx, rbx
0x18007b0f4  jz      short loc_18007B0D2
0x18007b0f6  call    cs:__imp_GetProcessHeap
0x18007b0fc  mov     r8, rbx; lpMem
0x18007b0ff  xor     edx, edx; dwFlags
0x18007b101  mov     rcx, rax; hHeap
0x18007b104  call    cs:__imp_HeapFree
0x18007b10a  jmp     short loc_18007B0D2
0x18007b10c  add     ebp, 104h
0x18007b112  mov     ebx, ebp
0x18007b114  add     rbx, rbx
0x18007b117  call    cs:__imp_GetProcessHeap
0x18007b11d  mov     rcx, rax; hHeap
0x18007b120  mov     r9, rbx; dwBytes
0x18007b123  mov     r8, rdi; lpMem
0x18007b126  xor     edx, edx; dwFlags
0x18007b128  call    cs:__imp_HeapReAlloc
0x18007b12e  test    rax, rax
0x18007b131  jz      loc_18007B0A9
0x18007b137  mov     rdi, rax
0x18007b13a  mov     eax, dword ptr cs:qword_18022B8E8+4
0x18007b140  jmp     loc_18007AFAB
0x18007b145  mov     r14d, 104h
0x18007b14b  add     ebp, r14d
0x18007b14e  mov     ebx, ebp
0x18007b150  add     rbx, rbx
0x18007b153  call    cs:__imp_GetProcessHeap
0x18007b159  mov     rcx, rax; hHeap
0x18007b15c  mov     r9, rbx; dwBytes
0x18007b15f  mov     r8, rdi; lpMem
0x18007b162  xor     edx, edx; dwFlags
0x18007b164  call    cs:__imp_HeapReAlloc
0x18007b16a  test    rax, rax
0x18007b16d  jz      loc_18007B0A9
0x18007b173  mov     rdi, rax
0x18007b176  mov     eax, dword ptr cs:qword_18022B8E8
0x18007b17c  jmp     loc_18007AF3F
0x18007b181  mov     [r14], r12w
0x18007b185  mov     dword ptr cs:qword_18022B8F0, esi
0x18007b18b  jmp     loc_18007B035
0x18007b190  mov     rdi, rax
0x18007b193  jmp     loc_18007AEDC
```
