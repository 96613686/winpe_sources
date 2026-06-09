# CSiteModeInfo::_CreateStreamFromProperties(long,ushort const *,ushort const *,ushort const *,ushort const *,long,long,SITEMODE_TASKS *,tagTILE_META_CONTENT *,ulong,IStream * *)

- ea: `0x1800fcc6c`
- end: `0x1800fcf59`
- name: `?_CreateStreamFromProperties@CSiteModeInfo@@CAJJPEBG000JJPEAUSITEMODE_TASKS@@PEAUtagTILE_META_CONTENT@@KPEAPEAUIStream@@@Z`
- size: `749`
- prototype: `static int(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, struct SITEMODE_TASKS *, struct tagTILE_META_CONTENT *, unsigned int, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800fb450`

## callees

- `0x180005030`
- `0x180099c70`
- `0x1800fba70`
- `0x1800fcc6c`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800fcca7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800fcca7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fccf4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd10`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd2c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd49`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fce73`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fce91`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fceaf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fccf4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd10`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd2c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fcd49`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fce73`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fce91`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800fceaf`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fccd8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcd6e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcd8e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcdb1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcde1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fce15`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fce3f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fced4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcef6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fccd8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcd6e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcd8e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcdb1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcde1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fce15`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fce3f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fced4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800fcef6`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800fcf1e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800fcf1e`

## pseudocode

```c
__int64 __fastcall CSiteModeInfo::_CreateStreamFromProperties(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *psz,
        int a6,
        int a7,
        struct SITEMODE_TASKS *a8,
        struct tagTILE_META_CONTENT *a9,
        unsigned int a10,
        struct IStream **a11)
{
  struct IStream **v11; // r13
  HRESULT v15; // ebx
  IStream *v16; // rax
  IStream *v17; // rdi
  struct tagTILE_META_CONTENT *v18; // rsi
  struct SITEMODE_TASKS *v19; // r14
  _DWORD *v20; // r12
  unsigned int v21; // esi
  __int64 v22; // r15
  bool v24[8]; // [rsp+20h] [rbp-18h] BYREF
  IStream *pstm[2]; // [rsp+28h] [rbp-10h] BYREF
  int pv; // [rsp+80h] [rbp+48h] BYREF

  pv = a1;
  v11 = a11;
  pstm[0] = 0;
  *a11 = 0;
  v15 = -2147024882;
  v16 = SHCreateMemStream(0, 0);
  ATL::CComPtrBase<IProtectionUtil>::Attach(pstm, v16);
  v17 = pstm[0];
  if ( pstm[0] )
  {
    v15 = IStream_Write(pstm[0], &pv, 4u);
    if ( v15 >= 0 )
    {
      v15 = IStream_WriteStr(v17, a2);
      if ( v15 >= 0 )
      {
        v15 = IStream_WriteStr(v17, a3);
        if ( v15 >= 0 )
        {
          v15 = IStream_WriteStr(v17, a4);
          if ( v15 >= 0 )
          {
            v15 = IStream_WriteStr(v17, psz);
            if ( v15 >= 0 )
            {
              v15 = IStream_Write(v17, &a6, 4u);
              if ( v15 >= 0 )
              {
                v15 = IStream_Write(v17, &a7, 4u);
                if ( v15 >= 0 )
                {
                  v15 = IStream_Write(v17, &a10, 4u);
                  if ( v15 >= 0 )
                  {
                    v18 = a9;
                    v24[0] = a9 != 0;
                    v15 = IStream_Write(v17, v24, 1u);
                    if ( v24[0] )
                      CSiteModeInfo::SetTileMetaToStream(v18, v17);
                    if ( v15 >= 0 )
                    {
                      v15 = IStream_Write(v17, &qword_1806196A8, 4u);
                      if ( v15 >= 0 )
                      {
                        v19 = a8;
                        v20 = (_DWORD *)((char *)a8 + 4);
                        v15 = IStream_Write(v17, (char *)a8 + 4, 4u);
                        if ( v15 >= 0 )
                        {
                          v21 = 0;
                          if ( *v20 )
                          {
                            while ( 1 )
                            {
                              v22 = 32LL * v21;
                              v15 = IStream_WriteStr(v17, *(PCWSTR *)((char *)v19 + v22 + 8));
                              if ( v15 < 0 )
                                break;
                              v15 = IStream_WriteStr(v17, *(PCWSTR *)((char *)v19 + v22 + 16));
                              if ( v15 < 0 )
                                break;
                              v15 = IStream_WriteStr(v17, *(PCWSTR *)((char *)v19 + v22 + 24));
                              if ( v15 < 0 )
                                break;
                              v15 = IStream_Write(v17, (char *)v19 + v21 + 168, 1u);
                              if ( v15 < 0 )
                                break;
                              v15 = IStream_Write(v17, (char *)v19 + v22 + 32, 4u);
                              if ( v15 < 0 )
                                break;
                              if ( ++v21 >= *v20 )
                              {
                                v11 = a11;
                                goto LABEL_23;
                              }
                            }
                          }
                          else
                          {
LABEL_23:
                            v15 = IStream_Reset(v17);
                            if ( v15 >= 0 )
                            {
                              pstm[0] = 0;
                              *v11 = v17;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(pstm);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800fcc6c  mov     [rsp-40h+pv], ecx
0x1800fcc70  push    rbp
0x1800fcc71  push    rbx
0x1800fcc72  push    rsi
0x1800fcc73  push    rdi
0x1800fcc74  push    r12
0x1800fcc76  push    r13
0x1800fcc78  push    r14
0x1800fcc7a  push    r15
0x1800fcc7c  mov     rbp, rsp
0x1800fcc7f  sub     rsp, 38h
0x1800fcc83  mov     r13, [rbp+arg_50]
0x1800fcc8a  mov     rsi, rdx
0x1800fcc8d  xor     r12d, r12d
0x1800fcc90  xor     edx, edx; cbInit
0x1800fcc92  xor     ecx, ecx; pInit
0x1800fcc94  mov     [rbp+pstm], r12
0x1800fcc98  mov     r15, r9
0x1800fcc9b  mov     r14, r8
0x1800fcc9e  mov     [r13+0], r12
0x1800fcca2  mov     ebx, 8007000Eh
0x1800fcca7  call    cs:__imp_SHCreateMemStream
0x1800fccae  nop     dword ptr [rax+rax+00h]
0x1800fccb3  mov     rdx, rax
0x1800fccb6  lea     rcx, [rbp+pstm]
0x1800fccba  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x1800fccbf  mov     rdi, [rbp+pstm]
0x1800fccc3  test    rdi, rdi
0x1800fccc6  jz      loc_1800FCF3C
0x1800fcccc  lea     r8d, [r12+4]; cb
0x1800fccd1  mov     rcx, rdi; pstm
0x1800fccd4  lea     rdx, [rbp+pv]; pv
0x1800fccd8  call    cs:__imp_IStream_Write
0x1800fccdf  nop     dword ptr [rax+rax+00h]
0x1800fcce4  mov     ebx, eax
0x1800fcce6  test    eax, eax
0x1800fcce8  js      loc_1800FCF3C
0x1800fccee  mov     rdx, rsi; psz
0x1800fccf1  mov     rcx, rdi; pstm
0x1800fccf4  call    cs:__imp_IStream_WriteStr
0x1800fccfb  nop     dword ptr [rax+rax+00h]
0x1800fcd00  mov     ebx, eax
0x1800fcd02  test    eax, eax
0x1800fcd04  js      loc_1800FCF3C
0x1800fcd0a  mov     rdx, r14; psz
0x1800fcd0d  mov     rcx, rdi; pstm
0x1800fcd10  call    cs:__imp_IStream_WriteStr
0x1800fcd17  nop     dword ptr [rax+rax+00h]
0x1800fcd1c  mov     ebx, eax
0x1800fcd1e  test    eax, eax
0x1800fcd20  js      loc_1800FCF3C
0x1800fcd26  mov     rdx, r15; psz
0x1800fcd29  mov     rcx, rdi; pstm
0x1800fcd2c  call    cs:__imp_IStream_WriteStr
0x1800fcd33  nop     dword ptr [rax+rax+00h]
0x1800fcd38  mov     ebx, eax
0x1800fcd3a  test    eax, eax
0x1800fcd3c  js      loc_1800FCF3C
0x1800fcd42  mov     rdx, [rbp+psz]; psz
0x1800fcd46  mov     rcx, rdi; pstm
0x1800fcd49  call    cs:__imp_IStream_WriteStr
0x1800fcd50  nop     dword ptr [rax+rax+00h]
0x1800fcd55  mov     ebx, eax
0x1800fcd57  test    eax, eax
0x1800fcd59  js      loc_1800FCF3C
0x1800fcd5f  lea     r15d, [r12+4]
0x1800fcd64  mov     rcx, rdi; pstm
0x1800fcd67  mov     r8d, r15d; cb
0x1800fcd6a  lea     rdx, [rbp+arg_28]; pv
0x1800fcd6e  call    cs:__imp_IStream_Write
0x1800fcd75  nop     dword ptr [rax+rax+00h]
0x1800fcd7a  mov     ebx, eax
0x1800fcd7c  test    eax, eax
0x1800fcd7e  js      loc_1800FCF3C
0x1800fcd84  mov     r8d, r15d; cb
0x1800fcd87  lea     rdx, [rbp+arg_30]; pv
0x1800fcd8b  mov     rcx, rdi; pstm
0x1800fcd8e  call    cs:__imp_IStream_Write
0x1800fcd95  nop     dword ptr [rax+rax+00h]
0x1800fcd9a  mov     ebx, eax
0x1800fcd9c  test    eax, eax
0x1800fcd9e  js      loc_1800FCF3C
0x1800fcda4  mov     r8d, r15d; cb
0x1800fcda7  lea     rdx, [rbp+arg_48]; pv
0x1800fcdae  mov     rcx, rdi; pstm
0x1800fcdb1  call    cs:__imp_IStream_Write
0x1800fcdb8  nop     dword ptr [rax+rax+00h]
0x1800fcdbd  mov     ebx, eax
0x1800fcdbf  test    eax, eax
0x1800fcdc1  js      loc_1800FCF3C
0x1800fcdc7  mov     rsi, [rbp+arg_40]
0x1800fcdce  lea     r8d, [r12+1]; cb
0x1800fcdd3  test    rsi, rsi
0x1800fcdd6  lea     rdx, [rbp+var_18]; pv
0x1800fcdda  mov     rcx, rdi; pstm
0x1800fcddd  setnz   [rbp+var_18]
0x1800fcde1  call    cs:__imp_IStream_Write
0x1800fcde8  nop     dword ptr [rax+rax+00h]
0x1800fcded  mov     ebx, eax
0x1800fcdef  cmp     [rbp+var_18], r12b
0x1800fcdf3  jz      short loc_1800FCE00
0x1800fcdf5  mov     rdx, rdi; struct IStream *
0x1800fcdf8  mov     rcx, rsi; struct tagTILE_META_CONTENT *
0x1800fcdfb  call    ?SetTileMetaToStream@CSiteModeInfo@@SAJPEAUtagTILE_META_CONTENT@@PEAUIStream@@@Z; CSiteModeInfo::SetTileMetaToStream(tagTILE_META_CONTENT *,IStream *)
0x1800fce00  test    ebx, ebx
0x1800fce02  js      loc_1800FCF3C
0x1800fce08  mov     r8d, r15d; cb
0x1800fce0b  lea     rdx, qword_1806196A8; pv
0x1800fce12  mov     rcx, rdi; pstm
0x1800fce15  call    cs:__imp_IStream_Write
0x1800fce1c  nop     dword ptr [rax+rax+00h]
0x1800fce21  mov     ebx, eax
0x1800fce23  test    eax, eax
0x1800fce25  js      loc_1800FCF3C
0x1800fce2b  mov     r14, [rbp+arg_38]
0x1800fce32  mov     r8d, r15d; cb
0x1800fce35  mov     rcx, rdi; pstm
0x1800fce38  lea     r12, [r14+4]
0x1800fce3c  mov     rdx, r12; pv
0x1800fce3f  call    cs:__imp_IStream_Write
0x1800fce46  nop     dword ptr [rax+rax+00h]
0x1800fce4b  mov     ebx, eax
0x1800fce4d  test    eax, eax
0x1800fce4f  js      loc_1800FCF3C
0x1800fce55  xor     esi, esi
0x1800fce57  cmp     [r12], esi
0x1800fce5b  jbe     loc_1800FCF1B
0x1800fce61  mov     r15d, esi
0x1800fce64  mov     rcx, rdi; pstm
0x1800fce67  shl     r15, 5
0x1800fce6b  mov     r13d, esi
0x1800fce6e  mov     rdx, [r15+r14+8]; psz
0x1800fce73  call    cs:__imp_IStream_WriteStr
0x1800fce7a  nop     dword ptr [rax+rax+00h]
0x1800fce7f  mov     ebx, eax
0x1800fce81  test    eax, eax
0x1800fce83  js      loc_1800FCF3C
0x1800fce89  mov     rdx, [r15+r14+10h]; psz
0x1800fce8e  mov     rcx, rdi; pstm
0x1800fce91  call    cs:__imp_IStream_WriteStr
0x1800fce98  nop     dword ptr [rax+rax+00h]
0x1800fce9d  mov     ebx, eax
0x1800fce9f  test    eax, eax
0x1800fcea1  js      loc_1800FCF3C
0x1800fcea7  mov     rdx, [r15+r14+18h]; psz
0x1800fceac  mov     rcx, rdi; pstm
0x1800fceaf  call    cs:__imp_IStream_WriteStr
0x1800fceb6  nop     dword ptr [rax+rax+00h]
0x1800fcebb  mov     ebx, eax
0x1800fcebd  test    eax, eax
0x1800fcebf  js      short loc_1800FCF3C
0x1800fcec1  lea     rdx, [r14+0A8h]
0x1800fcec8  mov     r8d, 1; cb
0x1800fcece  add     rdx, r13; pv
0x1800fced1  mov     rcx, rdi; pstm
0x1800fced4  call    cs:__imp_IStream_Write
0x1800fcedb  nop     dword ptr [rax+rax+00h]
0x1800fcee0  mov     ebx, eax
0x1800fcee2  test    eax, eax
0x1800fcee4  js      short loc_1800FCF3C
0x1800fcee6  lea     rdx, [r14+20h]
0x1800fceea  mov     r8d, 4; cb
0x1800fcef0  add     rdx, r15; pv
0x1800fcef3  mov     rcx, rdi; pstm
0x1800fcef6  call    cs:__imp_IStream_Write
0x1800fcefd  nop     dword ptr [rax+rax+00h]
0x1800fcf02  mov     ebx, eax
0x1800fcf04  test    eax, eax
0x1800fcf06  js      short loc_1800FCF3C
0x1800fcf08  inc     esi
0x1800fcf0a  cmp     esi, [r12]
0x1800fcf0e  jb      loc_1800FCE61
0x1800fcf14  mov     r13, [rbp+arg_50]
0x1800fcf1b  mov     rcx, rdi; pstm
0x1800fcf1e  call    cs:__imp_IStream_Reset
0x1800fcf25  nop     dword ptr [rax+rax+00h]
0x1800fcf2a  mov     ebx, eax
0x1800fcf2c  test    eax, eax
0x1800fcf2e  js      short loc_1800FCF3C
0x1800fcf30  mov     [rbp+pstm], 0
0x1800fcf38  mov     [r13+0], rdi
0x1800fcf3c  lea     rcx, [rbp+pstm]; void *
0x1800fcf40  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800fcf45  mov     eax, ebx
0x1800fcf47  add     rsp, 38h
0x1800fcf4b  pop     r15
0x1800fcf4d  pop     r14
0x1800fcf4f  pop     r13
0x1800fcf51  pop     r12
0x1800fcf53  pop     rdi
0x1800fcf54  pop     rsi
0x1800fcf55  pop     rbx
0x1800fcf56  pop     rbp
0x1800fcf57  retn
```
