# NgscbGetOSVolume

- ea: `0x180044054`
- end: `0x18004413b`
- name: `NgscbGetOSVolume`
- size: `231`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x1800430a8`
- `0x180067cc0`
- `0x180067f60`
- `0x180068d50`
- `0x180074be0`
- `0x180079124`
- `0x1800841e8`
- `0x1800a0988`
- `0x1800ad9fc`
- `0x1800ed8d4`
- `0x1800f2b50`

## callees

- `0x180044054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004411e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004411e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800440fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800440fb`

## pseudocode

```c
__int64 __fastcall NgscbGetOSVolume(_WORD *a1)
{
  const unsigned __int16 *v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r11
  __int64 v5; // rax
  _WORD *v6; // r9
  __int64 v7; // r10
  _WORD *v8; // rcx
  unsigned int v9; // edx
  UINT v11; // ebx
  WCHAR *v12; // rdi
  UINT SystemWindowsDirectoryW; // eax
  signed int LastError; // eax

  v1 = L"\\\\.\\";
  v2 = 260;
  v3 = 0;
  v5 = 2147483646;
  v6 = a1;
  do
  {
    if ( !v5 )
      break;
    if ( !*v1 )
      break;
    *v6++ = *v1++;
    --v5;
    ++v3;
    --v2;
  }
  while ( v2 );
  v7 = v3 - 1;
  v8 = v6 - 1;
  if ( v2 )
    v7 = v3;
  v9 = v2 == 0 ? 0x8007007A : 0;
  if ( v2 )
    v8 = v6;
  *v8 = 0;
  if ( v2 )
  {
    v11 = 260 - v7;
    if ( (unsigned __int64)(260 - v7) > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v12 = &a1[v7];
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v12, v11);
      if ( SystemWindowsDirectoryW )
      {
        v9 = 0;
        if ( SystemWindowsDirectoryW <= v11 )
          v12[2] = 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          return (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180044054  mov     [rsp+arg_0], rbx
0x180044059  mov     [rsp+arg_8], rsi
0x18004405e  push    rdi
0x18004405f  sub     rsp, 20h
0x180044063  mov     ebx, 104h
0x180044068  lea     rdx, asc_180136908; "\\\\.\\"
0x18004406f  xor     esi, esi
0x180044071  mov     r8d, ebx
0x180044074  mov     r11d, esi
0x180044077  mov     rdi, rcx
0x18004407a  mov     eax, 7FFFFFFEh
0x18004407f  mov     r9, rcx
0x180044082  test    rax, rax
0x180044085  jz      short loc_1800440A7
0x180044087  movzx   ecx, word ptr [rdx]
0x18004408a  test    cx, cx
0x18004408d  jz      short loc_1800440A7
0x18004408f  mov     [r9], cx
0x180044093  add     rdx, 2
0x180044097  add     r9, 2
0x18004409b  dec     rax
0x18004409e  inc     r11
0x1800440a1  sub     r8, 1
0x1800440a5  jnz     short loc_180044082
0x1800440a7  test    r8, r8
0x1800440aa  lea     r10, [r11-1]
0x1800440ae  mov     rax, r8
0x1800440b1  lea     rcx, [r9-2]
0x1800440b5  cmovnz  r10, r11
0x1800440b9  neg     rax
0x1800440bc  sbb     edx, edx
0x1800440be  not     edx
0x1800440c0  and     edx, 8007007Ah
0x1800440c6  test    r8, r8
0x1800440c9  cmovnz  rcx, r9
0x1800440cd  mov     [rcx], si
0x1800440d0  jnz     short loc_1800440E5
0x1800440d2  mov     rbx, [rsp+28h+arg_0]
0x1800440d7  mov     eax, edx
0x1800440d9  mov     rsi, [rsp+28h+arg_8]
0x1800440de  add     rsp, 20h
0x1800440e2  pop     rdi
0x1800440e3  retn
0x1800440e5  sub     rbx, r10
0x1800440e8  mov     eax, 0FFFFFFFFh
0x1800440ed  cmp     rbx, rax
0x1800440f0  ja      short loc_180044117
0x1800440f2  lea     rdi, [rdi+r10*2]
0x1800440f6  mov     edx, ebx; uSize
0x1800440f8  mov     rcx, rdi; lpBuffer
0x1800440fb  call    cs:__imp_GetSystemWindowsDirectoryW
0x180044102  nop     dword ptr [rax+rax+00h]
0x180044107  test    eax, eax
0x180044109  jz      short loc_18004411E
0x18004410b  mov     edx, esi
0x18004410d  cmp     eax, ebx
0x18004410f  ja      short loc_1800440D2
0x180044111  mov     [rdi+4], si
0x180044115  jmp     short loc_1800440D2
0x180044117  mov     edx, 80070216h
0x18004411c  jmp     short loc_1800440D2
0x18004411e  call    cs:__imp_GetLastError
0x180044125  nop     dword ptr [rax+rax+00h]
0x18004412a  mov     edx, eax
0x18004412c  test    eax, eax
0x18004412e  jle     short loc_1800440D2
0x180044130  movzx   edx, ax
0x180044133  or      edx, 80070000h
0x180044139  jmp     short loc_1800440D2
```
