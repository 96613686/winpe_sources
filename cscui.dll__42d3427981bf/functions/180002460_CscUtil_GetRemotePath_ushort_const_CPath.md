# CscUtil_GetRemotePath(ushort const *,CPath *)

- ea: `0x180002460`
- end: `0x180002806`
- name: `?CscUtil_GetRemotePath@@YAJPEBGPEAVCPath@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(PCWSTR SourceString, struct CPath *this)`
- caller_count: `3`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800202a0`
- `0x1800348b0`
- `0x180034f3c`

## callees

- `0x180002460`
- `0x180003c20`
- `0x1800065a0`
- `0x180008b40`
- `0x180032b8c`
- `0x18004c62a`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x1800024e2`
- `SHLWAPI!PathIsUNCW` at `0x1800024e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800027a4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000278d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002628`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000278d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002647`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002647`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024a9`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800024a9`
- `ntdll!RtlAppendPathElement` at `0x18000275a`
- `ntdll!RtlAppendPathElement` at `0x18000275a`
- `ntdll!RtlpEnsureBufferSize` at `0x18000253e`
- `ntdll!RtlpEnsureBufferSize` at `0x1800026d2`
- `ntdll!RtlpEnsureBufferSize` at `0x18000253e`
- `ntdll!RtlpEnsureBufferSize` at `0x1800026d2`
- `ntdll!RtlInitUnicodeString` at `0x1800024fe`
- `ntdll!RtlInitUnicodeString` at `0x180002695`
- `ntdll!RtlInitUnicodeString` at `0x180002745`
- `ntdll!RtlInitUnicodeString` at `0x1800024fe`
- `ntdll!RtlInitUnicodeString` at `0x180002695`
- `ntdll!RtlInitUnicodeString` at `0x180002745`
- `MPR!WNetGetConnectionW` at `0x1800025cc`
- `MPR!WNetGetConnectionW` at `0x180002668`
- `MPR!WNetGetConnectionW` at `0x1800025cc`
- `MPR!WNetGetConnectionW` at `0x180002668`

## pseudocode

```c
__int64 __fastcall CscUtil_GetRemotePath(PCWSTR SourceString, struct CPath *this)
{
  __int64 v5; // rdx
  SIZE_T v6; // r8
  __int64 v7; // rcx
  signed int v8; // esi
  unsigned __int64 v9; // rax
  __int64 v10; // rdx
  unsigned __int64 v11; // r8
  signed int ConnectionW; // eax
  WCHAR *v13; // r15
  SIZE_T v14; // r12
  HANDLE ProcessHeap; // rax
  signed int v16; // eax
  void *v17; // rdx
  __int64 Length; // r9
  _WORD *v19; // r12
  SIZE_T v20; // r8
  __int64 v21; // rcx
  PWSTR Buffer; // rdx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rcx
  int appended; // eax
  HANDLE v26; // rax
  int v27; // ecx
  int v28; // ecx
  DWORD nLength; // [rsp+20h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-28h] BYREF
  WCHAR RemoteName[2]; // [rsp+38h] [rbp-18h] BYREF
  WCHAR RootPathName; // [rsp+3Ch] [rbp-14h] BYREF
  int v33; // [rsp+3Eh] [rbp-12h]

  if ( SourceString[1] == 58 )
  {
    RootPathName = *SourceString;
    v33 = 58;
    if ( GetDriveTypeW(&RootPathName) != 4 )
      return 1;
    nLength = 0;
    ConnectionW = WNetGetConnectionW(&RootPathName, RemoteName, &nLength);
    v8 = ConnectionW;
    if ( ConnectionW == 234 )
    {
      *(_QWORD *)&DestinationString.Length = 0;
      v14 = 2LL * nLength;
      if ( !is_mul_ok(nLength, 2u) )
        return 2147942934LL;
      v13 = 0;
      ProcessHeap = GetProcessHeap();
      v8 = -2147418113;
      if ( ProcessHeap )
      {
        v8 = 0;
        v13 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v14);
        if ( !v13 )
          v8 = -2147024882;
      }
      if ( v8 < 0 )
        goto LABEL_18;
      v16 = WNetGetConnectionW(&RootPathName, v13, &nLength);
      v8 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v8 = (unsigned __int16)v16 | 0x80070000;
        if ( v8 < 0 )
        {
          CscUtil_HeapFree(v13, v17);
          goto LABEL_18;
        }
      }
    }
    else
    {
      if ( ConnectionW > 0 )
        v8 = (unsigned __int16)ConnectionW | 0x80070000;
      v13 = 0;
      if ( v8 < 0 )
      {
LABEL_18:
        if ( (_WORD)v8 == 2250 )
          return 1;
        goto LABEL_11;
      }
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, v13);
    Length = DestinationString.Length;
    v19 = (_WORD *)((char *)this + 520);
    *((_WORD *)this + 260) = 0;
    v20 = Length + 2;
    if ( (unsigned __int64)(Length + 2) > 0xFFFE )
    {
      v27 = -1073741562;
    }
    else
    {
      if ( this != (struct CPath *)-536LL && v20 <= *((_QWORD *)this + 69) )
        goto LABEL_35;
      if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)this + 536), v20) >= 0 )
      {
        LOWORD(Length) = DestinationString.Length;
LABEL_35:
        v21 = *((_QWORD *)this + 67);
        Buffer = DestinationString.Buffer;
        v23 = (unsigned __int64)(unsigned __int16)*v19 >> 1;
        *((_QWORD *)this + 66) = v21;
        memmove_0((void *)(v21 + 2 * v23), Buffer, (unsigned __int16)Length);
        v24 = (unsigned __int16)(*v19 + DestinationString.Length);
        *v19 = v24;
        *((_WORD *)this + 261) = v24 + 2;
        *(_WORD *)(*((_QWORD *)this + 66) + 2 * (v24 >> 1)) = 0;
        goto LABEL_36;
      }
      v27 = -1073741801;
    }
    v8 = ResultFromNtStatus(v27);
    if ( v8 < 0 )
    {
LABEL_40:
      if ( v13 )
      {
        v26 = GetProcessHeap();
        if ( v26 )
        {
          if ( !HeapFree(v26, 0, v13) )
            ResultFromLastError();
        }
      }
      goto LABEL_11;
    }
LABEL_36:
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString + 2);
    v8 = 0;
    appended = RtlAppendPathElement(1, (char *)this + 520, &DestinationString);
    if ( appended < 0 )
      v8 = ResultFromNtStatus(appended);
    goto LABEL_40;
  }
  if ( !PathIsUNCW(SourceString) )
    return 2147942561LL;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v5 = DestinationString.Length;
  *((_WORD *)this + 260) = 0;
  v6 = v5 + 2;
  if ( (unsigned __int64)(v5 + 2) > 0xFFFE )
  {
    v28 = -1073741562;
LABEL_49:
    v8 = ResultFromNtStatus(v28);
    goto LABEL_11;
  }
  if ( this != (struct CPath *)-536LL && v6 <= *((_QWORD *)this + 69) )
    goto LABEL_10;
  if ( RtlpEnsureBufferSize(0, (PRTL_BUFFER)((char *)this + 536), v6) < 0 )
  {
    v28 = -1073741801;
    goto LABEL_49;
  }
  LOWORD(v5) = DestinationString.Length;
LABEL_10:
  v7 = *((_QWORD *)this + 67);
  v8 = 0;
  v9 = (unsigned __int64)*((unsigned __int16 *)this + 260) >> 1;
  *((_QWORD *)this + 66) = v7;
  memmove_0((void *)(v7 + 2 * v9), DestinationString.Buffer, (unsigned __int16)v5);
  v10 = *((_QWORD *)this + 66);
  v11 = (unsigned __int16)(*((_WORD *)this + 260) + DestinationString.Length);
  *((_WORD *)this + 260) = v11;
  *((_WORD *)this + 261) = v11 + 2;
  *(_WORD *)(v10 + 2 * (v11 >> 1)) = 0;
LABEL_11:
  if ( !v8 )
    CPath::RemoveBackslash(this);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002460  mov     [rsp-28h+arg_10], rbx
0x180002465  mov     [rsp-28h+arg_18], rsi
0x18000246a  push    rbp
0x18000246b  push    rdi
0x18000246c  push    r12
0x18000246e  push    r14
0x180002470  push    r15
0x180002472  mov     rbp, rsp
0x180002475  sub     rsp, 50h
0x180002479  mov     rax, cs:__security_cookie
0x180002480  xor     rax, rsp
0x180002483  mov     [rbp+var_8], rax
0x180002487  cmp     word ptr [rcx+2], 3Ah ; ':'
0x18000248c  mov     rdi, rdx
0x18000248f  mov     rbx, rcx
0x180002492  jnz     short loc_1800024E2
0x180002494  movzx   eax, word ptr [rcx]
0x180002497  xor     r14d, r14d
0x18000249a  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x18000249e  mov     [rbp+RootPathName], ax
0x1800024a2  mov     [rbp+var_12], 3Ah ; ':'
0x1800024a9  call    cs:__imp_GetDriveTypeW
0x1800024af  cmp     eax, 4
0x1800024b2  jz      loc_1800025BC
0x1800024b8  mov     eax, 1
0x1800024bd  mov     rcx, [rbp+var_8]
0x1800024c1  xor     rcx, rsp; StackCookie
0x1800024c4  call    __security_check_cookie
0x1800024c9  lea     r11, [rsp+50h+var_s0]
0x1800024ce  mov     rbx, [r11+40h]
0x1800024d2  mov     rsi, [r11+48h]
0x1800024d6  mov     rsp, r11
0x1800024d9  pop     r15
0x1800024db  pop     r14
0x1800024dd  pop     r12
0x1800024df  pop     rdi
0x1800024e0  pop     rbp
0x1800024e1  retn
0x1800024e2  call    cs:__imp_PathIsUNCW
0x1800024e8  test    eax, eax
0x1800024ea  jz      loc_180002600
0x1800024f0  xorps   xmm0, xmm0
0x1800024f3  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800024f7  mov     rdx, rbx; SourceString
0x1800024fa  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800024fe  call    cs:__imp_RtlInitUnicodeString
0x180002504  movzx   edx, [rbp+DestinationString.Length]
0x180002508  xor     r14d, r14d
0x18000250b  mov     [rdi+208h], r14w
0x180002513  lea     r8, [rdx+2]; RequiredSize
0x180002517  cmp     r8, 0FFFEh
0x18000251e  ja      loc_1800027E1
0x180002524  lea     rax, [rdi+218h]
0x18000252b  test    rax, rax
0x18000252e  jz      short loc_180002539
0x180002530  cmp     r8, [rdi+228h]
0x180002537  jbe     short loc_180002550
0x180002539  mov     rdx, rax; Buffer
0x18000253c  xor     ecx, ecx; Flags
0x18000253e  call    cs:__imp_RtlpEnsureBufferSize
0x180002544  test    eax, eax
0x180002546  js      loc_1800027E8
0x18000254c  movzx   edx, [rbp+DestinationString.Length]
0x180002550  mov     rcx, [rdi+218h]
0x180002557  mov     esi, r14d
0x18000255a  movzx   eax, word ptr [rdi+208h]
0x180002561  shr     rax, 1
0x180002564  mov     [rdi+210h], rcx
0x18000256b  movzx   r8d, dx; Size
0x18000256f  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x180002573  lea     rcx, [rcx+rax*2]; void *
0x180002577  call    memmove_0
0x18000257c  movzx   eax, [rbp+DestinationString.Length]
0x180002580  add     ax, [rdi+208h]
0x180002587  mov     rdx, [rdi+210h]
0x18000258e  movzx   r8d, ax
0x180002592  mov     [rdi+208h], r8w
0x18000259a  lea     eax, [r8+2]
0x18000259e  shr     r8, 1
0x1800025a1  mov     [rdi+20Ah], ax
0x1800025a8  mov     [rdx+r8*2], r14w
0x1800025ad  test    esi, esi
0x1800025af  jz      loc_1800027F9
0x1800025b5  mov     eax, esi
0x1800025b7  jmp     loc_1800024BD
0x1800025bc  lea     r8, [rbp+nLength]; lpnLength
0x1800025c0  mov     [rbp+nLength], r14d
0x1800025c4  lea     rdx, [rbp+RemoteName]; lpRemoteName
0x1800025c8  lea     rcx, [rbp+RootPathName]; lpLocalName
0x1800025cc  call    cs:__imp_WNetGetConnectionW
0x1800025d2  mov     esi, eax
0x1800025d4  cmp     eax, 0EAh
0x1800025d9  jz      short loc_18000260A
0x1800025db  test    eax, eax
0x1800025dd  jle     short loc_1800025E8
0x1800025df  movzx   esi, ax
0x1800025e2  or      esi, 80070000h
0x1800025e8  mov     r15, r14
0x1800025eb  test    esi, esi
0x1800025ed  jns     loc_180002687
0x1800025f3  cmp     si, 8CAh
0x1800025f8  jz      loc_1800024B8
0x1800025fe  jmp     short loc_1800025AD
0x180002600  mov     eax, 800700A1h
0x180002605  jmp     loc_1800024BD
0x18000260a  mov     ecx, [rbp+nLength]
0x18000260d  mov     eax, 2
0x180002612  mul     rcx
0x180002615  mov     qword ptr [rbp+DestinationString.Length], r14
0x180002619  mov     r12, rax
0x18000261c  test    rdx, rdx
0x18000261f  jnz     loc_18000276F
0x180002625  mov     r15, r14
0x180002628  call    cs:__imp_GetProcessHeap
0x18000262e  test    rax, rax
0x180002631  mov     esi, 8000FFFFh
0x180002636  cmovnz  esi, r14d
0x18000263a  jz      short loc_180002659
0x18000263c  mov     r8, r12; dwBytes
0x18000263f  mov     edx, 8; dwFlags
0x180002644  mov     rcx, rax; hHeap
0x180002647  call    cs:__imp_HeapAlloc
0x18000264d  mov     r15, rax
0x180002650  test    rax, rax
0x180002653  jz      loc_1800027BC
0x180002659  test    esi, esi
0x18000265b  js      short loc_1800025F3
0x18000265d  lea     r8, [rbp+nLength]; lpnLength
0x180002661  mov     rdx, r15; lpRemoteName
0x180002664  lea     rcx, [rbp+RootPathName]; lpLocalName
0x180002668  call    cs:__imp_WNetGetConnectionW
0x18000266e  mov     esi, eax
0x180002670  test    eax, eax
0x180002672  jz      short loc_180002687
0x180002674  jle     short loc_18000267F
0x180002676  movzx   esi, ax
0x180002679  or      esi, 80070000h
0x18000267f  test    esi, esi
0x180002681  js      loc_1800027C6
0x180002687  xorps   xmm0, xmm0
0x18000268a  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000268e  mov     rdx, r15; SourceString
0x180002691  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002695  call    cs:__imp_RtlInitUnicodeString
0x18000269b  movzx   r9d, [rbp+DestinationString.Length]
0x1800026a0  lea     r12, [rdi+208h]
0x1800026a7  mov     [r12], r14w
0x1800026ac  lea     r8, [r9+2]; RequiredSize
0x1800026b0  cmp     r8, 0FFFEh
0x1800026b7  ja      loc_1800027D3
0x1800026bd  lea     rdx, [r12+10h]; Buffer
0x1800026c2  test    rdx, rdx
0x1800026c5  jz      short loc_1800026D0
0x1800026c7  cmp     r8, [rdi+228h]
0x1800026ce  jbe     short loc_1800026E5
0x1800026d0  xor     ecx, ecx; Flags
0x1800026d2  call    cs:__imp_RtlpEnsureBufferSize
0x1800026d8  test    eax, eax
0x1800026da  js      loc_1800027DA
0x1800026e0  movzx   r9d, [rbp+DestinationString.Length]
0x1800026e5  mov     rcx, [rdi+218h]
0x1800026ec  movzx   eax, word ptr [r12]
0x1800026f1  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1800026f5  shr     rax, 1
0x1800026f8  mov     [rdi+210h], rcx
0x1800026ff  movzx   r8d, r9w; Size
0x180002703  lea     rcx, [rcx+rax*2]; void *
0x180002707  call    memmove_0
0x18000270c  movzx   eax, [rbp+DestinationString.Length]
0x180002710  add     ax, [r12]
0x180002715  movzx   ecx, ax
0x180002718  mov     [r12], cx
0x18000271d  lea     eax, [rcx+2]
0x180002720  shr     rcx, 1
0x180002723  mov     [rdi+20Ah], ax
0x18000272a  mov     rax, [rdi+210h]
0x180002731  mov     [rax+rcx*2], r14w
0x180002736  xorps   xmm0, xmm0
0x180002739  lea     rdx, [rbx+4]; SourceString
0x18000273d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180002741  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180002745  call    cs:__imp_RtlInitUnicodeString
0x18000274b  lea     r8, [rbp+DestinationString]
0x18000274f  mov     rdx, r12
0x180002752  mov     ecx, 1
0x180002757  mov     esi, r14d
0x18000275a  call    cs:__imp_RtlAppendPathElement
0x180002760  test    eax, eax
0x180002762  jns     short loc_180002784
0x180002764  mov     ecx, eax; int
0x180002766  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000276b  mov     esi, eax
0x18000276d  jmp     short loc_180002784
0x18000276f  mov     eax, 80070216h
0x180002774  jmp     loc_1800024BD
0x180002779  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x18000277e  mov     esi, eax
0x180002780  test    eax, eax
0x180002782  jns     short loc_180002736
0x180002784  test    r15, r15
0x180002787  jz      loc_1800025AD
0x18000278d  call    cs:__imp_GetProcessHeap
0x180002793  test    rax, rax
0x180002796  jz      loc_1800025AD
0x18000279c  mov     r8, r15; lpMem
0x18000279f  xor     edx, edx; dwFlags
0x1800027a1  mov     rcx, rax; hHeap
0x1800027a4  call    cs:__imp_HeapFree
0x1800027aa  test    eax, eax
0x1800027ac  jnz     loc_1800025AD
0x1800027b2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800027b7  jmp     loc_1800025AD
0x1800027bc  mov     esi, 8007000Eh
0x1800027c1  jmp     loc_180002659
0x1800027c6  mov     rcx, r15; lpMem
0x1800027c9  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x1800027ce  jmp     loc_1800025F3
0x1800027d3  mov     ecx, 0C0000106h; int
0x1800027d8  jmp     short loc_180002779
0x1800027da  mov     ecx, 0C0000017h
0x1800027df  jmp     short loc_180002779
0x1800027e1  mov     ecx, 0C0000106h
0x1800027e6  jmp     short loc_1800027ED
0x1800027e8  mov     ecx, 0C0000017h; int
0x1800027ed  call    ?ResultFromNtStatus@@YAJJ@Z; ResultFromNtStatus(long)
0x1800027f2  mov     esi, eax
0x1800027f4  jmp     loc_1800025AD
0x1800027f9  mov     rcx, rdi; this
0x1800027fc  call    ?RemoveBackslash@CPath@@QEAAJXZ; CPath::RemoveBackslash(void)
0x180002801  jmp     loc_1800025B5
```
