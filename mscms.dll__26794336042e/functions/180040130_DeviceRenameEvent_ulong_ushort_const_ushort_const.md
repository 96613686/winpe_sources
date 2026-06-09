# DeviceRenameEvent(ulong,ushort const *,ushort const *)

- ea: `0x180040130`
- end: `0x180040321`
- name: `?DeviceRenameEvent@@YAHKPEBG0@Z`
- size: `497`
- prototype: `int(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x1800089d8`
- `0x18002e5f0`
- `0x18002f2d0`
- `0x180040130`
- `0x180043c10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800402b9`
- `ntdll!RtlNtStatusToDosError` at `0x1800402b9`
- `ntdll!NtRenameKey` at `0x1800402ab`
- `ntdll!NtRenameKey` at `0x1800402ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040259`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040259`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800402ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800402ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800402db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800402db`

## pseudocode

```c
__int64 __fastcall DeviceRenameEvent(int a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v5; // rdi
  __int64 v6; // r8
  __int64 v7; // rax
  wchar_t *v8; // rsi
  unsigned int v9; // ebx
  int v10; // eax
  DWORD v11; // ecx
  ULONG v12; // eax
  int v13; // eax
  ULONG v14; // edi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _UNICODE_STRING NewName; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  if ( !a2 )
    goto LABEL_30;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( !v6 )
    goto LABEL_30;
  if ( !a3 )
    goto LABEL_30;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( !v7 )
    goto LABEL_30;
  if ( a1 == 1835955314 )
  {
    v8 = gszDisplayProfileAssociations;
    goto LABEL_15;
  }
  if ( a1 == 1886549106 )
  {
    v8 = gszPrintProfileAssociations;
    goto LABEL_15;
  }
  if ( a1 != 1935896178 )
  {
LABEL_30:
    v11 = 87;
    goto LABEL_31;
  }
  v8 = gszCaptureProfileAssociations;
LABEL_15:
  v9 = 1;
  if ( v6 == v7 && !memcmp_0(a2, a3, 2 * v6) )
    return v9;
  v10 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s", gszICMRegPath, v8, a2);
  if ( v10 >= 0 )
  {
    v12 = RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0x20006u, &hKey);
    if ( v12 )
    {
      if ( v12 == 2 )
        goto LABEL_32;
    }
    else
    {
      NewName = 0;
      do
        ++v5;
      while ( a3[v5] );
      if ( (int)ULongLongToUShort(2 * v5, &NewName.Length) < 0 )
      {
        v11 = 534;
        goto LABEL_31;
      }
      NewName.MaximumLength = NewName.Length + 2;
      NewName.Buffer = a3;
      v13 = NtRenameKey(hKey, &NewName);
      v14 = v13;
      if ( v13 >= 0 )
        goto LABEL_32;
      v12 = RtlNtStatusToDosError(v13);
      if ( v12 == 317 )
        v12 = v14;
    }
    v11 = v12;
    goto LABEL_31;
  }
  v11 = (unsigned __int16)v10;
LABEL_31:
  SetLastError(v11);
  v9 = 0;
LABEL_32:
  if ( hKey )
    RegCloseKey(hKey);
  return v9;
}

```

## disassembly

```asm
0x180040130  mov     [rsp-8+arg_0], rbx
0x180040135  mov     [rsp-8+arg_18], rsi
0x18004013a  push    rbp
0x18004013b  push    rdi
0x18004013c  push    r12
0x18004013e  push    r14
0x180040140  push    r15
0x180040142  lea     rbp, [rsp-170h]
0x18004014a  sub     rsp, 270h
0x180040151  mov     rax, cs:__security_cookie
0x180040158  xor     rax, rsp
0x18004015b  mov     [rbp+190h+var_30], rax
0x180040162  xor     r12d, r12d
0x180040165  mov     r14, r8
0x180040168  mov     [rsp+290h+hKey], r12
0x18004016d  mov     r15, rdx
0x180040170  test    rdx, rdx
0x180040173  jz      loc_1800402D6
0x180040179  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004017d  mov     r8, rdi
0x180040180  inc     r8
0x180040183  cmp     [rdx+r8*2], r12w
0x180040188  jnz     short loc_180040180
0x18004018a  test    r8, r8
0x18004018d  jz      loc_1800402D6
0x180040193  test    r14, r14
0x180040196  jz      loc_1800402D6
0x18004019c  mov     rax, rdi
0x18004019f  inc     rax
0x1800401a2  cmp     [r14+rax*2], r12w
0x1800401a7  jnz     short loc_18004019F
0x1800401a9  test    rax, rax
0x1800401ac  jz      loc_1800402D6
0x1800401b2  cmp     ecx, 6D6E7472h
0x1800401b8  jz      short loc_1800401E0
0x1800401ba  cmp     ecx, 70727472h
0x1800401c0  jz      short loc_1800401D7
0x1800401c2  cmp     ecx, 73636E72h
0x1800401c8  jnz     loc_1800402D6
0x1800401ce  lea     rsi, gszCaptureProfileAssociations; "ProfileAssociations\\Capture"
0x1800401d5  jmp     short loc_1800401E7
0x1800401d7  lea     rsi, gszPrintProfileAssociations; "ProfileAssociations\\Print"
0x1800401de  jmp     short loc_1800401E7
0x1800401e0  lea     rsi, gszDisplayProfileAssociations; "ProfileAssociations\\Display"
0x1800401e7  mov     ebx, 1
0x1800401ec  cmp     r8, rax
0x1800401ef  jnz     short loc_180040207
0x1800401f1  add     r8, r8; Size
0x1800401f4  mov     rdx, r14; Buf2
0x1800401f7  mov     rcx, r15; Buf1
0x1800401fa  call    memcmp_0
0x1800401ff  test    eax, eax
0x180040201  jz      loc_1800402F4
0x180040207  mov     [rsp+290h+var_268], r15
0x18004020c  lea     r9, gszICMRegPath; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180040213  lea     r8, aSSS; "%s\\%s\\%s"
0x18004021a  mov     [rsp+290h+phkResult], rsi
0x18004021f  mov     edx, 104h; unsigned __int64
0x180040224  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x180040229  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004022e  test    eax, eax
0x180040230  jns     short loc_18004023A
0x180040232  movzx   ecx, ax
0x180040235  jmp     loc_1800402DB
0x18004023a  lea     rax, [rsp+290h+hKey]
0x18004023f  mov     r9d, 20006h; samDesired
0x180040245  xor     r8d, r8d; ulOptions
0x180040248  mov     [rsp+290h+phkResult], rax; phkResult
0x18004024d  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x180040252  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180040259  call    cs:__imp_RegOpenKeyExW
0x18004025f  test    eax, eax
0x180040261  jnz     short loc_1800402CB
0x180040263  xorps   xmm0, xmm0
0x180040266  movups  xmmword ptr [rsp+290h+NewName.Length], xmm0
0x18004026b  inc     rdi
0x18004026e  cmp     [r14+rdi*2], r12w
0x180040273  jnz     short loc_18004026B
0x180040275  lea     rcx, [rdi+rdi]; unsigned __int64
0x180040279  lea     rdx, [rsp+290h+NewName]; unsigned __int16 *
0x18004027e  call    ?ULongLongToUShort@@YAJ_KPEAG@Z; ULongLongToUShort(unsigned __int64,ushort *)
0x180040283  test    eax, eax
0x180040285  jns     short loc_18004028E
0x180040287  mov     ecx, 216h
0x18004028c  jmp     short loc_1800402DB
0x18004028e  movzx   eax, [rsp+290h+NewName.Length]
0x180040293  lea     rdx, [rsp+290h+NewName]; NewName
0x180040298  mov     rcx, [rsp+290h+hKey]; KeyHandle
0x18004029d  add     ax, 2
0x1800402a1  mov     [rsp+290h+NewName.MaximumLength], ax
0x1800402a6  mov     [rsp+290h+NewName.Buffer], r14
0x1800402ab  call    cs:__imp_NtRenameKey
0x1800402b1  mov     edi, eax
0x1800402b3  test    eax, eax
0x1800402b5  jns     short loc_1800402E4
0x1800402b7  mov     ecx, eax; Status
0x1800402b9  call    cs:__imp_RtlNtStatusToDosError
0x1800402bf  cmp     eax, 13Dh
0x1800402c4  cmovz   eax, edi
0x1800402c7  mov     ecx, eax
0x1800402c9  jmp     short loc_1800402DB
0x1800402cb  mov     ecx, 2
0x1800402d0  cmp     eax, ecx
0x1800402d2  jz      short loc_1800402E4
0x1800402d4  jmp     short loc_1800402C7
0x1800402d6  mov     ecx, 57h ; 'W'; dwErrCode
0x1800402db  call    cs:__imp_SetLastError
0x1800402e1  mov     ebx, r12d
0x1800402e4  mov     rcx, [rsp+290h+hKey]; hKey
0x1800402e9  test    rcx, rcx
0x1800402ec  jz      short loc_1800402F4
0x1800402ee  call    cs:__imp_RegCloseKey
0x1800402f4  mov     eax, ebx
0x1800402f6  mov     rcx, [rbp+190h+var_30]
0x1800402fd  xor     rcx, rsp; StackCookie
0x180040300  call    __security_check_cookie
0x180040305  lea     r11, [rsp+290h+var_20]
0x18004030d  mov     rbx, [r11+30h]
0x180040311  mov     rsi, [r11+48h]
0x180040315  mov     rsp, r11
0x180040318  pop     r15
0x18004031a  pop     r14
0x18004031c  pop     r12
0x18004031e  pop     rdi
0x18004031f  pop     rbp
0x180040320  retn
```
