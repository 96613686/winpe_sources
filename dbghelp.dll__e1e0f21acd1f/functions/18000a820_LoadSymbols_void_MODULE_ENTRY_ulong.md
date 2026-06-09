# LoadSymbols(void *,_MODULE_ENTRY *,ulong)

- ea: `0x18000a820`
- end: `0x18000ad2a`
- name: `?LoadSymbols@@YAHPEAXPEAU_MODULE_ENTRY@@K@Z`
- size: `1290`
- prototype: `__int64 __fastcall(void *, struct _MODULE_ENTRY *, unsigned int)`
- caller_count: `35`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18000a340`
- `0x18000a410`
- `0x18000bd00`
- `0x180016718`
- `0x180018e6c`
- `0x18001ab14`
- `0x1801992e8`
- `0x18019e3b0`
- `0x1801a1e60`
- `0x1801a208c`
- `0x1801a2378`
- `0x1801a2968`
- `0x1801a2dd8`
- `0x1801a2f8c`
- `0x1801a3b50`
- `0x1801a3f20`
- `0x1801a4f60`
- `0x1801a5030`
- `0x1801a51c0`
- `0x1801a5790`
- `0x1801a5a40`
- `0x1801a5d30`
- `0x1801a5e50`
- `0x1801a6330`
- `0x1801a6560`
- `0x1801a6a10`
- `0x1801a6c90`
- `0x1801a7000`
- `0x1801a7540`
- `0x1801a7690`
- `0x1801a7b20`
- `0x1801a8380`
- `0x1801a8420`
- `0x1801aacd0`
- `0x1801aba9c`

## callees

- `0x18000a820`
- `0x18000aeec`
- `0x18000dfac`
- `0x18000ec34`
- `0x180016c04`
- `0x180021340`
- `0x180021374`
- `0x180027430`
- `0x1801bf360`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000aad8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000aad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aaf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a9e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a9e3`

## string_xrefs

- `0x18000ab01`: `........CreateDirectory(%u,%ws)\n`
- `0x18000ac5c`: `........CopyFile(%u,%ws,%ws)\n`

## pseudocode

```c
__int64 __fastcall LoadSymbols(void *a1, struct _MODULE_ENTRY *a2, char a3)
{
  void *v5; // rdi
  DIA **v6; // r15
  DIA *v7; // r9
  _DWORD *v8; // rbx
  int v9; // eax
  DIA *v11; // rdx
  int *v12; // r14
  __int64 v13; // rdx
  unsigned __int64 v14; // rax
  __int64 v15; // rcx
  char *v16; // rdi
  BOOL DirectoryW; // ebx
  DWORD LastError; // eax
  unsigned int (*v19)(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *); // r8
  void *v20; // r9
  int v21; // ebx
  __int64 v22; // rsi
  DWORD v23; // eax
  unsigned int v24; // edi
  int *v25; // [rsp+20h] [rbp-D8h]
  unsigned int v26; // [rsp+28h] [rbp-D0h]
  _DWORD *v27; // [rsp+B0h] [rbp-48h]
  int *v28; // [rsp+B8h] [rbp-40h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+108h] [rbp+10h] BYREF
  struct _PROCESS_ENTRY *ProcessEntry; // [rsp+118h] [rbp+20h]

  v5 = a1;
  v6 = (DIA **)((char *)a2 + 19472);
  ProcessEntry = FindProcessEntry(a1);
  v7 = *v6;
  v8 = (_DWORD *)((char *)a2 + 24164);
  v27 = (_DWORD *)((char *)a2 + 24164);
  if ( *v6 )
    *v8 = *((_DWORD *)v7 + 12);
  else
    v27 = (_DWORD *)((char *)a2 + 24164);
  if ( *v8 == 2 )
  {
    v12 = (int *)*((_QWORD *)a2 + 40);
    v28 = v12;
    if ( !v12 )
      goto LABEL_15;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)v12 + v14) );
    if ( v14 > 2 && *(_WORD *)v12 == 92 && *((_WORD *)v12 + 1) == 92 )
    {
      v15 = -1;
      do
        ++v15;
      while ( *((_WORD *)v12 + v15) );
      SystemTimeAsFileTime = 0;
      if ( (_DWORD)v15 )
      {
        while ( *((_WORD *)v12 + (unsigned int)v15) != 92 )
        {
          LODWORD(v15) = v15 - 1;
          if ( !(_DWORD)v15 )
            goto LABEL_33;
        }
        do
          ++v13;
        while ( *((_WORD *)v12 + v13) );
        if ( (unsigned int)v15 < (unsigned __int64)(v13 - 1) )
        {
          v12 = (int *)((char *)v12 + 2 * (unsigned int)v15 + 2);
          v28 = v12;
        }
      }
LABEL_33:
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v16 = (char *)a2 + 23120;
      swprintf_s(
        (wchar_t *const)a2 + 11560,
        0x209u,
        L"%ws%ws_%08X%04X%04X%02X%02X%02X%02X%02X%02X%02X%02X%X_%08X_%08X%08X",
        &qword_1802B1A00,
        v12,
        *((_DWORD *)a2 + 4959),
        *((unsigned __int16 *)a2 + 9920),
        *((unsigned __int16 *)a2 + 9921),
        *((unsigned __int8 *)a2 + 19844),
        *((unsigned __int8 *)a2 + 19845),
        *((unsigned __int8 *)a2 + 19846),
        *((unsigned __int8 *)a2 + 19847),
        *((unsigned __int8 *)a2 + 19848),
        *((unsigned __int8 *)a2 + 19849),
        *((unsigned __int8 *)a2 + 19850),
        *((unsigned __int8 *)a2 + 19851),
        *((_DWORD *)a2 + 4957),
        *((_DWORD *)ProcessEntry + 14),
        SystemTimeAsFileTime.dwHighDateTime,
        SystemTimeAsFileTime.dwLowDateTime);
      DirectoryW = CreateDirectoryW((LPCWSTR)a2 + 11560, 0);
      if ( (unsigned int)spew() )
      {
        if ( DirectoryW )
          LastError = 0;
        else
          LastError = GetLastError();
        _pwprint(ProcessEntry, L"........CreateDirectory(%u,%ws)\n", LastError, (char *)a2 + 23120);
      }
      if ( !DirectoryW && GetLastError() != 183 )
        goto LABEL_11;
      v16 = (char *)a2 + 23120;
      v26 = *((_DWORD *)a2 + 4959);
      swprintf_s(
        (wchar_t *const)a2 + 11560,
        0x209u,
        L"%ws%ws_%08X%04X%04X%02X%02X%02X%02X%02X%02X%02X%02X%X_%08X_%08X%08X\\%ws",
        &qword_1802B1A00,
        v28);
      v21 = DbgCopyFileExW(
              *((const unsigned __int16 **)a2 + 40),
              (const unsigned __int16 *)a2 + 11560,
              v19,
              v20,
              v25,
              v26);
      if ( (unsigned int)spew() )
      {
        v22 = *((_QWORD *)a2 + 40);
        if ( v21 )
          v23 = 0;
        else
          v23 = GetLastError();
        _pwprint(ProcessEntry, L"........CopyFile(%u,%ws,%ws)\n", v23, v22, (char *)a2 + 23120);
      }
      v6 = (DIA **)((char *)a2 + 19472);
      if ( v21 )
      {
        if ( *v6 )
        {
          diaRelease(a2, *v6);
          *v6 = 0;
        }
        v8 = v27;
        *((_DWORD *)a2 + 4842) |= 1u;
        *v27 = 4;
      }
      else
      {
LABEL_11:
        v8 = v27;
        v11 = *v6;
        *v27 = 16;
        if ( v11 )
          *((_DWORD *)v11 + 12) = 16;
        memset_0(v16, 0, 0x412u);
      }
      v5 = a1;
    }
    else
    {
LABEL_15:
      *v8 = 1;
      if ( v7 )
        *((_DWORD *)v7 + 12) = 1;
    }
  }
  if ( (a3 & 4) != 0 )
  {
    return (*((_DWORD *)a2 + 4842) & 3) != 1;
  }
  else
  {
    if ( (a3 & 1) != 0 && (dword_1802AF9CC & 0x100) != 0 && (*((_DWORD *)a2 + 4842) & 3) == 1 )
      return 0;
    if ( *v8 == 4 || (v9 = *((_DWORD *)a2 + 4842), (v9 & 1) != 0) && (v9 & 2) == 0 )
    {
      v24 = modload(v5, a2);
      if ( v24 )
      {
        return *((_DWORD *)a2 + 599) != 0;
      }
      else if ( *v8 == 4 )
      {
        diaRelease(a2, *v6);
        *v6 = 0;
      }
      return v24;
    }
    else
    {
      return (a3 & 8) == 0;
    }
  }
}

```

## disassembly

```asm
0x18000a820  mov     [rsp+arg_10], rbx
0x18000a825  mov     [rsp+arg_0], rcx
0x18000a82a  push    rbp
0x18000a82b  push    rsi
0x18000a82c  push    rdi
0x18000a82d  push    r12
0x18000a82f  push    r13
0x18000a831  push    r14
0x18000a833  push    r15
0x18000a835  sub     rsp, 0C0h
0x18000a83c  mov     r12d, r8d
0x18000a83f  mov     r13, rdx
0x18000a842  mov     rdi, rcx
0x18000a845  call    ?FindProcessEntry@@YAPEAU_PROCESS_ENTRY@@PEAX@Z; FindProcessEntry(void *)
0x18000a84a  lea     r15, [r13+4C10h]
0x18000a851  mov     [rsp+0F8h+arg_18], rax
0x18000a859  mov     r9, [r15]
0x18000a85c  lea     rbx, [r13+5E64h]
0x18000a863  xor     ebp, ebp
0x18000a865  mov     [rsp+0F8h+var_48], rbx
0x18000a86d  test    r9, r9
0x18000a870  jnz     loc_18000A946
0x18000a876  mov     [rsp+0F8h+var_48], rbx
0x18000a87e  cmp     dword ptr [rbx], 2
0x18000a881  jz      loc_18000A951
0x18000a887  test    r12b, 4
0x18000a88b  jnz     short loc_18000A8D8
0x18000a88d  test    r12b, 1
0x18000a891  jnz     loc_18000ACC2
0x18000a897  cmp     dword ptr [rbx], 4
0x18000a89a  jz      loc_18000ACF0
0x18000a8a0  mov     eax, [r13+4BA8h]
0x18000a8a7  test    al, 1
0x18000a8a9  jnz     loc_18000ACE8
0x18000a8af  shr     r12d, 3
0x18000a8b3  not     r12d
0x18000a8b6  and     r12d, 1
0x18000a8ba  mov     eax, r12d
0x18000a8bd  mov     rbx, [rsp+0F8h+arg_10]
0x18000a8c5  add     rsp, 0C0h
0x18000a8cc  pop     r15
0x18000a8ce  pop     r14
0x18000a8d0  pop     r13
0x18000a8d2  pop     r12
0x18000a8d4  pop     rdi
0x18000a8d5  pop     rsi
0x18000a8d6  pop     rbp
0x18000a8d7  retn
0x18000a8d8  mov     ecx, [r13+4BA8h]
0x18000a8df  and     cl, 3
0x18000a8e2  cmp     cl, 1
0x18000a8e5  jnz     loc_18000ACB8
0x18000a8eb  xor     eax, eax
0x18000a8ed  jmp     short loc_18000A8BD
0x18000a8ef  mov     rbx, [rsp+0F8h+var_48]
0x18000a8f7  mov     rax, r15
0x18000a8fa  mov     ecx, 10h
0x18000a8ff  mov     rdx, [rax]
0x18000a902  mov     [rbx], ecx
0x18000a904  test    rdx, rdx
0x18000a907  jnz     loc_18000ACB0
0x18000a90d  xor     edx, edx; Val
0x18000a90f  mov     r8d, 412h; Size
0x18000a915  mov     rcx, rdi; void *
0x18000a918  call    memset_0
0x18000a91d  mov     rdi, [rsp+0F8h+arg_0]
0x18000a925  jmp     loc_18000A887
0x18000a92a  mov     dword ptr [rbx], 1
0x18000a930  test    r9, r9
0x18000a933  jz      loc_18000A887
0x18000a939  mov     dword ptr [r9+30h], 1
0x18000a941  jmp     loc_18000A887
0x18000a946  mov     eax, [r9+30h]
0x18000a94a  mov     [rbx], eax
0x18000a94c  jmp     loc_18000A87E
0x18000a951  mov     r14, [r13+140h]
0x18000a958  mov     [rsp+0F8h+var_40], r14
0x18000a960  test    r14, r14
0x18000a963  jz      short loc_18000A92A
0x18000a965  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000a969  mov     rax, rdx
0x18000a96c  inc     rax
0x18000a96f  cmp     [r14+rax*2], bp
0x18000a974  jnz     short loc_18000A96C
0x18000a976  cmp     rax, 2
0x18000a97a  jbe     short loc_18000A92A
0x18000a97c  cmp     word ptr [r14], 5Ch ; '\'
0x18000a981  jnz     short loc_18000A92A
0x18000a983  cmp     word ptr [r14+2], 5Ch ; '\'
0x18000a989  jnz     short loc_18000A92A
0x18000a98b  mov     rcx, rdx
0x18000a98e  inc     rcx
0x18000a991  cmp     [r14+rcx*2], bp
0x18000a996  jnz     short loc_18000A98E
0x18000a998  mov     qword ptr [rsp+0F8h+SystemTimeAsFileTime.dwLowDateTime], rbp
0x18000a9a0  test    ecx, ecx
0x18000a9a2  jz      short loc_18000A9DB
0x18000a9a4  mov     eax, ecx
0x18000a9a6  cmp     word ptr [r14+rax*2], 5Ch ; '\'
0x18000a9ac  jz      short loc_18000A9B5
0x18000a9ae  add     ecx, 0FFFFFFFFh
0x18000a9b1  jnz     short loc_18000A9A4
0x18000a9b3  jmp     short loc_18000A9DB
0x18000a9b5  mov     r8d, ecx
0x18000a9b8  inc     rdx
0x18000a9bb  cmp     [r14+rdx*2], bp
0x18000a9c0  jnz     short loc_18000A9B8
0x18000a9c2  lea     rax, [rdx-1]
0x18000a9c6  cmp     r8, rax
0x18000a9c9  jnb     short loc_18000A9DB
0x18000a9cb  lea     r14, [r14+r8*2]
0x18000a9cf  add     r14, 2
0x18000a9d3  mov     [rsp+0F8h+var_40], r14
0x18000a9db  lea     rcx, [rsp+0F8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a9e3  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a9e9  mov     eax, [rsp+0F8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000a9f0  movzx   ecx, byte ptr [r13+4D8Bh]
0x18000a9f8  movzx   edx, byte ptr [r13+4D8Ah]
0x18000aa00  movzx   r8d, byte ptr [r13+4D89h]
0x18000aa08  movzx   r9d, byte ptr [r13+4D88h]
0x18000aa10  movzx   edi, byte ptr [r13+4D84h]
0x18000aa18  movzx   r10d, byte ptr [r13+4D87h]
0x18000aa20  movzx   r11d, byte ptr [r13+4D86h]
0x18000aa28  movzx   ebx, byte ptr [r13+4D85h]
0x18000aa30  movzx   esi, word ptr [r13+4D82h]
0x18000aa38  movzx   ebp, word ptr [r13+4D80h]
0x18000aa40  mov     [rsp+0F8h+var_60], eax
0x18000aa47  mov     eax, [rsp+0F8h+SystemTimeAsFileTime.dwHighDateTime]
0x18000aa4e  mov     [rsp+0F8h+var_68], eax
0x18000aa55  mov     rax, [rsp+0F8h+arg_18]
0x18000aa5d  mov     eax, [rax+38h]
0x18000aa60  mov     [rsp+0F8h+var_70], eax
0x18000aa67  mov     eax, [r13+4D74h]
0x18000aa6e  mov     [rsp+0F8h+var_78], eax
0x18000aa75  mov     eax, [r13+4D7Ch]
0x18000aa7c  mov     [rsp+0F8h+var_80], ecx
0x18000aa80  mov     [rsp+0F8h+var_88], edx
0x18000aa84  mov     edx, 209h; BufferCount
0x18000aa89  mov     [rsp+0F8h+var_90], r8d
0x18000aa8e  lea     r8, aWsWs08x04x04x0; "%ws%ws_%08X%04X%04X%02X%02X%02X%02X%02X"...
0x18000aa95  mov     [rsp+0F8h+var_98], r9d
0x18000aa9a  lea     r9, qword_1802B1A00
0x18000aaa1  mov     [rsp+0F8h+var_A0], r10d
0x18000aaa6  mov     [rsp+0F8h+var_A8], r11d
0x18000aaab  mov     [rsp+0F8h+var_B0], ebx
0x18000aaaf  mov     [rsp+0F8h+var_B8], edi
0x18000aab3  lea     rdi, [r13+5A50h]
0x18000aaba  mov     [rsp+0F8h+var_C0], esi
0x18000aabe  mov     rcx, rdi; Buffer
0x18000aac1  mov     [rsp+0F8h+var_C8], ebp
0x18000aac5  mov     [rsp+0F8h+var_D0], eax
0x18000aac9  mov     [rsp+0F8h+var_D8], r14
0x18000aace  call    swprintf_s
0x18000aad3  xor     edx, edx; lpSecurityAttributes
0x18000aad5  mov     rcx, rdi; lpPathName
0x18000aad8  call    cs:__imp_CreateDirectoryW
0x18000aade  mov     ebx, eax
0x18000aae0  call    ?spew@@YAHXZ; spew(void)
0x18000aae5  xor     ebp, ebp
0x18000aae7  test    eax, eax
0x18000aae9  jz      short loc_18000AB13
0x18000aaeb  test    ebx, ebx
0x18000aaed  jz      short loc_18000AAF3
0x18000aaef  mov     eax, ebp
0x18000aaf1  jmp     short loc_18000AAF9
0x18000aaf3  call    cs:__imp_GetLastError
0x18000aaf9  mov     rcx, [rsp+0F8h+arg_18]; struct _PROCESS_ENTRY *
0x18000ab01  lea     rdx, aCreatedirector; "........CreateDirectory(%u,%ws)\n"
0x18000ab08  mov     r9, rdi
0x18000ab0b  mov     r8d, eax
0x18000ab0e  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000ab13  test    ebx, ebx
0x18000ab15  jnz     short loc_18000AB28
0x18000ab17  call    cs:__imp_GetLastError
0x18000ab1d  cmp     eax, 0B7h
0x18000ab22  jnz     loc_18000A8EF
0x18000ab28  mov     eax, [rsp+0F8h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ab2f  lea     r9, qword_1802B1A00
0x18000ab36  mov     rdx, [rsp+0F8h+var_40]
0x18000ab3e  movzx   ecx, byte ptr [r13+4D8Bh]
0x18000ab46  movzx   r8d, byte ptr [r13+4D8Ah]
0x18000ab4e  movzx   edi, byte ptr [r13+4D86h]
0x18000ab56  movzx   r10d, byte ptr [r13+4D89h]
0x18000ab5e  movzx   r11d, byte ptr [r13+4D88h]
0x18000ab66  movzx   ebx, byte ptr [r13+4D87h]
0x18000ab6e  movzx   esi, byte ptr [r13+4D85h]
0x18000ab76  movzx   ebp, byte ptr [r13+4D84h]
0x18000ab7e  movzx   r14d, word ptr [r13+4D82h]
0x18000ab86  movzx   r15d, word ptr [r13+4D80h]
0x18000ab8e  mov     [rsp+0F8h+var_58], rdx
0x18000ab96  mov     [rsp+0F8h+var_60], eax
0x18000ab9d  mov     eax, [rsp+0F8h+SystemTimeAsFileTime.dwHighDateTime]
0x18000aba4  mov     [rsp+0F8h+var_68], eax
0x18000abab  mov     rax, [rsp+0F8h+arg_18]
0x18000abb3  mov     eax, [rax+38h]
0x18000abb6  mov     [rsp+0F8h+var_70], eax
0x18000abbd  mov     eax, [r13+4D74h]
0x18000abc4  mov     [rsp+0F8h+var_78], eax
0x18000abcb  mov     eax, [r13+4D7Ch]
0x18000abd2  mov     [rsp+0F8h+var_80], ecx
0x18000abd6  mov     [rsp+0F8h+var_88], r8d
0x18000abdb  lea     r8, aWsWs08x04x04x0_0; "%ws%ws_%08X%04X%04X%02X%02X%02X%02X%02X"...
0x18000abe2  mov     [rsp+0F8h+var_90], r10d
0x18000abe7  mov     [rsp+0F8h+var_98], r11d
0x18000abec  mov     [rsp+0F8h+var_A0], ebx
0x18000abf0  mov     [rsp+0F8h+var_A8], edi
0x18000abf4  lea     rdi, [r13+5A50h]
0x18000abfb  mov     [rsp+0F8h+var_B0], esi
0x18000abff  mov     rcx, rdi; Buffer
0x18000ac02  mov     [rsp+0F8h+var_B8], ebp
0x18000ac06  mov     [rsp+0F8h+var_C0], r14d
0x18000ac0b  mov     [rsp+0F8h+var_C8], r15d
0x18000ac10  mov     [rsp+0F8h+var_D0], eax; unsigned int
0x18000ac14  mov     [rsp+0F8h+var_D8], rdx; int *
0x18000ac19  mov     edx, 209h; BufferCount
0x18000ac1e  call    swprintf_s
0x18000ac23  mov     rcx, [r13+140h]; unsigned __int16 *
0x18000ac2a  mov     rdx, rdi; unsigned __int16 *
0x18000ac2d  call    ?DbgCopyFileExW@@YAHPEBG0P6AKT_LARGE_INTEGER@@111KKPEAX22@Z2PEAHK@Z; DbgCopyFileExW(ushort const *,ushort const *,ulong (*)(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *),void *,int *,ulong)
0x18000ac32  mov     ebx, eax
0x18000ac34  call    ?spew@@YAHXZ; spew(void)
0x18000ac39  xor     ebp, ebp
0x18000ac3b  test    eax, eax
0x18000ac3d  jz      short loc_18000AC73
0x18000ac3f  mov     rsi, [r13+140h]
0x18000ac46  test    ebx, ebx
0x18000ac48  jz      short loc_18000AC4E
0x18000ac4a  mov     eax, ebp
0x18000ac4c  jmp     short loc_18000AC54
0x18000ac4e  call    cs:__imp_GetLastError
0x18000ac54  mov     rcx, [rsp+0F8h+arg_18]; struct _PROCESS_ENTRY *
0x18000ac5c  lea     rdx, aCopyfileUWsWs; "........CopyFile(%u,%ws,%ws)\n"
0x18000ac63  mov     r9, rsi
0x18000ac66  mov     [rsp+0F8h+var_D8], rdi
0x18000ac6b  mov     r8d, eax
0x18000ac6e  call    ?_pwprint@@YAHPEAU_PROCESS_ENTRY@@PEBGZZ; _pwprint(_PROCESS_ENTRY *,ushort const *,...)
0x18000ac73  lea     r15, [r13+4C10h]
0x18000ac7a  test    ebx, ebx
0x18000ac7c  jz      loc_18000A8EF
0x18000ac82  mov     rdx, [r15]; void *
0x18000ac85  test    rdx, rdx
0x18000ac88  jz      short loc_18000AC95
0x18000ac8a  mov     rcx, r13; struct _MODULE_ENTRY *
0x18000ac8d  call    ?diaRelease@@YAXPEAU_MODULE_ENTRY@@PEAX@Z; diaRelease(_MODULE_ENTRY *,void *)
0x18000ac92  mov     [r15], rbp
0x18000ac95  mov     rbx, [rsp+0F8h+var_48]
0x18000ac9d  or      dword ptr [r13+4BA8h], 1
0x18000aca5  mov     dword ptr [rbx], 4
0x18000acab  jmp     loc_18000A91D
0x18000acb0  mov     [rdx+30h], ecx
0x18000acb3  jmp     loc_18000A90D
0x18000acb8  mov     eax, 1
0x18000acbd  jmp     loc_18000A8BD
0x18000acc2  test    cs:dword_1802AF9CC, 100h
0x18000accc  jz      loc_18000A897
0x18000acd2  mov     eax, [r13+4BA8h]
0x18000acd9  and     al, 3
0x18000acdb  cmp     al, 1
0x18000acdd  jnz     loc_18000A897
0x18000ace3  jmp     loc_18000A8EB
0x18000ace8  test    al, 2
0x18000acea  jnz     loc_18000A8AF
0x18000acf0  mov     rdx, r13; struct _MODULE_ENTRY *
0x18000acf3  mov     rcx, rdi; void *
0x18000acf6  call    ?modload@@YAHPEAXPEAU_MODULE_ENTRY@@@Z; modload(void *,_MODULE_ENTRY *)
0x18000acfb  mov     edi, eax
0x18000acfd  test    eax, eax
0x18000acff  jz      short loc_18000AD10
0x18000ad01  cmp     [r13+95Ch], ebp
0x18000ad08  mov     edi, ebp
0x18000ad0a  setnz   dil
0x18000ad0e  jmp     short loc_18000AD23
0x18000ad10  cmp     dword ptr [rbx], 4
0x18000ad13  jnz     short loc_18000AD23
0x18000ad15  mov     rdx, [r15]; void *
0x18000ad18  mov     rcx, r13; struct _MODULE_ENTRY *
0x18000ad1b  call    ?diaRelease@@YAXPEAU_MODULE_ENTRY@@PEAX@Z; diaRelease(_MODULE_ENTRY *,void *)
0x18000ad20  mov     [r15], rbp
0x18000ad23  mov     eax, edi
0x18000ad25  jmp     loc_18000A8BD
```
