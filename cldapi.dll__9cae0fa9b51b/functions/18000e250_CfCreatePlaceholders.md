# CfCreatePlaceholders

- ea: `0x18000e250`
- end: `0x18000e51e`
- name: `CfCreatePlaceholders`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800046bc`
- `0x18000e250`
- `0x180010294`
- `0x180011594`
- `0x180012264`
- `0x180012c28`
- `0x18001cd74`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e356`
- `ntdll!RtlNtStatusToDosError` at `0x18000e356`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e2f3`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18000e2f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e4d8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e4d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e4ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e4ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e4c7`

## string_xrefs

- `0x18000e379`: `CreateFile on BaseDirectoryPath Failed`

## pseudocode

```c
__int64 __fastcall CfCreatePlaceholders(__int64 a1, __int64 a2, unsigned int a3, int a4, _DWORD *a5)
{
  int v7; // ebx
  void *v8; // r15
  const WCHAR *v9; // rdi
  const WCHAR *v10; // rsi
  __int64 v11; // rdx
  const wchar_t *v12; // r14
  NTSTATUS v13; // eax
  signed int v14; // eax
  int v15; // eax
  int v16; // eax
  HANDLE ProcessHeap; // rax
  __int64 v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h]
  int v21; // [rsp+50h] [rbp-B0h] BYREF
  void *v22; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+60h] [rbp-A0h]
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp-90h] BYREF
  __int64 v26; // [rsp+78h] [rbp-88h]
  unsigned __int64 UnbiasedTime; // [rsp+80h] [rbp-80h] BYREF
  __int64 v28; // [rsp+88h] [rbp-78h]
  int v29; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v30; // [rsp+98h] [rbp-68h]
  unsigned int v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  int v33; // [rsp+B0h] [rbp-50h]
  _DWORD v34[6]; // [rsp+F0h] [rbp-10h] BYREF
  void *v35; // [rsp+108h] [rbp+8h]
  char v36[4]; // [rsp+190h] [rbp+90h] BYREF
  char v37; // [rsp+194h] [rbp+94h] BYREF
  char v38; // [rsp+394h] [rbp+294h] BYREF

  v26 = a2;
  v28 = a1;
  v23 = a4;
  hObject = (HANDLE)-1LL;
  memset_0(v34, 0, 0x98u);
  v7 = 0;
  v22 = 0;
  v21 = 0;
  v8 = 0;
  NumberOfBytesTransferred = 0;
  memset_0(v36, 0, 0x404u);
  UnbiasedTime = 0;
  v9 = 0;
  v10 = 0;
  memset_0(&v29, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( a5 )
    *a5 = 0;
  if ( !a3 )
    v7 = -2147024809;
  if ( v7 > -1 )
  {
    v13 = CfpCreateFile(a1, v11, 0, 7u, v19, 0x21u, v20, &hObject);
    v14 = RtlNtStatusToDosError(v13);
    v12 = 0;
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    if ( v7 > -1 )
    {
      v10 = (const WCHAR *)&v38;
      v9 = (const WCHAR *)&v37;
      if ( (int)CfpGetSyncRootInfoByHandle(hObject, 0) < 0 )
      {
        v10 = 0;
        v9 = 0;
      }
      v15 = BuildSetPlaceholderInfo(v26, a3, &v22, &v21);
      v8 = v22;
      v7 = v15;
      if ( v15 > -1 )
      {
        v34[2] = v23;
        v34[4] = v21;
        v34[1] = -1073741823;
        v34[0] = -1879048166;
        v35 = v22;
        v7 = IssueHsmControl((unsigned __int64)hObject, v34, 0x98u, 0, 0, &NumberOfBytesTransferred, 0);
        if ( v7 > -1 )
        {
          LODWORD(v22) = 0;
          v16 = ProcessReturnedSetPlaceholderInfo((_DWORD)v8, v21, v26, a3, (__int64)&v22);
          v7 = (int)v22;
          if ( a5 )
            *a5 = v16;
        }
        else
        {
          v12 = L"IssueHsmControl Failed";
        }
      }
      else
      {
        v12 = L"BuildSetPlaceholderInfo Failed";
      }
    }
    else
    {
      v12 = L"CreateFile on BaseDirectoryPath Failed";
    }
  }
  else
  {
    v12 = L"Invalid PlaceholderCount";
  }
  v33 = v23;
  v31 = a3;
  v32 = v28;
  v30 = v12;
  TlmLogApiReliability(0xFu, (unsigned __int64)hObject, v28, v9, v10, UnbiasedTime, &v29, v7);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000e250  push    rbp
0x18000e252  push    rbx
0x18000e253  push    rsi
0x18000e254  push    rdi
0x18000e255  push    r12
0x18000e257  push    r13
0x18000e259  push    r14
0x18000e25b  push    r15
0x18000e25d  lea     rbp, [rsp-4B8h]
0x18000e265  sub     rsp, 5B8h
0x18000e26c  mov     rax, cs:__security_cookie
0x18000e273  xor     rax, rsp
0x18000e276  mov     [rbp+4F0h+var_50], rax
0x18000e27d  mov     r12, [rbp+4F0h+arg_20]
0x18000e284  mov     r13d, r8d
0x18000e287  mov     [rsp+5F0h+var_578], rdx
0x18000e28c  mov     r14, rcx
0x18000e28f  mov     [rbp+4F0h+var_568], rcx
0x18000e293  xor     edx, edx; Val
0x18000e295  mov     r8d, 98h; Size
0x18000e29b  mov     [rsp+5F0h+var_590], r9d
0x18000e2a0  lea     rcx, [rbp+4F0h+var_500]; void *
0x18000e2a4  mov     [rsp+5F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x18000e2ad  call    memset_0
0x18000e2b2  xor     ebx, ebx
0x18000e2b4  lea     rcx, [rbp+4F0h+var_460]; void *
0x18000e2bb  xor     edx, edx; Val
0x18000e2bd  mov     [rsp+5F0h+var_598], rbx
0x18000e2c2  mov     r8d, 404h; Size
0x18000e2c8  mov     [rsp+5F0h+var_5A0], ebx
0x18000e2cc  mov     r15d, ebx
0x18000e2cf  mov     [rsp+5F0h+NumberOfBytesTransferred], ebx
0x18000e2d3  call    memset_0
0x18000e2d8  xor     edx, edx; Val
0x18000e2da  mov     [rbp+4F0h+UnbiasedTime], rbx
0x18000e2de  lea     r8d, [rbx+58h]; Size
0x18000e2e2  mov     edi, ebx
0x18000e2e4  lea     rcx, [rbp+4F0h+var_560]; void *
0x18000e2e8  mov     esi, ebx
0x18000e2ea  call    memset_0
0x18000e2ef  lea     rcx, [rbp+4F0h+UnbiasedTime]; UnbiasedTime
0x18000e2f3  call    cs:__imp_QueryUnbiasedInterruptTime
0x18000e2fa  nop     dword ptr [rax+rax+00h]
0x18000e2ff  test    r12, r12
0x18000e302  jz      short loc_18000E308
0x18000e304  mov     [r12], ebx
0x18000e308  test    r13d, r13d
0x18000e30b  mov     eax, 57h ; 'W'
0x18000e310  cmovz   ebx, eax
0x18000e313  mov     eax, ebx
0x18000e315  or      eax, 80070000h
0x18000e31a  test    r13d, r13d
0x18000e31d  cmovz   ebx, eax
0x18000e320  cmp     ebx, 0FFFFFFFFh
0x18000e323  jg      short loc_18000E331
0x18000e325  lea     r14, aInvalidPlaceho
0x18000e32c  jmp     loc_18000E478
0x18000e331  lea     rax, [rsp+5F0h+hObject]
0x18000e336  mov     r9d, 7
0x18000e33c  mov     [rsp+5F0h+var_5B8], rax
0x18000e341  xor     r8d, r8d
0x18000e344  mov     rcx, r14
0x18000e347  mov     dword ptr [rsp+5F0h+lpNumberOfBytesTransferred], 21h ; '!'
0x18000e34f  call    CfpCreateFile
0x18000e354  mov     ecx, eax; Status
0x18000e356  call    cs:__imp_RtlNtStatusToDosError
0x18000e35d  nop     dword ptr [rax+rax+00h]
0x18000e362  xor     r14d, r14d
0x18000e365  mov     ebx, eax
0x18000e367  test    eax, eax
0x18000e369  jle     short loc_18000E374
0x18000e36b  movzx   ebx, ax
0x18000e36e  or      ebx, 80070000h
0x18000e374  cmp     ebx, 0FFFFFFFFh
0x18000e377  jg      short loc_18000E385
0x18000e379  lea     r14, aCreatefileOnBa
0x18000e380  jmp     loc_18000E478
0x18000e385  mov     rcx, [rsp+5F0h+hObject]; hFile
0x18000e38a  lea     r8, [rbp+4F0h+var_460]
0x18000e391  mov     r9d, 404h
0x18000e397  mov     qword ptr [rsp+5F0h+var_5D0], r14; __int64
0x18000e39c  mov     edx, 2
0x18000e3a1  call    CfpGetSyncRootInfoByHandle
0x18000e3a6  mov     rcx, [rsp+5F0h+var_578]
0x18000e3ab  lea     rsi, [rbp+4F0h+var_25C]
0x18000e3b2  test    eax, eax
0x18000e3b4  lea     rdi, [rbp+4F0h+var_45C]
0x18000e3bb  lea     r9, [rsp+5F0h+var_5A0]
0x18000e3c0  mov     edx, r13d
0x18000e3c3  lea     r8, [rsp+5F0h+var_598]
0x18000e3c8  cmovs   rsi, r14
0x18000e3cc  cmovs   rdi, r14
0x18000e3d0  call    BuildSetPlaceholderInfo
0x18000e3d5  mov     r15, [rsp+5F0h+var_598]
0x18000e3da  mov     ebx, eax
0x18000e3dc  cmp     eax, 0FFFFFFFFh
0x18000e3df  jg      short loc_18000E3ED
0x18000e3e1  lea     r14, aBuildsetplaceh
0x18000e3e8  jmp     loc_18000E478
0x18000e3ed  mov     eax, [rsp+5F0h+var_590]
0x18000e3f1  lea     rdx, [rbp+4F0h+var_500]
0x18000e3f5  mov     rcx, [rsp+5F0h+hObject]; hFile
0x18000e3fa  xor     r9d, r9d
0x18000e3fd  mov     [rbp+4F0h+var_4F8], eax
0x18000e400  mov     r8d, 98h
0x18000e406  mov     eax, [rsp+5F0h+var_5A0]
0x18000e40a  mov     [rbp+4F0h+var_4F0], eax
0x18000e40d  lea     rax, [rsp+5F0h+NumberOfBytesTransferred]
0x18000e412  mov     [rsp+5F0h+var_5C0], r14; __int64
0x18000e417  mov     [rsp+5F0h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x18000e41c  mov     [rsp+5F0h+var_5D0], r14d; DWORD
0x18000e421  mov     [rbp+4F0h+var_4FC], 0C0000001h
0x18000e428  mov     [rbp+4F0h+var_500], 9000001Ah
0x18000e42f  mov     [rbp+4F0h+var_4E8], r15
0x18000e433  call    IssueHsmControl
0x18000e438  mov     ebx, eax
0x18000e43a  cmp     eax, 0FFFFFFFFh
0x18000e43d  jg      short loc_18000E448
0x18000e43f  lea     r14, aIssuehsmcontro
0x18000e446  jmp     short loc_18000E478
0x18000e448  mov     r8, [rsp+5F0h+var_578]
0x18000e44d  lea     rax, [rsp+5F0h+var_598]
0x18000e452  mov     edx, [rsp+5F0h+var_5A0]
0x18000e456  mov     r9d, r13d
0x18000e459  mov     rcx, r15
0x18000e45c  mov     qword ptr [rsp+5F0h+var_5D0], rax
0x18000e461  mov     dword ptr [rsp+5F0h+var_598], r14d
0x18000e466  call    ProcessReturnedSetPlaceholderInfo
0x18000e46b  mov     ebx, dword ptr [rsp+5F0h+var_598]
0x18000e46f  test    r12, r12
0x18000e472  jz      short loc_18000E478
0x18000e474  mov     [r12], eax
0x18000e478  mov     eax, [rsp+5F0h+var_590]
0x18000e47c  mov     ecx, 0Fh
0x18000e481  mov     r8, [rbp+4F0h+var_568]
0x18000e485  mov     r9, rdi
0x18000e488  mov     rdx, [rsp+5F0h+hObject]
0x18000e48d  mov     [rbp+4F0h+var_540], eax
0x18000e490  lea     rax, [rbp+4F0h+var_560]
0x18000e494  mov     dword ptr [rsp+5F0h+var_5B8], ebx
0x18000e498  mov     [rsp+5F0h+var_5C0], rax
0x18000e49d  mov     rax, [rbp+4F0h+UnbiasedTime]
0x18000e4a1  mov     [rsp+5F0h+lpNumberOfBytesTransferred], rax
0x18000e4a6  mov     qword ptr [rsp+5F0h+var_5D0], rsi
0x18000e4ab  mov     [rbp+4F0h+var_550], r13d
0x18000e4af  mov     [rbp+4F0h+var_548], r8
0x18000e4b3  mov     [rbp+4F0h+var_558], r14
0x18000e4b7  call    TlmLogApiReliability
0x18000e4bc  mov     rcx, [rsp+5F0h+hObject]; hObject
0x18000e4c1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000e4c5  jz      short loc_18000E4D3
0x18000e4c7  call    cs:__imp_CloseHandle
0x18000e4ce  nop     dword ptr [rax+rax+00h]
0x18000e4d3  test    r15, r15
0x18000e4d6  jz      short loc_18000E4F8
0x18000e4d8  call    cs:__imp_GetProcessHeap
0x18000e4df  nop     dword ptr [rax+rax+00h]
0x18000e4e4  mov     r8, r15; lpMem
0x18000e4e7  xor     edx, edx; dwFlags
0x18000e4e9  mov     rcx, rax; hHeap
0x18000e4ec  call    cs:__imp_HeapFree
0x18000e4f3  nop     dword ptr [rax+rax+00h]
0x18000e4f8  mov     eax, ebx
0x18000e4fa  mov     rcx, [rbp+4F0h+var_50]
0x18000e501  xor     rcx, rsp; StackCookie
0x18000e504  call    __security_check_cookie
0x18000e509  add     rsp, 5B8h
0x18000e510  pop     r15
0x18000e512  pop     r14
0x18000e514  pop     r13
0x18000e516  pop     r12
0x18000e518  pop     rdi
0x18000e519  pop     rsi
0x18000e51a  pop     rbx
0x18000e51b  pop     rbp
0x18000e51c  retn
```
