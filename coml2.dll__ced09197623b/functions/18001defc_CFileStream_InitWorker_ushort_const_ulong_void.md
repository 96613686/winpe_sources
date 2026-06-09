# CFileStream::InitWorker(ushort const *,ulong,void *)

- ea: `0x18001defc`
- end: `0x18001e0ef`
- name: `?InitWorker@CFileStream@@AEAAJPEBGKPEAX@Z`
- size: `499`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, const unsigned __int16 *, unsigned int, void *)`
- caller_count: `6`
- callee_count: `11`
- tags: ``

## callers

- `0x18001c2ac`
- `0x1800362a4`
- `0x1800367e8`
- `0x18003ec7c`
- `0x18004c1b0`
- `0x18005ac70`

## callees

- `0x18001defc`
- `0x18001e2f0`
- `0x18001e364`
- `0x18001e718`
- `0x180026bc4`
- `0x180034df4`
- `0x18003aa00`
- `0x18003de98`
- `0x18003f858`
- `0x180042800`
- `0x18004bc24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e0a4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001dfe0`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001dfe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e0c0`

## pseudocode

```c
__int64 __fastcall CFileStream::InitWorker(CFileStream *this, WCHAR *a2, char a3, void *a4)
{
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rcx
  WCHAR *v10; // rax
  __int64 v11; // r8
  WCHAR *v12; // rcx
  int inited; // eax
  int TempFileName; // edi
  DWORD LastError; // eax
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rax
  LPWSTR FilePart; // [rsp+20h] [rbp-468h] BYREF
  WCHAR FileName[264]; // [rsp+30h] [rbp-458h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-248h] BYREF

  if ( *((_QWORD *)this + 8) != -1 )
    return 0;
  v7 = *((_QWORD *)this + 6);
  v8 = *(_DWORD *)(v7 + 32);
  if ( *(_WORD *)(v7 + 72) )
  {
    inited = CFileStream::Init_DupFileHandle(this, (unsigned int)a2);
  }
  else
  {
    if ( a2 )
    {
      v9 = 2147483646;
      v10 = FileName;
      v11 = 261;
      do
      {
        if ( !v9 )
          break;
        if ( !*a2 )
          break;
        *v10++ = *a2++;
        --v9;
        --v11;
      }
      while ( v11 );
      v12 = v10 - 1;
      if ( v11 )
        v12 = v10;
      *v12 = 0;
      if ( !v11 )
        return (unsigned int)-2147287031;
    }
    else
    {
      TempFileName = StgpGetTempFileName(FileName, 0, 0);
      if ( TempFileName < 0 )
        return (unsigned int)TempFileName;
    }
    inited = CFileStream::Init_OpenOrCreate(this, FileName, a3, a4);
  }
  TempFileName = inited;
  if ( inited >= 0 )
  {
    if ( *(_WORD *)(*((_QWORD *)this + 6) + 72LL) )
      goto LABEL_17;
    FilePart = 0;
    if ( GetFullPathNameW(FileName, 0x104u, Buffer, &FilePart) )
    {
      StringCbCopyW((unsigned __int16 *)(*((_QWORD *)this + 6) + 72LL), 0x20Au, Buffer);
      if ( (*(_BYTE *)(*((_QWORD *)this + 6) + 36LL) & 0x40) != 0 )
        CFileStream::DupFileHandleToOthers(this);
LABEL_17:
      if ( (v8 & 2) != 0 )
      {
        if ( (v8 & 0x240) == 0x240 )
          goto LABEL_19;
      }
      else if ( (v8 & 0x40) != 0 )
      {
LABEL_19:
        CFileStream::Init_MemoryMap(this);
        return 0;
      }
      if ( (v8 & 0x280) != 0x280 && (*(_BYTE *)(*((_QWORD *)this + 6) + 36LL) & 0xC0) == 0 )
        return 0;
      goto LABEL_19;
    }
    LastError = GetLastError();
    TempFileName = Win32ErrorToScode(LastError);
    UnProtectHandle(*((HANDLE *)this + 8));
    CloseHandle(*((HANDLE *)this + 8));
    v18 = *((_QWORD *)this + 6);
    *((_QWORD *)this + 8) = -1;
    if ( (*(_BYTE *)(v18 + 36) & 4) != 0 )
      CFileStream::DeleteTheFile(this, v17);
  }
  return (unsigned int)TempFileName;
}

```

## disassembly

```asm
0x18001defc  mov     [rsp+arg_8], rbx
0x18001df01  push    rbp
0x18001df02  push    rsi
0x18001df03  push    rdi
0x18001df04  push    r14
0x18001df06  push    r15
0x18001df08  sub     rsp, 460h
0x18001df0f  mov     rax, cs:__security_cookie
0x18001df16  xor     rax, rsp
0x18001df19  mov     [rsp+488h+var_38], rax
0x18001df21  cmp     qword ptr [rcx+40h], 0FFFFFFFFFFFFFFFFh
0x18001df26  mov     r14, r9
0x18001df29  mov     ebp, r8d
0x18001df2c  mov     rbx, rcx
0x18001df2f  jnz     loc_18001E02B
0x18001df35  mov     rax, [rcx+30h]
0x18001df39  xor     r15d, r15d
0x18001df3c  mov     esi, [rax+20h]
0x18001df3f  cmp     [rax+48h], r15w
0x18001df44  jnz     loc_18001E093
0x18001df4a  test    rdx, rdx
0x18001df4d  jz      loc_18001E078
0x18001df53  mov     ecx, 7FFFFFFEh
0x18001df58  lea     rax, [rsp+488h+FileName]
0x18001df5d  mov     r8d, 105h
0x18001df63  test    rcx, rcx
0x18001df66  jz      short loc_18001DF87
0x18001df68  movzx   r9d, word ptr [rdx]
0x18001df6c  test    r9w, r9w
0x18001df70  jz      short loc_18001DF87
0x18001df72  mov     [rax], r9w
0x18001df76  add     rdx, 2
0x18001df7a  add     rax, 2
0x18001df7e  dec     rcx
0x18001df81  sub     r8, 1
0x18001df85  jnz     short loc_18001DF63
0x18001df87  test    r8, r8
0x18001df8a  lea     rcx, [rax-2]
0x18001df8e  cmovnz  rcx, rax
0x18001df92  mov     [rcx], r15w
0x18001df96  jz      loc_18001E09D
0x18001df9c  mov     r9, r14; void *
0x18001df9f  lea     rdx, [rsp+488h+FileName]; unsigned __int16 *
0x18001dfa4  mov     r8d, ebp; unsigned int
0x18001dfa7  mov     rcx, rbx; this
0x18001dfaa  call    ?Init_OpenOrCreate@CFileStream@@AEAAJPEAGKPEAX@Z; CFileStream::Init_OpenOrCreate(ushort *,ulong,void *)
0x18001dfaf  mov     edi, eax
0x18001dfb1  test    eax, eax
0x18001dfb3  js      loc_18001E08F
0x18001dfb9  mov     rax, [rbx+30h]
0x18001dfbd  cmp     [rax+48h], r15w
0x18001dfc2  jnz     short loc_18001E017
0x18001dfc4  lea     r9, [rsp+488h+FilePart]; lpFilePart
0x18001dfc9  mov     [rsp+488h+FilePart], r15
0x18001dfce  lea     r8, [rsp+488h+Buffer]; lpBuffer
0x18001dfd6  mov     edx, 104h; nBufferLength
0x18001dfdb  lea     rcx, [rsp+488h+FileName]; lpFileName
0x18001dfe0  call    cs:__imp_GetFullPathNameW
0x18001dfe6  test    eax, eax
0x18001dfe8  jz      loc_18001E0A4
0x18001dfee  mov     rcx, [rbx+30h]
0x18001dff2  lea     r8, [rsp+488h+Buffer]; unsigned __int16 *
0x18001dffa  add     rcx, 48h ; 'H'; unsigned __int16 *
0x18001dffe  mov     edx, 20Ah; unsigned __int64
0x18001e003  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e008  mov     r11, [rbx+30h]
0x18001e00c  test    byte ptr [r11+24h], 40h
0x18001e011  jnz     loc_18001E0E2
0x18001e017  test    sil, 2
0x18001e01b  jnz     short loc_18001E054
0x18001e01d  test    sil, 40h
0x18001e021  jz      short loc_18001E061
0x18001e023  mov     rcx, rbx; this
0x18001e026  call    ?Init_MemoryMap@CFileStream@@AEAAJK@Z; CFileStream::Init_MemoryMap(ulong)
0x18001e02b  xor     eax, eax
0x18001e02d  mov     rcx, [rsp+488h+var_38]
0x18001e035  xor     rcx, rsp; StackCookie
0x18001e038  call    __security_check_cookie
0x18001e03d  mov     rbx, [rsp+488h+arg_8]
0x18001e045  add     rsp, 460h
0x18001e04c  pop     r15
0x18001e04e  pop     r14
0x18001e050  pop     rdi
0x18001e051  pop     rsi
0x18001e052  pop     rbp
0x18001e053  retn
0x18001e054  mov     ecx, 240h
0x18001e059  mov     eax, esi
0x18001e05b  and     eax, ecx
0x18001e05d  cmp     eax, ecx
0x18001e05f  jz      short loc_18001E023
0x18001e061  mov     eax, 280h
0x18001e066  and     esi, eax
0x18001e068  cmp     esi, eax
0x18001e06a  jz      short loc_18001E023
0x18001e06c  mov     rax, [rbx+30h]
0x18001e070  test    byte ptr [rax+24h], 0C0h
0x18001e074  jz      short loc_18001E02B
0x18001e076  jmp     short loc_18001E023
0x18001e078  xor     r8d, r8d; int
0x18001e07b  lea     rcx, [rsp+488h+FileName]; unsigned __int16 *
0x18001e080  call    ?StgpGetTempFileName@@YAJPEAG_KH@Z; StgpGetTempFileName(ushort *,unsigned __int64,int)
0x18001e085  mov     edi, eax
0x18001e087  test    eax, eax
0x18001e089  jns     loc_18001DF9C
0x18001e08f  mov     eax, edi
0x18001e091  jmp     short loc_18001E02D
0x18001e093  call    ?Init_DupFileHandle@CFileStream@@AEAAJK@Z; CFileStream::Init_DupFileHandle(ulong)
0x18001e098  jmp     loc_18001DFAF
0x18001e09d  mov     edi, 80030009h
0x18001e0a2  jmp     short loc_18001E08F
0x18001e0a4  call    cs:__imp_GetLastError
0x18001e0aa  mov     ecx, eax; unsigned int
0x18001e0ac  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18001e0b1  mov     edi, eax
0x18001e0b3  mov     rcx, [rbx+40h]; ObjectHandle
0x18001e0b7  call    ?UnProtectHandle@@YAJPEAX@Z; UnProtectHandle(void *)
0x18001e0bc  mov     rcx, [rbx+40h]; hObject
0x18001e0c0  call    cs:__imp_CloseHandle
0x18001e0c6  mov     rax, [rbx+30h]
0x18001e0ca  mov     qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x18001e0d2  test    byte ptr [rax+24h], 4
0x18001e0d6  jz      short loc_18001E08F
0x18001e0d8  mov     rcx, rbx; this
0x18001e0db  call    ?DeleteTheFile@CFileStream@@AEAAHPEBG@Z; CFileStream::DeleteTheFile(ushort const *)
0x18001e0e0  jmp     short loc_18001E08F
0x18001e0e2  mov     rcx, rbx; this
0x18001e0e5  call    ?DupFileHandleToOthers@CFileStream@@AEAAJXZ; CFileStream::DupFileHandleToOthers(void)
0x18001e0ea  jmp     loc_18001E017
```
