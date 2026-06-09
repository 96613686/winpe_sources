# DbgKdTransport::HandleFileIo(_DBGKD_FILE_IO const *)

- ea: `0x1801cecd4`
- end: `0x1801cf0b7`
- name: `?HandleFileIo@DbgKdTransport@@QEAAJPEBU_DBGKD_FILE_IO@@@Z`
- size: `995`
- prototype: `__int64 __fastcall(DbgKdTransport *__hidden this, const struct _DBGKD_FILE_IO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update`

## callers

- `0x1801d0980`

## callees

- `0x1800727b8`
- `0x1800797ec`
- `0x180098580`
- `0x1800c12b8`
- `0x1800f0f40`
- `0x180159910`
- `0x1801ce648`
- `0x1801ce6c0`
- `0x1801cecd4`
- `0x1801d0940`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ced53`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ced53`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf07d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801cf07d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cee58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cee58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801cef4d`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801cee83`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1801cee83`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801cef81`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1801cef81`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801cee47`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801cef3c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801cee47`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1801cef3c`

## string_xrefs

- `0x1801cedd0`: `WARNING: No file I/O done by target, .kdfiles files may not be updated\n`
- `0x1801ced83`: `READ: Received INVALID FILE_IO packet type %x.\n`

## pseudocode

```c
__int64 __fastcall DbgKdTransport::HandleFileIo(DbgKdTransport *this, const struct _DBGKD_FILE_IO *a2)
{
  __int128 v3; // xmm1
  __int128 v4; // xmm0
  unsigned int v6; // esi
  __int128 v7; // xmm1
  DbgKdTransport *v8; // rcx
  struct KD_FILE *v9; // rbx
  DbgKdTransport *v10; // rcx
  struct KD_FILE *v11; // rbx
  __int64 v12; // rax
  struct KD_FILE *v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // eax
  LONG v17; // [rsp+30h] [rbp-D0h]
  LONG DistanceToMoveHigh[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct KD_FILE *v19; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  LONG lDistanceToMove[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v22[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v23; // [rsp+90h] [rbp-70h]
  _BYTE Buffer[3920]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = *((_OWORD *)a2 + 1);
  *(_OWORD *)v20 = *(_OWORD *)a2;
  v4 = *((_OWORD *)a2 + 2);
  *(_OWORD *)lDistanceToMove = v3;
  v6 = -2135949302;
  v7 = *((_OWORD *)a2 + 3);
  *(_OWORD *)v22 = v4;
  v23 = v7;
  v19 = 0;
  DistanceToMoveHigh[1] = 0;
  EnterCriticalSection(&g_EngineLock);
  switch ( v20[0] )
  {
    case 0x3430u:
      v15 = DbgKdTransport::CreateKdFile(
              this,
              (const unsigned __int16 *)a2 + 32,
              v20[2],
              v20[3],
              lDistanceToMove[0],
              lDistanceToMove[1],
              v17,
              &v19,
              &v22[1]);
      v22[0] = (unsigned __int64)v19;
      v20[1] = v15;
      KdOut(L"KdFile request for '%ws' returns %08X\n", (char *)a2 + 64, v15);
      break;
    case 0x3431u:
      v13 = DbgKdTransport::TranslateKdFileHandle(v8, *(unsigned __int64 *)&v20[2]);
      if ( !v13 )
        goto LABEL_32;
      v14 = (unsigned int)KdTransportMaxPacketSize;
      if ( (unsigned int)lDistanceToMove[2] > (unsigned __int64)(unsigned int)KdTransportMaxPacketSize - 64 )
        goto LABEL_32;
      *((_DWORD *)v13 + 7) = 1;
      if ( (unsigned int)lDistanceToMove[2] > (unsigned __int64)(v14 - 80) )
        lDistanceToMove[2] = v14 - 80;
      DistanceToMoveHigh[1] = lDistanceToMove[1];
      if ( SetFilePointer(*((HANDLE *)v13 + 2), lDistanceToMove[0], &DistanceToMoveHigh[1], 0) == -1 && GetLastError() )
        goto LABEL_27;
      if ( !ReadFile(*((HANDLE *)v13 + 2), Buffer, lDistanceToMove[2], (LPDWORD)&lDistanceToMove[2], 0) )
        goto LABEL_17;
      dprintf(L".");
      if ( (unsigned int)++dword_1807F66C0 >= 0xA0 )
      {
        dprintf(L"\n");
        dword_1807F66C0 = 0;
      }
      v20[1] = 0;
      break;
    case 0x3432u:
      v11 = DbgKdTransport::TranslateKdFileHandle(v8, *(unsigned __int64 *)&v20[2]);
      if ( v11 )
      {
        v12 = (unsigned int)KdTransportMaxPacketSize;
        if ( (unsigned int)lDistanceToMove[2] <= (unsigned __int64)(unsigned int)KdTransportMaxPacketSize - 64 )
        {
          *((_DWORD *)v11 + 7) = 1;
          if ( (unsigned int)lDistanceToMove[2] > (unsigned __int64)(v12 - 80) )
            lDistanceToMove[2] = v12 - 80;
          DistanceToMoveHigh[1] = lDistanceToMove[1];
          if ( SetFilePointer(*((HANDLE *)v11 + 2), lDistanceToMove[0], &DistanceToMoveHigh[1], 0) != -1
            || !GetLastError() )
          {
            if ( WriteFile(*((HANDLE *)v11 + 2), (char *)a2 + 64, lDistanceToMove[2], (LPDWORD)&lDistanceToMove[2], 0) )
            {
              dprintf(L".");
              if ( (unsigned int)++dword_1807F66C0 >= 0xA0 )
              {
                dprintf(L"\n");
                dword_1807F66C0 = 0;
              }
              goto LABEL_20;
            }
LABEL_17:
            v20[1] = -1073741823;
            break;
          }
LABEL_27:
          v20[1] = -1073741807;
          break;
        }
      }
LABEL_32:
      v20[1] = -1073741811;
      break;
    case 0x3433u:
      v9 = DbgKdTransport::TranslateKdFileHandle(v8, *(unsigned __int64 *)&v20[2]);
      if ( v9 )
      {
        dprintf(L"\n");
        dword_1807F66C0 = 0;
        if ( !*((_DWORD *)v9 + 7) )
          WarnOut(L"WARNING: No file I/O done by target, .kdfiles files may not be updated\n");
        DbgKdTransport::CloseKdFile(v10, v9);
LABEL_20:
        v20[1] = 0;
        break;
      }
      goto LABEL_32;
    default:
      KdOut(L"READ: Received INVALID FILE_IO packet type %x.\n");
      v20[1] = -1073741811;
      v6 = -2135949304;
      break;
  }
  if ( (*(unsigned int (__fastcall **)(DbgKdTransport *, unsigned int *, __int64))(*(_QWORD *)this + 24LL))(
         this,
         v20,
         64) == -805306054 )
    v6 = -805306054;
  FlushCallbacks();
  LeaveCriticalSection(&g_EngineLock);
  return v6;
}

```

## disassembly

```asm
0x1801cecd4  mov     [rsp-8+arg_10], rbx
0x1801cecd9  mov     [rsp-8+arg_18], rsi
0x1801cecde  push    rbp
0x1801cecdf  push    rdi
0x1801cece0  push    r12
0x1801cece2  push    r14
0x1801cece4  push    r15
0x1801cece6  lea     rbp, [rsp-0F00h]
0x1801cecee  mov     eax, 1000h
0x1801cecf3  call    _alloca_probe
0x1801cecf8  sub     rsp, rax
0x1801cecfb  mov     rax, cs:__security_cookie
0x1801ced02  xor     rax, rsp
0x1801ced05  mov     [rbp+0F20h+var_30], rax
0x1801ced0c  movaps  xmm0, xmmword ptr [rdx]
0x1801ced0f  mov     r12, rcx
0x1801ced12  movaps  xmm1, xmmword ptr [rdx+10h]
0x1801ced16  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801ced1d  movaps  xmmword ptr [rsp+1020h+var_FC0], xmm0
0x1801ced22  xor     r14d, r14d
0x1801ced25  movaps  xmm0, xmmword ptr [rdx+20h]
0x1801ced29  mov     rdi, rdx
0x1801ced2c  movaps  xmmword ptr [rsp+1020h+lDistanceToMove], xmm1
0x1801ced31  mov     esi, 80B0000Ah
0x1801ced36  movaps  xmm1, xmmword ptr [rdx+30h]
0x1801ced3a  xor     r15d, r15d
0x1801ced3d  movaps  xmmword ptr [rbp+0F20h+var_FA0], xmm0
0x1801ced41  movaps  [rbp+0F20h+var_F90], xmm1
0x1801ced45  mov     [rsp+1020h+var_FC8], 0
0x1801ced4e  mov     qword ptr [rsp+1020h+DistanceToMoveHigh], r14
0x1801ced53  call    cs:__imp_EnterCriticalSection
0x1801ced5a  nop     dword ptr [rax+rax+00h]
0x1801ced5f  mov     edx, [rsp+1020h+var_FC0]
0x1801ced63  mov     eax, edx
0x1801ced65  sub     eax, 3430h
0x1801ced6a  jz      loc_1801CEFE4
0x1801ced70  sub     eax, 1
0x1801ced73  jz      loc_1801CEEDE
0x1801ced79  sub     eax, 1
0x1801ced7c  jz      short loc_1801CEDE9
0x1801ced7e  cmp     eax, 1
0x1801ced81  jz      short loc_1801CEDA1
0x1801ced83  lea     rcx, aReadReceivedIn_1; "READ: Received INVALID FILE_IO packet t"...
0x1801ced8a  call    ?KdOut@@YAXPEBGZZ; KdOut(ushort const *,...)
0x1801ced8f  mov     [rsp+1020h+var_FC0+4], 0C000000Dh
0x1801ced97  mov     esi, 80B00008h
0x1801ced9c  jmp     loc_1801CF03D
0x1801ceda1  mov     rdx, qword ptr [rsp+1020h+var_FC0+8]; unsigned __int64
0x1801ceda6  call    ?TranslateKdFileHandle@DbgKdTransport@@QEAAPEAUKD_FILE@@_K@Z; DbgKdTransport::TranslateKdFileHandle(unsigned __int64)
0x1801cedab  mov     rbx, rax
0x1801cedae  test    rax, rax
0x1801cedb1  jz      loc_1801CEFDA
0x1801cedb7  lea     rcx, asc_1805BAA38; "\n"
0x1801cedbe  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801cedc3  mov     cs:dword_1807F66C0, r14d
0x1801cedca  cmp     [rbx+1Ch], r14d
0x1801cedce  jnz     short loc_1801CEDDC
0x1801cedd0  lea     rcx, aWarningNoFileI; "WARNING: No file I/O done by target, .k"...
0x1801cedd7  call    ?WarnOut@@YAXPEBGZZ; WarnOut(ushort const *,...)
0x1801ceddc  mov     rdx, rbx; struct KD_FILE *
0x1801ceddf  call    ?CloseKdFile@DbgKdTransport@@QEAAXPEAUKD_FILE@@@Z; DbgKdTransport::CloseKdFile(KD_FILE *)
0x1801cede4  jmp     loc_1801CEED4
0x1801cede9  mov     rdx, qword ptr [rsp+1020h+var_FC0+8]; unsigned __int64
0x1801cedee  call    ?TranslateKdFileHandle@DbgKdTransport@@QEAAPEAUKD_FILE@@_K@Z; DbgKdTransport::TranslateKdFileHandle(unsigned __int64)
0x1801cedf3  mov     rbx, rax
0x1801cedf6  test    rax, rax
0x1801cedf9  jz      loc_1801CEFDA
0x1801cedff  mov     eax, cs:KdTransportMaxPacketSize
0x1801cee05  mov     ecx, [rsp+1020h+lDistanceToMove+8]
0x1801cee09  lea     rdx, [rax-40h]
0x1801cee0d  cmp     rcx, rdx
0x1801cee10  ja      loc_1801CEFDA
0x1801cee16  mov     dword ptr [rbx+1Ch], 1
0x1801cee1d  lea     rdx, [rax-50h]
0x1801cee21  mov     ecx, [rsp+1020h+lDistanceToMove+8]
0x1801cee25  cmp     rcx, rdx
0x1801cee28  jbe     short loc_1801CEE31
0x1801cee2a  add     eax, 0FFFFFFB0h
0x1801cee2d  mov     [rsp+1020h+lDistanceToMove+8], eax
0x1801cee31  mov     rdx, qword ptr [rsp+1020h+lDistanceToMove]; lDistanceToMove
0x1801cee36  lea     r8, [rsp+1020h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x1801cee3b  mov     qword ptr [rsp+1020h+DistanceToMoveHigh], rdx
0x1801cee40  xor     r9d, r9d; dwMoveMethod
0x1801cee43  mov     rcx, [rbx+10h]; hFile
0x1801cee47  call    cs:__imp_SetFilePointer
0x1801cee4e  nop     dword ptr [rax+rax+00h]
0x1801cee53  cmp     eax, 0FFFFFFFFh
0x1801cee56  jnz     short loc_1801CEE6C
0x1801cee58  call    cs:__imp_GetLastError
0x1801cee5f  nop     dword ptr [rax+rax+00h]
0x1801cee64  test    eax, eax
0x1801cee66  jnz     loc_1801CEF5D
0x1801cee6c  mov     r8d, [rsp+1020h+lDistanceToMove+8]; nNumberOfBytesToWrite
0x1801cee71  lea     rdx, [rdi+40h]; lpBuffer
0x1801cee75  mov     rcx, [rbx+10h]; hFile
0x1801cee79  lea     r9, [rsp+1020h+lDistanceToMove+8]; lpNumberOfBytesWritten
0x1801cee7e  mov     [rsp+1020h+lpOverlapped], r14; lpOverlapped
0x1801cee83  call    cs:__imp_WriteFile
0x1801cee8a  nop     dword ptr [rax+rax+00h]
0x1801cee8f  test    eax, eax
0x1801cee91  jnz     short loc_1801CEEA0
0x1801cee93  mov     [rsp+1020h+var_FC0+4], 0C0000001h
0x1801cee9b  jmp     loc_1801CF03D
0x1801ceea0  lea     rcx, asc_1805B8788; "."
0x1801ceea7  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801ceeac  mov     eax, cs:dword_1807F66C0
0x1801ceeb2  inc     eax
0x1801ceeb4  mov     cs:dword_1807F66C0, eax
0x1801ceeba  cmp     eax, 0A0h
0x1801ceebf  jb      short loc_1801CEED4
0x1801ceec1  lea     rcx, asc_1805BAA38; "\n"
0x1801ceec8  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801ceecd  mov     cs:dword_1807F66C0, r14d
0x1801ceed4  mov     [rsp+1020h+var_FC0+4], r14d
0x1801ceed9  jmp     loc_1801CF03D
0x1801ceede  mov     rdx, qword ptr [rsp+1020h+var_FC0+8]; unsigned __int64
0x1801ceee3  call    ?TranslateKdFileHandle@DbgKdTransport@@QEAAPEAUKD_FILE@@_K@Z; DbgKdTransport::TranslateKdFileHandle(unsigned __int64)
0x1801ceee8  mov     rbx, rax
0x1801ceeeb  test    rax, rax
0x1801ceeee  jz      loc_1801CEFDA
0x1801ceef4  mov     eax, cs:KdTransportMaxPacketSize
0x1801ceefa  mov     ecx, [rsp+1020h+lDistanceToMove+8]
0x1801ceefe  lea     rdx, [rax-40h]
0x1801cef02  cmp     rcx, rdx
0x1801cef05  ja      loc_1801CEFDA
0x1801cef0b  mov     dword ptr [rbx+1Ch], 1
0x1801cef12  lea     rdx, [rax-50h]
0x1801cef16  mov     ecx, [rsp+1020h+lDistanceToMove+8]
0x1801cef1a  cmp     rcx, rdx
0x1801cef1d  jbe     short loc_1801CEF26
0x1801cef1f  add     eax, 0FFFFFFB0h
0x1801cef22  mov     [rsp+1020h+lDistanceToMove+8], eax
0x1801cef26  mov     rdx, qword ptr [rsp+1020h+lDistanceToMove]; lDistanceToMove
0x1801cef2b  lea     r8, [rsp+1020h+DistanceToMoveHigh+4]; lpDistanceToMoveHigh
0x1801cef30  mov     qword ptr [rsp+1020h+DistanceToMoveHigh], rdx
0x1801cef35  xor     r9d, r9d; dwMoveMethod
0x1801cef38  mov     rcx, [rbx+10h]; hFile
0x1801cef3c  call    cs:__imp_SetFilePointer
0x1801cef43  nop     dword ptr [rax+rax+00h]
0x1801cef48  cmp     eax, 0FFFFFFFFh
0x1801cef4b  jnz     short loc_1801CEF6A
0x1801cef4d  call    cs:__imp_GetLastError
0x1801cef54  nop     dword ptr [rax+rax+00h]
0x1801cef59  test    eax, eax
0x1801cef5b  jz      short loc_1801CEF6A
0x1801cef5d  mov     [rsp+1020h+var_FC0+4], 0C0000011h
0x1801cef65  jmp     loc_1801CF03D
0x1801cef6a  mov     r8d, [rsp+1020h+lDistanceToMove+8]; nNumberOfBytesToRead
0x1801cef6f  lea     r9, [rsp+1020h+lDistanceToMove+8]; lpNumberOfBytesRead
0x1801cef74  mov     rcx, [rbx+10h]; hFile
0x1801cef78  lea     rdx, [rbp+0F20h+Buffer]; lpBuffer
0x1801cef7c  mov     [rsp+1020h+lpOverlapped], r14; lpOverlapped
0x1801cef81  call    cs:__imp_ReadFile
0x1801cef88  nop     dword ptr [rax+rax+00h]
0x1801cef8d  test    eax, eax
0x1801cef8f  jz      loc_1801CEE93
0x1801cef95  lea     rcx, asc_1805B8788; "."
0x1801cef9c  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801cefa1  mov     eax, cs:dword_1807F66C0
0x1801cefa7  inc     eax
0x1801cefa9  mov     cs:dword_1807F66C0, eax
0x1801cefaf  cmp     eax, 0A0h
0x1801cefb4  jb      short loc_1801CEFC9
0x1801cefb6  lea     rcx, asc_1805BAA38; "\n"
0x1801cefbd  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1801cefc2  mov     cs:dword_1807F66C0, r14d
0x1801cefc9  movzx   r15d, word ptr [rsp+1020h+lDistanceToMove+8]
0x1801cefcf  mov     [rsp+1020h+var_FC0+4], r14d
0x1801cefd4  lea     r14, [rbp+0F20h+Buffer]
0x1801cefd8  jmp     short loc_1801CF03D
0x1801cefda  mov     [rsp+1020h+var_FC0+4], 0C000000Dh
0x1801cefe2  jmp     short loc_1801CF03D
0x1801cefe4  mov     r9d, [rsp+1020h+var_FC0+0Ch]; unsigned int
0x1801cefe9  lea     rax, [rbp+0F20h+var_FA0+8]
0x1801cefed  mov     r8d, [rsp+1020h+var_FC0+8]; unsigned int
0x1801ceff2  lea     rdx, [rdi+40h]; Src
0x1801ceff6  mov     [rsp+1020h+var_FE0], rax; unsigned __int64 *
0x1801ceffb  mov     rcx, r12; this
0x1801ceffe  lea     rax, [rsp+1020h+var_FC8]
0x1801cf003  mov     [rsp+1020h+var_FE8], rax; struct KD_FILE **
0x1801cf008  mov     eax, [rsp+1020h+lDistanceToMove+4]
0x1801cf00c  mov     [rsp+1020h+var_FF8], eax; unsigned int
0x1801cf010  mov     eax, [rsp+1020h+lDistanceToMove]
0x1801cf014  mov     dword ptr [rsp+1020h+lpOverlapped], eax; dwShareMode
0x1801cf018  call    ?CreateKdFile@DbgKdTransport@@QEAAJPEBGKKKKKPEAPEAUKD_FILE@@PEA_K@Z; DbgKdTransport::CreateKdFile(ushort const *,ulong,ulong,ulong,ulong,ulong,KD_FILE * *,unsigned __int64 *)
0x1801cf01d  mov     rcx, [rsp+1020h+var_FC8]
0x1801cf022  lea     rdx, [rdi+40h]
0x1801cf026  mov     [rbp+0F20h+var_FA0], rcx
0x1801cf02a  mov     r8d, eax
0x1801cf02d  lea     rcx, aKdfileRequestF; "KdFile request for '%ws' returns %08X\n"
0x1801cf034  mov     [rsp+1020h+var_FC0+4], eax
0x1801cf038  call    ?KdOut@@YAXPEBGZZ; KdOut(ushort const *,...)
0x1801cf03d  mov     rax, [r12]
0x1801cf041  lea     rdx, [rsp+1020h+var_FC0]
0x1801cf046  mov     r9d, 0Bh
0x1801cf04c  mov     word ptr [rsp+1020h+var_FF8], r15w
0x1801cf052  mov     rcx, r12
0x1801cf055  mov     [rsp+1020h+lpOverlapped], r14
0x1801cf05a  mov     rax, [rax+18h]
0x1801cf05e  lea     r8d, [r9+35h]
0x1801cf062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf067  mov     edx, 0D000013Ah
0x1801cf06c  cmp     eax, edx
0x1801cf06e  cmovz   esi, edx
0x1801cf071  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1801cf076  lea     rcx, ?g_EngineLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801cf07d  call    cs:__imp_LeaveCriticalSection
0x1801cf084  nop     dword ptr [rax+rax+00h]
0x1801cf089  mov     eax, esi
0x1801cf08b  mov     rcx, [rbp+0F20h+var_30]
0x1801cf092  xor     rcx, rsp; StackCookie
0x1801cf095  call    __security_check_cookie
0x1801cf09a  lea     r11, [rsp+1020h+var_20]
0x1801cf0a2  mov     rbx, [r11+40h]
0x1801cf0a6  mov     rsi, [r11+48h]
0x1801cf0aa  mov     rsp, r11
0x1801cf0ad  pop     r15
0x1801cf0af  pop     r14
0x1801cf0b1  pop     r12
0x1801cf0b3  pop     rdi
0x1801cf0b4  pop     rbp
0x1801cf0b5  retn
```
