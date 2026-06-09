# PropMgrClient_LookupProp

- ea: `0x18000ec30`
- end: `0x18000f2a6`
- name: `PropMgrClient_LookupProp`
- size: `1654`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x18000ec30`
- `0x18000f940`
- `0x18000fb10`
- `0x18001e4c0`
- `0x18001f024`
- `0x180047fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f299`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f299`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ee07`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f181`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000ee07`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000f181`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ee45`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ee9b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f1bb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f211`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ee45`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000ee9b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f1bb`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x18000f211`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000efb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000efb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f229`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f289`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000edcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f13b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f272`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000edcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ef09`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f13b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f272`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f280`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ed22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f08c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f1de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ed22`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f08c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f1de`
- `USER32!FindWindowW` at `0x18000ef9c`
- `USER32!FindWindowW` at `0x18000ef9c`
- `USER32!GetPropW` at `0x18000edc1`
- `USER32!GetPropW` at `0x18000f12f`
- `USER32!GetPropW` at `0x18000edc1`
- `USER32!GetPropW` at `0x18000f12f`
- `USER32!GetWindowThreadProcessId` at `0x18000edec`
- `USER32!GetWindowThreadProcessId` at `0x18000f16a`
- `USER32!GetWindowThreadProcessId` at `0x18000edec`
- `USER32!GetWindowThreadProcessId` at `0x18000f16a`

## pseudocode

```c
__int64 __fastcall PropMgrClient_LookupProp(GUID *a1, int a2, struct _GUID *a3, struct tagVARIANT *a4)
{
  struct _GUID v4; // xmm0
  struct tagVARIANT *v5; // r15
  unsigned __int8 *v7; // r12
  unsigned int i; // r8d
  __int64 v9; // rdx
  __int64 v10; // rax
  struct _GUID v11; // xmm6
  int v12; // r14d
  unsigned int *v13; // rdi
  HWND WindowW; // rsi
  WCHAR *v15; // rax
  WCHAR *v16; // rbx
  _WORD *v17; // rcx
  unsigned __int8 *v18; // rdx
  int v19; // r8d
  unsigned __int64 v20; // rax
  HANDLE PropW; // r15
  HANDLE v22; // rbx
  HLOCAL v23; // rsi
  void *v24; // rcx
  __int64 v25; // rcx
  unsigned int PropertyFromEntry; // ebx
  unsigned int v28; // eax
  HWND v29; // rsi
  WCHAR *v30; // rax
  WCHAR *v31; // rdi
  _WORD *v32; // rbx
  char *Data4; // rdx
  char v34; // cl
  unsigned __int64 v35; // rax
  HANDLE v36; // r14
  HANDLE v37; // rbx
  HLOCAL v38; // rdi
  void *v39; // rcx
  __int64 v40; // rcx
  unsigned int Buffer; // [rsp+40h] [rbp-C0h] BYREF
  DWORD dwProcessId; // [rsp+44h] [rbp-BCh] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  struct tagVARIANT *Buf2; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID v46; // [rsp+70h] [rbp-90h] BYREF
  wchar_t WindowName[64]; // [rsp+80h] [rbp-80h] BYREF

  v4 = *a3;
  v5 = a4;
  Buf2 = a4;
  Buf1 = v4;
  v7 = (unsigned __int8 *)a1;
  for ( i = 0; i < 0xC; ++i )
  {
    v9 = 3LL * (int)i;
    a1 = off_18004CAA0[v9];
    v10 = *(_QWORD *)&a1->Data1 - *(_QWORD *)&v4.Data1;
    if ( *(_QWORD *)&a1->Data1 == *(_QWORD *)&v4.Data1 )
      v10 = *(_QWORD *)a1->Data4 - *(_QWORD *)v4.Data4;
    if ( !v10 )
    {
      _mm_lfence();
      v11 = **(GUID **)((char *)&off_18004CAA8 + v9 * 8);
      goto LABEL_8;
    }
  }
  v11 = v4;
LABEL_8:
  v12 = 8;
  v13 = (unsigned int *)(v7 + 4);
  if ( a2 != 16 )
    goto LABEL_63;
  if ( *(_DWORD *)v7 == -2147483647 )
  {
    WindowW = (HWND)(int)*v13;
  }
  else
  {
    if ( *(_DWORD *)v7 != -2147483646 )
      goto LABEL_63;
    if ( swprintf_s(WindowName, 0x40u, L"MSAA_DA_%lx", *v13) == -1 )
    {
      SetLastError(0x57u);
      goto LABEL_63;
    }
    WindowW = FindWindowW(L"MSAA_DA_Class", WindowName);
  }
  if ( WindowW )
  {
    v15 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
    v16 = v15;
    if ( !v15 )
    {
LABEL_36:
      PropertyFromEntry = 0;
      goto LABEL_38;
    }
    v17 = v15 + 5;
    *(_QWORD *)v15 = *(_QWORD *)L"MSAA_";
    v15[4] = aMsaa[4];
    if ( *(_DWORD *)v7 == -2147483647 )
    {
      *v17 = 42;
      v18 = v7 + 8;
      v17 = v15 + 6;
      v19 = 8;
    }
    else
    {
      v19 = 16;
      v18 = v7;
    }
    do
    {
      v17 += 2;
      v20 = (unsigned __int64)*v18++ >> 4;
      *(v17 - 2) = a0123456789abcd[v20];
      *(v17 - 1) = a0123456789abcd[*(v18 - 1) & 0xF];
      --v19;
    }
    while ( v19 );
    *v17 = 0;
    PropW = GetPropW(WindowW, v16);
    LocalFree(v16);
    if ( !PropW
      || (dwProcessId = 0, GetWindowThreadProcessId(WindowW, &dwProcessId), !dwProcessId)
      || (v22 = OpenProcess(0x10u, 0, dwProcessId)) == 0 )
    {
LABEL_35:
      v5 = Buf2;
      goto LABEL_36;
    }
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(v22, PropW, &Buffer, 4u, &NumberOfBytesRead) && NumberOfBytesRead == 4 )
    {
      v23 = LocalAlloc(0x40u, Buffer);
      v24 = v22;
      if ( !v23 )
      {
LABEL_34:
        CloseHandle(v24);
        goto LABEL_35;
      }
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(v22, PropW, v23, Buffer, &NumberOfBytesRead) && NumberOfBytesRead == Buffer )
      {
        CloseHandle(v22);
        v5 = Buf2;
        *(_QWORD *)Buf1.Data4 = Buffer;
        *(_QWORD *)&Buf1.Data1 = v23;
        v46 = v11;
        PropertyFromEntry = MapReaderMgr::_ReadPropertyFromEntry(
                              v25,
                              (__int64 *)&Buf1,
                              (__int64)v7,
                              0x10u,
                              (__int128 *)&v46,
                              0,
                              Buf2);
        LocalFree(v23);
        if ( PropertyFromEntry )
          return PropertyFromEntry;
        goto LABEL_37;
      }
      LocalFree(v23);
    }
    v24 = v22;
    goto LABEL_34;
  }
LABEL_63:
  PropertyFromEntry = 0;
LABEL_37:
  if ( a2 != 16 )
    return PropertyFromEntry;
LABEL_38:
  if ( *(_DWORD *)v7 == -2147483647 && *((_DWORD *)v7 + 3) )
  {
    v28 = *((_DWORD *)v7 + 2);
    v29 = (HWND)(int)*v13;
    Buf1.Data1 = -2147483647;
    *(_DWORD *)&Buf1.Data2 = (_DWORD)v29;
    *(_QWORD *)Buf1.Data4 = v28;
    if ( !(_DWORD)v29 )
      return 0;
    v30 = (WCHAR *)LocalAlloc(0x40u, 0x4Cu);
    v31 = v30;
    if ( !v30 )
      return 0;
    *(_QWORD *)v30 = *(_QWORD *)L"MSAA_";
    v32 = v30 + 5;
    v30[4] = aMsaa[4];
    LODWORD(Buf2) = -2147483647;
    if ( !memcmp_0(&Buf1, &Buf2, 4u) )
    {
      *v32 = 42;
      Data4 = (char *)Buf1.Data4;
      v32 = v31 + 6;
    }
    else
    {
      v12 = 16;
      Data4 = (char *)&Buf1;
    }
    do
    {
      v34 = *Data4;
      v32 += 2;
      v35 = (unsigned __int8)*Data4++;
      *(v32 - 2) = a0123456789abcd[v35 >> 4];
      *(v32 - 1) = a0123456789abcd[v34 & 0xF];
      --v12;
    }
    while ( v12 );
    *v32 = 0;
    v36 = GetPropW(v29, v31);
    LocalFree(v31);
    if ( !v36 )
      return 0;
    dwProcessId = 0;
    GetWindowThreadProcessId(v29, &dwProcessId);
    if ( !dwProcessId )
      return 0;
    v37 = OpenProcess(0x10u, 0, dwProcessId);
    if ( !v37 )
      return 0;
    Buffer = 0;
    NumberOfBytesRead = 0;
    if ( ReadProcessMemory(v37, v36, &Buffer, 4u, &NumberOfBytesRead) && NumberOfBytesRead == 4 )
    {
      v38 = LocalAlloc(0x40u, Buffer);
      v39 = v37;
      if ( !v38 )
      {
LABEL_61:
        CloseHandle(v39);
        return 0;
      }
      NumberOfBytesRead = 0;
      if ( ReadProcessMemory(v37, v36, v38, Buffer, &NumberOfBytesRead) && NumberOfBytesRead == Buffer )
      {
        CloseHandle(v37);
        *(_QWORD *)Buf1.Data4 = Buffer;
        *(_QWORD *)&Buf1.Data1 = v38;
        v46 = v11;
        PropertyFromEntry = MapReaderMgr::_ReadPropertyFromEntry(
                              v40,
                              (__int64 *)&Buf1,
                              (__int64)v7,
                              0x10u,
                              (__int128 *)&v46,
                              1,
                              v5);
        LocalFree(v38);
        return PropertyFromEntry;
      }
      LocalFree(v38);
    }
    v39 = v37;
    goto LABEL_61;
  }
  if ( *(_DWORD *)v7 == -2147483646 && *((_DWORD *)v7 + 3) )
  {
    *(_DWORD *)&Buf1.Data2 = *v13;
    *(_QWORD *)Buf1.Data4 = *((unsigned int *)v7 + 2);
    Buf1.Data1 = -2147483646;
    v46 = v11;
    return MapReaderMgr::_LookupProp((MapReaderMgr *)a1, (const unsigned __int8 *)&Buf1, 16, v7, 0x10u, &v46, 1, v5);
  }
  return PropertyFromEntry;
}

```

## disassembly

```asm
0x18000ec30  push    rbp
0x18000ec32  push    rbx
0x18000ec33  push    r12
0x18000ec35  push    r13
0x18000ec37  push    r14
0x18000ec39  push    r15
0x18000ec3b  lea     rbp, [rsp-38h]
0x18000ec40  sub     rsp, 138h
0x18000ec47  mov     rax, cs:__security_cookie
0x18000ec4e  xor     rax, rsp
0x18000ec51  mov     [rbp+60h+var_60], rax
0x18000ec55  movups  xmm0, xmmword ptr [r8]
0x18000ec59  mov     r15, r9
0x18000ec5c  mov     [rsp+160h+Buf2], r9
0x18000ec61  mov     r13d, edx
0x18000ec64  movaps  [rsp+160h+var_50], xmm6
0x18000ec6c  movaps  [rsp+160h+Buf1], xmm0
0x18000ec71  lea     rbx, __ImageBase
0x18000ec78  mov     r9, qword ptr [rsp+160h+Buf1+8]
0x18000ec7d  mov     r12, rcx
0x18000ec80  mov     r10, qword ptr [rsp+160h+Buf1]
0x18000ec85  xor     r8d, r8d
0x18000ec88  nop     dword ptr [rax+rax+00000000h]
0x18000ec90  cmp     r8d, 0Ch
0x18000ec94  jnb     loc_18000EF4F
0x18000ec9a  movsxd  rax, r8d
0x18000ec9d  lea     rcx, [rax+rax*2]
0x18000eca1  lea     rdx, ds:0[rcx*8]
0x18000eca9  mov     rcx, [rdx+rbx+4CAA0h]
0x18000ecb1  mov     rax, [rcx]
0x18000ecb4  sub     rax, r10
0x18000ecb7  jnz     short loc_18000ECC0
0x18000ecb9  mov     rax, [rcx+8]
0x18000ecbd  sub     rax, r9
0x18000ecc0  test    rax, rax
0x18000ecc3  jz      short loc_18000ECCA
0x18000ecc5  inc     r8d
0x18000ecc8  jmp     short loc_18000EC90
0x18000ecca  lfence
0x18000eccd  mov     rax, [rdx+rbx+4CAA8h]
0x18000ecd5  movups  xmm6, xmmword ptr [rax]
0x18000ecd8  mov     [rsp+160h+var_30], rsi
0x18000ece0  mov     r14d, 8
0x18000ece6  mov     [rsp+160h+var_38], rdi
0x18000ecee  lea     rdi, [r12+4]
0x18000ecf3  cmp     r13d, 10h
0x18000ecf7  jnz     loc_18000F29F
0x18000ecfd  mov     eax, [r12]
0x18000ed01  cmp     eax, 80000001h
0x18000ed06  jnz     loc_18000EF65
0x18000ed0c  movsxd  rsi, dword ptr [rdi]
0x18000ed0f  test    rsi, rsi
0x18000ed12  jz      loc_18000F29F
0x18000ed18  mov     edx, 4Ch ; 'L'; uBytes
0x18000ed1d  mov     ecx, 40h ; '@'; uFlags
0x18000ed22  call    cs:__imp_LocalAlloc
0x18000ed28  mov     rbx, rax
0x18000ed2b  test    rax, rax
0x18000ed2e  jz      loc_18000EFC1
0x18000ed34  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000ed3c  lea     rcx, [rbx+0Ah]
0x18000ed40  movsd   qword ptr [rax], xmm0
0x18000ed44  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000ed4b  mov     [rbx+8], ax
0x18000ed4f  cmp     dword ptr [r12], 80000001h
0x18000ed57  jnz     loc_18000EF57
0x18000ed5d  mov     word ptr [rcx], 2Ah ; '*'
0x18000ed62  lea     rdx, [r12+8]
0x18000ed67  add     rcx, 2
0x18000ed6b  mov     r8d, r14d
0x18000ed6e  lea     r9, __ImageBase
0x18000ed75  nop     word ptr [rax+rax+00000000h]
0x18000ed80  movzx   eax, byte ptr [rdx]
0x18000ed83  lea     rcx, [rcx+4]
0x18000ed87  shr     rax, 4
0x18000ed8b  lea     rdx, [rdx+1]
0x18000ed8f  movzx   eax, word ptr ds:rva a0123456789abcd[r9+rax*2]; "0123456789ABCDEF" ...
0x18000ed98  mov     [rcx-4], ax
0x18000ed9c  movzx   eax, byte ptr [rdx-1]
0x18000eda0  and     eax, 0Fh
0x18000eda3  movzx   eax, word ptr ds:rva a0123456789abcd[r9+rax*2]; "0123456789ABCDEF" ...
0x18000edac  mov     [rcx-2], ax
0x18000edb0  add     r8d, 0FFFFFFFFh
0x18000edb4  jnz     short loc_18000ED80
0x18000edb6  xor     eax, eax
0x18000edb8  mov     rdx, rbx; lpString
0x18000edbb  mov     [rcx], ax
0x18000edbe  mov     rcx, rsi; hWnd
0x18000edc1  call    cs:__imp_GetPropW
0x18000edc7  mov     rcx, rbx; hMem
0x18000edca  mov     r15, rax
0x18000edcd  call    cs:__imp_LocalFree
0x18000edd3  test    r15, r15
0x18000edd6  jz      loc_18000EFBC
0x18000eddc  lea     rdx, [rsp+160h+dwProcessId]; lpdwProcessId
0x18000ede1  mov     [rsp+160h+dwProcessId], 0
0x18000ede9  mov     rcx, rsi; hWnd
0x18000edec  call    cs:__imp_GetWindowThreadProcessId
0x18000edf2  mov     r8d, [rsp+160h+dwProcessId]; dwProcessId
0x18000edf7  test    r8d, r8d
0x18000edfa  jz      loc_18000EFBC
0x18000ee00  xor     edx, edx; bInheritHandle
0x18000ee02  mov     ecx, 10h; dwDesiredAccess
0x18000ee07  call    cs:__imp_OpenProcess
0x18000ee0d  mov     rbx, rax
0x18000ee10  test    rax, rax
0x18000ee13  jz      loc_18000EFBC
0x18000ee19  lea     rax, [rsp+160h+NumberOfBytesRead]
0x18000ee1e  mov     [rsp+160h+Buffer], 0
0x18000ee26  mov     r9d, 4; nSize
0x18000ee2c  mov     [rsp+160h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000ee31  lea     r8, [rsp+160h+Buffer]; lpBuffer
0x18000ee36  mov     [rsp+160h+NumberOfBytesRead], 0
0x18000ee3f  mov     rdx, r15; lpBaseAddress
0x18000ee42  mov     rcx, rbx; hProcess
0x18000ee45  call    cs:__imp_ReadProcessMemory
0x18000ee4b  test    eax, eax
0x18000ee4d  jz      loc_18000EFB3
0x18000ee53  cmp     [rsp+160h+NumberOfBytesRead], 4
0x18000ee59  jnz     loc_18000EFB3
0x18000ee5f  mov     edx, [rsp+160h+Buffer]; uBytes
0x18000ee63  mov     ecx, 40h ; '@'; uFlags
0x18000ee68  call    cs:__imp_LocalAlloc
0x18000ee6e  mov     rsi, rax
0x18000ee71  mov     rcx, rbx; hProcess
0x18000ee74  test    rax, rax
0x18000ee77  jz      loc_18000EFB6
0x18000ee7d  mov     r9d, [rsp+160h+Buffer]; nSize
0x18000ee82  lea     rax, [rsp+160h+NumberOfBytesRead]
0x18000ee87  mov     r8, rsi; lpBuffer
0x18000ee8a  mov     [rsp+160h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x18000ee8f  mov     rdx, r15; lpBaseAddress
0x18000ee92  mov     [rsp+160h+NumberOfBytesRead], 0
0x18000ee9b  call    cs:__imp_ReadProcessMemory
0x18000eea1  test    eax, eax
0x18000eea3  jz      loc_18000EFAA
0x18000eea9  mov     eax, [rsp+160h+Buffer]
0x18000eead  cmp     [rsp+160h+NumberOfBytesRead], rax
0x18000eeb2  jnz     loc_18000EFAA
0x18000eeb8  mov     rcx, rbx; hObject
0x18000eebb  call    cs:__imp_CloseHandle
0x18000eec1  mov     eax, [rsp+160h+Buffer]
0x18000eec5  lea     rdx, [rsp+160h+Buf1]
0x18000eeca  mov     r15, [rsp+160h+Buf2]
0x18000eecf  mov     r9d, 10h
0x18000eed5  mov     qword ptr [rsp+160h+Buf1+8], rax
0x18000eeda  mov     r8, r12
0x18000eedd  lea     rax, [rsp+160h+var_F0]
0x18000eee2  mov     qword ptr [rsp+160h+var_130], r15
0x18000eee7  mov     dword ptr [rsp+160h+var_138], 0
0x18000eeef  mov     [rsp+160h+lpNumberOfBytesRead], rax
0x18000eef4  mov     qword ptr [rsp+160h+Buf1], rsi
0x18000eef9  movdqa  xmmword ptr [rsp+160h+var_F0.Data1], xmm6
0x18000eeff  call    ?_ReadPropertyFromEntry@MapReaderMgr@@AEAAHVMemStream@@PEBEKU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_ReadPropertyFromEntry(MemStream,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000ef04  mov     rcx, rsi; hMem
0x18000ef07  mov     ebx, eax
0x18000ef09  call    cs:__imp_LocalFree
0x18000ef0f  test    ebx, ebx
0x18000ef11  jz      loc_18000EFC5
0x18000ef17  mov     eax, ebx
0x18000ef19  movaps  xmm6, [rsp+160h+var_50]
0x18000ef21  mov     rdi, [rsp+160h+var_38]
0x18000ef29  mov     rsi, [rsp+160h+var_30]
0x18000ef31  mov     rcx, [rbp+60h+var_60]
0x18000ef35  xor     rcx, rsp; StackCookie
0x18000ef38  call    __security_check_cookie
0x18000ef3d  add     rsp, 138h
0x18000ef44  pop     r15
0x18000ef46  pop     r14
0x18000ef48  pop     r13
0x18000ef4a  pop     r12
0x18000ef4c  pop     rbx
0x18000ef4d  pop     rbp
0x18000ef4e  retn
0x18000ef4f  movups  xmm6, xmm0
0x18000ef52  jmp     loc_18000ECD8
0x18000ef57  mov     r8d, 10h
0x18000ef5d  mov     rdx, r12
0x18000ef60  jmp     loc_18000ED6E
0x18000ef65  cmp     eax, 80000002h
0x18000ef6a  jnz     loc_18000F29F
0x18000ef70  mov     r9d, [rdi]
0x18000ef73  lea     r8, aMsaaDaLx; "MSAA_DA_%lx"
0x18000ef7a  mov     edx, 40h ; '@'; BufferCount
0x18000ef7f  lea     rcx, [rbp+60h+WindowName]; Buffer
0x18000ef83  call    swprintf_s
0x18000ef88  cmp     eax, 0FFFFFFFFh
0x18000ef8b  jz      loc_18000F294
0x18000ef91  lea     rdx, [rbp+60h+WindowName]; lpWindowName
0x18000ef95  lea     rcx, ClassName; "MSAA_DA_Class"
0x18000ef9c  call    cs:__imp_FindWindowW
0x18000efa2  mov     rsi, rax
0x18000efa5  jmp     loc_18000ED0F
0x18000efaa  mov     rcx, rsi; hMem
0x18000efad  call    cs:__imp_LocalFree
0x18000efb3  mov     rcx, rbx; hObject
0x18000efb6  call    cs:__imp_CloseHandle
0x18000efbc  mov     r15, [rsp+160h+Buf2]
0x18000efc1  xor     ebx, ebx
0x18000efc3  jmp     short loc_18000EFCF
0x18000efc5  cmp     r13d, 10h
0x18000efc9  jnz     loc_18000EF17
0x18000efcf  cmp     dword ptr [r12], 80000001h
0x18000efd7  jnz     short loc_18000EFE1
0x18000efd9  cmp     dword ptr [r12+0Ch], 0
0x18000efdf  jnz     short loc_18000F057
0x18000efe1  cmp     dword ptr [r12], 80000002h
0x18000efe9  jnz     loc_18000EF17
0x18000efef  cmp     dword ptr [r12+0Ch], 0
0x18000eff5  jz      loc_18000EF17
0x18000effb  mov     eax, [rdi]
0x18000effd  lea     rdx, [rsp+160h+Buf1]; unsigned __int8 *
0x18000f002  mov     dword ptr [rsp+160h+Buf1+4], eax
0x18000f006  mov     r9, r12; unsigned __int8 *
0x18000f009  mov     eax, [r12+8]
0x18000f00e  mov     r8d, 10h; unsigned int
0x18000f014  mov     [rsp+160h+var_128], r15; struct tagVARIANT *
0x18000f019  mov     dword ptr [rsp+160h+Buf1+8], eax
0x18000f01d  lea     rax, [rsp+160h+var_F0]
0x18000f022  mov     [rsp+160h+var_130], 1; int
0x18000f02a  mov     [rsp+160h+var_138], rax; struct _GUID *
0x18000f02f  mov     dword ptr [rsp+160h+lpNumberOfBytesRead], 10h; unsigned int
0x18000f037  mov     dword ptr [rsp+160h+Buf1], 80000002h
0x18000f03f  mov     dword ptr [rsp+160h+Buf1+0Ch], 0
0x18000f047  movdqa  xmmword ptr [rsp+160h+var_F0.Data1], xmm6
0x18000f04d  call    ?_LookupProp@MapReaderMgr@@AEAAHPEBEK0KU_GUID@@HPEAUtagVARIANT@@@Z; MapReaderMgr::_LookupProp(uchar const *,ulong,uchar const *,ulong,_GUID,int,tagVARIANT *)
0x18000f052  jmp     loc_18000EF19
0x18000f057  movsxd  rcx, dword ptr [rdi]
0x18000f05a  mov     eax, [r12+8]
0x18000f05f  mov     rsi, rcx
0x18000f062  mov     dword ptr [rsp+160h+Buf1], 80000001h
0x18000f06a  mov     dword ptr [rsp+160h+Buf1+4], ecx
0x18000f06e  mov     dword ptr [rsp+160h+Buf1+8], eax
0x18000f072  mov     dword ptr [rsp+160h+Buf1+0Ch], 0
0x18000f07a  test    ecx, ecx
0x18000f07c  jz      loc_18000F146
0x18000f082  mov     edx, 4Ch ; 'L'; uBytes
0x18000f087  mov     ecx, 40h ; '@'; uFlags
0x18000f08c  call    cs:__imp_LocalAlloc
0x18000f092  mov     rdi, rax
0x18000f095  test    rax, rax
0x18000f098  jz      loc_18000F146
0x18000f09e  movsd   xmm0, qword ptr cs:aMsaa; "MSAA_"
0x18000f0a6  lea     rdx, [rsp+160h+Buf2]; Buf2
0x18000f0ab  movsd   qword ptr [rax], xmm0
0x18000f0af  lea     rcx, [rsp+160h+Buf1]; Buf1
0x18000f0b4  movzx   eax, word ptr cs:aMsaa+8; "_"
0x18000f0bb  lea     rbx, [rdi+0Ah]
0x18000f0bf  mov     r8d, 4; Size
0x18000f0c5  mov     [rdi+8], ax
0x18000f0c9  mov     dword ptr [rsp+160h+Buf2], 80000001h
0x18000f0d1  call    memcmp_0
0x18000f0d6  test    eax, eax
0x18000f0d8  jnz     short loc_18000F14D
0x18000f0da  mov     word ptr [rbx], 2Ah ; '*'
0x18000f0df  lea     rdx, [rsp+160h+Buf1+8]
0x18000f0e4  add     rbx, 2
0x18000f0e8  lea     r8, __ImageBase
0x18000f0ef  nop
0x18000f0f0  movzx   ecx, byte ptr [rdx]
0x18000f0f3  lea     rbx, [rbx+4]
0x18000f0f7  mov     eax, ecx
0x18000f0f9  lea     rdx, [rdx+1]
0x18000f0fd  shr     rax, 4
0x18000f101  and     ecx, 0Fh
0x18000f104  movzx   eax, word ptr ds:rva a0123456789abcd[r8+rax*2]; "0123456789ABCDEF" ...
0x18000f10d  mov     [rbx-4], ax
0x18000f111  movzx   eax, word ptr ds:rva a0123456789abcd[r8+rcx*2]; "0123456789ABCDEF" ...
0x18000f11a  mov     [rbx-2], ax
0x18000f11e  add     r14d, 0FFFFFFFFh
0x18000f122  jnz     short loc_18000F0F0
0x18000f124  xor     eax, eax
0x18000f126  mov     rdx, rdi; lpString
0x18000f129  mov     rcx, rsi; hWnd
0x18000f12c  mov     [rbx], ax
0x18000f12f  call    cs:__imp_GetPropW
0x18000f135  mov     rcx, rdi; hMem
0x18000f138  mov     r14, rax
0x18000f13b  call    cs:__imp_LocalFree
0x18000f141  test    r14, r14
0x18000f144  jnz     short loc_18000F15A
0x18000f146  xor     ebx, ebx
0x18000f148  jmp     loc_18000EF17
0x18000f14d  mov     r14d, 10h
0x18000f153  lea     rdx, [rsp+160h+Buf1]
0x18000f158  jmp     short loc_18000F0E8
0x18000f15a  lea     rdx, [rsp+160h+dwProcessId]; lpdwProcessId
0x18000f15f  mov     [rsp+160h+dwProcessId], 0
0x18000f167  mov     rcx, rsi; hWnd
0x18000f16a  call    cs:__imp_GetWindowThreadProcessId
0x18000f170  mov     r8d, [rsp+160h+dwProcessId]; dwProcessId
0x18000f175  test    r8d, r8d
0x18000f178  jz      short loc_18000F146
0x18000f17a  xor     edx, edx; bInheritHandle
0x18000f17c  mov     ecx, 10h; dwDesiredAccess
0x18000f181  call    cs:__imp_OpenProcess
0x18000f187  mov     rbx, rax
0x18000f18a  test    rax, rax
0x18000f18d  jz      short loc_18000F146
0x18000f18f  lea     rax, [rsp+160h+NumberOfBytesRead]
  ... truncated ...
```
