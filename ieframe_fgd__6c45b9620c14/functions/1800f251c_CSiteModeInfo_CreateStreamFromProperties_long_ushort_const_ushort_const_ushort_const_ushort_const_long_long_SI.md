# CSiteModeInfo::_CreateStreamFromProperties(long,ushort const *,ushort const *,ushort const *,ushort const *,long,long,SITEMODE_TASKS *,tagTILE_META_CONTENT *,ulong,IStream * *)

- ea: `0x1800f251c`
- end: `0x1800f2798`
- name: `?_CreateStreamFromProperties@CSiteModeInfo@@CAJJPEBG000JJPEAUSITEMODE_TASKS@@PEAUtagTILE_META_CONTENT@@KPEAPEAUIStream@@@Z`
- size: `636`
- prototype: `static int(int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int, int, struct SITEMODE_TASKS *, struct tagTILE_META_CONTENT *, unsigned int, struct IStream **)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f0f80`

## callees

- `0x18000b9e0`
- `0x180092a2c`
- `0x1800f1518`
- `0x1800f251c`

## import_xrefs

- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800f2557`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x1800f2557`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f2598`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25ae`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25c4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25db`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f26db`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f26f3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f2707`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f2598`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25ae`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25c4`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f25db`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f26db`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f26f3`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_WriteStr` at `0x1800f2707`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2582`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f25fa`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2614`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2631`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f265b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2689`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f26ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2726`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2742`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2582`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f25fa`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2614`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2631`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f265b`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2689`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f26ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2726`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Write` at `0x1800f2742`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800f2764`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Reset` at `0x1800f2764`

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
                      v15 = IStream_Write(v17, &qword_1805D57E8, 4u);
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
0x1800f251c  mov     [rsp-40h+pv], ecx
0x1800f2520  push    rbp
0x1800f2521  push    rbx
0x1800f2522  push    rsi
0x1800f2523  push    rdi
0x1800f2524  push    r12
0x1800f2526  push    r13
0x1800f2528  push    r14
0x1800f252a  push    r15
0x1800f252c  mov     rbp, rsp
0x1800f252f  sub     rsp, 38h
0x1800f2533  mov     r13, [rbp+arg_50]
0x1800f253a  mov     rsi, rdx
0x1800f253d  xor     r12d, r12d
0x1800f2540  xor     edx, edx; cbInit
0x1800f2542  xor     ecx, ecx; pInit
0x1800f2544  mov     [rbp+pstm], r12
0x1800f2548  mov     r15, r9
0x1800f254b  mov     r14, r8
0x1800f254e  mov     [r13+0], r12
0x1800f2552  mov     ebx, 8007000Eh
0x1800f2557  call    cs:__imp_SHCreateMemStream
0x1800f255d  mov     rdx, rax
0x1800f2560  lea     rcx, [rbp+pstm]
0x1800f2564  call    ?Attach@?$CComPtrBase@UIProtectionUtil@@@ATL@@QEAAXPEAUIProtectionUtil@@@Z; ATL::CComPtrBase<IProtectionUtil>::Attach(IProtectionUtil *)
0x1800f2569  mov     rdi, [rbp+pstm]
0x1800f256d  test    rdi, rdi
0x1800f2570  jz      loc_1800F277C
0x1800f2576  lea     r8d, [r12+4]; cb
0x1800f257b  mov     rcx, rdi; pstm
0x1800f257e  lea     rdx, [rbp+pv]; pv
0x1800f2582  call    cs:__imp_IStream_Write
0x1800f2588  mov     ebx, eax
0x1800f258a  test    eax, eax
0x1800f258c  js      loc_1800F277C
0x1800f2592  mov     rdx, rsi; psz
0x1800f2595  mov     rcx, rdi; pstm
0x1800f2598  call    cs:__imp_IStream_WriteStr
0x1800f259e  mov     ebx, eax
0x1800f25a0  test    eax, eax
0x1800f25a2  js      loc_1800F277C
0x1800f25a8  mov     rdx, r14; psz
0x1800f25ab  mov     rcx, rdi; pstm
0x1800f25ae  call    cs:__imp_IStream_WriteStr
0x1800f25b4  mov     ebx, eax
0x1800f25b6  test    eax, eax
0x1800f25b8  js      loc_1800F277C
0x1800f25be  mov     rdx, r15; psz
0x1800f25c1  mov     rcx, rdi; pstm
0x1800f25c4  call    cs:__imp_IStream_WriteStr
0x1800f25ca  mov     ebx, eax
0x1800f25cc  test    eax, eax
0x1800f25ce  js      loc_1800F277C
0x1800f25d4  mov     rdx, [rbp+psz]; psz
0x1800f25d8  mov     rcx, rdi; pstm
0x1800f25db  call    cs:__imp_IStream_WriteStr
0x1800f25e1  mov     ebx, eax
0x1800f25e3  test    eax, eax
0x1800f25e5  js      loc_1800F277C
0x1800f25eb  lea     r15d, [r12+4]
0x1800f25f0  mov     rcx, rdi; pstm
0x1800f25f3  mov     r8d, r15d; cb
0x1800f25f6  lea     rdx, [rbp+arg_28]; pv
0x1800f25fa  call    cs:__imp_IStream_Write
0x1800f2600  mov     ebx, eax
0x1800f2602  test    eax, eax
0x1800f2604  js      loc_1800F277C
0x1800f260a  mov     r8d, r15d; cb
0x1800f260d  lea     rdx, [rbp+arg_30]; pv
0x1800f2611  mov     rcx, rdi; pstm
0x1800f2614  call    cs:__imp_IStream_Write
0x1800f261a  mov     ebx, eax
0x1800f261c  test    eax, eax
0x1800f261e  js      loc_1800F277C
0x1800f2624  mov     r8d, r15d; cb
0x1800f2627  lea     rdx, [rbp+arg_48]; pv
0x1800f262e  mov     rcx, rdi; pstm
0x1800f2631  call    cs:__imp_IStream_Write
0x1800f2637  mov     ebx, eax
0x1800f2639  test    eax, eax
0x1800f263b  js      loc_1800F277C
0x1800f2641  mov     rsi, [rbp+arg_40]
0x1800f2648  lea     r8d, [r12+1]; cb
0x1800f264d  test    rsi, rsi
0x1800f2650  lea     rdx, [rbp+var_18]; pv
0x1800f2654  mov     rcx, rdi; pstm
0x1800f2657  setnz   [rbp+var_18]
0x1800f265b  call    cs:__imp_IStream_Write
0x1800f2661  mov     ebx, eax
0x1800f2663  cmp     [rbp+var_18], r12b
0x1800f2667  jz      short loc_1800F2674
0x1800f2669  mov     rdx, rdi; struct IStream *
0x1800f266c  mov     rcx, rsi; struct tagTILE_META_CONTENT *
0x1800f266f  call    ?SetTileMetaToStream@CSiteModeInfo@@SAJPEAUtagTILE_META_CONTENT@@PEAUIStream@@@Z; CSiteModeInfo::SetTileMetaToStream(tagTILE_META_CONTENT *,IStream *)
0x1800f2674  test    ebx, ebx
0x1800f2676  js      loc_1800F277C
0x1800f267c  mov     r8d, r15d; cb
0x1800f267f  lea     rdx, qword_1805D57E8; pv
0x1800f2686  mov     rcx, rdi; pstm
0x1800f2689  call    cs:__imp_IStream_Write
0x1800f268f  mov     ebx, eax
0x1800f2691  test    eax, eax
0x1800f2693  js      loc_1800F277C
0x1800f2699  mov     r14, [rbp+arg_38]
0x1800f26a0  mov     r8d, r15d; cb
0x1800f26a3  mov     rcx, rdi; pstm
0x1800f26a6  lea     r12, [r14+4]
0x1800f26aa  mov     rdx, r12; pv
0x1800f26ad  call    cs:__imp_IStream_Write
0x1800f26b3  mov     ebx, eax
0x1800f26b5  test    eax, eax
0x1800f26b7  js      loc_1800F277C
0x1800f26bd  xor     esi, esi
0x1800f26bf  cmp     [r12], esi
0x1800f26c3  jbe     loc_1800F2761
0x1800f26c9  mov     r15d, esi
0x1800f26cc  mov     rcx, rdi; pstm
0x1800f26cf  shl     r15, 5
0x1800f26d3  mov     r13d, esi
0x1800f26d6  mov     rdx, [r15+r14+8]; psz
0x1800f26db  call    cs:__imp_IStream_WriteStr
0x1800f26e1  mov     ebx, eax
0x1800f26e3  test    eax, eax
0x1800f26e5  js      loc_1800F277C
0x1800f26eb  mov     rdx, [r15+r14+10h]; psz
0x1800f26f0  mov     rcx, rdi; pstm
0x1800f26f3  call    cs:__imp_IStream_WriteStr
0x1800f26f9  mov     ebx, eax
0x1800f26fb  test    eax, eax
0x1800f26fd  js      short loc_1800F277C
0x1800f26ff  mov     rdx, [r15+r14+18h]; psz
0x1800f2704  mov     rcx, rdi; pstm
0x1800f2707  call    cs:__imp_IStream_WriteStr
0x1800f270d  mov     ebx, eax
0x1800f270f  test    eax, eax
0x1800f2711  js      short loc_1800F277C
0x1800f2713  lea     rdx, [r14+0A8h]
0x1800f271a  mov     r8d, 1; cb
0x1800f2720  add     rdx, r13; pv
0x1800f2723  mov     rcx, rdi; pstm
0x1800f2726  call    cs:__imp_IStream_Write
0x1800f272c  mov     ebx, eax
0x1800f272e  test    eax, eax
0x1800f2730  js      short loc_1800F277C
0x1800f2732  lea     rdx, [r14+20h]
0x1800f2736  mov     r8d, 4; cb
0x1800f273c  add     rdx, r15; pv
0x1800f273f  mov     rcx, rdi; pstm
0x1800f2742  call    cs:__imp_IStream_Write
0x1800f2748  mov     ebx, eax
0x1800f274a  test    eax, eax
0x1800f274c  js      short loc_1800F277C
0x1800f274e  inc     esi
0x1800f2750  cmp     esi, [r12]
0x1800f2754  jb      loc_1800F26C9
0x1800f275a  mov     r13, [rbp+arg_50]
0x1800f2761  mov     rcx, rdi; pstm
0x1800f2764  call    cs:__imp_IStream_Reset
0x1800f276a  mov     ebx, eax
0x1800f276c  test    eax, eax
0x1800f276e  js      short loc_1800F277C
0x1800f2770  mov     [rbp+pstm], 0
0x1800f2778  mov     [r13+0], rdi
0x1800f277c  lea     rcx, [rbp+pstm]; void *
0x1800f2780  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800f2785  mov     eax, ebx
0x1800f2787  add     rsp, 38h
0x1800f278b  pop     r15
0x1800f278d  pop     r14
0x1800f278f  pop     r13
0x1800f2791  pop     r12
0x1800f2793  pop     rdi
0x1800f2794  pop     rsi
0x1800f2795  pop     rbx
0x1800f2796  pop     rbp
0x1800f2797  retn
```
