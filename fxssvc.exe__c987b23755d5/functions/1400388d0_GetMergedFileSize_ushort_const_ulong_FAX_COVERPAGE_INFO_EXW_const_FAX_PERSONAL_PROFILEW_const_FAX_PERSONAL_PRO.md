# GetMergedFileSize(ushort const *,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *)

- ea: `0x1400388d0`
- end: `0x140038ba6`
- name: `?GetMergedFileSize@@YAKPEBGKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@2@Z`
- size: `726`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, const struct _FAX_COVERPAGE_INFO_EXW *, const struct _FAX_PERSONAL_PROFILEW *, const struct _FAX_PERSONAL_PROFILEW *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14003567c`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140004df0`
- `0x14002e2dc`
- `0x140031268`
- `0x1400388d0`
- `0x1400507f4`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140038974`
- `KERNEL32!GetLastError` at `0x140038a32`
- `KERNEL32!GetLastError` at `0x140038a97`
- `KERNEL32!GetLastError` at `0x140038aeb`
- `KERNEL32!GetLastError` at `0x140038b4b`
- `KERNEL32!GetLastError` at `0x140038974`
- `KERNEL32!GetLastError` at `0x140038a32`
- `KERNEL32!GetLastError` at `0x140038a97`
- `KERNEL32!GetLastError` at `0x140038aeb`
- `KERNEL32!GetLastError` at `0x140038b4b`
- `KERNEL32!SetLastError` at `0x140038b7c`
- `KERNEL32!SetLastError` at `0x140038b7c`
- `KERNEL32!DeleteFileW` at `0x140038b29`
- `KERNEL32!DeleteFileW` at `0x140038b29`

## pseudocode

```c
__int64 __fastcall GetMergedFileSize(
        const unsigned __int16 *a1,
        unsigned int a2,
        const struct _FAX_COVERPAGE_INFO_EXW *a3,
        const struct _FAX_PERSONAL_PROFILEW *a4,
        const struct _FAX_PERSONAL_PROFILEW *a5)
{
  __int16 v8; // si
  unsigned int FileSize; // edi
  CMapDeviceId *v11; // rcx
  DWORD LastError; // ebx
  DWORD v13; // eax
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  unsigned int v16; // eax
  char v17; // al
  unsigned int v19; // [rsp+40h] [rbp-278h]
  __int16 v20[8]; // [rsp+50h] [rbp-268h] BYREF
  WCHAR FileName[264]; // [rsp+60h] [rbp-258h] BYREF

  v8 = 0;
  v20[0] = 0;
  FileSize = 0;
  memset_0(FileName, 0, 0x208u);
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    if ( !(unsigned int)GetBodyTiffResolution(a1, v20) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, LastError);
      }
LABEL_40:
      SetLastError(LastError);
      return FileSize;
    }
    v8 = v20[0];
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 4) != 0 && *((_BYTE *)v11 + 25) >= 5u )
    WPP_SF_(*((_QWORD *)v11 + 2), 33, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  if ( !(unsigned int)CreateCoverpageTiffFileEx2(v8, a2, a3, a5, a4, L"tmp", 0, FileName, v19) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        203,
        (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
        *((_QWORD *)a3 + 1),
        LastError);
    }
    goto LABEL_40;
  }
  FileSize = MyGetFileSize(FileName);
  if ( FileSize )
  {
    v16 = 0;
    if ( !a1 || (v16 = MyGetFileSize(a1)) != 0 )
    {
      LastError = 0;
      FileSize += v16;
      goto LABEL_34;
    }
    v13 = GetLastError();
    LastError = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 205;
      goto LABEL_26;
    }
  }
  else
  {
    v13 = GetLastError();
    LastError = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 204;
LABEL_26:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, &WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids, v13);
    }
  }
LABEL_34:
  if ( !DeleteFileW(FileName)
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v17 = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      206,
      (unsigned int)&WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids,
      (unsigned int)FileName,
      v17);
  }
  if ( !FileSize )
    goto LABEL_40;
  return FileSize;
}

```

## disassembly

```asm
0x1400388d0  push    rbx
0x1400388d2  push    rbp
0x1400388d3  push    rsi
0x1400388d4  push    rdi
0x1400388d5  push    r12
0x1400388d7  push    r14
0x1400388d9  push    r15
0x1400388db  sub     rsp, 280h
0x1400388e2  mov     rax, cs:__security_cookie
0x1400388e9  xor     rax, rsp
0x1400388ec  mov     [rsp+2B8h+var_48], rax
0x1400388f4  mov     r12, [rsp+2B8h+arg_20]
0x1400388fc  mov     rbp, r8
0x1400388ff  mov     r14d, edx
0x140038902  mov     rbx, rcx
0x140038905  xor     esi, esi
0x140038907  lea     rcx, [rsp+2B8h+FileName]; void *
0x14003890c  xor     edx, edx; Val
0x14003890e  mov     [rsp+2B8h+var_268], si
0x140038913  mov     r8d, 208h; Size
0x140038919  xor     edi, edi
0x14003891b  mov     r15, r9
0x14003891e  call    memset_0
0x140038923  mov     rcx, cs:WPP_GLOBAL_Control
0x14003892a  lea     rax, WPP_GLOBAL_Control
0x140038931  cmp     rcx, rax
0x140038934  jz      short loc_14003895E
0x140038936  test    byte ptr [rcx+1Ch], 4
0x14003893a  jz      short loc_14003895E
0x14003893c  cmp     byte ptr [rcx+19h], 5
0x140038940  jb      short loc_14003895E
0x140038942  mov     rcx, [rcx+10h]
0x140038946  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x14003894d  mov     edx, 0C9h
0x140038952  call    WPP_SF_
0x140038957  mov     rcx, cs:WPP_GLOBAL_Control
0x14003895e  test    rbx, rbx
0x140038961  jz      short loc_1400389D0
0x140038963  lea     rdx, [rsp+2B8h+var_268]; __int16 *
0x140038968  mov     rcx, rbx; unsigned __int16 *
0x14003896b  call    ?GetBodyTiffResolution@@YAHPEBGPEAF@Z; GetBodyTiffResolution(ushort const *,short *)
0x140038970  test    eax, eax
0x140038972  jnz     short loc_1400389C4
0x140038974  call    cs:__imp_GetLastError
0x14003897a  mov     ebx, eax
0x14003897c  mov     rcx, cs:WPP_GLOBAL_Control
0x140038983  lea     rax, WPP_GLOBAL_Control
0x14003898a  cmp     rcx, rax
0x14003898d  jz      loc_140038B7A
0x140038993  test    byte ptr [rcx+1Ch], 4
0x140038997  jz      loc_140038B7A
0x14003899d  cmp     byte ptr [rcx+19h], 2
0x1400389a1  jb      loc_140038B7A
0x1400389a7  mov     rcx, [rcx+10h]
0x1400389ab  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x1400389b2  mov     edx, 0CAh
0x1400389b7  mov     r9d, ebx
0x1400389ba  call    WPP_SF_d
0x1400389bf  jmp     loc_140038B7A
0x1400389c4  movzx   esi, [rsp+2B8h+var_268]
0x1400389c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400389d0  lea     rax, WPP_GLOBAL_Control
0x1400389d7  cmp     rcx, rax
0x1400389da  jz      short loc_1400389FD
0x1400389dc  test    byte ptr [rcx+1Ch], 4
0x1400389e0  jz      short loc_1400389FD
0x1400389e2  cmp     byte ptr [rcx+19h], 5
0x1400389e6  jb      short loc_1400389FD
0x1400389e8  mov     rcx, [rcx+10h]
0x1400389ec  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x1400389f3  mov     edx, 21h ; '!'
0x1400389f8  call    WPP_SF_
0x1400389fd  lea     rax, [rsp+2B8h+FileName]
0x140038a02  mov     r9, r12; struct _FAX_PERSONAL_PROFILEW *
0x140038a05  mov     [rsp+2B8h+var_280], rax; unsigned __int16 *
0x140038a0a  mov     r8, rbp; struct _FAX_COVERPAGE_INFO_EXW *
0x140038a0d  lea     rax, aTmp; "tmp"
0x140038a14  mov     [rsp+2B8h+var_288], rdi; unsigned __int16 *
0x140038a19  mov     [rsp+2B8h+var_290], rax; unsigned __int16 *
0x140038a1e  mov     edx, r14d; unsigned int
0x140038a21  movzx   ecx, si; __int16
0x140038a24  mov     [rsp+2B8h+var_298], r15; struct _FAX_PERSONAL_PROFILEW *
0x140038a29  call    ?CreateCoverpageTiffFileEx2@@YAHFKPEBU_FAX_COVERPAGE_INFO_EXW@@PEBU_FAX_PERSONAL_PROFILEW@@1PEBG2PEAGK@Z; CreateCoverpageTiffFileEx2(short,ulong,_FAX_COVERPAGE_INFO_EXW const *,_FAX_PERSONAL_PROFILEW const *,_FAX_PERSONAL_PROFILEW const *,ushort const *,ushort const *,ushort *,ulong)
0x140038a2e  test    eax, eax
0x140038a30  jnz     short loc_140038A87
0x140038a32  call    cs:__imp_GetLastError
0x140038a38  mov     ebx, eax
0x140038a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140038a41  lea     rax, WPP_GLOBAL_Control
0x140038a48  cmp     rcx, rax
0x140038a4b  jz      loc_140038B7A
0x140038a51  test    byte ptr [rcx+1Ch], 4
0x140038a55  jz      loc_140038B7A
0x140038a5b  cmp     byte ptr [rcx+19h], 2
0x140038a5f  jb      loc_140038B7A
0x140038a65  mov     r9, [rbp+8]
0x140038a69  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038a70  mov     rcx, [rcx+10h]
0x140038a74  mov     edx, 0CBh
0x140038a79  mov     dword ptr [rsp+2B8h+var_298], ebx
0x140038a7d  call    WPP_SF_Sd
0x140038a82  jmp     loc_140038B7A
0x140038a87  lea     rcx, [rsp+2B8h+FileName]; unsigned __int16 *
0x140038a8c  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x140038a91  mov     edi, eax
0x140038a93  test    eax, eax
0x140038a95  jnz     short loc_140038AD8
0x140038a97  call    cs:__imp_GetLastError
0x140038a9d  mov     ebx, eax
0x140038a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140038aa6  lea     rsi, WPP_GLOBAL_Control
0x140038aad  cmp     rcx, rsi
0x140038ab0  jz      short loc_140038B24
0x140038ab2  test    byte ptr [rcx+1Ch], 4
0x140038ab6  jz      short loc_140038B24
0x140038ab8  cmp     byte ptr [rcx+19h], 2
0x140038abc  jb      short loc_140038B24
0x140038abe  mov     edx, 0CCh
0x140038ac3  mov     rcx, [rcx+10h]
0x140038ac7  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038ace  mov     r9d, eax
0x140038ad1  call    WPP_SF_d
0x140038ad6  jmp     short loc_140038B24
0x140038ad8  xor     eax, eax
0x140038ada  test    rbx, rbx
0x140038add  jz      short loc_140038B19
0x140038adf  mov     rcx, rbx; unsigned __int16 *
0x140038ae2  call    ?MyGetFileSize@@YAKPEBG@Z; MyGetFileSize(ushort const *)
0x140038ae7  test    eax, eax
0x140038ae9  jnz     short loc_140038B19
0x140038aeb  call    cs:__imp_GetLastError
0x140038af1  mov     ebx, eax
0x140038af3  mov     rcx, cs:WPP_GLOBAL_Control
0x140038afa  lea     rsi, WPP_GLOBAL_Control
0x140038b01  cmp     rcx, rsi
0x140038b04  jz      short loc_140038B24
0x140038b06  test    byte ptr [rcx+1Ch], 4
0x140038b0a  jz      short loc_140038B24
0x140038b0c  cmp     byte ptr [rcx+19h], 2
0x140038b10  jb      short loc_140038B24
0x140038b12  mov     edx, 0CDh
0x140038b17  jmp     short loc_140038AC3
0x140038b19  xor     ebx, ebx
0x140038b1b  lea     rsi, WPP_GLOBAL_Control
0x140038b22  add     edi, eax
0x140038b24  lea     rcx, [rsp+2B8h+FileName]; lpFileName
0x140038b29  call    cs:__imp_DeleteFileW
0x140038b2f  test    eax, eax
0x140038b31  jnz     short loc_140038B76
0x140038b33  mov     rax, cs:WPP_GLOBAL_Control
0x140038b3a  cmp     rax, rsi
0x140038b3d  jz      short loc_140038B76
0x140038b3f  test    byte ptr [rax+1Ch], 4
0x140038b43  jz      short loc_140038B76
0x140038b45  cmp     byte ptr [rax+19h], 2
0x140038b49  jb      short loc_140038B76
0x140038b4b  call    cs:__imp_GetLastError
0x140038b51  mov     rcx, cs:WPP_GLOBAL_Control
0x140038b58  lea     r9, [rsp+2B8h+FileName]
0x140038b5d  mov     edx, 0CEh
0x140038b62  mov     dword ptr [rsp+2B8h+var_298], eax
0x140038b66  lea     r8, WPP_a943d7cf2a3c33d7029e640dc78b71f8_Traceguids
0x140038b6d  mov     rcx, [rcx+10h]
0x140038b71  call    WPP_SF_Sd
0x140038b76  test    edi, edi
0x140038b78  jnz     short loc_140038B82
0x140038b7a  mov     ecx, ebx; dwErrCode
0x140038b7c  call    cs:__imp_SetLastError
0x140038b82  mov     eax, edi
0x140038b84  mov     rcx, [rsp+2B8h+var_48]
0x140038b8c  xor     rcx, rsp; StackCookie
0x140038b8f  call    __security_check_cookie
0x140038b94  add     rsp, 280h
0x140038b9b  pop     r15
0x140038b9d  pop     r14
0x140038b9f  pop     r12
0x140038ba1  pop     rdi
0x140038ba2  pop     rsi
0x140038ba3  pop     rbp
0x140038ba4  pop     rbx
0x140038ba5  retn
```
