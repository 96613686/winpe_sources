# NgscbGetOSVolume

- ea: `0x18001106c`
- end: `0x180011144`
- name: `NgscbGetOSVolume`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180007210`
- `0x180007360`
- `0x180017a40`

## callees

- `0x18001106c`

## import_xrefs

- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180011100`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180011100`
- `KERNEL32!GetLastError` at `0x18001110a`
- `KERNEL32!GetLastError` at `0x18001110a`

## pseudocode

```c
__int64 __fastcall NgscbGetOSVolume(_WORD *a1)
{
  const wchar_t *v1; // rdx
  __int64 v2; // r8
  __int64 v3; // r11
  __int64 v5; // rax
  _WORD *v6; // r9
  __int64 v7; // r10
  _WORD *v8; // rcx
  unsigned int v9; // edx
  UINT v10; // ebx
  WCHAR *v11; // rdi
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
    v10 = 260 - v7;
    if ( (unsigned __int64)(260 - v7) > 0xFFFFFFFF )
    {
      return (unsigned int)-2147024362;
    }
    else
    {
      v11 = &a1[v7];
      SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(v11, v10);
      if ( SystemWindowsDirectoryW )
      {
        v9 = 0;
        if ( SystemWindowsDirectoryW <= v10 )
          v11[2] = 0;
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
0x18001106c  mov     [rsp+arg_0], rbx
0x180011071  mov     [rsp+arg_8], rsi
0x180011076  push    rdi
0x180011077  sub     rsp, 20h
0x18001107b  mov     ebx, 104h
0x180011080  lea     rdx, asc_180031AC8; "\\\\.\\"
0x180011087  xor     esi, esi
0x180011089  mov     r8d, ebx
0x18001108c  mov     r11d, esi
0x18001108f  mov     rdi, rcx
0x180011092  mov     eax, 7FFFFFFEh
0x180011097  mov     r9, rcx
0x18001109a  test    rax, rax
0x18001109d  jz      short loc_1800110BF
0x18001109f  movzx   ecx, word ptr [rdx]
0x1800110a2  test    cx, cx
0x1800110a5  jz      short loc_1800110BF
0x1800110a7  mov     [r9], cx
0x1800110ab  add     rdx, 2
0x1800110af  add     r9, 2
0x1800110b3  dec     rax
0x1800110b6  inc     r11
0x1800110b9  sub     r8, 1
0x1800110bd  jnz     short loc_18001109A
0x1800110bf  test    r8, r8
0x1800110c2  lea     r10, [r11-1]
0x1800110c6  mov     rax, r8
0x1800110c9  lea     rcx, [r9-2]
0x1800110cd  cmovnz  r10, r11
0x1800110d1  neg     rax
0x1800110d4  sbb     edx, edx
0x1800110d6  not     edx
0x1800110d8  and     edx, 8007007Ah
0x1800110de  test    r8, r8
0x1800110e1  cmovnz  rcx, r9
0x1800110e5  mov     [rcx], si
0x1800110e8  jz      short loc_180011132
0x1800110ea  sub     rbx, r10
0x1800110ed  mov     eax, 0FFFFFFFFh
0x1800110f2  cmp     rbx, rax
0x1800110f5  ja      short loc_18001112D
0x1800110f7  lea     rdi, [rdi+r10*2]
0x1800110fb  mov     edx, ebx; uSize
0x1800110fd  mov     rcx, rdi; lpBuffer
0x180011100  call    cs:__imp_GetSystemWindowsDirectoryW
0x180011106  test    eax, eax
0x180011108  jnz     short loc_180011121
0x18001110a  call    cs:__imp_GetLastError
0x180011110  mov     edx, eax
0x180011112  test    eax, eax
0x180011114  jle     short loc_180011132
0x180011116  movzx   edx, ax
0x180011119  or      edx, 80070000h
0x18001111f  jmp     short loc_180011132
0x180011121  mov     edx, esi
0x180011123  cmp     eax, ebx
0x180011125  ja      short loc_180011132
0x180011127  mov     [rdi+4], si
0x18001112b  jmp     short loc_180011132
0x18001112d  mov     edx, 80070216h
0x180011132  mov     rbx, [rsp+28h+arg_0]
0x180011137  mov     eax, edx
0x180011139  mov     rsi, [rsp+28h+arg_8]
0x18001113e  add     rsp, 20h
0x180011142  pop     rdi
0x180011143  retn
```
