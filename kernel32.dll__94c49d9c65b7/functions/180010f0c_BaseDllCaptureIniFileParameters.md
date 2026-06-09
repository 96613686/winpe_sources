# BaseDllCaptureIniFileParameters

- ea: `0x180010f0c`
- end: `0x1800114e4`
- name: `BaseDllCaptureIniFileParameters`
- size: `1496`
- prototype: `__int64 __fastcall(int, int, int, int, wchar_t *String, PCSZ SourceString, __int64, wchar_t *, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting`

## callers

- `0x180010290`

## callees

- `0x180010f0c`
- `0x180012ef8`
- `0x18002f3f0`
- `0x18007c010`

## import_xrefs

- `ntdll!strlen` at `0x1800112e7`
- `ntdll!strlen` at `0x1800113dd`
- `ntdll!strlen` at `0x1800112e7`
- `ntdll!strlen` at `0x1800113dd`
- `ntdll!wcslen` at `0x1800111bd`
- `ntdll!wcslen` at `0x1800111d8`
- `ntdll!wcslen` at `0x180011209`
- `ntdll!wcslen` at `0x1800111bd`
- `ntdll!wcslen` at `0x1800111d8`
- `ntdll!wcslen` at `0x180011209`
- `ntdll!RtlInitAnsiString` at `0x18001106b`
- `ntdll!RtlInitAnsiString` at `0x180011094`
- `ntdll!RtlInitAnsiString` at `0x18001106b`
- `ntdll!RtlInitAnsiString` at `0x180011094`
- `ntdll!RtlGetLongestNtPathLength` at `0x180010f89`
- `ntdll!RtlGetLongestNtPathLength` at `0x180011213`
- `ntdll!RtlGetLongestNtPathLength` at `0x180010f89`
- `ntdll!RtlGetLongestNtPathLength` at `0x180011213`
- `ntdll!RtlInitUnicodeString` at `0x180011030`
- `ntdll!RtlInitUnicodeString` at `0x180011077`
- `ntdll!RtlInitUnicodeString` at `0x1800110a0`
- `ntdll!RtlInitUnicodeString` at `0x180011030`
- `ntdll!RtlInitUnicodeString` at `0x180011077`
- `ntdll!RtlInitUnicodeString` at `0x1800110a0`
- `ntdll!RtlFreeHeap` at `0x18001143e`
- `ntdll!RtlFreeHeap` at `0x18001143e`
- `ntdll!RtlAllocateHeap` at `0x180010fcb`
- `ntdll!RtlAllocateHeap` at `0x180010fcb`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010fa6`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180010fa6`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18001140f`
- `KERNELBASE!GetEightBitStringToUnicodeStringRoutine` at `0x18001140f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800112f2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameA` at `0x1800112f2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800111fa`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800111fa`

## pseudocode

```c
__int64 __fastcall BaseDllCaptureIniFileParameters(
        __int64 a1,
        int a2,
        char a3,
        char a4,
        wchar_t *String,
        PCSZ SourceString,
        const char *a7,
        wchar_t *a8,
        int *a9,
        _QWORD *a10)
{
  char v11; // r14
  unsigned int v12; // r15d
  __int64 v13; // rax
  wchar_t *v14; // rsi
  int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // rcx
  ULONG LongestNtPathLength; // ebx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdi
  int v22; // ebx
  ULONG *GlobalData; // rax
  char *Heap; // rax
  char *v25; // rbx
  UNICODE_STRING *v26; // r9
  char *v27; // rdi
  __int64 v28; // rax
  __int64 v29; // rcx
  __int64 v30; // rcx
  PCSZ v31; // rdx
  char v32; // al
  int v33; // eax
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // eax
  int v38; // eax
  DWORD FullPathNameA; // eax
  unsigned __int64 v40; // r8
  UNICODE_STRING *v41; // rdx
  _WORD *v42; // rcx
  USHORT v43; // r15
  __int16 v44; // cx
  __int16 v45; // ax
  __int16 v46; // cx
  __int16 v47; // ax
  __int16 v48; // ax
  _WORD *v50; // rax
  __int64 (__fastcall *EightBitStringToUnicodeStringRoutine)(char *, __int128 *, _QWORD); // rax
  int v52; // r12d
  PCSZ v53; // [rsp+20h] [rbp-28h]
  __int128 v54; // [rsp+28h] [rbp-20h] BYREF
  unsigned int v55; // [rsp+90h] [rbp+48h]
  char v58; // [rsp+A8h] [rbp+60h]
  unsigned int Stringa; // [rsp+B0h] [rbp+68h]

  v58 = a4;
  v11 = a1;
  v54 = 0;
  if ( String )
  {
    if ( (_BYTE)a1 )
      v37 = wcslen(String);
    else
      v37 = strlen((const char *)String);
    a4 = v58;
    v12 = v37;
  }
  else
  {
    v12 = 0;
  }
  if ( SourceString )
  {
    LOBYTE(a1) = v11;
    v55 = BaseDllIniFileNameLength(a1, &SourceString);
    v13 = (__int64)a7;
    v53 = a7;
  }
  else
  {
    v55 = 0;
    v13 = 0;
    v53 = 0;
    a7 = 0;
  }
  if ( v13 )
  {
    LOBYTE(a1) = v11;
    v35 = BaseDllIniFileNameLength(a1, &a7);
    v53 = a7;
    Stringa = v35;
  }
  else
  {
    Stringa = 0;
  }
  v14 = a8;
  if ( !a8 || a9 )
  {
    v15 = 0;
  }
  else
  {
    v36 = (__int64)a8;
    if ( a4 )
    {
      if ( v11 )
      {
        if ( *a8 )
        {
          do
          {
            do
            {
              v48 = *(_WORD *)v36;
              v36 += 2;
            }
            while ( v48 );
          }
          while ( *(_WORD *)v36 );
        }
        v36 = (v36 - (__int64)a8) >> 1;
      }
      else
      {
        if ( *(_BYTE *)a8 )
        {
          do
          {
            while ( *(_BYTE *)v36++ )
              ;
          }
          while ( *(_BYTE *)v36 );
        }
        LODWORD(v36) = v36 - (_DWORD)a8;
      }
      v15 = v36;
    }
    else
    {
      if ( v11 )
        v38 = wcslen(a8);
      else
        v38 = strlen((const char *)a8);
      v15 = v38;
    }
  }
  if ( !String
    || (!v11
      ? (FullPathNameA = GetFullPathNameA((LPCSTR)String, 0, 0, 0))
      : (FullPathNameA = GetFullPathNameW(String, 0, 0, 0)),
        LongestNtPathLength = wcslen(L"\\\\?\\") + 1 + FullPathNameA,
        LongestNtPathLength <= RtlGetLongestNtPathLength()) )
  {
    LongestNtPathLength = RtlGetLongestNtPathLength();
  }
  v21 = 2 * LongestNtPathLength;
  v22 = v21 + 344;
  if ( !v11 )
    v22 += 2 * v12 + 2;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v17, v16, v19, v20);
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, v22 + 2 * (v55 + v15 + Stringa + 3));
  v25 = Heap;
  if ( !Heap )
    return 3221225495LL;
  *(_DWORD *)Heap = a2;
  v26 = (UNICODE_STRING *)(Heap + 40);
  Heap[4] = a3;
  Heap[136] = v58;
  *((_WORD *)Heap + 29) = v21;
  v27 = &Heap[v21 + 344];
  Heap[5] = v11;
  *((_QWORD *)Heap + 2) = 0;
  Heap[6] = 0;
  *((_QWORD *)Heap + 8) = Heap + 344;
  *((_WORD *)Heap + 28) = 0;
  if ( !String )
  {
    RtlInitUnicodeString((PUNICODE_STRING)(Heap + 40), L"win.ini");
    v28 = BaseDllIniFileMapping;
    *(_OWORD *)(v25 + 24) = *(_OWORD *)(v25 + 40);
    v29 = *(_QWORD *)(v28 + 16);
    if ( v29 )
      v30 = BaseStaticServerData + v29 - *(_QWORD *)(BaseStaticServerData + 2536);
    else
      v30 = 0;
    *((_QWORD *)v25 + 1) = v30;
    goto LABEL_18;
  }
  *((_WORD *)Heap + 21) = 2 * v12 + 2;
  if ( v11 )
  {
    v26->Length = 2 * v12;
    *((_QWORD *)Heap + 6) = String;
LABEL_56:
    v40 = *((_QWORD *)v25 + 6);
    v41 = (UNICODE_STRING *)(v25 + 24);
    *((_WORD *)v25 + 12) = 0;
    v42 = (_WORD *)(v40 + 2LL * v12);
    if ( v12 )
    {
      while ( 1 )
      {
        v50 = v42--;
        if ( (unsigned __int64)v42 <= v40 )
          break;
        if ( *v42 == 92 || *v42 == 47 || *v42 == 58 )
        {
          v42 = v50;
          break;
        }
      }
    }
    *((_QWORD *)v25 + 4) = v42;
    v43 = 2 * (v12 - ((__int64)((__int64)v42 - v40) >> 1));
    v41->Length = v43;
    *((_WORD *)v25 + 13) = v43 + 2;
    BaseDllFindIniFileNameMapping(v26, v41);
LABEL_18:
    v31 = SourceString;
    if ( SourceString )
    {
      v44 = 2 * v55;
      *((_WORD *)v25 + 37) = 2 * v55 + 1;
      *((_WORD *)v25 + 53) = 2 * (2 * v55 + 1);
      if ( v11 )
      {
        *((_QWORD *)v25 + 10) = v27;
        v45 = 0;
        *((_QWORD *)v25 + 14) = v31;
        v27 += 2 * v55 + 1;
      }
      else
      {
        *((_QWORD *)v25 + 14) = v27;
        v27 += 2 * v55 + 2;
        *((_QWORD *)v25 + 10) = v31;
        v45 = v55;
        v44 = 0;
      }
      *((_WORD *)v25 + 36) = v45;
      *((_WORD *)v25 + 52) = v44;
    }
    else
    {
      RtlInitAnsiString((PANSI_STRING)(v25 + 72), 0);
      RtlInitUnicodeString((PUNICODE_STRING)(v25 + 104), 0);
    }
    if ( v53 )
    {
      v46 = 2 * Stringa;
      *((_WORD *)v25 + 45) = 2 * Stringa + 1;
      *((_WORD *)v25 + 61) = 2 * (2 * Stringa + 1);
      if ( v11 )
      {
        *((_QWORD *)v25 + 12) = v27;
        v47 = 0;
        *((_QWORD *)v25 + 16) = v53;
        v27 += 2 * Stringa + 1;
      }
      else
      {
        *((_QWORD *)v25 + 16) = v27;
        v27 += 2 * Stringa + 2;
        *((_QWORD *)v25 + 12) = v53;
        v47 = Stringa;
        v46 = 0;
      }
      *((_WORD *)v25 + 44) = v47;
      *((_WORD *)v25 + 60) = v46;
    }
    else
    {
      RtlInitAnsiString((PANSI_STRING)(v25 + 88), 0);
      RtlInitUnicodeString((PUNICODE_STRING)(v25 + 120), 0);
    }
    v32 = v25[4];
    if ( v14 )
    {
      if ( !v32 )
      {
        if ( a9 )
          v33 = *a9;
        else
          v33 = 0;
        *((_DWORD *)v25 + 37) = v33;
        *((_DWORD *)v25 + 36) = 0;
        if ( !v11 )
        {
          *((_QWORD *)v25 + 19) = v14;
          *((_QWORD *)v25 + 20) = 0;
          goto LABEL_29;
        }
        *((_QWORD *)v25 + 20) = v14;
        goto LABEL_28;
      }
      if ( v11 )
      {
        *((_QWORD *)v25 + 20) = v14;
        *((_DWORD *)v25 + 42) = 2 * v15;
        *v27 = 0;
        *((_QWORD *)v25 + 18) = v27;
        *((_DWORD *)v25 + 38) = 0;
        goto LABEL_29;
      }
      *((_QWORD *)v25 + 18) = v14;
      *((_DWORD *)v25 + 38) = v15;
      *(_WORD *)v27 = 0;
      *((_QWORD *)v25 + 20) = v27;
    }
    else
    {
      *((_QWORD *)v25 + 20) = 0;
      if ( !v32 )
      {
        *((_QWORD *)v25 + 18) = 0;
LABEL_28:
        *((_QWORD *)v25 + 19) = 0;
LABEL_29:
        *a10 = v25;
        return 0;
      }
      *((_QWORD *)v25 + 18) = 0;
      *((_DWORD *)v25 + 38) = 0;
    }
    *((_DWORD *)v25 + 42) = 0;
    goto LABEL_29;
  }
  *((_QWORD *)&v54 + 1) = String;
  LOWORD(v54) = v12;
  WORD1(v54) = v12 + 1;
  v26->Length = 0;
  *((_QWORD *)Heap + 6) = v27;
  v27 += 2 * v12 + 2;
  EightBitStringToUnicodeStringRoutine = (__int64 (__fastcall *)(char *, __int128 *, _QWORD))GetEightBitStringToUnicodeStringRoutine();
  v52 = EightBitStringToUnicodeStringRoutine(v25 + 40, &v54, 0);
  if ( v52 >= 0 )
  {
    v26 = (UNICODE_STRING *)(v25 + 40);
    goto LABEL_56;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v25);
  return (unsigned int)v52;
}

```

## disassembly

```asm
0x180010f0c  mov     [rsp-40h+arg_18], r9b
0x180010f11  mov     [rsp-40h+arg_10], r8b
0x180010f16  mov     [rsp-40h+arg_8], edx
0x180010f1a  push    rbp
0x180010f1b  push    rbx
0x180010f1c  push    rsi
0x180010f1d  push    rdi
0x180010f1e  push    r12
0x180010f20  push    r13
0x180010f22  push    r14
0x180010f24  push    r15
0x180010f26  mov     rbp, rsp
0x180010f29  sub     rsp, 48h
0x180010f2d  mov     r12, [rbp+String]
0x180010f31  xor     ebx, ebx
0x180010f33  xorps   xmm0, xmm0
0x180010f36  mov     r14b, cl
0x180010f39  movups  [rbp+var_20], xmm0
0x180010f3d  test    r12, r12
0x180010f40  jnz     loc_1800111B1
0x180010f46  mov     r15d, ebx
0x180010f49  cmp     [rbp+SourceString], rbx
0x180010f4d  jnz     loc_18001110D
0x180010f53  mov     [rbp+arg_0], ebx
0x180010f56  mov     rax, rbx
0x180010f59  mov     [rbp+var_28], rbx
0x180010f5d  mov     [rbp+arg_30], rbx
0x180010f61  test    rax, rax
0x180010f64  jnz     loc_180011129
0x180010f6a  mov     dword ptr [rbp+String], ebx
0x180010f6d  mov     rsi, [rbp+arg_38]
0x180010f74  test    rsi, rsi
0x180010f77  jnz     loc_18001115B
0x180010f7d  mov     r13d, ebx
0x180010f80  test    r12, r12
0x180010f83  jnz     loc_1800111E6
0x180010f89  call    cs:__imp_RtlGetLongestNtPathLength
0x180010f8f  mov     ebx, eax
0x180010f91  lea     edi, [rbx+rbx]
0x180010f94  lea     ebx, [rdi+158h]
0x180010f9a  test    r14b, r14b
0x180010f9d  jnz     short loc_180010FA6
0x180010f9f  lea     ebx, [rbx+r15*2]
0x180010fa3  add     ebx, 2
0x180010fa6  call    cs:__imp_KernelBaseGetGlobalData
0x180010fac  mov     ecx, dword ptr [rbp+String]
0x180010faf  add     ecx, 3
0x180010fb2  add     ecx, r13d
0x180010fb5  add     ecx, [rbp+arg_0]
0x180010fb8  lea     r8d, [rbx+rcx*2]; Size
0x180010fbc  mov     rcx, gs:60h
0x180010fc5  mov     edx, [rax]; Flags
0x180010fc7  mov     rcx, [rcx+30h]; HeapHandle
0x180010fcb  call    cs:__imp_RtlAllocateHeap
0x180010fd1  mov     rbx, rax
0x180010fd4  test    rax, rax
0x180010fd7  jz      loc_1800112C6
0x180010fdd  mov     eax, [rbp+arg_8]
0x180010fe0  lea     rcx, [rbx+158h]
0x180010fe7  mov     [rbx], eax
0x180010fe9  lea     r9, [rbx+28h]
0x180010fed  mov     al, [rbp+arg_10]
0x180010ff0  mov     [rbx+4], al
0x180010ff3  mov     al, [rbp+arg_18]
0x180010ff6  mov     [rbx+88h], al
0x180010ffc  xor     eax, eax
0x180010ffe  mov     [rbx+3Ah], di
0x180011002  add     rdi, rcx
0x180011005  mov     [rbx+5], r14b
0x180011009  mov     qword ptr [rbx+10h], 0
0x180011011  mov     byte ptr [rbx+6], 0
0x180011015  mov     [rbx+40h], rcx
0x180011019  mov     [rbx+38h], ax
0x18001101d  test    r12, r12
0x180011020  jnz     loc_180011251
0x180011026  lea     rdx, SourceString; "win.ini"
0x18001102d  mov     rcx, r9; DestinationString
0x180011030  call    cs:__imp_RtlInitUnicodeString
0x180011036  movups  xmm0, xmmword ptr [rbx+28h]
0x18001103a  mov     rax, cs:BaseDllIniFileMapping
0x180011041  movdqu  xmmword ptr [rbx+18h], xmm0
0x180011046  mov     rcx, [rax+10h]
0x18001104a  test    rcx, rcx
0x18001104d  jnz     loc_180011145
0x180011053  mov     rcx, r12
0x180011056  mov     [rbx+8], rcx
0x18001105a  mov     rdx, [rbp+SourceString]; SourceString
0x18001105e  test    rdx, rdx
0x180011061  jnz     loc_1800112FD
0x180011067  lea     rcx, [rbx+48h]; DestinationString
0x18001106b  call    cs:__imp_RtlInitAnsiString
0x180011071  xor     edx, edx; SourceString
0x180011073  lea     rcx, [rbx+68h]; DestinationString
0x180011077  call    cs:__imp_RtlInitUnicodeString
0x18001107d  mov     r10d, 1
0x180011083  mov     rdx, [rbp+var_28]; SourceString
0x180011087  test    rdx, rdx
0x18001108a  jnz     loc_180011345
0x180011090  lea     rcx, [rbx+58h]; DestinationString
0x180011094  call    cs:__imp_RtlInitAnsiString
0x18001109a  xor     edx, edx; SourceString
0x18001109c  lea     rcx, [rbx+78h]; DestinationString
0x1800110a0  call    cs:__imp_RtlInitUnicodeString
0x1800110a6  mov     al, [rbx+4]
0x1800110a9  test    rsi, rsi
0x1800110ac  jz      loc_180011188
0x1800110b2  test    al, al
0x1800110b4  jnz     loc_180011496
0x1800110ba  mov     rax, [rbp+arg_40]
0x1800110c1  test    rax, rax
0x1800110c4  jz      loc_180011249
0x1800110ca  mov     eax, [rax]
0x1800110cc  mov     [rbx+94h], eax
0x1800110d2  mov     [rbx+90h], r12d
0x1800110d9  test    r14b, r14b
0x1800110dc  jz      loc_180011236
0x1800110e2  mov     [rbx+0A0h], rsi
0x1800110e9  mov     [rbx+98h], r12
0x1800110f0  mov     rax, [rbp+arg_48]
0x1800110f7  mov     [rax], rbx
0x1800110fa  xor     eax, eax
0x1800110fc  add     rsp, 48h
0x180011100  pop     r15
0x180011102  pop     r14
0x180011104  pop     r13
0x180011106  pop     r12
0x180011108  pop     rdi
0x180011109  pop     rsi
0x18001110a  pop     rbx
0x18001110b  pop     rbp
0x18001110c  retn
0x18001110d  lea     rdx, [rbp+SourceString]
0x180011111  mov     cl, r14b
0x180011114  call    BaseDllIniFileNameLength
0x180011119  mov     [rbp+arg_0], eax
0x18001111c  mov     rax, [rbp+arg_30]
0x180011120  mov     [rbp+var_28], rax
0x180011124  jmp     loc_180010F61
0x180011129  lea     rdx, [rbp+arg_30]
0x18001112d  mov     cl, r14b
0x180011130  call    BaseDllIniFileNameLength
0x180011135  mov     rcx, [rbp+arg_30]
0x180011139  mov     [rbp+var_28], rcx
0x18001113d  mov     dword ptr [rbp+String], eax
0x180011140  jmp     loc_180010F6D
0x180011145  mov     rax, cs:BaseStaticServerData
0x18001114c  sub     rcx, [rax+9E8h]
0x180011153  add     rcx, rax
0x180011156  jmp     loc_180011056
0x18001115b  cmp     [rbp+arg_40], rbx
0x180011162  jnz     loc_180010F7D
0x180011168  mov     rcx, rsi; Str
0x18001116b  test    r9b, r9b
0x18001116e  jz      short loc_1800111CF
0x180011170  test    r14b, r14b
0x180011173  jnz     loc_1800112D0
0x180011179  cmp     [rsi], bl
0x18001117b  jnz     loc_1800113A1
0x180011181  sub     ecx, esi
0x180011183  jmp     loc_1800112DF
0x180011188  mov     [rbx+0A0h], r12
0x18001118f  test    al, al
0x180011191  jz      loc_180011226
0x180011197  mov     [rbx+90h], r12
0x18001119e  mov     [rbx+98h], r12d
0x1800111a5  mov     [rbx+0A8h], r12d
0x1800111ac  jmp     loc_1800110F0
0x1800111b1  mov     rcx, r12; Str
0x1800111b4  test    r14b, r14b
0x1800111b7  jz      loc_1800113DD
0x1800111bd  call    cs:__imp_wcslen
0x1800111c3  mov     r9b, [rbp+arg_18]
0x1800111c7  mov     r15, rax
0x1800111ca  jmp     loc_180010F49
0x1800111cf  test    r14b, r14b
0x1800111d2  jz      loc_1800112E7
0x1800111d8  call    cs:__imp_wcslen
0x1800111de  mov     r13, rax
0x1800111e1  jmp     loc_180010F80
0x1800111e6  xor     r9d, r9d; lpFilePart
0x1800111e9  xor     r8d, r8d; lpBuffer
0x1800111ec  xor     edx, edx; nBufferLength
0x1800111ee  mov     rcx, r12; lpFileName
0x1800111f1  test    r14b, r14b
0x1800111f4  jz      loc_1800112F2
0x1800111fa  call    cs:__imp_GetFullPathNameW
0x180011200  lea     rcx, String; "\\\\?\\"
0x180011207  mov     ebx, eax
0x180011209  call    cs:__imp_wcslen
0x18001120f  inc     eax
0x180011211  add     ebx, eax
0x180011213  call    cs:__imp_RtlGetLongestNtPathLength
0x180011219  cmp     ebx, eax
0x18001121b  ja      loc_180010F91
0x180011221  jmp     loc_180010F89
0x180011226  mov     qword ptr [rbx+90h], 0
0x180011231  jmp     loc_1800110E9
0x180011236  mov     [rbx+98h], rsi
0x18001123d  mov     [rbx+0A0h], r12
0x180011244  jmp     loc_1800110F0
0x180011249  mov     eax, r12d
0x18001124c  jmp     loc_1800110CC
0x180011251  movzx   ecx, r15w
0x180011255  mov     r10d, 2
0x18001125b  add     cx, cx
0x18001125e  lea     eax, [r10+rcx]
0x180011262  mov     [rbx+2Ah], ax
0x180011266  test    r14b, r14b
0x180011269  jz      loc_1800113E8
0x18001126f  mov     [r9], cx
0x180011273  mov     [rbx+30h], r12
0x180011277  mov     r8, [rbx+30h]
0x18001127b  lea     rdx, [rbx+18h]; String1
0x18001127f  xor     r12d, r12d
0x180011282  mov     eax, r15d
0x180011285  mov     [rdx], r12w
0x180011289  lea     rcx, [r8+rax*2]
0x18001128d  test    r15d, r15d
0x180011290  jnz     loc_1800113B4
0x180011296  mov     [rbx+20h], rcx
0x18001129a  sub     rcx, r8
0x18001129d  sar     rcx, 1
0x1800112a0  lea     r8, [rbx+8]
0x1800112a4  sub     r15w, cx
0x1800112a8  mov     rcx, r9; String2
0x1800112ab  add     r15w, r15w
0x1800112af  mov     [rdx], r15w
0x1800112b3  add     r15w, r10w
0x1800112b7  mov     [rbx+1Ah], r15w
0x1800112bc  call    BaseDllFindIniFileNameMapping
0x1800112c1  jmp     loc_18001105A
0x1800112c6  mov     eax, 0C0000017h
0x1800112cb  jmp     loc_1800110FC
0x1800112d0  cmp     [rsi], bx
0x1800112d3  jnz     loc_18001138A
0x1800112d9  sub     rcx, rsi
0x1800112dc  sar     rcx, 1
0x1800112df  mov     r13d, ecx
0x1800112e2  jmp     loc_180010F80
0x1800112e7  call    cs:__imp_strlen
0x1800112ed  jmp     loc_1800111DE
0x1800112f2  call    cs:__imp_GetFullPathNameA
0x1800112f8  jmp     loc_180011200
0x1800112fd  mov     r9d, [rbp+arg_0]
0x180011301  mov     r10d, 1
0x180011307  movzx   eax, r9w
0x18001130b  lea     ecx, [rax+rax]
0x18001130e  lea     eax, [r10+rcx]
0x180011312  mov     [rbx+4Ah], ax
0x180011316  add     ax, ax
0x180011319  mov     [rbx+6Ah], ax
0x18001131d  test    r14b, r14b
0x180011320  jz      loc_18001145B
0x180011326  mov     [rbx+50h], rdi
0x18001132a  mov     eax, r12d
0x18001132d  lea     rdi, [rdi+r9*2]
0x180011331  mov     [rbx+70h], rdx
0x180011335  inc     rdi
0x180011338  mov     [rbx+48h], ax
0x18001133c  mov     [rbx+68h], cx
0x180011340  jmp     loc_180011083
0x180011345  mov     r9d, dword ptr [rbp+String]
0x180011349  movzx   eax, r9w
0x18001134d  lea     ecx, [rax+rax]
0x180011350  lea     eax, [r10+rcx]
0x180011354  mov     [rbx+5Ah], ax
0x180011358  add     ax, ax
0x18001135b  mov     [rbx+7Ah], ax
0x18001135f  test    r14b, r14b
0x180011362  jz      loc_180011477
0x180011368  mov     [rbx+60h], rdi
0x18001136c  mov     eax, r12d
0x18001136f  lea     rdi, [rdi+r9*2]
0x180011373  mov     [rbx+80h], rdx
0x18001137a  inc     rdi
0x18001137d  mov     [rbx+58h], ax
0x180011381  mov     [rbx+78h], cx
0x180011385  jmp     loc_1800110A6
0x18001138a  movzx   eax, word ptr [rcx]
0x18001138d  add     rcx, 2
0x180011391  test    ax, ax
0x180011394  jnz     short loc_18001138A
0x180011396  cmp     [rcx], bx
0x180011399  jz      loc_1800112D9
0x18001139f  jmp     short loc_18001138A
0x1800113a1  mov     al, [rcx]
0x1800113a3  inc     rcx
0x1800113a6  test    al, al
0x1800113a8  jnz     short loc_1800113A1
0x1800113aa  cmp     [rcx], bl
0x1800113ac  jz      loc_180011181
0x1800113b2  jmp     short loc_1800113A1
0x1800113b4  mov     rax, rcx
0x1800113b7  sub     rcx, r10
0x1800113ba  cmp     rcx, r8
0x1800113bd  jbe     loc_180011296
0x1800113c3  cmp     word ptr [rcx], 5Ch ; '\'
0x1800113c7  jz      short loc_1800113D5
0x1800113c9  cmp     word ptr [rcx], 2Fh ; '/'
0x1800113cd  jz      short loc_1800113D5
  ... truncated ...
```
