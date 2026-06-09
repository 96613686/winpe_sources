# EfspConstructNewPfileHeader

- ea: `0x14000a408`
- end: `0x14000a786`
- name: `EfspConstructNewPfileHeader`
- size: `894`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x140052604`
- `0x1400577d4`

## callees

- `0x14000a408`
- `0x14000a870`
- `0x14000c230`
- `0x14000c380`
- `0x14004f910`
- `0x140055448`
- `0x14005625c`
- `0x14005693c`
- `0x140057adc`
- `0x140057b2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a757`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a757`
- `ntoskrnl!ExAllocatePool2` at `0x14000a5a1`
- `ntoskrnl!ExAllocatePool2` at `0x14000a5a1`
- `ntoskrnl!ExUuidCreate` at `0x14000a68f`
- `ntoskrnl!ExUuidCreate` at `0x14000a68f`

## pseudocode

```c
__int64 __fastcall EfspConstructNewPfileHeader(
        UUID *a1,
        size_t a2,
        int a3,
        _QWORD *a4,
        __int64 a5,
        UUID **a6,
        unsigned int *a7)
{
  unsigned int v8; // r14d
  UUID *v10; // rdi
  NTSTATUS EfsStreamInfo; // ebx
  char *v12; // r12
  __int64 v13; // r13
  __int64 v14; // rcx
  unsigned int v15; // edx
  __int64 v16; // r8
  unsigned int v17; // r15d
  UUID *Pool2; // rax
  char *v19; // rsi
  __int64 v20; // r14
  void *v21; // rdx
  __int64 v22; // rcx
  _DWORD *v23; // rcx
  size_t Size; // [rsp+40h] [rbp-81h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-79h] BYREF
  __int64 v27; // [rsp+50h] [rbp-71h] BYREF
  void *Src; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-61h] BYREF
  void *v30; // [rsp+68h] [rbp-59h] BYREF
  void *v31; // [rsp+70h] [rbp-51h] BYREF
  __int128 v32; // [rsp+78h] [rbp-49h]
  _QWORD *v33; // [rsp+88h] [rbp-39h]
  __int64 v34; // [rsp+90h] [rbp-31h]
  UUID **v35; // [rsp+98h] [rbp-29h]
  unsigned int *v36; // [rsp+A0h] [rbp-21h]
  UUID Uuid; // [rsp+A8h] [rbp-19h] BYREF

  v34 = a5;
  v8 = a2;
  v35 = a6;
  v36 = a7;
  v33 = a4;
  v10 = 0;
  v30 = 0;
  v32 = 0;
  Size = 0;
  v27 = 0;
  v26 = 0;
  v29 = 0;
  Uuid = 0;
  Src = 0;
  v31 = 0;
  EfsStreamInfo = EfsGetEfsStreamInfo(a1, a2, 16);
  if ( EfsStreamInfo < 0 )
    goto LABEL_26;
  EfsStreamInfo = EfspCreateFileLicenseHeaderAndKey(
                    DWORD2(v32),
                    v32,
                    a3,
                    (unsigned int)&Size + 4,
                    (__int64)&v27,
                    (__int64)&Size,
                    (__int64)&v30);
  if ( EfsStreamInfo < 0 )
    goto LABEL_26;
  EfsStreamInfo = EfspAquirePFileStream(a1, &Src);
  if ( EfsStreamInfo < 0 )
    goto LABEL_26;
  v12 = (char *)Src;
  v13 = *(unsigned int *)((char *)Src + 14);
  v14 = *(unsigned int *)((char *)Src + v13 + 50);
  v15 = v14 + *(_DWORD *)((char *)Src + v13 + 54);
  if ( v15 < (unsigned int)v14 )
    goto LABEL_25;
  if ( v15 > v8 )
  {
    v16 = 5903;
LABEL_7:
    EfsStreamInfo = -1073741790;
    EfspTraceLogAssert(v14, 6, v16, 3221225506LL);
    goto LABEL_26;
  }
  Src = (void *)((unsigned int)Size - (unsigned __int64)DWORD2(v32));
  EfsStreamInfo = RtlLongLongAdd(v15, Src, &v26);
  if ( EfsStreamInfo >= 0 )
  {
    EfsStreamInfo = RtlLongLongAdd(v26, 32, &v26);
    if ( EfsStreamInfo >= 0 )
    {
      v17 = v26;
      if ( v26 > 0xFFFFFFFF )
        goto LABEL_25;
      if ( (unsigned int)v26 < 0x20 )
      {
        v16 = 5939;
        goto LABEL_7;
      }
      Pool2 = (UUID *)ExAllocatePool2(256, (unsigned int)v26, 1836279365);
      v10 = Pool2;
      if ( !Pool2 )
      {
        EfsStreamInfo = -1073741670;
        goto LABEL_26;
      }
      *Pool2 = *a1;
      Pool2[1] = a1[1];
      Pool2->Data1 = v17;
      EfsStreamInfo = EfspAquirePFileStream(Pool2, &v31);
      if ( EfsStreamInfo >= 0 )
      {
        v19 = (char *)v31;
        memmove(v31, v12, *(unsigned int *)(v12 + 14) + 18LL);
        v20 = *(unsigned int *)(v19 + 14);
        v21 = Src;
        *(_OWORD *)&v19[v20 + 18] = *(_OWORD *)&v12[v13 + 18];
        *(_OWORD *)&v19[v20 + 34] = *(_OWORD *)&v12[v13 + 34];
        *(_QWORD *)&v19[v20 + 50] = *(_QWORD *)&v12[v13 + 50];
        *(_DWORD *)&v19[v20 + 34] = Size;
        *(_DWORD *)&v19[v20 + 38] = v17 - 32;
        *(_QWORD *)&v19[v20 + 42] = 0;
        EfsStreamInfo = RtlLongLongAdd(*(unsigned int *)&v12[v13 + 50], v21, &v29);
        if ( EfsStreamInfo >= 0 )
        {
          if ( v29 <= 0xFFFFFFFF )
          {
            v22 = (unsigned int)v29;
            *(_DWORD *)&v19[v20 + 50] = v29;
            memmove(&v19[v22], &v12[*(unsigned int *)&v12[v13 + 50]], *(unsigned int *)&v19[v20 + 54]);
            EfsStreamInfo = ExUuidCreate(&Uuid);
            if ( EfsStreamInfo >= 0 )
            {
              v10[1] = Uuid;
              EfsStreamInfo = EfspGetSetPFileInfo(v19, *(unsigned int *)&v19[v20 + 38], (__int64)&Uuid, 16);
              if ( EfsStreamInfo >= 0 )
              {
                memmove(&v19[*(unsigned int *)&v19[v20 + 30]], v30, (unsigned int)Size);
                if ( v33 )
                {
                  v23 = (_DWORD *)v34;
                  if ( v34 )
                  {
                    *v33 = v27;
                    *v23 = HIDWORD(Size);
                    v27 = 0;
                  }
                }
                *v35 = v10;
                v10 = 0;
                *v36 = v17;
              }
            }
            goto LABEL_26;
          }
          *(_DWORD *)&v19[v20 + 50] = -1;
LABEL_25:
          EfsStreamInfo = -1073741675;
        }
      }
    }
  }
LABEL_26:
  if ( v27 )
    EfspClipSpFree(v27);
  if ( v30 )
    EfspClipSpFree(v30);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  return (unsigned int)EfsStreamInfo;
}

```

## disassembly

```asm
0x14000a408  push    rbp
0x14000a40a  push    rbx
0x14000a40b  push    rsi
0x14000a40c  push    rdi
0x14000a40d  push    r12
0x14000a40f  push    r13
0x14000a411  push    r14
0x14000a413  push    r15
0x14000a415  lea     rbp, [rsp-7]
0x14000a41a  sub     rsp, 0C8h
0x14000a421  mov     rax, cs:__security_cookie
0x14000a428  xor     rax, rsp
0x14000a42b  mov     [rbp+3Fh+var_48], rax
0x14000a42f  mov     rax, [rbp+3Fh+arg_20]
0x14000a433  xorps   xmm0, xmm0
0x14000a436  mov     [rbp+3Fh+var_70], rax
0x14000a43a  mov     r15, r8
0x14000a43d  mov     rax, [rbp+3Fh+arg_28]
0x14000a441  mov     r14d, edx
0x14000a444  mov     [rbp+3Fh+var_68], rax
0x14000a448  mov     rsi, rcx
0x14000a44b  mov     rax, [rbp+3Fh+arg_30]
0x14000a44f  mov     [rbp+3Fh+var_60], rax
0x14000a453  xor     eax, eax
0x14000a455  mov     [rbp+3Fh+var_78], r9
0x14000a459  mov     edi, eax
0x14000a45b  lea     r9, [rbp+3Fh+var_88]
0x14000a45f  mov     [rbp+3Fh+var_98], rax
0x14000a463  movups  [rbp+3Fh+var_88], xmm0
0x14000a467  lea     r8d, [rax+8]
0x14000a46b  mov     dword ptr [rsp+100h+Size], eax
0x14000a46f  mov     [rbp+3Fh+var_B0], rax
0x14000a473  mov     dword ptr [rbp+3Fh+Size+4], eax
0x14000a476  mov     [rbp+3Fh+var_B8], rax
0x14000a47a  mov     [rbp+3Fh+var_A0], rax
0x14000a47e  movups  xmmword ptr [rbp+3Fh+Uuid.Data1], xmm0
0x14000a482  mov     [rbp+3Fh+Src], rax
0x14000a486  mov     [rbp+3Fh+var_90], rax
0x14000a48a  mov     dword ptr [rsp+100h+var_E0], 10h; int
0x14000a492  call    EfsGetEfsStreamInfo
0x14000a497  mov     ebx, eax
0x14000a499  test    eax, eax
0x14000a49b  js      loc_14000A731
0x14000a4a1  mov     rdx, qword ptr [rbp+3Fh+var_88]
0x14000a4a5  lea     rax, [rbp+3Fh+var_98]
0x14000a4a9  mov     ecx, dword ptr [rbp+3Fh+var_88+8]
0x14000a4ac  lea     r9, [rbp+3Fh+Size+4]
0x14000a4b0  mov     [rsp+100h+var_D0], rax
0x14000a4b5  mov     r8, r15
0x14000a4b8  lea     rax, [rsp+100h+Size]
0x14000a4bd  mov     qword ptr [rsp+100h+var_D8], rax
0x14000a4c2  lea     rax, [rbp+3Fh+var_B0]
0x14000a4c6  mov     [rsp+100h+var_E0], rax
0x14000a4cb  call    EfspCreateFileLicenseHeaderAndKey
0x14000a4d0  mov     ebx, eax
0x14000a4d2  test    eax, eax
0x14000a4d4  js      loc_14000A731
0x14000a4da  lea     rdx, [rbp+3Fh+Src]
0x14000a4de  mov     rcx, rsi
0x14000a4e1  call    EfspAquirePFileStream
0x14000a4e6  mov     ebx, eax
0x14000a4e8  test    eax, eax
0x14000a4ea  js      loc_14000A731
0x14000a4f0  mov     r12, [rbp+3Fh+Src]
0x14000a4f4  mov     r13d, [r12+0Eh]
0x14000a4f9  mov     ecx, [r12+r13+32h]
0x14000a4fe  mov     edx, [r12+r13+36h]
0x14000a503  add     edx, ecx
0x14000a505  cmp     edx, ecx
0x14000a507  jb      loc_14000A72C
0x14000a50d  cmp     edx, r14d
0x14000a510  jbe     short loc_14000A530
0x14000a512  mov     r8d, 170Fh
0x14000a518  mov     r9d, 0C0000022h
0x14000a51e  mov     edx, 6
0x14000a523  mov     ebx, r9d
0x14000a526  call    EfspTraceLogAssert
0x14000a52b  jmp     loc_14000A731
0x14000a530  mov     eax, dword ptr [rbp+3Fh+var_88+8]
0x14000a533  lea     r8, [rbp+3Fh+var_B8]
0x14000a537  mov     r9d, dword ptr [rsp+100h+Size]
0x14000a53c  sub     r9, rax
0x14000a53f  mov     ecx, edx
0x14000a541  mov     rdx, r9
0x14000a544  mov     [rbp+3Fh+Src], r9
0x14000a548  call    RtlLongLongAdd
0x14000a54d  mov     ebx, eax
0x14000a54f  test    eax, eax
0x14000a551  js      loc_14000A731
0x14000a557  mov     rcx, [rbp+3Fh+var_B8]
0x14000a55b  lea     r8, [rbp+3Fh+var_B8]
0x14000a55f  mov     edx, 20h ; ' '
0x14000a564  call    RtlLongLongAdd
0x14000a569  mov     ebx, eax
0x14000a56b  test    eax, eax
0x14000a56d  js      loc_14000A731
0x14000a573  mov     r15, [rbp+3Fh+var_B8]
0x14000a577  mov     eax, 0FFFFFFFFh
0x14000a57c  cmp     r15, rax
0x14000a57f  ja      loc_14000A72C
0x14000a585  cmp     r15d, 20h ; ' '
0x14000a589  jnb     short loc_14000A593
0x14000a58b  mov     r8d, 1733h
0x14000a591  jmp     short loc_14000A518
0x14000a593  mov     edx, r15d
0x14000a596  mov     ecx, 100h
0x14000a59b  mov     r8d, 6D736645h
0x14000a5a1  call    cs:__imp_ExAllocatePool2
0x14000a5a8  nop     dword ptr [rax+rax+00h]
0x14000a5ad  mov     rdi, rax
0x14000a5b0  test    rax, rax
0x14000a5b3  jnz     short loc_14000A5BF
0x14000a5b5  mov     ebx, 0C000009Ah
0x14000a5ba  jmp     loc_14000A731
0x14000a5bf  movups  xmm0, xmmword ptr [rsi]
0x14000a5c2  lea     rdx, [rbp+3Fh+var_90]
0x14000a5c6  mov     rcx, rdi
0x14000a5c9  movups  xmmword ptr [rax], xmm0
0x14000a5cc  movups  xmm1, xmmword ptr [rsi+10h]
0x14000a5d0  movups  xmmword ptr [rax+10h], xmm1
0x14000a5d4  mov     [rax], r15d
0x14000a5d7  call    EfspAquirePFileStream
0x14000a5dc  mov     ebx, eax
0x14000a5de  test    eax, eax
0x14000a5e0  js      loc_14000A731
0x14000a5e6  mov     r8d, [r12+0Eh]
0x14000a5eb  mov     rdx, r12; Src
0x14000a5ee  mov     rsi, [rbp+3Fh+var_90]
0x14000a5f2  add     r8, 12h; Size
0x14000a5f6  mov     rcx, rsi; void *
0x14000a5f9  call    memmove
0x14000a5fe  movups  xmm0, xmmword ptr [r12+r13+12h]
0x14000a604  mov     r14d, [rsi+0Eh]
0x14000a608  lea     r8, [rbp+3Fh+var_A0]
0x14000a60c  mov     rdx, [rbp+3Fh+Src]
0x14000a610  movups  xmmword ptr [r14+rsi+12h], xmm0
0x14000a616  movups  xmm1, xmmword ptr [r12+r13+22h]
0x14000a61c  movups  xmmword ptr [r14+rsi+22h], xmm1
0x14000a622  movsd   xmm0, qword ptr [r12+r13+32h]
0x14000a629  movsd   qword ptr [r14+rsi+32h], xmm0
0x14000a630  mov     eax, dword ptr [rsp+100h+Size]
0x14000a634  mov     [r14+rsi+22h], eax
0x14000a639  lea     eax, [r15-20h]
0x14000a63d  mov     [r14+rsi+26h], eax
0x14000a642  mov     qword ptr [r14+rsi+2Ah], 0
0x14000a64b  mov     ecx, [r12+r13+32h]
0x14000a650  call    RtlLongLongAdd
0x14000a655  mov     ebx, eax
0x14000a657  test    eax, eax
0x14000a659  js      loc_14000A731
0x14000a65f  mov     eax, 0FFFFFFFFh
0x14000a664  cmp     [rbp+3Fh+var_A0], rax
0x14000a668  ja      loc_14000A727
0x14000a66e  mov     ecx, dword ptr [rbp+3Fh+var_A0]
0x14000a671  mov     [r14+rsi+32h], ecx
0x14000a676  add     rcx, rsi; void *
0x14000a679  mov     edx, [r12+r13+32h]
0x14000a67e  mov     r8d, [r14+rsi+36h]; Size
0x14000a683  add     rdx, r12; Src
0x14000a686  call    memmove
0x14000a68b  lea     rcx, [rbp+3Fh+Uuid]; Uuid
0x14000a68f  call    cs:__imp_ExUuidCreate
0x14000a696  nop     dword ptr [rax+rax+00h]
0x14000a69b  mov     ebx, eax
0x14000a69d  test    eax, eax
0x14000a69f  js      loc_14000A731
0x14000a6a5  movups  xmm0, xmmword ptr [rbp+3Fh+Uuid.Data1]
0x14000a6a9  xor     r9d, r9d
0x14000a6ac  mov     [rsp+100h+var_D8], 10h; int
0x14000a6b4  lea     rax, [rbp+3Fh+Uuid]
0x14000a6b8  mov     rcx, rsi; Src
0x14000a6bb  movdqu  xmmword ptr [rdi+10h], xmm0
0x14000a6c0  mov     edx, [r14+rsi+26h]; Size
0x14000a6c5  lea     r8d, [r9+4]
0x14000a6c9  mov     [rsp+100h+var_E0], rax; __int64
0x14000a6ce  call    EfspGetSetPFileInfo
0x14000a6d3  mov     ebx, eax
0x14000a6d5  test    eax, eax
0x14000a6d7  js      short loc_14000A731
0x14000a6d9  mov     ecx, [r14+rsi+1Eh]
0x14000a6de  mov     r8d, dword ptr [rsp+100h+Size]; Size
0x14000a6e3  add     rcx, rsi; void *
0x14000a6e6  mov     rdx, [rbp+3Fh+var_98]; Src
0x14000a6ea  call    memmove
0x14000a6ef  mov     rdx, [rbp+3Fh+var_78]
0x14000a6f3  test    rdx, rdx
0x14000a6f6  jz      short loc_14000A715
0x14000a6f8  mov     rcx, [rbp+3Fh+var_70]
0x14000a6fc  test    rcx, rcx
0x14000a6ff  jz      short loc_14000A715
0x14000a701  mov     rax, [rbp+3Fh+var_B0]
0x14000a705  mov     [rdx], rax
0x14000a708  mov     eax, dword ptr [rbp+3Fh+Size+4]
0x14000a70b  mov     [rcx], eax
0x14000a70d  mov     [rbp+3Fh+var_B0], 0
0x14000a715  mov     rax, [rbp+3Fh+var_68]
0x14000a719  mov     [rax], rdi
0x14000a71c  xor     edi, edi
0x14000a71e  mov     rax, [rbp+3Fh+var_60]
0x14000a722  mov     [rax], r15d
0x14000a725  jmp     short loc_14000A731
0x14000a727  mov     [r14+rsi+32h], eax
0x14000a72c  mov     ebx, 0C0000095h
0x14000a731  mov     rcx, [rbp+3Fh+var_B0]
0x14000a735  test    rcx, rcx
0x14000a738  jz      short loc_14000A73F
0x14000a73a  call    EfspClipSpFree
0x14000a73f  mov     rcx, [rbp+3Fh+var_98]
0x14000a743  test    rcx, rcx
0x14000a746  jz      short loc_14000A74D
0x14000a748  call    EfspClipSpFree
0x14000a74d  test    rdi, rdi
0x14000a750  jz      short loc_14000A763
0x14000a752  xor     edx, edx; Tag
0x14000a754  mov     rcx, rdi; P
0x14000a757  call    cs:__imp_ExFreePoolWithTag
0x14000a75e  nop     dword ptr [rax+rax+00h]
0x14000a763  mov     eax, ebx
0x14000a765  mov     rcx, [rbp+3Fh+var_48]
0x14000a769  xor     rcx, rsp; StackCookie
0x14000a76c  call    __security_check_cookie
0x14000a771  add     rsp, 0C8h
0x14000a778  pop     r15
0x14000a77a  pop     r14
0x14000a77c  pop     r13
0x14000a77e  pop     r12
0x14000a780  pop     rdi
0x14000a781  pop     rsi
0x14000a782  pop     rbx
0x14000a783  pop     rbp
0x14000a784  retn
```
