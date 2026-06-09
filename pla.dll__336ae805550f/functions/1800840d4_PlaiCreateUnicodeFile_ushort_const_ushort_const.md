# PlaiCreateUnicodeFile(ushort const *,ushort const *)

- ea: `0x1800840d4`
- end: `0x1800845c5`
- name: `?PlaiCreateUnicodeFile@@YAJPEBG0@Z`
- size: `1265`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800c9cf8`
- `0x180124a20`

## callees

- `0x180001580`
- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x1800840d4`
- `0x18013aee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008414e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800842d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800843ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008442c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008414e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800842d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800843ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008442c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084593`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084593`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800842ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008436c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180084397`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800842ca`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008436c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180084397`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180084138`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180084138`

## string_xrefs

- `0x1800841e5`: `PlaiCreateUnicodeFile`
- `0x18008454f`: `PlaiCreateUnicodeFile`

## pseudocode

```c
__int64 __fastcall PlaiCreateUnicodeFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  __int64 v3; // rbx
  HANDLE FileW; // r12
  DWORD v5; // eax
  unsigned int v6; // edi
  signed int ByteSize; // eax
  DWORD LastError; // eax
  signed int v9; // eax
  DWORD v10; // esi
  DWORD v11; // eax
  signed int v12; // eax
  DWORD v13; // eax
  signed int v14; // eax
  char Buffer[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v18; // [rsp+80h] [rbp-80h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v20[64]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v21[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v22[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v23[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v24[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v25[64]; // [rsp+310h] [rbp+210h] BYREF

  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  Buffer[0] = 0;
  v3 = -1;
  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    ByteSize = PlaiGetByteSize(a2, &nNumberOfBytesToWrite);
    v6 = ByteSize;
    if ( ByteSize < 0 )
    {
      v18 = 0;
      nNumberOfBytesToWrite = ByteSize;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_51;
      }
      PlaiWhoAmI(v21, 0x4000000000000800uLL);
      do
        ++v3;
      while ( v21[v3] );
LABEL_50:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &nNumberOfBytesToWrite, 4, byte_180147320, 1, &v18, 4);
LABEL_51:
      CloseHandle(FileW);
      return v6;
    }
    Buffer[0] = -1;
    if ( !WriteFile(FileW, Buffer, 1u, &NumberOfBytesWritten, 0) )
    {
      LastError = GetLastError();
      v9 = PlaiHResultFromWin32(LastError);
      v6 = v9;
      if ( v9 < 0 )
      {
        v18 = 0;
        nNumberOfBytesToWrite = v9;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_51;
        }
        PlaiWhoAmI(v22, 0x4000000000000800uLL);
        do
          ++v3;
        while ( v22[v3] );
        goto LABEL_50;
      }
    }
    Buffer[0] = -2;
    if ( WriteFile(FileW, Buffer, 1u, &NumberOfBytesWritten, 0) )
    {
      v6 = 0;
    }
    else
    {
      v11 = GetLastError();
      v12 = PlaiHResultFromWin32(v11);
      v6 = v12;
      if ( v12 < 0 )
      {
        v18 = 0;
        nNumberOfBytesToWrite = v12;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_51;
        }
        PlaiWhoAmI(v23, 0x4000000000000800uLL);
        do
          ++v3;
        while ( v23[v3] );
        goto LABEL_50;
      }
    }
    v10 = nNumberOfBytesToWrite;
    while ( v10 )
    {
      if ( WriteFile(FileW, a2, v10, &NumberOfBytesWritten, 0) )
      {
        v6 = 0;
      }
      else
      {
        v13 = GetLastError();
        v14 = PlaiHResultFromWin32(v13);
        v6 = v14;
        if ( v14 < 0 )
        {
          v18 = 0;
          nNumberOfBytesToWrite = v14;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v25, 0x4000000000000800uLL);
            do
              ++v3;
            while ( v25[v3] );
            goto LABEL_50;
          }
          goto LABEL_51;
        }
      }
      if ( !NumberOfBytesWritten )
      {
        v6 = -2147418113;
        nNumberOfBytesToWrite = -2147418113;
        v18 = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v24, 0x4000000000000800uLL);
          do
            ++v3;
          while ( v24[v3] );
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      v10 -= NumberOfBytesWritten;
      a2 = (const unsigned __int16 *)((char *)a2 + NumberOfBytesWritten);
    }
    goto LABEL_51;
  }
  v5 = GetLastError();
  v6 = PlaiHResultFromWin32(v5);
  nNumberOfBytesToWrite = 0;
  v18 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v20, 0x4000000000000800uLL);
    do
      ++v3;
    while ( v20[v3] );
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v18, 4, byte_180147320, 1, &nNumberOfBytesToWrite, 4);
  }
  return v6;
}

```

## disassembly

```asm
0x1800840d4  mov     [rsp-8+arg_10], rbx
0x1800840d9  push    rbp
0x1800840da  push    rsi
0x1800840db  push    rdi
0x1800840dc  push    r12
0x1800840de  push    r13
0x1800840e0  push    r14
0x1800840e2  push    r15
0x1800840e4  lea     rbp, [rsp-2A0h]
0x1800840ec  sub     rsp, 3A0h
0x1800840f3  mov     rax, cs:__security_cookie
0x1800840fa  xor     rax, rsp
0x1800840fd  mov     [rbp+2D0h+var_40], rax
0x180084104  xor     r13d, r13d
0x180084107  mov     r14, rdx
0x18008410a  mov     [rsp+3D0h+hTemplateFile], r13; hTemplateFile
0x18008410f  xor     r9d, r9d; lpSecurityAttributes
0x180084112  mov     [rsp+3D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008411a  xor     r8d, r8d; dwShareMode
0x18008411d  mov     edx, 40000000h; dwDesiredAccess
0x180084122  mov     [rsp+3D0h+dwCreationDisposition], 2; dwCreationDisposition
0x18008412a  mov     [rsp+3D0h+nNumberOfBytesToWrite], r13d
0x18008412f  mov     [rbp+2D0h+NumberOfBytesWritten], r13d
0x180084133  mov     [rsp+3D0h+Buffer], r13b
0x180084138  call    cs:__imp_CreateFileW
0x18008413e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180084142  mov     r12, rax
0x180084145  cmp     rax, rbx
0x180084148  jnz     loc_18008422F
0x18008414e  call    cs:__imp_GetLastError
0x180084154  mov     ecx, eax; unsigned int
0x180084156  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x18008415b  cmp     dword ptr cs:xmmword_180169738, r13d
0x180084162  mov     edi, eax
0x180084164  mov     [rsp+3D0h+nNumberOfBytesToWrite], r13d
0x180084169  mov     [rbp+2D0h+var_350], eax
0x18008416c  jz      loc_180084599
0x180084172  mov     rdx, 4000000000000800h; unsigned __int64
0x18008417c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180084183  jz      loc_180084599
0x180084189  mov     rax, cs:qword_180169748
0x180084190  and     rax, rdx
0x180084193  cmp     cs:qword_180169748, rax
0x18008419a  jnz     loc_180084599
0x1800841a0  lea     rcx, [rbp+2D0h+var_340]; unsigned __int16 *
0x1800841a4  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800841a9  lea     rax, [rbp+2D0h+var_340]
0x1800841ad  inc     rbx
0x1800841b0  cmp     [rax+rbx*2], r13w
0x1800841b5  jnz     short loc_1800841AD
0x1800841b7  lea     rax, [rbp+2D0h+var_340]
0x1800841bb  lea     ecx, [rbx+rbx]
0x1800841be  add     rcx, 2
0x1800841c2  lea     r9, [rbp+2D0h+var_350]
0x1800841c6  mov     [rsp+3D0h+var_370], rcx
0x1800841cb  lea     rdx, PLA_EVENT_ERROR
0x1800841d2  mov     [rsp+3D0h+var_378], rax
0x1800841d7  lea     rcx, [rsp+3D0h+nNumberOfBytesToWrite]
0x1800841dc  mov     [rsp+3D0h+var_380], 16h
0x1800841e5  lea     rax, aPlaicreateunic; "PlaiCreateUnicodeFile"
0x1800841ec  mov     [rsp+3D0h+var_388], rax
0x1800841f1  mov     eax, 4
0x1800841f6  mov     [rsp+3D0h+var_390], rax
0x1800841fb  mov     [rsp+3D0h+var_398], rcx
0x180084200  lea     rcx, byte_180147320
0x180084207  lea     r15d, [rax-3]
0x18008420b  mov     [rsp+3D0h+hTemplateFile], r15
0x180084210  lea     r8d, [rax+1]
0x180084214  mov     qword ptr [rsp+3D0h+dwFlagsAndAttributes], rcx
0x180084219  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180084220  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax
0x180084225  call    EventingWriteEvent
0x18008422a  jmp     loc_180084599
0x18008422f  lea     rdx, [rsp+3D0h+nNumberOfBytesToWrite]; unsigned int *
0x180084234  mov     rcx, r14; unsigned __int16 *
0x180084237  call    ?PlaiGetByteSize@@YAJPEBGPEAK@Z; PlaiGetByteSize(ushort const *,ulong *)
0x18008423c  mov     edi, eax
0x18008423e  test    eax, eax
0x180084240  jns     short loc_1800842AB
0x180084242  cmp     dword ptr cs:xmmword_180169738, r13d
0x180084249  mov     [rbp+2D0h+var_350], r13d
0x18008424d  mov     [rsp+3D0h+nNumberOfBytesToWrite], eax
0x180084251  jz      loc_180084590
0x180084257  mov     rdx, 4000000000000800h; unsigned __int64
0x180084261  test    qword ptr cs:xmmword_180169738+8, rdx
0x180084268  jz      loc_180084590
0x18008426e  mov     rax, cs:qword_180169748
0x180084275  and     rax, rdx
0x180084278  cmp     cs:qword_180169748, rax
0x18008427f  jnz     loc_180084590
0x180084285  lea     rcx, [rbp+2D0h+var_2C0]; unsigned __int16 *
0x180084289  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008428e  lea     rax, [rbp+2D0h+var_2C0]
0x180084292  inc     rbx
0x180084295  cmp     [rax+rbx*2], r13w
0x18008429a  jnz     short loc_180084292
0x18008429c  lea     rax, [rbp+2D0h+var_2C0]
0x1800842a0  mov     r15d, 1
0x1800842a6  jmp     loc_180084525
0x1800842ab  mov     r15d, 1
0x1800842b1  mov     [rsp+3D0h+Buffer], 0FFh
0x1800842b6  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800842b9  mov     qword ptr [rsp+3D0h+dwCreationDisposition], r13; lpOverlapped
0x1800842be  lea     r9, [rbp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800842c2  mov     rcx, r12; hFile
0x1800842c5  lea     rdx, [rsp+3D0h+Buffer]; lpBuffer
0x1800842ca  call    cs:__imp_WriteFile
0x1800842d0  test    eax, eax
0x1800842d2  jnz     short loc_180084353
0x1800842d4  call    cs:__imp_GetLastError
0x1800842da  mov     ecx, eax; unsigned int
0x1800842dc  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800842e1  mov     edi, eax
0x1800842e3  test    eax, eax
0x1800842e5  jns     short loc_180084353
0x1800842e7  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800842ee  mov     [rbp+2D0h+var_350], r13d
0x1800842f2  mov     [rsp+3D0h+nNumberOfBytesToWrite], eax
0x1800842f6  jz      loc_180084590
0x1800842fc  mov     rdx, 4000000000000800h; unsigned __int64
0x180084306  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008430d  jz      loc_180084590
0x180084313  mov     rax, cs:qword_180169748
0x18008431a  and     rax, rdx
0x18008431d  cmp     cs:qword_180169748, rax
0x180084324  jnz     loc_180084590
0x18008432a  lea     rcx, [rbp+2D0h+var_240]; unsigned __int16 *
0x180084331  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180084336  lea     rax, [rbp+2D0h+var_240]
0x18008433d  inc     rbx
0x180084340  cmp     [rax+rbx*2], r13w
0x180084345  jnz     short loc_18008433D
0x180084347  lea     rax, [rbp+2D0h+var_240]
0x18008434e  jmp     loc_180084525
0x180084353  lea     r9, [rbp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180084357  mov     [rsp+3D0h+Buffer], 0FEh
0x18008435c  mov     r8d, r15d; nNumberOfBytesToWrite
0x18008435f  mov     qword ptr [rsp+3D0h+dwCreationDisposition], r13; lpOverlapped
0x180084364  lea     rdx, [rsp+3D0h+Buffer]; lpBuffer
0x180084369  mov     rcx, r12; hFile
0x18008436c  call    cs:__imp_WriteFile
0x180084372  test    eax, eax
0x180084374  jz      short loc_1800843AD
0x180084376  mov     edi, r13d
0x180084379  mov     esi, [rsp+3D0h+nNumberOfBytesToWrite]
0x18008437d  test    esi, esi
0x18008437f  jz      loc_180084590
0x180084385  lea     r9, [rbp+2D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180084389  mov     qword ptr [rsp+3D0h+dwCreationDisposition], r13; lpOverlapped
0x18008438e  mov     r8d, esi; nNumberOfBytesToWrite
0x180084391  mov     rdx, r14; lpBuffer
0x180084394  mov     rcx, r12; hFile
0x180084397  call    cs:__imp_WriteFile
0x18008439d  test    eax, eax
0x18008439f  jz      loc_18008442C
0x1800843a5  mov     edi, r13d
0x1800843a8  jmp     loc_18008443F
0x1800843ad  call    cs:__imp_GetLastError
0x1800843b3  mov     ecx, eax; unsigned int
0x1800843b5  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1800843ba  mov     edi, eax
0x1800843bc  test    eax, eax
0x1800843be  jns     short loc_180084379
0x1800843c0  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800843c7  mov     [rbp+2D0h+var_350], r13d
0x1800843cb  mov     [rsp+3D0h+nNumberOfBytesToWrite], eax
0x1800843cf  jz      loc_180084590
0x1800843d5  mov     rdx, 4000000000000800h; unsigned __int64
0x1800843df  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800843e6  jz      loc_180084590
0x1800843ec  mov     rax, cs:qword_180169748
0x1800843f3  and     rax, rdx
0x1800843f6  cmp     cs:qword_180169748, rax
0x1800843fd  jnz     loc_180084590
0x180084403  lea     rcx, [rbp+2D0h+var_1C0]; unsigned __int16 *
0x18008440a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008440f  lea     rax, [rbp+2D0h+var_1C0]
0x180084416  inc     rbx
0x180084419  cmp     [rax+rbx*2], r13w
0x18008441e  jnz     short loc_180084416
0x180084420  lea     rax, [rbp+2D0h+var_1C0]
0x180084427  jmp     loc_180084525
0x18008442c  call    cs:__imp_GetLastError
0x180084432  mov     ecx, eax; unsigned int
0x180084434  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180084439  mov     edi, eax
0x18008443b  test    eax, eax
0x18008443d  js      short loc_1800844BE
0x18008443f  mov     eax, [rbp+2D0h+NumberOfBytesWritten]
0x180084442  test    eax, eax
0x180084444  jz      short loc_180084450
0x180084446  sub     esi, eax
0x180084448  add     r14, rax
0x18008444b  jmp     loc_18008437D
0x180084450  cmp     dword ptr cs:xmmword_180169738, r13d
0x180084457  mov     edi, 8000FFFFh
0x18008445c  mov     [rsp+3D0h+nNumberOfBytesToWrite], edi
0x180084460  mov     [rbp+2D0h+var_350], r13d
0x180084464  jz      loc_180084590
0x18008446a  mov     rdx, 4000000000000800h; unsigned __int64
0x180084474  test    qword ptr cs:xmmword_180169738+8, rdx
0x18008447b  jz      loc_180084590
0x180084481  mov     rax, cs:qword_180169748
0x180084488  and     rax, rdx
0x18008448b  cmp     cs:qword_180169748, rax
0x180084492  jnz     loc_180084590
0x180084498  lea     rcx, [rbp+2D0h+var_140]; unsigned __int16 *
0x18008449f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800844a4  lea     rax, [rbp+2D0h+var_140]
0x1800844ab  inc     rbx
0x1800844ae  cmp     [rax+rbx*2], r13w
0x1800844b3  jnz     short loc_1800844AB
0x1800844b5  lea     rax, [rbp+2D0h+var_140]
0x1800844bc  jmp     short loc_180084525
0x1800844be  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800844c5  mov     [rbp+2D0h+var_350], r13d
0x1800844c9  mov     [rsp+3D0h+nNumberOfBytesToWrite], eax
0x1800844cd  jz      loc_180084590
0x1800844d3  mov     rdx, 4000000000000800h; unsigned __int64
0x1800844dd  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800844e4  jz      loc_180084590
0x1800844ea  mov     rax, cs:qword_180169748
0x1800844f1  and     rax, rdx
0x1800844f4  cmp     cs:qword_180169748, rax
0x1800844fb  jnz     loc_180084590
0x180084501  lea     rcx, [rbp+2D0h+var_C0]; unsigned __int16 *
0x180084508  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18008450d  lea     rax, [rbp+2D0h+var_C0]
0x180084514  inc     rbx
0x180084517  cmp     [rax+rbx*2], r13w
0x18008451c  jnz     short loc_180084514
0x18008451e  lea     rax, [rbp+2D0h+var_C0]
0x180084525  lea     ecx, [rbx+rbx]
0x180084528  add     rcx, 2
0x18008452c  lea     r9, [rsp+3D0h+nNumberOfBytesToWrite]
0x180084531  mov     [rsp+3D0h+var_370], rcx
0x180084536  lea     rdx, PLA_EVENT_ERROR
0x18008453d  mov     [rsp+3D0h+var_378], rax
0x180084542  lea     rcx, [rbp+2D0h+var_350]
0x180084546  mov     [rsp+3D0h+var_380], 16h
0x18008454f  lea     rax, aPlaicreateunic; "PlaiCreateUnicodeFile"
0x180084556  mov     [rsp+3D0h+var_388], rax
0x18008455b  mov     eax, 4
0x180084560  mov     [rsp+3D0h+var_390], rax
0x180084565  mov     [rsp+3D0h+var_398], rcx
0x18008456a  lea     rcx, byte_180147320
0x180084571  mov     [rsp+3D0h+hTemplateFile], r15
0x180084576  mov     qword ptr [rsp+3D0h+dwFlagsAndAttributes], rcx
0x18008457b  lea     r8d, [rax+1]
0x18008457f  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180084586  mov     qword ptr [rsp+3D0h+dwCreationDisposition], rax
0x18008458b  call    EventingWriteEvent
0x180084590  mov     rcx, r12; hObject
0x180084593  call    cs:__imp_CloseHandle
0x180084599  mov     eax, edi
0x18008459b  mov     rcx, [rbp+2D0h+var_40]
0x1800845a2  xor     rcx, rsp; StackCookie
0x1800845a5  call    __security_check_cookie
0x1800845aa  mov     rbx, [rsp+3D0h+arg_10]
0x1800845b2  add     rsp, 3A0h
0x1800845b9  pop     r15
0x1800845bb  pop     r14
0x1800845bd  pop     r13
0x1800845bf  pop     r12
0x1800845c1  pop     rdi
0x1800845c2  pop     rsi
0x1800845c3  pop     rbp
0x1800845c4  retn
```
