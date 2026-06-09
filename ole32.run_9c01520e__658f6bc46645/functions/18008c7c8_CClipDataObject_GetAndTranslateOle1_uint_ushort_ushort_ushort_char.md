# CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)

- ea: `0x18008c7c8`
- end: `0x18008c9ac`
- name: `?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z`
- size: `484`
- prototype: `HRESULT __fastcall(CClipDataObject *this, unsigned int cf, wchar_t **ppszClass, wchar_t **ppszFile, wchar_t **ppszItem, char **ppszItemA)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18008cad4`
- `0x18008ce60`
- `0x18008d260`
- `0x18008d58c`

## callees

- `0x18000e9c8`
- `0x18008c7c8`
- `0x1800ac480`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008c928`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18008c928`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008c830`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18008c830`
- `USER32!GetClipboardData` at `0x18008c80f`
- `USER32!GetClipboardData` at `0x18008c80f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c97d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c945`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c961`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008c97d`

## pseudocode

```c
__int64 __fastcall CClipDataObject::GetAndTranslateOle1(
        CClipDataObject *this,
        UINT cf,
        wchar_t **ppszClass,
        wchar_t **ppszFile,
        wchar_t **ppszItem,
        char **ppszItemA)
{
  wchar_t *v6; // r12
  unsigned int UNICODEData; // ebx
  HANDLE ClipboardData; // rax
  void *v11; // r13
  char *v12; // rax
  char *v13; // rbp
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  char *v17; // rbp
  __int64 v18; // rcx
  __int64 v19; // rax
  char *v20; // rbp
  __int64 v21; // rcx
  char *v22; // rax
  int v23; // ecx

  v6 = 0;
  UNICODEData = 0;
  if ( ppszClass )
    *ppszClass = 0;
  if ( ppszFile )
    *ppszFile = 0;
  if ( ppszItem )
    *ppszItem = 0;
  ClipboardData = GetClipboardData(cf);
  v11 = ClipboardData;
  if ( ClipboardData )
  {
    v12 = (char *)GlobalLock(ClipboardData);
    v13 = v12;
    if ( v12 )
    {
      v14 = -1;
      if ( !ppszClass )
        goto LABEL_45;
      v15 = -1;
      do
        ++v15;
      while ( v12[v15] );
      UNICODEData = UtGetUNICODEData(v15 + 1, v12, 0, ppszClass);
      if ( !UNICODEData )
      {
LABEL_45:
        v16 = -1;
        do
          ++v16;
        while ( v13[v16] );
        v17 = &v13[v16 + 1];
        if ( !ppszFile )
          goto LABEL_46;
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        UNICODEData = UtGetUNICODEData(v18 + 1, v17, 0, ppszFile);
        if ( !UNICODEData )
        {
LABEL_46:
          v19 = -1;
          do
            ++v19;
          while ( v17[v19] );
          v20 = &v17[v19];
          if ( !ppszItem )
            goto LABEL_27;
          v21 = -1;
          do
            ++v21;
          while ( v20[v21 + 1] );
          UNICODEData = UtGetUNICODEData(v21 + 1, v20 + 1, 0, ppszItem);
          if ( !UNICODEData )
          {
LABEL_27:
            v6 = (wchar_t *)ppszItemA;
            if ( ppszItemA )
            {
              do
                ++v14;
              while ( v20[v14 + 1] );
              v22 = (char *)UtDupPtr(v20 + 1, v14 + 1);
              v23 = UNICODEData;
              *ppszItemA = v22;
              v6 = 0;
              if ( !v22 )
                v23 = -2147024882;
              UNICODEData = v23;
            }
          }
        }
      }
      GlobalUnlock(v11);
      if ( UNICODEData )
      {
        if ( ppszClass && *ppszClass )
        {
          CoTaskMemFree(*ppszClass);
          *ppszClass = v6;
        }
        if ( ppszFile && *ppszFile )
        {
          CoTaskMemFree(*ppszFile);
          *ppszFile = v6;
        }
        if ( ppszItem && *ppszItem )
        {
          CoTaskMemFree(*ppszItem);
          *ppszItem = v6;
        }
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147221037;
  }
  return UNICODEData;
}

```

## disassembly

```asm
0x18008c7c8  mov     [rsp+arg_0], rbx
0x18008c7cd  mov     [rsp+arg_8], rbp
0x18008c7d2  mov     [rsp+arg_10], rsi
0x18008c7d7  push    rdi
0x18008c7d8  push    r12
0x18008c7da  push    r13
0x18008c7dc  push    r14
0x18008c7de  push    r15
0x18008c7e0  sub     rsp, 20h
0x18008c7e4  xor     r12d, r12d
0x18008c7e7  mov     r14, ppszFile
0x18008c7ea  mov     r15, ppszClass
0x18008c7ed  mov     ebx, r12d
0x18008c7f0  test    ppszClass, ppszClass
0x18008c7f3  jz      short loc_18008C7F8
0x18008c7f5  mov     [ppszClass], r12
0x18008c7f8  test    r14, r14
0x18008c7fb  jz      short loc_18008C800
0x18008c7fd  mov     [ppszFile], r12
0x18008c800  mov     rsi, [rsp+48h+pstr]
0x18008c805  test    rsi, rsi
0x18008c808  jz      short loc_18008C80D
0x18008c80a  mov     [rsi], r12
0x18008c80d  mov     ecx, edx; uFormat
0x18008c80f  call    cs:__imp_GetClipboardData
0x18008c816  nop     dword ptr [rax+rax+00h]
0x18008c81b  mov     r13, rax
0x18008c81e  test    rax, rax
0x18008c821  jnz     short loc_18008C82D
0x18008c823  mov     ebx, 800401D3h
0x18008c828  jmp     $logRtn_5
0x18008c82d  mov     rcx, r13; hMem
0x18008c830  call    cs:__imp_GlobalLock
0x18008c837  nop     dword ptr [rax+rax+00h]
0x18008c83c  mov     rbp, rax
0x18008c83f  test    rax, rax
0x18008c842  jnz     short loc_18008C84E
0x18008c844  mov     ebx, 8007000Eh
0x18008c849  jmp     $logRtn_5
0x18008c84e  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008c852  test    r15, r15
0x18008c855  jz      short loc_18008C87D
0x18008c857  mov     rcx, rdi
0x18008c85a  inc     rcx
0x18008c85d  cmp     [rcx+rax], r12b
0x18008c861  jnz     short loc_18008C85A
0x18008c863  inc     ecx; ulLength
0x18008c865  mov     ppszFile, r15; pstr
0x18008c868  xor     r8d, r8d; szOLESTR
0x18008c86b  mov     rdx, rbp; szANSI
0x18008c86e  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x18008c873  mov     ebx, eax
0x18008c875  test    eax, eax
0x18008c877  jnz     $errRtn_100
0x18008c87d  mov     rcx, rdi
0x18008c880  inc     rcx
0x18008c883  cmp     [rcx+rbp], r12b
0x18008c887  jnz     short loc_18008C880
0x18008c889  inc     rbp
0x18008c88c  add     rbp, rcx
0x18008c88f  test    r14, r14
0x18008c892  jz      short loc_18008C8B6
0x18008c894  mov     rcx, rdi
0x18008c897  inc     rcx
0x18008c89a  cmp     [rcx+rbp], r12b
0x18008c89e  jnz     short loc_18008C897
0x18008c8a0  inc     ecx; ulLength
0x18008c8a2  mov     ppszFile, r14; pstr
0x18008c8a5  xor     r8d, r8d; szOLESTR
0x18008c8a8  mov     rdx, rbp; szANSI
0x18008c8ab  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x18008c8b0  mov     ebx, eax
0x18008c8b2  test    eax, eax
0x18008c8b4  jnz     short $errRtn_100
0x18008c8b6  mov     rax, rdi
0x18008c8b9  inc     rax
0x18008c8bc  cmp     [rax+rbp], r12b
0x18008c8c0  jnz     short loc_18008C8B9
0x18008c8c2  add     rbp, rax
0x18008c8c5  test    rsi, rsi
0x18008c8c8  jz      short loc_18008C8EE
0x18008c8ca  mov     rcx, rdi
0x18008c8cd  inc     rcx
0x18008c8d0  cmp     [rcx+rbp+1], r12b
0x18008c8d5  jnz     short loc_18008C8CD
0x18008c8d7  inc     ecx; ulLength
0x18008c8d9  lea     rdx, [rbp+1]; szANSI
0x18008c8dd  mov     ppszFile, rsi; pstr
0x18008c8e0  xor     r8d, r8d; szOLESTR
0x18008c8e3  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x18008c8e8  mov     ebx, eax
0x18008c8ea  test    eax, eax
0x18008c8ec  jnz     short $errRtn_100
0x18008c8ee  mov     r12, [rsp+48h+arg_28]
0x18008c8f3  test    r12, r12
0x18008c8f6  jz      short $errRtn_100
0x18008c8f8  inc     rdi
0x18008c8fb  cmp     byte ptr [rdi+rbp+1], 0
0x18008c900  jnz     short loc_18008C8F8
0x18008c902  lea     rdx, [rdi+1]; size
0x18008c906  lea     rcx, [rbp+1]; lpvIn
0x18008c90a  call    ?UtDupPtr@@YAPEAXPEAX_K@Z; UtDupPtr(void *,unsigned __int64)
0x18008c90f  mov     ecx, ebx
0x18008c911  mov     [r12], rax
0x18008c915  mov     ebx, 8007000Eh
0x18008c91a  xor     r12d, r12d
0x18008c91d  test    rax, rax
0x18008c920  cmovz   ecx, ebx
0x18008c923  mov     ebx, ecx
0x18008c925  mov     rcx, r13; hMem
0x18008c928  call    cs:__imp_GlobalUnlock
0x18008c92f  nop     dword ptr [rax+rax+00h]
0x18008c934  test    ebx, ebx
0x18008c936  jz      short $logRtn_5
0x18008c938  test    r15, r15
0x18008c93b  jz      short loc_18008C954
0x18008c93d  mov     rcx, [r15]; pv
0x18008c940  test    rcx, rcx
0x18008c943  jz      short loc_18008C954
0x18008c945  call    cs:__imp_CoTaskMemFree
0x18008c94c  nop     dword ptr [rax+rax+00h]
0x18008c951  mov     [r15], r12
0x18008c954  test    r14, r14
0x18008c957  jz      short loc_18008C970
0x18008c959  mov     rcx, [r14]; pv
0x18008c95c  test    rcx, rcx
0x18008c95f  jz      short loc_18008C970
0x18008c961  call    cs:__imp_CoTaskMemFree
0x18008c968  nop     dword ptr [rax+rax+00h]
0x18008c96d  mov     [r14], r12
0x18008c970  test    rsi, rsi
0x18008c973  jz      short $logRtn_5
0x18008c975  mov     rcx, [rsi]; pv
0x18008c978  test    rcx, rcx
0x18008c97b  jz      short $logRtn_5
0x18008c97d  call    cs:__imp_CoTaskMemFree
0x18008c984  nop     dword ptr [rax+rax+00h]
0x18008c989  mov     [rsi], r12
0x18008c98c  mov     rbp, [rsp+48h+arg_8]
0x18008c991  mov     eax, ebx
0x18008c993  mov     rbx, [rsp+48h+arg_0]
0x18008c998  mov     rsi, [rsp+48h+arg_10]
0x18008c99d  add     rsp, 20h
0x18008c9a1  pop     r15
0x18008c9a3  pop     r14
0x18008c9a5  pop     r13
0x18008c9a7  pop     r12
0x18008c9a9  pop     rdi
0x18008c9aa  retn
```
