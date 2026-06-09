# CFileStream::Move(ushort const *,ushort *)

- ea: `0x18005e59c`
- end: `0x18005e841`
- name: `?Move@CFileStream@@QEAAJPEBGPEAG@Z`
- size: `677`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, wchar_t *OldFileName, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005dc90`

## callees

- `0x180011530`
- `0x18001a820`
- `0x180053d40`
- `0x180056e84`
- `0x18005e59c`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cc16c`
- `0x1800cdb20`

## import_xrefs

- `msvcrt!_wrename` at `0x18005e7f1`
- `msvcrt!_wrename` at `0x18005e7f1`
- `MSDART!MpHeapAlloc` at `0x18005e661`
- `MSDART!MpHeapAlloc` at `0x18005e661`
- `ADVAPI32!SetFileSecurityW` at `0x18005e77c`
- `ADVAPI32!SetFileSecurityW` at `0x18005e77c`
- `ADVAPI32!GetFileSecurityW` at `0x18005e61f`
- `ADVAPI32!GetFileSecurityW` at `0x18005e68e`
- `ADVAPI32!GetFileSecurityW` at `0x18005e61f`
- `ADVAPI32!GetFileSecurityW` at `0x18005e68e`

## string_xrefs

- `0x18005e6e4`: `<CFileStream::Move|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18005e705`: `<CFileStream::Move|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileStream::Move(CFileStream *this, wchar_t *OldFileName, unsigned __int16 *a3)
{
  unsigned int v6; // edi
  DWORD v7; // esi
  _BYTE *v8; // r14
  BOOL FileSecurityW; // eax
  DWORD v10; // ecx
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // ebx
  LPDWORD lpnLengthNeeded; // [rsp+20h] [rbp-99h]
  int v18; // [rsp+28h] [rbp-91h]
  DWORD nLengthNeeded; // [rsp+30h] [rbp-89h] BYREF
  _BYTE v20[24]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE pSecurityDescriptor[128]; // [rsp+50h] [rbp-69h] BYREF

  CSysString::CSysString((CSysString *)v20, a3, 4u);
  if ( !CSysString::GetLength((CSysString *)v20, 0) )
  {
    v6 = -2147286781;
    goto LABEL_30;
  }
  nLengthNeeded = 0;
  v7 = 0;
  v8 = pSecurityDescriptor;
  FileSecurityW = GetFileSecurityW(a3, 4u, pSecurityDescriptor, 0x78u, &nLengthNeeded);
  v10 = nLengthNeeded;
  if ( nLengthNeeded > 0x78 )
  {
    while ( v7 < v10 )
    {
      if ( v7 )
      {
        operator delete(v8);
        v7 = 0;
        v10 = nLengthNeeded;
      }
      v8 = (_BYTE *)MpHeapAlloc(g_hHeapHandle, 10485760, v10);
      if ( !v8 )
      {
        v6 = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_28;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24));
          v18 = 175;
          LODWORD(lpnLengthNeeded) = -2147024882;
          v12 = 179209;
          goto LABEL_12;
        }
        LODWORD(lpnLengthNeeded) = 175;
        v13 = 2147942414LL;
        v14 = 179209;
        goto LABEL_14;
      }
      v7 = nLengthNeeded;
      FileSecurityW = GetFileSecurityW(a3, 4u, v8, nLengthNeeded, &nLengthNeeded);
      v10 = nLengthNeeded;
    }
  }
  if ( FileSecurityW )
  {
    if ( SetFileSecurityW(OldFileName, 4u, v8) )
    {
      v15 = 0;
      CFileStream::Delete(this, a3);
      if ( _wrename(OldFileName, a3) )
        v15 = -2147286781;
      v6 = v15;
      goto LABEL_28;
    }
    v6 = -2147024891;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24));
        v18 = 192;
        LODWORD(lpnLengthNeeded) = -2147024891;
        v12 = 196617;
        goto LABEL_12;
      }
      LODWORD(lpnLengthNeeded) = 192;
      v13 = 2147942405LL;
      v14 = 196617;
      goto LABEL_14;
    }
  }
  else
  {
    v6 = -2147024891;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CFileStream *)((char *)this + 24));
        v18 = 188;
        LODWORD(lpnLengthNeeded) = -2147024891;
        v12 = 192521;
LABEL_12:
        bidTraceW(
          off_18012A230[0],
          v12,
          L"<CFileStream::Move|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          lpnLengthNeeded,
          v18);
        goto LABEL_28;
      }
      LODWORD(lpnLengthNeeded) = 188;
      v13 = 2147942405LL;
      v14 = 192521;
LABEL_14:
      bidTraceW(off_18012A230[0], v14, L"<CFileStream::Move|ADO|ERR> 0x%08x{HRESULT} line %d\n", v13, lpnLengthNeeded);
    }
  }
LABEL_28:
  if ( v7 )
    operator delete(v8);
LABEL_30:
  CSysString::~CSysString((CSysString *)v20);
  return v6;
}

```

## disassembly

```asm
0x18005e59c  push    rbp
0x18005e59e  push    rbx
0x18005e59f  push    rsi
0x18005e5a0  push    rdi
0x18005e5a1  push    r12
0x18005e5a3  push    r14
0x18005e5a5  push    r15
0x18005e5a7  lea     rbp, [rsp-27h]
0x18005e5ac  sub     rsp, 0E0h
0x18005e5b3  mov     rax, cs:__security_cookie
0x18005e5ba  xor     rax, rsp
0x18005e5bd  mov     [rbp+57h+var_40], rax
0x18005e5c1  mov     rdi, r8
0x18005e5c4  mov     r12, rdx
0x18005e5c7  mov     r15, rcx
0x18005e5ca  mov     ebx, 4
0x18005e5cf  mov     r8b, bl; unsigned __int8
0x18005e5d2  mov     rdx, rdi; unsigned __int16 *
0x18005e5d5  lea     rcx, [rsp+110h+var_D8]; this
0x18005e5da  call    ??0CSysString@@QEAA@PEAGE@Z; CSysString::CSysString(ushort *,uchar)
0x18005e5df  nop
0x18005e5e0  xor     edx, edx; int
0x18005e5e2  lea     rcx, [rsp+110h+var_D8]; this
0x18005e5e7  call    ?GetLength@CSysString@@QEBAKH@Z; CSysString::GetLength(int)
0x18005e5ec  test    eax, eax
0x18005e5ee  jnz     short loc_18005E5FA
0x18005e5f0  mov     edi, 80030103h
0x18005e5f5  jmp     loc_18005E816
0x18005e5fa  mov     [rsp+110h+nLengthNeeded], 0
0x18005e602  xor     esi, esi
0x18005e604  lea     r14, [rbp+57h+pSecurityDescriptor]
0x18005e608  lea     rax, [rsp+110h+nLengthNeeded]
0x18005e60d  mov     [rsp+110h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18005e612  lea     r9d, [rsi+78h]; nLength
0x18005e616  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18005e61a  mov     edx, ebx; RequestedInformation
0x18005e61c  mov     rcx, rdi; lpFileName
0x18005e61f  call    cs:__imp_GetFileSecurityW
0x18005e626  nop     dword ptr [rax+rax+00h]
0x18005e62b  mov     ecx, [rsp+110h+nLengthNeeded]
0x18005e62f  cmp     ecx, 78h ; 'x'
0x18005e632  jbe     loc_18005E71D
0x18005e638  cmp     esi, ecx
0x18005e63a  jnb     loc_18005E71D
0x18005e640  test    esi, esi
0x18005e642  jz      short loc_18005E652
0x18005e644  mov     rcx, r14; void *
0x18005e647  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e64c  xor     esi, esi
0x18005e64e  mov     ecx, [rsp+110h+nLengthNeeded]
0x18005e652  mov     r8d, ecx
0x18005e655  mov     edx, 0A00000h
0x18005e65a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18005e661  call    cs:__imp_MpHeapAlloc
0x18005e668  nop     dword ptr [rax+rax+00h]
0x18005e66d  mov     r14, rax
0x18005e670  test    rax, rax
0x18005e673  jz      short loc_18005E6A0
0x18005e675  mov     esi, [rsp+110h+nLengthNeeded]
0x18005e679  lea     rax, [rsp+110h+nLengthNeeded]
0x18005e67e  mov     [rsp+110h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18005e683  mov     r9d, esi; nLength
0x18005e686  mov     r8, r14; pSecurityDescriptor
0x18005e689  mov     edx, ebx; RequestedInformation
0x18005e68b  mov     rcx, rdi; lpFileName
0x18005e68e  call    cs:__imp_GetFileSecurityW
0x18005e695  nop     dword ptr [rax+rax+00h]
0x18005e69a  mov     ecx, [rsp+110h+nLengthNeeded]
0x18005e69e  jmp     short loc_18005E638
0x18005e6a0  mov     edi, 8007000Eh
0x18005e6a5  test    byte ptr cs:_bidGblFlags, 2
0x18005e6ac  jz      loc_18005E809
0x18005e6b2  lea     rcx, [r15+18h]; this
0x18005e6b6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e6bb  cmp     eax, 0FFFFFFFFh
0x18005e6be  jz      short loc_18005E6F5
0x18005e6c0  lea     rcx, [r15+18h]; this
0x18005e6c4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e6c9  mov     [rsp+110h+var_E8], 0AFh
0x18005e6d1  mov     dword ptr [rsp+110h+lpnLengthNeeded], edi
0x18005e6d5  mov     edx, 2BC09h
0x18005e6da  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005e6e1  mov     r9d, eax
0x18005e6e4  lea     r8, aCfilestreamMov; "<CFileStream::Move|ADO|ERR> %u#,0x%08x{"...
0x18005e6eb  call    _bidTraceW
0x18005e6f0  jmp     loc_18005E809
0x18005e6f5  mov     dword ptr [rsp+110h+lpnLengthNeeded], 0AFh
0x18005e6fd  mov     r9d, edi
0x18005e700  mov     edx, 2BC09h
0x18005e705  lea     r8, aCfilestreamMov_0; "<CFileStream::Move|ADO|ERR> 0x%08x{HRES"...
0x18005e70c  mov     rcx, cs:off_18012A230; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005e713  call    _bidTraceW
0x18005e718  jmp     loc_18005E809
0x18005e71d  test    eax, eax
0x18005e71f  jnz     short loc_18005E774
0x18005e721  mov     ebx, 80070005h
0x18005e726  mov     edi, ebx
0x18005e728  test    byte ptr cs:_bidGblFlags, 2
0x18005e72f  jz      loc_18005E809
0x18005e735  lea     rcx, [r15+18h]; this
0x18005e739  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e73e  cmp     eax, 0FFFFFFFFh
0x18005e741  jz      short loc_18005E762
0x18005e743  lea     rcx, [r15+18h]; this
0x18005e747  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e74c  mov     [rsp+110h+var_E8], 0BCh
0x18005e754  mov     dword ptr [rsp+110h+lpnLengthNeeded], ebx
0x18005e758  mov     edx, 2F009h
0x18005e75d  jmp     loc_18005E6DA
0x18005e762  mov     dword ptr [rsp+110h+lpnLengthNeeded], 0BCh
0x18005e76a  mov     r9d, ebx
0x18005e76d  mov     edx, 2F009h
0x18005e772  jmp     short loc_18005E705
0x18005e774  mov     r8, r14; pSecurityDescriptor
0x18005e777  mov     edx, ebx; SecurityInformation
0x18005e779  mov     rcx, r12; lpFileName
0x18005e77c  call    cs:__imp_SetFileSecurityW
0x18005e783  nop     dword ptr [rax+rax+00h]
0x18005e788  test    eax, eax
0x18005e78a  jnz     short loc_18005E7DE
0x18005e78c  mov     ebx, 80070005h
0x18005e791  mov     edi, ebx
0x18005e793  test    byte ptr cs:_bidGblFlags, 2
0x18005e79a  jz      short loc_18005E809
0x18005e79c  lea     rcx, [r15+18h]; this
0x18005e7a0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e7a5  cmp     eax, 0FFFFFFFFh
0x18005e7a8  jz      short loc_18005E7C9
0x18005e7aa  lea     rcx, [r15+18h]; this
0x18005e7ae  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005e7b3  mov     [rsp+110h+var_E8], 0C0h
0x18005e7bb  mov     dword ptr [rsp+110h+lpnLengthNeeded], ebx
0x18005e7bf  mov     edx, 30009h
0x18005e7c4  jmp     loc_18005E6DA
0x18005e7c9  mov     dword ptr [rsp+110h+lpnLengthNeeded], 0C0h
0x18005e7d1  mov     r9d, ebx
0x18005e7d4  mov     edx, 30009h
0x18005e7d9  jmp     loc_18005E705
0x18005e7de  xor     ebx, ebx
0x18005e7e0  mov     rdx, rdi; unsigned __int16 *
0x18005e7e3  mov     rcx, r15; this
0x18005e7e6  call    ?Delete@CFileStream@@QEAAJPEBG@Z; CFileStream::Delete(ushort const *)
0x18005e7eb  mov     rdx, rdi; NewFileName
0x18005e7ee  mov     rcx, r12; OldFileName
0x18005e7f1  call    cs:__imp__wrename
0x18005e7f8  nop     dword ptr [rax+rax+00h]
0x18005e7fd  mov     edi, 80030103h
0x18005e802  test    eax, eax
0x18005e804  cmovnz  ebx, edi
0x18005e807  mov     edi, ebx
0x18005e809  test    esi, esi
0x18005e80b  jz      short loc_18005E816
0x18005e80d  mov     rcx, r14; void *
0x18005e810  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18005e815  nop
0x18005e816  lea     rcx, [rsp+110h+var_D8]; this
0x18005e81b  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x18005e820  mov     eax, edi
0x18005e822  mov     rcx, [rbp+57h+var_40]
0x18005e826  xor     rcx, rsp; StackCookie
0x18005e829  call    __security_check_cookie
0x18005e82e  add     rsp, 0E0h
0x18005e835  pop     r15
0x18005e837  pop     r14
0x18005e839  pop     r12
0x18005e83b  pop     rdi
0x18005e83c  pop     rsi
0x18005e83d  pop     rbx
0x18005e83e  pop     rbp
0x18005e83f  retn
```
