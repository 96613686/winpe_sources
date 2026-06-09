# PpfTransformStore::GetInstanceInfo(ushort *,uint *)

- ea: `0x180038f70`
- end: `0x180039208`
- name: `?GetInstanceInfo@PpfTransformStore@@SAJPEAGPEAI@Z`
- size: `664`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800107e8`

## callees

- `0x180009c64`
- `0x18000dfe0`
- `0x18002b604`
- `0x18002d1a8`
- `0x18002d5ec`
- `0x180038f70`
- `0x180039210`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003906d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800391c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003906d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800391c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039081`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180039081`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800391da`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800390e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800391b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800390e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800391b5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039136`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039185`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039136`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180039185`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800390b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800390b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PpfTransformStore::GetInstanceInfo(unsigned __int16 *a1, unsigned int *a2)
{
  void **v4; // rdi
  void **v5; // rax
  unsigned int v6; // ebx
  int v7; // eax
  int TransformsKeyPath; // eax
  int v9; // edi
  void *v10; // rbx
  HANDLE v11; // rax
  unsigned int ValueW; // eax
  __int64 v13; // rdx
  HANDLE ProcessHeap; // rax
  int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  DWORD pcbData; // [rsp+40h] [rbp-20h] BYREF
  DWORD v19; // [rsp+44h] [rbp-1Ch] BYREF
  HKEY hkey; // [rsp+48h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int pvData; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+48h] BYREF

  v4 = &qword_180072C30;
  v5 = &qword_180072C30;
  if ( (unsigned __int64)qword_180072C48 > 7 )
    v5 = (void **)qword_180072C30;
  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    0x247u,
    "PpfTransformStore::GetInstanceInfo",
    "Getting instance info: '%ws'",
    v5);
  if ( qword_180072C40 )
  {
    *a1 = 0;
    *a2 = 0;
    hKey = 0;
    v7 = PpfSystemCcsKey::Open((PpfSystemCcsKey *)&hKey);
    v6 = v7;
    if ( v7 >= 0 )
    {
      lpMem = 0;
      if ( (unsigned __int64)qword_180072C48 > 7 )
        v4 = (void **)qword_180072C30;
      TransformsKeyPath = GetTransformsKeyPath(v4, (__int64 *)&lpMem);
      v9 = TransformsKeyPath;
      if ( TransformsKeyPath >= 0 )
      {
        hkey = 0;
        v10 = lpMem;
        ValueW = RegOpenKeyExW(hKey, (LPCWSTR)lpMem, 0, 0x20019u, &hkey);
        if ( ValueW )
        {
          v13 = 596;
        }
        else
        {
          pvData = 0;
          pcbData = 4;
          ValueW = RegGetValueW(hkey, 0, L"LogDigestAlgID", 0x20000010u, 0, &pvData, &pcbData);
          if ( ValueW )
          {
            v13 = 601;
          }
          else
          {
            v25 = 0;
            v19 = 4;
            ValueW = RegGetValueW(hkey, 0, L"LogSupportedDigestAlgIDBitmap", 0x20000010u, 0, &v25, &v19);
            if ( !ValueW )
            {
              *a1 = pvData;
              *a2 = v25;
              if ( hkey )
                RegCloseKey(hkey);
              if ( v10 )
              {
                ProcessHeap = GetProcessHeap();
                HeapFree(ProcessHeap, 0, v10);
              }
              v6 = 0;
              goto LABEL_27;
            }
            v13 = 606;
          }
        }
        v9 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v13,
               (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
               (const char *)ValueW,
               phkResulta);
        if ( hkey )
          RegCloseKey(hkey);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x251,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
          (const char *)(unsigned int)TransformsKeyPath,
          phkResult);
        v10 = lpMem;
      }
      if ( v10 )
      {
        v11 = GetProcessHeap();
        HeapFree(v11, 0, v10);
      }
      v6 = v9;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
        (const char *)(unsigned int)v7,
        phkResult);
    }
LABEL_27:
    PpfSystemCcsKey::~PpfSystemCcsKey(&hKey);
    return v6;
  }
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x248,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
    (const char *)0x80070057LL,
    phkResult);
  return v6;
}

```

## disassembly

```asm
0x180038f70  mov     [rsp-28h+arg_0], rbx
0x180038f75  push    rbp
0x180038f76  push    rsi
0x180038f77  push    rdi
0x180038f78  push    r12
0x180038f7a  push    r14
0x180038f7c  mov     rbp, rsp
0x180038f7f  sub     rsp, 60h
0x180038f83  mov     rsi, rdx
0x180038f86  mov     r14, rcx
0x180038f89  lea     rdi, qword_180072C30
0x180038f90  mov     rax, rdi
0x180038f93  cmp     cs:qword_180072C48, 7
0x180038f9b  cmova   rax, cs:qword_180072C30
0x180038fa3  mov     [rsp+60h+phkResult], rax; int
0x180038fa8  lea     r9, aGettingInstanc; "Getting instance info: '%ws'"
0x180038faf  lea     r8, aPpftransformst_3; "PpfTransformStore::GetInstanceInfo"
0x180038fb6  mov     edx, 247h; unsigned int
0x180038fbb  lea     r12, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038fc2  mov     rcx, r12; char *
0x180038fc5  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038fca  cmp     cs:qword_180072C40, 0
0x180038fd2  jnz     short loc_180038FF2
0x180038fd4  mov     rcx, [rbp+28h]; this
0x180038fd8  mov     ebx, 80070057h
0x180038fdd  mov     r9d, ebx; char *
0x180038fe0  mov     r8, r12; unsigned int
0x180038fe3  mov     edx, 248h; void *
0x180038fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038fed  jmp     loc_1800391F1
0x180038ff2  xor     eax, eax
0x180038ff4  mov     [r14], ax
0x180038ff8  mov     [rsi], eax
0x180038ffa  mov     [rbp+hKey], rax
0x180038ffe  lea     rcx, [rbp+hKey]; this
0x180039002  call    ?Open@PpfSystemCcsKey@@QEAAJXZ; PpfSystemCcsKey::Open(void)
0x180039007  mov     ebx, eax
0x180039009  test    eax, eax
0x18003900b  jns     short loc_180039026
0x18003900d  mov     rcx, [rbp+28h]; this
0x180039011  mov     r9d, eax; char *
0x180039014  mov     r8, r12; unsigned int
0x180039017  mov     edx, 24Eh; void *
0x18003901c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039021  jmp     loc_1800391E8
0x180039026  mov     [rbp+lpMem], 0
0x18003902e  cmp     cs:qword_180072C48, 7
0x180039036  cmova   rdi, cs:qword_180072C30
0x18003903e  lea     rdx, [rbp+lpMem]
0x180039042  mov     rcx, rdi
0x180039045  call    GetTransformsKeyPath
0x18003904a  mov     edi, eax
0x18003904c  test    eax, eax
0x18003904e  jns     short loc_180039094
0x180039050  mov     rcx, [rbp+28h]; this
0x180039054  mov     r9d, eax; char *
0x180039057  mov     r8, r12; unsigned int
0x18003905a  mov     edx, 251h; void *
0x18003905f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039064  mov     rbx, [rbp+lpMem]
0x180039068  test    rbx, rbx
0x18003906b  jz      short loc_18003908D
0x18003906d  call    cs:__imp_GetProcessHeap
0x180039074  nop     dword ptr [rax+rax+00h]
0x180039079  mov     rcx, rax; hHeap
0x18003907c  mov     r8, rbx; lpMem
0x18003907f  xor     edx, edx; dwFlags
0x180039081  call    cs:__imp_HeapFree
0x180039088  nop     dword ptr [rax+rax+00h]
0x18003908d  mov     ebx, edi
0x18003908f  jmp     loc_1800391E8
0x180039094  mov     [rbp+hkey], 0
0x18003909c  lea     rax, [rbp+hkey]
0x1800390a0  mov     [rsp+60h+phkResult], rax; unsigned int
0x1800390a5  mov     r9d, 20019h; samDesired
0x1800390ab  xor     r8d, r8d; ulOptions
0x1800390ae  mov     rbx, [rbp+lpMem]
0x1800390b2  mov     rdx, rbx; lpSubKey
0x1800390b5  mov     rcx, [rbp+hKey]; hKey
0x1800390b9  call    cs:__imp_RegOpenKeyExW
0x1800390c0  nop     dword ptr [rax+rax+00h]
0x1800390c5  test    eax, eax
0x1800390c7  jz      short loc_1800390F9
0x1800390c9  mov     edx, 254h; void *
0x1800390ce  mov     rcx, [rbp+28h]; this
0x1800390d2  mov     r9d, eax; char *
0x1800390d5  mov     r8, r12; unsigned int
0x1800390d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800390dd  mov     edi, eax
0x1800390df  mov     rcx, [rbp+hkey]; hKey
0x1800390e3  test    rcx, rcx
0x1800390e6  jz      short loc_180039068
0x1800390e8  call    cs:__imp_RegCloseKey
0x1800390ef  nop     dword ptr [rax+rax+00h]
0x1800390f4  jmp     loc_180039068
0x1800390f9  mov     [rbp+arg_10], 0
0x180039100  mov     edi, 4
0x180039105  mov     [rbp+var_20], edi
0x180039108  lea     rax, [rbp+var_20]
0x18003910c  mov     [rsp+60h+pcbData], rax; pcbData
0x180039111  lea     rax, [rbp+arg_10]
0x180039115  mov     [rsp+60h+pvData], rax; pvData
0x18003911a  mov     [rsp+60h+phkResult], 0; pdwType
0x180039123  mov     r9d, 20000010h; dwFlags
0x180039129  lea     r8, aLogdigestalgid; "LogDigestAlgID"
0x180039130  xor     edx, edx; lpSubKey
0x180039132  mov     rcx, [rbp+hkey]; hkey
0x180039136  call    cs:__imp_RegGetValueW
0x18003913d  nop     dword ptr [rax+rax+00h]
0x180039142  test    eax, eax
0x180039144  jz      short loc_18003914D
0x180039146  mov     edx, 259h
0x18003914b  jmp     short loc_1800390CE
0x18003914d  mov     [rbp+arg_18], 0
0x180039154  mov     [rbp+var_1C], edi
0x180039157  lea     rax, [rbp+var_1C]
0x18003915b  mov     [rsp+60h+pcbData], rax; pcbData
0x180039160  lea     rax, [rbp+arg_18]
0x180039164  mov     [rsp+60h+pvData], rax; pvData
0x180039169  mov     [rsp+60h+phkResult], 0; pdwType
0x180039172  mov     r9d, 20000010h; dwFlags
0x180039178  lea     r8, aLogsupporteddi; "LogSupportedDigestAlgIDBitmap"
0x18003917f  xor     edx, edx; lpSubKey
0x180039181  mov     rcx, [rbp+hkey]; hkey
0x180039185  call    cs:__imp_RegGetValueW
0x18003918c  nop     dword ptr [rax+rax+00h]
0x180039191  test    eax, eax
0x180039193  jz      short loc_18003919F
0x180039195  mov     edx, 25Eh
0x18003919a  jmp     loc_1800390CE
0x18003919f  movzx   eax, word ptr [rbp+arg_10]
0x1800391a3  mov     [r14], ax
0x1800391a7  mov     eax, [rbp+arg_18]
0x1800391aa  mov     [rsi], eax
0x1800391ac  mov     rcx, [rbp+hkey]; hKey
0x1800391b0  test    rcx, rcx
0x1800391b3  jz      short loc_1800391C1
0x1800391b5  call    cs:__imp_RegCloseKey
0x1800391bc  nop     dword ptr [rax+rax+00h]
0x1800391c1  test    rbx, rbx
0x1800391c4  jz      short loc_1800391E6
0x1800391c6  call    cs:__imp_GetProcessHeap
0x1800391cd  nop     dword ptr [rax+rax+00h]
0x1800391d2  mov     rcx, rax; hHeap
0x1800391d5  mov     r8, rbx; lpMem
0x1800391d8  xor     edx, edx; dwFlags
0x1800391da  call    cs:__imp_HeapFree
0x1800391e1  nop     dword ptr [rax+rax+00h]
0x1800391e6  xor     ebx, ebx
0x1800391e8  lea     rcx, [rbp+hKey]; this
0x1800391ec  call    ??1PpfSystemCcsKey@@QEAA@XZ; PpfSystemCcsKey::~PpfSystemCcsKey(void)
0x1800391f1  mov     eax, ebx
0x1800391f3  mov     rbx, [rsp+60h+arg_0]
0x1800391fb  add     rsp, 60h
0x1800391ff  pop     r14
0x180039201  pop     r12
0x180039203  pop     rdi
0x180039204  pop     rsi
0x180039205  pop     rbp
0x180039206  retn
```
