# CInSeqHash::Save(void *)

- ea: `0x180068ab0`
- end: `0x180068dcb`
- name: `?Save@CInSeqHash@@AEAAHPEAX@Z`
- size: `795`
- prototype: `int(CInSeqHash *__hidden this, void *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180068f60`

## callees

- `0x18000d1f0`
- `0x18000f35c`
- `0x18000f430`
- `0x18000fa28`
- `0x180064168`
- `0x1800650ac`
- `0x180066954`
- `0x180068ab0`
- `0x180068dd4`
- `0x18006910c`
- `0x180069184`
- `0x18006a630`
- `0x18009b51c`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180068d8f`
- `KERNEL32!GetLastError` at `0x180068d8f`
- `KERNEL32!WriteFile` at `0x180068c51`
- `KERNEL32!WriteFile` at `0x180068c8b`
- `KERNEL32!WriteFile` at `0x180068d08`
- `KERNEL32!WriteFile` at `0x180068c51`
- `KERNEL32!WriteFile` at `0x180068c8b`
- `KERNEL32!WriteFile` at `0x180068d08`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CInSeqHash::Save(CInSeqHash *this, void *a2)
{
  unsigned int v4; // r15d
  DWORD *v5; // rdi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rbx
  int v9; // eax
  __int64 v10; // rcx
  PVOID *v11; // rcx
  DWORD LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-49h] BYREF
  char *v15; // [rsp+38h] [rbp-41h] BYREF
  __int64 v16; // [rsp+40h] [rbp-39h] BYREF
  __int64 i; // [rsp+48h] [rbp-31h] BYREF
  __int128 v18; // [rsp+50h] [rbp-29h] BYREF
  _OWORD v19[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v20; // [rsp+80h] [rbp+7h]
  __int128 v21; // [rsp+88h] [rbp+Fh] BYREF
  int v22; // [rsp+98h] [rbp+1Fh]

  v15 = (char *)this + 8;
  CReadWriteLock::LockRead((CInSeqHash *)((char *)this + 8));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 428) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 52), 37, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids);
  v4 = 0;
  NumberOfBytesWritten = 0;
  v22 = 2;
  v21 = xmmword_180103898;
  v5 = (DWORD *)((char *)this + 2776);
  CResizeBuffer<unsigned char>::append((char *)this + 2776, &v21, 20);
  LODWORD(v16) = *((_DWORD *)this + 13);
  CResizeBuffer<unsigned char>::append((char *)this + 2776, &v16, 4);
  v6 = -(__int64)(*((_DWORD *)this + 13) != 0);
  for ( i = v6; ; v6 = i )
  {
    if ( !v6 )
    {
      if ( !WriteFile(a2, *((LPCVOID *)this + 349), *v5, &NumberOfBytesWritten, 0) )
        goto LABEL_33;
      if ( *v5 != NumberOfBytesWritten )
        goto LABEL_33;
      *(_QWORD *)v5 = 0;
      if ( !WriteFile(a2, (char *)this + 80, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
        goto LABEL_33;
      if ( *((_DWORD *)this + 21) != 4660
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          38,
          &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids,
          *((unsigned int *)this + 21));
      }
      if ( !WriteFile(a2, (char *)this + 84, 4u, &NumberOfBytesWritten, 0) || NumberOfBytesWritten != 4 )
      {
LABEL_33:
        LastError = GetLastError();
        ReportWriteFailure(LastError);
        goto LABEL_34;
      }
      if ( *((_DWORD *)this + 21) != 4660 )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        {
LABEL_32:
          CSR::~CSR((CSR *)&v15);
          return 1;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 348) & 1) == 0 )
        {
LABEL_29:
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 428) & 4) != 0 )
            WPP_SF_d(v11[52], 40, &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids, v4);
          goto LABEL_32;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 42),
          39,
          &WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids,
          *((unsigned int *)this + 21));
      }
      v11 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_29;
    }
    memset(v19, 0, sizeof(v19));
    v20 = 0;
    v18 = 0;
    LOWORD(v19[0]) = 0;
    v16 = 0;
    CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc((char *)this + 32, &i, &v18, &v16);
    if ( v20 )
    {
      v7 = CKeyInSeq::SaveSrmp(&v18, (char *)this + 2776);
    }
    else
    {
      CResizeBuffer<unsigned char>::append((char *)this + 2776, &v18, 16);
      v7 = SaveQueueFormat(v19, (char *)this + 2776);
    }
    if ( !v7 )
      break;
    v8 = v16;
    v9 = CInSequence::Save(v16, (char *)this + 2776);
    v10 = v8;
    if ( !v9 )
      goto LABEL_12;
    ++v4;
    SafeRelease<CSockTransport>(v8);
    CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v18);
  }
  v10 = v16;
LABEL_12:
  SafeRelease<CSockTransport>(v10);
  CKeyInSeq::~CKeyInSeq((CKeyInSeq *)&v18);
LABEL_34:
  CSR::~CSR((CSR *)&v15);
  return 0;
}

```

## disassembly

```asm
0x180068ab0  mov     [rsp-8+arg_10], rbx
0x180068ab5  push    rbp
0x180068ab6  push    rsi
0x180068ab7  push    rdi
0x180068ab8  push    r14
0x180068aba  push    r15
0x180068abc  lea     rbp, [rsp-37h]
0x180068ac1  sub     rsp, 0B0h
0x180068ac8  mov     rax, cs:__security_cookie
0x180068acf  xor     rax, rsp
0x180068ad2  mov     [rbp+57h+var_30], rax
0x180068ad6  mov     r14, rdx
0x180068ad9  mov     rsi, rcx
0x180068adc  add     rcx, 8; this
0x180068ae0  mov     [rbp+57h+var_98], rcx
0x180068ae4  call    ?LockRead@CReadWriteLock@@QEAAXXZ; CReadWriteLock::LockRead(void)
0x180068ae9  nop
0x180068aea  lea     rbx, WPP_GLOBAL_Control
0x180068af1  mov     rcx, cs:WPP_GLOBAL_Control
0x180068af8  cmp     rcx, rbx
0x180068afb  jz      short loc_180068B1E
0x180068afd  test    byte ptr [rcx+1ACh], 4
0x180068b04  jz      short loc_180068B1E
0x180068b06  mov     edx, 25h ; '%'
0x180068b0b  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180068b12  mov     rcx, [rcx+1A0h]
0x180068b19  call    WPP_SF_
0x180068b1e  xor     r15d, r15d
0x180068b21  mov     [rbp+57h+NumberOfBytesWritten], r15d
0x180068b25  mov     [rbp+57h+var_38], 2
0x180068b2c  movups  xmm0, cs:xmmword_180103898
0x180068b33  movdqu  [rbp+57h+var_48], xmm0
0x180068b38  lea     rdi, [rsi+0AD8h]
0x180068b3f  lea     r8d, [r15+14h]
0x180068b43  lea     rdx, [rbp+57h+var_48]
0x180068b47  mov     rcx, rdi
0x180068b4a  call    ?append@?$CResizeBuffer@E@@QEAAXPEBE_K@Z; CResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x180068b4f  mov     eax, [rsi+34h]
0x180068b52  mov     dword ptr [rbp+57h+var_90], eax
0x180068b55  lea     r8d, [r15+4]
0x180068b59  lea     rdx, [rbp+57h+var_90]
0x180068b5d  mov     rcx, rdi
0x180068b60  call    ?append@?$CResizeBuffer@E@@QEAAXPEBE_K@Z; CResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x180068b65  mov     eax, [rsi+34h]
0x180068b68  neg     eax
0x180068b6a  sbb     rcx, rcx
0x180068b6d  mov     [rbp+57h+var_88], rcx
0x180068b71  test    rcx, rcx
0x180068b74  jz      loc_180068C37
0x180068b7a  xorps   xmm0, xmm0
0x180068b7d  movups  [rbp+57h+var_70], xmm0
0x180068b81  movups  [rbp+57h+var_60], xmm0
0x180068b85  mov     [rbp+57h+var_50], 0
0x180068b8d  movups  [rbp+57h+var_80], xmm0
0x180068b91  mov     word ptr [rbp+57h+var_70], 0
0x180068b97  mov     [rbp+57h+var_90], 0
0x180068b9f  lea     rcx, [rsi+20h]
0x180068ba3  lea     r9, [rbp+57h+var_90]
0x180068ba7  lea     r8, [rbp+57h+var_80]
0x180068bab  lea     rdx, [rbp+57h+var_88]
0x180068baf  call    ?GetNextAssoc@?$CMap@VCKeyInSeq@@AEAV1@V?$R@VCInSequence@@@@AEAV2@@@QEBAXAEAPEAU__POSITION@@AEAVCKeyInSeq@@AEAV?$R@VCInSequence@@@@@Z; CMap<CKeyInSeq,CKeyInSeq &,R<CInSequence>,R<CInSequence> &>::GetNextAssoc(__POSITION * &,CKeyInSeq &,R<CInSequence> &)
0x180068bb4  cmp     [rbp+57h+var_50], 0
0x180068bb9  jz      short loc_180068BC9
0x180068bbb  mov     rdx, rdi
0x180068bbe  lea     rcx, [rbp+57h+var_80]
0x180068bc2  call    ?SaveSrmp@CKeyInSeq@@AEAAHAEAV?$CResizeBuffer@E@@@Z; CKeyInSeq::SaveSrmp(CResizeBuffer<uchar> &)
0x180068bc7  jmp     short loc_180068BE7
0x180068bc9  mov     r8d, 10h
0x180068bcf  lea     rdx, [rbp+57h+var_80]
0x180068bd3  mov     rcx, rdi
0x180068bd6  call    ?append@?$CResizeBuffer@E@@QEAAXPEBE_K@Z; CResizeBuffer<uchar>::append(uchar const *,unsigned __int64)
0x180068bdb  mov     rdx, rdi
0x180068bde  lea     rcx, [rbp+57h+var_70]
0x180068be2  call    SaveQueueFormat
0x180068be7  test    eax, eax
0x180068be9  jz      short loc_180068C31
0x180068beb  mov     rdx, rdi
0x180068bee  mov     rbx, [rbp+57h+var_90]
0x180068bf2  mov     rcx, rbx
0x180068bf5  call    ?Save@CInSequence@@QEAAHAEAV?$CResizeBuffer@E@@@Z; CInSequence::Save(CResizeBuffer<uchar> &)
0x180068bfa  nop
0x180068bfb  mov     rcx, rbx
0x180068bfe  test    eax, eax
0x180068c00  jz      short loc_180068C1D
0x180068c02  inc     r15d
0x180068c05  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180068c0a  nop
0x180068c0b  lea     rcx, [rbp+57h+var_80]; this
0x180068c0f  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x180068c14  mov     rcx, [rbp+57h+var_88]
0x180068c18  jmp     loc_180068B71
0x180068c1d  call    ??$SafeRelease@VCSockTransport@@@@YAXPEAVCSockTransport@@@Z; SafeRelease<CSockTransport>(CSockTransport *)
0x180068c22  nop
0x180068c23  lea     rcx, [rbp+57h+var_80]; this
0x180068c27  call    ??1CKeyInSeq@@QEAA@XZ; CKeyInSeq::~CKeyInSeq(void)
0x180068c2c  jmp     loc_180068D9D
0x180068c31  mov     rcx, [rbp+57h+var_90]
0x180068c35  jmp     short loc_180068C1D
0x180068c37  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x180068c40  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180068c44  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180068c47  mov     rdx, [rsi+0AE8h]; lpBuffer
0x180068c4e  mov     rcx, r14; hFile
0x180068c51  call    cs:__imp_WriteFile
0x180068c57  test    eax, eax
0x180068c59  jz      loc_180068D8F
0x180068c5f  mov     eax, [rbp+57h+NumberOfBytesWritten]
0x180068c62  cmp     [rdi], eax
0x180068c64  jnz     loc_180068D8F
0x180068c6a  mov     qword ptr [rdi], 0
0x180068c71  lea     rdx, [rsi+50h]; lpBuffer
0x180068c75  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x180068c7e  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180068c82  mov     r8d, 4; nNumberOfBytesToWrite
0x180068c88  mov     rcx, r14; hFile
0x180068c8b  call    cs:__imp_WriteFile
0x180068c91  test    eax, eax
0x180068c93  jz      loc_180068D8F
0x180068c99  cmp     [rbp+57h+NumberOfBytesWritten], 4
0x180068c9d  jnz     loc_180068D8F
0x180068ca3  mov     edi, 1234h
0x180068ca8  cmp     [rsi+54h], edi
0x180068cab  jz      short loc_180068CE7
0x180068cad  mov     rcx, cs:WPP_GLOBAL_Control
0x180068cb4  lea     rbx, WPP_GLOBAL_Control
0x180068cbb  cmp     rcx, rbx
0x180068cbe  jz      short loc_180068CEE
0x180068cc0  test    byte ptr [rcx+15Ch], 1
0x180068cc7  jz      short loc_180068CEE
0x180068cc9  mov     edx, 26h ; '&'
0x180068cce  mov     r9d, [rsi+54h]
0x180068cd2  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180068cd9  mov     rcx, [rcx+150h]
0x180068ce0  call    WPP_SF_d
0x180068ce5  jmp     short loc_180068CEE
0x180068ce7  lea     rbx, WPP_GLOBAL_Control
0x180068cee  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x180068cf7  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180068cfb  mov     r8d, 4; nNumberOfBytesToWrite
0x180068d01  lea     rdx, [rsi+54h]; lpBuffer
0x180068d05  mov     rcx, r14; hFile
0x180068d08  call    cs:__imp_WriteFile
0x180068d0e  test    eax, eax
0x180068d10  jz      short loc_180068D8F
0x180068d12  cmp     [rbp+57h+NumberOfBytesWritten], 4
0x180068d16  jnz     short loc_180068D8F
0x180068d18  cmp     [rsi+54h], edi
0x180068d1b  jz      short loc_180068D4E
0x180068d1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068d24  cmp     rcx, rbx
0x180068d27  jz      short loc_180068D7F
0x180068d29  test    byte ptr [rcx+15Ch], 1
0x180068d30  jz      short loc_180068D55
0x180068d32  mov     edx, 27h ; '''
0x180068d37  mov     r9d, [rsi+54h]
0x180068d3b  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180068d42  mov     rcx, [rcx+150h]
0x180068d49  call    WPP_SF_d
0x180068d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180068d55  cmp     rcx, rbx
0x180068d58  jz      short loc_180068D7F
0x180068d5a  test    byte ptr [rcx+1ACh], 4
0x180068d61  jz      short loc_180068D7F
0x180068d63  mov     edx, 28h ; '('
0x180068d68  mov     r9d, r15d
0x180068d6b  lea     r8, WPP_d47abf12d2c63181d11479d5f9b3f4aa_Traceguids
0x180068d72  mov     rcx, [rcx+1A0h]
0x180068d79  call    WPP_SF_d
0x180068d7e  nop
0x180068d7f  lea     rcx, [rbp+57h+var_98]; this
0x180068d83  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x180068d88  mov     eax, 1
0x180068d8d  jmp     short loc_180068DA8
0x180068d8f  call    cs:__imp_GetLastError
0x180068d95  mov     ecx, eax; unsigned int
0x180068d97  call    ?ReportWriteFailure@@YAXK@Z; ReportWriteFailure(ulong)
0x180068d9c  nop
0x180068d9d  lea     rcx, [rbp+57h+var_98]; this
0x180068da1  call    ??1CSR@@QEAA@XZ; CSR::~CSR(void)
0x180068da6  xor     eax, eax
0x180068da8  mov     rcx, [rbp+57h+var_30]
0x180068dac  xor     rcx, rsp; StackCookie
0x180068daf  call    __security_check_cookie
0x180068db4  mov     rbx, [rsp+0D0h+arg_10]
0x180068dbc  add     rsp, 0B0h
0x180068dc3  pop     r15
0x180068dc5  pop     r14
0x180068dc7  pop     rdi
0x180068dc8  pop     rsi
0x180068dc9  pop     rbp
0x180068dca  retn
```
