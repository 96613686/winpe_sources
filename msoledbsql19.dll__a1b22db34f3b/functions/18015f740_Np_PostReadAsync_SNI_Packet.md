# Np::PostReadAsync(SNI_Packet *)

- ea: `0x18015f740`
- end: `0x18015fbf6`
- name: `?PostReadAsync@Np@@AEAAKPEAVSNI_Packet@@@Z`
- size: `1206`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18015fc10`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003250`
- `0x180003d80`
- `0x18015a6f0`
- `0x18015a880`
- `0x18015f740`
- `0x18017f0e0`
- `0x18017f1b0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18015f848`
- `KERNEL32!GetLastError` at `0x18015f8e4`
- `KERNEL32!GetLastError` at `0x18015f848`
- `KERNEL32!GetLastError` at `0x18015f8e4`
- `KERNEL32!GetOverlappedResult` at `0x18015f8d6`
- `KERNEL32!GetOverlappedResult` at `0x18015f8d6`
- `KERNEL32!ReadFile` at `0x18015f83e`
- `KERNEL32!ReadFile` at `0x18015f83e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Np::PostReadAsync(Np *this, struct SNI_Packet *a2)
{
  void *v4; // rbx
  DWORD v5; // r14d
  DWORD v6; // ebx
  wchar_t *v7; // r8
  __int64 v8; // rdx
  char *v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // r9
  int v13; // [rsp+28h] [rbp-50h]
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h] BYREF

  v15 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_180266910[0] )
    bidScopeEnterW(&v15, off_180266910[0], *((unsigned int *)this + 11), a2);
  v4 = (void *)(*((_QWORD *)a2 + 9) + *((unsigned int *)a2 + 22));
  v5 = *((_DWORD *)a2 + 21) - *((_DWORD *)a2 + 20);
  *((_QWORD *)a2 + 4) = 0;
  if ( *((_QWORD *)this + 10) )
  {
    v6 = 5023;
    if ( (bidGblFlags & 2) == 0 || !off_180264298[0] )
      goto LABEL_9;
    SniErrorIdFromStringId(0xC3B4u);
    v7 = off_180264298[0];
    v8 = 842752;
    v9 = off_180260F50[0];
LABEL_8:
    bidTraceW(v9, v8, v7, *((unsigned int *)this + 18));
LABEL_9:
    SNISetLastError(*((unsigned int *)this + 18), v6, 50100);
    goto LABEL_49;
  }
  SNI::detail::Transport::PrepareForAsyncCall(this, a2);
  if ( !ReadFile(*((HANDLE *)this + 8), v4, v5, 0, (LPOVERLAPPED)((char *)a2 + 16)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError == 997 )
      goto LABEL_49;
    if ( LastError != 234 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_9;
      if ( off_1802642A8[0] )
        bidTraceW(off_180260F60[0], 872448, off_1802642A8[0], LastError);
      if ( (bidGblFlags & 2) == 0 || !off_1802642B0[0] )
        goto LABEL_9;
      SniErrorIdFromStringId(0xC3B4u);
      v7 = off_1802642B0[0];
      v8 = 873472;
      v9 = off_180260F68[0];
      goto LABEL_8;
    }
    if ( (bidGblFlags & 2) != 0 && off_1802642A0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260F58[0],
        867328,
        off_1802642A0[0],
        0);
  }
  if ( SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(this) )
  {
    NumberOfBytesTransferred = 0;
    if ( GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)a2 + 16), &NumberOfBytesTransferred, 0) )
    {
      v11 = NumberOfBytesTransferred;
      if ( NumberOfBytesTransferred )
      {
        v6 = 0;
        *((_DWORD *)a2 + 20) += NumberOfBytesTransferred;
        if ( (bidGblFlags & 0x24002) == 0x24002 )
        {
          v11 = NumberOfBytesTransferred;
          if ( off_1802642D8[0] )
          {
            bidTraceW(off_180260F90[0], 908288, off_1802642D8[0], NumberOfBytesTransferred);
            v11 = NumberOfBytesTransferred;
          }
        }
        if ( (bidGblFlags & 0x24002) == 0x24002 )
          bidWriteBin(bidID, 16, *((_QWORD *)a2 + 9) + *((unsigned int *)a2 + 22), v11, 0);
      }
      else
      {
        v6 = 233;
        if ( (bidGblFlags & 2) != 0 && off_1802642C8[0] )
        {
          v13 = 233;
          SniErrorIdFromStringId(0xC3B6u);
          bidTraceW(off_180260F80[0], 897024, off_1802642C8[0], *((unsigned int *)this + 18));
        }
        SNISetLastError(*((unsigned int *)this + 18), 233, 50102);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802642D0[0] && bidID != -1 )
          ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD, int))off_180248050[0])(
            bidID,
            off_180260F88[0],
            898048,
            off_1802642D0[0],
            0,
            v13);
      }
    }
    else
    {
      v6 = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1802642B8[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_180260F70[0], 887808, off_1802642B8[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), v6, 50100);
      if ( (bidGblFlags & 2) != 0 && off_1802642C0[0] )
        bidTraceW(off_180260F78[0], 890880, off_1802642C0[0], v6);
    }
  }
  else
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802642E0[0] && bidID != -1 )
      ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
        bidID,
        off_180260F98[0],
        915456,
        off_1802642E0[0],
        0);
    v6 = 997;
  }
LABEL_49:
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802642E8[0] )
    bidTraceW(off_180260FA0[0], 920576, off_1802642E8[0], v6);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v15);
  return v6;
}

```

## disassembly

```asm
0x18015f740  mov     [rsp+arg_10], rbx
0x18015f745  push    rbp
0x18015f746  push    rsi
0x18015f747  push    rdi
0x18015f748  push    r14
0x18015f74a  push    r15
0x18015f74c  sub     rsp, 50h
0x18015f750  mov     rax, cs:__security_cookie
0x18015f757  xor     rax, rsp
0x18015f75a  mov     [rsp+78h+var_38], rax
0x18015f75f  mov     rsi, rdx
0x18015f762  mov     rdi, rcx
0x18015f765  mov     [rsp+78h+var_40], 0FFFFFFFFFFFFFFFFh
0x18015f76e  mov     eax, cs:_bidGblFlags
0x18015f774  and     eax, 20004h
0x18015f779  cmp     eax, 20004h
0x18015f77e  jnz     short loc_18015F7A4
0x18015f780  mov     rax, cs:off_180266910; "<Np::PostReadAsync|API|SNI> %u#, pPacke"...
0x18015f787  test    rax, rax
0x18015f78a  jz      short loc_18015F7A4
0x18015f78c  mov     r9, rdx
0x18015f78f  mov     r8d, [rcx+2Ch]
0x18015f793  mov     rdx, cs:off_180266910; "<Np::PostReadAsync|API|SNI> %u#, pPacke"...
0x18015f79a  lea     rcx, [rsp+78h+var_40]
0x18015f79f  call    _bidScopeEnterW
0x18015f7a4  mov     ebx, [rsi+58h]
0x18015f7a7  add     rbx, [rsi+48h]
0x18015f7ab  mov     r14d, [rsi+54h]
0x18015f7af  sub     r14d, [rsi+50h]
0x18015f7b3  lea     rbp, [rsi+10h]
0x18015f7b7  xor     r15d, r15d
0x18015f7ba  mov     [rbp+10h], r15
0x18015f7be  cmp     [rdi+50h], r15
0x18015f7c2  jz      short loc_18015F821
0x18015f7c4  mov     ebx, 139Fh
0x18015f7c9  test    byte ptr cs:_bidGblFlags, 2
0x18015f7d0  jz      short loc_18015F80C
0x18015f7d2  mov     rax, cs:off_180264298; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f7d9  test    rax, rax
0x18015f7dc  jz      short loc_18015F80C
0x18015f7de  mov     ecx, 0C3B4h; unsigned int
0x18015f7e3  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f7e8  mov     r8, cs:off_180264298; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f7ef  mov     edx, 0CDC00h
0x18015f7f4  mov     rcx, cs:off_180260F50; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f7fb  mov     [rsp+78h+var_50], ebx
0x18015f7ff  mov     r9d, [rdi+48h]
0x18015f803  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x18015f807  call    _bidTraceW
0x18015f80c  mov     r8d, 0C3B4h
0x18015f812  mov     edx, ebx
0x18015f814  mov     ecx, [rdi+48h]
0x18015f817  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015f81c  jmp     loc_18015FB8E
0x18015f821  mov     rdx, rsi; struct SNI_Packet *
0x18015f824  mov     rcx, rdi; this
0x18015f827  call    ?PrepareForAsyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForAsyncCall(SNI_Packet *)
0x18015f82c  mov     [rsp+78h+lpOverlapped], rbp; lpOverlapped
0x18015f831  xor     r9d, r9d; lpNumberOfBytesRead
0x18015f834  mov     r8d, r14d; nNumberOfBytesToRead
0x18015f837  mov     rdx, rbx; lpBuffer
0x18015f83a  mov     rcx, [rdi+40h]; hFile
0x18015f83e  call    cs:__imp_ReadFile
0x18015f844  test    eax, eax
0x18015f846  jnz     short loc_18015F8B2
0x18015f848  call    cs:__imp_GetLastError
0x18015f84e  mov     ebx, eax
0x18015f850  cmp     eax, 3E5h
0x18015f855  jz      loc_18015FB8E
0x18015f85b  cmp     eax, 0EAh
0x18015f860  jnz     loc_18015F97C
0x18015f866  test    byte ptr cs:_bidGblFlags, 2
0x18015f86d  jz      short loc_18015F8B2
0x18015f86f  mov     rax, cs:off_1802642A0; "<Np::PostReadAsync|ERR|SNI> ReadFile re"...
0x18015f876  test    rax, rax
0x18015f879  jz      short loc_18015F8B2
0x18015f87b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015f883  jz      short loc_18015F8B2
0x18015f885  mov     rax, cs:off_180248050
0x18015f88c  mov     [rsp+78h+lpOverlapped], r15
0x18015f891  mov     r9, cs:off_1802642A0; "<Np::PostReadAsync|ERR|SNI> ReadFile re"...
0x18015f898  mov     r8d, 0D3C00h
0x18015f89e  mov     rdx, cs:off_180260F58; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f8a5  mov     rcx, cs:_bidID
0x18015f8ac  call    cs:__guard_dispatch_icall_fptr
0x18015f8b2  mov     rcx, rdi; this
0x18015f8b5  call    ?FWillSkipCompletionPortOnSuccess@Transport@detail@SNI@@IEBA_NXZ; SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(void)
0x18015f8ba  test    al, al
0x18015f8bc  jz      loc_18015FB34
0x18015f8c2  mov     [rsp+78h+NumberOfBytesTransferred], r15d
0x18015f8c7  xor     r9d, r9d; bWait
0x18015f8ca  lea     r8, [rsp+78h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18015f8cf  mov     rdx, rbp; lpOverlapped
0x18015f8d2  mov     rcx, [rdi+40h]; hFile
0x18015f8d6  call    cs:__imp_GetOverlappedResult
0x18015f8dc  test    eax, eax
0x18015f8de  jnz     loc_18015F9EF
0x18015f8e4  call    cs:__imp_GetLastError
0x18015f8ea  mov     ebx, eax
0x18015f8ec  test    byte ptr cs:_bidGblFlags, 2
0x18015f8f3  jz      short loc_18015F92F
0x18015f8f5  mov     rax, cs:off_1802642B8; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f8fc  test    rax, rax
0x18015f8ff  jz      short loc_18015F92F
0x18015f901  mov     ecx, 0C3B4h; unsigned int
0x18015f906  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f90b  mov     [rsp+78h+var_50], ebx
0x18015f90f  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x18015f913  mov     r9d, [rdi+48h]
0x18015f917  mov     r8, cs:off_1802642B8; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f91e  mov     edx, 0D8C00h
0x18015f923  mov     rcx, cs:off_180260F70; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f92a  call    _bidTraceW
0x18015f92f  mov     r8d, 0C3B4h
0x18015f935  mov     edx, ebx
0x18015f937  mov     ecx, [rdi+48h]
0x18015f93a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015f93f  test    byte ptr cs:_bidGblFlags, 2
0x18015f946  jz      loc_18015FB8E
0x18015f94c  mov     rax, cs:off_1802642C0; "<Np::PostReadAsync|ERR|SNI> GetOverlapp"...
0x18015f953  test    rax, rax
0x18015f956  jz      loc_18015FB8E
0x18015f95c  mov     r9d, ebx
0x18015f95f  mov     r8, cs:off_1802642C0; "<Np::PostReadAsync|ERR|SNI> GetOverlapp"...
0x18015f966  mov     edx, 0D9800h
0x18015f96b  mov     rcx, cs:off_180260F78; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f972  call    _bidTraceW
0x18015f977  jmp     loc_18015FB8E
0x18015f97c  test    byte ptr cs:_bidGblFlags, 2
0x18015f983  jz      loc_18015F80C
0x18015f989  mov     rax, cs:off_1802642A8; "<Np::PostReadAsync|ERR|SNI> ReadFile: %"...
0x18015f990  test    rax, rax
0x18015f993  jz      short loc_18015F9B0
0x18015f995  mov     r9d, ebx
0x18015f998  mov     r8, cs:off_1802642A8; "<Np::PostReadAsync|ERR|SNI> ReadFile: %"...
0x18015f99f  mov     edx, 0D5000h
0x18015f9a4  mov     rcx, cs:off_180260F60; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f9ab  call    _bidTraceW
0x18015f9b0  test    byte ptr cs:_bidGblFlags, 2
0x18015f9b7  jz      loc_18015F80C
0x18015f9bd  mov     rax, cs:off_1802642B0; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f9c4  test    rax, rax
0x18015f9c7  jz      loc_18015F80C
0x18015f9cd  mov     ecx, 0C3B4h; unsigned int
0x18015f9d2  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f9d7  mov     r8, cs:off_1802642B0; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015f9de  mov     edx, 0D5400h
0x18015f9e3  mov     rcx, cs:off_180260F68; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f9ea  jmp     loc_18015F7FB
0x18015f9ef  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x18015f9f4  test    r9d, r9d
0x18015f9f7  jnz     loc_18015FABB
0x18015f9fd  mov     ebx, 0E9h
0x18015fa02  test    byte ptr cs:_bidGblFlags, 2
0x18015fa09  jz      short loc_18015FA45
0x18015fa0b  mov     rax, cs:off_1802642C8; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015fa12  test    rax, rax
0x18015fa15  jz      short loc_18015FA45
0x18015fa17  mov     ecx, 0C3B6h; unsigned int
0x18015fa1c  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015fa21  mov     [rsp+78h+var_50], ebx
0x18015fa25  mov     dword ptr [rsp+78h+lpOverlapped], eax
0x18015fa29  mov     r9d, [rdi+48h]
0x18015fa2d  mov     r8, cs:off_1802642C8; "<Np::PostReadAsync|ERR|SNI> ProviderNum"...
0x18015fa34  mov     edx, 0DB000h
0x18015fa39  mov     rcx, cs:off_180260F80; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015fa40  call    _bidTraceW
0x18015fa45  mov     r8d, 0C3B6h
0x18015fa4b  mov     edx, ebx
0x18015fa4d  mov     ecx, [rdi+48h]
0x18015fa50  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015fa55  mov     eax, cs:_bidGblFlags
0x18015fa5b  and     eax, 20002h
0x18015fa60  cmp     eax, 20002h
0x18015fa65  jnz     loc_18015FB8E
0x18015fa6b  mov     rax, cs:off_1802642D0; "<Np::PostReadAsync|SNI> 0-byte successf"...
0x18015fa72  test    rax, rax
0x18015fa75  jz      loc_18015FB8E
0x18015fa7b  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015fa83  jz      loc_18015FB8E
0x18015fa89  mov     rax, cs:off_180248050
0x18015fa90  mov     [rsp+78h+lpOverlapped], r15
0x18015fa95  mov     r9, cs:off_1802642D0; "<Np::PostReadAsync|SNI> 0-byte successf"...
0x18015fa9c  mov     r8d, 0DB400h
0x18015faa2  mov     rdx, cs:off_180260F88; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015faa9  mov     rcx, cs:_bidID
0x18015fab0  call    cs:__guard_dispatch_icall_fptr
0x18015fab6  jmp     loc_18015FB8E
0x18015fabb  mov     ebx, r15d
0x18015fabe  add     [rsi+50h], r9d
0x18015fac2  mov     eax, cs:_bidGblFlags
0x18015fac8  and     eax, 24002h
0x18015facd  cmp     eax, 24002h
0x18015fad2  jnz     short loc_18015FB02
0x18015fad4  mov     rax, cs:off_1802642D8; "<Np::PostReadAsync|SNI> Receive Packet,"...
0x18015fadb  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x18015fae0  test    rax, rax
0x18015fae3  jz      short loc_18015FB02
0x18015fae5  mov     r8, cs:off_1802642D8; "<Np::PostReadAsync|SNI> Receive Packet,"...
0x18015faec  mov     edx, 0DDC00h
0x18015faf1  mov     rcx, cs:off_180260F90; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015faf8  call    _bidTraceW
0x18015fafd  mov     r9d, [rsp+78h+NumberOfBytesTransferred]
0x18015fb02  mov     eax, cs:_bidGblFlags
0x18015fb08  and     eax, 24002h
0x18015fb0d  cmp     eax, 24002h
0x18015fb12  jnz     short loc_18015FB8E
0x18015fb14  mov     r8d, [rsi+58h]
0x18015fb18  add     r8, [rsi+48h]
0x18015fb1c  mov     [rsp+78h+lpOverlapped], r15
0x18015fb21  mov     edx, 10h
0x18015fb26  mov     rcx, cs:_bidID
0x18015fb2d  call    _bidWriteBin
0x18015fb32  jmp     short loc_18015FB8E
0x18015fb34  mov     eax, cs:_bidGblFlags
0x18015fb3a  and     eax, 20002h
0x18015fb3f  cmp     eax, 20002h
0x18015fb44  jnz     short loc_18015FB89
0x18015fb46  mov     rax, cs:off_1802642E0; "<Np::PostReadAsync|SNI> Suppressing suc"...
0x18015fb4d  test    rax, rax
0x18015fb50  jz      short loc_18015FB89
0x18015fb52  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18015fb5a  jz      short loc_18015FB89
0x18015fb5c  mov     rax, cs:off_180248050
0x18015fb63  mov     [rsp+78h+lpOverlapped], r15
0x18015fb68  mov     r9, cs:off_1802642E0; "<Np::PostReadAsync|SNI> Suppressing suc"...
0x18015fb6f  mov     r8d, 0DF800h
0x18015fb75  mov     rdx, cs:off_180260F98; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015fb7c  mov     rcx, cs:_bidID
0x18015fb83  call    cs:__guard_dispatch_icall_fptr
0x18015fb89  mov     ebx, 3E5h
0x18015fb8e  mov     eax, cs:_bidGblFlags
0x18015fb94  and     eax, 20002h
0x18015fb99  cmp     eax, 20002h
0x18015fb9e  jnz     short loc_18015FBC8
0x18015fba0  mov     rax, cs:off_1802642E8; "<Np::PostReadAsync|RET|SNI> %d{WINERR}"...
0x18015fba7  test    rax, rax
0x18015fbaa  jz      short loc_18015FBC8
0x18015fbac  mov     r9d, ebx
0x18015fbaf  mov     r8, cs:off_1802642E8; "<Np::PostReadAsync|RET|SNI> %d{WINERR}"...
0x18015fbb6  mov     edx, 0E0C00h
0x18015fbbb  mov     rcx, cs:off_180260FA0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015fbc2  call    _bidTraceW
0x18015fbc7  nop
0x18015fbc8  lea     rcx, [rsp+78h+var_40]; this
0x18015fbcd  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015fbd2  nop
0x18015fbd3  mov     eax, ebx
0x18015fbd5  mov     rcx, [rsp+78h+var_38]
0x18015fbda  xor     rcx, rsp; StackCookie
0x18015fbdd  call    __security_check_cookie
0x18015fbe2  mov     rbx, [rsp+78h+arg_10]
0x18015fbea  add     rsp, 50h
0x18015fbee  pop     r15
0x18015fbf0  pop     r14
0x18015fbf2  pop     rdi
0x18015fbf3  pop     rsi
0x18015fbf4  pop     rbp
0x18015fbf5  retn
```
