# CreateDriverUniqueUri(void *,_DRIVER_INFO_3W *,ushort * *)

- ea: `0x18001bc9c`
- end: `0x18001beb0`
- name: `?CreateDriverUniqueUri@@YAJPEAXPEAU_DRIVER_INFO_3W@@PEAPEAG@Z`
- size: `532`
- prototype: `__int64 __fastcall(void *, struct _DRIVER_INFO_3W *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b9c`

## callees

- `0x180007660`
- `0x18001bc9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001bce2`
- `KERNEL32!GetLastError` at `0x18001bce2`
- `KERNEL32!GetProcessHeap` at `0x18001bda8`
- `KERNEL32!GetProcessHeap` at `0x18001bde7`
- `KERNEL32!GetProcessHeap` at `0x18001bda8`
- `KERNEL32!GetProcessHeap` at `0x18001bde7`
- `KERNEL32!HeapAlloc` at `0x18001bdb6`
- `KERNEL32!HeapAlloc` at `0x18001bdb6`
- `KERNEL32!HeapFree` at `0x18001bdf5`
- `KERNEL32!HeapFree` at `0x18001bdf5`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001bd1b`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001bd1b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bdd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001bdd9`
- `VERSION!VerQueryValueW` at `0x18001be45`
- `VERSION!VerQueryValueW` at `0x18001be45`
- `VERSION!GetFileVersionInfoW` at `0x18001be1d`
- `VERSION!GetFileVersionInfoW` at `0x18001be1d`
- `VERSION!GetFileVersionInfoSizeW` at `0x18001bcce`
- `VERSION!GetFileVersionInfoSizeW` at `0x18001bcce`

## string_xrefs

- `0x18001bd60`: `http://schemas.microsoft.com/windows/printing/oemdriverpt`

## pseudocode

```c
__int64 __fastcall CreateDriverUniqueUri(void *a1, struct _DRIVER_INFO_3W *a2, unsigned __int16 **a3)
{
  signed int FileVersionInfoSizeW; // eax
  SIZE_T v6; // rdi
  void *v7; // rsi
  signed int LastError; // eax
  signed int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rax
  int v12; // ebx
  unsigned __int16 *v13; // rax
  unsigned __int16 *i; // rcx
  HANDLE ProcessHeap; // rax
  void *v16; // rax
  HANDLE v17; // rax
  int v19; // edx
  __int64 v20; // r8
  void *puLen; // [rsp+80h] [rbp+8h] BYREF
  DWORD v22; // [rsp+90h] [rbp+18h] BYREF
  LPVOID lpBuffer; // [rsp+98h] [rbp+20h] BYREF

  puLen = a1;
  *a3 = 0;
  v22 = 0;
  lpBuffer = 0;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW(a2->pConfigFile, &v22);
  v6 = FileVersionInfoSizeW;
  if ( !FileVersionInfoSizeW )
  {
    v7 = 0;
LABEL_3:
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
      goto LABEL_14;
    goto LABEL_6;
  }
  ProcessHeap = GetProcessHeap();
  v16 = HeapAlloc(ProcessHeap, 0, v6);
  LODWORD(puLen) = 0;
  v7 = v16;
  if ( !v16 )
  {
LABEL_13:
    v9 = -2147024882;
    goto LABEL_14;
  }
  if ( !GetFileVersionInfoW(a2->pConfigFile, 0, v6, v16) || !VerQueryValueW(v7, L"\\", &lpBuffer, (PUINT)&puLen) )
    goto LABEL_3;
  if ( (unsigned int)puLen < 0x18 )
  {
    v9 = -2147418113;
    goto LABEL_14;
  }
LABEL_6:
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2->pName[v11] );
  v12 = v11 + 89;
  v13 = SysAllocStringLen(0, (int)v11 + 89);
  *a3 = v13;
  if ( !v13 )
    goto LABEL_13;
  v9 = StringCchPrintfW(
         v13,
         v12 + 1,
         L"%s/%s/%d.%d.%d.%d/",
         L"http://schemas.microsoft.com/windows/printing/oemdriverpt",
         a2->pName,
         HIWORD(*((_DWORD *)lpBuffer + 4)),
         (unsigned __int16)*((_DWORD *)lpBuffer + 4),
         HIWORD(*((_DWORD *)lpBuffer + 5)),
         (unsigned __int16)*((_DWORD *)lpBuffer + 5));
  if ( v9 >= 0 )
  {
    do
      ++v10;
    while ( a2->pName[v10] );
    for ( i = *a3 + 58; *i && (_DWORD)v10; ++i )
    {
      v19 = *i;
      if ( (unsigned __int16)(v19 - 48) > 0x2Au || (v20 = 0x7FFFFFE03FFLL, !_bittest64(&v20, (unsigned int)(v19 - 48))) )
      {
        if ( (unsigned __int16)(v19 - 97) > 0x19u )
          *i = 95;
      }
      LODWORD(v10) = v10 - 2;
    }
    goto LABEL_16;
  }
LABEL_14:
  if ( *a3 )
  {
    SysFreeString(*a3);
    *a3 = 0;
  }
LABEL_16:
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001bc9c  mov     rax, rsp
0x18001bc9f  mov     [rax+10h], rbx
0x18001bca3  mov     [rax+8], rcx
0x18001bca7  push    rbp
0x18001bca8  push    rsi
0x18001bca9  push    rdi
0x18001bcaa  push    r14
0x18001bcac  push    r15
0x18001bcae  sub     rsp, 50h
0x18001bcb2  mov     rbp, rdx
0x18001bcb5  xor     r15d, r15d
0x18001bcb8  mov     [r8], r15
0x18001bcbb  lea     rdx, [rax+18h]; lpdwHandle
0x18001bcbf  mov     r14, r8
0x18001bcc2  mov     [rax+18h], r15d
0x18001bcc6  mov     [rax+20h], r15
0x18001bcca  mov     rcx, [rbp+28h]; lptstrFilename
0x18001bcce  call    cs:__imp_GetFileVersionInfoSizeW
0x18001bcd4  movsxd  rdi, eax
0x18001bcd7  test    eax, eax
0x18001bcd9  jnz     loc_18001BDA8
0x18001bcdf  mov     esi, r15d
0x18001bce2  call    cs:__imp_GetLastError
0x18001bce8  mov     ebx, eax
0x18001bcea  test    eax, eax
0x18001bcec  jle     short loc_18001BCF7
0x18001bcee  movzx   ebx, ax
0x18001bcf1  or      ebx, 80070000h
0x18001bcf7  test    ebx, ebx
0x18001bcf9  js      loc_18001BDD1
0x18001bcff  mov     rcx, [rbp+8]
0x18001bd03  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001bd07  mov     rax, rdi
0x18001bd0a  inc     rax
0x18001bd0d  cmp     [rcx+rax*2], r15w
0x18001bd12  jnz     short loc_18001BD0A
0x18001bd14  lea     ebx, [rax+59h]
0x18001bd17  xor     ecx, ecx; strIn
0x18001bd19  mov     edx, ebx; ui
0x18001bd1b  call    cs:__imp_SysAllocStringLen
0x18001bd21  mov     [r14], rax
0x18001bd24  mov     r11, rax
0x18001bd27  test    rax, rax
0x18001bd2a  jz      loc_18001BDCC
0x18001bd30  mov     rax, [rsp+78h+lpBuffer]
0x18001bd38  mov     r9d, [rax+14h]
0x18001bd3c  mov     r10d, [rax+10h]
0x18001bd40  lea     eax, [rbx+1]
0x18001bd43  movzx   r8d, r9w
0x18001bd47  mov     [rsp+78h+var_38], r8d
0x18001bd4c  lea     r8, aSSDDDD; "%s/%s/%d.%d.%d.%d/"
0x18001bd53  movzx   ecx, r10w
0x18001bd57  shr     r9d, 10h
0x18001bd5b  mov     [rsp+78h+var_40], r9d
0x18001bd60  lea     r9, aHttpSchemasMic_2; "http://schemas.microsoft.com/windows/pr"...
0x18001bd67  mov     [rsp+78h+var_48], ecx
0x18001bd6b  mov     rcx, r11; unsigned __int16 *
0x18001bd6e  shr     r10d, 10h
0x18001bd72  movsxd  rdx, eax; unsigned __int64
0x18001bd75  mov     rax, [rbp+8]
0x18001bd79  mov     [rsp+78h+var_50], r10d
0x18001bd7e  mov     [rsp+78h+var_58], rax
0x18001bd83  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001bd88  mov     ebx, eax
0x18001bd8a  test    eax, eax
0x18001bd8c  js      short loc_18001BDD1
0x18001bd8e  mov     rax, [rbp+8]
0x18001bd92  inc     rdi
0x18001bd95  cmp     [rax+rdi*2], r15w
0x18001bd9a  jnz     short loc_18001BD92
0x18001bd9c  mov     rcx, [r14]
0x18001bd9f  add     rcx, 74h ; 't'
0x18001bda3  jmp     loc_18001BEA5
0x18001bda8  call    cs:__imp_GetProcessHeap
0x18001bdae  mov     r8, rdi; dwBytes
0x18001bdb1  xor     edx, edx; dwFlags
0x18001bdb3  mov     rcx, rax; hHeap
0x18001bdb6  call    cs:__imp_HeapAlloc
0x18001bdbc  mov     dword ptr [rsp+78h+puLen], r15d
0x18001bdc4  mov     rsi, rax
0x18001bdc7  test    rax, rax
0x18001bdca  jnz     short loc_18001BE11
0x18001bdcc  mov     ebx, 8007000Eh
0x18001bdd1  mov     rcx, [r14]; bstrString
0x18001bdd4  test    rcx, rcx
0x18001bdd7  jz      short loc_18001BDE2
0x18001bdd9  call    cs:__imp_SysFreeString
0x18001bddf  mov     [r14], r15
0x18001bde2  test    rsi, rsi
0x18001bde5  jz      short loc_18001BDFB
0x18001bde7  call    cs:__imp_GetProcessHeap
0x18001bded  mov     r8, rsi; lpMem
0x18001bdf0  xor     edx, edx; dwFlags
0x18001bdf2  mov     rcx, rax; hHeap
0x18001bdf5  call    cs:__imp_HeapFree
0x18001bdfb  mov     eax, ebx
0x18001bdfd  mov     rbx, [rsp+78h+arg_8]
0x18001be05  add     rsp, 50h
0x18001be09  pop     r15
0x18001be0b  pop     r14
0x18001be0d  pop     rdi
0x18001be0e  pop     rsi
0x18001be0f  pop     rbp
0x18001be10  retn
0x18001be11  mov     rcx, [rbp+28h]; lptstrFilename
0x18001be15  mov     r9, rsi; lpData
0x18001be18  mov     r8d, edi; dwLen
0x18001be1b  xor     edx, edx; dwHandle
0x18001be1d  call    cs:__imp_GetFileVersionInfoW
0x18001be23  test    eax, eax
0x18001be25  jz      loc_18001BCE2
0x18001be2b  lea     r9, [rsp+78h+puLen]; puLen
0x18001be33  mov     rcx, rsi; pBlock
0x18001be36  lea     r8, [rsp+78h+lpBuffer]; lplpBuffer
0x18001be3e  lea     rdx, SubBlock; "\\"
0x18001be45  call    cs:__imp_VerQueryValueW
0x18001be4b  test    eax, eax
0x18001be4d  jz      loc_18001BCE2
0x18001be53  cmp     dword ptr [rsp+78h+puLen], 18h
0x18001be5b  jnb     loc_18001BCFF
0x18001be61  mov     ebx, 8000FFFFh
0x18001be66  jmp     loc_18001BDD1
0x18001be6b  test    edi, edi
0x18001be6d  jz      loc_18001BDE2
0x18001be73  movzx   edx, word ptr [rcx]
0x18001be76  lea     eax, [rdx-30h]
0x18001be79  cmp     ax, 2Ah ; '*'
0x18001be7d  ja      short loc_18001BE8F
0x18001be7f  mov     r8, 7FFFFFE03FFh
0x18001be89  bt      r8, rax
0x18001be8d  jb      short loc_18001BE9E
0x18001be8f  sub     dx, 61h ; 'a'
0x18001be93  cmp     dx, 19h
0x18001be97  jbe     short loc_18001BE9E
0x18001be99  mov     word ptr [rcx], 5Fh ; '_'
0x18001be9e  add     rcx, 2
0x18001bea2  add     edi, 0FFFFFFFEh
0x18001bea5  cmp     [rcx], r15w
0x18001bea9  jnz     short loc_18001BE6B
0x18001beab  jmp     loc_18001BDE2
```
