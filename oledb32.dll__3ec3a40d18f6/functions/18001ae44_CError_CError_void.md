# CError::~CError(void)

- ea: `0x18001ae44`
- end: `0x18001b02b`
- name: `??1CError@@QEAA@XZ`
- size: `487`
- prototype: `void __fastcall(CError *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18007b0d0`

## callees

- `0x180011bcc`
- `0x18001ae44`
- `0x18001b034`
- `0x180028320`
- `0x18002ec26`
- `0x18007b0f8`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18001aea0`
- `MSDART!UMSEnterCSWraper` at `0x18001aea0`
- `MSDART!MPDeleteCriticalSection` at `0x18001b000`
- `MSDART!MPDeleteCriticalSection` at `0x18001b000`
- `KERNEL32!LeaveCriticalSection` at `0x18001aeed`
- `KERNEL32!LeaveCriticalSection` at `0x18001aeed`

## pseudocode

```c
void __fastcall CError::~CError(CError *this)
{
  unsigned int v2; // edx
  __int64 v3; // rcx
  __int64 v4; // rcx
  struct CCriticalSection *v5; // rcx
  unsigned int i; // edi
  __int64 v7; // rsi
  _QWORD *v8; // rcx
  CImpIErrorInfo *v9; // rcx
  CExtBuffer *v10; // rcx
  struct CCriticalSection *v11; // [rsp+20h] [rbp-59h] BYREF
  __int64 v12; // [rsp+30h] [rbp-49h] BYREF
  __int64 v13; // [rsp+38h] [rbp-41h]
  unsigned int v14; // [rsp+40h] [rbp-39h]
  struct tagDISPPARAMS v15; // [rsp+78h] [rbp-1h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+27h]

  *(_QWORD *)this = &CError::`vftable';
  memset_0(&v12, 0, 0x78u);
  if ( *((_BYTE *)this + 88) )
  {
    v11 = g_csErrorCollection;
    UMSEnterCSWraper(&v11);
    v3 = *((_QWORD *)this + 9);
    if ( v3 )
      *(_QWORD *)(v3 + 80) = *((_QWORD *)this + 10);
    else
      g_pErrorCollectionListHeader = (struct CError *)*((_QWORD *)this + 10);
    v4 = *((_QWORD *)this + 10);
    if ( v4 )
      *(_QWORD *)(v4 + 72) = *((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = 0;
    *((_QWORD *)this + 10) = 0;
    *((_BYTE *)this + 88) = 0;
    v5 = v11;
    if ( v11 )
    {
      --*((_DWORD *)v11 + 12);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 8));
    }
  }
  _InterlockedDecrement(&g_cObj);
  if ( *((_QWORD *)this + 6) )
  {
    for ( i = 1; i <= *((_DWORD *)this + 10); ++i )
    {
      memcpy_0(
        &v12,
        (const void *)(*(_QWORD *)(*((_QWORD *)this + 6) + 32LL)
                     + **((_QWORD **)this + 6)
                     * (i & (unsigned __int64)-(__int64)((unsigned __int64)i < *(_QWORD *)(*((_QWORD *)this + 6) + 8LL)))),
        **((_QWORD **)this + 6));
      ClearDispParams(&v15);
      if ( !g_fProcessDetaching )
      {
        if ( v12 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          v12 = 0;
        }
        if ( v13 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          v13 = 0;
        }
        v7 = v16;
        if ( v16 )
        {
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v16 + 40LL))(v16, v14);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          v14 = 0;
          v16 = 0;
        }
      }
    }
  }
  v8 = (_QWORD *)*((_QWORD *)this + 3);
  if ( v8 )
  {
    *v8 = &CImpIErrorRecords::`vftable';
    operator delete(v8);
  }
  *((_QWORD *)this + 3) = 0;
  v9 = (CImpIErrorInfo *)*((_QWORD *)this + 4);
  if ( v9 )
    CImpIErrorInfo::`scalar deleting destructor'(v9, v2);
  *((_QWORD *)this + 4) = 0;
  v10 = (CExtBuffer *)*((_QWORD *)this + 6);
  if ( v10 )
    CExtBuffer::`scalar deleting destructor'(v10, v2);
  *((_QWORD *)this + 6) = 0;
  if ( *((_QWORD *)this + 7) )
    MPDeleteCriticalSection((char *)this + 56);
}

```

## disassembly

```asm
0x18001ae44  mov     [rsp-8+arg_8], rbx
0x18001ae49  mov     [rsp-8+arg_10], rsi
0x18001ae4e  push    rbp
0x18001ae4f  push    rdi
0x18001ae50  push    r14
0x18001ae52  lea     rbp, [rsp-47h]
0x18001ae57  sub     rsp, 0C0h
0x18001ae5e  mov     rax, cs:__security_cookie
0x18001ae65  xor     rax, rsp
0x18001ae68  mov     [rbp+57h+var_20], rax
0x18001ae6c  mov     rbx, rcx
0x18001ae6f  lea     rax, ??_7CError@@6B@; const CError::`vftable'
0x18001ae76  mov     [rcx], rax
0x18001ae79  xor     edx, edx; Val
0x18001ae7b  lea     r8d, [rdx+78h]; Size
0x18001ae7f  lea     rcx, [rbp+57h+var_A0]; void *
0x18001ae83  call    memset_0
0x18001ae88  xor     r14d, r14d
0x18001ae8b  cmp     [rbx+58h], r14b
0x18001ae8f  jz      short loc_18001AEF3
0x18001ae91  mov     rax, cs:?g_csErrorCollection@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csErrorCollection
0x18001ae98  mov     [rbp+57h+var_B0], rax
0x18001ae9c  lea     rcx, [rbp+57h+var_B0]
0x18001aea0  call    cs:__imp_UMSEnterCSWraper
0x18001aea6  mov     rcx, [rbx+48h]
0x18001aeaa  mov     rax, [rbx+50h]
0x18001aeae  test    rcx, rcx
0x18001aeb1  jz      short loc_18001AEB9
0x18001aeb3  mov     [rcx+50h], rax
0x18001aeb7  jmp     short loc_18001AEC0
0x18001aeb9  mov     cs:?g_pErrorCollectionListHeader@@3REAVCError@@EA, rax; CError * g_pErrorCollectionListHeader
0x18001aec0  mov     rcx, [rbx+50h]
0x18001aec4  test    rcx, rcx
0x18001aec7  jz      short loc_18001AED1
0x18001aec9  mov     rax, [rbx+48h]
0x18001aecd  mov     [rcx+48h], rax
0x18001aed1  mov     [rbx+48h], r14
0x18001aed5  mov     [rbx+50h], r14
0x18001aed9  mov     [rbx+58h], r14b
0x18001aedd  mov     rcx, [rbp+57h+var_B0]
0x18001aee1  test    rcx, rcx
0x18001aee4  jz      short loc_18001AEF3
0x18001aee6  dec     dword ptr [rcx+30h]
0x18001aee9  add     rcx, 8; lpCriticalSection
0x18001aeed  call    cs:__imp_LeaveCriticalSection
0x18001aef3  lock dec cs:?g_cObj@@3JA; long g_cObj
0x18001aefa  cmp     [rbx+30h], r14
0x18001aefe  jz      loc_18001AFB7
0x18001af04  mov     edi, 1
0x18001af09  cmp     [rbx+28h], edi
0x18001af0c  jb      loc_18001AFB7
0x18001af12  mov     r8, [rbx+30h]
0x18001af16  mov     eax, edi
0x18001af18  cmp     rax, [r8+8]
0x18001af1c  sbb     rdx, rdx
0x18001af1f  and     rdx, rax
0x18001af22  imul    rdx, [r8]
0x18001af26  add     rdx, [r8+20h]; Src
0x18001af2a  mov     r8, [r8]; Size
0x18001af2d  lea     rcx, [rbp+57h+var_A0]; void *
0x18001af31  call    memcpy_0
0x18001af36  lea     rcx, [rbp+57h+var_58]; struct tagDISPPARAMS *
0x18001af3a  call    ?ClearDispParams@@YAXPEAUtagDISPPARAMS@@@Z; ClearDispParams(tagDISPPARAMS *)
0x18001af3f  cmp     cs:?g_fProcessDetaching@@3HA, r14d; int g_fProcessDetaching
0x18001af46  jnz     short loc_18001AFAC
0x18001af48  mov     rcx, [rbp+57h+var_A0]
0x18001af4c  test    rcx, rcx
0x18001af4f  jz      short loc_18001AF61
0x18001af51  mov     rax, [rcx]
0x18001af54  mov     rax, [rax+10h]
0x18001af58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af5d  mov     [rbp+57h+var_A0], r14
0x18001af61  mov     rcx, [rbp+57h+var_98]
0x18001af65  test    rcx, rcx
0x18001af68  jz      short loc_18001AF7A
0x18001af6a  mov     rax, [rcx]
0x18001af6d  mov     rax, [rax+10h]
0x18001af71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af76  mov     [rbp+57h+var_98], r14
0x18001af7a  mov     rsi, [rbp+57h+var_30]
0x18001af7e  test    rsi, rsi
0x18001af81  jz      short loc_18001AFAC
0x18001af83  mov     rax, [rsi]
0x18001af86  mov     edx, [rbp+57h+var_90]
0x18001af89  mov     rcx, rsi
0x18001af8c  mov     rax, [rax+28h]
0x18001af90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af95  mov     rax, [rsi]
0x18001af98  mov     rcx, rsi
0x18001af9b  mov     rax, [rax+10h]
0x18001af9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001afa4  mov     [rbp+57h+var_90], r14d
0x18001afa8  mov     [rbp+57h+var_30], r14
0x18001afac  inc     edi
0x18001afae  cmp     edi, [rbx+28h]
0x18001afb1  jbe     loc_18001AF12
0x18001afb7  mov     rcx, [rbx+18h]; void *
0x18001afbb  test    rcx, rcx
0x18001afbe  jz      short loc_18001AFCF
0x18001afc0  lea     rax, ??_7CImpIErrorRecords@@6B@; const CImpIErrorRecords::`vftable'
0x18001afc7  mov     [rcx], rax
0x18001afca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001afcf  mov     [rbx+18h], r14
0x18001afd3  mov     rcx, [rbx+20h]; this
0x18001afd7  test    rcx, rcx
0x18001afda  jz      short loc_18001AFE1
0x18001afdc  call    ??_GCImpIErrorInfo@@QEAAPEAXI@Z; CImpIErrorInfo::`scalar deleting destructor'(uint)
0x18001afe1  mov     [rbx+20h], r14
0x18001afe5  mov     rcx, [rbx+30h]; this
0x18001afe9  test    rcx, rcx
0x18001afec  jz      short loc_18001AFF3
0x18001afee  call    ??_GCExtBuffer@@QEAAPEAXI@Z; CExtBuffer::`scalar deleting destructor'(uint)
0x18001aff3  mov     [rbx+30h], r14
0x18001aff7  lea     rcx, [rbx+38h]
0x18001affb  cmp     [rcx], r14
0x18001affe  jz      short loc_18001B007
0x18001b000  call    cs:__imp_MPDeleteCriticalSection
0x18001b006  nop
0x18001b007  mov     rcx, [rbp+57h+var_20]
0x18001b00b  xor     rcx, rsp; StackCookie
0x18001b00e  call    __security_check_cookie
0x18001b013  lea     r11, [rsp+0D0h+var_10]
0x18001b01b  mov     rbx, [r11+28h]
0x18001b01f  mov     rsi, [r11+30h]
0x18001b023  mov     rsp, r11
0x18001b026  pop     r14
0x18001b028  pop     rdi
0x18001b029  pop     rbp
0x18001b02a  retn
```
