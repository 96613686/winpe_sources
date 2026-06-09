# GetEventProperty(_EVENT_RECORD *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,uchar)

- ea: `0x18001be60`
- end: `0x18001c21d`
- name: `?GetEventProperty@@YAKPEAU_EVENT_RECORD@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@E@Z`
- size: `957`
- prototype: `__int64 __fastcall(PEVENT_RECORD pEvent)`
- caller_count: `39`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x180009078`
- `0x18000abe4`
- `0x18000b07c`
- `0x18001808c`
- `0x180019d60`
- `0x18001c230`
- `0x18001cf70`
- `0x18001db80`
- `0x1800205ec`
- `0x1800218a0`
- `0x18002367c`
- `0x18002394c`
- `0x180023cac`
- `0x1800249a0`
- `0x18002647c`
- `0x1800276f0`
- `0x180028554`
- `0x18002e9b4`
- `0x180031000`
- `0x180031b10`
- `0x180034ed0`
- `0x18003a404`
- `0x18003b404`
- `0x18003d97c`
- `0x18004eb40`
- `0x18004ee80`
- `0x18005c2f8`
- `0x18005c860`
- `0x180060334`
- `0x1800631f4`
- `0x1800632f8`
- `0x1800690d0`
- `0x18006b3ec`
- `0x18006b600`
- `0x180082a74`
- `0x180082ba8`
- `0x180082de4`
- `0x180086d94`
- `0x18008954c`

## callees

- `0x180004e20`
- `0x18001be60`
- `0x18001ca80`
- `0x18001ce44`
- `0x18001d3cc`
- `0x180037380`
- `0x18003bb60`
- `0x18004ca90`
- `0x18004cab4`
- `0x18004d8fc`
- `0x18004dea8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c157`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c052`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c0c6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c052`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001c0c6`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001becf`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetPropertySize` at `0x18001becf`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001bf69`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c026`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001bf69`
- `api-ms-win-eventing-tdh-l1-1-0!TdhGetProperty` at `0x18001c026`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetEventProperty(PEVENT_RECORD pEvent, __int64 a2, __int64 a3, char a4)
{
  ULONGLONG v7; // rdx
  TDHSTATUS PropertySize; // ebx
  unsigned __int64 v9; // rbx
  BYTE *v10; // rdi
  unsigned __int64 v11; // rcx
  void *v12; // rcx
  unsigned int v14; // eax
  BYTE *v15; // r14
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  PBYTE v20; // rcx
  size_t v21; // rdi
  size_t v22; // rbx
  _BYTE v23[8]; // [rsp+40h] [rbp-69h] BYREF
  PBYTE pBuffer; // [rsp+48h] [rbp-61h] BYREF
  void *v25; // [rsp+50h] [rbp-59h]
  __int64 v26; // [rsp+58h] [rbp-51h]
  ULONG pPropertySize; // [rsp+60h] [rbp-49h] BYREF
  PBYTE v28[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v29; // [rsp+78h] [rbp-31h]
  unsigned __int64 v30; // [rsp+80h] [rbp-29h] BYREF
  void *v31; // [rsp+88h] [rbp-21h] BYREF
  PROPERTY_DATA_DESCRIPTOR pPropertyData; // [rsp+90h] [rbp-19h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-9h] BYREF
  __int128 v34; // [rsp+B0h] [rbp+7h]

  pPropertySize = 0;
  pPropertyData.Reserved = 0;
  std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(&pBuffer);
  pPropertyData.ArrayIndex = -1;
  pPropertyData.PropertyName = v7;
  PropertySize = TdhGetPropertySize(pEvent, 0, 0, 1u, &pPropertyData, &pPropertySize);
  if ( !PropertySize )
  {
    if ( !pPropertySize )
      goto LABEL_12;
    if ( !a4 )
    {
      v9 = (unsigned __int64)pPropertySize >> 1;
      v10 = (BYTE *)v25;
      v11 = ((_BYTE *)v25 - pBuffer) >> 1;
      if ( v9 < v11 )
      {
        v10 = &pBuffer[2 * v9];
      }
      else
      {
        if ( v9 <= v11 )
          goto LABEL_10;
        if ( v9 > (v26 - (__int64)pBuffer) >> 1 )
        {
          std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pBuffer, v9);
          v10 = (BYTE *)v25;
          goto LABEL_10;
        }
        v22 = 2 * (v9 - v11);
        memset_0(v25, 0, v22);
        v10 += v22;
      }
      v25 = v10;
LABEL_10:
      PropertySize = TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, 2 * ((v10 - pBuffer) >> 1), pBuffer);
      if ( PropertySize )
      {
LABEL_11:
        std::wstring::_Assign<unsigned short>(a3, &qword_18009CA18, 0);
        goto LABEL_12;
      }
      goto LABEL_26;
    }
    v23[0] = 0;
    *(_OWORD *)v28 = 0;
    v29 = 0;
    std::vector<char>::_Construct_n<char const &>(v28, pPropertySize + 1, v23);
    PropertySize = TdhGetProperty(pEvent, 0, 0, 1u, &pPropertyData, LODWORD(v28[1]) - LODWORD(v28[0]), v28[0]);
    if ( PropertySize )
    {
      if ( v28[0] )
        std::_Deallocate<16>(v28[0], v29 - (unsigned __int64)v28[0]);
      goto LABEL_12;
    }
    v14 = MultiByteToWideChar(0, 1u, (LPCCH)v28[0], LODWORD(v28[1]) - LODWORD(v28[0]), 0, 0);
    if ( !v14 )
    {
LABEL_32:
      PropertySize = GetLastError();
      v20 = v28[0];
      if ( !v28[0] )
        goto LABEL_35;
      v19 = v29 - (unsigned __int64)v28[0];
      goto LABEL_34;
    }
    v15 = (BYTE *)v25;
    v16 = ((_BYTE *)v25 - pBuffer) >> 1;
    if ( v14 < v16 )
    {
      v15 = &pBuffer[2 * v14];
    }
    else
    {
      if ( v14 <= v16 )
        goto LABEL_23;
      if ( v14 > (unsigned __int64)((v26 - (__int64)pBuffer) >> 1) )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pBuffer, v14);
        v15 = (BYTE *)v25;
        goto LABEL_23;
      }
      v21 = 2 * (v14 - v16);
      memset_0(v25, 0, v21);
      v15 += v21;
    }
    v25 = v15;
LABEL_23:
    if ( MultiByteToWideChar(
           0,
           1u,
           (LPCCH)v28[0],
           LODWORD(v28[1]) - LODWORD(v28[0]),
           (LPWSTR)pBuffer,
           (v15 - pBuffer) >> 1) )
    {
      if ( v28[0] )
        std::_Deallocate<16>(v28[0], v29 - (unsigned __int64)v28[0]);
LABEL_26:
      v33 = 0;
      v34 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v33, pBuffer, ((_BYTE *)v25 - pBuffer) >> 1);
      if ( (__int128 *)a3 == &v33 )
      {
        v18 = *((_QWORD *)&v34 + 1);
      }
      else
      {
        v17 = *(_QWORD *)(a3 + 24);
        if ( v17 > 7 )
          std::_Deallocate<16>(*(void **)a3, 2 * v17 + 2);
        *(_OWORD *)a3 = v33;
        *(_OWORD *)(a3 + 16) = v34;
        v18 = 7;
        LOWORD(v33) = 0;
      }
      if ( v18 <= 7 )
      {
LABEL_35:
        if ( !PropertySize )
          goto LABEL_12;
        goto LABEL_36;
      }
      v19 = 2 * v18 + 2;
      v20 = (PBYTE)v33;
LABEL_34:
      std::_Deallocate<16>(v20, v19);
      goto LABEL_35;
    }
    goto LABEL_32;
  }
LABEL_36:
  if ( !a4 )
    goto LABEL_11;
LABEL_12:
  v12 = pBuffer;
  if ( pBuffer )
  {
    v30 = 2 * ((v26 - (__int64)pBuffer) >> 1);
    v31 = pBuffer;
    if ( v30 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v31, &v30);
      v12 = v31;
    }
    operator delete(v12);
  }
  return PropertySize;
}

```

## disassembly

```asm
0x18001be60  push    rbp
0x18001be62  push    rbx
0x18001be63  push    rsi
0x18001be64  push    rdi
0x18001be65  push    r12
0x18001be67  push    r14
0x18001be69  push    r15
0x18001be6b  lea     rbp, [rsp-27h]
0x18001be70  sub     rsp, 0D0h
0x18001be77  mov     rax, cs:__security_cookie
0x18001be7e  xor     rax, rsp
0x18001be81  mov     [rbp+57h+var_40], rax
0x18001be85  movzx   r15d, r9b
0x18001be89  mov     rsi, r8
0x18001be8c  mov     r14, rcx
0x18001be8f  xor     r12d, r12d
0x18001be92  mov     [rbp+57h+var_A0], r12d
0x18001be96  mov     [rbp+57h+var_70.Reserved], r12d
0x18001be9a  lea     rcx, [rbp+57h+var_B8]; void *
0x18001be9e  call    ??0?$vector@VServicePowerRequest@@V?$allocator@VServicePowerRequest@@@std@@@std@@QEAA@XZ; std::vector<ServicePowerRequest>::vector<ServicePowerRequest>(void)
0x18001bea3  nop
0x18001bea4  mov     [rbp+57h+var_70.ArrayIndex], 0FFFFFFFFh
0x18001beab  mov     [rbp+57h+var_70.PropertyName], rdx
0x18001beaf  lea     rax, [rbp+57h+var_A0]
0x18001beb3  mov     [rsp+100h+pPropertySize], rax; pPropertySize
0x18001beb8  lea     rax, [rbp+57h+var_70]
0x18001bebc  mov     [rsp+100h+pPropertyData], rax; pPropertyData
0x18001bec1  mov     r9d, 1; PropertyDataCount
0x18001bec7  xor     r8d, r8d; pTdhContext
0x18001beca  xor     edx, edx; TdhContextCount
0x18001becc  mov     rcx, r14; pEvent
0x18001becf  call    cs:__imp_TdhGetPropertySize
0x18001bed5  mov     ebx, eax
0x18001bed7  test    eax, eax
0x18001bed9  jnz     loc_18001C17C
0x18001bedf  mov     eax, [rbp+57h+var_A0]
0x18001bee2  test    eax, eax
0x18001bee4  jz      loc_18001BF8C
0x18001beea  test    r15b, r15b
0x18001beed  jnz     loc_18001BFDC
0x18001bef3  mov     ebx, eax
0x18001bef5  shr     rbx, 1
0x18001bef8  mov     rdx, [rbp+57h+var_B8]
0x18001befc  mov     rdi, [rbp+57h+var_B0]
0x18001bf00  mov     rcx, rdi
0x18001bf03  sub     rcx, rdx
0x18001bf06  sar     rcx, 1
0x18001bf09  cmp     rbx, rcx
0x18001bf0c  jb      short loc_18001BF35
0x18001bf0e  jbe     short loc_18001BF3D
0x18001bf10  mov     rax, [rbp+57h+var_A8]
0x18001bf14  sub     rax, rdx
0x18001bf17  sar     rax, 1
0x18001bf1a  cmp     rbx, rax
0x18001bf1d  jbe     loc_18001C1D3
0x18001bf23  mov     rdx, rbx
0x18001bf26  lea     rcx, [rbp+57h+var_B8]
0x18001bf2a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001bf2f  mov     rdi, [rbp+57h+var_B0]
0x18001bf33  jmp     short loc_18001BF3D
0x18001bf35  lea     rdi, [rdx+rbx*2]
0x18001bf39  mov     [rbp+57h+var_B0], rdi
0x18001bf3d  mov     rax, [rbp+57h+var_B8]
0x18001bf41  sub     rdi, rax
0x18001bf44  sar     rdi, 1
0x18001bf47  add     edi, edi
0x18001bf49  mov     [rsp+100h+pBuffer], rax; pBuffer
0x18001bf4e  mov     dword ptr [rsp+100h+pPropertySize], edi; BufferSize
0x18001bf52  lea     rax, [rbp+57h+var_70]
0x18001bf56  mov     [rsp+100h+pPropertyData], rax; pPropertyData
0x18001bf5b  mov     r9d, 1; PropertyDataCount
0x18001bf61  xor     r8d, r8d; pTdhContext
0x18001bf64  xor     edx, edx; TdhContextCount
0x18001bf66  mov     rcx, r14; pEvent
0x18001bf69  call    cs:__imp_TdhGetProperty
0x18001bf6f  mov     ebx, eax
0x18001bf71  test    eax, eax
0x18001bf73  jz      loc_18001C0E9
0x18001bf79  xor     r8d, r8d
0x18001bf7c  lea     rdx, qword_18009CA18
0x18001bf83  mov     rcx, rsi
0x18001bf86  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001bf8b  nop
0x18001bf8c  mov     rcx, [rbp+57h+var_B8]; void *
0x18001bf90  test    rcx, rcx
0x18001bf93  jz      short loc_18001BFBC
0x18001bf95  mov     rdx, [rbp+57h+var_A8]
0x18001bf99  sub     rdx, rcx
0x18001bf9c  sar     rdx, 1
0x18001bf9f  add     rdx, rdx; unsigned __int64
0x18001bfa2  mov     [rbp+57h+var_80], rdx
0x18001bfa6  mov     [rbp+57h+var_78], rcx
0x18001bfaa  cmp     rdx, 1000h
0x18001bfb1  jnb     loc_18001C203
0x18001bfb7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001bfbc  mov     eax, ebx
0x18001bfbe  mov     rcx, [rbp+57h+var_40]
0x18001bfc2  xor     rcx, rsp; StackCookie
0x18001bfc5  call    __security_check_cookie
0x18001bfca  add     rsp, 0D0h
0x18001bfd1  pop     r15
0x18001bfd3  pop     r14
0x18001bfd5  pop     r12
0x18001bfd7  pop     rdi
0x18001bfd8  pop     rsi
0x18001bfd9  pop     rbx
0x18001bfda  pop     rbp
0x18001bfdb  retn
0x18001bfdc  mov     [rbp+57h+var_C0], 0
0x18001bfe0  xorps   xmm0, xmm0
0x18001bfe3  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18001bfe8  mov     [rbp+57h+var_88], r12
0x18001bfec  lea     edx, [rax+1]
0x18001bfef  lea     r8, [rbp+57h+var_C0]
0x18001bff3  lea     rcx, [rbp+57h+var_98]
0x18001bff7  call    ??$_Construct_n@AEBD@?$vector@DV?$allocator@D@std@@@std@@AEAAX_KAEBD@Z; std::vector<char>::_Construct_n<char const &>(unsigned __int64,char const &)
0x18001bffc  nop
0x18001bffd  mov     rdx, [rbp+57h+var_98]
0x18001c001  mov     eax, dword ptr [rbp+57h+var_98+8]
0x18001c004  sub     eax, edx
0x18001c006  mov     [rsp+100h+pBuffer], rdx; pBuffer
0x18001c00b  mov     dword ptr [rsp+100h+pPropertySize], eax; BufferSize
0x18001c00f  lea     rax, [rbp+57h+var_70]
0x18001c013  mov     [rsp+100h+pPropertyData], rax; pPropertyData
0x18001c018  mov     r9d, 1; PropertyDataCount
0x18001c01e  xor     r8d, r8d; pTdhContext
0x18001c021  xor     edx, edx; TdhContextCount
0x18001c023  mov     rcx, r14; pEvent
0x18001c026  call    cs:__imp_TdhGetProperty
0x18001c02c  mov     ebx, eax
0x18001c02e  test    eax, eax
0x18001c030  jnz     loc_18001C18A
0x18001c036  mov     r8, [rbp+57h+var_98]; lpMultiByteStr
0x18001c03a  mov     r9d, dword ptr [rbp+57h+var_98+8]
0x18001c03e  sub     r9d, r8d; cbMultiByte
0x18001c041  mov     dword ptr [rsp+100h+pPropertySize], r12d; cchWideChar
0x18001c046  mov     [rsp+100h+pPropertyData], r12; lpWideCharStr
0x18001c04b  mov     edx, 1; dwFlags
0x18001c050  xor     ecx, ecx; CodePage
0x18001c052  call    cs:__imp_MultiByteToWideChar
0x18001c058  test    eax, eax
0x18001c05a  jz      loc_18001C157
0x18001c060  mov     rdx, [rbp+57h+var_B8]
0x18001c064  mov     r14, [rbp+57h+var_B0]
0x18001c068  mov     rcx, r14
0x18001c06b  sub     rcx, rdx
0x18001c06e  sar     rcx, 1
0x18001c071  mov     edi, eax
0x18001c073  cmp     rdi, rcx
0x18001c076  jb      loc_18001C1A8
0x18001c07c  jbe     short loc_18001C0A0
0x18001c07e  mov     rax, [rbp+57h+var_A8]
0x18001c082  sub     rax, rdx
0x18001c085  sar     rax, 1
0x18001c088  cmp     rdi, rax
0x18001c08b  jbe     loc_18001C1BB
0x18001c091  mov     edx, edi
0x18001c093  lea     rcx, [rbp+57h+var_B8]
0x18001c097  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@GV?$allocator@G@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<ushort>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18001c09c  mov     r14, [rbp+57h+var_B0]
0x18001c0a0  mov     rax, [rbp+57h+var_B8]
0x18001c0a4  mov     r8, [rbp+57h+var_98]; lpMultiByteStr
0x18001c0a8  sub     r14, rax
0x18001c0ab  sar     r14, 1
0x18001c0ae  mov     r9d, dword ptr [rbp+57h+var_98+8]
0x18001c0b2  sub     r9d, r8d; cbMultiByte
0x18001c0b5  mov     dword ptr [rsp+100h+pPropertySize], r14d; cchWideChar
0x18001c0ba  mov     [rsp+100h+pPropertyData], rax; lpWideCharStr
0x18001c0bf  mov     edx, 1; dwFlags
0x18001c0c4  xor     ecx, ecx; CodePage
0x18001c0c6  call    cs:__imp_MultiByteToWideChar
0x18001c0cc  test    eax, eax
0x18001c0ce  jz      loc_18001C157
0x18001c0d4  mov     rcx, [rbp+57h+var_98]
0x18001c0d8  test    rcx, rcx
0x18001c0db  jz      short loc_18001C0E9
0x18001c0dd  mov     rdx, [rbp+57h+var_88]
0x18001c0e1  sub     rdx, rcx
0x18001c0e4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c0e9  mov     rdx, [rbp+57h+var_B8]
0x18001c0ed  xorps   xmm0, xmm0
0x18001c0f0  movups  [rbp+57h+var_60], xmm0
0x18001c0f4  xorps   xmm1, xmm1
0x18001c0f7  movdqu  [rbp+57h+var_50], xmm1
0x18001c0fc  mov     r8, [rbp+57h+var_B0]
0x18001c100  sub     r8, rdx
0x18001c103  sar     r8, 1
0x18001c106  lea     rcx, [rbp+57h+var_60]
0x18001c10a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c10f  lea     rax, [rbp+57h+var_60]
0x18001c113  cmp     rsi, rax
0x18001c116  jz      loc_18001C1B5
0x18001c11c  mov     rdx, [rsi+18h]
0x18001c120  cmp     rdx, 7
0x18001c124  ja      loc_18001C1EE
0x18001c12a  movups  xmm0, [rbp+57h+var_60]
0x18001c12e  movups  xmmword ptr [rsi], xmm0
0x18001c131  movups  xmm1, [rbp+57h+var_50]
0x18001c135  movups  xmmword ptr [rsi+10h], xmm1
0x18001c139  mov     edx, 7
0x18001c13e  mov     word ptr [rbp+57h+var_60], r12w
0x18001c143  cmp     rdx, 7
0x18001c147  jbe     short loc_18001C174
0x18001c149  lea     rdx, ds:2[rdx*2]
0x18001c151  mov     rcx, qword ptr [rbp+57h+var_60]
0x18001c155  jmp     short loc_18001C16F
0x18001c157  call    cs:__imp_GetLastError
0x18001c15d  mov     ebx, eax
0x18001c15f  mov     rcx, [rbp+57h+var_98]
0x18001c163  test    rcx, rcx
0x18001c166  jz      short loc_18001C174
0x18001c168  mov     rdx, [rbp+57h+var_88]
0x18001c16c  sub     rdx, rcx
0x18001c16f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c174  test    ebx, ebx
0x18001c176  jz      loc_18001BF8C
0x18001c17c  test    r15b, r15b
0x18001c17f  jnz     loc_18001BF8C
0x18001c185  jmp     loc_18001BF79
0x18001c18a  mov     rcx, [rbp+57h+var_98]
0x18001c18e  test    rcx, rcx
0x18001c191  jz      loc_18001BF8C
0x18001c197  mov     rdx, [rbp+57h+var_88]
0x18001c19b  sub     rdx, rcx
0x18001c19e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c1a3  jmp     loc_18001BF8C
0x18001c1a8  lea     r14, [rdx+rdi*2]
0x18001c1ac  mov     [rbp+57h+var_B0], r14
0x18001c1b0  jmp     loc_18001C0A0
0x18001c1b5  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18001c1b9  jmp     short loc_18001C143
0x18001c1bb  sub     rdi, rcx
0x18001c1be  add     rdi, rdi
0x18001c1c1  mov     r8, rdi; Size
0x18001c1c4  xor     edx, edx; Val
0x18001c1c6  mov     rcx, r14; void *
0x18001c1c9  call    memset_0
0x18001c1ce  add     r14, rdi
0x18001c1d1  jmp     short loc_18001C1AC
0x18001c1d3  sub     rbx, rcx
0x18001c1d6  add     rbx, rbx
0x18001c1d9  mov     r8, rbx; Size
0x18001c1dc  xor     edx, edx; Val
0x18001c1de  mov     rcx, rdi; void *
0x18001c1e1  call    memset_0
0x18001c1e6  add     rdi, rbx
0x18001c1e9  jmp     loc_18001BF39
0x18001c1ee  lea     rdx, ds:2[rdx*2]
0x18001c1f6  mov     rcx, [rsi]
0x18001c1f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c1fe  jmp     loc_18001C12A
0x18001c203  lea     rdx, [rbp+57h+var_80]; unsigned __int64 *
0x18001c207  lea     rcx, [rbp+57h+var_78]; void **
0x18001c20b  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001c210  mov     rdx, [rbp+57h+var_80]
0x18001c214  mov     rcx, [rbp+57h+var_78]
0x18001c218  jmp     loc_18001BFB7
```
