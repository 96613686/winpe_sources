# AslFileMappingCreate

- ea: `0x1800614b8`
- end: `0x18006170c`
- name: `AslFileMappingCreate`
- size: `596`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x180040ee0`
- `0x180072eac`
- `0x1800a91d0`
- `0x1800a9c60`

## callees

- `0x18004281c`
- `0x1800614b8`
- `0x18006340c`
- `0x180075fa0`
- `0x180076e9c`
- `0x1800c05a0`
- `0x1800c0a94`
- `0x1800c0dac`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180061523`
- `ntdll!RtlInitUnicodeString` at `0x180061523`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800615a1`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800615a1`
- `ntdll!RtlAllocateHeap` at `0x180061540`
- `ntdll!RtlAllocateHeap` at `0x180061540`
- `ntdll!RtlFreeUnicodeString` at `0x1800616d8`
- `ntdll!RtlFreeUnicodeString` at `0x1800616d8`
- `ntdll!ZwQueryInformationFile` at `0x180061678`
- `ntdll!ZwQueryInformationFile` at `0x180061678`

## string_xrefs

- `0x1800615b1`: `RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]`
- `0x180061622`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x180061635`: `RtlFileMapInitializeByFilePath failed %S [%x]`
- `0x1800615c3`: `AslFileMappingCreate`
- `0x180061691`: `AslFileMappingCreate`

## pseudocode

```c
__int64 __fastcall AslFileMappingCreate(HANDLE **a1, const WCHAR *a2)
{
  HANDLE *Heap; // rax
  HANDLE *v5; // rsi
  unsigned int v6; // ebx
  NTSTATUS v7; // eax
  const char *v8; // r9
  __int64 v9; // r8
  int v10; // eax
  const char *v11; // r9
  __int64 v12; // r8
  int v13; // eax
  int v14; // ecx
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  FILE_INFORMATION_CLASS FileInformationClass[2]; // [rsp+20h] [rbp-50h]
  unsigned int v19; // [rsp+28h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-30h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+60h] [rbp-10h]

  v23 = 0;
  FileInformation = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  if ( !a2 || !*a2 || !a1 )
    return 3221225485LL;
  *a1 = 0;
  RtlInitUnicodeString(&DestinationString, a2);
  Heap = (HANDLE *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x50u);
  v5 = Heap;
  if ( Heap )
  {
    v7 = AslStringDuplicate(Heap, a2);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = "AslStringDuplicate failed [%x]";
      v9 = 123;
LABEL_22:
      FileInformationClass[0] = v7;
      AslLogCallPrintf(1, "AslFileMappingCreate", v9, v8, *(_QWORD *)FileInformationClass);
      goto LABEL_23;
    }
    if ( wcsnicmp(a2, L"\\SystemRoot\\", 0xCu) )
    {
      v10 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &DestinationString, 0, 0);
      v6 = v10;
      if ( v10 < 0 )
      {
        v19 = v10;
        v11 = "RtlDosPathNameToNtPathName_U_WithStatus failed for %S [%x]";
        v12 = 148;
LABEL_11:
        AslLogCallPrintf(1, "AslFileMappingCreate", v12, v11, a2, v19, *(_QWORD *)&DestinationString.Length);
        goto LABEL_23;
      }
    }
    v13 = RtlFileMapInitializeByNtPath(v5 + 1, &DestinationString);
    v6 = v13;
    if ( v13 >= 0 )
    {
      v23 = 0;
      IoStatusBlock = 0;
      FileInformation = 0;
      v7 = ZwQueryInformationFile(v5[1], &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      v6 = v7;
      if ( v7 >= 0 )
      {
        v6 = 0;
        v5[3] = (HANDLE)*((_QWORD *)&FileInformation + 1);
        *((_DWORD *)v5 + 14) = (*((_QWORD *)&FileInformation + 1) != 0) + 1;
        *a1 = v5;
        goto LABEL_25;
      }
      v8 = "NtQueryInformationFile failed [%x]";
      v9 = 183;
      goto LABEL_22;
    }
    if ( !(unsigned int)AslFileNotFound((unsigned int)v13) )
    {
      v15 = (unsigned int)(v14 + 1073741805);
      if ( (unsigned int)v15 > 0x30 || (v16 = 0x1000000008001LL, !_bittest64(&v16, v15)) )
      {
        if ( v6 != -1073741638 )
        {
          v19 = v6;
          v11 = "RtlFileMapInitializeByFilePath failed %S [%x]";
          v12 = 161;
          goto LABEL_11;
        }
      }
      AslLogCallPrintf(3, "AslFileMappingCreate", 163, "RtlFileMapInitializeByFilePath failed %S [%x]", a2, v6);
    }
LABEL_23:
    AslFileMappingDelete(v5);
    goto LABEL_25;
  }
  v6 = -1073741801;
LABEL_25:
  if ( DestinationString.Buffer != a2 )
    RtlFreeUnicodeString(&DestinationString);
  return v6;
}

```

## disassembly

```asm
0x1800614b8  mov     [rsp-28h+arg_10], rbx
0x1800614bd  mov     [rsp-28h+arg_18], rsi
0x1800614c2  push    rbp
0x1800614c3  push    rdi
0x1800614c4  push    r12
0x1800614c6  push    r14
0x1800614c8  push    r15
0x1800614ca  mov     rbp, rsp
0x1800614cd  sub     rsp, 70h
0x1800614d1  mov     rax, cs:__security_cookie
0x1800614d8  xor     rax, rsp
0x1800614db  mov     [rbp+var_8], rax
0x1800614df  xor     eax, eax
0x1800614e1  xorps   xmm0, xmm0
0x1800614e4  xor     r12d, r12d
0x1800614e7  mov     [rbp+var_10], rax
0x1800614eb  xorps   xmm1, xmm1
0x1800614ee  mov     rdi, rdx
0x1800614f1  mov     r14, rcx
0x1800614f4  movups  [rbp+FileInformation], xmm0
0x1800614f8  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800614fc  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x180061500  test    rdx, rdx
0x180061503  jz      loc_1800616E2
0x180061509  cmp     [rdx], r12w
0x18006150d  jz      loc_1800616E2
0x180061513  test    rcx, rcx
0x180061516  jz      loc_1800616E2
0x18006151c  mov     [rcx], r12
0x18006151f  lea     rcx, [rbp+DestinationString]; DestinationString
0x180061523  call    cs:__imp_RtlInitUnicodeString
0x180061529  mov     rcx, gs:60h
0x180061532  lea     edx, [r12+8]; Flags
0x180061537  lea     r8d, [r12+50h]; Size
0x18006153c  mov     rcx, [rcx+30h]; HeapHandle
0x180061540  call    cs:__imp_RtlAllocateHeap
0x180061546  mov     rsi, rax
0x180061549  test    rax, rax
0x18006154c  jnz     short loc_180061558
0x18006154e  mov     ebx, 0C0000017h
0x180061553  jmp     loc_1800616CE
0x180061558  mov     rdx, rdi
0x18006155b  mov     rcx, rsi
0x18006155e  call    AslStringDuplicate
0x180061563  mov     ebx, eax
0x180061565  test    eax, eax
0x180061567  jns     short loc_18006157B
0x180061569  lea     r9, aAslstringdupli_0; "AslStringDuplicate failed [%x]"
0x180061570  mov     r8d, 7Bh ; '{'
0x180061576  jmp     loc_180061691
0x18006157b  mov     r8d, 0Ch; MaxCount
0x180061581  lea     rdx, aSystemroot_2; "\\SystemRoot\\"
0x180061588  mov     rcx, rdi; String1
0x18006158b  call    _wcsnicmp
0x180061590  test    eax, eax
0x180061592  jz      short loc_1800615D9
0x180061594  xor     r9d, r9d
0x180061597  lea     rdx, [rbp+DestinationString]
0x18006159b  xor     r8d, r8d
0x18006159e  mov     rcx, rdi
0x1800615a1  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800615a7  mov     ebx, eax
0x1800615a9  test    eax, eax
0x1800615ab  jns     short loc_1800615D9
0x1800615ad  mov     [rsp+70h+var_48], eax
0x1800615b1  lea     r9, aRtldospathname_0; "RtlDosPathNameToNtPathName_U_WithStatus"...
0x1800615b8  mov     r8d, 94h
0x1800615be  mov     ecx, 1
0x1800615c3  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x1800615ca  mov     qword ptr [rsp+70h+FileInformationClass], rdi
0x1800615cf  call    AslLogCallPrintf
0x1800615d4  jmp     loc_1800616A6
0x1800615d9  lea     rdx, [rbp+DestinationString]
0x1800615dd  lea     rcx, [rsi+8]
0x1800615e1  call    RtlFileMapInitializeByNtPath
0x1800615e6  mov     ebx, eax
0x1800615e8  test    eax, eax
0x1800615ea  jns     short loc_18006164C
0x1800615ec  mov     ecx, eax
0x1800615ee  call    AslFileNotFound
0x1800615f3  test    eax, eax
0x1800615f5  jnz     loc_1800616A6
0x1800615fb  lea     eax, [rcx+3FFFFFEDh]
0x180061601  cmp     eax, 30h ; '0'
0x180061604  ja      short loc_180061616
0x180061606  mov     rcx, 1000000008001h
0x180061610  bt      rcx, rax
0x180061614  jb      short loc_180061631
0x180061616  cmp     ebx, 0C00000BAh
0x18006161c  jz      short loc_180061631
0x18006161e  mov     [rsp+70h+var_48], ebx
0x180061622  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x180061629  mov     r8d, 0A1h
0x18006162f  jmp     short loc_1800615BE
0x180061631  mov     [rsp+70h+var_48], ebx
0x180061635  lea     r9, aRtlfilemapinit; "RtlFileMapInitializeByFilePath failed %"...
0x18006163c  mov     r8d, 0A3h
0x180061642  mov     ecx, 3
0x180061647  jmp     loc_1800615C3
0x18006164c  xor     eax, eax
0x18006164e  mov     [rsp+70h+FileInformationClass], 5; FileInformationClass
0x180061656  xorps   xmm0, xmm0
0x180061659  mov     [rbp+var_10], rax
0x18006165d  xorps   xmm1, xmm1
0x180061660  lea     r8, [rbp+FileInformation]; FileInformation
0x180061664  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180061668  lea     r9d, [rax+18h]; Length
0x18006166c  movups  [rbp+FileInformation], xmm1
0x180061670  mov     rcx, [rsi+8]; FileHandle
0x180061674  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180061678  call    cs:__imp_ZwQueryInformationFile
0x18006167e  mov     ebx, eax
0x180061680  test    eax, eax
0x180061682  jns     short loc_1800616B0
0x180061684  lea     r9, aNtqueryinforma_0; "NtQueryInformationFile failed [%x]"
0x18006168b  mov     r8d, 0B7h
0x180061691  lea     rdx, aAslfilemapping_4; "AslFileMappingCreate"
0x180061698  mov     [rsp+70h+FileInformationClass], eax
0x18006169c  mov     ecx, 1
0x1800616a1  call    AslLogCallPrintf
0x1800616a6  mov     rcx, rsi
0x1800616a9  call    AslFileMappingDelete
0x1800616ae  jmp     short loc_1800616CE
0x1800616b0  mov     rax, qword ptr [rbp+FileInformation+8]
0x1800616b4  mov     ebx, r12d
0x1800616b7  mov     [rsi+18h], rax
0x1800616bb  mov     rax, qword ptr [rbp+FileInformation+8]
0x1800616bf  neg     rax
0x1800616c2  sbb     ecx, ecx
0x1800616c4  neg     ecx
0x1800616c6  inc     ecx
0x1800616c8  mov     [rsi+38h], ecx
0x1800616cb  mov     [r14], rsi
0x1800616ce  cmp     [rbp+DestinationString.Buffer], rdi
0x1800616d2  jz      short loc_1800616DE
0x1800616d4  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800616d8  call    cs:__imp_RtlFreeUnicodeString
0x1800616de  mov     eax, ebx
0x1800616e0  jmp     short loc_1800616E7
0x1800616e2  mov     eax, 0C000000Dh
0x1800616e7  mov     rcx, [rbp+var_8]
0x1800616eb  xor     rcx, rsp; StackCookie
0x1800616ee  call    __security_check_cookie
0x1800616f3  lea     r11, [rsp+70h+var_s0]
0x1800616f8  mov     rbx, [r11+40h]
0x1800616fc  mov     rsi, [r11+48h]
0x180061700  mov     rsp, r11
0x180061703  pop     r15
0x180061705  pop     r14
0x180061707  pop     r12
0x180061709  pop     rdi
0x18006170a  pop     rbp
0x18006170b  retn
```
