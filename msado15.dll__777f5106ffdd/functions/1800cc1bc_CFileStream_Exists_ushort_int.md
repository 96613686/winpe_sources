# CFileStream::Exists(ushort *,int *)

- ea: `0x1800cc1bc`
- end: `0x1800cc24d`
- name: `?Exists@CFileStream@@QEAAJPEAGPEAH@Z`
- size: `145`
- prototype: `int(CFileStream *__hidden this, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18005dc90`

## callees

- `0x18001a820`
- `0x180053d40`
- `0x180056e84`
- `0x1800cc1bc`

## import_xrefs

- `msvcrt!_waccess` at `0x1800cc1fc`
- `msvcrt!_waccess` at `0x1800cc1fc`
- `KERNEL32!GetLastError` at `0x1800cc20e`
- `KERNEL32!GetLastError` at `0x1800cc20e`

## pseudocode

```c
__int64 __fastcall CFileStream::Exists(CFileStream *this, unsigned __int16 *a2, int *a3)
{
  unsigned int v5; // ebx
  int v6; // eax
  signed int LastError; // eax
  _BYTE v9[24]; // [rsp+20h] [rbp-18h] BYREF

  CSysString::CSysString((CSysString *)v9, a2, 4u);
  if ( CSysString::GetLength((CSysString *)v9, 0) )
  {
    v5 = 0;
    v6 = _waccess(a2, 0);
    *a3 = v6;
    if ( v6 )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        else
          v5 = LastError;
      }
    }
  }
  else
  {
    v5 = -2147286781;
  }
  CSysString::~CSysString((CSysString *)v9);
  return v5;
}

```

## disassembly

```asm
0x1800cc1bc  mov     [rsp+arg_0], rbx
0x1800cc1c1  mov     [rsp+arg_8], rsi
0x1800cc1c6  push    rdi
0x1800cc1c7  sub     rsp, 30h
0x1800cc1cb  mov     rsi, r8
0x1800cc1ce  lea     rcx, [rsp+38h+var_18]; this
0x1800cc1d3  mov     r8b, 4; unsigned __int8
0x1800cc1d6  mov     rdi, rdx
0x1800cc1d9  call    ??0CSysString@@QEAA@PEAGE@Z; CSysString::CSysString(ushort *,uchar)
0x1800cc1de  xor     edx, edx; int
0x1800cc1e0  lea     rcx, [rsp+38h+var_18]; this
0x1800cc1e5  call    ?GetLength@CSysString@@QEBAKH@Z; CSysString::GetLength(int)
0x1800cc1ea  test    eax, eax
0x1800cc1ec  jnz     short loc_1800CC1F5
0x1800cc1ee  mov     ebx, 80030103h
0x1800cc1f3  jmp     short loc_1800CC230
0x1800cc1f5  xor     edx, edx; AccessMode
0x1800cc1f7  mov     rcx, rdi; FileName
0x1800cc1fa  xor     ebx, ebx
0x1800cc1fc  call    cs:__imp__waccess
0x1800cc203  nop     dword ptr [rax+rax+00h]
0x1800cc208  mov     [rsi], eax
0x1800cc20a  test    eax, eax
0x1800cc20c  jz      short loc_1800CC230
0x1800cc20e  call    cs:__imp_GetLastError
0x1800cc215  nop     dword ptr [rax+rax+00h]
0x1800cc21a  cmp     eax, 2
0x1800cc21d  jz      short loc_1800CC230
0x1800cc21f  test    eax, eax
0x1800cc221  jg      short loc_1800CC227
0x1800cc223  mov     ebx, eax
0x1800cc225  jmp     short loc_1800CC230
0x1800cc227  movzx   ebx, ax
0x1800cc22a  or      ebx, 80070000h
0x1800cc230  lea     rcx, [rsp+38h+var_18]; this
0x1800cc235  call    ??1CSysString@@QEAA@XZ; CSysString::~CSysString(void)
0x1800cc23a  mov     rsi, [rsp+38h+arg_8]
0x1800cc23f  mov     eax, ebx
0x1800cc241  mov     rbx, [rsp+38h+arg_0]
0x1800cc246  add     rsp, 30h
0x1800cc24a  pop     rdi
0x1800cc24b  retn
```
