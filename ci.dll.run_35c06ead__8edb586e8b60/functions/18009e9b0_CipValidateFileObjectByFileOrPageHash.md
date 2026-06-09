# CipValidateFileObjectByFileOrPageHash

- ea: `0x18009e9b0`
- end: `0x18009ed4e`
- name: `CipValidateFileObjectByFileOrPageHash`
- size: `926`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800644b0`
- `0x18008d750`
- `0x1800e3cc0`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18005afec`
- `0x18009df48`
- `0x18009e170`
- `0x18009e8d4`
- `0x18009e9b0`
- `0x1800a0780`
- `0x1800a0af0`
- `0x1800a4538`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x18009ea92`
- `ntoskrnl!FsRtlGetFileSize` at `0x18009ea92`
- `ntoskrnl!KeStackAttachProcess` at `0x18009eb74`
- `ntoskrnl!KeStackAttachProcess` at `0x18009eb74`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009ead7`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009ead7`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009ed02`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009ed02`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18009eb55`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18009eb55`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18009ed11`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18009ed11`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009eb46`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009eb46`

## pseudocode

```c
__int64 __fastcall CipValidateFileObjectByFileOrPageHash(
        struct _FILE_OBJECT *Object,
        unsigned int a2,
        char a3,
        char a4,
        __int64 a5,
        _OWORD *a6,
        __int64 a7,
        _BYTE *a8,
        void *a9,
        _DWORD *a10,
        _DWORD *a11,
        bool *a12,
        bool *a13,
        _QWORD *a14)
{
  DWORD LowPart; // ebx
  int FileOpenWithFlags; // r14d
  unsigned __int8 IsCimFile; // al
  __int16 v19; // si
  __int64 CurrentProcess; // rax
  int v21; // eax
  unsigned int *v22; // rdi
  __int64 CurrentServerSilo; // rax
  PVOID v24; // rsi
  __int64 v25; // r9
  __int64 v26; // rsi
  int v27; // edx
  int v28; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+28h] [rbp-D8h]
  unsigned __int8 v34; // [rsp+42h] [rbp-BEh]
  PVOID Entry; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-A0h]
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  bool *v40; // [rsp+70h] [rbp-90h]
  bool *v41; // [rsp+78h] [rbp-88h]
  _BYTE *v42; // [rsp+80h] [rbp-80h]
  _DWORD *v43; // [rsp+88h] [rbp-78h]
  void *v44; // [rsp+90h] [rbp-70h]
  _QWORD *v45; // [rsp+98h] [rbp-68h]
  void *v46[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v47; // [rsp+B0h] [rbp-50h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  struct _KAPC_STATE ApcState; // [rsp+D0h] [rbp-30h] BYREF

  LowPart = 0;
  v42 = a8;
  v43 = a11;
  v41 = a12;
  v44 = a9;
  v40 = a13;
  v38 = a2;
  v45 = a14;
  Entry = 0;
  v37 = 0;
  FileSize.QuadPart = 0;
  v39 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v48 = 0;
  if ( a10 && *a10 < 0x40u )
  {
    *a10 = 64;
    return (unsigned int)-1073741789;
  }
  else
  {
    FileOpenWithFlags = FsRtlGetFileSize(Object, &FileSize);
    if ( FileOpenWithFlags >= 0 )
    {
      IsCimFile = CipIsCimFile(Object);
      v19 = IsCimFile;
      v34 = IsCimFile;
      if ( IsCimFile || (LowPart = FileSize.LowPart, FileSize.QuadPart <= 0xFFFFFFFFuLL) )
      {
        CurrentProcess = PsGetCurrentProcess();
        v21 = CipAllocateLocalValidationContext(a2, 0, CurrentProcess, Object, &Entry);
        v22 = (unsigned int *)Entry;
        FileOpenWithFlags = v21;
        if ( v21 >= 0 )
        {
          *((_QWORD *)Entry + 85) = a7;
          *((_QWORD *)v22 + 414) = a5;
          v22[764] = (v22[764] | 0x80) ^ ((*((_WORD *)v22 + 1528) | 0x80) ^ (unsigned __int16)(v19 << 14)) & 0x4000;
          CurrentServerSilo = PsGetCurrentServerSilo();
          v24 = (PVOID)PsAttachSiloToCurrentThread(CurrentServerSilo);
          Entry = v24;
          KeStackAttachProcess(g_CiSystemProcess, &ApcState);
          FileOpenWithFlags = CiReadFileOpenWithFlags(Object, 0, FileSize.QuadPart, 7, v46, (__int64)&v37);
          if ( FileOpenWithFlags >= 0 )
          {
            LOBYTE(v31) = a3;
            FileOpenWithFlags = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _BYTE, _QWORD))CipValidateDataMappedFileWithContext)(
                                  v22,
                                  v37,
                                  (union _LARGE_INTEGER)FileSize.QuadPart,
                                  Object,
                                  v38,
                                  v31,
                                  a4,
                                  &v39);
            if ( FileOpenWithFlags >= 0 )
            {
              v26 = v39;
              if ( v40 )
              {
                if ( v34
                  || (v27 = *((_DWORD *)g_CipWhichLevelComparisons + 12), !_bittest(&v27, *(_BYTE *)(v39 + 52) & 0xF)) )
                {
                  *v40 = 0;
                }
                else
                {
                  LOBYTE(v25) = 1;
                  LOBYTE(v30) = 0;
                  v28 = CipMitigatePPLBypassThroughInterpreters(Object, v37, LowPart, v25, v30);
                  *v40 = v28 >= 0;
                }
              }
              if ( v41 )
                *v41 = (*(_DWORD *)(v26 + 64) & 4) != 0;
              if ( a6 )
              {
                *a6 = *(_OWORD *)v26;
                a6[1] = *(_OWORD *)(v26 + 16);
                a6[2] = *(_OWORD *)(v26 + 32);
                *(_OWORD *)v26 = 0;
                *(_OWORD *)(v26 + 16) = 0;
                *(_OWORD *)(v26 + 32) = 0;
              }
              if ( v42 )
                *v42 = *(_BYTE *)(v26 + 52);
              if ( v43 )
                *v43 = v22[754];
              if ( a10 )
              {
                *a10 = v22[755];
                if ( v44 )
                  memmove(v44, *((const void **)v22 + 378), v22[755]);
              }
              v24 = Entry;
              if ( v45 )
              {
                *v45 = v22;
                v22 = 0;
              }
            }
          }
          if ( v37 )
            CiReadFileClose(v46);
          KeUnstackDetachProcess(&ApcState);
          PsDetachSiloFromCurrentThread(v24);
        }
        if ( v22 )
          CiFreeValidationContext(v22);
      }
      else
      {
        return (unsigned int)-1073741701;
      }
    }
  }
  return (unsigned int)FileOpenWithFlags;
}

```

## disassembly

```asm
0x18009e9b0  push    rbp
0x18009e9b2  push    rbx
0x18009e9b3  push    rsi
0x18009e9b4  push    rdi
0x18009e9b5  push    r12
0x18009e9b7  push    r13
0x18009e9b9  push    r14
0x18009e9bb  push    r15
0x18009e9bd  lea     rbp, [rsp-18h]
0x18009e9c2  sub     rsp, 118h
0x18009e9c9  mov     rax, cs:__security_cookie
0x18009e9d0  xor     rax, rsp
0x18009e9d3  mov     [rbp+50h+var_50], rax
0x18009e9d7  mov     rax, [rbp+50h+arg_38]
0x18009e9de  xorps   xmm0, xmm0
0x18009e9e1  mov     r15, [rbp+50h+arg_48]
0x18009e9e8  xor     ebx, ebx
0x18009e9ea  mov     r13, [rbp+50h+arg_28]
0x18009e9f1  mov     r12, rcx
0x18009e9f4  mov     rcx, [rbp+50h+arg_40]
0x18009e9fb  mov     edi, edx
0x18009e9fd  mov     [rbp+50h+var_D0], rax
0x18009ea01  mov     rax, [rbp+50h+arg_50]
0x18009ea08  mov     [rbp+50h+var_C8], rax
0x18009ea0c  mov     rax, [rbp+50h+arg_58]
0x18009ea13  mov     [rsp+150h+var_D8], rax
0x18009ea18  mov     rax, [rbp+50h+arg_60]
0x18009ea1f  mov     [rbp+50h+var_C0], rcx
0x18009ea23  mov     rcx, [rbp+50h+arg_68]
0x18009ea2a  mov     [rsp+150h+var_E0], rax
0x18009ea2f  mov     [rsp+150h+var_110], r9b
0x18009ea34  mov     [rsp+150h+var_10F], r8b
0x18009ea39  mov     [rsp+150h+var_F0], edx
0x18009ea3d  mov     [rbp+50h+var_B8], rcx
0x18009ea41  mov     [rsp+150h+Entry], rbx
0x18009ea46  mov     [rsp+150h+var_F8], rbx
0x18009ea4b  mov     qword ptr [rsp+150h+FileSize], rbx
0x18009ea50  mov     [rsp+150h+var_E8], rbx
0x18009ea55  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink], xmm0
0x18009ea59  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink+10h], xmm0
0x18009ea5d  movups  xmmword ptr [rbp+50h+ApcState.Process], xmm0
0x18009ea61  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x18009ea65  movups  [rbp+50h+var_A0], xmm0
0x18009ea69  movups  [rbp+50h+var_90], xmm0
0x18009ea6d  test    r15, r15
0x18009ea70  jz      short loc_18009EA8A
0x18009ea72  cmp     dword ptr [r15], 40h ; '@'
0x18009ea76  jnb     short loc_18009EA8A
0x18009ea78  mov     dword ptr [r15], 40h ; '@'
0x18009ea7f  mov     r14d, 0C0000023h
0x18009ea85  jmp     loc_18009ED2A
0x18009ea8a  lea     rdx, [rsp+150h+FileSize]; FileSize
0x18009ea8f  mov     rcx, r12; FileObject
0x18009ea92  call    cs:__imp_FsRtlGetFileSize
0x18009ea99  nop     dword ptr [rax+rax+00h]
0x18009ea9e  mov     r14d, eax
0x18009eaa1  test    eax, eax
0x18009eaa3  js      loc_18009ED2A
0x18009eaa9  mov     rcx, r12
0x18009eaac  call    CipIsCimFile
0x18009eab1  movzx   esi, al
0x18009eab4  mov     [rsp+150h+var_10E], sil
0x18009eab9  test    al, al
0x18009eabb  jnz     short loc_18009EAD7
0x18009eabd  mov     rbx, qword ptr [rsp+150h+FileSize]
0x18009eac2  mov     eax, 0FFFFFFFFh
0x18009eac7  cmp     rbx, rax
0x18009eaca  jbe     short loc_18009EAD7
0x18009eacc  mov     r14d, 0C000007Bh
0x18009ead2  jmp     loc_18009ED2A
0x18009ead7  call    cs:__imp_PsGetCurrentProcess
0x18009eade  nop     dword ptr [rax+rax+00h]
0x18009eae3  mov     r9, r12
0x18009eae6  xor     edx, edx
0x18009eae8  mov     r8, rax
0x18009eaeb  mov     ecx, edi
0x18009eaed  lea     rax, [rsp+150h+Entry]
0x18009eaf2  mov     [rsp+150h+var_130], rax
0x18009eaf7  call    CipAllocateLocalValidationContext
0x18009eafc  mov     rdi, [rsp+150h+Entry]
0x18009eb01  mov     r14d, eax
0x18009eb04  test    eax, eax
0x18009eb06  js      loc_18009ED1D
0x18009eb0c  mov     rax, [rbp+50h+arg_30]
0x18009eb13  mov     [rdi+2A8h], rax
0x18009eb1a  mov     rax, [rbp+50h+arg_20]
0x18009eb21  mov     [rdi+0CF0h], rax
0x18009eb28  mov     eax, esi
0x18009eb2a  mov     ecx, [rdi+0BF0h]
0x18009eb30  shl     eax, 0Eh
0x18009eb33  bts     ecx, 7
0x18009eb37  xor     eax, ecx
0x18009eb39  and     eax, 4000h
0x18009eb3e  xor     eax, ecx
0x18009eb40  mov     [rdi+0BF0h], eax
0x18009eb46  call    cs:__imp_PsGetCurrentServerSilo
0x18009eb4d  nop     dword ptr [rax+rax+00h]
0x18009eb52  mov     rcx, rax
0x18009eb55  call    cs:__imp_PsAttachSiloToCurrentThread
0x18009eb5c  nop     dword ptr [rax+rax+00h]
0x18009eb61  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18009eb68  lea     rdx, [rbp+50h+ApcState]; ApcState
0x18009eb6c  mov     rsi, rax
0x18009eb6f  mov     [rsp+150h+Entry], rax
0x18009eb74  call    cs:__imp_KeStackAttachProcess
0x18009eb7b  nop     dword ptr [rax+rax+00h]
0x18009eb80  mov     r8, qword ptr [rsp+150h+FileSize]
0x18009eb85  lea     rax, [rsp+150h+var_F8]
0x18009eb8a  mov     [rsp+150h+var_128], rax; __int64
0x18009eb8f  mov     r9d, 7
0x18009eb95  lea     rax, [rbp+50h+var_B0]
0x18009eb99  xor     edx, edx
0x18009eb9b  mov     rcx, r12; Object
0x18009eb9e  mov     [rsp+150h+var_130], rax; PHANDLE
0x18009eba3  call    CiReadFileOpenWithFlags
0x18009eba8  mov     r14d, eax
0x18009ebab  test    eax, eax
0x18009ebad  js      loc_18009ECED
0x18009ebb3  mov     r8, qword ptr [rsp+150h+FileSize]
0x18009ebb8  lea     rax, [rsp+150h+var_E8]
0x18009ebbd  mov     rdx, [rsp+150h+var_F8]
0x18009ebc2  mov     r9, r12
0x18009ebc5  mov     [rsp+150h+var_118], rax
0x18009ebca  mov     rcx, rdi
0x18009ebcd  mov     al, [rsp+150h+var_110]
0x18009ebd1  mov     [rsp+150h+var_120], al
0x18009ebd5  mov     al, [rsp+150h+var_10F]
0x18009ebd9  mov     byte ptr [rsp+150h+var_128], al
0x18009ebdd  mov     eax, [rsp+150h+var_F0]
0x18009ebe1  mov     dword ptr [rsp+150h+var_130], eax
0x18009ebe5  call    CipValidateDataMappedFileWithContext
0x18009ebea  mov     r14d, eax
0x18009ebed  test    eax, eax
0x18009ebef  js      loc_18009ECED
0x18009ebf5  mov     rcx, [rsp+150h+var_E0]
0x18009ebfa  mov     rsi, [rsp+150h+var_E8]
0x18009ebff  test    rcx, rcx
0x18009ec02  jz      short loc_18009EC4D
0x18009ec04  cmp     [rsp+150h+var_10E], 0
0x18009ec09  jnz     short loc_18009EC4A
0x18009ec0b  mov     rax, cs:g_CipWhichLevelComparisons
0x18009ec12  movzx   r8d, byte ptr [rsi+34h]
0x18009ec17  and     r8d, 0Fh
0x18009ec1b  mov     edx, [rax+30h]
0x18009ec1e  bt      edx, r8d
0x18009ec22  jnb     short loc_18009EC4A
0x18009ec24  mov     rdx, [rsp+150h+var_F8]
0x18009ec29  mov     r9b, 1
0x18009ec2c  mov     r8d, ebx
0x18009ec2f  mov     byte ptr [rsp+150h+var_130], 0
0x18009ec34  mov     rcx, r12
0x18009ec37  call    CipMitigatePPLBypassThroughInterpreters
0x18009ec3c  mov     rcx, [rsp+150h+var_E0]
0x18009ec41  shr     eax, 1Fh
0x18009ec44  xor     al, 1
0x18009ec46  mov     [rcx], al
0x18009ec48  jmp     short loc_18009EC4D
0x18009ec4a  mov     byte ptr [rcx], 0
0x18009ec4d  mov     rcx, [rsp+150h+var_D8]
0x18009ec52  test    rcx, rcx
0x18009ec55  jz      short loc_18009EC61
0x18009ec57  mov     eax, [rsi+40h]
0x18009ec5a  shr     eax, 2
0x18009ec5d  and     al, 1
0x18009ec5f  mov     [rcx], al
0x18009ec61  test    r13, r13
0x18009ec64  jz      short loc_18009EC8E
0x18009ec66  movups  xmm0, xmmword ptr [rsi]
0x18009ec69  movups  xmmword ptr [r13+0], xmm0
0x18009ec6e  movups  xmm1, xmmword ptr [rsi+10h]
0x18009ec72  movups  xmmword ptr [r13+10h], xmm1
0x18009ec77  movups  xmm0, xmmword ptr [rsi+20h]
0x18009ec7b  xorps   xmm1, xmm1
0x18009ec7e  movups  xmmword ptr [r13+20h], xmm0
0x18009ec83  movups  xmmword ptr [rsi], xmm1
0x18009ec86  movups  xmmword ptr [rsi+10h], xmm1
0x18009ec8a  movups  xmmword ptr [rsi+20h], xmm1
0x18009ec8e  mov     rcx, [rbp+50h+var_D0]
0x18009ec92  test    rcx, rcx
0x18009ec95  jz      short loc_18009EC9C
0x18009ec97  mov     al, [rsi+34h]
0x18009ec9a  mov     [rcx], al
0x18009ec9c  mov     rdx, [rbp+50h+var_C8]
0x18009eca0  test    rdx, rdx
0x18009eca3  jz      short loc_18009ECAD
0x18009eca5  mov     eax, [rdi+0BC8h]
0x18009ecab  mov     [rdx], eax
0x18009ecad  test    r15, r15
0x18009ecb0  jz      short loc_18009ECDA
0x18009ecb2  mov     eax, [rdi+0BCCh]
0x18009ecb8  mov     [r15], eax
0x18009ecbb  mov     rax, [rbp+50h+var_C0]
0x18009ecbf  test    rax, rax
0x18009ecc2  jz      short loc_18009ECDA
0x18009ecc4  mov     r8d, [rdi+0BCCh]; Size
0x18009eccb  mov     rcx, rax; void *
0x18009ecce  mov     rdx, [rdi+0BD0h]; Src
0x18009ecd5  call    memmove
0x18009ecda  mov     rax, [rbp+50h+var_B8]
0x18009ecde  mov     rsi, [rsp+150h+Entry]
0x18009ece3  test    rax, rax
0x18009ece6  jz      short loc_18009ECED
0x18009ece8  mov     [rax], rdi
0x18009eceb  xor     edi, edi
0x18009eced  cmp     [rsp+150h+var_F8], 0
0x18009ecf3  jz      short loc_18009ECFE
0x18009ecf5  lea     rcx, [rbp+50h+var_B0]
0x18009ecf9  call    CiReadFileClose
0x18009ecfe  lea     rcx, [rbp+50h+ApcState]; ApcState
0x18009ed02  call    cs:__imp_KeUnstackDetachProcess
0x18009ed09  nop     dword ptr [rax+rax+00h]
0x18009ed0e  mov     rcx, rsi
0x18009ed11  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18009ed18  nop     dword ptr [rax+rax+00h]
0x18009ed1d  test    rdi, rdi
0x18009ed20  jz      short loc_18009ED2A
0x18009ed22  mov     rcx, rdi; Entry
0x18009ed25  call    CiFreeValidationContext
0x18009ed2a  mov     eax, r14d
0x18009ed2d  mov     rcx, [rbp+50h+var_50]
0x18009ed31  xor     rcx, rsp; StackCookie
0x18009ed34  call    __security_check_cookie
0x18009ed39  add     rsp, 118h
0x18009ed40  pop     r15
0x18009ed42  pop     r14
0x18009ed44  pop     r13
0x18009ed46  pop     r12
0x18009ed48  pop     rdi
0x18009ed49  pop     rsi
0x18009ed4a  pop     rbx
0x18009ed4b  pop     rbp
0x18009ed4c  retn
```
