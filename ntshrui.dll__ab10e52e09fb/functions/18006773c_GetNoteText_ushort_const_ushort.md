# GetNoteText(ushort const *,ushort * *)

- ea: `0x18006773c`
- end: `0x18006789a`
- name: `?GetNoteText@@YAJPEBGPEAPEAG@Z`
- size: `350`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800679b0`

## callees

- `0x1800098dc`
- `0x180013220`
- `0x18001b608`
- `0x180021f0c`
- `0x1800254e0`
- `0x18006773c`
- `0x180073598`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006785c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006786d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006785c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006786d`
- `KERNEL32!GetComputerNameW` at `0x1800677a5`
- `KERNEL32!GetComputerNameW` at `0x1800677a5`
- `SHCORE!IsOS` at `0x180067775`
- `SHCORE!IsOS` at `0x180067775`

## pseudocode

```c
__int64 __fastcall GetNoteText(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  int v4; // eax
  int Error; // ebx
  __int64 v6; // rax
  __int64 v7; // rcx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rdi
  LPVOID pv; // [rsp+20h] [rbp-40h] BYREF
  DWORD nSize[2]; // [rsp+28h] [rbp-38h] BYREF
  WCHAR Buffer[16]; // [rsp+30h] [rbp-30h] BYREF

  pv = 0;
  if ( IsOS(0x1Cu) )
  {
    v4 = SHFormatResMessageArgAlloc(g_hInstance, 3766, &pv);
  }
  else
  {
    nSize[0] = 16;
    if ( !GetComputerNameW(Buffer, nSize) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        return (unsigned int)Error;
    }
    v4 = SHFormatResMessageArgAlloc(g_hInstance, 3767, &pv);
  }
  Error = v4;
  if ( v4 >= 0 )
  {
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
    do
      ++v6;
    while ( *((_WORD *)pv + v6) );
    v8 = v6 + 1;
    v9 = v8 + v7;
    if ( v8 + v7 < v8 )
    {
      Error = -2147024362;
    }
    else
    {
      *(_QWORD *)nSize = 0;
      Error = _AllocArray<unsigned short,CTCoAllocPolicy>(v7, 1, v8 + v7, nSize);
      if ( Error >= 0 )
      {
        v10 = *(unsigned __int16 **)nSize;
        Error = StringCchCopyW(*(unsigned __int16 **)nSize, v9, (const unsigned __int16 *)pv);
        if ( Error < 0 || (Error = StringCchCatW(v10, v9, a1), Error < 0) )
          CoTaskMemFree(v10);
        else
          *a2 = v10;
      }
    }
    CoTaskMemFree(pv);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006773c  mov     [rsp-28h+arg_10], rbx
0x180067741  mov     [rsp-28h+arg_18], rsi
0x180067746  push    rbp
0x180067747  push    rdi
0x180067748  push    r12
0x18006774a  push    r14
0x18006774c  push    r15
0x18006774e  mov     rbp, rsp
0x180067751  sub     rsp, 60h
0x180067755  mov     rax, cs:__security_cookie
0x18006775c  xor     rax, rsp
0x18006775f  mov     [rbp+var_10], rax
0x180067763  xor     r12d, r12d
0x180067766  mov     r14, rcx
0x180067769  mov     r15, rdx
0x18006776c  mov     [rbp+pv], r12
0x180067770  lea     ecx, [r12+1Ch]; dwOS
0x180067775  call    cs:__imp_IsOS
0x18006777b  test    eax, eax
0x18006777d  jz      short loc_180067796
0x18006777f  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x180067786  lea     r8, [rbp+pv]
0x18006778a  mov     edx, 0EB6h
0x18006778f  call    SHFormatResMessageArgAlloc
0x180067794  jmp     short loc_1800677D7
0x180067796  lea     rdx, [rbp+nSize]; nSize
0x18006779a  mov     [rbp+nSize], 10h
0x1800677a1  lea     rcx, [rbp+Buffer]; lpBuffer
0x1800677a5  call    cs:__imp_GetComputerNameW
0x1800677ab  test    eax, eax
0x1800677ad  jnz     short loc_1800677BE
0x1800677af  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800677b4  mov     ebx, eax
0x1800677b6  test    eax, eax
0x1800677b8  js      loc_180067873
0x1800677be  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800677c5  lea     r9, [rbp+Buffer]
0x1800677c9  lea     r8, [rbp+pv]
0x1800677cd  mov     edx, 0EB7h
0x1800677d2  call    SHFormatResMessageArgAlloc
0x1800677d7  mov     ebx, eax
0x1800677d9  test    eax, eax
0x1800677db  js      loc_180067873
0x1800677e1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800677e5  mov     rcx, rax
0x1800677e8  inc     rcx
0x1800677eb  cmp     [r14+rcx*2], r12w
0x1800677f0  jnz     short loc_1800677E8
0x1800677f2  mov     rdx, [rbp+pv]
0x1800677f6  inc     rax
0x1800677f9  cmp     [rdx+rax*2], r12w
0x1800677fe  jnz     short loc_1800677F6
0x180067800  inc     rax
0x180067803  lea     rsi, [rax+rcx]
0x180067807  cmp     rsi, rax
0x18006780a  jb      short loc_180067864
0x18006780c  lea     r9, [rbp+nSize]
0x180067810  mov     qword ptr [rbp+nSize], r12
0x180067814  mov     r8, rsi
0x180067817  mov     edx, 1
0x18006781c  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180067821  mov     ebx, eax
0x180067823  test    eax, eax
0x180067825  js      short loc_180067869
0x180067827  mov     rdi, qword ptr [rbp+nSize]
0x18006782b  mov     rdx, rsi; unsigned __int64
0x18006782e  mov     r8, [rbp+pv]; unsigned __int16 *
0x180067832  mov     rcx, rdi; unsigned __int16 *
0x180067835  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006783a  mov     ebx, eax
0x18006783c  test    eax, eax
0x18006783e  js      short loc_180067859
0x180067840  mov     r8, r14; unsigned __int16 *
0x180067843  mov     rdx, rsi; unsigned __int64
0x180067846  mov     rcx, rdi; unsigned __int16 *
0x180067849  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006784e  mov     ebx, eax
0x180067850  test    eax, eax
0x180067852  js      short loc_180067859
0x180067854  mov     [r15], rdi
0x180067857  jmp     short loc_180067869
0x180067859  mov     rcx, rdi; pv
0x18006785c  call    cs:__imp_CoTaskMemFree
0x180067862  jmp     short loc_180067869
0x180067864  mov     ebx, 80070216h
0x180067869  mov     rcx, [rbp+pv]; pv
0x18006786d  call    cs:__imp_CoTaskMemFree
0x180067873  mov     eax, ebx
0x180067875  mov     rcx, [rbp+var_10]
0x180067879  xor     rcx, rsp; StackCookie
0x18006787c  call    __security_check_cookie
0x180067881  lea     r11, [rsp+60h+var_s0]
0x180067886  mov     rbx, [r11+40h]
0x18006788a  mov     rsi, [r11+48h]
0x18006788e  mov     rsp, r11
0x180067891  pop     r15
0x180067893  pop     r14
0x180067895  pop     r12
0x180067897  pop     rdi
0x180067898  pop     rbp
0x180067899  retn
```
