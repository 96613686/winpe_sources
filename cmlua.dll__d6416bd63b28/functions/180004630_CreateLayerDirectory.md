# _CreateLayerDirectory

- ea: `0x180004630`
- end: `0x1800047d9`
- name: `_CreateLayerDirectory`
- size: `425`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800029b0`

## callees

- `0x1800016d8`
- `0x180003f78`
- `0x180004630`
- `0x180004d54`
- `0x180005486`
- `0x1800054b0`

## import_xrefs

- `KERNEL32!SetCurrentDirectoryW` at `0x180004757`
- `KERNEL32!SetCurrentDirectoryW` at `0x180004789`
- `KERNEL32!SetCurrentDirectoryW` at `0x180004757`
- `KERNEL32!SetCurrentDirectoryW` at `0x180004789`
- `KERNEL32!CreateDirectoryW` at `0x180004768`
- `KERNEL32!CreateDirectoryW` at `0x180004768`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800046fa`
- `KERNEL32!GetCurrentDirectoryW` at `0x1800046fa`
- `KERNEL32!GetLastError` at `0x180004774`
- `KERNEL32!GetLastError` at `0x180004774`

## string_xrefs

- `0x18000479f`: `StringCchCopyEx failed with error: 0x%x\n`

## pseudocode

```c
__int64 __fastcall CreateLayerDirectory(unsigned __int16 *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  int v4; // edx
  unsigned int DirectoryW; // edi
  unsigned int v6; // ebp
  unsigned __int16 **v7; // r9
  int v8; // eax
  __int64 v9; // rax
  unsigned __int64 *v11; // [rsp+20h] [rbp-478h]
  wchar_t PathName[264]; // [rsp+30h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+240h] [rbp-258h] BYREF

  LODWORD(v2) = 0;
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  if ( (unsigned int)v3 <= 2 )
  {
    if ( *a1 == 92 )
      LODWORD(v2) = 0;
  }
  else if ( a1[1] == 58 )
  {
    LOBYTE(v2) = a1[2] == 92;
    LODWORD(v2) = v2 + 1;
  }
  else if ( *a1 == 92 )
  {
    if ( a1[1] == 92 )
    {
      v4 = 0;
      LODWORD(v2) = 2;
      while ( a1[(unsigned int)v2] != 92 || ++v4 != 2 )
      {
        LODWORD(v2) = v2 + 1;
        if ( (unsigned int)v2 >= (unsigned int)v3 )
          return 1;
      }
    }
    else
    {
      LODWORD(v2) = 1;
    }
  }
  v6 = v3 - 1;
LABEL_17:
  if ( (unsigned int)v2 >= v6 )
    goto LABEL_19;
  while ( 1 )
  {
    v2 = (unsigned int)(v2 + 1);
    if ( a1[v2] != 92 )
      goto LABEL_17;
LABEL_19:
    memset_0(Buffer, 0, 0x20Au);
    if ( !GetCurrentDirectoryW(0x105u, Buffer) )
      return 0;
    memset_0(PathName, 0, 0x20Au);
    v8 = StringCchCopyExW(PathName, 0x105u, a1, v7, v11, 0x900u);
    if ( v8 < 0 )
      break;
    v9 = (unsigned int)(v2 + 1);
    if ( (unsigned int)v9 >= 0x105 )
      return 0;
    if ( (unsigned __int64)(2 * v9) >= 0x20A )
      _report_rangecheckfailure();
    PathName[v9] = 0;
    if ( !SetCurrentDirectoryW(PathName) )
    {
      DirectoryW = CreateDirectoryW(PathName, 0);
      if ( !DirectoryW && GetLastError() != 183 )
        return DirectoryW;
    }
    SetCurrentDirectoryW(Buffer);
    if ( (unsigned int)v2 >= v6 )
      return 1;
  }
  MyDbgPrintfA(0xFFFFFFFFLL, "StringCchCopyEx failed with error: 0x%x\n", v8);
  return 0;
}

```

## disassembly

```asm
0x180004630  push    rbx
0x180004632  push    rbp
0x180004633  push    rsi
0x180004634  push    rdi
0x180004635  push    r13
0x180004637  push    r14
0x180004639  sub     rsp, 468h
0x180004640  mov     rax, cs:__security_cookie
0x180004647  xor     rax, rsp
0x18000464a  mov     [rsp+498h+var_48], rax
0x180004652  xor     r14d, r14d
0x180004655  mov     rsi, rcx
0x180004658  mov     ebx, r14d
0x18000465b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000465f  inc     rcx
0x180004662  cmp     [rsi+rcx*2], r14w
0x180004667  jnz     short loc_18000465F
0x180004669  cmp     ecx, 2
0x18000466c  jbe     short loc_1800046BD
0x18000466e  cmp     word ptr [rsi+2], 3Ah ; ':'
0x180004673  jnz     short loc_180004681
0x180004675  cmp     word ptr [rsi+4], 5Ch ; '\'
0x18000467a  setz    bl
0x18000467d  inc     ebx
0x18000467f  jmp     short loc_1800046C5
0x180004681  cmp     word ptr [rsi], 5Ch ; '\'
0x180004685  jnz     short loc_1800046C5
0x180004687  cmp     word ptr [rsi+2], 5Ch ; '\'
0x18000468c  jnz     short loc_1800046B6
0x18000468e  mov     edx, r14d
0x180004691  mov     ebx, 2
0x180004696  mov     eax, ebx
0x180004698  cmp     word ptr [rsi+rax*2], 5Ch ; '\'
0x18000469d  jnz     short loc_1800046A6
0x18000469f  inc     edx
0x1800046a1  cmp     edx, 2
0x1800046a4  jz      short loc_1800046C5
0x1800046a6  inc     ebx
0x1800046a8  cmp     ebx, ecx
0x1800046aa  jb      short loc_180004696
0x1800046ac  mov     edi, 1
0x1800046b1  jmp     loc_1800047B1
0x1800046b6  mov     ebx, 1
0x1800046bb  jmp     short loc_1800046C5
0x1800046bd  cmp     word ptr [rsi], 5Ch ; '\'
0x1800046c1  cmovz   ebx, r14d
0x1800046c5  lea     ebp, [rcx-1]
0x1800046c8  mov     r13d, 20Ah
0x1800046ce  cmp     ebx, ebp
0x1800046d0  jnb     short loc_1800046DB
0x1800046d2  inc     ebx
0x1800046d4  cmp     word ptr [rsi+rbx*2], 5Ch ; '\'
0x1800046d9  jnz     short loc_1800046CE
0x1800046db  mov     r8, r13; Size
0x1800046de  lea     rcx, [rsp+498h+Buffer]; void *
0x1800046e6  xor     edx, edx; Val
0x1800046e8  call    memset_0
0x1800046ed  lea     rdx, [rsp+498h+Buffer]; lpBuffer
0x1800046f5  mov     ecx, 105h; nBufferLength
0x1800046fa  call    cs:__imp_GetCurrentDirectoryW
0x180004700  test    eax, eax
0x180004702  jz      loc_1800047AE
0x180004708  mov     r8, r13; Size
0x18000470b  lea     rcx, [rsp+498h+PathName]; void *
0x180004710  xor     edx, edx; Val
0x180004712  call    memset_0
0x180004717  mov     r8, rsi; unsigned __int16 *
0x18000471a  mov     [rsp+498h+var_470], 900h; unsigned int
0x180004722  mov     edx, 105h; unsigned __int64
0x180004727  lea     rcx, [rsp+498h+PathName]; pszDest
0x18000472c  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180004731  test    eax, eax
0x180004733  js      short loc_18000479C
0x180004735  lea     eax, [rbx+1]
0x180004738  cmp     eax, 105h
0x18000473d  jnb     short loc_1800047AE
0x18000473f  lea     rcx, [rax+rax]
0x180004743  cmp     rcx, r13
0x180004746  jnb     loc_1800047D3
0x18000474c  mov     [rsp+rcx+498h+PathName], r14w
0x180004752  lea     rcx, [rsp+498h+PathName]; lpPathName
0x180004757  call    cs:__imp_SetCurrentDirectoryW
0x18000475d  test    eax, eax
0x18000475f  jnz     short loc_180004781
0x180004761  xor     edx, edx; lpSecurityAttributes
0x180004763  lea     rcx, [rsp+498h+PathName]; lpPathName
0x180004768  call    cs:__imp_CreateDirectoryW
0x18000476e  mov     edi, eax
0x180004770  test    eax, eax
0x180004772  jnz     short loc_180004781
0x180004774  call    cs:__imp_GetLastError
0x18000477a  cmp     eax, 0B7h
0x18000477f  jnz     short loc_1800047B1
0x180004781  lea     rcx, [rsp+498h+Buffer]; lpPathName
0x180004789  call    cs:__imp_SetCurrentDirectoryW
0x18000478f  cmp     ebx, ebp
0x180004791  jb      loc_1800046D2
0x180004797  jmp     loc_1800046AC
0x18000479c  mov     r8d, eax
0x18000479f  lea     rdx, aStringcchcopye; "StringCchCopyEx failed with error: 0x%x"...
0x1800047a6  or      ecx, 0FFFFFFFFh
0x1800047a9  call    MyDbgPrintfA
0x1800047ae  mov     edi, r14d
0x1800047b1  mov     eax, edi
0x1800047b3  mov     rcx, [rsp+498h+var_48]
0x1800047bb  xor     rcx, rsp; StackCookie
0x1800047be  call    __security_check_cookie
0x1800047c3  add     rsp, 468h
0x1800047ca  pop     r14
0x1800047cc  pop     r13
0x1800047ce  pop     rdi
0x1800047cf  pop     rsi
0x1800047d0  pop     rbp
0x1800047d1  pop     rbx
0x1800047d2  retn
0x1800047d3  call    __report_rangecheckfailure
```
