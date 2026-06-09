# FAX_RemoveMessage

- ea: `0x14001cb80`
- end: `0x14001cf5d`
- name: `FAX_RemoveMessage`
- size: `989`
- prototype: `unsigned int __fastcall(__int64, unsigned __int64, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004b98`
- `0x140004ce4`
- `0x140004df0`
- `0x140006b0c`
- `0x14000c5ac`
- `0x140012e20`
- `0x14001cb80`
- `0x140022970`
- `0x1400452ac`
- `0x1400552f0`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001cce7`
- `KERNEL32!GetLastError` at `0x14001cd48`
- `KERNEL32!GetLastError` at `0x14001cd7b`
- `KERNEL32!GetLastError` at `0x14001cce7`
- `KERNEL32!GetLastError` at `0x14001cd48`
- `KERNEL32!GetLastError` at `0x14001cd7b`
- `KERNEL32!FindFirstFileW` at `0x14001ccb2`
- `KERNEL32!FindFirstFileW` at `0x14001ccb2`
- `KERNEL32!FindClose` at `0x14001cd26`
- `KERNEL32!FindClose` at `0x14001cd26`
- `KERNEL32!LocalFree` at `0x14001ce90`
- `KERNEL32!LocalFree` at `0x14001ce90`
- `KERNEL32!DeleteFileW` at `0x14001cd71`
- `KERNEL32!DeleteFileW` at `0x14001cd71`
- `KERNEL32!EnterCriticalSection` at `0x14001cf0a`
- `KERNEL32!EnterCriticalSection` at `0x14001cf0a`
- `KERNEL32!LeaveCriticalSection` at `0x14001cf2f`
- `KERNEL32!LeaveCriticalSection` at `0x14001cf2f`
- `msvcrt!wcsrchr` at `0x14001ce0a`
- `msvcrt!wcsrchr` at `0x14001ce0a`

## pseudocode

```c
unsigned int __fastcall FAX_RemoveMessage(__int64 a1, unsigned __int64 a2, unsigned int a3)
{
  unsigned int result; // eax
  DWORD v6; // eax
  DWORD v7; // ebx
  HANDLE FirstFileW; // rcx
  unsigned __int64 v9; // rdi
  unsigned __int16 LastError; // ax
  unsigned __int16 v11; // ax
  wchar_t *v12; // rax
  CFaxArchiving *v13; // rcx
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  bool v17; // zf
  HLOCAL v18; // rsi
  unsigned int ArchiveEvent; // eax
  __int64 v20; // rax
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v23 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v21 = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 486, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  LODWORD(hMem) = 0;
  result = FaxSvcAccessCheck(0x2000000u, (int *)&hMem, &v21, 1);
  if ( !result )
  {
    if ( (v21 & 0xE03FF) == 0 )
      return 5;
    v6 = FindArchivedMessageAfterAccessCheck(a3, a2, v21, 0, FileName);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 487, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v6);
      }
    }
    else
    {
      FirstFileW = FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        v9 = 0;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          LastError = GetLastError();
          WPP_SF_hS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            488,
            (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            LastError,
            (__int64)FileName);
        }
      }
      else
      {
        v9 = FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
        if ( !FindClose(FirstFileW)
          && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v11 = GetLastError();
          WPP_SF_h(*((_QWORD *)WPP_GLOBAL_Control + 2), 489, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v11);
        }
      }
      if ( DeleteFileW(FileName) )
      {
        hMem = 0;
        v12 = wcsrchr(FileName, 0x5Cu);
        v14 = v12 + 1;
        if ( !v12 )
          v14 = 0;
        if ( v14 )
        {
          v15 = CFaxArchiving::ExtractComponentsFromArchiveFileName(v13, v14, &v23, &hMem);
          if ( v15 )
          {
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_Sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                492,
                (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (unsigned int)FileName,
                v15);
            }
          }
          else
          {
            v16 = 32;
            v17 = a3 == 0;
            v18 = hMem;
            if ( !v17 )
              v16 = 64;
            ArchiveEvent = CreateArchiveEvent(v23, v16, 1, hMem);
            if ( ArchiveEvent
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                491,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                ArchiveEvent);
            }
            if ( v18 )
              LocalFree(v18);
          }
        }
        else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 493, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, FileName);
        }
        if ( v9 )
        {
          EnterCriticalSection(&g_CsConfig);
          v20 = *((_QWORD *)g_pFaxConfig + 7);
          if ( v20 != -1 )
            *((_QWORD *)g_pFaxConfig + 7) = v20 - v9;
          LeaveCriticalSection(&g_CsConfig);
        }
        return v7;
      }
      v7 = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          490,
          (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
          v7,
          (__int64)FileName);
      }
      if ( v7 == 5 || v7 == 32 )
      {
        v7 = 7008;
      }
      else if ( v7 == 2 )
      {
        return 7009;
      }
    }
    if ( v7 == 8 || v7 == 14 )
      return 7001;
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x14001cb80  mov     [rsp-8+arg_0], rbx
0x14001cb85  push    rbp
0x14001cb86  push    rsi
0x14001cb87  push    rdi
0x14001cb88  push    r12
0x14001cb8a  push    r13
0x14001cb8c  lea     rbp, [rsp-3C0h]
0x14001cb94  sub     rsp, 4C0h
0x14001cb9b  mov     rax, cs:__security_cookie
0x14001cba2  xor     rax, rsp
0x14001cba5  mov     [rbp+3E0h+var_30], rax
0x14001cbac  mov     esi, r8d
0x14001cbaf  mov     [rsp+4E0h+var_4A0], rdx
0x14001cbb4  mov     rbx, rdx
0x14001cbb7  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x14001cbbc  xor     edx, edx; Val
0x14001cbbe  mov     r8d, 250h; Size
0x14001cbc4  call    memset_0
0x14001cbc9  mov     [rsp+4E0h+var_4B0], 0
0x14001cbd1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cbd8  lea     r12, WPP_GLOBAL_Control
0x14001cbdf  lea     r13, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001cbe6  cmp     rcx, r12
0x14001cbe9  jz      short loc_14001CC08
0x14001cbeb  test    byte ptr [rcx+1Ch], 4
0x14001cbef  jz      short loc_14001CC08
0x14001cbf1  cmp     byte ptr [rcx+19h], 5
0x14001cbf5  jb      short loc_14001CC08
0x14001cbf7  mov     rcx, [rcx+10h]
0x14001cbfb  mov     edx, 1E6h
0x14001cc00  mov     r8, r13
0x14001cc03  call    WPP_SF_
0x14001cc08  mov     r9d, 1; int
0x14001cc0e  mov     dword ptr [rsp+4E0h+hMem], 0
0x14001cc16  lea     r8, [rsp+4E0h+var_4B0]; unsigned int *
0x14001cc1b  mov     ecx, 2000000h; unsigned int
0x14001cc20  lea     rdx, [rsp+4E0h+hMem]; int *
0x14001cc25  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001cc2a  test    eax, eax
0x14001cc2c  jnz     loc_14001CF37
0x14001cc32  mov     r8d, [rsp+4E0h+var_4B0]
0x14001cc37  test    r8d, 0E03FFh
0x14001cc3e  jnz     short loc_14001CC4A
0x14001cc40  mov     eax, 5
0x14001cc45  jmp     loc_14001CF37
0x14001cc4a  lea     rax, [rbp+3E0h+FileName]
0x14001cc51  xor     r9d, r9d
0x14001cc54  mov     rdx, rbx
0x14001cc57  mov     [rsp+4E0h+var_4C0], rax
0x14001cc5c  mov     ecx, esi
0x14001cc5e  call    FindArchivedMessageAfterAccessCheck
0x14001cc63  mov     ebx, eax
0x14001cc65  test    eax, eax
0x14001cc67  jz      short loc_14001CCA6
0x14001cc69  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cc70  cmp     rcx, r12
0x14001cc73  jz      loc_14001CDDD
0x14001cc79  test    byte ptr [rcx+1Ch], 4
0x14001cc7d  jz      loc_14001CDDD
0x14001cc83  cmp     byte ptr [rcx+19h], 2
0x14001cc87  jb      loc_14001CDDD
0x14001cc8d  mov     rcx, [rcx+10h]
0x14001cc91  mov     edx, 1E7h
0x14001cc96  mov     r9d, eax
0x14001cc99  mov     r8, r13
0x14001cc9c  call    WPP_SF_d
0x14001cca1  jmp     loc_14001CDDD
0x14001cca6  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x14001ccab  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x14001ccb2  call    cs:__imp_FindFirstFileW
0x14001ccb8  mov     rcx, rax; hFindFile
0x14001ccbb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001ccbf  jnz     short loc_14001CD17
0x14001ccc1  xor     edi, edi
0x14001ccc3  mov     rax, cs:WPP_GLOBAL_Control
0x14001ccca  cmp     rax, r12
0x14001cccd  jz      loc_14001CD6A
0x14001ccd3  test    byte ptr [rax+1Ch], 4
0x14001ccd7  jz      loc_14001CD6A
0x14001ccdd  cmp     byte ptr [rax+19h], 2
0x14001cce1  jb      loc_14001CD6A
0x14001cce7  call    cs:__imp_GetLastError
0x14001cced  lea     rcx, [rbp+3E0h+FileName]
0x14001ccf4  mov     edx, 1E8h
0x14001ccf9  mov     [rsp+4E0h+var_4C0], rcx
0x14001ccfe  movzx   r9d, ax
0x14001cd02  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd09  mov     r8, r13
0x14001cd0c  mov     rcx, [rcx+10h]
0x14001cd10  call    WPP_SF_hS
0x14001cd15  jmp     short loc_14001CD6A
0x14001cd17  mov     edi, [rsp+4E0h+FindFileData.nFileSizeHigh]
0x14001cd1b  mov     eax, [rsp+4E0h+FindFileData.nFileSizeLow]
0x14001cd1f  shl     rdi, 20h
0x14001cd23  or      rdi, rax
0x14001cd26  call    cs:__imp_FindClose
0x14001cd2c  test    eax, eax
0x14001cd2e  jnz     short loc_14001CD6A
0x14001cd30  mov     rax, cs:WPP_GLOBAL_Control
0x14001cd37  cmp     rax, r12
0x14001cd3a  jz      short loc_14001CD6A
0x14001cd3c  test    byte ptr [rax+1Ch], 4
0x14001cd40  jz      short loc_14001CD6A
0x14001cd42  cmp     byte ptr [rax+19h], 2
0x14001cd46  jb      short loc_14001CD6A
0x14001cd48  call    cs:__imp_GetLastError
0x14001cd4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd55  mov     edx, 1E9h
0x14001cd5a  movzx   r9d, ax
0x14001cd5e  mov     r8, r13
0x14001cd61  mov     rcx, [rcx+10h]
0x14001cd65  call    WPP_SF_h
0x14001cd6a  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x14001cd71  call    cs:__imp_DeleteFileW
0x14001cd77  test    eax, eax
0x14001cd79  jnz     short loc_14001CDF5
0x14001cd7b  call    cs:__imp_GetLastError
0x14001cd81  mov     ebx, eax
0x14001cd83  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cd8a  cmp     rcx, r12
0x14001cd8d  jz      short loc_14001CDBB
0x14001cd8f  test    byte ptr [rcx+1Ch], 4
0x14001cd93  jz      short loc_14001CDBB
0x14001cd95  cmp     byte ptr [rcx+19h], 2
0x14001cd99  jb      short loc_14001CDBB
0x14001cd9b  mov     rcx, [rcx+10h]
0x14001cd9f  lea     rax, [rbp+3E0h+FileName]
0x14001cda6  mov     edx, 1EAh
0x14001cdab  mov     [rsp+4E0h+var_4C0], rax
0x14001cdb0  mov     r9d, ebx
0x14001cdb3  mov     r8, r13
0x14001cdb6  call    WPP_SF_DS
0x14001cdbb  cmp     ebx, 5
0x14001cdbe  jz      short loc_14001CDD8
0x14001cdc0  mov     edx, 20h ; ' '
0x14001cdc5  cmp     ebx, edx
0x14001cdc7  jz      short loc_14001CDD8
0x14001cdc9  cmp     ebx, 2
0x14001cdcc  jnz     short loc_14001CDDD
0x14001cdce  mov     ebx, 1B61h
0x14001cdd3  jmp     loc_14001CF35
0x14001cdd8  mov     ebx, 1B60h
0x14001cddd  cmp     ebx, 8
0x14001cde0  jz      short loc_14001CDEB
0x14001cde2  cmp     ebx, 0Eh
0x14001cde5  jnz     loc_14001CF35
0x14001cdeb  mov     ebx, 1B59h
0x14001cdf0  jmp     loc_14001CF35
0x14001cdf5  mov     edx, 5Ch ; '\'; Ch
0x14001cdfa  mov     [rsp+4E0h+hMem], 0
0x14001ce03  lea     rcx, [rbp+3E0h+FileName]; Str
0x14001ce0a  call    cs:__imp_wcsrchr
0x14001ce10  test    rax, rax
0x14001ce13  lea     rdx, [rax+2]
0x14001ce17  cmovz   rdx, rax; unsigned __int16 *
0x14001ce1b  test    rdx, rdx
0x14001ce1e  jz      loc_14001CECE
0x14001ce24  lea     r9, [rsp+4E0h+hMem]; void **
0x14001ce29  lea     r8, [rsp+4E0h+var_4A0]; unsigned __int64 *
0x14001ce2e  call    ?ExtractComponentsFromArchiveFileName@CFaxArchiving@@QEAAKPEBGPEA_KPEAPEAX@Z; CFaxArchiving::ExtractComponentsFromArchiveFileName(ushort const *,unsigned __int64 *,void * *)
0x14001ce33  test    eax, eax
0x14001ce35  jnz     short loc_14001CE98
0x14001ce37  mov     rcx, [rsp+4E0h+var_4A0]
0x14001ce3c  lea     edx, [rax+20h]
0x14001ce3f  lea     eax, [rdx+20h]
0x14001ce42  test    esi, esi
0x14001ce44  mov     rsi, [rsp+4E0h+hMem]
0x14001ce49  lea     r8d, [rax-3Fh]
0x14001ce4d  cmovnz  edx, eax
0x14001ce50  mov     r9, rsi
0x14001ce53  call    ?CreateArchiveEvent@@YAK_KW4FAX_ENUM_EVENT_TYPE@@W4FAX_ENUM_JOB_EVENT_TYPE@@PEAX@Z; CreateArchiveEvent(unsigned __int64,FAX_ENUM_EVENT_TYPE,FAX_ENUM_JOB_EVENT_TYPE,void *)
0x14001ce58  test    eax, eax
0x14001ce5a  jz      short loc_14001CE88
0x14001ce5c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce63  cmp     rcx, r12
0x14001ce66  jz      short loc_14001CE88
0x14001ce68  test    byte ptr [rcx+1Ch], 4
0x14001ce6c  jz      short loc_14001CE88
0x14001ce6e  cmp     byte ptr [rcx+19h], 2
0x14001ce72  jb      short loc_14001CE88
0x14001ce74  mov     rcx, [rcx+10h]
0x14001ce78  mov     edx, 1EBh
0x14001ce7d  mov     r9d, eax
0x14001ce80  mov     r8, r13
0x14001ce83  call    WPP_SF_d
0x14001ce88  test    rsi, rsi
0x14001ce8b  jz      short loc_14001CEFE
0x14001ce8d  mov     rcx, rsi; hMem
0x14001ce90  call    cs:__imp_LocalFree
0x14001ce96  jmp     short loc_14001CEFE
0x14001ce98  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce9f  cmp     rcx, r12
0x14001cea2  jz      short loc_14001CEFE
0x14001cea4  test    byte ptr [rcx+1Ch], 4
0x14001cea8  jz      short loc_14001CEFE
0x14001ceaa  cmp     byte ptr [rcx+19h], 2
0x14001ceae  jb      short loc_14001CEFE
0x14001ceb0  mov     rcx, [rcx+10h]
0x14001ceb4  lea     r9, [rbp+3E0h+FileName]
0x14001cebb  mov     edx, 1ECh
0x14001cec0  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x14001cec4  mov     r8, r13
0x14001cec7  call    WPP_SF_Sd
0x14001cecc  jmp     short loc_14001CEFE
0x14001cece  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ced5  cmp     rcx, r12
0x14001ced8  jz      short loc_14001CEFE
0x14001ceda  test    byte ptr [rcx+1Ch], 4
0x14001cede  jz      short loc_14001CEFE
0x14001cee0  cmp     byte ptr [rcx+19h], 2
0x14001cee4  jb      short loc_14001CEFE
0x14001cee6  mov     rcx, [rcx+10h]
0x14001ceea  lea     r9, [rbp+3E0h+FileName]
0x14001cef1  mov     edx, 1EDh
0x14001cef6  mov     r8, r13
0x14001cef9  call    WPP_SF_S
0x14001cefe  test    rdi, rdi
0x14001cf01  jz      short loc_14001CF35
0x14001cf03  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001cf0a  call    cs:__imp_EnterCriticalSection
0x14001cf10  mov     rdx, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14001cf17  mov     rax, [rdx+38h]
0x14001cf1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001cf1f  jz      short loc_14001CF28
0x14001cf21  sub     rax, rdi
0x14001cf24  mov     [rdx+38h], rax
0x14001cf28  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x14001cf2f  call    cs:__imp_LeaveCriticalSection
0x14001cf35  mov     eax, ebx
0x14001cf37  mov     rcx, [rbp+3E0h+var_30]
0x14001cf3e  xor     rcx, rsp; StackCookie
0x14001cf41  call    __security_check_cookie
0x14001cf46  mov     rbx, [rsp+4E0h+arg_0]
0x14001cf4e  add     rsp, 4C0h
0x14001cf55  pop     r13
0x14001cf57  pop     r12
0x14001cf59  pop     rdi
0x14001cf5a  pop     rsi
0x14001cf5b  pop     rbp
0x14001cf5c  retn
```
