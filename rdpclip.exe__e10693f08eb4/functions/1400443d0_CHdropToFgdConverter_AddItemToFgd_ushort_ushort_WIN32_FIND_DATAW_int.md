# CHdropToFgdConverter::AddItemToFgd(ushort *,ushort *,_WIN32_FIND_DATAW *,int)

- ea: `0x1400443d0`
- end: `0x140044a1f`
- name: `?AddItemToFgd@CHdropToFgdConverter@@AEAAJPEAG0PEAU_WIN32_FIND_DATAW@@H@Z`
- size: `1615`
- prototype: `__int64 __fastcall(CHdropToFgdConverter *this, unsigned __int16 *, unsigned __int16 *, struct _WIN32_FIND_DATAW *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x140043bf8`
- `0x140044dc4`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140005750`
- `0x140008bc8`
- `0x14000a640`
- `0x1400443d0`
- `0x1400453c0`
- `0x14006a120`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044755`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044755`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004495e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004495e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400445b7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400445b7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x140044706`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x140044706`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044687`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140044687`

## string_xrefs

- `0x14004489c`: `StringCbCopy failed!`

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
  signed int v12; // ebx
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
        v12 = CHdropToFgdConverter::ResizeFgds(this, v17);
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
0x1400443d0  push    rbp
0x1400443d2  push    rbx
0x1400443d3  push    rsi
0x1400443d4  push    rdi
0x1400443d5  push    r12
0x1400443d7  push    r13
0x1400443d9  push    r14
0x1400443db  lea     rbp, [rsp-1Fh]
0x1400443e0  sub     rsp, 90h
0x1400443e7  mov     rax, cs:__security_cookie
0x1400443ee  xor     rax, rsp
0x1400443f1  mov     [rbp+4Fh+var_40], rax
0x1400443f5  xor     ebx, ebx
0x1400443f7  mov     rax, r8
0x1400443fa  mov     r13, r9
0x1400443fd  mov     [rbp+4Fh+var_80], rax
0x140044401  mov     rsi, rdx
0x140044404  mov     rdi, rcx
0x140044407  cmp     [rcx+8], rbx
0x14004440b  jz      loc_1400449B5
0x140044411  cmp     [rcx], rbx
0x140044414  jz      loc_1400449B5
0x14004441a  test    rdx, rdx
0x14004441d  jz      loc_140044969
0x140044423  test    rax, rax
0x140044426  jz      loc_140044969
0x14004442c  cmp     [rbp+4Fh+arg_20], ebx
0x14004442f  jnz     loc_1400444CD
0x140044435  mov     rcx, [rcx+18h]
0x140044439  test    rcx, rcx
0x14004443c  jz      loc_1400444CD
0x140044442  mov     rax, [rcx]
0x140044445  mov     rax, [rax+20h]
0x140044449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004444e  test    eax, eax
0x140044450  jnz     short loc_1400444CD
0x140044452  mov     edx, [rdi+20h]
0x140044455  mov     rcx, [rdi+18h]
0x140044459  lea     r8d, [rdx+1]
0x14004445d  mov     rax, [rcx]
0x140044460  mov     [rdi+20h], r8d
0x140044464  xor     r8d, r8d
0x140044467  mov     rax, [rax+28h]
0x14004446b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044470  mov     rdx, cs:WPP_GLOBAL_Control
0x140044477  lea     rax, WPP_GLOBAL_Control
0x14004447e  mov     ebx, 1
0x140044483  cmp     rdx, rax
0x140044486  jz      loc_1400449FF
0x14004448c  test    [rdx+1Ch], bl
0x14004448f  jz      loc_1400449FF
0x140044495  lea     ecx, [rbx+3]
0x140044498  cmp     [rdx+19h], cl
0x14004449b  jb      loc_1400449FF
0x1400444a1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400444a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400444ad  lea     edx, [rbx+1Dh]
0x1400444b0  mov     r9d, eax
0x1400444b3  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi
0x1400444b8  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1400444bf  mov     rcx, [rcx+10h]
0x1400444c3  call    WPP_SF_DS
0x1400444c8  jmp     loc_1400449FF
0x1400444cd  mov     rax, [rdi+8]
0x1400444d1  mov     ecx, [rdi+10h]
0x1400444d4  mov     r12d, [rax]
0x1400444d7  imul    eax, r12d, 250h
0x1400444de  add     eax, 254h
0x1400444e3  cmp     ecx, eax
0x1400444e5  jnb     loc_14004456C
0x1400444eb  lea     edx, [rcx+rax]
0x1400444ee  cmp     edx, ecx
0x1400444f0  jb      short loc_1400444F6
0x1400444f2  cmp     edx, eax
0x1400444f4  jnb     short loc_1400444F8
0x1400444f6  mov     edx, eax; unsigned int
0x1400444f8  mov     rcx, rdi; this
0x1400444fb  call    ?ResizeFgds@CHdropToFgdConverter@@AEAAJI@Z; CHdropToFgdConverter::ResizeFgds(uint)
0x140044500  mov     ebx, eax
0x140044502  test    eax, eax
0x140044504  jns     short loc_14004456A
0x140044506  mov     rcx, cs:WPP_GLOBAL_Control
0x14004450d  lea     rax, WPP_GLOBAL_Control
0x140044514  cmp     rcx, rax
0x140044517  jz      loc_1400449FF
0x14004451d  test    byte ptr [rcx+1Ch], 8
0x140044521  jz      loc_1400449FF
0x140044527  cmp     byte ptr [rcx+19h], 2
0x14004452b  jb      loc_1400449FF
0x140044531  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044536  lea     rcx, aResizefgdsFail; "ResizeFgds failed!"
0x14004453d  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x140044541  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x140044546  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x14004454d  mov     rcx, cs:WPP_GLOBAL_Control
0x140044554  mov     edx, 1Fh
0x140044559  mov     r9d, eax
0x14004455c  mov     rcx, [rcx+10h]
0x140044560  call    WPP_SF_DsD
0x140044565  jmp     loc_1400449FF
0x14004456a  xor     ebx, ebx
0x14004456c  mov     r14, rbx
0x14004456f  test    r13, r13
0x140044572  jz      short loc_1400445AB
0x140044574  mov     rcx, [rdi+8]
0x140044578  mov     eax, [r13+0]
0x14004457c  imul    r11, r12, 250h
0x140044583  mov     [r11+rcx+28h], eax
0x140044588  mov     rcx, [rdi+8]
0x14004458c  mov     rax, [r13+14h]
0x140044590  mov     [r11+rcx+3Ch], rax
0x140044595  mov     eax, [r13+20h]
0x140044599  mov     rcx, [rdi+8]
0x14004459d  mov     [r11+rcx+48h], eax
0x1400445a2  mov     eax, [r13+1Ch]
0x1400445a6  jmp     loc_1400447A2
0x1400445ab  mov     rcx, rsi; lpFileName
0x1400445ae  cmp     [rbp+4Fh+arg_20], ebx
0x1400445b1  jz      loc_140044659
0x1400445b7  call    cs:__imp_GetFileAttributesW
0x1400445bd  mov     rcx, [rdi+8]
0x1400445c1  imul    r11, r12, 250h
0x1400445c8  mov     [r11+rcx+28h], eax
0x1400445cd  mov     rax, [rdi+8]
0x1400445d1  cmp     dword ptr [r11+rax+28h], 0FFFFFFFFh
0x1400445d7  jnz     short loc_140044641
0x1400445d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400445e0  lea     rax, WPP_GLOBAL_Control
0x1400445e7  cmp     rcx, rax
0x1400445ea  jz      short loc_140044623
0x1400445ec  mov     ebx, 1
0x1400445f1  test    [rcx+1Ch], bl
0x1400445f4  jz      short loc_140044623
0x1400445f6  cmp     byte ptr [rcx+19h], 2
0x1400445fa  jb      short loc_140044623
0x1400445fc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044601  mov     rcx, cs:WPP_GLOBAL_Control
0x140044608  lea     edx, [rbx+1Fh]
0x14004460b  mov     r9d, eax
0x14004460e  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rsi
0x140044613  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x14004461a  mov     rcx, [rcx+10h]
0x14004461e  call    WPP_SF_DS
0x140044623  call    cs:__imp_GetLastError
0x140044629  mov     ebx, eax
0x14004462b  test    eax, eax
0x14004462d  jle     loc_1400449FF
0x140044633  movzx   ebx, ax
0x140044636  or      ebx, 80070000h
0x14004463c  jmp     loc_1400449FF
0x140044641  mov     [r11+rax+48h], ebx
0x140044646  mov     ecx, 4044h
0x14004464b  mov     rax, [rdi+8]
0x14004464f  mov     [r11+rax+44h], ebx
0x140044654  jmp     loc_1400447B0
0x140044659  xorps   xmm0, xmm0
0x14004465c  mov     [rsp+0C0h+hTemplateFile], rbx; hTemplateFile
0x140044661  xor     eax, eax
0x140044663  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x140044667  xor     r9d, r9d; lpSecurityAttributes
0x14004466a  mov     [rbp+4Fh+FileInformation.nFileIndexLow], eax
0x14004466d  mov     edx, 80000000h; dwDesiredAccess
0x140044672  movups  xmmword ptr [rbp+4Fh+FileInformation.dwFileAttributes], xmm0
0x140044676  lea     r8d, [rax+3]; dwShareMode
0x14004467a  mov     [rsp+0C0h+dwCreationDisposition], r8d; dwCreationDisposition
0x14004467f  movups  xmmword ptr [rbp+4Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140044683  movups  xmmword ptr [rbp+4Fh+FileInformation.nFileSizeHigh], xmm0
0x140044687  call    cs:__imp_CreateFileW
0x14004468d  mov     r14, rax
0x140044690  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140044694  jnz     short loc_1400446EB
0x140044696  mov     rcx, cs:WPP_GLOBAL_Control
0x14004469d  lea     rax, WPP_GLOBAL_Control
0x1400446a4  cmp     rcx, rax
0x1400446a7  jz      loc_140044623
0x1400446ad  lea     ebx, [r14+2]
0x1400446b1  test    [rcx+1Ch], bl
0x1400446b4  jz      loc_140044623
0x1400446ba  cmp     byte ptr [rcx+19h], 2
0x1400446be  jb      loc_140044623
0x1400446c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400446c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400446d0  lea     edx, [rbx+20h]
0x1400446d3  mov     r9d, eax
0x1400446d6  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x1400446dd  mov     rcx, [rcx+10h]
0x1400446e1  call    WPP_SF_d
0x1400446e6  jmp     loc_140044623
0x1400446eb  xorps   xmm0, xmm0
0x1400446ee  lea     rdx, [rbp+4Fh+FileInformation]; lpFileInformation
0x1400446f2  xor     eax, eax
0x1400446f4  mov     rcx, r14; hFile
0x1400446f7  movups  xmmword ptr [rbp+4Fh+FileInformation.dwFileAttributes], xmm0
0x1400446fb  mov     [rbp+4Fh+FileInformation.nFileIndexLow], eax
0x1400446fe  movups  xmmword ptr [rbp+4Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x140044702  movups  xmmword ptr [rbp+4Fh+FileInformation.nFileSizeHigh], xmm0
0x140044706  call    cs:__imp_GetFileInformationByHandle
0x14004470c  test    eax, eax
0x14004470e  jnz     short loc_140044773
0x140044710  mov     rcx, cs:WPP_GLOBAL_Control
0x140044717  lea     rax, WPP_GLOBAL_Control
0x14004471e  cmp     rcx, rax
0x140044721  jz      short loc_140044755
0x140044723  mov     ebx, 1
0x140044728  test    [rcx+1Ch], bl
0x14004472b  jz      short loc_140044755
0x14004472d  cmp     byte ptr [rcx+19h], 2
0x140044731  jb      short loc_140044755
0x140044733  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044738  mov     rcx, cs:WPP_GLOBAL_Control
0x14004473f  lea     edx, [rbx+21h]
0x140044742  mov     r9d, eax
0x140044745  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
0x14004474c  mov     rcx, [rcx+10h]
0x140044750  call    WPP_SF_d
0x140044755  call    cs:__imp_GetLastError
0x14004475b  mov     ebx, eax
0x14004475d  test    eax, eax
0x14004475f  jle     loc_14004494D
0x140044765  movzx   ebx, ax
0x140044768  or      ebx, 80070000h
0x14004476e  jmp     loc_14004494D
0x140044773  mov     rcx, [rdi+8]
0x140044777  mov     eax, [rbp+4Fh+FileInformation.dwFileAttributes]
0x14004477a  imul    r11, r12, 250h
0x140044781  mov     [r11+rcx+28h], eax
0x140044786  mov     rcx, [rdi+8]
0x14004478a  mov     rax, qword ptr [rbp+4Fh+FileInformation.ftLastWriteTime.dwLowDateTime]
0x14004478e  mov     [r11+rcx+3Ch], rax
0x140044793  mov     eax, [rbp+4Fh+FileInformation.nFileSizeLow]
0x140044796  mov     rcx, [rdi+8]
0x14004479a  mov     [r11+rcx+48h], eax
0x14004479f  mov     eax, [rbp+4Fh+FileInformation.nFileSizeHigh]
0x1400447a2  mov     rcx, [rdi+8]
0x1400447a6  mov     [r11+rcx+44h], eax
0x1400447ab  mov     ecx, 4064h
0x1400447b0  mov     rax, [rdi+8]
0x1400447b4  mov     [r11+rax+4], ecx
0x1400447b9  mov     ecx, 4
0x1400447be  mov     rdx, [rdi]
0x1400447c1  mov     rax, [rdi+8]
0x1400447c5  add     rdx, 4
0x1400447c9  add     rdx, r11
0x1400447cc  add     rax, 4
0x1400447d0  add     rax, r11
0x1400447d3  lea     r8d, [rcx+7Ch]
0x1400447d7  movups  xmm0, xmmword ptr [rax]
0x1400447da  movups  xmmword ptr [rdx], xmm0
0x1400447dd  movups  xmm1, xmmword ptr [rax+10h]
0x1400447e1  movups  xmmword ptr [rdx+10h], xmm1
0x1400447e5  movups  xmm0, xmmword ptr [rax+20h]
0x1400447e9  movups  xmmword ptr [rdx+20h], xmm0
0x1400447ed  movups  xmm1, xmmword ptr [rax+30h]
0x1400447f1  movups  xmmword ptr [rdx+30h], xmm1
0x1400447f5  movups  xmm0, xmmword ptr [rax+40h]
0x1400447f9  movups  xmmword ptr [rdx+40h], xmm0
0x1400447fd  movups  xmm1, xmmword ptr [rax+50h]
0x140044801  movups  xmmword ptr [rdx+50h], xmm1
0x140044805  movups  xmm0, xmmword ptr [rax+60h]
0x140044809  movups  xmmword ptr [rdx+60h], xmm0
0x14004480d  movups  xmm1, xmmword ptr [rax+70h]
0x140044811  add     rax, r8
0x140044814  movups  xmmword ptr [rdx+70h], xmm1
0x140044818  add     rdx, r8
0x14004481b  sub     rcx, 1
0x14004481f  jnz     short loc_1400447D7
0x140044821  movups  xmm0, xmmword ptr [rax]
0x140044824  mov     r8, rsi; unsigned __int16 *
0x140044827  mov     esi, 208h
0x14004482c  movups  xmmword ptr [rdx], xmm0
0x14004482f  movups  xmm1, xmmword ptr [rax+10h]
0x140044833  movups  xmmword ptr [rdx+10h], xmm1
0x140044837  movups  xmm0, xmmword ptr [rax+20h]
0x14004483b  movups  xmmword ptr [rdx+20h], xmm0
0x14004483f  movups  xmm1, xmmword ptr [rax+30h]
0x140044843  movups  xmmword ptr [rdx+30h], xmm1
0x140044847  movups  xmm0, xmmword ptr [rax+40h]
0x14004484b  movups  xmmword ptr [rdx+40h], xmm0
0x14004484f  mov     rcx, [rdi+8]
0x140044853  mov     edx, esi; unsigned __int64
0x140044855  add     rcx, 4Ch ; 'L'
0x140044859  add     rcx, r11; unsigned __int16 *
0x14004485c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140044861  mov     ebx, eax
0x140044863  test    eax, eax
0x140044865  jns     short loc_1400448CB
0x140044867  mov     rcx, cs:WPP_GLOBAL_Control
0x14004486e  lea     rax, WPP_GLOBAL_Control
0x140044875  cmp     rcx, rax
0x140044878  jz      loc_14004494D
0x14004487e  test    byte ptr [rcx+1Ch], 8
0x140044882  jz      loc_14004494D
0x140044888  cmp     byte ptr [rcx+19h], 2
0x14004488c  jb      loc_14004494D
0x140044892  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140044897  mov     edx, 23h ; '#'
0x14004489c  lea     rcx, aStringcbcopyFa; "StringCbCopy failed!"
0x1400448a3  mov     [rsp+0C0h+dwFlagsAndAttributes], ebx
0x1400448a7  mov     qword ptr [rsp+0C0h+dwCreationDisposition], rcx
0x1400448ac  lea     r8, WPP_6b188fce9f953a3badf01269520c37ed_Traceguids
  ... truncated ...
```
