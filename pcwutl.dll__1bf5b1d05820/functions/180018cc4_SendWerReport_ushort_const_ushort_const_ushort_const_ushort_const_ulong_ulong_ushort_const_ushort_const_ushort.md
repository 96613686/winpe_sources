# SendWerReport(ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *,ushort const *,ushort const * *,ulong)

- ea: `0x180018cc4`
- end: `0x180018f7d`
- name: `?SendWerReport@@YAJPEBG000KK00PEAPEBGK@Z`
- size: `697`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, unsigned int, unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009c00`

## callees

- `0x1800189a0`
- `0x180018cc4`
- `0x180018f84`
- `0x1800191a2`
- `0x1800191f0`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180018d1e`
- `SHLWAPI!PathFindFileNameW` at `0x180018d1e`

## pseudocode

```c
__int64 __fastcall SendWerReport(
        LPCWSTR pszPath,
        WCHAR *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        unsigned __int16 *a8,
        const unsigned __int16 **a9)
{
  unsigned __int16 *FileNameW; // r15
  unsigned int v12; // edx
  __int64 v13; // rdi
  WCHAR *wzApplicationPath; // r9
  __int64 v15; // rax
  LPCWSTR v16; // rcx
  __int64 v17; // r8
  WCHAR *v18; // rcx
  unsigned __int16 *v19; // r12
  __int64 v20; // rbx
  __int64 v21; // rax
  WCHAR *wzApplicationName; // r9
  unsigned __int16 *v23; // rcx
  __int64 v24; // r8
  WCHAR *v25; // rcx
  unsigned __int16 *v26; // r13
  BOOL VersionInformation; // eax
  unsigned __int16 *v28; // r9
  WCHAR *wzFriendlyEventName; // r8
  WCHAR *v30; // rcx
  unsigned __int16 *v32[7]; // [rsp+48h] [rbp-B8h] BYREF
  _WER_REPORT_INFORMATION pReportInformation; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v34[24]; // [rsp+920h] [rbp+820h] BYREF
  unsigned __int16 v35[256]; // [rsp+950h] [rbp+850h] BYREF
  unsigned __int16 v36[256]; // [rsp+B50h] [rbp+A50h] BYREF

  memset_0(&pReportInformation.dwSize + 1, 0, 0x89Cu);
  pReportInformation.dwSize = 2208;
  FileNameW = PathFindFileNameW(pszPath);
  if ( FileNameW )
  {
    v13 = 2147483646;
    wzApplicationPath = pReportInformation.wzApplicationPath;
    v15 = 2147483646;
    v16 = pszPath;
    v17 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v16 )
        break;
      *wzApplicationPath++ = *v16++;
      --v15;
      --v17;
    }
    while ( v17 );
    v18 = wzApplicationPath - 1;
    v12 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = wzApplicationPath;
    *v18 = 0;
    if ( v17 )
    {
      v19 = v34;
      v20 = 128;
      if ( !GetVersionInformation(3, pszPath, v34, 0x15u) )
        v19 = L"0.0.0.0";
      if ( GetVersionInformation(0, pszPath, pReportInformation.wzApplicationName, 0x80u) )
        goto LABEL_20;
      v21 = 2147483646;
      wzApplicationName = pReportInformation.wzApplicationName;
      v23 = FileNameW;
      v24 = 128;
      do
      {
        if ( !v21 )
          break;
        if ( !*v23 )
          break;
        *wzApplicationName++ = *v23++;
        --v21;
        --v24;
      }
      while ( v24 );
      v25 = wzApplicationName - 1;
      v12 = v24 == 0 ? 0x8007007A : 0;
      if ( v24 )
        v25 = wzApplicationName;
      *v25 = 0;
      if ( v24 )
      {
LABEL_20:
        v26 = v35;
        if ( !GetVersionInformation(2, pszPath, v35, 0x100u) )
          v26 = L"unknown";
        VersionInformation = GetVersionInformation(1, pszPath, v36, 0x100u);
        v28 = v36;
        if ( !VersionInformation )
          v28 = L"unknown";
        if ( !a2 )
          goto LABEL_32;
        wzFriendlyEventName = pReportInformation.wzFriendlyEventName;
        do
        {
          if ( !v13 )
            break;
          if ( !*a2 )
            break;
          *wzFriendlyEventName++ = *a2++;
          --v13;
          --v20;
        }
        while ( v20 );
        v30 = wzFriendlyEventName - 1;
        v12 = v20 == 0 ? 0x8007007A : 0;
        if ( v20 )
          v30 = wzFriendlyEventName;
        *v30 = 0;
        if ( v20 )
        {
LABEL_32:
          v32[2] = pReportInformation.wzApplicationName;
          v32[4] = v28;
          v32[5] = L"100";
          v32[6] = a8;
          v32[0] = FileNameW;
          v32[1] = v19;
          v32[3] = v26;
          return (unsigned int)SendWerReportInternal(
                                 &pReportInformation,
                                 L"PCA2",
                                 0,
                                 0,
                                 (const unsigned __int16 **)v32,
                                 7u,
                                 a9,
                                 2u);
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147418113;
  }
  return v12;
}

```

## disassembly

```asm
0x180018cc4  push    rbp
0x180018cc6  push    rbx
0x180018cc7  push    rsi
0x180018cc8  push    rdi
0x180018cc9  push    r12
0x180018ccb  push    r13
0x180018ccd  push    r14
0x180018ccf  push    r15
0x180018cd1  lea     rbp, [rsp-0C68h]
0x180018cd9  sub     rsp, 0D68h
0x180018ce0  mov     rax, cs:__security_cookie
0x180018ce7  xor     rax, rsp
0x180018cea  mov     [rbp+0CA0h+var_50], rax
0x180018cf1  mov     rax, [rbp+0CA0h+arg_40]
0x180018cf8  mov     r14, rdx
0x180018cfb  mov     rsi, rcx
0x180018cfe  mov     [rsp+0DA0h+var_D60], rax
0x180018d03  xor     edx, edx; Val
0x180018d05  lea     rcx, [rbp+0CA0h+pReportInformation+4]; void *
0x180018d09  mov     r8d, 89Ch; Size
0x180018d0f  call    memset_0
0x180018d14  mov     rcx, rsi; pszPath
0x180018d17  mov     [rbp+0CA0h+pReportInformation.dwSize], 8A0h
0x180018d1e  call    cs:__imp_PathFindFileNameW
0x180018d24  xor     r13d, r13d
0x180018d27  mov     r15, rax
0x180018d2a  test    rax, rax
0x180018d2d  jnz     short loc_180018D39
0x180018d2f  mov     edx, 8000FFFFh
0x180018d34  jmp     loc_180018F58
0x180018d39  mov     edi, 7FFFFFFEh
0x180018d3e  lea     r9, [rbp+0CA0h+pReportInformation.wzApplicationPath]
0x180018d45  mov     eax, edi
0x180018d47  mov     rcx, rsi
0x180018d4a  mov     r8d, 104h
0x180018d50  test    rax, rax
0x180018d53  jz      short loc_180018D72
0x180018d55  movzx   edx, word ptr [rcx]
0x180018d58  test    dx, dx
0x180018d5b  jz      short loc_180018D72
0x180018d5d  mov     [r9], dx
0x180018d61  add     rcx, 2
0x180018d65  add     r9, 2
0x180018d69  dec     rax
0x180018d6c  sub     r8, 1
0x180018d70  jnz     short loc_180018D50
0x180018d72  mov     rax, r8
0x180018d75  lea     rcx, [r9-2]
0x180018d79  neg     rax
0x180018d7c  sbb     edx, edx
0x180018d7e  not     edx
0x180018d80  and     edx, 8007007Ah
0x180018d86  test    r8, r8
0x180018d89  cmovnz  rcx, r9
0x180018d8d  mov     [rcx], r13w
0x180018d91  jz      loc_180018F58
0x180018d97  mov     r9d, 15h
0x180018d9d  lea     r8, [rbp+0CA0h+var_480]
0x180018da4  mov     rdx, rsi
0x180018da7  lea     ecx, [r9-12h]
0x180018dab  call    ?GetVersionInformation@@YAHW4VERSION_INFO_TYPE@@PEBGPEAGK@Z; GetVersionInformation(VERSION_INFO_TYPE,ushort const *,ushort *,ulong)
0x180018db0  lea     rcx, a0000; "0.0.0.0"
0x180018db7  test    eax, eax
0x180018db9  lea     r12, [rbp+0CA0h+var_480]
0x180018dc0  mov     ebx, 80h
0x180018dc5  cmovz   r12, rcx
0x180018dc9  lea     r8, [rbp+0CA0h+pReportInformation.wzApplicationName]
0x180018dd0  xor     ecx, ecx
0x180018dd2  mov     r9d, ebx
0x180018dd5  mov     rdx, rsi
0x180018dd8  call    ?GetVersionInformation@@YAHW4VERSION_INFO_TYPE@@PEBGPEAGK@Z; GetVersionInformation(VERSION_INFO_TYPE,ushort const *,ushort *,ulong)
0x180018ddd  test    eax, eax
0x180018ddf  jnz     short loc_180018E38
0x180018de1  mov     rax, rdi
0x180018de4  lea     r9, [rbp+0CA0h+pReportInformation.wzApplicationName]
0x180018deb  mov     rcx, r15
0x180018dee  mov     r8d, ebx
0x180018df1  test    rax, rax
0x180018df4  jz      short loc_180018E13
0x180018df6  movzx   edx, word ptr [rcx]
0x180018df9  test    dx, dx
0x180018dfc  jz      short loc_180018E13
0x180018dfe  mov     [r9], dx
0x180018e02  add     rcx, 2
0x180018e06  add     r9, 2
0x180018e0a  dec     rax
0x180018e0d  sub     r8, 1
0x180018e11  jnz     short loc_180018DF1
0x180018e13  mov     rax, r8
0x180018e16  lea     rcx, [r9-2]
0x180018e1a  neg     rax
0x180018e1d  sbb     edx, edx
0x180018e1f  not     edx
0x180018e21  and     edx, 8007007Ah
0x180018e27  test    r8, r8
0x180018e2a  cmovnz  rcx, r9
0x180018e2e  mov     [rcx], r13w
0x180018e32  jz      loc_180018F58
0x180018e38  mov     r9d, 100h
0x180018e3e  lea     r8, [rbp+0CA0h+var_450]
0x180018e45  mov     rdx, rsi
0x180018e48  mov     ecx, 2
0x180018e4d  call    ?GetVersionInformation@@YAHW4VERSION_INFO_TYPE@@PEBGPEAGK@Z; GetVersionInformation(VERSION_INFO_TYPE,ushort const *,ushort *,ulong)
0x180018e52  lea     rcx, aUnknown; "unknown"
0x180018e59  test    eax, eax
0x180018e5b  lea     r13, [rbp+0CA0h+var_450]
0x180018e62  mov     r9d, 100h
0x180018e68  cmovz   r13, rcx
0x180018e6c  lea     r8, [rbp+0CA0h+var_250]
0x180018e73  mov     ecx, 1
0x180018e78  mov     rdx, rsi
0x180018e7b  call    ?GetVersionInformation@@YAHW4VERSION_INFO_TYPE@@PEBGPEAGK@Z; GetVersionInformation(VERSION_INFO_TYPE,ushort const *,ushort *,ulong)
0x180018e80  xor     r10d, r10d
0x180018e83  lea     r9, [rbp+0CA0h+var_250]
0x180018e8a  test    eax, eax
0x180018e8c  lea     rax, aUnknown; "unknown"
0x180018e93  cmovz   r9, rax
0x180018e97  test    r14, r14
0x180018e9a  jz      short loc_180018EE4
0x180018e9c  lea     r8, [rbp+0CA0h+pReportInformation.wzFriendlyEventName]
0x180018ea0  test    rdi, rdi
0x180018ea3  jz      short loc_180018EC3
0x180018ea5  movzx   eax, word ptr [r14]
0x180018ea9  test    ax, ax
0x180018eac  jz      short loc_180018EC3
0x180018eae  mov     [r8], ax
0x180018eb2  add     r14, 2
0x180018eb6  add     r8, 2
0x180018eba  dec     rdi
0x180018ebd  sub     rbx, 1
0x180018ec1  jnz     short loc_180018EA0
0x180018ec3  mov     rax, rbx
0x180018ec6  lea     rcx, [r8-2]
0x180018eca  neg     rax
0x180018ecd  sbb     edx, edx
0x180018ecf  not     edx
0x180018ed1  and     edx, 8007007Ah
0x180018ed7  test    rbx, rbx
0x180018eda  cmovnz  rcx, r8
0x180018ede  mov     [rcx], r10w
0x180018ee2  jz      short loc_180018F58
0x180018ee4  mov     [rsp+0DA0h+var_D68], 2; unsigned int
0x180018eec  lea     rax, [rbp+0CA0h+pReportInformation.wzApplicationName]
0x180018ef3  mov     [rsp+0DA0h+var_D48], rax
0x180018ef8  lea     rdx, pwzEventType; "PCA2"
0x180018eff  lea     rax, a100; "100"
0x180018f06  mov     [rsp+0DA0h+var_D38], r9
0x180018f0b  mov     [rsp+0DA0h+var_D30], rax
0x180018f10  lea     rcx, [rbp+0CA0h+pReportInformation]; pReportInformation
0x180018f14  mov     rax, [rbp+0CA0h+arg_38]
0x180018f1b  xor     r9d, r9d; unsigned int
0x180018f1e  mov     [rsp+0DA0h+var_D28], rax
0x180018f23  xor     r8d, r8d; dwFlags
0x180018f26  mov     rax, [rsp+0DA0h+var_D60]
0x180018f2b  mov     [rsp+0DA0h+var_D70], rax; unsigned __int16 **
0x180018f30  lea     rax, [rsp+0DA0h+var_D58]
0x180018f35  mov     [rsp+0DA0h+var_D78], 7; unsigned int
0x180018f3d  mov     [rsp+0DA0h+var_D80], rax; unsigned __int16 **
0x180018f42  mov     [rsp+0DA0h+var_D58], r15
0x180018f47  mov     [rsp+0DA0h+var_D50], r12
0x180018f4c  mov     [rsp+0DA0h+var_D40], r13
0x180018f51  call    ?SendWerReportInternal@@YAJPEAU_WER_REPORT_INFORMATION@@PEBGKKPEAPEBGK2K@Z; SendWerReportInternal(_WER_REPORT_INFORMATION *,ushort const *,ulong,ulong,ushort const * *,ulong,ushort const * *,ulong)
0x180018f56  mov     edx, eax
0x180018f58  mov     eax, edx
0x180018f5a  mov     rcx, [rbp+0CA0h+var_50]
0x180018f61  xor     rcx, rsp; StackCookie
0x180018f64  call    __security_check_cookie
0x180018f69  add     rsp, 0D68h
0x180018f70  pop     r15
0x180018f72  pop     r14
0x180018f74  pop     r13
0x180018f76  pop     r12
0x180018f78  pop     rdi
0x180018f79  pop     rsi
0x180018f7a  pop     rbx
0x180018f7b  pop     rbp
0x180018f7c  retn
```
