# SdbInitDatabaseEx

- ea: `0x1800a77cc`
- end: `0x1800a7b4e`
- name: `SdbInitDatabaseEx`
- size: `898`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18003f65c`

## callees

- `0x180040ee0`
- `0x180041774`
- `0x18004281c`
- `0x180060a18`
- `0x18006f7b4`
- `0x18006fbd4`
- `0x1800715f0`
- `0x180075fa0`
- `0x180076e90`
- `0x180076f20`
- `0x1800a77cc`
- `0x1800ab11c`
- `0x1800ab684`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800a7829`
- `ntdll!RtlAllocateHeap` at `0x1800a7829`
- `ntdll!RtlGetVersion` at `0x1800a7b13`
- `ntdll!RtlGetVersion` at `0x1800a7b13`

## string_xrefs

- `0x1800a7899`: `SdbpResolveInitSdbPath`
- `0x1800a788c`: `SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM`
- `0x1800a78b9`: `SdbpResolveInitSdbPath failed to resolve the sdb path [%x]`
- `0x1800a791f`: `Unable to open main database %S`
- `0x1800a7a22`: `Unable to open merge stub database %S`

## pseudocode

```c
char *SdbInitDatabaseEx()
{
  int v0; // ebx
  int *v1; // rsi
  __int64 v2; // rdx
  char *Heap; // rdi
  __int64 v5; // rdx
  int v6; // eax
  const wchar_t ****v7; // r15
  __int64 v8; // rax
  int MergeStubPath; // eax
  __int64 v10; // rdx
  const wchar_t ***v11; // rax
  const wchar_t **v12; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int16 v16; // [rsp+30h] [rbp-398h] BYREF
  int *v17; // [rsp+38h] [rbp-390h] BYREF
  int v18; // [rsp+40h] [rbp-388h]
  char *v19; // [rsp+48h] [rbp-380h]
  char *v20; // [rsp+50h] [rbp-378h]
  char *v21; // [rsp+58h] [rbp-370h]
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-368h] BYREF
  char v23; // [rsp+17Ah] [rbp-24Eh]
  wchar_t String2[264]; // [rsp+180h] [rbp-248h] BYREF

  v0 = 0;
  String2[0] = 0;
  memset_0(&String2[1], 0, 0x206u);
  v1 = 0;
  v17 = 0;
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x6F8u);
  v19 = Heap;
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 554, "Failed to allocate sdb context");
    return 0;
  }
  *((_WORD *)Heap + 292) = -31132;
  v16 = -31132;
  if ( (unsigned int)SdbGetPathSystemSdb(String2, v2, 1, &v16) )
  {
    v6 = 0;
  }
  else
  {
    AslLogCallPrintf(1, "SdbpResolveInitSdbPath", 466, "SdbGetPathSystemSdb failed to get file path for SDB_SYSTEM");
    v6 = -1073741823;
  }
  if ( v6 < 0 )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 569, "SdbpResolveInitSdbPath failed to resolve the sdb path [%x]", v6);
    v7 = (const wchar_t ****)(Heap + 8);
LABEL_22:
    if ( *v7 )
      SdbCloseDatabaseRead(*v7);
    v15 = *((_QWORD *)Heap + 2);
    if ( v15 )
      SdbCloseDatabaseRead(v15);
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
    if ( v1 )
      AslFree(NtCurrentPeb()->ProcessHeap, v1);
    return 0;
  }
  v18 = 0;
  *((_QWORD *)Heap + 1) = SdbOpenDatabaseEx((int *)String2, v5, 0);
  v7 = (const wchar_t ****)(Heap + 8);
  v20 = Heap + 8;
  v8 = *((_QWORD *)Heap + 1);
  if ( !v8 )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 597, "Unable to open main database %S", String2);
    goto LABEL_22;
  }
  *((_QWORD *)Heap + 7) = v8;
  *((_DWORD *)Heap + 16) = 3;
  *(_OWORD *)(Heap + 40) = *(_OWORD *)(v8 + 28);
  v21 = Heap + 36;
  *((_DWORD *)Heap + 9) |= 1u;
  MergeStubPath = SdbGetMergeStubPath(&v17, String2);
  if ( MergeStubPath == -1073741772 )
    goto LABEL_29;
  if ( MergeStubPath < 0 )
  {
    AslLogCallPrintf(1, "SdbInitDatabaseEx", 630, "Unable to find merge stub database for %S", String2);
    v1 = v17;
    goto LABEL_22;
  }
  v11 = *v7;
  if ( *v7 && (v12 = *v11) != 0 && *v12 && wcsicmp(*v12, String2) != 0 )
  {
LABEL_29:
    *((_QWORD *)Heap + 2) = 0;
    v1 = v17;
  }
  else
  {
    v18 = 0;
    v1 = v17;
    *((_QWORD *)Heap + 2) = SdbOpenDatabaseEx(v17, v10, 0);
    v14 = *((_QWORD *)Heap + 2);
    if ( !v14 )
    {
      AslLogCallPrintf(1, "SdbInitDatabaseEx", 666, "Unable to open merge stub database %S", String2);
      goto LABEL_22;
    }
    *((_QWORD *)Heap + 15) = v14;
    *((_DWORD *)Heap + 32) = 3;
    *(_OWORD *)(Heap + 104) = *(_OWORD *)(v14 + 28);
    *((_DWORD *)Heap + 9) |= 4u;
  }
  if ( v1 )
    AslFree(NtCurrentPeb()->ProcessHeap, v1);
  SdbpInitializeMatchers(Heap);
  *((_DWORD *)Heap + 138) = SdbpGetBinaryRuntimePlatform();
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  RtlGetVersion(&VersionInformation);
  LOBYTE(v0) = v23 != 1;
  *((_DWORD *)Heap + 142) = v0 + 1;
  return Heap;
}

```

## disassembly

```asm
0x1800a77cc  push    rbx
0x1800a77ce  push    rsi
0x1800a77cf  push    rdi
0x1800a77d0  push    r12
0x1800a77d2  push    r15
0x1800a77d4  sub     rsp, 3A0h
0x1800a77db  mov     rax, cs:__security_cookie
0x1800a77e2  xor     rax, rsp
0x1800a77e5  mov     [rsp+3C8h+var_38], rax
0x1800a77ed  xor     ebx, ebx
0x1800a77ef  mov     [rsp+3C8h+String2], bx
0x1800a77f7  xor     edx, edx; Val
0x1800a77f9  mov     r8d, 206h; Size
0x1800a77ff  lea     rcx, [rsp+3C8h+var_246]; void *
0x1800a7807  call    memset_0
0x1800a780c  mov     esi, ebx
0x1800a780e  mov     [rsp+3C8h+var_390], rbx
0x1800a7813  mov     rcx, gs:60h
0x1800a781c  lea     edx, [rbx+8]; Flags
0x1800a781f  mov     r8d, 6F8h; Size
0x1800a7825  mov     rcx, [rcx+30h]; HeapHandle
0x1800a7829  call    cs:__imp_RtlAllocateHeap
0x1800a782f  mov     rdi, rax
0x1800a7832  mov     [rsp+3C8h+var_380], rax
0x1800a7837  test    rax, rax
0x1800a783a  jnz     short loc_1800A785F
0x1800a783c  lea     r9, aFailedToAlloca_2; "Failed to allocate sdb context"
0x1800a7843  mov     r8d, 22Ah
0x1800a7849  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x1800a7850  lea     ecx, [rbx+1]
0x1800a7853  call    AslLogCallPrintf
0x1800a7858  xor     eax, eax
0x1800a785a  jmp     loc_1800A7B2F
0x1800a785f  mov     eax, 8664h
0x1800a7864  mov     [rdi+248h], ax
0x1800a786b  mov     [rsp+3C8h+var_398], ax
0x1800a7870  lea     r9, [rsp+3C8h+var_398]
0x1800a7875  mov     r8d, 1
0x1800a787b  lea     rcx, [rsp+3C8h+String2]
0x1800a7883  call    SdbGetPathSystemSdb
0x1800a7888  test    eax, eax
0x1800a788a  jnz     short loc_1800A78AF
0x1800a788c  lea     r9, aSdbgetpathsyst; "SdbGetPathSystemSdb failed to get file "...
0x1800a7893  mov     r8d, 1D2h
0x1800a7899  lea     rdx, aSdbpresolveini; "SdbpResolveInitSdbPath"
0x1800a78a0  lea     ecx, [rax+1]
0x1800a78a3  call    AslLogCallPrintf
0x1800a78a8  mov     eax, 0C0000001h
0x1800a78ad  jmp     short loc_1800A78B1
0x1800a78af  mov     eax, ebx
0x1800a78b1  test    eax, eax
0x1800a78b3  jns     short loc_1800A78E0
0x1800a78b5  mov     dword ptr [rsp+3C8h+var_3A8], eax
0x1800a78b9  lea     r9, aSdbpresolveini_0; "SdbpResolveInitSdbPath failed to resolv"...
0x1800a78c0  mov     r8d, 239h
0x1800a78c6  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x1800a78cd  mov     ecx, 1
0x1800a78d2  call    AslLogCallPrintf
0x1800a78d7  lea     r15, [rdi+8]
0x1800a78db  jmp     loc_1800A7A4D
0x1800a78e0  mov     [rsp+3C8h+var_388], ebx
0x1800a78e4  xor     r8d, r8d
0x1800a78e7  lea     rcx, [rsp+3C8h+String2]
0x1800a78ef  call    SdbOpenDatabaseEx
0x1800a78f4  mov     [rdi+8], rax
0x1800a78f8  jmp     short loc_1800A790E
0x1800a78fa  mov     rdi, [rsp+3C8h+var_380]
0x1800a78ff  mov     qword ptr [rdi+8], 0
0x1800a7907  xor     ebx, ebx
0x1800a7909  mov     rsi, [rsp+3C8h+var_390]
0x1800a790e  lea     r15, [rdi+8]
0x1800a7912  mov     [rsp+3C8h+var_378], r15
0x1800a7917  mov     rax, [r15]
0x1800a791a  test    rax, rax
0x1800a791d  jnz     short loc_1800A7931
0x1800a791f  lea     r9, aUnableToOpenMa; "Unable to open main database %S"
0x1800a7926  mov     r8d, 255h
0x1800a792c  jmp     loc_1800A7A2F
0x1800a7931  mov     [rdi+38h], rax
0x1800a7935  mov     dword ptr [rdi+40h], 3
0x1800a793c  movups  xmm0, xmmword ptr [rax+1Ch]
0x1800a7940  movdqu  xmmword ptr [rdi+28h], xmm0
0x1800a7945  lea     r12, [rdi+24h]
0x1800a7949  mov     [rsp+3C8h+var_370], r12
0x1800a794e  or      dword ptr [r12], 1
0x1800a7953  lea     rdx, [rsp+3C8h+String2]
0x1800a795b  lea     rcx, [rsp+3C8h+var_390]
0x1800a7960  call    SdbGetMergeStubPath
0x1800a7965  cmp     eax, 0C0000034h
0x1800a796a  jz      loc_1800A7ABE
0x1800a7970  test    eax, eax
0x1800a7972  jns     short loc_1800A79A9
0x1800a7974  lea     rax, [rsp+3C8h+String2]
0x1800a797c  mov     [rsp+3C8h+var_3A8], rax
0x1800a7981  lea     r9, aUnableToFindMe; "Unable to find merge stub database for "...
0x1800a7988  mov     r8d, 276h
0x1800a798e  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x1800a7995  mov     ecx, 1
0x1800a799a  call    AslLogCallPrintf
0x1800a799f  mov     rsi, [rsp+3C8h+var_390]
0x1800a79a4  jmp     loc_1800A7A4D
0x1800a79a9  mov     rax, [r15]
0x1800a79ac  test    rax, rax
0x1800a79af  jz      short loc_1800A79D7
0x1800a79b1  mov     rcx, [rax]
0x1800a79b4  test    rcx, rcx
0x1800a79b7  jz      short loc_1800A79D7
0x1800a79b9  cmp     [rcx], rbx
0x1800a79bc  jz      short loc_1800A79D7
0x1800a79be  lea     rdx, [rsp+3C8h+String2]; String2
0x1800a79c6  mov     rcx, [rcx]; String1
0x1800a79c9  call    _wcsicmp
0x1800a79ce  mov     ecx, ebx
0x1800a79d0  test    eax, eax
0x1800a79d2  setnz   cl
0x1800a79d5  jmp     short loc_1800A79D9
0x1800a79d7  mov     ecx, ebx
0x1800a79d9  test    ecx, ecx
0x1800a79db  jnz     loc_1800A7ABE
0x1800a79e1  mov     [rsp+3C8h+var_388], ebx
0x1800a79e5  xor     r8d, r8d
0x1800a79e8  mov     rsi, [rsp+3C8h+var_390]
0x1800a79ed  mov     rcx, rsi
0x1800a79f0  call    SdbOpenDatabaseEx
0x1800a79f5  mov     [rdi+10h], rax
0x1800a79f9  jmp     short loc_1800A7A19
0x1800a79fb  mov     rdi, [rsp+3C8h+var_380]
0x1800a7a00  mov     qword ptr [rdi+10h], 0
0x1800a7a08  xor     ebx, ebx
0x1800a7a0a  mov     rsi, [rsp+3C8h+var_390]
0x1800a7a0f  mov     r15, [rsp+3C8h+var_378]
0x1800a7a14  mov     r12, [rsp+3C8h+var_370]
0x1800a7a19  mov     rax, [rdi+10h]
0x1800a7a1d  test    rax, rax
0x1800a7a20  jnz     short loc_1800A7AA0
0x1800a7a22  lea     r9, aUnableToOpenMe; "Unable to open merge stub database %S"
0x1800a7a29  mov     r8d, 29Ah
0x1800a7a2f  lea     rax, [rsp+3C8h+String2]
0x1800a7a37  mov     [rsp+3C8h+var_3A8], rax
0x1800a7a3c  lea     rdx, aSdbinitdatabas; "SdbInitDatabaseEx"
0x1800a7a43  mov     ecx, 1
0x1800a7a48  call    AslLogCallPrintf
0x1800a7a4d  cmp     [r15], rbx
0x1800a7a50  jz      short loc_1800A7A5A
0x1800a7a52  mov     rcx, [r15]
0x1800a7a55  call    SdbCloseDatabaseRead
0x1800a7a5a  mov     rcx, [rdi+10h]
0x1800a7a5e  test    rcx, rcx
0x1800a7a61  jz      short loc_1800A7A68
0x1800a7a63  call    SdbCloseDatabaseRead
0x1800a7a68  mov     rcx, gs:60h
0x1800a7a71  mov     rdx, rdi
0x1800a7a74  mov     rcx, [rcx+30h]
0x1800a7a78  call    AslFree
0x1800a7a7d  test    rsi, rsi
0x1800a7a80  jz      loc_1800A7858
0x1800a7a86  mov     rcx, gs:60h
0x1800a7a8f  mov     rdx, rsi
0x1800a7a92  mov     rcx, [rcx+30h]
0x1800a7a96  call    AslFree
0x1800a7a9b  jmp     loc_1800A7858
0x1800a7aa0  mov     [rdi+78h], rax
0x1800a7aa4  mov     dword ptr [rdi+80h], 3
0x1800a7aae  movups  xmm0, xmmword ptr [rax+1Ch]
0x1800a7ab2  movdqu  xmmword ptr [rdi+68h], xmm0
0x1800a7ab7  or      dword ptr [r12], 4
0x1800a7abc  jmp     short loc_1800A7AC7
0x1800a7abe  mov     [rdi+10h], rbx
0x1800a7ac2  mov     rsi, [rsp+3C8h+var_390]
0x1800a7ac7  test    rsi, rsi
0x1800a7aca  jz      short loc_1800A7AE1
0x1800a7acc  mov     rcx, gs:60h
0x1800a7ad5  mov     rdx, rsi
0x1800a7ad8  mov     rcx, [rcx+30h]
0x1800a7adc  call    AslFree
0x1800a7ae1  mov     rcx, rdi
0x1800a7ae4  call    SdbpInitializeMatchers
0x1800a7ae9  call    SdbpGetBinaryRuntimePlatform
0x1800a7aee  mov     [rdi+228h], eax
0x1800a7af4  xor     edx, edx; Val
0x1800a7af6  mov     r8d, 118h; Size
0x1800a7afc  lea     rcx, [rsp+3C8h+VersionInformation.dwMajorVersion]; void *
0x1800a7b01  call    memset_0
0x1800a7b06  mov     [rsp+3C8h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800a7b0e  lea     rcx, [rsp+3C8h+VersionInformation]; lpVersionInformation
0x1800a7b13  call    cs:__imp_RtlGetVersion
0x1800a7b19  cmp     [rsp+3C8h+var_24E], 1
0x1800a7b21  setnz   bl
0x1800a7b24  inc     ebx
0x1800a7b26  mov     [rdi+238h], ebx
0x1800a7b2c  mov     rax, rdi
0x1800a7b2f  mov     rcx, [rsp+3C8h+var_38]
0x1800a7b37  xor     rcx, rsp; StackCookie
0x1800a7b3a  call    __security_check_cookie
0x1800a7b3f  add     rsp, 3A0h
0x1800a7b46  pop     r15
0x1800a7b48  pop     r12
0x1800a7b4a  pop     rdi
0x1800a7b4b  pop     rsi
0x1800a7b4c  pop     rbx
0x1800a7b4d  retn
0x1800cab37  push    rbp
0x1800cab39  sub     rsp, 30h
0x1800cab3d  mov     rbp, rdx
0x1800cab40  call    ShimExceptionHandler
0x1800cab45  nop
0x1800cab46  add     rsp, 30h
0x1800cab4a  pop     rbp
0x1800cab4b  retn
0x1800cab4d  push    rbp
0x1800cab4f  sub     rsp, 30h
0x1800cab53  mov     rbp, rdx
0x1800cab56  call    ShimExceptionHandler
0x1800cab5b  nop
0x1800cab5c  add     rsp, 30h
0x1800cab60  pop     rbp
0x1800cab61  retn
```
