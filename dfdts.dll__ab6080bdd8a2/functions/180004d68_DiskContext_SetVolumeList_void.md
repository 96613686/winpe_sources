# DiskContext::SetVolumeList(void)

- ea: `0x180004d68`
- end: `0x1800050ae`
- name: `?SetVolumeList@DiskContext@@AEAAKXZ`
- size: `838`
- prototype: `__int64 __fastcall(DiskContext *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180006c74`

## callees

- `0x180001fd6`
- `0x180002c90`
- `0x180003984`
- `0x180003bac`
- `0x18000454c`
- `0x180004d68`
- `0x18000833b`

## import_xrefs

- `KERNEL32!FindVolumeClose` at `0x18000505d`
- `KERNEL32!FindVolumeClose` at `0x18000505d`
- `KERNEL32!FindNextVolumeW` at `0x180004fdd`
- `KERNEL32!FindNextVolumeW` at `0x180004fdd`
- `KERNEL32!FindFirstVolumeW` at `0x180004e89`
- `KERNEL32!FindFirstVolumeW` at `0x180004e89`
- `KERNEL32!CreateFileW` at `0x180004f48`
- `KERNEL32!CreateFileW` at `0x180004f48`
- `KERNEL32!HeapAlloc` at `0x180004d93`
- `KERNEL32!HeapAlloc` at `0x180004e44`
- `KERNEL32!HeapAlloc` at `0x180004e69`
- `KERNEL32!HeapAlloc` at `0x180004d93`
- `KERNEL32!HeapAlloc` at `0x180004e44`
- `KERNEL32!HeapAlloc` at `0x180004e69`
- `KERNEL32!GetProcessHeap` at `0x180004d7b`
- `KERNEL32!GetProcessHeap` at `0x180004e30`
- `KERNEL32!GetProcessHeap` at `0x180004e5a`
- `KERNEL32!GetProcessHeap` at `0x180005065`
- `KERNEL32!GetProcessHeap` at `0x18000507e`
- `KERNEL32!GetProcessHeap` at `0x180004d7b`
- `KERNEL32!GetProcessHeap` at `0x180004e30`
- `KERNEL32!GetProcessHeap` at `0x180004e5a`
- `KERNEL32!GetProcessHeap` at `0x180005065`
- `KERNEL32!GetProcessHeap` at `0x18000507e`
- `KERNEL32!HeapFree` at `0x180005073`
- `KERNEL32!HeapFree` at `0x18000508c`
- `KERNEL32!HeapFree` at `0x180005073`
- `KERNEL32!HeapFree` at `0x18000508c`
- `KERNEL32!CloseHandle` at `0x180004fa6`
- `KERNEL32!CloseHandle` at `0x180005054`
- `KERNEL32!CloseHandle` at `0x180004fa6`
- `KERNEL32!CloseHandle` at `0x180005054`
- `KERNEL32!GetLastError` at `0x180004e98`
- `KERNEL32!GetLastError` at `0x180004f57`
- `KERNEL32!GetLastError` at `0x180004fee`
- `KERNEL32!GetLastError` at `0x180004e98`
- `KERNEL32!GetLastError` at `0x180004f57`
- `KERNEL32!GetLastError` at `0x180004fee`

## pseudocode

```c
__int64 __fastcall DiskContext::SetVolumeList(DiskContext *this)
{
  HANDLE ProcessHeap; // rax
  LPVOID v3; // rax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  HANDLE v6; // rax
  WCHAR *v7; // r14
  HANDLE v8; // rax
  void *v9; // r15
  HANDLE FirstVolumeW; // r12
  DWORD LastError; // eax
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // rbx
  HANDLE FileW; // rax
  void *v16; // rbp
  char v17; // al
  DWORD v18; // eax
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  HANDLE v22; // rax
  HANDLE v23; // rax
  __int64 result; // rax

  ProcessHeap = GetProcessHeap();
  v3 = HeapAlloc(ProcessHeap, 8u, 0x104u);
  *((_QWORD *)this + 76) = v3;
  if ( v3 )
  {
    v5 = DiskContext::SetDiskNumber(this);
    v4 = v5;
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, v5);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
          *((unsigned int *)this + 156));
      v6 = GetProcessHeap();
      v7 = (WCHAR *)HeapAlloc(v6, 8u, 0x208u);
      if ( v7 )
      {
        v8 = GetProcessHeap();
        v9 = HeapAlloc(v8, 8u, 0x208u);
        if ( v9 )
        {
          FirstVolumeW = FindFirstVolumeW(v7, 0x104u);
          if ( FirstVolumeW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
                LastError);
          }
          else
          {
            while ( 1 )
            {
              v12 = 260;
              v13 = v7;
              do
              {
                if ( !*v13 )
                  break;
                ++v13;
                --v12;
              }
              while ( v12 );
              v14 = (260 - v12) & -(__int64)(v12 != 0);
              if ( !v12 )
                break;
              memcpy_0(v9, v7, 2 * v14 - 2);
              *((_WORD *)v9 + v14) = 0;
              FileW = CreateFileW((LPCWSTR)v9, 0, 3u, 0, 3u, 0x80u, 0);
              v16 = FileW;
              if ( FileW == (HANDLE)-1LL )
              {
                v17 = GetLastError();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    (unsigned int)&WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids,
                    (_DWORD)v9,
                    v17);
                }
              }
              else
              {
                v4 = DiskContext::EnumerateDiskExtents(this, FileW, v7);
                if ( v4 )
                {
                  CloseHandle(v16);
                  goto LABEL_39;
                }
                CloseHandle(v16);
              }
              memset_0(v7, 0, 0x208u);
              memset_0(v9, 0, 0x208u);
              if ( !FindNextVolumeW(FirstVolumeW, v7, 0x104u) )
              {
                v18 = GetLastError();
                v4 = v18;
                if ( v18 != 18 )
                {
                  v19 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    v20 = 32;
                    v21 = v18;
LABEL_36:
                    WPP_SF_d(v19[2], v20, &WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids, v21);
                    goto LABEL_39;
                  }
                }
                goto LABEL_39;
              }
            }
            v4 = 87;
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v20 = 30;
              v21 = 87;
              goto LABEL_36;
            }
LABEL_39:
            FindVolumeClose(FirstVolumeW);
          }
        }
        else
        {
          v4 = 8;
        }
        v22 = GetProcessHeap();
        HeapFree(v22, 0, v7);
        if ( v9 )
        {
          v23 = GetProcessHeap();
          HeapFree(v23, 0, v9);
        }
      }
      else
      {
        v4 = 8;
      }
    }
  }
  else
  {
    v4 = 14;
  }
  result = 0;
  if ( !*((_QWORD *)this + 77) )
    return v4;
  return result;
}

```

## disassembly

```asm
0x180004d68  push    rbx
0x180004d6a  push    rbp
0x180004d6b  push    rdi
0x180004d6c  push    r12
0x180004d6e  push    r13
0x180004d70  push    r14
0x180004d72  push    r15
0x180004d74  sub     rsp, 40h
0x180004d78  mov     r13, rcx
0x180004d7b  call    cs:__imp_GetProcessHeap
0x180004d81  mov     r12d, 8
0x180004d87  mov     r8d, 104h; dwBytes
0x180004d8d  mov     rcx, rax; hHeap
0x180004d90  mov     edx, r12d; dwFlags
0x180004d93  call    cs:__imp_HeapAlloc
0x180004d99  xor     ebp, ebp
0x180004d9b  mov     [r13+260h], rax
0x180004da2  test    rax, rax
0x180004da5  jnz     short loc_180004DAF
0x180004da7  lea     ebx, [rax+0Eh]
0x180004daa  jmp     loc_180005092
0x180004daf  mov     rcx, r13; this
0x180004db2  call    ?SetDiskNumber@DiskContext@@AEAAKXZ; DiskContext::SetDiskNumber(void)
0x180004db7  mov     ebx, eax
0x180004db9  test    eax, eax
0x180004dbb  jz      short loc_180004DFB
0x180004dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dc4  lea     rdi, WPP_GLOBAL_Control
0x180004dcb  cmp     rcx, rdi
0x180004dce  jz      loc_180005092
0x180004dd4  test    byte ptr [rcx+1Ch], 1
0x180004dd8  jz      loc_180005092
0x180004dde  mov     rcx, [rcx+10h]
0x180004de2  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004de9  mov     edx, 1Bh
0x180004dee  mov     r9d, eax
0x180004df1  call    WPP_SF_d
0x180004df6  jmp     loc_180005092
0x180004dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e02  lea     rdi, WPP_GLOBAL_Control
0x180004e09  cmp     rcx, rdi
0x180004e0c  jz      short loc_180004E30
0x180004e0e  test    byte ptr [rcx+1Ch], 4
0x180004e12  jz      short loc_180004E30
0x180004e14  mov     r9d, [r13+270h]
0x180004e1b  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004e22  mov     rcx, [rcx+10h]
0x180004e26  mov     edx, 1Ch
0x180004e2b  call    WPP_SF_d
0x180004e30  call    cs:__imp_GetProcessHeap
0x180004e36  mov     ebx, 208h
0x180004e3b  mov     edx, r12d; dwFlags
0x180004e3e  mov     rcx, rax; hHeap
0x180004e41  mov     r8d, ebx; dwBytes
0x180004e44  call    cs:__imp_HeapAlloc
0x180004e4a  mov     r14, rax
0x180004e4d  test    rax, rax
0x180004e50  jnz     short loc_180004E5A
0x180004e52  mov     ebx, r12d
0x180004e55  jmp     loc_180005092
0x180004e5a  call    cs:__imp_GetProcessHeap
0x180004e60  mov     r8, rbx; dwBytes
0x180004e63  mov     edx, r12d; dwFlags
0x180004e66  mov     rcx, rax; hHeap
0x180004e69  call    cs:__imp_HeapAlloc
0x180004e6f  mov     r15, rax
0x180004e72  test    rax, rax
0x180004e75  jnz     short loc_180004E7F
0x180004e77  mov     ebx, r12d
0x180004e7a  jmp     loc_180005065
0x180004e7f  mov     ebx, 104h
0x180004e84  mov     rcx, r14; lpszVolumeName
0x180004e87  mov     edx, ebx; cchBufferLength
0x180004e89  call    cs:__imp_FindFirstVolumeW
0x180004e8f  mov     r12, rax
0x180004e92  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004e96  jnz     short loc_180004ED7
0x180004e98  call    cs:__imp_GetLastError
0x180004e9e  mov     ebx, eax
0x180004ea0  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ea7  cmp     rcx, rdi
0x180004eaa  jz      loc_180005065
0x180004eb0  test    byte ptr [rcx+1Ch], 1
0x180004eb4  jz      loc_180005065
0x180004eba  mov     rcx, [rcx+10h]
0x180004ebe  lea     edx, [r12+1Eh]
0x180004ec3  mov     r9d, eax
0x180004ec6  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004ecd  call    WPP_SF_d
0x180004ed2  jmp     loc_180005065
0x180004ed7  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004edb  xor     r8d, r8d
0x180004ede  mov     rdx, rbx
0x180004ee1  mov     rax, r14
0x180004ee4  cmp     [rax], r8w
0x180004ee8  jz      short loc_180004EF4
0x180004eea  add     rax, 2
0x180004eee  sub     rdx, 1
0x180004ef2  jnz     short loc_180004EE4
0x180004ef4  mov     rcx, rbx
0x180004ef7  mov     rax, rdx
0x180004efa  sub     rcx, rdx
0x180004efd  neg     rax
0x180004f00  sbb     rbx, rbx
0x180004f03  and     rbx, rcx
0x180004f06  test    rdx, rdx
0x180004f09  jz      loc_180005017
0x180004f0f  lea     r8, ds:0FFFFFFFFFFFFFFFEh[rbx*2]; Size
0x180004f17  mov     rdx, r14; Src
0x180004f1a  mov     rcx, r15; void *
0x180004f1d  call    memcpy_0
0x180004f22  xor     ecx, ecx
0x180004f24  xor     r9d, r9d; lpSecurityAttributes
0x180004f27  mov     [rsp+78h+hTemplateFile], rcx; hTemplateFile
0x180004f2c  xor     edx, edx; dwDesiredAccess
0x180004f2e  mov     [r15+rbx*2], cx
0x180004f33  mov     [rsp+78h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180004f3b  lea     eax, [rcx+3]
0x180004f3e  mov     rcx, r15; lpFileName
0x180004f41  mov     r8d, eax; dwShareMode
0x180004f44  mov     [rsp+78h+dwCreationDisposition], eax; dwCreationDisposition
0x180004f48  call    cs:__imp_CreateFileW
0x180004f4e  mov     rbp, rax
0x180004f51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004f55  jnz     short loc_180004F8B
0x180004f57  call    cs:__imp_GetLastError
0x180004f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f64  cmp     rcx, rdi
0x180004f67  jz      short loc_180004FB0
0x180004f69  test    byte ptr [rcx+1Ch], 1
0x180004f6d  jz      short loc_180004FB0
0x180004f6f  mov     rcx, [rcx+10h]
0x180004f73  lea     edx, [rbp+20h]
0x180004f76  mov     r9, r15
0x180004f79  mov     [rsp+78h+dwCreationDisposition], eax
0x180004f7d  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180004f84  call    WPP_SF_Sd
0x180004f89  jmp     short loc_180004FB0
0x180004f8b  mov     r8, r14; unsigned __int16 *
0x180004f8e  mov     rdx, rbp; hDevice
0x180004f91  mov     rcx, r13; this
0x180004f94  call    ?EnumerateDiskExtents@DiskContext@@AEAAKPEAXPEAG@Z; DiskContext::EnumerateDiskExtents(void *,ushort *)
0x180004f99  mov     ebx, eax
0x180004f9b  test    eax, eax
0x180004f9d  jnz     loc_180005051
0x180004fa3  mov     rcx, rbp; hObject
0x180004fa6  call    cs:__imp_CloseHandle
0x180004fac  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180004fb0  mov     ebx, 208h
0x180004fb5  xor     edx, edx; Val
0x180004fb7  mov     r8d, ebx; Size
0x180004fba  mov     rcx, r14; void *
0x180004fbd  call    memset_0
0x180004fc2  mov     r8d, ebx; Size
0x180004fc5  xor     edx, edx; Val
0x180004fc7  mov     rcx, r15; void *
0x180004fca  call    memset_0
0x180004fcf  mov     ebx, 104h
0x180004fd4  mov     rdx, r14; lpszVolumeName
0x180004fd7  mov     r8d, ebx; cchBufferLength
0x180004fda  mov     rcx, r12; hFindVolume
0x180004fdd  call    cs:__imp_FindNextVolumeW
0x180004fe3  xor     r8d, r8d
0x180004fe6  test    eax, eax
0x180004fe8  jnz     loc_180004EDE
0x180004fee  call    cs:__imp_GetLastError
0x180004ff4  mov     ebx, eax
0x180004ff6  cmp     eax, 12h
0x180004ff9  jz      short loc_18000505A
0x180004ffb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005002  cmp     rcx, rdi
0x180005005  jz      short loc_18000505A
0x180005007  test    byte ptr [rcx+1Ch], 1
0x18000500b  jz      short loc_18000505A
0x18000500d  mov     edx, 20h ; ' '
0x180005012  mov     r9d, eax
0x180005015  jmp     short loc_18000503B
0x180005017  neg     rdx
0x18000501a  sbb     ebx, ebx
0x18000501c  not     ebx
0x18000501e  and     ebx, 57h
0x180005021  mov     rcx, cs:WPP_GLOBAL_Control
0x180005028  cmp     rcx, rdi
0x18000502b  jz      short loc_18000504B
0x18000502d  test    byte ptr [rcx+1Ch], 1
0x180005031  jz      short loc_18000504B
0x180005033  mov     edx, 1Eh
0x180005038  mov     r9d, ebx
0x18000503b  mov     rcx, [rcx+10h]
0x18000503f  lea     r8, WPP_6840784a3f2339c3fb8e3bd3d3f5f082_Traceguids
0x180005046  call    WPP_SF_d
0x18000504b  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x18000504f  jz      short loc_18000505A
0x180005051  mov     rcx, rbp; hObject
0x180005054  call    cs:__imp_CloseHandle
0x18000505a  mov     rcx, r12; hFindVolume
0x18000505d  call    cs:__imp_FindVolumeClose
0x180005063  xor     ebp, ebp
0x180005065  call    cs:__imp_GetProcessHeap
0x18000506b  mov     r8, r14; lpMem
0x18000506e  xor     edx, edx; dwFlags
0x180005070  mov     rcx, rax; hHeap
0x180005073  call    cs:__imp_HeapFree
0x180005079  test    r15, r15
0x18000507c  jz      short loc_180005092
0x18000507e  call    cs:__imp_GetProcessHeap
0x180005084  mov     r8, r15; lpMem
0x180005087  xor     edx, edx; dwFlags
0x180005089  mov     rcx, rax; hHeap
0x18000508c  call    cs:__imp_HeapFree
0x180005092  cmp     [r13+268h], rbp
0x180005099  mov     eax, ebp
0x18000509b  cmovbe  eax, ebx
0x18000509e  add     rsp, 40h
0x1800050a2  pop     r15
0x1800050a4  pop     r14
0x1800050a6  pop     r13
0x1800050a8  pop     r12
0x1800050aa  pop     rdi
0x1800050ab  pop     rbp
0x1800050ac  pop     rbx
0x1800050ad  retn
```
