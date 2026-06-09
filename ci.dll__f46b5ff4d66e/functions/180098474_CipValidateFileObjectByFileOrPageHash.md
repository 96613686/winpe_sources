# CipValidateFileObjectByFileOrPageHash

- ea: `0x180098474`
- end: `0x180098812`
- name: `CipValidateFileObjectByFileOrPageHash`
- size: `926`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180063a10`
- `0x180095950`
- `0x1800e3750`

## callees

- `0x18002bef0`
- `0x18002c040`
- `0x18005a3ac`
- `0x180097ae8`
- `0x180097d10`
- `0x180098474`
- `0x1800989d8`
- `0x180099e10`
- `0x18009a180`
- `0x1800a2a68`

## import_xrefs

- `ntoskrnl!FsRtlGetFileSize` at `0x180098556`
- `ntoskrnl!FsRtlGetFileSize` at `0x180098556`
- `ntoskrnl!KeStackAttachProcess` at `0x180098638`
- `ntoskrnl!KeStackAttachProcess` at `0x180098638`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009859b`
- `ntoskrnl!PsGetCurrentProcess` at `0x18009859b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800987c6`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800987c6`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180098619`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180098619`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800987d5`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800987d5`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009860a`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009860a`

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
0x180098474  push    rbp
0x180098476  push    rbx
0x180098477  push    rsi
0x180098478  push    rdi
0x180098479  push    r12
0x18009847b  push    r13
0x18009847d  push    r14
0x18009847f  push    r15
0x180098481  lea     rbp, [rsp-18h]
0x180098486  sub     rsp, 118h
0x18009848d  mov     rax, cs:__security_cookie
0x180098494  xor     rax, rsp
0x180098497  mov     [rbp+50h+var_50], rax
0x18009849b  mov     rax, [rbp+50h+arg_38]
0x1800984a2  xorps   xmm0, xmm0
0x1800984a5  mov     r15, [rbp+50h+arg_48]
0x1800984ac  xor     ebx, ebx
0x1800984ae  mov     r13, [rbp+50h+arg_28]
0x1800984b5  mov     r12, rcx
0x1800984b8  mov     rcx, [rbp+50h+arg_40]
0x1800984bf  mov     edi, edx
0x1800984c1  mov     [rbp+50h+var_D0], rax
0x1800984c5  mov     rax, [rbp+50h+arg_50]
0x1800984cc  mov     [rbp+50h+var_C8], rax
0x1800984d0  mov     rax, [rbp+50h+arg_58]
0x1800984d7  mov     [rsp+150h+var_D8], rax
0x1800984dc  mov     rax, [rbp+50h+arg_60]
0x1800984e3  mov     [rbp+50h+var_C0], rcx
0x1800984e7  mov     rcx, [rbp+50h+arg_68]
0x1800984ee  mov     [rsp+150h+var_E0], rax
0x1800984f3  mov     [rsp+150h+var_110], r9b
0x1800984f8  mov     [rsp+150h+var_10F], r8b
0x1800984fd  mov     [rsp+150h+var_F0], edx
0x180098501  mov     [rbp+50h+var_B8], rcx
0x180098505  mov     [rsp+150h+Entry], rbx
0x18009850a  mov     [rsp+150h+var_F8], rbx
0x18009850f  mov     qword ptr [rsp+150h+FileSize], rbx
0x180098514  mov     [rsp+150h+var_E8], rbx
0x180098519  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink], xmm0
0x18009851d  movups  xmmword ptr [rbp+50h+ApcState.ApcListHead.Flink+10h], xmm0
0x180098521  movups  xmmword ptr [rbp+50h+ApcState.Process], xmm0
0x180098525  movups  xmmword ptr [rbp+50h+var_B0], xmm0
0x180098529  movups  [rbp+50h+var_A0], xmm0
0x18009852d  movups  [rbp+50h+var_90], xmm0
0x180098531  test    r15, r15
0x180098534  jz      short loc_18009854E
0x180098536  cmp     dword ptr [r15], 40h ; '@'
0x18009853a  jnb     short loc_18009854E
0x18009853c  mov     dword ptr [r15], 40h ; '@'
0x180098543  mov     r14d, 0C0000023h
0x180098549  jmp     loc_1800987EE
0x18009854e  lea     rdx, [rsp+150h+FileSize]; FileSize
0x180098553  mov     rcx, r12; FileObject
0x180098556  call    cs:__imp_FsRtlGetFileSize
0x18009855d  nop     dword ptr [rax+rax+00h]
0x180098562  mov     r14d, eax
0x180098565  test    eax, eax
0x180098567  js      loc_1800987EE
0x18009856d  mov     rcx, r12
0x180098570  call    CipIsCimFile
0x180098575  movzx   esi, al
0x180098578  mov     [rsp+150h+var_10E], sil
0x18009857d  test    al, al
0x18009857f  jnz     short loc_18009859B
0x180098581  mov     rbx, qword ptr [rsp+150h+FileSize]
0x180098586  mov     eax, 0FFFFFFFFh
0x18009858b  cmp     rbx, rax
0x18009858e  jbe     short loc_18009859B
0x180098590  mov     r14d, 0C000007Bh
0x180098596  jmp     loc_1800987EE
0x18009859b  call    cs:__imp_PsGetCurrentProcess
0x1800985a2  nop     dword ptr [rax+rax+00h]
0x1800985a7  mov     r9, r12
0x1800985aa  xor     edx, edx
0x1800985ac  mov     r8, rax
0x1800985af  mov     ecx, edi
0x1800985b1  lea     rax, [rsp+150h+Entry]
0x1800985b6  mov     [rsp+150h+var_130], rax
0x1800985bb  call    CipAllocateLocalValidationContext
0x1800985c0  mov     rdi, [rsp+150h+Entry]
0x1800985c5  mov     r14d, eax
0x1800985c8  test    eax, eax
0x1800985ca  js      loc_1800987E1
0x1800985d0  mov     rax, [rbp+50h+arg_30]
0x1800985d7  mov     [rdi+2A8h], rax
0x1800985de  mov     rax, [rbp+50h+arg_20]
0x1800985e5  mov     [rdi+0CE0h], rax
0x1800985ec  mov     eax, esi
0x1800985ee  mov     ecx, [rdi+0BE8h]
0x1800985f4  shl     eax, 0Eh
0x1800985f7  bts     ecx, 7
0x1800985fb  xor     eax, ecx
0x1800985fd  and     eax, 4000h
0x180098602  xor     eax, ecx
0x180098604  mov     [rdi+0BE8h], eax
0x18009860a  call    cs:__imp_PsGetCurrentServerSilo
0x180098611  nop     dword ptr [rax+rax+00h]
0x180098616  mov     rcx, rax
0x180098619  call    cs:__imp_PsAttachSiloToCurrentThread
0x180098620  nop     dword ptr [rax+rax+00h]
0x180098625  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18009862c  lea     rdx, [rbp+50h+ApcState]; ApcState
0x180098630  mov     rsi, rax
0x180098633  mov     [rsp+150h+Entry], rax
0x180098638  call    cs:__imp_KeStackAttachProcess
0x18009863f  nop     dword ptr [rax+rax+00h]
0x180098644  mov     r8, qword ptr [rsp+150h+FileSize]
0x180098649  lea     rax, [rsp+150h+var_F8]
0x18009864e  mov     [rsp+150h+var_128], rax; __int64
0x180098653  mov     r9d, 7
0x180098659  lea     rax, [rbp+50h+var_B0]
0x18009865d  xor     edx, edx
0x18009865f  mov     rcx, r12; Object
0x180098662  mov     [rsp+150h+var_130], rax; PHANDLE
0x180098667  call    CiReadFileOpenWithFlags
0x18009866c  mov     r14d, eax
0x18009866f  test    eax, eax
0x180098671  js      loc_1800987B1
0x180098677  mov     r8, qword ptr [rsp+150h+FileSize]
0x18009867c  lea     rax, [rsp+150h+var_E8]
0x180098681  mov     rdx, [rsp+150h+var_F8]
0x180098686  mov     r9, r12
0x180098689  mov     [rsp+150h+var_118], rax
0x18009868e  mov     rcx, rdi
0x180098691  mov     al, [rsp+150h+var_110]
0x180098695  mov     [rsp+150h+var_120], al
0x180098699  mov     al, [rsp+150h+var_10F]
0x18009869d  mov     byte ptr [rsp+150h+var_128], al
0x1800986a1  mov     eax, [rsp+150h+var_F0]
0x1800986a5  mov     dword ptr [rsp+150h+var_130], eax
0x1800986a9  call    CipValidateDataMappedFileWithContext
0x1800986ae  mov     r14d, eax
0x1800986b1  test    eax, eax
0x1800986b3  js      loc_1800987B1
0x1800986b9  mov     rcx, [rsp+150h+var_E0]
0x1800986be  mov     rsi, [rsp+150h+var_E8]
0x1800986c3  test    rcx, rcx
0x1800986c6  jz      short loc_180098711
0x1800986c8  cmp     [rsp+150h+var_10E], 0
0x1800986cd  jnz     short loc_18009870E
0x1800986cf  mov     rax, cs:g_CipWhichLevelComparisons
0x1800986d6  movzx   r8d, byte ptr [rsi+34h]
0x1800986db  and     r8d, 0Fh
0x1800986df  mov     edx, [rax+30h]
0x1800986e2  bt      edx, r8d
0x1800986e6  jnb     short loc_18009870E
0x1800986e8  mov     rdx, [rsp+150h+var_F8]
0x1800986ed  mov     r9b, 1
0x1800986f0  mov     r8d, ebx
0x1800986f3  mov     byte ptr [rsp+150h+var_130], 0
0x1800986f8  mov     rcx, r12
0x1800986fb  call    CipMitigatePPLBypassThroughInterpreters
0x180098700  mov     rcx, [rsp+150h+var_E0]
0x180098705  shr     eax, 1Fh
0x180098708  xor     al, 1
0x18009870a  mov     [rcx], al
0x18009870c  jmp     short loc_180098711
0x18009870e  mov     byte ptr [rcx], 0
0x180098711  mov     rcx, [rsp+150h+var_D8]
0x180098716  test    rcx, rcx
0x180098719  jz      short loc_180098725
0x18009871b  mov     eax, [rsi+40h]
0x18009871e  shr     eax, 2
0x180098721  and     al, 1
0x180098723  mov     [rcx], al
0x180098725  test    r13, r13
0x180098728  jz      short loc_180098752
0x18009872a  movups  xmm0, xmmword ptr [rsi]
0x18009872d  movups  xmmword ptr [r13+0], xmm0
0x180098732  movups  xmm1, xmmword ptr [rsi+10h]
0x180098736  movups  xmmword ptr [r13+10h], xmm1
0x18009873b  movups  xmm0, xmmword ptr [rsi+20h]
0x18009873f  xorps   xmm1, xmm1
0x180098742  movups  xmmword ptr [r13+20h], xmm0
0x180098747  movups  xmmword ptr [rsi], xmm1
0x18009874a  movups  xmmword ptr [rsi+10h], xmm1
0x18009874e  movups  xmmword ptr [rsi+20h], xmm1
0x180098752  mov     rcx, [rbp+50h+var_D0]
0x180098756  test    rcx, rcx
0x180098759  jz      short loc_180098760
0x18009875b  mov     al, [rsi+34h]
0x18009875e  mov     [rcx], al
0x180098760  mov     rdx, [rbp+50h+var_C8]
0x180098764  test    rdx, rdx
0x180098767  jz      short loc_180098771
0x180098769  mov     eax, [rdi+0BC0h]
0x18009876f  mov     [rdx], eax
0x180098771  test    r15, r15
0x180098774  jz      short loc_18009879E
0x180098776  mov     eax, [rdi+0BC4h]
0x18009877c  mov     [r15], eax
0x18009877f  mov     rax, [rbp+50h+var_C0]
0x180098783  test    rax, rax
0x180098786  jz      short loc_18009879E
0x180098788  mov     r8d, [rdi+0BC4h]; Size
0x18009878f  mov     rcx, rax; void *
0x180098792  mov     rdx, [rdi+0BC8h]; Src
0x180098799  call    memmove
0x18009879e  mov     rax, [rbp+50h+var_B8]
0x1800987a2  mov     rsi, [rsp+150h+Entry]
0x1800987a7  test    rax, rax
0x1800987aa  jz      short loc_1800987B1
0x1800987ac  mov     [rax], rdi
0x1800987af  xor     edi, edi
0x1800987b1  cmp     [rsp+150h+var_F8], 0
0x1800987b7  jz      short loc_1800987C2
0x1800987b9  lea     rcx, [rbp+50h+var_B0]
0x1800987bd  call    CiReadFileClose
0x1800987c2  lea     rcx, [rbp+50h+ApcState]; ApcState
0x1800987c6  call    cs:__imp_KeUnstackDetachProcess
0x1800987cd  nop     dword ptr [rax+rax+00h]
0x1800987d2  mov     rcx, rsi
0x1800987d5  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800987dc  nop     dword ptr [rax+rax+00h]
0x1800987e1  test    rdi, rdi
0x1800987e4  jz      short loc_1800987EE
0x1800987e6  mov     rcx, rdi; Entry
0x1800987e9  call    CiFreeValidationContext
0x1800987ee  mov     eax, r14d
0x1800987f1  mov     rcx, [rbp+50h+var_50]
0x1800987f5  xor     rcx, rsp; StackCookie
0x1800987f8  call    __security_check_cookie
0x1800987fd  add     rsp, 118h
0x180098804  pop     r15
0x180098806  pop     r14
0x180098808  pop     r13
0x18009880a  pop     r12
0x18009880c  pop     rdi
0x18009880d  pop     rsi
0x18009880e  pop     rbx
0x18009880f  pop     rbp
0x180098810  retn
```
