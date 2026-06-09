# CHdropToFgdConverter::AddItemToFgd(ushort *,ushort *,_WIN32_FIND_DATAW *,int)

- ea: `0x1800af938`
- end: `0x1800aff87`
- name: `?AddItemToFgd@CHdropToFgdConverter@@AEAAJPEAG0PEAU_WIN32_FIND_DATAW@@H@Z`
- size: `1615`
- prototype: `__int64 __fastcall(CHdropToFgdConverter *this, unsigned __int16 *, unsigned __int16 *, struct _WIN32_FIND_DATAW *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x1800af160`
- `0x1800b032c`

## callees

- `0x1800091a8`
- `0x18002e4e0`
- `0x18002e600`
- `0x180033da0`
- `0x180059838`
- `0x180063160`
- `0x1800af938`
- `0x1800b0930`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afcbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afb8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800afcbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800afec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800afec6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800afb1f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800afb1f`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800afc6e`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800afc6e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800afbef`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800afbef`

## string_xrefs

- `0x1800afe04`: `StringCbCopy failed!`

## pseudocode

```c
__int64 __fastcall CHdropToFgdConverter::AddItemToFgd(
        CHdropToFgdConverter *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct _WIN32_FIND_DATAW *a4,
        int a5)
{
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v14; // ecx
  __int64 v15; // r12
  unsigned int v16; // eax
  unsigned int v17; // edx
  unsigned int v18; // eax
  char *FileW; // r14
  __int64 v20; // r11
  DWORD nFileSizeHigh; // eax
  DWORD FileAttributesW; // eax
  __int64 v23; // rax
  unsigned int v24; // eax
  signed int v25; // eax
  int v26; // ecx
  unsigned int v27; // eax
  unsigned int v28; // eax
  signed int LastError; // eax
  __int64 v30; // rcx
  _OWORD *v31; // rdx
  _OWORD *v32; // rax
  __int128 v33; // xmm1
  __int64 v34; // r11
  unsigned int v35; // eax
  int v36; // edx
  __int64 v37; // rcx
  __int64 v38; // rdx
  void (__fastcall *v39)(__int64, __int64, __int64); // rax
  unsigned int v40; // eax
  unsigned int v41; // eax
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-29h] BYREF

  if ( *((_QWORD *)this + 1) && *(_QWORD *)this )
  {
    if ( a2 && a3 )
    {
      if ( !a5 )
      {
        v8 = *((_QWORD *)this + 3);
        if ( v8 )
        {
          if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8) )
          {
            v9 = *((unsigned int *)this + 8);
            v10 = (__int64 *)*((_QWORD *)this + 3);
            v11 = *v10;
            *((_DWORD *)this + 8) = v9 + 1;
            (*(void (__fastcall **)(__int64 *, __int64, _QWORD))(v11 + 40))(v10, v9, 0);
            v12 = 1;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DS(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                (unsigned int)WPP_6b188fce9f953a3badf01269520c37ed_Traceguids,
                CurrentThreadActivityIdPrefix,
                (__int64)a2);
            }
            return (unsigned int)v12;
          }
        }
      }
      v14 = *((_DWORD *)this + 4);
      v15 = **((unsigned int **)this + 1);
      v16 = 592 * v15 + 596;
      if ( v14 < v16 )
      {
        v17 = v14 + v16;
        if ( v14 + v16 < v14 || v17 < v16 )
          v17 = 592 * v15 + 596;
        v12 = CHdropToFgdConverter::ResizeFgds((const void **)this, v17);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              31,
              (unsigned int)WPP_6b188fce9f953a3badf01269520c37ed_Traceguids,
              v18,
              (__int64)"ResizeFgds failed!",
              v12);
          }
          return (unsigned int)v12;
        }
      }
      FileW = 0;
      if ( a4 )
      {
        v20 = 592 * v15;
        *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 40) = a4->dwFileAttributes;
        *(FILETIME *)(v20 + *((_QWORD *)this + 1) + 60) = a4->ftLastWriteTime;
        *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 72) = a4->nFileSizeLow;
        nFileSizeHigh = a4->nFileSizeHigh;
LABEL_45:
        *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 68) = nFileSizeHigh;
        v26 = 16484;
        goto LABEL_46;
      }
      if ( a5 )
      {
        FileAttributesW = GetFileAttributesW(a2);
        v20 = 592 * v15;
        *(_DWORD *)(592 * v15 + *((_QWORD *)this + 1) + 40) = FileAttributesW;
        v23 = *((_QWORD *)this + 1);
        if ( *(_DWORD *)(592 * v15 + v23 + 40) != -1 )
        {
          *(_DWORD *)(v20 + v23 + 72) = 0;
          v26 = 16452;
          *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 68) = 0;
LABEL_46:
          *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 4) = v26;
          v30 = 4;
          v31 = (_OWORD *)(v20 + *(_QWORD *)this + 4LL);
          v32 = (_OWORD *)(v20 + *((_QWORD *)this + 1) + 4LL);
          do
          {
            *v31 = *v32;
            v31[1] = v32[1];
            v31[2] = v32[2];
            v31[3] = v32[3];
            v31[4] = v32[4];
            v31[5] = v32[5];
            v31[6] = v32[6];
            v33 = v32[7];
            v32 += 8;
            v31[7] = v33;
            v31 += 8;
            --v30;
          }
          while ( v30 );
          *v31 = *v32;
          v31[1] = v32[1];
          v31[2] = v32[2];
          v31[3] = v32[3];
          v31[4] = v32[4];
          v12 = StringCbCopyW((unsigned __int16 *)(v20 + *((_QWORD *)this + 1) + 76LL), 0x208u, a2);
          if ( v12 >= 0 )
          {
            v12 = StringCbCopyW((unsigned __int16 *)(v34 + *(_QWORD *)this + 76LL), 0x208u, a3);
            if ( v12 >= 0 )
            {
              if ( !a5 )
              {
                v37 = *((_QWORD *)this + 3);
                if ( v37 )
                {
                  v38 = *((unsigned int *)this + 8);
                  v39 = *(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v37 + 40LL);
                  *((_DWORD *)this + 8) = v38 + 1;
                  v39(v37, v38, 1);
                }
              }
              ++**(_DWORD **)this;
              ++**((_DWORD **)this + 1);
              v12 = 0;
              goto LABEL_63;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v35 = RdpWppGetCurrentThreadActivityIdPrefix();
              v36 = 36;
              goto LABEL_53;
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v35 = RdpWppGetCurrentThreadActivityIdPrefix();
            v36 = 35;
LABEL_53:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              (unsigned int)WPP_6b188fce9f953a3badf01269520c37ed_Traceguids,
              v35,
              (__int64)"StringCbCopy failed!",
              v12);
          }
LABEL_63:
          if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(FileW);
          return (unsigned int)v12;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v24 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            32,
            (unsigned int)WPP_6b188fce9f953a3badf01269520c37ed_Traceguids,
            v24,
            (__int64)a2);
        }
      }
      else
      {
        memset(&FileInformation, 0, sizeof(FileInformation));
        FileW = (char *)CreateFileW(a2, 0x80000000, 3u, 0, 3u, 0, 0);
        if ( FileW != (char *)-1LL )
        {
          memset(&FileInformation, 0, sizeof(FileInformation));
          if ( !GetFileInformationByHandle(FileW, &FileInformation) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v28 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids, v28);
            }
            LastError = GetLastError();
            v12 = LastError;
            if ( LastError > 0 )
              v12 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_63;
          }
          v20 = 592 * v15;
          *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 40) = FileInformation.dwFileAttributes;
          *(FILETIME *)(v20 + *((_QWORD *)this + 1) + 60) = FileInformation.ftLastWriteTime;
          *(_DWORD *)(v20 + *((_QWORD *)this + 1) + 72) = FileInformation.nFileSizeLow;
          nFileSizeHigh = FileInformation.nFileSizeHigh;
          goto LABEL_45;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids, v27);
        }
      }
      v25 = GetLastError();
      v12 = v25;
      if ( v25 > 0 )
        return (unsigned __int16)v25 | 0x80070000;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v40 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids, v40);
      }
      return (unsigned int)-2147467259;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v41 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids, v41);
    }
    return (unsigned int)-2147418113;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800af938  push    rbp
0x1800af93a  push    rbx
0x1800af93b  push    rsi
0x1800af93c  push    rdi
0x1800af93d  push    r12
0x1800af93f  push    r13
0x1800af941  push    r14
0x1800af943  lea     rbp, [rsp-1Fh]
0x1800af948  sub     rsp, 90h
0x1800af94f  mov     rax, cs:__security_cookie
0x1800af956  xor     rax, rsp
0x1800af959  mov     [rbp+4Fh+var_40], rax
0x1800af95d  xor     ebx, ebx
0x1800af95f  mov     rax, r8
0x1800af962  mov     r13, r9
0x1800af965  mov     [rbp+4Fh+var_80], rax
0x1800af969  mov     rsi, rdx
0x1800af96c  mov     rdi, rcx
0x1800af96f  cmp     [rcx+8], rbx
0x1800af973  jz      loc_1800AFF1D
0x1800af979  cmp     [rcx], rbx
0x1800af97c  jz      loc_1800AFF1D
0x1800af982  test    rdx, rdx
0x1800af985  jz      loc_1800AFED1
0x1800af98b  test    rax, rax
0x1800af98e  jz      loc_1800AFED1
0x1800af994  cmp     [rbp+4Fh+arg_20], ebx
0x1800af997  jnz     loc_1800AFA35
0x1800af99d  mov     rcx, [rcx+18h]
0x1800af9a1  test    rcx, rcx
0x1800af9a4  jz      loc_1800AFA35
0x1800af9aa  mov     rax, [rcx]
0x1800af9ad  mov     rax, [rax+20h]
0x1800af9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9b6  test    eax, eax
0x1800af9b8  jnz     short loc_1800AFA35
0x1800af9ba  mov     edx, [rdi+20h]
0x1800af9bd  mov     rcx, [rdi+18h]
0x1800af9c1  lea     r8d, [rdx+1]
0x1800af9c5  mov     rax, [rcx]
0x1800af9c8  mov     [rdi+20h], r8d
0x1800af9cc  xor     r8d, r8d
0x1800af9cf  mov     rax, [rax+28h]
0x1800af9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af9d8  mov     rdx, cs:WPP_GLOBAL_Control
0x1800af9df  lea     rax, WPP_GLOBAL_Control
0x1800af9e6  mov     ebx, 1
0x1800af9eb  cmp     rdx, rax
0x1800af9ee  jz      loc_1800AFF67
0x1800af9f4  test    [rdx+1Ch], bl
0x1800af9f7  jz      loc_1800AFF67
0x1800af9fd  lea     ecx, [rbx+3]
0x1800afa00  cmp     [rdx+19h], cl
0x1800afa03  jb      loc_1800AFF67
0x1800afa09  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afa0e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa15  lea     edx, [rbx+1Dh]
0x1800afa18  mov     r9d, eax
0x1800afa1b  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi
0x1800afa20  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1800afa27  mov     rcx, [rcx+10h]
0x1800afa2b  call    WPP_SF_DS
0x1800afa30  jmp     loc_1800AFF67
0x1800afa35  mov     rax, [rdi+8]
0x1800afa39  mov     ecx, [rdi+10h]
0x1800afa3c  mov     r12d, [rax]
0x1800afa3f  imul    eax, r12d, 250h
0x1800afa46  add     eax, 254h
0x1800afa4b  cmp     ecx, eax
0x1800afa4d  jnb     loc_1800AFAD4
0x1800afa53  lea     edx, [rcx+rax]
0x1800afa56  cmp     edx, ecx
0x1800afa58  jb      short loc_1800AFA5E
0x1800afa5a  cmp     edx, eax
0x1800afa5c  jnb     short loc_1800AFA60
0x1800afa5e  mov     edx, eax; unsigned int
0x1800afa60  mov     rcx, rdi; this
0x1800afa63  call    ?ResizeFgds@CHdropToFgdConverter@@AEAAJI@Z; CHdropToFgdConverter::ResizeFgds(uint)
0x1800afa68  mov     ebx, eax
0x1800afa6a  test    eax, eax
0x1800afa6c  jns     short loc_1800AFAD2
0x1800afa6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa75  lea     rax, WPP_GLOBAL_Control
0x1800afa7c  cmp     rcx, rax
0x1800afa7f  jz      loc_1800AFF67
0x1800afa85  test    byte ptr [rcx+1Ch], 8
0x1800afa89  jz      loc_1800AFF67
0x1800afa8f  cmp     byte ptr [rcx+19h], 2
0x1800afa93  jb      loc_1800AFF67
0x1800afa99  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afa9e  lea     rcx, aResizefgdsFail; "ResizeFgds failed!"
0x1800afaa5  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x1800afaa9  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x1800afaae  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1800afab5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afabc  mov     edx, 1Fh
0x1800afac1  mov     r9d, eax
0x1800afac4  mov     rcx, [rcx+10h]
0x1800afac8  call    WPP_SF_DsD
0x1800afacd  jmp     loc_1800AFF67
0x1800afad2  xor     ebx, ebx
0x1800afad4  mov     r14, rbx
0x1800afad7  test    r13, r13
0x1800afada  jz      short loc_1800AFB13
0x1800afadc  mov     rcx, [rdi+8]
0x1800afae0  mov     eax, [r13+0]
0x1800afae4  imul    r11, r12, 250h
0x1800afaeb  mov     [r11+rcx+28h], eax
0x1800afaf0  mov     rcx, [rdi+8]
0x1800afaf4  mov     rax, [r13+14h]
0x1800afaf8  mov     [r11+rcx+3Ch], rax
0x1800afafd  mov     eax, [r13+20h]
0x1800afb01  mov     rcx, [rdi+8]
0x1800afb05  mov     [r11+rcx+48h], eax
0x1800afb0a  mov     eax, [r13+1Ch]
0x1800afb0e  jmp     loc_1800AFD0A
0x1800afb13  mov     rcx, rsi; lpFileName
0x1800afb16  cmp     [rbp+4Fh+arg_20], ebx
0x1800afb19  jz      loc_1800AFBC1
0x1800afb1f  call    cs:__imp_GetFileAttributesW
0x1800afb25  mov     rcx, [rdi+8]
0x1800afb29  imul    r11, r12, 250h
0x1800afb30  mov     [r11+rcx+28h], eax
0x1800afb35  mov     rax, [rdi+8]
0x1800afb39  cmp     dword ptr [r11+rax+28h], 0FFFFFFFFh
0x1800afb3f  jnz     short loc_1800AFBA9
0x1800afb41  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afb48  lea     rax, WPP_GLOBAL_Control
0x1800afb4f  cmp     rcx, rax
0x1800afb52  jz      short loc_1800AFB8B
0x1800afb54  mov     ebx, 1
0x1800afb59  test    [rcx+1Ch], bl
0x1800afb5c  jz      short loc_1800AFB8B
0x1800afb5e  cmp     byte ptr [rcx+19h], 2
0x1800afb62  jb      short loc_1800AFB8B
0x1800afb64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afb69  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afb70  lea     edx, [rbx+1Fh]
0x1800afb73  mov     r9d, eax
0x1800afb76  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi
0x1800afb7b  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1800afb82  mov     rcx, [rcx+10h]
0x1800afb86  call    WPP_SF_DS
0x1800afb8b  call    cs:__imp_GetLastError
0x1800afb91  mov     ebx, eax
0x1800afb93  test    eax, eax
0x1800afb95  jle     loc_1800AFF67
0x1800afb9b  movzx   ebx, ax
0x1800afb9e  or      ebx, 80070000h
0x1800afba4  jmp     loc_1800AFF67
0x1800afba9  mov     [r11+rax+48h], ebx
0x1800afbae  mov     ecx, 4044h
0x1800afbb3  mov     rax, [rdi+8]
0x1800afbb7  mov     [r11+rax+44h], ebx
0x1800afbbc  jmp     loc_1800AFD18
0x1800afbc1  xorps   xmm0, xmm0
0x1800afbc4  mov     [rsp+0C0h+hTemplateFile], rbx; hTemplateFile
0x1800afbc9  xor     eax, eax
0x1800afbcb  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800afbcf  xor     r9d, r9d; lpSecurityAttributes
0x1800afbd2  mov     [rbp+4Fh+FileInformation.nFileIndexLow], eax
0x1800afbd5  mov     edx, 80000000h; dwDesiredAccess
0x1800afbda  movups  xmmword ptr [rbp+4Fh+FileInformation.dwFileAttributes], xmm0
0x1800afbde  lea     r8d, [rax+3]; dwShareMode
0x1800afbe2  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800afbe7  movups  xmmword ptr [rbp+4Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800afbeb  movups  xmmword ptr [rbp+4Fh+FileInformation.nFileSizeHigh], xmm0
0x1800afbef  call    cs:__imp_CreateFileW
0x1800afbf5  mov     r14, rax
0x1800afbf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800afbfc  jnz     short loc_1800AFC53
0x1800afbfe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afc05  lea     rax, WPP_GLOBAL_Control
0x1800afc0c  cmp     rcx, rax
0x1800afc0f  jz      loc_1800AFB8B
0x1800afc15  lea     ebx, [r14+2]
0x1800afc19  test    [rcx+1Ch], bl
0x1800afc1c  jz      loc_1800AFB8B
0x1800afc22  cmp     byte ptr [rcx+19h], 2
0x1800afc26  jb      loc_1800AFB8B
0x1800afc2c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afc31  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afc38  lea     edx, [rbx+20h]
0x1800afc3b  mov     r9d, eax
0x1800afc3e  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1800afc45  mov     rcx, [rcx+10h]
0x1800afc49  call    WPP_SF_d
0x1800afc4e  jmp     loc_1800AFB8B
0x1800afc53  xorps   xmm0, xmm0
0x1800afc56  lea     rdx, [rbp+4Fh+FileInformation]; lpFileInformation
0x1800afc5a  xor     eax, eax
0x1800afc5c  mov     rcx, r14; hFile
0x1800afc5f  movups  xmmword ptr [rbp+4Fh+FileInformation.dwFileAttributes], xmm0
0x1800afc63  mov     [rbp+4Fh+FileInformation.nFileIndexLow], eax
0x1800afc66  movups  xmmword ptr [rbp+4Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800afc6a  movups  xmmword ptr [rbp+4Fh+FileInformation.nFileSizeHigh], xmm0
0x1800afc6e  call    cs:__imp_GetFileInformationByHandle
0x1800afc74  test    eax, eax
0x1800afc76  jnz     short loc_1800AFCDB
0x1800afc78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afc7f  lea     rax, WPP_GLOBAL_Control
0x1800afc86  cmp     rcx, rax
0x1800afc89  jz      short loc_1800AFCBD
0x1800afc8b  mov     ebx, 1
0x1800afc90  test    [rcx+1Ch], bl
0x1800afc93  jz      short loc_1800AFCBD
0x1800afc95  cmp     byte ptr [rcx+19h], 2
0x1800afc99  jb      short loc_1800AFCBD
0x1800afc9b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afca0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afca7  lea     edx, [rbx+21h]
0x1800afcaa  mov     r9d, eax
0x1800afcad  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1800afcb4  mov     rcx, [rcx+10h]
0x1800afcb8  call    WPP_SF_d
0x1800afcbd  call    cs:__imp_GetLastError
0x1800afcc3  mov     ebx, eax
0x1800afcc5  test    eax, eax
0x1800afcc7  jle     loc_1800AFEB5
0x1800afccd  movzx   ebx, ax
0x1800afcd0  or      ebx, 80070000h
0x1800afcd6  jmp     loc_1800AFEB5
0x1800afcdb  mov     rcx, [rdi+8]
0x1800afcdf  mov     eax, [rbp+4Fh+FileInformation.dwFileAttributes]
0x1800afce2  imul    r11, r12, 250h
0x1800afce9  mov     [r11+rcx+28h], eax
0x1800afcee  mov     rcx, [rdi+8]
0x1800afcf2  mov     rax, qword ptr [rbp+4Fh+FileInformation.ftLastWriteTime.dwLowDateTime]
0x1800afcf6  mov     [r11+rcx+3Ch], rax
0x1800afcfb  mov     eax, [rbp+4Fh+FileInformation.nFileSizeLow]
0x1800afcfe  mov     rcx, [rdi+8]
0x1800afd02  mov     [r11+rcx+48h], eax
0x1800afd07  mov     eax, [rbp+4Fh+FileInformation.nFileSizeHigh]
0x1800afd0a  mov     rcx, [rdi+8]
0x1800afd0e  mov     [r11+rcx+44h], eax
0x1800afd13  mov     ecx, 4064h
0x1800afd18  mov     rax, [rdi+8]
0x1800afd1c  mov     [r11+rax+4], ecx
0x1800afd21  mov     ecx, 4
0x1800afd26  mov     rdx, [rdi]
0x1800afd29  mov     rax, [rdi+8]
0x1800afd2d  add     rdx, 4
0x1800afd31  add     rdx, r11
0x1800afd34  add     rax, 4
0x1800afd38  add     rax, r11
0x1800afd3b  lea     r8d, [rcx+7Ch]
0x1800afd3f  movups  xmm0, xmmword ptr [rax]
0x1800afd42  movups  xmmword ptr [rdx], xmm0
0x1800afd45  movups  xmm1, xmmword ptr [rax+10h]
0x1800afd49  movups  xmmword ptr [rdx+10h], xmm1
0x1800afd4d  movups  xmm0, xmmword ptr [rax+20h]
0x1800afd51  movups  xmmword ptr [rdx+20h], xmm0
0x1800afd55  movups  xmm1, xmmword ptr [rax+30h]
0x1800afd59  movups  xmmword ptr [rdx+30h], xmm1
0x1800afd5d  movups  xmm0, xmmword ptr [rax+40h]
0x1800afd61  movups  xmmword ptr [rdx+40h], xmm0
0x1800afd65  movups  xmm1, xmmword ptr [rax+50h]
0x1800afd69  movups  xmmword ptr [rdx+50h], xmm1
0x1800afd6d  movups  xmm0, xmmword ptr [rax+60h]
0x1800afd71  movups  xmmword ptr [rdx+60h], xmm0
0x1800afd75  movups  xmm1, xmmword ptr [rax+70h]
0x1800afd79  add     rax, r8
0x1800afd7c  movups  xmmword ptr [rdx+70h], xmm1
0x1800afd80  add     rdx, r8
0x1800afd83  sub     rcx, 1
0x1800afd87  jnz     short loc_1800AFD3F
0x1800afd89  movups  xmm0, xmmword ptr [rax]
0x1800afd8c  mov     r8, rsi; unsigned __int16 *
0x1800afd8f  mov     esi, 208h
0x1800afd94  movups  xmmword ptr [rdx], xmm0
0x1800afd97  movups  xmm1, xmmword ptr [rax+10h]
0x1800afd9b  movups  xmmword ptr [rdx+10h], xmm1
0x1800afd9f  movups  xmm0, xmmword ptr [rax+20h]
0x1800afda3  movups  xmmword ptr [rdx+20h], xmm0
0x1800afda7  movups  xmm1, xmmword ptr [rax+30h]
0x1800afdab  movups  xmmword ptr [rdx+30h], xmm1
0x1800afdaf  movups  xmm0, xmmword ptr [rax+40h]
0x1800afdb3  movups  xmmword ptr [rdx+40h], xmm0
0x1800afdb7  mov     rcx, [rdi+8]
0x1800afdbb  mov     edx, esi; unsigned __int64
0x1800afdbd  add     rcx, 4Ch ; 'L'
0x1800afdc1  add     rcx, r11; unsigned __int16 *
0x1800afdc4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800afdc9  mov     ebx, eax
0x1800afdcb  test    eax, eax
0x1800afdcd  jns     short loc_1800AFE33
0x1800afdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afdd6  lea     rax, WPP_GLOBAL_Control
0x1800afddd  cmp     rcx, rax
0x1800afde0  jz      loc_1800AFEB5
0x1800afde6  test    byte ptr [rcx+1Ch], 8
0x1800afdea  jz      loc_1800AFEB5
0x1800afdf0  cmp     byte ptr [rcx+19h], 2
0x1800afdf4  jb      loc_1800AFEB5
0x1800afdfa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afdff  mov     edx, 23h ; '#'
0x1800afe04  lea     rcx, aStringcbcopyFa; "StringCbCopy failed!"
0x1800afe0b  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x1800afe0f  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x1800afe14  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
  ... truncated ...
```
