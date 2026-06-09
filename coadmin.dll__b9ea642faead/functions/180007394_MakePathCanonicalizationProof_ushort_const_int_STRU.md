# MakePathCanonicalizationProof(ushort const *,int,STRU *)

- ea: `0x180007394`
- end: `0x1800076b2`
- name: `?MakePathCanonicalizationProof@@YAJPEBGHPEAVSTRU@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, LPCWSTR *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x180004dd0`
- `0x1800063c0`
- `0x18000de90`

## callees

- `0x180007394`
- `0x18000fb50`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180007535`
- `KERNEL32!CreateFileW` at `0x180007535`
- `KERNEL32!CloseHandle` at `0x180007666`
- `KERNEL32!CloseHandle` at `0x180007666`
- `KERNEL32!GetLastError` at `0x180007643`
- `KERNEL32!GetLastError` at `0x180007643`
- `ntdll!NtQueryInformationFile` at `0x180007582`
- `ntdll!NtQueryInformationFile` at `0x1800075d5`
- `ntdll!NtQueryInformationFile` at `0x180007582`
- `ntdll!NtQueryInformationFile` at `0x1800075d5`
- `ntdll!RtlNtStatusToDosError` at `0x1800075e6`
- `ntdll!RtlNtStatusToDosError` at `0x1800075e6`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000755f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800075a8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000755f`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800075a8`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000743c`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x180007453`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000747a`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800074dd`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800074f3`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000743c`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x180007453`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000747a`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800074dd`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x1800074f3`
- `IisRTL!?SetLen@STRU@@QEAA_NK@Z` at `0x1800073ff`
- `IisRTL!?SetLen@STRU@@QEAA_NK@Z` at `0x1800073ff`
- `IisRTL!?Append@STRU@@QEAAJPEBGK@Z` at `0x180007639`
- `IisRTL!?Append@STRU@@QEAAJPEBGK@Z` at `0x180007639`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180007687`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180007687`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007620`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x180007620`

## pseudocode

```c
__int64 __fastcall MakePathCanonicalizationProof(const unsigned __int16 *a1, int a2, LPCWSTR *a3)
{
  const unsigned __int16 *v5; // rsi
  unsigned __int16 v6; // cx
  int v7; // ebx
  unsigned __int16 v8; // ax
  char *FileW; // rsi
  ULONG v10; // ebx
  const unsigned __int16 *v11; // r15
  NTSTATUS v12; // eax
  int v13; // r14d
  unsigned int v14; // ebx
  signed int v15; // eax
  signed int LastError; // eax
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v19[4]; // [rsp+50h] [rbp-9h] BYREF
  PVOID FileInformation; // [rsp+70h] [rbp+17h]
  int v21; // [rsp+78h] [rbp+1Fh]
  __int16 v22; // [rsp+7Ch] [rbp+23h]
  unsigned __int16 v23[4]; // [rsp+80h] [rbp+27h] BYREF

  v19[0] = 0;
  v22 = 256;
  FileInformation = v19;
  v21 = 32;
  v5 = a1;
  IoStatusBlock = 0;
  if ( !a1 || !a3 )
    goto LABEL_45;
  STRU::SetLen((STRU *)a3, 0);
  v6 = *v5;
  if ( *(_DWORD *)v5 != 6029404 )
  {
    if ( !a2 )
      goto LABEL_21;
    if ( (unsigned __int16)(v6 - 65) > 0x19u )
      v8 = *v5;
    else
      v8 = v6 + 32;
    if ( (unsigned __int16)(v8 - 97) <= 0x19u && *(_DWORD *)(v5 + 1) == 6029370 )
    {
      v23[0] = *v5;
      *(_DWORD *)&v23[1] = 58;
LABEL_21:
      v7 = STRU::Append((STRU *)a3, L"\\\\?\\");
      if ( v7 < 0 )
        goto LABEL_46;
LABEL_22:
      v7 = STRU::Append((STRU *)a3, v5);
      if ( v7 < 0 )
        goto LABEL_46;
      if ( !a2 )
        goto LABEL_47;
      FileW = (char *)CreateFileW(a3[4], 0x80000000, 1u, 0, 3u, 0x80u, 0);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( !FileW || FileW == (char *)-1LL )
        {
LABEL_43:
          if ( v7 >= 0 )
            goto LABEL_47;
LABEL_46:
          *a3[4] = 0;
          *((_DWORD *)a3 + 12) = 0;
          goto LABEL_47;
        }
LABEL_42:
        CloseHandle(FileW);
        goto LABEL_43;
      }
      v10 = (2 * *((_DWORD *)a3 + 12) + 25) & 0xFFFFFFF0;
      if ( BUFFER::Resize((BUFFER *)v19, v10) )
      {
        v11 = (const unsigned __int16 *)FileInformation;
        v12 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, v10, FileNameInformation);
        v13 = v12;
        if ( v12 == -2147483643 || v12 == -1073741789 )
        {
          v14 = (*(_DWORD *)v11 + 25) & 0xFFFFFFF0;
          if ( !BUFFER::Resize((BUFFER *)v19, v14) )
            goto LABEL_29;
          v11 = (const unsigned __int16 *)FileInformation;
          v13 = NtQueryInformationFile(FileW, &IoStatusBlock, FileInformation, v14, FileNameInformation);
        }
        if ( v13 >= 0 )
        {
          *a3[4] = 0;
          *((_DWORD *)a3 + 12) = 0;
          v7 = STRU::Copy((STRU *)a3, v23);
          if ( v7 >= 0 )
            v7 = STRU::Append((STRU *)a3, v11 + 2, *(_DWORD *)v11 >> 1);
        }
        else
        {
          v15 = RtlNtStatusToDosError(v13);
          v7 = v15;
          if ( v15 == 317 )
          {
            v7 = v13 | 0x10000000;
          }
          else if ( v15 > 0 )
          {
            v7 = (unsigned __int16)v15 | 0x80070000;
          }
        }
        goto LABEL_42;
      }
LABEL_29:
      v7 = -2147024882;
      goto LABEL_42;
    }
LABEL_45:
    v7 = -2147024809;
    goto LABEL_46;
  }
  if ( v5[2] != 63 && v5[2] != 46 || v5[3] != 92 )
  {
    if ( a2 )
      *(_DWORD *)v23 = 92;
    v7 = STRU::Append((STRU *)a3, L"\\\\?\\UNC\\");
    if ( v7 < 0 )
      goto LABEL_46;
    v5 += 2;
    goto LABEL_22;
  }
  v7 = STRU::Append((STRU *)a3, L"\\\\?\\");
  if ( v7 < 0 )
    goto LABEL_46;
  v7 = STRU::Append((STRU *)a3, v5 + 4);
  if ( v7 < 0 )
    goto LABEL_46;
LABEL_47:
  BUFFER::~BUFFER((BUFFER *)v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007394  mov     [rsp-8+arg_8], rbx
0x180007399  push    rbp
0x18000739a  push    rsi
0x18000739b  push    rdi
0x18000739c  push    r14
0x18000739e  push    r15
0x1800073a0  lea     rbp, [rsp-37h]
0x1800073a5  sub     rsp, 90h
0x1800073ac  mov     rax, cs:__security_cookie
0x1800073b3  xor     rax, rsp
0x1800073b6  mov     [rbp+57h+var_28], rax
0x1800073ba  mov     [rbp+57h+var_60], 0
0x1800073c2  xorps   xmm0, xmm0
0x1800073c5  mov     [rbp+57h+var_34], 100h
0x1800073cb  lea     rax, [rbp+57h+var_60]
0x1800073cf  mov     [rbp+57h+FileInformation], rax
0x1800073d3  mov     ebx, 20h ; ' '
0x1800073d8  mov     [rbp+57h+var_38], ebx
0x1800073db  mov     rdi, r8
0x1800073de  mov     r15d, edx
0x1800073e1  mov     rsi, rcx
0x1800073e4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800073e8  test    rcx, rcx
0x1800073eb  jz      loc_180007672
0x1800073f1  test    r8, r8
0x1800073f4  jz      loc_180007672
0x1800073fa  xor     edx, edx
0x1800073fc  mov     rcx, r8
0x1800073ff  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x180007405  movzx   ecx, word ptr [rsi]
0x180007408  lea     edx, [rbx+3Ch]
0x18000740b  lea     r8d, [rbx-7]
0x18000740f  cmp     cx, dx
0x180007412  jnz     short loc_18000748F
0x180007414  cmp     [rsi+2], dx
0x180007418  jnz     short loc_18000748F
0x18000741a  lea     r14, [rsi+4]
0x18000741e  cmp     word ptr [r14], 3Fh ; '?'
0x180007423  jz      short loc_18000742C
0x180007425  cmp     word ptr [r14], 2Eh ; '.'
0x18000742a  jnz     short loc_180007468
0x18000742c  cmp     [rsi+6], dx
0x180007430  jnz     short loc_180007468
0x180007432  lea     rdx, asc_180012688; "\\\\?\\"
0x180007439  mov     rcx, rdi
0x18000743c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007442  mov     ebx, eax
0x180007444  test    eax, eax
0x180007446  js      loc_180007677
0x18000744c  lea     rdx, [rsi+8]
0x180007450  mov     rcx, rdi
0x180007453  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007459  mov     ebx, eax
0x18000745b  test    eax, eax
0x18000745d  js      loc_180007677
0x180007463  jmp     loc_180007683
0x180007468  test    r15d, r15d
0x18000746b  jz      short loc_180007470
0x18000746d  mov     dword ptr [rbp+57h+var_30], edx
0x180007470  lea     rdx, aUnc; "\\\\?\\UNC\\"
0x180007477  mov     rcx, rdi
0x18000747a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180007480  mov     ebx, eax
0x180007482  test    eax, eax
0x180007484  js      loc_180007677
0x18000748a  mov     rsi, r14
0x18000748d  jmp     short loc_1800074ED
0x18000748f  test    r15d, r15d
0x180007492  jz      short loc_1800074D3
0x180007494  lea     eax, [rcx-41h]
0x180007497  cmp     ax, r8w
0x18000749b  ja      short loc_1800074A2
0x18000749d  lea     eax, [rbx+rcx]
0x1800074a0  jmp     short loc_1800074A5
0x1800074a2  movzx   eax, cx
0x1800074a5  sub     ax, 61h ; 'a'
0x1800074a9  cmp     ax, r8w
0x1800074ad  ja      loc_180007672
0x1800074b3  mov     eax, 3Ah ; ':'
0x1800074b8  cmp     [rsi+2], ax
0x1800074bc  jnz     loc_180007672
0x1800074c2  cmp     [rsi+4], dx
0x1800074c6  jnz     loc_180007672
0x1800074cc  mov     [rbp+57h+var_30], cx
0x1800074d0  mov     dword ptr [rbp+57h+var_30+2], eax
0x1800074d3  lea     rdx, asc_180012688; "\\\\?\\"
0x1800074da  mov     rcx, rdi
0x1800074dd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800074e3  mov     ebx, eax
0x1800074e5  test    eax, eax
0x1800074e7  js      loc_180007677
0x1800074ed  mov     rdx, rsi
0x1800074f0  mov     rcx, rdi
0x1800074f3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800074f9  mov     ebx, eax
0x1800074fb  test    eax, eax
0x1800074fd  js      loc_180007677
0x180007503  test    r15d, r15d
0x180007506  jz      loc_180007683
0x18000750c  mov     rcx, [rdi+20h]; lpFileName
0x180007510  xor     r9d, r9d; lpSecurityAttributes
0x180007513  mov     [rsp+0B0h+hTemplateFile], 0; hTemplateFile
0x18000751c  mov     edx, 80000000h; dwDesiredAccess
0x180007521  mov     [rsp+0B0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180007529  mov     [rsp+0B0h+dwCreationDisposition], 3; dwCreationDisposition
0x180007531  lea     r8d, [r9+1]; dwShareMode
0x180007535  call    cs:__imp_CreateFileW
0x18000753b  mov     rsi, rax
0x18000753e  lea     rcx, [rax-1]
0x180007542  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180007546  ja      loc_180007643
0x18000754c  mov     ecx, [rdi+30h]
0x18000754f  lea     ebx, ds:19h[rcx*2]
0x180007556  and     ebx, 0FFFFFFF0h
0x180007559  lea     rcx, [rbp+57h+var_60]
0x18000755d  mov     edx, ebx
0x18000755f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180007565  test    al, al
0x180007567  jz      short loc_1800075B2
0x180007569  mov     r15, [rbp+57h+FileInformation]
0x18000756d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180007571  mov     r8, r15; FileInformation
0x180007574  mov     [rsp+0B0h+dwCreationDisposition], 9; FileInformationClass
0x18000757c  mov     r9d, ebx; Length
0x18000757f  mov     rcx, rsi; FileHandle
0x180007582  call    cs:__imp_NtQueryInformationFile
0x180007588  mov     r14d, eax
0x18000758b  cmp     eax, 80000005h
0x180007590  jz      short loc_180007599
0x180007592  cmp     eax, 0C0000023h
0x180007597  jnz     short loc_1800075DE
0x180007599  mov     ebx, [r15]
0x18000759c  lea     rcx, [rbp+57h+var_60]
0x1800075a0  add     ebx, 19h
0x1800075a3  and     ebx, 0FFFFFFF0h
0x1800075a6  mov     edx, ebx
0x1800075a8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800075ae  test    al, al
0x1800075b0  jnz     short loc_1800075BC
0x1800075b2  mov     ebx, 8007000Eh
0x1800075b7  jmp     loc_180007663
0x1800075bc  mov     r15, [rbp+57h+FileInformation]
0x1800075c0  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800075c4  mov     r8, r15; FileInformation
0x1800075c7  mov     [rsp+0B0h+dwCreationDisposition], 9; FileInformationClass
0x1800075cf  mov     r9d, ebx; Length
0x1800075d2  mov     rcx, rsi; FileHandle
0x1800075d5  call    cs:__imp_NtQueryInformationFile
0x1800075db  mov     r14d, eax
0x1800075de  test    r14d, r14d
0x1800075e1  jns     short loc_18000760D
0x1800075e3  mov     ecx, r14d; Status
0x1800075e6  call    cs:__imp_RtlNtStatusToDosError
0x1800075ec  mov     ebx, eax
0x1800075ee  cmp     eax, 13Dh
0x1800075f3  jz      short loc_180007604
0x1800075f5  test    eax, eax
0x1800075f7  jle     short loc_180007663
0x1800075f9  movzx   ebx, ax
0x1800075fc  or      ebx, 80070000h
0x180007602  jmp     short loc_180007663
0x180007604  mov     ebx, r14d
0x180007607  bts     ebx, 1Ch
0x18000760b  jmp     short loc_180007663
0x18000760d  mov     rcx, [rdi+20h]
0x180007611  lea     rdx, [rbp+57h+var_30]
0x180007615  xor     eax, eax
0x180007617  mov     [rcx], ax
0x18000761a  mov     rcx, rdi
0x18000761d  mov     [rdi+30h], eax
0x180007620  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180007626  mov     ebx, eax
0x180007628  test    eax, eax
0x18000762a  js      short loc_180007663
0x18000762c  mov     r8d, [r15]
0x18000762f  lea     rdx, [r15+4]
0x180007633  shr     r8d, 1
0x180007636  mov     rcx, rdi
0x180007639  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18000763f  mov     ebx, eax
0x180007641  jmp     short loc_180007663
0x180007643  call    cs:__imp_GetLastError
0x180007649  mov     ebx, eax
0x18000764b  test    eax, eax
0x18000764d  jle     short loc_180007658
0x18000764f  movzx   ebx, ax
0x180007652  or      ebx, 80070000h
0x180007658  test    rsi, rsi
0x18000765b  jz      short loc_18000766C
0x18000765d  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180007661  jz      short loc_18000766C
0x180007663  mov     rcx, rsi; hObject
0x180007666  call    cs:__imp_CloseHandle
0x18000766c  test    ebx, ebx
0x18000766e  jns     short loc_180007683
0x180007670  jmp     short loc_180007677
0x180007672  mov     ebx, 80070057h
0x180007677  mov     rcx, [rdi+20h]
0x18000767b  xor     eax, eax
0x18000767d  mov     [rcx], ax
0x180007680  mov     [rdi+30h], eax
0x180007683  lea     rcx, [rbp+57h+var_60]
0x180007687  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000768d  mov     eax, ebx
0x18000768f  mov     rcx, [rbp+57h+var_28]
0x180007693  xor     rcx, rsp; StackCookie
0x180007696  call    __security_check_cookie
0x18000769b  mov     rbx, [rsp+0B0h+arg_8]
0x1800076a3  add     rsp, 90h
0x1800076aa  pop     r15
0x1800076ac  pop     r14
0x1800076ae  pop     rdi
0x1800076af  pop     rsi
0x1800076b0  pop     rbp
0x1800076b1  retn
```
