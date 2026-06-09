# CipValidateFileObjectByFileOrPageHash

- ea: `0x180099aa4`
- end: `0x180099e42`
- name: `CipValidateFileObjectByFileOrPageHash`
- size: `926`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180064340`
- `0x180096f80`
- `0x1800e3740`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18005b0bc`
- `0x180099118`
- `0x180099340`
- `0x180099aa4`
- `0x18009a008`
- `0x18009b440`
- `0x18009b7b0`
- `0x1800a4098`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x180099b86`
- `ntoskrnl!FsRtlGetFileSize` at `0x180099b86`
- `ntoskrnl!KeStackAttachProcess` at `0x180099c68`
- `ntoskrnl!KeStackAttachProcess` at `0x180099c68`
- `ntoskrnl!PsGetCurrentProcess` at `0x180099bcb`
- `ntoskrnl!PsGetCurrentProcess` at `0x180099bcb`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180099df6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180099df6`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180099c49`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180099c49`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180099e05`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180099e05`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180099c3a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x180099c3a`

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
          *((_QWORD *)v22 + 412) = a5;
          v22[762] = (v22[762] | 0x80) ^ ((*((_WORD *)v22 + 1524) | 0x80) ^ (unsigned __int16)(v19 << 14)) & 0x4000;
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
                *v43 = v22[752];
              if ( a10 )
              {
                *a10 = v22[753];
                if ( v44 )
                  memmove(v44, *((const void **)v22 + 377), v22[753]);
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
0x180099aa4  push    rbp
0x180099aa6  push    rbx
0x180099aa7  push    rsi
0x180099aa8  push    rdi
0x180099aa9  push    r12
0x180099aab  push    r13
0x180099aad  push    r14
0x180099aaf  push    r15
0x180099ab1  lea     rbp, [rsp-18h]
0x180099ab6  sub     rsp, 118h
0x180099abd  mov     rax, cs:__security_cookie
0x180099ac4  xor     rax, rsp
0x180099ac7  mov     [rbp+50h+var_50], rax
0x180099acb  mov     rax, [rbp+50h+arg_38]
0x180099ad2  xorps   xmm0, xmm0
0x180099ad5  mov     r15, [rbp+50h+arg_48]
0x180099adc  xor     ebx, ebx
0x180099ade  mov     r13, [rbp+50h+arg_28]
0x180099ae5  mov     r12, rcx
0x180099ae8  mov     rcx, [rbp+50h+arg_40]
0x180099aef  mov     edi, edx
0x180099af1  mov     [rbp+50h+var_D0], rax
0x180099af5  mov     rax, [rbp+50h+arg_50]
0x180099afc  mov     [rbp+50h+var_C8], rax
0x180099b00  mov     rax, [rbp+50h+arg_58]
0x180099b07  mov     [rsp+150h+var_D8], rax
0x180099b0c  mov     rax, [rbp+50h+arg_60]
0x180099b13  mov     [rbp+50h+var_C0], rcx
0x180099b17  mov     rcx, [rbp+50h+arg_68]
0x180099b1e  mov     [rsp+150h+var_E0], rax
0x180099b23  mov     [rsp+150h+var_110], r9b
0x180099b28  mov     [rsp+150h+var_10F], r8b
0x180099b2d  mov     [rsp+150h+var_F0], edx
0x180099b31  mov     [rbp+50h+var_B8], rcx
0x180099b35  mov     [rsp+150h+Entry], rbx
0x180099b3a  mov     [rsp+150h+var_F8], rbx
0x180099b3f  mov     qword ptr [rsp+150h+FileSize], rbx
0x180099b44  mov     [rsp+150h+var_E8], rbx
0x180099b49  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink], xmm0
0x180099b4d  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink+10h], xmm0
0x180099b51  movups  xmmword ptr [rbp+50h+ApcState.Process], xmm0
0x180099b55  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x180099b59  movups  [rbp+50h+var_A0], xmm0
0x180099b5d  movups  [rbp+50h+var_90], xmm0
0x180099b61  test    r15, r15
0x180099b64  jz      short loc_180099B7E
0x180099b66  cmp     dword ptr [r15], 40h ; '@'
0x180099b6a  jnb     short loc_180099B7E
0x180099b6c  mov     dword ptr [r15], 40h ; '@'
0x180099b73  mov     r14d, 0C0000023h
0x180099b79  jmp     loc_180099E1E
0x180099b7e  lea     rdx, [rsp+150h+FileSize]; FileSize
0x180099b83  mov     rcx, r12; FileObject
0x180099b86  call    cs:__imp_FsRtlGetFileSize
0x180099b8d  nop     dword ptr [rax+rax+00h]
0x180099b92  mov     r14d, eax
0x180099b95  test    eax, eax
0x180099b97  js      loc_180099E1E
0x180099b9d  mov     rcx, r12
0x180099ba0  call    CipIsCimFile
0x180099ba5  movzx   esi, al
0x180099ba8  mov     [rsp+150h+var_10E], sil
0x180099bad  test    al, al
0x180099baf  jnz     short loc_180099BCB
0x180099bb1  mov     rbx, qword ptr [rsp+150h+FileSize]
0x180099bb6  mov     eax, 0FFFFFFFFh
0x180099bbb  cmp     rbx, rax
0x180099bbe  jbe     short loc_180099BCB
0x180099bc0  mov     r14d, 0C000007Bh
0x180099bc6  jmp     loc_180099E1E
0x180099bcb  call    cs:__imp_PsGetCurrentProcess
0x180099bd2  nop     dword ptr [rax+rax+00h]
0x180099bd7  mov     r9, r12
0x180099bda  xor     edx, edx
0x180099bdc  mov     r8, rax
0x180099bdf  mov     ecx, edi
0x180099be1  lea     rax, [rsp+150h+Entry]
0x180099be6  mov     [rsp+150h+var_130], rax
0x180099beb  call    CipAllocateLocalValidationContext
0x180099bf0  mov     rdi, [rsp+150h+Entry]
0x180099bf5  mov     r14d, eax
0x180099bf8  test    eax, eax
0x180099bfa  js      loc_180099E11
0x180099c00  mov     rax, [rbp+50h+arg_30]
0x180099c07  mov     [rdi+2A8h], rax
0x180099c0e  mov     rax, [rbp+50h+arg_20]
0x180099c15  mov     [rdi+0CE0h], rax
0x180099c1c  mov     eax, esi
0x180099c1e  mov     ecx, [rdi+0BE8h]
0x180099c24  shl     eax, 0Eh
0x180099c27  bts     ecx, 7
0x180099c2b  xor     eax, ecx
0x180099c2d  and     eax, 4000h
0x180099c32  xor     eax, ecx
0x180099c34  mov     [rdi+0BE8h], eax
0x180099c3a  call    cs:__imp_PsGetCurrentServerSilo
0x180099c41  nop     dword ptr [rax+rax+00h]
0x180099c46  mov     rcx, rax
0x180099c49  call    cs:__imp_PsAttachSiloToCurrentThread
0x180099c50  nop     dword ptr [rax+rax+00h]
0x180099c55  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180099c5c  lea     rdx, [rbp+50h+ApcState]; ApcState
0x180099c60  mov     rsi, rax
0x180099c63  mov     [rsp+150h+Entry], rax
0x180099c68  call    cs:__imp_KeStackAttachProcess
0x180099c6f  nop     dword ptr [rax+rax+00h]
0x180099c74  mov     r8, qword ptr [rsp+150h+FileSize]
0x180099c79  lea     rax, [rsp+150h+var_F8]
0x180099c7e  mov     [rsp+150h+var_128], rax; __int64
0x180099c83  mov     r9d, 7
0x180099c89  lea     rax, [rbp+50h+var_B0]
0x180099c8d  xor     edx, edx
0x180099c8f  mov     rcx, r12; Object
0x180099c92  mov     [rsp+150h+var_130], rax; PHANDLE
0x180099c97  call    CiReadFileOpenWithFlags
0x180099c9c  mov     r14d, eax
0x180099c9f  test    eax, eax
0x180099ca1  js      loc_180099DE1
0x180099ca7  mov     r8, qword ptr [rsp+150h+FileSize]
0x180099cac  lea     rax, [rsp+150h+var_E8]
0x180099cb1  mov     rdx, [rsp+150h+var_F8]
0x180099cb6  mov     r9, r12
0x180099cb9  mov     [rsp+150h+var_118], rax
0x180099cbe  mov     rcx, rdi
0x180099cc1  mov     al, [rsp+150h+var_110]
0x180099cc5  mov     [rsp+150h+var_120], al
0x180099cc9  mov     al, [rsp+150h+var_10F]
0x180099ccd  mov     byte ptr [rsp+150h+var_128], al
0x180099cd1  mov     eax, [rsp+150h+var_F0]
0x180099cd5  mov     dword ptr [rsp+150h+var_130], eax
0x180099cd9  call    CipValidateDataMappedFileWithContext
0x180099cde  mov     r14d, eax
0x180099ce1  test    eax, eax
0x180099ce3  js      loc_180099DE1
0x180099ce9  mov     rcx, [rsp+150h+var_E0]
0x180099cee  mov     rsi, [rsp+150h+var_E8]
0x180099cf3  test    rcx, rcx
0x180099cf6  jz      short loc_180099D41
0x180099cf8  cmp     [rsp+150h+var_10E], 0
0x180099cfd  jnz     short loc_180099D3E
0x180099cff  mov     rax, cs:g_CipWhichLevelComparisons
0x180099d06  movzx   r8d, byte ptr [rsi+34h]
0x180099d0b  and     r8d, 0Fh
0x180099d0f  mov     edx, [rax+30h]
0x180099d12  bt      edx, r8d
0x180099d16  jnb     short loc_180099D3E
0x180099d18  mov     rdx, [rsp+150h+var_F8]
0x180099d1d  mov     r9b, 1
0x180099d20  mov     r8d, ebx
0x180099d23  mov     byte ptr [rsp+150h+var_130], 0
0x180099d28  mov     rcx, r12
0x180099d2b  call    CipMitigatePPLBypassThroughInterpreters
0x180099d30  mov     rcx, [rsp+150h+var_E0]
0x180099d35  shr     eax, 1Fh
0x180099d38  xor     al, 1
0x180099d3a  mov     [rcx], al
0x180099d3c  jmp     short loc_180099D41
0x180099d3e  mov     byte ptr [rcx], 0
0x180099d41  mov     rcx, [rsp+150h+var_D8]
0x180099d46  test    rcx, rcx
0x180099d49  jz      short loc_180099D55
0x180099d4b  mov     eax, [rsi+40h]
0x180099d4e  shr     eax, 2
0x180099d51  and     al, 1
0x180099d53  mov     [rcx], al
0x180099d55  test    r13, r13
0x180099d58  jz      short loc_180099D82
0x180099d5a  movups  xmm0, xmmword ptr [rsi]
0x180099d5d  movups  xmmword ptr [r13+0], xmm0
0x180099d62  movups  xmm1, xmmword ptr [rsi+10h]
0x180099d66  movups  xmmword ptr [r13+10h], xmm1
0x180099d6b  movups  xmm0, xmmword ptr [rsi+20h]
0x180099d6f  xorps   xmm1, xmm1
0x180099d72  movups  xmmword ptr [r13+20h], xmm0
0x180099d77  movups  xmmword ptr [rsi], xmm1
0x180099d7a  movups  xmmword ptr [rsi+10h], xmm1
0x180099d7e  movups  xmmword ptr [rsi+20h], xmm1
0x180099d82  mov     rcx, [rbp+50h+var_D0]
0x180099d86  test    rcx, rcx
0x180099d89  jz      short loc_180099D90
0x180099d8b  mov     al, [rsi+34h]
0x180099d8e  mov     [rcx], al
0x180099d90  mov     rdx, [rbp+50h+var_C8]
0x180099d94  test    rdx, rdx
0x180099d97  jz      short loc_180099DA1
0x180099d99  mov     eax, [rdi+0BC0h]
0x180099d9f  mov     [rdx], eax
0x180099da1  test    r15, r15
0x180099da4  jz      short loc_180099DCE
0x180099da6  mov     eax, [rdi+0BC4h]
0x180099dac  mov     [r15], eax
0x180099daf  mov     rax, [rbp+50h+var_C0]
0x180099db3  test    rax, rax
0x180099db6  jz      short loc_180099DCE
0x180099db8  mov     r8d, [rdi+0BC4h]; Size
0x180099dbf  mov     rcx, rax; void *
0x180099dc2  mov     rdx, [rdi+0BC8h]; Src
0x180099dc9  call    memmove
0x180099dce  mov     rax, [rbp+50h+var_B8]
0x180099dd2  mov     rsi, [rsp+150h+Entry]
0x180099dd7  test    rax, rax
0x180099dda  jz      short loc_180099DE1
0x180099ddc  mov     [rax], rdi
0x180099ddf  xor     edi, edi
0x180099de1  cmp     [rsp+150h+var_F8], 0
0x180099de7  jz      short loc_180099DF2
0x180099de9  lea     rcx, [rbp+50h+var_B0]
0x180099ded  call    CiReadFileClose
0x180099df2  lea     rcx, [rbp+50h+ApcState]; ApcState
0x180099df6  call    cs:__imp_KeUnstackDetachProcess
0x180099dfd  nop     dword ptr [rax+rax+00h]
0x180099e02  mov     rcx, rsi
0x180099e05  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180099e0c  nop     dword ptr [rax+rax+00h]
0x180099e11  test    rdi, rdi
0x180099e14  jz      short loc_180099E1E
0x180099e16  mov     rcx, rdi; Entry
0x180099e19  call    CiFreeValidationContext
0x180099e1e  mov     eax, r14d
0x180099e21  mov     rcx, [rbp+50h+var_50]
0x180099e25  xor     rcx, rsp; StackCookie
0x180099e28  call    __security_check_cookie
0x180099e2d  add     rsp, 118h
0x180099e34  pop     r15
0x180099e36  pop     r14
0x180099e38  pop     r13
0x180099e3a  pop     r12
0x180099e3c  pop     rdi
0x180099e3d  pop     rsi
0x180099e3e  pop     rbx
0x180099e3f  pop     rbp
0x180099e40  retn
```
