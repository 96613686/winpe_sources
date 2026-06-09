# OpenSyncHistoryFile(void *,ulong)

- ea: `0x18000dd40`
- end: `0x18000df72`
- name: `?OpenSyncHistoryFile@@YAPEAXPEAXK@Z`
- size: `562`
- prototype: `__int64 __fastcall(_QWORD *, DWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c3c`
- `0x180039d90`

## callees

- `0x1800060e0`
- `0x180007f10`
- `0x18000dd40`
- `0x18000df80`
- `0x180013bec`
- `0x18001d810`
- `0x18001eb8c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df22`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df22`

## string_xrefs

- `0x18000dda2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x18000dee7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall OpenSyncHistoryFile(_QWORD *a1, DWORD a2)
{
  unsigned int v4; // eax
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v8; // rax
  __int64 v9; // r8
  unsigned __int16 *v10; // rax
  unsigned int v11; // r10d
  __int64 v12; // r9
  __int64 v13; // rcx
  const wchar_t *v14; // r8
  __int64 v15; // rdx
  unsigned __int16 *v16; // rax
  wchar_t v17; // r9
  unsigned __int16 *v18; // rcx
  int v19; // eax
  HANDLE v20; // rbx
  HANDLE hObject; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE *p_hObject; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v23[264]; // [rsp+50h] [rbp-B0h] BYREF

  hObject = (HANDLE)-1LL;
  p_hObject = &hObject;
  v4 = PRGetProfilePath(a1[3], v23);
  if ( v4 )
  {
    v5 = 233;
    v6 = v4;
LABEL_3:
    DebugTraceError(v6, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", v5);
    ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_hObject);
    return -1;
  }
  v8 = -1;
  do
    ++v8;
  while ( v23[v8] );
  if ( (int)v8 + 19 > 260 )
  {
    v5 = 239;
    v6 = 0;
    goto LABEL_3;
  }
  v9 = 261;
  v10 = v23;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = v9 == 0 ? 0x80070057 : 0;
  v12 = (261 - v9) & -(__int64)(v9 != 0);
  if ( v9 )
  {
    v13 = 2147483646;
    v14 = L"\\Microsoft\\Protect\\";
    v15 = 261 - v12;
    v16 = &v23[v12];
    if ( 261 != v12 )
    {
      do
      {
        if ( !v13 )
          break;
        v17 = *v14;
        if ( !*v14 )
          break;
        ++v14;
        *v16++ = v17;
        --v13;
        --v15;
      }
      while ( v15 );
    }
    v18 = v16 - 1;
    if ( v15 )
      v18 = v16;
    *v18 = 0;
    v11 = v15 == 0 ? 0x8007007A : 0;
  }
  if ( v11 )
  {
    v5 = 249;
    v6 = v11;
    goto LABEL_3;
  }
  v19 = OpenFileInStorageArea(a1, a2, v23, L"SYNCHIST", &hObject);
  if ( v19 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        WPP_GLOBAL_Control,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"dwLastError",
        v19,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp",
        6);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return -1;
  }
  v20 = hObject;
  hObject = (HANDLE)-1LL;
  ScopedCloseHandle::~ScopedCloseHandle((ScopedCloseHandle *)&p_hObject);
  return (__int64)v20;
}

```

## disassembly

```asm
0x18000dd40  mov     [rsp-8+arg_10], rbx
0x18000dd45  mov     [rsp-8+arg_18], rsi
0x18000dd4a  push    rbp
0x18000dd4b  push    rdi
0x18000dd4c  push    r14
0x18000dd4e  lea     rbp, [rsp-170h]
0x18000dd56  sub     rsp, 270h
0x18000dd5d  mov     rax, cs:__security_cookie
0x18000dd64  xor     rax, rsp
0x18000dd67  mov     [rbp+180h+var_20], rax
0x18000dd6e  mov     edi, edx
0x18000dd70  mov     rbx, rcx
0x18000dd73  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000dd77  mov     [rsp+280h+hObject], r14
0x18000dd7c  lea     rax, [rsp+280h+hObject]
0x18000dd81  mov     [rsp+280h+var_238], rax
0x18000dd86  lea     rdx, [rsp+280h+var_230]
0x18000dd8b  mov     rcx, [rcx+18h]
0x18000dd8f  call    PRGetProfilePath
0x18000dd94  xor     esi, esi
0x18000dd96  test    eax, eax
0x18000dd98  jz      short loc_18000DDC8
0x18000dd9a  mov     r9d, 0E9h
0x18000dda0  mov     ecx, eax
0x18000dda2  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000dda9  lea     rdx, aDwlasterror; "dwLastError"
0x18000ddb0  call    DebugTraceError
0x18000ddb5  nop
0x18000ddb6  lea     rcx, [rsp+280h+var_238]; this
0x18000ddbb  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x18000ddc0  mov     rax, r14
0x18000ddc3  jmp     loc_18000DF4A
0x18000ddc8  lea     rcx, [rsp+280h+var_230]
0x18000ddcd  mov     rax, r14
0x18000ddd0  inc     rax
0x18000ddd3  cmp     [rcx+rax*2], si
0x18000ddd7  jnz     short loc_18000DDD0
0x18000ddd9  add     eax, 13h
0x18000dddc  cmp     eax, 104h
0x18000dde1  jle     short loc_18000DDED
0x18000dde3  mov     r9d, 0EFh
0x18000dde9  xor     ecx, ecx
0x18000ddeb  jmp     short loc_18000DDA2
0x18000dded  mov     edx, 105h
0x18000ddf2  mov     r8d, edx
0x18000ddf5  lea     rax, [rsp+280h+var_230]
0x18000ddfa  cmp     [rax], si
0x18000ddfd  jz      short loc_18000DE09
0x18000ddff  add     rax, 2
0x18000de03  sub     r8, 1
0x18000de07  jnz     short loc_18000DDFA
0x18000de09  mov     rax, r8
0x18000de0c  neg     rax
0x18000de0f  sbb     r10d, r10d
0x18000de12  not     r10d
0x18000de15  and     r10d, 80070057h
0x18000de1c  mov     rax, r8
0x18000de1f  mov     rcx, rdx
0x18000de22  sub     rcx, r8
0x18000de25  neg     rax
0x18000de28  sbb     r9, r9
0x18000de2b  and     r9, rcx
0x18000de2e  test    r8, r8
0x18000de31  jz      short loc_18000DE8F
0x18000de33  mov     ecx, 7FFFFFFEh
0x18000de38  lea     r8, aMicrosoftProte; "\\Microsoft\\Protect\\"
0x18000de3f  sub     rdx, r9
0x18000de42  lea     rax, [rsp+280h+var_230]
0x18000de47  lea     rax, [rax+r9*2]
0x18000de4b  jz      short loc_18000DE71
0x18000de4d  test    rcx, rcx
0x18000de50  jz      short loc_18000DE71
0x18000de52  movzx   r9d, word ptr [r8]
0x18000de56  test    r9w, r9w
0x18000de5a  jz      short loc_18000DE71
0x18000de5c  add     r8, 2
0x18000de60  mov     [rax], r9w
0x18000de64  add     rax, 2
0x18000de68  dec     rcx
0x18000de6b  sub     rdx, 1
0x18000de6f  jnz     short loc_18000DE4D
0x18000de71  lea     rcx, [rax-2]
0x18000de75  test    rdx, rdx
0x18000de78  cmovnz  rcx, rax
0x18000de7c  mov     [rcx], si
0x18000de7f  neg     rdx
0x18000de82  sbb     r10d, r10d
0x18000de85  not     r10d
0x18000de88  and     r10d, 8007007Ah
0x18000de8f  test    r10d, r10d
0x18000de92  jz      short loc_18000DEA2
0x18000de94  mov     r9d, 0F9h
0x18000de9a  mov     ecx, r10d
0x18000de9d  jmp     loc_18000DDA2
0x18000dea2  lea     rax, [rsp+280h+hObject]
0x18000dea7  mov     [rsp+280h+var_260], rax; void **
0x18000deac  lea     r9, aSynchist; "SYNCHIST"
0x18000deb3  lea     r8, [rsp+280h+var_230]; unsigned __int16 *
0x18000deb8  mov     edx, edi; unsigned int
0x18000deba  mov     rcx, rbx; void *
0x18000debd  call    ?OpenFileInStorageArea@@YAKPEAXKPEBG1PEAPEAX@Z; OpenFileInStorageArea(void *,ulong,ushort const *,ushort const *,void * *)
0x18000dec2  test    eax, eax
0x18000dec4  jz      short loc_18000DF33
0x18000dec6  lea     rcx, WPP_GLOBAL_Control
0x18000decd  mov     rdx, cs:WPP_GLOBAL_Control
0x18000ded4  cmp     rdx, rcx
0x18000ded7  jz      short loc_18000DF0F
0x18000ded9  test    byte ptr [rdx+1Ch], 1
0x18000dedd  jz      short loc_18000DF0F
0x18000dedf  mov     [rsp+280h+var_250], 106h
0x18000dee7  lea     rcx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000deee  mov     [rsp+280h+var_258], rcx
0x18000def3  mov     dword ptr [rsp+280h+var_260], eax
0x18000def7  lea     r9, aDwlasterror; "dwLastError"
0x18000defe  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x18000df05  mov     rcx, [rdx+10h]
0x18000df09  call    WPP_SF_sDsd
0x18000df0e  nop
0x18000df0f  mov     rcx, [rsp+280h+hObject]; hObject
0x18000df14  lea     rax, [rcx-1]
0x18000df18  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000df1c  ja      loc_18000DDC0
0x18000df22  call    cs:__imp_CloseHandle
0x18000df29  nop     dword ptr [rax+rax+00h]
0x18000df2e  jmp     loc_18000DDC0
0x18000df33  mov     rbx, [rsp+280h+hObject]
0x18000df38  mov     [rsp+280h+hObject], r14
0x18000df3d  lea     rcx, [rsp+280h+var_238]; this
0x18000df42  call    ??1ScopedCloseHandle@@QEAA@XZ; ScopedCloseHandle::~ScopedCloseHandle(void)
0x18000df47  mov     rax, rbx
0x18000df4a  mov     rcx, [rbp+180h+var_20]
0x18000df51  xor     rcx, rsp; StackCookie
0x18000df54  call    __security_check_cookie
0x18000df59  lea     r11, [rsp+280h+var_10]
0x18000df61  mov     rbx, [r11+30h]
0x18000df65  mov     rsi, [r11+38h]
0x18000df69  mov     rsp, r11
0x18000df6c  pop     r14
0x18000df6e  pop     rdi
0x18000df6f  pop     rbp
0x18000df70  retn
```
