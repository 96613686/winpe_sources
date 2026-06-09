# CDefragOperation::_ReadBootOptimizationFile(unsigned __int64,unsigned __int64,IVolume *,ushort *)

- ea: `0x180021430`
- end: `0x18002181f`
- name: `?_ReadBootOptimizationFile@CDefragOperation@@IEAAJ_K0PEAUIVolume@@PEAG@Z`
- size: `1007`
- prototype: `__int64 __fastcall(CDefragOperation *this, __int64, __int64, struct IVolume *, LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180053410`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180021430`
- `0x180044448`
- `0x180067b0a`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002157d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002157d`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800215fc`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800215fc`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002159b`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18002159b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021793`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800215c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800215c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021715`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021715`

## string_xrefs

- `0x180021480`: `CDefragOperation::_ReadBootOptimizationFile`

## pseudocode

```c
__int64 __fastcall CDefragOperation::_ReadBootOptimizationFile(
        CDefragOperation *this,
        __int64 a2,
        __int64 a3,
        struct IVolume *a4,
        LPCWSTR lpFileName)
{
  __int64 v8; // rbx
  struct IVolume *v9; // rdi
  __int16 v10; // ax
  HANDLE FileW; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DWORD nFileSizeLow; // esi
  void *v17; // rax
  __int64 v18; // rsi
  unsigned int v19; // r15d
  DWORD v20; // r12d
  __int64 i; // r13
  __int16 v22; // cx
  unsigned int v23; // esi
  __int16 v25; // ax
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-B4h]
  __int16 v29; // [rsp+4Eh] [rbp-B2h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  CDefragOperation *v31; // [rsp+88h] [rbp-78h]
  struct IVolume *v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v35[264]; // [rsp+E0h] [rbp-20h] BYREF

  v31 = this;
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragOperation::_ReadBootOptimizationFile",
    1146,
    1);
  v8 = -1;
  v33 = -1;
  v9 = 0;
  v32 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  pv = 0;
  NumberOfBytesRead = 0;
  if ( !lpFileName )
  {
    LastFailureAsHRESULT = -2147024809;
    v10 = 1160;
    goto LABEL_37;
  }
  LastFailureAsHRESULT = 0;
  v28 = 1160;
  if ( a4 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)a4 + 8LL))(a4);
  v9 = a4;
  v32 = a4;
  memset_0(v35, 0, 0x208u);
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IVolume *))(*(_QWORD *)a4 + 176LL))(a4);
  v10 = 1168;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_37;
  v28 = 1168;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IVolume *, __int64, __int64))(*(_QWORD *)a4 + 184LL))(
                           a4,
                           a2,
                           a3);
  v10 = 1171;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_37;
  v28 = 1171;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  v8 = (__int64)FileW;
  v33 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v25 = 1186;
LABEL_40:
    LastFailureAsHRESULT = 1;
    v28 = v25;
    goto LABEL_30;
  }
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v13, v12, v14, v15);
    v10 = 1190;
    goto LABEL_37;
  }
  LastFailureAsHRESULT = 0;
  v28 = 1190;
  nFileSizeLow = FileInformation.nFileSizeLow;
  v17 = CoTaskMemAlloc(FileInformation.nFileSizeLow);
  pv = v17;
  if ( !v17 )
  {
    LastFailureAsHRESULT = -2147024882;
    v29 = 1195;
    goto LABEL_30;
  }
  LastFailureAsHRESULT = 0;
  v28 = 1195;
  if ( !ReadFile((HANDLE)v8, v17, nFileSizeLow, &NumberOfBytesRead, 0) )
  {
    v25 = 1201;
    goto LABEL_40;
  }
  if ( NumberOfBytesRead < nFileSizeLow )
  {
    v25 = 1208;
    goto LABEL_40;
  }
  v18 = 0;
  v19 = 0;
  v20 = NumberOfBytesRead >> 1;
  for ( i = 0; (unsigned int)i < v20; i = (unsigned int)(i + 1) )
  {
    v22 = *((_WORD *)pv + i);
    if ( v22 == 10 )
    {
      ++v19;
      if ( (unsigned int)v18 < 0x104 && v19 > 2 )
      {
        if ( (unsigned __int64)(2 * v18) >= 0x208 )
          goto LABEL_27;
        v35[v18] = 0;
        LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IVolume *, _WORD *))(*(_QWORD *)a4 + 168LL))(a4, v35);
        v10 = 1241;
        if ( LastFailureAsHRESULT < 0 )
          goto LABEL_37;
        v28 = 1241;
      }
      goto LABEL_25;
    }
    if ( v22 == 13 )
      continue;
    if ( (unsigned int)v18 >= 0x104 )
    {
      ++v19;
LABEL_25:
      LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CDefragOperation *))(*(_QWORD *)v31 + 32LL))(v31);
      v10 = 1247;
      if ( LastFailureAsHRESULT < 0 )
        goto LABEL_37;
      v18 = 0;
      goto LABEL_18;
    }
    v35[v18] = v22;
    LastFailureAsHRESULT = (*(__int64 (__fastcall **)(CDefragOperation *))(*(_QWORD *)v31 + 32LL))(v31);
    v10 = 1226;
    if ( LastFailureAsHRESULT < 0 )
      goto LABEL_37;
    v18 = (unsigned int)(v18 + 1);
LABEL_18:
    v28 = v10;
  }
  if ( (unsigned int)(v18 - 1) > 0x102 )
    goto LABEL_29;
  if ( (unsigned __int64)(2 * v18) >= 0x208 )
LABEL_27:
    _report_rangecheckfailure();
  v35[v18] = 0;
  LastFailureAsHRESULT = (*(__int64 (__fastcall **)(struct IVolume *, _WORD *))(*(_QWORD *)a4 + 168LL))(a4, v35);
  v10 = 1257;
  if ( LastFailureAsHRESULT < 0 )
  {
LABEL_37:
    v29 = v10;
    goto LABEL_30;
  }
  v28 = 1257;
LABEL_29:
  LastFailureAsHRESULT = 0;
LABEL_30:
  CoTaskMemFree(pv);
  v23 = LastFailureAsHRESULT;
  if ( v9 )
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v8);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v23;
}

```

## disassembly

```asm
0x180021430  push    rbp
0x180021432  push    rbx
0x180021433  push    rsi
0x180021434  push    rdi
0x180021435  push    r12
0x180021437  push    r13
0x180021439  push    r14
0x18002143b  push    r15
0x18002143d  lea     rbp, [rsp-208h]
0x180021445  sub     rsp, 308h
0x18002144c  mov     rax, cs:__security_cookie
0x180021453  xor     rax, rsp
0x180021456  mov     [rbp+240h+var_50], rax
0x18002145d  mov     r14, r9
0x180021460  mov     r12, r8
0x180021463  mov     r15, rdx
0x180021466  mov     [rbp+240h+var_2B8], rcx
0x18002146a  mov     rsi, [rbp+240h+lpFileName]
0x180021471  mov     r13d, 1
0x180021477  mov     r9d, r13d; unsigned __int16
0x18002147a  mov     r8d, 47Ah; unsigned __int16
0x180021480  lea     rdx, aCdefragoperati_24; "CDefragOperation::_ReadBootOptimization"...
0x180021487  lea     rcx, [rsp+340h+var_2F8]; this
0x18002148c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180021491  nop
0x180021492  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180021496  mov     [rbp+240h+var_2A8], rbx
0x18002149a  xor     edi, edi
0x18002149c  mov     [rbp+240h+var_2B0], rdi
0x1800214a0  xorps   xmm0, xmm0
0x1800214a3  xor     eax, eax
0x1800214a5  movups  xmmword ptr [rbp+240h+FileInformation.dwFileAttributes], xmm0
0x1800214a9  movups  xmmword ptr [rbp+240h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800214ad  movups  xmmword ptr [rbp+240h+FileInformation.nFileSizeHigh], xmm0
0x1800214b1  mov     [rbp+240h+FileInformation.nFileIndexLow], eax
0x1800214b4  mov     [rbp+240h+pv], rax
0x1800214b8  mov     [rsp+340h+NumberOfBytesRead], eax
0x1800214bc  test    rsi, rsi
0x1800214bf  jz      loc_18002177C
0x1800214c5  mov     [rsp+340h+var_2F8], eax
0x1800214c9  mov     eax, 488h
0x1800214ce  mov     [rsp+340h+var_2F4], ax
0x1800214d3  test    r14, r14
0x1800214d6  jz      short loc_1800214E8
0x1800214d8  mov     rax, [r14]
0x1800214db  mov     rcx, r14
0x1800214de  mov     rax, [rax+8]
0x1800214e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214e7  nop
0x1800214e8  mov     rdi, r14
0x1800214eb  mov     [rbp+240h+var_2B0], r14
0x1800214ef  xor     edx, edx; Val
0x1800214f1  mov     r8d, 208h; Size
0x1800214f7  lea     rcx, [rbp+240h+var_260]; void *
0x1800214fb  call    memset_0
0x180021500  mov     rax, [r14]
0x180021503  mov     rcx, r14
0x180021506  mov     rax, [rax+0B0h]
0x18002150d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021512  mov     [rsp+340h+var_2F8], eax
0x180021516  test    eax, eax
0x180021518  mov     eax, 490h
0x18002151d  js      loc_180021789
0x180021523  mov     [rsp+340h+var_2F4], ax
0x180021528  mov     rax, [r14]
0x18002152b  mov     r8, r12
0x18002152e  mov     rdx, r15
0x180021531  mov     rcx, r14
0x180021534  mov     rax, [rax+0B8h]
0x18002153b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021540  mov     [rsp+340h+var_2F8], eax
0x180021544  test    eax, eax
0x180021546  mov     eax, 493h
0x18002154b  js      loc_180021789
0x180021551  mov     [rsp+340h+var_2F4], ax
0x180021556  mov     [rsp+340h+hTemplateFile], 0; hTemplateFile
0x18002155f  mov     [rsp+340h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180021567  mov     [rsp+340h+dwCreationDisposition], 3; dwCreationDisposition
0x18002156f  xor     r9d, r9d; lpSecurityAttributes
0x180021572  mov     r8d, r13d; dwShareMode
0x180021575  mov     edx, 80000000h; dwDesiredAccess
0x18002157a  mov     rcx, rsi; lpFileName
0x18002157d  call    cs:__imp_CreateFileW
0x180021583  mov     rbx, rax
0x180021586  mov     [rbp+240h+var_2A8], rax
0x18002158a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002158e  jz      loc_18002179B
0x180021594  lea     rdx, [rbp+240h+FileInformation]; lpFileInformation
0x180021598  mov     rcx, rax; hFile
0x18002159b  call    cs:__imp_GetFileInformationByHandle
0x1800215a1  test    eax, eax
0x1800215a3  jz      loc_1800217B6
0x1800215a9  mov     [rsp+340h+var_2F8], 0
0x1800215b1  mov     eax, 4A6h
0x1800215b6  mov     [rsp+340h+var_2F4], ax
0x1800215bb  mov     esi, [rbp+240h+FileInformation.nFileSizeLow]
0x1800215be  mov     ecx, esi; cb
0x1800215c0  call    cs:__imp_CoTaskMemAlloc
0x1800215c6  mov     [rbp+240h+pv], rax
0x1800215ca  mov     ecx, 4ABh
0x1800215cf  test    rax, rax
0x1800215d2  jz      loc_18002176D
0x1800215d8  mov     [rsp+340h+var_2F8], 0
0x1800215e0  mov     [rsp+340h+var_2F4], cx
0x1800215e5  mov     qword ptr [rsp+340h+dwCreationDisposition], 0; lpOverlapped
0x1800215ee  lea     r9, [rsp+340h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800215f3  mov     r8d, esi; nNumberOfBytesToRead
0x1800215f6  mov     rdx, rax; lpBuffer
0x1800215f9  mov     rcx, rbx; hFile
0x1800215fc  call    cs:__imp_ReadFile
0x180021602  test    eax, eax
0x180021604  jz      loc_1800217C6
0x18002160a  mov     r12d, [rsp+340h+NumberOfBytesRead]
0x18002160f  cmp     r12d, esi
0x180021612  jb      loc_1800217A2
0x180021618  xor     esi, esi
0x18002161a  xor     r15d, r15d
0x18002161d  shr     r12d, 1
0x180021620  xor     r13d, r13d
0x180021623  cmp     r13d, r12d
0x180021626  jnb     loc_1800216FB
0x18002162c  mov     rcx, [rbp+240h+pv]
0x180021630  movzx   ecx, word ptr [rcx+r13*2]
0x180021635  cmp     cx, 0Ah
0x180021639  jz      short loc_18002167F
0x18002163b  cmp     cx, 0Dh
0x18002163f  jz      short loc_18002167A
0x180021641  cmp     esi, 104h
0x180021647  jnb     loc_1800217CD
0x18002164d  mov     [rbp+rsi*2+240h+var_260], cx
0x180021652  mov     rcx, [rbp+240h+var_2B8]
0x180021656  mov     rax, [rcx]
0x180021659  mov     rax, [rax+20h]
0x18002165d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021662  mov     [rsp+340h+var_2F8], eax
0x180021666  test    eax, eax
0x180021668  mov     eax, 4CAh
0x18002166d  js      loc_180021789
0x180021673  inc     esi
0x180021675  mov     [rsp+340h+var_2F4], ax
0x18002167a  inc     r13d
0x18002167d  jmp     short loc_180021623
0x18002167f  inc     r15d
0x180021682  cmp     esi, 104h
0x180021688  jnb     short loc_1800216D0
0x18002168a  cmp     r15d, 2
0x18002168e  jbe     short loc_1800216D0
0x180021690  lea     rcx, [rsi+rsi]
0x180021694  cmp     rcx, 208h
0x18002169b  jnb     short loc_1800216F5
0x18002169d  xor     eax, eax
0x18002169f  mov     [rbp+rcx+240h+var_260], ax
0x1800216a4  mov     rax, [r14]
0x1800216a7  lea     rdx, [rbp+240h+var_260]
0x1800216ab  mov     rcx, r14
0x1800216ae  mov     rax, [rax+0A8h]
0x1800216b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ba  mov     [rsp+340h+var_2F8], eax
0x1800216be  test    eax, eax
0x1800216c0  mov     eax, 4D9h
0x1800216c5  js      loc_180021789
0x1800216cb  mov     [rsp+340h+var_2F4], ax
0x1800216d0  mov     rcx, [rbp+240h+var_2B8]
0x1800216d4  mov     rax, [rcx]
0x1800216d7  mov     rax, [rax+20h]
0x1800216db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216e0  mov     [rsp+340h+var_2F8], eax
0x1800216e4  test    eax, eax
0x1800216e6  mov     eax, 4DFh
0x1800216eb  js      loc_180021789
0x1800216f1  xor     esi, esi
0x1800216f3  jmp     short loc_180021675
0x1800216f5  call    __report_rangecheckfailure
0x1800216fb  lea     eax, [rsi-1]
0x1800216fe  cmp     eax, 102h
0x180021703  jbe     loc_1800217D5
0x180021709  mov     [rsp+340h+var_2F8], 0
0x180021711  mov     rcx, [rbp+240h+pv]; pv
0x180021715  call    cs:__imp_CoTaskMemFree
0x18002171b  mov     esi, [rsp+340h+var_2F8]
0x18002171f  test    rdi, rdi
0x180021722  jz      short loc_180021734
0x180021724  mov     rax, [rdi]
0x180021727  mov     rcx, rdi
0x18002172a  mov     rax, [rax+10h]
0x18002172e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021733  nop
0x180021734  lea     rcx, [rbx-1]
0x180021738  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002173c  jbe     short loc_180021790
0x18002173e  lea     rcx, [rsp+340h+var_2F8]; this
0x180021743  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180021748  mov     eax, esi
0x18002174a  mov     rcx, [rbp+240h+var_50]
0x180021751  xor     rcx, rsp; StackCookie
0x180021754  call    __security_check_cookie
0x180021759  add     rsp, 308h
0x180021760  pop     r15
0x180021762  pop     r14
0x180021764  pop     r13
0x180021766  pop     r12
0x180021768  pop     rdi
0x180021769  pop     rsi
0x18002176a  pop     rbx
0x18002176b  pop     rbp
0x18002176c  retn
0x18002176d  mov     [rsp+340h+var_2F8], 8007000Eh
0x180021775  mov     [rsp+340h+var_2F2], cx
0x18002177a  jmp     short loc_180021711
0x18002177c  mov     [rsp+340h+var_2F8], 80070057h
0x180021784  mov     eax, 488h
0x180021789  mov     [rsp+340h+var_2F2], ax
0x18002178e  jmp     short loc_180021711
0x180021790  mov     rcx, rbx; hObject
0x180021793  call    cs:__imp_CloseHandle
0x180021799  jmp     short loc_18002173E
0x18002179b  mov     eax, 4A2h
0x1800217a0  jmp     short loc_1800217A7
0x1800217a2  mov     eax, 4B8h
0x1800217a7  mov     [rsp+340h+var_2F8], r13d
0x1800217ac  mov     [rsp+340h+var_2F4], ax
0x1800217b1  jmp     loc_180021711
0x1800217b6  call    GetLastFailureAsHRESULT
0x1800217bb  mov     [rsp+340h+var_2F8], eax
0x1800217bf  mov     eax, 4A6h
0x1800217c4  jmp     short loc_180021789
0x1800217c6  mov     eax, 4B1h
0x1800217cb  jmp     short loc_1800217A7
0x1800217cd  inc     r15d
0x1800217d0  jmp     loc_1800216D0
0x1800217d5  lea     rcx, [rsi+rsi]
0x1800217d9  cmp     rcx, 208h
0x1800217e0  jnb     loc_1800216F5
0x1800217e6  xor     eax, eax
0x1800217e8  mov     [rbp+rcx+240h+var_260], ax
0x1800217ed  mov     rax, [r14]
0x1800217f0  lea     rdx, [rbp+240h+var_260]
0x1800217f4  mov     rcx, r14
0x1800217f7  mov     rax, [rax+0A8h]
0x1800217fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021803  mov     [rsp+340h+var_2F8], eax
0x180021807  test    eax, eax
0x180021809  mov     eax, 4E9h
0x18002180e  js      loc_180021789
0x180021814  mov     [rsp+340h+var_2F4], ax
0x180021819  jmp     loc_180021709
```
