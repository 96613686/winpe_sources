# CscUtil_ConvertItemToUNCPath(IShellItem *,ushort * *,ushort *,ushort *)

- ea: `0x180032064`
- end: `0x1800321b2`
- name: `?CscUtil_ConvertItemToUNCPath@@YAJPEAUIShellItem@@PEAPEAGPEAG2@Z`
- size: `334`
- prototype: `int(struct IShellItem *, unsigned __int16 **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800251a0`
- `0x180028ba0`
- `0x180029718`
- `0x1800298c0`
- `0x18002c144`

## callees

- `0x180003d60`
- `0x180004b80`
- `0x180006c94`
- `0x180011860`
- `0x180032064`
- `0x1800321b8`
- `0x18004c670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032193`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180032193`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800320ed`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800320ed`

## pseudocode

```c
__int64 __fastcall CscUtil_ConvertItemToUNCPath(
        struct IShellItem *a1,
        unsigned __int16 **a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  struct IShellItemVtbl *lpVtbl; // rax
  int StringCopy; // ebx
  unsigned __int16 *v9; // rcx
  struct IShellItemVtbl *v10; // rax
  unsigned int *v11; // r9
  LPVOID pv; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v14; // [rsp+28h] [rbp-18h] BYREF
  WCHAR RootPathName[2]; // [rsp+30h] [rbp-10h] BYREF
  __int16 v16; // [rsp+34h] [rbp-Ch]

  *a2 = 0;
  lpVtbl = a1->lpVtbl;
  v14 = 0;
  pv = 0;
  StringCopy = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned __int16 **, unsigned __int16 *))lpVtbl->GetDisplayName)(
                 a1,
                 2147844096LL,
                 &v14,
                 a4);
  if ( StringCopy < 0 )
    return (unsigned int)StringCopy;
  if ( !a3 )
    goto LABEL_6;
  v9 = v14;
  *a3 = 0;
  if ( v9[1] == 58 )
  {
    RootPathName[0] = *v9;
    RootPathName[1] = v9[1];
    v16 = 0;
    if ( GetDriveTypeW(RootPathName) == 4 )
      StringCchCopyW(a3, 3u, RootPathName);
LABEL_6:
    v9 = v14;
  }
  StringCopy = PathConvertToUNC(v9, (unsigned __int16 **)&pv);
  if ( StringCopy >= 0 )
  {
    StringCopy = CscUtil_CreateStringCopy((const unsigned __int16 *)pv, a2);
    CoTaskMemFree(pv);
  }
  else
  {
    v10 = a1->lpVtbl;
    *(_DWORD *)RootPathName = 0;
    if ( !((unsigned int (__fastcall *)(struct IShellItem *, __int64, WCHAR *))v10->GetAttributes)(
            a1,
            0x10000,
            RootPathName) )
    {
      pv = 0;
      if ( (int)GetLinkTarget(v14, 3, (unsigned __int16 **)&pv, v11) >= 0 )
      {
        if ( pv )
        {
          StringCopy = CscUtil_CreateStringCopy((const unsigned __int16 *)pv, a2);
          LocalFreeString((unsigned __int16 **)&pv);
        }
      }
    }
  }
  CoTaskMemFree(v14);
  return (unsigned int)StringCopy;
}

```

## disassembly

```asm
0x180032064  push    rbp
0x180032066  push    rbx
0x180032067  push    rsi
0x180032068  push    rdi
0x180032069  push    r14
0x18003206b  mov     rbp, rsp
0x18003206e  sub     rsp, 40h
0x180032072  mov     rax, cs:__security_cookie
0x180032079  xor     rax, rsp
0x18003207c  mov     [rbp+var_8], rax
0x180032080  mov     qword ptr [rdx], 0
0x180032087  mov     rdi, r8
0x18003208a  mov     rax, [rcx]
0x18003208d  lea     r8, [rbp+var_18]
0x180032091  mov     rsi, rdx
0x180032094  mov     [rbp+var_18], 0
0x18003209c  mov     edx, 80058000h
0x1800320a1  mov     [rbp+pv], 0
0x1800320a9  mov     r14, rcx
0x1800320ac  mov     rax, [rax+28h]
0x1800320b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800320b5  mov     ebx, eax
0x1800320b7  test    eax, eax
0x1800320b9  js      loc_180032199
0x1800320bf  test    rdi, rdi
0x1800320c2  jz      short loc_180032107
0x1800320c4  mov     rcx, [rbp+var_18]
0x1800320c8  xor     eax, eax
0x1800320ca  mov     [rdi], ax
0x1800320cd  cmp     word ptr [rcx+2], 3Ah ; ':'
0x1800320d2  jnz     short loc_18003210B
0x1800320d4  movzx   eax, word ptr [rcx]
0x1800320d7  mov     [rbp+RootPathName], ax
0x1800320db  movzx   eax, word ptr [rcx+2]
0x1800320df  lea     rcx, [rbp+RootPathName]; lpRootPathName
0x1800320e3  mov     [rbp+RootPathName+2], ax
0x1800320e7  xor     eax, eax
0x1800320e9  mov     [rbp+var_C], ax
0x1800320ed  call    cs:__imp_GetDriveTypeW
0x1800320f3  cmp     eax, 4
0x1800320f6  jnz     short loc_180032107
0x1800320f8  lea     r8, [rbp+RootPathName]; unsigned __int16 *
0x1800320fc  mov     rcx, rdi; unsigned __int16 *
0x1800320ff  lea     edx, [rax-1]; unsigned __int64
0x180032102  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180032107  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x18003210b  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18003210f  call    ?PathConvertToUNC@@YAJPEBGPEAPEAG@Z; PathConvertToUNC(ushort const *,ushort * *)
0x180032114  mov     ebx, eax
0x180032116  test    eax, eax
0x180032118  jns     short loc_180032177
0x18003211a  mov     rax, [r14]
0x18003211d  lea     r8, [rbp+RootPathName]
0x180032121  mov     edx, 10000h
0x180032126  mov     dword ptr [rbp+RootPathName], 0
0x18003212d  mov     rcx, r14
0x180032130  mov     rax, [rax+30h]
0x180032134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032139  test    eax, eax
0x18003213b  jnz     short loc_18003218F
0x18003213d  mov     rcx, [rbp+var_18]; unsigned __int16 *
0x180032141  lea     r8, [rbp+pv]; unsigned __int16 **
0x180032145  lea     edx, [rax+3]; unsigned int
0x180032148  mov     [rbp+pv], 0
0x180032150  call    ?GetLinkTarget@@YAJPEBGKPEAPEAGPEAK@Z; GetLinkTarget(ushort const *,ulong,ushort * *,ulong *)
0x180032155  test    eax, eax
0x180032157  js      short loc_18003218F
0x180032159  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18003215d  test    rcx, rcx
0x180032160  jz      short loc_18003218F
0x180032162  mov     rdx, rsi; unsigned __int16 **
0x180032165  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x18003216a  lea     rcx, [rbp+pv]; unsigned __int16 **
0x18003216e  mov     ebx, eax
0x180032170  call    ?LocalFreeString@@YAXPEAPEAG@Z; LocalFreeString(ushort * *)
0x180032175  jmp     short loc_18003218F
0x180032177  mov     rcx, [rbp+pv]; unsigned __int16 *
0x18003217b  mov     rdx, rsi; unsigned __int16 **
0x18003217e  call    ?CscUtil_CreateStringCopy@@YAJPEBGPEAPEAG@Z; CscUtil_CreateStringCopy(ushort const *,ushort * *)
0x180032183  mov     rcx, [rbp+pv]; pv
0x180032187  mov     ebx, eax
0x180032189  call    cs:__imp_CoTaskMemFree
0x18003218f  mov     rcx, [rbp+var_18]; pv
0x180032193  call    cs:__imp_CoTaskMemFree
0x180032199  mov     eax, ebx
0x18003219b  mov     rcx, [rbp+var_8]
0x18003219f  xor     rcx, rsp; StackCookie
0x1800321a2  call    __security_check_cookie
0x1800321a7  add     rsp, 40h
0x1800321ab  pop     r14
0x1800321ad  pop     rdi
0x1800321ae  pop     rsi
0x1800321af  pop     rbx
0x1800321b0  pop     rbp
0x1800321b1  retn
```
