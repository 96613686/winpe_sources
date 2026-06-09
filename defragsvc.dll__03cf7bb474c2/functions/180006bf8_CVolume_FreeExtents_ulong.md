# CVolume::_FreeExtents(ulong *)

- ea: `0x180006bf8`
- end: `0x18000702a`
- name: `?_FreeExtents@CVolume@@IEAAJPEAK@Z`
- size: `1074`
- prototype: `__int64 __fastcall(CVolume *__hidden this, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008670`
- `0x180008980`
- `0x180034a60`
- `0x1800630d0`
- `0x180064684`

## callees

- `0x180006400`
- `0x180006bf8`
- `0x180008530`
- `0x180046494`
- `0x18004a92c`

## import_xrefs

- `ntdll!RtlClearBits` at `0x180006e63`
- `ntdll!RtlClearBits` at `0x180006e63`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180006c4d`
- `SXSHARED!SxTracerGetThreadContextRetail` at `0x180006c4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVolume::_FreeExtents(CVolume *this, unsigned int *a2)
{
  int ThreadContextRetail; // eax
  CSxGlobalTracer *v5; // rcx
  int v6; // ebx
  unsigned int v8; // edi
  __int64 v9; // rax
  int v10; // edx
  BOOL v11; // ecx
  __int16 v12; // ax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // r14d
  __int64 v20; // rbx
  unsigned int v21; // edx
  ULONG v22; // r9d
  __int64 v23; // r14
  __int64 v24; // r15
  __int64 *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r14
  __int64 v28; // rsi
  bool v29; // zf
  __int64 v30; // rax
  int v31; // ecx
  __int64 v32; // rdx
  __int16 v33; // ax
  __int128 v34; // [rsp+20h] [rbp-40h] BYREF
  const char *v35; // [rsp+30h] [rbp-30h]
  __int128 v36; // [rsp+38h] [rbp-28h] BYREF
  __int64 v37; // [rsp+48h] [rbp-18h]
  int v38; // [rsp+50h] [rbp-10h]
  unsigned int v39; // [rsp+A8h] [rbp+48h] BYREF

  LODWORD(v34) = 0;
  *(_QWORD *)((char *)&v34 + 4) = 153;
  WORD6(v34) = 1;
  v35 = "CVolume::_FreeExtents";
  v36 = 0;
  v37 = 0;
  v38 = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)&v36 + 8);
  if ( ThreadContextRetail >= 0 )
  {
    *(_QWORD *)&v36 = *(_QWORD *)(*((_QWORD *)&v36 + 1) + 32LL);
    *(_QWORD *)(*((_QWORD *)&v36 + 1) + 32LL) = &v34;
LABEL_3:
    v5 = WPP_GLOBAL_Control;
    goto LABEL_4;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_3;
  }
LABEL_4:
  if ( WORD6(v34) )
  {
    if ( WORD6(v34) == 1 )
    {
      if ( v5 == (CSxGlobalTracer *)&WPP_GLOBAL_Control || (*((_DWORD *)v5 + 7) & 0x20000000) == 0 )
        goto LABEL_8;
      v32 = 12;
LABEL_47:
      WPP_SF_s(*((_QWORD *)v5 + 2), v32, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids, v35);
      goto LABEL_8;
    }
    if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x20000) != 0 )
    {
      v32 = 13;
      goto LABEL_47;
    }
  }
  else if ( v5 != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x8000000) != 0 )
  {
    v32 = 11;
    goto LABEL_47;
  }
LABEL_8:
  if ( !a2 || (v8 = *a2) == 0 )
  {
    v6 = 0;
    WORD2(v34) = 165;
    goto LABEL_10;
  }
  *a2 = 0;
  v9 = *((_QWORD *)this + 19);
  v39 = 0;
  v10 = *(_DWORD *)(v9 + 28);
  if ( !v10 )
  {
    v33 = 175;
LABEL_58:
    v6 = -2147467259;
    WORD3(v34) = v33;
    goto LABEL_10;
  }
  v11 = (v8 & 0xF0000000) == v10;
  v12 = 175;
LABEL_15:
  v6 = 0;
  v13 = 183;
  WORD2(v34) = v12;
  LODWORD(v34) = 0;
  if ( v8 && v11 )
  {
    v39 = v8;
    v14 = *((_QWORD *)this + 19);
    if ( *(_DWORD *)(v14 + 28) )
    {
      if ( (v8 & 0xF0000000) == *(_DWORD *)(v14 + 28) )
      {
        v15 = ((unsigned __int16)v8 - 1) & (unsigned int)-((unsigned __int16)v8 != 0);
        v16 = *(__int64 **)(*(_QWORD *)(v14 + 8) + 8LL * (HIWORD(v8) & 0xFFF));
        if ( v16 )
        {
          if ( (unsigned int)v15 < *(_DWORD *)(v14 + 20) )
          {
            v17 = *(_QWORD *)(v14 + 32) * (unsigned int)v15;
            v18 = *v16;
            LODWORD(v34) = 0;
            WORD2(v34) = 183;
            v8 = *(_DWORD *)(v17 + v18 + 20);
            v19 = *(_DWORD *)(v17 + v18 + 16);
            while ( 1 )
            {
              v20 = *((_QWORD *)this + 19);
              if ( !v19 )
              {
                v6 = CBulkAllocator<_CExtent>::Free(*((_QWORD *)this + 19), &v39, v15, v13, v34, *((_QWORD *)&v34 + 1));
                LODWORD(v34) = v6;
                if ( v6 < 0 )
                {
                  WORD3(v34) = 199;
                  goto LABEL_11;
                }
                WORD2(v34) = 199;
                v30 = *((_QWORD *)this + 19);
                v39 = 0;
                v31 = *(_DWORD *)(v30 + 28);
                if ( !v31 )
                {
                  v33 = 203;
                  goto LABEL_58;
                }
                if ( (v8 & 0xF0000000) != v31 || (v11 = 1, !v8) )
                  v11 = 0;
                v12 = 203;
                goto LABEL_15;
              }
              if ( !*(_DWORD *)(v20 + 28) )
                break;
              v21 = v19 & 0xF0000000;
              if ( (v19 & 0xF0000000) != *(_DWORD *)(v20 + 28)
                || (v22 = (unsigned __int16)v19 != 0 ? (unsigned __int16)v19 - 1 : 0,
                    v23 = HIWORD(v19) & 0xFFF,
                    v24 = (unsigned int)v23,
                    (v25 = *(__int64 **)(*(_QWORD *)(v20 + 8) + 8 * v23)) == 0)
                || v22 >= *(_DWORD *)(v20 + 20) )
              {
                v6 = -2147024809;
                goto LABEL_65;
              }
              v26 = *(_QWORD *)(v20 + 32);
              v27 = *v25;
              LODWORD(v34) = 0;
              WORD2(v34) = 190;
              if ( !*(_DWORD *)(v20 + 28) )
              {
                v6 = -2147467259;
                goto LABEL_62;
              }
              if ( v21 != *(_DWORD *)(v20 + 28)
                || (v28 = *(_QWORD *)(*(_QWORD *)(v20 + 8) + 8 * v24)) == 0
                || v22 >= *(_DWORD *)(v20 + 20) )
              {
                v6 = -2147024809;
LABEL_62:
                WORD3(v34) = 194;
                goto LABEL_10;
              }
              v19 = *(_DWORD *)(v26 * v22 + v27 + 20);
              RtlClearBits((PRTL_BITMAP)(v28 + 16), v22, 1u);
              if ( *(_DWORD *)(v28 + 32) == *(_DWORD *)(v20 + 20) )
                ++*(_DWORD *)(v20 + 24);
              v29 = (*(_DWORD *)(v28 + 32))-- == 1;
              if ( v29 && *(_DWORD *)(v20 + 24) > 1u )
              {
                CoTaskMemFree(*(LPVOID *)(v28 + 8));
                *(_QWORD *)(v28 + 8) = 0;
                CoTaskMemFree(*(LPVOID *)v28);
                *(_QWORD *)v28 = 0;
                CoTaskMemFree((LPVOID)v28);
                *(_QWORD *)(*(_QWORD *)(v20 + 8) + 8 * v24) = 0;
                --*(_DWORD *)(v20 + 24);
              }
              else if ( (unsigned int)v24 < *(_DWORD *)(v20 + 16) )
              {
                *(_DWORD *)(v20 + 16) = v24;
              }
              LODWORD(v34) = 0;
              WORD2(v34) = 194;
            }
            v6 = -2147467259;
LABEL_65:
            WORD3(v34) = 190;
            goto LABEL_10;
          }
        }
      }
      v6 = -2147024809;
    }
    else
    {
      v6 = -2147467259;
    }
    WORD3(v34) = 183;
LABEL_10:
    LODWORD(v34) = v6;
  }
LABEL_11:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v34);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180006bf8  mov     [rsp-38h+arg_0], rbx
0x180006bfd  push    rbp
0x180006bfe  push    rsi
0x180006bff  push    rdi
0x180006c00  push    r12
0x180006c02  push    r13
0x180006c04  push    r14
0x180006c06  push    r15
0x180006c08  mov     rbp, rsp
0x180006c0b  sub     rsp, 60h
0x180006c0f  mov     rbx, rdx
0x180006c12  mov     r13, rcx
0x180006c15  xor     r12d, r12d
0x180006c18  mov     [rbp+var_40], r12d
0x180006c1c  mov     [rbp+var_3C], 99h
0x180006c24  lea     r15d, [r12+1]
0x180006c29  mov     [rbp+var_34], r15w
0x180006c2e  lea     rax, aCvolumeFreeext; "CVolume::_FreeExtents"
0x180006c35  mov     [rbp+var_30], rax
0x180006c39  xorps   xmm0, xmm0
0x180006c3c  movdqu  [rbp+var_28], xmm0
0x180006c41  mov     [rbp+var_18], r12
0x180006c45  mov     [rbp+var_10], r12d
0x180006c49  lea     rcx, [rbp+var_28+8]
0x180006c4d  call    cs:__imp_SxTracerGetThreadContextRetail
0x180006c53  lea     rsi, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x180006c5a  lea     rdi, WPP_GLOBAL_Control
0x180006c61  test    eax, eax
0x180006c63  js      loc_180006F6E
0x180006c69  mov     rcx, qword ptr [rbp+var_28+8]
0x180006c6d  mov     rax, [rcx+20h]
0x180006c71  mov     qword ptr [rbp+var_28], rax
0x180006c75  lea     rax, [rbp+var_40]
0x180006c79  mov     [rcx+20h], rax
0x180006c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c84  movzx   eax, [rbp+var_34]
0x180006c88  test    ax, ax
0x180006c8b  jz      loc_180006FA1
0x180006c91  cmp     ax, r15w
0x180006c95  jnz     loc_180006F30
0x180006c9b  cmp     rcx, rdi
0x180006c9e  jz      short loc_180006CAD
0x180006ca0  test    dword ptr [rcx+1Ch], 20000000h
0x180006ca7  jnz     loc_180006FBE
0x180006cad  test    rbx, rbx
0x180006cb0  jnz     short loc_180006CE4
0x180006cb2  mov     ebx, r12d
0x180006cb5  mov     eax, 0A5h
0x180006cba  mov     word ptr [rbp+var_3C], ax
0x180006cbe  mov     [rbp+var_40], ebx
0x180006cc1  lea     rcx, [rbp+var_40]; this
0x180006cc5  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180006cca  mov     eax, ebx
0x180006ccc  mov     rbx, [rsp+60h+arg_0]
0x180006cd4  add     rsp, 60h
0x180006cd8  pop     r15
0x180006cda  pop     r14
0x180006cdc  pop     r13
0x180006cde  pop     r12
0x180006ce0  pop     rdi
0x180006ce1  pop     rsi
0x180006ce2  pop     rbp
0x180006ce3  retn
0x180006ce4  mov     edi, [rbx]
0x180006ce6  test    edi, edi
0x180006ce8  jz      short loc_180006CB2
0x180006cea  mov     [rbx], r12d
0x180006ced  mov     rax, [r13+98h]
0x180006cf4  mov     [rbp+arg_8], r12d
0x180006cf8  mov     edx, [rax+1Ch]
0x180006cfb  test    edx, edx
0x180006cfd  jz      loc_180006FC5
0x180006d03  mov     eax, edi
0x180006d05  mov     esi, 0F0000000h
0x180006d0a  and     eax, esi
0x180006d0c  mov     ecx, r12d
0x180006d0f  cmp     eax, edx
0x180006d11  setz    cl
0x180006d14  mov     eax, 0AFh
0x180006d19  mov     ebx, r12d
0x180006d1c  mov     r10d, 0C2h
0x180006d22  lea     r11d, [r10-4]
0x180006d26  lea     r9d, [r10-0Bh]
0x180006d2a  mov     word ptr [rbp+var_3C], ax
0x180006d2e  mov     [rbp+var_40], ebx
0x180006d31  test    edi, edi
0x180006d33  jz      short loc_180006CC1
0x180006d35  test    ecx, ecx
0x180006d37  jz      short loc_180006CC1
0x180006d39  mov     [rbp+arg_8], edi
0x180006d3c  mov     rdx, [r13+98h]
0x180006d43  cmp     [rdx+1Ch], r12d
0x180006d47  jbe     loc_18000701A
0x180006d4d  mov     eax, edi
0x180006d4f  and     eax, esi
0x180006d51  cmp     eax, [rdx+1Ch]
0x180006d54  jnz     loc_180007013
0x180006d5a  movzx   eax, di
0x180006d5d  lea     ecx, [rax-1]
0x180006d60  neg     eax
0x180006d62  sbb     r8d, r8d
0x180006d65  and     r8d, ecx
0x180006d68  mov     ecx, edi
0x180006d6a  shr     rcx, 10h
0x180006d6e  and     ecx, 0FFFh
0x180006d74  mov     rax, [rdx+8]
0x180006d78  mov     rax, [rax+rcx*8]
0x180006d7c  test    rax, rax
0x180006d7f  jz      loc_180007013
0x180006d85  cmp     r8d, [rdx+14h]
0x180006d89  jnb     loc_180007013
0x180006d8f  mov     ecx, r8d
0x180006d92  imul    rcx, [rdx+20h]
0x180006d97  mov     rax, [rax]
0x180006d9a  mov     [rbp+var_40], r12d
0x180006d9e  mov     word ptr [rbp+var_3C], r9w
0x180006da3  mov     edi, [rcx+rax+14h]
0x180006da7  mov     r14d, [rcx+rax+10h]
0x180006dac  mov     rbx, [r13+98h]
0x180006db3  test    r14d, r14d
0x180006db6  jz      loc_180006ED7
0x180006dbc  cmp     [rbx+1Ch], r12d
0x180006dc0  jbe     loc_180007004
0x180006dc6  mov     edx, r14d
0x180006dc9  and     edx, esi
0x180006dcb  cmp     edx, [rbx+1Ch]
0x180006dce  jnz     loc_180006FFD
0x180006dd4  movzx   eax, r14w
0x180006dd8  lea     ecx, [rax-1]
0x180006ddb  neg     eax
0x180006ddd  sbb     r9d, r9d
0x180006de0  and     r9d, ecx
0x180006de3  shr     r14d, 10h
0x180006de7  and     r14d, 0FFFh
0x180006dee  mov     r15d, r14d
0x180006df1  mov     rax, [rbx+8]
0x180006df5  mov     rcx, [rax+r14*8]
0x180006df9  test    rcx, rcx
0x180006dfc  jz      loc_180006FFD
0x180006e02  cmp     r9d, [rbx+14h]
0x180006e06  jnb     loc_180006FFD
0x180006e0c  mov     r8, [rbx+20h]
0x180006e10  mov     r14, [rcx]
0x180006e13  mov     [rbp+var_40], r12d
0x180006e17  mov     word ptr [rbp+var_3C], r11w
0x180006e1c  cmp     [rbx+1Ch], r12d
0x180006e20  jbe     loc_180006FEE
0x180006e26  cmp     edx, [rbx+1Ch]
0x180006e29  jnz     loc_180006FE7
0x180006e2f  mov     rax, [rbx+8]
0x180006e33  mov     rsi, [rax+r15*8]
0x180006e37  test    rsi, rsi
0x180006e3a  jz      loc_180006FE7
0x180006e40  cmp     r9d, [rbx+14h]
0x180006e44  jnb     loc_180006FE7
0x180006e4a  mov     eax, r9d
0x180006e4d  imul    rax, r8
0x180006e51  mov     r14d, [rax+r14+14h]
0x180006e56  lea     rcx, [rsi+10h]; BitMapHeader
0x180006e5a  mov     r8d, 1; NumberToClear
0x180006e60  mov     edx, r9d; StartingIndex
0x180006e63  call    cs:__imp_RtlClearBits
0x180006e69  mov     eax, [rbx+14h]
0x180006e6c  cmp     [rsi+20h], eax
0x180006e6f  jnz     short loc_180006E74
0x180006e71  inc     dword ptr [rbx+18h]
0x180006e74  add     dword ptr [rsi+20h], 0FFFFFFFFh
0x180006e78  jz      short loc_180006EA1
0x180006e7a  cmp     r15d, [rbx+10h]
0x180006e7e  jnb     short loc_180006E84
0x180006e80  mov     [rbx+10h], r15d
0x180006e84  mov     [rbp+var_40], r12d
0x180006e88  mov     r10d, 0C2h
0x180006e8e  mov     word ptr [rbp+var_3C], r10w
0x180006e93  mov     esi, 0F0000000h
0x180006e98  lea     r11d, [r10-4]
0x180006e9c  jmp     loc_180006DAC
0x180006ea1  cmp     dword ptr [rbx+18h], 1
0x180006ea5  jbe     short loc_180006E7A
0x180006ea7  mov     rcx, [rsi+8]; pv
0x180006eab  call    cs:__imp_CoTaskMemFree
0x180006eb1  mov     [rsi+8], r12
0x180006eb5  mov     rcx, [rsi]; pv
0x180006eb8  call    cs:__imp_CoTaskMemFree
0x180006ebe  mov     [rsi], r12
0x180006ec1  mov     rcx, rsi; pv
0x180006ec4  call    cs:__imp_CoTaskMemFree
0x180006eca  mov     rax, [rbx+8]
0x180006ece  mov     [rax+r15*8], r12
0x180006ed2  dec     dword ptr [rbx+18h]
0x180006ed5  jmp     short loc_180006E84
0x180006ed7  lea     rdx, [rbp+arg_8]
0x180006edb  mov     rcx, rbx
0x180006ede  call    ?Free@?$CBulkAllocator@U_CExtent@@@@QEAAJPEAK@Z; CBulkAllocator<_CExtent>::Free(ulong *)
0x180006ee3  mov     ebx, eax
0x180006ee5  mov     [rbp+var_40], eax
0x180006ee8  test    eax, eax
0x180006eea  js      short loc_180006F60
0x180006eec  mov     r15d, 0C7h
0x180006ef2  mov     word ptr [rbp+var_3C], r15w
0x180006ef7  mov     rax, [r13+98h]
0x180006efe  mov     [rbp+arg_8], r12d
0x180006f02  mov     ecx, [rax+1Ch]
0x180006f05  test    ecx, ecx
0x180006f07  jz      loc_180006FCC
0x180006f0d  mov     eax, edi
0x180006f0f  and     eax, esi
0x180006f11  cmp     eax, ecx
0x180006f13  jnz     loc_180006FDF
0x180006f19  test    edi, edi
0x180006f1b  mov     ecx, 1
0x180006f20  jz      loc_180006FDF
0x180006f26  mov     eax, 0CBh
0x180006f2b  jmp     loc_180006D19
0x180006f30  cmp     rcx, rdi
0x180006f33  jz      loc_180006CAD
0x180006f39  test    dword ptr [rcx+1Ch], 20000h
0x180006f40  jz      loc_180006CAD
0x180006f46  mov     edx, 0Dh
0x180006f4b  mov     r9, [rbp+var_30]
0x180006f4f  mov     r8, rsi
0x180006f52  mov     rcx, [rcx+10h]
0x180006f56  call    WPP_SF_s
0x180006f5b  jmp     loc_180006CAD
0x180006f60  mov     eax, 0C7h
0x180006f65  mov     word ptr [rbp+var_3C+2], ax
0x180006f69  jmp     loc_180006CC1
0x180006f6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f75  cmp     rcx, rdi
0x180006f78  jz      loc_180006C84
0x180006f7e  test    [rcx+1Ch], r15b
0x180006f82  jz      loc_180006C84
0x180006f88  mov     edx, 0Ah
0x180006f8d  mov     r9d, eax
0x180006f90  mov     r8, rsi
0x180006f93  mov     rcx, [rcx+10h]
0x180006f97  call    WPP_SF_d
0x180006f9c  jmp     loc_180006C7D
0x180006fa1  cmp     rcx, rdi
0x180006fa4  jz      loc_180006CAD
0x180006faa  test    dword ptr [rcx+1Ch], 8000000h
0x180006fb1  jz      loc_180006CAD
0x180006fb7  mov     edx, 0Bh
0x180006fbc  jmp     short loc_180006F4B
0x180006fbe  mov     edx, 0Ch
0x180006fc3  jmp     short loc_180006F4B
0x180006fc5  mov     eax, 0AFh
0x180006fca  jmp     short loc_180006FD1
0x180006fcc  mov     eax, 0CBh
0x180006fd1  mov     ebx, 80004005h
0x180006fd6  mov     word ptr [rbp+var_3C+2], ax
0x180006fda  jmp     loc_180006CBE
0x180006fdf  mov     ecx, r12d
0x180006fe2  jmp     loc_180006F26
0x180006fe7  mov     ebx, 80070057h
0x180006fec  jmp     short loc_180006FF3
0x180006fee  mov     ebx, 80004005h
0x180006ff3  mov     word ptr [rbp+var_3C+2], r10w
0x180006ff8  jmp     loc_180006CBE
0x180006ffd  mov     ebx, 80070057h
0x180007002  jmp     short loc_180007009
0x180007004  mov     ebx, 80004005h
0x180007009  mov     word ptr [rbp+var_3C+2], r11w
0x18000700e  jmp     loc_180006CBE
0x180007013  mov     ebx, 80070057h
0x180007018  jmp     short loc_18000701F
0x18000701a  mov     ebx, 80004005h
0x18000701f  mov     word ptr [rbp+var_3C+2], r9w
0x180007024  jmp     loc_180006CBE
```
