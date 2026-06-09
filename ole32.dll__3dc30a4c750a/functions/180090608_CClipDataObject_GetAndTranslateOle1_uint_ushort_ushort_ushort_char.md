# CClipDataObject::GetAndTranslateOle1(uint,ushort * *,ushort * *,ushort * *,char * *)

- ea: `0x180090608`
- end: `0x1800907b6`
- name: `?GetAndTranslateOle1@CClipDataObject@@AEAAJIPEAPEAG00PEAPEAD@Z`
- size: `430`
- prototype: `HRESULT __fastcall(CClipDataObject *this, unsigned int cf, wchar_t **ppszClass, wchar_t **ppszFile, wchar_t **ppszItem, char **ppszItemA)`
- caller_count: `4`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800908d4`
- `0x180090c04`
- `0x180090fa4`
- `0x180091294`

## callees

- `0x18001ac2c`
- `0x180090608`
- `0x1800a5688`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180090757`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180090757`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009065f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18009065f`
- `USER32!GetClipboardData` at `0x180090644`
- `USER32!GetClipboardData` at `0x180090644`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009076e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009079a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009076e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180090784`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009079a`

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
  HANDLE ClipboardData; // rax
  void *v10; // r13
  unsigned int UNICODEData; // ebx
  char *v12; // rax
  char *v13; // rbp
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rbp
  __int64 v18; // rcx
  __int64 v19; // rax
  char *v20; // rbp
  __int64 v21; // rcx
  char *v22; // rax
  int v23; // ecx

  v6 = 0;
  if ( ppszClass )
    *ppszClass = 0;
  if ( ppszFile )
    *ppszFile = 0;
  if ( ppszItem )
    *ppszItem = 0;
  ClipboardData = GetClipboardData(cf);
  v10 = ClipboardData;
  if ( ClipboardData )
  {
    v12 = (char *)GlobalLock(ClipboardData);
    v13 = v12;
    if ( v12 )
    {
      v14 = -1;
      UNICODEData = 0;
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
      GlobalUnlock(v10);
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
0x180090608  push    rbx
0x18009060a  push    rbp
0x18009060b  push    rsi
0x18009060c  push    rdi
0x18009060d  push    r12
0x18009060f  push    r13
0x180090611  push    r14
0x180090613  push    r15
0x180090615  sub     rsp, 28h
0x180090619  xor     r12d, r12d
0x18009061c  mov     r14, ppszFile
0x18009061f  mov     r15, ppszClass
0x180090622  test    ppszClass, ppszClass
0x180090625  jz      short loc_18009062A
0x180090627  mov     [ppszClass], r12
0x18009062a  test    r14, r14
0x18009062d  jz      short loc_180090632
0x18009062f  mov     [ppszFile], r12
0x180090632  mov     rsi, [rsp+68h+pstr]
0x18009063a  test    rsi, rsi
0x18009063d  jz      short loc_180090642
0x18009063f  mov     [rsi], r12
0x180090642  mov     ecx, edx; uFormat
0x180090644  call    cs:__imp_GetClipboardData
0x18009064a  mov     r13, rax
0x18009064d  test    rax, rax
0x180090650  jnz     short loc_18009065C
0x180090652  mov     ebx, 800401D3h
0x180090657  jmp     $logRtn_7
0x18009065c  mov     rcx, r13; hMem
0x18009065f  call    cs:__imp_GlobalLock
0x180090665  mov     rbp, rax
0x180090668  test    rax, rax
0x18009066b  jnz     short loc_180090677
0x18009066d  mov     ebx, 8007000Eh
0x180090672  jmp     $logRtn_7
0x180090677  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009067b  mov     ebx, r12d
0x18009067e  test    r15, r15
0x180090681  jz      short loc_1800906A9
0x180090683  mov     rcx, rdi
0x180090686  inc     rcx
0x180090689  cmp     [rcx+rax], r12b
0x18009068d  jnz     short loc_180090686
0x18009068f  inc     ecx; ulLength
0x180090691  mov     ppszFile, r15; pstr
0x180090694  xor     r8d, r8d; szOLESTR
0x180090697  mov     rdx, rbp; szANSI
0x18009069a  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x18009069f  mov     ebx, eax
0x1800906a1  test    eax, eax
0x1800906a3  jnz     $errRtn_127
0x1800906a9  mov     rax, rdi
0x1800906ac  inc     rax
0x1800906af  cmp     [rax+rbp], r12b
0x1800906b3  jnz     short loc_1800906AC
0x1800906b5  inc     rbp
0x1800906b8  add     rbp, rax
0x1800906bb  test    r14, r14
0x1800906be  jz      short loc_1800906E2
0x1800906c0  mov     rcx, rdi
0x1800906c3  inc     rcx
0x1800906c6  cmp     [rcx+rbp], r12b
0x1800906ca  jnz     short loc_1800906C3
0x1800906cc  inc     ecx; ulLength
0x1800906ce  mov     ppszFile, r14; pstr
0x1800906d1  xor     r8d, r8d; szOLESTR
0x1800906d4  mov     rdx, rbp; szANSI
0x1800906d7  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x1800906dc  mov     ebx, eax
0x1800906de  test    eax, eax
0x1800906e0  jnz     short $errRtn_127
0x1800906e2  mov     rax, rdi
0x1800906e5  inc     rax
0x1800906e8  cmp     [rax+rbp], r12b
0x1800906ec  jnz     short loc_1800906E5
0x1800906ee  add     rbp, rax
0x1800906f1  test    rsi, rsi
0x1800906f4  jz      short loc_18009071A
0x1800906f6  mov     rcx, rdi
0x1800906f9  inc     rcx
0x1800906fc  cmp     [rcx+rbp+1], r12b
0x180090701  jnz     short loc_1800906F9
0x180090703  inc     ecx; ulLength
0x180090705  lea     rdx, [rbp+1]; szANSI
0x180090709  mov     ppszFile, rsi; pstr
0x18009070c  xor     r8d, r8d; szOLESTR
0x18009070f  call    ?UtGetUNICODEData@@YAJKPEADPEAGPEAPEAG@Z; UtGetUNICODEData(ulong,char *,ushort *,ushort * *)
0x180090714  mov     ebx, eax
0x180090716  test    eax, eax
0x180090718  jnz     short $errRtn_127
0x18009071a  mov     r12, [rsp+68h+arg_28]
0x180090722  test    r12, r12
0x180090725  jz      short $errRtn_127
0x180090727  inc     rdi
0x18009072a  cmp     byte ptr [rdi+rbp+1], 0
0x18009072f  jnz     short loc_180090727
0x180090731  lea     rdx, [rdi+1]; size
0x180090735  lea     rcx, [rbp+1]; lpvIn
0x180090739  call    ?UtDupPtr@@YAPEAXPEAX_K@Z; UtDupPtr(void *,unsigned __int64)
0x18009073e  mov     ecx, ebx
0x180090740  mov     [r12], rax
0x180090744  mov     ebx, 8007000Eh
0x180090749  xor     r12d, r12d
0x18009074c  test    rax, rax
0x18009074f  cmovz   ecx, ebx
0x180090752  mov     ebx, ecx
0x180090754  mov     rcx, r13; hMem
0x180090757  call    cs:__imp_GlobalUnlock
0x18009075d  test    ebx, ebx
0x18009075f  jz      short $logRtn_7
0x180090761  test    r15, r15
0x180090764  jz      short loc_180090777
0x180090766  mov     rcx, [r15]; pv
0x180090769  test    rcx, rcx
0x18009076c  jz      short loc_180090777
0x18009076e  call    cs:__imp_CoTaskMemFree
0x180090774  mov     [r15], r12
0x180090777  test    r14, r14
0x18009077a  jz      short loc_18009078D
0x18009077c  mov     rcx, [r14]; pv
0x18009077f  test    rcx, rcx
0x180090782  jz      short loc_18009078D
0x180090784  call    cs:__imp_CoTaskMemFree
0x18009078a  mov     [r14], r12
0x18009078d  test    rsi, rsi
0x180090790  jz      short $logRtn_7
0x180090792  mov     rcx, [rsi]; pv
0x180090795  test    rcx, rcx
0x180090798  jz      short $logRtn_7
0x18009079a  call    cs:__imp_CoTaskMemFree
0x1800907a0  mov     [rsi], r12
0x1800907a3  mov     eax, ebx
0x1800907a5  add     rsp, 28h
0x1800907a9  pop     r15
0x1800907ab  pop     r14
0x1800907ad  pop     r13
0x1800907af  pop     r12
0x1800907b1  pop     rdi
0x1800907b2  pop     rsi
0x1800907b3  pop     rbp
0x1800907b4  pop     rbx
0x1800907b5  retn
```
