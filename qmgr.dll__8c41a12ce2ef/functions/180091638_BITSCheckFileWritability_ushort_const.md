# BITSCheckFileWritability(ushort const *)

- ea: `0x180091638`
- end: `0x180091816`
- name: `?BITSCheckFileWritability@@YAJPEBG@Z`
- size: `478`
- prototype: `signed int __fastcall(const unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028d60`
- `0x18008b6b0`
- `0x180096bc4`
- `0x1800ca9b8`

## callees

- `0x180091638`
- `0x18009e9c8`
- `0x1800ab738`
- `0x1800f5574`
- `0x1800f5798`
- `0x1800f5d60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800916de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800916de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091799`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800917cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800917f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800917fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800917f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800917fd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800916ba`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800916ba`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800917e2`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x1800917e2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180091778`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180091778`

## string_xrefs

- `0x18009176e`: `CreateFile2`
- `0x180091746`: `BITSCreateFile2AsApp`

## pseudocode

```c
signed int __fastcall BITSCheckFileWritability(const unsigned __int16 *a1, int a2, int a3)
{
  DWORD v4; // eax
  const wchar_t *v5; // rdi
  void *File2; // rax
  void *v7; // rbx
  char LastError; // al
  signed int result; // eax
  _QWORD v10[2]; // [rsp+40h] [rbp-20h] BYREF
  __int128 v11; // [rsp+50h] [rbp-10h]
  int TokenInformation; // [rsp+88h] [rbp+28h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp+30h] BYREF

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_SDDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, (_DWORD)a1, 0, 0, 3, 0);
  ReturnLength = 0;
  TokenInformation = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    v11 = 0;
    v10[1] = 0;
    v10[0] = 32;
    if ( TokenInformation && IsAppContainerFileFunctionalitySupported() )
    {
      v5 = L"BITSCreateFile2AsApp";
      File2 = (void *)BITSCreateFile2AsApp(a1, 0x40000000, 0, 3, (struct _CREATEFILE2_EXTENDED_PARAMETERS *)v10);
    }
    else
    {
      v5 = L"CreateFile2";
      File2 = (void *)CreateFile2(a1, 0x40000000, 0, 3, v10);
    }
    v7 = File2;
    if ( File2 != (void *)-1LL )
    {
      if ( GetFileType(File2) != 1 )
      {
        CloseHandle(v7);
        return -2147024809;
      }
      CloseHandle(v7);
      return 0;
    }
    if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)&WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids,
        (_DWORD)v5,
        LastError);
    }
  }
  else if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids, v4);
  }
  if ( GetLastError() == 2 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180091638  mov     rax, rsp
0x18009163b  mov     [rax+8], rbx
0x18009163f  push    rbp
0x180091640  push    rdi
0x180091641  push    r14
0x180091643  mov     rbp, rsp
0x180091646  sub     rsp, 60h
0x18009164a  mov     rbx, rcx
0x18009164d  mov     rcx, cs:WPP_GLOBAL_Control
0x180091654  lea     r14, WPP_GLOBAL_Control
0x18009165b  cmp     rcx, r14
0x18009165e  jz      short loc_18009168E
0x180091660  test    byte ptr [rcx+1Ch], 1
0x180091664  jz      short loc_18009168E
0x180091666  mov     rcx, [rcx+10h]
0x18009166a  mov     r9, rbx
0x18009166d  mov     dword ptr [rax-40h], 0
0x180091674  mov     dword ptr [rax-48h], 3
0x18009167b  mov     dword ptr [rax-50h], 0
0x180091682  mov     dword ptr [rax-58h], 40000000h
0x180091689  call    WPP_SF_SDDDD
0x18009168e  mov     r9d, 4; TokenInformationLength
0x180091694  mov     [rbp+arg_10], 0
0x18009169b  lea     rax, [rbp+arg_10]
0x18009169f  mov     [rbp+TokenInformation], 0
0x1800916a6  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800916aa  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x1800916af  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800916b6  lea     edx, [r9+19h]; TokenInformationClass
0x1800916ba  call    cs:__imp_GetTokenInformation
0x1800916c0  test    eax, eax
0x1800916c2  jnz     short loc_180091708
0x1800916c4  mov     rax, cs:WPP_GLOBAL_Control
0x1800916cb  cmp     rax, r14
0x1800916ce  jz      loc_1800917C0
0x1800916d4  test    byte ptr [rax+1Ch], 4
0x1800916d8  jz      loc_1800917C0
0x1800916de  call    cs:__imp_GetLastError
0x1800916e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800916eb  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x1800916f2  mov     edx, 28h ; '('
0x1800916f7  mov     r9d, eax
0x1800916fa  mov     rcx, [rcx+10h]
0x1800916fe  call    WPP_SF_d
0x180091703  jmp     loc_1800917C0
0x180091708  cmp     [rbp+TokenInformation], 0
0x18009170c  xorps   xmm0, xmm0
0x18009170f  movdqu  [rbp+var_10], xmm0
0x180091714  mov     [rbp+var_18], 0
0x18009171c  mov     [rbp+var_20], 20h ; ' '
0x180091724  jz      short loc_180091757
0x180091726  call    ?IsAppContainerFileFunctionalitySupported@@YA_NXZ; IsAppContainerFileFunctionalitySupported(void)
0x18009172b  test    al, al
0x18009172d  jz      short loc_180091757
0x18009172f  lea     rax, [rbp+var_20]
0x180091733  mov     r9d, 3; unsigned int
0x180091739  xor     r8d, r8d; unsigned int
0x18009173c  mov     [rsp+60h+ReturnLength], rax; struct _CREATEFILE2_EXTENDED_PARAMETERS *
0x180091741  mov     edx, 40000000h; unsigned int
0x180091746  lea     rdi, aBitscreatefile; "BITSCreateFile2AsApp"
0x18009174d  mov     rcx, rbx; unsigned __int16 *
0x180091750  call    ?BITSCreateFile2AsApp@@YAPEAXPEBGKKKPEAU_CREATEFILE2_EXTENDED_PARAMETERS@@@Z; BITSCreateFile2AsApp(ushort const *,ulong,ulong,ulong,_CREATEFILE2_EXTENDED_PARAMETERS *)
0x180091755  jmp     short loc_18009177E
0x180091757  lea     rax, [rbp+var_20]
0x18009175b  mov     r9d, 3
0x180091761  xor     r8d, r8d
0x180091764  mov     [rsp+60h+ReturnLength], rax
0x180091769  mov     edx, 40000000h
0x18009176e  lea     rdi, aCreatefile2; "CreateFile2"
0x180091775  mov     rcx, rbx
0x180091778  call    cs:__imp_CreateFile2
0x18009177e  mov     rbx, rax
0x180091781  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180091785  jnz     short loc_1800917DF
0x180091787  mov     rax, cs:WPP_GLOBAL_Control
0x18009178e  cmp     rax, r14
0x180091791  jz      short loc_1800917C0
0x180091793  test    byte ptr [rax+1Ch], 2
0x180091797  jz      short loc_1800917C0
0x180091799  call    cs:__imp_GetLastError
0x18009179f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800917a6  lea     edx, [rbx+2Ah]
0x1800917a9  mov     r9, rdi
0x1800917ac  mov     dword ptr [rsp+60h+ReturnLength], eax
0x1800917b0  lea     r8, WPP_7b4a73baf3a33c57420c316f1a1c0ce8_Traceguids
0x1800917b7  mov     rcx, [rcx+10h]
0x1800917bb  call    WPP_SF_Sd
0x1800917c0  call    cs:__imp_GetLastError
0x1800917c6  cmp     eax, 2
0x1800917c9  jz      short loc_180091803
0x1800917cb  call    cs:__imp_GetLastError
0x1800917d1  test    eax, eax
0x1800917d3  jle     short loc_180091805
0x1800917d5  movzx   eax, ax
0x1800917d8  or      eax, 80070000h
0x1800917dd  jmp     short loc_180091805
0x1800917df  mov     rcx, rbx; hFile
0x1800917e2  call    cs:__imp_GetFileType
0x1800917e8  mov     rcx, rbx; hObject
0x1800917eb  cmp     eax, 1
0x1800917ee  jz      short loc_1800917FD
0x1800917f0  call    cs:__imp_CloseHandle
0x1800917f6  mov     eax, 80070057h
0x1800917fb  jmp     short loc_180091805
0x1800917fd  call    cs:__imp_CloseHandle
0x180091803  xor     eax, eax
0x180091805  mov     rbx, [rsp+60h+arg_0]
0x18009180d  add     rsp, 60h
0x180091811  pop     r14
0x180091813  pop     rdi
0x180091814  pop     rbp
0x180091815  retn
```
