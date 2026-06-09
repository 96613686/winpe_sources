# TMBSchemaCompilation::GetBinFileName(ushort *,ulong *)

- ea: `0x180017114`
- end: `0x180017368`
- name: `?GetBinFileName@TMBSchemaCompilation@@QEAAJPEAGPEAK@Z`
- size: `596`
- prototype: `signed int __fastcall(TMBSchemaCompilation *this, wchar_t *lpFileName, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800031c0`

## callees

- `0x1800113fc`
- `0x180017114`
- `0x180017b70`
- `0x18002e0ca`
- `0x18002e110`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800172d4`
- `msvcrt!swprintf_s` at `0x1800172d4`
- `msvcrt!wcscpy_s` at `0x180017238`
- `msvcrt!wcscpy_s` at `0x180017238`
- `msvcrt!wcsrchr` at `0x180017182`
- `msvcrt!wcsrchr` at `0x180017182`
- `KERNEL32!GetFileAttributesW` at `0x180017195`
- `KERNEL32!GetFileAttributesW` at `0x180017195`
- `KERNEL32!GetLastError` at `0x1800171a0`
- `KERNEL32!GetLastError` at `0x1800171a0`
- `KERNEL32!GetModuleFileNameW` at `0x180017170`
- `KERNEL32!GetModuleFileNameW` at `0x180017170`
- `ole32!CoTaskMemAlloc` at `0x180017209`
- `ole32!CoTaskMemAlloc` at `0x180017209`

## pseudocode

```c
signed int __fastcall TMBSchemaCompilation::GetBinFileName(
        TMBSchemaCompilation *this,
        wchar_t *lpFileName,
        unsigned int *a3)
{
  wchar_t *v6; // rax
  DWORD FileAttributesW; // eax
  signed int result; // eax
  bool v9; // sf
  __int64 v10; // rcx
  wchar_t *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int32 v14; // eax
  int v15; // r8d
  TFileMapping *v16; // rcx
  int v17; // eax
  bool v18[4]; // [rsp+30h] [rbp-848h] BYREF
  wchar_t Filename[1024]; // [rsp+40h] [rbp-838h] BYREF

  if ( !*((_QWORD *)this + 321) )
  {
    memset_0(Filename, 0, sizeof(Filename));
    GetModuleFileNameW(g_hModule, Filename, 0x400u);
    v6 = wcsrchr(Filename, 0x5Cu);
    if ( v6 )
      *v6 = 0;
    FileAttributesW = GetFileAttributesW(Filename);
    if ( FileAttributesW == -1 )
    {
      result = GetLastError();
      v9 = result < 0;
      if ( result > 0 )
      {
        result = (unsigned __int16)result | 0x80070000;
        v9 = result < 0;
      }
      if ( v9 )
        return result;
    }
    else
    {
      if ( (FileAttributesW & 0x10) == 0 )
        return -2147024893;
      if ( !*((_QWORD *)this + 321) )
      {
        v10 = -1;
        do
          ++v10;
        while ( Filename[v10] );
        *((_QWORD *)this + 320) = v10;
        v11 = (wchar_t *)CoTaskMemAlloc(saturated_mul(v10 + 2, 2u));
        *((_QWORD *)this + 321) = v11;
        if ( !v11 )
          return -2147024882;
        wcscpy_s(v11, *((_QWORD *)this + 320) + 2LL, Filename);
        v12 = *((_QWORD *)this + 320);
        v13 = *((_QWORD *)this + 321);
        if ( *(_WORD *)(v13 + 2 * v12 - 2) != 92 )
        {
          *(_WORD *)(v13 + 2 * v12) = 92;
          *(_WORD *)(*((_QWORD *)this + 321) + 2LL * *((_QWORD *)this + 320) + 2) = 0;
          v12 = *((_QWORD *)this + 320) + 1LL;
        }
        *((_QWORD *)this + 320) = v12 + 23;
        TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(this);
      }
    }
  }
  if ( lpFileName && *a3 < *((_DWORD *)this + 640) )
    return -2145318874;
  v14 = *((_DWORD *)this + 644);
  *(_DWORD *)v18 = 0;
  _InterlockedExchange((volatile __int32 *)v18, v14);
  if ( lpFileName )
  {
    if ( *(int *)v18 < 0 )
    {
      *lpFileName = 0;
    }
    else
    {
      swprintf_s(lpFileName, *a3, L"%sMBSchema.bin.%08xh", *((_QWORD *)this + 321), *(_DWORD *)v18);
      v15 = *(_DWORD *)v18;
      v16 = (TMBSchemaCompilation *)((char *)this + 40 * (*(_DWORD *)v18 % 63));
      v17 = *((_DWORD *)v16 + 8);
      if ( v17 )
      {
        *((_DWORD *)v16 + 8) = v17 + 1;
      }
      else
      {
        *((_DWORD *)v16 + 8) = 1;
        *((_DWORD *)v16 + 9) = v15;
        result = TFileMapping::Load(v16, lpFileName, v15);
        if ( result < 0 )
          return result;
      }
    }
  }
  *a3 = *((_DWORD *)this + 640);
  return lpFileName && *lpFileName == 0;
}

```

## disassembly

```asm
0x180017114  push    rbx
0x180017116  push    rbp
0x180017117  push    rsi
0x180017118  push    rdi
0x180017119  push    r14
0x18001711b  sub     rsp, 850h
0x180017122  mov     rax, cs:__security_cookie
0x180017129  xor     rax, rsp
0x18001712c  mov     [rsp+878h+var_38], rax
0x180017134  xor     ebp, ebp
0x180017136  mov     rsi, r8
0x180017139  mov     rdi, rdx
0x18001713c  mov     rbx, rcx
0x18001713f  cmp     [rcx+0A08h], rbp
0x180017146  jnz     loc_180017289
0x18001714c  xor     edx, edx; Val
0x18001714e  lea     rcx, [rsp+878h+Filename]; void *
0x180017153  mov     r8d, 800h; Size
0x180017159  call    memset_0
0x18001715e  mov     rcx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; hModule
0x180017165  lea     rdx, [rsp+878h+Filename]; lpFilename
0x18001716a  mov     r8d, 400h; nSize
0x180017170  call    cs:__imp_GetModuleFileNameW
0x180017176  lea     r14d, [rbp+5Ch]
0x18001717a  mov     edx, r14d; Ch
0x18001717d  lea     rcx, [rsp+878h+Filename]; Str
0x180017182  call    cs:__imp_wcsrchr
0x180017188  test    rax, rax
0x18001718b  jz      short loc_180017190
0x18001718d  mov     [rax], bp
0x180017190  lea     rcx, [rsp+878h+Filename]; lpFileName
0x180017195  call    cs:__imp_GetFileAttributesW
0x18001719b  cmp     eax, 0FFFFFFFFh
0x18001719e  jnz     short loc_1800171BF
0x1800171a0  call    cs:__imp_GetLastError
0x1800171a6  test    eax, eax
0x1800171a8  jle     short loc_1800171B4
0x1800171aa  movzx   eax, ax
0x1800171ad  or      eax, 80070000h
0x1800171b2  test    eax, eax
0x1800171b4  jns     loc_180017289
0x1800171ba  jmp     loc_18001734A
0x1800171bf  test    al, 10h
0x1800171c1  jnz     short loc_1800171CD
0x1800171c3  mov     eax, 80070003h
0x1800171c8  jmp     loc_18001734A
0x1800171cd  cmp     [rbx+0A08h], rbp
0x1800171d4  jnz     loc_180017289
0x1800171da  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800171de  lea     rax, [rsp+878h+Filename]
0x1800171e3  mov     rcx, r8
0x1800171e6  inc     rcx
0x1800171e9  cmp     [rax+rcx*2], bp
0x1800171ed  jnz     short loc_1800171E6
0x1800171ef  mov     [rbx+0A00h], rcx
0x1800171f6  mov     eax, 2
0x1800171fb  add     rcx, 2
0x1800171ff  mul     rcx
0x180017202  cmovb   rax, r8
0x180017206  mov     rcx, rax; cb
0x180017209  call    cs:__imp_CoTaskMemAlloc
0x18001720f  mov     [rbx+0A08h], rax
0x180017216  test    rax, rax
0x180017219  jnz     short loc_180017225
0x18001721b  mov     eax, 8007000Eh
0x180017220  jmp     loc_18001734A
0x180017225  mov     rdx, [rbx+0A00h]
0x18001722c  lea     r8, [rsp+878h+Filename]; Source
0x180017231  add     rdx, 2; SizeInWords
0x180017235  mov     rcx, rax; Destination
0x180017238  call    cs:__imp_wcscpy_s
0x18001723e  mov     rax, [rbx+0A00h]
0x180017245  mov     rcx, [rbx+0A08h]
0x18001724c  cmp     [rcx+rax*2-2], r14w
0x180017252  jz      short loc_180017276
0x180017254  mov     [rcx+rax*2], r14w
0x180017259  mov     rdx, [rbx+0A00h]
0x180017260  mov     rcx, [rbx+0A08h]
0x180017267  mov     [rcx+rdx*2+2], bp
0x18001726c  mov     rax, [rbx+0A00h]
0x180017273  inc     rax
0x180017276  add     rax, 17h
0x18001727a  mov     rcx, rbx; this
0x18001727d  mov     [rbx+0A00h], rax
0x180017284  call    ?WalkTheFileSystemToFindTheLatestBinFileName@TMBSchemaCompilation@@AEAAJXZ; TMBSchemaCompilation::WalkTheFileSystemToFindTheLatestBinFileName(void)
0x180017289  test    rdi, rdi
0x18001728c  jz      short loc_1800172A2
0x18001728e  mov     eax, [rbx+0A00h]
0x180017294  cmp     [rsi], eax
0x180017296  jnb     short loc_1800172A2
0x180017298  mov     eax, 80210826h
0x18001729d  jmp     loc_18001734A
0x1800172a2  mov     eax, [rbx+0A10h]
0x1800172a8  mov     dword ptr [rsp+878h+var_848], ebp
0x1800172ac  xchg    eax, dword ptr [rsp+878h+var_848]
0x1800172b0  test    rdi, rdi
0x1800172b3  jz      short loc_180017331
0x1800172b5  mov     eax, dword ptr [rsp+878h+var_848]
0x1800172b9  test    eax, eax
0x1800172bb  js      short loc_18001732E
0x1800172bd  mov     edx, [rsi]; BufferCount
0x1800172bf  lea     r8, aSmbschemaBin08; "%sMBSchema.bin.%08xh"
0x1800172c6  mov     r9, [rbx+0A08h]
0x1800172cd  mov     rcx, rdi; Buffer
0x1800172d0  mov     [rsp+878h+var_858], eax
0x1800172d4  call    cs:__imp_swprintf_s
0x1800172da  mov     r8d, dword ptr [rsp+878h+var_848]; bool
0x1800172df  mov     eax, 82082083h
0x1800172e4  imul    r8d
0x1800172e7  mov     ecx, r8d
0x1800172ea  add     edx, r8d
0x1800172ed  sar     edx, 5
0x1800172f0  mov     eax, edx
0x1800172f2  shr     eax, 1Fh
0x1800172f5  add     edx, eax
0x1800172f7  imul    eax, edx, 3Fh ; '?'
0x1800172fa  sub     ecx, eax
0x1800172fc  movsxd  rax, ecx
0x1800172ff  lea     rcx, [rax+rax*4]
0x180017303  lea     rcx, [rbx+rcx*8]; this
0x180017307  mov     eax, [rcx+20h]
0x18001730a  test    eax, eax
0x18001730c  jz      short loc_180017315
0x18001730e  inc     eax
0x180017310  mov     [rcx+20h], eax
0x180017313  jmp     short loc_180017331
0x180017315  mov     rdx, rdi; lpFileName
0x180017318  mov     dword ptr [rcx+20h], 1
0x18001731f  mov     [rcx+24h], r8d
0x180017323  call    ?Load@TFileMapping@@QEAAJPEBG_N@Z; TFileMapping::Load(ushort const *,bool)
0x180017328  test    eax, eax
0x18001732a  jns     short loc_180017331
0x18001732c  jmp     short loc_18001734A
0x18001732e  mov     [rdi], bp
0x180017331  mov     eax, [rbx+0A00h]
0x180017337  mov     [rsi], eax
0x180017339  test    rdi, rdi
0x18001733c  jnz     short loc_180017342
0x18001733e  xor     eax, eax
0x180017340  jmp     short loc_18001734A
0x180017342  cmp     bp, [rdi]
0x180017345  mov     eax, ebp
0x180017347  setz    al
0x18001734a  mov     rcx, [rsp+878h+var_38]
0x180017352  xor     rcx, rsp; StackCookie
0x180017355  call    __security_check_cookie
0x18001735a  add     rsp, 850h
0x180017361  pop     r14
0x180017363  pop     rdi
0x180017364  pop     rsi
0x180017365  pop     rbp
0x180017366  pop     rbx
0x180017367  retn
```
