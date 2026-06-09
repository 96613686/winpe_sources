# CopyRepositoryBackupFiles(ushort const *,ushort const *)

- ea: `0x180039088`
- end: `0x180039267`
- name: `?CopyRepositoryBackupFiles@@YAJPEBG0@Z`
- size: `479`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003c714`

## callees

- `0x1800012b8`
- `0x180013880`
- `0x180013f90`
- `0x180023b3c`
- `0x180039088`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800390a4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039122`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800390a4`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180039122`
- `wbemcomn!GetMemLogObject` at `0x1800390b2`
- `wbemcomn!GetMemLogObject` at `0x180039130`
- `wbemcomn!GetMemLogObject` at `0x1800390b2`
- `wbemcomn!GetMemLogObject` at `0x180039130`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800390c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039140`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800390c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180039140`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003921f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003921f`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180039211`
- `api-ms-win-core-file-l2-1-0!CopyFileExW` at `0x180039211`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CopyRepositoryBackupFiles(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rax
  unsigned __int16 *v5; // rbp
  CMemoryLog *v6; // rax
  unsigned int v7; // ebx
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  CMemoryLog *MemLogObject; // rax
  int i; // edi
  const unsigned __int16 *v12; // rbx
  signed int LastError; // eax
  _QWORD v15[2]; // [rsp+30h] [rbp-58h] BYREF
  _QWORD v16[9]; // [rsp+40h] [rbp-48h] BYREF

  v4 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
  v5 = v4;
  if ( v4 )
  {
    v16[0] = v4;
    v16[1] = 0;
    v8 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x20Au);
    v9 = v8;
    if ( v8 )
    {
      v15[0] = v8;
      v15[1] = 0;
      for ( i = 0; ; ++i )
      {
        if ( i == 5 )
        {
          CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v15);
          v7 = 0;
          goto LABEL_19;
        }
        StringCchCopyW(v5, 0x105u, a1);
        StringCchCopyW(v9, 0x105u, a2);
        v12 = off_180049FD0[i];
        StringCchCatW(v5, 0x105u, v12);
        StringCchCatW(v9, 0x105u, v12);
        if ( !CopyFileExW(v5, v9, 0, 0, 0, 0) )
          break;
      }
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v15);
    }
    else
    {
      MemLogObject = GetMemLogObject();
      v7 = -2147217402;
      CMemoryLog::Write(MemLogObject, -2147217402);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
      }
    }
LABEL_19:
    CVectorDeleteMe<unsigned short>::~CVectorDeleteMe<unsigned short>(v16);
  }
  else
  {
    v6 = GetMemLogObject();
    v7 = -2147217402;
    CMemoryLog::Write(v6, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749894LL);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180039088  push    rbx
0x18003908a  push    rbp
0x18003908b  push    rsi
0x18003908c  push    rdi
0x18003908d  push    r13
0x18003908f  push    r14
0x180039091  push    r15
0x180039093  sub     rsp, 50h
0x180039097  mov     r14, rdx
0x18003909a  mov     r15, rcx
0x18003909d  mov     ebx, 20Ah
0x1800390a2  mov     ecx, ebx
0x1800390a4  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800390aa  mov     rbp, rax
0x1800390ad  test    rax, rax
0x1800390b0  jnz     short loc_180039111
0x1800390b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800390b8  mov     ebx, 80041006h
0x1800390bd  mov     edx, ebx
0x1800390bf  mov     rcx, rax
0x1800390c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800390c8  lea     rax, WPP_GLOBAL_Control
0x1800390cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390d6  cmp     rcx, rax
0x1800390d9  jz      loc_180039256
0x1800390df  test    byte ptr [rcx+1Ch], 1
0x1800390e3  jz      loc_180039256
0x1800390e9  cmp     byte ptr [rcx+19h], 2
0x1800390ed  jb      loc_180039256
0x1800390f3  lea     edx, [rbp+23h]
0x1800390f6  mov     r9d, 80041006h
0x1800390fc  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039103  mov     rcx, [rcx+10h]
0x180039107  call    WPP_SF_d
0x18003910c  jmp     loc_180039256
0x180039111  mov     [rsp+88h+var_48], rbp
0x180039116  mov     [rsp+88h+var_40], 0
0x18003911f  mov     rcx, rbx
0x180039122  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180039128  mov     rsi, rax
0x18003912b  test    rax, rax
0x18003912e  jnz     short loc_18003918F
0x180039130  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180039136  mov     ebx, 80041006h
0x18003913b  mov     edx, ebx
0x18003913d  mov     rcx, rax
0x180039140  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180039146  lea     rax, WPP_GLOBAL_Control
0x18003914d  mov     rcx, cs:WPP_GLOBAL_Control
0x180039154  cmp     rcx, rax
0x180039157  jz      loc_18003924C
0x18003915d  test    byte ptr [rcx+1Ch], 1
0x180039161  jz      loc_18003924C
0x180039167  cmp     byte ptr [rcx+19h], 2
0x18003916b  jb      loc_18003924C
0x180039171  lea     edx, [rsi+24h]
0x180039174  mov     r9d, 80041006h
0x18003917a  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x180039181  mov     rcx, [rcx+10h]
0x180039185  call    WPP_SF_d
0x18003918a  jmp     loc_18003924C
0x18003918f  mov     [rsp+88h+var_58], rsi
0x180039194  mov     [rsp+88h+var_50], 0
0x18003919d  xor     edi, edi
0x18003919f  mov     r13d, 105h
0x1800391a5  cmp     edi, 5
0x1800391a8  jz      loc_180039240
0x1800391ae  mov     r8, r15; unsigned __int16 *
0x1800391b1  mov     rdx, r13; unsigned __int64
0x1800391b4  mov     rcx, rbp; unsigned __int16 *
0x1800391b7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800391bc  mov     r8, r14; unsigned __int16 *
0x1800391bf  mov     rdx, r13; unsigned __int64
0x1800391c2  mov     rcx, rsi; unsigned __int16 *
0x1800391c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800391ca  movsxd  r10, edi
0x1800391cd  lea     rbx, off_180049FD0; "\\index.btr"
0x1800391d4  mov     rbx, [rbx+r10*8]
0x1800391d8  mov     r8, rbx; unsigned __int16 *
0x1800391db  mov     rdx, r13; unsigned __int64
0x1800391de  mov     rcx, rbp; unsigned __int16 *
0x1800391e1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800391e6  mov     r8, rbx; unsigned __int16 *
0x1800391e9  mov     rdx, r13; unsigned __int64
0x1800391ec  mov     rcx, rsi; unsigned __int16 *
0x1800391ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800391f4  mov     [rsp+88h+dwCopyFlags], 0; dwCopyFlags
0x1800391fc  mov     [rsp+88h+pbCancel], 0; pbCancel
0x180039205  xor     r9d, r9d; lpData
0x180039208  xor     r8d, r8d; lpProgressRoutine
0x18003920b  mov     rdx, rsi; lpNewFileName
0x18003920e  mov     rcx, rbp; lpExistingFileName
0x180039211  call    cs:__imp_CopyFileExW
0x180039217  test    eax, eax
0x180039219  jz      short loc_18003921F
0x18003921b  inc     edi
0x18003921d  jmp     short loc_1800391A5
0x18003921f  call    cs:__imp_GetLastError
0x180039225  mov     ebx, eax
0x180039227  test    eax, eax
0x180039229  jle     short loc_180039234
0x18003922b  movzx   ebx, ax
0x18003922e  or      ebx, 80070000h
0x180039234  lea     rcx, [rsp+88h+var_58]
0x180039239  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003923e  jmp     short loc_18003924C
0x180039240  lea     rcx, [rsp+88h+var_58]
0x180039245  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x18003924a  xor     ebx, ebx
0x18003924c  lea     rcx, [rsp+88h+var_48]
0x180039251  call    ??1?$CVectorDeleteMe@G@@QEAA@XZ; CVectorDeleteMe<ushort>::~CVectorDeleteMe<ushort>(void)
0x180039256  mov     eax, ebx
0x180039258  add     rsp, 50h
0x18003925c  pop     r15
0x18003925e  pop     r14
0x180039260  pop     r13
0x180039262  pop     rdi
0x180039263  pop     rsi
0x180039264  pop     rbp
0x180039265  pop     rbx
0x180039266  retn
```
